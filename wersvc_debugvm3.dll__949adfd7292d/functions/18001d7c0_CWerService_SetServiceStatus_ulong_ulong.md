# CWerService::_SetServiceStatus(ulong,ulong)

- ea: `0x18001d7c0`
- end: `0x18001d924`
- name: `?_SetServiceStatus@CWerService@@AEAAJKK@Z`
- size: `356`
- prototype: `__int64 __fastcall(CWerService *__hidden this, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800154e4`
- `0x1800181f8`
- `0x180018700`
- `0x180018950`
- `0x18001d92c`
- `0x18001e054`

## callees

- `0x1800029d0`
- `0x180006a80`
- `0x180011f38`
- `0x180013df4`
- `0x18001d7c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8e5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001d8db`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001d8db`

## pseudocode

```c
signed int __fastcall CWerService::_SetServiceStatus(CWerService *this, __int64 a2, __int64 a3, __int64 a4)
{
  DWORD v4; // ebx
  HANDLE v6; // rcx
  signed int result; // eax
  int v8; // eax
  SERVICE_STATUS_HANDLE v9; // rcx
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF

  v4 = a2;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 38)
    || (MicrosoftTelemetryAssertTriggeredNoArgs(v6, a2, a3, a4), v6 = WPP_GLOBAL_Control, *((_QWORD *)this + 38)) )
  {
    *((_DWORD *)this + 78) = v4;
    ServiceStatus.dwServiceType = 32;
    ServiceStatus.dwCurrentState = v4;
    memset(&ServiceStatus.dwControlsAccepted, 0, 20);
    if ( v4 <= 7 && (v8 = 146, _bittest(&v8, v4)) )
    {
      ServiceStatus.dwControlsAccepted = 1027;
    }
    else if ( v4 == 4 || v4 <= 1 || v4 >= 7 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, a2, a3, a4);
    }
    v9 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 38);
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    if ( SetServiceStatus(v9, &ServiceStatus) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      if ( result >= 0 )
        return -2147467259;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    return -2147418113;
  }
  return result;
}

```

## disassembly

```asm
0x18001d7c0  mov     [rsp+arg_10], rbx
0x18001d7c5  mov     [rsp+arg_18], rbp
0x18001d7ca  push    rdi
0x18001d7cb  sub     rsp, 60h
0x18001d7cf  mov     rax, cs:__security_cookie
0x18001d7d6  xor     rax, rsp
0x18001d7d9  mov     [rsp+68h+var_18], rax
0x18001d7de  mov     ebx, edx
0x18001d7e0  mov     rdi, rcx
0x18001d7e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7ea  lea     rbp, WPP_GLOBAL_Control
0x18001d7f1  cmp     rcx, rbp
0x18001d7f4  jz      short loc_18001D823
0x18001d7f6  test    byte ptr [rcx+1Ch], 4
0x18001d7fa  jz      short loc_18001D823
0x18001d7fc  mov     rcx, [rcx+10h]
0x18001d800  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001d807  mov     edx, 3Fh ; '?'
0x18001d80c  mov     [rsp+68h+var_48], 0
0x18001d814  mov     r9d, ebx
0x18001d817  call    WPP_SF_Dd
0x18001d81c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d823  cmp     qword ptr [rdi+130h], 0
0x18001d82b  jnz     short loc_18001D86D
0x18001d82d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d832  cmp     qword ptr [rdi+130h], 0
0x18001d83a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d841  jnz     short loc_18001D86D
0x18001d843  cmp     rcx, rbp
0x18001d846  jz      short loc_18001D863
0x18001d848  test    byte ptr [rcx+1Ch], 1
0x18001d84c  jz      short loc_18001D863
0x18001d84e  mov     rcx, [rcx+10h]
0x18001d852  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001d859  mov     edx, 40h ; '@'
0x18001d85e  call    WPP_SF_
0x18001d863  mov     eax, 8000FFFFh
0x18001d868  jmp     loc_18001D905
0x18001d86d  mov     [rdi+138h], ebx
0x18001d873  xorps   xmm0, xmm0
0x18001d876  mov     [rsp+68h+ServiceStatus.dwWaitHint], 0
0x18001d87e  mov     [rsp+68h+ServiceStatus.dwServiceType], 20h ; ' '
0x18001d886  mov     [rsp+68h+ServiceStatus.dwCurrentState], ebx
0x18001d88a  movdqu  xmmword ptr [rsp+68h+ServiceStatus.dwControlsAccepted], xmm0
0x18001d890  cmp     ebx, 7
0x18001d893  ja      short loc_18001D8A9
0x18001d895  mov     eax, 92h
0x18001d89a  bt      eax, ebx
0x18001d89d  jnb     short loc_18001D8A9
0x18001d89f  mov     [rsp+68h+ServiceStatus.dwControlsAccepted], 403h
0x18001d8a7  jmp     short loc_18001D8BD
0x18001d8a9  cmp     ebx, 4
0x18001d8ac  jz      short loc_18001D8B8
0x18001d8ae  cmp     ebx, 1
0x18001d8b1  jbe     short loc_18001D8B8
0x18001d8b3  cmp     ebx, 7
0x18001d8b6  jb      short loc_18001D8BD
0x18001d8b8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d8bd  mov     rcx, [rdi+130h]; hServiceStatus
0x18001d8c4  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18001d8c9  mov     qword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], 0
0x18001d8d2  mov     qword ptr [rsp+68h+ServiceStatus.dwCheckPoint], 0
0x18001d8db  call    cs:__imp_SetServiceStatus
0x18001d8e1  test    eax, eax
0x18001d8e3  jnz     short loc_18001D903
0x18001d8e5  call    cs:__imp_GetLastError
0x18001d8eb  test    eax, eax
0x18001d8ed  jle     short loc_18001D8F7
0x18001d8ef  movzx   eax, ax
0x18001d8f2  or      eax, 80070000h
0x18001d8f7  test    eax, eax
0x18001d8f9  mov     ecx, 80004005h
0x18001d8fe  cmovns  eax, ecx
0x18001d901  jmp     short loc_18001D905
0x18001d903  xor     eax, eax
0x18001d905  mov     rcx, [rsp+68h+var_18]
0x18001d90a  xor     rcx, rsp; StackCookie
0x18001d90d  call    __security_check_cookie
0x18001d912  lea     r11, [rsp+68h+var_8]
0x18001d917  mov     rbx, [r11+20h]
0x18001d91b  mov     rbp, [r11+28h]
0x18001d91f  mov     rsp, r11
0x18001d922  pop     rdi
0x18001d923  retn
```
