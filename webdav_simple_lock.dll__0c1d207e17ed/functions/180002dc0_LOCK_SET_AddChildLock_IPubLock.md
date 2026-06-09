# LOCK_SET::AddChildLock(IPubLock *)

- ea: `0x180002dc0`
- end: `0x18000304f`
- name: `?AddChildLock@LOCK_SET@@UEAAJPEAVIPubLock@@@Z`
- size: `655`
- prototype: `int(LOCK_SET *__hidden this, struct IPubLock *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180002dc0`
- `0x180003058`
- `0x180003614`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall LOCK_SET::AddChildLock(LOCK_SET *this, struct IPubLock *a2)
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
  v6 = (char *)this + 1832;
  Key = STATIC_WSTRING_HASH::FindKey((LOCK_SET *)((char *)this + 1832), v5);
  v8 = (URI_LOCK_LIST *)(((unsigned __int64)Key - 32) & -(__int64)(Key != 0));
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
    v14 = (unsigned __int16 *)*((_QWORD *)v8 + 4);
    v15 = *v14;
    if ( *((_DWORD *)this + 720) )
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
    *((_QWORD *)v8 + 5) = *(_QWORD *)&v6[8 * v17];
    *(_QWORD *)&v6[8 * v17] = (char *)v8 + 32;
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
0x180002dc0  mov     [rsp+arg_8], rbx
0x180002dc5  mov     [rsp+arg_10], rbp
0x180002dca  push    rsi
0x180002dcb  push    rdi
0x180002dcc  push    r12
0x180002dce  push    r14
0x180002dd0  push    r15
0x180002dd2  sub     rsp, 20h
0x180002dd6  mov     rax, [rdx]
0x180002dd9  mov     rdi, rcx
0x180002ddc  xor     ebp, ebp
0x180002dde  mov     rcx, rdx
0x180002de1  mov     r15, rdx
0x180002de4  mov     [rsp+48h+arg_0], rbp
0x180002de9  mov     rax, [rax+20h]
0x180002ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df2  lea     r14, [rdi+728h]
0x180002df9  mov     rdx, rax; unsigned __int16 *
0x180002dfc  mov     rcx, r14; this
0x180002dff  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180002e04  mov     r12d, 0FA232CF3h
0x180002e0a  lea     rcx, [rax-20h]
0x180002e0e  neg     rax
0x180002e11  sbb     rbx, rbx
0x180002e14  and     rbx, rcx
0x180002e17  jnz     loc_180002F81
0x180002e1d  mov     ecx, 300h; Size
0x180002e22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e27  mov     rbx, rax
0x180002e2a  test    rax, rax
0x180002e2d  jz      loc_180002FB4
0x180002e33  mov     [rax+2D0h], rbp
0x180002e3a  lea     rsi, ??_7URI_LOCK_LIST@@6B@; const URI_LOCK_LIST::`vftable'
0x180002e41  mov     [rax], rsi
0x180002e44  add     rax, 50h ; 'P'
0x180002e48  mov     [rbx+2E0h], rax
0x180002e4f  mov     [rbx+2D8h], ebp
0x180002e55  mov     [rbx+2E8h], rbp
0x180002e5c  mov     [rbx+2F0h], rbp
0x180002e63  mov     [rbx+2F8h], rbp
0x180002e6a  mov     rcx, [r15]
0x180002e6d  mov     rax, [rcx+20h]
0x180002e71  mov     rcx, r15
0x180002e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e79  mov     rdx, rax
0x180002e7c  mov     rcx, rbx
0x180002e7f  mov     rax, [rsi+8]
0x180002e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e88  mov     esi, eax
0x180002e8a  test    eax, eax
0x180002e8c  jns     short loc_180002EA6
0x180002e8e  mov     rcx, [rbx]
0x180002e91  lea     edx, [rbp+1]
0x180002e94  mov     rax, [rcx]
0x180002e97  mov     rcx, rbx
0x180002e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9f  mov     eax, esi
0x180002ea1  jmp     loc_180003038
0x180002ea6  lea     r9, [rbx+20h]
0x180002eaa  mov     r8d, ebp
0x180002ead  mov     rdx, [r9]
0x180002eb0  movzx   eax, word ptr [rdx]
0x180002eb3  cmp     [r14+418h], ebp
0x180002eba  jz      short loc_180002EED
0x180002ebc  jmp     short loc_180002ECF
0x180002ebe  movzx   eax, ax
0x180002ec1  lea     rdx, [rdx+2]
0x180002ec5  imul    r8d, 65h ; 'e'
0x180002ec9  add     r8d, eax
0x180002ecc  movzx   eax, word ptr [rdx]
0x180002ecf  test    ax, ax
0x180002ed2  jnz     short loc_180002EBE
0x180002ed4  jmp     short loc_180002EF2
0x180002ed6  movzx   ecx, ax
0x180002ed9  lea     rdx, [rdx+2]
0x180002edd  movzx   eax, word ptr [rdx]
0x180002ee0  and     ecx, 0FFDFh
0x180002ee6  imul    r8d, 65h ; 'e'
0x180002eea  add     r8d, ecx
0x180002eed  test    ax, ax
0x180002ef0  jnz     short loc_180002ED6
0x180002ef2  mov     eax, r12d
0x180002ef5  mul     r8d
0x180002ef8  shr     edx, 7
0x180002efb  imul    eax, edx, 83h
0x180002f01  sub     r8d, eax
0x180002f04  mov     rax, [r14+r8*8]
0x180002f08  mov     [r9+8], rax
0x180002f0c  mov     [r14+r8*8], r9
0x180002f10  lea     r9, [rbx+38h]
0x180002f14  mov     r8d, ebp
0x180002f17  mov     rdx, [r9]
0x180002f1a  movzx   eax, word ptr [rdx]
0x180002f1d  cmp     [rdi+0F60h], ebp
0x180002f23  jz      short loc_180002F56
0x180002f25  jmp     short loc_180002F38
0x180002f27  movzx   eax, ax
0x180002f2a  lea     rdx, [rdx+2]
0x180002f2e  imul    r8d, 65h ; 'e'
0x180002f32  add     r8d, eax
0x180002f35  movzx   eax, word ptr [rdx]
0x180002f38  test    ax, ax
0x180002f3b  jnz     short loc_180002F27
0x180002f3d  jmp     short loc_180002F5B
0x180002f3f  movzx   ecx, ax
0x180002f42  lea     rdx, [rdx+2]
0x180002f46  movzx   eax, word ptr [rdx]
0x180002f49  and     ecx, 0FFDFh
0x180002f4f  imul    r8d, 65h ; 'e'
0x180002f53  add     r8d, ecx
0x180002f56  test    ax, ax
0x180002f59  jnz     short loc_180002F3F
0x180002f5b  mov     eax, r12d
0x180002f5e  mul     r8d
0x180002f61  shr     edx, 7
0x180002f64  imul    eax, edx, 83h
0x180002f6a  sub     r8d, eax
0x180002f6d  mov     rax, [rdi+r8*8+0B48h]
0x180002f75  mov     [r9+8], rax
0x180002f79  mov     [rdi+r8*8+0B48h], r9
0x180002f81  lea     r8, [rsp+48h+arg_0]; struct LOCK_ENTRY **
0x180002f86  mov     rdx, r15; struct IPubLock *
0x180002f89  mov     rcx, rbx; this
0x180002f8c  call    ?AddLock2@URI_LOCK_LIST@@QEAAJPEAVIPubLock@@PEAPEAULOCK_ENTRY@@@Z; URI_LOCK_LIST::AddLock2(IPubLock *,LOCK_ENTRY * *)
0x180002f91  mov     ebx, eax
0x180002f93  test    eax, eax
0x180002f95  js      loc_180003036
0x180002f9b  mov     r9, [rsp+48h+arg_0]
0x180002fa0  mov     r8d, ebp
0x180002fa3  add     r9, 10h
0x180002fa7  mov     rdx, [r9]
0x180002faa  cmp     [rdi+1380h], ebp
0x180002fb0  jz      short loc_180002FE7
0x180002fb2  jmp     short loc_180002FC9
0x180002fb4  mov     eax, 8007000Eh
0x180002fb9  jmp     short loc_180003038
0x180002fbb  imul    r8d, 65h ; 'e'
0x180002fbf  lea     rdx, [rdx+2]
0x180002fc3  movzx   ecx, cx
0x180002fc6  add     r8d, ecx
0x180002fc9  movzx   ecx, word ptr [rdx]
0x180002fcc  test    cx, cx
0x180002fcf  jnz     short loc_180002FBB
0x180002fd1  jmp     short loc_180002FEF
0x180002fd3  imul    r8d, 65h ; 'e'
0x180002fd7  lea     rdx, [rdx+2]
0x180002fdb  movzx   ecx, ax
0x180002fde  and     ecx, 0FFDFh
0x180002fe4  add     r8d, ecx
0x180002fe7  movzx   eax, word ptr [rdx]
0x180002fea  test    ax, ax
0x180002fed  jnz     short loc_180002FD3
0x180002fef  mov     eax, r12d
0x180002ff2  mov     rcx, r15
0x180002ff5  mul     r8d
0x180002ff8  shr     edx, 7
0x180002ffb  imul    eax, edx, 83h
0x180003001  sub     r8d, eax
0x180003004  mov     rax, [rdi+r8*8+0F68h]
0x18000300c  mov     [r9+8], rax
0x180003010  mov     [rdi+r8*8+0F68h], r9
0x180003018  mov     rax, [r15]
0x18000301b  mov     rax, [rax+48h]
0x18000301f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003024  test    eax, eax
0x180003026  jnz     short loc_180003030
0x180003028  inc     dword ptr [rdi+1388h]
0x18000302e  jmp     short loc_180003036
0x180003030  inc     dword ptr [rdi+138Ch]
0x180003036  mov     eax, ebx
0x180003038  mov     rbx, [rsp+48h+arg_8]
0x18000303d  mov     rbp, [rsp+48h+arg_10]
0x180003042  add     rsp, 20h
0x180003046  pop     r15
0x180003048  pop     r14
0x18000304a  pop     r12
0x18000304c  pop     rdi
0x18000304d  pop     rsi
0x18000304e  retn
```
