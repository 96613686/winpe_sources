# CSxSimpleArray<_GUID>::Append(_GUID)

- ea: `0x1800041d4`
- end: `0x180004280`
- name: `?Append@?$CSxSimpleArray@U_GUID@@@@QEAAJU_GUID@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019524`
- `0x18001e898`

## callees

- `0x1800041d4`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180004229`

## pseudocode

```c
__int64 __fastcall CSxSimpleArray<_GUID>::Append(__int64 a1, _OWORD *a2)
{
  unsigned int v2; // eax
  unsigned int v5; // esi
  int v6; // edi
  unsigned int v7; // ebp
  LPVOID v8; // rax
  SIZE_T cb; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  v5 = v2 + 1;
  if ( v2 + 1 < v2 )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    v6 = 0;
    cb = 0;
    if ( v5 > *(_DWORD *)(a1 + 20) )
    {
      v7 = SxScaledGrowth(v5);
      v6 = ULongLongMult(v7, 0x10u, &cb);
      if ( v6 >= 0 )
      {
        v8 = CoTaskMemRealloc(*(LPVOID *)(a1 + 8), cb);
        if ( v8 )
        {
          *(_QWORD *)(a1 + 8) = v8;
          *(_DWORD *)(a1 + 20) = v7;
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    CoTaskMemFree(0);
    if ( v6 >= 0 )
    {
      *(_OWORD *)(*(_QWORD *)(a1 + 8) + 16LL * *(unsigned int *)(a1 + 16)) = *a2;
      *(_DWORD *)(a1 + 16) = v5;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800041d4  mov     [rsp+arg_8], rbx
0x1800041d9  mov     [rsp+arg_10], rbp
0x1800041de  push    rsi
0x1800041df  push    rdi
0x1800041e0  push    r14
0x1800041e2  sub     rsp, 20h
0x1800041e6  mov     eax, [rcx+10h]
0x1800041e9  mov     r14, rdx
0x1800041ec  mov     rbx, rcx
0x1800041ef  lea     esi, [rax+1]
0x1800041f2  cmp     esi, eax
0x1800041f4  jb      short loc_180004266
0x1800041f6  xor     edi, edi
0x1800041f8  mov     [rsp+38h+cb], rdi
0x1800041fd  cmp     esi, [rcx+14h]
0x180004200  jbe     short loc_180004242
0x180004202  mov     ecx, esi; unsigned int
0x180004204  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180004209  mov     ecx, eax; unsigned __int64
0x18000420b  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180004210  lea     edx, [rdi+10h]; unsigned __int64
0x180004213  mov     ebp, eax
0x180004215  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000421a  mov     edi, eax
0x18000421c  test    eax, eax
0x18000421e  js      short loc_180004242
0x180004220  mov     rdx, [rsp+38h+cb]; cb
0x180004225  mov     rcx, [rbx+8]; pv
0x180004229  call    cs:__imp_CoTaskMemRealloc
0x18000422f  test    rax, rax
0x180004232  jnz     short loc_18000423B
0x180004234  mov     edi, 8007000Eh
0x180004239  jmp     short loc_180004242
0x18000423b  mov     [rbx+8], rax
0x18000423f  mov     [rbx+14h], ebp
0x180004242  xor     ecx, ecx; pv
0x180004244  call    cs:__imp_CoTaskMemFree
0x18000424a  test    edi, edi
0x18000424c  js      short loc_18000426B
0x18000424e  mov     ecx, [rbx+10h]
0x180004251  mov     rax, [rbx+8]
0x180004255  add     rcx, rcx
0x180004258  movaps  xmm0, xmmword ptr [r14]
0x18000425c  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180004261  mov     [rbx+10h], esi
0x180004264  jmp     short loc_18000426B
0x180004266  mov     edi, 80070216h
0x18000426b  mov     rbx, [rsp+38h+arg_8]
0x180004270  mov     eax, edi
0x180004272  mov     rbp, [rsp+38h+arg_10]
0x180004277  add     rsp, 20h
0x18000427b  pop     r14
0x18000427d  pop     rdi
0x18000427e  pop     rsi
0x18000427f  retn
```
