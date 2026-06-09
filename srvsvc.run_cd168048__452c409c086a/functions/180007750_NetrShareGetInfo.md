# NetrShareGetInfo

- ea: `0x180007750`
- end: `0x180007bd6`
- name: `NetrShareGetInfo`
- size: `1158`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007750`
- `0x180008de0`
- `0x180028c24`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800078d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000796d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800078d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000796d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800079cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007bb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007bc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800079cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007bb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007bc6`
- `ntdll!RtlInitUnicodeString` at `0x180007804`
- `ntdll!RtlInitUnicodeString` at `0x180007815`
- `ntdll!RtlInitUnicodeString` at `0x180007823`
- `ntdll!RtlInitUnicodeString` at `0x180007901`
- `ntdll!RtlInitUnicodeString` at `0x18000790e`
- `ntdll!RtlInitUnicodeString` at `0x180007804`
- `ntdll!RtlInitUnicodeString` at `0x180007815`
- `ntdll!RtlInitUnicodeString` at `0x180007823`
- `ntdll!RtlInitUnicodeString` at `0x180007901`
- `ntdll!RtlInitUnicodeString` at `0x18000790e`
- `ntdll!RtlAdjustPrivilege` at `0x18000783b`
- `ntdll!RtlAdjustPrivilege` at `0x18000783b`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000789b`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000789b`
- `RPCRT4!RpcImpersonateClient` at `0x180007843`
- `RPCRT4!RpcImpersonateClient` at `0x180007843`
- `RPCRT4!RpcRevertToSelf` at `0x1800078a3`
- `RPCRT4!RpcRevertToSelf` at `0x1800078a3`

## pseudocode

