# LOCK_SET::AddParentLock(IPubLock *)

- ea: `0x1800031b0`
- end: `0x18000343f`
- name: `?AddParentLock@LOCK_SET@@UEAAJPEAVIPubLock@@@Z`
- size: `655`
- prototype: `int(LOCK_SET *__hidden this, struct IPubLock *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180003058`
- `0x1800031b0`
- `0x180003614`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall LOCK_SET::AddParentLock(LOCK_SET *this, struct IPubLock *a2)
{
  __int64 v2; // rax
  wchar_t *v5; // rax
  char *v6; // r14
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax
  URI_LOCK_LIST *v8; // rbx
  URI_LOCK_LIST *v9; // rax
  const unsigned __int16 *v10; // rax
  int v11; // esi
  unsigned int v13; // r8d
  unsigned __int16 *v14; // rdx
  unsigned __int16 v15; // ax
  unsigned __int16 v16; // cx
  __int64 v17; // r8
  unsigned int v18; // r8d
  unsigned __int16 *v19; // rdx
  unsigned __int16 v20; // ax
  unsigned __int16 v21; // cx
  unsigned int v22; // r8d
  int v23; // ebx
  unsigned int v24; // r8d
  char *v25; // r9
  unsigned __int16 *v26; // rdx
  unsigned __int16 v27; // cx
  unsigned __int16 v28; // ax
  unsigned int v29; // r8d
  struct LOCK_ENTRY *v30; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(_QWORD *)a2;
  v30 = 0;
  v5 = (wchar_t *)(*(__int64 (__fastcall **)(struct IPubLock *))(v2 + 32))(a2);
  v6 = (char *)this + 776;
  Key = STATIC_WSTRING_HASH::FindKey((LOCK_SET *)((char *)this + 776), v5);
  v8 = (URI_LOCK_LIST *)(((unsigned __int64)Key - 8) & -(__int64)(Key != 0));
  if ( !v8 )
  {
    v9 = (URI_LOCK_LIST *)operator new(0x300u);
    v8 = v9;
    if ( !v9 )
      return 2147942414LL;
    *((_QWORD *)v9 + 90) = 0;
    *(_QWORD *)v9 = &URI_LOCK_LIST::`vftable';
    *((_QWORD *)v9 + 92) = (char *)v9 + 80;
    *((_DWORD *)v9 + 182) = 0;
    *((_QWORD *)v9 + 93) = 0;
    *((_QWORD *)v9 + 94) = 0;
    *((_QWORD *)v9 + 95) = 0;
    v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 32LL))(a2);
    v11 = URI_LOCK_LIST::Initialize(v8, v10);
    if ( v11 < 0 )
    {
      (**(void (__fastcall ***)(URI_LOCK_LIST *, __int64))v8)(v8, 1);
      return (unsigned int)v11;
    }
    v13 = 0;
    v14 = (unsigned __int16 *)*((_QWORD *)v8 + 1);
    v15 = *v14;
    if ( *((_DWORD *)this + 456) )
    {
      while ( v15 )
      {
        ++v14;
        v13 = v15 + 101 * v13;
        v15 = *v14;
      }
    }
    else
    {
      while ( v15 )
      {
        v16 = v15;
        v15 = *++v14;
        v13 = (v16 & 0xFFDF) + 101 * v13;
      }
    }
    v17 = v13 % 0x83;
    *((_QWORD *)v8 + 2) = *(_QWORD *)&v6[8 * v17];
    *(_QWORD *)&v6[8 * v17] = (char *)v8 + 8;
    v18 = 0;
    v19 = (unsigned __int16 *)*((_QWORD *)v8 + 7);
    v20 = *v19;
    if ( *((_DWORD *)this + 984) )
    {
      while ( v20 )
      {
        ++v19;
        v18 = v20 + 101 * v18;
        v20 = *v19;
      }
    }
    else
    {
      while ( v20 )
      {
        v21 = v20;
        v20 = *++v19;
        v18 = (v21 & 0xFFDF) + 101 * v18;
      }
    }
    v22 = v18 % 0x83;
    *((_QWORD *)v8 + 8) = *((_QWORD *)this + v22 + 361);
    *((_QWORD *)this + v22 + 361) = (char *)v8 + 56;
  }
  v23 = URI_LOCK_LIST::AddLock2(v8, a2, &v30);
  if ( v23 >= 0 )
  {
    v24 = 0;
    v25 = (char *)v30 + 16;
    v26 = (unsigned __int16 *)*((_QWORD *)v30 + 2);
    if ( *((_DWORD *)this + 1248) )
    {
      while ( 1 )
      {
        v27 = *v26;
        if ( !*v26 )
          break;
        ++v26;
        v24 = v27 + 101 * v24;
      }
    }
    else
    {
      while ( 1 )
      {
        v28 = *v26;
        if ( !*v26 )
          break;
        ++v26;
        v24 = (v28 & 0xFFDF) + 101 * v24;
      }
    }
    v29 = v24 % 0x83;
    *((_QWORD *)v30 + 3) = *((_QWORD *)this + v29 + 493);
    *((_QWORD *)this + v29 + 493) = v25;
    if ( (*(unsigned int (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 72LL))(a2) )
      ++*((_DWORD *)this + 1251);
    else
      ++*((_DWORD *)this + 1250);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1800031b0  mov     [rsp+arg_8], rbx
0x1800031b5  mov     [rsp+arg_10], rbp
0x1800031ba  push    rsi
0x1800031bb  push    rdi
0x1800031bc  push    r12
0x1800031be  push    r14
0x1800031c0  push    r15
0x1800031c2  sub     rsp, 20h
0x1800031c6  mov     rax, [rdx]
0x1800031c9  mov     rdi, rcx
0x1800031cc  xor     ebp, ebp
0x1800031ce  mov     rcx, rdx
0x1800031d1  mov     r15, rdx
0x1800031d4  mov     [rsp+48h+arg_0], rbp
0x1800031d9  mov     rax, [rax+20h]
0x1800031dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e2  lea     r14, [rdi+308h]
0x1800031e9  mov     rdx, rax; unsigned __int16 *
0x1800031ec  mov     rcx, r14; this
0x1800031ef  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x1800031f4  mov     r12d, 0FA232CF3h
0x1800031fa  lea     rcx, [rax-8]
0x1800031fe  neg     rax
0x180003201  sbb     rbx, rbx
0x180003204  and     rbx, rcx
0x180003207  jnz     loc_180003371
0x18000320d  mov     ecx, 300h; Size
0x180003212  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003217  mov     rbx, rax
0x18000321a  test    rax, rax
0x18000321d  jz      loc_1800033A4
0x180003223  mov     [rax+2D0h], rbp
0x18000322a  lea     rsi, ??_7URI_LOCK_LIST@@6B@; const URI_LOCK_LIST::`vftable'
0x180003231  mov     [rax], rsi
0x180003234  add     rax, 50h ; 'P'
0x180003238  mov     [rbx+2E0h], rax
0x18000323f  mov     [rbx+2D8h], ebp
0x180003245  mov     [rbx+2E8h], rbp
0x18000324c  mov     [rbx+2F0h], rbp
0x180003253  mov     [rbx+2F8h], rbp
0x18000325a  mov     rcx, [r15]
0x18000325d  mov     rax, [rcx+20h]
0x180003261  mov     rcx, r15
0x180003264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003269  mov     rdx, rax
0x18000326c  mov     rcx, rbx
0x18000326f  mov     rax, [rsi+8]
0x180003273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003278  mov     esi, eax
0x18000327a  test    eax, eax
0x18000327c  jns     short loc_180003296
0x18000327e  mov     rcx, [rbx]
0x180003281  lea     edx, [rbp+1]
0x180003284  mov     rax, [rcx]
0x180003287  mov     rcx, rbx
0x18000328a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328f  mov     eax, esi
0x180003291  jmp     loc_180003428
0x180003296  lea     r9, [rbx+8]
0x18000329a  mov     r8d, ebp
0x18000329d  mov     rdx, [r9]
0x1800032a0  movzx   eax, word ptr [rdx]
0x1800032a3  cmp     [r14+418h], ebp
0x1800032aa  jz      short loc_1800032DD
0x1800032ac  jmp     short loc_1800032BF
0x1800032ae  movzx   eax, ax
0x1800032b1  lea     rdx, [rdx+2]
0x1800032b5  imul    r8d, 65h ; 'e'
0x1800032b9  add     r8d, eax
0x1800032bc  movzx   eax, word ptr [rdx]
0x1800032bf  test    ax, ax
0x1800032c2  jnz     short loc_1800032AE
0x1800032c4  jmp     short loc_1800032E2
0x1800032c6  movzx   ecx, ax
0x1800032c9  lea     rdx, [rdx+2]
0x1800032cd  movzx   eax, word ptr [rdx]
0x1800032d0  and     ecx, 0FFDFh
0x1800032d6  imul    r8d, 65h ; 'e'
0x1800032da  add     r8d, ecx
0x1800032dd  test    ax, ax
0x1800032e0  jnz     short loc_1800032C6
0x1800032e2  mov     eax, r12d
0x1800032e5  mul     r8d
0x1800032e8  shr     edx, 7
0x1800032eb  imul    eax, edx, 83h
0x1800032f1  sub     r8d, eax
0x1800032f4  mov     rax, [r14+r8*8]
0x1800032f8  mov     [r9+8], rax
0x1800032fc  mov     [r14+r8*8], r9
0x180003300  lea     r9, [rbx+38h]
0x180003304  mov     r8d, ebp
0x180003307  mov     rdx, [r9]
0x18000330a  movzx   eax, word ptr [rdx]
0x18000330d  cmp     [rdi+0F60h], ebp
0x180003313  jz      short loc_180003346
0x180003315  jmp     short loc_180003328
0x180003317  movzx   eax, ax
0x18000331a  lea     rdx, [rdx+2]
0x18000331e  imul    r8d, 65h ; 'e'
0x180003322  add     r8d, eax
0x180003325  movzx   eax, word ptr [rdx]
0x180003328  test    ax, ax
0x18000332b  jnz     short loc_180003317
0x18000332d  jmp     short loc_18000334B
0x18000332f  movzx   ecx, ax
0x180003332  lea     rdx, [rdx+2]
0x180003336  movzx   eax, word ptr [rdx]
0x180003339  and     ecx, 0FFDFh
0x18000333f  imul    r8d, 65h ; 'e'
0x180003343  add     r8d, ecx
0x180003346  test    ax, ax
0x180003349  jnz     short loc_18000332F
0x18000334b  mov     eax, r12d
0x18000334e  mul     r8d
0x180003351  shr     edx, 7
0x180003354  imul    eax, edx, 83h
0x18000335a  sub     r8d, eax
0x18000335d  mov     rax, [rdi+r8*8+0B48h]
0x180003365  mov     [r9+8], rax
0x180003369  mov     [rdi+r8*8+0B48h], r9
0x180003371  lea     r8, [rsp+48h+arg_0]; struct LOCK_ENTRY **
0x180003376  mov     rdx, r15; struct IPubLock *
0x180003379  mov     rcx, rbx; this
0x18000337c  call    ?AddLock2@URI_LOCK_LIST@@QEAAJPEAVIPubLock@@PEAPEAULOCK_ENTRY@@@Z; URI_LOCK_LIST::AddLock2(IPubLock *,LOCK_ENTRY * *)
0x180003381  mov     ebx, eax
0x180003383  test    eax, eax
0x180003385  js      loc_180003426
0x18000338b  mov     r9, [rsp+48h+arg_0]
0x180003390  mov     r8d, ebp
0x180003393  add     r9, 10h
0x180003397  mov     rdx, [r9]
0x18000339a  cmp     [rdi+1380h], ebp
0x1800033a0  jz      short loc_1800033D7
0x1800033a2  jmp     short loc_1800033B9
0x1800033a4  mov     eax, 8007000Eh
0x1800033a9  jmp     short loc_180003428
0x1800033ab  imul    r8d, 65h ; 'e'
0x1800033af  lea     rdx, [rdx+2]
0x1800033b3  movzx   ecx, cx
0x1800033b6  add     r8d, ecx
0x1800033b9  movzx   ecx, word ptr [rdx]
0x1800033bc  test    cx, cx
0x1800033bf  jnz     short loc_1800033AB
0x1800033c1  jmp     short loc_1800033DF
0x1800033c3  imul    r8d, 65h ; 'e'
0x1800033c7  lea     rdx, [rdx+2]
0x1800033cb  movzx   ecx, ax
0x1800033ce  and     ecx, 0FFDFh
0x1800033d4  add     r8d, ecx
0x1800033d7  movzx   eax, word ptr [rdx]
0x1800033da  test    ax, ax
0x1800033dd  jnz     short loc_1800033C3
0x1800033df  mov     eax, r12d
0x1800033e2  mov     rcx, r15
0x1800033e5  mul     r8d
0x1800033e8  shr     edx, 7
0x1800033eb  imul    eax, edx, 83h
0x1800033f1  sub     r8d, eax
0x1800033f4  mov     rax, [rdi+r8*8+0F68h]
0x1800033fc  mov     [r9+8], rax
0x180003400  mov     [rdi+r8*8+0F68h], r9
0x180003408  mov     rax, [r15]
0x18000340b  mov     rax, [rax+48h]
0x18000340f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003414  test    eax, eax
0x180003416  jnz     short loc_180003420
0x180003418  inc     dword ptr [rdi+1388h]
0x18000341e  jmp     short loc_180003426
0x180003420  inc     dword ptr [rdi+138Ch]
0x180003426  mov     eax, ebx
0x180003428  mov     rbx, [rsp+48h+arg_8]
0x18000342d  mov     rbp, [rsp+48h+arg_10]
0x180003432  add     rsp, 20h
0x180003436  pop     r15
0x180003438  pop     r14
0x18000343a  pop     r12
0x18000343c  pop     rdi
0x18000343d  pop     rsi
0x18000343e  retn
```
