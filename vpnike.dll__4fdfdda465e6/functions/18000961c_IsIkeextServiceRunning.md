# IsIkeextServiceRunning

- ea: `0x18000961c`
- end: `0x18000981b`
- name: `IsIkeextServiceRunning`
- size: `511`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c2a0`
- `0x180039278`

## callees

- `0x180007590`
- `0x180007794`
- `0x180007894`
- `0x18000961c`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000978f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000978f`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800096ac`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800096ac`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180009785`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180009785`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180009722`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180009722`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800097b6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800097c4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800097b6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800097c4`

## string_xrefs

- `0x1800096cf`: `OpenSCManager failed with error: %d`
- `0x18000973f`: `OpenService failed with error: %d`
- `0x18000979e`: `QueryServiceStatus failed with error: %d`

## pseudocode

```c
bool IsIkeextServiceRunning()
{
  bool v0; // bl
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  DWORD LastError; // eax
  __int64 v4; // r9
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  DWORD v7; // eax
  const wchar_t *v8; // rdx
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-E0h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[2044]; // [rsp+44h] [rbp-BCh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids);
  }
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v11 = 0;
  v0 = 0;
  memset_0(v12, 0, sizeof(v12));
  v1 = OpenSCManagerA(0, 0, 1u);
  v2 = v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"OpenSCManager failed with error: %d", LastError);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v11);
    }
    goto LABEL_20;
  }
  v5 = OpenServiceA(v1, "ikeext", 4u);
  v6 = v5;
  if ( v5 )
  {
    if ( QueryServiceStatus(v5, &ServiceStatus) )
    {
      v0 = ServiceStatus.dwCurrentState == 4;
    }
    else
    {
      v7 = GetLastError();
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v8 = L"QueryServiceStatus failed with error: %d";
LABEL_12:
        LOWORD(v11) = 0;
        FormatRRASErrorString(&v11, v8, v7);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v11);
      }
    }
  }
  else
  {
    v7 = GetLastError();
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v8 = L"OpenService failed with error: %d";
      goto LABEL_12;
    }
  }
  CloseServiceHandle(v2);
  if ( v6 )
    CloseServiceHandle(v6);
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v4) = v0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids, v4);
  }
  return v0;
}

