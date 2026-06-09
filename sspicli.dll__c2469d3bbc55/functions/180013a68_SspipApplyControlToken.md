# SspipApplyControlToken

- ea: `0x180013a68`
- end: `0x180013be1`
- name: `SspipApplyControlToken`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180013a10`

## callees

- `0x1800084b0`
- `0x180013a68`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180013ae4`
- `ntdll!NtQueryInformationThread` at `0x180013ae4`
- `RPCRT4!I_RpcExceptionFilter` at `0x180022482`
- `RPCRT4!I_RpcExceptionFilter` at `0x180022482`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013bbe`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013bbe`
- `RPCRT4!NdrClientCall3` at `0x180013bab`
- `RPCRT4!NdrClientCall3` at `0x180013bab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013b5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013b5d`

## pseudocode

```c
int __fastcall SspipApplyControlToken(_QWORD *a1, __int64 a2)
{
  int result; // eax
  _QWORD v4[2]; // [rsp+48h] [rbp-80h] BYREF
  __int128 ThreadInformation; // [rsp+58h] [rbp-70h] BYREF
  __int128 v6; // [rsp+68h] [rbp-60h]
  __int128 v7; // [rsp+78h] [rbp-50h]
  __int128 v8; // [rsp+88h] [rbp-40h] BYREF
  _QWORD v9[2]; // [rsp+98h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+A8h] [rbp-20h] BYREF

  v4[0] = 0;
  v8 = 0;
  v9[0] = *a1;
  v9[1] = a1[1];
  result = IsOkayToExecRpc(v4);
  if ( result >= 0 )
  {
    ThreadInformation = 0;
    v6 = 0;
    v7 = 0;
    result = NtQueryInformationThread(
               (HANDLE)0xFFFFFFFFFFFFFFFELL,
               ThreadBasicInformation,
               &ThreadInformation,
               0x30u,
               0);
    if ( result >= 0 )
    {
      v8 = v6;
      if ( SecpLsaInprocDispatch )
      {
        return (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD *, __int64))(SecpLsaInprocDispatch + 40))(
                 0,
                 &v8,
                 v9,
                 a2);
      }
      else
      {
        ActivityId = 0;
        EventActivityIdControl(1u, &ActivityId);
        v4[1] = 0;
        return (unsigned int)NdrClientCall3(
                               (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
                               0x17u,
                               0,
                               v4[0],
                               &ActivityId,
                               &v8,
                               v9,
                               a2).Pointer;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013a68  mov     r11, rsp
0x180013a6b  push    rbx
0x180013a6c  sub     rsp, 0C0h
0x180013a73  mov     rax, cs:__security_cookie
0x180013a7a  xor     rax, rsp
0x180013a7d  mov     [rsp+0C8h+var_10], rax
0x180013a85  mov     rbx, rdx
0x180013a88  mov     qword ptr [r11-80h], 0
0x180013a90  xorps   xmm0, xmm0
0x180013a93  movups  xmmword ptr [r11-40h], xmm0
0x180013a98  mov     rax, [rcx]
0x180013a9b  mov     [r11-30h], rax
0x180013a9f  mov     rax, [rcx+8]
0x180013aa3  mov     [r11-28h], rax
0x180013aa7  lea     rcx, [r11-80h]
0x180013aab  call    IsOkayToExecRpc
0x180013ab0  test    eax, eax
0x180013ab2  js      loc_180013BC8
0x180013ab8  xorps   xmm0, xmm0
0x180013abb  movups  [rsp+0C8h+ThreadInformation], xmm0
0x180013ac0  movups  [rsp+0C8h+var_60], xmm0
0x180013ac5  movups  [rsp+0C8h+var_50], xmm0
0x180013aca  mov     [rsp+0C8h+ReturnLength], 0; ReturnLength
0x180013ad3  mov     r9d, 30h ; '0'; ThreadInformationLength
0x180013ad9  lea     r8, [rsp+0C8h+ThreadInformation]; ThreadInformation
0x180013ade  xor     edx, edx; ThreadInformationClass
0x180013ae0  lea     rcx, [rdx-2]; ThreadHandle
0x180013ae4  call    cs:__imp_NtQueryInformationThread
0x180013aea  test    eax, eax
0x180013aec  js      loc_180013BC8
0x180013af2  mov     rax, qword ptr [rsp+0C8h+var_60]
0x180013af7  mov     qword ptr [rsp+0C8h+var_40], rax
0x180013aff  mov     rax, qword ptr [rsp+0C8h+var_60+8]
0x180013b04  mov     qword ptr [rsp+0C8h+var_40+8], rax
0x180013b0c  xor     eax, eax
0x180013b0e  test    eax, eax
0x180013b10  js      loc_180013BC8
0x180013b16  mov     rax, cs:SecpLsaInprocDispatch
0x180013b1d  test    rax, rax
0x180013b20  jz      short loc_180013B45
0x180013b22  mov     r9, rbx
0x180013b25  lea     r8, [rsp+0C8h+var_30]
0x180013b2d  lea     rdx, [rsp+0C8h+var_40]
0x180013b35  xor     ecx, ecx
0x180013b37  mov     rax, [rax+28h]
0x180013b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b40  jmp     loc_180013BC8
0x180013b45  xorps   xmm0, xmm0
0x180013b48  movups  xmmword ptr [rsp+0C8h+ActivityId.Data1], xmm0
0x180013b50  lea     rdx, [rsp+0C8h+ActivityId]; ActivityId
0x180013b58  mov     ecx, 1; ControlCode
0x180013b5d  call    cs:__imp_EventActivityIdControl
0x180013b63  mov     [rsp+0C8h+var_78], 0
0x180013b6c  mov     [rsp+0C8h+var_90], rbx
0x180013b71  lea     rax, [rsp+0C8h+var_30]
0x180013b79  mov     [rsp+0C8h+var_98], rax
0x180013b7e  lea     rax, [rsp+0C8h+var_40]
0x180013b86  mov     [rsp+0C8h+var_A0], rax
0x180013b8b  lea     rax, [rsp+0C8h+ActivityId]
0x180013b93  mov     [rsp+0C8h+ReturnLength], rax
0x180013b98  mov     r9, [rsp+0C8h+var_80]
0x180013b9d  xor     r8d, r8d; pReturnValue
0x180013ba0  lea     edx, [r8+17h]; nProcNum
0x180013ba4  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180013bab  call    cs:__imp_NdrClientCall3
0x180013bb1  mov     [rsp+0C8h+var_78], rax
0x180013bb6  mov     [rsp+0C8h+var_88], eax
0x180013bba  jmp     short loc_180013BC8
0x180013bbc  mov     ecx, eax; Status
0x180013bbe  call    cs:__imp_I_RpcMapWin32Status
0x180013bc4  mov     [rsp+0C8h+var_88], eax
0x180013bc8  mov     rcx, [rsp+0C8h+var_10]
0x180013bd0  xor     rcx, rsp; StackCookie
0x180013bd3  call    __security_check_cookie
0x180013bd8  add     rsp, 0C0h
0x180013bdf  pop     rbx
0x180013be0  retn
0x180022474  push    rbp
0x180022476  sub     rsp, 40h
0x18002247a  mov     rbp, rdx
0x18002247d  mov     rcx, [rcx]
0x180022480  mov     ecx, [rcx]; ExceptionCode
0x180022482  call    cs:__imp_I_RpcExceptionFilter
0x180022488  nop
0x180022489  add     rsp, 40h
0x18002248d  pop     rbp
0x18002248e  retn
```
