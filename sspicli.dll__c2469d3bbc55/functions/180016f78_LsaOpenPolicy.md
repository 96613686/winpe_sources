# LsaOpenPolicy

- ea: `0x180016f78`
- end: `0x180017122`
- name: `LsaOpenPolicy`
- size: `426`
- prototype: `NTSTATUS __stdcall(PLSA_UNICODE_STRING SystemName, PLSA_OBJECT_ATTRIBUTES ObjectAttributes, ACCESS_MASK DesiredAccess, PLSA_HANDLE PolicyHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000f1a0`

## callees

- `0x180014808`
- `0x18001491c`
- `0x180016afc`
- `0x180016f78`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x1800224c6`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800224e2`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800224c6`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800224e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x180017055`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800170d2`
- `RPCRT4!I_RpcMapWin32Status` at `0x180017055`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800170d2`
- `RPCRT4!NdrClientCall3` at `0x1800170b9`
- `RPCRT4!NdrClientCall3` at `0x1800170b9`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
NTSTATUS __stdcall LsaOpenPolicy(
        PLSA_UNICODE_STRING SystemName,
        PLSA_OBJECT_ATTRIBUTES ObjectAttributes,
        ACCESS_MASK DesiredAccess,
        PLSA_HANDLE PolicyHandle)
{
  CLIENT_CALL_RETURN v6; // rdi
  int v7; // r9d
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v11; // [rsp+28h] [rbp-60h]
  __int64 v12; // [rsp+48h] [rbp-40h] BYREF
  __int64 v13; // [rsp+50h] [rbp-38h] BYREF
  __int64 v14; // [rsp+58h] [rbp-30h]
  __int64 v15; // [rsp+90h] [rbp+8h] BYREF
  PLSA_OBJECT_ATTRIBUTES Simple; // [rsp+98h] [rbp+10h]
  int v17; // [rsp+A0h] [rbp+18h] BYREF
  PLSA_HANDLE v18; // [rsp+A8h] [rbp+20h]

  v18 = PolicyHandle;
  Simple = ObjectAttributes;
  v15 = 0;
  v17 = 0;
  v12 = 1;
  v13 = 0;
  v14 = 0;
  *PolicyHandle = 0;
  if ( !ObjectAttributes )
  {
    LODWORD(v6.Pointer) = -1073741811;
    goto LABEL_10;
  }
  ObjectAttributes->RootDirectory = 0;
  LODWORD(v6.Pointer) = LsapCreatePrivateHandleFromString(SystemName, &v15, DesiredAccess);
  if ( SLODWORD(v6.Simple) >= 0 )
  {
    v8 = v15;
    LODWORD(v6.Pointer) = LsarOpenPolicy3(
                            *(_QWORD *)(v15 + 16),
                            (_DWORD)ObjectAttributes,
                            DesiredAccess,
                            v7,
                            (__int64)&v12,
                            (__int64)&v17,
                            (__int64)&v13,
                            v15 + 8);
    v9 = 0;
    if ( SLODWORD(v6.Simple) >= 0 )
      v9 = v13;
    v14 = v9;
    if ( SLODWORD(v6.Simple) < 0 )
    {
      Simple = 0;
      LODWORD(v11) = 1;
      v6.Pointer = NdrClientCall3(
                     (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                     0x2Cu,
                     0,
                     *(_QWORD *)(v8 + 16),
                     ObjectAttributes,
                     v11,
                     v8 + 8).Pointer;
      Simple = (PLSA_OBJECT_ATTRIBUTES)v6.Simple;
      if ( SLODWORD(v6.Simple) < 0 )
        goto LABEL_10;
    }
    *(_DWORD *)(v8 + 48) = HIDWORD(v14);
    *PolicyHandle = (PVOID)v8;
  }
  if ( SLODWORD(v6.Simple) < 0 )
LABEL_10:
    LsapFreePrivateHandle(&v15, ObjectAttributes, *(_QWORD *)&DesiredAccess);
  return (NTSTATUS)v6.Pointer;
}

```

## disassembly

```asm
0x180016f78  mov     rax, rsp
0x180016f7b  mov     [rax+20h], r9
0x180016f7f  mov     [rax+18h], r8d
0x180016f83  mov     [rax+10h], rdx
0x180016f87  mov     [rax+8], rcx
0x180016f8b  push    rsi
0x180016f8c  push    rdi
0x180016f8d  push    r14
0x180016f8f  push    r15
0x180016f91  sub     rsp, 68h
0x180016f95  mov     r15, r9
0x180016f98  mov     r14, rdx
0x180016f9b  mov     qword ptr [rax+8], 0
0x180016fa3  mov     dword ptr [rax+18h], 0
0x180016faa  mov     qword ptr [rax-40h], 0
0x180016fb2  mov     qword ptr [rax-38h], 0
0x180016fba  mov     qword ptr [rax-30h], 0
0x180016fc2  mov     dword ptr [rax-40h], 1
0x180016fc9  mov     qword ptr [r9], 0
0x180016fd0  test    rdx, rdx
0x180016fd3  jnz     short loc_180016FDF
0x180016fd5  mov     edi, 0C000000Dh
0x180016fda  jmp     loc_180017108
0x180016fdf  mov     qword ptr [rdx+8], 0
0x180016fe7  lea     rdx, [rsp+88h+arg_0]
0x180016fef  call    LsapCreatePrivateHandleFromString
0x180016ff4  mov     edi, eax
0x180016ff6  test    eax, eax
0x180016ff8  js      loc_180017104
0x180016ffe  mov     rsi, [rsp+88h+arg_0]
0x180017006  lea     rax, [rsi+8]
0x18001700a  mov     [rsp+88h+var_50], rax
0x18001700f  lea     rax, [rsp+88h+var_38]
0x180017014  mov     [rsp+88h+var_58], rax
0x180017019  lea     rax, [rsp+88h+arg_10]
0x180017021  mov     [rsp+88h+var_60], rax
0x180017026  lea     rax, [rsp+88h+var_40]
0x18001702b  mov     [rsp+88h+var_68], rax
0x180017030  mov     rdx, r14
0x180017033  mov     rcx, [rsi+10h]
0x180017037  call    LsarOpenPolicy3
0x18001703c  mov     edi, eax
0x18001703e  mov     [rsp+88h+var_48], eax
0x180017042  xor     eax, eax
0x180017044  test    edi, edi
0x180017046  cmovns  rax, [rsp+88h+var_38]
0x18001704c  mov     [rsp+88h+var_30], rax
0x180017051  jmp     short loc_180017081
0x180017053  mov     ecx, eax; Status
0x180017055  call    cs:__imp_I_RpcMapWin32Status
0x18001705b  mov     edi, 0C0000001h
0x180017060  test    eax, eax
0x180017062  cmovs   edi, eax
0x180017065  mov     [rsp+88h+var_48], edi
0x180017069  mov     r15, [rsp+88h+arg_18]
0x180017071  mov     r14, [rsp+88h+arg_8]
0x180017079  mov     rsi, [rsp+88h+arg_0]
0x180017081  test    edi, edi
0x180017083  jns     short loc_1800170FA
0x180017085  lea     rax, [rsi+8]
0x180017089  mov     [rsp+88h+arg_8], 0
0x180017095  mov     [rsp+88h+var_58], rax
0x18001709a  mov     dword ptr [rsp+88h+var_60], 1
0x1800170a2  mov     [rsp+88h+var_68], r14
0x1800170a7  mov     r9, [rsi+10h]
0x1800170ab  xor     r8d, r8d; pReturnValue
0x1800170ae  lea     edx, [r8+2Ch]; nProcNum
0x1800170b2  lea     rcx, pProxyInfo; pProxyInfo
0x1800170b9  call    cs:__imp_NdrClientCall3
0x1800170bf  mov     rdi, rax
0x1800170c2  mov     [rsp+88h+arg_8], rax
0x1800170ca  mov     [rsp+88h+var_48], eax
0x1800170ce  jmp     short loc_1800170F6
0x1800170d0  mov     ecx, eax; Status
0x1800170d2  call    cs:__imp_I_RpcMapWin32Status
0x1800170d8  mov     edi, 0C0000001h
0x1800170dd  test    eax, eax
0x1800170df  cmovs   edi, eax
0x1800170e2  mov     [rsp+88h+var_48], edi
0x1800170e6  mov     r15, [rsp+88h+arg_18]
0x1800170ee  mov     rsi, [rsp+88h+arg_0]
0x1800170f6  test    edi, edi
0x1800170f8  js      short loc_180017108
0x1800170fa  mov     eax, dword ptr [rsp+88h+var_30+4]
0x1800170fe  mov     [rsi+30h], eax
0x180017101  mov     [r15], rsi
0x180017104  test    edi, edi
0x180017106  jns     short loc_180017115
0x180017108  lea     rcx, [rsp+88h+arg_0]
0x180017110  call    LsapFreePrivateHandle
0x180017115  mov     eax, edi
0x180017117  add     rsp, 68h
0x18001711b  pop     r15
0x18001711d  pop     r14
0x18001711f  pop     rdi
0x180017120  pop     rsi
0x180017121  retn
0x1800224b8  push    rbp
0x1800224ba  sub     rsp, 40h
0x1800224be  mov     rbp, rdx
0x1800224c1  mov     rcx, [rcx]
0x1800224c4  mov     ecx, [rcx]; ExceptionCode
0x1800224c6  call    cs:__imp_I_RpcExceptionFilter
0x1800224cc  nop
0x1800224cd  add     rsp, 40h
0x1800224d1  pop     rbp
0x1800224d2  retn
0x1800224d4  push    rbp
0x1800224d6  sub     rsp, 40h
0x1800224da  mov     rbp, rdx
0x1800224dd  mov     rcx, [rcx]
0x1800224e0  mov     ecx, [rcx]; ExceptionCode
0x1800224e2  call    cs:__imp_I_RpcExceptionFilter
0x1800224e8  nop
0x1800224e9  add     rsp, 40h
0x1800224ed  pop     rbp
0x1800224ee  retn
```
