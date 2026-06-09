# p9fs::File::Write(unsigned __int64,gsl::span<gsl::byte const,-1>)

- ea: `0x180022650`
- end: `0x18002271f`
- name: `?Write@File@p9fs@@UEAA?AV?$Task@V?$BasicExpected@IJ@util@@@2@_KV?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004120`
- `0x180004144`
- `0x1800221d0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800226e3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800226e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall p9fs::File::Write(__int64 a1, __int64 *a2, __int64 a3, _OWORD *a4)
{
  char *v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  const char *v12; // r9

  v8 = (char *)operator new(0x1E0u);
  v9 = (__int64)(v8 + 48);
  *((_QWORD *)v8 + 55) = a1;
  *((_QWORD *)v8 + 56) = a3;
  *(_OWORD *)(v8 + 456) = *a4;
  *((_QWORD *)v8 + 6) = p9fs::File::Write__ResumeCoro_1;
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
  *(_BYTE *)(v9 + 384) = 0;
  p9fs::File::Write__ResumeCoro_1(v9, v10, v11, v12);
  return a2;
}

```

## disassembly

```asm
0x180022650  push    rbx
0x180022652  push    rbp
0x180022653  push    rsi
0x180022654  push    rdi
0x180022655  push    r14
0x180022657  push    r15
0x180022659  sub     rsp, 58h
0x18002265d  mov     rax, cs:__security_cookie
0x180022664  xor     rax, rsp
0x180022667  mov     [rsp+88h+var_48], rax
0x18002266c  mov     rsi, r9
0x18002266f  mov     rbp, r8
0x180022672  mov     rdi, rdx
0x180022675  mov     r14, rcx
0x180022678  mov     [rsp+88h+var_60], rdx
0x18002267d  mov     r15d, 180h
0x180022683  lea     rcx, [r15+60h]; Size
0x180022687  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002268c  mov     [rsp+88h+var_68], rax
0x180022691  lea     rbx, [rax+30h]
0x180022695  mov     [rsp+88h+var_68], rbx
0x18002269a  mov     [rbx+r15+8], r14
0x18002269f  mov     [rbx+r15+10h], rbp
0x1800226a4  movups  xmm0, xmmword ptr [rsi]
0x1800226a7  movdqu  xmmword ptr [rbx+r15+18h], xmm0
0x1800226ae  lea     rax, p9fs__File__Write$_ResumeCoro$1
0x1800226b5  mov     [rbx], rax
0x1800226b8  mov     dword ptr [rbx+8], 10002h
0x1800226bf  xor     esi, esi
0x1800226c1  mov     [rbx-27h], esi
0x1800226c4  mov     [rbx-23h], si
0x1800226c8  mov     [rbx-21h], sil
0x1800226cc  mov     [rbx-10h], rsi
0x1800226d0  mov     [rbx-30h], rsi
0x1800226d4  mov     [rbx-28h], sil
0x1800226d8  lea     rcx, [rbx-20h]
0x1800226dc  mov     [rcx], rsi
0x1800226df  mov     [rcx+8], rsi
0x1800226e3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800226e9  mov     byte ptr [rbx-10h], 1
0x1800226ed  mov     [rbx-0Ch], esi
0x1800226f0  mov     [rdi], rbx
0x1800226f3  xor     eax, eax
0x1800226f5  mov     [rbx+r15], al
0x1800226f9  mov     rcx, rbx
0x1800226fc  call    p9fs__File__Write$_ResumeCoro$1
0x180022701  nop
0x180022702  mov     rax, rdi
0x180022705  mov     rcx, [rsp+88h+var_48]
0x18002270a  xor     rcx, rsp; StackCookie
0x18002270d  call    __security_check_cookie
0x180022712  add     rsp, 58h
0x180022716  pop     r15
0x180022718  pop     r14
0x18002271a  pop     rdi
0x18002271b  pop     rsi
0x18002271c  pop     rbp
0x18002271d  pop     rbx
0x18002271e  retn
```
