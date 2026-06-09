# WcCopyFileBasicInformation

- ea: `0x14001e028`
- end: `0x14001e222`
- name: `WcCopyFileBasicInformation`
- size: `506`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PFLT_INSTANCE Instance, PFILE_OBJECT, PFLT_INSTANCE, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001e374`

## callees

- `0x1400020c4`
- `0x140007c60`
- `0x14001e028`
- `0x14001e228`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x14001e1a8`
- `FLTMGR!FltSetInformationFile` at `0x14001e1a8`
- `FLTMGR!FltQueryInformationFile` at `0x14001e094`
- `FLTMGR!FltQueryInformationFile` at `0x14001e140`
- `FLTMGR!FltQueryInformationFile` at `0x14001e094`
- `FLTMGR!FltQueryInformationFile` at `0x14001e140`

## pseudocode

```c
__int64 __fastcall WcCopyFileBasicInformation(
        PFILE_OBJECT FileObject,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT a3,
        PFLT_INSTANCE a4,
        char a5)
{
  int v9; // edx
  NTSTATUS InformationFile; // ebx
  int v11; // r9d
  char v13; // [rsp+30h] [rbp-51h]
  NTSTATUS v14; // [rsp+38h] [rbp-49h]
  __int128 FileInformation; // [rsp+40h] [rbp-41h] BYREF
  __int128 v16; // [rsp+50h] [rbp-31h]
  __int64 v17; // [rsp+60h] [rbp-21h]
  _OWORD v18[2]; // [rsp+68h] [rbp-19h] BYREF
  __int64 v19; // [rsp+88h] [rbp+7h]

  v17 = 0;
  v19 = 0;
  FileInformation = 0;
  v16 = 0;
  memset(v18, 0, sizeof(v18));
  InformationFile = FltQueryInformationFile(Instance, FileObject, &FileInformation, 0x28u, FileBasicInformation, 0);
  if ( InformationFile >= 0 )
  {
    if ( (a5 & 4) == 0 )
    {
      FileInformation = 0;
      v16 = 0;
    }
    if ( (a5 & 8) != 0 )
    {
      InformationFile = FltQueryInformationFile(a4, a3, v18, 0x28u, FileBasicInformation, 0);
      if ( InformationFile < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return (unsigned int)InformationFile;
        v14 = InformationFile;
        v11 = 128;
        v13 = 51;
        goto LABEL_4;
      }
      LODWORD(v17) = v19 & 0xFFFFBFFF | v17;
    }
    else
    {
      LODWORD(v17) = 0;
    }
    InformationFile = FltSetInformationFile(a4, a3, &FileInformation, 0x28u, FileBasicInformation);
    if ( InformationFile < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)InformationFile;
      v14 = InformationFile;
      v11 = 129;
      v13 = 71;
      goto LABEL_4;
    }
    if ( (a5 & 8) != 0 && (v17 & 0x800) != 0 )
      return (unsigned int)WcCopyFileCompression(FileObject, Instance, a3, a4);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = InformationFile;
    v11 = 127;
    v13 = 28;
LABEL_4:
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      15,
      v11,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      v13,
      v14,
      FileInformation,
      v16);
  }
  return (unsigned int)InformationFile;
}

```

## disassembly

