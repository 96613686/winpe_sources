# CUmRdpPrn::DeleteNamedPrinterQueue(ushort *)

- ea: `0x1800149b0`
- end: `0x180014cfe`
- name: `?DeleteNamedPrinterQueue@CUmRdpPrn@@QEAAHPEAG@Z`
- size: `846`
- prototype: `__int64 __fastcall(CUmRdpPrn *this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800032f0`
- `0x180010848`
- `0x1800117a0`

## callees

- `0x18000a01c`
- `0x18000a3ac`
- `0x18000a41c`
- `0x18000bd04`
- `0x18000bd44`
- `0x18001294c`
- `0x1800149b0`
- `0x180019734`
- `0x1800197e8`
- `0x180019b50`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c1d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014ae7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014ae7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014a96`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014a96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014a7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014a7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014c7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014c7c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014ca5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014ca5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014cb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014cb0`
- `WINSPOOL!OpenPrinterW` at `0x180014b04`
- `WINSPOOL!OpenPrinterW` at `0x180014b04`
- `WINSPOOL!SetPrinterW` at `0x180014b8e`
- `WINSPOOL!SetPrinterW` at `0x180014ba4`
- `WINSPOOL!SetPrinterW` at `0x180014b8e`
- `WINSPOOL!SetPrinterW` at `0x180014ba4`
- `WINSPOOL!DeletePrinter` at `0x180014bb3`
- `WINSPOOL!DeletePrinter` at `0x180014bb3`
- `WINSPOOL!ClosePrinter` at `0x180014a65`
- `WINSPOOL!ClosePrinter` at `0x180014cc0`
- `WINSPOOL!ClosePrinter` at `0x180014a65`
- `WINSPOOL!ClosePrinter` at `0x180014cc0`
- `WINSPOOL!GetPrinterW` at `0x180014b33`
- `WINSPOOL!GetPrinterW` at `0x180014b72`
- `WINSPOOL!GetPrinterW` at `0x180014b33`
- `WINSPOOL!GetPrinterW` at `0x180014b72`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x180014a5b`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x180014a5b`
- `WINSPOOL!__imp_GetDefaultPrinterW` at `0x180014aaf`
- `WINSPOOL!__imp_GetDefaultPrinterW` at `0x180014aaf`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::DeleteNamedPrinterQueue(CUmRdpPrn *this, unsigned __int16 *a2)
{
  __int64 result; // rax
  struct tagDRDEVLST *v5; // r14
  BYTE *v6; // rbx
  __int64 v7; // rdi
  void **v8; // r14
  int v9; // r14d
  WCHAR *v10; // rax
  int v11; // r8d
  int v12; // edx
  unsigned int v13; // edi
  unsigned int v14; // r9d
  CUmRdpDr *v15; // rcx
  int v16; // edx
  DWORD cbBuf; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE phPrinter; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchBuffer; // [rsp+48h] [rbp-B8h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszBuffer[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp+180h] BYREF

  result = 0;
  phPrinter = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  *(_OWORD *)&pDefault.pDatatype = 0;
  cbBuf = 0;
  pcchBuffer = 261;
  pszBuffer[0] = 0;
  if ( !*((_DWORD *)this + 7) )
    return result;
  v5 = (struct tagDRDEVLST *)*((_QWORD *)this + 5);
  v6 = 0;
  if ( (unsigned int)DRDEVLST_FindByServerDeviceName(v5, a2, &cbBuf) )
  {
    v7 = 10LL * cbBuf;
    v8 = *(void ***)(*(_QWORD *)v5 + 80LL * cbBuf + 72);
    if ( v8 )
    {
      WTBLOBJ_RemoveWaitableObject(*((void **)this + 15), *v8);
      FindClosePrinterChangeNotification(*v8);
      ClosePrinter(v8[1]);
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v8);
      *(_QWORD *)(**((_QWORD **)this + 5) + 8 * v7 + 72) = 0;
    }
  }
  if ( ImpersonateLoggedOnUser(*((HANDLE *)this + 23)) )
  {
    if ( !GetDefaultPrinterW(pszBuffer, &pcchBuffer) )
      goto LABEL_13;
    v10 = pszBuffer;
    do
    {
      v11 = *(WCHAR *)((char *)v10 + (char *)a2 - (char *)pszBuffer);
      v12 = *v10 - v11;
      if ( v12 )
        break;
      ++v10;
    }
    while ( v11 );
    if ( v12 )
LABEL_13:
      v9 = 0;
    else
      v9 = 1;
    if ( RevertToSelf() )
      goto LABEL_16;
  }
  else
  {
    v9 = 0;
  }
  GetLastError();
