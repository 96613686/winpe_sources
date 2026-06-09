# RegistryPaths::Initialize(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *)

- ea: `0x14002f284`
- end: `0x14002f37e`
- name: `?Initialize@RegistryPaths@@QEAAKPEAUHKEY__@@PEB_W01@Z`
- size: `250`
- prototype: `unsigned int __fastcall(RegistryPaths *__hidden this, HKEY, const wchar_t *, HKEY, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002a6d4`

## callees

- `0x140003700`
- `0x140006cd0`
- `0x14000d6e8`
- `0x140022cec`
- `0x14002f284`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002f328`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002f328`

## pseudocode

```c
__int64 __fastcall RegistryPaths::Initialize(RegistryPaths *this, HKEY a2, const wchar_t *a3, __int64 a4)
{
  hKey = a2;
  qword_140042240 = a4;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                          &qword_1400421D0,
                          L"Software")
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                          &qword_1400421F0,
                          L"System")
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                          qword_140042210,
                          qword_1400421D0,
                          (qword_1400421D8 - qword_1400421D0) >> 1)
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          qword_140042210,
                          L"\\Microsoft\\Windows\\CurrentVersion\\WINEVT",
                          40) )
  {
    byte_140042230 = CompareStringOrdinal(L"System", -1, L"System", 6, 1) != 2;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ae15e7b640843c37a4c21db51df2f09e_Traceguids, 14);
    }
    return 14;
  }
}

```

## disassembly

```asm
0x14002f284  sub     rsp, 38h
0x14002f288  mov     cs:hKey, rdx
0x14002f28f  lea     rcx, qword_1400421D0
0x14002f296  lea     rdx, aSoftware; "Software"
0x14002f29d  mov     cs:qword_140042240, r9
0x14002f2a4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x14002f2a9  test    al, al
0x14002f2ab  jz      loc_14002F33C
0x14002f2b1  lea     rdx, aSystem; "System"
0x14002f2b8  lea     rcx, qword_1400421F0
0x14002f2bf  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x14002f2c4  test    al, al
0x14002f2c6  jz      short loc_14002F33C
0x14002f2c8  mov     rdx, cs:qword_1400421D0
0x14002f2cf  lea     rcx, qword_140042210
0x14002f2d6  mov     r8, cs:qword_1400421D8
0x14002f2dd  sub     r8, rdx
0x14002f2e0  sar     r8, 1
0x14002f2e3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14002f2e8  test    al, al
0x14002f2ea  jz      short loc_14002F33C
0x14002f2ec  mov     r8d, 28h ; '('
0x14002f2f2  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\CurrentVersion\\W"...
0x14002f2f9  lea     rcx, qword_140042210
0x14002f300  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002f305  test    al, al
0x14002f307  jz      short loc_14002F33C
0x14002f309  mov     r9d, 6; cchCount2
0x14002f30f  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x14002f317  lea     r8, aSystem; "System"
0x14002f31e  or      edx, 0FFFFFFFFh; cchCount1
0x14002f321  lea     rcx, aSystem; "System"
0x14002f328  call    cs:__imp_CompareStringOrdinal
0x14002f32e  cmp     eax, 2
0x14002f331  setnz   cs:byte_140042230
0x14002f338  xor     eax, eax
0x14002f33a  jmp     short loc_14002F379
0x14002f33c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f343  lea     rax, WPP_GLOBAL_Control
0x14002f34a  cmp     rcx, rax
0x14002f34d  jz      short loc_14002F374
0x14002f34f  test    byte ptr [rcx+1Ch], 4
0x14002f353  jz      short loc_14002F374
0x14002f355  cmp     byte ptr [rcx+19h], 2
0x14002f359  jb      short loc_14002F374
0x14002f35b  mov     rcx, [rcx+10h]
0x14002f35f  lea     r8, WPP_ae15e7b640843c37a4c21db51df2f09e_Traceguids
0x14002f366  mov     edx, 0Ah
0x14002f36b  lea     r9d, [rdx+4]
0x14002f36f  call    WPP_SF_d
0x14002f374  mov     eax, 0Eh
0x14002f379  add     rsp, 38h
0x14002f37d  retn
```
