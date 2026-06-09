# HexEncodeString(ushort const *,STRU *)

- ea: `0x180002f0c`
- end: `0x180002fca`
- name: `?HexEncodeString@@YAJPEBGPEAVSTRU@@@Z`
- size: `190`
- prototype: `int __fastcall(const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b34`

## callees

- `0x180002f0c`

## import_xrefs

- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180002fb2`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180002fb2`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180002f3a`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180002f3a`

## pseudocode

```c
int __fastcall HexEncodeString(const unsigned __int16 *a1, struct STRU *a2)
{
  __int64 v4; // rdx
  int result; // eax
  unsigned __int16 v6; // ax
  const unsigned __int16 *v7; // rbx
  _WORD *i; // rdx

  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  result = STRU::Resize(a2, 8 * v4 + 2);
  if ( result >= 0 )
  {
    v6 = *a1;
    v7 = a1 + 1;
    for ( i = (_WORD *)*((_QWORD *)a2 + 4); v6; ++v7 )
    {
      *i = a0123456789abcd[(unsigned __int64)v6 >> 12];
      i[1] = a0123456789abcd[((unsigned __int64)v6 >> 8) & 0xF];
      i[2] = a0123456789abcd[((unsigned __int64)v6 >> 4) & 0xF];
      i[3] = a0123456789abcd[v6 & 0xF];
      i += 4;
      v6 = *v7;
    }
    *i = 0;
    STRU::SyncWithBuffer(a2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002f0c  mov     [rsp+arg_0], rbx
0x180002f11  mov     [rsp+arg_8], rsi
0x180002f16  push    rdi
0x180002f17  sub     rsp, 20h
0x180002f1b  mov     rdi, rdx
0x180002f1e  mov     rbx, rcx
0x180002f21  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002f25  xor     esi, esi
0x180002f27  inc     rdx
0x180002f2a  cmp     [rcx+rdx*2], si
0x180002f2e  jnz     short loc_180002F27
0x180002f30  lea     edx, ds:2[rdx*8]
0x180002f37  mov     rcx, rdi
0x180002f3a  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180002f40  test    eax, eax
0x180002f42  js      short loc_180002FBA
0x180002f44  movzx   eax, word ptr [rbx]
0x180002f47  add     rbx, 2
0x180002f4b  mov     rdx, [rdi+20h]
0x180002f4f  test    ax, ax
0x180002f52  jz      short loc_180002FAC
0x180002f54  lea     r8, a0123456789abcd; "0123456789ABCDEF"
0x180002f5b  movzx   ecx, ax
0x180002f5e  mov     eax, ecx
0x180002f60  shr     rax, 0Ch
0x180002f64  movzx   eax, word ptr [r8+rax*2]
0x180002f69  mov     [rdx], ax
0x180002f6c  mov     eax, ecx
0x180002f6e  shr     rax, 8
0x180002f72  and     eax, 0Fh
0x180002f75  movzx   eax, word ptr [r8+rax*2]
0x180002f7a  mov     [rdx+2], ax
0x180002f7e  mov     eax, ecx
0x180002f80  shr     rax, 4
0x180002f84  and     ecx, 0Fh
0x180002f87  and     eax, 0Fh
0x180002f8a  movzx   eax, word ptr [r8+rax*2]
0x180002f8f  mov     [rdx+4], ax
0x180002f93  movzx   eax, word ptr [r8+rcx*2]
0x180002f98  mov     [rdx+6], ax
0x180002f9c  add     rdx, 8
0x180002fa0  movzx   eax, word ptr [rbx]
0x180002fa3  lea     rbx, [rbx+2]
0x180002fa7  test    ax, ax
0x180002faa  jnz     short loc_180002F5B
0x180002fac  mov     rcx, rdi
0x180002faf  mov     [rdx], si
0x180002fb2  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180002fb8  xor     eax, eax
0x180002fba  mov     rbx, [rsp+28h+arg_0]
0x180002fbf  mov     rsi, [rsp+28h+arg_8]
0x180002fc4  add     rsp, 20h
0x180002fc8  pop     rdi
0x180002fc9  retn
```