LABEL_16:
  v13 = OpenPrinterW(a2, &phPrinter, &pDefault);
  if ( v13 )
  {
    cbBuf = 0;
    if ( !GetPrinterW(phPrinter, 5u, 0, 0, &cbBuf) && GetLastError() == 122 )
    {
      v6 = (BYTE *)operator new(cbBuf);
      if ( v6 )
      {
        if ( GetPrinterW(phPrinter, 5u, v6, cbBuf, &cbBuf) )
        {
          *((_DWORD *)v6 + 4) |= 0x400u;
          SetPrinterW(phPrinter, 5u, v6, 0);
        }
      }
    }
    v13 = SetPrinterW(phPrinter, 0, 0, 3u) && DeletePrinter(phPrinter);
  }
  else
  {
    phPrinter = 0;
  }
  if ( v9 )
  {
    v15 = *(CUmRdpDr **)this;
    phkResult = 0;
    if ( !(unsigned int)CUmRdpDr::CreateUmRdpRpc(v15, (struct CUmRdpRpc **)&phkResult) )
    {
      CUmRdpRpc::RestoreDefaultPrinter((CUmRdpRpc *)phkResult, v16);
      CUmRdpRpc::Release((CUmRdpRpc *)phkResult);
    }
  }
  if ( v13 )
  {
    if ( v6 )
    {
      if ( *((_QWORD *)v6 + 1) )
      {
        phkResult = 0;
        StringCchPrintfW(
          SubKey,
          0x104u,
          L"SYSTEM\\CurrentControlSet\\Control\\DeviceClasses\\{28d78fad-5a12-11d1-ae5b-0000f803a8c2}\\##?#Root#RDPBUS#000"
           "0#{28d78fad-5a12-11d1-ae5b-0000f803a8c2}\\#%s\\Device Parameters");
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &phkResult) )
        {
          RegSetValueExW(phkResult, L"recyclable", 0, 0, 0, 0);
          RegCloseKey(phkResult);
        }
      }
    }
  }
  else
  {
    phkResult = (HKEY)a2;
    TsLogError(&EVENT_NOTIFY_DELETE_PRINTER_FAILED, 1, (unsigned __int16 **const)&phkResult, v14);
    GetLastError();
  }
  if ( phPrinter )
    ClosePrinter(phPrinter);
  --*((_DWORD *)this + 2);
  if ( v6 )
    operator delete(v6);
  return v13;
}

