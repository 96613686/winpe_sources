# PfsQueryFileInfo

- ea: `0x180086914`
- end: `0x180086a6c`
- name: `PfsQueryFileInfo`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180084948`

## callees

- `0x180069920`
- `0x180071b0c`
- `0x180086914`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800869e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800869e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180086a4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180086a4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800869bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800869bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800869ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180086a40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800869ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180086a40`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180086971`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800869dd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180086971`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800869dd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180086a08`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180086a08`

## pseudocode

```c
__int64 __fastcall PfsQueryFileInfo(_DWORD *a1)
{
  struct _QUERY_SERVICE_CONFIGW *v2; // rdi
  DWORD LastError; // ebx
  SIZE_T v4; // r8
  HANDLE ProcessHeap; // rcx
  DWORD v6; // ebx
  struct _QUERY_SERVICE_CONFIGW *v7; // rax
  HANDLE v8; // rcx
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-48h] BYREF
  SC_HANDLE hService[2]; // [rsp+28h] [rbp-40h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-30h] BYREF

  pcbBytesNeeded = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = 0;
  *(_OWORD *)hService = 0;
  LastError = PfsServiceCtxStart(hService, L"fileinfo");
  if ( !LastError )
  {
    if ( QueryServiceConfigW(hService[1], 0, 0, &pcbBytesNeeded) )
    {
      LastError = 50;
      goto LABEL_17;
    }
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      if ( *(_QWORD *)&PfSvcGlobals )
      {
        v4 = pcbBytesNeeded;
        ProcessHeap = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL);
      }
      else
      {
        v6 = pcbBytesNeeded;
        ProcessHeap = GetProcessHeap();
        v4 = v6;
      }
      v7 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(ProcessHeap, 0, v4);
      v2 = v7;
      if ( !v7 )
      {
        LastError = 8;
        goto LABEL_17;
      }
      if ( !QueryServiceConfigW(hService[1], v7, pcbBytesNeeded, &pcbBytesNeeded) )
        goto LABEL_11;
      if ( v2->dwStartType )
      {
        *a1 = 0;
      }
      else
      {
        if ( !QueryServiceStatus(hService[1], &ServiceStatus) )
        {
LABEL_11:
          LastError = GetLastError();
          goto LABEL_17;
        }
        *a1 = ServiceStatus.dwCurrentState == 4;
      }
      LastError = 0;
    }
  }
LABEL_17:
  PfsServiceCtxCleanup(hService);
  if ( v2 )
  {
    if ( *(_QWORD *)&PfSvcGlobals )
      v8 = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL);
    else
      v8 = GetProcessHeap();
    HeapFree(v8, 0, v2);
  }
  return LastError;
}

```

## disassembly

