# ForceCryptServiceToStart

- ea: `0x18004da6c`
- end: `0x18004dc1d`
- name: `ForceCryptServiceToStart`
- size: `433`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, DWORD dwStartType)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180005920`

## callees

- `0x180005d00`
- `0x18004da6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dbfb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dbfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004daf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004daf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbdf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004db2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004db2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004db6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004db6a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004daa1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004daa1`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18004dbca`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18004dbca`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004dbea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004dbf3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004dbea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004dbf3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004dad9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004dad9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004db15`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004db52`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004db15`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004db52`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18004dba3`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18004dba3`

## pseudocode

```c
__int64 __fastcall ForceCryptServiceToStart(LPCWSTR lpServiceName, DWORD dwStartType)
{
  unsigned int v4; // r14d
  SC_HANDLE v5; // rax
  unsigned __int16 *v6; // rcx
  SC_HANDLE v7; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v9; // rax
  unsigned __int16 *v10; // rcx
  SC_HANDLE v11; // rdi
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  struct _QUERY_SERVICE_CONFIGW *v13; // rbp
  BOOL v14; // ebx
  unsigned __int16 *v15; // rcx
  unsigned int v16; // r8d
  int lpBinaryPathName; // [rsp+20h] [rbp-68h]
  int lpLoadOrderGroup; // [rsp+28h] [rbp-60h]
  DWORD pcbBytesNeeded; // [rsp+A0h] [rbp+18h] BYREF

  pcbBytesNeeded = 0;
  v4 = 0;
  v5 = OpenSCManagerW(0, 0, 0xE0000000);
  v7 = v5;
  if ( v5 )
  {
    v9 = OpenServiceW(v5, lpServiceName, 0x13u);
    v11 = v9;
    if ( !v9 )
    {
      ErrLog_LogError(v10, 4u, 0xC0u, 0, lpBinaryPathName, lpLoadOrderGroup);
      LastError = GetLastError();
LABEL_17:
      CloseServiceHandle(v7);
      goto LABEL_18;
    }
    if ( QueryServiceConfigW(v9, 0, 0, &pcbBytesNeeded) )
    {
      v12 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded);
      v13 = v12;
      if ( v12 )
      {
        v14 = !QueryServiceConfigW(v11, v12, pcbBytesNeeded, &pcbBytesNeeded);
        if ( v13->dwStartType == 4 )
          v14 = 1;
        LocalFree(v13);
        if ( !v14 )
          goto LABEL_21;
      }
    }
    if ( ChangeServiceConfigW(v11, 0xFFFFFFFF, dwStartType, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
LABEL_21:
      if ( StartServiceW(v11, 0, 0) )
      {
        v4 = 1;
        goto LABEL_16;
      }
      v16 = 259;
    }
    else
    {
      v16 = 250;
    }
    ErrLog_LogError(v15, 4u, v16, 0, lpBinaryPathName, lpLoadOrderGroup);
LABEL_16:
    LastError = GetLastError();
    CloseServiceHandle(v11);
    goto LABEL_17;
  }
  ErrLog_LogError(v6, 4u, 0xB6u, 0, lpBinaryPathName, lpLoadOrderGroup);
  LastError = GetLastError();
LABEL_18:
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x18004da6c  mov     rax, rsp
0x18004da6f  mov     [rax+8], rbx
0x18004da73  mov     [rax+10h], rbp
0x18004da77  mov     [rax+18h], r8d
0x18004da7b  push    rsi
0x18004da7c  push    rdi
0x18004da7d  push    r13
0x18004da7f  push    r14
0x18004da81  push    r15
0x18004da83  sub     rsp, 60h
0x18004da87  mov     r15d, edx
0x18004da8a  mov     dword ptr [rax+18h], 0
0x18004da91  mov     rbx, rcx
0x18004da94  xor     edx, edx; lpDatabaseName
0x18004da96  xor     ecx, ecx; lpMachineName
0x18004da98  mov     r8d, 0E0000000h; dwDesiredAccess
0x18004da9e  xor     r14d, r14d
0x18004daa1  call    cs:__imp_OpenSCManagerW
0x18004daa7  mov     rsi, rax
0x18004daaa  test    rax, rax
0x18004daad  jnz     short loc_18004DACD
0x18004daaf  xor     r9d, r9d; unsigned int
0x18004dab2  lea     edx, [rax+4]; unsigned int
0x18004dab5  mov     r8d, 0B6h; unsigned int
0x18004dabb  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18004dac0  call    cs:__imp_GetLastError
0x18004dac6  mov     ebx, eax
0x18004dac8  jmp     loc_18004DBF9
0x18004dacd  mov     r8d, 13h; dwDesiredAccess
0x18004dad3  mov     rdx, rbx; lpServiceName
0x18004dad6  mov     rcx, rsi; hSCManager
0x18004dad9  call    cs:__imp_OpenServiceW
0x18004dadf  mov     rdi, rax
0x18004dae2  test    rax, rax
0x18004dae5  jnz     short loc_18004DB05
0x18004dae7  xor     r9d, r9d; unsigned int
0x18004daea  lea     edx, [rax+4]; unsigned int
0x18004daed  mov     r8d, 0C0h; unsigned int
0x18004daf3  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18004daf8  call    cs:__imp_GetLastError
0x18004dafe  mov     ebx, eax
0x18004db00  jmp     loc_18004DBF0
0x18004db05  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18004db0d  xor     r8d, r8d; cbBufSize
0x18004db10  xor     edx, edx; lpServiceConfig
0x18004db12  mov     rcx, rdi; hService
0x18004db15  call    cs:__imp_QueryServiceConfigW
0x18004db1b  mov     r13d, 1
0x18004db21  test    eax, eax
0x18004db23  jz      short loc_18004DB74
0x18004db25  mov     edx, [rsp+88h+pcbBytesNeeded]; uBytes
0x18004db2c  xor     ecx, ecx; uFlags
0x18004db2e  call    cs:__imp_LocalAlloc
0x18004db34  mov     rbp, rax
0x18004db37  test    rax, rax
0x18004db3a  jz      short loc_18004DB74
0x18004db3c  mov     r8d, [rsp+88h+pcbBytesNeeded]; cbBufSize
0x18004db44  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18004db4c  mov     rdx, rax; lpServiceConfig
0x18004db4f  mov     rcx, rdi; hService
0x18004db52  call    cs:__imp_QueryServiceConfigW
0x18004db58  xor     ebx, ebx
0x18004db5a  mov     rcx, rbp; hMem
0x18004db5d  test    eax, eax
0x18004db5f  setz    bl
0x18004db62  cmp     dword ptr [rbp+4], 4
0x18004db66  cmovz   ebx, r13d
0x18004db6a  call    cs:__imp_LocalFree
0x18004db70  test    ebx, ebx
0x18004db72  jz      short loc_18004DBC2
0x18004db74  mov     [rsp+88h+lpDisplayName], r14; lpDisplayName
0x18004db79  or      edx, 0FFFFFFFFh; dwServiceType
0x18004db7c  mov     [rsp+88h+lpPassword], r14; lpPassword
0x18004db81  mov     r9d, edx; dwErrorControl
0x18004db84  mov     [rsp+88h+lpServiceStartName], r14; lpServiceStartName
0x18004db89  mov     r8d, r15d; dwStartType
0x18004db8c  mov     [rsp+88h+lpDependencies], r14; lpDependencies
0x18004db91  mov     rcx, rdi; hService
0x18004db94  mov     [rsp+88h+lpdwTagId], r14; lpdwTagId
0x18004db99  mov     [rsp+88h+lpLoadOrderGroup], r14; int
0x18004db9e  mov     [rsp+88h+lpBinaryPathName], r14; int
0x18004dba3  call    cs:__imp_ChangeServiceConfigW
0x18004dba9  test    eax, eax
0x18004dbab  jnz     short loc_18004DBC2
0x18004dbad  mov     r8d, 0FAh; unsigned int
0x18004dbb3  mov     edx, 4; unsigned int
0x18004dbb8  xor     r9d, r9d; unsigned int
0x18004dbbb  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18004dbc0  jmp     short loc_18004DBDF
0x18004dbc2  xor     r8d, r8d; lpServiceArgVectors
0x18004dbc5  xor     edx, edx; dwNumServiceArgs
0x18004dbc7  mov     rcx, rdi; hService
0x18004dbca  call    cs:__imp_StartServiceW
0x18004dbd0  test    eax, eax
0x18004dbd2  jnz     short loc_18004DBDC
0x18004dbd4  mov     r8d, 103h
0x18004dbda  jmp     short loc_18004DBB3
0x18004dbdc  mov     r14d, r13d
0x18004dbdf  call    cs:__imp_GetLastError
0x18004dbe5  mov     rcx, rdi; hSCObject
0x18004dbe8  mov     ebx, eax
0x18004dbea  call    cs:__imp_CloseServiceHandle
0x18004dbf0  mov     rcx, rsi; hSCObject
0x18004dbf3  call    cs:__imp_CloseServiceHandle
0x18004dbf9  mov     ecx, ebx; dwErrCode
0x18004dbfb  call    cs:__imp_SetLastError
0x18004dc01  lea     r11, [rsp+88h+var_28]
0x18004dc06  mov     eax, r14d
0x18004dc09  mov     rbx, [r11+30h]
0x18004dc0d  mov     rbp, [r11+38h]
0x18004dc11  mov     rsp, r11
0x18004dc14  pop     r15
0x18004dc16  pop     r14
0x18004dc18  pop     r13
0x18004dc1a  pop     rdi
0x18004dc1b  pop     rsi
0x18004dc1c  retn
```
