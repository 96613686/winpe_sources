# Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName(Pca::MergeSdb::Utils::TempFilePathHolder &,ushort const *)

- ea: `0x14002be40`
- end: `0x14002c072`
- name: `?GetUniqueTempDirectoryFileName@SdbFileData@Utils@MergeSdb@Pca@@SAKAEAVTempFilePathHolder@234@PEBG@Z`
- size: `562`
- prototype: `__int64 __fastcall(struct Pca::MergeSdb::Utils::TempFilePathHolder *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x140024958`

## callees

- `0x140001e68`
- `0x14001008c`
- `0x14002269c`
- `0x140028538`
- `0x14002be40`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002bf9d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002bf9d`
- `ntdll!RtlDoesFileExists_U` at `0x14002bfd4`
- `ntdll!RtlDoesFileExists_U` at `0x14002bfd4`

## string_xrefs

- `0x14002bf09`: `Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName`
- `0x14002bf45`: `Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName`
- `0x14002c00b`: `Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName`
- `0x14002c02d`: `Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName`
- `0x14002bf38`: `Failed to expand temp directory.`
- `0x14002bf02`: `StringCchCopyW failed to copy temp path input (%d)`
- `0x14002bfbc`: `%s\temp.%08X%08X.sdb`
- `0x14002bf66`: `Failed to expand temp dir`
- `0x14002bffa`: `wil::str_printf_nothrow failed to format temp file name (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName(
        struct Pca::MergeSdb::Utils::TempFilePathHolder *a1,
        const unsigned __int16 *a2)
{
  __int64 v4; // rax
  _WORD *v5; // r9
  __int64 v6; // r8
  _WORD *v7; // rcx
  __int64 v8; // rdx
  unsigned __int64 v9; // rax
  unsigned __int64 v11; // rcx
  DWORD dwLowDateTime; // r14d
  int i; // esi
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // [rsp+20h] [rbp-258h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-248h] BYREF
  _WORD v18[264]; // [rsp+40h] [rbp-238h] BYREF

  Pca::MergeSdb::Utils::TempFilePathHolder::Delete(a1);
  memset_0(v18, 0, 0x208u);
  if ( a2 && *a2 )
  {
    v4 = 2147483646;
    v5 = v18;
    v6 = 260;
    do
    {
      if ( !v4 )
        break;
      if ( !*a2 )
        break;
      *v5++ = *a2++;
      --v4;
      --v6;
    }
    while ( v6 );
    v7 = v5 - 1;
    v8 = v6 == 0 ? 0x8007007A : 0;
    if ( v6 )
      v7 = v5;
    *v7 = 0;
    if ( !v6 )
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName",
        2459,
        "StringCchCopyW failed to copy temp path input (%d)",
        122);
    v9 = -1;
    do
      ++v9;
    while ( v18[v9] );
    if ( v9 < 2 )
    {
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName",
        2464,
        "Failed to expand temp directory.");
      return 1359;
    }
    if ( v9 < 6 )
    {
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName",
        2477,
        "Failed to expand temp dir");
      return 1359;
    }
    v11 = 2 * v9 - 2;
    if ( *(_WORD *)((char *)v18 + v11) == 92 )
    {
      if ( v11 >= 0x208 )
        _report_rangecheckfailure(v11, v8);
      *(_WORD *)((char *)v18 + v11) = 0;
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
    for ( i = 0; ; ++i )
    {
      LODWORD(v16) = dwLowDateTime + i;
      v14 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              a1,
              L"%s\\temp.%08X%08X.sdb",
              v18,
              SystemTimeAsFileTime.dwHighDateTime,
              v16);
      v15 = v14;
      if ( v14 < 0 )
        break;
      if ( !RtlDoesFileExists_U(*(PCWSTR *)a1) || i >= 10 )
        return 0;
    }
    if ( (v14 & 0x1FFF0000) == 0x70000 )
      v15 = (unsigned __int16)v14;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName",
      2495,
      "wil::str_printf_nothrow failed to format temp file name (%d)",
      v15);
    return v15;
  }
  else
  {
    AslLogCallPrintf(1, "Pca::MergeSdb::Utils::SdbFileData::GetUniqueTempDirectoryFileName", 2453, "Invalid parameter.");
    return 87;
  }
}

