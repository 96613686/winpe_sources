# FreeTemplateSettings(_BLB_TEMPLATE_SETTINGS &)

- ea: `0x14012e6e4`
- end: `0x14012e7e6`
- name: `?FreeTemplateSettings@@YAXAEAU_BLB_TEMPLATE_SETTINGS@@@Z`
- size: `258`
- prototype: `void __fastcall(struct _BLB_TEMPLATE_SETTINGS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14010e288`

## callees

- `0x14012e07c`
- `0x14012e1e0`
- `0x14012e6e4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14012e6f9`
- `ole32!CoTaskMemFree` at `0x14012e70a`
- `ole32!CoTaskMemFree` at `0x14012e732`
- `ole32!CoTaskMemFree` at `0x14012e74d`
- `ole32!CoTaskMemFree` at `0x14012e76b`
- `ole32!CoTaskMemFree` at `0x14012e77d`
- `ole32!CoTaskMemFree` at `0x14012e78f`
- `ole32!CoTaskMemFree` at `0x14012e7a1`
- `ole32!CoTaskMemFree` at `0x14012e6f9`
- `ole32!CoTaskMemFree` at `0x14012e70a`
- `ole32!CoTaskMemFree` at `0x14012e732`
- `ole32!CoTaskMemFree` at `0x14012e74d`
- `ole32!CoTaskMemFree` at `0x14012e76b`
- `ole32!CoTaskMemFree` at `0x14012e77d`
- `ole32!CoTaskMemFree` at `0x14012e78f`
- `ole32!CoTaskMemFree` at `0x14012e7a1`

## pseudocode

```c
void __fastcall FreeTemplateSettings(struct _BLB_TEMPLATE_SETTINGS *a1)
{
  void *v2; // rcx
  bool v3; // zf
  __int64 i; // rsi
  __int64 v5; // rbx
  void *v6; // rcx
  void *v7; // rcx

  CoTaskMemFree(*(LPVOID *)a1);
  v2 = (void *)*((_QWORD *)a1 + 2);
  *(_QWORD *)a1 = 0;
  CoTaskMemFree(v2);
  v3 = *((_QWORD *)a1 + 4) == 0;
  *((_QWORD *)a1 + 2) = 0;
  if ( !v3 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 6); *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v5 + 8) = 0 )
    {
      v5 = 3 * i;
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a1 + 4) + 24 * i));
      *(_QWORD *)(*((_QWORD *)a1 + 4) + 24 * i) = 0;
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a1 + 4) + 24 * i + 8));
      i = (unsigned int)(i + 1);
    }
    CoTaskMemFree(*((LPVOID *)a1 + 4));
    *((_QWORD *)a1 + 4) = 0;
  }
  CoTaskMemFree(*((LPVOID *)a1 + 10));
  v6 = (void *)*((_QWORD *)a1 + 11);
  *((_QWORD *)a1 + 10) = 0;
  CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)a1 + 12);
  *((_QWORD *)a1 + 11) = 0;
  CoTaskMemFree(v7);
  *((_QWORD *)a1 + 12) = 0;
  if ( *((_DWORD *)a1 + 30) )
    FreeFileSpecs((struct _BLB_FILESPEC_INFO **)a1 + 16, (unsigned int *)a1 + 30);
  FreeComponents((struct _BLB_COMPONENT **)a1 + 18, (unsigned int *)a1 + 34);
}

```

## disassembly

```asm
0x14012e6e4  mov     [rsp+arg_0], rbx
0x14012e6e9  mov     [rsp+arg_8], rsi
0x14012e6ee  push    rdi
0x14012e6ef  sub     rsp, 20h
0x14012e6f3  mov     rdi, rcx
0x14012e6f6  mov     rcx, [rcx]; pv
0x14012e6f9  call    cs:__imp_CoTaskMemFree
0x14012e6ff  mov     rcx, [rdi+10h]; pv
0x14012e703  mov     qword ptr [rdi], 0
0x14012e70a  call    cs:__imp_CoTaskMemFree
0x14012e710  cmp     qword ptr [rdi+20h], 0
0x14012e715  mov     qword ptr [rdi+10h], 0
0x14012e71d  jz      short loc_14012E779
0x14012e71f  xor     esi, esi
0x14012e721  cmp     [rdi+18h], esi
0x14012e724  jbe     short loc_14012E767
0x14012e726  mov     rcx, [rdi+20h]
0x14012e72a  lea     rbx, [rsi+rsi*2]
0x14012e72e  mov     rcx, [rcx+rbx*8]; pv
0x14012e732  call    cs:__imp_CoTaskMemFree
0x14012e738  mov     rax, [rdi+20h]
0x14012e73c  mov     qword ptr [rax+rbx*8], 0
0x14012e744  mov     rcx, [rdi+20h]
0x14012e748  mov     rcx, [rcx+rbx*8+8]; pv
0x14012e74d  call    cs:__imp_CoTaskMemFree
0x14012e753  mov     rax, [rdi+20h]
0x14012e757  inc     esi
0x14012e759  mov     qword ptr [rax+rbx*8+8], 0
0x14012e762  cmp     esi, [rdi+18h]
0x14012e765  jb      short loc_14012E726
0x14012e767  mov     rcx, [rdi+20h]; pv
0x14012e76b  call    cs:__imp_CoTaskMemFree
0x14012e771  mov     qword ptr [rdi+20h], 0
0x14012e779  mov     rcx, [rdi+50h]; pv
0x14012e77d  call    cs:__imp_CoTaskMemFree
0x14012e783  mov     rcx, [rdi+58h]; pv
0x14012e787  mov     qword ptr [rdi+50h], 0
0x14012e78f  call    cs:__imp_CoTaskMemFree
0x14012e795  mov     rcx, [rdi+60h]; pv
0x14012e799  mov     qword ptr [rdi+58h], 0
0x14012e7a1  call    cs:__imp_CoTaskMemFree
0x14012e7a7  lea     rdx, [rdi+78h]; unsigned int *
0x14012e7ab  mov     qword ptr [rdi+60h], 0
0x14012e7b3  cmp     dword ptr [rdx], 0
0x14012e7b6  jz      short loc_14012E7C4
0x14012e7b8  lea     rcx, [rdi+80h]; struct _BLB_FILESPEC_INFO **
0x14012e7bf  call    ?FreeFileSpecs@@YAXAEAPEAU_BLB_FILESPEC_INFO@@AEAK@Z; FreeFileSpecs(_BLB_FILESPEC_INFO * &,ulong &)
0x14012e7c4  lea     rdx, [rdi+88h]; unsigned int *
0x14012e7cb  lea     rcx, [rdi+90h]; struct _BLB_COMPONENT **
0x14012e7d2  mov     rbx, [rsp+28h+arg_0]
0x14012e7d7  mov     rsi, [rsp+28h+arg_8]
0x14012e7dc  add     rsp, 20h
0x14012e7e0  pop     rdi
0x14012e7e1  jmp     ?FreeComponents@@YAXAEAPEAU_BLB_COMPONENT@@AEAK@Z; FreeComponents(_BLB_COMPONENT * &,ulong &)
```
