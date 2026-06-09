# AddOrUpdateTrackedPath(_UNICODE_STRING const *,_TRACKING_MODE,uchar,uchar)

- ea: `0x140005910`
- end: `0x140005ddc`
- name: `?AddOrUpdateTrackedPath@@YAJPEBU_UNICODE_STRING@@W4_TRACKING_MODE@@EE@Z`
- size: `1228`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, installer_update`

## callers

- `0x140001a94`
- `0x14001e23c`

## callees

- `0x140002644`
- `0x140003944`
- `0x140005910`
- `0x14000dd24`
- `0x14000e1d0`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400059e5`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400059e5`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x140005c2b`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x140005c2b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005c76`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005d25`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005c76`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005d25`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400059ad`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400059ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005aa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005abf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ad5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005db5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005aa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005abf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ad5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005db5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005b2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005b90`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005b2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005b90`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400059cc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005a19`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005afe`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400059cc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005a19`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005afe`
- `FLTMGR!FltAttachVolume` at `0x140005cd8`
- `FLTMGR!FltAttachVolume` at `0x140005cd8`
- `FLTMGR!FltGetVolumeFromName` at `0x140005cac`
- `FLTMGR!FltGetVolumeFromName` at `0x140005cac`
- `FLTMGR!FltObjectDereference` at `0x140005d0d`
- `FLTMGR!FltObjectDereference` at `0x140005d0d`

## string_xrefs

- `0x140005960`: `Failed to convert path [%wZ] to NT (0x%08X)`
- `0x140005bf1`: `Failed to allocate memory for the path prefix entry`
- `0x140005c3b`: `Failed to insert path prefix entry`

## pseudocode

```c
__int64 __fastcall AddOrUpdateTrackedPath(const UNICODE_STRING *a1, int a2, char a3, char a4)
{
  _QWORD *v5; // r14
  int NtPath; // eax
  unsigned int v8; // edi
  _QWORD *v9; // rbx
  char v10; // r15
  char *v11; // r13
  BOOLEAN i; // dl
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  PUNICODE_PREFIX_TABLE_ENTRY v14; // rsi
  char *m; // rbx
  char *j; // rbx
  struct _RTL_SPLAY_LINKS *k; // rbx
  struct _RTL_SPLAY_LINKS *RightChild; // rcx
  struct _RTL_SPLAY_LINKS *Parent; // rcx
  struct _RTL_SPLAY_LINKS *LeftChild; // rcx
  struct _RTL_SPLAY_LINKS *v21; // rcx
  _QWORD *PoolWithTag; // rax
  _QWORD *v23; // rsi
  char *v24; // rax
  int v25; // eax
  NTSTATUS VolumeFromName; // eax
  NTSTATUS v27; // eax
  void *v28; // rcx
  void *v29; // rcx
  PFLT_VOLUME RetVolume; // [rsp+20h] [rbp-30h] BYREF
  UNICODE_STRING VolumeName; // [rsp+28h] [rbp-28h] BYREF
  UNICODE_STRING String2; // [rsp+38h] [rbp-18h] BYREF

  v5 = 0;
  String2 = 0;
  RetVolume = 0;
  VolumeName = 0;
  NtPath = GetNtPath(a1, &String2, &VolumeName);
  v8 = NtPath;
  if ( NtPath < 0 )
  {
    v9 = 0;
    v10 = 0;
    WriteLogMessage(3, L"Failed to convert path [%wZ] to NT (0x%08X)", a1, (unsigned int)NtPath);
    goto LABEL_60;
  }
  v11 = 0;
  if ( String2.Length >= 2u && String2.Buffer[((unsigned __int64)String2.Length >> 1) - 1] == 92 )
    String2.Length -= 2;
  ExAcquireFastMutex(&stru_140019468);
  v10 = 1;
  for ( i = 1; ; i = 0 )
  {
    UnicodePrefix = RtlNextUnicodePrefix(&g_TrackingInfo, i);
    v14 = UnicodePrefix;
    if ( !UnicodePrefix )
      break;
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)&UnicodePrefix[1], &String2, 1u) )
    {
      for ( j = (char *)qword_140019448; j; j = *(char **)j )
      {
        if ( RtlEqualUnicodeString((PCUNICODE_STRING)(j + 8), &VolumeName, 1u) )
        {
          v11 = j;
          break;
        }
      }
      LODWORD(v14[1].CaseMatch) = a2;
      if ( a3 )
      {
        for ( k = v14[1].Links.Parent; k; k = v14[1].Links.Parent )
        {
          v14[1].Links.Parent = k->Parent;
          RightChild = k[2].RightChild;
          if ( RightChild )
          {
            ExFreePoolWithTag(RightChild, 0x6E6D7377u);
            k[2].RightChild = 0;
          }
          Parent = k[2].Parent;
          if ( Parent )
          {
            ExFreePoolWithTag(Parent, 0x6E6D7377u);
            k[2].Parent = 0;
          }
          LeftChild = k[1].LeftChild;
          if ( LeftChild )
          {
            ExFreePoolWithTag(LeftChild, 0x6E6D7377u);
            k[1].LeftChild = 0;
          }
          v21 = k->RightChild;
          if ( v21 )
          {
            ExFreePoolWithTag(v21, 0x6E6D7377u);
            k->RightChild = 0;
          }
          ExFreePoolWithTag(k, 0x6E6D7377u);
        }
      }
LABEL_52:
      ExReleaseFastMutex(&stru_140019468);
      v10 = 0;
      if ( a4 && !v11 && !IsLogPathUnderPath(&VolumeName) )
      {
        VolumeFromName = FltGetVolumeFromName((PFLT_FILTER)FilterHandle, &VolumeName, &RetVolume);
        v8 = VolumeFromName;
        if ( VolumeFromName >= 0 )
        {
          v27 = FltAttachVolume((PFLT_FILTER)FilterHandle, RetVolume, 0, 0);
          v8 = v27;
          if ( v27 < 0 )
            WriteLogMessage(3, L"Failed to attach to volume [%wZ] (0x%08X)", &VolumeName, (unsigned int)v27, RetVolume);
        }
        else
        {
          WriteLogMessage(
            3,
            L"Failed to get volume object for [%wZ] (0x%08X)",
            &VolumeName,
            (unsigned int)VolumeFromName,
            RetVolume);
        }
      }
      v9 = 0;
      goto LABEL_60;
    }
  }
  for ( m = (char *)qword_140019448; m; m = *(char **)m )
  {
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)(m + 8), &VolumeName, 1u) )
    {
      v11 = m;
      break;
    }
  }
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, 0x58u, 0x6E6D7377u);
  v23 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported || !PoolWithTag )
  {
    v9 = PoolWithTag;
    if ( !PoolWithTag )
    {
      WriteLogMessage(3, L"Failed to allocate memory for the path prefix entry");
      goto LABEL_45;
    }
  }
  else
  {
    memset(PoolWithTag, 0, 0x58u);
    v9 = v23;
  }
  *(UNICODE_STRING *)(v23 + 7) = String2;
  String2 = 0;
  *((_DWORD *)v23 + 18) = a2;
  if ( !v11 )
  {
    v24 = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x18u, 0x6E6D7377u);
    if ( !ExPoolZeroingNativelySupported && v24 )
    {
      *(_OWORD *)v24 = 0;
      *((_QWORD *)v24 + 2) = 0;
      v5 = v24;
      goto LABEL_41;
    }
    v5 = v24;
    if ( v24 )
    {
LABEL_41:
      v25 = Duplicate(&VolumeName, (PUNICODE_STRING)(v24 + 8));
      v8 = v25;
      if ( v25 < 0 )
      {
        WriteLogMessage(3, L"Failed to duplicate volume device name (0x%08X)", (unsigned int)v25);
        goto LABEL_60;
      }
      goto LABEL_48;
    }
    WriteLogMessage(3, L"Failed to allocate memory for the volume list entry");
