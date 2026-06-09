# YOpenPrinterEx(ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *)

- ea: `0x140004890`
- end: `0x140004ad2`
- name: `?YOpenPrinterEx@@YAKPEAGPEAPEAX0PEAU_DEVMODE_CONTAINER@@KW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@Z`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002a70`
- `0x140002b00`
- `0x140004890`
- `0x140004ae0`
- `0x140004e90`
- `0x1400065f0`
- `0x140006860`
- `0x1400166e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400049bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004a1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400049bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004a1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ab1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004962`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400049b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004962`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400049b7`
- `RPCRT4!RpcRevertToSelf` at `0x14000495a`
- `RPCRT4!RpcRevertToSelf` at `0x14000495a`
- `RPCRT4!RpcImpersonateClient` at `0x1400049a7`
- `RPCRT4!RpcImpersonateClient` at `0x1400049a7`

## pseudocode

```c
DWORD __fastcall YOpenPrinterEx(
        unsigned __int16 *a1,
        void **a2,
        WCHAR *a3,
        unsigned int *a4,
        ACCESS_MASK a5,
        int a6,
        struct _SPLCLIENT_CONTAINER *a7)
{
  __int64 v11; // rcx
  int v12; // edi
  DWORD v13; // ebx
  RPC_STATUS v15; // eax
  char v16; // al
  int v17; // ecx
  unsigned __int64 v18; // r9
  DWORD IsValidDevmodeNo; // r8d
  unsigned __int64 v20; // rdx
  char LastError; // al
  int v22; // ecx
  struct _PRINTER_DEFAULTSW v23; // [rsp+30h] [rbp-68h] BYREF
  __int128 v24; // [rsp+48h] [rbp-50h]
  __int128 v25; // [rsp+58h] [rbp-40h]
  __int128 v26; // [rsp+68h] [rbp-30h]
  __int64 v27; // [rsp+78h] [rbp-20h]

  memset(&v23, 0, sizeof(v23));
  if ( g_bNoPrintersMode && !(unsigned int)CheckLocalCall() )
    return 1801;
  if ( a7 && !*((_QWORD *)a7 + 1) )
    return 87;
  if ( a6 == 1 && (v15 = RpcImpersonateClient(0)) != 0 )
  {
    SetLastError(v15);
    return GetLastError();
  }
  else
  {
    if ( !a4 )
      goto LABEL_25;
    v11 = *((_QWORD *)a4 + 1);
    if ( !v11 )
      goto LABEL_7;
    v18 = *a4;
    IsValidDevmodeNo = -2147024883;
    if ( v18 >= 0x4C )
    {
      v20 = *(unsigned __int16 *)(v11 + 68) + (unsigned __int64)*(unsigned __int16 *)(v11 + 70);
      if ( v18 >= v20 )
        IsValidDevmodeNo = SplIsValidDevmodeNoSize<_devicemodeW,unsigned short>(v11, v20, 2147942413LL);
    }
    if ( (unsigned int)BoolFromHResult(IsValidDevmodeNo) )
    {
LABEL_7:
      v23.pDevMode = (LPDEVMODEW)*((_QWORD *)a4 + 1);
      v23.DesiredAccess = a5;
      v23.pDatatype = a3;
      if ( a7 )
      {
        v12 = OpenPrinterExW(a1, a2, &v23, a7);
      }
      else
      {
        v24 = 0;
        v27 = 0;
        v25 = 0;
        v26 = 0;
        if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
        {
          LastError = GetLastError();
          McTemplateU0zqd_EtwEventWriteTransfer(v22, (unsigned int)DocPerf_OpenPrinter2_Start, (_DWORD)a1, 0, LastError);
        }
        v12 = RouterOpenPrinterW(a1, a2, &v23, 0, 0, 1);
        if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
        {
          v16 = GetLastError();
          McTemplateU0zqd_EtwEventWriteTransfer(v17, (unsigned int)DocPerf_OpenPrinter2_Stop, (_DWORD)a1, 0, v16);
        }
      }
      if ( a6 == 1 )
      {
        v13 = GetLastError();
        RpcRevertToSelf();
        SetLastError(v13);
      }
      if ( v12 )
      {
        _InterlockedIncrement(&ServerHandleCount);
        return 0;
      }
      else
      {
        *a2 = 0;
        return GetLastError();
      }
    }
    else
    {
LABEL_25:
      YRevertToSelf(a6);
      return 87;
    }
  }
}

