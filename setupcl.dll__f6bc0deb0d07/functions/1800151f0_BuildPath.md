# BuildPath

- ea: `0x1800151f0`
- end: `0x1800153bf`
- name: `BuildPath`
- size: `463`
- prototype: `wchar_t *__fastcall(STRSAFE_PCNZWCH pszSrc, STRSAFE_PCNZWCH)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004428`
- `0x180009374`
- `0x18000d220`
- `0x1800153c8`
- `0x1800156f8`

## callees

- `0x180014bc4`
- `0x1800151f0`
- `0x180015474`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001529e`
- `ntdll!RtlAllocateHeap` at `0x18001529e`
- `ntdll!RtlFreeHeap` at `0x18001537e`
- `ntdll!RtlFreeHeap` at `0x18001537e`

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
0x1800151f0  mov     rax, rsp
0x1800151f3  mov     [rax+10h], rbx
0x1800151f7  push    rbp
0x1800151f8  push    rsi
0x1800151f9  push    rdi
0x1800151fa  push    r12
0x1800151fc  push    r13
0x1800151fe  push    r14
0x180015200  push    r15
0x180015202  sub     rsp, 40h
0x180015206  xor     r13d, r13d
0x180015209  mov     rsi, rdx
0x18001520c  mov     [rax+18h], r13
0x180015210  mov     rbp, rcx
0x180015213  mov     [rax+8], r13
0x180015217  test    rcx, rcx
0x18001521a  jz      loc_180015395
0x180015220  test    rdx, rdx
0x180015223  jz      loc_180015395
0x180015229  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001522d  mov     r14d, r13d
0x180015230  mov     rdi, rbx
0x180015233  inc     rdi
0x180015236  cmp     [rcx+rdi*2], r13w
0x18001523b  jnz     short loc_180015233
0x18001523d  inc     rbx
0x180015240  cmp     [rdx+rbx*2], r13w
0x180015245  jnz     short loc_18001523D
0x180015247  mov     r8d, 1
0x18001524d  test    edi, edi
0x18001524f  jz      short loc_18001527D
0x180015251  lea     eax, [rdi-1]
0x180015254  lea     edx, [r8+5Bh]
0x180015258  cmp     dx, [rcx+rax*2]
0x18001525c  jnz     short loc_180015276
0x18001525e  cmp     dx, [rsi]
0x180015261  lea     eax, [rbx-1]
0x180015264  cmovnz  eax, ebx
0x180015267  mov     ebx, eax
0x180015269  lea     rax, [rsi+2]
0x18001526d  cmovnz  rax, rsi
0x180015271  mov     rsi, rax
0x180015274  jmp     short loc_18001527D
0x180015276  cmp     dx, [rsi]
0x180015279  cmovnz  r14d, r8d
0x18001527d  lea     ecx, [rbx+1]
0x180015280  mov     edx, 8; Flags
0x180015285  add     ecx, r14d
0x180015288  add     ecx, edi
0x18001528a  mov     r12d, ecx
0x18001528d  lea     r8, [rcx+rcx]; Size
0x180015291  mov     rcx, gs:60h
0x18001529a  mov     rcx, [rcx+30h]; HeapHandle
0x18001529e  call    cs:__imp_RtlAllocateHeap
0x1800152a4  mov     r15, rax
0x1800152a7  test    rax, rax
0x1800152aa  jnz     short loc_1800152C1
0x1800152ac  mov     rax, gs:30h
0x1800152b5  mov     dword ptr [rax+68h], 8
0x1800152bc  jmp     loc_1800153A5
0x1800152c1  lea     rax, [rsp+78h+cchDest]
0x1800152c9  mov     r9d, edi; cchToCopy
0x1800152cc  mov     [rsp+78h+pcchRemaining], rax; pcchRemaining
0x1800152d1  mov     r8, rbp; pszSrc
0x1800152d4  lea     rax, [rsp+78h+pszDest]
0x1800152dc  mov     rdx, r12; cchDest
0x1800152df  mov     rcx, r15; pszDest
0x1800152e2  mov     [rsp+78h+ppszDestEnd], rax; ppszDestEnd
0x1800152e7  call    StringCchCopyNExW
0x1800152ec  mov     edi, eax
0x1800152ee  test    eax, eax
0x1800152f0  js      short loc_18001536C
0x1800152f2  test    r14d, r14d
0x1800152f5  jz      short loc_180015339
0x1800152f7  mov     rdx, [rsp+78h+cchDest]; cchDest
0x1800152ff  lea     rax, [rsp+78h+cchDest]
0x180015307  mov     rcx, [rsp+78h+pszDest]; pszDest
0x18001530f  lea     r8, asc_180019770; "\\"
0x180015316  mov     [rsp+78h+pcchRemaining], rax; pcchRemaining
0x18001531b  mov     r9d, 1; cchToCopy
0x180015321  lea     rax, [rsp+78h+pszDest]
0x180015329  mov     [rsp+78h+ppszDestEnd], rax; ppszDestEnd
0x18001532e  call    StringCchCopyNExW
0x180015333  mov     edi, eax
0x180015335  test    eax, eax
0x180015337  js      short loc_18001536C
0x180015339  mov     rdx, [rsp+78h+cchDest]; cchDest
0x180015341  mov     r8, rsi; pszSrc
0x180015344  mov     rcx, [rsp+78h+pszDest]; pszDest
0x18001534c  mov     r9d, ebx; cchToCopy
0x18001534f  call    StringCchCopyNW
0x180015354  mov     edi, eax
0x180015356  test    eax, eax
0x180015358  js      short loc_18001536C
0x18001535a  mov     rax, gs:30h
0x180015363  mov     [rax+68h], r13d
0x180015367  mov     rax, r15
0x18001536a  jmp     short loc_1800153A7
0x18001536c  mov     rcx, gs:60h
0x180015375  mov     r8, r15; P
0x180015378  xor     edx, edx; Flags
0x18001537a  mov     rcx, [rcx+30h]; HeapHandle
0x18001537e  call    cs:__imp_RtlFreeHeap
0x180015384  mov     rax, gs:30h
0x18001538d  movzx   ecx, di
0x180015390  mov     [rax+68h], ecx
0x180015393  jmp     short loc_1800153A5
0x180015395  mov     rax, gs:30h
0x18001539e  mov     dword ptr [rax+68h], 57h ; 'W'
0x1800153a5  xor     eax, eax
0x1800153a7  mov     rbx, [rsp+78h+arg_8]
0x1800153af  add     rsp, 40h
0x1800153b3  pop     r15
0x1800153b5  pop     r14
0x1800153b7  pop     r13
0x1800153b9  pop     r12
0x1800153bb  pop     rdi
0x1800153bc  pop     rsi
0x1800153bd  pop     rbp
0x1800153be  retn
```
