# CProbedAssemblyInformation::ProbeManifestExistence(int,bool &,bool &,_WIN32_FILE_ATTRIBUTE_DATA &)

- ea: `0x18000bc20`
- end: `0x18000bff7`
- name: `?ProbeManifestExistence@CProbedAssemblyInformation@@QEBAHHAEA_N0AEAU_WIN32_FILE_ATTRIBUTE_DATA@@@Z`
- size: `983`
- prototype: `__int64 __fastcall(CProbedAssemblyInformation *__hidden this, int, bool *, bool *, struct _WIN32_FILE_ATTRIBUTE_DATA *lpFileInformation)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000c070`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000bc20`
- `0x18000dffc`
- `0x18001c2c8`
- `0x18001e5d0`
- `0x180020820`
- `0x18004d2d0`
- `0x18005533c`
- `0x1800587a0`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18000bd94`
- `ntdll!RtlPopFrame` at `0x18000bd94`
- `ntdll!RtlPushFrame` at `0x18000bca5`
- `ntdll!RtlPushFrame` at `0x18000bca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bee7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bee7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf69`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000bd01`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000bd01`

## pseudocode

```c
__int64 __fastcall CProbedAssemblyInformation::ProbeManifestExistence(
        CProbedAssemblyInformation *this,
        int a2,
        bool *a3,
        bool *a4,
        struct _WIN32_FILE_ATTRIBUTE_DATA *lpFileInformation)
{
  bool v6; // bl
  const char *v9; // rcx
  bool v10; // di
  _WORD *v11; // rax
  unsigned int v12; // ebx
  DWORD LastError; // eax
  unsigned int i; // ecx
  DWORD v16; // eax
  bool v17[4]; // [rsp+38h] [rbp-D0h] BYREF
  int v18; // [rsp+3Ch] [rbp-CCh]
  int v19; // [rsp+40h] [rbp-C8h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A8h]
  __int64 v22; // [rsp+68h] [rbp-A0h]
  unsigned int *v23; // [rsp+70h] [rbp-98h]
  _QWORD v24[2]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 *v25; // [rsp+88h] [rbp-80h]
  unsigned __int64 v26; // [rsp+98h] [rbp-70h]
  char v27; // [rsp+A0h] [rbp-68h] BYREF

  v6 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006C620;
  v23 = (unsigned int *)&v19;
  v18 = a2;
  v19 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v21 = 544438355;
  LODWORD(v22) = 234;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v10 = 0;
  *a3 = 0;
  *a4 = 0;
  v17[0] = 0;
  if ( !*(_QWORD *)this )
  {
    SetLastError(0x54Fu);
    *v23 = 0;
    goto LABEL_9;
  }
  v11 = (_WORD *)*((_QWORD *)this + 4);
  if ( *v11 == 92 && v11[1] == 63 && v11[2] == 63 && v11[3] == 92 )
  {
    LODWORD(v22) = 246;
    FusionpTraceParameterCheck(v9);
    SetLastError(0x57u);
    *v23 = 0;
    goto LABEL_9;
  }
  SetLastError(0);
  if ( !GetFileAttributesExW(*((LPCWSTR *)this + 4), GetFileExInfoStandard, lpFileInformation) )
  {
    LastError = GetLastError();
    for ( i = 0; i < 2; ++i )
    {
      if ( LastError == *((_DWORD *)&qword_18007E410 + i) )
        goto LABEL_8;
    }
    if ( i == 2 )
    {
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006C880);
      goto LABEL_9;
    }
  }
  v6 = 1;
  if ( !v18 || *((_QWORD *)this + 73) )
  {
LABEL_8:
    *a3 = v6;
    *a4 = v10;
    SetLastError(0);
    *v23 = 1;
    goto LABEL_9;
  }
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v24);
  SetLastError(0);
  if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetPathExtension((char *)this + 16, v24) )
  {
    if ( !FusionpEqualStrings(v25, v26, (WCHAR *)L"DLL", 3, 1u)
      && !FusionpEqualStrings(v25, v26, (WCHAR *)L"MUI", 3, 1u) )
    {
      if ( lpFileInformation->nFileSizeHigh || lpFileInformation->nFileSizeLow > 0x800000 )
      {
        SetLastError(0x3719u);
        *v23 = 0;
        FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078828);
        CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v24);
        goto LABEL_9;
      }
      goto LABEL_21;
    }
    SetLastError(0);
    if ( (unsigned int)IsBinaryFileContainManifestInResource(*((const unsigned __int16 **)this + 4), v17) )
    {
      v10 = v17[0];
      v6 = v17[0];
LABEL_21:
      v24[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
      if ( v25 != (unsigned __int16 *)&v27 )
        CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v24);
      goto LABEL_8;
    }
    *v23 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078848);
    CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v24);
  }
  else
  {
    *v23 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078868);
    CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v24);
  }
LABEL_9:
  v12 = *v23;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v12 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v16 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v16, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v12;
}

```

