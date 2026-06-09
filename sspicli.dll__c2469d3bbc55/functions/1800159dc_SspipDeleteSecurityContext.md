# SspipDeleteSecurityContext

- ea: `0x1800159dc`
- end: `0x180015c0e`
- name: `SspipDeleteSecurityContext`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005370`

## callees

- `0x1800084b0`
- `0x18000c460`
- `0x18000e890`
- `0x1800159dc`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180015ab5`
- `ntdll!NtQueryInformationThread` at `0x180015ab5`
- `RPCRT4!I_RpcExceptionFilter` at `0x180022504`
- `RPCRT4!I_RpcExceptionFilter` at `0x180022504`
- `RPCRT4!I_RpcMapWin32Status` at `0x180015b9f`
- `RPCRT4!I_RpcMapWin32Status` at `0x180015b9f`
- `RPCRT4!NdrClientCall3` at `0x180015b89`
- `RPCRT4!NdrClientCall3` at `0x180015b89`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015bf9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015bf9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015b36`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015b36`

## pseudocode

```c
int __fastcall SspipDeleteSecurityContext(_QWORD *a1)
{
  int result; // eax
  CLIENT_CALL_RETURN v3; // rbx
  __int64 v4; // [rsp+48h] [rbp-B0h] BYREF
  CLIENT_CALL_RETURN v5; // [rsp+50h] [rbp-A8h]
  struct _SECPKG_APP_MODE_INFO v6; // [rsp+58h] [rbp-A0h] BYREF
  __int128 ThreadInformation; // [rsp+88h] [rbp-70h] BYREF
  __int128 v8; // [rsp+98h] [rbp-60h]
  __int128 v9; // [rsp+A8h] [rbp-50h]
  __int128 v10; // [rsp+B8h] [rbp-40h] BYREF
  __int128 v11; // [rsp+C8h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+D8h] [rbp-20h] BYREF

  v4 = 0;
  v11 = 0;
  v10 = 0;
  memset(&v6, 0, sizeof(v6));
  if ( !*a1 && !a1[1] )
    return 0;
  result = IsOkayToExecRpc(&v4);
  if ( result >= 0 )
  {
    v10 = *(_OWORD *)a1;
    ThreadInformation = 0;
    v8 = 0;
    v9 = 0;
    result = NtQueryInformationThread(
               (HANDLE)0xFFFFFFFFFFFFFFFELL,
               ThreadBasicInformation,
               &ThreadInformation,
               0x30u,
               0);
    if ( result >= 0 )
    {
      v11 = v8;
      if ( SecpLsaInprocDispatch )
      {
        LODWORD(v3.Pointer) = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int128 *, _QWORD))(SecpLsaInprocDispatch
                                                                                                + 32))(
                                0,
                                &v11,
                                &v10,
                                0);
      }
      else
      {
        while ( 1 )
        {
          ActivityId = 0;
          EventActivityIdControl(1u, &ActivityId);
          v5.Simple = 0;
          v3.Pointer = NdrClientCall3(
                         (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
                         0x16u,
                         0,
                         v4,
                         &ActivityId,
                         &v11,
                         &v10,
                         &v6).Pointer;
          v5.Pointer = v3.Pointer;
          if ( LODWORD(v3.Pointer) != -1073741801 && LODWORD(v3.Pointer) != -1073741670 )
            break;
          Sleep(0x7Du);
          CleanupAppModeInfo(&v6);
        }
      }
      if ( v6.UserFunction )
        LsaCallbackHandler(v6.UserFunction, v6.Argument1, v6.Argument2, (unsigned int)&v6.UserData, 0);
      CleanupAppModeInfo(&v6);
      return (int)v3.Pointer;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800159dc  mov     r11, rsp
0x1800159df  mov     [r11+10h], rbx
0x1800159e3  push    rsi
0x1800159e4  sub     rsp, 0F0h
0x1800159eb  mov     rax, cs:__security_cookie
0x1800159f2  xor     rax, rsp
0x1800159f5  mov     [rsp+0F8h+var_10], rax
0x1800159fd  mov     rsi, rcx
0x180015a00  mov     [rsp+0F8h+var_B0], 0
0x180015a09  xorps   xmm0, xmm0
0x180015a0c  movups  xmmword ptr [r11-30h], xmm0
0x180015a11  xorps   xmm1, xmm1
0x180015a14  movups  xmmword ptr [r11-40h], xmm1
0x180015a19  movups  xmmword ptr [rsp+0F8h+var_A0.UserFunction], xmm0
0x180015a1e  movups  xmmword ptr [rsp+0F8h+var_A0.Argument2], xmm0
0x180015a23  movups  xmmword ptr [rsp+0F8h+var_A0.UserData.pvBuffer], xmm0
0x180015a28  cmp     qword ptr [rcx], 0
0x180015a2c  jnz     short loc_180015A58
0x180015a2e  cmp     qword ptr [rcx+8], 0
0x180015a33  jnz     short loc_180015A58
0x180015a35  xor     eax, eax
0x180015a37  mov     rcx, [rsp+0F8h+var_10]
0x180015a3f  xor     rcx, rsp; StackCookie
0x180015a42  call    __security_check_cookie
0x180015a47  mov     rbx, [rsp+0F8h+arg_8]
0x180015a4f  add     rsp, 0F0h
0x180015a56  pop     rsi
0x180015a57  retn
0x180015a58  lea     rcx, [rsp+0F8h+var_B0]
0x180015a5d  call    IsOkayToExecRpc
0x180015a62  test    eax, eax
0x180015a64  js      short loc_180015A37
0x180015a66  mov     rax, [rsi]
0x180015a69  mov     [rsp+0F8h+var_40], rax
0x180015a71  mov     rax, [rsi+8]
0x180015a75  mov     [rsp+0F8h+var_38], rax
0x180015a7d  xorps   xmm0, xmm0
0x180015a80  movups  [rsp+0F8h+ThreadInformation], xmm0
0x180015a88  movups  [rsp+0F8h+var_60], xmm0
0x180015a90  movups  [rsp+0F8h+var_50], xmm0
0x180015a98  mov     [rsp+0F8h+ReturnLength], 0; ReturnLength
0x180015aa1  mov     r9d, 30h ; '0'; ThreadInformationLength
0x180015aa7  lea     r8, [rsp+0F8h+ThreadInformation]; ThreadInformation
0x180015aaf  xor     edx, edx; ThreadInformationClass
0x180015ab1  lea     rcx, [rdx-2]; ThreadHandle
0x180015ab5  call    cs:__imp_NtQueryInformationThread
0x180015abb  test    eax, eax
0x180015abd  js      loc_180015A37
0x180015ac3  mov     rax, qword ptr [rsp+0F8h+var_60]
0x180015acb  mov     qword ptr [rsp+0F8h+var_30], rax
0x180015ad3  mov     rax, qword ptr [rsp+0F8h+var_60+8]
0x180015adb  mov     qword ptr [rsp+0F8h+var_30+8], rax
0x180015ae3  xor     eax, eax
0x180015ae5  test    eax, eax
0x180015ae7  js      loc_180015A37
0x180015aed  mov     rax, cs:SecpLsaInprocDispatch
0x180015af4  test    rax, rax
0x180015af7  jz      short loc_180015B1E
0x180015af9  xor     r9d, r9d
0x180015afc  lea     r8, [rsp+0F8h+var_40]
0x180015b04  lea     rdx, [rsp+0F8h+var_30]
0x180015b0c  xor     ecx, ecx
0x180015b0e  mov     rax, [rax+20h]
0x180015b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b17  mov     ebx, eax
0x180015b19  jmp     loc_180015BBB
0x180015b1e  xorps   xmm0, xmm0
0x180015b21  movups  xmmword ptr [rsp+0F8h+ActivityId.Data1], xmm0
0x180015b29  lea     rdx, [rsp+0F8h+ActivityId]; ActivityId
0x180015b31  mov     ecx, 1; ControlCode
0x180015b36  call    cs:__imp_EventActivityIdControl
0x180015b3c  mov     [rsp+0F8h+var_A8], 0
0x180015b45  lea     rax, [rsp+0F8h+var_A0]
0x180015b4a  mov     [rsp+0F8h+var_C0], rax
0x180015b4f  lea     rax, [rsp+0F8h+var_40]
0x180015b57  mov     [rsp+0F8h+var_C8], rax
0x180015b5c  lea     rax, [rsp+0F8h+var_30]
0x180015b64  mov     [rsp+0F8h+var_D0], rax
0x180015b69  lea     rax, [rsp+0F8h+ActivityId]
0x180015b71  mov     [rsp+0F8h+ReturnLength], rax
0x180015b76  mov     r9, [rsp+0F8h+var_B0]
0x180015b7b  xor     r8d, r8d; pReturnValue
0x180015b7e  lea     edx, [r8+16h]; nProcNum
0x180015b82  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180015b89  call    cs:__imp_NdrClientCall3
0x180015b8f  mov     rbx, rax
0x180015b92  mov     [rsp+0F8h+var_A8], rax
0x180015b97  mov     [rsp+0F8h+var_B8], eax
0x180015b9b  jmp     short loc_180015BAB
0x180015b9d  mov     ecx, eax; Status
0x180015b9f  call    cs:__imp_I_RpcMapWin32Status
0x180015ba5  mov     ebx, eax
0x180015ba7  mov     [rsp+0F8h+var_B8], eax
0x180015bab  cmp     ebx, 0C0000017h
0x180015bb1  jz      short loc_180015BF4
0x180015bb3  cmp     ebx, 0C000009Ah
0x180015bb9  jz      short loc_180015BF4
0x180015bbb  cmp     [rsp+0F8h+var_A0.UserFunction], 0
0x180015bc0  jz      short loc_180015BE3
0x180015bc2  mov     ecx, [rsp+0F8h+var_A0.UserFunction]
0x180015bc6  mov     [rsp+0F8h+ReturnLength], 0
0x180015bcf  lea     r9, [rsp+0F8h+var_A0.UserData]
0x180015bd4  mov     r8, [rsp+0F8h+var_A0.Argument2]
0x180015bd9  mov     rdx, [rsp+0F8h+var_A0.Argument1]
0x180015bde  call    LsaCallbackHandler
0x180015be3  lea     rcx, [rsp+0F8h+var_A0]; struct _SECPKG_APP_MODE_INFO *
0x180015be8  call    ?CleanupAppModeInfo@@YAXPEAU_SECPKG_APP_MODE_INFO@@@Z; CleanupAppModeInfo(_SECPKG_APP_MODE_INFO *)
0x180015bed  mov     eax, ebx
0x180015bef  jmp     loc_180015A37
0x180015bf4  mov     ecx, 7Dh ; '}'; dwMilliseconds
0x180015bf9  call    cs:__imp_Sleep
0x180015bff  lea     rcx, [rsp+0F8h+var_A0]; struct _SECPKG_APP_MODE_INFO *
0x180015c04  call    ?CleanupAppModeInfo@@YAXPEAU_SECPKG_APP_MODE_INFO@@@Z; CleanupAppModeInfo(_SECPKG_APP_MODE_INFO *)
0x180015c09  jmp     loc_180015B1E
0x1800224f6  push    rbp
0x1800224f8  sub     rsp, 40h
0x1800224fc  mov     rbp, rdx
0x1800224ff  mov     rcx, [rcx]
0x180022502  mov     ecx, [rcx]; ExceptionCode
0x180022504  call    cs:__imp_I_RpcExceptionFilter
0x18002250a  nop
0x18002250b  add     rsp, 40h
0x18002250f  pop     rbp
0x180022510  retn
```
