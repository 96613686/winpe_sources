# SclStateValidateAndRetrieveChanges

- ea: `0x180004844`
- end: `0x180004c82`
- name: `SclStateValidateAndRetrieveChanges`
- size: `1086`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005a90`
- `0x180005da0`

## callees

- `0x18000154c`
- `0x180004844`
- `0x18000548c`
- `0x180007ac4`
- `0x180007b30`
- `0x180009374`
- `0x180009904`
- `0x18000a524`
- `0x18000de94`
- `0x1800153c8`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180004a0c`
- `ntdll!RtlInitUnicodeString` at `0x180004a0c`
- `ntdll!NtClose` at `0x180004bce`
- `ntdll!NtClose` at `0x180004bce`
- `ntdll!RtlFreeHeap` at `0x180004c11`
- `ntdll!RtlFreeHeap` at `0x180004c2e`
- `ntdll!RtlFreeHeap` at `0x180004c50`
- `ntdll!RtlFreeHeap` at `0x180004c11`
- `ntdll!RtlFreeHeap` at `0x180004c2e`
- `ntdll!RtlFreeHeap` at `0x180004c50`
- `ntdll!NtQuerySystemInformation` at `0x180004942`
- `ntdll!NtQuerySystemInformation` at `0x180004942`

## string_xrefs

- `0x180004aac`: `SECURITY`
- `0x18000497b`: `System32\config`

## pseudocode

```c
__int64 __fastcall SclStateValidateAndRetrieveChanges(__int64 a1, __int64 a2, _QWORD *a3)
{
  const wchar_t *v4; // r13
  WCHAR *v5; // r12
  _DWORD *v7; // rcx
  __int64 v8; // r10
  _QWORD *v9; // rdi
  _QWORD *v10; // rsi
  int v11; // ecx
  int CanonicalMountKeyPath; // ebx
  wchar_t *v13; // rax
  int v14; // eax
  _QWORD *v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rcx
  _QWORD *v19; // [rsp+28h] [rbp-D8h]
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22[2]; // [rsp+50h] [rbp-B0h]
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  _OWORD SystemInformation[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-60h]
  _BYTE v29[528]; // [rsp+B0h] [rbp-50h] BYREF

  v25 = 0;
  *(_QWORD *)v22 = 0;
  DestinationString = 0;
  v4 = 0;
  v24 = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  P = 0;
  v5 = 0;
  v21 = 0;
  v28 = 0;
  Handle = 0;
  if ( !SclOSIsValid(a2) || *a3 || (v9 = a3 + 1, a3[1]) || (v10 = a3 + 2, a3[2]) || a3[3] || a3[4] )
  {
    v9 = a3 + 1;
    v10 = a3 + 2;
    goto LABEL_21;
  }
  if ( v7 )
  {
    v11 = *v7 - 1;
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        v4 = *(const wchar_t **)(v8 + 8);
        goto LABEL_14;
      }
LABEL_21:
      CanonicalMountKeyPath = -1073741811;
      goto LABEL_22;
    }
  }
  CanonicalMountKeyPath = SclExpandString(L"%SYSTEMROOT%", v29);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_22;
  CanonicalMountKeyPath = NtQuerySystemInformation(SystemTimeOfDayInformation, SystemInformation, 0x30u, 0);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_22;
  v4 = (const wchar_t *)v29;
  *(_QWORD *)&SystemInformation[0] -= v28;
  v25 = *(_QWORD *)&SystemInformation[0];
  *(_QWORD *)v22 = &v25;
LABEL_14:
  v13 = BuildPathMulti(3u, v4, L"System32\\config", L"SETUPCL");
  v24 = v13;
  if ( v13 )
  {
    CanonicalMountKeyPath = SclRegGetCanonicalMountKeyPath((__int64)v13, &v21);
    if ( CanonicalMountKeyPath < 0 )
    {
      v5 = v21;
    }
    else
    {
      v14 = SclDosPathToNtPath((__int64)v24, &P);
      v5 = v21;
      CanonicalMountKeyPath = v14;
      if ( v14 >= 0 )
        CanonicalMountKeyPath = SclRegLoadUnloadHive(1, v21, (const WCHAR *)P);
    }
  }
  else
  {
    CanonicalMountKeyPath = -1073741801;
  }
LABEL_22:
  LODWORD(v21) = CanonicalMountKeyPath >= 0;
  if ( CanonicalMountKeyPath < 0 )
  {
    if ( CanonicalMountKeyPath == -1073741772 )
    {
      if ( a1 )
        v16 = a1 + 1152;
      else
        v16 = 0;
      SclLogGenericMessage(
        v16,
        1,
        (int)SclEvent_Generic_Info,
        2050,
        (__int64)"SclStateValidateAndRetrieveChanges",
        "SetupCl hive file not found; no stored changes");
      CanonicalMountKeyPath = 0;
    }
    else
    {
      if ( a1 )
        v17 = a1 + 1152;
      else
        v17 = 0;
      SclLogGenericMessage(
        v17,
        3,
        (int)SclEvent_Generic_Error,
        2058,
        (__int64)"SclStateValidateAndRetrieveChanges",
        "(%lx): Failure while loading SetupCl hive",
        CanonicalMountKeyPath);
    }
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, v5);
    CanonicalMountKeyPath = SclCreateKeyEx(0, &DestinationString, 0x20019u, 0, 0, &Handle);
    if ( CanonicalMountKeyPath >= 0 )
    {
      CanonicalMountKeyPath = SclpStateValidateAndRetrieveChangedKeys(a1, v4, *(_QWORD **)v22, Handle, L"DEFAULT", a3);
      if ( CanonicalMountKeyPath >= 0 )
      {
        v19 = v9;
        v15 = *(_QWORD **)v22;
        CanonicalMountKeyPath = SclpStateValidateAndRetrieveChangedKeys(a1, v4, *(_QWORD **)v22, Handle, L"SAM", v19);
        if ( CanonicalMountKeyPath >= 0 )
        {
          CanonicalMountKeyPath = SclpStateValidateAndRetrieveChangedKeys(a1, v4, v15, Handle, L"SECURITY", v10);
          if ( CanonicalMountKeyPath >= 0 )
          {
            CanonicalMountKeyPath = SclpStateValidateAndRetrieveChangedKeys(a1, v4, v15, Handle, L"SOFTWARE", a3 + 3);
            if ( CanonicalMountKeyPath >= 0 )
              CanonicalMountKeyPath = SclpStateValidateAndRetrieveChangedKeys(a1, v4, v15, Handle, L"SYSTEM", a3 + 4);
          }
        }
      }
    }
  }
  if ( Handle )
    NtClose(Handle);
  if ( (_BYTE)v21 )
  {
    if ( CanonicalMountKeyPath < 0 )
      SclRegLoadUnloadHive(0, v5, 0);
    else
      CanonicalMountKeyPath = SclRegLoadUnloadHive(0, v5, 0);
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( v24 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
  return (unsigned int)CanonicalMountKeyPath;
}

```

