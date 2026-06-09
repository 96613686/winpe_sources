# CDataFormat::GetDataOnMedium(Windows::ApplicationModel::DataTransfer::IDataPackage *,Microsoft::WRL::Wrappers::SRWLock &&,tagSTGMEDIUM *)

- ea: `0x18002e9a0`
- end: `0x18002ed06`
- name: `?GetDataOnMedium@CDataFormat@@QEAAJPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@$$QEAVSRWLock@Wrappers@WRL@Microsoft@@PEAUtagSTGMEDIUM@@@Z`
- size: `870`
- prototype: `__int64 __fastcall(__int64, __int64, void *, STGMEDIUM *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d820`

## callees

- `0x18002e9a0`
- `0x18003703c`
- `0x180038eb8`
- `0x18003bd18`
- `0x18007b4d0`
- `0x180081010`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18002eb52`
- `SHCORE!SHCreateThread` at `0x18002eb52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ea5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002eace`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ea5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002eace`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ea71`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002eae0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ea71`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002eae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eaef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eaef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb5c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002eba3`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002eba3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002ec85`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002ec85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eccf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eccf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!InSendMessageEx` at `0x18002e9e4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!InSendMessageEx` at `0x18002e9e4`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18002ec10`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18002ec10`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x18002ec30`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x18002ec30`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18002ebfd`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18002ec57`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18002ebfd`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18002ec57`

## pseudocode

```c
__int64 __fastcall CDataFormat::GetDataOnMedium(__int64 a1, __int64 a2, void *a3, STGMEDIUM *a4)
{
  DWORD tymed; // ebx
  int StreamOnHGlobal; // ebx
  void *v10; // rcx
  HANDLE CurrentThread; // rax
  __int64 v12; // rcx
  HANDLE v13; // rax
  signed int LastError; // eax
  signed int v15; // eax
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // rsi
  LPLOCKBYTES v17; // rcx
  __int64 v18; // rcx
  char *v19; // rcx
  __int64 v20; // rcx
  char v22[8]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v23; // [rsp+38h] [rbp-41h]
  char v24[8]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v25; // [rsp+48h] [rbp-31h]
  int pData; // [rsp+50h] [rbp-29h] BYREF
  __int64 v27; // [rsp+58h] [rbp-21h]
  STGMEDIUM *v28; // [rsp+60h] [rbp-19h]
  HGLOBAL hGlobal; // [rsp+68h] [rbp-11h]
  __int64 v30; // [rsp+70h] [rbp-9h]
  __int64 v31; // [rsp+78h] [rbp-1h] BYREF
  void *TokenHandle[10]; // [rsp+80h] [rbp+7h] BYREF
  LPLOCKBYTES pplkbyt; // [rsp+E0h] [rbp+67h] BYREF

  tymed = a4->tymed;
  if ( tymed != (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 80LL))(a1) )
    return (unsigned int)-2147221399;
  if ( (InSendMessageEx(0) & 9) != 1 )
    return (unsigned int)CDataFormat::InternalGetDataOnMedium(a1, a2, a3, a4);
  pData = 0;
  v27 = a1;
  v28 = a4;
  hGlobal = 0;
  v31 = 0;
  TokenHandle[0] = 0;
  TokenHandle[1] = a3;
  v30 = 0;
  LOBYTE(pplkbyt) = 0;
  IsRunningInAppContainer(v10, (bool *)&pplkbyt);
  if ( !(_BYTE)pplkbyt )
  {
    v22[0] = 0;
    v23 = 0;
    if ( (int)CImpersonateCaller::Impersonate((CImpersonateCaller *)v22) >= 0 )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xCu, 1, TokenHandle) )
        GetLastError();
    }
    if ( v22[0] )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 40LL))(v23);
    v12 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  v24[0] = 0;
  v25 = 0;
  StreamOnHGlobal = CImpersonateCaller::Impersonate((CImpersonateCaller *)v24);
  if ( StreamOnHGlobal >= 0 )
  {
    v13 = GetCurrentThread();
    if ( !OpenThreadToken(v13, 0xCu, 1, TokenHandle) )
    {
      LastError = GetLastError();
      StreamOnHGlobal = LastError;
      if ( LastError > 0 )
        StreamOnHGlobal = (unsigned __int16)LastError | 0x80070000;
      if ( StreamOnHGlobal >= 0 )
      {
        StreamOnHGlobal = -2147467259;
        goto LABEL_43;
      }
      if ( StreamOnHGlobal != -2147023888 )
        goto LABEL_43;
    }
    StreamOnHGlobal = CMarshaledInterface::Marshal(&v31, &GUID_61ebf5c7_efea_4346_9554_981d7e198ffe, a2, 1);
    if ( StreamOnHGlobal >= 0 )
    {
      if ( !SHCreateThread(
              CClipboardStatics::InternalGetTrustLevelStatic,
              &pData,
              0x48u,
              lambda_ae2b942e1e5f1bbac87b234ec8ea7602_::_lambda_invoker_cdecl_) )
      {
        v15 = GetLastError();
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        if ( v15 >= 0 )
          v15 = -2147467259;
        StreamOnHGlobal = v15;
        goto LABEL_43;
      }
      StreamOnHGlobal = pData;
      if ( pData >= 0 )
      {
        if ( hGlobal )
        {
          if ( a4->tymed == 4 )
          {
            p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&a4->hBitmap;
            StreamOnHGlobal = CreateStreamOnHGlobal(hGlobal, 1, &a4->pstm);
            if ( StreamOnHGlobal >= 0 )
            {
              hGlobal = 0;
              StreamOnHGlobal = (*(__int64 (__fastcall **)(HBITMAP, __int64))(*(_QWORD *)p_hBitmap->hBitmap + 48LL))(
                                  p_hBitmap->hBitmap,
                                  v30);
              if ( StreamOnHGlobal >= 0 )
              {
                pplkbyt = 0;
                StreamOnHGlobal = (*(__int64 (__fastcall **)(HBITMAP, _QWORD, __int64, LPLOCKBYTES *))(*(_QWORD *)p_hBitmap->hBitmap + 40LL))(
                                    p_hBitmap->hBitmap,
                                    0,
                                    2,
                                    &pplkbyt);
                if ( StreamOnHGlobal >= 0 )
                  goto LABEL_43;
              }
              ReleaseStgMedium(a4);
            }
          }
          else
          {
            pplkbyt = 0;
            StreamOnHGlobal = CreateILockBytesOnHGlobal(hGlobal, 1, &pplkbyt);
            if ( StreamOnHGlobal >= 0 )
            {
              hGlobal = 0;
              StreamOnHGlobal = StgCreateDocfileOnILockBytes(pplkbyt, 0x1012u, 0, &a4->pstg);
              if ( StreamOnHGlobal >= 0 )
              {
                StreamOnHGlobal = (*(__int64 (__fastcall **)(HBITMAP, _QWORD))(*(_QWORD *)a4->hBitmap + 72LL))(
                                    a4->hBitmap,
                                    0);
                if ( StreamOnHGlobal < 0 )
                  ReleaseStgMedium(a4);
              }
            }
            v17 = pplkbyt;
            if ( pplkbyt )
            {
              pplkbyt = 0;
              ((void (__fastcall *)(LPLOCKBYTES))v17->lpVtbl->Release)(v17);
            }
            if ( StreamOnHGlobal >= 0 )
              goto LABEL_43;
          }
          if ( hGlobal )
            GlobalFree(hGlobal);
        }
      }
    }
  }
