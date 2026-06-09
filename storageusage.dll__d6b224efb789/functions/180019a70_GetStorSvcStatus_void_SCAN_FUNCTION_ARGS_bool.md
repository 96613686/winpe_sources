# GetStorSvcStatus(void *,SCAN_FUNCTION_ARGS,bool &)

- ea: `0x180019a70`
- end: `0x180019c2b`
- name: `?GetStorSvcStatus@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800010b0`
- `0x180001a7c`
- `0x180019590`
- `0x180019a70`
- `0x18001ac48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019b3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019b3b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180019b0c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180019b57`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180019b0c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180019b57`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180019b87`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180019b90`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180019b87`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180019b90`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180019ae6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180019ae6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180019abc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180019abc`

## pseudocode

```c
__int64 __fastcall GetStorSvcStatus(const unsigned __int16 *a1)
{
  int v1; // eax
  DWORD dwStartType; // r15d
  int v3; // r12d
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r14
  DWORD LastWin32Error; // ebx
  __int64 v7; // r8
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rdi
  DWORD v10; // ebx
  HANDLE v11; // rax
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  struct _QUERY_SERVICE_CONFIGW *v13; // rsi
  HANDLE ProcessHeap; // rax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v19; // [rsp+50h] [rbp-9h] BYREF
  DWORD v20; // [rsp+54h] [rbp-5h] BYREF
  DWORD dwCurrentState; // [rsp+58h] [rbp-1h] BYREF
  __int64 v22; // [rsp+60h] [rbp+7h] BYREF
  _SERVICE_STATUS_PROCESS v23; // [rsp+68h] [rbp+Fh] BYREF
  DWORD pcbBytesNeeded; // [rsp+D8h] [rbp+7Fh] BYREF

  memset(&v23, 0, sizeof(v23));
  v1 = QuerySvcStatus(a1, &v23);
  dwStartType = 0;
  pcbBytesNeeded = 0;
  v3 = v1;
  v4 = OpenSCManagerW(0, 0, 4u);
  v5 = v4;
  if ( v4 )
  {
    v8 = OpenServiceW(v4, L"StorSvc", 1u);
    v9 = v8;
    if ( v8 )
    {
      if ( (QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded) || GetLastError() == 122)
        && (v10 = pcbBytesNeeded,
            v11 = GetProcessHeap(),
            v12 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(v11, 0, v10),
            (v13 = v12) != 0) )
      {
        if ( QueryServiceConfigW(v9, v12, pcbBytesNeeded, &pcbBytesNeeded) )
        {
          dwStartType = v13->dwStartType;
          LastWin32Error = 0;
        }
        else
        {
          LastWin32Error = GetLastWin32Error();
        }
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v13);
      }
      else
      {
        LastWin32Error = GetLastWin32Error();
      }
      CloseServiceHandle(v9);
    }
    else
    {
      LastWin32Error = GetLastWin32Error();
    }
    CloseServiceHandle(v5);
  }
  else
  {
    LastWin32Error = GetLastWin32Error();
  }
  if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL, v7) )
  {
    dwCurrentState = v23.dwCurrentState;
    v22 = 0x1000000;
    pcbBytesNeeded = LastWin32Error;
    v19 = v3;
    v20 = dwStartType;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v15,
      (unsigned int)qword_180037F00,
      v16,
      v17,
      (__int64)&dwCurrentState,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&pcbBytesNeeded,
      (__int64)&v22);
  }
  return 0;
}

```

## disassembly

