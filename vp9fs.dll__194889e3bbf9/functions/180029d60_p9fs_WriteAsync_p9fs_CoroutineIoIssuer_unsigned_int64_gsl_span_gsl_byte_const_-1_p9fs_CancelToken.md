# p9fs::WriteAsync(p9fs::CoroutineIoIssuer &,unsigned __int64,gsl::span<gsl::byte const,-1>,p9fs::CancelToken &)

- ea: `0x180029d60`
- end: `0x180029e34`
- name: `?WriteAsync@p9fs@@YA?AV?$Task@UIoResult@p9fs@@@1@AEAUCoroutineIoIssuer@1@_KV?$span@$$CBW4byte@gsl@@$0?0@gsl@@AEAVCancelToken@1@@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800221d0`

## callees

- `0x180004120`
- `0x180004144`
- `0x180029be0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180029dfe`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180029dfe`

## pseudocode

```c
_QWORD *__fastcall p9fs::WriteAsync(_QWORD *a1, __int64 a2, __int64 a3, _OWORD *a4, __int64 a5)
{
  char *v9; // rax
  char *v10; // rbx

  v9 = (char *)operator new(0x110u);
  v10 = v9 + 48;
  *((_QWORD *)v9 + 29) = a2;
  *((_QWORD *)v9 + 30) = a3;
  *(_OWORD *)(v9 + 248) = *a4;
  *((_QWORD *)v9 + 33) = a5;
  *((_QWORD *)v9 + 6) = p9fs::WriteAsync__ResumeCoro_1;
  *((_DWORD *)v9 + 14) = 65538;
  *(_DWORD *)(v9 + 9) = 0;
  *(_WORD *)(v9 + 13) = 0;
  v9[15] = 0;
  *((_QWORD *)v9 + 4) = 0;
  *(_QWORD *)v9 = 0;
  v9[8] = 0;
  *((_QWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 3) = 0;
  __ExceptionPtrCreate(v9 + 16);
  *a1 = v10;
  v10[176] = 0;
  p9fs::WriteAsync__ResumeCoro_1(v10);
  return a1;
}

```

## disassembly

```asm
0x180029d60  push    rbx
0x180029d62  push    rbp
0x180029d63  push    rsi
0x180029d64  push    rdi
0x180029d65  push    r14
0x180029d67  push    r15
0x180029d69  sub     rsp, 58h
0x180029d6d  mov     rax, cs:__security_cookie
0x180029d74  xor     rax, rsp
0x180029d77  mov     [rsp+88h+var_48], rax
0x180029d7c  mov     rsi, r9
0x180029d7f  mov     rbp, r8
0x180029d82  mov     r14, rdx
0x180029d85  mov     rdi, rcx
0x180029d88  mov     [rsp+88h+var_60], rcx
0x180029d8d  mov     r15d, 0B0h
0x180029d93  lea     rcx, [r15+60h]; Size
0x180029d97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029d9c  mov     [rsp+88h+var_68], rax
0x180029da1  lea     rbx, [rax+30h]
0x180029da5  mov     [rsp+88h+var_68], rbx
0x180029daa  mov     [rbx+r15+8], r14
0x180029daf  mov     [rbx+r15+10h], rbp
0x180029db4  movups  xmm0, xmmword ptr [rsi]
0x180029db7  movdqu  xmmword ptr [rbx+r15+18h], xmm0
0x180029dbe  mov     rax, [rsp+88h+arg_20]
0x180029dc6  mov     [rbx+r15+28h], rax
0x180029dcb  lea     rax, p9fs__WriteAsync$_ResumeCoro$1
0x180029dd2  mov     [rbx], rax
0x180029dd5  mov     dword ptr [rbx+8], 10002h
0x180029ddc  xor     edx, edx
0x180029dde  mov     [rbx-27h], edx
0x180029de1  mov     [rbx-23h], dx
0x180029de5  mov     [rbx-21h], dl
0x180029de8  mov     [rbx-10h], rdx
0x180029dec  mov     [rbx-30h], rdx
0x180029df0  mov     [rbx-28h], dl
0x180029df3  lea     rcx, [rbx-20h]
0x180029df7  mov     [rcx], rdx
0x180029dfa  mov     [rcx+8], rdx
0x180029dfe  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180029e04  nop
0x180029e05  mov     [rdi], rbx
0x180029e08  xor     eax, eax
0x180029e0a  mov     [rbx+r15], al
0x180029e0e  mov     rcx, rbx
0x180029e11  call    p9fs__WriteAsync$_ResumeCoro$1
0x180029e16  nop
0x180029e17  mov     rax, rdi
0x180029e1a  mov     rcx, [rsp+88h+var_48]
0x180029e1f  xor     rcx, rsp; StackCookie
0x180029e22  call    __security_check_cookie
0x180029e27  add     rsp, 58h
0x180029e2b  pop     r15
0x180029e2d  pop     r14
0x180029e2f  pop     rdi
0x180029e30  pop     rsi
0x180029e31  pop     rbp
0x180029e32  pop     rbx
0x180029e33  retn
```
