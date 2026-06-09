# LogSecurityMessage(bool,uint)

- ea: `0x14000a568`
- end: `0x14000a81a`
- name: `?LogSecurityMessage@@YAX_NI@Z`
- size: `690`
- prototype: `void(bool, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140005d74`
- `0x14000a238`

## callees

- `0x140001008`
- `0x140001048`
- `0x14000a358`
- `0x14000a568`
- `0x1400146ac`
- `0x140015a7c`
- `0x1400175a0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000a7d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a7d1`
- `ADVAPI32!DeregisterEventSource` at `0x14000a7ae`
- `ADVAPI32!DeregisterEventSource` at `0x14000a7ae`
- `ADVAPI32!GetUserNameW` at `0x14000a696`
- `ADVAPI32!GetUserNameW` at `0x14000a696`
- `ADVAPI32!RegisterEventSourceW` at `0x14000a677`
- `ADVAPI32!RegisterEventSourceW` at `0x14000a677`
- `ADVAPI32!ReportEventW` at `0x14000a7a5`
- `ADVAPI32!ReportEventW` at `0x14000a7a5`
- `ADVAPI32!LookupAccountNameW` at `0x14000a6cb`
- `ADVAPI32!LookupAccountNameW` at `0x14000a737`
- `ADVAPI32!LookupAccountNameW` at `0x14000a6cb`
- `ADVAPI32!LookupAccountNameW` at `0x14000a737`
- `ADVAPI32!RegCloseKey` at `0x14000a7e1`
- `ADVAPI32!RegCloseKey` at `0x14000a7f1`
- `ADVAPI32!RegCloseKey` at `0x14000a7e1`
- `ADVAPI32!RegCloseKey` at `0x14000a7f1`

## string_xrefs

- `0x14000a64e`: `LogSecuritySuccesses`
- `0x14000a62b`: `LogSecurityFailures`

## pseudocode

