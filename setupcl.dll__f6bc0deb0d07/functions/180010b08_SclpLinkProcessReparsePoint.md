# SclpLinkProcessReparsePoint

- ea: `0x180010b08`
- end: `0x180010f3b`
- name: `SclpLinkProcessReparsePoint`
- size: `1075`
- prototype: `__int64 __fastcall(void *, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x180016340`

## callees

- `0x18000a524`
- `0x1800109f0`
- `0x180010b08`
- `0x180014fa0`
- `0x180016118`

## import_xrefs

- `ntdll!NtClose` at `0x180010f11`
- `ntdll!NtClose` at `0x180010f11`
- `ntdll!RtlFreeHeap` at `0x180010f02`
- `ntdll!RtlFreeHeap` at `0x180010f02`
- `ntdll!NtOpenFile` at `0x180010c28`
- `ntdll!NtOpenFile` at `0x180010c28`

## string_xrefs

- `0x180010b8d`: `Ignoring unrecognized reparse tag [0x%x], [ID=0x%I64x]`
- `0x180010ba5`: `SclpLinkProcessReparsePoint`
- `0x180010c30`: `SclpLinkProcessReparsePoint`
- `0x180010c7f`: `(%lx): Failed to retrieve reparse point's path, path restrictions will not be honored [ID=0x%I64x]`
- `0x180010cd5`: `Not changing symbolic link %s due to path restrictions`
- `0x180010d3e`: `(%lx): Failed to validate if we should process symbolic link %s`
- `0x180010c37`: `<path unavailable>`
- `0x180010d85`: `<path unavailable>`
- `0x180010e2b`: `<path unavailable>`
- `0x180010e6e`: `<path unavailable>`
- `0x180010db1`: `(%lx): Failed to retarget reparse point [ID=0x%I64x]: [%ws]`
- `0x180010e41`: `Successfully processed reparse point [%ws]; update %s`
- `0x180010e86`: `(%lx): Failed to process reparse point [ID=0x%I64x]: [%ws]`

## pseudocode

