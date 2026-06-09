# p9fs::Socket::AcceptAsync(p9fs::CancelToken &)

- ea: `0x18002b570`
- end: `0x18002b63c`
- name: `?AcceptAsync@Socket@p9fs@@UEAA?AV?$Task@V?$unique_ptr@VISocket@p9fs@@U?$default_delete@VISocket@p9fs@@@std@@@std@@@2@AEAVCancelToken@2@@Z`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004120`
- `0x180004144`
- `0x18002b190`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b5fb`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b5fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall p9fs::Socket::AcceptAsync(__int64 a1, _QWORD *a2, __int64 a3)
{
  char *v6; // rax
  char *v7; // rbx

  v6 = (char *)operator new(0x140u);
  v7 = v6 + 48;
  *((_QWORD *)v6 + 37) = a1;
  *((_QWORD *)v6 + 38) = a3;
  *((_QWORD *)v6 + 6) = p9fs::Socket::AcceptAsync__ResumeCoro_1;
  *((_DWORD *)v6 + 14) = 65538;
  *(_DWORD *)(v6 + 9) = 0;
  *(_WORD *)(v6 + 13) = 0;
  v6[15] = 0;
  *((_QWORD *)v6 + 4) = 0;
  *(_QWORD *)v6 = 0;
  v6[8] = 0;
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  __ExceptionPtrCreate(v6 + 16);
  *((_QWORD *)v7 - 2) = 0;
  *a2 = v7;
  v7[240] = 0;
  p9fs::Socket::AcceptAsync__ResumeCoro_1(v7);
  return a2;
}

```

## disassembly

```asm
0x18002b570  mov     [rsp+arg_0], rbx
0x18002b575  mov     [rsp+arg_10], rbp
0x18002b57a  push    rsi
0x18002b57b  push    rdi
0x18002b57c  push    r14
0x18002b57e  sub     rsp, 50h
0x18002b582  mov     rax, cs:__security_cookie
0x18002b589  xor     rax, rsp
0x18002b58c  mov     [rsp+68h+var_28], rax
0x18002b591  mov     rsi, r8
0x18002b594  mov     rdi, rdx
0x18002b597  mov     rbp, rcx
0x18002b59a  mov     [rsp+68h+var_40], rdx
0x18002b59f  mov     r14d, 0F0h
0x18002b5a5  lea     rcx, [r14+50h]; Size
0x18002b5a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b5ae  mov     [rsp+68h+var_48], rax
0x18002b5b3  lea     rbx, [rax+30h]
0x18002b5b7  mov     [rsp+68h+var_48], rbx
0x18002b5bc  mov     [rbx+r14+8], rbp
0x18002b5c1  mov     [rbx+r14+10h], rsi
0x18002b5c6  lea     rax, p9fs__Socket__AcceptAsync$_ResumeCoro$1
0x18002b5cd  mov     [rbx], rax
0x18002b5d0  mov     dword ptr [rbx+8], 10002h
0x18002b5d7  xor     esi, esi
0x18002b5d9  mov     [rbx-27h], esi
0x18002b5dc  mov     [rbx-23h], si
0x18002b5e0  mov     [rbx-21h], sil
0x18002b5e4  mov     [rbx-10h], rsi
0x18002b5e8  mov     [rbx-30h], rsi
0x18002b5ec  mov     [rbx-28h], sil
0x18002b5f0  lea     rcx, [rbx-20h]
0x18002b5f4  mov     [rcx], rsi
0x18002b5f7  mov     [rcx+8], rsi
0x18002b5fb  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002b601  mov     [rbx-10h], rsi
0x18002b605  mov     [rdi], rbx
0x18002b608  xor     eax, eax
0x18002b60a  mov     [rbx+r14], al
0x18002b60e  mov     rcx, rbx
0x18002b611  call    p9fs__Socket__AcceptAsync$_ResumeCoro$1
0x18002b616  nop
0x18002b617  mov     rax, rdi
0x18002b61a  mov     rcx, [rsp+68h+var_28]
0x18002b61f  xor     rcx, rsp; StackCookie
0x18002b622  call    __security_check_cookie
0x18002b627  lea     r11, [rsp+68h+var_18]
0x18002b62c  mov     rbx, [r11+20h]
0x18002b630  mov     rbp, [r11+30h]
0x18002b634  mov     rsp, r11
0x18002b637  pop     r14
0x18002b639  pop     rdi
0x18002b63a  pop     rsi
0x18002b63b  retn
```
