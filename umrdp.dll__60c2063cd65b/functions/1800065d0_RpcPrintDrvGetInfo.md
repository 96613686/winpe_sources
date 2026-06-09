# RpcPrintDrvGetInfo

- ea: `0x1800065d0`
- end: `0x1800069d3`
- name: `RpcPrintDrvGetInfo`
- size: `1027`
- prototype: `int __fastcall(__int64, WCHAR *, unsigned int *, unsigned int *, int, LPHANDLE lpTargetHandle)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x1800065d0`
- `0x1800069e0`
- `0x180008460`
- `0x18000d410`
- `0x18000e3a4`
- `0x18000e784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000670e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000694f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000670e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000694f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006809`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006809`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006834`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006840`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006916`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000691f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006834`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006840`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006916`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000691f`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800066d0`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800066d0`
- `ntdll!RtlLookupElementGenericTable` at `0x180006818`
- `ntdll!RtlLookupElementGenericTable` at `0x180006818`
- `RPCRT4!RpcImpersonateClient` at `0x180006872`
- `RPCRT4!RpcImpersonateClient` at `0x180006872`
- `RPCRT4!RpcRevertToSelf` at `0x1800068c1`
- `RPCRT4!RpcRevertToSelf` at `0x1800068c1`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180006978`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180006978`
- `WINSTA!WinStationVirtualOpenEx` at `0x1800068b0`
- `WINSTA!WinStationVirtualOpenEx` at `0x180006941`
- `WINSTA!WinStationVirtualOpenEx` at `0x1800068b0`
- `WINSTA!WinStationVirtualOpenEx` at `0x180006941`
- `WINSPOOL!GetPrinterDataW` at `0x1800066bc`
- `WINSPOOL!GetPrinterDataW` at `0x1800066bc`
- `WINSPOOL!OpenPrinterW` at `0x180006671`
- `WINSPOOL!OpenPrinterW` at `0x180006671`
- `WINSPOOL!ClosePrinter` at `0x180006706`
- `WINSPOOL!ClosePrinter` at `0x180006706`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x180006637`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x180006637`

## pseudocode

