# BlbCleanupCatalogTemplateInfo(_BLBCAT_TEMPLATE_INFO *)

- ea: `0x1400f4964`
- end: `0x1400f4a55`
- name: `?BlbCleanupCatalogTemplateInfo@@YAXPEAU_BLBCAT_TEMPLATE_INFO@@@Z`
- size: `241`
- prototype: `void __fastcall(struct _BLBCAT_TEMPLATE_INFO *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140042ca0`
- `0x140049e40`
- `0x14010e288`

## callees

- `0x140007ad3`
- `0x1400f4918`
- `0x1400f4964`
- `0x1400f4a5c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400f497a`
- `ole32!CoTaskMemFree` at `0x1400f4989`
- `ole32!CoTaskMemFree` at `0x1400f49b9`
- `ole32!CoTaskMemFree` at `0x1400f49c8`
- `ole32!CoTaskMemFree` at `0x1400f49d7`
- `ole32!CoTaskMemFree` at `0x1400f49e6`
- `ole32!CoTaskMemFree` at `0x1400f49f5`
- `ole32!CoTaskMemFree` at `0x1400f4a23`
- `ole32!CoTaskMemFree` at `0x1400f4a35`
- `ole32!CoTaskMemFree` at `0x1400f497a`
- `ole32!CoTaskMemFree` at `0x1400f4989`
- `ole32!CoTaskMemFree` at `0x1400f49b9`
- `ole32!CoTaskMemFree` at `0x1400f49c8`
- `ole32!CoTaskMemFree` at `0x1400f49d7`
- `ole32!CoTaskMemFree` at `0x1400f49e6`
- `ole32!CoTaskMemFree` at `0x1400f49f5`
- `ole32!CoTaskMemFree` at `0x1400f4a23`
- `ole32!CoTaskMemFree` at `0x1400f4a35`

## pseudocode

```c
void __fastcall BlbCleanupCatalogTemplateInfo(struct _BLBCAT_TEMPLATE_INFO *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 i; // rdi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  unsigned int j; // edi
  void *v10; // rcx

  v2 = (void *)*((_QWORD *)a1 + 2);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)a1 + 4);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( *((_QWORD *)a1 + 6) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 10); i = (unsigned int)(i + 1) )
      BlbCleanupCatalogTargetInfo((struct _BLBCAT_TARGET_INFO *)(*((_QWORD *)a1 + 6) + 40 * i));
    CoTaskMemFree(*((LPVOID *)a1 + 6));
  }
  v5 = (void *)*((_QWORD *)a1 + 7);
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)a1 + 8);
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)a1 + 9);
  if ( v7 )
    CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)a1 + 13);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( *((_QWORD *)a1 + 11) )
  {
    for ( j = 0; j < *((_DWORD *)a1 + 20); ++j )
      BlbCleanupCatalogVolumeInfo((struct _BLBCAT_VOLUME_INFO *)(*((_QWORD *)a1 + 11) + 120LL * j));
    CoTaskMemFree(*((LPVOID *)a1 + 11));
  }
  v10 = (void *)*((_QWORD *)a1 + 16);
  if ( v10 )
    CoTaskMemFree(v10);
  memset_0(a1, 0, 0x90u);
}

```

## disassembly

```asm
0x1400f4964  mov     [rsp+arg_0], rbx
0x1400f4969  push    rdi
0x1400f496a  sub     rsp, 20h
0x1400f496e  mov     rbx, rcx
0x1400f4971  mov     rcx, [rcx+10h]; pv
0x1400f4975  test    rcx, rcx
0x1400f4978  jz      short loc_1400F4980
0x1400f497a  call    cs:__imp_CoTaskMemFree
0x1400f4980  mov     rcx, [rbx+20h]; pv
0x1400f4984  test    rcx, rcx
0x1400f4987  jz      short loc_1400F498F
0x1400f4989  call    cs:__imp_CoTaskMemFree
0x1400f498f  cmp     qword ptr [rbx+30h], 0
0x1400f4994  jz      short loc_1400F49BF
0x1400f4996  xor     edi, edi
0x1400f4998  cmp     [rbx+28h], edi
0x1400f499b  jbe     short loc_1400F49B5
0x1400f499d  mov     rax, [rbx+30h]
0x1400f49a1  lea     rcx, [rdi+rdi*4]
0x1400f49a5  lea     rcx, [rax+rcx*8]; struct _BLBCAT_TARGET_INFO *
0x1400f49a9  call    ?BlbCleanupCatalogTargetInfo@@YAXPEAU_BLBCAT_TARGET_INFO@@@Z; BlbCleanupCatalogTargetInfo(_BLBCAT_TARGET_INFO *)
0x1400f49ae  inc     edi
0x1400f49b0  cmp     edi, [rbx+28h]
0x1400f49b3  jb      short loc_1400F499D
0x1400f49b5  mov     rcx, [rbx+30h]; pv
0x1400f49b9  call    cs:__imp_CoTaskMemFree
0x1400f49bf  mov     rcx, [rbx+38h]; pv
0x1400f49c3  test    rcx, rcx
0x1400f49c6  jz      short loc_1400F49CE
0x1400f49c8  call    cs:__imp_CoTaskMemFree
0x1400f49ce  mov     rcx, [rbx+40h]; pv
0x1400f49d2  test    rcx, rcx
0x1400f49d5  jz      short loc_1400F49DD
0x1400f49d7  call    cs:__imp_CoTaskMemFree
0x1400f49dd  mov     rcx, [rbx+48h]; pv
0x1400f49e1  test    rcx, rcx
0x1400f49e4  jz      short loc_1400F49EC
0x1400f49e6  call    cs:__imp_CoTaskMemFree
0x1400f49ec  mov     rcx, [rbx+68h]; pv
0x1400f49f0  test    rcx, rcx
0x1400f49f3  jz      short loc_1400F49FB
0x1400f49f5  call    cs:__imp_CoTaskMemFree
0x1400f49fb  cmp     qword ptr [rbx+58h], 0
0x1400f4a00  jz      short loc_1400F4A29
0x1400f4a02  xor     edi, edi
0x1400f4a04  cmp     [rbx+50h], edi
0x1400f4a07  jbe     short loc_1400F4A1F
0x1400f4a09  mov     eax, edi
0x1400f4a0b  imul    rcx, rax, 78h ; 'x'
0x1400f4a0f  add     rcx, [rbx+58h]; struct _BLBCAT_VOLUME_INFO *
0x1400f4a13  call    ?BlbCleanupCatalogVolumeInfo@@YAXPEAU_BLBCAT_VOLUME_INFO@@@Z; BlbCleanupCatalogVolumeInfo(_BLBCAT_VOLUME_INFO *)
0x1400f4a18  inc     edi
0x1400f4a1a  cmp     edi, [rbx+50h]
0x1400f4a1d  jb      short loc_1400F4A09
0x1400f4a1f  mov     rcx, [rbx+58h]; pv
0x1400f4a23  call    cs:__imp_CoTaskMemFree
0x1400f4a29  mov     rcx, [rbx+80h]; pv
0x1400f4a30  test    rcx, rcx
0x1400f4a33  jz      short loc_1400F4A3B
0x1400f4a35  call    cs:__imp_CoTaskMemFree
0x1400f4a3b  xor     edx, edx; Val
0x1400f4a3d  mov     r8d, 90h; Size
0x1400f4a43  mov     rcx, rbx; void *
0x1400f4a46  mov     rbx, [rsp+28h+arg_0]
0x1400f4a4b  add     rsp, 20h
0x1400f4a4f  pop     rdi
0x1400f4a50  jmp     memset_0
```
