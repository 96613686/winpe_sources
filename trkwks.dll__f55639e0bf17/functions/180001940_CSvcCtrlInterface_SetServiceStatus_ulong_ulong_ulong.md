# CSvcCtrlInterface::SetServiceStatus(ulong,ulong,ulong)

- ea: `0x180001940`
- end: `0x1800019c2`
- name: `?SetServiceStatus@CSvcCtrlInterface@@QEAAXKKK@Z`
- size: `130`
- prototype: `void __fastcall(CSvcCtrlInterface *this, DWORD, DWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800016f4`
- `0x1800017e0`
- `0x180001cb8`
- `0x180001e28`

## callees

- `0x180001940`
- `0x180011000`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800019a4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800019a4`

## pseudocode

```c
void __fastcall CSvcCtrlInterface::SetServiceStatus(CSvcCtrlInterface *this, DWORD a2, DWORD a3)
{
  SERVICE_STATUS_HANDLE v3; // rcx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  *((_DWORD *)this + 4) = a2;
  *((_DWORD *)this + 6) = a3;
  if ( a2 - 2 <= 1 )
  {
    ServiceStatus.dwCheckPoint = *((_DWORD *)this + 5);
    *((_DWORD *)this + 5) = ServiceStatus.dwCheckPoint + 1;
    ServiceStatus.dwWaitHint = 30000;
  }
  else
  {
    *((_DWORD *)this + 5) = 0;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  }
  v3 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 4);
  ServiceStatus.dwServiceType = 48;
  ServiceStatus.dwCurrentState = a2;
  ServiceStatus.dwControlsAccepted = a3;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  if ( v3 )
    SetServiceStatus(v3, &ServiceStatus);
}

```

## disassembly

```asm
0x180001940  sub     rsp, 58h
0x180001944  mov     rax, cs:__security_cookie
0x18000194b  xor     rax, rsp
0x18000194e  mov     [rsp+58h+var_18], rax
0x180001953  lea     eax, [rdx-2]
0x180001956  mov     [rcx+10h], edx
0x180001959  xor     r9d, r9d
0x18000195c  mov     [rcx+18h], r8d
0x180001960  cmp     eax, 1
0x180001963  jbe     short loc_1800019AC
0x180001965  mov     [rcx+14h], r9d
0x180001969  mov     qword ptr [rsp+58h+ServiceStatus.dwCheckPoint], r9
0x18000196e  mov     rcx, [rcx+20h]; hServiceStatus
0x180001972  mov     [rsp+58h+ServiceStatus.dwServiceType], 30h ; '0'
0x18000197a  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x18000197e  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], r8d
0x180001983  mov     qword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], r9
0x180001988  test    rcx, rcx
0x18000198b  jnz     short loc_18000199F
0x18000198d  mov     rcx, [rsp+58h+var_18]
0x180001992  xor     rcx, rsp; StackCookie
0x180001995  call    __security_check_cookie
0x18000199a  add     rsp, 58h
0x18000199e  retn
0x18000199f  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800019a4  call    cs:__imp_SetServiceStatus
0x1800019aa  jmp     short loc_18000198D
0x1800019ac  mov     eax, [rcx+14h]
0x1800019af  mov     [rsp+58h+ServiceStatus.dwCheckPoint], eax
0x1800019b3  inc     eax
0x1800019b5  mov     [rcx+14h], eax
0x1800019b8  mov     [rsp+58h+ServiceStatus.dwWaitHint], 7530h
0x1800019c0  jmp     short loc_18000196E
```
