# NetrConnectionEnum

- ea: `0x180011be0`
- end: `0x180011e24`
- name: `NetrConnectionEnum`
- size: `580`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008ca0`
- `0x18000b940`
- `0x180011be0`
- `0x180028c24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011e00`
- `ntdll!RtlInitUnicodeString` at `0x180011c90`
- `ntdll!RtlInitUnicodeString` at `0x180011c9d`
- `ntdll!RtlInitUnicodeString` at `0x180011cae`
- `ntdll!RtlInitUnicodeString` at `0x180011d9e`
- `ntdll!RtlInitUnicodeString` at `0x180011c90`
- `ntdll!RtlInitUnicodeString` at `0x180011c9d`
- `ntdll!RtlInitUnicodeString` at `0x180011cae`
- `ntdll!RtlInitUnicodeString` at `0x180011d9e`
- `ntdll!RtlAdjustPrivilege` at `0x180011cc1`
- `ntdll!RtlAdjustPrivilege` at `0x180011cc1`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180011d13`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180011d13`
- `RPCRT4!RpcImpersonateClient` at `0x180011cc9`
- `RPCRT4!RpcImpersonateClient` at `0x180011cc9`
- `RPCRT4!RpcRevertToSelf` at `0x180011d1b`
- `RPCRT4!RpcRevertToSelf` at `0x180011d1b`

## pseudocode

```c
__int64 __fastcall NetrConnectionEnum(__int64 a1, const wchar_t *a2, __int64 a3, int a4, _DWORD *a5, _DWORD *a6)
{
  struct _GENERIC_MAPPING *GenericMapping; // r15
  PSECURITY_DESCRIPTOR v11; // r12
  const WCHAR *v12; // rbx
  RPC_STATUS v13; // eax
  int v14; // r8d
  NTSTATUS v15; // ebx
  struct _UNICODE_STRING *v16; // rbx
  _DWORD *v17; // rdi
  int v18; // eax
  unsigned int InfoCommon; // r14d
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-79h]
  unsigned __int8 GenerateOnClose[4]; // [rsp+60h] [rbp-39h] BYREF
  int AccessStatus; // [rsp+64h] [rbp-35h] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-31h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int8 OldValue; // [rsp+F8h] [rbp+5Fh] BYREF

  if ( a2 && StringCchLengthW(a2, 0x400u, 0) )
    return 87;
  if ( *(_DWORD *)a3 > 1u )
    return 124;
  if ( !a2 || !*a2 || !*(_QWORD *)(a3 + 8) )
    return 87;
  GenericMapping = qword_18005C5A8;
  v11 = qword_18005C5B0;
  v12 = SsConnectionSecurityObject;
  OldValue = 0;
  DestinationString = 0;
  GrantedAccess = 0;
  ObjectTypeName = 0;
  GenerateOnClose[0] = 0;
  ObjectName = 0;
  AccessStatus = 0;
  RtlInitUnicodeString(&DestinationString, L"Server");
  RtlInitUnicodeString(&ObjectTypeName, v12);
  RtlInitUnicodeString(&ObjectName, L"SRV Connection Info");
  RtlAdjustPrivilege(0x15u, 1u, 0, &OldValue);
  v13 = RpcImpersonateClient(0);
  if ( v13 )
    goto LABEL_12;
  v15 = NtAccessCheckAndAuditAlarm(
          &DestinationString,
          0,
          &ObjectTypeName,
          &ObjectName,
          v11,
          1u,
          GenericMapping,
          0,
          &GrantedAccess,
          &AccessStatus,
          GenerateOnClose);
  RpcRevertToSelf();
  if ( v15 < 0 || AccessStatus )
  {
    LOBYTE(v13) = 5;
LABEL_12:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_SLl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          v14,
          (_DWORD)SsConnectionSecurityObject,
          1,
          v13);
    }
    return 5;
  }
  v16 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x60u);
  if ( !v16 )
    return 8;
  *(_DWORD *)&v16[4].Length = *(_DWORD *)a3;
  RtlInitUnicodeString(v16, a2);
  v17 = a6;
  if ( a6 )
    v18 = *a6;
  else
    v18 = 0;
  HIDWORD(v16[5].Buffer) = v18;
  LODWORD(SecurityDescriptor) = a4;
  InfoCommon = SsServerFsControlGetInfoCommonEx(qword_18005CDB8, 0x146003u, v16, (SIZE_T)SecurityDescriptor);
  **(_DWORD **)(a3 + 8) = *(_DWORD *)&v16[5].Length;
  *a5 = *(_DWORD *)(&v16[5].MaximumLength + 1);
  if ( *(_DWORD *)&v16[5].Length && v17 )
    *v17 = HIDWORD(v16[5].Buffer);
  LocalFree(v16);
  return InfoCommon;
}

