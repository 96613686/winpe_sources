# CPrivateNotificationWindow::CreateInstance(CPrivateNotificationWindowSink *,CPrivateNotificationWindow * *)

- ea: `0x180063fa4`
- end: `0x180064094`
- name: `?CreateInstance@CPrivateNotificationWindow@@SAJPEAVCPrivateNotificationWindowSink@@PEAPEAV1@@Z`
- size: `240`
- prototype: `__int64 __fastcall(struct CPrivateNotificationWindowSink *, struct CPrivateNotificationWindow **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180026934`
- `0x18003f350`

## callees

- `0x180002ae4`
- `0x180063fa4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006400b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006400b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063ff6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063ff6`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x180064034`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x180064034`

## pseudocode

```c
__int64 __fastcall CPrivateNotificationWindow::CreateInstance(
        struct CPrivateNotificationWindowSink *a1,
        struct _RTL_CRITICAL_SECTION **a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v6; // rax
  signed int LastError; // eax
  signed int v8; // ebx

  *a2 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    v4->LockCount = 1;
    v4->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CPrivateNotificationWindow::`vftable';
    v4->OwningThread = 0;
    CurrentThreadId = GetCurrentThreadId();
    v4->SpinCount = 0;
    LODWORD(v4->LockSemaphore) = CurrentThreadId;
    InitializeCriticalSection(v4 + 1);
    v4->SpinCount = (ULONG_PTR)a1;
    v6 = SHCreateWorkerWindowW(CPrivateNotificationWindow::s_NotifierWndProc, -3, 0, 0, 0, v4);
    v4->OwningThread = (HANDLE)v6;
    if ( v6 )
    {
      *a2 = v4;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
        v8 = -2147467259;
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v4->DebugInfo->Type)(v4, 1);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180063fa4  mov     [rsp+arg_0], rbx
0x180063fa9  mov     [rsp+arg_8], rsi
0x180063fae  push    rdi
0x180063faf  sub     rsp, 30h
0x180063fb3  mov     rbx, rdx
0x180063fb6  mov     qword ptr [rdx], 0
0x180063fbd  mov     rsi, rcx
0x180063fc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180063fc7  mov     ecx, 50h ; 'P'; unsigned __int64
0x180063fcc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180063fd1  mov     rdi, rax
0x180063fd4  test    rax, rax
0x180063fd7  jz      loc_18006407D
0x180063fdd  lea     rax, ??_7CPrivateNotificationWindow@@6B@; const CPrivateNotificationWindow::`vftable'
0x180063fe4  mov     dword ptr [rdi+8], 1
0x180063feb  mov     [rdi], rax
0x180063fee  mov     qword ptr [rdi+10h], 0
0x180063ff6  call    cs:__imp_GetCurrentThreadId
0x180063ffc  lea     rcx, [rdi+28h]; lpCriticalSection
0x180064000  mov     qword ptr [rdi+20h], 0
0x180064008  mov     [rdi+18h], eax
0x18006400b  call    cs:__imp_InitializeCriticalSection
0x180064011  xor     r9d, r9d
0x180064014  mov     [rsp+38h+var_10], rdi
0x180064019  xor     r8d, r8d
0x18006401c  mov     [rdi+20h], rsi
0x180064020  lea     rcx, ?s_NotifierWndProc@CPrivateNotificationWindow@@KA_JPEAUHWND__@@I_K_J@Z; CPrivateNotificationWindow::s_NotifierWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180064027  mov     [rsp+38h+var_18], 0
0x180064030  lea     rdx, [r9-3]
0x180064034  call    cs:__imp_SHCreateWorkerWindowW
0x18006403a  mov     [rdi+10h], rax
0x18006403e  test    rax, rax
0x180064041  jnz     short loc_180064076
0x180064043  call    cs:__imp_GetLastError
0x180064049  mov     ebx, eax
0x18006404b  test    eax, eax
0x18006404d  jle     short loc_180064058
0x18006404f  movzx   ebx, ax
0x180064052  or      ebx, 80070000h
0x180064058  test    ebx, ebx
0x18006405a  js      short loc_180064061
0x18006405c  mov     ebx, 80004005h
0x180064061  mov     rax, [rdi]
0x180064064  mov     edx, 1
0x180064069  mov     rcx, rdi
0x18006406c  mov     rax, [rax]
0x18006406f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064074  jmp     short loc_180064082
0x180064076  mov     [rbx], rdi
0x180064079  xor     ebx, ebx
0x18006407b  jmp     short loc_180064082
0x18006407d  mov     ebx, 8007000Eh
0x180064082  mov     rsi, [rsp+38h+arg_8]
0x180064087  mov     eax, ebx
0x180064089  mov     rbx, [rsp+38h+arg_0]
0x18006408e  add     rsp, 30h
0x180064092  pop     rdi
0x180064093  retn
```
