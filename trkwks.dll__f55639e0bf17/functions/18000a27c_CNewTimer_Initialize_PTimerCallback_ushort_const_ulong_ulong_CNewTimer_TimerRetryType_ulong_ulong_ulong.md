# CNewTimer::Initialize(PTimerCallback *,ushort const *,ulong,ulong,CNewTimer::TimerRetryType,ulong,ulong,ulong)

- ea: `0x18000a27c`
- end: `0x18000a34c`
- name: `?Initialize@CNewTimer@@QEAAXPEAVPTimerCallback@@PEBGKKW4TimerRetryType@1@KKK@Z`
- size: `208`
- prototype: `void *__fastcall(__int64, __int64, struct _FILETIME, __int64, int, __int64, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a880`

## callees

- `0x180008cb4`
- `0x18000a038`
- `0x18000a27c`
- `0x18000a354`
- `0x18000d038`

## import_xrefs

- `ntdll!NtCreateTimer` at `0x18000a2ed`
- `ntdll!NtCreateTimer` at `0x18000a2ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a333`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a308`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a308`

## pseudocode

```c
void *__fastcall CNewTimer::Initialize(
        __int64 a1,
        __int64 a2,
        struct _FILETIME a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7,
        int a8,
        int a9)
{
  int v11; // eax
  int v12; // eax
  HANDLE *v13; // rbx
  signed int Timer; // eax
  void (*v15)(void *, unsigned __int8); // rdx
  unsigned int v16; // r9d
  void *result; // rax
  DWORD LastError; // eax
  struct _FILETIME FileTime; // [rsp+50h] [rbp+18h] BYREF

  FileTime = a3;
  CFILETIME::SetToUTC(&FileTime);
  v11 = a5;
  *(_DWORD *)(a1 + 8) |= 1u;
  *(_DWORD *)(a1 + 100) = v11;
  *(_DWORD *)(a1 + 104) = a7;
  v12 = a8;
  *(_QWORD *)(a1 + 88) = a2;
  v13 = (HANDLE *)(a1 + 56);
  *(_DWORD *)(a1 + 108) = v12;
  *(_DWORD *)(a1 + 112) = a9;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 96) = 5;
  *(_DWORD *)(a1 + 72) = 2;
  Timer = NtCreateTimer((PHANDLE)(a1 + 56), 0x1F0003u, 0, SynchronizationTimer);
  if ( Timer < 0 )
  {
    *v13 = 0;
    RaiseException(Timer, 0, 0, 0);
    __debugbreak();
  }
  CNewTimer::LoadFromRegistry((CNewTimer *)a1);
  result = TrkRegisterWaitForSingleObjectEx(*v13, v15, (void *)a1, v16, 0x10u);
  *(_QWORD *)(a1 + 80) = result;
  if ( !result )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  return result;
}

```

## disassembly

```asm
0x18000a27c  mov     [rsp+arg_0], rbx
0x18000a281  mov     qword ptr [rsp+FileTime.dwLowDateTime], r8
0x18000a286  push    rdi
0x18000a287  sub     rsp, 30h
0x18000a28b  mov     rdi, rcx
0x18000a28e  mov     rbx, rdx
0x18000a291  lea     rcx, [rsp+38h+FileTime]; lpFileTime
0x18000a296  call    ?SetToUTC@CFILETIME@@QEAAXXZ; CFILETIME::SetToUTC(void)
0x18000a29b  mov     eax, [rsp+38h+arg_20]
0x18000a29f  mov     r9d, 1; TimerType
0x18000a2a5  or      [rdi+8], r9d
0x18000a2a9  xor     r8d, r8d; ObjectAttributes
0x18000a2ac  mov     [rdi+64h], eax
0x18000a2af  mov     edx, 1F0003h; DesiredAccess
0x18000a2b4  mov     eax, [rsp+38h+arg_30]
0x18000a2b8  mov     [rdi+68h], eax
0x18000a2bb  mov     eax, [rsp+38h+arg_38]
0x18000a2bf  mov     [rdi+58h], rbx
0x18000a2c3  lea     rbx, [rdi+38h]
0x18000a2c7  mov     [rdi+6Ch], eax
0x18000a2ca  mov     rcx, rbx; TimerHandle
0x18000a2cd  mov     eax, [rsp+38h+arg_40]
0x18000a2d4  mov     [rdi+70h], eax
0x18000a2d7  mov     qword ptr [rdi+40h], 0
0x18000a2df  mov     dword ptr [rdi+60h], 5
0x18000a2e6  mov     dword ptr [rdi+48h], 2
0x18000a2ed  call    cs:__imp_NtCreateTimer
0x18000a2f3  test    eax, eax
0x18000a2f5  jns     short loc_18000A30F
0x18000a2f7  xor     r9d, r9d; lpArguments
0x18000a2fa  mov     qword ptr [rbx], 0
0x18000a301  xor     r8d, r8d; nNumberOfArguments
0x18000a304  xor     edx, edx; dwExceptionFlags
0x18000a306  mov     ecx, eax; dwExceptionCode
0x18000a308  call    cs:__imp_RaiseException
0x18000a30e  int     3; Trap to Debugger
0x18000a30f  mov     rcx, rdi; this
0x18000a312  call    ?LoadFromRegistry@CNewTimer@@AEAAXXZ; CNewTimer::LoadFromRegistry(void)
0x18000a317  mov     rcx, [rbx]; hObject
0x18000a31a  mov     r8, rdi; void *
0x18000a31d  mov     [rsp+38h+var_18], 10h; unsigned int
0x18000a325  call    ?TrkRegisterWaitForSingleObjectEx@@YAPEAXPEAXP6AX0E@Z0KK@Z; TrkRegisterWaitForSingleObjectEx(void *,void (*)(void *,uchar),void *,ulong,ulong)
0x18000a32a  mov     [rdi+50h], rax
0x18000a32e  test    rax, rax
0x18000a331  jnz     short loc_18000A341
0x18000a333  call    cs:__imp_GetLastError
0x18000a339  mov     ecx, eax; int
0x18000a33b  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000a341  mov     rbx, [rsp+38h+arg_0]
0x18000a346  add     rsp, 30h
0x18000a34a  pop     rdi
0x18000a34b  retn
```
