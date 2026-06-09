# SampLookupAccountRidRegistry(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,long,ulong *,_SID_NAME_USE *)

- ea: `0x1800049a0`
- end: `0x180004d14`
- name: `?SampLookupAccountRidRegistry@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@JPEAKPEAW4_SID_NAME_USE@@@Z`
- size: `884`
- prototype: `int __high(enum _SAMP_OBJECT_TYPE, struct _UNICODE_STRING *, int, unsigned int *, enum _SID_NAME_USE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003d40`
- `0x1800ac954`

## callees

- `0x1800049a0`
- `0x180004fa0`
- `0x1800213d0`
- `0x180027e24`

## import_xrefs

- `ntdll!NtClose` at `0x180004ab3`
- `ntdll!NtClose` at `0x180004bae`
- `ntdll!NtClose` at `0x180004c9c`
- `ntdll!NtClose` at `0x180004ab3`
- `ntdll!NtClose` at `0x180004bae`
- `ntdll!NtClose` at `0x180004c9c`
- `ntdll!RtlpNtQueryValueKey` at `0x180004aa7`
- `ntdll!RtlpNtQueryValueKey` at `0x180004ba2`
- `ntdll!RtlpNtQueryValueKey` at `0x180004c90`
- `ntdll!RtlpNtQueryValueKey` at `0x180004aa7`
- `ntdll!RtlpNtQueryValueKey` at `0x180004ba2`
- `ntdll!RtlpNtQueryValueKey` at `0x180004c90`
- `ntdll!RtlpNtOpenKey` at `0x180004a6d`
- `ntdll!RtlpNtOpenKey` at `0x180004b68`
- `ntdll!RtlpNtOpenKey` at `0x180004c4c`
- `ntdll!RtlpNtOpenKey` at `0x180004a6d`
- `ntdll!RtlpNtOpenKey` at `0x180004b68`
- `ntdll!RtlpNtOpenKey` at `0x180004c4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c5d`

## pseudocode

