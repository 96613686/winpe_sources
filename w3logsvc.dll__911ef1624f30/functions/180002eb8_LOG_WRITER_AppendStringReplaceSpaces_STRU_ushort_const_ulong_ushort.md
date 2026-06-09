# LOG_WRITER::AppendStringReplaceSpaces(STRU *,ushort const *,ulong,ushort)

- ea: `0x180002eb8`
- end: `0x180002f40`
- name: `?AppendStringReplaceSpaces@LOG_WRITER@@AEAAJPEAVSTRU@@PEBGKG@Z`
- size: `136`
- prototype: `__int64 __fastcall(LOG_WRITER *this, struct STRU *, unsigned __int16 *, unsigned int, unsigned __int16)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023d8`
- `0x1800029c0`
- `0x180005f04`

## callees

- `0x180002eb8`

## import_xrefs

- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180002edc`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180002edc`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180002f2d`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180002f2d`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::AppendStringReplaceSpaces(
        LOG_WRITER *this,
        struct STRU *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 a5)
{
  unsigned int v6; // ebp
  int v9; // esi
  unsigned __int16 *v10; // r8
  unsigned int i; // ecx
  unsigned __int16 v12; // ax

  v6 = a4 + *((_DWORD *)a2 + 12);
  v9 = STRU::Resize(a2, 2 * v6 + 4);
  if ( v9 >= 0 )
  {
    v10 = (unsigned __int16 *)(*((_QWORD *)a2 + 4) + 2LL * *((unsigned int *)a2 + 12));
    for ( i = 0; i < a4; ++i )
    {
      v12 = *a3;
      if ( *a3 <= 0x20u || v12 == 127 )
        v12 = a5;
      *v10 = v12;
      ++a3;
      ++v10;
    }
    *v10 = 32;
    STRU::SetLen(a2, v6 + 1);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002eb8  push    rbx
0x180002eba  push    rbp
0x180002ebb  push    rsi
0x180002ebc  push    rdi
0x180002ebd  push    r14
0x180002ebf  sub     rsp, 20h
0x180002ec3  mov     ebp, [rdx+30h]
0x180002ec6  mov     rbx, rdx
0x180002ec9  add     ebp, r9d
0x180002ecc  mov     rcx, rbx
0x180002ecf  mov     r14d, r9d
0x180002ed2  mov     rdi, r8
0x180002ed5  lea     edx, ds:4[rbp*2]
0x180002edc  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180002ee2  mov     esi, eax
0x180002ee4  test    eax, eax
0x180002ee6  js      short loc_180002F33
0x180002ee8  mov     rcx, [rbx+20h]
0x180002eec  mov     edx, [rbx+30h]
0x180002eef  lea     r8, [rcx+rdx*2]
0x180002ef3  xor     ecx, ecx
0x180002ef5  lea     edx, [rcx+20h]
0x180002ef8  test    r14d, r14d
0x180002efb  jz      short loc_180002F23
0x180002efd  movzx   eax, word ptr [rdi]
0x180002f00  cmp     ax, dx
0x180002f03  jbe     short loc_180002F0B
0x180002f05  cmp     ax, 7Fh
0x180002f09  jnz     short loc_180002F10
0x180002f0b  movzx   eax, [rsp+48h+arg_20]
0x180002f10  mov     [r8], ax
0x180002f14  add     rdi, 2
0x180002f18  add     r8, 2
0x180002f1c  inc     ecx
0x180002f1e  cmp     ecx, r14d
0x180002f21  jb      short loc_180002EFD
0x180002f23  mov     [r8], dx
0x180002f27  mov     rcx, rbx
0x180002f2a  lea     edx, [rbp+1]
0x180002f2d  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180002f33  mov     eax, esi
0x180002f35  add     rsp, 20h
0x180002f39  pop     r14
0x180002f3b  pop     rdi
0x180002f3c  pop     rsi
0x180002f3d  pop     rbp
0x180002f3e  pop     rbx
0x180002f3f  retn
```
