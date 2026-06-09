# CUtils::GetRealmParameters(void)

- ea: `0x180047458`
- end: `0x180047562`
- name: `?GetRealmParameters@CUtils@@AEAAXXZ`
- size: `266`
- prototype: `void __fastcall(CUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180001220`

## callees

- `0x180026a40`
- `0x180029c20`
- `0x180047458`
- `0x180047568`
- `0x180055030`

## string_xrefs

- `0x180047481`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Policy`

## pseudocode

```c
void __fastcall CUtils::GetRealmParameters(CUtils *this)
{
  unsigned int v1; // [rsp+20h] [rbp-29h] BYREF
  _QWORD v2[3]; // [rsp+28h] [rbp-21h] BYREF
  unsigned __int16 v3[8]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v4[22]; // [rsp+50h] [rbp+7h]
  unsigned __int16 v5[8]; // [rsp+68h] [rbp+1Fh] BYREF
  __int128 v6; // [rsp+78h] [rbp+2Fh]
  __int128 v7; // [rsp+88h] [rbp+3Fh]

  *(_OWORD *)v5 = *(_OWORD *)L"User Identity Attribute";
  memset(v2, 0, sizeof(v2));
  v6 = *(_OWORD *)L"ntity Attribute";
  v7 = *(_OWORD *)L"tribute";
  *(_OWORD *)v3 = *(_OWORD *)L"Override User-Name";
  *(_OWORD *)v4 = *(_OWORD *)L" User-Name";
  *(_QWORD *)&v4[14] = *(_QWORD *)L"ame";
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)v2,
                        HKEY_LOCAL_MACHINE,
                        L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
                        0x20019u) )
  {
    if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v2, v5, &qword_1800784D0) )
      dword_1800784CC = 1;
    v1 = 0;
    if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v2, v3, &v1) )
      CUtils::_instance = v1 != 0;
    ATL::CRegKey::Close((ATL::CRegKey *)v2);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v2);
}

```

## disassembly

```asm
0x180047458  push    rbp
0x18004745a  lea     rbp, [rsp-57h]
0x18004745f  sub     rsp, 0A0h
0x180047466  mov     rax, cs:__security_cookie
0x18004746d  xor     rax, rsp
0x180047470  mov     [rbp+57h+var_8], rax
0x180047474  movups  xmm0, xmmword ptr cs:aUserIdentityAt; "User Identity Attribute"
0x18004747b  mov     r9d, 20019h; unsigned int
0x180047481  lea     r8, ?IAS_KEY@CUtils@@0QBGB; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180047488  movups  xmm1, xmmword ptr cs:aUserIdentityAt+10h; "ntity Attribute"
0x18004748f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180047496  lea     rcx, [rbp+57h+var_78]; this
0x18004749a  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x18004749e  mov     [rbp+57h+var_78], 0
0x1800474a6  movups  xmm0, xmmword ptr cs:aUserIdentityAt+20h; "tribute"
0x1800474ad  mov     [rbp+57h+var_70], 0
0x1800474b5  movups  [rbp+57h+var_28], xmm1
0x1800474b9  mov     [rbp+57h+var_68], 0
0x1800474c1  movups  xmm1, xmmword ptr cs:aOverrideUserNa; "Override User-Name"
0x1800474c8  movups  [rbp+57h+var_18], xmm0
0x1800474cc  movups  xmm0, xmmword ptr cs:aOverrideUserNa+10h; " User-Name"
0x1800474d3  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x1800474d7  movsd   xmm1, qword ptr cs:aOverrideUserNa+1Eh; "ame"
0x1800474df  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800474e3  movsd   qword ptr [rbp+57h+var_50+0Eh], xmm1
0x1800474e8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800474ed  test    eax, eax
0x1800474ef  jnz     short loc_180047544
0x1800474f1  lea     r8, qword_1800784D0; unsigned int *
0x1800474f8  lea     rdx, [rbp+57h+var_38]; unsigned __int16 *
0x1800474fc  lea     rcx, [rbp+57h+var_78]; this
0x180047500  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180047505  test    eax, eax
0x180047507  jnz     short loc_180047513
0x180047509  mov     cs:dword_1800784CC, 1
0x180047513  lea     r8, [rbp+57h+var_80]; unsigned int *
0x180047517  mov     [rbp+57h+var_80], 0
0x18004751e  lea     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180047522  lea     rcx, [rbp+57h+var_78]; this
0x180047526  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18004752b  test    eax, eax
0x18004752d  jnz     short loc_18004753B
0x18004752f  cmp     [rbp+57h+var_80], eax
0x180047532  setnz   al
0x180047535  mov     cs:?_instance@CUtils@@0V1@A, eax; CUtils CUtils::_instance
0x18004753b  lea     rcx, [rbp+57h+var_78]; this
0x18004753f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180047544  lea     rcx, [rbp+57h+var_78]; this
0x180047548  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004754d  mov     rcx, [rbp+57h+var_8]
0x180047551  xor     rcx, rsp; StackCookie
0x180047554  call    __security_check_cookie
0x180047559  add     rsp, 0A0h
0x180047560  pop     rbp
0x180047561  retn
```
