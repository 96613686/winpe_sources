# SclFsProcessVolume

- ea: `0x18001188c`
- end: `0x180011cad`
- name: `SclFsProcessVolume`
- size: `1057`
- prototype: `__int64 __fastcall(_BYTE *, _WORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800065f8`

## callees

- `0x180001cd4`
- `0x180007c28`
- `0x18000a524`
- `0x18000e740`
- `0x18001188c`
- `0x180011cb4`
- `0x180011d8c`
- `0x18001204c`
- `0x180012114`
- `0x18001555c`
- `0x1800179e0`

## import_xrefs

- `ntdll!NtClose` at `0x180011c7b`
- `ntdll!NtClose` at `0x180011c7b`
- `ntdll!_wcsicmp` at `0x1800119a3`
- `ntdll!_wcsicmp` at `0x1800119b7`
- `ntdll!_wcsicmp` at `0x1800119a3`
- `ntdll!_wcsicmp` at `0x1800119b7`

## string_xrefs

- `0x180011ab5`: `The current (host) OS is not supported for FS SID replacement!`

## pseudocode

```c
__int64 __fastcall SclFsProcessVolume(_BYTE *a1, _WORD *a2)
{
  int VolumeHandle; // ebx
  int v4; // r12d
  int v5; // ebx
  int v6; // eax
  unsigned int v7; // r15d
  unsigned int v8; // ebx
  int v9; // r15d
  unsigned int v10; // r14d
  int v11; // ecx
  int v12; // r9d
  unsigned int v13; // r15d
  int v14; // ecx
  int v15; // ecx
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v18; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-A8h] BYREF
  int v20; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v21[3]; // [rsp+64h] [rbp-9Ch] BYREF
  wchar_t String1[264]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v23[264]; // [rsp+280h] [rbp+180h] BYREF

  Handle = 0;
  v18 = 0;
  v17 = 0;
  v21[0] = 0;
  v20 = 0;
  VolumeHandle = RtlStringCchCopyW(v23, 0x104u, a2);
  if ( VolumeHandle < 0 )
    goto LABEL_31;
  StrRTrm(v23);
  VolumeHandle = SclGetVolumeHandle(v23, &Handle);
  if ( VolumeHandle < 0 )
    goto LABEL_31;
  VolumeHandle = SclpFsGetVolumeFileSystemName(Handle, String1);
  if ( VolumeHandle < 0 )
    goto LABEL_31;
  v4 = (_DWORD)a1 + 1152;
  if ( !a1 )
    v4 = 0;
  SclLogGenericMessage(v4, 1, (unsigned int)SclEvent_Generic_Info, 108, (__int64)"SclFsProcessVolume");
  v5 = _wcsicmp(String1, L"NTFS");
  v6 = _wcsicmp(String1, L"ReFS");
  if ( !v5 )
  {
    VolumeHandle = SclpNtfsGetVersion(Handle, &v18, &v17);
    if ( VolumeHandle < 0 )
      goto LABEL_31;
    v7 = v17;
    v8 = v18;
    SclLogGenericMessage(v4, 1, (unsigned int)SclEvent_Generic_Info, 137, (__int64)"SclFsProcessVolume");
    if ( v8 >= 3 && (v8 != 3 || v7) )
    {
      VolumeHandle = SclGetOSVersion(v21, &v20);
      if ( VolumeHandle < 0 )
        goto LABEL_31;
      v9 = v20;
      v10 = v21[0];
      SclLogGenericMessage(v4, 1, (unsigned int)SclEvent_Generic_Info, 163, (__int64)"SclFsProcessVolume");
      if ( v10 < 6 || v10 == 6 && !v9 )
      {
        v11 = 0;
        if ( a1 )
          v11 = (_DWORD)a1 + 1152;
        VolumeHandle = -1073741637;
        SclLogGenericMessage(v11, 3, (unsigned int)SclEvent_Generic_Error, 172, (__int64)"SclFsProcessVolume");
        goto LABEL_31;
      }
      goto LABEL_25;
    }
    v12 = 146;
    goto LABEL_28;
  }
  if ( v6 )
  {
    v12 = 218;
LABEL_28:
    v15 = 0;
    VolumeHandle = -1073741637;
    if ( a1 )
      v15 = (_DWORD)a1 + 1152;
    SclLogGenericMessage(v15, 3, (unsigned int)SclEvent_Generic_Error, v12, (__int64)"SclFsProcessVolume");
    goto LABEL_31;
  }
  VolumeHandle = SclpRefsGetVersion(Handle, &v18, &v17);
  if ( VolumeHandle < 0 )
    goto LABEL_31;
  v13 = v18;
  SclLogGenericMessage(v4, 1, (unsigned int)SclEvent_Generic_Info, 197, (__int64)"SclFsProcessVolume");
  if ( __PAIR64__(v13, v17) >= 0x30000000CLL )
  {
LABEL_25:
    if ( *a1 )
    {
      SclLogGenericMessage(
        (_DWORD)a1 + 1152,
        1,
        (unsigned int)SclEvent_Generic_Info,
        229,
        (__int64)"SclFsProcessVolume");
      VolumeHandle = SclpFsProcessVolumeByHandle(a1, Handle);
    }
    goto LABEL_31;
  }
  v14 = 0;
  if ( a1 )
    v14 = (_DWORD)a1 + 1152;
  VolumeHandle = -1073741637;
  SclLogGenericMessage(v14, 3, (unsigned int)SclEvent_Generic_Error, 206, (__int64)"SclFsProcessVolume");
LABEL_31:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)VolumeHandle;
}

```

