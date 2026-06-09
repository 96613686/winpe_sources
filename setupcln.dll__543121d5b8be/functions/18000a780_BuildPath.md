# BuildPath

- ea: `0x18000a780`
- end: `0x18000a94f`
- name: `BuildPath`
- size: `463`
- prototype: `wchar_t *__fastcall(STRSAFE_PCNZWCH pszSrc, STRSAFE_PCNZWCH)`
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800040c0`
- `0x180006518`
- `0x180006b48`
- `0x180009800`
- `0x180009860`
- `0x18000a0f0`
- `0x18000b18c`
- `0x18000bb18`
- `0x18000c580`

## callees

- `0x1800095d0`
- `0x18000a780`
- `0x18000a958`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a90e`
- `ntdll!RtlFreeHeap` at `0x18000a90e`
- `ntdll!RtlAllocateHeap` at `0x18000a82e`
- `ntdll!RtlAllocateHeap` at `0x18000a82e`

## pseudocode

```c
wchar_t *__fastcall BuildPath(STRSAFE_PCNZWCH pszSrc, STRSAFE_PCNZWCH a2)
{
  const wchar_t *v2; // rsi
  __int64 v4; // rbx
  int v5; // r14d
  __int64 v6; // rdi
  int v7; // eax
  STRSAFE_PCNZWCH v8; // rax
  __int64 v9; // rcx
  size_t v10; // r12
  wchar_t *Heap; // r15
  HRESULT v12; // eax
  unsigned __int16 v13; // di
  HRESULT v14; // eax
  HRESULT v15; // eax
  DWORD v17; // [rsp+30h] [rbp-48h]
  DWORD v18; // [rsp+30h] [rbp-48h]
  size_t cchDest; // [rsp+80h] [rbp+8h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+90h] [rbp+18h] BYREF

  v2 = a2;
  pszDest = 0;
  cchDest = 0;
  if ( pszSrc && a2 )
  {
    v4 = -1;
    v5 = 0;
    v6 = -1;
    do
      ++v6;
    while ( pszSrc[v6] );
    do
      ++v4;
    while ( a2[v4] );
    if ( (_DWORD)v6 )
    {
      if ( pszSrc[(unsigned int)(v6 - 1)] == 92 )
      {
        v7 = v4 - 1;
        if ( *a2 != 92 )
          v7 = v4;
        LODWORD(v4) = v7;
        v8 = a2 + 1;
        if ( *a2 != 92 )
          v8 = a2;
        v2 = v8;
      }
      else if ( *a2 != 92 )
      {
        v5 = 1;
      }
    }
    v9 = (unsigned int)(v6 + v5 + v4 + 1);
    v10 = (unsigned int)v9;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v9);
    if ( Heap )
    {
      v12 = StringCchCopyNExW(Heap, v10, pszSrc, (unsigned int)v6, &pszDest, &cchDest, v17);
      v13 = v12;
      if ( v12 >= 0 )
      {
        if ( !v5 || (v14 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v18), v13 = v14, v14 >= 0) )
        {
          v15 = StringCchCopyNW(pszDest, cchDest, v2, (unsigned int)v4);
          v13 = v15;
          if ( v15 >= 0 )
          {
            NtCurrentTeb()->LastErrorValue = 0;
            return Heap;
          }
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      NtCurrentTeb()->LastErrorValue = v13;
    }
    else
    {
      NtCurrentTeb()->LastErrorValue = 8;
    }
  }
  else
  {
    NtCurrentTeb()->LastErrorValue = 87;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a780  mov     rax, rsp
0x18000a783  mov     [rax+10h], rbx
0x18000a787  push    rbp
0x18000a788  push    rsi
0x18000a789  push    rdi
0x18000a78a  push    r12
0x18000a78c  push    r13
0x18000a78e  push    r14
0x18000a790  push    r15
0x18000a792  sub     rsp, 40h
0x18000a796  xor     r13d, r13d
0x18000a799  mov     rsi, rdx
0x18000a79c  mov     [rax+18h], r13
0x18000a7a0  mov     rbp, rcx
0x18000a7a3  mov     [rax+8], r13
0x18000a7a7  test    rcx, rcx
0x18000a7aa  jz      loc_18000A925
0x18000a7b0  test    rdx, rdx
0x18000a7b3  jz      loc_18000A925
0x18000a7b9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a7bd  mov     r14d, r13d
0x18000a7c0  mov     rdi, rbx
0x18000a7c3  inc     rdi
0x18000a7c6  cmp     [rcx+rdi*2], r13w
0x18000a7cb  jnz     short loc_18000A7C3
0x18000a7cd  inc     rbx
0x18000a7d0  cmp     [rdx+rbx*2], r13w
0x18000a7d5  jnz     short loc_18000A7CD
0x18000a7d7  mov     r8d, 1
0x18000a7dd  test    edi, edi
0x18000a7df  jz      short loc_18000A80D
0x18000a7e1  lea     eax, [rdi-1]
0x18000a7e4  lea     edx, [r8+5Bh]
0x18000a7e8  cmp     dx, [rcx+rax*2]
0x18000a7ec  jnz     short loc_18000A806
0x18000a7ee  cmp     dx, [rsi]
0x18000a7f1  lea     eax, [rbx-1]
0x18000a7f4  cmovnz  eax, ebx
0x18000a7f7  mov     ebx, eax
0x18000a7f9  lea     rax, [rsi+2]
0x18000a7fd  cmovnz  rax, rsi
0x18000a801  mov     rsi, rax
0x18000a804  jmp     short loc_18000A80D
0x18000a806  cmp     dx, [rsi]
0x18000a809  cmovnz  r14d, r8d
0x18000a80d  lea     ecx, [rbx+1]
0x18000a810  mov     edx, 8; Flags
0x18000a815  add     ecx, r14d
0x18000a818  add     ecx, edi
0x18000a81a  mov     r12d, ecx
0x18000a81d  lea     r8, [rcx+rcx]; Size
0x18000a821  mov     rcx, gs:60h
0x18000a82a  mov     rcx, [rcx+30h]; HeapHandle
0x18000a82e  call    cs:__imp_RtlAllocateHeap
0x18000a834  mov     r15, rax
0x18000a837  test    rax, rax
0x18000a83a  jnz     short loc_18000A851
0x18000a83c  mov     rax, gs:30h
0x18000a845  mov     dword ptr [rax+68h], 8
0x18000a84c  jmp     loc_18000A935
0x18000a851  lea     rax, [rsp+78h+cchDest]
0x18000a859  mov     r9d, edi; cchToCopy
0x18000a85c  mov     [rsp+78h+pcchRemaining], rax; pcchRemaining
0x18000a861  mov     r8, rbp; pszSrc
0x18000a864  lea     rax, [rsp+78h+pszDest]
0x18000a86c  mov     rdx, r12; cchDest
0x18000a86f  mov     rcx, r15; pszDest
0x18000a872  mov     [rsp+78h+ppszDestEnd], rax; ppszDestEnd
0x18000a877  call    StringCchCopyNExW
0x18000a87c  mov     edi, eax
0x18000a87e  test    eax, eax
0x18000a880  js      short loc_18000A8FC
0x18000a882  test    r14d, r14d
0x18000a885  jz      short loc_18000A8C9
0x18000a887  mov     rdx, [rsp+78h+cchDest]; cchDest
0x18000a88f  lea     rax, [rsp+78h+cchDest]
0x18000a897  mov     rcx, [rsp+78h+pszDest]; pszDest
0x18000a89f  lea     r8, SubBlock; "\\"
0x18000a8a6  mov     [rsp+78h+pcchRemaining], rax; pcchRemaining
0x18000a8ab  mov     r9d, 1; cchToCopy
0x18000a8b1  lea     rax, [rsp+78h+pszDest]
0x18000a8b9  mov     [rsp+78h+ppszDestEnd], rax; ppszDestEnd
0x18000a8be  call    StringCchCopyNExW
0x18000a8c3  mov     edi, eax
0x18000a8c5  test    eax, eax
0x18000a8c7  js      short loc_18000A8FC
0x18000a8c9  mov     rdx, [rsp+78h+cchDest]; cchDest
0x18000a8d1  mov     r8, rsi; pszSrc
0x18000a8d4  mov     rcx, [rsp+78h+pszDest]; pszDest
0x18000a8dc  mov     r9d, ebx; cchToCopy
0x18000a8df  call    StringCchCopyNW
0x18000a8e4  mov     edi, eax
0x18000a8e6  test    eax, eax
0x18000a8e8  js      short loc_18000A8FC
0x18000a8ea  mov     rax, gs:30h
0x18000a8f3  mov     [rax+68h], r13d
0x18000a8f7  mov     rax, r15
0x18000a8fa  jmp     short loc_18000A937
0x18000a8fc  mov     rcx, gs:60h
0x18000a905  mov     r8, r15; P
0x18000a908  xor     edx, edx; Flags
0x18000a90a  mov     rcx, [rcx+30h]; HeapHandle
0x18000a90e  call    cs:__imp_RtlFreeHeap
0x18000a914  mov     rax, gs:30h
0x18000a91d  movzx   ecx, di
0x18000a920  mov     [rax+68h], ecx
0x18000a923  jmp     short loc_18000A935
0x18000a925  mov     rax, gs:30h
0x18000a92e  mov     dword ptr [rax+68h], 57h ; 'W'
0x18000a935  xor     eax, eax
0x18000a937  mov     rbx, [rsp+78h+arg_8]
0x18000a93f  add     rsp, 40h
0x18000a943  pop     r15
0x18000a945  pop     r14
0x18000a947  pop     r13
0x18000a949  pop     r12
0x18000a94b  pop     rdi
0x18000a94c  pop     rsi
0x18000a94d  pop     rbp
0x18000a94e  retn
```
