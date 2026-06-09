# SspipGetUserName

- ea: `0x18000a820`
- end: `0x18000aa91`
- name: `SspipGetUserName`
- size: `625`
- prototype: `__int64 __fastcall(unsigned int, struct _UNICODE_STRING *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a6e0`

## callees

- `0x1800084f0`
- `0x18000a820`
- `0x18001b020`
- `0x18001b048`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18000aa0b`
- `ntdll!RtlCopyUnicodeString` at `0x18000aa0b`
- `ntdll!NtQueryInformationThread` at `0x18000a8f4`
- `ntdll!NtQueryInformationThread` at `0x18000a8f4`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002237e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002237e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000a9ce`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000a9ce`
- `RPCRT4!NdrClientCall3` at `0x18000a9b8`
- `RPCRT4!NdrClientCall3` at `0x18000a9b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa3c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a96d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a96d`

## pseudocode

```c
__int64 __fastcall SspipGetUserName(unsigned int a1, struct _UNICODE_STRING *a2, _DWORD *a3)
{
  CLIENT_CALL_RETURN v3; // rbx
  NTSTATUS v7; // eax
  __int64 v8; // r12
  CLIENT_CALL_RETURN v10; // [rsp+50h] [rbp-C8h] BYREF
  int Pointer; // [rsp+58h] [rbp-C0h]
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-B8h] BYREF
  struct _UNICODE_STRING *v13; // [rsp+70h] [rbp-A8h]
  __int128 ThreadInformation; // [rsp+80h] [rbp-98h] BYREF
  __int128 v15; // [rsp+90h] [rbp-88h]
  __int128 v16; // [rsp+A0h] [rbp-78h]
  __int128 v17; // [rsp+B0h] [rbp-68h] BYREF
  GUID ActivityId; // [rsp+C0h] [rbp-58h] BYREF

  v3.Simple = (LONG_PTR)a3;
  v13 = a2;
  v17 = 0;
  SourceString = 0;
  *a3 = 0;
  v10.Simple = 0;
  v7 = IsOkayToExec(&v10);
  if ( v7 < 0 )
    goto LABEL_13;
  v8 = *(_QWORD *)(v10.Simple + 24);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_54021242344439e0b4b6b44468378b0e_Traceguids);
  ThreadInformation = 0;
  v15 = 0;
  v16 = 0;
  v7 = NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadBasicInformation, &ThreadInformation, 0x30u, 0);
  if ( v7 < 0 )
  {
LABEL_13:
    LODWORD(v3.Pointer) = v7;
  }
  else
  {
    v17 = v15;
    if ( SecpLsaInprocDispatch )
    {
      LODWORD(v3.Pointer) = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, UNICODE_STRING *, CLIENT_CALL_RETURN))(SecpLsaInprocDispatch + 56))(
                              0,
                              &v17,
                              a1,
                              &SourceString,
                              v3);
    }
    else
    {
      ActivityId = 0;
      EventActivityIdControl(1u, &ActivityId);
      v10.Simple = 0;
      v3.Pointer = NdrClientCall3(
                     (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
                     0x19u,
                     0,
                     v8,
                     &ActivityId,
                     &v17,
                     a1,
                     &SourceString,
                     v3.Simple).Pointer;
      v10.Pointer = v3.Pointer;
      Pointer = (int)v3.Pointer;
    }
    if ( SLODWORD(v3.Simple) >= 0 )
    {
      if ( a2->MaximumLength >= SourceString.Length )
      {
        RtlCopyUnicodeString(a2, &SourceString);
      }
      else
      {
        a2->Length = SourceString.Length;
        LODWORD(v3.Pointer) = -2147483643;
      }
    }
  }
  if ( SourceString.Buffer )
  {
    if ( SecpLsaInprocDispatch )
      (*(void (**)(void))SecpLsaInprocDispatch)();
    else
      LocalFree(SourceString.Buffer);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      &WPP_54021242344439e0b4b6b44468378b0e_Traceguids,
      LODWORD(v3.Pointer));
  return LODWORD(v3.Pointer);
}

