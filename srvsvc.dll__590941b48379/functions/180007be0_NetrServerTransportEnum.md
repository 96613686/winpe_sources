# NetrServerTransportEnum

- ea: `0x180007be0`
- end: `0x180007f96`
- name: `NetrServerTransportEnum`
- size: `950`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007be0`
- `0x180008de0`
- `0x180028c24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007dde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007dde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ea7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ea7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f66`
- `ntdll!RtlInitUnicodeString` at `0x180007c76`
- `ntdll!RtlInitUnicodeString` at `0x180007c87`
- `ntdll!RtlInitUnicodeString` at `0x180007c99`
- `ntdll!RtlInitUnicodeString` at `0x180007c76`
- `ntdll!RtlInitUnicodeString` at `0x180007c87`
- `ntdll!RtlInitUnicodeString` at `0x180007c99`
- `ntdll!RtlAdjustPrivilege` at `0x180007cb1`
- `ntdll!RtlAdjustPrivilege` at `0x180007cb1`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180007d13`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180007d13`
- `RPCRT4!RpcImpersonateClient` at `0x180007cb9`
- `RPCRT4!RpcImpersonateClient` at `0x180007cb9`
- `RPCRT4!RpcRevertToSelf` at `0x180007d1b`
- `RPCRT4!RpcRevertToSelf` at `0x180007d1b`

## pseudocode

```c
__int64 __fastcall NetrServerTransportEnum(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, int *a5)
{
  struct _GENERIC_MAPPING *GenericMapping; // rsi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // r15
  const WCHAR *v10; // rdi
  RPC_STATUS v11; // eax
  int v12; // r8d
  NTSTATUS v13; // edi
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rdi
  int v16; // eax
  void *v17; // rcx
  bool v18; // zf
  unsigned int v19; // r15d
  __int64 v20; // rsi
  ULONG v21; // r13d
  unsigned int i; // eax
  void *v23; // rcx
  HLOCAL v24; // rax
  HANDLE v25; // rcx
  unsigned int v26; // eax
  void *v27; // rcx
  unsigned __int8 GenerateOnClose[8]; // [rsp+60h] [rbp-78h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-70h] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp-68h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+78h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-50h] BYREF
  struct _UNICODE_STRING SubsystemName; // [rsp+98h] [rbp-40h] BYREF
  unsigned int OldValue; // [rsp+E8h] [rbp+10h] BYREF

  if ( !a2 )
    return 87;
  if ( *(_DWORD *)a2 >= 3u )
    return 124;
  if ( !*(_QWORD *)(a2 + 8) )
    return 87;
  if ( !dword_18005CE2C )
    goto LABEL_8;
  GenericMapping = qword_18005C688;
  SecurityDescriptor = qword_18005C690;
  v10 = SsTransportEnumSecurityObject;
  LOBYTE(OldValue) = 0;
  SubsystemName = 0;
  GrantedAccess = 0;
  DestinationString = 0;
  GenerateOnClose[0] = 0;
  ObjectName = 0;
  LODWORD(FileHandle) = 0;
  RtlInitUnicodeString(&SubsystemName, L"Server");
  RtlInitUnicodeString(&DestinationString, v10);
  RtlInitUnicodeString(&ObjectName, L"SRV Transport Info");
  RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)&OldValue);
  v11 = RpcImpersonateClient(0);
  if ( v11 )
  {
LABEL_36:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_SLl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        v12,
        (_DWORD)SsTransportEnumSecurityObject,
        1,
        v11);
    }
    return 5;
  }
  v13 = NtAccessCheckAndAuditAlarm(
          &SubsystemName,
          0,
          &DestinationString,
          &ObjectName,
          SecurityDescriptor,
          1u,
          GenericMapping,
          0,
          &GrantedAccess,
          (PNTSTATUS)&FileHandle,
          GenerateOnClose);
  RpcRevertToSelf();
  if ( v13 < 0 || (_DWORD)FileHandle )
  {
    LOBYTE(v11) = 5;
    goto LABEL_36;
  }
