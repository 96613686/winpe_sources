# CUpdUtil::ExpandCascTable(CConstraintTag *,COptExpr *,CValRef *,CRemapBasePvr *,DRgPExpr &,DRgPExpr &)

- ea: `0x101ba85e0`
- end: `0x101bab322`
- name: `?ExpandCascTable@CUpdUtil@@AEBAXPEAVCConstraintTag@@PEAVCOptExpr@@PEAVCValRef@@PEAVCRemapBasePvr@@AEAVDRgPExpr@@4@Z`
- size: `11586`
- prototype: `void __usercall(CUpdUtil *__hidden this@<rcx>, struct CConstraintTag *@<rdx>, struct COptExpr *@<r8>, struct CValRef *@<r9>, struct CRemapBasePvr *, struct DRgPExpr *, struct DRgPExpr *)`
- caller_count: `1`
- callee_count: `44`
- tags: `broker_com_uri`

## callers

- `0x101ba8320`

## callees

- `0x100401070`
- `0x100407430`
- `0x10045a980`
- `0x10045ab00`
- `0x10046b580`
- `0x10046c910`
- `0x10046d010`
- `0x10046d130`
- `0x10046e3a0`
- `0x100473380`
- `0x100473f00`
- `0x100478130`
- `0x100478580`
- `0x1004886d0`
- `0x100491150`
- `0x100495960`
- `0x10049afe0`
- `0x10049b2f0`
- `0x10049bb30`
- `0x1004a0090`
- `0x1004a9670`
- `0x1004b7bf0`
- `0x1004bac40`
- `0x1004bb490`
- `0x1004c2000`
- `0x1004c48c0`
- `0x1004c7f30`
- `0x100638640`
- `0x10063d600`
- `0x10063ef20`
- `0x10063f4a0`
- `0x100739960`
- `0x100739de0`
- `0x100741ad0`
- `0x10075b470`
- `0x100e869b0`
- `0x10193d560`
- `0x101ba85e0`
- `0x101bac440`
- `0x101bbed00`
- `0x101bc0350`
- `0x101bc0a20`
- `0x101bc7230`
- `0x101bcfad0`

## import_xrefs

- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba895e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba92d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa27a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa6d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa7ae`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa81b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa86e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba895e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba92d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa27a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa6d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa7ae`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa81b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa86e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8732`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba87f6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8a11`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8a49`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8a81`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8b5b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8b93`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8c4e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8d96`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8dce`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba900c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9044`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba91a6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba91de`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9391`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba93c9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9401`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9439`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9503`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba964c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba971d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9755`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba98a0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba98dc`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9914`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9a23`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9b78`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9cb2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9eaa`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9f31`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa483`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa53a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa572`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa924`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa95c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baaa2e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baaaa5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baab8d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baade3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baaf3c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8732`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba87f6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8a11`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8a49`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8a81`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8b5b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8b93`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8c4e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8d96`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba8dce`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba900c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9044`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba91a6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba91de`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9391`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba93c9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9401`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9439`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9503`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba964c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba971d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9755`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba98a0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba98dc`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9914`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9a23`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9b78`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9cb2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9eaa`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101ba9f31`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa483`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa53a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa572`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa924`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa95c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baaa2e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baaaa5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baab8d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baade3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baaf3c`
- `sqldk!SystemThread_TlsIndex` at `0x101baa0e2`
- `sqldk!SystemThread_TlsIndex` at `0x101baa133`
- `sqldk!SystemThread_TlsIndex` at `0x101baa190`
- `sqldk!SystemThread_TlsOffset` at `0x101baa0eb`
- `sqldk!SystemThread_TlsOffset` at `0x101baa13c`
- `sqldk!SystemThread_TlsOffset` at `0x101baa19a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101baa40a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101baa41a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101baa439`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101bab27f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101baa40a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101baa41a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101baa439`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101bab27f`
- `sqldk!??_V@YAXPEAX@Z` at `0x101ba985a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101bab246`
- `sqldk!??_V@YAXPEAX@Z` at `0x101bab2d7`
- `sqldk!??_V@YAXPEAX@Z` at `0x101ba985a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101bab246`
- `sqldk!??_V@YAXPEAX@Z` at `0x101bab2d7`

## string_xrefs

- `0x101ba894d`: `Sql\Ntdbms\include\common\stdarray.inl`
- `0x101ba92c5`: `Sql\Ntdbms\include\common\stdarray.inl`
- `0x101baa6c6`: `Sql\Ntdbms\include\common\stdarray.inl`
- `0x101baa79d`: `Sql\Ntdbms\include\common\stdarray.inl`
- `0x101baa80a`: `Sql\Ntdbms\include\common\stdarray.inl`

## pseudocode

```c

```
