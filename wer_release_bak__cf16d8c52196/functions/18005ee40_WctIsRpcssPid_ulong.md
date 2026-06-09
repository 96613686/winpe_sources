# WctIsRpcssPid(ulong)

- ea: `0x18005ee40`
- end: `0x18005efcd`
- name: `?WctIsRpcssPid@@YAHK@Z`
- size: `397`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18004e684`

## callees

- `0x180004bb4`
- `0x18001c650`
- `0x18001fe24`
- `0x18005ee40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ef20`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ef20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eefc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eefc`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005eef2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005ef61`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005eef2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005ef61`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005eecc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005eecc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef7a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef83`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef7a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef83`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005eeac`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005eeac`

## pseudocode

```c
__int64 __fastcall WctIsRpcssPid(int a1)
{
  wchar_t *v2; // rcx
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  SC_HANDLE v6; // rdi
  DWORD v7; // eax
  BYTE *v8; // rax
  BYTE *v9; // r14
  DWORD cbBufSize; // [rsp+70h] [rbp+40h] BYREF
  BYTE *v12; // [rsp+78h] [rbp+48h] BYREF
  __int64 v13; // [rsp+80h] [rbp+50h] BYREF

  cbBufSize = 0;
  v12 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( a1 )
  {
    v4 = OpenSCManagerW(0, 0, 1u);
    v5 = v4;
    if ( !v4 )
    {
LABEL_17:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    v6 = OpenServiceW(v4, L"RPCSS", 4u);
    if ( !v6 )
    {
LABEL_16:
      CloseServiceHandle(v5);
      goto LABEL_17;
    }
    if ( QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, 0, 0, &cbBufSize) )
    {
      v7 = 4096;
      cbBufSize = 4096;
    }
    else
    {
      if ( GetLastError() != 122 )
      {
LABEL_15:
        CloseServiceHandle(v6);
        goto LABEL_16;
      }
      v7 = cbBufSize;
    }
    v8 = (BYTE *)HeapAlloc(g_hWerheap, 0, v7);
    v12 = 0;
    v9 = v8;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v12);
    v13 = 0;
    v12 = v9;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v13);
    if ( v9 && QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, v9, cbBufSize, &cbBufSize) && a1 == *((_DWORD *)v9 + 7) )
      v3 = 1;
    goto LABEL_15;
  }
LABEL_18:
  if ( v2 != (wchar_t *)&WPP_GLOBAL_Control && (v2[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)v2 + 2), 37, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v3);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v12);
  return v3;
}

```

## disassembly

