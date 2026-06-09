# p9fs::ReadAsync(p9fs::CoroutineIoIssuer &,unsigned __int64,gsl::span<gsl::byte,-1>,p9fs::CancelToken &)

- ea: `0x180029770`
- end: `0x180029844`
- name: `?ReadAsync@p9fs@@YA?AV?$Task@UIoResult@p9fs@@@1@AEAUCoroutineIoIssuer@1@_KV?$span@W4byte@gsl@@$0?0@gsl@@AEAVCancelToken@1@@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020600`

## callees

- `0x180004120`
- `0x180004144`
- `0x1800295f0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002980e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002980e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall p9fs::ReadAsync(_QWORD *a1, __int64 a2, __int64 a3, _OWORD *a4, __int64 a5)
{
  char *v9; // rax
  char *v10; // rbx

  v9 = (char *)operator new(0x110u);
  v10 = v9 + 48;
  *((_QWORD *)v9 + 29) = a2;
  *((_QWORD *)v9 + 30) = a3;
  *(_OWORD *)(v9 + 248) = *a4;
  *((_QWORD *)v9 + 33) = a5;
  *((_QWORD *)v9 + 6) = p9fs::ReadAsync__ResumeCoro_1;
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
  p9fs::ReadAsync__ResumeCoro_1(v10);
  return a1;
}

```

## disassembly

```asm
0x180029770  push    rbx
0x180029772  push    rbp
0x180029773  push    rsi
0x180029774  push    rdi
0x180029775  push    r14
0x180029777  push    r15
0x180029779  sub     rsp, 58h
0x18002977d  mov     rax, cs:__security_cookie
0x180029784  xor     rax, rsp
0x180029787  mov     [rsp+88h+var_48], rax
0x18002978c  mov     rsi, r9
0x18002978f  mov     rbp, r8
0x180029792  mov     r14, rdx
0x180029795  mov     rdi, rcx
0x180029798  mov     [rsp+88h+var_60], rcx
0x18002979d  mov     r15d, 0B0h
0x1800297a3  lea     rcx, [r15+60h]; Size
0x1800297a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800297ac  mov     [rsp+88h+var_68], rax
0x1800297b1  lea     rbx, [rax+30h]
0x1800297b5  mov     [rsp+88h+var_68], rbx
0x1800297ba  mov     [rbx+r15+8], r14
0x1800297bf  mov     [rbx+r15+10h], rbp
0x1800297c4  movups  xmm0, xmmword ptr [rsi]
0x1800297c7  movdqu  xmmword ptr [rbx+r15+18h], xmm0
0x1800297ce  mov     rax, [rsp+88h+arg_20]
0x1800297d6  mov     [rbx+r15+28h], rax
0x1800297db  lea     rax, p9fs__ReadAsync$_ResumeCoro$1
0x1800297e2  mov     [rbx], rax
0x1800297e5  mov     dword ptr [rbx+8], 10002h
0x1800297ec  xor     edx, edx
0x1800297ee  mov     [rbx-27h], edx
0x1800297f1  mov     [rbx-23h], dx
0x1800297f5  mov     [rbx-21h], dl
0x1800297f8  mov     [rbx-10h], rdx
0x1800297fc  mov     [rbx-30h], rdx
0x180029800  mov     [rbx-28h], dl
0x180029803  lea     rcx, [rbx-20h]
0x180029807  mov     [rcx], rdx
0x18002980a  mov     [rcx+8], rdx
0x18002980e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180029814  nop
0x180029815  mov     [rdi], rbx
0x180029818  xor     eax, eax
0x18002981a  mov     [rbx+r15], al
0x18002981e  mov     rcx, rbx
0x180029821  call    p9fs__ReadAsync$_ResumeCoro$1
0x180029826  nop
0x180029827  mov     rax, rdi
0x18002982a  mov     rcx, [rsp+88h+var_48]
0x18002982f  xor     rcx, rsp; StackCookie
0x180029832  call    __security_check_cookie
0x180029837  add     rsp, 58h
0x18002983b  pop     r15
0x18002983d  pop     r14
0x18002983f  pop     rdi
0x180029840  pop     rsi
0x180029841  pop     rbp
0x180029842  pop     rbx
0x180029843  retn
```
