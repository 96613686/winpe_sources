# p9fs::Socket::RecvAsync(gsl::span<gsl::byte,-1>,p9fs::CancelToken &)

- ea: `0x18002b650`
- end: `0x18002b719`
- name: `?RecvAsync@Socket@p9fs@@UEAA?AV?$Task@_K@2@V?$span@W4byte@gsl@@$0?0@gsl@@AEAVCancelToken@2@@Z`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004144`
- `0x180029850`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b6e4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b6e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall p9fs::Socket::RecvAsync(__int64 a1, _QWORD *a2, _OWORD *a3, __int64 a4)
{
  char *v8; // rax
  char *v9; // r14

  v8 = (char *)operator new(0x120u);
  v9 = v8 + 48;
  *((_QWORD *)v8 + 31) = a1 + 16;
  *((_OWORD *)v8 + 16) = *a3;
  *((_QWORD *)v8 + 34) = a4;
  *((_QWORD *)v8 + 6) = p9fs::RecvAsync__ResumeCoro_1;
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
  *a2 = v9;
  v9[192] = 0;
  p9fs::RecvAsync__ResumeCoro_1(v9);
  return a2;
}

```

## disassembly

```asm
0x18002b650  mov     [rsp+arg_0], rbx
0x18002b655  mov     [rsp+arg_10], rsi
0x18002b65a  push    rdi
0x18002b65b  push    r14
0x18002b65d  push    r15
0x18002b65f  sub     rsp, 50h
0x18002b663  mov     rsi, r9
0x18002b666  mov     rdi, r8
0x18002b669  mov     r15, rdx
0x18002b66c  mov     rbx, rcx
0x18002b66f  mov     [rsp+68h+var_38], rdx
0x18002b674  mov     ecx, 120h; Size
0x18002b679  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b67e  mov     rcx, rax
0x18002b681  mov     [rsp+68h+var_40], rax
0x18002b686  lea     r14, [rax+30h]
0x18002b68a  mov     [rsp+68h+var_40], r14
0x18002b68f  lea     rax, [rbx+10h]
0x18002b693  mov     [r14+0C8h], rax
0x18002b69a  movups  xmm0, xmmword ptr [rdi]
0x18002b69d  movdqu  xmmword ptr [r14+0D0h], xmm0
0x18002b6a6  mov     [r14+0E0h], rsi
0x18002b6ad  lea     rax, p9fs__RecvAsync$_ResumeCoro$1
0x18002b6b4  mov     [r14], rax
0x18002b6b7  mov     dword ptr [r14+8], 10002h
0x18002b6bf  mov     dword ptr [rcx+9], 0
0x18002b6c6  xor     eax, eax
0x18002b6c8  mov     [rcx+0Dh], ax
0x18002b6cc  mov     [rcx+0Fh], al
0x18002b6cf  mov     [rcx+20h], rax
0x18002b6d3  mov     [rcx], rax
0x18002b6d6  mov     [rcx+8], al
0x18002b6d9  add     rcx, 10h
0x18002b6dd  mov     [rcx], rax
0x18002b6e0  mov     [rcx+8], rax
0x18002b6e4  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002b6ea  nop
0x18002b6eb  mov     [r15], r14
0x18002b6ee  xor     eax, eax
0x18002b6f0  mov     [r14+0C0h], al
0x18002b6f7  mov     rcx, r14
0x18002b6fa  call    p9fs__RecvAsync$_ResumeCoro$1
0x18002b6ff  nop
0x18002b700  mov     rax, r15
0x18002b703  lea     r11, [rsp+68h+var_18]
0x18002b708  mov     rbx, [r11+20h]
0x18002b70c  mov     rsi, [r11+30h]
0x18002b710  mov     rsp, r11
0x18002b713  pop     r15
0x18002b715  pop     r14
0x18002b717  pop     rdi
0x18002b718  retn
```
