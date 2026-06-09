# SspipFreeCredentialsHandle

- ea: `0x18000765c`
- end: `0x18000788e`
- name: `SspipFreeCredentialsHandle`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180007610`

## callees

- `0x18000765c`
- `0x1800084b0`
- `0x18000c460`
- `0x18000e890`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180007735`
- `ntdll!NtQueryInformationThread` at `0x180007735`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800222fe`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800222fe`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000781f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000781f`
- `RPCRT4!NdrClientCall3` at `0x180007809`
- `RPCRT4!NdrClientCall3` at `0x180007809`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007879`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007879`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800077b6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800077b6`

## pseudocode

```c
int __fastcall SspipFreeCredentialsHandle(_QWORD *a1)
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
                                                                                                + 16))(
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
                         0x14u,
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
0x18000765c  mov     r11, rsp
0x18000765f  mov     [r11+10h], rbx
0x180007663  push    rsi
0x180007664  sub     rsp, 0F0h
0x18000766b  mov     rax, cs:__security_cookie
0x180007672  xor     rax, rsp
0x180007675  mov     [rsp+0F8h+var_10], rax
0x18000767d  mov     rsi, rcx
0x180007680  mov     [rsp+0F8h+var_B0], 0
0x180007689  xorps   xmm0, xmm0
0x18000768c  movups  xmmword ptr [r11-30h], xmm0
0x180007691  xorps   xmm1, xmm1
0x180007694  movups  xmmword ptr [r11-40h], xmm1
0x180007699  movups  xmmword ptr [rsp+0F8h+var_A0.UserFunction], xmm0
0x18000769e  movups  xmmword ptr [rsp+0F8h+var_A0.Argument2], xmm0
0x1800076a3  movups  xmmword ptr [rsp+0F8h+var_A0.UserData.pvBuffer], xmm0
0x1800076a8  cmp     qword ptr [rcx], 0
0x1800076ac  jnz     short loc_1800076D8
0x1800076ae  cmp     qword ptr [rcx+8], 0
0x1800076b3  jnz     short loc_1800076D8
0x1800076b5  xor     eax, eax
0x1800076b7  mov     rcx, [rsp+0F8h+var_10]
0x1800076bf  xor     rcx, rsp; StackCookie
0x1800076c2  call    __security_check_cookie
0x1800076c7  mov     rbx, [rsp+0F8h+arg_8]
0x1800076cf  add     rsp, 0F0h
0x1800076d6  pop     rsi
0x1800076d7  retn
0x1800076d8  lea     rcx, [rsp+0F8h+var_B0]
0x1800076dd  call    IsOkayToExecRpc
0x1800076e2  test    eax, eax
0x1800076e4  js      short loc_1800076B7
0x1800076e6  mov     rax, [rsi]
0x1800076e9  mov     [rsp+0F8h+var_40], rax
0x1800076f1  mov     rax, [rsi+8]
0x1800076f5  mov     [rsp+0F8h+var_38], rax
0x1800076fd  xorps   xmm0, xmm0
0x180007700  movups  [rsp+0F8h+ThreadInformation], xmm0
0x180007708  movups  [rsp+0F8h+var_60], xmm0
0x180007710  movups  [rsp+0F8h+var_50], xmm0
0x180007718  mov     [rsp+0F8h+ReturnLength], 0; ReturnLength
0x180007721  mov     r9d, 30h ; '0'; ThreadInformationLength
0x180007727  lea     r8, [rsp+0F8h+ThreadInformation]; ThreadInformation
0x18000772f  xor     edx, edx; ThreadInformationClass
0x180007731  lea     rcx, [rdx-2]; ThreadHandle
0x180007735  call    cs:__imp_NtQueryInformationThread
0x18000773b  test    eax, eax
0x18000773d  js      loc_1800076B7
0x180007743  mov     rax, qword ptr [rsp+0F8h+var_60]
0x18000774b  mov     qword ptr [rsp+0F8h+var_30], rax
0x180007753  mov     rax, qword ptr [rsp+0F8h+var_60+8]
0x18000775b  mov     qword ptr [rsp+0F8h+var_30+8], rax
0x180007763  xor     eax, eax
0x180007765  test    eax, eax
0x180007767  js      loc_1800076B7
0x18000776d  mov     rax, cs:SecpLsaInprocDispatch
0x180007774  test    rax, rax
0x180007777  jz      short loc_18000779E
0x180007779  xor     r9d, r9d
0x18000777c  lea     r8, [rsp+0F8h+var_40]
0x180007784  lea     rdx, [rsp+0F8h+var_30]
0x18000778c  xor     ecx, ecx
0x18000778e  mov     rax, [rax+10h]
0x180007792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007797  mov     ebx, eax
0x180007799  jmp     loc_18000783B
0x18000779e  xorps   xmm0, xmm0
0x1800077a1  movups  xmmword ptr [rsp+0F8h+ActivityId.Data1], xmm0
0x1800077a9  lea     rdx, [rsp+0F8h+ActivityId]; ActivityId
0x1800077b1  mov     ecx, 1; ControlCode
0x1800077b6  call    cs:__imp_EventActivityIdControl
0x1800077bc  mov     [rsp+0F8h+var_A8], 0
0x1800077c5  lea     rax, [rsp+0F8h+var_A0]
0x1800077ca  mov     [rsp+0F8h+var_C0], rax
0x1800077cf  lea     rax, [rsp+0F8h+var_40]
0x1800077d7  mov     [rsp+0F8h+var_C8], rax
0x1800077dc  lea     rax, [rsp+0F8h+var_30]
0x1800077e4  mov     [rsp+0F8h+var_D0], rax
0x1800077e9  lea     rax, [rsp+0F8h+ActivityId]
0x1800077f1  mov     [rsp+0F8h+ReturnLength], rax
0x1800077f6  mov     r9, [rsp+0F8h+var_B0]
0x1800077fb  xor     r8d, r8d; pReturnValue
0x1800077fe  lea     edx, [r8+14h]; nProcNum
0x180007802  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180007809  call    cs:__imp_NdrClientCall3
0x18000780f  mov     rbx, rax
0x180007812  mov     [rsp+0F8h+var_A8], rax
0x180007817  mov     [rsp+0F8h+var_B8], eax
0x18000781b  jmp     short loc_18000782B
0x18000781d  mov     ecx, eax; Status
0x18000781f  call    cs:__imp_I_RpcMapWin32Status
0x180007825  mov     ebx, eax
0x180007827  mov     [rsp+0F8h+var_B8], eax
0x18000782b  cmp     ebx, 0C0000017h
0x180007831  jz      short loc_180007874
0x180007833  cmp     ebx, 0C000009Ah
0x180007839  jz      short loc_180007874
0x18000783b  cmp     [rsp+0F8h+var_A0.UserFunction], 0
0x180007840  jz      short loc_180007863
0x180007842  mov     ecx, [rsp+0F8h+var_A0.UserFunction]
0x180007846  mov     [rsp+0F8h+ReturnLength], 0
0x18000784f  lea     r9, [rsp+0F8h+var_A0.UserData]
0x180007854  mov     r8, [rsp+0F8h+var_A0.Argument2]
0x180007859  mov     rdx, [rsp+0F8h+var_A0.Argument1]
0x18000785e  call    LsaCallbackHandler
0x180007863  lea     rcx, [rsp+0F8h+var_A0]; struct _SECPKG_APP_MODE_INFO *
0x180007868  call    ?CleanupAppModeInfo@@YAXPEAU_SECPKG_APP_MODE_INFO@@@Z; CleanupAppModeInfo(_SECPKG_APP_MODE_INFO *)
0x18000786d  mov     eax, ebx
0x18000786f  jmp     loc_1800076B7
0x180007874  mov     ecx, 7Dh ; '}'; dwMilliseconds
0x180007879  call    cs:__imp_Sleep
0x18000787f  lea     rcx, [rsp+0F8h+var_A0]; struct _SECPKG_APP_MODE_INFO *
0x180007884  call    ?CleanupAppModeInfo@@YAXPEAU_SECPKG_APP_MODE_INFO@@@Z; CleanupAppModeInfo(_SECPKG_APP_MODE_INFO *)
0x180007889  jmp     loc_18000779E
0x1800222f0  push    rbp
0x1800222f2  sub     rsp, 40h
0x1800222f6  mov     rbp, rdx
0x1800222f9  mov     rcx, [rcx]
0x1800222fc  mov     ecx, [rcx]; ExceptionCode
0x1800222fe  call    cs:__imp_I_RpcExceptionFilter
0x180022304  nop
0x180022305  add     rsp, 40h
0x180022309  pop     rbp
0x18002230a  retn
```
