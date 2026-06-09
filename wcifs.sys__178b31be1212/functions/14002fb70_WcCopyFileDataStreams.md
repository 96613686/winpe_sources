# WcCopyFileDataStreams

- ea: `0x14002fb70`
- end: `0x14002fecb`
- name: `WcCopyFileDataStreams`
- size: `859`
- prototype: `__int64 __fastcall(void *, struct _FILE_OBJECT *, struct _FLT_INSTANCE *, void *, struct _FILE_OBJECT *FileObject, struct _FLT_INSTANCE *, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001e374`
- `0x14002daa4`

## callees

- `0x1400020c4`
- `0x140007c60`
- `0x140017b48`
- `0x14001d5b0`
- `0x14002fb70`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14002fcf7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002fcf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe47`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe47`
- `ntoskrnl!ExAllocatePool2` at `0x14002fc24`
- `ntoskrnl!ExAllocatePool2` at `0x14002fc24`
- `FLTMGR!FltSetInformationFile` at `0x14002fd36`
- `FLTMGR!FltSetInformationFile` at `0x14002fd36`
- `FLTMGR!FltQueryInformationFile` at `0x14002fc59`
- `FLTMGR!FltQueryInformationFile` at `0x14002fc59`

## pseudocode

```c
__int64 __fastcall WcCopyFileDataStreams(
        void *a1,
        struct _FILE_OBJECT *a2,
        struct _FLT_INSTANCE *a3,
        void *a4,
        struct _FILE_OBJECT *FileObject,
        struct _FLT_INSTANCE *a6,
        char a7)
{
  int v9; // ebx
  _DWORD *Pool2; // rsi
  ULONG v11; // edi
  __int64 v12; // rdx
  int v13; // edx
  NTSTATUS v14; // eax
  int v15; // edx
  int v16; // r9d
  unsigned int *i; // rdi
  __int64 v18; // rax
  int LengthReturned; // [rsp+28h] [rbp-79h]
  char v21; // [rsp+30h] [rbp-71h]
  char v22; // [rsp+38h] [rbp-69h]
  ULONG v23; // [rsp+50h] [rbp-51h] BYREF
  PFLT_INSTANCE Instance; // [rsp+58h] [rbp-49h]
  UNICODE_STRING String1; // [rsp+60h] [rbp-41h] BYREF
  UNICODE_STRING String2; // [rsp+70h] [rbp-31h] BYREF
  __int64 FileInformation; // [rsp+80h] [rbp-21h] BYREF
  void *v28; // [rsp+88h] [rbp-19h]
  void *v29; // [rsp+90h] [rbp-11h]
  __int128 v30; // [rsp+98h] [rbp-9h] BYREF

  v30 = *(_OWORD *)L"::$DATA";
  Instance = a6;
  v28 = a4;
  String1 = 0;
  v29 = a1;
  *(_QWORD *)&String2.Length = 1048590;
  String2.Buffer = (PWSTR)&v30;
  v23 = 0;
  if ( (a7 & 3) == 0 )
    return (unsigned int)-1073741811;
  Pool2 = 0;
  v11 = 32;
  do
  {
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0x69664357u);
    v11 += 2048;
    v12 = 32;
    if ( v11 >= 0x20 )
      v12 = v11;
    Pool2 = (_DWORD *)ExAllocatePool2(256, v12, 1768309591);
    if ( !Pool2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v13,
          15,
          116,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          107,
          v11);
      }
      return (unsigned int)-1073741801;
    }
    v14 = FltQueryInformationFile(a3, a2, Pool2, v11, FileStreamInformation, &v23);
    v9 = v14;
  }
  while ( v14 == -2147483643 || v14 == -1073741789 );
  if ( v14 < 0 )
  {
    if ( v14 == -1073741811 || v14 == -1073741822 )
    {
      v9 = 0;
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v22 = v14;
      v16 = 117;
      v21 = -120;
      goto LABEL_32;
    }
    goto LABEL_33;
  }
  if ( !v23 || !Pool2[1] )
    goto LABEL_33;
  for ( i = Pool2; ; i = (unsigned int *)((char *)i + v18) )
  {
    String1.Buffer = (PWSTR)(i + 6);
    String1.Length = *((_WORD *)i + 2);
    String1.MaximumLength = *((_WORD *)i + 2);
    if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
      break;
    if ( (a7 & 2) != 0 )
    {
      FileInformation = *((_QWORD *)i + 1);
      v9 = FltSetInformationFile(Instance, FileObject, &FileInformation, 8u, FileEndOfFileInformation);
      if ( v9 < 0 )
        goto LABEL_33;
      LOBYTE(LengthReturned) = 0;
      v9 = WcCopyStreamData(a3, a2, *((_QWORD *)i + 1), Instance, FileObject, LengthReturned);
      if ( v9 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_33;
        v22 = v9;
        v16 = 118;
        v21 = -37;
        goto LABEL_32;
      }
    }
LABEL_28:
    v18 = *i;
    if ( !(_DWORD)v18 )
      goto LABEL_33;
  }
  if ( (a7 & 1) == 0 )
    goto LABEL_28;
  v9 = WcCopyDataStreamByName(
         &String1,
         v29,
         (__int64)a2,
         a3,
         &String1,
         v28,
         (__int64)FileObject,
         Instance,
         *((_QWORD *)i + 1));
  if ( v9 >= 0 )
    goto LABEL_28;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_33;
  v22 = v9;
  v16 = 119;
  v21 = -16;
LABEL_32:
  LOBYTE(v15) = 2;
  WPP_RECORDER_SF_sDd(
    wil_details_featureDescriptors_a->DeviceExtension,
    v15,
    15,
    v16,
    (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
    (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
    v21,
    v22);
LABEL_33:
  ExFreePoolWithTag(Pool2, 0x69664357u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002fb70  push    rbp
0x14002fb72  push    rbx
0x14002fb73  push    rsi
0x14002fb74  push    rdi
0x14002fb75  push    r12
0x14002fb77  push    r13
0x14002fb79  push    r15
0x14002fb7b  lea     rbp, [rsp-0Fh]
0x14002fb80  sub     rsp, 0B0h
0x14002fb87  mov     rax, cs:__security_cookie
0x14002fb8e  xor     rax, rsp
0x14002fb91  mov     [rbp+3Fh+var_38], rax
0x14002fb95  test    [rbp+3Fh+arg_30], 3
0x14002fb99  mov     r12, r8
0x14002fb9c  movups  xmm0, xmmword ptr cs:aData; "::$DATA"
0x14002fba3  mov     rax, [rbp+3Fh+arg_28]
0x14002fba7  mov     r15, rdx
0x14002fbaa  mov     r13, [rbp+3Fh+FileObject]
0x14002fbae  movdqu  [rbp+3Fh+var_48], xmm0
0x14002fbb3  mov     [rbp+3Fh+Instance], rax
0x14002fbb7  lea     rax, [rbp+3Fh+var_48]
0x14002fbbb  xorps   xmm0, xmm0
0x14002fbbe  mov     [rbp+3Fh+var_58], r9
0x14002fbc2  movups  xmmword ptr [rbp+3Fh+String1.Length], xmm0
0x14002fbc6  mov     [rbp+3Fh+var_50], rcx
0x14002fbca  mov     qword ptr [rbp+3Fh+String2.Length], 10000Eh
0x14002fbd2  mov     [rbp+3Fh+String2.Buffer], rax
0x14002fbd6  mov     [rbp+3Fh+var_90], 0
0x14002fbdd  jnz     short loc_14002FBE9
0x14002fbdf  mov     ebx, 0C000000Dh
0x14002fbe4  jmp     loc_14002FEAA
0x14002fbe9  xor     esi, esi
0x14002fbeb  lea     edi, [rsi+20h]
0x14002fbee  test    rsi, rsi
0x14002fbf1  jz      short loc_14002FC07
0x14002fbf3  mov     edx, 69664357h; Tag
0x14002fbf8  mov     rcx, rsi; P
0x14002fbfb  call    cs:__imp_ExFreePoolWithTag
0x14002fc02  nop     dword ptr [rax+rax+00h]
0x14002fc07  add     edi, 800h
0x14002fc0d  mov     edx, 20h ; ' '
0x14002fc12  cmp     edi, 20h ; ' '
0x14002fc15  jb      short loc_14002FC19
0x14002fc17  mov     edx, edi
0x14002fc19  mov     ecx, 100h
0x14002fc1e  mov     r8d, 69664357h
0x14002fc24  call    cs:__imp_ExAllocatePool2
0x14002fc2b  nop     dword ptr [rax+rax+00h]
0x14002fc30  mov     rsi, rax
0x14002fc33  test    rax, rax
0x14002fc36  jz      loc_14002FE55
0x14002fc3c  lea     rax, [rbp+3Fh+var_90]
0x14002fc40  mov     r9d, edi; Length
0x14002fc43  mov     [rsp+0E0h+LengthReturned], rax; LengthReturned
0x14002fc48  mov     r8, rsi; FileInformation
0x14002fc4b  mov     rdx, r15; FileObject
0x14002fc4e  mov     [rsp+0E0h+FileInformationClass], 16h; FileInformationClass
0x14002fc56  mov     rcx, r12; Instance
0x14002fc59  call    cs:__imp_FltQueryInformationFile
0x14002fc60  nop     dword ptr [rax+rax+00h]
0x14002fc65  mov     ebx, eax
0x14002fc67  cmp     eax, 80000005h
0x14002fc6c  jz      short loc_14002FBEE
0x14002fc6e  cmp     eax, 0C0000023h
0x14002fc73  jz      loc_14002FBEE
0x14002fc79  test    eax, eax
0x14002fc7b  jns     short loc_14002FCBD
0x14002fc7d  cmp     eax, 0C000000Dh
0x14002fc82  jz      short loc_14002FCB6
0x14002fc84  cmp     eax, 0C0000002h
0x14002fc89  jz      short loc_14002FCB6
0x14002fc8b  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fc92  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fc99  jz      loc_14002FE3F
0x14002fc9f  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14002fca3  mov     r9d, 75h ; 'u'
0x14002fca9  mov     dword ptr [rsp+0E0h+var_B0], 0F88h
0x14002fcb1  jmp     loc_14002FE0F
0x14002fcb6  xor     ebx, ebx
0x14002fcb8  jmp     loc_14002FE3F
0x14002fcbd  cmp     [rbp+3Fh+var_90], 0
0x14002fcc1  jz      loc_14002FE3F
0x14002fcc7  cmp     dword ptr [rsi+4], 0
0x14002fccb  jz      loc_14002FE3F
0x14002fcd1  mov     rdi, rsi
0x14002fcd4  lea     rax, [rdi+18h]
0x14002fcd8  mov     r8b, 1; CaseInSensitive
0x14002fcdb  mov     [rbp+3Fh+String1.Buffer], rax
0x14002fcdf  lea     rdx, [rbp+3Fh+String2]; String2
0x14002fce3  movzx   eax, word ptr [rdi+4]
0x14002fce7  lea     rcx, [rbp+3Fh+String1]; String1
0x14002fceb  mov     [rbp+3Fh+String1.Length], ax
0x14002fcef  movzx   eax, word ptr [rdi+4]
0x14002fcf3  mov     [rbp+3Fh+String1.MaximumLength], ax
0x14002fcf7  call    cs:__imp_RtlCompareUnicodeString
0x14002fcfe  nop     dword ptr [rax+rax+00h]
0x14002fd03  test    eax, eax
0x14002fd05  jnz     loc_14002FD97
0x14002fd0b  test    [rbp+3Fh+arg_30], 2
0x14002fd0f  jz      loc_14002FDDF
0x14002fd15  mov     rax, [rdi+8]
0x14002fd19  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x14002fd1d  mov     rcx, [rbp+3Fh+Instance]; Instance
0x14002fd21  mov     r9d, 8; Length
0x14002fd27  mov     rdx, r13; FileObject
0x14002fd2a  mov     [rbp+3Fh+FileInformation], rax
0x14002fd2e  mov     [rsp+0E0h+FileInformationClass], 14h; FileInformationClass
0x14002fd36  call    cs:__imp_FltSetInformationFile
0x14002fd3d  nop     dword ptr [rax+rax+00h]
0x14002fd42  mov     ebx, eax
0x14002fd44  test    eax, eax
0x14002fd46  js      loc_14002FE3F
0x14002fd4c  mov     r9, [rbp+3Fh+Instance]
0x14002fd50  mov     rdx, r15
0x14002fd53  mov     r8, [rdi+8]
0x14002fd57  mov     rcx, r12
0x14002fd5a  mov     byte ptr [rsp+0E0h+LengthReturned], 0
0x14002fd5f  mov     qword ptr [rsp+0E0h+FileInformationClass], r13
0x14002fd64  call    WcCopyStreamData
0x14002fd69  mov     ebx, eax
0x14002fd6b  test    eax, eax
0x14002fd6d  jns     short loc_14002FDDF
0x14002fd6f  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fd76  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fd7d  jz      loc_14002FE3F
0x14002fd83  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14002fd87  mov     r9d, 76h ; 'v'
0x14002fd8d  mov     dword ptr [rsp+0E0h+var_B0], 0FDBh
0x14002fd95  jmp     short loc_14002FE0F
0x14002fd97  test    [rbp+3Fh+arg_30], 1
0x14002fd9b  jz      short loc_14002FDDF
0x14002fd9d  mov     rax, [rdi+8]
0x14002fda1  lea     rcx, [rbp+3Fh+String1]
0x14002fda5  mov     rdx, [rbp+3Fh+var_50]
0x14002fda9  mov     r9, r12
0x14002fdac  mov     [rsp+0E0h+var_A0], rax
0x14002fdb1  mov     r8, r15
0x14002fdb4  mov     rax, [rbp+3Fh+Instance]
0x14002fdb8  mov     [rsp+0E0h+var_A8], rax
0x14002fdbd  mov     rax, [rbp+3Fh+var_58]
0x14002fdc1  mov     [rsp+0E0h+var_B0], r13
0x14002fdc6  mov     [rsp+0E0h+LengthReturned], rax
0x14002fdcb  lea     rax, [rbp+3Fh+String1]
0x14002fdcf  mov     qword ptr [rsp+0E0h+FileInformationClass], rax
0x14002fdd4  call    WcCopyDataStreamByName
0x14002fdd9  mov     ebx, eax
0x14002fddb  test    eax, eax
0x14002fddd  js      short loc_14002FDED
0x14002fddf  mov     eax, [rdi]
0x14002fde1  test    eax, eax
0x14002fde3  jz      short loc_14002FE3F
0x14002fde5  add     rdi, rax
0x14002fde8  jmp     loc_14002FCD4
0x14002fded  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fdf4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fdfb  jz      short loc_14002FE3F
0x14002fdfd  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14002fe01  mov     r9d, 77h ; 'w'
0x14002fe07  mov     dword ptr [rsp+0E0h+var_B0], 0FF0h
0x14002fe0f  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002fe16  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002fe1d  mov     [rsp+0E0h+LengthReturned], rax
0x14002fe22  mov     r8d, 0Fh
0x14002fe28  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002fe2f  mov     dl, 2
0x14002fe31  mov     qword ptr [rsp+0E0h+FileInformationClass], rax
0x14002fe36  mov     rcx, [rcx+40h]
0x14002fe3a  call    WPP_RECORDER_SF_sDd
0x14002fe3f  mov     edx, 69664357h; Tag
0x14002fe44  mov     rcx, rsi; P
0x14002fe47  call    cs:__imp_ExFreePoolWithTag
0x14002fe4e  nop     dword ptr [rax+rax+00h]
0x14002fe53  jmp     short loc_14002FEAA
0x14002fe55  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fe5c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fe63  jz      short loc_14002FEA5
0x14002fe65  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002fe6c  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002fe73  mov     dword ptr [rsp+0E0h+var_A8], edi
0x14002fe77  mov     r9d, 74h ; 't'
0x14002fe7d  mov     dword ptr [rsp+0E0h+var_B0], 0F6Bh
0x14002fe85  mov     dl, 2
0x14002fe87  mov     [rsp+0E0h+LengthReturned], rax
0x14002fe8c  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002fe93  mov     rcx, [rcx+40h]
0x14002fe97  lea     r8d, [r9-65h]
0x14002fe9b  mov     qword ptr [rsp+0E0h+FileInformationClass], rax
0x14002fea0  call    WPP_RECORDER_SF_sDd
0x14002fea5  mov     ebx, 0C0000017h
0x14002feaa  mov     eax, ebx
0x14002feac  mov     rcx, [rbp+3Fh+var_38]
0x14002feb0  xor     rcx, rsp; StackCookie
0x14002feb3  call    __security_check_cookie
0x14002feb8  add     rsp, 0B0h
0x14002febf  pop     r15
0x14002fec1  pop     r13
0x14002fec3  pop     r12
0x14002fec5  pop     rdi
0x14002fec6  pop     rsi
0x14002fec7  pop     rbx
0x14002fec8  pop     rbp
0x14002fec9  retn
```
