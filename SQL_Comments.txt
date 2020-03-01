select Artist.Name,sum(invoiceline.quantity*invoiceline.unitprice) as Amount_Spent from Artist
join Album on Artist.ArtistId=Album.ArtistId
join Track on Album.AlbumId=Track.AlbumId
join InvoiceLine on Track.TrackId=InvoiceLine.TrackId
join Invoice on InvoiceLine.InvoiceId=Invoice.InvoiceId
GROUP by Artist.Name
order by Amount_Spent DESC