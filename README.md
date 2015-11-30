```perl
# NAME

Method::Signatures - method and function declarations with signatures and no source filter

# VERSION

20141021

# SYNOPSIS

        package Foo;
    
        use Method::Signatures;
    
        method new (%args) {
            return bless {%args}, $self;
        }
    
        # Can also get type checking if you like:
    
        method set (Str $key, Int $val) {
            return $self->{$key} = $val;        # now you know $val is always an integer
        }

# DESCRIPTION

Provides two new keywords, func and method, so that you can write subroutines with signatures instead of having to spell out my ```$self = shift; my($thing) = @_

func is like sub but takes a signature where the prototype would normally go. This takes the place of my($foo, $bar) = @_ and does a whole lot more.

method is like func but specifically for making methods. It will automatically provide the invocant as $self (by default). No more my $self = shift.

# INSTALLATION

This module sources are hosted on github https://github.com/evalEmpire/method-signatures.git and uses Module::Build to generate the distribution. It can be istalled:

- directly

       cpanm git://github.com/evalEmpire/method-signatures.git

- from CPAN

       cpan Method::Signatures
       cpanm Method::Signatures

- maualy cloninig the repository:

       git clone https://github.com/evalEmpire/method-signatures.git
       cd method-signatures
       perl Build.PL
       ./Build install 

# REQUIREMENTS

    This distribution requires Perl v5.8.1.

    This distribution requires the following modules:

      * Any::Moose (version 0.11)

      * Const::Fast (version 0.006)

      * Devel::Declare (version 0.006002)

      * Devel::Declare::MethodInstaller::Simple (version 0.006002)

      * Lexical::SealRequireHints (version 0.008)

      * Module::Build (version 0.26)

      * Mouse (version 0.64)

      * PPI (version 1.203)

      * Sub::Name (version 0.03)

      * Test::Exception (version 0.29)

      * Test::Warn (version 0.10)

    This distribution recommends the following modules:

      * Data::Alias (version 1.08)

      * Moose (version 0.96)

