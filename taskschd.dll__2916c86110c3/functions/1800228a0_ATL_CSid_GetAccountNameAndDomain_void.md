# ATL::CSid::GetAccountNameAndDomain(void)

- ea: `0x1800228a0`
- end: `0x180022b3c`
- name: `?GetAccountNameAndDomain@CSid@ATL@@AEBAXXZ`
- size: `668`
- prototype: `void __fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f730`

## callees

- `0x180022820`
- `0x1800228a0`
- `0x180023134`
- `0x1800236b8`
- `0x1800394dc`
- `0x18004ab04`
- `0x18004e950`

## import_xrefs

- `msvcrt!memmove_s` at `0x180022ab9`
- `msvcrt!memmove_s` at `0x180022ad7`
- `msvcrt!memmove_s` at `0x180022ab9`
- `msvcrt!memmove_s` at `0x180022ad7`
- `msvcrt!memcpy_s` at `0x180022977`
- `msvcrt!memcpy_s` at `0x1800229da`
- `msvcrt!memcpy_s` at `0x180022977`
- `msvcrt!memcpy_s` at `0x1800229da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ae2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180022904`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180022a92`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180022904`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180022a92`

## pseudocode

```c
void __fastcall ATL::CSid::GetAccountNameAndDomain(ATL::CSid *this)
{
  enum _SID_NAME_USE *peUse; // r15
  __int64 v3; // rbx
  char **v4; // r15
  __int64 v5; // rdi
  unsigned __int64 v6; // r12
  unsigned __int64 v7; // r13
  char *v8; // rcx
  rsize_t v9; // rdx
  char **v10; // rdi
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // r15
  char *v13; // rcx
  rsize_t v14; // rdx
  LPWSTR *v15; // rdi
  WCHAR *v16; // r12
  DWORD LastError; // eax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-89h] BYREF
  DWORD cchName[3]; // [rsp+44h] [rbp-85h] BYREF
  WCHAR Name[32]; // [rsp+50h] [rbp-79h] BYREF
  WCHAR Source[32]; // [rsp+90h] [rbp-39h] BYREF

  peUse = (enum _SID_NAME_USE *)((char *)this + 80);
  cchName[0] = 32;
  cchReferencedDomainName = 32;
  if ( LookupAccountSidW(
         *((LPCWSTR *)this + 14),
         (char *)this + 8,
         Name,
         cchName,
         Source,
         &cchReferencedDomainName,
         (PSID_NAME_USE)this + 20) )
  {
    v3 = -1;
    v4 = (char **)((char *)this + 88);
    v5 = -1;
    do
      ++v5;
    while ( Name[v5] );
    if ( (_DWORD)v5 )
    {
      v6 = ((char *)Name - *v4) >> 1;
      v7 = *((unsigned int *)*v4 - 4);
      if ( (int)((*((_DWORD *)*v4 - 3) - v5) | (1 - *((_DWORD *)*v4 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((char *)this + 88);
      v8 = *v4;
      v9 = 2LL * (int)v5;
      if ( v6 <= v7 )
        memmove_s(v8, v9, &v8[2 * v6], v9);
      else
        memcpy_s(v8, v9, Name, v9);
      ATL::CSimpleStringT<unsigned short,0>::SetLength((char *)this + 88, (unsigned int)v5);
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 88);
    }
    v10 = (char **)((char *)this + 96);
    do
      ++v3;
    while ( Source[v3] );
    if ( (_DWORD)v3 )
    {
      v11 = ((char *)Source - *v10) >> 1;
      v12 = *((unsigned int *)*v10 - 4);
      if ( (int)((*((_DWORD *)*v10 - 3) - v3) | (1 - *((_DWORD *)*v10 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v10);
      v13 = *v10;
      v14 = 2LL * (int)v3;
      if ( v11 <= v12 )
        memmove_s(v13, v14, &v13[2 * v11], v14);
      else
        memcpy_s(v13, v14, Source, v14);
      ATL::CSimpleStringT<unsigned short,0>::SetLength(v10, (unsigned int)v3);
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 96);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      if ( (((*(_DWORD *)(*((_QWORD *)this + 11) - 12LL) - 2 * cchName[0])
           | (1 - *(_DWORD *)(*((_QWORD *)this + 11) - 8LL)))
          & 0x80000000) != 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((char *)this + 88);
      v15 = (LPWSTR *)((char *)this + 96);
      v16 = (WCHAR *)*((_QWORD *)this + 11);
      if ( (((*(_DWORD *)(*((_QWORD *)this + 12) - 12LL) - 2 * cchReferencedDomainName)
           | (1 - *(_DWORD *)(*((_QWORD *)this + 12) - 8LL)))
          & 0x80000000) != 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v15);
      if ( !LookupAccountSidW(
              *((LPCWSTR *)this + 14),
              (char *)this + 8,
              v16,
              cchName,
              *v15,
              &cchReferencedDomainName,
              peUse) )
        ATL::AtlThrowLastWin32();
      ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer((char *)this + 88);
      ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v15);
    }
    else if ( LastError == 1332 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 88);
      ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 96);
      *peUse = SidTypeUnknown;
    }
  }
}

```

## disassembly

```asm
0x1800228a0  push    rbp
0x1800228a2  push    rbx
0x1800228a3  push    rsi
0x1800228a4  push    rdi
0x1800228a5  push    r12
0x1800228a7  push    r13
0x1800228a9  push    r14
0x1800228ab  push    r15
0x1800228ad  lea     rbp, [rsp-1Fh]
0x1800228b2  sub     rsp, 0E8h
0x1800228b9  mov     rax, cs:__security_cookie
0x1800228c0  xor     rax, rsp
0x1800228c3  mov     [rbp+57h+var_50], rax
0x1800228c7  mov     eax, 20h ; ' '
0x1800228cc  lea     r15, [rcx+50h]
0x1800228d0  mov     [rsp+120h+cchName], eax
0x1800228d4  lea     rdx, [rcx+8]; Sid
0x1800228d8  mov     [rsp+120h+var_E0], eax
0x1800228dc  lea     r9, [rsp+120h+cchName]; cchName
0x1800228e1  lea     rax, [rsp+120h+var_E0]
0x1800228e6  mov     [rsp+120h+peUse], r15; peUse
0x1800228eb  mov     [rsp+120h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800228f0  lea     r8, [rbp+57h+Name]; Name
0x1800228f4  lea     rax, [rbp+57h+Source]
0x1800228f8  mov     r14, rcx
0x1800228fb  mov     rcx, [rcx+70h]; lpSystemName
0x1800228ff  mov     [rsp+120h+ReferencedDomainName], rax; ReferencedDomainName
0x180022904  call    cs:__imp_LookupAccountSidW
0x18002290a  xor     r12d, r12d
0x18002290d  test    eax, eax
0x18002290f  jz      loc_180022AE2
0x180022915  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022919  lea     r15, [r14+58h]
0x18002291d  mov     rdi, rbx
0x180022920  lea     rax, [rbp+57h+Name]
0x180022924  inc     rdi
0x180022927  cmp     [rax+rdi*2], r12w
0x18002292c  jnz     short loc_180022924
0x18002292e  mov     esi, 1
0x180022933  test    edi, edi
0x180022935  jz      loc_180022A0A
0x18002293b  mov     rax, [r15]
0x18002293e  lea     r12, [rbp+57h+Name]
0x180022942  sub     r12, rax
0x180022945  mov     ecx, esi
0x180022947  sar     r12, 1
0x18002294a  sub     ecx, [rax-8]
0x18002294d  mov     r13d, [rax-10h]
0x180022951  mov     eax, [rax-0Ch]
0x180022954  sub     eax, edi
0x180022956  or      ecx, eax
0x180022958  jl      loc_180022AA6
0x18002295e  mov     rcx, [r15]; Destination
0x180022961  movsxd  rdx, edi
0x180022964  add     rdx, rdx; DestinationSize
0x180022967  mov     r9, rdx; SourceSize
0x18002296a  cmp     r12, r13
0x18002296d  jbe     loc_180022AB5
0x180022973  lea     r8, [rbp+57h+Name]; Source
0x180022977  call    cs:__imp_memcpy_s
0x18002297d  mov     edx, edi
0x18002297f  mov     rcx, r15
0x180022982  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180022987  xor     r12d, r12d
0x18002298a  lea     rdi, [r14+60h]
0x18002298e  lea     rax, [rbp+57h+Source]
0x180022992  inc     rbx
0x180022995  cmp     [rax+rbx*2], r12w
0x18002299a  jnz     short loc_180022992
0x18002299c  test    ebx, ebx
0x18002299e  jz      short loc_180022A17
0x1800229a0  mov     rax, [rdi]
0x1800229a3  lea     r14, [rbp+57h+Source]
0x1800229a7  sub     r14, rax
0x1800229aa  sar     r14, 1
0x1800229ad  sub     esi, [rax-8]
0x1800229b0  mov     r15d, [rax-10h]
0x1800229b4  mov     eax, [rax-0Ch]
0x1800229b7  sub     eax, ebx
0x1800229b9  or      esi, eax
0x1800229bb  jl      loc_180022AC4
0x1800229c1  mov     rcx, [rdi]; Destination
0x1800229c4  movsxd  rdx, ebx
0x1800229c7  add     rdx, rdx; DestinationSize
0x1800229ca  mov     r9, rdx; SourceSize
0x1800229cd  cmp     r14, r15
0x1800229d0  jbe     loc_180022AD3
0x1800229d6  lea     r8, [rbp+57h+Source]; Source
0x1800229da  call    cs:__imp_memcpy_s
0x1800229e0  mov     edx, ebx
0x1800229e2  mov     rcx, rdi
0x1800229e5  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800229ea  mov     rcx, [rbp+57h+var_50]
0x1800229ee  xor     rcx, rsp; StackCookie
0x1800229f1  call    __security_check_cookie
0x1800229f6  add     rsp, 0E8h
0x1800229fd  pop     r15
0x1800229ff  pop     r14
0x180022a01  pop     r13
0x180022a03  pop     r12
0x180022a05  pop     rdi
0x180022a06  pop     rsi
0x180022a07  pop     rbx
0x180022a08  pop     rbp
0x180022a09  retn
0x180022a0a  mov     rcx, r15
0x180022a0d  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022a12  jmp     loc_18002298A
0x180022a17  mov     rcx, rdi
0x180022a1a  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022a1f  jmp     short loc_1800229EA
0x180022a21  mov     eax, [rsp+120h+cchName]
0x180022a25  lea     rbx, [r14+58h]
0x180022a29  mov     esi, 1
0x180022a2e  mov     ecx, esi
0x180022a30  lea     edx, [rax+rax]
0x180022a33  mov     rax, [rbx]
0x180022a36  sub     ecx, [rax-8]
0x180022a39  mov     eax, [rax-0Ch]
0x180022a3c  sub     eax, edx
0x180022a3e  or      ecx, eax
0x180022a40  jl      loc_180022B1A
0x180022a46  mov     eax, [rsp+120h+var_E0]
0x180022a4a  lea     rdi, [r14+60h]
0x180022a4e  mov     r12, [rbx]
0x180022a51  lea     edx, [rax+rax]
0x180022a54  mov     rax, [rdi]
0x180022a57  mov     ecx, [rax-0Ch]
0x180022a5a  sub     esi, [rax-8]
0x180022a5d  sub     ecx, edx
0x180022a5f  or      esi, ecx
0x180022a61  jge     short loc_180022A6B
0x180022a63  mov     rcx, rdi
0x180022a66  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180022a6b  mov     rcx, [r14+70h]; lpSystemName
0x180022a6f  lea     rax, [rsp+120h+var_E0]
0x180022a74  mov     [rsp+120h+peUse], r15; peUse
0x180022a79  lea     r9, [rsp+120h+cchName]; cchName
0x180022a7e  mov     [rsp+120h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180022a83  lea     rdx, [r14+8]; Sid
0x180022a87  mov     rax, [rdi]
0x180022a8a  mov     r8, r12; Name
0x180022a8d  mov     [rsp+120h+ReferencedDomainName], rax; ReferencedDomainName
0x180022a92  call    cs:__imp_LookupAccountSidW
0x180022a98  test    eax, eax
0x180022a9a  jnz     loc_180022B27
0x180022aa0  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180022aa6  mov     edx, edi
0x180022aa8  mov     rcx, r15
0x180022aab  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180022ab0  jmp     loc_18002295E
0x180022ab5  lea     r8, [rcx+r12*2]; Source
0x180022ab9  call    cs:__imp_memmove_s
0x180022abf  jmp     loc_18002297D
0x180022ac4  mov     edx, ebx
0x180022ac6  mov     rcx, rdi
0x180022ac9  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180022ace  jmp     loc_1800229C1
0x180022ad3  lea     r8, [rcx+r14*2]; Source
0x180022ad7  call    cs:__imp_memmove_s
0x180022add  jmp     loc_1800229E0
0x180022ae2  call    cs:__imp_GetLastError
0x180022ae8  cmp     eax, 7Ah ; 'z'
0x180022aeb  jz      loc_180022A21
0x180022af1  cmp     eax, 534h
0x180022af6  jnz     loc_1800229EA
0x180022afc  lea     rcx, [r14+58h]
0x180022b00  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022b05  lea     rcx, [r14+60h]
0x180022b09  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180022b0e  mov     dword ptr [r15], 8
0x180022b15  jmp     loc_1800229EA
0x180022b1a  mov     rcx, rbx
0x180022b1d  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180022b22  jmp     loc_180022A46
0x180022b27  mov     rcx, rbx
0x180022b2a  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180022b2f  mov     rcx, rdi
0x180022b32  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180022b37  jmp     loc_1800229EA
```
