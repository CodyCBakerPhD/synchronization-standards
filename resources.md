# Resources

Both NWB and BIDS generally expect all temporal data within a 'session' to be aligned to the same common time basis.

Details of how that alignment is performed are often left out, or assumed to be included in the official publication (usually methods section).



### DICOM

DICOM Synchronization module: https://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.7.4.2.html#sect_C.7.4.2.1.1

Note that the important `Synchronization Channel` is required if referenced by a [waveform](https://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.10.8.html)

It also refers to the IEEE 1588 (2019) Precision Time Protocol as the finest grain method: https://standards.ieee.org/ieee/1588/6825/#:~:text=This%20standard%20defines%20a%20network,access%20pending%20leap%2Dsecond%20changes., https://ieeexplore.ieee.org/document/9120376 (500 page PDF)



### BIDS

`SimultaneousRecording` and `SimultaneousRecordingWith` discussion: https://github.com/bids-standard/bids-specification/issues/86



### How another format deals with time bases

EAF ([ELAN](https://archive.mpi.nl/tla/elan) Annotation Format): https://standards.clarin.eu/sis/views/view-spec.xq?id=SpecEAF#:~:text=The%20abbreviation%20EAF%20stands%20for,and%20video%20recordings%20in%20EAF.

EAF documentation (2014): https://www.mpi.nl/tools/elan/EAF_Annotation_Format_2.8_and_ELAN.pdf

EAF XML Schema (2014): https://www.mpi.nl/tools/elan/EAFv2.8.xsd

Example `.eaf` file: https://github.com/aclew/Highvol_templates/blob/master/0270.eaf

None of which explains what the critical value of `TIME_VALUE` is relative to (presumably the required `date` timestamp from the header) nor other explanations of temporal precision, especially across `TIME_SLOT` coming from multiple microphones or cameras.


