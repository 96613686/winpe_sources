# SetTetheringServiceStatus(ulong,ulong)

- ea: `0x18000b774`
- end: `0x18000b87f`
- name: `?SetTetheringServiceStatus@@YAXKK@Z`
- size: `267`
- prototype: `void __fastcall(DWORD, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000ae30`
- `0x18000b370`
- `0x18000b680`
- `0x18000b888`

## callees

- `0x18000b774`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000bff4`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b806`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b806`

## pseudocode

```c
void __fastcall SetTetheringServiceStatus(DWORD a1, __int64 a2, __int64 a3)
{
  DWORD v3; // edi
  TetheringServiceTelemetry *v5; // rcx
  TetheringServiceTelemetry *v6; // rcx

  v3 = a2;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v5 + 2), 19, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, a1);
  }
  g_ServiceStatus.dwCurrentState = a1;
  g_ServiceStatus.dwWin32ExitCode = v3;
  if ( a1 - 2 <= 1 )
    g_ServiceStatus.dwWaitHint = 50;
  if ( SetServiceStatus(hServiceStatus, &g_ServiceStatus) )
    goto LABEL_13;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, v3);
LABEL_13:
    v6 = WPP_GLOBAL_Control;
  }
  g_ServiceStatus.dwWaitHint = 0;
  g_ErrorCode = v3;
  if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v6 + 2), 21, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
}

```

## disassembly

```asm
0x18000b774  mov     [rsp+arg_0], rbx
0x18000b779  mov     [rsp+arg_8], rsi
0x18000b77e  push    rdi
0x18000b77f  sub     rsp, 30h
0x18000b783  mov     edi, edx
0x18000b785  mov     ebx, ecx
0x18000b787  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b78e  lea     rsi, WPP_GLOBAL_Control
0x18000b795  cmp     rcx, rsi
0x18000b798  jz      short loc_18000B7DA
0x18000b79a  test    byte ptr [rcx+1Ch], 8
0x18000b79e  jz      short loc_18000B7B7
0x18000b7a0  mov     rcx, [rcx+10h]
0x18000b7a4  mov     r9d, ebx
0x18000b7a7  mov     [rsp+38h+var_18], edx
0x18000b7ab  call    WPP_SF_dD
0x18000b7b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7b7  cmp     rcx, rsi
0x18000b7ba  jz      short loc_18000B7DA
0x18000b7bc  test    byte ptr [rcx+1Ch], 4
0x18000b7c0  jz      short loc_18000B7DA
0x18000b7c2  mov     rcx, [rcx+10h]
0x18000b7c6  lea     r8, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000b7cd  mov     edx, 13h
0x18000b7d2  mov     r9d, ebx
0x18000b7d5  call    WPP_SF_d
0x18000b7da  lea     eax, [rbx-2]
0x18000b7dd  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ebx; _SERVICE_STATUS g_ServiceStatus ...
0x18000b7e3  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, edi; _SERVICE_STATUS g_ServiceStatus ...
0x18000b7e9  cmp     eax, 1
0x18000b7ec  ja      short loc_18000B7F8
0x18000b7ee  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 32h ; '2'; _SERVICE_STATUS g_ServiceStatus ...
0x18000b7f8  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000b7ff  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18000b806  call    cs:__imp_SetServiceStatus
0x18000b80c  test    eax, eax
0x18000b80e  jnz     short loc_18000B838
0x18000b810  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b817  cmp     rcx, rsi
0x18000b81a  jz      short loc_18000B83F
0x18000b81c  test    byte ptr [rcx+1Ch], 1
0x18000b820  jz      short loc_18000B83F
0x18000b822  mov     rcx, [rcx+10h]
0x18000b826  lea     edx, [rax+14h]
0x18000b829  mov     r9d, edi
0x18000b82c  lea     r8, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000b833  call    WPP_SF_d
0x18000b838  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b83f  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0; _SERVICE_STATUS g_ServiceStatus ...
0x18000b849  mov     cs:?g_ErrorCode@@3KA, edi; ulong g_ErrorCode
0x18000b84f  cmp     rcx, rsi
0x18000b852  jz      short loc_18000B86F
0x18000b854  test    byte ptr [rcx+1Ch], 8
0x18000b858  jz      short loc_18000B86F
0x18000b85a  mov     rcx, [rcx+10h]
0x18000b85e  lea     r8, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000b865  mov     edx, 15h
0x18000b86a  call    WPP_SF_
0x18000b86f  mov     rbx, [rsp+38h+arg_0]
0x18000b874  mov     rsi, [rsp+38h+arg_8]
0x18000b879  add     rsp, 30h
0x18000b87d  pop     rdi
0x18000b87e  retn
```
