# CSxRefArray<CWriterEntryArray,CWriterEntry>::Alloc(ulong)

- ea: `0x1800036c4`
- end: `0x18000373a`
- name: `?Alloc@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJK@Z`
- size: `118`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004124`
- `0x180017960`

## callees

- `0x1800036c4`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180003708`

## pseudocode

```c
__int64 __fastcall CSxRefArray<CWriterEntryArray,CWriterEntry>::Alloc(__int64 a1, unsigned int a2)
{
  int v2; // edi
  unsigned int v4; // esi
  LPVOID v5; // rax
  SIZE_T cb; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  cb = 0;
  if ( a2 > *(_DWORD *)(a1 + 12) )
  {
    v4 = SxScaledGrowth(a2);
    v2 = ULongLongMult(v4, 8u, &cb);
    if ( v2 >= 0 )
    {
      v5 = CoTaskMemRealloc(*(LPVOID *)a1, cb);
      if ( v5 )
      {
        *(_QWORD *)a1 = v5;
        *(_DWORD *)(a1 + 12) = v4;
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
0x1800036c4  mov     [rsp+arg_8], rbx
0x1800036c9  mov     [rsp+arg_10], rsi
0x1800036ce  push    rdi
0x1800036cf  sub     rsp, 20h
0x1800036d3  xor     edi, edi
0x1800036d5  mov     rbx, rcx
0x1800036d8  mov     [rsp+28h+cb], rdi
0x1800036dd  cmp     edx, [rcx+0Ch]
0x1800036e0  jbe     short loc_180003720
0x1800036e2  mov     ecx, edx; unsigned int
0x1800036e4  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x1800036e9  mov     ecx, eax; unsigned __int64
0x1800036eb  lea     r8, [rsp+28h+cb]; unsigned __int64 *
0x1800036f0  lea     edx, [rdi+8]; unsigned __int64
0x1800036f3  mov     esi, eax
0x1800036f5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800036fa  mov     edi, eax
0x1800036fc  test    eax, eax
0x1800036fe  js      short loc_180003720
0x180003700  mov     rdx, [rsp+28h+cb]; cb
0x180003705  mov     rcx, [rbx]; pv
0x180003708  call    cs:__imp_CoTaskMemRealloc
0x18000370e  test    rax, rax
0x180003711  jnz     short loc_18000371A
0x180003713  mov     edi, 8007000Eh
0x180003718  jmp     short loc_180003720
0x18000371a  mov     [rbx], rax
0x18000371d  mov     [rbx+0Ch], esi
0x180003720  xor     ecx, ecx; pv
0x180003722  call    cs:__imp_CoTaskMemFree
0x180003728  mov     rbx, [rsp+28h+arg_8]
0x18000372d  mov     eax, edi
0x18000372f  mov     rsi, [rsp+28h+arg_10]
0x180003734  add     rsp, 20h
0x180003738  pop     rdi
0x180003739  retn
```