```asm
0x18005ee40  push    rbp
0x18005ee42  push    rbx
0x18005ee43  push    rsi
0x18005ee44  push    rdi
0x18005ee45  push    r13
0x18005ee47  push    r14
0x18005ee49  push    r15
0x18005ee4b  mov     rbp, rsp
0x18005ee4e  sub     rsp, 30h
0x18005ee52  mov     r15d, ecx
0x18005ee55  mov     [rbp+cbBufSize], 0
0x18005ee5c  mov     [rbp+arg_8], 0
0x18005ee64  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee6b  lea     r13, WPP_GLOBAL_Control
0x18005ee72  cmp     rcx, r13
0x18005ee75  jz      short loc_18005EE99
0x18005ee77  test    byte ptr [rcx+1Ch], 4
0x18005ee7b  jz      short loc_18005EE99
0x18005ee7d  mov     rcx, [rcx+10h]
0x18005ee81  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005ee88  mov     edx, 24h ; '$'
0x18005ee8d  call    WPP_SF_
0x18005ee92  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee99  xor     ebx, ebx
0x18005ee9b  test    r15d, r15d
0x18005ee9e  jz      loc_18005EF90
0x18005eea4  xor     edx, edx; lpDatabaseName
0x18005eea6  lea     r8d, [rbx+1]; dwDesiredAccess
0x18005eeaa  xor     ecx, ecx; lpMachineName
0x18005eeac  call    cs:__imp_OpenSCManagerW
0x18005eeb2  mov     rsi, rax
0x18005eeb5  test    rax, rax
0x18005eeb8  jz      loc_18005EF89
0x18005eebe  lea     r8d, [rbx+4]; dwDesiredAccess
0x18005eec2  mov     rcx, rax; hSCManager
0x18005eec5  lea     rdx, ServiceName; "RPCSS"
0x18005eecc  call    cs:__imp_OpenServiceW
0x18005eed2  mov     rdi, rax
0x18005eed5  test    rax, rax
0x18005eed8  jz      loc_18005EF80
0x18005eede  lea     rax, [rbp+cbBufSize]
0x18005eee2  xor     r9d, r9d; cbBufSize
0x18005eee5  xor     r8d, r8d; lpBuffer
0x18005eee8  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005eeed  xor     edx, edx; InfoLevel
0x18005eeef  mov     rcx, rdi; hService
0x18005eef2  call    cs:__imp_QueryServiceStatusEx
0x18005eef8  test    eax, eax
0x18005eefa  jnz     short loc_18005EF0C
0x18005eefc  call    cs:__imp_GetLastError
0x18005ef02  cmp     eax, 7Ah ; 'z'
0x18005ef05  jnz     short loc_18005EF77
0x18005ef07  mov     eax, [rbp+cbBufSize]
0x18005ef0a  jmp     short loc_18005EF14
0x18005ef0c  mov     eax, 1000h
0x18005ef11  mov     [rbp+cbBufSize], eax
0x18005ef14  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18005ef1b  xor     edx, edx; dwFlags
0x18005ef1d  mov     r8d, eax; dwBytes
0x18005ef20  call    cs:__imp_HeapAlloc
0x18005ef26  lea     rcx, [rbp+arg_8]; void *
0x18005ef2a  mov     [rbp+arg_8], rbx
0x18005ef2e  mov     r14, rax
0x18005ef31  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005ef36  lea     rcx, [rbp+arg_10]; void *
0x18005ef3a  mov     [rbp+arg_10], rbx
0x18005ef3e  mov     [rbp+arg_8], r14
0x18005ef42  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005ef47  test    r14, r14
0x18005ef4a  jz      short loc_18005EF77
0x18005ef4c  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x18005ef50  lea     rax, [rbp+cbBufSize]
0x18005ef54  mov     r8, r14; lpBuffer
0x18005ef57  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005ef5c  xor     edx, edx; InfoLevel
0x18005ef5e  mov     rcx, rdi; hService
0x18005ef61  call    cs:__imp_QueryServiceStatusEx
0x18005ef67  test    eax, eax
0x18005ef69  jz      short loc_18005EF77
0x18005ef6b  cmp     r15d, [r14+1Ch]
0x18005ef6f  mov     eax, 1
0x18005ef74  cmovz   ebx, eax
0x18005ef77  mov     rcx, rdi; hSCObject
0x18005ef7a  call    cs:__imp_CloseServiceHandle
0x18005ef80  mov     rcx, rsi; hSCObject
0x18005ef83  call    cs:__imp_CloseServiceHandle
0x18005ef89  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ef90  cmp     rcx, r13
0x18005ef93  jz      short loc_18005EFB3
0x18005ef95  test    byte ptr [rcx+1Ch], 4
0x18005ef99  jz      short loc_18005EFB3
0x18005ef9b  mov     rcx, [rcx+10h]
0x18005ef9f  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005efa6  mov     edx, 25h ; '%'
0x18005efab  mov     r9d, ebx
0x18005efae  call    WPP_SF_d
0x18005efb3  lea     rcx, [rbp+arg_8]; void *
0x18005efb7  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005efbc  mov     eax, ebx
0x18005efbe  add     rsp, 30h
0x18005efc2  pop     r15
0x18005efc4  pop     r14
0x18005efc6  pop     r13
0x18005efc8  pop     rdi
0x18005efc9  pop     rsi
0x18005efca  pop     rbx
0x18005efcb  pop     rbp
0x18005efcc  retn
```
