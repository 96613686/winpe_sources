# SspipAcquireCredentialsHandle

- ea: `0x180006548`
- end: `0x1800069d0`
- name: `SspipAcquireCredentialsHandle`
- size: `1160`
- prototype: `NTSTATUS __fastcall(__int64, __int64, int, __int64, int, __int64, __int64, __int64, int, _OWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180005190`
- `0x180010f00`

## callees

- `0x180006548`
- `0x1800084b0`
- `0x18000c460`
- `0x18000e890`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180006687`
- `ntdll!NtQueryInformationThread` at `0x180006687`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800222d9`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800222d9`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000695b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000695b`
- `RPCRT4!NdrClientCall3` at `0x18000687d`
- `RPCRT4!NdrClientCall3` at `0x18000687d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800067ab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800067ab`

## pseudocode

```c
NTSTATUS __fastcall SspipAcquireCredentialsHandle(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        _OWORD *a10,
        __int64 *a11)
{
  NTSTATUS result; // eax
  __int64 *v13; // rsi
  int Pointer; // ebx
  char v15; // r14
  CLIENT_CALL_RETURN v16; // rax
  __int64 v17; // [rsp+40h] [rbp-1C8h]
  __int64 v18; // [rsp+68h] [rbp-1A0h]
  __int64 v20; // [rsp+98h] [rbp-170h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-168h]
  __int64 v22; // [rsp+A8h] [rbp-160h]
  __int64 v23; // [rsp+B0h] [rbp-158h]
  __int64 v24; // [rsp+B8h] [rbp-150h]
  __int64 v25; // [rsp+C0h] [rbp-148h] BYREF
  struct _SECPKG_APP_MODE_INFO v26; // [rsp+C8h] [rbp-140h] BYREF
  __int128 v27; // [rsp+F8h] [rbp-110h] BYREF
  __int64 v28; // [rsp+108h] [rbp-100h]
  __int64 v29; // [rsp+110h] [rbp-F8h]
  CLIENT_CALL_RETURN v30; // [rsp+118h] [rbp-F0h]
  _OWORD *v31; // [rsp+120h] [rbp-E8h]
  _SECPKG_APP_MODE_INFO v32; // [rsp+130h] [rbp-D8h] BYREF
  __int128 ThreadInformation; // [rsp+160h] [rbp-A8h] BYREF
  __int128 v34; // [rsp+170h] [rbp-98h]
  __int128 v35; // [rsp+180h] [rbp-88h]
  __int128 v36; // [rsp+190h] [rbp-78h] BYREF
  __int128 v37; // [rsp+1A0h] [rbp-68h] BYREF
  GUID ActivityId; // [rsp+1B0h] [rbp-58h] BYREF

  v23 = a4;
  v24 = a2;
  v29 = a1;
  v31 = a10;
  v22 = a7;
  v21 = a8;
  v25 = 0;
  v20 = 0;
  v36 = 0;
  v27 = 0;
  v28 = 0;
  v37 = 0;
  memset(&v32, 0, sizeof(v32));
  memset(&v26, 0, sizeof(v26));
  result = IsOkayToExecRpc(&v25);
  if ( result >= 0 )
  {
    ThreadInformation = 0;
    v34 = 0;
    v35 = 0;
    result = NtQueryInformationThread(
               (HANDLE)0xFFFFFFFFFFFFFFFELL,
               ThreadBasicInformation,
               &ThreadInformation,
               0x30u,
               0);
    if ( result >= 0 )
    {
      v36 = v34;
      v13 = &v20;
      if ( a11 )
        v13 = a11;
      LODWORD(v27) = 0;
      *((_QWORD *)&v27 + 1) = a6;
      v28 = a6;
      if ( SecpLsaInprocDispatch )
      {
        Pointer = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64, __int64, int, __int64, __int128 *, __int64, __int64, int, __int128 *, __int64 *, _QWORD, _QWORD))(SecpLsaInprocDispatch + 8))(
                    0,
                    &v36,
                    a1,
                    v24,
                    a3,
                    v23,
                    &v27,
                    v22,
                    v21,
                    a9,
                    &v37,
                    v13,
                    0,
                    0);
      }
      else
      {
        do
        {
          v15 = 0;
          ActivityId = 0;
          EventActivityIdControl(1u, &ActivityId);
          v30.Simple = 0;
          LODWORD(v18) = a9;
          LODWORD(v17) = a3;
          v16.Pointer = NdrClientCall3(
                          (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
                          0x13u,
                          0,
                          v25,
                          &ActivityId,
                          &v36,
                          v29,
                          v24,
                          v17,
                          v23,
                          &v27,
                          v22,
                          v21,
                          v18,
                          &v37,
                          v13,
                          &v32,
                          &v26).Pointer;
          Pointer = (int)v16.Pointer;
          v30.Pointer = v16.Pointer;
          if ( v26.UserFunction && ((int)(LODWORD(v16.Pointer) + 0x80000000) < 0 || LODWORD(v16.Pointer) == -2146893055) )
          {
            CleanupAppModeInfo(&v32);
            Pointer = LsaCallbackHandler(
                        v26.UserFunction,
                        v26.Argument1,
                        v26.Argument2,
                        (unsigned int)&v26.UserData,
                        (__int64)&v32.UserData);
            if ( Pointer >= 0 )
            {
              if ( v26.ReturnToLsa )
              {
                v32.UserFunction = v26.UserFunction;
                v32.Argument1 = v26.Argument1;
                v32.Argument2 = v26.Argument2;
                v32.ReturnToLsa = 0;
                v15 = 1;
                CleanupAppModeInfo(&v26);
              }
            }
          }
        }
        while ( v15 );
      }
      if ( Pointer >= 0 )
      {
        *a10 = v37;
        Pointer = 0;
      }
      CleanupAppModeInfo(&v32);
      CleanupAppModeInfo(&v26);
      return Pointer;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006548  mov     r11, rsp
0x18000654b  push    rbx
0x18000654c  push    rsi
0x18000654d  push    r12
0x18000654f  push    r13
0x180006551  push    r14
0x180006553  push    r15
0x180006555  sub     rsp, 1D8h
0x18000655c  mov     rax, cs:__security_cookie
0x180006563  xor     rax, rsp
0x180006566  mov     [rsp+208h+var_48], rax
0x18000656e  mov     [rsp+208h+var_158], r9
0x180006576  mov     [rsp+208h+var_178], r8d
0x18000657e  mov     [rsp+208h+var_150], rdx
0x180006586  mov     r12, rcx
0x180006589  mov     [rsp+208h+var_F8], rcx
0x180006591  mov     r14, [rsp+208h+arg_50]
0x180006599  mov     r15, [rsp+208h+arg_48]
0x1800065a1  mov     [rsp+208h+var_E8], r15
0x1800065a9  mov     rbx, [rsp+208h+arg_28]
0x1800065b1  mov     rax, [rsp+208h+arg_30]
0x1800065b9  mov     [rsp+208h+var_160], rax
0x1800065c1  mov     rax, [rsp+208h+arg_38]
0x1800065c9  mov     [rsp+208h+var_168], rax
0x1800065d1  mov     r13, r15
0x1800065d4  mov     qword ptr [r11-148h], 0
0x1800065df  mov     qword ptr [r11-170h], 0
0x1800065ea  xorps   xmm0, xmm0
0x1800065ed  movups  xmmword ptr [r11-78h], xmm0
0x1800065f2  xorps   xmm1, xmm1
0x1800065f5  xor     eax, eax
0x1800065f7  movups  [rsp+208h+var_110], xmm1
0x1800065ff  mov     [r11-100h], rax
0x180006606  movups  xmmword ptr [r11-68h], xmm0
0x18000660b  movups  xmmword ptr [rsp+208h+var_D8.UserFunction], xmm1
0x180006613  movups  xmmword ptr [rsp+208h+var_D8.Argument2], xmm1
0x18000661b  movups  xmmword ptr [rsp+208h+var_D8.UserData.pvBuffer], xmm1
0x180006623  movups  xmmword ptr [rsp+208h+var_140.UserFunction], xmm0
0x18000662b  movups  xmmword ptr [rsp+208h+var_140.Argument2], xmm0
0x180006633  movups  xmmword ptr [rsp+208h+var_140.UserData.pvBuffer], xmm0
0x18000663b  lea     rcx, [r11-148h]
0x180006642  call    IsOkayToExecRpc
0x180006647  test    eax, eax
0x180006649  js      loc_1800069AE
0x18000664f  xorps   xmm0, xmm0
0x180006652  movups  [rsp+208h+ThreadInformation], xmm0
0x18000665a  movups  [rsp+208h+var_98], xmm0
0x180006662  movups  [rsp+208h+var_88], xmm0
0x18000666a  mov     [rsp+208h+ReturnLength], 0; ReturnLength
0x180006673  mov     r9d, 30h ; '0'; ThreadInformationLength
0x180006679  lea     r8, [rsp+208h+ThreadInformation]; ThreadInformation
0x180006681  xor     edx, edx; ThreadInformationClass
0x180006683  lea     rcx, [rdx-2]; ThreadHandle
0x180006687  call    cs:__imp_NtQueryInformationThread
0x18000668d  test    eax, eax
0x18000668f  js      loc_1800069AE
0x180006695  mov     rax, qword ptr [rsp+208h+var_98]
0x18000669d  mov     qword ptr [rsp+208h+var_78], rax
0x1800066a5  mov     rax, qword ptr [rsp+208h+var_98+8]
0x1800066ad  mov     qword ptr [rsp+208h+var_78+8], rax
0x1800066b5  xor     eax, eax
0x1800066b7  test    eax, eax
0x1800066b9  js      loc_1800069AE
0x1800066bf  lea     rsi, [rsp+208h+var_170]
0x1800066c7  test    r14, r14
0x1800066ca  cmovnz  rsi, r14
0x1800066ce  mov     dword ptr [rsp+208h+var_110], eax
0x1800066d5  mov     qword ptr [rsp+208h+var_110+8], rbx
0x1800066dd  mov     [rsp+208h+var_100], rbx
0x1800066e5  mov     rax, cs:SecpLsaInprocDispatch
0x1800066ec  test    rax, rax
0x1800066ef  jz      loc_180006788
0x1800066f5  mov     [rsp+208h+var_1A0], 0
0x1800066fe  mov     [rsp+208h+var_1A8], 0
0x180006707  mov     [rsp+208h+var_1B0], rsi
0x18000670c  lea     rcx, [rsp+208h+var_68]
0x180006714  mov     [rsp+208h+var_1B8], rcx
0x180006719  mov     ecx, [rsp+208h+arg_40]
0x180006720  mov     dword ptr [rsp+208h+var_1C0], ecx
0x180006724  mov     rcx, [rsp+208h+var_168]
0x18000672c  mov     [rsp+208h+var_1C8], rcx
0x180006731  mov     rcx, [rsp+208h+var_160]
0x180006739  mov     [rsp+208h+var_1D0], rcx
0x18000673e  lea     rcx, [rsp+208h+var_110]
0x180006746  mov     [rsp+208h+var_1D8], rcx
0x18000674b  mov     rcx, [rsp+208h+var_158]
0x180006753  mov     [rsp+208h+var_1E0], rcx
0x180006758  mov     ecx, [rsp+208h+var_178]
0x18000675f  mov     dword ptr [rsp+208h+ReturnLength], ecx
0x180006763  mov     r9, [rsp+208h+var_150]
0x18000676b  mov     r8, r12
0x18000676e  lea     rdx, [rsp+208h+var_78]
0x180006776  xor     ecx, ecx
0x180006778  mov     rax, [rax+8]
0x18000677c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006781  mov     ebx, eax
0x180006783  jmp     loc_180006975
0x180006788  mov     r12d, [rsp+208h+arg_40]
0x180006790  xor     r14b, r14b
0x180006793  xorps   xmm0, xmm0
0x180006796  movups  xmmword ptr [rsp+208h+ActivityId.Data1], xmm0
0x18000679e  lea     rdx, [rsp+208h+ActivityId]; ActivityId
0x1800067a6  mov     ecx, 1; ControlCode
0x1800067ab  call    cs:__imp_EventActivityIdControl
0x1800067b1  mov     [rsp+208h+var_F0], 0
0x1800067bd  lea     rax, [rsp+208h+var_140]
0x1800067c5  mov     [rsp+208h+var_180], rax
0x1800067cd  lea     rax, [rsp+208h+var_D8]
0x1800067d5  mov     [rsp+208h+var_188], rax
0x1800067dd  mov     [rsp+208h+var_190], rsi
0x1800067e2  lea     rax, [rsp+208h+var_68]
0x1800067ea  mov     [rsp+208h+var_198], rax
0x1800067ef  mov     dword ptr [rsp+208h+var_1A0], r12d
0x1800067f4  mov     rax, [rsp+208h+var_168]
0x1800067fc  mov     [rsp+208h+var_1A8], rax
0x180006801  mov     rax, [rsp+208h+var_160]
0x180006809  mov     [rsp+208h+var_1B0], rax
0x18000680e  lea     rax, [rsp+208h+var_110]
0x180006816  mov     [rsp+208h+var_1B8], rax
0x18000681b  mov     rax, [rsp+208h+var_158]
0x180006823  mov     [rsp+208h+var_1C0], rax
0x180006828  mov     eax, [rsp+208h+var_178]
0x18000682f  mov     dword ptr [rsp+208h+var_1C8], eax
0x180006833  mov     rax, [rsp+208h+var_150]
0x18000683b  mov     [rsp+208h+var_1D0], rax
0x180006840  mov     rax, [rsp+208h+var_F8]
0x180006848  mov     [rsp+208h+var_1D8], rax
0x18000684d  lea     rax, [rsp+208h+var_78]
0x180006855  mov     [rsp+208h+var_1E0], rax
0x18000685a  lea     rax, [rsp+208h+ActivityId]
0x180006862  mov     [rsp+208h+ReturnLength], rax
0x180006867  mov     r9, [rsp+208h+var_148]
0x18000686f  xor     r8d, r8d; pReturnValue
0x180006872  lea     edx, [r8+13h]; nProcNum
0x180006876  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000687d  call    cs:__imp_NdrClientCall3
0x180006883  mov     rbx, rax
0x180006886  mov     [rsp+208h+var_F0], rax
0x18000688e  mov     [rsp+208h+var_174], ebx
0x180006895  cmp     [rsp+208h+var_140.UserFunction], 0
0x18000689d  jz      loc_18000694E
0x1800068a3  mov     ecx, 80000000h
0x1800068a8  add     eax, ecx
0x1800068aa  test    ecx, eax
0x1800068ac  jnz     short loc_1800068BA
0x1800068ae  cmp     ebx, 80090301h
0x1800068b4  jnz     loc_18000694E
0x1800068ba  lea     rcx, [rsp+208h+var_D8]; struct _SECPKG_APP_MODE_INFO *
0x1800068c2  call    ?CleanupAppModeInfo@@YAXPEAU_SECPKG_APP_MODE_INFO@@@Z; CleanupAppModeInfo(_SECPKG_APP_MODE_INFO *)
0x1800068c7  mov     ecx, [rsp+208h+var_140.UserFunction]
0x1800068ce  lea     rax, [rsp+208h+var_D8.UserData]
0x1800068d6  mov     [rsp+208h+ReturnLength], rax
0x1800068db  lea     r9, [rsp+208h+var_140.UserData]
0x1800068e3  mov     r8, [rsp+208h+var_140.Argument2]
0x1800068eb  mov     rdx, [rsp+208h+var_140.Argument1]
0x1800068f3  call    LsaCallbackHandler
0x1800068f8  mov     ebx, eax
0x1800068fa  test    eax, eax
0x1800068fc  js      short loc_18000694E
0x1800068fe  cmp     [rsp+208h+var_140.ReturnToLsa], 0
0x180006906  jz      short loc_18000694E
0x180006908  mov     eax, [rsp+208h+var_140.UserFunction]
0x18000690f  mov     [rsp+208h+var_D8.UserFunction], eax
0x180006916  mov     rax, [rsp+208h+var_140.Argument1]
0x18000691e  mov     [rsp+208h+var_D8.Argument1], rax
0x180006926  mov     rax, [rsp+208h+var_140.Argument2]
0x18000692e  mov     [rsp+208h+var_D8.Argument2], rax
0x180006936  mov     [rsp+208h+var_D8.ReturnToLsa], 0
0x18000693e  mov     r14b, 1
0x180006941  lea     rcx, [rsp+208h+var_140]; struct _SECPKG_APP_MODE_INFO *
0x180006949  call    ?CleanupAppModeInfo@@YAXPEAU_SECPKG_APP_MODE_INFO@@@Z; CleanupAppModeInfo(_SECPKG_APP_MODE_INFO *)
0x18000694e  test    r14b, r14b
0x180006951  jnz     loc_180006790
0x180006957  jmp     short loc_180006975
0x180006959  mov     ecx, eax; Status
0x18000695b  call    cs:__imp_I_RpcMapWin32Status
0x180006961  mov     ebx, eax
0x180006963  mov     [rsp+208h+var_174], eax
0x18000696a  mov     r15, [rsp+208h+var_E8]
0x180006972  mov     r13, r15
0x180006975  test    ebx, ebx
0x180006977  js      short loc_180006992
0x180006979  mov     rax, [rsp+208h+var_68]
0x180006981  mov     [r15], rax
0x180006984  mov     rax, [rsp+208h+var_60]
0x18000698c  mov     [r13+8], rax
0x180006990  xor     ebx, ebx
0x180006992  lea     rcx, [rsp+208h+var_D8]; struct _SECPKG_APP_MODE_INFO *
0x18000699a  call    ?CleanupAppModeInfo@@YAXPEAU_SECPKG_APP_MODE_INFO@@@Z; CleanupAppModeInfo(_SECPKG_APP_MODE_INFO *)
0x18000699f  lea     rcx, [rsp+208h+var_140]; struct _SECPKG_APP_MODE_INFO *
0x1800069a7  call    ?CleanupAppModeInfo@@YAXPEAU_SECPKG_APP_MODE_INFO@@@Z; CleanupAppModeInfo(_SECPKG_APP_MODE_INFO *)
0x1800069ac  mov     eax, ebx
0x1800069ae  mov     rcx, [rsp+208h+var_48]
0x1800069b6  xor     rcx, rsp; StackCookie
0x1800069b9  call    __security_check_cookie
0x1800069be  add     rsp, 1D8h
0x1800069c5  pop     r15
0x1800069c7  pop     r14
0x1800069c9  pop     r13
0x1800069cb  pop     r12
0x1800069cd  pop     rsi
0x1800069ce  pop     rbx
0x1800069cf  retn
0x1800222c8  push    rbp
0x1800222ca  sub     rsp, 90h
0x1800222d1  mov     rbp, rdx
0x1800222d4  mov     rcx, [rcx]
0x1800222d7  mov     ecx, [rcx]; ExceptionCode
0x1800222d9  call    cs:__imp_I_RpcExceptionFilter
0x1800222df  nop
0x1800222e0  add     rsp, 90h
0x1800222e7  pop     rbp
0x1800222e8  retn
```