```c
__int64 __fastcall SclpLinkProcessReparsePoint(void *a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v4; // r13
  char *v6; // rdi
  int v7; // r15d
  int v8; // r12d
  int v10; // esi
  const wchar_t *v11; // rax
  int v12; // r13d
  _WORD *v13; // rdx
  int IsLinkInPaths; // eax
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rax
  const char *v17; // rax
  const wchar_t *v18; // rdx
  __int64 v19; // [rsp+30h] [rbp-69h]
  int v20; // [rsp+50h] [rbp-49h] BYREF
  void *FileHandle; // [rsp+58h] [rbp-41h] BYREF
  PVOID P; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v23[2]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v24; // [rsp+78h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp+17h] BYREF
  int v27; // [rsp+100h] [rbp+67h] BYREF
  __int64 v28; // [rsp+108h] [rbp+6Fh]

  v28 = a2;
  v4 = a2;
  if ( !a1 || !a4 )
    return 3221225485LL;
  FileHandle = 0;
  P = 0;
  v6 = 0;
  v27 = 0;
  v7 = 0;
  v20 = 0;
  v8 = 0;
  if ( a4 != -1296 )
    ++*(_QWORD *)(a4 + 1296);
  if ( a3 != -1610612733 && a3 != -1610612724 )
  {
    SclLogGenericMessage(
      a4 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      209,
      (__int64)"SclpLinkProcessReparsePoint",
      "Ignoring unrecognized reparse tag [0x%x], [ID=0x%I64x]",
      a3,
      a2);
    return 0;
  }
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = a1;
  v23[1] = &v24;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v23;
  v23[0] = 524296;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  IoStatusBlock = 0;
  v24 = a2;
  v10 = NtOpenFile(&FileHandle, 0x100003u, &ObjectAttributes, &IoStatusBlock, 3u, 0x206020u);
  v11 = L"<path unavailable>";
  if ( v10 < 0 )
    goto LABEL_41;
  v12 = 1;
  v10 = CanonicalizeObjectPathByHandle(FileHandle, &P);
  if ( v10 < 0 )
  {
    if ( *(_QWORD *)(a4 + 1072) )
      SclLogGenericMessage(
        a4 + 1152,
        3,
        (int)SclEvent_Generic_Error,
        234,
        (__int64)"SclpLinkProcessReparsePoint",
        "(%lx): Failed to retrieve reparse point's path, path restrictions will not be honored [ID=0x%I64x]",
        v10,
        v28);
    v10 = 0;
  }
  v6 = (char *)P;
  if ( !P || (v13 = *(_WORD **)(a4 + 1072)) == 0 )
  {
LABEL_18:
    if ( *(_BYTE *)a4 && v12 )
    {
      if ( v7 )
        v15 = (const wchar_t *)(a4 + 32);
      else
        v15 = 0;
      v10 = RetargetLinkReparsePointByHandle((char *)FileHandle, v15, (const wchar_t *)(a4 + 552), &v20);
      if ( v10 < 0 )
      {
        v4 = v28;
        v16 = L"<path unavailable>";
        if ( v6 )
          v16 = (const wchar_t *)v6;
        LODWORD(v19) = v10;
        SclLogGenericMessage(
          a4 + 1152,
          3,
          (int)SclEvent_Generic_Error,
          299,
          (__int64)"SclpLinkProcessReparsePoint",
          "(%lx): Failed to retarget reparse point [ID=0x%I64x]: [%ws]",
          v19,
          v28,
          v16);
        goto LABEL_28;
      }
      v8 = v20;
    }
    if ( v8 && a4 != -1304 )
      ++*(_QWORD *)(a4 + 1304);
    if ( v12 )
    {
      v17 = "performed";
      if ( !v8 )
        v17 = "not performed";
      v18 = L"<path unavailable>";
      if ( v6 )
        v18 = (const wchar_t *)v6;
      SclLogGenericMessage(
        a4 + 1152,
        1,
        (int)SclEvent_Generic_Info,
        320,
        (__int64)"SclpLinkProcessReparsePoint",
        "Successfully processed reparse point [%ws]; update %s",
        v18,
        v17);
    }
    goto LABEL_43;
  }
  IsLinkInPaths = SclpIsLinkInPaths((wchar_t *)P, v13, &v27);
  v10 = IsLinkInPaths;
  if ( IsLinkInPaths >= 0 )
  {
    v7 = v27;
    if ( !v27 )
    {
      SclLogGenericMessage(
        a4 + 1152,
        1,
        (int)SclEvent_Generic_Info,
        254,
        (__int64)"SclpLinkProcessReparsePoint",
        "Not changing symbolic link %s due to path restrictions",
        v6);
      v12 = 0;
    }
    goto LABEL_18;
  }
  SclLogGenericMessage(
    a4 + 1152,
    3,
    (int)SclEvent_Generic_Error,
    264,
    (__int64)"SclpLinkProcessReparsePoint",
    "(%lx): Failed to validate if we should process symbolic link %s",
    IsLinkInPaths,
    v6);
  v4 = v28;
LABEL_28:
  if ( v6 )
    v11 = (const wchar_t *)v6;
  else
    v11 = L"<path unavailable>";
LABEL_41:
  LODWORD(v19) = v10;
  SclLogGenericMessage(
    a4 + 1152,
    3,
    (int)SclEvent_Generic_Error,
    330,
    (__int64)"SclpLinkProcessReparsePoint",
    "(%lx): Failed to process reparse point [ID=0x%I64x]: [%ws]",
    v19,
    v4,
    v11);
  if ( *(_QWORD *)(a4 + 1072) )
  {
    SclLogGenericMessage(
      a4 + 1152,
      1,
      (int)SclEvent_Generic_Info,
      339,
      (__int64)"SclpLinkProcessReparsePoint",
      "Will ignore error and continue processing");
    v10 = 0;
  }
LABEL_43:
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010b08  mov     [rsp-8+arg_10], rbx
0x180010b0d  mov     [rsp-8+arg_8], rdx
0x180010b12  push    rbp
0x180010b13  push    rsi
0x180010b14  push    rdi
0x180010b15  push    r12
0x180010b17  push    r13
0x180010b19  push    r14
0x180010b1b  push    r15
0x180010b1d  lea     rbp, [rsp-27h]
0x180010b22  sub     rsp, 0C0h
0x180010b29  mov     r13, rdx
0x180010b2c  mov     rbx, r9
0x180010b2f  xor     edx, edx
0x180010b31  test    rcx, rcx
0x180010b34  jz      loc_180010F1B
0x180010b3a  test    rbx, rbx
0x180010b3d  jz      loc_180010F1B
0x180010b43  lea     rax, [r9+510h]
0x180010b4a  mov     [rbp+57h+FileHandle], rdx
0x180010b4e  mov     [rbp+57h+P], rdx
0x180010b52  mov     edi, edx
0x180010b54  mov     [rbp+57h+arg_0], edx
0x180010b57  mov     r15d, edx
0x180010b5a  mov     [rbp+57h+var_A0], edx
0x180010b5d  mov     r12d, edx
0x180010b60  test    rax, rax
0x180010b63  jz      short loc_180010B76
0x180010b65  mov     rax, [r9+510h]
0x180010b6c  inc     rax
0x180010b6f  mov     [r9+510h], rax
0x180010b76  cmp     r8d, 0A0000003h
0x180010b7d  jz      short loc_180010BCF
0x180010b7f  cmp     r8d, 0A000000Ch
0x180010b86  jz      short loc_180010BCF
0x180010b88  mov     [rsp+0F0h+var_B8], r13
0x180010b8d  lea     rax, aIgnoringUnreco; "Ignoring unrecognized reparse tag [0x%x"...
0x180010b94  mov     dword ptr [rsp+0F0h+var_C0], r8d
0x180010b99  lea     rcx, [r9+480h]
0x180010ba0  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180010ba5  lea     r14, aSclplinkproces; "SclpLinkProcessReparsePoint"
0x180010bac  lea     r8, SclEvent_Generic_Info
0x180010bb3  mov     qword ptr [rsp+0F0h+ShareAccess], r14
0x180010bb8  mov     r9d, 0D1h
0x180010bbe  mov     edx, 1
0x180010bc3  call    SclLogGenericMessage
0x180010bc8  xor     eax, eax
0x180010bca  jmp     loc_180010F20
0x180010bcf  xorps   xmm0, xmm0
0x180010bd2  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rdx
0x180010bd6  lea     rax, [rbp+57h+var_78]
0x180010bda  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x180010bde  mov     [rbp+57h+var_80], rax
0x180010be2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180010be6  lea     rax, [rbp+57h+var_88]
0x180010bea  mov     [rsp+0F0h+OpenOptions], 206020h; OpenOptions
0x180010bf2  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180010bf6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180010bfa  mov     edx, 100003h; DesiredAccess
0x180010bff  mov     [rbp+57h+var_88], 80008h
0x180010c07  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180010c0b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180010c13  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180010c17  mov     [rbp+57h+var_78], r13
0x180010c1b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180010c20  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x180010c28  call    cs:__imp_NtOpenFile
0x180010c2e  mov     esi, eax
0x180010c30  lea     r14, aSclplinkproces; "SclpLinkProcessReparsePoint"
0x180010c37  lea     rax, aPathUnavailabl; "<path unavailable>"
0x180010c3e  test    esi, esi
0x180010c40  js      loc_180010E75
0x180010c46  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180010c4a  lea     rdx, [rbp+57h+P]
0x180010c4e  mov     r13d, 1
0x180010c54  call    CanonicalizeObjectPathByHandle
0x180010c59  mov     esi, eax
0x180010c5b  test    eax, eax
0x180010c5d  jns     short loc_180010CA5
0x180010c5f  cmp     [rbx+430h], rdi
0x180010c66  jz      short loc_180010CA3
0x180010c68  mov     rax, [rbp+57h+arg_8]
0x180010c6c  lea     rcx, [rbx+480h]
0x180010c73  mov     [rsp+0F0h+var_B8], rax
0x180010c78  lea     r8, SclEvent_Generic_Error
0x180010c7f  lea     rax, aLxFailedToRetr; "(%lx): Failed to retrieve reparse point"...
0x180010c86  mov     dword ptr [rsp+0F0h+var_C0], esi
0x180010c8a  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180010c8f  lea     edx, [r13+2]
0x180010c93  mov     r9d, 0EAh
0x180010c99  mov     qword ptr [rsp+0F0h+ShareAccess], r14
0x180010c9e  call    SclLogGenericMessage
0x180010ca3  xor     esi, esi
0x180010ca5  mov     rdi, [rbp+57h+P]
0x180010ca9  test    rdi, rdi
0x180010cac  jz      short loc_180010D0A
0x180010cae  mov     rdx, [rbx+430h]
0x180010cb5  test    rdx, rdx
0x180010cb8  jz      short loc_180010D0A
0x180010cba  lea     r8, [rbp+57h+arg_0]
0x180010cbe  mov     rcx, rdi; String1
0x180010cc1  call    SclpIsLinkInPaths
0x180010cc6  mov     esi, eax
0x180010cc8  test    eax, eax
0x180010cca  js      short loc_180010D27
0x180010ccc  mov     r15d, [rbp+57h+arg_0]
0x180010cd0  test    r15d, r15d
0x180010cd3  jnz     short loc_180010D0A
0x180010cd5  lea     rax, aNotChangingSym; "Not changing symbolic link %s due to pa"...
0x180010cdc  mov     [rsp+0F0h+var_C0], rdi
0x180010ce1  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180010ce6  lea     rcx, [rbx+480h]
0x180010ced  mov     r9d, 0FEh
0x180010cf3  mov     qword ptr [rsp+0F0h+ShareAccess], r14
0x180010cf8  lea     r8, SclEvent_Generic_Info
0x180010cff  mov     edx, r13d
0x180010d02  call    SclLogGenericMessage
0x180010d07  xor     r13d, r13d
0x180010d0a  cmp     [rbx], r12b
0x180010d0d  jz      loc_180010DE5
0x180010d13  test    r13d, r13d
0x180010d16  jz      loc_180010DE5
0x180010d1c  test    r15d, r15d
0x180010d1f  jz      short loc_180010D65
0x180010d21  lea     rdx, [rbx+20h]
0x180010d25  jmp     short loc_180010D67
0x180010d27  mov     [rsp+0F0h+var_B8], rdi
0x180010d2c  lea     rcx, [rbx+480h]
0x180010d33  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180010d37  lea     r8, SclEvent_Generic_Error
0x180010d3e  lea     rax, aLxFailedToVali; "(%lx): Failed to validate if we should "...
0x180010d45  mov     r9d, 108h
0x180010d4b  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180010d50  mov     edx, 3
0x180010d55  mov     qword ptr [rsp+0F0h+ShareAccess], r14
0x180010d5a  call    SclLogGenericMessage
0x180010d5f  mov     r13, [rbp+57h+arg_8]
0x180010d63  jmp     short loc_180010DD0
0x180010d65  xor     edx, edx
0x180010d67  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180010d6b  lea     r8, [rbx+228h]
0x180010d72  lea     r9, [rbp+57h+var_A0]
0x180010d76  call    RetargetLinkReparsePointByHandle
0x180010d7b  mov     esi, eax
0x180010d7d  test    eax, eax
0x180010d7f  jns     short loc_180010DE1
0x180010d81  mov     r13, [rbp+57h+arg_8]
0x180010d85  lea     rax, aPathUnavailabl; "<path unavailable>"
0x180010d8c  test    rdi, rdi
0x180010d8f  lea     rcx, [rbx+480h]
0x180010d96  mov     r9d, 12Bh
0x180010d9c  lea     r8, SclEvent_Generic_Error
0x180010da3  cmovnz  rax, rdi
0x180010da7  mov     edx, 3
0x180010dac  mov     [rsp+0F0h+var_B0], rax
0x180010db1  lea     rax, aLxFailedToReta_0; "(%lx): Failed to retarget reparse point"...
0x180010db8  mov     [rsp+0F0h+var_B8], r13
0x180010dbd  mov     dword ptr [rsp+0F0h+var_C0], esi
0x180010dc1  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180010dc6  mov     qword ptr [rsp+0F0h+ShareAccess], r14
0x180010dcb  call    SclLogGenericMessage
0x180010dd0  test    rdi, rdi
0x180010dd3  jz      loc_180010E6E
0x180010dd9  mov     rax, rdi
0x180010ddc  jmp     loc_180010E75
0x180010de1  mov     r12d, [rbp+57h+var_A0]
0x180010de5  test    r12d, r12d
0x180010de8  jz      short loc_180010E07
0x180010dea  lea     rax, [rbx+518h]
0x180010df1  test    rax, rax
0x180010df4  jz      short loc_180010E07
0x180010df6  mov     rax, [rbx+518h]
0x180010dfd  inc     rax
0x180010e00  mov     [rbx+518h], rax
0x180010e07  test    r13d, r13d
0x180010e0a  jz      loc_180010EEB
0x180010e10  test    r12d, r12d
0x180010e13  lea     rcx, aNotPerformed; "not performed"
0x180010e1a  lea     rax, aPerformed; "performed"
0x180010e21  mov     r9d, 140h
0x180010e27  cmovz   rax, rcx
0x180010e2b  lea     rdx, aPathUnavailabl; "<path unavailable>"
0x180010e32  mov     [rsp+0F0h+var_B8], rax
0x180010e37  lea     rcx, [rbx+480h]
0x180010e3e  test    rdi, rdi
0x180010e41  lea     rax, aSuccessfullyPr; "Successfully processed reparse point [%"...
0x180010e48  lea     r8, SclEvent_Generic_Info
0x180010e4f  cmovnz  rdx, rdi
0x180010e53  mov     [rsp+0F0h+var_C0], rdx
0x180010e58  mov     edx, 1
0x180010e5d  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180010e62  mov     qword ptr [rsp+0F0h+ShareAccess], r14
0x180010e67  call    SclLogGenericMessage
0x180010e6c  jmp     short loc_180010EEB
0x180010e6e  lea     rax, aPathUnavailabl; "<path unavailable>"
0x180010e75  mov     [rsp+0F0h+var_B0], rax
0x180010e7a  lea     r15, [rbx+480h]
0x180010e81  mov     [rsp+0F0h+var_B8], r13
0x180010e86  lea     rax, aLxFailedToProc_6; "(%lx): Failed to process reparse point "...
0x180010e8d  mov     dword ptr [rsp+0F0h+var_C0], esi
0x180010e91  lea     r8, SclEvent_Generic_Error
0x180010e98  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180010e9d  mov     r9d, 14Ah
0x180010ea3  mov     edx, 3
0x180010ea8  mov     qword ptr [rsp+0F0h+ShareAccess], r14
0x180010ead  mov     rcx, r15
0x180010eb0  call    SclLogGenericMessage
0x180010eb5  cmp     [rbx+430h], r12
0x180010ebc  jz      short loc_180010EEB
0x180010ebe  lea     rax, aWillIgnoreErro; "Will ignore error and continue processi"...
0x180010ec5  mov     r9d, 153h
0x180010ecb  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180010ed0  lea     r8, SclEvent_Generic_Info
0x180010ed7  mov     edx, 1
0x180010edc  mov     qword ptr [rsp+0F0h+ShareAccess], r14
0x180010ee1  mov     rcx, r15
0x180010ee4  call    SclLogGenericMessage
0x180010ee9  xor     esi, esi
0x180010eeb  test    rdi, rdi
0x180010eee  jz      short loc_180010F08
0x180010ef0  mov     rcx, gs:60h
0x180010ef9  mov     r8, rdi; P
0x180010efc  xor     edx, edx; Flags
0x180010efe  mov     rcx, [rcx+30h]; HeapHandle
0x180010f02  call    cs:__imp_RtlFreeHeap
0x180010f08  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180010f0c  test    rcx, rcx
0x180010f0f  jz      short loc_180010F17
0x180010f11  call    cs:__imp_NtClose
0x180010f17  mov     eax, esi
0x180010f19  jmp     short loc_180010F20
0x180010f1b  mov     eax, 0C000000Dh
0x180010f20  mov     rbx, [rsp+0F0h+arg_10]
0x180010f28  add     rsp, 0C0h
0x180010f2f  pop     r15
0x180010f31  pop     r14
0x180010f33  pop     r13
0x180010f35  pop     r12
0x180010f37  pop     rdi
0x180010f38  pop     rsi
0x180010f39  pop     rbp
0x180010f3a  retn
```
