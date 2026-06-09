# SxspCreateMultiLevelDirectory(ushort const *,ushort const *)

- ea: `0x18005f8cc`
- end: `0x18005fb08`
- name: `?SxspCreateMultiLevelDirectory@@YAHPEBG0@Z`
- size: `572`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180063d20`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180013af0`
- `0x180014260`
- `0x18001c270`
- `0x18001d6f0`
- `0x180029380`
- `0x180032350`
- `0x18005d2b0`
- `0x18005f8cc`
- `0x18006a110`

## import_xrefs

- `ntdll!wcsspn` at `0x18005fa6d`
- `ntdll!wcsspn` at `0x18005fa6d`
- `ntdll!wcscspn` at `0x18005f9cd`
- `ntdll!wcscspn` at `0x18005f9cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f95d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f977`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f9e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fa07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fa29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fab1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f95d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f977`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f9e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fa07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fa29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fab1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005fa3c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005fa3c`

## pseudocode

```c
__int64 __fastcall SxspCreateMultiLevelDirectory(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  const char *v4; // rcx
  __int64 v5; // r8
  char **v6; // rcx
  size_t v7; // rdi
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-E0h] BYREF
  int v11; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v12; // [rsp+30h] [rbp-D0h]
  __int64 *v13; // [rsp+38h] [rbp-C8h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  int v15; // [rsp+48h] [rbp-B8h]
  unsigned int *v16; // [rsp+50h] [rbp-B0h]
  _BYTE v17[16]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpPathName; // [rsp+70h] [rbp-90h]

  v11 = 1;
  v13 = &qword_180075510;
  v14 = 544438355;
  v16 = (unsigned int *)&v10;
  v10 = 0;
  v12 = 0;
  v15 = 2904;
  CFrame::BaseEnter((CFrame *)&v11);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v17);
  if ( a2 )
  {
    SetLastError(0);
    v5 = -1;
    do
      ++v5;
    while ( a1[v5] );
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v17, a1, v5) )
    {
      while ( *a2 )
      {
        v7 = wcscspn(a2, L"\\/");
        if ( !v7 )
          break;
        SetLastError(0);
        if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(v17) )
        {
          v6 = off_1800754D0;
          goto LABEL_7;
        }
        SetLastError(0);
        if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v17, a2, v7) )
        {
          v6 = off_1800754B0;
          goto LABEL_7;
        }
        SetLastError(0);
        if ( !CreateDirectoryW(lpPathName, 0) && GetLastError() != 183 )
        {
          *v16 = 0;
          FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180075490);
          goto LABEL_19;
        }
        a2 += v7 + wcsspn(&a2[v7], L"\\/");
      }
      SetLastError(0);
      *v16 = 1;
    }
    else
    {
      v6 = off_1800754F0;
LABEL_7:
      *v16 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v6);
    }
  }
  else
  {
    v15 = 2909;
    FusionpTraceParameterCheck(v4);
    SetLastError(0x57u);
    *v16 = 0;
  }
LABEL_19:
  v8 = *v16;
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v17);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v11);
  return v8;
}

```

## disassembly

