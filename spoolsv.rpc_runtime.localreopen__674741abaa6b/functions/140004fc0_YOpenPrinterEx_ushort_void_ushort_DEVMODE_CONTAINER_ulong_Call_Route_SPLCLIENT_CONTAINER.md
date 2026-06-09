# YOpenPrinterEx(ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *)

- ea: `0x140004fc0`
- end: `0x140005239`
- name: `?YOpenPrinterEx@@YAKPEAGPEAPEAX0PEAU_DEVMODE_CONTAINER@@KW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@Z`
- size: `633`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400028e0`
- `0x140002f40`
- `0x140004a28`
- `0x140004fc0`
- `0x140005240`
- `0x140005630`
- `0x140007090`
- `0x140017b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000510c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000510c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005212`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000509e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005100`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000509e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005100`
- `RPCRT4!RpcRevertToSelf` at `0x140005090`
- `RPCRT4!RpcRevertToSelf` at `0x140005090`
- `RPCRT4!RpcImpersonateClient` at `0x1400050ea`
- `RPCRT4!RpcImpersonateClient` at `0x1400050ea`

## pseudocode

```c
DWORD __fastcall YOpenPrinterEx(
        unsigned __int16 *a1,
        void **a2,
        WCHAR *a3,
        unsigned int *a4,
        ACCESS_MASK a5,
        unsigned int a6,
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
0x140004fc0  mov     [rsp+arg_10], rbp
0x140004fc5  push    rdi
0x140004fc6  push    r14
0x140004fc8  push    r15
0x140004fca  sub     rsp, 80h
0x140004fd1  xor     eax, eax
0x140004fd3  xorps   xmm0, xmm0
0x140004fd6  cmp     cs:?g_bNoPrintersMode@@3_NA, al; bool g_bNoPrintersMode
0x140004fdc  mov     rdi, r9
0x140004fdf  mov     rbp, r8
0x140004fe2  mov     qword ptr [rsp+98h+var_68.DesiredAccess], rax
0x140004fe7  mov     r15, rdx
0x140004fea  mov     r14, rcx
0x140004fed  movups  xmmword ptr [rsp+98h+var_68.pDatatype], xmm0
0x140004ff2  jnz     loc_1400051FB
0x140004ff8  mov     [rsp+98h+arg_0], rbx
0x140005000  mov     rbx, [rsp+98h+arg_30]
0x140005008  test    rbx, rbx
0x14000500b  jz      short loc_140005018
0x14000500d  cmp     qword ptr [rbx+8], 0
0x140005012  jz      loc_1400050E1
0x140005018  mov     [rsp+98h+arg_8], rsi
0x140005020  mov     esi, [rsp+98h+arg_28]
0x140005027  cmp     esi, 1
0x14000502a  jz      loc_1400050E8
0x140005030  test    rdi, rdi
0x140005033  jz      loc_1400051E0
0x140005039  mov     rcx, [rdi+8]
0x14000503d  test    rcx, rcx
0x140005040  jnz     loc_1400051B1
0x140005046  mov     rax, [rdi+8]
0x14000504a  mov     [rsp+98h+var_68.pDevMode], rax
0x14000504f  mov     eax, [rsp+98h+arg_20]
0x140005056  mov     [rsp+98h+var_68.DesiredAccess], eax
0x14000505a  mov     [rsp+98h+var_68.pDatatype], rbp
0x14000505f  test    rbx, rbx
0x140005062  jz      loc_14000511A
0x140005068  mov     r9, rbx; struct _SPLCLIENT_CONTAINER *
0x14000506b  lea     r8, [rsp+98h+var_68]; struct _PRINTER_DEFAULTSW *
0x140005070  mov     rdx, r15; void **
0x140005073  mov     rcx, r14; unsigned __int16 *
0x140005076  call    ?OpenPrinterExW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAU_SPLCLIENT_CONTAINER@@@Z; OpenPrinterExW(ushort *,void * *,_PRINTER_DEFAULTSW *,_SPLCLIENT_CONTAINER *)
0x14000507b  mov     edi, eax
0x14000507d  cmp     esi, 1
0x140005080  jnz     short loc_1400050AA
0x140005082  call    cs:__imp_GetLastError
0x140005089  nop     dword ptr [rax+rax+00h]
0x14000508e  mov     ebx, eax
0x140005090  call    cs:__imp_RpcRevertToSelf
0x140005097  nop     dword ptr [rax+rax+00h]
0x14000509c  mov     ecx, ebx; dwErrCode
0x14000509e  call    cs:__imp_SetLastError
0x1400050a5  nop     dword ptr [rax+rax+00h]
0x1400050aa  test    edi, edi
0x1400050ac  jz      loc_140005199
0x1400050b2  lock inc cs:?ServerHandleCount@@3JA; long ServerHandleCount
0x1400050b9  xor     eax, eax
0x1400050bb  mov     rsi, [rsp+98h+arg_8]
0x1400050c3  mov     rbx, [rsp+98h+arg_0]
0x1400050cb  mov     rbp, [rsp+98h+arg_10]
0x1400050d3  add     rsp, 80h
0x1400050da  pop     r15
0x1400050dc  pop     r14
0x1400050de  pop     rdi
0x1400050df  retn
0x1400050e1  mov     eax, 57h ; 'W'
0x1400050e6  jmp     short loc_1400050C3
0x1400050e8  xor     ecx, ecx; BindingHandle
0x1400050ea  call    cs:__imp_RpcImpersonateClient
0x1400050f1  nop     dword ptr [rax+rax+00h]
0x1400050f6  test    eax, eax
0x1400050f8  jz      loc_140005030
0x1400050fe  mov     ecx, eax; dwErrCode
0x140005100  call    cs:__imp_SetLastError
0x140005107  nop     dword ptr [rax+rax+00h]
0x14000510c  call    cs:__imp_GetLastError
0x140005113  nop     dword ptr [rax+rax+00h]
0x140005118  jmp     short loc_1400050BB
0x14000511a  xorps   xmm0, xmm0
0x14000511d  xor     eax, eax
0x14000511f  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x140005126  movups  [rsp+98h+var_50], xmm0
0x14000512b  mov     [rsp+98h+var_20], rax
0x140005130  movups  [rsp+98h+var_40], xmm0
0x140005135  movups  [rsp+98h+var_30], xmm0
0x14000513a  jnz     loc_140005212
0x140005140  mov     [rsp+98h+var_70], 1; int
0x140005148  lea     r8, [rsp+98h+var_68]; struct _PRINTER_DEFAULTSW *
0x14000514d  xor     r9d, r9d; unsigned __int8 *
0x140005150  mov     [rsp+98h+var_78], 0; unsigned int
0x140005158  mov     rdx, r15; void **
0x14000515b  mov     rcx, r14; lpValueName
0x14000515e  call    ?RouterOpenPrinterW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAEKH@Z; RouterOpenPrinterW(ushort *,void * *,_PRINTER_DEFAULTSW *,uchar *,ulong,int)
0x140005163  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x14000516a  mov     edi, eax
0x14000516c  jz      loc_14000507D
0x140005172  call    cs:__imp_GetLastError
0x140005179  nop     dword ptr [rax+rax+00h]
0x14000517e  xor     r9d, r9d
0x140005181  lea     rdx, DocPerf_OpenPrinter2_Stop
0x140005188  mov     r8, r14
0x14000518b  mov     [rsp+98h+var_78], eax
0x14000518f  call    McTemplateU0zqd_EtwEventWriteTransfer
0x140005194  jmp     loc_14000507D
0x140005199  mov     qword ptr [r15], 0
0x1400051a0  call    cs:__imp_GetLastError
0x1400051a7  nop     dword ptr [rax+rax+00h]
0x1400051ac  jmp     loc_1400050BB
0x1400051b1  mov     r9d, [rdi]
0x1400051b4  mov     r8d, 8007000Dh
0x1400051ba  cmp     r9, 4Ch ; 'L'
0x1400051be  jb      short loc_1400051D0
0x1400051c0  movzx   edx, word ptr [rcx+46h]
0x1400051c4  movzx   eax, word ptr [rcx+44h]
0x1400051c8  add     rdx, rax
0x1400051cb  cmp     r9, rdx
0x1400051ce  jnb     short loc_1400051F1
0x1400051d0  mov     ecx, r8d; dwErrCode
0x1400051d3  call    BoolFromHResult
0x1400051d8  test    eax, eax
0x1400051da  jnz     loc_140005046
0x1400051e0  mov     ecx, esi
0x1400051e2  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x1400051e7  mov     eax, 57h ; 'W'
0x1400051ec  jmp     loc_1400050BB
0x1400051f1  call    ??$SplIsValidDevmodeNoSize@U_devicemodeW@@G@@YAJPEAU_devicemodeW@@@Z; SplIsValidDevmodeNoSize<_devicemodeW,ushort>(_devicemodeW *)
0x1400051f6  mov     r8d, eax
0x1400051f9  jmp     short loc_1400051D0
0x1400051fb  call    CheckLocalCall
0x140005200  test    eax, eax
0x140005202  jnz     loc_140004FF8
0x140005208  mov     eax, 709h
0x14000520d  jmp     loc_1400050CB
0x140005212  call    cs:__imp_GetLastError
0x140005219  nop     dword ptr [rax+rax+00h]
0x14000521e  xor     r9d, r9d
0x140005221  lea     rdx, DocPerf_OpenPrinter2_Start
0x140005228  mov     r8, r14
0x14000522b  mov     [rsp+98h+var_78], eax
0x14000522f  call    McTemplateU0zqd_EtwEventWriteTransfer
0x140005234  jmp     loc_140005140
```