```c
__int64 __fastcall SampLookupAccountRidRegistry(int a1, __int64 a2, NTSTATUS a3, ULONG *a4, _DWORD *a5)
{
  NTSTATUS v9; // edi
  PUNICODE_STRING v10; // rcx
  __int64 v11; // rdx
  HANDLE v12; // rcx
  unsigned int v13; // ebx
  PUNICODE_STRING v14; // rcx
  __int64 v15; // rdx
  HANDLE v17; // rcx
  HANDLE v18; // rcx
  HANDLE KeyHandle; // [rsp+30h] [rbp-50h] BYREF
  ULONG v20[2]; // [rsp+38h] [rbp-48h] BYREF
  HLOCAL hMem[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG DataLength; // [rsp+B0h] [rbp+30h] BYREF

  KeyHandle = 0;
  DataLength = 0;
  *(_QWORD *)v20 = 0;
  *(_OWORD *)hMem = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a1 == 2 || (v9 = -1073741772, a1 == 5) )
  {
    v9 = SampBuildAccountKeyName(2, hMem, a2);
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v11 = 100;
LABEL_31:
        WPP_SF_Dd(v10[3].Buffer, v11, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v9, v9);
        return (unsigned int)v9;
      }
      return (unsigned int)v9;
    }
    ObjectAttributes.RootDirectory = SampKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)hMem;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
    SampFreeUnicodeString(hMem);
    if ( v9 >= 0 )
    {
      v12 = KeyHandle;
      DataLength = 0;
      *a5 = 2;
      v13 = RtlpNtQueryValueKey(v12, a4, 0, &DataLength, (ULONG)v20);
      NtClose(KeyHandle);
      v14 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return v13;
      v15 = 101;
      goto LABEL_9;
    }
  }
  if ( ((a1 - 3) & 0xFFFFFFFD) != 0 )
  {
LABEL_18:
    if ( (unsigned int)(a1 - 4) > 1 )
      goto LABEL_27;
    v13 = SampBuildAccountKeyName(4, hMem, a2);
    if ( (v13 & 0x80000000) != 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return v13;
      v15 = 104;
      goto LABEL_9;
    }
    ObjectAttributes.RootDirectory = SampKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)hMem;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      hMem[1] = 0;
    }
    if ( v9 < 0 )
    {
LABEL_27:
      if ( v9 == -1073741772 )
        v9 = a3;
      v10 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)v9;
      v11 = 106;
      goto LABEL_31;
    }
    v18 = KeyHandle;
    DataLength = 0;
    *a5 = 1;
    v13 = RtlpNtQueryValueKey(v18, a4, 0, &DataLength, (ULONG)v20);
    NtClose(KeyHandle);
    v14 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return v13;
    v15 = 105;
LABEL_9:
    WPP_SF_Dd(v14[3].Buffer, v15, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v13, v13);
    return v13;
  }
  v9 = SampBuildAccountKeyName(3, hMem, a2);
  if ( v9 >= 0 )
  {
    ObjectAttributes.RootDirectory = SampKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)hMem;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
    SampFreeUnicodeString(hMem);
    if ( v9 >= 0 )
    {
      v17 = KeyHandle;
      DataLength = 0;
      *a5 = 4;
      v13 = RtlpNtQueryValueKey(v17, a4, 0, &DataLength, (ULONG)v20);
      NtClose(KeyHandle);
      v14 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return v13;
      v15 = 103;
      goto LABEL_9;
    }
    goto LABEL_18;
  }
  v10 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v11 = 102;
    goto LABEL_31;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800049a0  mov     [rsp-28h+arg_8], rbx
0x1800049a5  mov     [rsp-28h+arg_10], rsi
0x1800049aa  push    rbp
0x1800049ab  push    rdi
0x1800049ac  push    r12
0x1800049ae  push    r14
0x1800049b0  push    r15
0x1800049b2  mov     rbp, rsp
0x1800049b5  sub     rsp, 80h
0x1800049bc  xor     r12d, r12d
0x1800049bf  xorps   xmm1, xmm1
0x1800049c2  mov     [rbp+KeyHandle], r12
0x1800049c6  xorps   xmm0, xmm0
0x1800049c9  mov     [rbp+DataLength], r12d
0x1800049cd  mov     r14, r9
0x1800049d0  mov     qword ptr [rbp+var_48], r12
0x1800049d4  mov     r15d, r8d
0x1800049d7  mov     rsi, rdx
0x1800049da  mov     ebx, ecx
0x1800049dc  movups  xmmword ptr [rbp+hMem], xmm0
0x1800049e0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1800049e4  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1800049e8  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1800049ec  cmp     ecx, 2
0x1800049ef  jz      short loc_1800049FF
0x1800049f1  mov     edi, 0C0000034h
0x1800049f6  cmp     ecx, 5
0x1800049f9  jnz     loc_180004AEC
0x1800049ff  mov     r8, rsi
0x180004a02  lea     rdx, [rbp+hMem]
0x180004a06  mov     ecx, 2
0x180004a0b  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x180004a10  mov     edi, eax
0x180004a12  test    eax, eax
0x180004a14  jns     short loc_180004A34
0x180004a16  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a1d  test    dword ptr [rcx+44h], 20000h
0x180004a24  jz      loc_180004CF6
0x180004a2a  mov     edx, 64h ; 'd'
0x180004a2f  jmp     loc_180004CDF
0x180004a34  mov     rax, cs:SampKey
0x180004a3b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180004a3f  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180004a43  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180004a47  lea     rax, [rbp+hMem]
0x180004a4b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180004a52  xorps   xmm0, xmm0
0x180004a55  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180004a59  xor     r9d, r9d; Unused
0x180004a5c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180004a63  mov     edx, 20019h; DesiredAccess
0x180004a68  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180004a6d  call    cs:__imp_RtlpNtOpenKey
0x180004a73  lea     rcx, [rbp+hMem]
0x180004a77  mov     edi, eax
0x180004a79  call    SampFreeUnicodeString
0x180004a7e  test    edi, edi
0x180004a80  js      short loc_180004AEC
0x180004a82  mov     rax, [rbp+arg_20]
0x180004a86  lea     r9, [rbp+DataLength]; DataLength
0x180004a8a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180004a8e  xor     r8d, r8d; Data
0x180004a91  mov     rdx, r14; Type
0x180004a94  mov     [rbp+DataLength], r12d
0x180004a98  mov     dword ptr [rax], 2
0x180004a9e  lea     rax, [rbp+var_48]
0x180004aa2  mov     qword ptr [rsp+80h+Unused], rax; Unused
0x180004aa7  call    cs:__imp_RtlpNtQueryValueKey
0x180004aad  mov     rcx, [rbp+KeyHandle]; Handle
0x180004ab1  mov     ebx, eax
0x180004ab3  call    cs:__imp_NtClose
0x180004ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ac0  test    dword ptr [rcx+44h], 20000h
0x180004ac7  jz      short loc_180004AE5
0x180004ac9  mov     edx, 65h ; 'e'
0x180004ace  mov     rcx, [rcx+38h]
0x180004ad2  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180004ad9  mov     r9d, ebx
0x180004adc  mov     [rsp+80h+Unused], ebx
0x180004ae0  call    WPP_SF_Dd
0x180004ae5  mov     eax, ebx
0x180004ae7  jmp     loc_180004CF8
0x180004aec  lea     eax, [rbx-3]
0x180004aef  test    eax, 0FFFFFFFDh
0x180004af4  jnz     loc_180004BD2
0x180004afa  mov     r8, rsi
0x180004afd  lea     rdx, [rbp+hMem]
0x180004b01  mov     ecx, 3
0x180004b06  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x180004b0b  mov     edi, eax
0x180004b0d  test    eax, eax
0x180004b0f  jns     short loc_180004B2F
0x180004b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b18  test    dword ptr [rcx+44h], 20000h
0x180004b1f  jz      loc_180004CF6
0x180004b25  mov     edx, 66h ; 'f'
0x180004b2a  jmp     loc_180004CDF
0x180004b2f  mov     rax, cs:SampKey
0x180004b36  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180004b3a  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180004b3e  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180004b42  lea     rax, [rbp+hMem]
0x180004b46  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180004b4d  xorps   xmm0, xmm0
0x180004b50  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180004b54  xor     r9d, r9d; Unused
0x180004b57  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180004b5e  mov     edx, 20019h; DesiredAccess
0x180004b63  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180004b68  call    cs:__imp_RtlpNtOpenKey
0x180004b6e  lea     rcx, [rbp+hMem]
0x180004b72  mov     edi, eax
0x180004b74  call    SampFreeUnicodeString
0x180004b79  test    edi, edi
0x180004b7b  js      short loc_180004BD2
0x180004b7d  mov     rax, [rbp+arg_20]
0x180004b81  lea     r9, [rbp+DataLength]; DataLength
0x180004b85  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180004b89  xor     r8d, r8d; Data
0x180004b8c  mov     rdx, r14; Type
0x180004b8f  mov     [rbp+DataLength], r12d
0x180004b93  mov     dword ptr [rax], 4
0x180004b99  lea     rax, [rbp+var_48]
0x180004b9d  mov     qword ptr [rsp+80h+Unused], rax; Unused
0x180004ba2  call    cs:__imp_RtlpNtQueryValueKey
0x180004ba8  mov     rcx, [rbp+KeyHandle]; Handle
0x180004bac  mov     ebx, eax
0x180004bae  call    cs:__imp_NtClose
0x180004bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bbb  test    dword ptr [rcx+44h], 20000h
0x180004bc2  jz      loc_180004AE5
0x180004bc8  mov     edx, 67h ; 'g'
0x180004bcd  jmp     loc_180004ACE
0x180004bd2  add     ebx, 0FFFFFFFCh
0x180004bd5  cmp     ebx, 1
0x180004bd8  ja      loc_180004CC0
0x180004bde  mov     r8, rsi
0x180004be1  lea     rdx, [rbp+hMem]
0x180004be5  mov     ecx, 4
0x180004bea  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x180004bef  mov     ebx, eax
0x180004bf1  test    eax, eax
0x180004bf3  jns     short loc_180004C13
0x180004bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bfc  test    dword ptr [rcx+44h], 20000h
0x180004c03  jz      loc_180004AE5
0x180004c09  mov     edx, 68h ; 'h'
0x180004c0e  jmp     loc_180004ACE
0x180004c13  mov     rax, cs:SampKey
0x180004c1a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180004c1e  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180004c22  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180004c26  lea     rax, [rbp+hMem]
0x180004c2a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180004c31  xorps   xmm0, xmm0
0x180004c34  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180004c38  xor     r9d, r9d; Unused
0x180004c3b  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180004c42  mov     edx, 20019h; DesiredAccess
0x180004c47  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180004c4c  call    cs:__imp_RtlpNtOpenKey
0x180004c52  mov     rcx, [rbp+hMem+8]; hMem
0x180004c56  mov     edi, eax
0x180004c58  test    rcx, rcx
0x180004c5b  jz      short loc_180004C67
0x180004c5d  call    cs:__imp_LocalFree
0x180004c63  mov     [rbp+hMem+8], r12
0x180004c67  test    edi, edi
0x180004c69  js      short loc_180004CC0
0x180004c6b  mov     rax, [rbp+arg_20]
0x180004c6f  lea     r9, [rbp+DataLength]; DataLength
0x180004c73  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180004c77  xor     r8d, r8d; Data
0x180004c7a  mov     rdx, r14; Type
0x180004c7d  mov     [rbp+DataLength], r12d
0x180004c81  mov     dword ptr [rax], 1
0x180004c87  lea     rax, [rbp+var_48]
0x180004c8b  mov     qword ptr [rsp+80h+Unused], rax; Unused
0x180004c90  call    cs:__imp_RtlpNtQueryValueKey
0x180004c96  mov     rcx, [rbp+KeyHandle]; Handle
0x180004c9a  mov     ebx, eax
0x180004c9c  call    cs:__imp_NtClose
0x180004ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ca9  test    dword ptr [rcx+44h], 20000h
0x180004cb0  jz      loc_180004AE5
0x180004cb6  mov     edx, 69h ; 'i'
0x180004cbb  jmp     loc_180004ACE
0x180004cc0  cmp     edi, 0C0000034h
0x180004cc6  cmovz   edi, r15d
0x180004cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cd1  test    dword ptr [rcx+44h], 20000h
0x180004cd8  jz      short loc_180004CF6
0x180004cda  mov     edx, 6Ah ; 'j'
0x180004cdf  mov     rcx, [rcx+38h]
0x180004ce3  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180004cea  mov     r9d, edi
0x180004ced  mov     [rsp+80h+Unused], edi
0x180004cf1  call    WPP_SF_Dd
0x180004cf6  mov     eax, edi
0x180004cf8  lea     r11, [rsp+80h+var_s0]
0x180004d00  mov     rbx, [r11+38h]
0x180004d04  mov     rsi, [r11+40h]
0x180004d08  mov     rsp, r11
0x180004d0b  pop     r15
0x180004d0d  pop     r14
0x180004d0f  pop     r12
0x180004d11  pop     rdi
0x180004d12  pop     rbp
0x180004d13  retn
```
