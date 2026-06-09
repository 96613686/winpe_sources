# PlugPlayServiceStatusUpdate

- ea: `0x180016050`
- end: `0x1800160d6`
- name: `PlugPlayServiceStatusUpdate`
- size: `134`
- prototype: `BOOL __fastcall(__int64, DWORD, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180015f80`
- `0x1800160dc`

## callees

- `0x180016050`
- `0x180018970`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800160be`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800160be`

## pseudocode

```c
BOOL __fastcall PlugPlayServiceStatusUpdate(__int64 a1, DWORD a2, DWORD a3)
{
  BOOL result; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  PlugPlayServiceCurrentState = a2;
  if ( PlugPlayServiceStatusHandle )
  {
    ServiceStatus.dwServiceType = 48;
    ServiceStatus.dwCurrentState = a2;
    ServiceStatus.dwCheckPoint = a3;
    if ( a2 == 4 )
    {
      ServiceStatus.dwControlsAccepted = 5;
    }
    else
    {
      ServiceStatus.dwControlsAccepted = 0;
      if ( a2 - 2 <= 1 )
      {
        ServiceStatus.dwWaitHint = 1000;
        goto LABEL_7;
      }
    }
    ServiceStatus.dwWaitHint = 0;
LABEL_7:
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    return SetServiceStatus(PlugPlayServiceStatusHandle, &ServiceStatus);
  }
  return result;
}

```

## disassembly

```asm
0x180016050  sub     rsp, 58h
0x180016054  mov     rax, cs:__security_cookie
0x18001605b  xor     rax, rsp
0x18001605e  mov     [rsp+58h+var_18], rax
0x180016063  mov     rcx, cs:PlugPlayServiceStatusHandle; hServiceStatus
0x18001606a  xor     r9d, r9d
0x18001606d  mov     cs:PlugPlayServiceCurrentState, edx
0x180016073  test    rcx, rcx
0x180016076  jz      short loc_1800160C4
0x180016078  mov     [rsp+58h+ServiceStatus.dwServiceType], 30h ; '0'
0x180016080  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x180016084  mov     [rsp+58h+ServiceStatus.dwCheckPoint], r8d
0x180016089  cmp     edx, 4
0x18001608c  jnz     short loc_180016098
0x18001608e  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], 5
0x180016096  jmp     short loc_1800160A5
0x180016098  lea     eax, [rdx-2]
0x18001609b  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], r9d
0x1800160a0  cmp     eax, 1
0x1800160a3  jbe     short loc_1800160AC
0x1800160a5  mov     [rsp+58h+ServiceStatus.dwWaitHint], r9d
0x1800160aa  jmp     short loc_1800160B4
0x1800160ac  mov     [rsp+58h+ServiceStatus.dwWaitHint], 3E8h
0x1800160b4  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800160b9  mov     qword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], r9
0x1800160be  call    cs:__imp_SetServiceStatus
0x1800160c4  mov     rcx, [rsp+58h+var_18]
0x1800160c9  xor     rcx, rsp; StackCookie
0x1800160cc  call    __security_check_cookie
0x1800160d1  add     rsp, 58h
0x1800160d5  retn
```
