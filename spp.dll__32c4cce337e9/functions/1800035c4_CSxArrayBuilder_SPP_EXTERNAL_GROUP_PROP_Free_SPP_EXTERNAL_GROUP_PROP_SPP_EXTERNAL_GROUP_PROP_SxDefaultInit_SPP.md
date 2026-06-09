# CSxArrayBuilder<_SPP_EXTERNAL_GROUP_PROP,&Free_SPP_EXTERNAL_GROUP_PROP(_SPP_EXTERNAL_GROUP_PROP *),&SxDefaultInit<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *),&SxDefaultTransfer<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *,_SPP_EXTERNAL_GROUP_PROP *)>::Alloc(ulong)

- ea: `0x1800035c4`
- end: `0x18000363e`
- name: `?Alloc@?$CSxArrayBuilder@U_SPP_EXTERNAL_GROUP_PROP@@$1?Free_SPP_EXTERNAL_GROUP_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_EXTERNAL_GROUP_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_EXTERNAL_GROUP_PROP@@@@YAX00@Z@@QEAAJK@Z`
- size: `122`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003bf0`
- `0x180009bb0`

## callees

- `0x1800035c4`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000360b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000360b`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SPP_EXTERNAL_GROUP_PROP,&void Free_SPP_EXTERNAL_GROUP_PROP(_SPP_EXTERNAL_GROUP_PROP *),&void SxDefaultInit<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *),&void SxDefaultTransfer<_SPP_EXTERNAL_GROUP_PROP>(_SPP_EXTERNAL_GROUP_PROP *,_SPP_EXTERNAL_GROUP_PROP *)>::Alloc(
        __int64 a1,
        unsigned int a2)
{
  int v2; // edi
  unsigned int v4; // esi
  LPVOID v5; // rax
  SIZE_T cb; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  cb = 0;
  if ( a2 > *(_DWORD *)(a1 + 20) )
  {
    v4 = SxScaledGrowth(a2);
    v2 = ULongLongMult(v4, 0xB0u, &cb);
    if ( v2 >= 0 )
    {
      v5 = CoTaskMemRealloc(*(LPVOID *)(a1 + 8), cb);
      if ( v5 )
      {
        *(_QWORD *)(a1 + 8) = v5;
        *(_DWORD *)(a1 + 20) = v4;
      }
      else
      {
        v2 = -2147024882;
      }
    }
  }
  CoTaskMemFree(0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800035c4  mov     [rsp+arg_8], rbx
0x1800035c9  mov     [rsp+arg_10], rsi
0x1800035ce  push    rdi
0x1800035cf  sub     rsp, 20h
0x1800035d3  xor     edi, edi
0x1800035d5  mov     rbx, rcx
0x1800035d8  mov     [rsp+28h+cb], rdi
0x1800035dd  cmp     edx, [rcx+14h]
0x1800035e0  jbe     short loc_180003624
0x1800035e2  mov     ecx, edx; unsigned int
0x1800035e4  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x1800035e9  mov     ecx, eax; unsigned __int64
0x1800035eb  lea     r8, [rsp+28h+cb]; unsigned __int64 *
0x1800035f0  mov     edx, 0B0h; unsigned __int64
0x1800035f5  mov     esi, eax
0x1800035f7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800035fc  mov     edi, eax
0x1800035fe  test    eax, eax
0x180003600  js      short loc_180003624
0x180003602  mov     rdx, [rsp+28h+cb]; cb
0x180003607  mov     rcx, [rbx+8]; pv
0x18000360b  call    cs:__imp_CoTaskMemRealloc
0x180003611  test    rax, rax
0x180003614  jnz     short loc_18000361D
0x180003616  mov     edi, 8007000Eh
0x18000361b  jmp     short loc_180003624
0x18000361d  mov     [rbx+8], rax
0x180003621  mov     [rbx+14h], esi
0x180003624  xor     ecx, ecx; pv
0x180003626  call    cs:__imp_CoTaskMemFree
0x18000362c  mov     rbx, [rsp+28h+arg_8]
0x180003631  mov     eax, edi
0x180003633  mov     rsi, [rsp+28h+arg_10]
0x180003638  add     rsp, 20h
0x18000363c  pop     rdi
0x18000363d  retn
```