LABEL_8:
  v14 = (unsigned __int16 *)LocalAlloc(0x40u, 0x60u);
  v15 = v14;
  if ( !v14 )
    return 8;
  *((_DWORD *)v14 + 16) = *(_DWORD *)a2;
  if ( a5 )
    v16 = *a5;
  else
    v16 = 0;
  *((_DWORD *)v15 + 23) = v16;
  v17 = *(void **)(*(_QWORD *)(a2 + 8) + 8LL);
  if ( v17 )
  {
    LocalFree(v17);
    *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL) = 0;
  }
  v18 = (v15[36] & 1) == 0;
  v19 = 0;
  v20 = *(_QWORD *)(a2 + 8);
  FileHandle = qword_18005CDB8;
  GrantedAccess = *((_DWORD *)v15 + 23);
  if ( v18 )
  {
    v21 = a3;
    if ( a3 > 0x2000 )
      v21 = 0x2000;
  }
  else
  {
    v21 = 1024;
    if ( a3 <= 0x400 )
      v21 = a3;
  }
  *(_QWORD *)(v20 + 8) = 0;
  for ( i = 0; ; i = OldValue + 1 )
  {
    OldValue = i;
    if ( i >= 5 )
      break;
    v23 = *(void **)(v20 + 8);
    if ( v23 )
      LocalFree(v23);
    v24 = LocalAlloc(0x40u, v21);
    *(_QWORD *)(v20 + 8) = v24;
    if ( !v24 )
    {
      v19 = 8;
      break;
    }
    v25 = FileHandle;
    *((_DWORD *)v15 + 23) = GrantedAccess;
    v26 = SsServerFsControlCommon(v25, 0x14601Fu, v15, *(PVOID *)(v20 + 8), v21);
    v19 = v26;
    if ( v26 != 2123 && v26 != 234 || v21 >= a3 )
      break;
    v21 = a3;
    if ( *((_DWORD *)v15 + 22) + 1024 < a3 )
      v21 = *((_DWORD *)v15 + 22) + 1024;
  }
  v27 = *(void **)(v20 + 8);
  if ( v27 && !*((_DWORD *)v15 + 20) )
  {
    LocalFree(v27);
    *(_QWORD *)(v20 + 8) = 0;
  }
  **(_DWORD **)(a2 + 8) = *((_DWORD *)v15 + 20);
  *a4 = *((_DWORD *)v15 + 21);
  if ( *((_DWORD *)v15 + 20) )
  {
    if ( a5 )
      *a5 = *((_DWORD *)v15 + 23);
  }
  LocalFree(v15);
  return v19;
}