LABEL_45:
    v8 = -1073741670;
    goto LABEL_60;
  }
LABEL_48:
  if ( RtlInsertUnicodePrefix(&g_TrackingInfo, (PUNICODE_STRING)(v23 + 7), (PUNICODE_PREFIX_TABLE_ENTRY)v23) )
  {
    if ( v5 )
    {
      *v5 = qword_140019448;
      qword_140019448 = v5;
      v5 = 0;
    }
    goto LABEL_52;
  }
  WriteLogMessage(3, L"Failed to insert path prefix entry");
  v8 = -1073741616;
LABEL_60:
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  if ( v10 )
    ExReleaseFastMutex(&stru_140019468);
  if ( v5 )
  {
    v28 = (void *)v5[2];
    if ( v28 )
    {
      ExFreePoolWithTag(v28, 0x6E6D7377u);
      v5[2] = 0;
    }
    ExFreePoolWithTag(v5, 0x6E6D7377u);
  }
  if ( v9 )
  {
    v29 = (void *)v9[8];
    if ( v29 )
    {
      ExFreePoolWithTag(v29, 0x6E6D7377u);
      v9[8] = 0;
    }
    ExFreePoolWithTag(v9, 0x6E6D7377u);
  }
  if ( String2.Buffer )
    ExFreePoolWithTag(String2.Buffer, 0x6E6D7377u);
  return v8;
}

