# ATL::CComModule::Term(void)

- ea: `0x180004424`
- end: `0x180004594`
- name: `?Term@CComModule@ATL@@QEAAXXZ`
- size: `368`
- prototype: `void __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004994`

## callees

- `0x180001494`
- `0x180004424`
- `0x180004f40`
- `0x180006010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800044b8`
- `KERNEL32!DeleteCriticalSection` at `0x1800044dd`
- `KERNEL32!DeleteCriticalSection` at `0x180004502`
- `KERNEL32!DeleteCriticalSection` at `0x1800044b8`
- `KERNEL32!DeleteCriticalSection` at `0x1800044dd`
- `KERNEL32!DeleteCriticalSection` at `0x180004502`
- `KERNEL32!HeapDestroy` at `0x180004565`
- `KERNEL32!HeapDestroy` at `0x180004583`
- `KERNEL32!HeapDestroy` at `0x180004565`
- `KERNEL32!HeapDestroy` at `0x180004583`

## pseudocode

```c
void __fastcall ATL::CComModule::Term(ATL::CComModule *this)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx
  void (__fastcall *v3)(_QWORD); // rax
  __int64 v4; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rbx
  HANDLE v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rbx
  void *v10; // rcx
  _OWORD Buf2[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-18h]

  v1 = (_QWORD *)qword_18000A280;
  if ( qword_18000A280 )
  {
    while ( *v1 )
    {
      v2 = v1[4];
      if ( v2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      v3 = (void (__fastcall *)(_QWORD))v1[8];
      v1[4] = 0;
      v3(0);
      v4 = 72;
      if ( _Module == 176 )
        v4 = 56;
      v1 = (_QWORD *)((char *)v1 + v4);
    }
  }
  v12 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  if ( memcmp_0(&Buf1, Buf2, 0x28u) )
    DeleteCriticalSection(&Buf1);
  if ( memcmp_0(&stru_18000A2C0, Buf2, 0x28u) )
    DeleteCriticalSection(&stru_18000A2C0);
  if ( memcmp_0(&CriticalSection, Buf2, 0x28u) )
    DeleteCriticalSection(&CriticalSection);
  v5 = qword_18000A348;
  if ( qword_18000A348 )
  {
    do
    {
      ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
      v6 = (_QWORD *)v5[2];
      operator delete(v5);
      v5 = v6;
    }
    while ( v6 );
  }
  v7 = hHeap;
  if ( hHeap && byte_18000A320 )
  {
    v8 = qword_18000A338;
    if ( qword_18000A338 )
    {
      v9 = 0;
      do
      {
        v10 = *(void **)(v8 + 8 * v9);
        if ( v10 )
        {
          HeapDestroy(v10);
          v8 = qword_18000A338;
        }
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 <= dword_18000A330 );
      v7 = hHeap;
    }
    HeapDestroy(v7);
  }
}

```

## disassembly

```asm
0x180004424  mov     [rsp+arg_0], rbx
0x180004429  push    rdi
0x18000442a  sub     rsp, 50h
0x18000442e  mov     rbx, cs:qword_18000A280
0x180004435  test    rbx, rbx
0x180004438  jz      short loc_180004482
0x18000443a  jmp     short loc_18000447C
0x18000443c  mov     rcx, [rbx+20h]
0x180004440  test    rcx, rcx
0x180004443  jz      short loc_180004451
0x180004445  mov     rax, [rcx]
0x180004448  mov     rax, [rax+10h]
0x18000444c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004451  mov     rax, [rbx+40h]
0x180004455  xor     ecx, ecx
0x180004457  mov     qword ptr [rbx+20h], 0
0x18000445f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004464  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x18000446e  mov     eax, 48h ; 'H'
0x180004473  lea     ecx, [rax-10h]
0x180004476  cmovz   eax, ecx
0x180004479  add     rbx, rax
0x18000447c  cmp     qword ptr [rbx], 0
0x180004480  jnz     short loc_18000443C
0x180004482  xor     eax, eax
0x180004484  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180004489  xorps   xmm0, xmm0
0x18000448c  mov     [rsp+58h+var_18], rax
0x180004491  lea     rcx, Buf1; Buf1
0x180004498  movups  [rsp+58h+Buf2], xmm0
0x18000449d  lea     ebx, [rax+28h]
0x1800044a0  mov     r8d, ebx; Size
0x1800044a3  movups  [rsp+58h+var_28], xmm0
0x1800044a8  call    memcmp_0
0x1800044ad  test    eax, eax
0x1800044af  jz      short loc_1800044BE
0x1800044b1  lea     rcx, Buf1; lpCriticalSection
0x1800044b8  call    cs:__imp_DeleteCriticalSection
0x1800044be  mov     r8, rbx; Size
0x1800044c1  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800044c6  lea     rcx, stru_18000A2C0; Buf1
0x1800044cd  call    memcmp_0
0x1800044d2  test    eax, eax
0x1800044d4  jz      short loc_1800044E3
0x1800044d6  lea     rcx, stru_18000A2C0; lpCriticalSection
0x1800044dd  call    cs:__imp_DeleteCriticalSection
0x1800044e3  mov     r8, rbx; Size
0x1800044e6  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800044eb  lea     rcx, CriticalSection; Buf1
0x1800044f2  call    memcmp_0
0x1800044f7  test    eax, eax
0x1800044f9  jz      short loc_180004508
0x1800044fb  lea     rcx, CriticalSection; lpCriticalSection
0x180004502  call    cs:__imp_DeleteCriticalSection
0x180004508  mov     rdi, cs:qword_18000A348
0x18000450f  test    rdi, rdi
0x180004512  jz      short loc_180004539
0x180004514  mov     rcx, [rdi+8]
0x180004518  mov     rax, [rdi]
0x18000451b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004520  mov     rbx, [rdi+10h]
0x180004524  mov     edx, 18h; unsigned __int64
0x180004529  mov     rcx, rdi; void *
0x18000452c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004531  mov     rdi, rbx
0x180004534  test    rbx, rbx
0x180004537  jnz     short loc_180004514
0x180004539  mov     rcx, cs:hHeap
0x180004540  test    rcx, rcx
0x180004543  jz      short loc_180004589
0x180004545  cmp     cs:byte_18000A320, 0
0x18000454c  jz      short loc_180004589
0x18000454e  mov     rdx, cs:qword_18000A338
0x180004555  test    rdx, rdx
0x180004558  jz      short loc_180004583
0x18000455a  xor     ebx, ebx
0x18000455c  mov     rcx, [rdx+rbx*8]; hHeap
0x180004560  test    rcx, rcx
0x180004563  jz      short loc_180004572
0x180004565  call    cs:__imp_HeapDestroy
0x18000456b  mov     rdx, cs:qword_18000A338
0x180004572  inc     ebx
0x180004574  cmp     ebx, cs:dword_18000A330
0x18000457a  jbe     short loc_18000455C
0x18000457c  mov     rcx, cs:hHeap; hHeap
0x180004583  call    cs:__imp_HeapDestroy
0x180004589  mov     rbx, [rsp+58h+arg_0]
0x18000458e  add     rsp, 50h
0x180004592  pop     rdi
0x180004593  retn
```