## disassembly

```asm
0x18000bc20  mov     r11, rsp
0x18000bc23  push    rbp
0x18000bc24  push    rbx
0x18000bc25  lea     rbp, [r11-68h]
0x18000bc29  sub     rsp, 158h
0x18000bc30  mov     rax, cs:__security_cookie
0x18000bc37  xor     rax, rsp
0x18000bc3a  mov     [rbp+60h+var_40], rax
0x18000bc3e  mov     [r11+10h], rsi
0x18000bc42  lea     rax, qword_18006C620
0x18000bc49  mov     [r11-18h], rdi
0x18000bc4d  mov     rsi, rcx
0x18000bc50  mov     [r11-20h], r12
0x18000bc54  lea     rcx, [rsp+160h+Frame]; Frame
0x18000bc59  mov     r12, [rbp+60h+lpFileInformation]
0x18000bc60  xor     ebx, ebx
0x18000bc62  mov     [r11-30h], r14
0x18000bc66  mov     r14, r8
0x18000bc69  mov     [rsp+160h+Frame.Context], rax
0x18000bc6e  lea     rax, [rsp+160h+var_128]
0x18000bc73  mov     [r11-38h], r15
0x18000bc77  mov     r15, r9
0x18000bc7a  mov     [rsp+160h+var_F8], rax
0x18000bc7f  mov     [rsp+160h+var_12C], edx
0x18000bc83  mov     [rsp+160h+var_128], ebx
0x18000bc87  mov     [rsp+160h+Frame.Flags], 1
0x18000bc8f  mov     [rsp+160h+Frame.Previous], rbx
0x18000bc94  mov     [rsp+160h+var_108], 20737853h
0x18000bc9d  mov     dword ptr [rsp+160h+var_100], 0EAh
0x18000bca5  call    cs:__imp_RtlPushFrame
0x18000bcac  nop     dword ptr [rax+rax+00h]
0x18000bcb1  cmp     cs:g_FusionEnterExitTracingEnabled, bl
0x18000bcb7  jnz     loc_18000BDFA
0x18000bcbd  xor     dil, dil
0x18000bcc0  mov     [r14], bl
0x18000bcc3  mov     [r15], bl
0x18000bcc6  mov     [rsp+160h+var_130], dil
0x18000bccb  cmp     [rsi], rbx
0x18000bcce  jz      loc_18000BF19
0x18000bcd4  mov     rax, [rsi+20h]
0x18000bcd8  mov     [rsp+160h+var_20], r13
0x18000bce0  cmp     word ptr [rax], 5Ch ; '\'
0x18000bce4  jz      loc_18000BF36
0x18000bcea  xor     ecx, ecx; dwErrCode
0x18000bcec  call    cs:__imp_SetLastError
0x18000bcf3  nop     dword ptr [rax+rax+00h]
0x18000bcf8  mov     rcx, [rsi+20h]; lpFileName
0x18000bcfc  mov     r8, r12; lpFileInformation
0x18000bcff  xor     edx, edx; fInfoLevelId
0x18000bd01  call    cs:__imp_GetFileAttributesExW
0x18000bd08  nop     dword ptr [rax+rax+00h]
0x18000bd0d  test    eax, eax
0x18000bd0f  jz      loc_18000BDB9
0x18000bd15  cmp     [rsp+160h+var_12C], 0
0x18000bd1a  mov     bl, 1
0x18000bd1c  jz      short loc_18000BD2C
0x18000bd1e  cmp     qword ptr [rsi+248h], 0
0x18000bd26  jz      loc_18000BE04
0x18000bd2c  mov     [r14], bl
0x18000bd2f  xor     ecx, ecx; dwErrCode
0x18000bd31  mov     [r15], dil
0x18000bd34  call    cs:__imp_SetLastError
0x18000bd3b  nop     dword ptr [rax+rax+00h]
0x18000bd40  mov     rax, [rsp+160h+var_F8]
0x18000bd45  mov     dword ptr [rax], 1
0x18000bd4b  mov     r13, [rsp+160h+var_20]
0x18000bd53  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18000bd5a  mov     rax, [rsp+160h+var_F8]
0x18000bd5f  mov     r15, [rsp+160h+var_30]
0x18000bd67  mov     r14, [rsp+160h+var_28]
0x18000bd6f  mov     r12, [rsp+160h+var_18]
0x18000bd77  mov     ebx, [rax]
0x18000bd79  mov     rdi, [rsp+150h]
0x18000bd81  mov     rsi, [rsp+160h+arg_8]
0x18000bd89  jnz     loc_18000BFCD
0x18000bd8f  lea     rcx, [rsp+160h+Frame]; Frame
0x18000bd94  call    cs:__imp_RtlPopFrame
0x18000bd9b  nop     dword ptr [rax+rax+00h]
0x18000bda0  mov     eax, ebx
0x18000bda2  mov     rcx, [rbp+60h+var_40]
0x18000bda6  xor     rcx, rsp; StackCookie
0x18000bda9  call    __security_check_cookie
0x18000bdae  add     rsp, 158h
0x18000bdb5  pop     rbx
0x18000bdb6  pop     rbp
0x18000bdb7  retn
0x18000bdb9  call    cs:__imp_GetLastError
0x18000bdc0  nop     dword ptr [rax+rax+00h]
0x18000bdc5  mov     ecx, ebx
0x18000bdc7  lea     r8, qword_18007E410
0x18000bdce  cmp     ecx, 2
0x18000bdd1  jnb     short loc_18000BDE3
0x18000bdd3  mov     edx, ecx
0x18000bdd5  cmp     eax, [r8+rdx*4]
0x18000bdd9  jz      loc_18000BD2C
0x18000bddf  inc     ecx
0x18000bde1  jmp     short loc_18000BDCE
0x18000bde3  jnz     loc_18000BD15
0x18000bde9  lea     rcx, off_18006C880; struct _CALL_SITE_INFO *
0x18000bdf0  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18000bdf5  jmp     loc_18000BD4B
0x18000bdfa  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18000bdff  jmp     loc_18000BCBD
0x18000be04  lea     rcx, [rsp+70h]
0x18000be09  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18000be0e  xor     ecx, ecx; dwErrCode
0x18000be10  call    cs:__imp_SetLastError
0x18000be17  nop     dword ptr [rax+rax+00h]
0x18000be1c  lea     rdx, [rsp+70h]
0x18000be21  lea     rcx, [rsi+10h]
0x18000be25  call    ?Win32GetPathExtension@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHAEAV1@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetPathExtension(CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18000be2a  test    eax, eax
0x18000be2c  jz      loc_18000BF81
0x18000be32  mov     rdx, [rbp+60h+var_D0]; unsigned __int64
0x18000be36  lea     r8, aDll; "DLL"
0x18000be3d  mov     rcx, [rbp+60h+var_E0]; unsigned __int16 *
0x18000be41  mov     r9d, 3; unsigned __int64
0x18000be47  mov     [rsp+20h], bl; bool
0x18000be4b  call    ?FusionpEqualStrings@@YA_NPEBG_K01_N@Z; FusionpEqualStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x18000be50  test    al, al
0x18000be52  jz      short loc_18000BEAD
0x18000be54  xor     ecx, ecx; dwErrCode
0x18000be56  call    cs:__imp_SetLastError
0x18000be5d  nop     dword ptr [rax+rax+00h]
0x18000be62  mov     rcx, [rsi+20h]; unsigned __int16 *
0x18000be66  lea     rdx, [rsp+160h+var_130]; bool *
0x18000be6b  call    ?IsBinaryFileContainManifestInResource@@YAHPEBGAEA_N@Z; IsBinaryFileContainManifestInResource(ushort const *,bool &)
0x18000be70  test    eax, eax
0x18000be72  jz      loc_18000BFA7
0x18000be78  movzx   edi, [rsp+160h+var_130]
0x18000be7d  movzx   ebx, dil
0x18000be81  mov     rdx, [rbp+60h+var_E0]
0x18000be85  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x18000be8c  mov     [rsp+70h], rax
0x18000be91  lea     rax, [rbp+60h+var_C8]
0x18000be95  cmp     rdx, rax
0x18000be98  jz      loc_18000BD2C
0x18000be9e  lea     rcx, [rsp+70h]
0x18000bea3  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x18000bea8  jmp     loc_18000BD2C
0x18000bead  mov     rdx, [rbp+60h+var_D0]; unsigned __int64
0x18000beb1  lea     r8, aMui; "MUI"
0x18000beb8  mov     rcx, [rbp+60h+var_E0]; unsigned __int16 *
0x18000bebc  mov     r9d, 3; unsigned __int64
0x18000bec2  mov     [rsp+20h], bl; bool
0x18000bec6  call    ?FusionpEqualStrings@@YA_NPEBG_K01_N@Z; FusionpEqualStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x18000becb  test    al, al
0x18000becd  jnz     short loc_18000BE54
0x18000becf  cmp     dword ptr [r12+1Ch], 0
0x18000bed5  ja      short loc_18000BEE2
0x18000bed7  cmp     dword ptr [r12+20h], 800000h
0x18000bee0  jbe     short loc_18000BE81
0x18000bee2  mov     ecx, 3719h; dwErrCode
0x18000bee7  call    cs:__imp_SetLastError
0x18000beee  nop     dword ptr [rax+rax+00h]
0x18000bef3  mov     rax, [rsp+160h+var_F8]
0x18000bef8  lea     rcx, off_180078828; struct _CALL_SITE_INFO *
0x18000beff  mov     dword ptr [rax], 0
0x18000bf05  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18000bf0a  lea     rcx, [rsp+70h]
0x18000bf0f  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18000bf14  jmp     loc_18000BD4B
0x18000bf19  mov     ecx, 54Fh; dwErrCode
0x18000bf1e  call    cs:__imp_SetLastError
0x18000bf25  nop     dword ptr [rax+rax+00h]
0x18000bf2a  mov     rax, [rsp+160h+var_F8]
0x18000bf2f  mov     [rax], ebx
0x18000bf31  jmp     loc_18000BD53
0x18000bf36  cmp     word ptr [rax+2], 3Fh ; '?'
0x18000bf3b  jnz     loc_18000BCEA
0x18000bf41  cmp     word ptr [rax+4], 3Fh ; '?'
0x18000bf46  jnz     loc_18000BCEA
0x18000bf4c  cmp     word ptr [rax+6], 5Ch ; '\'
0x18000bf51  jnz     loc_18000BCEA
0x18000bf57  mov     dword ptr [rsp+160h+var_100], 0F6h
0x18000bf5f  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18000bf64  mov     ecx, 57h ; 'W'; dwErrCode
0x18000bf69  call    cs:__imp_SetLastError
0x18000bf70  nop     dword ptr [rax+rax+00h]
0x18000bf75  mov     rax, [rsp+160h+var_F8]
0x18000bf7a  mov     [rax], ebx
0x18000bf7c  jmp     loc_18000BD4B
0x18000bf81  mov     rax, [rsp+160h+var_F8]
0x18000bf86  lea     rcx, off_180078868; struct _CALL_SITE_INFO *
0x18000bf8d  mov     dword ptr [rax], 0
0x18000bf93  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18000bf98  lea     rcx, [rsp+70h]
0x18000bf9d  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18000bfa2  jmp     loc_18000BD4B
0x18000bfa7  mov     rax, [rsp+160h+var_F8]
0x18000bfac  lea     rcx, off_180078848; struct _CALL_SITE_INFO *
0x18000bfb3  mov     dword ptr [rax], 0
0x18000bfb9  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18000bfbe  lea     rcx, [rsp+70h]
0x18000bfc3  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18000bfc8  jmp     loc_18000BD4B
0x18000bfcd  test    ebx, ebx
0x18000bfcf  jz      short loc_18000BFDD
0x18000bfd1  xor     ecx, ecx; char *
0x18000bfd3  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18000bfd8  jmp     loc_18000BD8F
0x18000bfdd  call    cs:__imp_GetLastError
0x18000bfe4  nop     dword ptr [rax+rax+00h]
0x18000bfe9  mov     ecx, eax; unsigned int
0x18000bfeb  xor     edx, edx; Format
0x18000bfed  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18000bff2  jmp     loc_18000BD8F
```