```c
__int64 __fastcall NetrShareGetInfo(PCWSTR SourceString, PCWSTR a2, unsigned int a3, _QWORD *a4)
{
  ACCESS_MASK DesiredAccess; // r14d
  const WCHAR *v9; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // r12
  struct _GENERIC_MAPPING *GenericMapping; // r15
  int v12; // edx
  unsigned int v13; // ebx
  int v14; // r8d
  NTSTATUS v15; // ebx
  struct _UNICODE_STRING *v16; // rax
  struct _UNICODE_STRING *v17; // rbx
  int v18; // r14d
  HLOCAL v19; // rsi
  void *v20; // r15
  DWORD LastError; // edi
  unsigned int v22; // r12d
  ULONG v23; // ebp
  DWORD v24; // eax
  unsigned __int8 GenerateOnClose[4]; // [rsp+60h] [rbp-68h] BYREF
  int AccessStatus; // [rsp+64h] [rbp-64h] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-60h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+70h] [rbp-58h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+80h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-38h] BYREF
  int OldValue; // [rsp+D8h] [rbp+10h] BYREF

  if ( !a2 || !*a2 )
    return 87;
  if ( a3 == 1005 )
    goto LABEL_4;
  if ( a3 > 0x1F5 )
  {
    if ( a3 == 502 || a3 == 503 )
      goto LABEL_50;
    return 124;
  }
  if ( a3 == 501 || a3 < 2 )
  {
LABEL_4:
    DesiredAccess = 1;
    goto LABEL_5;
  }
  if ( a3 != 2 )
    return 124;
LABEL_50:
  DesiredAccess = 2;
LABEL_5:
  v9 = SsSharePrintSecurityObject;
  SecurityDescriptor = qword_18005C6F0;
  GenericMapping = qword_18005C6E8;
  LOBYTE(OldValue) = 0;
  DestinationString = 0;
  GrantedAccess = 0;
  ObjectTypeName = 0;
  GenerateOnClose[0] = 0;
  ObjectName = 0;
  AccessStatus = 0;
  RtlInitUnicodeString(&DestinationString, L"Server");
  RtlInitUnicodeString(&ObjectTypeName, v9);
  RtlInitUnicodeString(&ObjectName, a2);
  RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)&OldValue);
  v13 = RpcImpersonateClient(0);
  if ( v13 )
    goto LABEL_41;
  v15 = NtAccessCheckAndAuditAlarm(
          &DestinationString,
          0,
          &ObjectTypeName,
          &ObjectName,
          SecurityDescriptor,
          DesiredAccess,
          GenericMapping,
          0,
          &GrantedAccess,
          &AccessStatus,
          GenerateOnClose);
  RpcRevertToSelf();
  if ( v15 < 0 || AccessStatus )
  {
    v13 = 5;
LABEL_41:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_SLl(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v14, (_DWORD)SsSharePrintSecurityObject, DesiredAccess, v13);
    }
    return v13;
  }
  if ( a3 > 2 && a3 - 501 > 2 && a3 != 505 && a3 != 1005 )
    return 124;
  if ( SourceString && *SourceString == 92 && SourceString[1] == 92 )
    SourceString += 2;
  v16 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x60u);
  v17 = v16;
  if ( !v16 )
    return 8;
  v18 = 0;
  *(_DWORD *)&v16[4].Length = a3;
  HIDWORD(v16[5].Buffer) = 0;
  LODWORD(v16[4].Buffer) = 1;
  RtlInitUnicodeString(v16, a2);
  RtlInitUnicodeString(v17 + 1, SourceString);
  v19 = 0;
  v20 = (void *)((__int64 (__fastcall *)(_QWORD))qword_18005E540)(0);
  if ( v20 )
  {
    LastError = 0;
    v22 = 0;
    OldValue = HIDWORD(v17[5].Buffer);
    v23 = 1024;
    if ( ((__int64)v17[4].Buffer & 1) == 0 )
      v23 = 0x2000;
    while ( v22 < 5 )
    {
      if ( v19 )
        LocalFree(v19);
      v19 = LocalAlloc(0x40u, v23);
      if ( !v19 )
      {
        LastError = 8;
        goto LABEL_24;
      }
      HIDWORD(v17[5].Buffer) = OldValue;
      v24 = SsServerFsControlCommon(v20, 0x146033u, v17, v19, v23);
      LastError = v24;
      if ( v24 != 2123 && v24 != 234 || v23 == -1 )
        goto LABEL_20;
      v23 = -1;
      if ( LODWORD(v17[5].Buffer) != -1025 )
        v23 = LODWORD(v17[5].Buffer) + 1024;
      ++v22;
    }
    if ( !v19 )
      goto LABEL_22;
LABEL_20:
    if ( !*(_DWORD *)&v17[5].Length )
    {
      LocalFree(v19);
      v19 = 0;
    }
LABEL_22:
    if ( !LastError || LastError == 234 )
      v18 = *(_DWORD *)&v17[5].Length;
LABEL_24:
    LocalFree(v17);
    ((void (__fastcall *)(void *))qword_18005E548)(v20);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 2 )
      LastError = 2114;
    LocalFree(v17);
  }
  if ( LastError )
  {
    if ( v19 )
      LocalFree(v19);
    return LastError;
  }
  if ( v18 )
  {
    *a4 = v19;
    return 0;
  }
  else
  {
    if ( v19 )
      LocalFree(v19);
    return 2310;
  }
}

```

## disassembly

