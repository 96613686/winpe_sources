# NetrServerStatisticsGet

- ea: `0x180011830`
- end: `0x1800119d3`
- name: `NetrServerStatisticsGet`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b4c0`
- `0x180011830`
- `0x180028c24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001193c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001193c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119c6`
- `ntdll!RtlInitUnicodeString` at `0x180011895`
- `ntdll!RtlInitUnicodeString` at `0x1800118a2`
- `ntdll!RtlInitUnicodeString` at `0x1800118b3`
- `ntdll!RtlInitUnicodeString` at `0x180011895`
- `ntdll!RtlInitUnicodeString` at `0x1800118a2`
- `ntdll!RtlInitUnicodeString` at `0x1800118b3`
- `ntdll!RtlAdjustPrivilege` at `0x1800118c6`
- `ntdll!RtlAdjustPrivilege` at `0x1800118c6`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18001191c`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18001191c`
- `RPCRT4!RpcImpersonateClient` at `0x1800118ce`
- `RPCRT4!RpcImpersonateClient` at `0x1800118ce`
- `RPCRT4!RpcRevertToSelf` at `0x180011924`
- `RPCRT4!RpcRevertToSelf` at `0x180011924`

## pseudocode

```c
__int64 __fastcall NetrServerStatisticsGet(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  struct _GENERIC_MAPPING *GenericMapping; // rdi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // rsi
  const WCHAR *v7; // rbx
  RPC_STATUS v8; // eax
  int v9; // r8d
  NTSTATUS v10; // ebx
  HLOCAL v11; // rax
  __int64 v12; // rcx
  void *v13; // rdi
  unsigned int Info; // ebx
  unsigned __int8 GenerateOnClose[4]; // [rsp+60h] [rbp-11h] BYREF
  int AccessStatus; // [rsp+64h] [rbp-Dh] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-9h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+70h] [rbp-1h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+80h] [rbp+Fh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp+1Fh] BYREF
  unsigned __int8 OldValue; // [rsp+E0h] [rbp+6Fh] BYREF

  if ( a3 )
    return 124;
  if ( a4 )
    return 87;
  GenericMapping = qword_18005C630;
  SecurityDescriptor = qword_18005C638;
  v7 = SsStatisticsSecurityObject;
  OldValue = 0;
  DestinationString = 0;
  GrantedAccess = 0;
  ObjectTypeName = 0;
  GenerateOnClose[0] = 0;
  ObjectName = 0;
  AccessStatus = 0;
  RtlInitUnicodeString(&DestinationString, L"Server");
  RtlInitUnicodeString(&ObjectTypeName, v7);
  RtlInitUnicodeString(&ObjectName, L"SRV Stat Info");
  RtlAdjustPrivilege(0x15u, 1u, 0, &OldValue);
  v8 = RpcImpersonateClient(0);
  if ( !v8 )
  {
    v10 = NtAccessCheckAndAuditAlarm(
            &DestinationString,
            0,
            &ObjectTypeName,
            &ObjectName,
            SecurityDescriptor,
            1u,
            GenericMapping,
            0,
            &GrantedAccess,
            &AccessStatus,
            GenerateOnClose);
    RpcRevertToSelf();
    if ( v10 >= 0 && !AccessStatus )
    {
      v11 = LocalAlloc(0x40u, 0x60u);
      v13 = v11;
      if ( !v11 )
        return 8;
      Info = SsServerFsControlGetInfo(v12, v11, a5);
      LocalFree(v13);
      return Info;
    }
    LOBYTE(v8) = 5;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_SLl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      v9,
      (_DWORD)SsStatisticsSecurityObject,
      1,
      v8);
  }
  return 5;
}

