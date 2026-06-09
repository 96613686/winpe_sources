# GetAngleBracketString(char const * *,STRA *,STRU *)

- ea: `0x18001c3c8`
- end: `0x18001c45a`
- name: `?GetAngleBracketString@@YAJPEAPEBDPEAVSTRA@@PEAVSTRU@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(const char **, struct STRA *, struct STRU *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007294`
- `0x18000a4cc`
- `0x18000a7d4`

## callees

- `0x18001c3c8`

## import_xrefs

- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18001c422`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18001c422`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18001c43d`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18001c43d`

## pseudocode

```c
int __fastcall GetAngleBracketString(const char **a1, struct STRA *a2, struct STRU *a3)
{
  unsigned __int64 v3; // rax
  const char *v5; // rdi
  const char *v7; // rbx
  __int64 v8; // rcx
  int result; // eax

  v5 = *a1 + 1;
  v7 = v5;
  for ( LOBYTE(v3) = *v5; (_BYTE)v3; LOBYTE(v3) = *v7 )
  {
    if ( (unsigned __int8)v3 <= 0x3Eu )
    {
      v8 = 0x4000000100000201LL;
      if ( _bittest64(&v8, v3) )
        break;
    }
    ++v7;
  }
  if ( *v7 != 62 )
    return -2147024809;
  if ( !a2 || (result = STRA::Copy(a2, v5, (_DWORD)v7 - (_DWORD)v5), result >= 0) )
  {
    if ( !a3 || (result = STRU::CopyA(a3, v5, (_DWORD)v7 - (_DWORD)v5), result >= 0) )
    {
      *a1 = v7 + 1;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001c3c8  push    rbx
0x18001c3ca  push    rsi
0x18001c3cb  push    rdi
0x18001c3cc  push    r14
0x18001c3ce  sub     rsp, 28h
0x18001c3d2  mov     rdi, [rcx]
0x18001c3d5  mov     rsi, r8
0x18001c3d8  inc     rdi
0x18001c3db  mov     r9, rdx
0x18001c3de  mov     r14, rcx
0x18001c3e1  mov     rbx, rdi
0x18001c3e4  mov     al, [rdi]
0x18001c3e6  jmp     short loc_18001C401
0x18001c3e8  cmp     al, 3Eh ; '>'
0x18001c3ea  ja      short loc_18001C3FC
0x18001c3ec  mov     rcx, 4000000100000201h
0x18001c3f6  bt      rcx, rax
0x18001c3fa  jb      short loc_18001C405
0x18001c3fc  inc     rbx
0x18001c3ff  mov     al, [rbx]
0x18001c401  test    al, al
0x18001c403  jnz     short loc_18001C3E8
0x18001c405  cmp     byte ptr [rbx], 3Eh ; '>'
0x18001c408  jz      short loc_18001C411
0x18001c40a  mov     eax, 80070057h
0x18001c40f  jmp     short loc_18001C450
0x18001c411  test    r9, r9
0x18001c414  jz      short loc_18001C42C
0x18001c416  mov     r8d, ebx
0x18001c419  mov     rdx, rdi
0x18001c41c  sub     r8d, edi
0x18001c41f  mov     rcx, r9
0x18001c422  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18001c428  test    eax, eax
0x18001c42a  js      short loc_18001C450
0x18001c42c  test    rsi, rsi
0x18001c42f  jz      short loc_18001C447
0x18001c431  mov     r8d, ebx
0x18001c434  mov     rdx, rdi
0x18001c437  sub     r8d, edi
0x18001c43a  mov     rcx, rsi
0x18001c43d  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x18001c443  test    eax, eax
0x18001c445  js      short loc_18001C450
0x18001c447  lea     rax, [rbx+1]
0x18001c44b  mov     [r14], rax
0x18001c44e  xor     eax, eax
0x18001c450  add     rsp, 28h
0x18001c454  pop     r14
0x18001c456  pop     rdi
0x18001c457  pop     rsi
0x18001c458  pop     rbx
0x18001c459  retn
```