```asm
0x18005f8cc  mov     [rsp-8+arg_10], rbx
0x18005f8d1  push    rbp
0x18005f8d2  push    rsi
0x18005f8d3  push    rdi
0x18005f8d4  lea     rbp, [rsp-1A0h]
0x18005f8dc  sub     rsp, 2A0h
0x18005f8e3  mov     rax, cs:__security_cookie
0x18005f8ea  xor     rax, rsp
0x18005f8ed  mov     [rbp+1B0h+var_20], rax
0x18005f8f4  lea     rax, qword_180075510
0x18005f8fb  mov     [rsp+2B0h+var_288], 1
0x18005f903  mov     [rsp+2B0h+var_278], rax
0x18005f908  mov     rdi, rcx
0x18005f90b  lea     rax, [rsp+2B0h+var_290]
0x18005f910  mov     [rsp+2B0h+var_270], 20737853h
0x18005f919  xor     esi, esi
0x18005f91b  mov     [rsp+2B0h+var_260], rax
0x18005f920  lea     rcx, [rsp+2B0h+var_288]; this
0x18005f925  mov     [rsp+2B0h+var_290], esi
0x18005f929  mov     rbx, rdx
0x18005f92c  mov     [rsp+2B0h+var_280], rsi
0x18005f931  mov     [rsp+2B0h+var_268], 0B58h
0x18005f939  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005f93e  lea     rcx, [rsp+2B0h+var_250]; void *
0x18005f943  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005f948  test    rbx, rbx
0x18005f94b  jnz     short loc_18005F975
0x18005f94d  mov     [rsp+2B0h+var_268], 0B5Dh
0x18005f955  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18005f95a  lea     ecx, [rsi+57h]; dwErrCode
0x18005f95d  call    cs:__imp_SetLastError
0x18005f964  nop     dword ptr [rax+rax+00h]
0x18005f969  mov     rax, [rsp+2B0h+var_260]
0x18005f96e  mov     [rax], esi
0x18005f970  jmp     loc_18005FAC8
0x18005f975  xor     ecx, ecx; dwErrCode
0x18005f977  call    cs:__imp_SetLastError
0x18005f97e  nop     dword ptr [rax+rax+00h]
0x18005f983  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005f987  inc     r8
0x18005f98a  cmp     [rdi+r8*2], si
0x18005f98f  jnz     short loc_18005F987
0x18005f991  mov     rdx, rdi
0x18005f994  lea     rcx, [rsp+2B0h+var_250]
0x18005f999  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18005f99e  test    eax, eax
0x18005f9a0  jnz     short loc_18005F9BA
0x18005f9a2  lea     rcx, off_1800754F0; struct _CALL_SITE_INFO *
0x18005f9a9  mov     rax, [rsp+2B0h+var_260]
0x18005f9ae  mov     [rax], esi
0x18005f9b0  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005f9b5  jmp     loc_18005FAC8
0x18005f9ba  cmp     [rbx], si
0x18005f9bd  jz      loc_18005FAAF
0x18005f9c3  lea     rdx, ?Result@?1??PathSeparators@?$CCharTraitsBase@GD@@SAPEBGXZ@4QBGB; "\\/"
0x18005f9ca  mov     rcx, rbx; String
0x18005f9cd  call    cs:__imp_wcscspn
0x18005f9d4  nop     dword ptr [rax+rax+00h]
0x18005f9d9  mov     rdi, rax
0x18005f9dc  test    rax, rax
0x18005f9df  jz      loc_18005FAAF
0x18005f9e5  xor     ecx, ecx; dwErrCode
0x18005f9e7  call    cs:__imp_SetLastError
0x18005f9ee  nop     dword ptr [rax+rax+00h]
0x18005f9f3  lea     rcx, [rsp+2B0h+var_250]
0x18005f9f8  call    ?Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)
0x18005f9fd  test    eax, eax
0x18005f9ff  jz      loc_18005FAA3
0x18005fa05  xor     ecx, ecx; dwErrCode
0x18005fa07  call    cs:__imp_SetLastError
0x18005fa0e  nop     dword ptr [rax+rax+00h]
0x18005fa13  mov     r8, rdi
0x18005fa16  lea     rcx, [rsp+2B0h+var_250]
0x18005fa1b  mov     rdx, rbx
0x18005fa1e  call    ?Win32Append@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(ushort const *,unsigned __int64)
0x18005fa23  test    eax, eax
0x18005fa25  jz      short loc_18005FA97
0x18005fa27  xor     ecx, ecx; dwErrCode
0x18005fa29  call    cs:__imp_SetLastError
0x18005fa30  nop     dword ptr [rax+rax+00h]
0x18005fa35  mov     rcx, [rsp+2B0h+lpPathName]; lpPathName
0x18005fa3a  xor     edx, edx; lpSecurityAttributes
0x18005fa3c  call    cs:__imp_CreateDirectoryW
0x18005fa43  nop     dword ptr [rax+rax+00h]
0x18005fa48  test    eax, eax
0x18005fa4a  jnz     short loc_18005FA5F
0x18005fa4c  call    cs:__imp_GetLastError
0x18005fa53  nop     dword ptr [rax+rax+00h]
0x18005fa58  cmp     eax, 0B7h
0x18005fa5d  jnz     short loc_18005FA82
0x18005fa5f  lea     rbx, [rbx+rdi*2]
0x18005fa63  mov     rcx, rbx; String
0x18005fa66  lea     rdx, ?Result@?1??PathSeparators@?$CCharTraitsBase@GD@@SAPEBGXZ@4QBGB; "\\/"
0x18005fa6d  call    cs:__imp_wcsspn
0x18005fa74  nop     dword ptr [rax+rax+00h]
0x18005fa79  lea     rbx, [rbx+rax*2]
0x18005fa7d  jmp     loc_18005F9BA
0x18005fa82  mov     rax, [rsp+2B0h+var_260]
0x18005fa87  lea     rcx, off_180075490; struct _CALL_SITE_INFO *
0x18005fa8e  mov     [rax], esi
0x18005fa90  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18005fa95  jmp     short loc_18005FAC8
0x18005fa97  lea     rcx, off_1800754B0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005fa9e  jmp     loc_18005F9A9
0x18005faa3  lea     rcx, off_1800754D0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005faaa  jmp     loc_18005F9A9
0x18005faaf  xor     ecx, ecx; dwErrCode
0x18005fab1  call    cs:__imp_SetLastError
0x18005fab8  nop     dword ptr [rax+rax+00h]
0x18005fabd  mov     rax, [rsp+2B0h+var_260]
0x18005fac2  mov     dword ptr [rax], 1
0x18005fac8  mov     rax, [rsp+2B0h+var_260]
0x18005facd  lea     rcx, [rsp+2B0h+var_250]; void *
0x18005fad2  mov     ebx, [rax]
0x18005fad4  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005fad9  lea     rcx, [rsp+2B0h+var_288]; this
0x18005fade  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005fae3  mov     eax, ebx
0x18005fae5  mov     rcx, [rbp+1B0h+var_20]
0x18005faec  xor     rcx, rsp; StackCookie
0x18005faef  call    __security_check_cookie
0x18005faf4  mov     rbx, [rsp+2B0h+arg_10]
0x18005fafc  add     rsp, 2A0h
0x18005fb03  pop     rdi
0x18005fb04  pop     rsi
0x18005fb05  pop     rbp
0x18005fb06  retn
```