```

## disassembly

```asm
0x18000961c  push    rbp
0x18000961e  push    rbx
0x18000961f  push    rsi
0x180009620  push    rdi
0x180009621  push    r14
0x180009623  push    r15
0x180009625  lea     rbp, [rsp-758h]
0x18000962d  sub     rsp, 858h
0x180009634  mov     rax, cs:__security_cookie
0x18000963b  xor     rax, rsp
0x18000963e  mov     [rbp+780h+var_40], rax
0x180009645  mov     rcx, cs:WPP_GLOBAL_Control
0x18000964c  lea     r15, WPP_GLOBAL_Control
0x180009653  mov     r14d, 1
0x180009659  cmp     rcx, r15
0x18000965c  jz      short loc_18000967E
0x18000965e  test    [rcx+1Ch], r14b
0x180009662  jz      short loc_18000967E
0x180009664  cmp     byte ptr [rcx+19h], 6
0x180009668  jb      short loc_18000967E
0x18000966a  mov     rcx, [rcx+10h]
0x18000966e  lea     edx, [r14+0Fh]
0x180009672  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x180009679  call    WPP_SF_
0x18000967e  xorps   xmm0, xmm0
0x180009681  lea     rcx, [rsp+880h+var_83C]; void *
0x180009686  xor     eax, eax
0x180009688  xor     edx, edx; Val
0x18000968a  movups  xmmword ptr [rsp+880h+ServiceStatus.dwServiceType], xmm0
0x18000968f  mov     r8d, 7FCh; Size
0x180009695  mov     [rsp+880h+var_840], eax
0x180009699  movups  xmmword ptr [rsp+880h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000969e  xor     bl, bl
0x1800096a0  call    memset_0
0x1800096a5  mov     r8d, r14d; dwDesiredAccess
0x1800096a8  xor     edx, edx; lpDatabaseName
0x1800096aa  xor     ecx, ecx; lpMachineName
0x1800096ac  call    cs:__imp_OpenSCManagerA
0x1800096b2  mov     rsi, rax
0x1800096b5  test    rax, rax
0x1800096b8  jnz     short loc_180009712
0x1800096ba  call    cs:__imp_GetLastError
0x1800096c0  test    cs:byte_1800AA941, 4
0x1800096c7  jz      loc_1800097CA
0x1800096cd  xor     ecx, ecx
0x1800096cf  lea     rdx, aOpenscmanagerF; "OpenSCManager failed with error: %d"
0x1800096d6  mov     word ptr [rsp+880h+var_840], cx
0x1800096db  mov     r8d, eax
0x1800096de  lea     rcx, [rsp+880h+var_840]
0x1800096e3  call    FormatRRASErrorString
0x1800096e8  test    cs:byte_1800AA941, 4
0x1800096ef  jz      loc_1800097CA
0x1800096f5  lea     r8, [rsp+880h+var_840]
0x1800096fa  lea     rdx, RasVpnIkeTraceError
0x180009701  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009708  call    McTemplateU0z_EventWriteTransfer
0x18000970d  jmp     loc_1800097CA
0x180009712  mov     r8d, 4; dwDesiredAccess
0x180009718  lea     rdx, ServiceName; "ikeext"
0x18000971f  mov     rcx, rsi; hSCManager
0x180009722  call    cs:__imp_OpenServiceA
0x180009728  mov     rdi, rax
0x18000972b  test    rax, rax
0x18000972e  jnz     short loc_18000977D
0x180009730  call    cs:__imp_GetLastError
0x180009736  test    cs:byte_1800AA941, 4
0x18000973d  jz      short loc_1800097B3
0x18000973f  lea     rdx, aOpenserviceFai; "OpenService failed with error: %d"
0x180009746  xor     ecx, ecx
0x180009748  mov     r8d, eax
0x18000974b  mov     word ptr [rsp+880h+var_840], cx
0x180009750  lea     rcx, [rsp+880h+var_840]
0x180009755  call    FormatRRASErrorString
0x18000975a  test    cs:byte_1800AA941, 4
0x180009761  jz      short loc_1800097B3
0x180009763  lea     r8, [rsp+880h+var_840]
0x180009768  lea     rdx, RasVpnIkeTraceError
0x18000976f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009776  call    McTemplateU0z_EventWriteTransfer
0x18000977b  jmp     short loc_1800097B3
0x18000977d  lea     rdx, [rsp+880h+ServiceStatus]; lpServiceStatus
0x180009782  mov     rcx, rdi; hService
0x180009785  call    cs:__imp_QueryServiceStatus
0x18000978b  test    eax, eax
0x18000978d  jnz     short loc_1800097A7
0x18000978f  call    cs:__imp_GetLastError
0x180009795  test    cs:byte_1800AA941, 4
0x18000979c  jz      short loc_1800097B3
0x18000979e  lea     rdx, aQueryservicest_0; "QueryServiceStatus failed with error: %"...
0x1800097a5  jmp     short loc_180009746
0x1800097a7  cmp     [rsp+880h+ServiceStatus.dwCurrentState], 4
0x1800097ac  movzx   ebx, bl
0x1800097af  cmovz   ebx, r14d
0x1800097b3  mov     rcx, rsi; hSCObject
0x1800097b6  call    cs:__imp_CloseServiceHandle
0x1800097bc  test    rdi, rdi
0x1800097bf  jz      short loc_1800097CA
0x1800097c1  mov     rcx, rdi; hSCObject
0x1800097c4  call    cs:__imp_CloseServiceHandle
0x1800097ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097d1  cmp     rcx, r15
0x1800097d4  jz      short loc_1800097FA
0x1800097d6  test    [rcx+1Ch], r14b
0x1800097da  jz      short loc_1800097FA
0x1800097dc  cmp     byte ptr [rcx+19h], 6
0x1800097e0  jb      short loc_1800097FA
0x1800097e2  mov     rcx, [rcx+10h]
0x1800097e6  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x1800097ed  mov     edx, 11h
0x1800097f2  mov     r9b, bl
0x1800097f5  call    WPP_SF_c
0x1800097fa  mov     al, bl
0x1800097fc  mov     rcx, [rbp+780h+var_40]
0x180009803  xor     rcx, rsp; StackCookie
0x180009806  call    __security_check_cookie
0x18000980b  add     rsp, 858h
0x180009812  pop     r15
0x180009814  pop     r14
0x180009816  pop     rdi
0x180009817  pop     rsi
0x180009818  pop     rbx
0x180009819  pop     rbp
0x18000981a  retn
```