```c
void __fastcall LogSecurityMessage(char a1, unsigned int a2)
{
  unsigned __int16 *v4; // rsi
  DWORD v5; // r15d
  WORD v6; // r12
  HANDLE v7; // r14
  WCHAR *v8; // rdi
  void *v9; // rbx
  WCHAR *ReferencedDomainName; // rax
  WORD v11; // ax
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbSid; // [rsp+54h] [rbp-ACh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbBuffer; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v18; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR Strings[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( !Global::g_fWindowsNT )
    return;
  v4 = 0;
  pcbBuffer = 256;
  cchReferencedDomainName = 0;
  cbSid = 0;
  peUse = 0;
  v18 = 0;
  phkResult = 0;
  hKey = 0;
  *(_OWORD *)Strings = 0;
  OpenRegSettings(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &phkResult);
  OpenRegSettings(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &hKey);
  if ( a1 )
  {
    if ( CheckWSHFlag(L"LogSecurityFailures", phkResult, hKey, 1) )
    {
      v5 = -1057029144;
      v6 = 16;
      goto LABEL_7;
    }
  }
  else if ( CheckWSHFlag(L"LogSecuritySuccesses", phkResult, hKey, 0) )
  {
    v5 = 16712681;
    v6 = 8;
LABEL_7:
    v7 = RegisterEventSourceW(0, L"Windows Script Host");
    if ( v7 )
    {
      v8 = 0;
      v9 = 0;
      if ( GetUserNameW(Buffer, &pcbBuffer) )
      {
        LookupAccountNameW(0, Buffer, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
        if ( cbSid )
        {
          if ( cchReferencedDomainName )
          {
            v9 = operator new(cbSid);
            ReferencedDomainName = (WCHAR *)operator new(saturated_mul(cchReferencedDomainName, 2u));
            v8 = ReferencedDomainName;
            if ( v9 )
            {
              if ( !ReferencedDomainName
                || !LookupAccountNameW(0, Buffer, v9, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
              {
                operator delete(v9);
                v9 = 0;
              }
            }
          }
        }
      }
      LoadStr(&v18, a2);
      v4 = v18;
      if ( v18 )
      {
        Strings[0] = v18;
        v11 = 1;
        Strings[1] = 0;
      }
      else
      {
        Strings[0] = 0;
        v11 = 0;
      }
      ReportEventW(v7, v6, 0, v5, v9, v11, 0, Strings, 0);
      DeregisterEventSource(v7);
      if ( v9 )
        operator delete(v9);
      if ( v8 )
        operator delete(v8);
    }
  }
  SysFreeString(v4);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x14000a568  push    rbp
0x14000a56a  push    rbx
0x14000a56b  push    rsi
0x14000a56c  push    rdi
0x14000a56d  push    r12
0x14000a56f  push    r13
0x14000a571  push    r14
0x14000a573  push    r15
0x14000a575  lea     rbp, [rsp-1B8h]
0x14000a57d  sub     rsp, 2B8h
0x14000a584  mov     rax, cs:__security_cookie
0x14000a58b  xor     rax, rsp
0x14000a58e  mov     [rbp+1F0h+var_50], rax
0x14000a595  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x14000a59c  mov     r13d, edx
0x14000a59f  mov     bl, cl
0x14000a5a1  jz      loc_14000A7F7
0x14000a5a7  xor     esi, esi
0x14000a5a9  mov     [rsp+2F0h+pcbBuffer], 100h
0x14000a5b1  xorps   xmm0, xmm0
0x14000a5b4  mov     [rsp+2F0h+var_2A0], 0
0x14000a5bc  mov     edi, 20019h
0x14000a5c1  mov     [rsp+2F0h+cbSid], 0
0x14000a5c9  mov     r8d, edi; samDesired
0x14000a5cc  mov     [rsp+2F0h+var_298], 0
0x14000a5d4  lea     r9, [rsp+2F0h+phkResult]; phkResult
0x14000a5d9  mov     [rsp+2F0h+var_278], rsi
0x14000a5de  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x14000a5e5  mov     [rsp+2F0h+phkResult], rsi
0x14000a5ea  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000a5f1  mov     [rsp+2F0h+hKey], rsi
0x14000a5f6  movups  xmmword ptr [rbp+1F0h+Strings], xmm0
0x14000a5fa  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x14000a5ff  lea     r9, [rsp+2F0h+hKey]; phkResult
0x14000a604  mov     r8d, edi; samDesired
0x14000a607  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x14000a60e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a615  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x14000a61a  mov     r8, [rsp+2F0h+hKey]; HKEY
0x14000a61f  mov     rdx, [rsp+2F0h+phkResult]; hKey
0x14000a624  test    bl, bl
0x14000a626  jz      short loc_14000A64B
0x14000a628  mov     r9b, 1; bool
0x14000a62b  lea     rcx, aLogsecurityfai; "LogSecurityFailures"
0x14000a632  call    ?CheckWSHFlag@@YA_NPEBGPEAUHKEY__@@1_N@Z; CheckWSHFlag(ushort const *,HKEY__ *,HKEY__ *,bool)
0x14000a637  test    al, al
0x14000a639  jz      loc_14000A7CE
0x14000a63f  mov     r15d, 0C0FF03E8h
0x14000a645  lea     r12d, [rsi+10h]
0x14000a649  jmp     short loc_14000A66E
0x14000a64b  xor     r9d, r9d; bool
0x14000a64e  lea     rcx, aLogsecuritysuc; "LogSecuritySuccesses"
0x14000a655  call    ?CheckWSHFlag@@YA_NPEBGPEAUHKEY__@@1_N@Z; CheckWSHFlag(ushort const *,HKEY__ *,HKEY__ *,bool)
0x14000a65a  test    al, al
0x14000a65c  jz      loc_14000A7CE
0x14000a662  mov     r15d, 0FF03E9h
0x14000a668  mov     r12d, 8
0x14000a66e  lea     rdx, SourceName; "Windows Script Host"
0x14000a675  xor     ecx, ecx; lpUNCServerName
0x14000a677  call    cs:__imp_RegisterEventSourceW
0x14000a67d  mov     r14, rax
0x14000a680  test    rax, rax
0x14000a683  jz      loc_14000A7CE
0x14000a689  lea     rdx, [rsp+2F0h+pcbBuffer]; pcbBuffer
0x14000a68e  xor     edi, edi
0x14000a690  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x14000a694  xor     ebx, ebx
0x14000a696  call    cs:__imp_GetUserNameW
0x14000a69c  test    eax, eax
0x14000a69e  jz      loc_14000A74B
0x14000a6a4  lea     rax, [rsp+2F0h+var_298]
0x14000a6a9  xor     r8d, r8d; Sid
0x14000a6ac  mov     [rsp+2F0h+peUse], rax; peUse
0x14000a6b1  lea     r9, [rsp+2F0h+cbSid]; cbSid
0x14000a6b6  lea     rax, [rsp+2F0h+var_2A0]
0x14000a6bb  xor     ecx, ecx; lpSystemName
0x14000a6bd  mov     [rsp+2F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14000a6c2  lea     rdx, [rbp+1F0h+Buffer]; lpAccountName
0x14000a6c6  mov     [rsp+2F0h+ReferencedDomainName], rbx; ReferencedDomainName
0x14000a6cb  call    cs:__imp_LookupAccountNameW
0x14000a6d1  mov     eax, [rsp+2F0h+cbSid]
0x14000a6d5  test    eax, eax
0x14000a6d7  jz      short loc_14000A74B
0x14000a6d9  cmp     [rsp+2F0h+var_2A0], ebx
0x14000a6dd  jbe     short loc_14000A74B
0x14000a6df  mov     ecx, eax; Size
0x14000a6e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a6e6  mov     ecx, [rsp+2F0h+var_2A0]
0x14000a6ea  mov     rbx, rax
0x14000a6ed  lea     eax, [rdi+2]
0x14000a6f0  mul     rcx
0x14000a6f3  lea     rcx, [rdi-1]
0x14000a6f7  cmovb   rax, rcx
0x14000a6fb  mov     rcx, rax; Size
0x14000a6fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a703  mov     rdi, rax
0x14000a706  test    rbx, rbx
0x14000a709  jz      short loc_14000A74B
0x14000a70b  test    rax, rax
0x14000a70e  jz      short loc_14000A741
0x14000a710  lea     rax, [rsp+2F0h+var_298]
0x14000a715  mov     r8, rbx; Sid
0x14000a718  mov     [rsp+2F0h+peUse], rax; peUse
0x14000a71d  lea     r9, [rsp+2F0h+cbSid]; cbSid
0x14000a722  lea     rax, [rsp+2F0h+var_2A0]
0x14000a727  xor     ecx, ecx; lpSystemName
0x14000a729  mov     [rsp+2F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14000a72e  lea     rdx, [rbp+1F0h+Buffer]; lpAccountName
0x14000a732  mov     [rsp+2F0h+ReferencedDomainName], rdi; ReferencedDomainName
0x14000a737  call    cs:__imp_LookupAccountNameW
0x14000a73d  test    eax, eax
0x14000a73f  jnz     short loc_14000A74B
0x14000a741  mov     rcx, rbx; Block
0x14000a744  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a749  xor     ebx, ebx
0x14000a74b  mov     edx, r13d; unsigned int
0x14000a74e  lea     rcx, [rsp+2F0h+var_278]; unsigned __int16 **
0x14000a753  call    ?LoadStr@@YAHPEAPEAGI@Z; LoadStr(ushort * *,uint)
0x14000a758  mov     rsi, [rsp+2F0h+var_278]
0x14000a75d  test    rsi, rsi
0x14000a760  jnz     short loc_14000A76A
0x14000a762  mov     [rbp+1F0h+Strings], rsi
0x14000a766  xor     eax, eax
0x14000a768  jmp     short loc_14000A77B
0x14000a76a  mov     [rbp+1F0h+Strings], rsi
0x14000a76e  mov     eax, 1
0x14000a773  mov     [rbp+1F0h+Strings+8], 0
0x14000a77b  xor     r8d, r8d; wCategory
0x14000a77e  lea     rcx, [rbp+1F0h+Strings]
0x14000a782  mov     [rsp+2F0h+lpRawData], r8; lpRawData
0x14000a787  mov     r9d, r15d; dwEventID
0x14000a78a  mov     [rsp+2F0h+lpStrings], rcx; lpStrings
0x14000a78f  movzx   edx, r12w; wType
0x14000a793  mov     dword ptr [rsp+2F0h+peUse], r8d; dwDataSize
0x14000a798  mov     rcx, r14; hEventLog
0x14000a79b  mov     word ptr [rsp+2F0h+cchReferencedDomainName], ax; wNumStrings
0x14000a7a0  mov     [rsp+2F0h+ReferencedDomainName], rbx; lpUserSid
0x14000a7a5  call    cs:__imp_ReportEventW
0x14000a7ab  mov     rcx, r14; hEventLog
0x14000a7ae  call    cs:__imp_DeregisterEventSource
0x14000a7b4  test    rbx, rbx
0x14000a7b7  jz      short loc_14000A7C1
0x14000a7b9  mov     rcx, rbx; Block
0x14000a7bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a7c1  test    rdi, rdi
0x14000a7c4  jz      short loc_14000A7CE
0x14000a7c6  mov     rcx, rdi; Block
0x14000a7c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a7ce  mov     rcx, rsi; bstrString
0x14000a7d1  call    cs:__imp_SysFreeString
0x14000a7d7  mov     rcx, [rsp+2F0h+hKey]; hKey
0x14000a7dc  test    rcx, rcx
0x14000a7df  jz      short loc_14000A7E7
0x14000a7e1  call    cs:__imp_RegCloseKey
0x14000a7e7  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x14000a7ec  test    rcx, rcx
0x14000a7ef  jz      short loc_14000A7F7
0x14000a7f1  call    cs:__imp_RegCloseKey
0x14000a7f7  mov     rcx, [rbp+1F0h+var_50]
0x14000a7fe  xor     rcx, rsp; StackCookie
0x14000a801  call    __security_check_cookie
0x14000a806  add     rsp, 2B8h
0x14000a80d  pop     r15
0x14000a80f  pop     r14
0x14000a811  pop     r13
0x14000a813  pop     r12
0x14000a815  pop     rdi
0x14000a816  pop     rsi
0x14000a817  pop     rbx
0x14000a818  pop     rbp
0x14000a819  retn
```