```asm
0x180019a70  mov     [rsp-8+arg_0], rbx
0x180019a75  mov     [rsp-8+arg_8], rsi
0x180019a7a  push    rbp
0x180019a7b  push    rdi
0x180019a7c  push    r12
0x180019a7e  push    r14
0x180019a80  push    r15
0x180019a82  lea     rbp, [rsp-37h]
0x180019a87  sub     rsp, 90h
0x180019a8e  xorps   xmm0, xmm0
0x180019a91  lea     rdx, [rbp+57h+var_48]; struct _SERVICE_STATUS_PROCESS *
0x180019a95  xor     eax, eax
0x180019a97  movups  xmmword ptr [rbp+57h+var_48.dwServiceType], xmm0
0x180019a9b  mov     [rbp+57h+var_48.dwServiceFlags], eax
0x180019a9e  movups  xmmword ptr [rbp+57h+var_48.dwServiceSpecificExitCode], xmm0
0x180019aa2  call    ?QuerySvcStatus@@YAJPEBGPEAU_SERVICE_STATUS_PROCESS@@@Z; QuerySvcStatus(ushort const *,_SERVICE_STATUS_PROCESS *)
0x180019aa7  xor     r15d, r15d
0x180019aaa  mov     [rbp+57h+pcbBytesNeeded], 0
0x180019ab1  xor     edx, edx; lpDatabaseName
0x180019ab3  xor     ecx, ecx; lpMachineName
0x180019ab5  mov     r12d, eax
0x180019ab8  lea     r8d, [r15+4]; dwDesiredAccess
0x180019abc  call    cs:__imp_OpenSCManagerW
0x180019ac2  mov     r14, rax
0x180019ac5  test    rax, rax
0x180019ac8  jnz     short loc_180019AD6
0x180019aca  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180019acf  mov     ebx, eax
0x180019ad1  jmp     loc_180019B96
0x180019ad6  mov     r8d, 1; dwDesiredAccess
0x180019adc  lea     rdx, ServiceName; "StorSvc"
0x180019ae3  mov     rcx, r14; hSCManager
0x180019ae6  call    cs:__imp_OpenServiceW
0x180019aec  mov     rdi, rax
0x180019aef  test    rax, rax
0x180019af2  jnz     short loc_180019B00
0x180019af4  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180019af9  mov     ebx, eax
0x180019afb  jmp     loc_180019B8D
0x180019b00  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180019b04  xor     r8d, r8d; cbBufSize
0x180019b07  xor     edx, edx; lpServiceConfig
0x180019b09  mov     rcx, rdi; hService
0x180019b0c  call    cs:__imp_QueryServiceConfigW
0x180019b12  test    eax, eax
0x180019b14  jnz     short loc_180019B2A
0x180019b16  call    cs:__imp_GetLastError
0x180019b1c  cmp     eax, 7Ah ; 'z'
0x180019b1f  jz      short loc_180019B2A
0x180019b21  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180019b26  mov     ebx, eax
0x180019b28  jmp     short loc_180019B84
0x180019b2a  mov     ebx, [rbp+57h+pcbBytesNeeded]
0x180019b2d  call    cs:__imp_GetProcessHeap
0x180019b33  mov     r8d, ebx; dwBytes
0x180019b36  xor     edx, edx; dwFlags
0x180019b38  mov     rcx, rax; hHeap
0x180019b3b  call    cs:__imp_HeapAlloc
0x180019b41  mov     rsi, rax
0x180019b44  test    rax, rax
0x180019b47  jz      short loc_180019B21
0x180019b49  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x180019b4d  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180019b51  mov     rdx, rax; lpServiceConfig
0x180019b54  mov     rcx, rdi; hService
0x180019b57  call    cs:__imp_QueryServiceConfigW
0x180019b5d  test    eax, eax
0x180019b5f  jnz     short loc_180019B6A
0x180019b61  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180019b66  mov     ebx, eax
0x180019b68  jmp     short loc_180019B70
0x180019b6a  mov     r15d, [rsi+4]
0x180019b6e  xor     ebx, ebx
0x180019b70  call    cs:__imp_GetProcessHeap
0x180019b76  mov     r8, rsi; lpMem
0x180019b79  xor     edx, edx; dwFlags
0x180019b7b  mov     rcx, rax; hHeap
0x180019b7e  call    cs:__imp_HeapFree
0x180019b84  mov     rcx, rdi; hSCObject
0x180019b87  call    cs:__imp_CloseServiceHandle
0x180019b8d  mov     rcx, r14; hSCObject
0x180019b90  call    cs:__imp_CloseServiceHandle
0x180019b96  mov     eax, cs:dword_180040010
0x180019b9c  cmp     eax, 5
0x180019b9f  jbe     short loc_180019C0D
0x180019ba1  mov     rdx, 400000000000h
0x180019bab  lea     rcx, dword_180040010
0x180019bb2  call    _tlgKeywordOn
0x180019bb7  test    al, al
0x180019bb9  jz      short loc_180019C0D
0x180019bbb  mov     eax, [rbp+57h+var_48.dwCurrentState]
0x180019bbe  lea     rdx, qword_180037F00
0x180019bc5  mov     [rbp+57h+var_58], eax
0x180019bc8  lea     rax, [rbp+57h+var_50]
0x180019bcc  mov     [rsp+0B0h+var_70], rax
0x180019bd1  lea     rax, [rbp+57h+pcbBytesNeeded]
0x180019bd5  mov     [rsp+0B0h+var_78], rax
0x180019bda  lea     rax, [rbp+57h+var_60]
0x180019bde  mov     [rsp+0B0h+var_80], rax
0x180019be3  lea     rax, [rbp+57h+var_5C]
0x180019be7  mov     [rsp+0B0h+var_88], rax
0x180019bec  lea     rax, [rbp+57h+var_58]
0x180019bf0  mov     [rsp+0B0h+var_90], rax
0x180019bf5  mov     [rbp+57h+var_50], 1000000h
0x180019bfd  mov     [rbp+57h+pcbBytesNeeded], ebx
0x180019c00  mov     [rbp+57h+var_60], r12d
0x180019c04  mov     [rbp+57h+var_5C], r15d
0x180019c08  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180019c0d  lea     r11, [rsp+0B0h+var_20]
0x180019c15  xor     eax, eax
0x180019c17  mov     rbx, [r11+30h]
0x180019c1b  mov     rsi, [r11+38h]
0x180019c1f  mov     rsp, r11
0x180019c22  pop     r15
0x180019c24  pop     r14
0x180019c26  pop     r12
0x180019c28  pop     rdi
0x180019c29  pop     rbp
0x180019c2a  retn
```