```asm
0x14001e028  push    rbp
0x14001e02a  push    rbx
0x14001e02b  push    rsi
0x14001e02c  push    rdi
0x14001e02d  push    r12
0x14001e02f  push    r14
0x14001e031  push    r15
0x14001e033  lea     rbp, [rsp-1Fh]
0x14001e038  sub     rsp, 0A0h
0x14001e03f  mov     rax, cs:__security_cookie
0x14001e046  xor     rax, rsp
0x14001e049  mov     [rbp+4Fh+var_40], rax
0x14001e04d  xor     eax, eax
0x14001e04f  mov     r12, rdx
0x14001e052  xorps   xmm0, xmm0
0x14001e055  mov     [rsp+0D0h+LengthReturned], rax; LengthReturned
0x14001e05a  xorps   xmm1, xmm1
0x14001e05d  mov     [rbp+4Fh+var_70], rax
0x14001e061  mov     r14, r9
0x14001e064  mov     [rbp+4Fh+var_48], rax
0x14001e068  mov     rsi, r8
0x14001e06b  mov     [rsp+0D0h+FileInformationClass], 4; FileInformationClass
0x14001e073  mov     r15, rcx
0x14001e076  lea     r9d, [rax+28h]; Length
0x14001e07a  mov     rdx, rcx; FileObject
0x14001e07d  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x14001e081  mov     rcx, r12; Instance
0x14001e084  movups  [rbp+4Fh+FileInformation], xmm0
0x14001e088  movups  [rbp+4Fh+var_80], xmm0
0x14001e08c  movups  [rbp+4Fh+var_68], xmm1
0x14001e090  movups  [rbp+4Fh+var_58], xmm1
0x14001e094  call    cs:__imp_FltQueryInformationFile
0x14001e09b  nop     dword ptr [rax+rax+00h]
0x14001e0a0  mov     ebx, eax
0x14001e0a2  test    eax, eax
0x14001e0a4  jns     short loc_14001E101
0x14001e0a6  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e0ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e0b4  jz      loc_14001E201
0x14001e0ba  mov     [rsp+0D0h+var_98], ebx
0x14001e0be  mov     r9d, 7Fh
0x14001e0c4  mov     dword ptr [rsp+0D0h+var_A0], 111Ch
0x14001e0cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e0d3  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001e0da  mov     [rsp+0D0h+LengthReturned], rax
0x14001e0df  mov     r8d, 0Fh
0x14001e0e5  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001e0ec  mov     dl, 2
0x14001e0ee  mov     qword ptr [rsp+0D0h+FileInformationClass], rax
0x14001e0f3  mov     rcx, [rcx+40h]
0x14001e0f7  call    WPP_RECORDER_SF_sDd
0x14001e0fc  jmp     loc_14001E201
0x14001e101  mov     edi, [rbp+4Fh+arg_20]
0x14001e104  test    dil, 4
0x14001e108  jnz     short loc_14001E11A
0x14001e10a  xorps   xmm0, xmm0
0x14001e10d  xorps   xmm1, xmm1
0x14001e110  movdqu  [rbp+4Fh+FileInformation], xmm0
0x14001e115  movdqu  [rbp+4Fh+var_80], xmm1
0x14001e11a  and     edi, 8
0x14001e11d  jz      short loc_14001E189
0x14001e11f  mov     [rsp+0D0h+LengthReturned], 0; LengthReturned
0x14001e128  lea     r8, [rbp+4Fh+var_68]; FileInformation
0x14001e12c  mov     r9d, 28h ; '('; Length
0x14001e132  mov     [rsp+0D0h+FileInformationClass], 4; FileInformationClass
0x14001e13a  mov     rdx, rsi; FileObject
0x14001e13d  mov     rcx, r14; Instance
0x14001e140  call    cs:__imp_FltQueryInformationFile
0x14001e147  nop     dword ptr [rax+rax+00h]
0x14001e14c  mov     ebx, eax
0x14001e14e  test    eax, eax
0x14001e150  jns     short loc_14001E17D
0x14001e152  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e159  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e160  jz      loc_14001E201
0x14001e166  mov     [rsp+0D0h+var_98], ebx
0x14001e16a  mov     r9d, 80h
0x14001e170  mov     dword ptr [rsp+0D0h+var_A0], 1133h
0x14001e178  jmp     loc_14001E0CC
0x14001e17d  mov     eax, dword ptr [rbp+4Fh+var_48]
0x14001e180  btr     eax, 0Eh
0x14001e184  or      dword ptr [rbp+4Fh+var_70], eax
0x14001e187  jmp     short loc_14001E190
0x14001e189  mov     dword ptr [rbp+4Fh+var_70], 0
0x14001e190  mov     r9d, 28h ; '('; Length
0x14001e196  mov     [rsp+0D0h+FileInformationClass], 4; FileInformationClass
0x14001e19e  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x14001e1a2  mov     rdx, rsi; FileObject
0x14001e1a5  mov     rcx, r14; Instance
0x14001e1a8  call    cs:__imp_FltSetInformationFile
0x14001e1af  nop     dword ptr [rax+rax+00h]
0x14001e1b4  mov     ebx, eax
0x14001e1b6  test    eax, eax
0x14001e1b8  jns     short loc_14001E1E1
0x14001e1ba  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e1c1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e1c8  jz      short loc_14001E201
0x14001e1ca  mov     [rsp+0D0h+var_98], ebx
0x14001e1ce  mov     r9d, 81h
0x14001e1d4  mov     dword ptr [rsp+0D0h+var_A0], 1147h
0x14001e1dc  jmp     loc_14001E0CC
0x14001e1e1  test    edi, edi
0x14001e1e3  jz      short loc_14001E201
0x14001e1e5  test    dword ptr [rbp+4Fh+var_70], 800h
0x14001e1ec  jz      short loc_14001E201
0x14001e1ee  mov     r9, r14; PFLT_INSTANCE
0x14001e1f1  mov     r8, rsi; PFILE_OBJECT
0x14001e1f4  mov     rdx, r12; Instance
0x14001e1f7  mov     rcx, r15; FileObject
0x14001e1fa  call    WcCopyFileCompression
0x14001e1ff  mov     ebx, eax
0x14001e201  mov     eax, ebx
0x14001e203  mov     rcx, [rbp+4Fh+var_40]
0x14001e207  xor     rcx, rsp; StackCookie
0x14001e20a  call    __security_check_cookie
0x14001e20f  add     rsp, 0A0h
0x14001e216  pop     r15
0x14001e218  pop     r14
0x14001e21a  pop     r12
0x14001e21c  pop     rdi
0x14001e21d  pop     rsi
0x14001e21e  pop     rbx
0x14001e21f  pop     rbp
0x14001e220  retn
```
