# CWdsDeviceControllerRequest::CleanupImpersonation(void)

- ea: `0x1800013d0`
- end: `0x1800014be`
- name: `?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ`
- size: `238`
- prototype: `__int64 __fastcall(CWdsDeviceControllerRequest *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180001370`
- `0x180005430`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`
- `0x1800063b4`
- `0x180006dfc`

## callees

- `0x1800013d0`
- `0x180014d58`
- `0x180014ee0`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800013ed`
- `KERNEL32!EnterCriticalSection` at `0x1800013ed`
- `KERNEL32!LeaveCriticalSection` at `0x1800014a1`
- `KERNEL32!LeaveCriticalSection` at `0x1800014a1`
- `KERNEL32!GetCurrentThreadId` at `0x1800013ff`
- `KERNEL32!GetCurrentThreadId` at `0x180001412`
- `KERNEL32!GetCurrentThreadId` at `0x1800013ff`
- `KERNEL32!GetCurrentThreadId` at `0x180001412`

## string_xrefs

- `0x18000141b`: `A WDC started impersonating on one of its own threads but did not revert to self! CurrentThread:%u ImpersonationThread:%u`
- `0x180001465`: `A WDC started impersonating on the request thread but did not revert to self; reverting on its behalf`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerRequest::CleanupImpersonation(CWdsDeviceControllerRequest *this)
{
  unsigned int v2; // ebx
  unsigned int v3; // ebp
  const char *v4; // rdx
  DWORD CurrentThreadId; // eax
  const char *v6; // rdx

  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 27) )
  {
    v3 = *((_DWORD *)this + 28);
    if ( v3 == GetCurrentThreadId() )
    {
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(
          0x40000u,
          L"A WDC started impersonating on the request thread but did not revert to self; reverting on its behalf");
      v2 = (*(__int64 (__fastcall **)(CWdsDeviceControllerRequest *))(*(_QWORD *)this + 64LL))(this);
      ElValidateHr(v2, v6, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollerrequest.cpp", 0x97u);
    }
    else
    {
      if ( g_ErrLibTraceFunctionEx )
      {
        CurrentThreadId = GetCurrentThreadId();
        g_ErrLibTraceFunctionEx(
          0x80000u,
          L"A WDC started impersonating on one of its own threads but did not revert to self! CurrentThread:%u ImpersonationThread:%u",
          CurrentThreadId,
          v3);
      }
      if ( ElValidateWin32(0x139Fu, v4, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollerrequest.cpp", 0x8Fu) )
        v2 = -2147019873;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v2;
}

```

## disassembly

```asm
0x1800013d0  mov     [rsp+arg_0], rbx
0x1800013d5  mov     [rsp+arg_8], rbp
0x1800013da  mov     [rsp+arg_10], rsi
0x1800013df  push    rdi
0x1800013e0  sub     rsp, 30h
0x1800013e4  mov     rdi, rcx
0x1800013e7  xor     ebx, ebx
0x1800013e9  add     rcx, 40h ; '@'; lpCriticalSection
0x1800013ed  call    cs:__imp_EnterCriticalSection
0x1800013f3  cmp     [rdi+6Ch], ebx
0x1800013f6  jz      loc_18000149D
0x1800013fc  mov     ebp, [rdi+70h]
0x1800013ff  call    cs:__imp_GetCurrentThreadId
0x180001405  cmp     ebp, eax
0x180001407  jz      short loc_180001459
0x180001409  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rbx; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001410  jz      short loc_180001437
0x180001412  call    cs:__imp_GetCurrentThreadId
0x180001418  mov     r9d, ebp
0x18000141b  lea     rdx, aAWdcStartedImp; "A WDC started impersonating on one of i"...
0x180001422  mov     r8d, eax
0x180001425  mov     ecx, 80000h
0x18000142a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001431  call    cs:__guard_dispatch_icall_fptr
0x180001437  mov     r9d, 8Fh; unsigned int
0x18000143d  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180001444  mov     ecx, 139Fh; unsigned int
0x180001449  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000144e  test    eax, eax
0x180001450  jz      short loc_18000149D
0x180001452  mov     ebx, 8007139Fh
0x180001457  jmp     short loc_18000149D
0x180001459  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180001460  test    rax, rax
0x180001463  jz      short loc_180001477
0x180001465  lea     rdx, aAWdcStartedImp_0; "A WDC started impersonating on the requ"...
0x18000146c  mov     ecx, 40000h
0x180001471  call    cs:__guard_dispatch_icall_fptr
0x180001477  mov     rax, [rdi]
0x18000147a  mov     rcx, rdi
0x18000147d  mov     rax, [rax+40h]
0x180001481  call    cs:__guard_dispatch_icall_fptr
0x180001487  mov     r9d, 97h; unsigned int
0x18000148d  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180001494  mov     ecx, eax; int
0x180001496  mov     ebx, eax
0x180001498  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000149d  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800014a1  call    cs:__imp_LeaveCriticalSection
0x1800014a7  mov     rbp, [rsp+38h+arg_8]
0x1800014ac  mov     eax, ebx
0x1800014ae  mov     rbx, [rsp+38h+arg_0]
0x1800014b3  mov     rsi, [rsp+38h+arg_10]
0x1800014b8  add     rsp, 30h
0x1800014bc  pop     rdi
0x1800014bd  retn
```