```

## disassembly

```asm
0x14002be40  mov     [rsp+arg_8], rbx
0x14002be45  mov     [rsp+arg_10], rbp
0x14002be4a  push    rsi
0x14002be4b  push    r14
0x14002be4d  push    r15
0x14002be4f  sub     rsp, 260h
0x14002be56  mov     rax, cs:__security_cookie
0x14002be5d  xor     rax, rsp
0x14002be60  mov     [rsp+278h+var_28], rax
0x14002be68  mov     rbx, rdx
0x14002be6b  mov     r15, rcx
0x14002be6e  call    ?Delete@TempFilePathHolder@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::TempFilePathHolder::Delete(void)
0x14002be73  mov     esi, 208h
0x14002be78  lea     rcx, [rsp+278h+var_238]; void *
0x14002be7d  mov     r8d, esi; Size
0x14002be80  xor     edx, edx; Val
0x14002be82  call    memset_0
0x14002be87  xor     ebp, ebp
0x14002be89  test    rbx, rbx
0x14002be8c  jz      loc_14002C020
0x14002be92  cmp     [rbx], bp
0x14002be95  jz      loc_14002C020
0x14002be9b  mov     eax, 7FFFFFFEh
0x14002bea0  lea     r9, [rsp+278h+var_238]
0x14002bea5  mov     r8d, 104h
0x14002beab  test    rax, rax
0x14002beae  jz      short loc_14002BECD
0x14002beb0  movzx   ecx, word ptr [rbx]
0x14002beb3  test    cx, cx
0x14002beb6  jz      short loc_14002BECD
0x14002beb8  mov     [r9], cx
0x14002bebc  add     rbx, 2
0x14002bec0  add     r9, 2
0x14002bec4  dec     rax
0x14002bec7  sub     r8, 1
0x14002becb  jnz     short loc_14002BEAB
0x14002becd  mov     rax, r8
0x14002bed0  lea     rcx, [r9-2]
0x14002bed4  neg     rax
0x14002bed7  sbb     edx, edx
0x14002bed9  not     edx
0x14002bedb  and     edx, 8007007Ah
0x14002bee1  test    r8, r8
0x14002bee4  cmovnz  rcx, r9
0x14002bee8  mov     [rcx], bp
0x14002beeb  jnz     short loc_14002BF20
0x14002beed  mov     eax, edx
0x14002beef  and     eax, 1FFF0000h
0x14002bef4  cmp     eax, 70000h
0x14002bef9  jnz     short loc_14002BEFE
0x14002befb  movzx   edx, dx
0x14002befe  mov     [rsp+278h+var_258], edx
0x14002bf02  lea     r9, aStringcchcopyw; "StringCchCopyW failed to copy temp path"...
0x14002bf09  lea     rdx, aPcaMergesdbUti_0; "Pca::MergeSdb::Utils::SdbFileData::GetU"...
0x14002bf10  mov     r8d, 99Bh
0x14002bf16  mov     ecx, 1
0x14002bf1b  call    AslLogCallPrintf
0x14002bf20  lea     rcx, [rsp+278h+var_238]
0x14002bf25  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002bf29  inc     rax
0x14002bf2c  cmp     [rcx+rax*2], bp
0x14002bf30  jnz     short loc_14002BF29
0x14002bf32  cmp     rax, 2
0x14002bf36  jnb     short loc_14002BF60
0x14002bf38  lea     r9, aFailedToExpand_0; "Failed to expand temp directory."
0x14002bf3f  mov     r8d, 9A0h
0x14002bf45  lea     rdx, aPcaMergesdbUti_0; "Pca::MergeSdb::Utils::SdbFileData::GetU"...
0x14002bf4c  mov     ecx, 1
0x14002bf51  call    AslLogCallPrintf
0x14002bf56  mov     eax, 54Fh
0x14002bf5b  jmp     loc_14002C043
0x14002bf60  cmp     rax, 6
0x14002bf64  jnb     short loc_14002BF75
0x14002bf66  lea     r9, aFailedToExpand_3; "Failed to expand temp dir"
0x14002bf6d  mov     r8d, 9ADh
0x14002bf73  jmp     short loc_14002BF45
0x14002bf75  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x14002bf7d  cmp     [rsp+rcx+278h+var_238], 5Ch ; '\'
0x14002bf83  jnz     short loc_14002BF93
0x14002bf85  cmp     rcx, rsi
0x14002bf88  jnb     loc_14002C06C
0x14002bf8e  mov     [rsp+rcx+278h+var_238], bp
0x14002bf93  lea     rcx, [rsp+278h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002bf98  mov     qword ptr [rsp+278h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x14002bf9d  call    cs:__imp_GetSystemTimeAsFileTime
0x14002bfa3  mov     r14d, [rsp+278h+SystemTimeAsFileTime.dwLowDateTime]
0x14002bfa8  mov     esi, ebp
0x14002bfaa  mov     r9d, [rsp+278h+SystemTimeAsFileTime.dwHighDateTime]
0x14002bfaf  lea     eax, [r14+rsi]
0x14002bfb3  lea     r8, [rsp+278h+var_238]
0x14002bfb8  mov     [rsp+278h+var_258], eax
0x14002bfbc  lea     rdx, aSTemp08x08xSdb; "%s\\temp.%08X%08X.sdb"
0x14002bfc3  mov     rcx, r15
0x14002bfc6  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x14002bfcb  mov     ebx, eax
0x14002bfcd  test    eax, eax
0x14002bfcf  js      short loc_14002BFEB
0x14002bfd1  mov     rcx, [r15]; FileName
0x14002bfd4  call    cs:__imp_RtlDoesFileExists_U
0x14002bfda  test    al, al
0x14002bfdc  jz      short loc_14002BFE7
0x14002bfde  cmp     esi, 0Ah
0x14002bfe1  jge     short loc_14002BFE7
0x14002bfe3  inc     esi
0x14002bfe5  jmp     short loc_14002BFAA
0x14002bfe7  xor     eax, eax
0x14002bfe9  jmp     short loc_14002C043
0x14002bfeb  and     eax, 1FFF0000h
0x14002bff0  cmp     eax, 70000h
0x14002bff5  jnz     short loc_14002BFFA
0x14002bff7  movzx   ebx, bx
0x14002bffa  lea     r9, aWilStrPrintfNo_0; "wil::str_printf_nothrow failed to forma"...
0x14002c001  mov     [rsp+278h+var_258], ebx
0x14002c005  mov     r8d, 9BFh
0x14002c00b  lea     rdx, aPcaMergesdbUti_0; "Pca::MergeSdb::Utils::SdbFileData::GetU"...
0x14002c012  mov     ecx, 1
0x14002c017  call    AslLogCallPrintf
0x14002c01c  mov     eax, ebx
0x14002c01e  jmp     short loc_14002C043
0x14002c020  lea     r9, aInvalidParamet; "Invalid parameter."
0x14002c027  mov     r8d, 995h
0x14002c02d  lea     rdx, aPcaMergesdbUti_0; "Pca::MergeSdb::Utils::SdbFileData::GetU"...
0x14002c034  mov     ecx, 1
0x14002c039  call    AslLogCallPrintf
0x14002c03e  mov     eax, 57h ; 'W'
0x14002c043  mov     rcx, [rsp+278h+var_28]
0x14002c04b  xor     rcx, rsp; StackCookie
0x14002c04e  call    __security_check_cookie
0x14002c053  lea     r11, [rsp+278h+var_18]
0x14002c05b  mov     rbx, [r11+28h]
0x14002c05f  mov     rbp, [r11+30h]
0x14002c063  mov     rsp, r11
0x14002c066  pop     r15
0x14002c068  pop     r14
0x14002c06a  pop     rsi
0x14002c06b  retn
0x14002c06c  call    __report_rangecheckfailure
```
