# WcCopyFileDataStreams

- ea: `0x14002fb20`
- end: `0x14002fe7b`
- name: `WcCopyFileDataStreams`
- size: `859`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001e374`
- `0x14002da54`

## callees

- `0x1400020c4`
- `0x140007c60`
- `0x140017b48`
- `0x14001d5b0`
- `0x14002fb20`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14002fca7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002fca7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fdf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fdf7`
- `ntoskrnl!ExAllocatePool2` at `0x14002fbd4`
- `ntoskrnl!ExAllocatePool2` at `0x14002fbd4`
- `FLTMGR!FltSetInformationFile` at `0x14002fce6`
- `FLTMGR!FltSetInformationFile` at `0x14002fce6`
- `FLTMGR!FltQueryInformationFile` at `0x14002fc09`
- `FLTMGR!FltQueryInformationFile` at `0x14002fc09`

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
  char v20; // [rsp+30h] [rbp-71h]
  char v21; // [rsp+38h] [rbp-69h]
  ULONG LengthReturned; // [rsp+50h] [rbp-51h] BYREF
  PFLT_INSTANCE Instance; // [rsp+58h] [rbp-49h]
  UNICODE_STRING String1; // [rsp+60h] [rbp-41h] BYREF
  UNICODE_STRING String2; // [rsp+70h] [rbp-31h] BYREF
  __int64 FileInformation; // [rsp+80h] [rbp-21h] BYREF
  void *v27; // [rsp+88h] [rbp-19h]
  void *v28; // [rsp+90h] [rbp-11h]
  __int128 v29; // [rsp+98h] [rbp-9h] BYREF

  v29 = *(_OWORD *)L"::$DATA";
  Instance = a6;
  v27 = a4;
  String1 = 0;
  v28 = a1;
  *(_QWORD *)&String2.Length = 1048590;
  String2.Buffer = (PWSTR)&v29;
  LengthReturned = 0;
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
          WPP_GLOBAL_Control->DeviceExtension,
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
    v14 = FltQueryInformationFile(a3, a2, Pool2, v11, FileStreamInformation, &LengthReturned);
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
      v21 = v14;
      v16 = 117;
      v20 = -120;
      goto LABEL_32;
    }
    goto LABEL_33;
  }
  if ( !LengthReturned || !Pool2[1] )
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
      v9 = WcCopyStreamData(a3, a2, *((_QWORD *)i + 1), Instance, FileObject, 0);
      if ( v9 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_33;
        v21 = v9;
        v16 = 118;
        v20 = -37;
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
         v28,
         (__int64)a2,
         a3,
         &String1,
         v27,
         (__int64)FileObject,
         Instance,
         *((_QWORD *)i + 1));
  if ( v9 >= 0 )
    goto LABEL_28;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_33;
  v21 = v9;
  v16 = 119;
  v20 = -16;