## disassembly

```asm
0x180004844  mov     [rsp-8+arg_18], rbx
0x180004849  push    rbp
0x18000484a  push    rsi
0x18000484b  push    rdi
0x18000484c  push    r12
0x18000484e  push    r13
0x180004850  push    r14
0x180004852  push    r15
0x180004854  lea     rbp, [rsp-1D0h]
0x18000485c  sub     rsp, 2D0h
0x180004863  mov     rax, cs:__security_cookie
0x18000486a  xor     rax, rsp
0x18000486d  mov     [rbp+200h+var_40], rax
0x180004874  xor     ebx, ebx
0x180004876  xorps   xmm0, xmm0
0x180004879  mov     r15, rcx
0x18000487c  mov     [rsp+300h+var_298], rbx
0x180004881  mov     rcx, rdx
0x180004884  mov     qword ptr [rsp+300h+var_2B0], rbx
0x180004889  movups  xmmword ptr [rsp+300h+DestinationString.Length], xmm0
0x18000488e  mov     r13d, ebx
0x180004891  mov     [rsp+300h+var_2A0], rbx
0x180004896  movups  [rbp+200h+SystemInformation], xmm0
0x18000489a  mov     [rsp+300h+P], rbx
0x18000489f  mov     r12d, ebx
0x1800048a2  movups  [rbp+200h+var_270], xmm0
0x1800048a6  mov     [rsp+300h+var_2B8], rbx
0x1800048ab  mov     r14, r8
0x1800048ae  movups  [rbp+200h+var_260], xmm0
0x1800048b2  mov     [rsp+300h+Handle], rbx
0x1800048b7  mov     r10, rdx
0x1800048ba  call    SclOSIsValid
0x1800048bf  test    al, al
0x1800048c1  jz      loc_1800049E4
0x1800048c7  cmp     [r14], rbx
0x1800048ca  jnz     loc_1800049E4
0x1800048d0  lea     rdi, [r14+8]
0x1800048d4  cmp     [rdi], rbx
0x1800048d7  jnz     loc_1800049E4
0x1800048dd  lea     rsi, [r14+10h]
0x1800048e1  cmp     [rsi], rbx
0x1800048e4  jnz     loc_1800049E4
0x1800048ea  cmp     [r14+18h], rbx
0x1800048ee  jnz     loc_1800049E4
0x1800048f4  cmp     [r14+20h], rbx
0x1800048f8  jnz     loc_1800049E4
0x1800048fe  test    rcx, rcx
0x180004901  jz      short loc_180004919
0x180004903  mov     ecx, [rcx]
0x180004905  sub     ecx, 1
0x180004908  jz      short loc_180004919
0x18000490a  cmp     ecx, 1
0x18000490d  jnz     loc_1800049EC
0x180004913  mov     r13, [r10+8]
0x180004917  jmp     short loc_180004971
0x180004919  lea     rdx, [rbp+200h+var_250]; void *
0x18000491d  lea     rcx, aSystemroot_0; "%SYSTEMROOT%"
0x180004924  call    SclExpandString
0x180004929  mov     ebx, eax
0x18000492b  test    eax, eax
0x18000492d  js      loc_1800049F1
0x180004933  xor     r9d, r9d; ReturnLength
0x180004936  lea     rdx, [rbp+200h+SystemInformation]; SystemInformation
0x18000493a  lea     r8d, [r9+30h]; SystemInformationLength
0x18000493e  lea     ecx, [r9+3]; SystemInformationClass
0x180004942  call    cs:__imp_NtQuerySystemInformation
0x180004948  mov     ebx, eax
0x18000494a  test    eax, eax
0x18000494c  js      loc_1800049F1
0x180004952  mov     rax, qword ptr [rbp+200h+SystemInformation]
0x180004956  lea     r13, [rbp+200h+var_250]
0x18000495a  sub     rax, qword ptr [rbp+200h+var_260]
0x18000495e  mov     qword ptr [rbp+200h+SystemInformation], rax
0x180004962  mov     [rsp+300h+var_298], rax
0x180004967  lea     rax, [rsp+300h+var_298]
0x18000496c  mov     qword ptr [rsp+300h+var_2B0], rax
0x180004971  lea     r9, aSetupcl; "SETUPCL"
0x180004978  mov     rdx, r13
0x18000497b  lea     r8, aSystem32Config; "System32\\config"
0x180004982  mov     ecx, 3
0x180004987  call    BuildPathMulti
0x18000498c  mov     [rsp+300h+var_2A0], rax
0x180004991  test    rax, rax
0x180004994  jnz     short loc_18000499D
0x180004996  mov     ebx, 0C0000017h
0x18000499b  jmp     short loc_1800049F1
0x18000499d  lea     rdx, [rsp+300h+var_2B8]
0x1800049a2  mov     rcx, rax
0x1800049a5  call    SclRegGetCanonicalMountKeyPath
0x1800049aa  mov     ebx, eax
0x1800049ac  test    eax, eax
0x1800049ae  js      short loc_1800049DD
0x1800049b0  mov     rcx, [rsp+300h+var_2A0]
0x1800049b5  lea     rdx, [rsp+300h+P]
0x1800049ba  call    SclDosPathToNtPath
0x1800049bf  mov     r12, [rsp+300h+var_2B8]
0x1800049c4  mov     ebx, eax
0x1800049c6  test    eax, eax
0x1800049c8  js      short loc_1800049F1
0x1800049ca  mov     r8, [rsp+300h+P]
0x1800049cf  mov     rdx, r12
0x1800049d2  mov     cl, 1
0x1800049d4  call    SclRegLoadUnloadHive
0x1800049d9  mov     ebx, eax
0x1800049db  jmp     short loc_1800049F1
0x1800049dd  mov     r12, [rsp+300h+var_2B8]
0x1800049e2  jmp     short loc_1800049F1
0x1800049e4  lea     rdi, [r14+8]
0x1800049e8  lea     rsi, [r14+10h]
0x1800049ec  mov     ebx, 0C000000Dh
0x1800049f1  mov     eax, ebx
0x1800049f3  shr     eax, 1Fh
0x1800049f6  xor     al, 1
0x1800049f8  mov     dword ptr [rsp+300h+var_2B8], eax
0x1800049fc  test    ebx, ebx
0x1800049fe  js      loc_180004B36
0x180004a04  mov     rdx, r12; SourceString
0x180004a07  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x180004a0c  call    cs:__imp_RtlInitUnicodeString
0x180004a12  lea     rax, [rsp+300h+Handle]
0x180004a17  xor     r9d, r9d
0x180004a1a  mov     [rsp+300h+var_2D8], rax
0x180004a1f  lea     rdx, [rsp+300h+DestinationString]
0x180004a24  mov     r8d, 20019h
0x180004a2a  mov     [rsp+300h+SourceString], 0
0x180004a33  xor     ecx, ecx
0x180004a35  call    SclCreateKeyEx
0x180004a3a  mov     ebx, eax
0x180004a3c  test    eax, eax
0x180004a3e  js      loc_180004BC4
0x180004a44  mov     r9, [rsp+300h+Handle]; int
0x180004a49  lea     rax, aDefault_0; "DEFAULT"
0x180004a50  mov     r8, qword ptr [rsp+300h+var_2B0]; int
0x180004a55  mov     rdx, r13; int
0x180004a58  mov     [rsp+300h+var_2D8], r14; __int64
0x180004a5d  mov     rcx, r15; int
0x180004a60  mov     [rsp+300h+SourceString], rax; SourceString
0x180004a65  call    SclpStateValidateAndRetrieveChangedKeys
0x180004a6a  mov     ebx, eax
0x180004a6c  test    eax, eax
0x180004a6e  js      loc_180004BC4
0x180004a74  mov     r9, [rsp+300h+Handle]; int
0x180004a79  lea     rax, aSam; "SAM"
0x180004a80  mov     [rsp+300h+var_2D8], rdi; __int64
0x180004a85  mov     rdx, r13; int
0x180004a88  mov     rdi, qword ptr [rsp+300h+var_2B0]
0x180004a8d  mov     rcx, r15; int
0x180004a90  mov     r8, rdi; int
0x180004a93  mov     [rsp+300h+SourceString], rax; SourceString
0x180004a98  call    SclpStateValidateAndRetrieveChangedKeys
0x180004a9d  mov     ebx, eax
0x180004a9f  test    eax, eax
0x180004aa1  js      loc_180004BC4
0x180004aa7  mov     r9, [rsp+300h+Handle]; int
0x180004aac  lea     rax, aSecurity; "SECURITY"
0x180004ab3  mov     [rsp+300h+var_2D8], rsi; __int64
0x180004ab8  mov     r8, rdi; int
0x180004abb  mov     rdx, r13; int
0x180004abe  mov     [rsp+300h+SourceString], rax; SourceString
0x180004ac3  mov     rcx, r15; int
0x180004ac6  call    SclpStateValidateAndRetrieveChangedKeys
0x180004acb  mov     ebx, eax
0x180004acd  test    eax, eax
0x180004acf  js      loc_180004BC4
0x180004ad5  mov     r9, [rsp+300h+Handle]; int
0x180004ada  lea     rax, [r14+18h]
0x180004ade  mov     [rsp+300h+var_2D8], rax; __int64
0x180004ae3  mov     r8, rdi; int
0x180004ae6  lea     rax, aSoftware; "SOFTWARE"
0x180004aed  mov     rdx, r13; int
0x180004af0  mov     rcx, r15; int
0x180004af3  mov     [rsp+300h+SourceString], rax; SourceString
0x180004af8  call    SclpStateValidateAndRetrieveChangedKeys
0x180004afd  mov     ebx, eax
0x180004aff  test    eax, eax
0x180004b01  js      loc_180004BC4
0x180004b07  mov     r9, [rsp+300h+Handle]; int
0x180004b0c  lea     rax, [r14+20h]
0x180004b10  mov     [rsp+300h+var_2D8], rax; __int64
0x180004b15  mov     r8, rdi; int
0x180004b18  lea     rax, aSystem; "SYSTEM"
0x180004b1f  mov     rdx, r13; int
0x180004b22  mov     rcx, r15; int
0x180004b25  mov     [rsp+300h+SourceString], rax; SourceString
0x180004b2a  call    SclpStateValidateAndRetrieveChangedKeys
0x180004b2f  mov     ebx, eax
0x180004b31  jmp     loc_180004BC4
0x180004b36  cmp     ebx, 0C0000034h
0x180004b3c  jnz     short loc_180004B81
0x180004b3e  test    r15, r15
0x180004b41  jz      short loc_180004B4C
0x180004b43  lea     rcx, [r15+480h]
0x180004b4a  jmp     short loc_180004B4E
0x180004b4c  xor     ecx, ecx
0x180004b4e  lea     rax, aSetupclHiveFil; "SetupCl hive file not found; no stored "...
0x180004b55  mov     r9d, 802h
0x180004b5b  mov     [rsp+300h+var_2D8], rax
0x180004b60  lea     r8, SclEvent_Generic_Info
0x180004b67  lea     rax, aSclstatevalida; "SclStateValidateAndRetrieveChanges"
0x180004b6e  mov     edx, 1
0x180004b73  mov     [rsp+300h+SourceString], rax
0x180004b78  call    SclLogGenericMessage
0x180004b7d  xor     ebx, ebx
0x180004b7f  jmp     short loc_180004BC4
0x180004b81  test    r15, r15
0x180004b84  jz      short loc_180004B8F
0x180004b86  lea     rcx, [r15+480h]
0x180004b8d  jmp     short loc_180004B91
0x180004b8f  xor     ecx, ecx
0x180004b91  lea     rax, aLxFailureWhile; "(%lx): Failure while loading SetupCl hi"...
0x180004b98  mov     [rsp+300h+var_2D0], ebx
0x180004b9c  mov     [rsp+300h+var_2D8], rax
0x180004ba1  lea     r8, SclEvent_Generic_Error
0x180004ba8  lea     rax, aSclstatevalida; "SclStateValidateAndRetrieveChanges"
0x180004baf  mov     r9d, 80Ah
0x180004bb5  mov     edx, 3
0x180004bba  mov     [rsp+300h+SourceString], rax
0x180004bbf  call    SclLogGenericMessage
0x180004bc4  mov     rcx, [rsp+300h+Handle]; Handle
0x180004bc9  test    rcx, rcx
0x180004bcc  jz      short loc_180004BD4
0x180004bce  call    cs:__imp_NtClose
0x180004bd4  cmp     byte ptr [rsp+300h+var_2B8], 0
0x180004bd9  jz      short loc_180004BF5
0x180004bdb  xor     r8d, r8d
0x180004bde  xor     ecx, ecx
0x180004be0  mov     rdx, r12
0x180004be3  test    ebx, ebx
0x180004be5  js      short loc_180004BF0
0x180004be7  call    SclRegLoadUnloadHive
0x180004bec  mov     ebx, eax
0x180004bee  jmp     short loc_180004BF5
0x180004bf0  call    SclRegLoadUnloadHive
0x180004bf5  mov     rax, [rsp+300h+P]
0x180004bfa  test    rax, rax
0x180004bfd  jz      short loc_180004C17
0x180004bff  mov     rcx, gs:60h
0x180004c08  mov     r8, rax; P
0x180004c0b  xor     edx, edx; Flags
0x180004c0d  mov     rcx, [rcx+30h]; HeapHandle
0x180004c11  call    cs:__imp_RtlFreeHeap
0x180004c17  test    r12, r12
0x180004c1a  jz      short loc_180004C34
0x180004c1c  mov     rcx, gs:60h
0x180004c25  mov     r8, r12; P
0x180004c28  xor     edx, edx; Flags
0x180004c2a  mov     rcx, [rcx+30h]; HeapHandle
0x180004c2e  call    cs:__imp_RtlFreeHeap
0x180004c34  mov     rax, [rsp+300h+var_2A0]
0x180004c39  test    rax, rax
0x180004c3c  jz      short loc_180004C56
0x180004c3e  mov     rcx, gs:60h
0x180004c47  mov     r8, rax; P
0x180004c4a  xor     edx, edx; Flags
0x180004c4c  mov     rcx, [rcx+30h]; HeapHandle
0x180004c50  call    cs:__imp_RtlFreeHeap
0x180004c56  mov     eax, ebx
0x180004c58  mov     rcx, [rbp+200h+var_40]
0x180004c5f  xor     rcx, rsp; StackCookie
0x180004c62  call    __security_check_cookie
0x180004c67  mov     rbx, [rsp+300h+arg_18]
0x180004c6f  add     rsp, 2D0h
0x180004c76  pop     r15
0x180004c78  pop     r14
0x180004c7a  pop     r13
0x180004c7c  pop     r12
0x180004c7e  pop     rdi
0x180004c7f  pop     rsi
0x180004c80  pop     rbp
0x180004c81  retn
```
