# CHandleCache::lAddToList(ushort const *,void *)

- ea: `0x180002fa0`
- end: `0x18000317e`
- name: `?lAddToList@CHandleCache@@QEAAJPEBGPEAX@Z`
- size: `478`
- prototype: `int __fastcall(CHandleCache *this, const unsigned __int16 *, void (__fastcall **)(_QWORD, __int64))`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002770`
- `0x1800121e0`

## callees

- `0x180002e10`
- `0x180002fa0`
- `0x180017010`

## import_xrefs

- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180003107`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180003107`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003010`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000308f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800030ee`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003010`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000308f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800030ee`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002fc4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003070`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800030d0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002fc4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003070`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800030d0`

## pseudocode

```c
int __fastcall CHandleCache::lAddToList(
        CHandleCache *this,
        const unsigned __int16 *a2,
        void (__fastcall **a3)(_QWORD, __int64))
{
  char *v6; // rax
  void (__fastcall ***v7)(_QWORD, __int64); // rdi
  char *v8; // r14
  char *v9; // rcx
  __int64 v10; // rax
  int v11; // ebp
  unsigned __int16 *v12; // rax
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  __int64 v14; // rcx
  int v15; // ebp
  unsigned __int16 *v16; // rax
  int result; // eax
  unsigned __int16 *v18; // [rsp+20h] [rbp-38h]
  _WORD v19[2]; // [rsp+28h] [rbp-30h] BYREF
  int v20; // [rsp+2Ch] [rbp-2Ch]

  v6 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
  v7 = (void (__fastcall ***)(_QWORD, __int64))v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = &CObject::`vftable';
    *(_QWORD *)v6 = &CEntry::`vftable';
    v8 = v6 + 16;
    *((_WORD *)v6 + 8) = 0;
    *((_QWORD *)v6 + 1) = v6 + 16;
    *((_DWORD *)v6 + 5) = 0;
    *((_QWORD *)v6 + 3) = 0;
    *((_DWORD *)v6 + 5) = 0;
    v9 = (char *)*((_QWORD *)v6 + 1);
    if ( v9 != v6 + 16 )
      CWin32DefaultArena::WbemMemFree(v9);
    v7[1] = (void (__fastcall **)(_QWORD, __int64))v8;
  }
  else
  {
    v7 = 0;
  }
  if ( !v7 )
    return -2147217402;
  v7[3] = a3;
  v19[0] = 0;
  v18 = v19;
  v20 = 0;
  if ( a2 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v11 = v10 + 1;
    v12 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v10 + 1, 2u));
    if ( v12 )
    {
      v18 = v12;
      v20 = v11;
      StringCchCopyW(v12, v11, a2);
    }
  }
  *((_DWORD *)v7 + 5) = 0;
  v13 = (void (__fastcall ***)(_QWORD, __int64))v7[1];
  if ( v13 != v7 + 2 )
    CWin32DefaultArena::WbemMemFree(v13);
  v7[1] = (void (__fastcall **)(_QWORD, __int64))(v7 + 2);
  if ( v18 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v18[v14] );
    v15 = v14 + 1;
    v16 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v14 + 1, 2u));
    if ( v16 )
    {
      v7[1] = (void (__fastcall **)(_QWORD, __int64))v16;
      *((_DWORD *)v7 + 5) = v15;
      StringCchCopyW(v16, v15, v18);
    }
  }
  v20 = 0;
  if ( v18 != v19 )
    CWin32DefaultArena::WbemMemFree(v18);
  result = CFlexArray::InsertAt((CHandleCache *)((char *)this + 8), *((_DWORD *)this + 2), v7);
  if ( result )
  {
    (**v7)(v7, 1);
    return -2147217402;
  }
  return result;
}

```

## disassembly

