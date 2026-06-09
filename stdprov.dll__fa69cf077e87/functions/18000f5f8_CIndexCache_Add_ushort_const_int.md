# CIndexCache::Add(ushort const *,int)

- ea: `0x18000f5f8`
- end: `0x18000f6e5`
- name: `?Add@CIndexCache@@QEAAHPEBGH@Z`
- size: `237`
- prototype: `__int64 __fastcall(CIndexCache *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800118ec`

## callees

- `0x180002e10`
- `0x18000f5f8`
- `0x180017010`

## import_xrefs

- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x18000f6b2`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x18000f6b2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f6a1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f6a1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f63e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f662`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f63e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f662`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIndexCache::Add(CIndexCache *this, const unsigned __int16 *a2, int a3)
{
  __int64 v6; // rax
  unsigned int v7; // esi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  void (__fastcall ***v10)(void *, __int64); // rax
  void (__fastcall ***v11)(void *, __int64); // rbx

  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
  }
  else
  {
    LODWORD(v6) = 0;
  }
  v7 = v6 + 1;
  v8 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v6 + 1), 2u));
  v9 = v8;
  if ( v8 )
  {
    StringCchCopyW(v8, v7, a2);
    v10 = (void (__fastcall ***)(void *, __int64))CWin32DefaultArena::WbemMemAlloc(0x20u);
    v11 = v10;
    if ( v10 )
    {
      *v10 = (void (__fastcall **)(void *, __int64))&CObject::`vftable';
      *v10 = (void (__fastcall **)(void *, __int64))&CCacheEntry::`vftable';
      *((_DWORD *)v10 + 2) = a3;
      v10[2] = (void (__fastcall **)(void *, __int64))v9;
      v10[3] = 0;
    }
    else
    {
      v11 = 0;
    }
    if ( v11 )
    {
      if ( !CFlexArray::InsertAt((CIndexCache *)((char *)this + 8), *((_DWORD *)this + 2), v11) )
        return 1;
      (**v11)(v11, 1);
    }
    else
    {
      CWin32DefaultArena::WbemMemFree(v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f5f8  push    rbx
0x18000f5fa  push    rbp
0x18000f5fb  push    rsi
0x18000f5fc  push    rdi
0x18000f5fd  push    r14
0x18000f5ff  push    r15
0x18000f601  sub     rsp, 28h
0x18000f605  mov     ebp, r8d
0x18000f608  mov     rbx, rdx
0x18000f60b  mov     r14, rcx
0x18000f60e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000f612  xor     r15d, r15d
0x18000f615  test    rdx, rdx
0x18000f618  jz      short loc_18000F629
0x18000f61a  mov     rax, rcx
0x18000f61d  inc     rax
0x18000f620  cmp     [rdx+rax*2], r15w
0x18000f625  jnz     short loc_18000F61D
0x18000f627  jmp     short loc_18000F62C
0x18000f629  mov     rax, r15
0x18000f62c  lea     esi, [rax+1]
0x18000f62f  mov     eax, 2
0x18000f634  mul     rsi
0x18000f637  cmovb   rax, rcx
0x18000f63b  mov     rcx, rax
0x18000f63e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000f644  mov     rdi, rax
0x18000f647  test    rax, rax
0x18000f64a  jz      loc_18000F6D6
0x18000f650  mov     r8, rbx; unsigned __int16 *
0x18000f653  mov     edx, esi; unsigned __int64
0x18000f655  mov     rcx, rax; unsigned __int16 *
0x18000f658  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f65d  mov     ecx, 20h ; ' '
0x18000f662  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000f668  mov     rbx, rax
0x18000f66b  mov     [rsp+58h+arg_8], rax
0x18000f670  test    rax, rax
0x18000f673  jz      short loc_18000F696
0x18000f675  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x18000f67c  mov     [rbx], rax
0x18000f67f  lea     rax, ??_7CCacheEntry@@6B@; const CCacheEntry::`vftable'
0x18000f686  mov     [rbx], rax
0x18000f689  mov     [rbx+8], ebp
0x18000f68c  mov     [rbx+10h], rdi
0x18000f690  mov     [rbx+18h], r15
0x18000f694  jmp     short loc_18000F699
0x18000f696  mov     rbx, r15
0x18000f699  test    rbx, rbx
0x18000f69c  jnz     short loc_18000F6A9
0x18000f69e  mov     rcx, rdi
0x18000f6a1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000f6a7  jmp     short loc_18000F6D6
0x18000f6a9  lea     rcx, [r14+8]
0x18000f6ad  mov     r8, rbx
0x18000f6b0  mov     edx, [rcx]
0x18000f6b2  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x18000f6b8  test    eax, eax
0x18000f6ba  jnz     short loc_18000F6C3
0x18000f6bc  mov     eax, 1
0x18000f6c1  jmp     short loc_18000F6D8
0x18000f6c3  mov     rax, [rbx]
0x18000f6c6  mov     edx, 1
0x18000f6cb  mov     rcx, rbx
0x18000f6ce  mov     rax, [rax]
0x18000f6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d6  xor     eax, eax
0x18000f6d8  add     rsp, 28h
0x18000f6dc  pop     r15
0x18000f6de  pop     r14
0x18000f6e0  pop     rdi
0x18000f6e1  pop     rsi
0x18000f6e2  pop     rbp
0x18000f6e3  pop     rbx
0x18000f6e4  retn
```
