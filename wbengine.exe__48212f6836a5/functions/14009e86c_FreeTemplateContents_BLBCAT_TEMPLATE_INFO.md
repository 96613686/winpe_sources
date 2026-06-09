# FreeTemplateContents(_BLBCAT_TEMPLATE_INFO *)

- ea: `0x14009e86c`
- end: `0x14009e959`
- name: `?FreeTemplateContents@@YAXPEAU_BLBCAT_TEMPLATE_INFO@@@Z`
- size: `237`
- prototype: `void __fastcall(struct _BLBCAT_TEMPLATE_INFO *)`
- caller_count: `7`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14003f388`
- `0x14003fbf0`
- `0x140043ce0`
- `0x140049e40`
- `0x14004f000`
- `0x14009ff70`
- `0x140135c69`

## callees

- `0x140006ca8`
- `0x140098ec8`
- `0x140098fc8`
- `0x14009e86c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14009e8b5`
- `ole32!CoTaskMemFree` at `0x14009e8cc`
- `ole32!CoTaskMemFree` at `0x14009e8e3`
- `ole32!CoTaskMemFree` at `0x14009e8fa`
- `ole32!CoTaskMemFree` at `0x14009e911`
- `ole32!CoTaskMemFree` at `0x14009e928`
- `ole32!CoTaskMemFree` at `0x14009e942`
- `ole32!CoTaskMemFree` at `0x14009e8b5`
- `ole32!CoTaskMemFree` at `0x14009e8cc`
- `ole32!CoTaskMemFree` at `0x14009e8e3`
- `ole32!CoTaskMemFree` at `0x14009e8fa`
- `ole32!CoTaskMemFree` at `0x14009e911`
- `ole32!CoTaskMemFree` at `0x14009e928`
- `ole32!CoTaskMemFree` at `0x14009e942`

## string_xrefs

- `0x14009e87a`: `pTemplate`

## pseudocode

```c
void __fastcall FreeTemplateContents(struct _BLBCAT_TEMPLATE_INFO *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( !a1 )
    BlbAssert("base\\stor\\blb\\catalog\\catglbl.cpp", 0x298u, "pTemplate");
  CBLBCatalog::FreeTargets((struct _BLBCAT_TARGET_INFO **)a1 + 6, (unsigned int *)a1 + 10);
  CBLBCatalog::FreeVolumes((struct _BLBCAT_VOLUME_INFO **)a1 + 11, (unsigned int *)a1 + 20);
  v2 = (void *)*((_QWORD *)a1 + 4);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)a1 + 2);
  *((_QWORD *)a1 + 4) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)a1 + 9);
  *((_QWORD *)a1 + 2) = 0;
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)a1 + 7);
  *((_QWORD *)a1 + 9) = 0;
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)a1 + 8);
  *((_QWORD *)a1 + 7) = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)a1 + 13);
  *((_QWORD *)a1 + 8) = 0;
  if ( v7 )
    CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)a1 + 16);
  *((_QWORD *)a1 + 13) = 0;
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x14009e86c  push    rbx
0x14009e86e  sub     rsp, 20h
0x14009e872  mov     rbx, rcx
0x14009e875  test    rcx, rcx
0x14009e878  jnz     short loc_14009E892
0x14009e87a  lea     r8, aPtemplate; "pTemplate"
0x14009e881  mov     edx, 298h; unsigned int
0x14009e886  lea     rcx, aBaseStorBlbCat_9; "base\\stor\\blb\\catalog\\catglbl.cpp"
0x14009e88d  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14009e892  lea     rdx, [rbx+28h]; unsigned int *
0x14009e896  lea     rcx, [rbx+30h]; struct _BLBCAT_TARGET_INFO **
0x14009e89a  call    ?FreeTargets@CBLBCatalog@@SAXPEAPEAU_BLBCAT_TARGET_INFO@@PEAK@Z; CBLBCatalog::FreeTargets(_BLBCAT_TARGET_INFO * *,ulong *)
0x14009e89f  lea     rdx, [rbx+50h]; unsigned int *
0x14009e8a3  lea     rcx, [rbx+58h]; struct _BLBCAT_VOLUME_INFO **
0x14009e8a7  call    ?FreeVolumes@CBLBCatalog@@SAXPEAPEAU_BLBCAT_VOLUME_INFO@@PEAK@Z; CBLBCatalog::FreeVolumes(_BLBCAT_VOLUME_INFO * *,ulong *)
0x14009e8ac  mov     rcx, [rbx+20h]; pv
0x14009e8b0  test    rcx, rcx
0x14009e8b3  jz      short loc_14009E8BB
0x14009e8b5  call    cs:__imp_CoTaskMemFree
0x14009e8bb  mov     rcx, [rbx+10h]; pv
0x14009e8bf  mov     qword ptr [rbx+20h], 0
0x14009e8c7  test    rcx, rcx
0x14009e8ca  jz      short loc_14009E8D2
0x14009e8cc  call    cs:__imp_CoTaskMemFree
0x14009e8d2  mov     rcx, [rbx+48h]; pv
0x14009e8d6  mov     qword ptr [rbx+10h], 0
0x14009e8de  test    rcx, rcx
0x14009e8e1  jz      short loc_14009E8E9
0x14009e8e3  call    cs:__imp_CoTaskMemFree
0x14009e8e9  mov     rcx, [rbx+38h]; pv
0x14009e8ed  mov     qword ptr [rbx+48h], 0
0x14009e8f5  test    rcx, rcx
0x14009e8f8  jz      short loc_14009E900
0x14009e8fa  call    cs:__imp_CoTaskMemFree
0x14009e900  mov     rcx, [rbx+40h]; pv
0x14009e904  mov     qword ptr [rbx+38h], 0
0x14009e90c  test    rcx, rcx
0x14009e90f  jz      short loc_14009E917
0x14009e911  call    cs:__imp_CoTaskMemFree
0x14009e917  mov     rcx, [rbx+68h]; pv
0x14009e91b  mov     qword ptr [rbx+40h], 0
0x14009e923  test    rcx, rcx
0x14009e926  jz      short loc_14009E92E
0x14009e928  call    cs:__imp_CoTaskMemFree
0x14009e92e  mov     rcx, [rbx+80h]; pv
0x14009e935  mov     qword ptr [rbx+68h], 0
0x14009e93d  test    rcx, rcx
0x14009e940  jz      short loc_14009E953
0x14009e942  call    cs:__imp_CoTaskMemFree
0x14009e948  mov     qword ptr [rbx+80h], 0
0x14009e953  add     rsp, 20h
0x14009e957  pop     rbx
0x14009e958  retn
```