## disassembly

```asm
0x18001188c  mov     [rsp-8+arg_10], rbx
0x180011891  push    rbp
0x180011892  push    rsi
0x180011893  push    rdi
0x180011894  push    r12
0x180011896  push    r13
0x180011898  push    r14
0x18001189a  push    r15
0x18001189c  lea     rbp, [rsp-3A0h]
0x1800118a4  sub     rsp, 4A0h
0x1800118ab  mov     rax, cs:__security_cookie
0x1800118b2  xor     rax, rsp
0x1800118b5  mov     [rbp+3D0h+var_40], rax
0x1800118bc  mov     r14, rdx
0x1800118bf  mov     [rsp+4D0h+Handle], 0
0x1800118c8  mov     rsi, rcx
0x1800118cb  mov     [rsp+4D0h+var_47C], 0
0x1800118d3  mov     r8, rdx
0x1800118d6  mov     [rsp+4D0h+var_480], 0
0x1800118de  mov     edx, 104h
0x1800118e3  mov     [rsp+4D0h+var_46C], 0
0x1800118eb  lea     rcx, [rbp+3D0h+var_250]
0x1800118f2  mov     [rsp+4D0h+var_470], 0
0x1800118fa  call    RtlStringCchCopyW
0x1800118ff  mov     ebx, eax
0x180011901  test    eax, eax
0x180011903  js      loc_180011C71
0x180011909  lea     rcx, [rbp+3D0h+var_250]
0x180011910  call    StrRTrm
0x180011915  lea     rdx, [rsp+4D0h+Handle]
0x18001191a  lea     rcx, [rbp+3D0h+var_250]
0x180011921  call    SclGetVolumeHandle
0x180011926  mov     ebx, eax
0x180011928  test    eax, eax
0x18001192a  js      loc_180011C71
0x180011930  mov     rcx, [rsp+4D0h+Handle]
0x180011935  lea     rdx, [rsp+4D0h+String1]
0x18001193a  call    SclpFsGetVolumeFileSystemName
0x18001193f  mov     ebx, eax
0x180011941  test    eax, eax
0x180011943  js      loc_180011C71
0x180011949  xor     eax, eax
0x18001194b  lea     r13, [rsi+480h]
0x180011952  mov     r9d, 6Ch ; 'l'
0x180011958  lea     rdi, aSclfsprocessvo; "SclFsProcessVolume"
0x18001195f  test    rsi, rsi
0x180011962  lea     r8, SclEvent_Generic_Info
0x180011969  mov     r12, r13
0x18001196c  cmovz   r12, rax
0x180011970  lea     rax, [rsp+4D0h+String1]
0x180011975  mov     [rsp+4D0h+var_4A0], rax
0x18001197a  lea     edx, [r9-6Bh]
0x18001197e  lea     rax, aFileSystemType; "File system type is: [%ws]"
0x180011985  mov     rcx, r12
0x180011988  mov     [rsp+4D0h+var_4A8], rax
0x18001198d  mov     [rsp+4D0h+var_4B0], rdi
0x180011992  call    SclLogGenericMessage
0x180011997  lea     rdx, aNtfs; "NTFS"
0x18001199e  lea     rcx, [rsp+4D0h+String1]; String1
0x1800119a3  call    cs:__imp__wcsicmp
0x1800119a9  lea     rdx, aRefs; "ReFS"
0x1800119b0  mov     ebx, eax
0x1800119b2  lea     rcx, [rsp+4D0h+String1]; String1
0x1800119b7  call    cs:__imp__wcsicmp
0x1800119bd  test    ebx, ebx
0x1800119bf  jnz     loc_180011B1C
0x1800119c5  mov     rcx, [rsp+4D0h+Handle]
0x1800119ca  lea     r8, [rsp+4D0h+var_480]
0x1800119cf  lea     rdx, [rsp+4D0h+var_47C]
0x1800119d4  call    SclpNtfsGetVersion
0x1800119d9  mov     ebx, eax
0x1800119db  test    eax, eax
0x1800119dd  js      loc_180011C71
0x1800119e3  mov     r15d, [rsp+4D0h+var_480]
0x1800119e8  lea     rax, aTheVersionOfVo_0; "The version of volume [%ws] is NTFS [%u"...
0x1800119ef  mov     ebx, [rsp+4D0h+var_47C]
0x1800119f3  lea     r8, SclEvent_Generic_Info
0x1800119fa  mov     [rsp+4D0h+var_490], r15d
0x1800119ff  mov     r9d, 89h
0x180011a05  mov     [rsp+4D0h+var_498], ebx
0x180011a09  mov     edx, 1
0x180011a0e  mov     [rsp+4D0h+var_4A0], r14
0x180011a13  mov     rcx, r12
0x180011a16  mov     [rsp+4D0h+var_4A8], rax
0x180011a1b  mov     [rsp+4D0h+var_4B0], rdi
0x180011a20  call    SclLogGenericMessage
0x180011a25  mov     edi, 3
0x180011a2a  cmp     ebx, edi
0x180011a2c  jb      loc_180011AF2
0x180011a32  jnz     short loc_180011A3E
0x180011a34  cmp     r15d, 1
0x180011a38  jb      loc_180011AF2
0x180011a3e  lea     rdx, [rsp+4D0h+var_470]
0x180011a43  lea     rcx, [rsp+4D0h+var_46C]
0x180011a48  call    SclGetOSVersion
0x180011a4d  mov     ebx, eax
0x180011a4f  test    eax, eax
0x180011a51  js      loc_180011C71
0x180011a57  mov     r15d, [rsp+4D0h+var_470]
0x180011a5c  lea     rax, aTheVersionOfTh; "The version of the current (host) OS is"...
0x180011a63  mov     r14d, [rsp+4D0h+var_46C]
0x180011a68  lea     r8, SclEvent_Generic_Info
0x180011a6f  mov     [rsp+4D0h+var_498], r15d
0x180011a74  mov     r9d, 0A3h
0x180011a7a  mov     dword ptr [rsp+4D0h+var_4A0], r14d
0x180011a7f  mov     edx, 1
0x180011a84  mov     [rsp+4D0h+var_4A8], rax
0x180011a89  mov     rcx, r12
0x180011a8c  lea     rax, aSclfsprocessvo; "SclFsProcessVolume"
0x180011a93  mov     [rsp+4D0h+var_4B0], rax
0x180011a98  call    SclLogGenericMessage
0x180011a9d  cmp     r14d, 6
0x180011aa1  jb      short loc_180011AB3
0x180011aa3  jnz     loc_180011BDE
0x180011aa9  cmp     r15d, 1
0x180011aad  jnb     loc_180011BDE
0x180011ab3  xor     ecx, ecx
0x180011ab5  lea     rax, aTheCurrentHost; "The current (host) OS is not supported "...
0x180011abc  mov     [rsp+4D0h+var_4A8], rax
0x180011ac1  lea     r8, SclEvent_Generic_Error
0x180011ac8  test    rsi, rsi
0x180011acb  lea     rax, aSclfsprocessvo; "SclFsProcessVolume"
0x180011ad2  mov     r9d, 0ACh
0x180011ad8  mov     [rsp+4D0h+var_4B0], rax
0x180011add  cmovnz  rcx, r13
0x180011ae1  mov     edx, edi
0x180011ae3  mov     ebx, 0C00000BBh
0x180011ae8  call    SclLogGenericMessage
0x180011aed  jmp     loc_180011BD6
0x180011af2  lea     rax, aTheNtfsVersion; "The NTFS version of volume [%ws] is not"...
0x180011af9  mov     [rsp+4D0h+var_4A0], r14
0x180011afe  mov     [rsp+4D0h+var_4A8], rax
0x180011b03  mov     r9d, 92h
0x180011b09  lea     rax, aSclfsprocessvo; "SclFsProcessVolume"
0x180011b10  mov     edx, edi
0x180011b12  mov     [rsp+4D0h+var_4B0], rax
0x180011b17  jmp     loc_180011C57
0x180011b1c  test    eax, eax
0x180011b1e  jnz     loc_180011C36
0x180011b24  mov     rcx, [rsp+4D0h+Handle]
0x180011b29  lea     r8, [rsp+4D0h+var_480]
0x180011b2e  lea     rdx, [rsp+4D0h+var_47C]
0x180011b33  call    SclpRefsGetVersion
0x180011b38  mov     ebx, eax
0x180011b3a  test    eax, eax
0x180011b3c  js      loc_180011C71
0x180011b42  mov     eax, [rsp+4D0h+var_480]
0x180011b46  lea     r8, SclEvent_Generic_Info
0x180011b4d  mov     r15d, [rsp+4D0h+var_47C]
0x180011b52  mov     r9d, 0C5h
0x180011b58  mov     [rsp+4D0h+var_490], eax
0x180011b5c  mov     edx, 1
0x180011b61  mov     [rsp+4D0h+var_498], r15d
0x180011b66  lea     rax, aTheVersionOfVo; "The version of volume [%ws] is ReFS [%u"...
0x180011b6d  mov     [rsp+4D0h+var_4A0], r14
0x180011b72  mov     rcx, r12
0x180011b75  mov     [rsp+4D0h+var_4A8], rax
0x180011b7a  mov     [rsp+4D0h+var_4B0], rdi
0x180011b7f  call    SclLogGenericMessage
0x180011b84  mov     edi, 3
0x180011b89  cmp     r15d, edi
0x180011b8c  jb      short loc_180011B97
0x180011b8e  jnz     short loc_180011BDE
0x180011b90  cmp     [rsp+4D0h+var_480], 0Ch
0x180011b95  jnb     short loc_180011BDE
0x180011b97  xor     ecx, ecx
0x180011b99  mov     [rsp+4D0h+var_4A0], r14
0x180011b9e  lea     rax, aTheRefsVersion; "The ReFS version of volume [%ws] is not"...
0x180011ba5  test    rsi, rsi
0x180011ba8  mov     [rsp+4D0h+var_4A8], rax
0x180011bad  lea     r8, SclEvent_Generic_Error
0x180011bb4  lea     rax, aSclfsprocessvo; "SclFsProcessVolume"
0x180011bbb  cmovnz  rcx, r13
0x180011bbf  mov     r9d, 0CEh
0x180011bc5  mov     [rsp+4D0h+var_4B0], rax
0x180011bca  mov     edx, edi
0x180011bcc  mov     ebx, 0C00000BBh
0x180011bd1  call    SclLogGenericMessage
0x180011bd6  test    ebx, ebx
0x180011bd8  js      loc_180011C71
0x180011bde  cmp     byte ptr [rsi], 0
0x180011be1  jz      loc_180011C71
0x180011be7  lea     rax, [rbp+3D0h+var_250]
0x180011bee  mov     r9d, 0E5h
0x180011bf4  mov     [rsp+4D0h+var_4A0], rax
0x180011bf9  lea     r8, SclEvent_Generic_Info
0x180011c00  lea     rax, aProcessingVolu; "Processing volume [%ws]..."
0x180011c07  mov     edx, 1
0x180011c0c  mov     [rsp+4D0h+var_4A8], rax
0x180011c11  mov     rcx, r13
0x180011c14  lea     rax, aSclfsprocessvo; "SclFsProcessVolume"
0x180011c1b  mov     [rsp+4D0h+var_4B0], rax
0x180011c20  call    SclLogGenericMessage
0x180011c25  mov     rdx, [rsp+4D0h+Handle]
0x180011c2a  mov     rcx, rsi
0x180011c2d  call    SclpFsProcessVolumeByHandle
0x180011c32  mov     ebx, eax
0x180011c34  jmp     short loc_180011C71
0x180011c36  mov     [rsp+4D0h+var_4A0], r14
0x180011c3b  lea     rax, aVolumeWsDoesNo; "Volume [%ws] does not have a supported "...
0x180011c42  mov     [rsp+4D0h+var_4A8], rax
0x180011c47  mov     r9d, 0DAh
0x180011c4d  mov     [rsp+4D0h+var_4B0], rdi
0x180011c52  mov     edx, 3
0x180011c57  xor     ecx, ecx
0x180011c59  lea     r8, SclEvent_Generic_Error
0x180011c60  test    rsi, rsi
0x180011c63  mov     ebx, 0C00000BBh
0x180011c68  cmovnz  rcx, r13
0x180011c6c  call    SclLogGenericMessage
0x180011c71  mov     rcx, [rsp+4D0h+Handle]; Handle
0x180011c76  test    rcx, rcx
0x180011c79  jz      short loc_180011C81
0x180011c7b  call    cs:__imp_NtClose
0x180011c81  mov     eax, ebx
0x180011c83  mov     rcx, [rbp+3D0h+var_40]
0x180011c8a  xor     rcx, rsp; StackCookie
0x180011c8d  call    __security_check_cookie
0x180011c92  mov     rbx, [rsp+4D0h+arg_10]
0x180011c9a  add     rsp, 4A0h
0x180011ca1  pop     r15
0x180011ca3  pop     r14
0x180011ca5  pop     r13
0x180011ca7  pop     r12
0x180011ca9  pop     rdi
0x180011caa  pop     rsi
0x180011cab  pop     rbp
0x180011cac  retn
```
