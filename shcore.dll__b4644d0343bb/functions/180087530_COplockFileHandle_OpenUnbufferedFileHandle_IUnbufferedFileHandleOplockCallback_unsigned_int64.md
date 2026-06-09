# COplockFileHandle::OpenUnbufferedFileHandle(IUnbufferedFileHandleOplockCallback *,unsigned __int64 *)

- ea: `0x180087530`
- end: `0x180087605`
- name: `?OpenUnbufferedFileHandle@COplockFileHandle@@UEAAJPEAUIUnbufferedFileHandleOplockCallback@@PEA_K@Z`
- size: `213`
- prototype: `__int64 __fastcall(COplockFileHandle *__hidden this, struct IUnbufferedFileHandleOplockCallback *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180035ae0`
- `0x180087530`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800875cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800875cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800875f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800875f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008755d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008755d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800875aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800875aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COplockFileHandle::OpenUnbufferedFileHandle(
        COplockFileHandle *this,
        struct IUnbufferedFileHandleOplockCallback *a2,
        unsigned __int64 *a3)
{
  char *v5; // rdi
  __int64 (__fastcall *v6)(char *, _QWORD, unsigned __int64 *); // rbx
  DWORD CurrentProcessId; // eax
  int v8; // ebx
  int LastError; // eax
  int v11; // [rsp+20h] [rbp-38h] BYREF
  HANDLE hMutex; // [rsp+28h] [rbp-30h]

  v5 = (char *)this + 8;
  Microsoft::WRL::Wrappers::Mutex::Lock(&v11, *((_QWORD *)this + 8), 0xFFFFFFFFLL);
  v6 = *(__int64 (__fastcall **)(char *, _QWORD, unsigned __int64 *))(*(_QWORD *)v5 + 24LL);
  CurrentProcessId = GetCurrentProcessId();
  v8 = v6(v5, CurrentProcessId, a3);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v5 + 32LL))(v5, *a3);
    if ( v8 < 0 )
    {
      CloseHandle((HANDLE)*a3);
      *a3 = 0;
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(char *, struct IUnbufferedFileHandleOplockCallback *))(*(_QWORD *)v5 + 40LL))(
             v5,
             a2);
    }
  }
  if ( hMutex && (v11 & 0xFFFFFF7F) == 0 && !ReleaseMutex(hMutex) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180087530  push    rbx
0x180087532  push    rbp
0x180087533  push    rsi
0x180087534  push    rdi
0x180087535  sub     rsp, 38h
0x180087539  mov     rsi, r8
0x18008753c  mov     rbp, rdx
0x18008753f  lea     rdi, [rcx+8]
0x180087543  or      r8d, 0FFFFFFFFh
0x180087547  mov     rdx, [rcx+40h]
0x18008754b  lea     rcx, [rsp+58h+var_38]
0x180087550  call    ?Lock@Mutex@Wrappers@WRL@Microsoft@@SA?AV?$SyncLockWithStatusT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@234@PEAXK@Z; Microsoft::WRL::Wrappers::Mutex::Lock(void *,ulong)
0x180087555  nop
0x180087556  mov     rax, [rdi]
0x180087559  mov     rbx, [rax+18h]
0x18008755d  call    cs:__imp_GetCurrentProcessId
0x180087563  mov     r8, rsi
0x180087566  mov     edx, eax
0x180087568  mov     rcx, rdi
0x18008756b  mov     rax, rbx
0x18008756e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087573  mov     ebx, eax
0x180087575  test    eax, eax
0x180087577  js      short loc_1800875B7
0x180087579  mov     rax, [rdi]
0x18008757c  mov     rdx, [rsi]
0x18008757f  mov     rcx, rdi
0x180087582  mov     rax, [rax+20h]
0x180087586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008758b  mov     ebx, eax
0x18008758d  test    eax, eax
0x18008758f  js      short loc_1800875A7
0x180087591  mov     rax, [rdi]
0x180087594  mov     rdx, rbp
0x180087597  mov     rcx, rdi
0x18008759a  mov     rax, [rax+28h]
0x18008759e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800875a3  mov     ebx, eax
0x1800875a5  jmp     short loc_1800875B7
0x1800875a7  mov     rcx, [rsi]; hObject
0x1800875aa  call    cs:__imp_CloseHandle
0x1800875b0  mov     qword ptr [rsi], 0
0x1800875b7  mov     rcx, [rsp+58h+hMutex]; hMutex
0x1800875bc  test    rcx, rcx
0x1800875bf  jz      short loc_1800875FA
0x1800875c1  test    [rsp+58h+var_38], 0FFFFFF7Fh
0x1800875c9  jnz     short loc_1800875FA
0x1800875cb  call    cs:__imp_ReleaseMutex
0x1800875d1  test    eax, eax
0x1800875d3  jnz     short loc_1800875FA
0x1800875d5  call    cs:__imp_GetLastError
0x1800875db  test    eax, eax
0x1800875dd  jle     short loc_1800875E7
0x1800875df  movzx   eax, ax
0x1800875e2  or      eax, 80070000h
0x1800875e7  xor     r9d, r9d; lpArguments
0x1800875ea  xor     r8d, r8d; nNumberOfArguments
0x1800875ed  lea     edx, [r9+1]; dwExceptionFlags
0x1800875f1  mov     ecx, eax; dwExceptionCode
0x1800875f3  call    cs:__imp_RaiseException
0x1800875f9  int     3; Trap to Debugger
0x1800875fa  mov     eax, ebx
0x1800875fc  add     rsp, 38h
0x180087600  pop     rdi
0x180087601  pop     rsi
0x180087602  pop     rbp
0x180087603  pop     rbx
0x180087604  retn
```