```

## disassembly

```asm
0x140005910  mov     [rsp-38h+arg_0], rbx
0x140005915  mov     [rsp-38h+arg_18], r9b
0x14000591a  mov     [rsp-38h+arg_8], edx
0x14000591e  push    rbp
0x14000591f  push    rsi
0x140005920  push    rdi
0x140005921  push    r12
0x140005923  push    r13
0x140005925  push    r14
0x140005927  push    r15
0x140005929  mov     rbp, rsp
0x14000592c  sub     rsp, 50h
0x140005930  mov     r12b, r8b
0x140005933  lea     rdx, [rbp+String2]; DestinationString
0x140005937  xorps   xmm0, xmm0
0x14000593a  lea     r8, [rbp+VolumeName]; struct _UNICODE_STRING *
0x14000593e  xorps   xmm1, xmm1
0x140005941  xor     r14d, r14d
0x140005944  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140005948  mov     [rbp+RetVolume], r14
0x14000594c  mov     rsi, rcx
0x14000594f  movups  xmmword ptr [rbp+VolumeName.Length], xmm1
0x140005953  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140005958  mov     edi, eax
0x14000595a  test    eax, eax
0x14000595c  jns     short loc_14000597D
0x14000595e  xor     ebx, ebx
0x140005960  lea     rdx, aFailedToConver; "Failed to convert path [%wZ] to NT (0x%"...
0x140005967  xor     r15b, r15b
0x14000596a  mov     r9d, eax
0x14000596d  mov     r8, rsi
0x140005970  lea     ecx, [rbx+3]
0x140005973  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005978  jmp     loc_140005D04
0x14000597d  movzx   edx, [rbp+String2.Length]
0x140005981  xor     r13d, r13d
0x140005984  cmp     edx, 2
0x140005987  jb      short loc_1400059A6
0x140005989  mov     rax, [rbp+String2.Buffer]
0x14000598d  mov     ecx, edx
0x14000598f  shr     rcx, 1
0x140005992  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140005998  jnz     short loc_1400059A6
0x14000599a  mov     eax, 0FFFEh
0x14000599f  add     dx, ax
0x1400059a2  mov     [rbp+String2.Length], dx
0x1400059a6  lea     rcx, stru_140019468; FastMutex
0x1400059ad  call    cs:__imp_ExAcquireFastMutex
0x1400059b4  nop     dword ptr [rax+rax+00h]
0x1400059b9  mov     r15b, 1
0x1400059bc  mov     dl, r15b
0x1400059bf  jmp     short loc_1400059DE
0x1400059c1  lea     rcx, [rsi+38h]; String1
0x1400059c5  mov     r8b, r15b; CaseInSensitive
0x1400059c8  lea     rdx, [rbp+String2]; String2
0x1400059cc  call    cs:__imp_RtlEqualUnicodeString
0x1400059d3  nop     dword ptr [rax+rax+00h]
0x1400059d8  test    al, al
0x1400059da  jnz     short loc_140005A05
0x1400059dc  xor     edx, edx; Restart
0x1400059de  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x1400059e5  call    cs:__imp_RtlNextUnicodePrefix
0x1400059ec  nop     dword ptr [rax+rax+00h]
0x1400059f1  mov     rsi, rax
0x1400059f4  test    rax, rax
0x1400059f7  jnz     short loc_1400059C1
0x1400059f9  mov     rbx, cs:qword_140019448
0x140005a00  jmp     loc_140005B11
0x140005a05  mov     rbx, cs:qword_140019448
0x140005a0c  jmp     short loc_140005A2C
0x140005a0e  lea     rcx, [rbx+8]; String1
0x140005a12  mov     r8b, r15b; CaseInSensitive
0x140005a15  lea     rdx, [rbp+VolumeName]; String2
0x140005a19  call    cs:__imp_RtlEqualUnicodeString
0x140005a20  nop     dword ptr [rax+rax+00h]
0x140005a25  test    al, al
0x140005a27  jnz     short loc_140005A33
0x140005a29  mov     rbx, [rbx]
0x140005a2c  test    rbx, rbx
0x140005a2f  jnz     short loc_140005A0E
0x140005a31  jmp     short loc_140005A36
0x140005a33  mov     r13, rbx
0x140005a36  mov     eax, [rbp+arg_8]
0x140005a39  mov     [rsi+48h], eax
0x140005a3c  test    r12b, r12b
0x140005a3f  jz      loc_140005C6F
0x140005a45  mov     rbx, [rsi+50h]
0x140005a49  test    rbx, rbx
0x140005a4c  jz      loc_140005C6F
0x140005a52  mov     r15d, 6E6D7377h
0x140005a58  mov     rax, [rbx]
0x140005a5b  mov     [rsi+50h], rax
0x140005a5f  mov     rcx, [rbx+40h]; P
0x140005a63  test    rcx, rcx
0x140005a66  jz      short loc_140005A7B
0x140005a68  mov     edx, r15d; Tag
0x140005a6b  call    cs:__imp_ExFreePoolWithTag
0x140005a72  nop     dword ptr [rax+rax+00h]
0x140005a77  mov     [rbx+40h], r14
0x140005a7b  mov     rcx, [rbx+30h]; P
0x140005a7f  test    rcx, rcx
0x140005a82  jz      short loc_140005A97
0x140005a84  mov     edx, r15d; Tag
0x140005a87  call    cs:__imp_ExFreePoolWithTag
0x140005a8e  nop     dword ptr [rax+rax+00h]
0x140005a93  mov     [rbx+30h], r14
0x140005a97  mov     rcx, [rbx+20h]; P
0x140005a9b  test    rcx, rcx
0x140005a9e  jz      short loc_140005AB3
0x140005aa0  mov     edx, r15d; Tag
0x140005aa3  call    cs:__imp_ExFreePoolWithTag
0x140005aaa  nop     dword ptr [rax+rax+00h]
0x140005aaf  mov     [rbx+20h], r14
0x140005ab3  mov     rcx, [rbx+10h]; P
0x140005ab7  test    rcx, rcx
0x140005aba  jz      short loc_140005ACF
0x140005abc  mov     edx, r15d; Tag
0x140005abf  call    cs:__imp_ExFreePoolWithTag
0x140005ac6  nop     dword ptr [rax+rax+00h]
0x140005acb  mov     [rbx+10h], r14
0x140005acf  mov     edx, r15d; Tag
0x140005ad2  mov     rcx, rbx; P
0x140005ad5  call    cs:__imp_ExFreePoolWithTag
0x140005adc  nop     dword ptr [rax+rax+00h]
0x140005ae1  mov     rbx, [rsi+50h]
0x140005ae5  test    rbx, rbx
0x140005ae8  jnz     loc_140005A58
0x140005aee  jmp     loc_140005C6F
0x140005af3  lea     rcx, [rbx+8]; String1
0x140005af7  mov     r8b, r15b; CaseInSensitive
0x140005afa  lea     rdx, [rbp+VolumeName]; String2
0x140005afe  call    cs:__imp_RtlEqualUnicodeString
0x140005b05  nop     dword ptr [rax+rax+00h]
0x140005b0a  test    al, al
0x140005b0c  jnz     short loc_140005B18
0x140005b0e  mov     rbx, [rbx]
0x140005b11  test    rbx, rbx
0x140005b14  jnz     short loc_140005AF3
0x140005b16  jmp     short loc_140005B1B
0x140005b18  mov     r13, rbx
0x140005b1b  mov     ebx, 58h ; 'X'
0x140005b20  mov     r8d, 6E6D7377h; Tag
0x140005b26  mov     edx, ebx; NumberOfBytes
0x140005b28  mov     ecx, 401h; PoolType
0x140005b2d  call    cs:__imp_ExAllocatePoolWithTag
0x140005b34  nop     dword ptr [rax+rax+00h]
0x140005b39  cmp     cs:ExPoolZeroingNativelySupported, r14b
0x140005b40  mov     rsi, rax
0x140005b43  jnz     loc_140005BE5
0x140005b49  test    rax, rax
0x140005b4c  jz      loc_140005BE5
0x140005b52  mov     r8d, ebx; Size
0x140005b55  xor     edx, edx; Val
0x140005b57  mov     rcx, rax; void *
0x140005b5a  call    memset
0x140005b5f  mov     rbx, rsi
0x140005b62  mov     eax, [rbp+arg_8]
0x140005b65  xorps   xmm1, xmm1
0x140005b68  movups  xmm0, xmmword ptr [rbp+String2.Length]
0x140005b6c  movdqu  xmmword ptr [rsi+38h], xmm0
0x140005b71  movups  xmmword ptr [rbp+String2.Length], xmm1
0x140005b75  mov     [rsi+48h], eax
0x140005b78  test    r13, r13
0x140005b7b  jnz     loc_140005C1D
0x140005b81  lea     edx, [r13+18h]; NumberOfBytes
0x140005b85  mov     ecx, 401h; PoolType
0x140005b8a  mov     r8d, 6E6D7377h; Tag
0x140005b90  call    cs:__imp_ExAllocatePoolWithTag
0x140005b97  nop     dword ptr [rax+rax+00h]
0x140005b9c  cmp     cs:ExPoolZeroingNativelySupported, r14b
0x140005ba3  jnz     short loc_140005C0C
0x140005ba5  test    rax, rax
0x140005ba8  jz      short loc_140005C0C
0x140005baa  xorps   xmm0, xmm0
0x140005bad  xor     ecx, ecx
0x140005baf  movups  xmmword ptr [rax], xmm0
0x140005bb2  mov     [rax+10h], rcx
0x140005bb6  mov     r14, rax
0x140005bb9  lea     rdx, [rax+8]; DestinationString
0x140005bbd  lea     rcx, [rbp+VolumeName]; SourceString
0x140005bc1  call    ?Duplicate@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)
0x140005bc6  mov     edi, eax
0x140005bc8  test    eax, eax
0x140005bca  jns     short loc_140005C1D
0x140005bcc  mov     r8d, eax
0x140005bcf  lea     rdx, aFailedToDuplic_0; "Failed to duplicate volume device name "...
0x140005bd6  mov     ecx, 3
0x140005bdb  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005be0  jmp     loc_140005D04
0x140005be5  mov     rbx, rsi
0x140005be8  test    rsi, rsi
0x140005beb  jnz     loc_140005B62
0x140005bf1  lea     rdx, aFailedToAlloca_9; "Failed to allocate memory for the path "...
0x140005bf8  mov     ecx, 3
0x140005bfd  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005c02  mov     edi, 0C000009Ah
0x140005c07  jmp     loc_140005D04
0x140005c0c  mov     r14, rax
0x140005c0f  test    rax, rax
0x140005c12  jnz     short loc_140005BB9
0x140005c14  lea     rdx, aFailedToAlloca_6; "Failed to allocate memory for the volum"...
0x140005c1b  jmp     short loc_140005BF8
0x140005c1d  mov     r8, rsi; PrefixTableEntry
0x140005c20  lea     rdx, [rsi+38h]; Prefix
0x140005c24  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x140005c2b  call    cs:__imp_RtlInsertUnicodePrefix
0x140005c32  nop     dword ptr [rax+rax+00h]
0x140005c37  test    al, al
0x140005c39  jnz     short loc_140005C56
0x140005c3b  lea     rdx, aFailedToInsert_1; "Failed to insert path prefix entry"
0x140005c42  mov     ecx, 3
0x140005c47  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005c4c  mov     edi, 0C00000D0h
0x140005c51  jmp     loc_140005D04
0x140005c56  test    r14, r14
0x140005c59  jz      short loc_140005C6F
0x140005c5b  mov     rax, cs:qword_140019448
0x140005c62  mov     [r14], rax
0x140005c65  mov     cs:qword_140019448, r14
0x140005c6c  xor     r14d, r14d
0x140005c6f  lea     rcx, stru_140019468; FastMutex
0x140005c76  call    cs:__imp_ExReleaseFastMutex
0x140005c7d  nop     dword ptr [rax+rax+00h]
0x140005c82  xor     r15b, r15b
0x140005c85  cmp     [rbp+arg_18], r15b
0x140005c89  jz      short loc_140005D02
0x140005c8b  test    r13, r13
0x140005c8e  jnz     short loc_140005D02
0x140005c90  lea     rcx, [rbp+VolumeName]; struct _UNICODE_STRING *
0x140005c94  call    ?IsLogPathUnderPath@@YAEPEBU_UNICODE_STRING@@@Z; IsLogPathUnderPath(_UNICODE_STRING const *)
0x140005c99  test    al, al
0x140005c9b  jnz     short loc_140005D02
0x140005c9d  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x140005ca4  lea     r8, [rbp+RetVolume]; RetVolume
0x140005ca8  lea     rdx, [rbp+VolumeName]; VolumeName
0x140005cac  call    cs:__imp_FltGetVolumeFromName
0x140005cb3  nop     dword ptr [rax+rax+00h]
0x140005cb8  mov     edi, eax
0x140005cba  test    eax, eax
0x140005cbc  jns     short loc_140005CC7
0x140005cbe  lea     rdx, aFailedToGetVol_0; "Failed to get volume object for [%wZ] ("...
0x140005cc5  jmp     short loc_140005CF1
0x140005cc7  mov     rdx, [rbp+RetVolume]; Volume
0x140005ccb  xor     r9d, r9d; RetInstance
0x140005cce  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x140005cd5  xor     r8d, r8d; InstanceName
0x140005cd8  call    cs:__imp_FltAttachVolume
0x140005cdf  nop     dword ptr [rax+rax+00h]
0x140005ce4  mov     edi, eax
0x140005ce6  test    eax, eax
0x140005ce8  jns     short loc_140005D02
0x140005cea  lea     rdx, aFailedToAttach; "Failed to attach to volume [%wZ] (0x%08"...
0x140005cf1  mov     r9d, eax
0x140005cf4  lea     r8, [rbp+VolumeName]
0x140005cf8  mov     ecx, 3
0x140005cfd  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005d02  xor     ebx, ebx
0x140005d04  mov     rcx, [rbp+RetVolume]; FltObject
0x140005d08  test    rcx, rcx
0x140005d0b  jz      short loc_140005D19
0x140005d0d  call    cs:__imp_FltObjectDereference
0x140005d14  nop     dword ptr [rax+rax+00h]
0x140005d19  test    r15b, r15b
0x140005d1c  jz      short loc_140005D31
0x140005d1e  lea     rcx, stru_140019468; FastMutex
0x140005d25  call    cs:__imp_ExReleaseFastMutex
0x140005d2c  nop     dword ptr [rax+rax+00h]
0x140005d31  test    r14, r14
0x140005d34  jz      short loc_140005D6C
0x140005d36  mov     rcx, [r14+10h]; P
0x140005d3a  test    rcx, rcx
0x140005d3d  jz      short loc_140005D58
0x140005d3f  mov     edx, 6E6D7377h; Tag
0x140005d44  call    cs:__imp_ExFreePoolWithTag
0x140005d4b  nop     dword ptr [rax+rax+00h]
0x140005d50  mov     qword ptr [r14+10h], 0
0x140005d58  mov     edx, 6E6D7377h; Tag
0x140005d5d  mov     rcx, r14; P
0x140005d60  call    cs:__imp_ExFreePoolWithTag
0x140005d67  nop     dword ptr [rax+rax+00h]
0x140005d6c  test    rbx, rbx
0x140005d6f  jz      short loc_140005DA7
0x140005d71  mov     rcx, [rbx+40h]; P
0x140005d75  test    rcx, rcx
0x140005d78  jz      short loc_140005D93
0x140005d7a  mov     edx, 6E6D7377h; Tag
0x140005d7f  call    cs:__imp_ExFreePoolWithTag
0x140005d86  nop     dword ptr [rax+rax+00h]
0x140005d8b  mov     qword ptr [rbx+40h], 0
0x140005d93  mov     edx, 6E6D7377h; Tag
0x140005d98  mov     rcx, rbx; P
0x140005d9b  call    cs:__imp_ExFreePoolWithTag
0x140005da2  nop     dword ptr [rax+rax+00h]
0x140005da7  mov     rcx, [rbp+String2.Buffer]; P
0x140005dab  test    rcx, rcx
0x140005dae  jz      short loc_140005DC1
0x140005db0  mov     edx, 6E6D7377h; Tag
0x140005db5  call    cs:__imp_ExFreePoolWithTag
0x140005dbc  nop     dword ptr [rax+rax+00h]
0x140005dc1  mov     rbx, [rsp+50h+arg_0]
  ... truncated ...
```
