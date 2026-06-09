# CSxArrayBuilder<_SPP_ONDISK_VOLUME_PROP,&Free_SPP_ONDISK_VOLUME_PROP(_SPP_ONDISK_VOLUME_PROP *),&SxDefaultInit<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *),&SxDefaultTransfer<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *,_SPP_ONDISK_VOLUME_PROP *)>::Alloc(ulong)

- ea: `0x180003644`
- end: `0x1800036bc`
- name: `?Alloc@?$CSxArrayBuilder@U_SPP_ONDISK_VOLUME_PROP@@$1?Free_SPP_ONDISK_VOLUME_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ONDISK_VOLUME_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ONDISK_VOLUME_PROP@@@@YAX00@Z@@QEAAJK@Z`
- size: `120`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003ee8`
- `0x18001212c`

## callees

- `0x180003644`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003689`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003689`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SPP_ONDISK_VOLUME_PROP,&void Free_SPP_ONDISK_VOLUME_PROP(_SPP_ONDISK_VOLUME_PROP *),&void SxDefaultInit<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *),&void SxDefaultTransfer<_SPP_ONDISK_VOLUME_PROP>(_SPP_ONDISK_VOLUME_PROP *,_SPP_ONDISK_VOLUME_PROP *)>::Alloc(
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
    v2 = ULongLongMult(v4, 0x30u, &cb);
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
0x180003644  mov     [rsp+arg_8], rbx
0x180003649  mov     [rsp+arg_10], rsi
0x18000364e  push    rdi
0x18000364f  sub     rsp, 20h
0x180003653  xor     edi, edi
0x180003655  mov     rbx, rcx
0x180003658  mov     [rsp+28h+cb], rdi
0x18000365d  cmp     edx, [rcx+14h]
0x180003660  jbe     short loc_1800036A2
0x180003662  mov     ecx, edx; unsigned int
0x180003664  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003669  mov     ecx, eax; unsigned __int64
0x18000366b  lea     r8, [rsp+28h+cb]; unsigned __int64 *
0x180003670  lea     edx, [rdi+30h]; unsigned __int64
0x180003673  mov     esi, eax
0x180003675  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000367a  mov     edi, eax
0x18000367c  test    eax, eax
0x18000367e  js      short loc_1800036A2
0x180003680  mov     rdx, [rsp+28h+cb]; cb
0x180003685  mov     rcx, [rbx+8]; pv
0x180003689  call    cs:__imp_CoTaskMemRealloc
0x18000368f  test    rax, rax
0x180003692  jnz     short loc_18000369B
0x180003694  mov     edi, 8007000Eh
0x180003699  jmp     short loc_1800036A2
0x18000369b  mov     [rbx+8], rax
0x18000369f  mov     [rbx+14h], esi
0x1800036a2  xor     ecx, ecx; pv
0x1800036a4  call    cs:__imp_CoTaskMemFree
0x1800036aa  mov     rbx, [rsp+28h+arg_8]
0x1800036af  mov     eax, edi
0x1800036b1  mov     rsi, [rsp+28h+arg_10]
0x1800036b6  add     rsp, 20h
0x1800036ba  pop     rdi
0x1800036bb  retn
```
