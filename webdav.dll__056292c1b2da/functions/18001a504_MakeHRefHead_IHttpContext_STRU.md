# MakeHRefHead(IHttpContext *,STRU *)

- ea: `0x18001a504`
- end: `0x18001a642`
- name: `?MakeHRefHead@@YAJPEAVIHttpContext@@PEAVSTRU@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct STRU *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003c4c`

## callees

- `0x18001a504`
- `0x180023010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001a58a`
- `msvcrt!wcsrchr` at `0x18001a58a`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001a62f`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001a62f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001a56a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001a56a`

## pseudocode

```c
__int64 __fastcall MakeHRefHead(struct IHttpContext *a1, struct STRU *a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  int v5; // ecx
  const unsigned __int16 *v6; // rdx
  unsigned __int16 v7; // ax
  unsigned __int16 *v8; // r8
  unsigned int v9; // edi
  __int64 v10; // rbx
  wchar_t *v11; // rdx
  __int16 v12; // ax

  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  v5 = 0;
  v6 = *(const unsigned __int16 **)(v4 + 72);
  v7 = *v6;
  v8 = (unsigned __int16 *)(v6 + 1);
  while ( v7 )
  {
    if ( v7 == 47 && ++v5 == 3 )
    {
      --v8;
      break;
    }
    v7 = *v8++;
  }
  v9 = STRU::Copy(a2, v6, v8 - v6);
  if ( (v9 & 0x80000000) == 0 )
  {
    v10 = *((_QWORD *)a2 + 4);
    v11 = wcsrchr((const wchar_t *)v10, 0x3Au);
    if ( v11 )
    {
      if ( ((*(_WORD *)v10 - 72) & 0xFFDF) == 0
        && ((*(_WORD *)(v10 + 2) - 84) & 0xFFDF) == 0
        && ((*(_WORD *)(v10 + 4) - 84) & 0xFFDF) == 0
        && ((*(_WORD *)(v10 + 6) - 80) & 0xFFDF) == 0 )
      {
        v12 = *(_WORD *)(v10 + 8);
        if ( v12 == 58 )
        {
          if ( v11[1] != 56 || v11[2] != 48 || v11[3] )
            return v9;
LABEL_25:
          *v11 = 0;
          STRU::SyncWithBuffer(a2);
          return v9;
        }
        if ( ((v12 - 83) & 0xFFDF) == 0
          && *(_WORD *)(v10 + 10) == 58
          && v11[1] == 52
          && v11[2] == 52
          && v11[3] == 51
          && !v11[4] )
        {
          goto LABEL_25;
        }
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18001a504  push    rbx
0x18001a506  push    rbp
0x18001a507  push    rsi
0x18001a508  push    rdi
0x18001a509  push    r14
0x18001a50b  sub     rsp, 20h
0x18001a50f  mov     rax, [rcx]
0x18001a512  mov     rsi, rdx
0x18001a515  mov     rax, [rax+18h]
0x18001a519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a51e  mov     r8, rax
0x18001a521  mov     rcx, [rax]
0x18001a524  mov     rax, [rcx+8]
0x18001a528  mov     rcx, r8
0x18001a52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a530  xor     ebp, ebp
0x18001a532  mov     ecx, ebp
0x18001a534  mov     rdx, [rax+48h]
0x18001a538  movzx   eax, word ptr [rdx]
0x18001a53b  lea     r8, [rdx+2]
0x18001a53f  jmp     short loc_18001A556
0x18001a541  cmp     ax, 2Fh ; '/'
0x18001a545  jnz     short loc_18001A54E
0x18001a547  inc     ecx
0x18001a549  cmp     ecx, 3
0x18001a54c  jz      short loc_18001A55D
0x18001a54e  movzx   eax, word ptr [r8]
0x18001a552  add     r8, 2
0x18001a556  test    ax, ax
0x18001a559  jnz     short loc_18001A541
0x18001a55b  jmp     short loc_18001A561
0x18001a55d  sub     r8, 2
0x18001a561  sub     r8, rdx
0x18001a564  mov     rcx, rsi
0x18001a567  sar     r8, 1
0x18001a56a  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001a570  mov     edi, eax
0x18001a572  test    eax, eax
0x18001a574  js      loc_18001A635
0x18001a57a  mov     rbx, [rsi+20h]
0x18001a57e  mov     r14d, 3Ah ; ':'
0x18001a584  mov     edx, r14d; Ch
0x18001a587  mov     rcx, rbx; Str
0x18001a58a  call    cs:__imp_wcsrchr
0x18001a590  mov     rdx, rax
0x18001a593  test    rax, rax
0x18001a596  jz      loc_18001A635
0x18001a59c  movzx   ecx, word ptr [rbx]
0x18001a59f  mov     r8d, 0FFDFh
0x18001a5a5  sub     cx, 48h ; 'H'
0x18001a5a9  test    r8w, cx
0x18001a5ad  jnz     loc_18001A635
0x18001a5b3  movzx   ecx, word ptr [rbx+2]
0x18001a5b7  sub     cx, 54h ; 'T'
0x18001a5bb  test    r8w, cx
0x18001a5bf  jnz     short loc_18001A635
0x18001a5c1  movzx   eax, word ptr [rbx+4]
0x18001a5c5  sub     ax, 54h ; 'T'
0x18001a5c9  test    r8w, ax
0x18001a5cd  jnz     short loc_18001A635
0x18001a5cf  movzx   eax, word ptr [rbx+6]
0x18001a5d3  sub     ax, 50h ; 'P'
0x18001a5d7  test    r8w, ax
0x18001a5db  jnz     short loc_18001A635
0x18001a5dd  movzx   eax, word ptr [rbx+8]
0x18001a5e1  cmp     ax, r14w
0x18001a5e5  jnz     short loc_18001A5FD
0x18001a5e7  cmp     word ptr [rdx+2], 38h ; '8'
0x18001a5ec  jnz     short loc_18001A635
0x18001a5ee  cmp     word ptr [rdx+4], 30h ; '0'
0x18001a5f3  jnz     short loc_18001A635
0x18001a5f5  cmp     [rdx+6], bp
0x18001a5f9  jz      short loc_18001A629
0x18001a5fb  jmp     short loc_18001A635
0x18001a5fd  sub     ax, 53h ; 'S'
0x18001a601  test    r8w, ax
0x18001a605  jnz     short loc_18001A635
0x18001a607  cmp     [rbx+0Ah], r14w
0x18001a60c  jnz     short loc_18001A635
0x18001a60e  cmp     word ptr [rdx+2], 34h ; '4'
0x18001a613  jnz     short loc_18001A635
0x18001a615  cmp     word ptr [rdx+4], 34h ; '4'
0x18001a61a  jnz     short loc_18001A635
0x18001a61c  cmp     word ptr [rdx+6], 33h ; '3'
0x18001a621  jnz     short loc_18001A635
0x18001a623  cmp     [rdx+8], bp
0x18001a627  jnz     short loc_18001A635
0x18001a629  mov     rcx, rsi
0x18001a62c  mov     [rdx], bp
0x18001a62f  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001a635  mov     eax, edi
0x18001a637  add     rsp, 20h
0x18001a63b  pop     r14
0x18001a63d  pop     rdi
0x18001a63e  pop     rsi
0x18001a63f  pop     rbp
0x18001a640  pop     rbx
0x18001a641  retn
```
