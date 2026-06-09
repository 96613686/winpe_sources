# Diagnostics::OTelLogRecord::GetLogLevelFromString(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18002ba50`
- end: `0x18002bc81`
- name: `?GetLogLevelFromString@OTelLogRecord@Diagnostics@@SA?AW4LogLevel@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002c64c`
- `0x1800434a0`
- `0x180043ec0`
- `0x180044d70`
- `0x180045e10`

## callees

- `0x180008a2c`
- `0x18001815c`
- `0x180018bec`
- `0x18002ba50`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bab9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002baf5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bb32`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bb74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bbb2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bbda`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bc0b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bab9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002baf5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bb32`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bb74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bbb2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bbda`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bc0b`

## pseudocode

```c
int __fastcall Diagnostics::OTelLogRecord::GetLogLevelFromString(WCHAR *lpString1)
{
  int *v1; // rsi
  const WCHAR **v2; // rbx
  int result; // eax
  LPCWCH v4; // rdi
  int *v5; // r14
  LPCWCH v6; // rbp
  const WCHAR *v7; // rcx
  int v8; // edx
  int *v9; // rsi
  const WCHAR *v10; // rcx
  int v11; // edx
  int *v12; // r14
  _QWORD *v13; // rbp
  const WCHAR *v14; // rcx
  int v15; // edx
  int *v16; // rdi
  _QWORD *v17; // rsi
  const WCHAR *v18; // rcx
  int v19; // edx
  int *v20; // r14
  _QWORD *v21; // rbp
  const WCHAR *v22; // rcx
  const WCHAR *v23; // rcx
  unsigned int v24; // eax
  const char *v25; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = (int *)(lpString1 + 8);
  v2 = (const WCHAR **)lpString1;
  if ( !*((_QWORD *)lpString1 + 2) )
    return 0;
  v4 = lpString1 + 12;
  if ( *((_QWORD *)lpString1 + 3) <= 7u )
  {
    v5 = (int *)(lpString1 + 8);
    v6 = lpString1 + 12;
  }
  else
  {
    lpString1 = *(WCHAR **)lpString1;
    v5 = (int *)(v2 + 2);
    v6 = (LPCWCH)(v2 + 3);
  }
  if ( CompareStringOrdinal(lpString1, *v1, L"TRACE", -1, 1) == 2 )
    return 1;
  v7 = (const WCHAR *)v2;
  v8 = *v1;
  if ( *(_QWORD *)v4 <= 7u )
  {
    v9 = v5;
  }
  else
  {
    v7 = *v2;
    v9 = (int *)(v2 + 2);
    v4 = v6;
  }
  result = CompareStringOrdinal(v7, v8, L"DEBUG", -1, 1);
  if ( result != 2 )
  {
    v10 = (const WCHAR *)v2;
    v11 = *v5;
    if ( *(_QWORD *)v4 <= 7u )
    {
      v12 = v9;
      v13 = v4;
    }
    else
    {
      v10 = *v2;
      v12 = (int *)(v2 + 2);
      v13 = v2 + 3;
    }
    if ( CompareStringOrdinal(v10, v11, L"INFO", -1, 1) == 2 )
    {
      return 3;
    }
    else
    {
      v14 = (const WCHAR *)v2;
      v15 = *v9;
      if ( *(_QWORD *)v4 <= 7u )
      {
        v16 = v12;
        v17 = v13;
      }
      else
      {
        v14 = *v2;
        v16 = (int *)(v2 + 2);
        v17 = v2 + 3;
      }
      if ( CompareStringOrdinal(v14, v15, L"WARN", -1, 1) == 2 )
        return 4;
      v18 = (const WCHAR *)v2;
      v19 = *v12;
      if ( *v13 <= 7u )
      {
        v20 = v16;
        v21 = v17;
      }
      else
      {
        v18 = *v2;
        v20 = (int *)(v2 + 2);
        v21 = v2 + 3;
      }
      if ( CompareStringOrdinal(v18, v19, L"WARNING", -1, 1) == 2 )
      {
        return 4;
      }
      else
      {
        v22 = (const WCHAR *)v2;
        if ( *v17 > 7u )
          v22 = *v2;
        if ( CompareStringOrdinal(v22, *v16, L"ERROR", -1, 1) == 2 )
        {
          return 5;
        }
        else
        {
          v23 = (const WCHAR *)v2;
          if ( *v21 > 7u )
            v23 = *v2;
          if ( CompareStringOrdinal(v23, *v20, L"FATAL", -1, 1) != 2 )
          {
            std::wstring::c_str(v2);
            v24 = wil::verify_hresult<long>(2147942487LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x285,
              (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
              (const char *)v24,
              (int)"Invalid logLevel string value '%ls'",
              v25);
          }
          return 6;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002ba50  mov     rax, rsp
0x18002ba53  mov     [rax+8], rbx
0x18002ba57  mov     [rax+10h], rbp
0x18002ba5b  mov     [rax+18h], rsi
0x18002ba5f  mov     [rax+20h], rdi
0x18002ba63  push    r13
0x18002ba65  push    r14
0x18002ba67  push    r15
0x18002ba69  sub     rsp, 30h
0x18002ba6d  lea     rsi, [rcx+10h]
0x18002ba71  mov     rbx, rcx
0x18002ba74  cmp     qword ptr [rsi], 0
0x18002ba78  jnz     short loc_18002BA81
0x18002ba7a  xor     eax, eax
0x18002ba7c  jmp     loc_18002BC22
0x18002ba81  lea     rdi, [rcx+18h]
0x18002ba85  cmp     qword ptr [rdi], 7
0x18002ba89  jbe     short loc_18002BA98
0x18002ba8b  mov     rcx, [rcx]; lpString1
0x18002ba8e  lea     r14, [rbx+10h]
0x18002ba92  lea     rbp, [rbx+18h]
0x18002ba96  jmp     short loc_18002BA9E
0x18002ba98  mov     r14, rsi
0x18002ba9b  mov     rbp, rdi
0x18002ba9e  mov     edx, [rsi]; cchCount1
0x18002baa0  lea     r8, aTrace; "TRACE"
0x18002baa7  or      r13d, 0FFFFFFFFh
0x18002baab  mov     r15d, 1
0x18002bab1  mov     r9d, r13d; cchCount2
0x18002bab4  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002bab9  call    cs:__imp_CompareStringOrdinal
0x18002babf  cmp     eax, 2
0x18002bac2  jnz     short loc_18002BACC
0x18002bac4  mov     eax, r15d
0x18002bac7  jmp     loc_18002BC22
0x18002bacc  cmp     qword ptr [rdi], 7
0x18002bad0  mov     rcx, rbx; lpString1
0x18002bad3  mov     edx, [rsi]; cchCount1
0x18002bad5  jbe     short loc_18002BAE3
0x18002bad7  mov     rcx, [rbx]
0x18002bada  lea     rsi, [rbx+10h]
0x18002bade  mov     rdi, rbp
0x18002bae1  jmp     short loc_18002BAE6
0x18002bae3  mov     rsi, r14
0x18002bae6  mov     r9d, r13d; cchCount2
0x18002bae9  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002baee  lea     r8, aDebug; "DEBUG"
0x18002baf5  call    cs:__imp_CompareStringOrdinal
0x18002bafb  cmp     eax, 2
0x18002bafe  jz      loc_18002BC22
0x18002bb04  cmp     qword ptr [rdi], 7
0x18002bb08  mov     rcx, rbx; lpString1
0x18002bb0b  mov     edx, [r14]; cchCount1
0x18002bb0e  jbe     short loc_18002BB1D
0x18002bb10  mov     rcx, [rbx]
0x18002bb13  lea     r14, [rbx+10h]
0x18002bb17  lea     rbp, [rbx+18h]
0x18002bb1b  jmp     short loc_18002BB23
0x18002bb1d  mov     r14, rsi
0x18002bb20  mov     rbp, rdi
0x18002bb23  mov     r9d, r13d; cchCount2
0x18002bb26  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002bb2b  lea     r8, aInfo_0; "INFO"
0x18002bb32  call    cs:__imp_CompareStringOrdinal
0x18002bb38  cmp     eax, 2
0x18002bb3b  jnz     short loc_18002BB47
0x18002bb3d  mov     eax, 3
0x18002bb42  jmp     loc_18002BC22
0x18002bb47  cmp     qword ptr [rdi], 7
0x18002bb4b  mov     rcx, rbx; lpString1
0x18002bb4e  mov     edx, [rsi]; cchCount1
0x18002bb50  jbe     short loc_18002BB5F
0x18002bb52  mov     rcx, [rbx]
0x18002bb55  lea     rdi, [rbx+10h]
0x18002bb59  lea     rsi, [rbx+18h]
0x18002bb5d  jmp     short loc_18002BB65
0x18002bb5f  mov     rdi, r14
0x18002bb62  mov     rsi, rbp
0x18002bb65  mov     r9d, r13d; cchCount2
0x18002bb68  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002bb6d  lea     r8, aWarn; "WARN"
0x18002bb74  call    cs:__imp_CompareStringOrdinal
0x18002bb7a  cmp     eax, 2
0x18002bb7d  jz      loc_18002BC1D
0x18002bb83  cmp     qword ptr [rbp+0], 7
0x18002bb88  mov     rcx, rbx; lpString1
0x18002bb8b  mov     edx, [r14]; cchCount1
0x18002bb8e  jbe     short loc_18002BB9D
0x18002bb90  mov     rcx, [rbx]
0x18002bb93  lea     r14, [rbx+10h]
0x18002bb97  lea     rbp, [rbx+18h]
0x18002bb9b  jmp     short loc_18002BBA3
0x18002bb9d  mov     r14, rdi
0x18002bba0  mov     rbp, rsi
0x18002bba3  mov     r9d, r13d; cchCount2
0x18002bba6  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002bbab  lea     r8, aWarning; "WARNING"
0x18002bbb2  call    cs:__imp_CompareStringOrdinal
0x18002bbb8  cmp     eax, 2
0x18002bbbb  jz      short loc_18002BC1D
0x18002bbbd  cmp     qword ptr [rsi], 7
0x18002bbc1  mov     rcx, rbx
0x18002bbc4  jbe     short loc_18002BBC9
0x18002bbc6  mov     rcx, [rbx]; lpString1
0x18002bbc9  mov     edx, [rdi]; cchCount1
0x18002bbcb  lea     r8, aError; "ERROR"
0x18002bbd2  mov     r9d, r13d; cchCount2
0x18002bbd5  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002bbda  call    cs:__imp_CompareStringOrdinal
0x18002bbe0  cmp     eax, 2
0x18002bbe3  jnz     short loc_18002BBEC
0x18002bbe5  mov     eax, 5
0x18002bbea  jmp     short loc_18002BC22
0x18002bbec  cmp     qword ptr [rbp+0], 7
0x18002bbf1  mov     rcx, rbx
0x18002bbf4  jbe     short loc_18002BBF9
0x18002bbf6  mov     rcx, [rbx]; lpString1
0x18002bbf9  mov     edx, [r14]; cchCount1
0x18002bbfc  lea     r8, aFatal; "FATAL"
0x18002bc03  mov     r9d, r13d; cchCount2
0x18002bc06  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002bc0b  call    cs:__imp_CompareStringOrdinal
0x18002bc11  cmp     eax, 2
0x18002bc14  jnz     short loc_18002BC41
0x18002bc16  mov     eax, 6
0x18002bc1b  jmp     short loc_18002BC22
0x18002bc1d  mov     eax, 4
0x18002bc22  mov     rbx, [rsp+48h+arg_0]
0x18002bc27  mov     rbp, [rsp+48h+arg_8]
0x18002bc2c  mov     rsi, [rsp+48h+arg_10]
0x18002bc31  mov     rdi, [rsp+48h+arg_18]
0x18002bc36  add     rsp, 30h
0x18002bc3a  pop     r15
0x18002bc3c  pop     r14
0x18002bc3e  pop     r13
0x18002bc40  retn
0x18002bc41  mov     rcx, rbx
0x18002bc44  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002bc49  mov     ecx, 80070057h
0x18002bc4e  mov     rdx, rax
0x18002bc51  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002bc56  mov     rcx, [rsp+48h]; this
0x18002bc5b  lea     r8, aCW1SSrcCalliop_14; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18002bc62  mov     [rsp+48h+var_20], rdx; char *
0x18002bc67  mov     r9d, eax; char *
0x18002bc6a  lea     rax, aInvalidLogleve_0; "Invalid logLevel string value '%ls'"
0x18002bc71  mov     edx, 285h; void *
0x18002bc76  mov     qword ptr [rsp+48h+bIgnoreCase], rax; int
0x18002bc7b  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
