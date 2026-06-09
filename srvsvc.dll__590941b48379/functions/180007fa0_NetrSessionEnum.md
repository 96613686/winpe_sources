# NetrSessionEnum

- ea: `0x180007fa0`
- end: `0x180008462`
- name: `NetrSessionEnum`
- size: `1218`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007fa0`
- `0x180008de0`
- `0x18000b940`
- `0x180028c24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008156`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800081f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008156`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800081f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800082e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800082e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008432`
- `ntdll!RtlInitUnicodeString` at `0x180008077`
- `ntdll!RtlInitUnicodeString` at `0x180008088`
- `ntdll!RtlInitUnicodeString` at `0x18000809a`
- `ntdll!RtlInitUnicodeString` at `0x180008174`
- `ntdll!RtlInitUnicodeString` at `0x180008181`
- `ntdll!RtlInitUnicodeString` at `0x180008077`
- `ntdll!RtlInitUnicodeString` at `0x180008088`
- `ntdll!RtlInitUnicodeString` at `0x18000809a`
- `ntdll!RtlInitUnicodeString` at `0x180008174`
- `ntdll!RtlInitUnicodeString` at `0x180008181`
- `ntdll!RtlAdjustPrivilege` at `0x1800080b2`
- `ntdll!RtlAdjustPrivilege` at `0x1800080b2`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180008110`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180008110`
- `RPCRT4!RpcImpersonateClient` at `0x1800080ba`
- `RPCRT4!RpcImpersonateClient` at `0x1800080ba`
- `RPCRT4!RpcRevertToSelf` at `0x180008118`
- `RPCRT4!RpcRevertToSelf` at `0x180008118`

## pseudocode

```c
__int64 __fastcall NetrSessionEnum(
        __int64 a1,
        const WCHAR *a2,
        const wchar_t *a3,
        int *a4,
        SIZE_T uBytes,
        _DWORD *a6,
        int *a7)
{
  const WCHAR *v8; // r12
  const WCHAR *v9; // rbp
  ULONG v10; // r13d
  __int64 v11; // rax
  int v12; // eax
  ACCESS_MASK DesiredAccess; // edi
  const WCHAR *v14; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rsi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // r15
  RPC_STATUS v17; // eax
  int v18; // r8d
  NTSTATUS v19; // ebx
  HLOCAL v20; // rbx
  int v21; // eax
  unsigned int v22; // r15d
  unsigned int v23; // edi
  bool v24; // zf
  __int64 v25; // rsi
  unsigned int j; // eax
  void *v27; // rcx
  HLOCAL v28; // rax
  void *v29; // rcx
  unsigned int v30; // eax
  void *v31; // rcx
  __int64 v33; // rcx
  const WCHAR *i; // rax
  int v35; // eax
  int v36; // eax
  unsigned __int8 GenerateOnClose[4]; // [rsp+60h] [rbp-68h] BYREF
  int AccessStatus; // [rsp+64h] [rbp-64h] BYREF
  DWORD GrantedAccess[2]; // [rsp+68h] [rbp-60h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+70h] [rbp-58h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+80h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-38h] BYREF
  int OldValue; // [rsp+D8h] [rbp+10h] BYREF

  v8 = a3;
  v9 = a2;
  v10 = 1024;
  if ( a2 )
  {
    v33 = 1024;
    for ( i = a2; *i; ++i )
    {
      if ( !--v33 )
        return 87;
    }
  }
  if ( a3 && StringCchLengthW(a3, 0x400u, 0) )
    return 87;
  if ( !a4 )
    return 87;
  v11 = *((_QWORD *)a4 + 1);
  if ( !v11 || *(_QWORD *)(v11 + 8) )
    return 87;
  v12 = *a4;
  if ( *a4 == 10 || !v12 )
  {
    DesiredAccess = 1;
  }
  else
  {
    v35 = v12 - 1;
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( v36 )
      {
        if ( v36 != 500 )
          return 124;
      }
    }
    DesiredAccess = 2;
  }
  v14 = SsSessionSecurityObject;
  GenericMapping = qword_18005C668;
  SecurityDescriptor = qword_18005C670;
  LOBYTE(OldValue) = 0;
  DestinationString = 0;
  GrantedAccess[0] = 0;
  ObjectTypeName = 0;
  GenerateOnClose[0] = 0;
  ObjectName = 0;
  AccessStatus = 0;
  RtlInitUnicodeString(&DestinationString, L"Server");
  RtlInitUnicodeString(&ObjectTypeName, v14);
  RtlInitUnicodeString(&ObjectName, L"SRV Session Info");
  RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)&OldValue);
  v17 = RpcImpersonateClient(0);
  if ( v17 )
    goto LABEL_53;
  v19 = NtAccessCheckAndAuditAlarm(
          &DestinationString,
          0,
          &ObjectTypeName,
          &ObjectName,
          SecurityDescriptor,
          DesiredAccess,
          GenericMapping,
          0,
          GrantedAccess,
          &AccessStatus,
          GenerateOnClose);
  RpcRevertToSelf();
  if ( v19 < 0 || AccessStatus )
  {
    LOBYTE(v17) = 5;
LABEL_53:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_SLl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        v18,
        (_DWORD)SsSessionSecurityObject,
        DesiredAccess,
        v17);
    }
    return 5;
  }
  if ( v9 && !*v9 )
    v9 = 0;
  if ( v8 && !*v8 )
    v8 = 0;
  if ( v9 && (*v9 != 92 || v9[1] != 92) )
    return 2351;
  v20 = LocalAlloc(0x40u, 0x60u);
  if ( !v20 )
    return 8;
  *((_DWORD *)v20 + 16) = *a4;
  RtlInitUnicodeString((PUNICODE_STRING)v20, v9);
  RtlInitUnicodeString((PUNICODE_STRING)v20 + 1, v8);
  v21 = (int)a7;
  if ( a7 )
    v21 = *a7;
  v22 = uBytes;
  v23 = 0;
  OldValue = v21;
  *((_DWORD *)v20 + 23) = v21;
  v24 = (*((_BYTE *)v20 + 72) & 1) == 0;
  v25 = *((_QWORD *)a4 + 1);
  *(_QWORD *)GrantedAccess = qword_18005CDB8;
  if ( v24 )
  {
    v10 = v22;
    if ( v22 > 0x2000 )
      v10 = 0x2000;
  }
  else if ( v22 <= 0x400 )
  {
    v10 = v22;
  }
  *(_QWORD *)(v25 + 8) = 0;
  for ( j = 0; ; j = AccessStatus + 1 )
  {
    AccessStatus = j;
    if ( j >= 5 )
      break;
    v27 = *(void **)(v25 + 8);
    if ( v27 )
      LocalFree(v27);
    v28 = LocalAlloc(0x40u, v10);
    *(_QWORD *)(v25 + 8) = v28;
    if ( !v28 )
    {
      v23 = 8;
      break;
    }
    v29 = *(void **)GrantedAccess;
    *((_DWORD *)v20 + 23) = OldValue;
    v30 = SsServerFsControlCommon(v29, 0x146027u, (unsigned __int16 *)v20, *(PVOID *)(v25 + 8), v10);
    v23 = v30;
    if ( v30 != 2123 && v30 != 234 || v10 >= v22 )
      break;
    v10 = v22;
    if ( *((_DWORD *)v20 + 22) + 1024 < v22 )
      v10 = *((_DWORD *)v20 + 22) + 1024;
  }
  v31 = *(void **)(v25 + 8);
  if ( v31 && !*((_DWORD *)v20 + 20) )
  {
    LocalFree(v31);
    *(_QWORD *)(v25 + 8) = 0;
  }
  **((_DWORD **)a4 + 1) = *((_DWORD *)v20 + 20);
  if ( a6 )
    *a6 = *((_DWORD *)v20 + 21);
  if ( *((_DWORD *)v20 + 20) )
  {
    if ( a7 )
      *a7 = *((_DWORD *)v20 + 23);
  }
  else if ( !*((_DWORD *)v20 + 21) )
  {
    if ( v8 )
    {
      v23 = 2221;
    }
    else if ( v9 )
    {
      v23 = 2312;
    }
  }
  LocalFree(v20);
  return v23;
}

