# GetUserStateKeyName

- ea: `0x1400978b4`
- end: `0x140097b44`
- name: `GetUserStateKeyName`
- size: `656`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400976f4`
- `0x140097f3c`

## callees

- `0x140027310`
- `0x140038250`
- `0x1400434c0`
- `0x14008f7e8`
- `0x1400978b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140097964`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140097964`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140097953`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140097953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400978f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400978f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400978e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400978e9`

## string_xrefs

- `0x140097913`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x14009799b`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x1400979f3`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140097a67`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140097ad0`: `onecore\ds\security\eas\policyengine\extnlib\fvewrappers.cpp`
- `0x140097902`: `ConvertSidToStringSid`

## pseudocode

```c
__int64 __fastcall GetUserStateKeyName(PSID Sid, _QWORD *a2)
{
  unsigned __int16 *LastError; // rbx
  __int64 v5; // rax
  unsigned __int64 v6; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v8; // rax
  unsigned __int64 v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v14; // [rsp+20h] [rbp-20h]
  const wchar_t *v15; // [rsp+28h] [rbp-18h]
  unsigned __int16 *v16; // [rsp+68h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp+30h] BYREF

  *a2 = 0;
  StringSid = 0;
  CAutoPtr<unsigned short *,&void DeleteSidString(unsigned short *)>::Free(&StringSid);
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v5 = -1;
    do
      ++v5;
    while ( StringSid[v5] );
    v6 = (unsigned int)(2 * v5 + 114);
    ProcessHeap = GetProcessHeap();
    v8 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v6);
    v16 = v8;
    LastError = v8;
    if ( v8 )
    {
      v9 = v6 >> 1;
      v10 = StringCchCatW(v8, v9, L"Software\\Microsoft\\Windows\\CurrentVersion\\EAS\\UserState");
      if ( v10 )
      {
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          v10,
          L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
          442,
          L"StringCchCat(hr)",
          &pPassword);
        v15 = L"StringCchCat";
        LODWORD(v14) = 443;
      }
      else
      {
        v11 = StringCchCatW(LastError, v9, L"\\");
        if ( v11 )
        {
          DbgPrintfW(
            1u,
            L"(0x%08x) %ws:%u : %ws:%ws\n",
            v11,
            L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
            451,
            L"StringCchCat(hr)",
            &pPassword);
          v15 = L"StringCchCat";
          LODWORD(v14) = 452;
        }
        else
        {
          v12 = StringCchCatW(LastError, v9, StringSid);
          if ( !v12 )
          {
            v16 = 0;
            *a2 = LastError;
            CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v16);
            LODWORD(LastError) = 0;
            goto LABEL_16;
          }
          DbgPrintfW(
            1u,
            L"(0x%08x) %ws:%u : %ws:%ws\n",
            v12,
            L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
            460,
            L"StringCchCat(hr)",
            &pPassword);
          v15 = L"StringCchCat";
          LODWORD(v14) = 461;
        }
      }
      LODWORD(LastError) = 87;
    }
    else
    {
      LODWORD(LastError) = 14;
      v15 = L"HeapAlloc";
      LODWORD(v14) = 434;
    }
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      (unsigned int)LastError,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      v14,
      v15,
      &pPassword);
    CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v16);
  }
  else
  {
    LastError = (unsigned __int16 *)GetLastError();
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      LastError,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\fvewrappers.cpp",
      425,
      L"ConvertSidToStringSid",
      &pPassword);
  }
LABEL_16:
  CAutoPtr<unsigned short *,&void DeleteSidString(unsigned short *)>::Free(&StringSid);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400978b4  mov     [rsp-18h+arg_0], rbx
0x1400978b9  mov     [rsp-18h+arg_18], rsi
0x1400978be  push    rbp
0x1400978bf  push    rdi
0x1400978c0  push    r14
0x1400978c2  mov     rbp, rsp
0x1400978c5  sub     rsp, 40h
0x1400978c9  mov     rbx, rcx
0x1400978cc  xor     r14d, r14d
0x1400978cf  lea     rcx, [rbp+StringSid]
0x1400978d3  mov     [rdx], r14
0x1400978d6  mov     [rbp+StringSid], r14
0x1400978da  mov     rsi, rdx
0x1400978dd  call    ?Free@?$CAutoPtr@PEAG$1?DeleteSidString@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&DeleteSidString(ushort *)>::Free(void)
0x1400978e2  lea     rdx, [rbp+StringSid]; StringSid
0x1400978e6  mov     rcx, rbx; Sid
0x1400978e9  call    cs:__imp_ConvertSidToStringSidW
0x1400978ef  test    eax, eax
0x1400978f1  jnz     short loc_14009793A
0x1400978f3  call    cs:__imp_GetLastError
0x1400978f9  mov     ebx, eax
0x1400978fb  lea     rdi, pPassword
0x140097902  lea     rax, aConvertsidtost_0; "ConvertSidToStringSid"
0x140097909  mov     [rsp+40h+var_10], rdi
0x14009790e  mov     [rsp+40h+var_18], rax
0x140097913  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x14009791a  mov     r8d, ebx
0x14009791d  mov     dword ptr [rsp+40h+var_20], 1A9h
0x140097925  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x14009792c  lea     ecx, [r14+1]; unsigned int
0x140097930  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097935  jmp     loc_140097B26
0x14009793a  mov     rcx, [rbp+StringSid]
0x14009793e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140097942  inc     rax
0x140097945  cmp     [rcx+rax*2], r14w
0x14009794a  jnz     short loc_140097942
0x14009794c  lea     edi, ds:72h[rax*2]
0x140097953  call    cs:__imp_GetProcessHeap
0x140097959  mov     r8d, edi; dwBytes
0x14009795c  mov     edx, 8; dwFlags
0x140097961  mov     rcx, rax; hHeap
0x140097964  call    cs:__imp_HeapAlloc
0x14009796a  mov     [rbp+arg_8], rax
0x14009796e  mov     rbx, rax
0x140097971  test    rax, rax
0x140097974  jnz     short loc_1400979C4
0x140097976  lea     rdi, pPassword
0x14009797d  mov     ebx, 0Eh
0x140097982  mov     [rsp+40h+var_10], rdi
0x140097987  lea     rax, aHeapalloc; "HeapAlloc"
0x14009798e  mov     [rsp+40h+var_18], rax
0x140097993  mov     dword ptr [rsp+40h+var_20], 1B2h
0x14009799b  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x1400979a2  mov     r8d, ebx
0x1400979a5  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x1400979ac  mov     ecx, 1; unsigned int
0x1400979b1  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x1400979b6  lea     rcx, [rbp+arg_8]
0x1400979ba  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x1400979bf  jmp     loc_140097B26
0x1400979c4  shr     rdi, 1
0x1400979c7  lea     r8, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400979ce  mov     rdx, rdi; unsigned __int64
0x1400979d1  mov     rcx, rbx; unsigned __int16 *
0x1400979d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400979d9  test    eax, eax
0x1400979db  jz      short loc_140097A3B
0x1400979dd  lea     rcx, aStringcchcatHr; "StringCchCat(hr)"
0x1400979e4  mov     r8d, eax
0x1400979e7  lea     rdi, pPassword
0x1400979ee  mov     [rsp+40h+var_10], rdi
0x1400979f3  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x1400979fa  mov     [rsp+40h+var_18], rcx
0x1400979ff  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140097a06  mov     ecx, 1; unsigned int
0x140097a0b  mov     dword ptr [rsp+40h+var_20], 1BAh
0x140097a13  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097a18  mov     [rsp+40h+var_10], rdi
0x140097a1d  lea     rax, aStringcchcat; "StringCchCat"
0x140097a24  mov     [rsp+40h+var_18], rax
0x140097a29  mov     dword ptr [rsp+40h+var_20], 1BBh
0x140097a31  mov     ebx, 57h ; 'W'
0x140097a36  jmp     loc_14009799B
0x140097a3b  lea     r8, SubStr; "\\"
0x140097a42  mov     rdx, rdi; unsigned __int64
0x140097a45  mov     rcx, rbx; unsigned __int16 *
0x140097a48  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140097a4d  test    eax, eax
0x140097a4f  jz      short loc_140097AA7
0x140097a51  lea     rcx, aStringcchcatHr; "StringCchCat(hr)"
0x140097a58  mov     r8d, eax
0x140097a5b  lea     rdi, pPassword
0x140097a62  mov     [rsp+40h+var_10], rdi
0x140097a67  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x140097a6e  mov     [rsp+40h+var_18], rcx
0x140097a73  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140097a7a  mov     ecx, 1; unsigned int
0x140097a7f  mov     dword ptr [rsp+40h+var_20], 1C3h
0x140097a87  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097a8c  mov     [rsp+40h+var_10], rdi
0x140097a91  lea     rax, aStringcchcat; "StringCchCat"
0x140097a98  mov     [rsp+40h+var_18], rax
0x140097a9d  mov     dword ptr [rsp+40h+var_20], 1C4h
0x140097aa5  jmp     short loc_140097A31
0x140097aa7  mov     r8, [rbp+StringSid]; unsigned __int16 *
0x140097aab  mov     rdx, rdi; unsigned __int64
0x140097aae  mov     rcx, rbx; unsigned __int16 *
0x140097ab1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140097ab6  test    eax, eax
0x140097ab8  jz      short loc_140097B13
0x140097aba  lea     rcx, aStringcchcatHr; "StringCchCat(hr)"
0x140097ac1  mov     r8d, eax
0x140097ac4  lea     rdi, pPassword
0x140097acb  mov     [rsp+40h+var_10], rdi
0x140097ad0  lea     r9, aOnecoreDsSecur_2; "onecore\\ds\\security\\eas\\policyengin"...
0x140097ad7  mov     [rsp+40h+var_18], rcx
0x140097adc  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140097ae3  mov     ecx, 1; unsigned int
0x140097ae8  mov     dword ptr [rsp+40h+var_20], 1CCh
0x140097af0  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140097af5  mov     [rsp+40h+var_10], rdi
0x140097afa  lea     rax, aStringcchcat; "StringCchCat"
0x140097b01  mov     [rsp+40h+var_18], rax
0x140097b06  mov     dword ptr [rsp+40h+var_20], 1CDh
0x140097b0e  jmp     loc_140097A31
0x140097b13  lea     rcx, [rbp+arg_8]
0x140097b17  mov     [rbp+arg_8], r14
0x140097b1b  mov     [rsi], rbx
0x140097b1e  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x140097b23  mov     ebx, r14d
0x140097b26  lea     rcx, [rbp+StringSid]
0x140097b2a  call    ?Free@?$CAutoPtr@PEAG$1?DeleteSidString@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&DeleteSidString(ushort *)>::Free(void)
0x140097b2f  mov     rsi, [rsp+40h+arg_18]
0x140097b34  mov     eax, ebx
0x140097b36  mov     rbx, [rsp+40h+arg_0]
0x140097b3b  add     rsp, 40h
0x140097b3f  pop     r14
0x140097b41  pop     rdi
0x140097b42  pop     rbp
0x140097b43  retn
```
