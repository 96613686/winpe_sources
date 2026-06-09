# p9fs::BlockingCode<_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_>(_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_)

- ea: `0x18000ccb8`
- end: `0x18000cd6c`
- name: `??$BlockingCode@V_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_@@@p9fs@@YA?AV?$Task@J@0@V_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_@@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012700`

## callees

- `0x180004120`
- `0x180004144`
- `0x18000cab0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000cd3b`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000cd3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall p9fs::BlockingCode<_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_>(_QWORD *a1, _OWORD *a2)
{
  char *v4; // rax
  char *v5; // rbx

  v4 = (char *)operator new(0xB0u);
  v5 = v4 + 48;
  *(_OWORD *)(v4 + 136) = *a2;
  *(_OWORD *)(v4 + 152) = a2[1];
  *((_QWORD *)v4 + 6) = p9fs::BlockingCode__ResumeCoro_1__lambda_ba3c1d9efddbfd0bb9bd71913ea5c746___;
  *((_DWORD *)v4 + 14) = 65538;
  *(_DWORD *)(v4 + 9) = 0;
  *(_WORD *)(v4 + 13) = 0;
  v4[15] = 0;
  *((_QWORD *)v4 + 4) = 0;
  *(_QWORD *)v4 = 0;
  v4[8] = 0;
  *((_QWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 3) = 0;
  __ExceptionPtrCreate(v4 + 16);
  *a1 = v5;
  v5[80] = 0;
  p9fs::BlockingCode__ResumeCoro_1__lambda_ba3c1d9efddbfd0bb9bd71913ea5c746___(v5);
  return a1;
}

```

## disassembly

```asm
0x18000ccb8  push    rbx
0x18000ccba  push    rbp
0x18000ccbb  push    rsi
0x18000ccbc  push    rdi
0x18000ccbd  sub     rsp, 58h
0x18000ccc1  mov     rax, cs:__security_cookie
0x18000ccc8  xor     rax, rsp
0x18000cccb  mov     [rsp+78h+var_38], rax
0x18000ccd0  mov     rsi, rdx
0x18000ccd3  mov     rdi, rcx
0x18000ccd6  mov     [rsp+78h+var_50], rcx
0x18000ccdb  mov     ebp, 50h ; 'P'
0x18000cce0  lea     rcx, [rbp+60h]; Size
0x18000cce4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cce9  mov     [rsp+78h+var_58], rax
0x18000ccee  lea     rbx, [rax+30h]
0x18000ccf2  mov     [rsp+78h+var_58], rbx
0x18000ccf7  movups  xmm0, xmmword ptr [rsi]
0x18000ccfa  movups  xmmword ptr [rbx+rbp+8], xmm0
0x18000ccff  movups  xmm1, xmmword ptr [rsi+10h]
0x18000cd03  movups  xmmword ptr [rbx+rbp+18h], xmm1
0x18000cd08  lea     rax, p9fs__BlockingCode$_ResumeCoro$1__lambda_ba3c1d9efddbfd0bb9bd71913ea5c746___
0x18000cd0f  mov     [rbx], rax
0x18000cd12  mov     dword ptr [rbx+8], 10002h
0x18000cd19  xor     edx, edx
0x18000cd1b  mov     [rbx-27h], edx
0x18000cd1e  mov     [rbx-23h], dx
0x18000cd22  mov     [rbx-21h], dl
0x18000cd25  mov     [rbx-10h], rdx
0x18000cd29  mov     [rbx-30h], rdx
0x18000cd2d  mov     [rbx-28h], dl
0x18000cd30  lea     rcx, [rbx-20h]
0x18000cd34  mov     [rcx], rdx
0x18000cd37  mov     [rcx+8], rdx
0x18000cd3b  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000cd41  nop
0x18000cd42  mov     [rdi], rbx
0x18000cd45  xor     eax, eax
0x18000cd47  mov     [rbx+rbp], al
0x18000cd4a  mov     rcx, rbx
0x18000cd4d  call    p9fs__BlockingCode$_ResumeCoro$1__lambda_ba3c1d9efddbfd0bb9bd71913ea5c746___
0x18000cd52  nop
0x18000cd53  mov     rax, rdi
0x18000cd56  mov     rcx, [rsp+78h+var_38]
0x18000cd5b  xor     rcx, rsp; StackCookie
0x18000cd5e  call    __security_check_cookie
0x18000cd63  add     rsp, 58h
0x18000cd67  pop     rdi
0x18000cd68  pop     rsi
0x18000cd69  pop     rbp
0x18000cd6a  pop     rbx
0x18000cd6b  retn
```