```

## disassembly

```asm
0x18000a820  push    rbx
0x18000a822  push    rsi
0x18000a823  push    rdi
0x18000a824  push    r12
0x18000a826  push    r13
0x18000a828  push    r14
0x18000a82a  push    r15
0x18000a82c  sub     rsp, 0E0h
0x18000a833  mov     rax, cs:__security_cookie
0x18000a83a  xor     rax, rsp
0x18000a83d  mov     [rsp+118h+var_48], rax
0x18000a845  mov     rbx, r8
0x18000a848  mov     r14, rdx
0x18000a84b  mov     r15d, ecx
0x18000a84e  mov     rsi, rdx
0x18000a851  mov     [rsp+118h+var_A8], rdx
0x18000a856  xorps   xmm0, xmm0
0x18000a859  movups  [rsp+118h+var_68], xmm0
0x18000a861  xorps   xmm1, xmm1
0x18000a864  movups  xmmword ptr [rsp+118h+SourceString.Length], xmm1
0x18000a869  xor     r13d, r13d
0x18000a86c  mov     [r8], r13d
0x18000a86f  mov     [rsp+118h+var_C8], r13
0x18000a874  lea     rcx, [rsp+118h+var_C8]
0x18000a879  call    IsOkayToExec
0x18000a87e  test    eax, eax
0x18000a880  js      loc_18000AA13
0x18000a886  mov     rax, [rsp+118h+var_C8]
0x18000a88b  mov     r12, [rax+18h]
0x18000a88f  lea     rdi, WPP_GLOBAL_Control
0x18000a896  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a89d  cmp     rcx, rdi
0x18000a8a0  jz      short loc_18000A8BD
0x18000a8a2  test    byte ptr [rcx+1Ch], 4
0x18000a8a6  jz      short loc_18000A8BD
0x18000a8a8  mov     edx, 16h
0x18000a8ad  lea     r8, WPP_54021242344439e0b4b6b44468378b0e_Traceguids
0x18000a8b4  mov     rcx, [rcx+10h]
0x18000a8b8  call    WPP_SF_
0x18000a8bd  xorps   xmm0, xmm0
0x18000a8c0  movups  [rsp+118h+ThreadInformation], xmm0
0x18000a8c8  movups  [rsp+118h+var_88], xmm0
0x18000a8d0  movups  [rsp+118h+var_78], xmm0
0x18000a8d8  mov     [rsp+118h+ReturnLength], r13; ReturnLength
0x18000a8dd  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18000a8e3  lea     r8, [rsp+118h+ThreadInformation]; ThreadInformation
0x18000a8eb  xor     edx, edx; ThreadInformationClass
0x18000a8ed  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000a8f4  call    cs:__imp_NtQueryInformationThread
0x18000a8fa  test    eax, eax
0x18000a8fc  js      loc_18000AA1A
0x18000a902  mov     rax, qword ptr [rsp+118h+var_88]
0x18000a90a  mov     qword ptr [rsp+118h+var_68], rax
0x18000a912  mov     rax, qword ptr [rsp+118h+var_88+8]
0x18000a91a  mov     qword ptr [rsp+118h+var_68+8], rax
0x18000a922  mov     rax, cs:SecpLsaInprocDispatch
0x18000a929  test    rax, rax
0x18000a92c  jz      short loc_18000A955
0x18000a92e  mov     [rsp+118h+ReturnLength], rbx
0x18000a933  lea     r9, [rsp+118h+SourceString]
0x18000a938  mov     r8d, r15d
0x18000a93b  lea     rdx, [rsp+118h+var_68]
0x18000a943  xor     ecx, ecx
0x18000a945  mov     rax, [rax+38h]
0x18000a949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a94e  mov     ebx, eax
0x18000a950  jmp     loc_18000A9E9
0x18000a955  xorps   xmm0, xmm0
0x18000a958  movups  xmmword ptr [rsp+118h+ActivityId.Data1], xmm0
0x18000a960  lea     rdx, [rsp+118h+ActivityId]; ActivityId
0x18000a968  mov     ecx, 1; ControlCode
0x18000a96d  call    cs:__imp_EventActivityIdControl
0x18000a973  mov     [rsp+118h+var_C8], r13
0x18000a978  mov     [rsp+118h+var_D8], rbx
0x18000a97d  lea     rax, [rsp+118h+SourceString]
0x18000a982  mov     [rsp+118h+var_E0], rax
0x18000a987  mov     [rsp+118h+var_E8], r15d
0x18000a98c  lea     rax, [rsp+118h+var_68]
0x18000a994  mov     [rsp+118h+var_F0], rax
0x18000a999  lea     rax, [rsp+118h+ActivityId]
0x18000a9a1  mov     [rsp+118h+ReturnLength], rax
0x18000a9a6  mov     r9, r12
0x18000a9a9  xor     r8d, r8d; pReturnValue
0x18000a9ac  mov     edx, 19h; nProcNum
0x18000a9b1  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000a9b8  call    cs:__imp_NdrClientCall3
0x18000a9be  mov     rbx, rax
0x18000a9c1  mov     [rsp+118h+var_C8], rax
0x18000a9c6  mov     [rsp+118h+var_C0], eax
0x18000a9ca  jmp     short loc_18000A9E9
0x18000a9cc  mov     ecx, eax; Status
0x18000a9ce  call    cs:__imp_I_RpcMapWin32Status
0x18000a9d4  mov     ebx, eax
0x18000a9d6  mov     [rsp+118h+var_C0], eax
0x18000a9da  lea     rdi, WPP_GLOBAL_Control
0x18000a9e1  mov     rsi, [rsp+118h+var_A8]
0x18000a9e6  mov     r14, rsi
0x18000a9e9  test    ebx, ebx
0x18000a9eb  js      short loc_18000AA1C
0x18000a9ed  movzx   eax, [rsp+118h+SourceString.Length]
0x18000a9f2  cmp     [rsi+2], ax
0x18000a9f6  jnb     short loc_18000AA03
0x18000a9f8  mov     [r14], ax
0x18000a9fc  mov     ebx, 80000005h
0x18000aa01  jmp     short loc_18000AA1C
0x18000aa03  lea     rdx, [rsp+118h+SourceString]; SourceString
0x18000aa08  mov     rcx, rsi; DestinationString
0x18000aa0b  call    cs:__imp_RtlCopyUnicodeString
0x18000aa11  jmp     short loc_18000AA1C
0x18000aa13  lea     rdi, WPP_GLOBAL_Control
0x18000aa1a  mov     ebx, eax
0x18000aa1c  mov     rcx, [rsp+118h+SourceString.Buffer]; hMem
0x18000aa21  test    rcx, rcx
0x18000aa24  jz      short loc_18000AA42
0x18000aa26  mov     rax, cs:SecpLsaInprocDispatch
0x18000aa2d  test    rax, rax
0x18000aa30  jz      short loc_18000AA3C
0x18000aa32  mov     rax, [rax]
0x18000aa35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa3a  jmp     short loc_18000AA42
0x18000aa3c  call    cs:__imp_LocalFree
0x18000aa42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa49  cmp     rcx, rdi
0x18000aa4c  jz      short loc_18000AA6C
0x18000aa4e  test    byte ptr [rcx+1Ch], 4
0x18000aa52  jz      short loc_18000AA6C
0x18000aa54  mov     edx, 17h
0x18000aa59  mov     r9d, ebx
0x18000aa5c  lea     r8, WPP_54021242344439e0b4b6b44468378b0e_Traceguids
0x18000aa63  mov     rcx, [rcx+10h]
0x18000aa67  call    WPP_SF_D
0x18000aa6c  mov     eax, ebx
0x18000aa6e  mov     rcx, [rsp+118h+var_48]
0x18000aa76  xor     rcx, rsp; StackCookie
0x18000aa79  call    __security_check_cookie
0x18000aa7e  add     rsp, 0E0h
0x18000aa85  pop     r15
0x18000aa87  pop     r14
0x18000aa89  pop     r13
0x18000aa8b  pop     r12
0x18000aa8d  pop     rdi
0x18000aa8e  pop     rsi
0x18000aa8f  pop     rbx
0x18000aa90  retn
0x180022370  push    rbp
0x180022372  sub     rsp, 50h
0x180022376  mov     rbp, rdx
0x180022379  mov     rcx, [rcx]
0x18002237c  mov     ecx, [rcx]; ExceptionCode
0x18002237e  call    cs:__imp_I_RpcExceptionFilter
0x180022384  nop
0x180022385  add     rsp, 50h
0x180022389  pop     rbp
0x18002238a  retn
```
