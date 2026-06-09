# WctIsRpcssPid(ulong)

- ea: `0x1800614f4`
- end: `0x1800616b2`
- name: `?WctIsRpcssPid@@YAHK@Z`
- size: `446`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180050a48`

## callees

- `0x180004c64`
- `0x18001e0d0`
- `0x180020680`
- `0x1800614f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800615ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800615ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800615c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800615c2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800615b2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180061633`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800615b2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180061633`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180061586`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180061586`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180061652`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180061661`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180061652`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180061661`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180061560`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180061560`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
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
    WPP_SF_d(*((_QWORD *)v2 + 2), 37, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v3);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v12);
  return v3;
}

```

## disassembly

```asm
0x1800614f4  push    rbp
0x1800614f6  push    rbx
0x1800614f7  push    rsi
0x1800614f8  push    rdi
0x1800614f9  push    r13
0x1800614fb  push    r14
0x1800614fd  push    r15
0x1800614ff  mov     rbp, rsp
0x180061502  sub     rsp, 30h
0x180061506  mov     r15d, ecx
0x180061509  mov     [rbp+cbBufSize], 0
0x180061510  mov     [rbp+arg_8], 0
0x180061518  mov     rcx, cs:WPP_GLOBAL_Control
0x18006151f  lea     r13, WPP_GLOBAL_Control
0x180061526  cmp     rcx, r13
0x180061529  jz      short loc_18006154D
0x18006152b  test    byte ptr [rcx+1Ch], 4
0x18006152f  jz      short loc_18006154D
0x180061531  mov     rcx, [rcx+10h]
0x180061535  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006153c  mov     edx, 24h ; '$'
0x180061541  call    WPP_SF_
0x180061546  mov     rcx, cs:WPP_GLOBAL_Control
0x18006154d  xor     ebx, ebx
0x18006154f  test    r15d, r15d
0x180061552  jz      loc_180061674
0x180061558  xor     edx, edx; lpDatabaseName
0x18006155a  lea     r8d, [rbx+1]; dwDesiredAccess
0x18006155e  xor     ecx, ecx; lpMachineName
0x180061560  call    cs:__imp_OpenSCManagerW
0x180061567  nop     dword ptr [rax+rax+00h]
0x18006156c  mov     rsi, rax
0x18006156f  test    rax, rax
0x180061572  jz      loc_18006166D
0x180061578  lea     r8d, [rbx+4]; dwDesiredAccess
0x18006157c  mov     rcx, rax; hSCManager
0x18006157f  lea     rdx, ServiceName; "RPCSS"
0x180061586  call    cs:__imp_OpenServiceW
0x18006158d  nop     dword ptr [rax+rax+00h]
0x180061592  mov     rdi, rax
0x180061595  test    rax, rax
0x180061598  jz      loc_18006165E
0x18006159e  lea     rax, [rbp+cbBufSize]
0x1800615a2  xor     r9d, r9d; cbBufSize
0x1800615a5  xor     r8d, r8d; lpBuffer
0x1800615a8  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800615ad  xor     edx, edx; InfoLevel
0x1800615af  mov     rcx, rdi; hService
0x1800615b2  call    cs:__imp_QueryServiceStatusEx
0x1800615b9  nop     dword ptr [rax+rax+00h]
0x1800615be  test    eax, eax
0x1800615c0  jnz     short loc_1800615D8
0x1800615c2  call    cs:__imp_GetLastError
0x1800615c9  nop     dword ptr [rax+rax+00h]
0x1800615ce  cmp     eax, 7Ah ; 'z'
0x1800615d1  jnz     short loc_18006164F
0x1800615d3  mov     eax, [rbp+cbBufSize]
0x1800615d6  jmp     short loc_1800615E0
0x1800615d8  mov     eax, 1000h
0x1800615dd  mov     [rbp+cbBufSize], eax
0x1800615e0  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800615e7  xor     edx, edx; dwFlags
0x1800615e9  mov     r8d, eax; dwBytes
0x1800615ec  call    cs:__imp_HeapAlloc
0x1800615f3  nop     dword ptr [rax+rax+00h]
0x1800615f8  lea     rcx, [rbp+arg_8]; void *
0x1800615fc  mov     [rbp+arg_8], rbx
0x180061600  mov     r14, rax
0x180061603  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180061608  lea     rcx, [rbp+arg_10]; void *
0x18006160c  mov     [rbp+arg_10], rbx
0x180061610  mov     [rbp+arg_8], r14
0x180061614  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180061619  test    r14, r14
0x18006161c  jz      short loc_18006164F
0x18006161e  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x180061622  lea     rax, [rbp+cbBufSize]
0x180061626  mov     r8, r14; lpBuffer
0x180061629  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18006162e  xor     edx, edx; InfoLevel
0x180061630  mov     rcx, rdi; hService
0x180061633  call    cs:__imp_QueryServiceStatusEx
0x18006163a  nop     dword ptr [rax+rax+00h]
0x18006163f  test    eax, eax
0x180061641  jz      short loc_18006164F
0x180061643  cmp     r15d, [r14+1Ch]
0x180061647  mov     eax, 1
0x18006164c  cmovz   ebx, eax
0x18006164f  mov     rcx, rdi; hSCObject
0x180061652  call    cs:__imp_CloseServiceHandle
0x180061659  nop     dword ptr [rax+rax+00h]
0x18006165e  mov     rcx, rsi; hSCObject
0x180061661  call    cs:__imp_CloseServiceHandle
0x180061668  nop     dword ptr [rax+rax+00h]
0x18006166d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061674  cmp     rcx, r13
0x180061677  jz      short loc_180061697
0x180061679  test    byte ptr [rcx+1Ch], 4
0x18006167d  jz      short loc_180061697
0x18006167f  mov     rcx, [rcx+10h]
0x180061683  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006168a  mov     edx, 25h ; '%'
0x18006168f  mov     r9d, ebx
0x180061692  call    WPP_SF_d
0x180061697  lea     rcx, [rbp+arg_8]; void *
0x18006169b  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800616a0  mov     eax, ebx
0x1800616a2  add     rsp, 30h
0x1800616a6  pop     r15
0x1800616a8  pop     r14
0x1800616aa  pop     r13
0x1800616ac  pop     rdi
0x1800616ad  pop     rsi
0x1800616ae  pop     rbx
0x1800616af  pop     rbp
0x1800616b0  retn
```
