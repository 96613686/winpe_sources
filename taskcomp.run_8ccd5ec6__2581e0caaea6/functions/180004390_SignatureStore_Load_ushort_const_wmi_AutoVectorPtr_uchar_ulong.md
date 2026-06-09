# SignatureStore::Load(ushort const *,wmi::AutoVectorPtr<uchar> &,ulong &)

- ea: `0x180004390`
- end: `0x1800047e7`
- name: `?Load@SignatureStore@@SAJPEBGAEAV?$AutoVectorPtr@E@wmi@@AEAK@Z`
- size: `1111`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b218`
- `0x18000d0e8`
- `0x180011080`

## callees

- `0x180003480`
- `0x180003600`
- `0x180004390`
- `0x1800050d0`
- `0x180005150`
- `0x180005224`
- `0x1800068e4`
- `0x180007988`
- `0x180007994`
- `0x18000d128`
- `0x18000d190`
- `0x18000d214`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800044fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000466f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800044fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000466f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000441b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000441b`

## string_xrefs

- `0x18000440d`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\CompatibilityAdapter\Signatures`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SignatureStore::Load(unsigned __int16 *a1, __int64 a2, BYTE *a3)
{
  const WCHAR *v5; // rdi
  LSTATUS v6; // eax
  int v7; // r8d
  signed int v8; // ebx
  BYTE *v9; // rax
  BYTE *v10; // rsi
  LSTATUS v11; // eax
  int v12; // r8d
  BYTE *v13; // rcx
  BYTE *v14; // rcx
  const WCHAR *v15; // rdx
  LSTATUS v16; // eax
  int v17; // r8d
  const WCHAR **v19; // [rsp+58h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-1h] BYREF
  char v21[8]; // [rsp+68h] [rbp+7h] BYREF
  __int64 v22; // [rsp+70h] [rbp+Fh]
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp+17h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+67h] BYREF
  DWORD cbData; // [rsp+E0h] [rbp+7Fh] BYREF

  v5 = a1 + 1;
  if ( *a1 != 92 )
    v5 = a1;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = tsched::StoreSecurity::g_pRestrictedKeySecurity;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  hKey = 0;
  v6 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CompatibilityAdapter\\Signatures",
         0,
         0,
         0,
         0x2001Fu,
         &SecurityAttributes,
         &hKey,
         0);
  v8 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v7, (_DWORD)v5, v6);
    }
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_66;
  }
  Type = 0;
  cbData = 64;
  v9 = (BYTE *)operator new[](0x40u);
  v10 = v9;
  if ( v9 )
  {
    v11 = RegQueryValueExW(hKey, v5, 0, &Type, v9, &cbData);
    v8 = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v12, (_DWORD)v5, v11);
      }
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      v13 = v10;
LABEL_24:
      operator delete(v13);
      goto LABEL_66;
    }
    if ( Type != 3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v12, (_DWORD)v5, Type);
      }
LABEL_35:
      v14 = v10;
LABEL_36:
      operator delete(v14);
      v8 = -2147418113;
      goto LABEL_66;
    }
    if ( cbData != 64 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v12, (_DWORD)v5, 3, cbData);
      }
      goto LABEL_35;
    }
    v22 = 0;
    wmi::AutoVectorPtr<unsigned char>::operator=(a2, v10);
    _bstr_t::_bstr_t((_bstr_t *)&v19, v5);
    _bstr_t::_bstr_t((_bstr_t *)v21, L".fp");
    _bstr_t::operator+=(&v19, v21);
    _bstr_t::~_bstr_t((_bstr_t *)v21);
    Type = 0;
    cbData = 4;
    if ( v19 )
      v15 = *v19;
    else
      v15 = 0;
    v16 = RegQueryValueExW(hKey, v15, 0, &Type, a3, &cbData);
    v8 = v16;
    if ( v16 )
    {
      if ( v16 != 2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v17, (_DWORD)v5, v16);
        }
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        _bstr_t::~_bstr_t((_bstr_t *)&v19);
        v13 = 0;
        goto LABEL_24;
      }
      *(_DWORD *)a3 = 0;
LABEL_65:
      _bstr_t::~_bstr_t((_bstr_t *)&v19);
      operator delete(0);
      v8 = 0;
      goto LABEL_66;
    }
    if ( Type == 4 )
    {
      if ( cbData == 4 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)WPP_18f9f5786677348a014147273dcee318_Traceguids,
            (_DWORD)v5,
            *(_DWORD *)a3);
        }
        goto LABEL_65;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v17, (_DWORD)v5, cbData, 4);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v17, (_DWORD)v5, Type);
    }
    _bstr_t::~_bstr_t((_bstr_t *)&v19);
    v14 = 0;
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_18f9f5786677348a014147273dcee318_Traceguids, v5);
  }
  operator delete(0);
  v8 = -2147024882;
LABEL_66:
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004390  mov     r11, rsp
0x180004393  mov     [r11+10h], rbx
0x180004397  push    rbp
0x180004398  push    rsi
0x180004399  push    rdi
0x18000439a  push    r14
0x18000439c  push    r15
0x18000439e  lea     rbp, [r11-5Fh]
0x1800043a2  sub     rsp, 90h
0x1800043a9  mov     r14, r8
0x1800043ac  mov     r15, rdx
0x1800043af  lea     rdi, [rcx+2]
0x1800043b3  cmp     word ptr [rcx], 5Ch ; '\'
0x1800043b7  cmovnz  rdi, rcx
0x1800043bb  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x1800043c3  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x1800043ca  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800043ce  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x1800043d6  mov     [rbp+57h+hKey], 0
0x1800043de  mov     qword ptr [r11-78h], 0
0x1800043e6  lea     rax, [rbp+57h+hKey]
0x1800043ea  mov     [r11-80h], rax
0x1800043ee  lea     rax, [rbp+57h+SecurityAttributes]
0x1800043f2  mov     [rsp+30h], rax; lpSecurityAttributes
0x1800043f7  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x1800043ff  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x180004407  xor     r9d, r9d; lpClass
0x18000440a  xor     r8d, r8d; Reserved
0x18000440d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180004414  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000441b  call    cs:__imp_RegCreateKeyExW
0x180004422  nop     dword ptr [rax+rax+00h]
0x180004427  mov     ebx, eax
0x180004429  test    eax, eax
0x18000442b  jz      short loc_180004477
0x18000442d  lea     rdx, WPP_GLOBAL_Control
0x180004434  mov     rcx, cs:WPP_GLOBAL_Control
0x18000443b  cmp     rcx, rdx
0x18000443e  jz      short loc_180004461
0x180004440  test    byte ptr [rcx+1Ch], 2
0x180004444  jz      short loc_180004461
0x180004446  cmp     byte ptr [rcx+19h], 2
0x18000444a  jb      short loc_180004461
0x18000444c  mov     edx, 0Ah
0x180004451  mov     [rsp+0B0h+dwOptions], eax
0x180004455  mov     r9, rdi
0x180004458  mov     rcx, [rcx+10h]
0x18000445c  call    WPP_SF_Sd
0x180004461  test    ebx, ebx
0x180004463  jle     loc_1800047C4
0x180004469  movzx   ebx, bx
0x18000446c  or      ebx, 80070000h
0x180004472  jmp     loc_1800047C4
0x180004477  mov     [rbp+57h+Type], 0
0x18000447e  mov     [rbp+57h+cbData], 40h ; '@'
0x180004485  mov     ecx, 40h ; '@'; unsigned __int64
0x18000448a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000448f  mov     rsi, rax
0x180004492  test    rax, rax
0x180004495  jnz     short loc_1800044DE
0x180004497  lea     rdx, WPP_GLOBAL_Control
0x18000449e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044a5  cmp     rcx, rdx
0x1800044a8  jz      short loc_1800044CD
0x1800044aa  test    byte ptr [rcx+1Ch], 2
0x1800044ae  jz      short loc_1800044CD
0x1800044b0  cmp     byte ptr [rcx+19h], 2
0x1800044b4  jb      short loc_1800044CD
0x1800044b6  lea     edx, [rax+0Bh]
0x1800044b9  mov     r9, rdi
0x1800044bc  lea     r8, WPP_18f9f5786677348a014147273dcee318_Traceguids
0x1800044c3  mov     rcx, [rcx+10h]
0x1800044c7  call    WPP_SF_S
0x1800044cc  nop
0x1800044cd  xor     ecx, ecx; Block
0x1800044cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800044d4  mov     ebx, 8007000Eh
0x1800044d9  jmp     loc_1800047C4
0x1800044de  lea     rax, [rbp+57h+cbData]
0x1800044e2  mov     qword ptr [rsp+0B0h+samDesired], rax; lpcbData
0x1800044e7  mov     qword ptr [rsp+0B0h+dwOptions], rsi; lpData
0x1800044ec  lea     r9, [rbp+57h+Type]; lpType
0x1800044f0  xor     r8d, r8d; lpReserved
0x1800044f3  mov     rdx, rdi; lpValueName
0x1800044f6  mov     rcx, [rbp+57h+hKey]; hKey
0x1800044fa  call    cs:__imp_RegQueryValueExW
0x180004501  nop     dword ptr [rax+rax+00h]
0x180004506  mov     ebx, eax
0x180004508  test    eax, eax
0x18000450a  jz      short loc_18000455A
0x18000450c  lea     rdx, WPP_GLOBAL_Control
0x180004513  mov     rcx, cs:WPP_GLOBAL_Control
0x18000451a  cmp     rcx, rdx
0x18000451d  jz      short loc_180004540
0x18000451f  test    byte ptr [rcx+1Ch], 2
0x180004523  jz      short loc_180004540
0x180004525  cmp     byte ptr [rcx+19h], 2
0x180004529  jb      short loc_180004540
0x18000452b  mov     edx, 0Ch
0x180004530  mov     [rsp+0B0h+dwOptions], eax
0x180004534  mov     r9, rdi
0x180004537  mov     rcx, [rcx+10h]
0x18000453b  call    WPP_SF_Sd
0x180004540  test    ebx, ebx
0x180004542  jle     short loc_18000454D
0x180004544  movzx   ebx, bx
0x180004547  or      ebx, 80070000h
0x18000454d  mov     rcx, rsi; Block
0x180004550  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004555  jmp     loc_1800047C4
0x18000455a  mov     eax, [rbp+57h+Type]
0x18000455d  cmp     eax, 3
0x180004560  jz      short loc_180004598
0x180004562  lea     rdx, WPP_GLOBAL_Control
0x180004569  mov     rcx, cs:WPP_GLOBAL_Control
0x180004570  cmp     rcx, rdx
0x180004573  jz      short loc_1800045DD
0x180004575  test    byte ptr [rcx+1Ch], 2
0x180004579  jz      short loc_1800045DD
0x18000457b  cmp     byte ptr [rcx+19h], 2
0x18000457f  jb      short loc_1800045DD
0x180004581  mov     edx, 0Dh
0x180004586  mov     [rsp+0B0h+dwOptions], eax
0x18000458a  mov     r9, rdi
0x18000458d  mov     rcx, [rcx+10h]
0x180004591  call    WPP_SF_Sd
0x180004596  jmp     short loc_1800045DD
0x180004598  mov     eax, [rbp+57h+cbData]
0x18000459b  cmp     eax, 40h ; '@'
0x18000459e  jz      short loc_1800045EF
0x1800045a0  lea     rdx, WPP_GLOBAL_Control
0x1800045a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045ae  cmp     rcx, rdx
0x1800045b1  jz      short loc_1800045DD
0x1800045b3  test    byte ptr [rcx+1Ch], 2
0x1800045b7  jz      short loc_1800045DD
0x1800045b9  cmp     byte ptr [rcx+19h], 2
0x1800045bd  jb      short loc_1800045DD
0x1800045bf  mov     edx, 0Eh
0x1800045c4  mov     [rsp+0B0h+samDesired], eax
0x1800045c8  mov     [rsp+0B0h+dwOptions], 3
0x1800045d0  mov     r9, rdi
0x1800045d3  mov     rcx, [rcx+10h]
0x1800045d7  call    WPP_SF_Sdd
0x1800045dc  nop
0x1800045dd  mov     rcx, rsi; Block
0x1800045e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045e5  mov     ebx, 8000FFFFh
0x1800045ea  jmp     loc_1800047C4
0x1800045ef  mov     [rbp+57h+var_48], 0
0x1800045f7  mov     rdx, rsi
0x1800045fa  mov     rcx, r15
0x1800045fd  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x180004602  mov     rdx, rdi; unsigned __int16 *
0x180004605  lea     rcx, [rbp+57h+var_60]; this
0x180004609  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000460e  nop
0x18000460f  lea     rdx, psz; ".fp"
0x180004616  lea     rcx, [rbp+57h+var_50]; this
0x18000461a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000461f  nop
0x180004620  lea     rdx, [rbp+57h+var_50]
0x180004624  lea     rcx, [rbp+57h+var_60]
0x180004628  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18000462d  nop
0x18000462e  lea     rcx, [rbp+57h+var_50]; this
0x180004632  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004637  mov     [rbp+57h+Type], 0
0x18000463e  mov     esi, 4
0x180004643  mov     [rbp+57h+cbData], esi
0x180004646  mov     rax, [rbp+57h+var_60]
0x18000464a  test    rax, rax
0x18000464d  jz      short loc_180004654
0x18000464f  mov     rdx, [rax]
0x180004652  jmp     short loc_180004656
0x180004654  xor     edx, edx; lpValueName
0x180004656  lea     rax, [rbp+57h+cbData]
0x18000465a  mov     qword ptr [rsp+0B0h+samDesired], rax; lpcbData
0x18000465f  mov     qword ptr [rsp+0B0h+dwOptions], r14; lpData
0x180004664  lea     r9, [rbp+57h+Type]; lpType
0x180004668  xor     r8d, r8d; lpReserved
0x18000466b  mov     rcx, [rbp+57h+hKey]; hKey
0x18000466f  call    cs:__imp_RegQueryValueExW
0x180004676  nop     dword ptr [rax+rax+00h]
0x18000467b  mov     ebx, eax
0x18000467d  test    eax, eax
0x18000467f  jz      short loc_1800046E4
0x180004681  cmp     eax, 2
0x180004684  jnz     short loc_180004692
0x180004686  mov     dword ptr [r14], 0
0x18000468d  jmp     loc_1800047B1
0x180004692  lea     rdx, WPP_GLOBAL_Control
0x180004699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046a0  cmp     rcx, rdx
0x1800046a3  jz      short loc_1800046C6
0x1800046a5  test    byte ptr [rcx+1Ch], 2
0x1800046a9  jz      short loc_1800046C6
0x1800046ab  cmp     byte ptr [rcx+19h], 2
0x1800046af  jb      short loc_1800046C6
0x1800046b1  mov     edx, 0Fh
0x1800046b6  mov     [rsp+0B0h+dwOptions], ebx
0x1800046ba  mov     r9, rdi
0x1800046bd  mov     rcx, [rcx+10h]
0x1800046c1  call    WPP_SF_Sd
0x1800046c6  test    ebx, ebx
0x1800046c8  jle     short loc_1800046D3
0x1800046ca  movzx   ebx, bx
0x1800046cd  or      ebx, 80070000h
0x1800046d3  lea     rcx, [rbp+57h+var_60]; this
0x1800046d7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800046dc  nop
0x1800046dd  xor     ecx, ecx
0x1800046df  jmp     loc_180004550
0x1800046e4  mov     eax, [rbp+57h+Type]
0x1800046e7  cmp     eax, esi
0x1800046e9  jz      short loc_180004721
0x1800046eb  lea     rdx, WPP_GLOBAL_Control
0x1800046f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046f9  cmp     rcx, rdx
0x1800046fc  jz      short loc_180004761
0x1800046fe  test    byte ptr [rcx+1Ch], 2
0x180004702  jz      short loc_180004761
0x180004704  cmp     byte ptr [rcx+19h], 2
0x180004708  jb      short loc_180004761
0x18000470a  mov     edx, 10h
0x18000470f  mov     [rsp+0B0h+dwOptions], eax
0x180004713  mov     r9, rdi
0x180004716  mov     rcx, [rcx+10h]
0x18000471a  call    WPP_SF_Sd
0x18000471f  jmp     short loc_180004761
0x180004721  mov     eax, [rbp+57h+cbData]
0x180004724  cmp     eax, esi
0x180004726  jz      short loc_180004772
0x180004728  lea     rdx, WPP_GLOBAL_Control
0x18000472f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004736  cmp     rcx, rdx
0x180004739  jz      short loc_180004761
0x18000473b  test    byte ptr [rcx+1Ch], 2
0x18000473f  jz      short loc_180004761
0x180004741  cmp     byte ptr [rcx+19h], 2
0x180004745  jb      short loc_180004761
0x180004747  mov     edx, 11h
0x18000474c  mov     [rsp+0B0h+samDesired], esi
0x180004750  mov     [rsp+0B0h+dwOptions], eax
0x180004754  mov     r9, rdi
0x180004757  mov     rcx, [rcx+10h]
0x18000475b  call    WPP_SF_Sdd
0x180004760  nop
0x180004761  lea     rcx, [rbp+57h+var_60]; this
0x180004765  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000476a  nop
0x18000476b  xor     ecx, ecx
0x18000476d  jmp     loc_1800045E0
0x180004772  lea     rdx, WPP_GLOBAL_Control
0x180004779  mov     rcx, cs:WPP_GLOBAL_Control
0x180004780  cmp     rcx, rdx
0x180004783  jz      short loc_1800047B1
0x180004785  test    byte ptr [rcx+1Ch], 2
0x180004789  jz      short loc_1800047B1
0x18000478b  cmp     [rcx+19h], sil
0x18000478f  jb      short loc_1800047B1
0x180004791  mov     edx, 12h
0x180004796  mov     eax, [r14]
0x180004799  mov     [rsp+0B0h+dwOptions], eax
0x18000479d  mov     r9, rdi
0x1800047a0  lea     r8, WPP_18f9f5786677348a014147273dcee318_Traceguids
0x1800047a7  mov     rcx, [rcx+10h]
0x1800047ab  call    WPP_SF_SD
0x1800047b0  nop
0x1800047b1  lea     rcx, [rbp+57h+var_60]; this
0x1800047b5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800047ba  nop
0x1800047bb  xor     ecx, ecx; Block
0x1800047bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800047c2  xor     ebx, ebx
0x1800047c4  lea     rcx, [rbp+57h+hKey]; this
0x1800047c8  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800047cd  mov     eax, ebx
0x1800047cf  mov     rbx, [rsp+0B0h+arg_8]
0x1800047d7  add     rsp, 90h
0x1800047de  pop     r15
0x1800047e0  pop     r14
0x1800047e2  pop     rdi
0x1800047e3  pop     rsi
0x1800047e4  pop     rbp
0x1800047e5  retn
```