```

## disassembly

```asm
0x180011be0  push    rbp
0x180011be2  push    rbx
0x180011be3  push    rsi
0x180011be4  push    rdi
0x180011be5  push    r12
0x180011be7  push    r13
0x180011be9  push    r14
0x180011beb  push    r15
0x180011bed  lea     rbp, [rsp-0Fh]
0x180011bf2  sub     rsp, 0A8h
0x180011bf9  xor     r13d, r13d
0x180011bfc  mov     r14d, r9d
0x180011bff  mov     rsi, r8
0x180011c02  mov     rdi, rdx
0x180011c05  test    rdx, rdx
0x180011c08  jz      short loc_180011C22
0x180011c0a  xor     r8d, r8d; pcchLength
0x180011c0d  mov     edx, 400h; cchMax
0x180011c12  mov     rcx, rdi; psz
0x180011c15  call    StringCchLengthW
0x180011c1a  test    eax, eax
0x180011c1c  jnz     loc_180011E0B
0x180011c22  cmp     dword ptr [rsi], 1
0x180011c25  jbe     short loc_180011C31
0x180011c27  mov     eax, 7Ch ; '|'
0x180011c2c  jmp     loc_180011E10
0x180011c31  test    rdi, rdi
0x180011c34  jz      loc_180011E0B
0x180011c3a  cmp     [rdi], r13w
0x180011c3e  jz      loc_180011E0B
0x180011c44  cmp     [rsi+8], r13
0x180011c48  jz      loc_180011E0B
0x180011c4e  mov     r15, cs:qword_18005C5A8
0x180011c55  lea     rdx, SourceName; "Server"
0x180011c5c  mov     r12, cs:qword_18005C5B0
0x180011c63  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180011c67  mov     rbx, cs:SsConnectionSecurityObject
0x180011c6e  xorps   xmm0, xmm0
0x180011c71  xorps   xmm1, xmm1
0x180011c74  mov     [rbp+47h+OldValue], r13b
0x180011c78  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x180011c7c  mov     [rbp+47h+var_78], r13d
0x180011c80  movups  xmmword ptr [rbp+47h+ObjectTypeName.Length], xmm1
0x180011c84  mov     [rbp+47h+var_80], r13b
0x180011c88  movups  xmmword ptr [rbp+47h+ObjectName.Length], xmm0
0x180011c8c  mov     [rbp+47h+var_7C], r13d
0x180011c90  call    cs:__imp_RtlInitUnicodeString
0x180011c96  mov     rdx, rbx; SourceString
0x180011c99  lea     rcx, [rbp+47h+ObjectTypeName]; DestinationString
0x180011c9d  call    cs:__imp_RtlInitUnicodeString
0x180011ca3  lea     rdx, aSrvConnectionI; "SRV Connection Info"
0x180011caa  lea     rcx, [rbp+47h+ObjectName]; DestinationString
0x180011cae  call    cs:__imp_RtlInitUnicodeString
0x180011cb4  xor     r8d, r8d; ForThread
0x180011cb7  lea     r9, [rbp+47h+OldValue]; OldValue
0x180011cbb  mov     dl, 1; NewValue
0x180011cbd  lea     ecx, [r8+15h]; Privilege
0x180011cc1  call    cs:__imp_RtlAdjustPrivilege
0x180011cc7  xor     ecx, ecx; BindingHandle
0x180011cc9  call    cs:__imp_RpcImpersonateClient
0x180011ccf  test    eax, eax
0x180011cd1  jnz     short loc_180011D30
0x180011cd3  lea     rax, [rbp+47h+var_80]
0x180011cd7  xor     edx, edx; HandleId
0x180011cd9  mov     [rsp+0E0h+GenerateOnClose], rax; GenerateOnClose
0x180011cde  lea     r9, [rbp+47h+ObjectName]; ObjectName
0x180011ce2  lea     rax, [rbp+47h+var_7C]
0x180011ce6  mov     [rsp+0E0h+AccessStatus], rax; AccessStatus
0x180011ceb  lea     r8, [rbp+47h+ObjectTypeName]; ObjectTypeName
0x180011cef  lea     rax, [rbp+47h+var_78]
0x180011cf3  mov     [rsp+0E0h+GrantedAccess], rax; GrantedAccess
0x180011cf8  lea     rcx, [rbp+47h+DestinationString]; SubsystemName
0x180011cfc  mov     [rsp+0E0h+ObjectCreation], r13b; ObjectCreation
0x180011d01  mov     [rsp+0E0h+GenericMapping], r15; GenericMapping
0x180011d06  mov     [rsp+0E0h+DesiredAccess], 1; DesiredAccess
0x180011d0e  mov     [rsp+0E0h+SecurityDescriptor], r12; SecurityDescriptor
0x180011d13  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180011d19  mov     ebx, eax
0x180011d1b  call    cs:__imp_RpcRevertToSelf
0x180011d21  test    ebx, ebx
0x180011d23  js      short loc_180011D2B
0x180011d25  cmp     [rbp+47h+var_7C], r13d
0x180011d29  jz      short loc_180011D78
0x180011d2b  mov     eax, 5
0x180011d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d37  lea     rdx, WPP_GLOBAL_Control
0x180011d3e  cmp     rcx, rdx
0x180011d41  jz      short loc_180011D6E
0x180011d43  test    dword ptr [rcx+1Ch], 200h
0x180011d4a  jz      short loc_180011D6E
0x180011d4c  cmp     byte ptr [rcx+19h], 1
0x180011d50  jb      short loc_180011D6E
0x180011d52  mov     r9, cs:SsConnectionSecurityObject
0x180011d59  mov     rcx, [rcx+10h]
0x180011d5d  mov     [rsp+0E0h+DesiredAccess], eax
0x180011d61  mov     dword ptr [rsp+0E0h+SecurityDescriptor], 1
0x180011d69  call    WPP_SF_SLl
0x180011d6e  mov     eax, 5
0x180011d73  jmp     loc_180011E10
0x180011d78  mov     edx, 60h ; '`'; uBytes
0x180011d7d  lea     ecx, [rdx-20h]; uFlags
0x180011d80  call    cs:__imp_LocalAlloc
0x180011d86  mov     rbx, rax
0x180011d89  test    rax, rax
0x180011d8c  jnz     short loc_180011D93
0x180011d8e  lea     eax, [rbx+8]
0x180011d91  jmp     short loc_180011E10
0x180011d93  mov     eax, [rsi]
0x180011d95  mov     rdx, rdi; SourceString
0x180011d98  mov     rcx, rbx; DestinationString
0x180011d9b  mov     [rbx+40h], eax
0x180011d9e  call    cs:__imp_RtlInitUnicodeString
0x180011da4  mov     rdi, [rbp+47h+arg_28]
0x180011da8  test    rdi, rdi
0x180011dab  jz      short loc_180011DB1
0x180011dad  mov     eax, [rdi]
0x180011daf  jmp     short loc_180011DB4
0x180011db1  mov     eax, r13d
0x180011db4  mov     [rbx+5Ch], eax
0x180011db7  mov     r8, rbx; hMem
0x180011dba  mov     r9, [rsi+8]
0x180011dbe  mov     edx, 146003h; FsControlCode
0x180011dc3  mov     rcx, cs:qword_18005CDB8; FileHandle
0x180011dca  add     r9, 8
0x180011dce  mov     dword ptr [rsp+0E0h+SecurityDescriptor], r14d; uBytes
0x180011dd3  call    SsServerFsControlGetInfoCommonEx
0x180011dd8  mov     rdx, [rsi+8]
0x180011ddc  mov     r14d, eax
0x180011ddf  mov     ecx, [rbx+50h]
0x180011de2  mov     [rdx], ecx
0x180011de4  mov     rcx, [rbp+47h+arg_20]
0x180011de8  mov     edx, [rbx+54h]
0x180011deb  mov     [rcx], edx
0x180011ded  cmp     [rbx+50h], r13d
0x180011df1  jbe     short loc_180011DFD
0x180011df3  test    rdi, rdi
0x180011df6  jz      short loc_180011DFD
0x180011df8  mov     ecx, [rbx+5Ch]
0x180011dfb  mov     [rdi], ecx
0x180011dfd  mov     rcx, rbx; hMem
0x180011e00  call    cs:__imp_LocalFree
0x180011e06  mov     eax, r14d
0x180011e09  jmp     short loc_180011E10
0x180011e0b  mov     eax, 57h ; 'W'
0x180011e10  add     rsp, 0A8h
0x180011e17  pop     r15
0x180011e19  pop     r14
0x180011e1b  pop     r13
0x180011e1d  pop     r12
0x180011e1f  pop     rdi
0x180011e20  pop     rsi
0x180011e21  pop     rbx
0x180011e22  pop     rbp
0x180011e23  retn
```