```

## disassembly

```asm
0x180007fa0  push    rbp
0x180007fa2  push    r12
0x180007fa4  push    r13
0x180007fa6  push    r14
0x180007fa8  sub     rsp, 0A8h
0x180007faf  mov     r14, r9
0x180007fb2  mov     r12, r8
0x180007fb5  mov     rbp, rdx
0x180007fb8  mov     r13d, 400h
0x180007fbe  test    rdx, rdx
0x180007fc1  jnz     loc_180008336
0x180007fc7  test    r12, r12
0x180007fca  jnz     loc_180008393
0x180007fd0  test    r14, r14
0x180007fd3  jz      loc_180008354
0x180007fd9  mov     rax, [r9+8]
0x180007fdd  test    rax, rax
0x180007fe0  jz      loc_180008354
0x180007fe6  cmp     qword ptr [rax+8], 0
0x180007feb  jnz     loc_180008354
0x180007ff1  mov     eax, [r9]
0x180007ff4  mov     [rsp+0C8h+arg_18], rdi
0x180007ffc  cmp     eax, 0Ah
0x180007fff  jnz     loc_1800083AA
0x180008005  mov     edi, 1
0x18000800a  xor     eax, eax
0x18000800c  mov     [rsp+0C8h+arg_0], rbx
0x180008014  mov     rbx, cs:SsSessionSecurityObject
0x18000801b  lea     rdx, SourceName; "Server"
0x180008022  xorps   xmm0, xmm0
0x180008025  mov     [rsp+0C8h+arg_10], rsi
0x18000802d  mov     rsi, cs:qword_18005C668
0x180008034  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x18000803c  xorps   xmm1, xmm1
0x18000803f  mov     [rsp+0C8h+var_28], r15
0x180008047  mov     r15, cs:qword_18005C670
0x18000804e  mov     byte ptr [rsp+0C8h+OldValue], 0
0x180008056  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x18000805e  mov     [rsp+0C8h+var_60], eax
0x180008062  movups  xmmword ptr [rsp+0C8h+ObjectTypeName.Length], xmm1
0x18000806a  mov     [rsp+0C8h+var_68], al
0x18000806e  movups  xmmword ptr [rsp+0C8h+ObjectName.Length], xmm0
0x180008073  mov     [rsp+0C8h+var_64], eax
0x180008077  call    cs:__imp_RtlInitUnicodeString
0x18000807d  mov     rdx, rbx; SourceString
0x180008080  lea     rcx, [rsp+0C8h+ObjectTypeName]; DestinationString
0x180008088  call    cs:__imp_RtlInitUnicodeString
0x18000808e  lea     rdx, aSrvSessionInfo; "SRV Session Info"
0x180008095  lea     rcx, [rsp+0C8h+ObjectName]; DestinationString
0x18000809a  call    cs:__imp_RtlInitUnicodeString
0x1800080a0  lea     r9, [rsp+0C8h+OldValue]; OldValue
0x1800080a8  xor     r8d, r8d; ForThread
0x1800080ab  mov     dl, 1; NewValue
0x1800080ad  mov     ecx, 15h; Privilege
0x1800080b2  call    cs:__imp_RtlAdjustPrivilege
0x1800080b8  xor     ecx, ecx; BindingHandle
0x1800080ba  call    cs:__imp_RpcImpersonateClient
0x1800080c0  test    eax, eax
0x1800080c2  jnz     loc_18000836D
0x1800080c8  lea     rax, [rsp+0C8h+var_68]
0x1800080cd  xor     edx, edx; HandleId
0x1800080cf  mov     [rsp+0C8h+GenerateOnClose], rax; GenerateOnClose
0x1800080d4  lea     r9, [rsp+0C8h+ObjectName]; ObjectName
0x1800080d9  lea     rax, [rsp+0C8h+var_64]
0x1800080de  mov     [rsp+0C8h+AccessStatus], rax; AccessStatus
0x1800080e3  lea     r8, [rsp+0C8h+ObjectTypeName]; ObjectTypeName
0x1800080eb  lea     rax, [rsp+0C8h+var_60]
0x1800080f0  mov     [rsp+0C8h+GrantedAccess], rax; GrantedAccess
0x1800080f5  lea     rcx, [rsp+0C8h+DestinationString]; SubsystemName
0x1800080fd  mov     [rsp+0C8h+ObjectCreation], 0; ObjectCreation
0x180008102  mov     [rsp+0C8h+GenericMapping], rsi; GenericMapping
0x180008107  mov     [rsp+0C8h+DesiredAccess], edi; DesiredAccess
0x18000810b  mov     [rsp+0C8h+SecurityDescriptor], r15; SecurityDescriptor
0x180008110  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180008116  mov     ebx, eax
0x180008118  call    cs:__imp_RpcRevertToSelf
0x18000811e  test    ebx, ebx
0x180008120  js      loc_180008368
0x180008126  cmp     [rsp+0C8h+var_64], 0
0x18000812b  jnz     loc_180008368
0x180008131  test    rbp, rbp
0x180008134  jnz     loc_1800083F7
0x18000813a  test    r12, r12
0x18000813d  jnz     loc_180008406
0x180008143  test    rbp, rbp
0x180008146  jnz     loc_180008416
0x18000814c  mov     edx, 60h ; '`'; uBytes
0x180008151  mov     ecx, 40h ; '@'; uFlags
0x180008156  call    cs:__imp_LocalAlloc
0x18000815c  mov     rbx, rax
0x18000815f  test    rax, rax
0x180008162  jz      loc_180008322
0x180008168  mov     eax, [r14]
0x18000816b  mov     rdx, rbp; SourceString
0x18000816e  mov     rcx, rbx; DestinationString
0x180008171  mov     [rbx+40h], eax
0x180008174  call    cs:__imp_RtlInitUnicodeString
0x18000817a  lea     rcx, [rbx+10h]; DestinationString
0x18000817e  mov     rdx, r12; SourceString
0x180008181  call    cs:__imp_RtlInitUnicodeString
0x180008187  mov     rax, [rsp+0C8h+arg_30]
0x18000818f  test    rax, rax
0x180008192  jz      loc_1800082CF
0x180008198  mov     eax, [rax]
0x18000819a  mov     r15d, dword ptr [rsp+0C8h+uBytes]
0x1800081a2  xor     edi, edi
0x1800081a4  mov     [rsp+0C8h+OldValue], eax
0x1800081ab  mov     [rbx+5Ch], eax
0x1800081ae  test    byte ptr [rbx+48h], 1
0x1800081b2  mov     rax, cs:qword_18005CDB8
0x1800081b9  mov     rsi, [r14+8]
0x1800081bd  mov     qword ptr [rsp+0C8h+var_60], rax
0x1800081c2  jz      loc_1800082D4
0x1800081c8  cmp     r15d, r13d
0x1800081cb  cmovbe  r13d, r15d
0x1800081cf  mov     [rsi+8], rdi
0x1800081d3  xor     eax, eax
0x1800081d5  mov     [rsp+0C8h+var_64], eax
0x1800081d9  cmp     eax, 5
0x1800081dc  jnb     short loc_180008243
0x1800081de  mov     rcx, [rsi+8]; hMem
0x1800081e2  test    rcx, rcx
0x1800081e5  jnz     loc_180008432
0x1800081eb  mov     edx, r13d; uBytes
0x1800081ee  mov     ecx, 40h ; '@'; uFlags
0x1800081f3  call    cs:__imp_LocalAlloc
0x1800081f9  mov     [rsi+8], rax
0x1800081fd  test    rax, rax
0x180008200  jz      loc_18000832C
0x180008206  mov     eax, [rsp+0C8h+OldValue]
0x18000820d  mov     r8, rbx; hMem
0x180008210  mov     rcx, qword ptr [rsp+0C8h+var_60]; FileHandle
0x180008215  mov     edx, 146027h; FsControlCode
0x18000821a  mov     [rbx+5Ch], eax
0x18000821d  mov     r9, [rsi+8]; OutputBuffer
0x180008221  mov     dword ptr [rsp+0C8h+SecurityDescriptor], r13d; ULONG
0x180008226  call    SsServerFsControlCommon
0x18000822b  mov     edi, eax
0x18000822d  cmp     eax, 84Bh
0x180008232  jz      loc_1800082FB
0x180008238  cmp     eax, 0EAh
0x18000823d  jz      loc_1800082FB
0x180008243  mov     rcx, [rsi+8]; hMem
0x180008247  test    rcx, rcx
0x18000824a  jz      short loc_180008256
0x18000824c  cmp     dword ptr [rbx+50h], 0
0x180008250  jz      loc_1800082E8
0x180008256  mov     rcx, [r14+8]
0x18000825a  mov     eax, [rbx+50h]
0x18000825d  mov     [rcx], eax
0x18000825f  mov     rcx, [rsp+0C8h+arg_28]
0x180008267  test    rcx, rcx
0x18000826a  jz      short loc_180008271
0x18000826c  mov     eax, [rbx+54h]
0x18000826f  mov     [rcx], eax
0x180008271  cmp     dword ptr [rbx+50h], 0
0x180008275  ja      loc_18000843D
0x18000827b  cmp     dword ptr [rbx+54h], 0
0x18000827f  jnz     short loc_180008295
0x180008281  test    r12, r12
0x180008284  jnz     loc_180008458
0x18000828a  test    rbp, rbp
0x18000828d  mov     eax, 908h
0x180008292  cmovnz  edi, eax
0x180008295  mov     rcx, rbx; hMem
0x180008298  call    cs:__imp_LocalFree
0x18000829e  mov     eax, edi
0x1800082a0  mov     rbx, [rsp+0C8h+arg_0]
0x1800082a8  mov     rsi, [rsp+0C8h+arg_10]
0x1800082b0  mov     r15, [rsp+0C8h+var_28]
0x1800082b8  mov     rdi, [rsp+0C8h+arg_18]
0x1800082c0  add     rsp, 0A8h
0x1800082c7  pop     r14
0x1800082c9  pop     r13
0x1800082cb  pop     r12
0x1800082cd  pop     rbp
0x1800082ce  retn
0x1800082cf  jmp     loc_18000819A
0x1800082d4  mov     ecx, 2000h
0x1800082d9  mov     r13d, r15d
0x1800082dc  cmp     r15d, ecx
0x1800082df  cmova   r13d, ecx
0x1800082e3  jmp     loc_1800081CF
0x1800082e8  call    cs:__imp_LocalFree
0x1800082ee  mov     qword ptr [rsi+8], 0
0x1800082f6  jmp     loc_180008256
0x1800082fb  cmp     r13d, r15d
0x1800082fe  jnb     loc_180008243
0x180008304  mov     ecx, [rbx+58h]
0x180008307  mov     r13d, r15d
0x18000830a  mov     eax, [rsp+0C8h+var_64]
0x18000830e  add     ecx, 400h
0x180008314  cmp     ecx, r15d
0x180008317  cmovb   r13d, ecx
0x18000831b  inc     eax
0x18000831d  jmp     loc_1800081D5
0x180008322  mov     eax, 8
0x180008327  jmp     loc_1800082A0
0x18000832c  mov     edi, 8
0x180008331  jmp     loc_180008243
0x180008336  mov     rcx, r13
0x180008339  mov     rax, rbp
0x18000833c  nop     dword ptr [rax+00h]
0x180008340  cmp     word ptr [rax], 0
0x180008344  jz      loc_180007FC7
0x18000834a  add     rax, 2
0x18000834e  sub     rcx, 1
0x180008352  jnz     short loc_180008340
0x180008354  mov     eax, 57h ; 'W'
0x180008359  add     rsp, 0A8h
0x180008360  pop     r14
0x180008362  pop     r13
0x180008364  pop     r12
0x180008366  pop     rbp
0x180008367  retn
0x180008368  mov     eax, 5
0x18000836d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008374  lea     rdx, WPP_GLOBAL_Control
0x18000837b  cmp     rcx, rdx
0x18000837e  jz      short loc_180008389
0x180008380  test    dword ptr [rcx+1Ch], 200h
0x180008387  jnz     short loc_1800083D7
0x180008389  mov     eax, 5
0x18000838e  jmp     loc_1800082A0
0x180008393  xor     r8d, r8d; pcchLength
0x180008396  mov     rdx, r13; cchMax
0x180008399  mov     rcx, r12; psz
0x18000839c  call    StringCchLengthW
0x1800083a1  test    eax, eax
0x1800083a3  jnz     short loc_180008354
0x1800083a5  jmp     loc_180007FD0
0x1800083aa  test    eax, eax
0x1800083ac  jz      loc_180008005
0x1800083b2  sub     eax, 1
0x1800083b5  jz      short loc_1800083CD
0x1800083b7  sub     eax, 1
0x1800083ba  jz      short loc_1800083CD
0x1800083bc  cmp     eax, 1F4h
0x1800083c1  jz      short loc_1800083CD
0x1800083c3  mov     eax, 7Ch ; '|'
0x1800083c8  jmp     loc_1800082B8
0x1800083cd  mov     edi, 2
0x1800083d2  jmp     loc_18000800A
0x1800083d7  cmp     byte ptr [rcx+19h], 1
0x1800083db  jb      short loc_180008389
0x1800083dd  mov     r9, cs:SsSessionSecurityObject
0x1800083e4  mov     rcx, [rcx+10h]
0x1800083e8  mov     [rsp+0C8h+DesiredAccess], eax
0x1800083ec  mov     dword ptr [rsp+0C8h+SecurityDescriptor], edi
0x1800083f0  call    WPP_SF_SLl
0x1800083f5  jmp     short loc_180008389
0x1800083f7  xor     eax, eax
0x1800083f9  cmp     [rbp+0], ax
0x1800083fd  cmovz   rbp, rax
0x180008401  jmp     loc_18000813A
0x180008406  xor     eax, eax
0x180008408  cmp     [r12], ax
0x18000840d  cmovz   r12, rax
0x180008411  jmp     loc_180008143
0x180008416  cmp     word ptr [rbp+0], 5Ch ; '\'
0x18000841b  jnz     short loc_180008428
0x18000841d  cmp     word ptr [rbp+2], 5Ch ; '\'
0x180008422  jz      loc_18000814C
0x180008428  mov     eax, 92Fh
0x18000842d  jmp     loc_1800082A0
0x180008432  call    cs:__imp_LocalFree
0x180008438  jmp     loc_1800081EB
0x18000843d  mov     rcx, [rsp+0C8h+arg_30]
0x180008445  test    rcx, rcx
0x180008448  jz      loc_180008295
0x18000844e  mov     eax, [rbx+5Ch]
0x180008451  mov     [rcx], eax
0x180008453  jmp     loc_180008295
0x180008458  mov     edi, 8ADh
0x18000845d  jmp     loc_180008295
```
