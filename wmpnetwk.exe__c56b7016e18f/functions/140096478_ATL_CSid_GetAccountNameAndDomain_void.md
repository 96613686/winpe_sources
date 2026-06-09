# ATL::CSid::GetAccountNameAndDomain(void)

- ea: `0x140096478`
- end: `0x1400965c8`
- name: `?GetAccountNameAndDomain@CSid@ATL@@AEBAXXZ`
- size: `336`
- prototype: `void __fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140044548`

## callees

- `0x140007020`
- `0x14000c780`
- `0x1400151f0`
- `0x140027660`
- `0x140038f58`
- `0x140045f20`
- `0x140096478`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x1400964dd`
- `ADVAPI32!LookupAccountSidW` at `0x140096577`
- `ADVAPI32!LookupAccountSidW` at `0x1400964dd`
- `ADVAPI32!LookupAccountSidW` at `0x140096577`
- `KERNEL32!GetLastError` at `0x140096506`
- `KERNEL32!GetLastError` at `0x140096506`

## pseudocode

```c
void __fastcall ATL::CSid::GetAccountNameAndDomain(LPCWSTR *this)
{
  enum _SID_NAME_USE *peUse; // rsi
  DWORD LastError; // eax
  WCHAR *v4; // rbx
  WCHAR *v5; // rax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-69h] BYREF
  DWORD cchName[3]; // [rsp+44h] [rbp-65h] BYREF
  WCHAR Name[32]; // [rsp+50h] [rbp-59h] BYREF
  WCHAR ReferencedDomainName[32]; // [rsp+90h] [rbp-19h] BYREF

  peUse = (enum _SID_NAME_USE *)(this + 10);
  cchName[0] = 32;
  cchReferencedDomainName = 32;
  if ( LookupAccountSidW(
         this[14],
         this + 1,
         Name,
         cchName,
         ReferencedDomainName,
         &cchReferencedDomainName,
         (PSID_NAME_USE)this + 20) )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(this + 11, Name);
    ATL::CSimpleStringT<unsigned short,0>::SetString(this + 12, ReferencedDomainName);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v4 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(this + 11, 2 * cchName[0]);
      v5 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(this + 12, 2 * cchReferencedDomainName);
      if ( !LookupAccountSidW(this[14], this + 1, v4, cchName, v5, &cchReferencedDomainName, peUse) )
        ATL::AtlThrowLastWin32();
      ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(this + 11, 0xFFFFFFFFLL);
      ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(this + 12, 0xFFFFFFFFLL);
    }
    else if ( LastError == 1332 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Empty(this + 11);
      ATL::CSimpleStringT<unsigned short,0>::Empty(this + 12);
      *peUse = SidTypeUnknown;
    }
  }
}

```

## disassembly

```asm
0x140096478  mov     [rsp-8+arg_8], rbx
0x14009647d  mov     [rsp-8+arg_10], rsi
0x140096482  push    rbp
0x140096483  push    rdi
0x140096484  push    r12
0x140096486  push    r14
0x140096488  push    r15
0x14009648a  lea     rbp, [rsp-37h]
0x14009648f  sub     rsp, 0E0h
0x140096496  mov     rax, cs:__security_cookie
0x14009649d  xor     rax, rsp
0x1400964a0  mov     [rbp+57h+var_30], rax
0x1400964a4  mov     eax, 20h ; ' '
0x1400964a9  lea     rsi, [rcx+50h]
0x1400964ad  mov     [rbp+57h+cchName], eax
0x1400964b0  lea     rdx, [rcx+8]; Sid
0x1400964b4  mov     [rbp+57h+var_C0], eax
0x1400964b7  lea     r9, [rbp+57h+cchName]; cchName
0x1400964bb  lea     rax, [rbp+57h+var_C0]
0x1400964bf  mov     [rsp+100h+peUse], rsi; peUse
0x1400964c4  mov     [rsp+100h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1400964c9  lea     r8, [rbp+57h+Name]; Name
0x1400964cd  lea     rax, [rbp+57h+var_70]
0x1400964d1  mov     rdi, rcx
0x1400964d4  mov     rcx, [rcx+70h]; lpSystemName
0x1400964d8  mov     [rsp+100h+ReferencedDomainName], rax; ReferencedDomainName
0x1400964dd  call    cs:__imp_LookupAccountSidW
0x1400964e3  test    eax, eax
0x1400964e5  jz      short loc_140096506
0x1400964e7  lea     rcx, [rdi+58h]
0x1400964eb  lea     rdx, [rbp+57h+Name]
0x1400964ef  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1400964f4  lea     rcx, [rdi+60h]
0x1400964f8  lea     rdx, [rbp+57h+var_70]
0x1400964fc  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140096501  jmp     loc_1400965A0
0x140096506  call    cs:__imp_GetLastError
0x14009650c  cmp     eax, 7Ah ; 'z'
0x14009650f  jz      short loc_140096536
0x140096511  cmp     eax, 534h
0x140096516  jnz     loc_1400965A0
0x14009651c  lea     rcx, [rdi+58h]
0x140096520  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140096525  lea     rcx, [rdi+60h]
0x140096529  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14009652e  mov     dword ptr [rsi], 8
0x140096534  jmp     short loc_1400965A0
0x140096536  mov     edx, [rbp+57h+cchName]
0x140096539  lea     rcx, [rdi+58h]
0x14009653d  add     edx, edx
0x14009653f  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x140096544  mov     edx, [rbp+57h+var_C0]
0x140096547  lea     rcx, [rdi+60h]
0x14009654b  add     edx, edx
0x14009654d  mov     rbx, rax
0x140096550  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x140096555  lea     rcx, [rbp+57h+var_C0]
0x140096559  mov     [rsp+100h+peUse], rsi; peUse
0x14009655e  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x140096563  lea     r9, [rbp+57h+cchName]; cchName
0x140096567  mov     rcx, [rdi+70h]; lpSystemName
0x14009656b  lea     rdx, [rdi+8]; Sid
0x14009656f  mov     r8, rbx; Name
0x140096572  mov     [rsp+100h+ReferencedDomainName], rax; ReferencedDomainName
0x140096577  call    cs:__imp_LookupAccountSidW
0x14009657d  test    eax, eax
0x14009657f  jnz     short loc_140096587
0x140096581  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140096587  or      ebx, 0FFFFFFFFh
0x14009658a  lea     rcx, [rdi+58h]
0x14009658e  mov     edx, ebx
0x140096590  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x140096595  mov     edx, ebx
0x140096597  lea     rcx, [rdi+60h]
0x14009659b  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x1400965a0  mov     rcx, [rbp+57h+var_30]
0x1400965a4  xor     rcx, rsp; StackCookie
0x1400965a7  call    __security_check_cookie
0x1400965ac  lea     r11, [rsp+100h+var_20]
0x1400965b4  mov     rbx, [r11+38h]
0x1400965b8  mov     rsi, [r11+40h]
0x1400965bc  mov     rsp, r11
0x1400965bf  pop     r15
0x1400965c1  pop     r14
0x1400965c3  pop     r12
0x1400965c5  pop     rdi
0x1400965c6  pop     rbp
0x1400965c7  retn
```
