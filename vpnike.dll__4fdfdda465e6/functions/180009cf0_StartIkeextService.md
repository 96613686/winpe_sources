# StartIkeextService

- ea: `0x180009cf0`
- end: `0x180009ee2`
- name: `StartIkeextService`
- size: `498`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039278`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x180009cf0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e29`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180009d6b`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180009d6b`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180009e1f`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180009e1f`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180009de3`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180009de3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180009e7f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180009e8d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180009e7f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180009e8d`

## string_xrefs

- `0x180009d90`: `OpenSCManager failed with error: %d`
- `0x180009e04`: `OpenService failed with error: %d`
- `0x180009e42`: `StartService failed with error: %d`

## pseudocode

```c
__int64 StartIkeextService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  DWORD LastError; // eax
  DWORD v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  DWORD v6; // eax
  DWORD v7; // eax
  int v9; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v10[2044]; // [rsp+24h] [rbp-DCh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids);
  }
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  v0 = OpenSCManagerA(0, 0, 1u);
  v1 = v0;
  if ( !v0 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"OpenSCManager failed with error: %d", LastError);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v9);
    }
    goto LABEL_21;
  }
  v4 = OpenServiceA(v0, "ikeext", 0x14u);
  v5 = v4;
  if ( v4 )
  {
    v3 = 0;
    if ( StartServiceA(v4, 0, 0) )
      goto LABEL_19;
    v7 = GetLastError();
    if ( v7 != 1056 )
      v3 = v7;
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_19;
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"StartService failed with error: %d", v3);
    goto LABEL_17;
  }
  v6 = GetLastError();
  v3 = v6;
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"OpenService failed with error: %d", v6);
LABEL_17:
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v9);
  }
LABEL_19:
  CloseServiceHandle(v1);
  if ( v5 )
    CloseServiceHandle(v5);
LABEL_21:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180009cf0  push    rbp
0x180009cf2  push    rbx
0x180009cf3  push    rsi
0x180009cf4  push    rdi
0x180009cf5  push    r14
0x180009cf7  lea     rbp, [rsp-730h]
0x180009cff  sub     rsp, 830h
0x180009d06  mov     rax, cs:__security_cookie
0x180009d0d  xor     rax, rsp
0x180009d10  mov     [rbp+750h+var_30], rax
0x180009d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d1e  lea     r14, WPP_GLOBAL_Control
0x180009d25  cmp     rcx, r14
0x180009d28  jz      short loc_180009D4B
0x180009d2a  test    byte ptr [rcx+1Ch], 1
0x180009d2e  jz      short loc_180009D4B
0x180009d30  cmp     byte ptr [rcx+19h], 6
0x180009d34  jb      short loc_180009D4B
0x180009d36  mov     rcx, [rcx+10h]
0x180009d3a  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x180009d41  mov     edx, 12h
0x180009d46  call    WPP_SF_
0x180009d4b  xor     eax, eax
0x180009d4d  lea     rcx, [rsp+850h+var_82C]; void *
0x180009d52  xor     edx, edx; Val
0x180009d54  mov     [rsp+850h+var_830], eax
0x180009d58  mov     r8d, 7FCh; Size
0x180009d5e  call    memset_0
0x180009d63  xor     edx, edx; lpDatabaseName
0x180009d65  xor     ecx, ecx; lpMachineName
0x180009d67  lea     r8d, [rdx+1]; dwDesiredAccess
0x180009d6b  call    cs:__imp_OpenSCManagerA
0x180009d71  mov     rsi, rax
0x180009d74  test    rax, rax
0x180009d77  jnz     short loc_180009DD3
0x180009d79  call    cs:__imp_GetLastError
0x180009d7f  test    cs:byte_1800AA941, 4
0x180009d86  mov     ebx, eax
0x180009d88  jz      loc_180009E93
0x180009d8e  xor     ecx, ecx
0x180009d90  lea     rdx, aOpenscmanagerF; "OpenSCManager failed with error: %d"
0x180009d97  mov     word ptr [rsp+850h+var_830], cx
0x180009d9c  mov     r8d, eax
0x180009d9f  lea     rcx, [rsp+850h+var_830]
0x180009da4  call    FormatRRASErrorString
0x180009da9  test    cs:byte_1800AA941, 4
0x180009db0  jz      loc_180009E93
0x180009db6  lea     r8, [rsp+850h+var_830]
0x180009dbb  lea     rdx, RasVpnIkeTraceError
0x180009dc2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009dc9  call    McTemplateU0z_EventWriteTransfer
0x180009dce  jmp     loc_180009E93
0x180009dd3  mov     r8d, 14h; dwDesiredAccess
0x180009dd9  lea     rdx, ServiceName; "ikeext"
0x180009de0  mov     rcx, rsi; hSCManager
0x180009de3  call    cs:__imp_OpenServiceA
0x180009de9  mov     rdi, rax
0x180009dec  test    rax, rax
0x180009def  jnz     short loc_180009E15
0x180009df1  call    cs:__imp_GetLastError
0x180009df7  test    cs:byte_1800AA941, 4
0x180009dfe  mov     ebx, eax
0x180009e00  jz      short loc_180009E7C
0x180009e02  xor     ecx, ecx
0x180009e04  lea     rdx, aOpenserviceFai; "OpenService failed with error: %d"
0x180009e0b  mov     word ptr [rsp+850h+var_830], cx
0x180009e10  mov     r8d, eax
0x180009e13  jmp     short loc_180009E51
0x180009e15  xor     r8d, r8d; lpServiceArgVectors
0x180009e18  xor     edx, edx; dwNumServiceArgs
0x180009e1a  mov     rcx, rdi; hService
0x180009e1d  xor     ebx, ebx
0x180009e1f  call    cs:__imp_StartServiceA
0x180009e25  test    eax, eax
0x180009e27  jnz     short loc_180009E7C
0x180009e29  call    cs:__imp_GetLastError
0x180009e2f  cmp     eax, 420h
0x180009e34  cmovnz  ebx, eax
0x180009e37  test    cs:byte_1800AA941, 4
0x180009e3e  jz      short loc_180009E7C
0x180009e40  xor     eax, eax
0x180009e42  lea     rdx, aStartserviceFa; "StartService failed with error: %d"
0x180009e49  mov     word ptr [rsp+850h+var_830], ax
0x180009e4e  mov     r8d, ebx
0x180009e51  lea     rcx, [rsp+850h+var_830]
0x180009e56  call    FormatRRASErrorString
0x180009e5b  test    cs:byte_1800AA941, 4
0x180009e62  jz      short loc_180009E7C
0x180009e64  lea     r8, [rsp+850h+var_830]
0x180009e69  lea     rdx, RasVpnIkeTraceError
0x180009e70  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009e77  call    McTemplateU0z_EventWriteTransfer
0x180009e7c  mov     rcx, rsi; hSCObject
0x180009e7f  call    cs:__imp_CloseServiceHandle
0x180009e85  test    rdi, rdi
0x180009e88  jz      short loc_180009E93
0x180009e8a  mov     rcx, rdi; hSCObject
0x180009e8d  call    cs:__imp_CloseServiceHandle
0x180009e93  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e9a  cmp     rcx, r14
0x180009e9d  jz      short loc_180009EC3
0x180009e9f  test    byte ptr [rcx+1Ch], 1
0x180009ea3  jz      short loc_180009EC3
0x180009ea5  cmp     byte ptr [rcx+19h], 6
0x180009ea9  jb      short loc_180009EC3
0x180009eab  mov     rcx, [rcx+10h]
0x180009eaf  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x180009eb6  mov     edx, 13h
0x180009ebb  mov     r9d, ebx
0x180009ebe  call    WPP_SF_d
0x180009ec3  mov     eax, ebx
0x180009ec5  mov     rcx, [rbp+750h+var_30]
0x180009ecc  xor     rcx, rsp; StackCookie
0x180009ecf  call    __security_check_cookie
0x180009ed4  add     rsp, 830h
0x180009edb  pop     r14
0x180009edd  pop     rdi
0x180009ede  pop     rsi
0x180009edf  pop     rbx
0x180009ee0  pop     rbp
0x180009ee1  retn
```
