# CShareMediaSettingsWriterImpl::StartWMPNSSService(void)

- ea: `0x1800142d0`
- end: `0x1800144be`
- name: `?StartWMPNSSService@CShareMediaSettingsWriterImpl@@UEAAJXZ`
- size: `494`
- prototype: `__int64 __fastcall(CShareMediaSettingsWriterImpl *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x180001d60`
- `0x180003860`
- `0x180003888`
- `0x1800142d0`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x18001432b`
- `ADVAPI32!OpenSCManagerW` at `0x18001432b`
- `ADVAPI32!OpenServiceW` at `0x18001436a`
- `ADVAPI32!OpenServiceW` at `0x18001436a`
- `ADVAPI32!QueryServiceStatus` at `0x180014391`
- `ADVAPI32!QueryServiceStatus` at `0x1800143f4`
- `ADVAPI32!QueryServiceStatus` at `0x180014442`
- `ADVAPI32!QueryServiceStatus` at `0x180014391`
- `ADVAPI32!QueryServiceStatus` at `0x1800143f4`
- `ADVAPI32!QueryServiceStatus` at `0x180014442`
- `ADVAPI32!CloseServiceHandle` at `0x180014469`
- `ADVAPI32!CloseServiceHandle` at `0x180014472`
- `ADVAPI32!CloseServiceHandle` at `0x180014469`
- `ADVAPI32!CloseServiceHandle` at `0x180014472`
- `ADVAPI32!StartServiceW` at `0x1800143cc`
- `ADVAPI32!StartServiceW` at `0x1800143cc`
- `KERNEL32!Sleep` at `0x18001442e`
- `KERNEL32!Sleep` at `0x18001442e`
- `KERNEL32!GetLastError` at `0x180014343`
- `KERNEL32!GetLastError` at `0x18001439f`
- `KERNEL32!GetLastError` at `0x1800143d6`
- `KERNEL32!GetLastError` at `0x180014402`
- `KERNEL32!GetLastError` at `0x180014450`
- `KERNEL32!GetLastError` at `0x180014343`
- `KERNEL32!GetLastError` at `0x18001439f`
- `KERNEL32!GetLastError` at `0x1800143d6`
- `KERNEL32!GetLastError` at `0x180014402`
- `KERNEL32!GetLastError` at `0x180014450`

## string_xrefs

- `0x180014322`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CShareMediaSettingsWriterImpl::StartWMPNSSService(CShareMediaSettingsWriterImpl *this)
{
  SC_HANDLE v1; // rbp
  signed int v2; // ebx
  signed int LastError; // eax
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  signed int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  unsigned int v9; // edi
  signed int v10; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
  v1 = OpenSCManagerW(0, L"ServicesActive", 1u);
  if ( v1 )
  {
    v2 = 0;
    goto LABEL_9;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_9:
    v4 = OpenServiceW(v1, L"wmpnetworksvc", 0x14u);
    v5 = v4;
    if ( !v4 )
    {
LABEL_34:
      CloseServiceHandle(v1);
      goto LABEL_35;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(v4, &ServiceStatus) )
    {
      v2 = 0;
    }
    else
    {
      v6 = GetLastError();
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      if ( v2 < 0 )
        goto LABEL_33;
    }
    if ( ServiceStatus.dwCurrentState == 1 )
    {
      if ( StartServiceW(v5, 0, 0) )
        goto LABEL_41;
      v7 = GetLastError();
      v2 = v7;
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      if ( v2 >= 0 )
      {
LABEL_41:
        if ( QueryServiceStatus(v5, &ServiceStatus) )
        {
          v2 = 0;
          goto LABEL_25;
        }
        v8 = GetLastError();
        v2 = v8;
        if ( v8 > 0 )
          v2 = (unsigned __int16)v8 | 0x80070000;
        if ( v2 >= 0 )
        {
LABEL_25:
          v9 = 0;
          while ( v9 < 0x2710 && ServiceStatus.dwCurrentState == 2 )
          {
            Sleep(0x3E8u);
            v9 += 1000;
            if ( QueryServiceStatus(v5, &ServiceStatus) )
            {
              v2 = 0;
            }
            else
            {
              v10 = GetLastError();
              v2 = v10;
              if ( v10 > 0 )
                v2 = (unsigned __int16)v10 | 0x80070000;
              if ( v2 < 0 )
                break;
            }
          }
        }
      }
    }
LABEL_33:
    CloseServiceHandle(v5);
    goto LABEL_34;
  }
LABEL_35:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800142d0  push    rbx
0x1800142d2  push    rbp
0x1800142d3  push    rsi
0x1800142d4  push    rdi
0x1800142d5  push    r12
0x1800142d7  push    r15
0x1800142d9  sub     rsp, 58h
0x1800142dd  mov     rax, cs:__security_cookie
0x1800142e4  xor     rax, rsp
0x1800142e7  mov     [rsp+88h+var_48], rax
0x1800142ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142f3  lea     r12, WPP_GLOBAL_Control
0x1800142fa  mov     edi, 14h
0x1800142ff  cmp     rcx, r12
0x180014302  jz      short loc_18001431C
0x180014304  test    byte ptr [rcx+1Ch], 20h
0x180014308  jz      short loc_18001431C
0x18001430a  mov     rcx, [rcx+10h]
0x18001430e  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180014315  mov     edx, edi
0x180014317  call    WPP_SF_
0x18001431c  mov     r8d, 1; dwDesiredAccess
0x180014322  lea     rdx, DatabaseName; "ServicesActive"
0x180014329  xor     ecx, ecx; lpMachineName
0x18001432b  call    cs:__imp_OpenSCManagerW
0x180014331  mov     rbp, rax
0x180014334  mov     r15d, 80070000h
0x18001433a  test    rax, rax
0x18001433d  jz      short loc_180014343
0x18001433f  xor     ebx, ebx
0x180014341  jmp     short loc_18001435D
0x180014343  call    cs:__imp_GetLastError
0x180014349  mov     ebx, eax
0x18001434b  test    eax, eax
0x18001434d  jle     short loc_180014355
0x18001434f  movzx   ebx, ax
0x180014352  or      ebx, r15d
0x180014355  test    ebx, ebx
0x180014357  js      loc_180014478
0x18001435d  mov     r8d, edi; dwDesiredAccess
0x180014360  lea     rdx, ServiceName; "wmpnetworksvc"
0x180014367  mov     rcx, rbp; hSCManager
0x18001436a  call    cs:__imp_OpenServiceW
0x180014370  mov     rsi, rax
0x180014373  test    rax, rax
0x180014376  jz      loc_18001446F
0x18001437c  xorps   xmm0, xmm0
0x18001437f  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x180014384  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x180014389  mov     rcx, rax; hService
0x18001438c  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180014391  call    cs:__imp_QueryServiceStatus
0x180014397  test    eax, eax
0x180014399  jz      short loc_18001439F
0x18001439b  xor     ebx, ebx
0x18001439d  jmp     short loc_1800143B9
0x18001439f  call    cs:__imp_GetLastError
0x1800143a5  mov     ebx, eax
0x1800143a7  test    eax, eax
0x1800143a9  jle     short loc_1800143B1
0x1800143ab  movzx   ebx, ax
0x1800143ae  or      ebx, r15d
0x1800143b1  test    ebx, ebx
0x1800143b3  js      loc_180014466
0x1800143b9  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 1
0x1800143be  jnz     loc_180014466
0x1800143c4  xor     r8d, r8d; lpServiceArgVectors
0x1800143c7  xor     edx, edx; dwNumServiceArgs
0x1800143c9  mov     rcx, rsi; hService
0x1800143cc  call    cs:__imp_StartServiceW
0x1800143d2  test    eax, eax
0x1800143d4  jnz     short loc_1800143EC
0x1800143d6  call    cs:__imp_GetLastError
0x1800143dc  mov     ebx, eax
0x1800143de  test    eax, eax
0x1800143e0  jle     short loc_1800143E8
0x1800143e2  movzx   ebx, ax
0x1800143e5  or      ebx, r15d
0x1800143e8  test    ebx, ebx
0x1800143ea  js      short loc_180014466
0x1800143ec  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x1800143f1  mov     rcx, rsi; hService
0x1800143f4  call    cs:__imp_QueryServiceStatus
0x1800143fa  test    eax, eax
0x1800143fc  jz      short loc_180014402
0x1800143fe  xor     ebx, ebx
0x180014400  jmp     short loc_180014418
0x180014402  call    cs:__imp_GetLastError
0x180014408  mov     ebx, eax
0x18001440a  test    eax, eax
0x18001440c  jle     short loc_180014414
0x18001440e  movzx   ebx, ax
0x180014411  or      ebx, r15d
0x180014414  test    ebx, ebx
0x180014416  js      short loc_180014466
0x180014418  xor     edi, edi
0x18001441a  cmp     edi, 2710h
0x180014420  jnb     short loc_180014466
0x180014422  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 2
0x180014427  jnz     short loc_180014466
0x180014429  mov     ecx, 3E8h; dwMilliseconds
0x18001442e  call    cs:__imp_Sleep
0x180014434  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x180014439  mov     rcx, rsi; hService
0x18001443c  add     edi, 3E8h
0x180014442  call    cs:__imp_QueryServiceStatus
0x180014448  test    eax, eax
0x18001444a  jz      short loc_180014450
0x18001444c  xor     ebx, ebx
0x18001444e  jmp     short loc_18001441A
0x180014450  call    cs:__imp_GetLastError
0x180014456  mov     ebx, eax
0x180014458  test    eax, eax
0x18001445a  jle     short loc_180014462
0x18001445c  movzx   ebx, ax
0x18001445f  or      ebx, r15d
0x180014462  test    ebx, ebx
0x180014464  jns     short loc_18001441A
0x180014466  mov     rcx, rsi; hSCObject
0x180014469  call    cs:__imp_CloseServiceHandle
0x18001446f  mov     rcx, rbp; hSCObject
0x180014472  call    cs:__imp_CloseServiceHandle
0x180014478  mov     rcx, cs:WPP_GLOBAL_Control
0x18001447f  cmp     rcx, r12
0x180014482  jz      short loc_1800144A2
0x180014484  test    byte ptr [rcx+1Ch], 20h
0x180014488  jz      short loc_1800144A2
0x18001448a  mov     rcx, [rcx+10h]
0x18001448e  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180014495  mov     edx, 15h
0x18001449a  mov     r9d, ebx
0x18001449d  call    WPP_SF_d
0x1800144a2  mov     eax, ebx
0x1800144a4  mov     rcx, [rsp+88h+var_48]
0x1800144a9  xor     rcx, rsp; StackCookie
0x1800144ac  call    __security_check_cookie
0x1800144b1  add     rsp, 58h
0x1800144b5  pop     r15
0x1800144b7  pop     r12
0x1800144b9  pop     rdi
0x1800144ba  pop     rsi
0x1800144bb  pop     rbp
0x1800144bc  pop     rbx
0x1800144bd  retn
```
