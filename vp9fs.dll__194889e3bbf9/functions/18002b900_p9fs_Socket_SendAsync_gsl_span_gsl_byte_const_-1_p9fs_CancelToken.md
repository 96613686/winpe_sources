# p9fs::Socket::SendAsync(gsl::span<gsl::byte const,-1>,p9fs::CancelToken &)

- ea: `0x18002b900`
- end: `0x18002b9c9`
- name: `?SendAsync@Socket@p9fs@@UEAA?AV?$Task@_K@2@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@AEAVCancelToken@2@@Z`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004144`
- `0x180029a20`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b994`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002b994`

## pseudocode

```c
_QWORD *__fastcall p9fs::Socket::SendAsync(__int64 a1, _QWORD *a2, _OWORD *a3, __int64 a4)
{
  char *v8; // rax
  char *v9; // r14

  v8 = (char *)operator new(0x120u);
  v9 = v8 + 48;
  *((_QWORD *)v8 + 31) = a1 + 16;
  *((_OWORD *)v8 + 16) = *a3;
  *((_QWORD *)v8 + 34) = a4;
  *((_QWORD *)v8 + 6) = p9fs::SendAsync__ResumeCoro_1;
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
  p9fs::SendAsync__ResumeCoro_1(v9);
  return a2;
}

```

## disassembly

```asm
0x18002b900  mov     [rsp+arg_0], rbx
0x18002b905  mov     [rsp+arg_10], rsi
0x18002b90a  push    rdi
0x18002b90b  push    r14
0x18002b90d  push    r15
0x18002b90f  sub     rsp, 50h
0x18002b913  mov     rsi, r9
0x18002b916  mov     rdi, r8
0x18002b919  mov     r15, rdx
0x18002b91c  mov     rbx, rcx
0x18002b91f  mov     [rsp+68h+var_38], rdx
0x18002b924  mov     ecx, 120h; Size
0x18002b929  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b92e  mov     rcx, rax
0x18002b931  mov     [rsp+68h+var_40], rax
0x18002b936  lea     r14, [rax+30h]
0x18002b93a  mov     [rsp+68h+var_40], r14
0x18002b93f  lea     rax, [rbx+10h]
0x18002b943  mov     [r14+0C8h], rax
0x18002b94a  movups  xmm0, xmmword ptr [rdi]
0x18002b94d  movdqu  xmmword ptr [r14+0D0h], xmm0
0x18002b956  mov     [r14+0E0h], rsi
0x18002b95d  lea     rax, p9fs__SendAsync$_ResumeCoro$1
0x18002b964  mov     [r14], rax
0x18002b967  mov     dword ptr [r14+8], 10002h
0x18002b96f  mov     dword ptr [rcx+9], 0
0x18002b976  xor     eax, eax
0x18002b978  mov     [rcx+0Dh], ax
0x18002b97c  mov     [rcx+0Fh], al
0x18002b97f  mov     [rcx+20h], rax
0x18002b983  mov     [rcx], rax
0x18002b986  mov     [rcx+8], al
0x18002b989  add     rcx, 10h
0x18002b98d  mov     [rcx], rax
0x18002b990  mov     [rcx+8], rax
0x18002b994  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002b99a  nop
0x18002b99b  mov     [r15], r14
0x18002b99e  xor     eax, eax
0x18002b9a0  mov     [r14+0C0h], al
0x18002b9a7  mov     rcx, r14
0x18002b9aa  call    p9fs__SendAsync$_ResumeCoro$1
0x18002b9af  nop
0x18002b9b0  mov     rax, r15
0x18002b9b3  lea     r11, [rsp+68h+var_18]
0x18002b9b8  mov     rbx, [r11+20h]
0x18002b9bc  mov     rsi, [r11+30h]
0x18002b9c0  mov     rsp, r11
0x18002b9c3  pop     r15
0x18002b9c5  pop     r14
0x18002b9c7  pop     rdi
0x18002b9c8  retn
```