```asm
0x180007750  push    rbp
0x180007752  push    rsi
0x180007753  push    rdi
0x180007754  push    r13
0x180007756  sub     rsp, 0A8h
0x18000775d  mov     r13, r9
0x180007760  mov     edi, r8d
0x180007763  mov     rsi, rdx
0x180007766  mov     rbp, rcx
0x180007769  test    rdx, rdx
0x18000776c  jz      loc_180007A98
0x180007772  cmp     word ptr [rdx], 0
0x180007776  jz      loc_180007A98
0x18000777c  mov     [rsp+0C8h+arg_18], r14
0x180007784  cmp     r8d, 3EDh
0x18000778b  jnz     loc_180007AEA
0x180007791  mov     r14d, 1
0x180007797  xor     eax, eax
0x180007799  mov     [rsp+0C8h+arg_0], rbx
0x1800077a1  mov     rbx, cs:SsSharePrintSecurityObject
0x1800077a8  lea     rdx, SourceName; "Server"
0x1800077af  xorps   xmm0, xmm0
0x1800077b2  mov     [rsp+0C8h+arg_10], r12
0x1800077ba  mov     r12, cs:qword_18005C6F0
0x1800077c1  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1800077c9  xorps   xmm1, xmm1
0x1800077cc  mov     [rsp+0C8h+var_28], r15
0x1800077d4  mov     r15, cs:qword_18005C6E8
0x1800077db  mov     byte ptr [rsp+0C8h+OldValue], 0
0x1800077e3  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x1800077eb  mov     [rsp+0C8h+var_60], eax
0x1800077ef  movups  xmmword ptr [rsp+0C8h+ObjectTypeName.Length], xmm1
0x1800077f7  mov     [rsp+0C8h+var_68], al
0x1800077fb  movups  xmmword ptr [rsp+0C8h+ObjectName.Length], xmm0
0x180007800  mov     [rsp+0C8h+var_64], eax
0x180007804  call    cs:__imp_RtlInitUnicodeString
0x18000780a  mov     rdx, rbx; SourceString
0x18000780d  lea     rcx, [rsp+0C8h+ObjectTypeName]; DestinationString
0x180007815  call    cs:__imp_RtlInitUnicodeString
0x18000781b  mov     rdx, rsi; SourceString
0x18000781e  lea     rcx, [rsp+0C8h+ObjectName]; DestinationString
0x180007823  call    cs:__imp_RtlInitUnicodeString
0x180007829  lea     r9, [rsp+0C8h+OldValue]; OldValue
0x180007831  xor     r8d, r8d; ForThread
0x180007834  mov     dl, 1; NewValue
0x180007836  mov     ecx, 15h; Privilege
0x18000783b  call    cs:__imp_RtlAdjustPrivilege
0x180007841  xor     ecx, ecx; BindingHandle
0x180007843  call    cs:__imp_RpcImpersonateClient
0x180007849  mov     ebx, eax
0x18000784b  test    eax, eax
0x18000784d  jnz     loc_180007AB9
0x180007853  lea     rax, [rsp+0C8h+var_68]
0x180007858  xor     edx, edx; HandleId
0x18000785a  mov     [rsp+0C8h+GenerateOnClose], rax; GenerateOnClose
0x18000785f  lea     r9, [rsp+0C8h+ObjectName]; ObjectName
0x180007864  lea     rax, [rsp+0C8h+var_64]
0x180007869  mov     [rsp+0C8h+AccessStatus], rax; AccessStatus
0x18000786e  lea     r8, [rsp+0C8h+ObjectTypeName]; ObjectTypeName
0x180007876  lea     rax, [rsp+0C8h+var_60]
0x18000787b  mov     [rsp+0C8h+GrantedAccess], rax; GrantedAccess
0x180007880  lea     rcx, [rsp+0C8h+DestinationString]; SubsystemName
0x180007888  mov     [rsp+0C8h+ObjectCreation], bl; ObjectCreation
0x18000788c  mov     [rsp+0C8h+GenericMapping], r15; GenericMapping
0x180007891  mov     [rsp+0C8h+DesiredAccess], r14d; DesiredAccess
0x180007896  mov     [rsp+0C8h+SecurityDescriptor], r12; SecurityDescriptor
0x18000789b  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x1800078a1  mov     ebx, eax
0x1800078a3  call    cs:__imp_RpcRevertToSelf
0x1800078a9  test    ebx, ebx
0x1800078ab  js      loc_180007AB4
0x1800078b1  cmp     [rsp+0C8h+var_64], 0
0x1800078b6  jnz     loc_180007AB4
0x1800078bc  cmp     edi, 2
0x1800078bf  ja      loc_180007A33
0x1800078c5  test    rbp, rbp
0x1800078c8  jnz     loc_180007B54
0x1800078ce  mov     edx, 60h ; '`'; uBytes
0x1800078d3  mov     ecx, 40h ; '@'; uFlags
0x1800078d8  call    cs:__imp_LocalAlloc
0x1800078de  mov     rbx, rax
0x1800078e1  test    rax, rax
0x1800078e4  jz      loc_180007B73
0x1800078ea  xor     r14d, r14d
0x1800078ed  mov     [rax+40h], edi
0x1800078f0  mov     rdx, rsi; SourceString
0x1800078f3  mov     [rax+5Ch], r14d
0x1800078f7  mov     rcx, rax; DestinationString
0x1800078fa  mov     dword ptr [rax+48h], 1
0x180007901  call    cs:__imp_RtlInitUnicodeString
0x180007907  lea     rcx, [rbx+10h]; DestinationString
0x18000790b  mov     rdx, rbp; SourceString
0x18000790e  call    cs:__imp_RtlInitUnicodeString
0x180007914  mov     rax, cs:qword_18005E540
0x18000791b  xor     ecx, ecx
0x18000791d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007922  xor     esi, esi
0x180007924  mov     r15, rax
0x180007927  test    rax, rax
0x18000792a  jz      loc_180007B7A
0x180007930  mov     eax, [rbx+5Ch]
0x180007933  xor     edi, edi
0x180007935  xor     r12d, r12d
0x180007938  mov     [rsp+0C8h+OldValue], eax
0x18000793f  test    byte ptr [rbx+48h], 1
0x180007943  mov     ebp, 400h
0x180007948  mov     eax, 2000h
0x18000794d  cmovz   ebp, eax
0x180007950  mov     rax, rsi
0x180007953  cmp     r12d, 5
0x180007957  jnb     loc_180007ADC
0x18000795d  test    rsi, rsi
0x180007960  jnz     loc_180007B9B
0x180007966  mov     edx, ebp; uBytes
0x180007968  mov     ecx, 40h ; '@'; uFlags
0x18000796d  call    cs:__imp_LocalAlloc
0x180007973  mov     rsi, rax
0x180007976  test    rax, rax
0x180007979  jz      loc_180007AAA
0x18000797f  mov     eax, [rsp+0C8h+OldValue]
0x180007986  mov     r9, rsi; OutputBuffer
0x180007989  mov     r8, rbx; hMem
0x18000798c  mov     [rbx+5Ch], eax
0x18000798f  mov     edx, 146033h; FsControlCode
0x180007994  mov     dword ptr [rsp+0C8h+SecurityDescriptor], ebp; ULONG
0x180007998  mov     rcx, r15; FileHandle
0x18000799b  call    SsServerFsControlCommon
0x1800079a0  mov     edi, eax
0x1800079a2  cmp     eax, 84Bh
0x1800079a7  jz      loc_180007A64
0x1800079ad  cmp     eax, 0EAh
0x1800079b2  jz      loc_180007A64
0x1800079b8  cmp     [rbx+50h], r14d
0x1800079bc  jz      short loc_180007A26
0x1800079be  test    edi, edi
0x1800079c0  jnz     loc_180007A87
0x1800079c6  mov     r14d, [rbx+50h]
0x1800079ca  mov     rcx, rbx; hMem
0x1800079cd  call    cs:__imp_LocalFree
0x1800079d3  mov     rax, cs:qword_18005E548
0x1800079da  mov     rcx, r15
0x1800079dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e2  test    edi, edi
0x1800079e4  jnz     loc_180007BA9
0x1800079ea  test    r14d, r14d
0x1800079ed  jz      loc_180007BBE
0x1800079f3  mov     [r13+0], rsi
0x1800079f7  xor     eax, eax
0x1800079f9  mov     rbx, [rsp+0C8h+arg_0]
0x180007a01  mov     r12, [rsp+0C8h+arg_10]
0x180007a09  mov     r15, [rsp+0C8h+var_28]
0x180007a11  mov     r14, [rsp+0C8h+arg_18]
0x180007a19  add     rsp, 0A8h
0x180007a20  pop     r13
0x180007a22  pop     rdi
0x180007a23  pop     rsi
0x180007a24  pop     rbp
0x180007a25  retn
0x180007a26  mov     rcx, rsi; hMem
0x180007a29  call    cs:__imp_LocalFree
0x180007a2f  xor     esi, esi
0x180007a31  jmp     short loc_1800079BE
0x180007a33  lea     eax, [rdi-1F5h]
0x180007a39  cmp     eax, 2
0x180007a3c  jbe     loc_1800078C5
0x180007a42  cmp     edi, 1F9h
0x180007a48  jz      loc_1800078C5
0x180007a4e  cmp     edi, 3EDh
0x180007a54  jz      loc_1800078C5
0x180007a5a  mov     edi, 7Ch ; '|'
0x180007a5f  jmp     loc_180007BB7
0x180007a64  cmp     ebp, 0FFFFFFFFh
0x180007a67  jnb     loc_1800079B8
0x180007a6d  mov     eax, [rbx+58h]
0x180007a70  mov     ebp, 0FFFFFFFFh
0x180007a75  add     eax, 400h
0x180007a7a  cmp     eax, ebp
0x180007a7c  cmovb   ebp, eax
0x180007a7f  inc     r12d
0x180007a82  jmp     loc_180007950
0x180007a87  cmp     edi, 0EAh
0x180007a8d  jz      loc_1800079C6
0x180007a93  jmp     loc_1800079CA
0x180007a98  mov     eax, 57h ; 'W'
0x180007a9d  add     rsp, 0A8h
0x180007aa4  pop     r13
0x180007aa6  pop     rdi
0x180007aa7  pop     rsi
0x180007aa8  pop     rbp
0x180007aa9  retn
0x180007aaa  mov     edi, 8
0x180007aaf  jmp     loc_1800079CA
0x180007ab4  mov     ebx, 5
0x180007ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ac0  lea     rax, WPP_GLOBAL_Control
0x180007ac7  cmp     rcx, rax
0x180007aca  jz      short loc_180007AD5
0x180007acc  test    dword ptr [rcx+1Ch], 200h
0x180007ad3  jnz     short loc_180007B33
0x180007ad5  mov     eax, ebx
0x180007ad7  jmp     loc_1800079F9
0x180007adc  test    rax, rax
0x180007adf  jnz     loc_1800079B8
0x180007ae5  jmp     loc_1800079BE
0x180007aea  cmp     edi, 1F5h
0x180007af0  ja      short loc_180007B1B
0x180007af2  jz      loc_180007791
0x180007af8  mov     eax, edi
0x180007afa  test    edi, edi
0x180007afc  jz      loc_180007791
0x180007b02  sub     eax, 1
0x180007b05  jz      loc_180007791
0x180007b0b  cmp     eax, 1
0x180007b0e  jnz     short loc_180007B29
0x180007b10  mov     r14d, 2
0x180007b16  jmp     loc_180007797
0x180007b1b  mov     eax, edi
0x180007b1d  sub     eax, 1F6h
0x180007b22  jz      short loc_180007B10
0x180007b24  cmp     eax, 1
0x180007b27  jz      short loc_180007B10
0x180007b29  mov     eax, 7Ch ; '|'
0x180007b2e  jmp     loc_180007A11
0x180007b33  cmp     byte ptr [rcx+19h], 1
0x180007b37  jb      short loc_180007AD5
0x180007b39  mov     r9, cs:SsSharePrintSecurityObject
0x180007b40  mov     rcx, [rcx+10h]
0x180007b44  mov     [rsp+0C8h+DesiredAccess], ebx
0x180007b48  mov     dword ptr [rsp+0C8h+SecurityDescriptor], r14d
0x180007b4d  call    WPP_SF_SLl
0x180007b52  jmp     short loc_180007AD5
0x180007b54  cmp     word ptr [rbp+0], 5Ch ; '\'
0x180007b59  jnz     loc_1800078CE
0x180007b5f  cmp     word ptr [rbp+2], 5Ch ; '\'
0x180007b64  jnz     loc_1800078CE
0x180007b6a  add     rbp, 4
0x180007b6e  jmp     loc_1800078CE
0x180007b73  mov     edi, 8
0x180007b78  jmp     short loc_180007BB7
0x180007b7a  call    cs:__imp_GetLastError
0x180007b80  mov     edi, eax
0x180007b82  mov     rcx, rbx; hMem
0x180007b85  cmp     edi, 2
0x180007b88  mov     eax, 842h
0x180007b8d  cmovz   edi, eax
0x180007b90  call    cs:__imp_LocalFree
0x180007b96  jmp     loc_1800079E2
0x180007b9b  mov     rcx, rsi; hMem
0x180007b9e  call    cs:__imp_LocalFree
0x180007ba4  jmp     loc_180007966
0x180007ba9  test    rsi, rsi
0x180007bac  jz      short loc_180007BB7
0x180007bae  mov     rcx, rsi; hMem
0x180007bb1  call    cs:__imp_LocalFree
0x180007bb7  mov     eax, edi
0x180007bb9  jmp     loc_1800079F9
0x180007bbe  test    rsi, rsi
0x180007bc1  jz      short loc_180007BCC
0x180007bc3  mov     rcx, rsi; hMem
0x180007bc6  call    cs:__imp_LocalFree
0x180007bcc  mov     eax, 906h
0x180007bd1  jmp     loc_1800079F9
```
