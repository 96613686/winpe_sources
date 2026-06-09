# CSxSimpleArray<ushort>::Alloc(ulong)

- ea: `0x180003740`
- end: `0x1800037b8`
- name: `?Alloc@?$CSxSimpleArray@G@@QEAAJK@Z`
- size: `120`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004188`
- `0x180008654`
- `0x18000e720`

## callees

- `0x180003740`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800037a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800037a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003785`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003785`

## pseudocode

```c
__int64 __fastcall CSxSimpleArray<unsigned short>::Alloc(__int64 a1, unsigned int a2)
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
    v2 = ULongLongMult(v4, 2u, &cb);
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
0x180003740  mov     [rsp+arg_8], rbx
0x180003745  mov     [rsp+arg_10], rsi
0x18000374a  push    rdi
0x18000374b  sub     rsp, 20h
0x18000374f  xor     edi, edi
0x180003751  mov     rbx, rcx
0x180003754  mov     [rsp+28h+cb], rdi
0x180003759  cmp     edx, [rcx+14h]
0x18000375c  jbe     short loc_18000379E
0x18000375e  mov     ecx, edx; unsigned int
0x180003760  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180003765  mov     ecx, eax; unsigned __int64
0x180003767  lea     r8, [rsp+28h+cb]; unsigned __int64 *
0x18000376c  lea     edx, [rdi+2]; unsigned __int64
0x18000376f  mov     esi, eax
0x180003771  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180003776  mov     edi, eax
0x180003778  test    eax, eax
0x18000377a  js      short loc_18000379E
0x18000377c  mov     rdx, [rsp+28h+cb]; cb
0x180003781  mov     rcx, [rbx+8]; pv
0x180003785  call    cs:__imp_CoTaskMemRealloc
0x18000378b  test    rax, rax
0x18000378e  jnz     short loc_180003797
0x180003790  mov     edi, 8007000Eh
0x180003795  jmp     short loc_18000379E
0x180003797  mov     [rbx+8], rax
0x18000379b  mov     [rbx+14h], esi
0x18000379e  xor     ecx, ecx; pv
0x1800037a0  call    cs:__imp_CoTaskMemFree
0x1800037a6  mov     rbx, [rsp+28h+arg_8]
0x1800037ab  mov     eax, edi
0x1800037ad  mov     rsi, [rsp+28h+arg_10]
0x1800037b2  add     rsp, 20h
0x1800037b6  pop     rdi
0x1800037b7  retn
```