```c
int __fastcall RpcPrintDrvGetInfo(
        __int64 a1,
        WCHAR *a2,
        unsigned int *a3,
        unsigned int *a4,
        int a5,
        LPHANDLE lpTargetHandle)
{
  __int64 v9; // rdx
  WCHAR *v10; // rax
  unsigned int v11; // r15d
  signed int v12; // ebx
  signed int LastError; // eax
  signed int v14; // eax
  int result; // eax
  __int64 v16; // rax
  WCHAR *v18; // rcx
  WCHAR *v19; // rdx
  __int16 v20; // ax
  WCHAR v21; // ax
  CUMRDPService *v22; // rbx
  signed int PrinterClientDeviceId; // esi
  __int64 v24; // r14
  struct _RTL_CRITICAL_SECTION *v25; // rbp
  struct _RTL_CRITICAL_SECTION *v26; // r14
  __int64 *v27; // rax
  __int64 *v28; // rbx
  bool v29; // sf
  const char *v30; // rbx
  void *v31; // rdi
  RPC_STATUS v32; // eax
  signed int v33; // ebx
  BYTE pData[4]; // [rsp+30h] [rbp-68h] BYREF
  DWORD pcbNeeded; // [rsp+34h] [rbp-64h] BYREF
  HANDLE phPrinter; // [rsp+38h] [rbp-60h] BYREF
  __int64 Buffer; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v38; // [rsp+48h] [rbp-50h]
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+50h] [rbp-48h] BYREF
  DWORD pType; // [rsp+A8h] [rbp+10h] BYREF

  if ( !a2 )
    return -2147024809;
  v9 = 260;
  v10 = a2;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  if ( !v9 )
    return -2147024809;
  v11 = 0;
  if ( (unsigned __int8)IsQueryWin32SubsystemHostPresent(0) && (unsigned int)QueryWin32SubsystemHost() == 1 )
  {
    *(_QWORD *)&pDefault.DesiredAccess = 983052;
    phPrinter = (HANDLE)-1LL;
    *(_OWORD *)&pDefault.pDatatype = 0;
    if ( OpenPrinterW(a2, &phPrinter, &pDefault) )
    {
      pType = 0;
      *(_DWORD *)pData = 0;
      pcbNeeded = 0;
      if ( GetPrinterDataW(phPrinter, (LPWSTR)L"ContainerTsSessionId", &pType, pData, 4u, &pcbNeeded) )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
      }
      else if ( pType != 4 || (unsigned int)RtlGetCurrentServiceSessionId() == *(_DWORD *)pData )
      {
        v12 = -2147024809;
      }
      else
      {
        v12 = 0;
        v11 = *(_DWORD *)pData;
      }
      ClosePrinter(phPrinter);
    }
    else
    {
      v14 = GetLastError();
      v12 = v14;
      if ( v14 > 0 )
        v12 = (unsigned __int16)v14 | 0x80070000;
    }
    if ( v12 < 0 )
      return -2147024809;
  }
  else
  {
    v16 = -1;
    while ( a2[++v16] != 0 )
      ;
    v18 = &a2[v16];
    v19 = v18;
    while ( 1 )
    {
      v20 = *--v19;
      if ( v19 <= a2 )
        break;
      if ( v20 == 40 )
        goto LABEL_28;
    }
    if ( v20 != 40 )
      return -2147024809;
    do
LABEL_28:
      ++v19;
    while ( v19 < v18 && (unsigned __int16)(*v19 - 48) > 9u );
    v21 = *v19;
    if ( *v19 < 0x30u )
      return -2147024809;
    do
    {
      if ( v21 > 0x39u )
        break;
      ++v19;
      v11 = v21 + 2 * (5 * v11 - 24);
      v21 = *v19;
    }
    while ( *v19 >= 0x30u );
    if ( !v11 )
      return -2147024809;
  }
  v22 = g_pService;
  PrinterClientDeviceId = -2147467259;
  v24 = 0;
  v25 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pService + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pService + 224));
  Buffer = 0;
  v38 = v11;
  if ( *((_DWORD *)v22 + 54) )
  {
    v26 = (struct _RTL_CRITICAL_SECTION *)((char *)v22 + 176);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v22 + 176));
    v27 = (__int64 *)RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)v22 + 104), &Buffer);
    v28 = v27;
    if ( !v27 )
    {
      LeaveCriticalSection(v26);
      LeaveCriticalSection(v25);
      return PrinterClientDeviceId;
    }
    _InterlockedIncrement((volatile signed __int32 *)(*v27 + 16));
    LeaveCriticalSection(v26);
    v24 = *v28;
  }
  LeaveCriticalSection(v25);
  if ( !v24 )
    return PrinterClientDeviceId;
  PrinterClientDeviceId = CUmRdpPrn::GetPrinterClientDeviceId((CUmRdpPrn *)(v24 + 24), a2, a4);
  CUmRdpDr::Release((CUmRdpDr *)v24);
  if ( PrinterClientDeviceId < 0 )
    return PrinterClientDeviceId;
  *a3 = v11;
  result = RpcImpersonateClient(0);
  v29 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v29 = result < 0;
  }
  if ( !v29 )
  {
    v30 = "TSVCTKT";
    if ( !a5 )
      v30 = "XPSRD";
    v31 = (void *)WinStationVirtualOpenEx(0, v11, v30, 1);
    PrinterClientDeviceId = GetLastError();
    RpcRevertToSelf();
    if ( v31 )
      goto LABEL_55;
    if ( PrinterClientDeviceId != 5 )
    {
      if ( PrinterClientDeviceId > 0 )
        return (unsigned __int16)PrinterClientDeviceId | 0x80070000;
      return PrinterClientDeviceId;
    }
    if ( !(unsigned int)IsCallerSameAsUser(v11) || (v31 = (void *)WinStationVirtualOpenEx(0, v11, v30, 1)) != 0 )
    {
LABEL_55:
      pType = 0;
      v32 = I_RpcBindingInqLocalClientPID(0, &pType);
      v33 = v32;
      if ( v32 > 0 )
        v33 = (unsigned __int16)v32 | 0x80070000;
      if ( v33 >= 0 )
        v33 = DuplicateHandleInPid(v31, pType, lpTargetHandle);
      if ( v31 )
        CloseHandle(v31);
      return v33;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800065d0  push    rdi
0x1800065d2  push    r12
0x1800065d4  push    r13
0x1800065d6  sub     rsp, 80h
0x1800065dd  mov     r13, r9
0x1800065e0  mov     r12, r8
0x1800065e3  mov     rdi, rdx
0x1800065e6  test    rdx, rdx
0x1800065e9  jz      loc_1800069BF
0x1800065ef  mov     edx, 104h
0x1800065f4  mov     rax, rdi
0x1800065f7  cmp     word ptr [rax], 0
0x1800065fb  jz      short loc_180006607
0x1800065fd  add     rax, 2
0x180006601  sub     rdx, 1
0x180006605  jnz     short loc_1800065F7
0x180006607  xor     eax, eax
0x180006609  mov     ecx, 80070057h
0x18000660e  test    rdx, rdx
0x180006611  cmovnz  ecx, eax
0x180006614  jz      loc_1800069C4
0x18000661a  mov     [rsp+98h+var_28], r15
0x18000661f  xor     r15d, r15d
0x180006622  mov     [rsp+98h+arg_0], rbx
0x18000662a  call    IsQueryWin32SubsystemHostPresent
0x18000662f  test    al, al
0x180006631  jz      loc_180006735
0x180006637  call    cs:__imp_QueryWin32SubsystemHost
0x18000663d  cmp     eax, 1
0x180006640  jnz     loc_180006735
0x180006646  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000664d  mov     qword ptr [rsp+98h+pDefault.DesiredAccess], 0F000Ch
0x180006656  xorps   xmm0, xmm0
0x180006659  mov     [rsp+98h+phPrinter], rax
0x18000665e  lea     r8, [rsp+98h+pDefault]; pDefault
0x180006663  mov     rcx, rdi; pPrinterName
0x180006666  lea     rdx, [rsp+98h+phPrinter]; phPrinter
0x18000666b  movdqu  xmmword ptr [rsp+98h+pDefault.pDatatype], xmm0
0x180006671  call    cs:__imp_OpenPrinterW
0x180006677  test    eax, eax
0x180006679  jz      loc_18000670E
0x18000667f  mov     rcx, [rsp+98h+phPrinter]; hPrinter
0x180006684  lea     rax, [rsp+98h+var_64]
0x180006689  mov     [rsp+98h+pcbNeeded], rax; pcbNeeded
0x18000668e  lea     r9, [rsp+98h+pData]; pData
0x180006693  lea     r8, [rsp+98h+pType]; pType
0x18000669b  mov     [rsp+98h+nSize], 4; nSize
0x1800066a3  lea     rdx, aContainertsses; "ContainerTsSessionId"
0x1800066aa  mov     [rsp+98h+pType], r15d
0x1800066b2  mov     dword ptr [rsp+98h+pData], r15d
0x1800066b7  mov     [rsp+98h+var_64], r15d
0x1800066bc  call    cs:__imp_GetPrinterDataW
0x1800066c2  test    eax, eax
0x1800066c4  jnz     short loc_1800066EC
0x1800066c6  cmp     [rsp+98h+pType], 4
0x1800066ce  jnz     short loc_1800066E5
0x1800066d0  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800066d6  mov     ecx, dword ptr [rsp+98h+pData]
0x1800066da  cmp     eax, ecx
0x1800066dc  jz      short loc_1800066E5
0x1800066de  xor     ebx, ebx
0x1800066e0  mov     r15d, ecx
0x1800066e3  jmp     short loc_180006701
0x1800066e5  mov     ebx, 80070057h
0x1800066ea  jmp     short loc_180006701
0x1800066ec  call    cs:__imp_GetLastError
0x1800066f2  mov     ebx, eax
0x1800066f4  test    eax, eax
0x1800066f6  jle     short loc_180006701
0x1800066f8  movzx   ebx, ax
0x1800066fb  or      ebx, 80070000h
0x180006701  mov     rcx, [rsp+98h+phPrinter]; hPrinter
0x180006706  call    cs:__imp_ClosePrinter
0x18000670c  jmp     short loc_180006723
0x18000670e  call    cs:__imp_GetLastError
0x180006714  mov     ebx, eax
0x180006716  test    eax, eax
0x180006718  jle     short loc_180006723
0x18000671a  movzx   ebx, ax
0x18000671d  or      ebx, 80070000h
0x180006723  test    ebx, ebx
0x180006725  jns     loc_1800067B8
0x18000672b  mov     eax, 80070057h
0x180006730  jmp     loc_1800068F9
0x180006735  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000673c  nop     dword ptr [rax+00h]
0x180006740  cmp     [rdi+rax*2+2], r15w
0x180006746  lea     rax, [rax+1]
0x18000674a  jnz     short loc_180006740
0x18000674c  lea     rcx, [rdi+rax*2]
0x180006750  mov     rdx, rcx
0x180006753  movzx   eax, word ptr [rdx-2]
0x180006757  sub     rdx, 2
0x18000675b  cmp     rdx, rdi
0x18000675e  jbe     short loc_180006768
0x180006760  cmp     ax, 28h ; '('
0x180006764  jnz     short loc_180006753
0x180006766  jmp     short loc_18000676E
0x180006768  cmp     ax, 28h ; '('
0x18000676c  jnz     short loc_18000672B
0x18000676e  add     rdx, 2
0x180006772  cmp     rdx, rcx
0x180006775  jnb     short loc_180006784
0x180006777  movzx   eax, word ptr [rdx]
0x18000677a  sub     ax, 30h ; '0'
0x18000677e  cmp     ax, 9
0x180006782  ja      short loc_18000676E
0x180006784  movzx   eax, word ptr [rdx]
0x180006787  cmp     ax, 30h ; '0'
0x18000678b  jb      short loc_18000672B
0x18000678d  cmp     ax, 39h ; '9'
0x180006791  ja      short loc_1800067AF
0x180006793  movzx   eax, ax
0x180006796  lea     r15d, [r15+r15*4]
0x18000679a  add     rdx, 2
0x18000679e  lea     r15d, [r15-18h]
0x1800067a2  lea     r15d, [rax+r15*2]
0x1800067a6  movzx   eax, word ptr [rdx]
0x1800067a9  cmp     ax, 30h ; '0'
0x1800067ad  jnb     short loc_18000678D
0x1800067af  test    r15d, r15d
0x1800067b2  jz      loc_18000672B
0x1800067b8  mov     rbx, cs:?g_pService@@3PEAVCUMRDPService@@EA; CUMRDPService * g_pService
0x1800067bf  mov     [rsp+98h+arg_10], rbp
0x1800067c7  mov     [rsp+98h+arg_18], rsi
0x1800067cf  mov     esi, 80004005h
0x1800067d4  mov     [rsp+98h+var_20], r14
0x1800067d9  xor     r14d, r14d
0x1800067dc  lea     rbp, [rbx+0E0h]
0x1800067e3  mov     rcx, rbp; lpCriticalSection
0x1800067e6  call    cs:__imp_EnterCriticalSection
0x1800067ec  mov     [rsp+98h+Buffer], r14
0x1800067f1  mov     [rsp+98h+var_50], r15d
0x1800067f6  cmp     [rbx+0D8h], r14d
0x1800067fd  jz      short loc_18000683D
0x1800067ff  lea     r14, [rbx+0B0h]
0x180006806  mov     rcx, r14; lpCriticalSection
0x180006809  call    cs:__imp_EnterCriticalSection
0x18000680f  lea     rdx, [rsp+98h+Buffer]; Buffer
0x180006814  lea     rcx, [rbx+68h]; Table
0x180006818  call    cs:__imp_RtlLookupElementGenericTable
0x18000681e  mov     rbx, rax
0x180006821  test    rax, rax
0x180006824  jz      loc_180006913
0x18000682a  mov     rcx, [rax]
0x18000682d  lock inc dword ptr [rcx+10h]
0x180006831  mov     rcx, r14; lpCriticalSection
0x180006834  call    cs:__imp_LeaveCriticalSection
0x18000683a  mov     r14, [rbx]
0x18000683d  mov     rcx, rbp; lpCriticalSection
0x180006840  call    cs:__imp_LeaveCriticalSection
0x180006846  test    r14, r14
0x180006849  jz      loc_1800068E2
0x18000684f  lea     rcx, [r14+18h]; this
0x180006853  mov     r8, r13; unsigned int *
0x180006856  mov     rdx, rdi; unsigned __int16 *
0x180006859  call    ?GetPrinterClientDeviceId@CUmRdpPrn@@QEAAJPEBGPEAK@Z; CUmRdpPrn::GetPrinterClientDeviceId(ushort const *,ulong *)
0x18000685e  mov     rcx, r14; this
0x180006861  mov     esi, eax
0x180006863  call    ?Release@CUmRdpDr@@QEAAJXZ; CUmRdpDr::Release(void)
0x180006868  test    esi, esi
0x18000686a  js      short loc_1800068E2
0x18000686c  xor     ecx, ecx; BindingHandle
0x18000686e  mov     [r12], r15d
0x180006872  call    cs:__imp_RpcImpersonateClient
0x180006878  test    eax, eax
0x18000687a  jle     short loc_180006886
0x18000687c  movzx   eax, ax
0x18000687f  or      eax, 80070000h
0x180006884  test    eax, eax
0x180006886  js      short loc_1800068E4
0x180006888  cmp     [rsp+98h+arg_20], 0
0x180006890  lea     rax, aXpsrd; "XPSRD"
0x180006897  lea     rbx, aTsvctkt; "TSVCTKT"
0x18000689e  mov     r9d, 1
0x1800068a4  cmovz   rbx, rax
0x1800068a8  mov     edx, r15d
0x1800068ab  mov     r8, rbx
0x1800068ae  xor     ecx, ecx
0x1800068b0  call    cs:__imp_WinStationVirtualOpenEx
0x1800068b6  mov     rdi, rax
0x1800068b9  call    cs:__imp_GetLastError
0x1800068bf  mov     esi, eax
0x1800068c1  call    cs:__imp_RpcRevertToSelf
0x1800068c7  test    rdi, rdi
0x1800068ca  jnz     loc_180006963
0x1800068d0  cmp     esi, 5
0x1800068d3  jz      short loc_180006927
0x1800068d5  test    esi, esi
0x1800068d7  jle     short loc_1800068E2
0x1800068d9  movzx   esi, si
0x1800068dc  or      esi, 80070000h
0x1800068e2  mov     eax, esi
0x1800068e4  mov     r14, [rsp+98h+var_20]
0x1800068e9  mov     rsi, [rsp+98h+arg_18]
0x1800068f1  mov     rbp, [rsp+98h+arg_10]
0x1800068f9  mov     rbx, [rsp+98h+arg_0]
0x180006901  mov     r15, [rsp+98h+var_28]
0x180006906  add     rsp, 80h
0x18000690d  pop     r13
0x18000690f  pop     r12
0x180006911  pop     rdi
0x180006912  retn
0x180006913  mov     rcx, r14; lpCriticalSection
0x180006916  call    cs:__imp_LeaveCriticalSection
0x18000691c  mov     rcx, rbp; lpCriticalSection
0x18000691f  call    cs:__imp_LeaveCriticalSection
0x180006925  jmp     short loc_1800068E2
0x180006927  mov     ecx, r15d; unsigned int
0x18000692a  call    ?IsCallerSameAsUser@@YAHK@Z; IsCallerSameAsUser(ulong)
0x18000692f  test    eax, eax
0x180006931  jz      short loc_180006963
0x180006933  mov     r9d, 1
0x180006939  mov     r8, rbx
0x18000693c  mov     edx, r15d
0x18000693f  xor     ecx, ecx
0x180006941  call    cs:__imp_WinStationVirtualOpenEx
0x180006947  mov     rdi, rax
0x18000694a  test    rax, rax
0x18000694d  jnz     short loc_180006963
0x18000694f  call    cs:__imp_GetLastError
0x180006955  test    eax, eax
0x180006957  jle     short loc_1800068E4
0x180006959  movzx   eax, ax
0x18000695c  or      eax, 80070000h
0x180006961  jmp     short loc_1800068E4
0x180006963  lea     rdx, [rsp+98h+pType]; Pid
0x18000696b  mov     [rsp+98h+pType], 0
0x180006976  xor     ecx, ecx; Binding
0x180006978  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000697e  mov     ebx, eax
0x180006980  test    eax, eax
0x180006982  jle     short loc_18000698D
0x180006984  movzx   ebx, ax
0x180006987  or      ebx, 80070000h
0x18000698d  test    ebx, ebx
0x18000698f  js      short loc_1800069AA
0x180006991  mov     r8, [rsp+98h+lpTargetHandle]; lpTargetHandle
0x180006999  mov     rcx, rdi; hSourceHandle
0x18000699c  mov     edx, [rsp+98h+pType]; dwProcessId
0x1800069a3  call    ?DuplicateHandleInPid@@YAJPEAXKPEAPEAX@Z; DuplicateHandleInPid(void *,ulong,void * *)
0x1800069a8  mov     ebx, eax
0x1800069aa  test    rdi, rdi
0x1800069ad  jz      short loc_1800069B8
0x1800069af  mov     rcx, rdi; hObject
0x1800069b2  call    cs:__imp_CloseHandle
0x1800069b8  mov     eax, ebx
0x1800069ba  jmp     loc_1800068E4
0x1800069bf  mov     ecx, 80070057h
0x1800069c4  mov     eax, ecx
0x1800069c6  add     rsp, 80h
0x1800069cd  pop     r13
0x1800069cf  pop     r12
0x1800069d1  pop     rdi
0x1800069d2  retn
```