```asm
0x180086914  push    rbp
0x180086916  push    rbx
0x180086917  push    rdi
0x180086918  push    r14
0x18008691a  mov     rbp, rsp
0x18008691d  sub     rsp, 68h
0x180086921  mov     rax, cs:__security_cookie
0x180086928  xor     rax, rsp
0x18008692b  mov     [rbp+var_10], rax
0x18008692f  xorps   xmm0, xmm0
0x180086932  mov     [rbp+pcbBytesNeeded], 0
0x180086939  mov     r14, rcx
0x18008693c  lea     rdx, aFileinfo; "fileinfo"
0x180086943  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x180086947  lea     rcx, [rbp+hService]
0x18008694b  xor     edi, edi
0x18008694d  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x180086951  movups  xmmword ptr [rbp+hService], xmm0
0x180086955  call    PfsServiceCtxStart
0x18008695a  mov     ebx, eax
0x18008695c  test    eax, eax
0x18008695e  jnz     loc_180086A20
0x180086964  mov     rcx, [rbp+hService+8]; hService
0x180086968  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x18008696c  xor     r8d, r8d; cbBufSize
0x18008696f  xor     edx, edx; lpServiceConfig
0x180086971  call    cs:__imp_QueryServiceConfigW
0x180086977  test    eax, eax
0x180086979  jz      short loc_180086983
0x18008697b  lea     ebx, [rdi+32h]
0x18008697e  jmp     loc_180086A20
0x180086983  call    cs:__imp_GetLastError
0x180086989  mov     ebx, eax
0x18008698b  cmp     eax, 7Ah ; 'z'
0x18008698e  jnz     loc_180086A20
0x180086994  mov     rcx, cs:PfSvcGlobals
0x18008699b  test    rcx, rcx
0x18008699e  jz      short loc_1800869AA
0x1800869a0  mov     r8d, [rbp+pcbBytesNeeded]
0x1800869a4  mov     rcx, [rcx+58h]
0x1800869a8  jmp     short loc_1800869B9
0x1800869aa  mov     ebx, [rbp+pcbBytesNeeded]
0x1800869ad  call    cs:__imp_GetProcessHeap
0x1800869b3  mov     rcx, rax; hHeap
0x1800869b6  mov     r8d, ebx; dwBytes
0x1800869b9  xor     edx, edx; dwFlags
0x1800869bb  call    cs:__imp_HeapAlloc
0x1800869c1  mov     rdi, rax
0x1800869c4  test    rax, rax
0x1800869c7  jnz     short loc_1800869CE
0x1800869c9  lea     ebx, [rax+8]
0x1800869cc  jmp     short loc_180086A20
0x1800869ce  mov     r8d, [rbp+pcbBytesNeeded]; cbBufSize
0x1800869d2  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x1800869d6  mov     rcx, [rbp+hService+8]; hService
0x1800869da  mov     rdx, rdi; lpServiceConfig
0x1800869dd  call    cs:__imp_QueryServiceConfigW
0x1800869e3  test    eax, eax
0x1800869e5  jnz     short loc_1800869F1
0x1800869e7  call    cs:__imp_GetLastError
0x1800869ed  mov     ebx, eax
0x1800869ef  jmp     short loc_180086A20
0x1800869f1  cmp     dword ptr [rdi+4], 0
0x1800869f5  jz      short loc_180086A00
0x1800869f7  mov     dword ptr [r14], 0
0x1800869fe  jmp     short loc_180086A1E
0x180086a00  mov     rcx, [rbp+hService+8]; hService
0x180086a04  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180086a08  call    cs:__imp_QueryServiceStatus
0x180086a0e  test    eax, eax
0x180086a10  jz      short loc_1800869E7
0x180086a12  xor     eax, eax
0x180086a14  cmp     [rbp+ServiceStatus.dwCurrentState], 4
0x180086a18  setz    al
0x180086a1b  mov     [r14], eax
0x180086a1e  xor     ebx, ebx
0x180086a20  lea     rcx, [rbp+hService]
0x180086a24  call    PfsServiceCtxCleanup
0x180086a29  test    rdi, rdi
0x180086a2c  jz      short loc_180086A54
0x180086a2e  mov     rcx, cs:PfSvcGlobals
0x180086a35  test    rcx, rcx
0x180086a38  jz      short loc_180086A40
0x180086a3a  mov     rcx, [rcx+58h]
0x180086a3e  jmp     short loc_180086A49
0x180086a40  call    cs:__imp_GetProcessHeap
0x180086a46  mov     rcx, rax; hHeap
0x180086a49  mov     r8, rdi; lpMem
0x180086a4c  xor     edx, edx; dwFlags
0x180086a4e  call    cs:__imp_HeapFree
0x180086a54  mov     eax, ebx
0x180086a56  mov     rcx, [rbp+var_10]
0x180086a5a  xor     rcx, rsp; StackCookie
0x180086a5d  call    __security_check_cookie
0x180086a62  add     rsp, 68h
0x180086a66  pop     r14
0x180086a68  pop     rdi
0x180086a69  pop     rbx
0x180086a6a  pop     rbp
0x180086a6b  retn
```
