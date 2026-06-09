# p9fs::XAttr::Write(unsigned __int64,gsl::span<gsl::byte const,-1>)

- ea: `0x18002af00`
- end: `0x18002afcf`
- name: `?Write@XAttr@p9fs@@UEAA?AV?$Task@V?$BasicExpected@IJ@util@@@2@_KV?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004120`
- `0x180004144`
- `0x18002ad00`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002af93`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002af93`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall p9fs::XAttr::Write(__int64 a1, _QWORD *a2, __int64 a3, _OWORD *a4)
{
  char *v8; // rax
  char *v9; // rbx

  v8 = (char *)operator new(0xB0u);
  v9 = v8 + 48;
  *((_QWORD *)v8 + 17) = a1;
  *((_QWORD *)v8 + 18) = a3;
  *(_OWORD *)(v8 + 152) = *a4;
  *((_QWORD *)v8 + 6) = p9fs::XAttr::Write__ResumeCoro_1;
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
  v9[80] = 0;
  p9fs::XAttr::Write__ResumeCoro_1(v9);
  return a2;
}

```

## disassembly

```asm
0x18002af00  push    rbx
0x18002af02  push    rbp
0x18002af03  push    rsi
0x18002af04  push    rdi
0x18002af05  push    r14
0x18002af07  push    r15
0x18002af09  sub     rsp, 58h
0x18002af0d  mov     rax, cs:__security_cookie
0x18002af14  xor     rax, rsp
0x18002af17  mov     [rsp+88h+var_48], rax
0x18002af1c  mov     rsi, r9
0x18002af1f  mov     rbp, r8
0x18002af22  mov     rdi, rdx
0x18002af25  mov     r14, rcx
0x18002af28  mov     [rsp+88h+var_60], rdx
0x18002af2d  mov     r15d, 50h ; 'P'
0x18002af33  lea     rcx, [r15+60h]; Size
0x18002af37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002af3c  mov     [rsp+88h+var_68], rax
0x18002af41  lea     rbx, [rax+30h]
0x18002af45  mov     [rsp+88h+var_68], rbx
0x18002af4a  mov     [rbx+r15+8], r14
0x18002af4f  mov     [rbx+r15+10h], rbp
0x18002af54  movups  xmm0, xmmword ptr [rsi]
0x18002af57  movdqu  xmmword ptr [rbx+r15+18h], xmm0
0x18002af5e  lea     rax, p9fs__XAttr__Write$_ResumeCoro$1
0x18002af65  mov     [rbx], rax
0x18002af68  mov     dword ptr [rbx+8], 10002h
0x18002af6f  xor     esi, esi
0x18002af71  mov     [rbx-27h], esi
0x18002af74  mov     [rbx-23h], si
0x18002af78  mov     [rbx-21h], sil
0x18002af7c  mov     [rbx-10h], rsi
0x18002af80  mov     [rbx-30h], rsi
0x18002af84  mov     [rbx-28h], sil
0x18002af88  lea     rcx, [rbx-20h]
0x18002af8c  mov     [rcx], rsi
0x18002af8f  mov     [rcx+8], rsi
0x18002af93  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002af99  mov     byte ptr [rbx-10h], 1
0x18002af9d  mov     [rbx-0Ch], esi
0x18002afa0  mov     [rdi], rbx
0x18002afa3  xor     eax, eax
0x18002afa5  mov     [rbx+r15], al
0x18002afa9  mov     rcx, rbx
0x18002afac  call    p9fs__XAttr__Write$_ResumeCoro$1
0x18002afb1  nop
0x18002afb2  mov     rax, rdi
0x18002afb5  mov     rcx, [rsp+88h+var_48]
0x18002afba  xor     rcx, rsp; StackCookie
0x18002afbd  call    __security_check_cookie
0x18002afc2  add     rsp, 58h
0x18002afc6  pop     r15
0x18002afc8  pop     r14
0x18002afca  pop     rdi
0x18002afcb  pop     rsi
0x18002afcc  pop     rbp
0x18002afcd  pop     rbx
0x18002afce  retn
```
