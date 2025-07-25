---
title: QCSchema JSON
---

## Specification

@Note [Reference](https://molssi-qc-schema.readthedocs.io)

JSON files are identified by the extension ``json`` and parsed following the ``qcschema_molecule`` or ``qcschema_input`` format.
The ``molecule`` entry from a ``qcschema_input`` will be extracted, but there is no guarantee that the input information will be used by the program.


## Example

Caffeine molecule in ``qcschema_molecule`` format.


```json
{
  "schema_version": 2,
  "schema_name": "qcschema_molecule",
  "provenance": {
    "creator": "mctc-lib",
    "version": "0.2.3",
    "routine": "mctc_io_write_qcschema::write_qcschema"
  },
  "symbols": [
    "C", "N", "C", "N", "C", "C", "C", "O", "N", "C", "O", "N",
    "C", "C", "H", "H", "H", "H", "H", "H", "H", "H", "H", "H"
  ],
  "geometry": [
     2.0280536328008760E+00, 9.2407587256767454E-02,-1.4305223630546618E-01,
     4.7502035191684326E+00, 2.3810543955731494E-02,-1.4324120887654343E-01,
     6.3343605825088858E+00, 2.0709504064354083E+00,-1.4229634602115726E-01,
     8.7286430580574415E+00, 1.3800666865770403E+00,-1.4267429116331171E-01,
     8.6532430021976250E+00,-1.1931728137816557E+00,-1.4229634602115726E-01,
     6.2385514889727283E+00,-2.0836115686975827E+00,-1.4210737345008001E-01,
     5.6327054260991156E+00,-4.6995588701197342E+00,-1.3946175745499875E-01,
     3.4493163398727531E+00,-5.4809604515240968E+00,-1.4324120887654343E-01,
     7.7750874644017181E+00,-6.2442206661050452E+00,-1.3114696432760045E-01,
     1.0302217657417570E+01,-5.3974345751079591E+00,-1.3681614145991747E-01,
     1.2074024483837716E+01,-6.9158291837135346E+00,-1.3662716888884024E-01,
     1.0700382864677302E+01,-2.7907469296685923E+00,-1.4154045573684831E-01,
     1.3246032369658721E+01,-1.7697281281382971E+00,-1.4210737345008001E-01,
     7.4088586216540389E+00,-8.9590006222005893E+00,-1.1640710378357619E-01,
     1.3870586717068980E+00, 2.0558326007492296E+00,-1.4172942830792554E-01,
     1.3462405963542154E+00,-8.6360464982295970E-01, 1.5560001502499454E+00,
     1.3462405963542154E+00,-8.6133697897003281E-01,-1.8434274308584184E+00,
     5.6559490523416152E+00, 4.0016831651315083E+00,-1.4135148316577109E-01,
     1.4674287061860456E+01,-3.2622334945062916E+00,-1.4343018144762065E-01,
     1.3508893216027154E+01,-6.0811373372653921E-01, 1.5490081651200875E+00,
     1.3507759380600691E+01,-6.0622400801576681E-01,-1.8320890765937843E+00,
     5.4140641613627567E+00,-9.4924701903516215E+00,-1.1017100893802745E-01,
     8.3191394965330758E+00,-9.7494728870166600E+00, 1.5654487788038070E+00,
     8.3151710725404531E+00,-9.7685591166954602E+00,-1.7910820286700244E+00
  ],
  "molecular_charge": 0,
  "connectivity": [
    [ 0, 1, 1],
    [ 1, 2, 4],
    [ 2, 3, 4],
    [ 3, 4, 4],
    [ 1, 5, 1],
    [ 4, 5, 4],
    [ 5, 6, 1],
    [ 6, 7, 2],
    [ 6, 8, 1],
    [ 8, 9, 1],
    [ 9,10, 2],
    [ 4,11, 1],
    [ 9,11, 1],
    [11,12, 1],
    [ 8,13, 1],
    [ 0,14, 1],
    [ 0,15, 1],
    [ 0,16, 1],
    [ 2,17, 1],
    [12,18, 1],
    [12,19, 1],
    [12,20, 1],
    [13,21, 1],
    [13,22, 1],
    [13,23, 1]
  ]
}
```

## Extensions

The reader supports the following extensions:

- Periodic boundary conditions are specified by providing the lattice vectors in Bohr
  as extras to the molecule in periodic.lattice as flattened array.

```json
"extras": {
  "periodic": {
    "lattice": [
       5.5900366437622173, 0.0000000000000000, 0.0000000000000000,
       0.0000000000000000, 8.6808915904526547, 0.0000000000000000,
       0.0000000000000000, 0.0000000000000000, 8.6808915904526547
    ]
  }
}
```

## Missing features

The schema is not verified on completeness and not all data is stored in the final structure type.

@Note Feel free to contribute support for missing features
      or bring missing features to our attention by opening an issue.
