# ATL::CSid::GetAccountNameAndDomain(void)

- ea: `0x1800244e4`
- end: `0x1800247ab`
- name: `?GetAccountNameAndDomain@CSid@ATL@@AEBAXXZ`
- size: `711`
- prototype: `void __fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fa5c`

## callees

- `0x180024460`
- `0x1800244e4`
- `0x180024e18`
- `0x1800253fc`
- `0x18003c614`
- `0x18004e6d4`
- `0x180052640`

## import_xrefs

- `msvcrt!memmove_s` at `0x180024716`
- `msvcrt!memmove_s` at `0x18002473a`
- `msvcrt!memmove_s` at `0x180024716`
- `msvcrt!memmove_s` at `0x18002473a`
- `msvcrt!memcpy_s` at `0x1800245c1`
- `msvcrt!memcpy_s` at `0x18002462a`
- `msvcrt!memcpy_s` at `0x1800245c1`
- `msvcrt!memcpy_s` at `0x18002462a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002474b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002474b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180024548`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800246e9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180024548`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800246e9`

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
0x1800244e4  push    rbp
0x1800244e6  push    rbx
0x1800244e7  push    rsi
0x1800244e8  push    rdi
0x1800244e9  push    r12
0x1800244eb  push    r13
0x1800244ed  push    r14
0x1800244ef  push    r15
0x1800244f1  lea     rbp, [rsp-1Fh]
0x1800244f6  sub     rsp, 0E8h
0x1800244fd  mov     rax, cs:__security_cookie
0x180024504  xor     rax, rsp
0x180024507  mov     [rbp+57h+var_50], rax
0x18002450b  mov     eax, 20h ; ' '
0x180024510  lea     r15, [rcx+50h]
0x180024514  mov     [rsp+120h+cchName], eax
0x180024518  lea     rdx, [rcx+8]; Sid
0x18002451c  mov     [rsp+120h+var_E0], eax
0x180024520  lea     r9, [rsp+120h+cchName]; cchName
0x180024525  lea     rax, [rsp+120h+var_E0]
0x18002452a  mov     [rsp+120h+peUse], r15; peUse
0x18002452f  mov     [rsp+120h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180024534  lea     r8, [rbp+57h+Name]; Name
0x180024538  lea     rax, [rbp+57h+Source]
0x18002453c  mov     r14, rcx
0x18002453f  mov     rcx, [rcx+70h]; lpSystemName
0x180024543  mov     [rsp+120h+ReferencedDomainName], rax; ReferencedDomainName
0x180024548  call    cs:__imp_LookupAccountSidW
0x18002454f  nop     dword ptr [rax+rax+00h]
0x180024554  xor     r12d, r12d
0x180024557  test    eax, eax
0x180024559  jz      loc_18002474B
0x18002455f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180024563  lea     r15, [r14+58h]
0x180024567  mov     rdi, rbx
0x18002456a  lea     rax, [rbp+57h+Name]
0x18002456e  inc     rdi
0x180024571  cmp     [rax+rdi*2], r12w
0x180024576  jnz     short loc_18002456E
0x180024578  mov     esi, 1
0x18002457d  test    edi, edi
0x18002457f  jz      loc_180024661
0x180024585  mov     rax, [r15]
0x180024588  lea     r12, [rbp+57h+Name]
0x18002458c  sub     r12, rax
0x18002458f  mov     ecx, esi
0x180024591  sar     r12, 1
0x180024594  sub     ecx, [rax-8]
0x180024597  mov     r13d, [rax-10h]
0x18002459b  mov     eax, [rax-0Ch]
0x18002459e  sub     eax, edi
0x1800245a0  or      ecx, eax
0x1800245a2  jl      loc_180024703
0x1800245a8  mov     rcx, [r15]; Destination
0x1800245ab  movsxd  rdx, edi
0x1800245ae  add     rdx, rdx; DestinationSize
0x1800245b1  mov     r9, rdx; SourceSize
0x1800245b4  cmp     r12, r13
0x1800245b7  jbe     loc_180024712
0x1800245bd  lea     r8, [rbp+57h+Name]; Source
0x1800245c1  call    cs:__imp_memcpy_s
0x1800245c8  nop     dword ptr [rax+rax+00h]
0x1800245cd  mov     edx, edi
0x1800245cf  mov     rcx, r15
0x1800245d2  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800245d7  xor     r12d, r12d
0x1800245da  lea     rdi, [r14+60h]
0x1800245de  lea     rax, [rbp+57h+Source]
0x1800245e2  inc     rbx
0x1800245e5  cmp     [rax+rbx*2], r12w
0x1800245ea  jnz     short loc_1800245E2
0x1800245ec  test    ebx, ebx
0x1800245ee  jz      short loc_18002466E
0x1800245f0  mov     rax, [rdi]
0x1800245f3  lea     r14, [rbp+57h+Source]
0x1800245f7  sub     r14, rax
0x1800245fa  sar     r14, 1
0x1800245fd  sub     esi, [rax-8]
0x180024600  mov     r15d, [rax-10h]
0x180024604  mov     eax, [rax-0Ch]
0x180024607  sub     eax, ebx
0x180024609  or      esi, eax
0x18002460b  jl      loc_180024727
0x180024611  mov     rcx, [rdi]; Destination
0x180024614  movsxd  rdx, ebx
0x180024617  add     rdx, rdx; DestinationSize
0x18002461a  mov     r9, rdx; SourceSize
0x18002461d  cmp     r14, r15
0x180024620  jbe     loc_180024736
0x180024626  lea     r8, [rbp+57h+Source]; Source
0x18002462a  call    cs:__imp_memcpy_s
0x180024631  nop     dword ptr [rax+rax+00h]
0x180024636  mov     edx, ebx
0x180024638  mov     rcx, rdi
0x18002463b  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180024640  mov     rcx, [rbp+57h+var_50]
0x180024644  xor     rcx, rsp; StackCookie
0x180024647  call    __security_check_cookie
0x18002464c  add     rsp, 0E8h
0x180024653  pop     r15
0x180024655  pop     r14
0x180024657  pop     r13
0x180024659  pop     r12
0x18002465b  pop     rdi
0x18002465c  pop     rsi
0x18002465d  pop     rbx
0x18002465e  pop     rbp
0x18002465f  retn
0x180024661  mov     rcx, r15
0x180024664  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024669  jmp     loc_1800245DA
0x18002466e  mov     rcx, rdi
0x180024671  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024676  jmp     short loc_180024640
0x180024678  mov     eax, [rsp+120h+cchName]
0x18002467c  lea     rbx, [r14+58h]
0x180024680  mov     esi, 1
0x180024685  mov     ecx, esi
0x180024687  lea     edx, [rax+rax]
0x18002468a  mov     rax, [rbx]
0x18002468d  sub     ecx, [rax-8]
0x180024690  mov     eax, [rax-0Ch]
0x180024693  sub     eax, edx
0x180024695  or      ecx, eax
0x180024697  jl      loc_180024789
0x18002469d  mov     eax, [rsp+120h+var_E0]
0x1800246a1  lea     rdi, [r14+60h]
0x1800246a5  mov     r12, [rbx]
0x1800246a8  lea     edx, [rax+rax]
0x1800246ab  mov     rax, [rdi]
0x1800246ae  mov     ecx, [rax-0Ch]
0x1800246b1  sub     esi, [rax-8]
0x1800246b4  sub     ecx, edx
0x1800246b6  or      esi, ecx
0x1800246b8  jge     short loc_1800246C2
0x1800246ba  mov     rcx, rdi
0x1800246bd  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800246c2  mov     rcx, [r14+70h]; lpSystemName
0x1800246c6  lea     rax, [rsp+120h+var_E0]
0x1800246cb  mov     [rsp+120h+peUse], r15; peUse
0x1800246d0  lea     r9, [rsp+120h+cchName]; cchName
0x1800246d5  mov     [rsp+120h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800246da  lea     rdx, [r14+8]; Sid
0x1800246de  mov     rax, [rdi]
0x1800246e1  mov     r8, r12; Name
0x1800246e4  mov     [rsp+120h+ReferencedDomainName], rax; ReferencedDomainName
0x1800246e9  call    cs:__imp_LookupAccountSidW
0x1800246f0  nop     dword ptr [rax+rax+00h]
0x1800246f5  test    eax, eax
0x1800246f7  jnz     loc_180024796
0x1800246fd  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180024703  mov     edx, edi
0x180024705  mov     rcx, r15
0x180024708  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002470d  jmp     loc_1800245A8
0x180024712  lea     r8, [rcx+r12*2]; Source
0x180024716  call    cs:__imp_memmove_s
0x18002471d  nop     dword ptr [rax+rax+00h]
0x180024722  jmp     loc_1800245CD
0x180024727  mov     edx, ebx
0x180024729  mov     rcx, rdi
0x18002472c  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180024731  jmp     loc_180024611
0x180024736  lea     r8, [rcx+r14*2]; Source
0x18002473a  call    cs:__imp_memmove_s
0x180024741  nop     dword ptr [rax+rax+00h]
0x180024746  jmp     loc_180024636
0x18002474b  call    cs:__imp_GetLastError
0x180024752  nop     dword ptr [rax+rax+00h]
0x180024757  cmp     eax, 7Ah ; 'z'
0x18002475a  jz      loc_180024678
0x180024760  cmp     eax, 534h
0x180024765  jnz     loc_180024640
0x18002476b  lea     rcx, [r14+58h]
0x18002476f  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180024774  lea     rcx, [r14+60h]
0x180024778  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18002477d  mov     dword ptr [r15], 8
0x180024784  jmp     loc_180024640
0x180024789  mov     rcx, rbx
0x18002478c  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180024791  jmp     loc_18002469D
0x180024796  mov     rcx, rbx
0x180024799  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002479e  mov     rcx, rdi
0x1800247a1  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x1800247a6  jmp     loc_180024640
```
