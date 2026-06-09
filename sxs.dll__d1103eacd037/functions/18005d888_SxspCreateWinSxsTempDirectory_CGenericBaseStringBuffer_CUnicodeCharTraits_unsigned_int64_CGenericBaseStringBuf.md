# SxspCreateWinSxsTempDirectory(CGenericBaseStringBuffer<CUnicodeCharTraits> &,unsigned __int64 *,CGenericBaseStringBuffer<CUnicodeCharTraits> *,unsigned __int64 *)

- ea: `0x18005d888`
- end: `0x18005db30`
- name: `?SxspCreateWinSxsTempDirectory@@YAHAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEA_KPEAV1@1@Z`
- size: `680`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x18006425c`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18001d6f0`
- `0x18001e5d0`
- `0x180020820`
- `0x180023260`
- `0x18002a7b4`
- `0x18002d3dc`
- `0x180032350`
- `0x18005d888`
- `0x180060e14`
- `0x1800632cc`
- `0x180063428`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d958`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d978`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d99b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d9b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d9d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dadd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d958`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d978`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d99b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d9b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d9d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005da1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dadd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005da42`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005da42`

## string_xrefs

- `0x18005d9e9`: `InstallTemp`

## pseudocode

```c
__int64 __fastcall SxspCreateWinSxsTempDirectory(__int64 a1, __int64 a2, _BYTE *a3)
{
  _BYTE *v5; // rsi
  int v6; // ebx
  char **v7; // rcx
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-E0h] BYREF
  int v11; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v12; // [rsp+30h] [rbp-D0h]
  __int64 *v13; // [rsp+38h] [rbp-C8h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  int v15; // [rsp+48h] [rbp-B8h]
  int *v16; // [rsp+50h] [rbp-B0h]
  struct _SYSTEMTIME LocalTime; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+68h] [rbp-98h]
  _BYTE v19[176]; // [rsp+70h] [rbp-90h] BYREF

  v11 = 1;
  v13 = &qword_180073100;
  v14 = 544438355;
  v16 = &v10;
  v10 = 0;
  v12 = 0;
  v15 = 2846;
  CFrame::BaseEnter((CFrame *)&v11);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v19);
  v5 = v19;
  if ( a3 )
    v5 = a3;
  if ( **(_WORD **)(a1 + 16) || **((_WORD **)v5 + 2) )
  {
LABEL_28:
    SetLastError(0x54Fu);
    *v16 = 0;
  }
  else
  {
    v6 = 0;
    while ( !**(_WORD **)(a1 + 16) )
    {
      if ( v6 >= 2 )
        goto LABEL_28;
      v18 = 0;
      LocalTime = 0;
      SetLastError(0);
      if ( !(unsigned int)SxspCreateLocallyUniqueId(&LocalTime) )
      {
        v7 = off_180075610;
        goto LABEL_26;
      }
      SetLastError(0);
      if ( !(unsigned int)SxspFormatLocallyUniqueId(&LocalTime, v5) )
      {
        v7 = off_1800755F0;
        goto LABEL_26;
      }
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyRootDirectory(a1) )
      {
        v7 = off_1800755D0;
        goto LABEL_26;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveTrailingPathSeparators(a1) )
      {
        v7 = off_1800755B0;
        goto LABEL_26;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement(a1, L"InstallTemp", 11) )
      {
        v7 = off_180075590;
        goto LABEL_26;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(a1) )
      {
        v7 = off_180075570;
        goto LABEL_26;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(
                            a1,
                            *((_QWORD *)v5 + 2),
                            *((_QWORD *)v5 + 4)) )
      {
        v7 = off_180075550;
LABEL_26:
        *v16 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v7);
        goto LABEL_29;
      }
      if ( !CreateDirectoryW(*(LPCWSTR *)(a1 + 16), 0) )
      {
        CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(a1);
        if ( GetLastError() != 183 )
        {
          FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180075530);
          goto LABEL_29;
        }
      }
      ++v6;
    }
    v10 = 1;
  }
LABEL_29:
  v8 = v10;
  CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v19);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v11);
  return v8;
}

```

## disassembly

