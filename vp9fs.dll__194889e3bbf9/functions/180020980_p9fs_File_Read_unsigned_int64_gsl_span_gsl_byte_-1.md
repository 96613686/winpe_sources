# p9fs::File::Read(unsigned __int64,gsl::span<gsl::byte,-1>)

- ea: `0x180020980`
- end: `0x180020a4f`
- name: `?Read@File@p9fs@@UEAA?AV?$Task@V?$BasicExpected@IJ@util@@@2@_KV?$span@W4byte@gsl@@$0?0@gsl@@@Z`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004120`
- `0x180004144`
- `0x180020600`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180020a13`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180020a13`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall p9fs::File::Read(__int64 a1, __int64 *a2, __int64 a3, _OWORD *a4)
{
  char *v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  const char *v12; // r9

  v8 = (char *)operator new(0x170u);
  v9 = (__int64)(v8 + 48);
  *((_QWORD *)v8 + 41) = a1;
  *((_QWORD *)v8 + 42) = a3;
  *(_OWORD *)(v8 + 344) = *a4;
  *((_QWORD *)v8 + 6) = p9fs::File::Read__ResumeCoro_1;
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
  *(_BYTE *)(v9 - 16) = 1;
  *(_DWORD *)(v9 - 12) = 0;
  *a2 = v9;
  *(_BYTE *)(v9 + 272) = 0;
  p9fs::File::Read__ResumeCoro_1(v9, v10, v11, v12);
  return a2;
}

```

## disassembly

```asm
0x180020980  push    rbx
0x180020982  push    rbp
0x180020983  push    rsi
0x180020984  push    rdi
0x180020985  push    r14
0x180020987  push    r15
0x180020989  sub     rsp, 58h
0x18002098d  mov     rax, cs:__security_cookie
0x180020994  xor     rax, rsp
0x180020997  mov     [rsp+88h+var_48], rax
0x18002099c  mov     rsi, r9
0x18002099f  mov     rbp, r8
0x1800209a2  mov     rdi, rdx
0x1800209a5  mov     r14, rcx
0x1800209a8  mov     [rsp+88h+var_60], rdx
0x1800209ad  mov     r15d, 110h
0x1800209b3  lea     rcx, [r15+60h]; Size
0x1800209b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800209bc  mov     [rsp+88h+var_68], rax
0x1800209c1  lea     rbx, [rax+30h]
0x1800209c5  mov     [rsp+88h+var_68], rbx
0x1800209ca  mov     [rbx+r15+8], r14
0x1800209cf  mov     [rbx+r15+10h], rbp
0x1800209d4  movups  xmm0, xmmword ptr [rsi]
0x1800209d7  movdqu  xmmword ptr [rbx+r15+18h], xmm0
0x1800209de  lea     rax, p9fs__File__Read$_ResumeCoro$1
0x1800209e5  mov     [rbx], rax
0x1800209e8  mov     dword ptr [rbx+8], 10002h
0x1800209ef  xor     esi, esi
0x1800209f1  mov     [rbx-27h], esi
0x1800209f4  mov     [rbx-23h], si
0x1800209f8  mov     [rbx-21h], sil
0x1800209fc  mov     [rbx-10h], rsi
0x180020a00  mov     [rbx-30h], rsi
0x180020a04  mov     [rbx-28h], sil
0x180020a08  lea     rcx, [rbx-20h]
0x180020a0c  mov     [rcx], rsi
0x180020a0f  mov     [rcx+8], rsi
0x180020a13  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180020a19  mov     byte ptr [rbx-10h], 1
0x180020a1d  mov     [rbx-0Ch], esi
0x180020a20  mov     [rdi], rbx
0x180020a23  xor     eax, eax
0x180020a25  mov     [rbx+r15], al
0x180020a29  mov     rcx, rbx
0x180020a2c  call    p9fs__File__Read$_ResumeCoro$1
0x180020a31  nop
0x180020a32  mov     rax, rdi
0x180020a35  mov     rcx, [rsp+88h+var_48]
0x180020a3a  xor     rcx, rsp; StackCookie
0x180020a3d  call    __security_check_cookie
0x180020a42  add     rsp, 58h
0x180020a46  pop     r15
0x180020a48  pop     r14
0x180020a4a  pop     rdi
0x180020a4b  pop     rsi
0x180020a4c  pop     rbp
0x180020a4d  pop     rbx
0x180020a4e  retn
```