```

## disassembly

```asm
0x180011830  push    rbp
0x180011832  push    rbx
0x180011833  push    rsi
0x180011834  push    rdi
0x180011835  lea     rbp, [rsp-37h]
0x18001183a  sub     rsp, 0A8h
0x180011841  test    r8d, r8d
0x180011844  jnz     loc_180011959
0x18001184a  test    r9d, r9d
0x18001184d  jnz     loc_180011983
0x180011853  mov     rdi, cs:qword_18005C630
0x18001185a  lea     rdx, SourceName; "Server"
0x180011861  mov     rsi, cs:qword_18005C638
0x180011868  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18001186c  mov     rbx, cs:SsStatisticsSecurityObject
0x180011873  xorps   xmm0, xmm0
0x180011876  xorps   xmm1, xmm1
0x180011879  mov     [rbp+4Fh+OldValue], r9b
0x18001187d  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180011881  mov     [rbp+4Fh+var_58], r9d
0x180011885  movups  xmmword ptr [rbp+4Fh+ObjectTypeName.Length], xmm1
0x180011889  mov     [rbp+4Fh+var_60], r9b
0x18001188d  movups  xmmword ptr [rbp+4Fh+ObjectName.Length], xmm0
0x180011891  mov     [rbp+4Fh+var_5C], r9d
0x180011895  call    cs:__imp_RtlInitUnicodeString
0x18001189b  mov     rdx, rbx; SourceString
0x18001189e  lea     rcx, [rbp+4Fh+ObjectTypeName]; DestinationString
0x1800118a2  call    cs:__imp_RtlInitUnicodeString
0x1800118a8  lea     rdx, aSrvStatInfo; "SRV Stat Info"
0x1800118af  lea     rcx, [rbp+4Fh+ObjectName]; DestinationString
0x1800118b3  call    cs:__imp_RtlInitUnicodeString
0x1800118b9  xor     r8d, r8d; ForThread
0x1800118bc  lea     r9, [rbp+4Fh+OldValue]; OldValue
0x1800118c0  mov     dl, 1; NewValue
0x1800118c2  lea     ecx, [r8+15h]; Privilege
0x1800118c6  call    cs:__imp_RtlAdjustPrivilege
0x1800118cc  xor     ecx, ecx; BindingHandle
0x1800118ce  call    cs:__imp_RpcImpersonateClient
0x1800118d4  test    eax, eax
0x1800118d6  jnz     loc_180011960
0x1800118dc  lea     rax, [rbp+4Fh+var_60]
0x1800118e0  xor     edx, edx; HandleId
0x1800118e2  mov     [rsp+0C0h+GenerateOnClose], rax; GenerateOnClose
0x1800118e7  lea     r9, [rbp+4Fh+ObjectName]; ObjectName
0x1800118eb  lea     rax, [rbp+4Fh+var_5C]
0x1800118ef  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x1800118f4  lea     r8, [rbp+4Fh+ObjectTypeName]; ObjectTypeName
0x1800118f8  lea     rax, [rbp+4Fh+var_58]
0x1800118fc  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x180011901  lea     rcx, [rbp+4Fh+DestinationString]; SubsystemName
0x180011905  mov     [rsp+0C0h+ObjectCreation], 0; ObjectCreation
0x18001190a  mov     [rsp+0C0h+GenericMapping], rdi; GenericMapping
0x18001190f  mov     [rsp+0C0h+DesiredAccess], 1; DesiredAccess
0x180011917  mov     [rsp+0C0h+SecurityDescriptor], rsi; SecurityDescriptor
0x18001191c  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180011922  mov     ebx, eax
0x180011924  call    cs:__imp_RpcRevertToSelf
0x18001192a  test    ebx, ebx
0x18001192c  js      short loc_18001198A
0x18001192e  cmp     [rbp+4Fh+var_5C], 0
0x180011932  jnz     short loc_18001198A
0x180011934  mov     edx, 60h ; '`'; uBytes
0x180011939  lea     ecx, [rdx-20h]; uFlags
0x18001193c  call    cs:__imp_LocalAlloc
0x180011942  mov     rdi, rax
0x180011945  test    rax, rax
0x180011948  jnz     short loc_1800119B5
0x18001194a  lea     eax, [rdi+8]
0x18001194d  add     rsp, 0A8h
0x180011954  pop     rdi
0x180011955  pop     rsi
0x180011956  pop     rbx
0x180011957  pop     rbp
0x180011958  retn
0x180011959  mov     eax, 7Ch ; '|'
0x18001195e  jmp     short loc_18001194D
0x180011960  mov     rcx, cs:WPP_GLOBAL_Control
0x180011967  lea     rdx, WPP_GLOBAL_Control
0x18001196e  cmp     rcx, rdx
0x180011971  jz      short loc_18001197C
0x180011973  test    dword ptr [rcx+1Ch], 200h
0x18001197a  jnz     short loc_180011991
0x18001197c  mov     eax, 5
0x180011981  jmp     short loc_18001194D
0x180011983  mov     eax, 57h ; 'W'
0x180011988  jmp     short loc_18001194D
0x18001198a  mov     eax, 5
0x18001198f  jmp     short loc_180011960
0x180011991  cmp     byte ptr [rcx+19h], 1
0x180011995  jb      short loc_18001197C
0x180011997  mov     r9, cs:SsStatisticsSecurityObject
0x18001199e  mov     rcx, [rcx+10h]
0x1800119a2  mov     [rsp+0C0h+DesiredAccess], eax
0x1800119a6  mov     dword ptr [rsp+0C0h+SecurityDescriptor], 1
0x1800119ae  call    WPP_SF_SLl
0x1800119b3  jmp     short loc_18001197C
0x1800119b5  mov     r8, [rbp+4Fh+arg_20]
0x1800119b9  mov     rdx, rdi
0x1800119bc  call    SsServerFsControlGetInfo
0x1800119c1  mov     rcx, rdi; hMem
0x1800119c4  mov     ebx, eax
0x1800119c6  call    cs:__imp_LocalFree
0x1800119cc  mov     eax, ebx
0x1800119ce  jmp     loc_18001194D
```
