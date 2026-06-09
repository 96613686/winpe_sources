# p9fs::XAttr::Read(unsigned __int64,gsl::span<gsl::byte,-1>)

- ea: `0x18002ac00`
- end: `0x18002accf`
- name: `?Read@XAttr@p9fs@@UEAA?AV?$Task@V?$BasicExpected@IJ@util@@@2@_KV?$span@W4byte@gsl@@$0?0@gsl@@@Z`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004120`
- `0x180004144`
- `0x18002aaa0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002ac93`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002ac93`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall p9fs::XAttr::Read(__int64 a1, _QWORD *a2, __int64 a3, _OWORD *a4)
{
  char *v8; // rax
  char *v9; // rbx

  v8 = (char *)operator new(0xD0u);
  v9 = v8 + 48;
  *((_QWORD *)v8 + 21) = a1;
  *((_QWORD *)v8 + 22) = a3;
  *(_OWORD *)(v8 + 184) = *a4;
  *((_QWORD *)v8 + 6) = p9fs::XAttr::Read__ResumeCoro_1;
  *((_DWORD *)v8 + 14) = 65538;
  *(_DWORD *)(v8 + 9) = 0;
  *(_WORD *)(v8 + 13) = 0;
  v8[15] = 0;
  *((_QWORD *)v8 + 4) = 0;
  *(_QWORD *)v8 = 0;
  v8[8] = 0;
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  __ExceptionPtrCreate(v8 + 16);
  *(v9 - 16) = 1;
  *((_DWORD *)v9 - 3) = 0;
  *a2 = v9;
  v9[112] = 0;
  p9fs::XAttr::Read__ResumeCoro_1(v9);
  return a2;
}

```

## disassembly

```asm
0x18002ac00  push    rbx
0x18002ac02  push    rbp
0x18002ac03  push    rsi
0x18002ac04  push    rdi
0x18002ac05  push    r14
0x18002ac07  push    r15
0x18002ac09  sub     rsp, 58h
0x18002ac0d  mov     rax, cs:__security_cookie
0x18002ac14  xor     rax, rsp
0x18002ac17  mov     [rsp+88h+var_48], rax
0x18002ac1c  mov     rsi, r9
0x18002ac1f  mov     rbp, r8
0x18002ac22  mov     rdi, rdx
0x18002ac25  mov     r14, rcx
0x18002ac28  mov     [rsp+88h+var_60], rdx
0x18002ac2d  mov     r15d, 70h ; 'p'
0x18002ac33  lea     rcx, [r15+60h]; Size
0x18002ac37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ac3c  mov     [rsp+88h+var_68], rax
0x18002ac41  lea     rbx, [rax+30h]
0x18002ac45  mov     [rsp+88h+var_68], rbx
0x18002ac4a  mov     [rbx+r15+8], r14
0x18002ac4f  mov     [rbx+r15+10h], rbp
0x18002ac54  movups  xmm0, xmmword ptr [rsi]
0x18002ac57  movdqu  xmmword ptr [rbx+r15+18h], xmm0
0x18002ac5e  lea     rax, p9fs__XAttr__Read$_ResumeCoro$1
0x18002ac65  mov     [rbx], rax
0x18002ac68  mov     dword ptr [rbx+8], 10002h
0x18002ac6f  xor     esi, esi
0x18002ac71  mov     [rbx-27h], esi
0x18002ac74  mov     [rbx-23h], si
0x18002ac78  mov     [rbx-21h], sil
0x18002ac7c  mov     [rbx-10h], rsi
0x18002ac80  mov     [rbx-30h], rsi
0x18002ac84  mov     [rbx-28h], sil
0x18002ac88  lea     rcx, [rbx-20h]
0x18002ac8c  mov     [rcx], rsi
0x18002ac8f  mov     [rcx+8], rsi
0x18002ac93  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002ac99  mov     byte ptr [rbx-10h], 1
0x18002ac9d  mov     [rbx-0Ch], esi
0x18002aca0  mov     [rdi], rbx
0x18002aca3  xor     eax, eax
0x18002aca5  mov     [rbx+r15], al
0x18002aca9  mov     rcx, rbx
0x18002acac  call    p9fs__XAttr__Read$_ResumeCoro$1
0x18002acb1  nop
0x18002acb2  mov     rax, rdi
0x18002acb5  mov     rcx, [rsp+88h+var_48]
0x18002acba  xor     rcx, rsp; StackCookie
0x18002acbd  call    __security_check_cookie
0x18002acc2  add     rsp, 58h
0x18002acc6  pop     r15
0x18002acc8  pop     r14
0x18002acca  pop     rdi
0x18002accb  pop     rsi
0x18002accc  pop     rbp
0x18002accd  pop     rbx
0x18002acce  retn
```
