# CSxSimpleArray<ushort *>::Append(ushort *)

- ea: `0x18002758c`
- end: `0x180027632`
- name: `?Append@?$CSxSimpleArray@PEAG@@QEAAJPEAG@Z`
- size: `166`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002849c`
- `0x180028b7c`

## callees

- `0x18000f8ac`
- `0x18000f9ec`
- `0x18002758c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800275fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800275fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800275e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800275e2`

## pseudocode

```c
__int64 __fastcall CSxSimpleArray<unsigned short *>::Append(__int64 a1, __int64 a2)
{
  unsigned int v2; // eax
  unsigned int v5; // esi
  int v6; // edi
  unsigned int v7; // r14d
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
      v6 = ULongLongMult(v7, 8u, &cb);
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
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * *(unsigned int *)(a1 + 16)) = a2;
      *(_DWORD *)(a1 + 16) = v5;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002758c  mov     [rsp+arg_8], rbx
0x180027591  mov     [rsp+arg_10], rbp
0x180027596  push    rsi
0x180027597  push    rdi
0x180027598  push    r14
0x18002759a  sub     rsp, 20h
0x18002759e  mov     eax, [rcx+10h]
0x1800275a1  mov     rbp, rdx
0x1800275a4  mov     rbx, rcx
0x1800275a7  lea     esi, [rax+1]
0x1800275aa  cmp     esi, eax
0x1800275ac  jb      short loc_180027618
0x1800275ae  xor     edi, edi
0x1800275b0  mov     [rsp+38h+cb], rdi
0x1800275b5  cmp     esi, [rcx+14h]
0x1800275b8  jbe     short loc_1800275FC
0x1800275ba  mov     ecx, esi; unsigned int
0x1800275bc  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x1800275c1  mov     ecx, eax; unsigned __int64
0x1800275c3  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800275c8  lea     edx, [rdi+8]; unsigned __int64
0x1800275cb  mov     r14d, eax
0x1800275ce  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800275d3  mov     edi, eax
0x1800275d5  test    eax, eax
0x1800275d7  js      short loc_1800275FC
0x1800275d9  mov     rdx, [rsp+38h+cb]; cb
0x1800275de  mov     rcx, [rbx+8]; pv
0x1800275e2  call    cs:__imp_CoTaskMemRealloc
0x1800275e8  test    rax, rax
0x1800275eb  jnz     short loc_1800275F4
0x1800275ed  mov     edi, 8007000Eh
0x1800275f2  jmp     short loc_1800275FC
0x1800275f4  mov     [rbx+8], rax
0x1800275f8  mov     [rbx+14h], r14d
0x1800275fc  xor     ecx, ecx; pv
0x1800275fe  call    cs:__imp_CoTaskMemFree
0x180027604  test    edi, edi
0x180027606  js      short loc_18002761D
0x180027608  mov     ecx, [rbx+10h]
0x18002760b  mov     rax, [rbx+8]
0x18002760f  mov     [rax+rcx*8], rbp
0x180027613  mov     [rbx+10h], esi
0x180027616  jmp     short loc_18002761D
0x180027618  mov     edi, 80070216h
0x18002761d  mov     rbx, [rsp+38h+arg_8]
0x180027622  mov     eax, edi
0x180027624  mov     rbp, [rsp+38h+arg_10]
0x180027629  add     rsp, 20h
0x18002762d  pop     r14
0x18002762f  pop     rdi
0x180027630  pop     rsi
0x180027631  retn
```
