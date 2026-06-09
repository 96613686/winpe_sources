# p9fs::Handler::ProcessMessage(p9fs::SpanReader &,p9fs::Handler::MessageResponse &)

- ea: `0x180017a44`
- end: `0x180017b02`
- name: `?ProcessMessage@Handler@p9fs@@AEAA?AV?$Task@X@2@AEAVSpanReader@2@AEAVMessageResponse@12@@Z`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000ef00`
- `0x180017570`

## callees

- `0x180004120`
- `0x180004144`
- `0x180017090`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180017acc`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180017acc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall p9fs::Handler::ProcessMessage(__int64 a1, __int64 *a2, __int64 a3, __int64 a4)
{
  char *v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  const char *v12; // r9

  v8 = (char *)operator new(0x4D0u);
  v9 = (__int64)(v8 + 32);
  *((_QWORD *)v8 + 151) = a1;
  *((_QWORD *)v8 + 152) = a3;
  *((_QWORD *)v8 + 153) = a4;
  *((_QWORD *)v8 + 4) = p9fs::Handler::ProcessMessage__ResumeCoro_1;
  *((_DWORD *)v8 + 10) = 65538;
  *(_DWORD *)(v8 + 9) = 0;
  *(_WORD *)(v8 + 13) = 0;
  v8[15] = 0;
  *(_QWORD *)v8 = 0;
  v8[8] = 0;
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  __ExceptionPtrCreate(v8 + 16);
  *a2 = v9;
  *(_BYTE *)(v9 + 1168) = 0;
  p9fs::Handler::ProcessMessage__ResumeCoro_1(v9, v10, v11, v12);
  return a2;
}

```

## disassembly

```asm
0x180017a44  push    rbx
0x180017a46  push    rbp
0x180017a47  push    rsi
0x180017a48  push    rdi
0x180017a49  push    r14
0x180017a4b  push    r15
0x180017a4d  sub     rsp, 58h
0x180017a51  mov     rax, cs:__security_cookie
0x180017a58  xor     rax, rsp
0x180017a5b  mov     [rsp+88h+var_48], rax
0x180017a60  mov     rsi, r9
0x180017a63  mov     rbp, r8
0x180017a66  mov     rdi, rdx
0x180017a69  mov     r14, rcx
0x180017a6c  mov     [rsp+88h+var_60], rdx
0x180017a71  mov     r15d, 490h
0x180017a77  lea     rcx, [r15+40h]; Size
0x180017a7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017a80  mov     [rsp+88h+var_68], rax
0x180017a85  lea     rbx, [rax+20h]
0x180017a89  mov     [rsp+88h+var_68], rbx
0x180017a8e  mov     [rbx+r15+8], r14
0x180017a93  mov     [rbx+r15+10h], rbp
0x180017a98  mov     [rbx+r15+18h], rsi
0x180017a9d  lea     rax, p9fs__Handler__ProcessMessage$_ResumeCoro$1
0x180017aa4  mov     [rbx], rax
0x180017aa7  mov     dword ptr [rbx+8], 10002h
0x180017aae  xor     edx, edx
0x180017ab0  mov     [rbx-17h], edx
0x180017ab3  mov     [rbx-13h], dx
0x180017ab7  mov     [rbx-11h], dl
0x180017aba  mov     [rbx-20h], rdx
0x180017abe  mov     [rbx-18h], dl
0x180017ac1  lea     rcx, [rbx-10h]
0x180017ac5  mov     [rcx], rdx
0x180017ac8  mov     [rcx+8], rdx
0x180017acc  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180017ad2  nop
0x180017ad3  mov     [rdi], rbx
0x180017ad6  xor     eax, eax
0x180017ad8  mov     [rbx+r15], al
0x180017adc  mov     rcx, rbx
0x180017adf  call    p9fs__Handler__ProcessMessage$_ResumeCoro$1
0x180017ae4  nop
0x180017ae5  mov     rax, rdi
0x180017ae8  mov     rcx, [rsp+88h+var_48]
0x180017aed  xor     rcx, rsp; StackCookie
0x180017af0  call    __security_check_cookie
0x180017af5  add     rsp, 58h
0x180017af9  pop     r15
0x180017afb  pop     r14
0x180017afd  pop     rdi
0x180017afe  pop     rsi
0x180017aff  pop     rbp
0x180017b00  pop     rbx
0x180017b01  retn
```