```

## disassembly

```asm
0x140004890  mov     [rsp+arg_10], rbp
0x140004895  push    rdi
0x140004896  push    r14
0x140004898  push    r15
0x14000489a  sub     rsp, 80h
0x1400048a1  xor     eax, eax
0x1400048a3  xorps   xmm0, xmm0
0x1400048a6  cmp     cs:?g_bNoPrintersMode@@3_NA, al; bool g_bNoPrintersMode
0x1400048ac  mov     rdi, r9
0x1400048af  mov     rbp, r8
0x1400048b2  mov     qword ptr [rsp+98h+var_68.DesiredAccess], rax
0x1400048b7  mov     r15, rdx
0x1400048ba  mov     r14, rcx
0x1400048bd  movups  xmmword ptr [rsp+98h+var_68.pDatatype], xmm0
0x1400048c2  jnz     loc_140004A9A
0x1400048c8  mov     [rsp+98h+arg_0], rbx
0x1400048d0  mov     rbx, [rsp+98h+arg_30]
0x1400048d8  test    rbx, rbx
0x1400048db  jz      short loc_1400048E8
0x1400048dd  cmp     qword ptr [rbx+8], 0
0x1400048e2  jz      loc_14000499E
0x1400048e8  mov     [rsp+98h+arg_8], rsi
0x1400048f0  mov     esi, [rsp+98h+arg_28]
0x1400048f7  cmp     esi, 1
0x1400048fa  jz      loc_1400049A5
0x140004900  test    rdi, rdi
0x140004903  jz      loc_140004A7F
0x140004909  mov     rcx, [rdi+8]
0x14000490d  test    rcx, rcx
0x140004910  jnz     loc_140004A50
0x140004916  mov     rax, [rdi+8]
0x14000491a  mov     [rsp+98h+var_68.pDevMode], rax
0x14000491f  mov     eax, [rsp+98h+arg_20]
0x140004926  mov     [rsp+98h+var_68.DesiredAccess], eax
0x14000492a  mov     [rsp+98h+var_68.pDatatype], rbp
0x14000492f  test    rbx, rbx
0x140004932  jz      loc_1400049C5
0x140004938  mov     r9, rbx; struct _SPLCLIENT_CONTAINER *
0x14000493b  lea     r8, [rsp+98h+var_68]; struct _PRINTER_DEFAULTSW *
0x140004940  mov     rdx, r15; void **
0x140004943  mov     rcx, r14; unsigned __int16 *
0x140004946  call    ?OpenPrinterExW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAU_SPLCLIENT_CONTAINER@@@Z; OpenPrinterExW(ushort *,void * *,_PRINTER_DEFAULTSW *,_SPLCLIENT_CONTAINER *)
0x14000494b  mov     edi, eax
0x14000494d  cmp     esi, 1
0x140004950  jnz     short loc_140004968
0x140004952  call    cs:__imp_GetLastError
0x140004958  mov     ebx, eax
0x14000495a  call    cs:__imp_RpcRevertToSelf
0x140004960  mov     ecx, ebx; dwErrCode
0x140004962  call    cs:__imp_SetLastError
0x140004968  test    edi, edi
0x14000496a  jz      loc_140004A3E
0x140004970  lock inc cs:?ServerHandleCount@@3JA; long ServerHandleCount
0x140004977  xor     eax, eax
0x140004979  mov     rsi, [rsp+98h+arg_8]
0x140004981  mov     rbx, [rsp+98h+arg_0]
0x140004989  mov     rbp, [rsp+98h+arg_10]
0x140004991  add     rsp, 80h
0x140004998  pop     r15
0x14000499a  pop     r14
0x14000499c  pop     rdi
0x14000499d  retn
0x14000499e  mov     eax, 57h ; 'W'
0x1400049a3  jmp     short loc_140004981
0x1400049a5  xor     ecx, ecx; BindingHandle
0x1400049a7  call    cs:__imp_RpcImpersonateClient
0x1400049ad  test    eax, eax
0x1400049af  jz      loc_140004900
0x1400049b5  mov     ecx, eax; dwErrCode
0x1400049b7  call    cs:__imp_SetLastError
0x1400049bd  call    cs:__imp_GetLastError
0x1400049c3  jmp     short loc_140004979
0x1400049c5  xorps   xmm0, xmm0
0x1400049c8  xor     eax, eax
0x1400049ca  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x1400049d1  movups  [rsp+98h+var_50], xmm0
0x1400049d6  mov     [rsp+98h+var_20], rax
0x1400049db  movups  [rsp+98h+var_40], xmm0
0x1400049e0  movups  [rsp+98h+var_30], xmm0
0x1400049e5  jnz     loc_140004AB1
0x1400049eb  mov     [rsp+98h+var_70], 1; int
0x1400049f3  lea     r8, [rsp+98h+var_68]; struct _PRINTER_DEFAULTSW *
0x1400049f8  xor     r9d, r9d; unsigned __int8 *
0x1400049fb  mov     [rsp+98h+var_78], 0; unsigned int
0x140004a03  mov     rdx, r15; void **
0x140004a06  mov     rcx, r14; lpValueName
0x140004a09  call    ?RouterOpenPrinterW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAEKH@Z; RouterOpenPrinterW(ushort *,void * *,_PRINTER_DEFAULTSW *,uchar *,ulong,int)
0x140004a0e  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x140004a15  mov     edi, eax
0x140004a17  jz      loc_14000494D
0x140004a1d  call    cs:__imp_GetLastError
0x140004a23  xor     r9d, r9d
0x140004a26  lea     rdx, DocPerf_OpenPrinter2_Stop
0x140004a2d  mov     r8, r14
0x140004a30  mov     [rsp+98h+var_78], eax
0x140004a34  call    McTemplateU0zqd_EtwEventWriteTransfer
0x140004a39  jmp     loc_14000494D
0x140004a3e  mov     qword ptr [r15], 0
0x140004a45  call    cs:__imp_GetLastError
0x140004a4b  jmp     loc_140004979
0x140004a50  mov     r9d, [rdi]
0x140004a53  mov     r8d, 8007000Dh
0x140004a59  cmp     r9, 4Ch ; 'L'
0x140004a5d  jb      short loc_140004A6F
0x140004a5f  movzx   edx, word ptr [rcx+46h]
0x140004a63  movzx   eax, word ptr [rcx+44h]
0x140004a67  add     rdx, rax
0x140004a6a  cmp     r9, rdx
0x140004a6d  jnb     short loc_140004A90
0x140004a6f  mov     ecx, r8d; dwErrCode
0x140004a72  call    BoolFromHResult
0x140004a77  test    eax, eax
0x140004a79  jnz     loc_140004916
0x140004a7f  mov     ecx, esi
0x140004a81  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x140004a86  mov     eax, 57h ; 'W'
0x140004a8b  jmp     loc_140004979
0x140004a90  call    ??$SplIsValidDevmodeNoSize@U_devicemodeW@@G@@YAJPEAU_devicemodeW@@@Z; SplIsValidDevmodeNoSize<_devicemodeW,ushort>(_devicemodeW *)
0x140004a95  mov     r8d, eax
0x140004a98  jmp     short loc_140004A6F
0x140004a9a  call    CheckLocalCall
0x140004a9f  test    eax, eax
0x140004aa1  jnz     loc_1400048C8
0x140004aa7  mov     eax, 709h
0x140004aac  jmp     loc_140004989
0x140004ab1  call    cs:__imp_GetLastError
0x140004ab7  xor     r9d, r9d
0x140004aba  lea     rdx, DocPerf_OpenPrinter2_Start
0x140004ac1  mov     r8, r14
0x140004ac4  mov     [rsp+98h+var_78], eax
0x140004ac8  call    McTemplateU0zqd_EtwEventWriteTransfer
0x140004acd  jmp     loc_1400049EB
```
