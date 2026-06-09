# CPrivateNotificationWindow::Init(CPrivateNotificationWindowSink *)

- ea: `0x180018970`
- end: `0x1800189bd`
- name: `?Init@CPrivateNotificationWindow@@IEAAJPEAVCPrivateNotificationWindowSink@@@Z`
- size: `77`
- prototype: `__int64 __fastcall(CPrivateNotificationWindow *__hidden this, struct CPrivateNotificationWindowSink *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bcb8`
- `0x18000bd74`
- `0x180018884`

## callees

- `0x1800092b8`
- `0x180018970`

## import_xrefs

- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x18001899c`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x18001899c`

## pseudocode

```c
__int64 __fastcall CPrivateNotificationWindow::Init(
        CPrivateNotificationWindow *this,
        struct CPrivateNotificationWindowSink *a2)
{
  __int64 v3; // rax

  *((_QWORD *)this + 4) = a2;
  v3 = SHCreateWorkerWindowW(CPrivateNotificationWindow::s_NotifierWndProc, -3, 0);
  *((_QWORD *)this + 2) = v3;
  if ( v3 )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x180018970  push    rbx
0x180018972  sub     rsp, 30h
0x180018976  mov     [rcx+20h], rdx
0x18001897a  xor     r9d, r9d
0x18001897d  mov     [rsp+38h+var_10], rcx
0x180018982  mov     rbx, rcx
0x180018985  xor     r8d, r8d
0x180018988  mov     [rsp+38h+var_18], 0
0x180018991  lea     rcx, ?s_NotifierWndProc@CPrivateNotificationWindow@@KA_JPEAUHWND__@@I_K_J@Z; CPrivateNotificationWindow::s_NotifierWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180018998  lea     rdx, [r9-3]
0x18001899c  call    cs:__imp_SHCreateWorkerWindowW
0x1800189a2  mov     [rbx+10h], rax
0x1800189a6  test    rax, rax
0x1800189a9  jz      short loc_1800189B3
0x1800189ab  xor     eax, eax
0x1800189ad  add     rsp, 30h
0x1800189b1  pop     rbx
0x1800189b2  retn
0x1800189b3  add     rsp, 30h
0x1800189b7  pop     rbx
0x1800189b8  jmp     ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
```
