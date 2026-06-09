# UtilGetServicesInfo

- ea: `0x18000f7e4`
- end: `0x18000f9e8`
- name: `UtilGetServicesInfo`
- size: `516`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18000d640`

## callees

- `0x180002a00`
- `0x180002ff0`
- `0x18000f7e4`
- `0x180011ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f90b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f90b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f924`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000f819`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000f819`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f9bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f9bf`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18000f901`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18000f901`

## pseudocode

```c
__int64 __fastcall UtilGetServicesInfo(void **a1, DWORD *a2)
{
  SC_HANDLE v4; // rbp
  signed int v5; // eax
  unsigned int v6; // edi
  BYTE *v7; // rbx
  DWORD cbBufSize; // esi
  DWORD v9; // eax
  BYTE *v10; // rax
  BYTE *v11; // rcx
  BYTE *lpServices; // rdi
  signed int LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  void *v17; // rcx
  DWORD ResumeHandle[14]; // [rsp+50h] [rbp-38h] BYREF
  DWORD pcbBytesNeeded; // [rsp+A0h] [rbp+18h] BYREF
  DWORD ServicesReturned; // [rsp+A8h] [rbp+20h] BYREF

  ServicesReturned = 0;
  pcbBytesNeeded = 0;
  ResumeHandle[0] = 0;
  v4 = OpenSCManagerW(0, 0, 4u);
  if ( v4 )
  {
    v7 = 0;
    cbBufSize = 4096;
    v9 = 0;
    for ( pcbBytesNeeded = 0; ; v9 = pcbBytesNeeded )
    {
      cbBufSize += v9;
      v10 = (BYTE *)operator new(cbBufSize, (const struct std::nothrow_t *)&std::nothrow);
      v11 = v7;
      lpServices = v10;
      v7 = v10;
      if ( v11 )
        operator delete(v11);
      if ( !lpServices )
        break;
      ResumeHandle[0] = 0;
      if ( EnumServicesStatusExW(
             v4,
             SC_ENUM_PROCESS_INFO,
             0x30u,
             1u,
             lpServices,
             cbBufSize,
             &pcbBytesNeeded,
             &ServicesReturned,
             ResumeHandle,
             0) )
      {
        v17 = *a1;
        v7 = 0;
        *a1 = lpServices;
        if ( v17 )
          operator delete(v17);
        v6 = 0;
        *a2 = ServicesReturned;
        ServicesReturned = 0;
        goto LABEL_26;
      }
      if ( GetLastError() != 234 )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 103;
          v16 = v6;
LABEL_25:
          WPP_SF_d(v14[2], v15, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v16);
          goto LABEL_26;
        }
        goto LABEL_26;
      }
    }
    v6 = -2147024882;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 102;
      v16 = 2147942414LL;
      goto LABEL_25;
    }
LABEL_26:
    CloseServiceHandle(v4);
    if ( v7 )
      operator delete(v7);
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f7e4  mov     rax, rsp
0x18000f7e7  mov     [rax+8], rbx
0x18000f7eb  push    rbp
0x18000f7ec  push    rsi
0x18000f7ed  push    rdi
0x18000f7ee  push    r14
0x18000f7f0  push    r15
0x18000f7f2  sub     rsp, 60h
0x18000f7f6  mov     r15, rdx
0x18000f7f9  mov     dword ptr [rax+20h], 0
0x18000f800  xor     edx, edx; lpDatabaseName
0x18000f802  mov     dword ptr [rax+18h], 0
0x18000f809  mov     r14, rcx
0x18000f80c  mov     dword ptr [rax-38h], 0
0x18000f813  xor     ecx, ecx; lpMachineName
0x18000f815  lea     r8d, [rdx+4]; dwDesiredAccess
0x18000f819  call    cs:__imp_OpenSCManagerW
0x18000f81f  mov     rbp, rax
0x18000f822  test    rax, rax
0x18000f825  jnz     short loc_18000F87A
0x18000f827  call    cs:__imp_GetLastError
0x18000f82d  mov     edi, eax
0x18000f82f  test    eax, eax
0x18000f831  jle     short loc_18000F83C
0x18000f833  movzx   edi, ax
0x18000f836  or      edi, 80070000h
0x18000f83c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f843  lea     rax, WPP_GLOBAL_Control
0x18000f84a  cmp     rcx, rax
0x18000f84d  jz      loc_18000F9D2
0x18000f853  test    byte ptr [rcx+1Ch], 1
0x18000f857  jz      loc_18000F9D2
0x18000f85d  mov     rcx, [rcx+10h]
0x18000f861  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000f868  mov     edx, 65h ; 'e'
0x18000f86d  mov     r9d, edi
0x18000f870  call    WPP_SF_d
0x18000f875  jmp     loc_18000F9D2
0x18000f87a  xor     ebx, ebx
0x18000f87c  mov     esi, 1000h
0x18000f881  xor     eax, eax
0x18000f883  mov     [rsp+88h+arg_10], eax
0x18000f88a  add     esi, eax
0x18000f88c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f893  mov     ecx, esi; unsigned __int64
0x18000f895  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f89a  mov     rcx, rbx; Block
0x18000f89d  mov     rdi, rax
0x18000f8a0  mov     rbx, rax
0x18000f8a3  test    rcx, rcx
0x18000f8a6  jz      short loc_18000F8AD
0x18000f8a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f8ad  test    rdi, rdi
0x18000f8b0  jz      loc_18000F983
0x18000f8b6  mov     [rsp+88h+pszGroupName], 0; pszGroupName
0x18000f8bf  lea     rax, [rsp+88h+ResumeHandle]
0x18000f8c4  mov     [rsp+88h+lpResumeHandle], rax; lpResumeHandle
0x18000f8c9  xor     edx, edx; InfoLevel
0x18000f8cb  lea     rax, [rsp+88h+ServicesReturned]
0x18000f8d3  mov     [rsp+88h+ResumeHandle], 0
0x18000f8db  mov     [rsp+88h+lpServicesReturned], rax; lpServicesReturned
0x18000f8e0  mov     rcx, rbp; hSCManager
0x18000f8e3  lea     rax, [rsp+88h+arg_10]
0x18000f8eb  mov     [rsp+88h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000f8f0  lea     r9d, [rdx+1]; dwServiceState
0x18000f8f4  mov     [rsp+88h+cbBufSize], esi; cbBufSize
0x18000f8f8  lea     r8d, [rdx+30h]; dwServiceType
0x18000f8fc  mov     [rsp+88h+lpServices], rdi; lpServices
0x18000f901  call    cs:__imp_EnumServicesStatusExW
0x18000f907  test    eax, eax
0x18000f909  jnz     short loc_18000F95C
0x18000f90b  call    cs:__imp_GetLastError
0x18000f911  cmp     eax, 0EAh
0x18000f916  jnz     short loc_18000F924
0x18000f918  mov     eax, [rsp+88h+arg_10]
0x18000f91f  jmp     loc_18000F88A
0x18000f924  call    cs:__imp_GetLastError
0x18000f92a  mov     edi, eax
0x18000f92c  test    eax, eax
0x18000f92e  jle     short loc_18000F939
0x18000f930  movzx   edi, ax
0x18000f933  or      edi, 80070000h
0x18000f939  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f940  lea     rax, WPP_GLOBAL_Control
0x18000f947  cmp     rcx, rax
0x18000f94a  jz      short loc_18000F9BC
0x18000f94c  test    byte ptr [rcx+1Ch], 1
0x18000f950  jz      short loc_18000F9BC
0x18000f952  mov     edx, 67h ; 'g'
0x18000f957  mov     r9d, edi
0x18000f95a  jmp     short loc_18000F9AC
0x18000f95c  mov     rcx, [r14]; Block
0x18000f95f  xor     ebx, ebx
0x18000f961  mov     [r14], rdi
0x18000f964  test    rcx, rcx
0x18000f967  jz      short loc_18000F96E
0x18000f969  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f96e  mov     eax, [rsp+88h+ServicesReturned]
0x18000f975  xor     edi, edi
0x18000f977  mov     [r15], eax
0x18000f97a  mov     [rsp+88h+ServicesReturned], ebx
0x18000f981  jmp     short loc_18000F9BC
0x18000f983  mov     edi, 8007000Eh
0x18000f988  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f98f  lea     rax, WPP_GLOBAL_Control
0x18000f996  cmp     rcx, rax
0x18000f999  jz      short loc_18000F9BC
0x18000f99b  test    byte ptr [rcx+1Ch], 1
0x18000f99f  jz      short loc_18000F9BC
0x18000f9a1  mov     edx, 66h ; 'f'
0x18000f9a6  mov     r9d, 8007000Eh
0x18000f9ac  mov     rcx, [rcx+10h]
0x18000f9b0  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000f9b7  call    WPP_SF_d
0x18000f9bc  mov     rcx, rbp; hSCObject
0x18000f9bf  call    cs:__imp_CloseServiceHandle
0x18000f9c5  test    rbx, rbx
0x18000f9c8  jz      short loc_18000F9D2
0x18000f9ca  mov     rcx, rbx; Block
0x18000f9cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f9d2  mov     rbx, [rsp+88h+arg_0]
0x18000f9da  mov     eax, edi
0x18000f9dc  add     rsp, 60h
0x18000f9e0  pop     r15
0x18000f9e2  pop     r14
0x18000f9e4  pop     rdi
0x18000f9e5  pop     rsi
0x18000f9e6  pop     rbp
0x18000f9e7  retn
```
