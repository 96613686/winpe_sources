# PfScStringInsertEx

- ea: `0x18003a2ac`
- end: `0x18003a458`
- name: `PfScStringInsertEx`
- size: `428`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003b00`
- `0x180006170`
- `0x180007a64`
- `0x180009344`
- `0x1800277ec`
- `0x180037578`
- `0x18003a148`
- `0x180048780`
- `0x1800553b8`
- `0x180069094`
- `0x1800810ec`
- `0x180081440`
- `0x180081b6c`
- `0x180082cd8`
- `0x180082fc4`
- `0x18009fad0`
- `0x1800a0660`
- `0x1800a2f60`

## callees

- `0x18003a2ac`
- `0x18003a460`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a39b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a39b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a3d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a3d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a3a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a3a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a448`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a448`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a37e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a37e`

## pseudocode

```c
__int64 __fastcall PfScStringInsertEx(__int64 a1, unsigned __int8 *a2, int a3, __int64 a4)
{
  _BYTE *v5; // rdi
  unsigned int v9; // r10d
  unsigned __int8 *v10; // rbp
  unsigned __int8 *v11; // r9
  unsigned __int8 *v12; // rdx
  unsigned __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 inserted; // rax
  __int64 v17; // rbx
  int v19; // eax
  _BYTE Mem[256]; // [rsp+30h] [rbp-158h] BYREF

  v5 = Mem;
  v9 = 16;
  v10 = &a2[2 * a3];
  while ( 2 )
  {
    v11 = a2 - 2;
    v12 = a2;
    v13 = (unsigned __int64)v5;
    v14 = 314159;
    while ( 1 )
    {
      if ( v12 != v10 && *(_WORD *)v12 != 92 )
        goto LABEL_5;
      if ( v13 >= (unsigned __int64)&v5[16 * v9] )
        break;
      *(_QWORD *)v13 = v14;
      v15 = v12 - v11;
      v11 = v12;
      *(_DWORD *)(v13 + 8) = (v15 >> 1) - 1;
      v13 += 16LL;
      if ( v12 == v10 )
      {
        v13 = (__int64)(v13 - (_QWORD)v5) >> 4;
        goto LABEL_9;
      }
LABEL_5:
      v14 = v12[1] + 37 * (*v12 + 37 * v14);
      v12 += 2;
    }
    LODWORD(v13) = ((__int64)(v13 - (_QWORD)v5) >> 4) + 1;
    while ( v12 < v10 )
    {
      v19 = v13 + 1;
      if ( *(_WORD *)v12 != 92 )
        v19 = v13;
      v12 += 2;
      LODWORD(v13) = v19;
    }
LABEL_9:
    if ( (unsigned int)v13 <= v9 )
    {
      RtlAcquireSRWLockExclusive(a1);
      *(_DWORD *)(a1 + 136) = GetCurrentThreadId();
      inserted = PfScStringInsertInternal(a1, (_DWORD)a2, a3, (_DWORD)v5, v13, a4);
      *(_DWORD *)(a1 + 136) = 0;
      v17 = inserted;
      RtlReleaseSRWLockExclusive(a1);
LABEL_14:
      if ( v5 && v5 != Mem )
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v5);
      return v17;
    }
    if ( (unsigned int)v13 > 0x100 )
    {
      v17 = 0;
      goto LABEL_14;
    }
    v5 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 16LL * (unsigned int)v13);
    if ( v5 )
    {
      v9 = v13;
      continue;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18003a2ac  push    rbx
0x18003a2ae  push    rbp
0x18003a2af  push    rsi
0x18003a2b0  push    rdi
0x18003a2b1  push    r12
0x18003a2b3  push    r13
0x18003a2b5  push    r14
0x18003a2b7  push    r15
0x18003a2b9  sub     rsp, 148h
0x18003a2c0  mov     rax, cs:__security_cookie
0x18003a2c7  xor     rax, rsp
0x18003a2ca  mov     [rsp+188h+var_58], rax
0x18003a2d2  mov     r15d, r8d
0x18003a2d5  lea     rdi, [rsp+188h+Mem]
0x18003a2da  mov     r13, r9
0x18003a2dd  mov     r14, rdx
0x18003a2e0  mov     rsi, rcx
0x18003a2e3  mov     r10d, 10h
0x18003a2e9  lea     rbp, [rdx+r15*2]
0x18003a2ed  mov     r8d, r10d
0x18003a2f0  lea     r9, [r14-2]
0x18003a2f4  shl     r8, 4
0x18003a2f8  mov     rdx, r14
0x18003a2fb  add     r8, rdi
0x18003a2fe  mov     rbx, rdi
0x18003a301  mov     ecx, 4CB2Fh
0x18003a306  cmp     rdx, rbp
0x18003a309  jz      short loc_18003A32C
0x18003a30b  cmp     word ptr [rdx], 5Ch ; '\'
0x18003a30f  jz      short loc_18003A32C
0x18003a311  movzx   eax, byte ptr [rdx]
0x18003a314  imul    rcx, 25h ; '%'
0x18003a318  add     rcx, rax
0x18003a31b  movzx   eax, byte ptr [rdx+1]
0x18003a31f  imul    rcx, 25h ; '%'
0x18003a323  add     rcx, rax
0x18003a326  add     rdx, 2
0x18003a32a  jmp     short loc_18003A306
0x18003a32c  cmp     rbx, r8
0x18003a32f  jnb     loc_18003A409
0x18003a335  mov     rax, rdx
0x18003a338  mov     [rbx], rcx
0x18003a33b  sub     rax, r9
0x18003a33e  mov     r9, rdx
0x18003a341  sar     rax, 1
0x18003a344  dec     eax
0x18003a346  mov     [rbx+8], eax
0x18003a349  add     rbx, 10h
0x18003a34d  cmp     rdx, rbp
0x18003a350  jnz     short loc_18003A311
0x18003a352  sub     rbx, rdi
0x18003a355  sar     rbx, 4
0x18003a359  cmp     ebx, r10d
0x18003a35c  jbe     short loc_18003A398
0x18003a35e  cmp     ebx, 100h
0x18003a364  ja      loc_18003A454
0x18003a36a  mov     rcx, cs:PfSvcGlobals
0x18003a371  xor     edx, edx; dwFlags
0x18003a373  mov     r8d, ebx
0x18003a376  shl     r8, 4; dwBytes
0x18003a37a  mov     rcx, [rcx+58h]; hHeap
0x18003a37e  call    cs:__imp_HeapAlloc
0x18003a384  mov     rdi, rax
0x18003a387  test    rax, rax
0x18003a38a  jz      loc_18003A450
0x18003a390  mov     r10d, ebx
0x18003a393  jmp     loc_18003A2ED
0x18003a398  mov     rcx, rsi
0x18003a39b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003a3a1  call    cs:__imp_GetCurrentThreadId
0x18003a3a7  mov     r9, rdi
0x18003a3aa  mov     [rsp+188h+var_160], r13
0x18003a3af  mov     r8d, r15d
0x18003a3b2  mov     [rsi+88h], eax
0x18003a3b8  mov     rdx, r14
0x18003a3bb  mov     [rsp+188h+var_168], ebx
0x18003a3bf  mov     rcx, rsi
0x18003a3c2  call    PfScStringInsertInternal
0x18003a3c7  mov     rcx, rsi
0x18003a3ca  mov     dword ptr [rsi+88h], 0
0x18003a3d4  mov     rbx, rax
0x18003a3d7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003a3dd  test    rdi, rdi
0x18003a3e0  jnz     short loc_18003A42E
0x18003a3e2  mov     rax, rbx
0x18003a3e5  mov     rcx, [rsp+188h+var_58]
0x18003a3ed  xor     rcx, rsp; StackCookie
0x18003a3f0  call    __security_check_cookie
0x18003a3f5  add     rsp, 148h
0x18003a3fc  pop     r15
0x18003a3fe  pop     r14
0x18003a400  pop     r13
0x18003a402  pop     r12
0x18003a404  pop     rdi
0x18003a405  pop     rsi
0x18003a406  pop     rbp
0x18003a407  pop     rbx
0x18003a408  retn
0x18003a409  sub     rbx, rdi
0x18003a40c  sar     rbx, 4
0x18003a410  inc     ebx
0x18003a412  jmp     short loc_18003A424
0x18003a414  cmp     word ptr [rdx], 5Ch ; '\'
0x18003a418  lea     eax, [rbx+1]
0x18003a41b  cmovnz  eax, ebx
0x18003a41e  add     rdx, 2
0x18003a422  mov     ebx, eax
0x18003a424  cmp     rdx, rbp
0x18003a427  jb      short loc_18003A414
0x18003a429  jmp     loc_18003A359
0x18003a42e  lea     rax, [rsp+188h+Mem]
0x18003a433  cmp     rdi, rax
0x18003a436  jz      short loc_18003A3E2
0x18003a438  mov     rcx, cs:PfSvcGlobals
0x18003a43f  mov     r8, rdi; lpMem
0x18003a442  xor     edx, edx; dwFlags
0x18003a444  mov     rcx, [rcx+58h]; hHeap
0x18003a448  call    cs:__imp_HeapFree
0x18003a44e  jmp     short loc_18003A3E2
0x18003a450  xor     ebx, ebx
0x18003a452  jmp     short loc_18003A3E2
0x18003a454  xor     ebx, ebx
0x18003a456  jmp     short loc_18003A3DD
```