```

## disassembly

```asm
0x1800149b0  mov     [rsp-8+arg_10], rbx
0x1800149b5  push    rbp
0x1800149b6  push    rsi
0x1800149b7  push    rdi
0x1800149b8  push    r14
0x1800149ba  push    r15
0x1800149bc  lea     rbp, [rsp-3A0h]
0x1800149c4  sub     rsp, 4A0h
0x1800149cb  mov     rax, cs:__security_cookie
0x1800149d2  xor     rax, rsp
0x1800149d5  mov     [rbp+3C0h+var_30], rax
0x1800149dc  xor     eax, eax
0x1800149de  mov     [rsp+4C0h+phPrinter], 0
0x1800149e7  xorps   xmm0, xmm0
0x1800149ea  mov     r15, rdx
0x1800149ed  mov     rsi, rcx
0x1800149f0  mov     qword ptr [rsp+4C0h+pDefault.DesiredAccess], 0F000Ch
0x1800149f9  movdqu  xmmword ptr [rsp+4C0h+pDefault.pDatatype], xmm0
0x1800149ff  mov     [rsp+4C0h+cbBuf], 0
0x180014a07  mov     [rsp+4C0h+pcchBuffer], 105h
0x180014a0f  mov     [rsp+4C0h+pszBuffer], ax
0x180014a14  cmp     [rcx+1Ch], eax
0x180014a17  jz      loc_180014CD8
0x180014a1d  mov     r14, [rcx+28h]
0x180014a21  lea     r8, [rsp+4C0h+cbBuf]; unsigned int *
0x180014a26  mov     rcx, r14; struct tagDRDEVLST *
0x180014a29  xor     ebx, ebx
0x180014a2b  call    ?DRDEVLST_FindByServerDeviceName@@YAHPEAUtagDRDEVLST@@PEBGPEAK@Z; DRDEVLST_FindByServerDeviceName(tagDRDEVLST *,ushort const *,ulong *)
0x180014a30  test    eax, eax
0x180014a32  jz      short loc_180014A8F
0x180014a34  mov     eax, [rsp+4C0h+cbBuf]
0x180014a38  lea     rdi, [rax+rax*4]
0x180014a3c  mov     rax, [r14]
0x180014a3f  add     rdi, rdi
0x180014a42  mov     r14, [rax+rdi*8+48h]
0x180014a47  test    r14, r14
0x180014a4a  jz      short loc_180014A8F
0x180014a4c  mov     rdx, [r14]; void *
0x180014a4f  mov     rcx, [rsi+78h]; void *
0x180014a53  call    ?WTBLOBJ_RemoveWaitableObject@@YAXPEAX0@Z; WTBLOBJ_RemoveWaitableObject(void *,void *)
0x180014a58  mov     rcx, [r14]; hChange
0x180014a5b  call    cs:__imp_FindClosePrinterChangeNotification
0x180014a61  mov     rcx, [r14+8]; hPrinter
0x180014a65  call    cs:__imp_ClosePrinter
0x180014a6b  mov     rcx, gs:60h
0x180014a74  mov     r8, r14; lpMem
0x180014a77  xor     edx, edx; dwFlags
0x180014a79  mov     rcx, [rcx+30h]; hHeap
0x180014a7d  call    cs:__imp_HeapFree
0x180014a83  mov     rax, [rsi+28h]
0x180014a87  mov     rcx, [rax]
0x180014a8a  mov     [rcx+rdi*8+48h], rbx
0x180014a8f  mov     rcx, [rsi+0B8h]; hToken
0x180014a96  call    cs:__imp_ImpersonateLoggedOnUser
0x180014a9c  test    eax, eax
0x180014a9e  jnz     short loc_180014AA5
0x180014aa0  xor     r14d, r14d
0x180014aa3  jmp     short loc_180014AF1
0x180014aa5  lea     rdx, [rsp+4C0h+pcchBuffer]; pcchBuffer
0x180014aaa  lea     rcx, [rsp+4C0h+pszBuffer]; pszBuffer
0x180014aaf  call    cs:__imp_GetDefaultPrinterW
0x180014ab5  test    eax, eax
0x180014ab7  jz      short loc_180014AE4
0x180014ab9  lea     rax, [rsp+4C0h+pszBuffer]
0x180014abe  mov     rcx, r15
0x180014ac1  sub     rcx, rax
0x180014ac4  movzx   edx, word ptr [rax]
0x180014ac7  movzx   r8d, word ptr [rax+rcx]
0x180014acc  sub     edx, r8d
0x180014acf  jnz     short loc_180014ADA
0x180014ad1  add     rax, 2
0x180014ad5  test    r8d, r8d
0x180014ad8  jnz     short loc_180014AC4
0x180014ada  test    edx, edx
0x180014adc  jnz     short loc_180014AE4
0x180014ade  lea     r14d, [rdx+1]
0x180014ae2  jmp     short loc_180014AE7
0x180014ae4  xor     r14d, r14d
0x180014ae7  call    cs:__imp_RevertToSelf
0x180014aed  test    eax, eax
0x180014aef  jnz     short loc_180014AF7
0x180014af1  call    cs:__imp_GetLastError
0x180014af7  lea     r8, [rsp+4C0h+pDefault]; pDefault
0x180014afc  mov     rcx, r15; pPrinterName
0x180014aff  lea     rdx, [rsp+4C0h+phPrinter]; phPrinter
0x180014b04  call    cs:__imp_OpenPrinterW
0x180014b0a  mov     edi, eax
0x180014b0c  test    eax, eax
0x180014b0e  jz      loc_180014BC8
0x180014b14  mov     rcx, [rsp+4C0h+phPrinter]; hPrinter
0x180014b19  lea     rax, [rsp+4C0h+cbBuf]
0x180014b1e  xor     r9d, r9d; cbBuf
0x180014b21  mov     [rsp+4C0h+cbBuf], ebx
0x180014b25  xor     r8d, r8d; pPrinter
0x180014b28  mov     [rsp+4C0h+pcbNeeded], rax; pcbNeeded
0x180014b2d  lea     edi, [r9+5]
0x180014b31  mov     edx, edi; Level
0x180014b33  call    cs:__imp_GetPrinterW
0x180014b39  test    eax, eax
0x180014b3b  jnz     short loc_180014B94
0x180014b3d  call    cs:__imp_GetLastError
0x180014b43  cmp     eax, 7Ah ; 'z'
0x180014b46  jnz     short loc_180014B94
0x180014b48  mov     ecx, [rsp+4C0h+cbBuf]; Size
0x180014b4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014b51  mov     rbx, rax
0x180014b54  test    rax, rax
0x180014b57  jz      short loc_180014B94
0x180014b59  mov     r9d, [rsp+4C0h+cbBuf]; cbBuf
0x180014b5e  lea     rax, [rsp+4C0h+cbBuf]
0x180014b63  mov     rcx, [rsp+4C0h+phPrinter]; hPrinter
0x180014b68  mov     r8, rbx; pPrinter
0x180014b6b  mov     edx, edi; Level
0x180014b6d  mov     [rsp+4C0h+pcbNeeded], rax; pcbNeeded
0x180014b72  call    cs:__imp_GetPrinterW
0x180014b78  test    eax, eax
0x180014b7a  jz      short loc_180014B94
0x180014b7c  bts     dword ptr [rbx+10h], 0Ah
0x180014b81  xor     r9d, r9d; Command
0x180014b84  mov     rcx, [rsp+4C0h+phPrinter]; hPrinter
0x180014b89  mov     r8, rbx; pPrinter
0x180014b8c  mov     edx, edi; Level
0x180014b8e  call    cs:__imp_SetPrinterW
0x180014b94  mov     rcx, [rsp+4C0h+phPrinter]; hPrinter
0x180014b99  mov     r9d, 3; Command
0x180014b9f  xor     r8d, r8d; pPrinter
0x180014ba2  xor     edx, edx; Level
0x180014ba4  call    cs:__imp_SetPrinterW
0x180014baa  test    eax, eax
0x180014bac  jz      short loc_180014BC4
0x180014bae  mov     rcx, [rsp+4C0h+phPrinter]; hPrinter
0x180014bb3  call    cs:__imp_DeletePrinter
0x180014bb9  test    eax, eax
0x180014bbb  jz      short loc_180014BC4
0x180014bbd  mov     edi, 1
0x180014bc2  jmp     short loc_180014BCD
0x180014bc4  xor     edi, edi
0x180014bc6  jmp     short loc_180014BCD
0x180014bc8  mov     [rsp+4C0h+phPrinter], rbx
0x180014bcd  test    r14d, r14d
0x180014bd0  jz      short loc_180014C00
0x180014bd2  mov     rcx, [rsi]; this
0x180014bd5  lea     rdx, [rsp+4C0h+phkResult]; struct CUmRdpRpc **
0x180014bda  mov     [rsp+4C0h+phkResult], 0
0x180014be3  call    ?CreateUmRdpRpc@CUmRdpDr@@QEAAJAEAPEAVCUmRdpRpc@@@Z; CUmRdpDr::CreateUmRdpRpc(CUmRdpRpc * &)
0x180014be8  test    eax, eax
0x180014bea  jnz     short loc_180014C00
0x180014bec  mov     rcx, [rsp+4C0h+phkResult]; this
0x180014bf1  call    ?RestoreDefaultPrinter@CUmRdpRpc@@QEAAIH@Z; CUmRdpRpc::RestoreDefaultPrinter(int)
0x180014bf6  mov     rcx, [rsp+4C0h+phkResult]; this
0x180014bfb  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x180014c00  test    edi, edi
0x180014c02  jnz     short loc_180014C28
0x180014c04  lea     r8, [rsp+4C0h+phkResult]; unsigned __int16 **
0x180014c09  mov     [rsp+4C0h+phkResult], r15
0x180014c0e  lea     edx, [rdi+1]; int
0x180014c11  lea     rcx, EVENT_NOTIFY_DELETE_PRINTER_FAILED; struct _EVENT_DESCRIPTOR *
0x180014c18  call    ?TsLogError@@YAXAEBU_EVENT_DESCRIPTOR@@HQEAPEAGK@Z; TsLogError(_EVENT_DESCRIPTOR const &,int,ushort * * const,ulong)
0x180014c1d  call    cs:__imp_GetLastError
0x180014c23  jmp     loc_180014CB6
0x180014c28  test    rbx, rbx
0x180014c2b  jz      loc_180014CB6
0x180014c31  mov     r9, [rbx+8]
0x180014c35  test    r9, r9
0x180014c38  jz      short loc_180014CB6
0x180014c3a  lea     r8, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x180014c41  mov     [rsp+4C0h+phkResult], 0
0x180014c4a  mov     edx, 104h; unsigned __int64
0x180014c4f  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x180014c56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014c5b  lea     rax, [rsp+4C0h+phkResult]
0x180014c60  mov     r9d, 0F003Fh; samDesired
0x180014c66  xor     r8d, r8d; ulOptions
0x180014c69  mov     [rsp+4C0h+pcbNeeded], rax; phkResult
0x180014c6e  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x180014c75  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014c7c  call    cs:__imp_RegOpenKeyExW
0x180014c82  test    eax, eax
0x180014c84  jnz     short loc_180014CB6
0x180014c86  mov     rcx, [rsp+4C0h+phkResult]; hKey
0x180014c8b  lea     rdx, aRecyclable; "recyclable"
0x180014c92  mov     [rsp+4C0h+cbData], eax; cbData
0x180014c96  xor     r9d, r9d; dwType
0x180014c99  xor     r8d, r8d; Reserved
0x180014c9c  mov     [rsp+4C0h+pcbNeeded], 0; lpData
0x180014ca5  call    cs:__imp_RegSetValueExW
0x180014cab  mov     rcx, [rsp+4C0h+phkResult]; hKey
0x180014cb0  call    cs:__imp_RegCloseKey
0x180014cb6  mov     rcx, [rsp+4C0h+phPrinter]; hPrinter
0x180014cbb  test    rcx, rcx
0x180014cbe  jz      short loc_180014CC6
0x180014cc0  call    cs:__imp_ClosePrinter
0x180014cc6  dec     dword ptr [rsi+8]
0x180014cc9  test    rbx, rbx
0x180014ccc  jz      short loc_180014CD6
0x180014cce  mov     rcx, rbx; Block
0x180014cd1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014cd6  mov     eax, edi
0x180014cd8  mov     rcx, [rbp+3C0h+var_30]
0x180014cdf  xor     rcx, rsp; StackCookie
0x180014ce2  call    __security_check_cookie
0x180014ce7  mov     rbx, [rsp+4C0h+arg_10]
0x180014cef  add     rsp, 4A0h
0x180014cf6  pop     r15
0x180014cf8  pop     r14
0x180014cfa  pop     rdi
0x180014cfb  pop     rsi
0x180014cfc  pop     rbp
0x180014cfd  retn
```