```asm
0x180002fa0  mov     [rsp+arg_0], rbx
0x180002fa5  mov     [rsp+arg_8], rbp
0x180002faa  push    rsi
0x180002fab  push    rdi
0x180002fac  push    r12
0x180002fae  push    r14
0x180002fb0  push    r15
0x180002fb2  sub     rsp, 30h
0x180002fb6  mov     rbp, r8
0x180002fb9  mov     rbx, rdx
0x180002fbc  mov     r15, rcx
0x180002fbf  mov     ecx, 20h ; ' '
0x180002fc4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180002fca  mov     rdi, rax
0x180002fcd  mov     [rsp+58h+arg_18], rax
0x180002fd2  test    rax, rax
0x180002fd5  jz      loc_18000315B
0x180002fdb  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x180002fe2  mov     [rdi], rax
0x180002fe5  lea     rax, ??_7CEntry@@6B@; const CEntry::`vftable'
0x180002fec  mov     [rdi], rax
0x180002fef  lea     r14, [rdi+10h]
0x180002ff3  xor     esi, esi
0x180002ff5  mov     [r14], si
0x180002ff9  mov     [rdi+8], r14
0x180002ffd  mov     [rdi+14h], esi
0x180003000  mov     [rdi+18h], rsi
0x180003004  mov     [rdi+14h], esi
0x180003007  mov     rcx, [rdi+8]
0x18000300b  cmp     rcx, r14
0x18000300e  jz      short loc_180003016
0x180003010  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180003016  mov     [rdi+8], r14
0x18000301a  test    rdi, rdi
0x18000301d  jz      loc_180003177
0x180003023  mov     [rdi+18h], rbp
0x180003027  mov     [rsp+58h+var_30], si
0x18000302c  lea     rax, [rsp+58h+var_30]
0x180003031  mov     [rsp+58h+var_38], rax
0x180003036  mov     [rsp+58h+var_2C], esi
0x18000303a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180003041  test    rbx, rbx
0x180003044  jz      short loc_18000307F
0x180003046  mov     rax, r12
0x180003049  nop     dword ptr [rax+00000000h]
0x180003050  lea     rax, [rax+1]
0x180003054  cmp     word ptr [rbx+rax*2], 0
0x180003059  jnz     short loc_180003050
0x18000305b  lea     ebp, [rax+1]
0x18000305e  movsxd  r14, ebp
0x180003061  mov     eax, 2
0x180003066  mul     r14
0x180003069  cmovb   rax, r12
0x18000306d  mov     rcx, rax
0x180003070  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003076  test    rax, rax
0x180003079  jnz     loc_180003128
0x18000307f  mov     [rdi+14h], esi
0x180003082  lea     rbx, [rdi+10h]
0x180003086  mov     rcx, [rdi+8]
0x18000308a  cmp     rcx, rbx
0x18000308d  jz      short loc_180003095
0x18000308f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180003095  mov     [rdi+8], rbx
0x180003099  mov     rbx, [rsp+58h+var_38]
0x18000309e  test    rbx, rbx
0x1800030a1  jz      short loc_1800030DB
0x1800030a3  mov     rcx, r12
0x1800030a6  nop     word ptr [rax+rax+00000000h]
0x1800030b0  lea     rcx, [rcx+1]
0x1800030b4  cmp     word ptr [rbx+rcx*2], 0
0x1800030b9  jnz     short loc_1800030B0
0x1800030bb  lea     ebp, [rcx+1]
0x1800030be  movsxd  r14, ebp
0x1800030c1  mov     eax, 2
0x1800030c6  mul     r14
0x1800030c9  cmovb   rax, r12
0x1800030cd  mov     rcx, rax
0x1800030d0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800030d6  test    rax, rax
0x1800030d9  jnz     short loc_180003144
0x1800030db  mov     [rsp+58h+var_2C], esi
0x1800030df  lea     rax, [rsp+58h+var_30]
0x1800030e4  mov     rcx, [rsp+58h+var_38]
0x1800030e9  cmp     rcx, rax
0x1800030ec  jz      short loc_1800030F4
0x1800030ee  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800030f4  lea     rax, [rsp+58h+var_30]
0x1800030f9  mov     [rsp+58h+var_38], rax
0x1800030fe  lea     rcx, [r15+8]
0x180003102  mov     r8, rdi
0x180003105  mov     edx, [rcx]
0x180003107  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x18000310d  test    eax, eax
0x18000310f  jnz     short loc_180003164
0x180003111  mov     rbx, [rsp+58h+arg_0]
0x180003116  mov     rbp, [rsp+58h+arg_8]
0x18000311b  add     rsp, 30h
0x18000311f  pop     r15
0x180003121  pop     r14
0x180003123  pop     r12
0x180003125  pop     rdi
0x180003126  pop     rsi
0x180003127  retn
0x180003128  mov     [rsp+58h+var_38], rax
0x18000312d  mov     [rsp+58h+var_2C], ebp
0x180003131  mov     r8, rbx; unsigned __int16 *
0x180003134  mov     rdx, r14; unsigned __int64
0x180003137  mov     rcx, rax; unsigned __int16 *
0x18000313a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000313f  jmp     loc_18000307F
0x180003144  mov     [rdi+8], rax
0x180003148  mov     [rdi+14h], ebp
0x18000314b  mov     r8, rbx; unsigned __int16 *
0x18000314e  mov     rdx, r14; unsigned __int64
0x180003151  mov     rcx, rax; unsigned __int16 *
0x180003154  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003159  jmp     short loc_1800030DB
0x18000315b  xor     esi, esi
0x18000315d  mov     edi, esi
0x18000315f  jmp     loc_18000301A
0x180003164  mov     rax, [rdi]
0x180003167  mov     edx, 1
0x18000316c  mov     rcx, rdi
0x18000316f  mov     rax, [rax]
0x180003172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003177  mov     eax, 80041006h
0x18000317c  jmp     short loc_180003111
```
