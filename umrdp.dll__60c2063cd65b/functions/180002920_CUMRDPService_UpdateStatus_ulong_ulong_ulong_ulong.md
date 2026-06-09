# CUMRDPService::UpdateStatus(ulong,ulong,ulong,ulong)

- ea: `0x180002920`
- end: `0x180002a10`
- name: `?UpdateStatus@CUMRDPService@@AEAAHKKKK@Z`
- size: `240`
- prototype: `__int64 __fastcall(CUMRDPService *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180001a20`
- `0x18000e8f0`
- `0x18000efdc`

## callees

- `0x180002920`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800029de`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800029de`

## pseudocode

```c
BOOL __fastcall CUMRDPService::UpdateStatus(CUMRDPService *this, int a2, __int64 a3, int a4)
{
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int64 v8; // rcx
  __int64 v9; // rcx
  BOOL result; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  if ( !*((_QWORD *)this + 2) )
    return 0;
  *((_DWORD *)this + 8) = 132;
  if ( a2 == 4 )
    *((_DWORD *)this + 8) = 133;
  *((_DWORD *)this + 7) = a2;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 11) = a4;
  v6 = *(_OWORD *)((char *)this + 24);
  v7 = *(_OWORD *)((char *)this + 36);
  v8 = *((_QWORD *)this + 36);
  *(_OWORD *)&ServiceStatus.dwServiceType = v6;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = v7;
  if ( v8 )
    ServiceStatus.dwControlsAccepted = ServiceStatus.dwControlsAccepted & 0xFFFFFFF8
                                     | (LOBYTE(ServiceStatus.dwControlsAccepted) | 0xFFFFFFF8)
                                     & (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v9 = *((_QWORD *)this + 39);
  if ( v9 )
    ServiceStatus.dwControlsAccepted |= (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  result = SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 2), &ServiceStatus);
  if ( a2 == 1 )
    *((_QWORD *)this + 2) = 0;
  return result;
}

```

## disassembly

```asm
0x180002920  mov     [rsp+arg_18], rbx
0x180002925  push    rsi
0x180002926  sub     rsp, 50h
0x18000292a  mov     rax, cs:__security_cookie
0x180002931  xor     rax, rsp
0x180002934  mov     [rsp+58h+var_18], rax
0x180002939  cmp     qword ptr [rcx+10h], 0
0x18000293e  mov     esi, edx
0x180002940  mov     rbx, rcx
0x180002943  jz      loc_180002A06
0x180002949  mov     [rsp+58h+arg_8], rbp
0x18000294e  mov     dword ptr [rcx+20h], 84h
0x180002955  cmp     edx, 4
0x180002958  jnz     short loc_180002961
0x18000295a  mov     dword ptr [rcx+20h], 85h
0x180002961  xor     ebp, ebp
0x180002963  mov     [rcx+1Ch], esi
0x180002966  mov     [rcx+24h], rbp
0x18000296a  mov     [rcx+30h], ebp
0x18000296d  mov     [rcx+2Ch], r9d
0x180002971  movups  xmm0, xmmword ptr [rcx+18h]
0x180002975  movups  xmm1, xmmword ptr [rcx+24h]
0x180002979  mov     rcx, [rcx+120h]
0x180002980  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180002985  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm1
0x18000298a  test    rcx, rcx
0x18000298d  jz      short loc_1800029B9
0x18000298f  mov     rax, [rcx]
0x180002992  mov     [rsp+58h+arg_10], rdi
0x180002997  mov     edi, [rsp+58h+ServiceStatus.dwControlsAccepted]
0x18000299b  mov     rax, [rax+8]
0x18000299f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a4  mov     ecx, edi
0x1800029a6  and     edi, 0FFFFFFF8h
0x1800029a9  or      ecx, 0FFFFFFF8h
0x1800029ac  and     eax, ecx
0x1800029ae  or      eax, edi
0x1800029b0  mov     rdi, [rsp+58h+arg_10]
0x1800029b5  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], eax
0x1800029b9  mov     rcx, [rbx+138h]
0x1800029c0  test    rcx, rcx
0x1800029c3  jz      short loc_1800029D5
0x1800029c5  mov     rax, [rcx]
0x1800029c8  mov     rax, [rax+8]
0x1800029cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d1  or      [rsp+58h+ServiceStatus.dwControlsAccepted], eax
0x1800029d5  mov     rcx, [rbx+10h]; hServiceStatus
0x1800029d9  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800029de  call    cs:__imp_SetServiceStatus
0x1800029e4  cmp     esi, 1
0x1800029e7  jz      short loc_180002A0A
0x1800029e9  mov     rbp, [rsp+58h+arg_8]
0x1800029ee  mov     rcx, [rsp+58h+var_18]
0x1800029f3  xor     rcx, rsp; StackCookie
0x1800029f6  call    __security_check_cookie
0x1800029fb  mov     rbx, [rsp+58h+arg_18]
0x180002a00  add     rsp, 50h
0x180002a04  pop     rsi
0x180002a05  retn
0x180002a06  xor     eax, eax
0x180002a08  jmp     short loc_1800029EE
0x180002a0a  mov     [rbx+10h], rbp
0x180002a0e  jmp     short loc_1800029E9
```
