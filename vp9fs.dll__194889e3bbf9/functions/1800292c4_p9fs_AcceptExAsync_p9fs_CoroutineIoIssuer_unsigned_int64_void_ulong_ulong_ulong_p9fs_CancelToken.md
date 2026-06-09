# p9fs::AcceptExAsync(p9fs::CoroutineIoIssuer &,unsigned __int64,void *,ulong,ulong,ulong,p9fs::CancelToken &)

- ea: `0x1800292c4`
- end: `0x1800293ad`
- name: `?AcceptExAsync@p9fs@@YA?AV?$Task@V?$BasicExpected@KK@util@@@1@AEAUCoroutineIoIssuer@1@_KPEAXKKKAEAVCancelToken@1@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b190`

## callees

- `0x180004120`
- `0x180004144`
- `0x1800290e0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180029371`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180029371`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall p9fs::AcceptExAsync(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        __int64 a8)
{
  char *v12; // rax
  char *v13; // rbx

  v12 = (char *)operator new(0x150u);
  v13 = v12 + 48;
  *((_QWORD *)v12 + 35) = a2;
  *((_QWORD *)v12 + 36) = a3;
  *((_QWORD *)v12 + 37) = a4;
  *((_DWORD *)v12 + 76) = 0;
  *((_DWORD *)v12 + 77) = 52;
  *((_DWORD *)v12 + 78) = 52;
  *((_QWORD *)v12 + 40) = a8;
  *((_QWORD *)v12 + 6) = p9fs::AcceptExAsync__ResumeCoro_1;
  *((_DWORD *)v12 + 14) = 65538;
  *(_DWORD *)(v12 + 9) = 0;
  *(_WORD *)(v12 + 13) = 0;
  v12[15] = 0;
  *((_QWORD *)v12 + 4) = 0;
  *(_QWORD *)v12 = 0;
  v12[8] = 0;
  *((_QWORD *)v12 + 2) = 0;
  *((_QWORD *)v12 + 3) = 0;
  __ExceptionPtrCreate(v12 + 16);
  *(v13 - 16) = 1;
  *((_DWORD *)v13 - 3) = 0;
  *a1 = v13;
  v13[224] = 0;
  p9fs::AcceptExAsync__ResumeCoro_1(v13);
  return a1;
}

```

## disassembly

```asm
0x1800292c4  push    rbx
0x1800292c6  push    rbp
0x1800292c7  push    rsi
0x1800292c8  push    rdi
0x1800292c9  push    r14
0x1800292cb  push    r15
0x1800292cd  sub     rsp, 58h
0x1800292d1  mov     rax, cs:__security_cookie
0x1800292d8  xor     rax, rsp
0x1800292db  mov     [rsp+88h+var_48], rax
0x1800292e0  mov     rsi, r9
0x1800292e3  mov     rbp, r8
0x1800292e6  mov     r14, rdx
0x1800292e9  mov     rdi, rcx
0x1800292ec  mov     [rsp+88h+var_60], rcx
0x1800292f1  mov     r15d, 0E0h
0x1800292f7  lea     rcx, [r15+70h]; Size
0x1800292fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029300  mov     [rsp+88h+var_68], rax
0x180029305  lea     rbx, [rax+30h]
0x180029309  mov     [rsp+88h+var_68], rbx
0x18002930e  mov     [rbx+r15+8], r14
0x180029313  mov     [rbx+r15+10h], rbp
0x180029318  mov     [rbx+r15+18h], rsi
0x18002931d  xor     esi, esi
0x18002931f  mov     [rbx+r15+20h], esi
0x180029324  lea     eax, [rsi+34h]
0x180029327  mov     [rbx+r15+24h], eax
0x18002932c  mov     [rbx+r15+28h], eax
0x180029331  mov     rax, [rsp+88h+arg_38]
0x180029339  mov     [rbx+r15+30h], rax
0x18002933e  lea     rax, p9fs__AcceptExAsync$_ResumeCoro$1
0x180029345  mov     [rbx], rax
0x180029348  mov     dword ptr [rbx+8], 10002h
0x18002934f  mov     [rbx-27h], esi
0x180029352  mov     [rbx-23h], si
0x180029356  mov     [rbx-21h], sil
0x18002935a  mov     [rbx-10h], rsi
0x18002935e  mov     [rbx-30h], rsi
0x180029362  mov     [rbx-28h], sil
0x180029366  lea     rcx, [rbx-20h]
0x18002936a  mov     [rcx], rsi
0x18002936d  mov     [rcx+8], rsi
0x180029371  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180029377  mov     byte ptr [rbx-10h], 1
0x18002937b  mov     [rbx-0Ch], esi
0x18002937e  mov     [rdi], rbx
0x180029381  xor     eax, eax
0x180029383  mov     [rbx+r15], al
0x180029387  mov     rcx, rbx
0x18002938a  call    p9fs__AcceptExAsync$_ResumeCoro$1
0x18002938f  nop
0x180029390  mov     rax, rdi
0x180029393  mov     rcx, [rsp+88h+var_48]
0x180029398  xor     rcx, rsp; StackCookie
0x18002939b  call    __security_check_cookie
0x1800293a0  add     rsp, 58h
0x1800293a4  pop     r15
0x1800293a6  pop     r14
0x1800293a8  pop     rdi
0x1800293a9  pop     rsi
0x1800293aa  pop     rbp
0x1800293ab  pop     rbx
0x1800293ac  retn
```
