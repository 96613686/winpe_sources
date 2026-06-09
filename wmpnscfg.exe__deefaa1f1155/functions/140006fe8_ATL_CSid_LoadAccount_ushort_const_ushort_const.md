# ATL::CSid::LoadAccount(ushort const *,ushort const *)

- ea: `0x140006fe8`
- end: `0x14000721d`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBG0@Z`
- size: `565`
- prototype: `bool(ATL::CSid *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140006d7c`

## callees

- `0x1400014f0`
- `0x140002e98`
- `0x140003004`
- `0x14000326c`
- `0x14000339c`
- `0x14000491c`
- `0x140006fe8`
- `0x140007258`

## import_xrefs

- `ADVAPI32!CopySid` at `0x140007132`
- `ADVAPI32!CopySid` at `0x140007132`
- `ADVAPI32!LookupAccountNameW` at `0x1400070ae`
- `ADVAPI32!LookupAccountNameW` at `0x140007114`
- `ADVAPI32!LookupAccountNameW` at `0x1400070ae`
- `ADVAPI32!LookupAccountNameW` at `0x140007114`
- `KERNEL32!GetLastError` at `0x1400070b8`
- `KERNEL32!GetLastError` at `0x1400070b8`

## pseudocode

```c
char __fastcall ATL::CSid::LoadAccount(ATL::CSid *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  enum _SID_NAME_USE *peUse; // r14
  char *v5; // r13
  char *v7; // r15
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  WCHAR *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // r8
  DWORD v17; // ecx
  __int64 v18; // rbx
  __int64 v19; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-BCh] BYREF
  char *v29; // [rsp+48h] [rbp-B8h]
  LPWSTR ReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[136]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE Sid[80]; // [rsp+E0h] [rbp-20h] BYREF

  peUse = (enum _SID_NAME_USE *)((char *)this + 80);
  v5 = (char *)this + 88;
  *((_DWORD *)this + 20) = 7;
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 88, a2, a3);
  v7 = (char *)this + 96;
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 96, v8, v9);
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 104, v10, v11);
  v29 = (char *)this + 112;
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 112, v12, v13);
  *((_BYTE *)this + 76) = 0;
  if ( !a2 )
    return 0;
  ReferencedDomainName = 0;
  ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateHeap(&ReferencedDomainName, 256);
  v14 = ReferencedDomainName;
  cbSid = 68;
  cchReferencedDomainName = 128;
  if ( !LookupAccountNameW(0, a2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, peUse) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_18;
    if ( cbSid > 0x44 )
      ATL::AtlThrowImpl(-2147467259);
    if ( cchReferencedDomainName > 0x80 )
    {
      ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::Reallocate(
        &ReferencedDomainName,
        2LL * cchReferencedDomainName);
      v14 = ReferencedDomainName;
    }
    if ( !LookupAccountNameW(0, a2, Sid, &cbSid, v14, &cchReferencedDomainName, peUse) )
      goto LABEL_18;
  }
  v17 = cbSid;
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(v17, (char *)this + 8, Sid) )
  {
LABEL_18:
    *peUse = SidTypeInvalid;
    ATL::CSimpleStringT<unsigned short,0>::Empty(v5, v15, v16);
    ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 96, v21, v22);
    ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 104, v23, v24);
    ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 112, v25, v26);
    *((_BYTE *)this + 76) = 0;
    if ( ReferencedDomainName != (LPWSTR)v31 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&ReferencedDomainName);
    return 0;
  }
  v18 = -1;
  if ( v14 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v14[v19] );
  }
  else
  {
    v19 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(v7, v14, v19);
  do
    ++v18;
  while ( a2[v18] );
  ATL::CSimpleStringT<unsigned short,0>::SetString(v5, a2, (unsigned int)v18);
  ATL::CSimpleStringT<unsigned short,0>::SetString(v29, 0, 0);
  if ( ReferencedDomainName != (LPWSTR)v31 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&ReferencedDomainName);
  return 1;
}