LABEL_43:
  if ( v24[0] )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 40LL))(v25);
  v18 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = (char *)TokenHandle[0];
  TokenHandle[0] = 0;
  if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v19);
  v20 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18002e9a0  push    rbp
0x18002e9a2  push    rbx
0x18002e9a3  push    rsi
0x18002e9a4  push    rdi
0x18002e9a5  push    r12
0x18002e9a7  push    r13
0x18002e9a9  push    r14
0x18002e9ab  push    r15
0x18002e9ad  lea     rbp, [rsp-1Fh]
0x18002e9b2  sub     rsp, 98h
0x18002e9b9  mov     rdi, r9
0x18002e9bc  mov     r14, r8
0x18002e9bf  mov     r15, rdx
0x18002e9c2  mov     rsi, rcx
0x18002e9c5  mov     ebx, [r9]
0x18002e9c8  mov     rax, [rcx]
0x18002e9cb  mov     rax, [rax+50h]
0x18002e9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9d4  cmp     ebx, eax
0x18002e9d6  jz      short loc_18002E9E2
0x18002e9d8  mov     ebx, 80040069h
0x18002e9dd  jmp     loc_18002ECF0
0x18002e9e2  xor     ecx, ecx; lpReserved
0x18002e9e4  call    cs:__imp_InSendMessageEx
0x18002e9ea  and     al, 9
0x18002e9ec  mov     r13d, 1
0x18002e9f2  cmp     al, r13b
0x18002e9f5  jz      short loc_18002EA0F
0x18002e9f7  mov     r9, rdi
0x18002e9fa  mov     r8, r14
0x18002e9fd  mov     rdx, r15
0x18002ea00  mov     rcx, rsi
0x18002ea03  call    ?InternalGetDataOnMedium@CDataFormat@@IEAAJPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@$$QEAVSRWLock@Wrappers@WRL@Microsoft@@PEAUtagSTGMEDIUM@@@Z; CDataFormat::InternalGetDataOnMedium(Windows::ApplicationModel::DataTransfer::IDataPackage *,Microsoft::WRL::Wrappers::SRWLock &&,tagSTGMEDIUM *)
0x18002ea08  mov     ebx, eax
0x18002ea0a  jmp     loc_18002ECF0
0x18002ea0f  xor     r12d, r12d
0x18002ea12  mov     [rbp+57h+pData], r12d
0x18002ea16  mov     [rbp+57h+var_78], rsi
0x18002ea1a  mov     [rbp+57h+var_70], rdi
0x18002ea1e  mov     [rbp+57h+hGlobal], r12
0x18002ea22  mov     [rbp+57h+var_58], r12
0x18002ea26  mov     [rbp+57h+TokenHandle], r12
0x18002ea2a  mov     [rbp+57h+var_48], r14
0x18002ea2e  mov     [rbp+57h+var_60], r12
0x18002ea32  mov     byte ptr [rbp+57h+pplkbyt], r12b
0x18002ea36  lea     rdx, [rbp+57h+pplkbyt]; bool *
0x18002ea3a  call    ?IsRunningInAppContainer@@YAJPEAXPEA_N@Z; IsRunningInAppContainer(void *,bool *)
0x18002ea3f  lea     esi, [r12+0Ch]
0x18002ea44  cmp     byte ptr [rbp+57h+pplkbyt], r12b
0x18002ea48  jnz     short loc_18002EAB3
0x18002ea4a  mov     [rbp+57h+var_A0], r12b
0x18002ea4e  mov     [rbp+57h+var_98], r12
0x18002ea52  lea     rcx, [rbp+57h+var_A0]; this
0x18002ea56  call    ?Impersonate@CImpersonateCaller@@QEAAJXZ; CImpersonateCaller::Impersonate(void)
0x18002ea5b  test    eax, eax
0x18002ea5d  js      short loc_18002EA82
0x18002ea5f  call    cs:__imp_GetCurrentThread
0x18002ea65  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002ea69  mov     r8d, r13d; OpenAsSelf
0x18002ea6c  mov     edx, esi; DesiredAccess
0x18002ea6e  mov     rcx, rax; ThreadHandle
0x18002ea71  call    cs:__imp_OpenThreadToken
0x18002ea77  test    eax, eax
0x18002ea79  jnz     short loc_18002EA82
0x18002ea7b  call    cs:__imp_GetLastError
0x18002ea81  nop
0x18002ea82  cmp     [rbp+57h+var_A0], r12b
0x18002ea86  jz      short loc_18002EA99
0x18002ea88  mov     rcx, [rbp+57h+var_98]
0x18002ea8c  mov     rax, [rcx]
0x18002ea8f  mov     rax, [rax+28h]
0x18002ea93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea98  nop
0x18002ea99  mov     rcx, [rbp+57h+var_98]
0x18002ea9d  test    rcx, rcx
0x18002eaa0  jz      short loc_18002EAB3
0x18002eaa2  mov     [rbp+57h+var_98], r12
0x18002eaa6  mov     rax, [rcx]
0x18002eaa9  mov     rax, [rax+10h]
0x18002eaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eab2  nop
0x18002eab3  mov     [rbp+57h+var_90], r12b
0x18002eab7  mov     [rbp+57h+var_88], r12
0x18002eabb  lea     rcx, [rbp+57h+var_90]; this
0x18002eabf  call    ?Impersonate@CImpersonateCaller@@QEAAJXZ; CImpersonateCaller::Impersonate(void)
0x18002eac4  mov     ebx, eax
0x18002eac6  test    eax, eax
0x18002eac8  js      loc_18002EC8C
0x18002eace  call    cs:__imp_GetCurrentThread
0x18002ead4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002ead8  mov     r8d, r13d; OpenAsSelf
0x18002eadb  mov     edx, esi; DesiredAccess
0x18002eadd  mov     rcx, rax; ThreadHandle
0x18002eae0  call    cs:__imp_OpenThreadToken
0x18002eae6  mov     esi, 80070000h
0x18002eaeb  test    eax, eax
0x18002eaed  jnz     short loc_18002EB1A
0x18002eaef  call    cs:__imp_GetLastError
0x18002eaf5  mov     ebx, eax
0x18002eaf7  test    eax, eax
0x18002eaf9  jle     short loc_18002EB00
0x18002eafb  movzx   ebx, ax
0x18002eafe  or      ebx, esi
0x18002eb00  test    ebx, ebx
0x18002eb02  js      short loc_18002EB0E
0x18002eb04  mov     ebx, 80004005h
0x18002eb09  jmp     loc_18002EC8C
0x18002eb0e  cmp     ebx, 800703F0h
0x18002eb14  jnz     loc_18002EC8C
0x18002eb1a  mov     r9d, r13d
0x18002eb1d  mov     r8, r15
0x18002eb20  lea     rdx, _GUID_61ebf5c7_efea_4346_9554_981d7e198ffe
0x18002eb27  lea     rcx, [rbp+57h+var_58]
0x18002eb2b  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x18002eb30  mov     ebx, eax
0x18002eb32  test    eax, eax
0x18002eb34  js      loc_18002EC8C
0x18002eb3a  lea     r9, _lambda_ae2b942e1e5f1bbac87b234ec8ea7602____lambda_invoker_cdecl_; pfnCallback
0x18002eb41  mov     r8d, 48h ; 'H'; flags
0x18002eb47  lea     rdx, [rbp+57h+pData]; pData
0x18002eb4b  lea     rcx, ?InternalGetTrustLevelStatic@CClipboardStatics@@SA?AW4TrustLevel@@XZ; pfnThreadProc
0x18002eb52  call    cs:__imp_SHCreateThread
0x18002eb58  test    eax, eax
0x18002eb5a  jnz     short loc_18002EB7C
0x18002eb5c  call    cs:__imp_GetLastError
0x18002eb62  test    eax, eax
0x18002eb64  jle     short loc_18002EB6B
0x18002eb66  movzx   eax, ax
0x18002eb69  or      eax, esi
0x18002eb6b  mov     ebx, 80004005h
0x18002eb70  test    eax, eax
0x18002eb72  cmovns  eax, ebx
0x18002eb75  mov     ebx, eax
0x18002eb77  jmp     loc_18002EC8C
0x18002eb7c  mov     ebx, [rbp+57h+pData]
0x18002eb7f  test    ebx, ebx
0x18002eb81  js      loc_18002EC8C
0x18002eb87  mov     rcx, [rbp+57h+hGlobal]; hGlobal
0x18002eb8b  test    rcx, rcx
0x18002eb8e  jz      loc_18002EC8C
0x18002eb94  cmp     dword ptr [rdi], 4
0x18002eb97  jnz     short loc_18002EC05
0x18002eb99  lea     rsi, [rdi+8]
0x18002eb9d  mov     r8, rsi; ppstm
0x18002eba0  mov     edx, r13d; fDeleteOnRelease
0x18002eba3  call    cs:__imp_CreateStreamOnHGlobal
0x18002eba9  mov     ebx, eax
0x18002ebab  test    eax, eax
0x18002ebad  js      loc_18002EC7C
0x18002ebb3  mov     [rbp+57h+hGlobal], r12
0x18002ebb7  mov     rcx, [rsi]
0x18002ebba  mov     rax, [rcx]
0x18002ebbd  mov     rdx, [rbp+57h+var_60]
0x18002ebc1  mov     rax, [rax+30h]
0x18002ebc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebca  mov     ebx, eax
0x18002ebcc  test    eax, eax
0x18002ebce  js      short loc_18002EBFA
0x18002ebd0  mov     [rbp+57h+pplkbyt], r12
0x18002ebd4  mov     rcx, [rsi]
0x18002ebd7  mov     rdx, r12
0x18002ebda  mov     rax, [rcx]
0x18002ebdd  lea     r9, [rbp+57h+pplkbyt]
0x18002ebe1  mov     r8d, 2
0x18002ebe7  mov     rax, [rax+28h]
0x18002ebeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebf0  mov     ebx, eax
0x18002ebf2  test    eax, eax
0x18002ebf4  jns     loc_18002EC8C
0x18002ebfa  mov     rcx, rdi; LPSTGMEDIUM
0x18002ebfd  call    cs:__imp_ReleaseStgMedium
0x18002ec03  jmp     short loc_18002EC7C
0x18002ec05  mov     [rbp+57h+pplkbyt], r12
0x18002ec09  lea     r8, [rbp+57h+pplkbyt]; pplkbyt
0x18002ec0d  mov     edx, r13d; fDeleteOnRelease
0x18002ec10  call    cs:__imp_CreateILockBytesOnHGlobal
0x18002ec16  mov     ebx, eax
0x18002ec18  test    eax, eax
0x18002ec1a  js      short loc_18002EC5E
0x18002ec1c  mov     [rbp+57h+hGlobal], r12
0x18002ec20  lea     r9, [rdi+8]; ppstgOpen
0x18002ec24  xor     r8d, r8d; reserved
0x18002ec27  mov     edx, 1012h; grfMode
0x18002ec2c  mov     rcx, [rbp+57h+pplkbyt]; plkbyt
0x18002ec30  call    cs:__imp_StgCreateDocfileOnILockBytes
0x18002ec36  mov     ebx, eax
0x18002ec38  test    eax, eax
0x18002ec3a  js      short loc_18002EC5E
0x18002ec3c  mov     rcx, [rdi+8]
0x18002ec40  mov     rax, [rcx]
0x18002ec43  xor     edx, edx
0x18002ec45  mov     rax, [rax+48h]
0x18002ec49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec4e  mov     ebx, eax
0x18002ec50  test    eax, eax
0x18002ec52  jns     short loc_18002EC5E
0x18002ec54  mov     rcx, rdi; LPSTGMEDIUM
0x18002ec57  call    cs:__imp_ReleaseStgMedium
0x18002ec5d  nop
0x18002ec5e  mov     rcx, [rbp+57h+pplkbyt]
0x18002ec62  test    rcx, rcx
0x18002ec65  jz      short loc_18002EC78
0x18002ec67  mov     [rbp+57h+pplkbyt], r12
0x18002ec6b  mov     rax, [rcx]
0x18002ec6e  mov     rax, [rax+10h]
0x18002ec72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec77  nop
0x18002ec78  test    ebx, ebx
0x18002ec7a  jns     short loc_18002EC8C
0x18002ec7c  mov     rcx, [rbp+57h+hGlobal]; hMem
0x18002ec80  test    rcx, rcx
0x18002ec83  jz      short loc_18002EC8C
0x18002ec85  call    cs:__imp_GlobalFree
0x18002ec8b  nop
0x18002ec8c  cmp     [rbp+57h+var_90], r12b
0x18002ec90  jz      short loc_18002ECA3
0x18002ec92  mov     rcx, [rbp+57h+var_88]
0x18002ec96  mov     rax, [rcx]
0x18002ec99  mov     rax, [rax+28h]
0x18002ec9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eca2  nop
0x18002eca3  mov     rcx, [rbp+57h+var_88]
0x18002eca7  test    rcx, rcx
0x18002ecaa  jz      short loc_18002ECBD
0x18002ecac  mov     [rbp+57h+var_88], r12
0x18002ecb0  mov     rax, [rcx]
0x18002ecb3  mov     rax, [rax+10h]
0x18002ecb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecbc  nop
0x18002ecbd  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002ecc1  mov     [rbp+57h+TokenHandle], r12
0x18002ecc5  lea     rax, [rcx-1]
0x18002ecc9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002eccd  ja      short loc_18002ECD6
0x18002eccf  call    cs:__imp_CloseHandle
0x18002ecd5  nop
0x18002ecd6  mov     rcx, [rbp+57h+var_58]
0x18002ecda  test    rcx, rcx
0x18002ecdd  jz      short loc_18002ECF0
0x18002ecdf  mov     [rbp+57h+var_58], r12
0x18002ece3  mov     rax, [rcx]
0x18002ece6  mov     rax, [rax+10h]
0x18002ecea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecef  nop
0x18002ecf0  mov     eax, ebx
0x18002ecf2  add     rsp, 98h
0x18002ecf9  pop     r15
0x18002ecfb  pop     r14
0x18002ecfd  pop     r13
0x18002ecff  pop     r12
0x18002ed01  pop     rdi
0x18002ed02  pop     rsi
0x18002ed03  pop     rbx
0x18002ed04  pop     rbp
0x18002ed05  retn
```
