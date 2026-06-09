# p9fs::Handler::FillData(uint,p9fs::CancelToken &)

- ea: `0x180010424`
- end: `0x1800104e6`
- name: `?FillData@Handler@p9fs@@AEAA?AV?$Task@_N@2@IAEAVCancelToken@2@@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016b50`

## callees

- `0x180004120`
- `0x180004144`
- `0x180010160`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800104b0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800104b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall p9fs::Handler::FillData(__int64 a1, _QWORD *a2, int a3, __int64 a4)
{
  char *v8; // rax
  char *v9; // rbx

  v8 = (char *)operator new(0xB0u);
  v9 = v8 + 48;
  *((_QWORD *)v8 + 19) = a1;
  *((_DWORD *)v8 + 40) = a3;
  *((_QWORD *)v8 + 21) = a4;
  *((_QWORD *)v8 + 6) = p9fs::Handler::FillData__ResumeCoro_1;
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
  v9[96] = 0;
  p9fs::Handler::FillData__ResumeCoro_1(v9);
  return a2;
}

```

## disassembly

```asm
0x180010424  push    rbx
0x180010426  push    rbp
0x180010427  push    rsi
0x180010428  push    rdi
0x180010429  push    r14
0x18001042b  push    r15
0x18001042d  sub     rsp, 58h
0x180010431  mov     rax, cs:__security_cookie
0x180010438  xor     rax, rsp
0x18001043b  mov     [rsp+88h+var_48], rax
0x180010440  mov     rsi, r9
0x180010443  mov     ebp, r8d
0x180010446  mov     rdi, rdx
0x180010449  mov     r14, rcx
0x18001044c  mov     [rsp+88h+var_60], rdx
0x180010451  mov     r15d, 60h ; '`'
0x180010457  lea     rcx, [r15+50h]; Size
0x18001045b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010460  mov     [rsp+88h+var_68], rax
0x180010465  lea     rbx, [rax+30h]
0x180010469  mov     [rsp+88h+var_68], rbx
0x18001046e  mov     [rbx+r15+8], r14
0x180010473  mov     [rbx+r15+10h], ebp
0x180010478  mov     [rbx+r15+18h], rsi
0x18001047d  lea     rax, p9fs__Handler__FillData$_ResumeCoro$1
0x180010484  mov     [rbx], rax
0x180010487  mov     dword ptr [rbx+8], 10002h
0x18001048e  xor     edx, edx
0x180010490  mov     [rbx-27h], edx
0x180010493  mov     [rbx-23h], dx
0x180010497  mov     [rbx-21h], dl
0x18001049a  mov     [rbx-10h], rdx
0x18001049e  mov     [rbx-30h], rdx
0x1800104a2  mov     [rbx-28h], dl
0x1800104a5  lea     rcx, [rbx-20h]
0x1800104a9  mov     [rcx], rdx
0x1800104ac  mov     [rcx+8], rdx
0x1800104b0  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800104b6  nop
0x1800104b7  mov     [rdi], rbx
0x1800104ba  xor     eax, eax
0x1800104bc  mov     [rbx+r15], al
0x1800104c0  mov     rcx, rbx
0x1800104c3  call    p9fs__Handler__FillData$_ResumeCoro$1
0x1800104c8  nop
0x1800104c9  mov     rax, rdi
0x1800104cc  mov     rcx, [rsp+88h+var_48]
0x1800104d1  xor     rcx, rsp; StackCookie
0x1800104d4  call    __security_check_cookie
0x1800104d9  add     rsp, 58h
0x1800104dd  pop     r15
0x1800104df  pop     r14
0x1800104e1  pop     rdi
0x1800104e2  pop     rsi
0x1800104e3  pop     rbp
0x1800104e4  pop     rbx
0x1800104e5  retn
```