LABEL_32:
  LOBYTE(v15) = 2;
  WPP_RECORDER_SF_sDd(
    WPP_GLOBAL_Control->DeviceExtension,
    v15,
    15,
    v16,
    (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
    (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
    v20,
    v21);
LABEL_33:
  ExFreePoolWithTag(Pool2, 0x69664357u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002fb20  push    rbp
0x14002fb22  push    rbx
0x14002fb23  push    rsi
0x14002fb24  push    rdi
0x14002fb25  push    r12
0x14002fb27  push    r13
0x14002fb29  push    r15
0x14002fb2b  lea     rbp, [rsp-0Fh]
0x14002fb30  sub     rsp, 0B0h
0x14002fb37  mov     rax, cs:__security_cookie
0x14002fb3e  xor     rax, rsp
0x14002fb41  mov     [rbp+3Fh+var_38], rax
0x14002fb45  test    [rbp+3Fh+arg_30], 3
0x14002fb49  mov     r12, r8
0x14002fb4c  movups  xmm0, xmmword ptr cs:aData; "::$DATA"
0x14002fb53  mov     rax, [rbp+3Fh+arg_28]
0x14002fb57  mov     r15, rdx
0x14002fb5a  mov     r13, [rbp+3Fh+FileObject]
0x14002fb5e  movdqu  [rbp+3Fh+var_48], xmm0
0x14002fb63  mov     [rbp+3Fh+Instance], rax
0x14002fb67  lea     rax, [rbp+3Fh+var_48]
0x14002fb6b  xorps   xmm0, xmm0
0x14002fb6e  mov     [rbp+3Fh+var_58], r9
0x14002fb72  movups  xmmword ptr [rbp+3Fh+String1.Length], xmm0
0x14002fb76  mov     [rbp+3Fh+var_50], rcx
0x14002fb7a  mov     qword ptr [rbp+3Fh+String2.Length], 10000Eh
0x14002fb82  mov     [rbp+3Fh+String2.Buffer], rax
0x14002fb86  mov     [rbp+3Fh+var_90], 0
0x14002fb8d  jnz     short loc_14002FB99
0x14002fb8f  mov     ebx, 0C000000Dh
0x14002fb94  jmp     loc_14002FE5A
0x14002fb99  xor     esi, esi
0x14002fb9b  lea     edi, [rsi+20h]
0x14002fb9e  test    rsi, rsi
0x14002fba1  jz      short loc_14002FBB7
0x14002fba3  mov     edx, 69664357h; Tag
0x14002fba8  mov     rcx, rsi; P
0x14002fbab  call    cs:__imp_ExFreePoolWithTag
0x14002fbb2  nop     dword ptr [rax+rax+00h]
0x14002fbb7  add     edi, 800h
0x14002fbbd  mov     edx, 20h ; ' '
0x14002fbc2  cmp     edi, 20h ; ' '
0x14002fbc5  jb      short loc_14002FBC9
0x14002fbc7  mov     edx, edi
0x14002fbc9  mov     ecx, 100h
0x14002fbce  mov     r8d, 69664357h
0x14002fbd4  call    cs:__imp_ExAllocatePool2
0x14002fbdb  nop     dword ptr [rax+rax+00h]
0x14002fbe0  mov     rsi, rax
0x14002fbe3  test    rax, rax
0x14002fbe6  jz      loc_14002FE05
0x14002fbec  lea     rax, [rbp+3Fh+var_90]
0x14002fbf0  mov     r9d, edi; Length
0x14002fbf3  mov     [rsp+0E0h+LengthReturned], rax; LengthReturned
0x14002fbf8  mov     r8, rsi; FileInformation
0x14002fbfb  mov     rdx, r15; FileObject
0x14002fbfe  mov     [rsp+0E0h+FileInformationClass], 16h; FileInformationClass
0x14002fc06  mov     rcx, r12; Instance
0x14002fc09  call    cs:__imp_FltQueryInformationFile
0x14002fc10  nop     dword ptr [rax+rax+00h]
0x14002fc15  mov     ebx, eax
0x14002fc17  cmp     eax, 80000005h
0x14002fc1c  jz      short loc_14002FB9E
0x14002fc1e  cmp     eax, 0C0000023h
0x14002fc23  jz      loc_14002FB9E
0x14002fc29  test    eax, eax
0x14002fc2b  jns     short loc_14002FC6D
0x14002fc2d  cmp     eax, 0C000000Dh
0x14002fc32  jz      short loc_14002FC66
0x14002fc34  cmp     eax, 0C0000002h
0x14002fc39  jz      short loc_14002FC66
0x14002fc3b  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fc42  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fc49  jz      loc_14002FDEF
0x14002fc4f  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14002fc53  mov     r9d, 75h ; 'u'
0x14002fc59  mov     dword ptr [rsp+0E0h+var_B0], 0F88h
0x14002fc61  jmp     loc_14002FDBF
0x14002fc66  xor     ebx, ebx
0x14002fc68  jmp     loc_14002FDEF
0x14002fc6d  cmp     [rbp+3Fh+var_90], 0
0x14002fc71  jz      loc_14002FDEF
0x14002fc77  cmp     dword ptr [rsi+4], 0
0x14002fc7b  jz      loc_14002FDEF
0x14002fc81  mov     rdi, rsi
0x14002fc84  lea     rax, [rdi+18h]
0x14002fc88  mov     r8b, 1; CaseInSensitive
0x14002fc8b  mov     [rbp+3Fh+String1.Buffer], rax
0x14002fc8f  lea     rdx, [rbp+3Fh+String2]; String2
0x14002fc93  movzx   eax, word ptr [rdi+4]
0x14002fc97  lea     rcx, [rbp+3Fh+String1]; String1
0x14002fc9b  mov     [rbp+3Fh+String1.Length], ax
0x14002fc9f  movzx   eax, word ptr [rdi+4]
0x14002fca3  mov     [rbp+3Fh+String1.MaximumLength], ax
0x14002fca7  call    cs:__imp_RtlCompareUnicodeString
0x14002fcae  nop     dword ptr [rax+rax+00h]
0x14002fcb3  test    eax, eax
0x14002fcb5  jnz     loc_14002FD47
0x14002fcbb  test    [rbp+3Fh+arg_30], 2
0x14002fcbf  jz      loc_14002FD8F
0x14002fcc5  mov     rax, [rdi+8]
0x14002fcc9  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x14002fccd  mov     rcx, [rbp+3Fh+Instance]; Instance
0x14002fcd1  mov     r9d, 8; Length
0x14002fcd7  mov     rdx, r13; FileObject
0x14002fcda  mov     [rbp+3Fh+FileInformation], rax
0x14002fcde  mov     [rsp+0E0h+FileInformationClass], 14h; FileInformationClass
0x14002fce6  call    cs:__imp_FltSetInformationFile
0x14002fced  nop     dword ptr [rax+rax+00h]
0x14002fcf2  mov     ebx, eax
0x14002fcf4  test    eax, eax
0x14002fcf6  js      loc_14002FDEF
0x14002fcfc  mov     r9, [rbp+3Fh+Instance]
0x14002fd00  mov     rdx, r15
0x14002fd03  mov     r8, [rdi+8]
0x14002fd07  mov     rcx, r12
0x14002fd0a  mov     byte ptr [rsp+0E0h+LengthReturned], 0
0x14002fd0f  mov     qword ptr [rsp+0E0h+FileInformationClass], r13
0x14002fd14  call    WcCopyStreamData
0x14002fd19  mov     ebx, eax
0x14002fd1b  test    eax, eax
0x14002fd1d  jns     short loc_14002FD8F
0x14002fd1f  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fd26  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fd2d  jz      loc_14002FDEF
0x14002fd33  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14002fd37  mov     r9d, 76h ; 'v'
0x14002fd3d  mov     dword ptr [rsp+0E0h+var_B0], 0FDBh
0x14002fd45  jmp     short loc_14002FDBF
0x14002fd47  test    [rbp+3Fh+arg_30], 1
0x14002fd4b  jz      short loc_14002FD8F
0x14002fd4d  mov     rax, [rdi+8]
0x14002fd51  lea     rcx, [rbp+3Fh+String1]
0x14002fd55  mov     rdx, [rbp+3Fh+var_50]
0x14002fd59  mov     r9, r12
0x14002fd5c  mov     [rsp+0E0h+var_A0], rax
0x14002fd61  mov     r8, r15
0x14002fd64  mov     rax, [rbp+3Fh+Instance]
0x14002fd68  mov     [rsp+0E0h+var_A8], rax
0x14002fd6d  mov     rax, [rbp+3Fh+var_58]
0x14002fd71  mov     [rsp+0E0h+var_B0], r13
0x14002fd76  mov     [rsp+0E0h+LengthReturned], rax
0x14002fd7b  lea     rax, [rbp+3Fh+String1]
0x14002fd7f  mov     qword ptr [rsp+0E0h+FileInformationClass], rax
0x14002fd84  call    WcCopyDataStreamByName
0x14002fd89  mov     ebx, eax
0x14002fd8b  test    eax, eax
0x14002fd8d  js      short loc_14002FD9D
0x14002fd8f  mov     eax, [rdi]
0x14002fd91  test    eax, eax
0x14002fd93  jz      short loc_14002FDEF
0x14002fd95  add     rdi, rax
0x14002fd98  jmp     loc_14002FC84
0x14002fd9d  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fda4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fdab  jz      short loc_14002FDEF
0x14002fdad  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x14002fdb1  mov     r9d, 77h ; 'w'
0x14002fdb7  mov     dword ptr [rsp+0E0h+var_B0], 0FF0h
0x14002fdbf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fdc6  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002fdcd  mov     [rsp+0E0h+LengthReturned], rax
0x14002fdd2  mov     r8d, 0Fh
0x14002fdd8  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002fddf  mov     dl, 2
0x14002fde1  mov     qword ptr [rsp+0E0h+FileInformationClass], rax
0x14002fde6  mov     rcx, [rcx+40h]
0x14002fdea  call    WPP_RECORDER_SF_sDd
0x14002fdef  mov     edx, 69664357h; Tag
0x14002fdf4  mov     rcx, rsi; P
0x14002fdf7  call    cs:__imp_ExFreePoolWithTag
0x14002fdfe  nop     dword ptr [rax+rax+00h]
0x14002fe03  jmp     short loc_14002FE5A
0x14002fe05  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fe0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fe13  jz      short loc_14002FE55
0x14002fe15  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe1c  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002fe23  mov     dword ptr [rsp+0E0h+var_A8], edi
0x14002fe27  mov     r9d, 74h ; 't'
0x14002fe2d  mov     dword ptr [rsp+0E0h+var_B0], 0F6Bh
0x14002fe35  mov     dl, 2
0x14002fe37  mov     [rsp+0E0h+LengthReturned], rax
0x14002fe3c  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002fe43  mov     rcx, [rcx+40h]
0x14002fe47  lea     r8d, [r9-65h]
0x14002fe4b  mov     qword ptr [rsp+0E0h+FileInformationClass], rax
0x14002fe50  call    WPP_RECORDER_SF_sDd
0x14002fe55  mov     ebx, 0C0000017h
0x14002fe5a  mov     eax, ebx
0x14002fe5c  mov     rcx, [rbp+3Fh+var_38]
0x14002fe60  xor     rcx, rsp; StackCookie
0x14002fe63  call    __security_check_cookie
0x14002fe68  add     rsp, 0B0h
0x14002fe6f  pop     r15
0x14002fe71  pop     r13
0x14002fe73  pop     r12
0x14002fe75  pop     rdi
0x14002fe76  pop     rsi
0x14002fe77  pop     rbx
0x14002fe78  pop     rbp
0x14002fe79  retn
```