```

## disassembly

```asm
0x180007be0  mov     rax, rsp
0x180007be3  push    rbx
0x180007be4  push    rbp
0x180007be5  push    r14
0x180007be7  sub     rsp, 0C0h
0x180007bee  mov     r14, r9
0x180007bf1  mov     ebp, r8d
0x180007bf4  mov     rbx, rdx
0x180007bf7  test    rdx, rdx
0x180007bfa  jz      loc_180007F8C
0x180007c00  cmp     dword ptr [rdx], 3
0x180007c03  jnb     loc_180007F0D
0x180007c09  cmp     qword ptr [rdx+8], 0
0x180007c0e  jz      loc_180007F8C
0x180007c14  mov     [rax+8], rsi
0x180007c18  mov     [rax+18h], rdi
0x180007c1c  mov     [rax+20h], r12
0x180007c20  xor     r12d, r12d
0x180007c23  cmp     cs:dword_18005CE2C, r12d
0x180007c2a  mov     [rax-28h], r15
0x180007c2e  jz      loc_180007D34
0x180007c34  mov     rsi, cs:qword_18005C688
0x180007c3b  lea     rdx, SourceName; "Server"
0x180007c42  mov     r15, cs:qword_18005C690
0x180007c49  lea     rcx, [rax-40h]; DestinationString
0x180007c4d  mov     rdi, cs:SsTransportEnumSecurityObject
0x180007c54  xorps   xmm0, xmm0
0x180007c57  xorps   xmm1, xmm1
0x180007c5a  mov     [rax+10h], r12b
0x180007c5e  movups  xmmword ptr [rax-40h], xmm0
0x180007c62  mov     [rax-68h], r12d
0x180007c66  movups  xmmword ptr [rax-50h], xmm1
0x180007c6a  mov     [rax-78h], r12b
0x180007c6e  movups  xmmword ptr [rax-60h], xmm0
0x180007c72  mov     [rax-70h], r12d
0x180007c76  call    cs:__imp_RtlInitUnicodeString
0x180007c7c  mov     rdx, rdi; SourceString
0x180007c7f  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x180007c87  call    cs:__imp_RtlInitUnicodeString
0x180007c8d  lea     rdx, aSrvTransportIn; "SRV Transport Info"
0x180007c94  lea     rcx, [rsp+0D8h+ObjectName]; DestinationString
0x180007c99  call    cs:__imp_RtlInitUnicodeString
0x180007c9f  lea     r9, [rsp+0D8h+OldValue]; OldValue
0x180007ca7  xor     r8d, r8d; ForThread
0x180007caa  mov     dl, 1; NewValue
0x180007cac  mov     ecx, 15h; Privilege
0x180007cb1  call    cs:__imp_RtlAdjustPrivilege
0x180007cb7  xor     ecx, ecx; BindingHandle
0x180007cb9  call    cs:__imp_RpcImpersonateClient
0x180007cbf  test    eax, eax
0x180007cc1  jnz     loc_180007EE7
0x180007cc7  lea     rax, [rsp+0D8h+var_78]
0x180007ccc  xor     edx, edx; HandleId
0x180007cce  mov     [rsp+0D8h+GenerateOnClose], rax; GenerateOnClose
0x180007cd3  lea     r9, [rsp+0D8h+ObjectName]; ObjectName
0x180007cd8  lea     rax, [rsp+0D8h+FileHandle]
0x180007cdd  mov     [rsp+0D8h+AccessStatus], rax; AccessStatus
0x180007ce2  lea     r8, [rsp+0D8h+DestinationString]; ObjectTypeName
0x180007cea  lea     rax, [rsp+0D8h+var_68]
0x180007cef  mov     [rsp+0D8h+GrantedAccess], rax; GrantedAccess
0x180007cf4  lea     rcx, [rsp+0D8h+SubsystemName]; SubsystemName
0x180007cfc  mov     [rsp+0D8h+ObjectCreation], r12b; ObjectCreation
0x180007d01  mov     [rsp+0D8h+GenericMapping], rsi; GenericMapping
0x180007d06  mov     [rsp+0D8h+DesiredAccess], 1; DesiredAccess
0x180007d0e  mov     [rsp+0D8h+SecurityDescriptor], r15; SecurityDescriptor
0x180007d13  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180007d19  mov     edi, eax
0x180007d1b  call    cs:__imp_RpcRevertToSelf
0x180007d21  test    edi, edi
0x180007d23  js      loc_180007F17
0x180007d29  cmp     dword ptr [rsp+0D8h+FileHandle], r12d
0x180007d2e  jnz     loc_180007F17
0x180007d34  mov     edx, 60h ; '`'; uBytes
0x180007d39  mov     ecx, 40h ; '@'; uFlags
0x180007d3e  call    cs:__imp_LocalAlloc
0x180007d44  mov     rdi, rax
0x180007d47  test    rax, rax
0x180007d4a  jz      loc_180007F42
0x180007d50  mov     eax, [rbx]
0x180007d52  mov     [rdi+40h], eax
0x180007d55  mov     rax, [rsp+0D8h+arg_20]
0x180007d5d  test    rax, rax
0x180007d60  jnz     loc_180007F4C
0x180007d66  mov     eax, r12d
0x180007d69  mov     [rdi+5Ch], eax
0x180007d6c  mov     rax, [rbx+8]
0x180007d70  mov     rcx, [rax+8]; hMem
0x180007d74  test    rcx, rcx
0x180007d77  jnz     loc_180007F53
0x180007d7d  test    byte ptr [rdi+48h], 1
0x180007d81  mov     r15d, r12d
0x180007d84  mov     rax, cs:qword_18005CDB8
0x180007d8b  mov     rsi, [rbx+8]
0x180007d8f  mov     [rsp+0D8h+FileHandle], rax
0x180007d94  mov     eax, [rdi+5Ch]
0x180007d97  mov     [rsp+0D8h+var_68], eax
0x180007d9b  mov     [rsp+0D8h+var_20], r13
0x180007da3  jz      loc_180007E94
0x180007da9  mov     r13d, 400h
0x180007daf  cmp     ebp, r13d
0x180007db2  cmovbe  r13d, ebp
0x180007db6  mov     [rsi+8], r12
0x180007dba  mov     eax, r12d
0x180007dbd  mov     [rsp+0D8h+OldValue], eax
0x180007dc4  cmp     eax, 5
0x180007dc7  jnb     short loc_180007E2C
0x180007dc9  mov     rcx, [rsi+8]; hMem
0x180007dcd  test    rcx, rcx
0x180007dd0  jnz     loc_180007F66
0x180007dd6  mov     edx, r13d; uBytes
0x180007dd9  mov     ecx, 40h ; '@'; uFlags
0x180007dde  call    cs:__imp_LocalAlloc
0x180007de4  mov     [rsi+8], rax
0x180007de8  test    rax, rax
0x180007deb  jz      loc_180007EDC
0x180007df1  mov     eax, [rsp+0D8h+var_68]
0x180007df5  mov     r8, rdi; hMem
0x180007df8  mov     rcx, [rsp+0D8h+FileHandle]; FileHandle
0x180007dfd  mov     edx, 14601Fh; FsControlCode
0x180007e02  mov     [rdi+5Ch], eax
0x180007e05  mov     r9, [rsi+8]; OutputBuffer
0x180007e09  mov     dword ptr [rsp+0D8h+SecurityDescriptor], r13d; ULONG
0x180007e0e  call    SsServerFsControlCommon
0x180007e13  mov     r15d, eax
0x180007e16  cmp     eax, 84Bh
0x180007e1b  jz      loc_180007EB3
0x180007e21  cmp     eax, 0EAh
0x180007e26  jz      loc_180007EB3
0x180007e2c  mov     rcx, [rsi+8]; hMem
0x180007e30  mov     r13, [rsp+0D8h+var_20]
0x180007e38  test    rcx, rcx
0x180007e3b  jz      short loc_180007E43
0x180007e3d  cmp     dword ptr [rdi+50h], 0
0x180007e41  jz      short loc_180007EA7
0x180007e43  mov     eax, [rdi+50h]
0x180007e46  mov     rcx, [rbx+8]
0x180007e4a  mov     [rcx], eax
0x180007e4c  mov     eax, [rdi+54h]
0x180007e4f  mov     [r14], eax
0x180007e52  cmp     dword ptr [rdi+50h], 0
0x180007e56  ja      loc_180007F71
0x180007e5c  mov     rcx, rdi; hMem
0x180007e5f  call    cs:__imp_LocalFree
0x180007e65  mov     eax, r15d
0x180007e68  mov     r12, [rsp+0D8h+arg_18]
0x180007e70  mov     rdi, [rsp+0D8h+arg_10]
0x180007e78  mov     rsi, [rsp+0D8h+arg_0]
0x180007e80  mov     r15, [rsp+0D8h+var_28]
0x180007e88  add     rsp, 0C0h
0x180007e8f  pop     r14
0x180007e91  pop     rbp
0x180007e92  pop     rbx
0x180007e93  retn
0x180007e94  mov     eax, 2000h
0x180007e99  mov     r13d, ebp
0x180007e9c  cmp     ebp, eax
0x180007e9e  cmova   r13d, eax
0x180007ea2  jmp     loc_180007DB6
0x180007ea7  call    cs:__imp_LocalFree
0x180007ead  mov     [rsi+8], r12
0x180007eb1  jmp     short loc_180007E43
0x180007eb3  cmp     r13d, ebp
0x180007eb6  jnb     loc_180007E2C
0x180007ebc  mov     ecx, [rdi+58h]
0x180007ebf  mov     r13d, ebp
0x180007ec2  mov     eax, [rsp+0D8h+OldValue]
0x180007ec9  add     ecx, 400h
0x180007ecf  cmp     ecx, ebp
0x180007ed1  cmovb   r13d, ecx
0x180007ed5  inc     eax
0x180007ed7  jmp     loc_180007DBD
0x180007edc  mov     r15d, 8
0x180007ee2  jmp     loc_180007E2C
0x180007ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007eee  lea     rdx, WPP_GLOBAL_Control
0x180007ef5  cmp     rcx, rdx
0x180007ef8  jz      short loc_180007F03
0x180007efa  test    dword ptr [rcx+1Ch], 200h
0x180007f01  jnz     short loc_180007F1E
0x180007f03  mov     eax, 5
0x180007f08  jmp     loc_180007E68
0x180007f0d  mov     eax, 7Ch ; '|'
0x180007f12  jmp     loc_180007E88
0x180007f17  mov     eax, 5
0x180007f1c  jmp     short loc_180007EE7
0x180007f1e  cmp     byte ptr [rcx+19h], 1
0x180007f22  jb      short loc_180007F03
0x180007f24  mov     r9, cs:SsTransportEnumSecurityObject
0x180007f2b  mov     rcx, [rcx+10h]
0x180007f2f  mov     [rsp+0D8h+DesiredAccess], eax
0x180007f33  mov     dword ptr [rsp+0D8h+SecurityDescriptor], 1
0x180007f3b  call    WPP_SF_SLl
0x180007f40  jmp     short loc_180007F03
0x180007f42  mov     eax, 8
0x180007f47  jmp     loc_180007E68
0x180007f4c  mov     eax, [rax]
0x180007f4e  jmp     loc_180007D69
0x180007f53  call    cs:__imp_LocalFree
0x180007f59  mov     rax, [rbx+8]
0x180007f5d  mov     [rax+8], r12
0x180007f61  jmp     loc_180007D7D
0x180007f66  call    cs:__imp_LocalFree
0x180007f6c  jmp     loc_180007DD6
0x180007f71  mov     rcx, [rsp+0D8h+arg_20]
0x180007f79  test    rcx, rcx
0x180007f7c  jz      loc_180007E5C
0x180007f82  mov     eax, [rdi+5Ch]
0x180007f85  mov     [rcx], eax
0x180007f87  jmp     loc_180007E5C
0x180007f8c  mov     eax, 57h ; 'W'
0x180007f91  jmp     loc_180007E88
```