```

## disassembly

```asm
0x140006fe8  mov     [rsp-8+arg_10], rbx
0x140006fed  push    rbp
0x140006fee  push    rsi
0x140006fef  push    rdi
0x140006ff0  push    r12
0x140006ff2  push    r13
0x140006ff4  push    r14
0x140006ff6  push    r15
0x140006ff8  lea     rbp, [rsp-40h]
0x140006ffd  sub     rsp, 140h
0x140007004  mov     rax, cs:__security_cookie
0x14000700b  xor     rax, rsp
0x14000700e  mov     [rbp+70h+var_40], rax
0x140007012  lea     r14, [rcx+50h]
0x140007016  mov     rbx, rcx
0x140007019  lea     r13, [rcx+58h]
0x14000701d  mov     dword ptr [r14], 7
0x140007024  mov     rcx, r13
0x140007027  mov     rsi, rdx
0x14000702a  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14000702f  lea     r15, [rbx+60h]
0x140007033  mov     rcx, r15
0x140007036  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14000703b  lea     rcx, [rbx+68h]
0x14000703f  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140007044  lea     rax, [rbx+70h]
0x140007048  mov     rcx, rax
0x14000704b  mov     [rsp+170h+var_128], rax
0x140007050  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140007055  xor     eax, eax
0x140007057  mov     [rbx+4Ch], al
0x14000705a  test    rsi, rsi
0x14000705d  jz      loc_1400071E9
0x140007063  mov     edx, 100h
0x140007068  mov     [rsp+170h+var_120], rax
0x14000706d  lea     rcx, [rsp+170h+var_120]
0x140007072  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140007077  mov     rdi, [rsp+170h+var_120]
0x14000707c  lea     rax, [rsp+170h+var_130]
0x140007081  mov     [rsp+170h+peUse], r14; peUse
0x140007086  lea     r9, [rsp+170h+cbSid]; cbSid
0x14000708b  mov     [rsp+170h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140007090  lea     r8, [rbp+70h+Sid]; Sid
0x140007094  mov     rdx, rsi; lpAccountName
0x140007097  mov     [rsp+170h+ReferencedDomainName], rdi; ReferencedDomainName
0x14000709c  xor     ecx, ecx; lpSystemName
0x14000709e  mov     [rsp+170h+cbSid], 44h ; 'D'
0x1400070a6  mov     [rsp+170h+var_130], 80h
0x1400070ae  call    cs:__imp_LookupAccountNameW
0x1400070b4  test    eax, eax
0x1400070b6  jnz     short loc_140007122
0x1400070b8  call    cs:__imp_GetLastError
0x1400070be  cmp     eax, 7Ah ; 'z'
0x1400070c1  jnz     loc_1400071A6
0x1400070c7  cmp     [rsp+170h+cbSid], 44h ; 'D'
0x1400070cc  ja      loc_140007212
0x1400070d2  cmp     [rsp+170h+var_130], 80h
0x1400070da  jbe     short loc_1400070F2
0x1400070dc  mov     edx, [rsp+170h+var_130]
0x1400070e0  lea     rcx, [rsp+170h+var_120]
0x1400070e5  add     rdx, rdx
0x1400070e8  call    ?Reallocate@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@QEAAPEAG_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::Reallocate(unsigned __int64)
0x1400070ed  mov     rdi, [rsp+170h+var_120]
0x1400070f2  lea     rax, [rsp+170h+var_130]
0x1400070f7  mov     [rsp+170h+peUse], r14; peUse
0x1400070fc  mov     [rsp+170h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140007101  lea     r9, [rsp+170h+cbSid]; cbSid
0x140007106  lea     r8, [rbp+70h+Sid]; Sid
0x14000710a  mov     [rsp+170h+ReferencedDomainName], rdi; ReferencedDomainName
0x14000710f  mov     rdx, rsi; lpAccountName
0x140007112  xor     ecx, ecx; lpSystemName
0x140007114  call    cs:__imp_LookupAccountNameW
0x14000711a  test    eax, eax
0x14000711c  jz      loc_1400071A6
0x140007122  mov     ecx, [rsp+170h+cbSid]; nDestinationSidLength
0x140007126  lea     rdx, [rbx+8]; pDestinationSid
0x14000712a  lea     r8, [rbp+70h+Sid]; pSourceSid
0x14000712e  mov     byte ptr [rbx+4Ch], 1
0x140007132  call    cs:__imp_CopySid
0x140007138  xor     ecx, ecx
0x14000713a  test    eax, eax
0x14000713c  jz      short loc_1400071A6
0x14000713e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140007142  test    rdi, rdi
0x140007145  jnz     short loc_14000714C
0x140007147  mov     r8d, ecx
0x14000714a  jmp     short loc_140007159
0x14000714c  mov     r8, rbx
0x14000714f  inc     r8
0x140007152  cmp     [rdi+r8*2], cx
0x140007157  jnz     short loc_14000714F
0x140007159  mov     rdx, rdi
0x14000715c  mov     rcx, r15
0x14000715f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140007164  xor     eax, eax
0x140007166  inc     rbx
0x140007169  cmp     [rsi+rbx*2], ax
0x14000716d  jnz     short loc_140007166
0x14000716f  mov     r8d, ebx
0x140007172  mov     rdx, rsi
0x140007175  mov     rcx, r13
0x140007178  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000717d  mov     rcx, [rsp+170h+var_128]
0x140007182  xor     r8d, r8d
0x140007185  xor     edx, edx
0x140007187  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000718c  lea     rcx, [rsp+170h+var_118]
0x140007191  cmp     [rsp+170h+var_120], rcx
0x140007196  jz      short loc_1400071A2
0x140007198  lea     rcx, [rsp+170h+var_120]
0x14000719d  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1400071a2  mov     al, 1
0x1400071a4  jmp     short loc_1400071EB
0x1400071a6  mov     rcx, r13
0x1400071a9  mov     dword ptr [r14], 7
0x1400071b0  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400071b5  mov     rcx, r15
0x1400071b8  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400071bd  lea     rcx, [rbx+68h]
0x1400071c1  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400071c6  lea     rcx, [rbx+70h]
0x1400071ca  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400071cf  lea     rax, [rsp+170h+var_118]
0x1400071d4  mov     byte ptr [rbx+4Ch], 0
0x1400071d8  cmp     [rsp+170h+var_120], rax
0x1400071dd  jz      short loc_1400071E9
0x1400071df  lea     rcx, [rsp+170h+var_120]
0x1400071e4  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1400071e9  xor     al, al
0x1400071eb  mov     rcx, [rbp+70h+var_40]
0x1400071ef  xor     rcx, rsp; StackCookie
0x1400071f2  call    __security_check_cookie
0x1400071f7  mov     rbx, [rsp+170h+arg_10]
0x1400071ff  add     rsp, 140h
0x140007206  pop     r15
0x140007208  pop     r14
0x14000720a  pop     r13
0x14000720c  pop     r12
0x14000720e  pop     rdi
0x14000720f  pop     rsi
0x140007210  pop     rbp
0x140007211  retn
0x140007212  mov     ecx, 80004005h; int
0x140007217  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
