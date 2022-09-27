## Problem description
Describe here what problem you are solving. If you are adding new functionality, describe why the new functionality is added. Often this is (or should be) the same description is in the Linear ticket.
Please don't just link to the Linear ticket here, don't force the reviewer to jump back and forth between GH and Linear.

Example:
> Support for SomeExchange is quite broken. Either the imports fail outright (ca. 25% of the cases) or when an unsupported transaction is encountered it is silently ignored, i.e. there is no indication to the user that certain transactions were not imported.

## Background
You've just put a lot of effort into understanding the underlying code before making a change. Share these leanings with
the reviewer. Assume they don’t know the code very well.

Example:
> The CSV import logic for BlockFi is pretty straight-forward:
>- transfers with a positive amount are credits, with a negative amount debits
>- trades are transactions of type ["Trade", "Ach Trade"] that share the same datetime

## Solution
Describe in a few sentences the approach you took to address the problem.

Example:
> The CSV import logic generalizes well so I simply added the previously unsupported transaction types to the list of transactions. The outright import failures were caused by transactions with empty dates, so I added some code to ignore those. Finally, for any transaction we ignored I added logging in place so that in the future we have a good idea what transactions fail to import, without having to download and analyze the user's CSVs.

## Future work
While addressing the problem you might have noticed other problems which are orthogonal. If that's the case, summarise the issues here and consider creating corresponding tickets in Linear.

Example:
> At the UX level there is no indication for transactions that are ignored. This is something we should address. I created ticket XXX.

## Required for SOC2 compliance

- [ ] Security impact of change has been considered
- [ ] Code follows company security practices and guidelines
- [ ] Automated tests covering modified code pass