```asm
0x18005d888  mov     [rsp-8+arg_8], rbx
0x18005d88d  mov     [rsp-8+arg_18], rsi
0x18005d892  push    rbp
0x18005d893  push    rdi
0x18005d894  push    r14
0x18005d896  lea     rbp, [rsp-30h]
0x18005d89b  sub     rsp, 130h
0x18005d8a2  mov     rax, cs:__security_cookie
0x18005d8a9  xor     rax, rsp
0x18005d8ac  mov     [rbp+40h+var_20], rax
0x18005d8b0  lea     rax, qword_180073100
0x18005d8b7  mov     [rsp+140h+var_118], 1
0x18005d8bf  mov     [rsp+140h+var_108], rax
0x18005d8c4  mov     rdi, rcx
0x18005d8c7  lea     rax, [rsp+140h+var_120]
0x18005d8cc  mov     [rsp+140h+var_100], 20737853h
0x18005d8d5  xor     r14d, r14d
0x18005d8d8  mov     [rsp+140h+var_F0], rax
0x18005d8dd  lea     rcx, [rsp+140h+var_118]; this
0x18005d8e2  mov     [rsp+140h+var_120], r14d
0x18005d8e7  mov     rbx, r8
0x18005d8ea  mov     [rsp+140h+var_110], r14
0x18005d8ef  mov     [rsp+140h+var_F8], 0B1Eh
0x18005d8f7  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005d8fc  lea     rcx, [rsp+140h+var_D0]
0x18005d901  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005d906  mov     rax, [rdi+10h]
0x18005d90a  lea     rsi, [rsp+140h+var_D0]
0x18005d90f  test    rbx, rbx
0x18005d912  cmovnz  rsi, rbx
0x18005d916  cmp     [rax], r14w
0x18005d91a  jnz     loc_18005DAD8
0x18005d920  mov     rax, [rsi+10h]
0x18005d924  cmp     [rax], r14w
0x18005d928  jnz     loc_18005DAD8
0x18005d92e  mov     ebx, r14d
0x18005d931  mov     rax, [rdi+10h]
0x18005d935  cmp     [rax], r14w
0x18005d939  jnz     loc_18005DACE
0x18005d93f  cmp     ebx, 2
0x18005d942  jge     loc_18005DAD8
0x18005d948  xorps   xmm0, xmm0
0x18005d94b  xor     eax, eax
0x18005d94d  xor     ecx, ecx; dwErrCode
0x18005d94f  mov     [rsp+140h+var_D8], eax
0x18005d953  movups  xmmword ptr [rsp+140h+LocalTime.wYear], xmm0
0x18005d958  call    cs:__imp_SetLastError
0x18005d95f  nop     dword ptr [rax+rax+00h]
0x18005d964  lea     rcx, [rsp+140h+LocalTime]; lpLocalTime
0x18005d969  call    ?SxspCreateLocallyUniqueId@@YAHPEAU_SXSP_LOCALLY_UNIQUE_ID@@@Z; SxspCreateLocallyUniqueId(_SXSP_LOCALLY_UNIQUE_ID *)
0x18005d96e  test    eax, eax
0x18005d970  jz      loc_18005DAB8
0x18005d976  xor     ecx, ecx; dwErrCode
0x18005d978  call    cs:__imp_SetLastError
0x18005d97f  nop     dword ptr [rax+rax+00h]
0x18005d984  mov     rdx, rsi
0x18005d987  lea     rcx, [rsp+140h+LocalTime]
0x18005d98c  call    ?SxspFormatLocallyUniqueId@@YAHAEBU_SXSP_LOCALLY_UNIQUE_ID@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspFormatLocallyUniqueId(_SXSP_LOCALLY_UNIQUE_ID const &,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18005d991  test    eax, eax
0x18005d993  jz      loc_18005DAAF
0x18005d999  xor     ecx, ecx; dwErrCode
0x18005d99b  call    cs:__imp_SetLastError
0x18005d9a2  nop     dword ptr [rax+rax+00h]
0x18005d9a7  mov     rcx, rdi
0x18005d9aa  call    ?SxspGetAssemblyRootDirectory@@YAHAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGetAssemblyRootDirectory(CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18005d9af  test    eax, eax
0x18005d9b1  jz      loc_18005DAA6
0x18005d9b7  xor     ecx, ecx; dwErrCode
0x18005d9b9  call    cs:__imp_SetLastError
0x18005d9c0  nop     dword ptr [rax+rax+00h]
0x18005d9c5  mov     rcx, rdi
0x18005d9c8  call    ?Win32RemoveTrailingPathSeparators@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveTrailingPathSeparators(void)
0x18005d9cd  test    eax, eax
0x18005d9cf  jz      loc_18005DA9D
0x18005d9d5  xor     ecx, ecx; dwErrCode
0x18005d9d7  call    cs:__imp_SetLastError
0x18005d9de  nop     dword ptr [rax+rax+00h]
0x18005d9e3  mov     r8d, 0Bh
0x18005d9e9  lea     rdx, aInstalltemp; "InstallTemp"
0x18005d9f0  mov     rcx, rdi
0x18005d9f3  call    ?Win32AppendPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement(ushort const *,unsigned __int64)
0x18005d9f8  test    eax, eax
0x18005d9fa  jz      loc_18005DA94
0x18005da00  xor     ecx, ecx; dwErrCode
0x18005da02  call    cs:__imp_SetLastError
0x18005da09  nop     dword ptr [rax+rax+00h]
0x18005da0e  mov     rcx, rdi
0x18005da11  call    ?Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)
0x18005da16  test    eax, eax
0x18005da18  jz      short loc_18005DA8B
0x18005da1a  xor     ecx, ecx; dwErrCode
0x18005da1c  call    cs:__imp_SetLastError
0x18005da23  nop     dword ptr [rax+rax+00h]
0x18005da28  mov     r8, [rsi+20h]
0x18005da2c  mov     rcx, rdi
0x18005da2f  mov     rdx, [rsi+10h]
0x18005da33  call    ?Win32Append@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(ushort const *,unsigned __int64)
0x18005da38  test    eax, eax
0x18005da3a  jz      short loc_18005DA82
0x18005da3c  mov     rcx, [rdi+10h]; lpPathName
0x18005da40  xor     edx, edx; lpSecurityAttributes
0x18005da42  call    cs:__imp_CreateDirectoryW
0x18005da49  nop     dword ptr [rax+rax+00h]
0x18005da4e  test    eax, eax
0x18005da50  jnz     short loc_18005DA6D
0x18005da52  mov     rcx, rdi
0x18005da55  call    ?Clear@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAX_N@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(bool)
0x18005da5a  call    cs:__imp_GetLastError
0x18005da61  nop     dword ptr [rax+rax+00h]
0x18005da66  cmp     eax, 0B7h
0x18005da6b  jnz     short loc_18005DA74
0x18005da6d  inc     ebx
0x18005da6f  jmp     loc_18005D931
0x18005da74  lea     rcx, off_180075530; struct _CALL_SITE_INFO *
0x18005da7b  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18005da80  jmp     short loc_18005DAF1
0x18005da82  lea     rcx, off_180075550; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005da89  jmp     short loc_18005DABF
0x18005da8b  lea     rcx, off_180075570; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005da92  jmp     short loc_18005DABF
0x18005da94  lea     rcx, off_180075590; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005da9b  jmp     short loc_18005DABF
0x18005da9d  lea     rcx, off_1800755B0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005daa4  jmp     short loc_18005DABF
0x18005daa6  lea     rcx, off_1800755D0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005daad  jmp     short loc_18005DABF
0x18005daaf  lea     rcx, off_1800755F0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005dab6  jmp     short loc_18005DABF
0x18005dab8  lea     rcx, off_180075610; struct _CALL_SITE_INFO *
0x18005dabf  mov     rax, [rsp+140h+var_F0]
0x18005dac4  mov     [rax], r14d
0x18005dac7  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005dacc  jmp     short loc_18005DAF1
0x18005dace  mov     [rsp+140h+var_120], 1
0x18005dad6  jmp     short loc_18005DAF1
0x18005dad8  mov     ecx, 54Fh; dwErrCode
0x18005dadd  call    cs:__imp_SetLastError
0x18005dae4  nop     dword ptr [rax+rax+00h]
0x18005dae9  mov     rax, [rsp+140h+var_F0]
0x18005daee  mov     [rax], r14d
0x18005daf1  mov     ebx, [rsp+140h+var_120]
0x18005daf5  lea     rcx, [rsp+140h+var_D0]
0x18005dafa  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005daff  lea     rcx, [rsp+140h+var_118]; this
0x18005db04  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005db09  mov     eax, ebx
0x18005db0b  mov     rcx, [rbp+40h+var_20]
0x18005db0f  xor     rcx, rsp; StackCookie
0x18005db12  call    __security_check_cookie
0x18005db17  lea     r11, [rsp+140h+var_10]
0x18005db1f  mov     rbx, [r11+28h]
0x18005db23  mov     rsi, [r11+38h]
0x18005db27  mov     rsp, r11
0x18005db2a  pop     r14
0x18005db2c  pop     rdi
0x18005db2d  pop     rbp
0x18005db2e  retn
```
