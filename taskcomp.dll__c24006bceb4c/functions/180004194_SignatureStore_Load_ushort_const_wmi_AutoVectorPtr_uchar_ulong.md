# SignatureStore::Load(ushort const *,wmi::AutoVectorPtr<uchar> &,ulong &)

- ea: `0x180004194`
- end: `0x1800045d8`
- name: `?Load@SignatureStore@@SAJPEBGAEAV?$AutoVectorPtr@E@wmi@@AEAK@Z`
- size: `1092`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, BYTE *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ac28`
- `0x18000c8b4`
- `0x180010678`

## callees

- `0x180003300`
- `0x180003470`
- `0x180004194`
- `0x180004e50`
- `0x180004ec0`
- `0x180004f88`
- `0x1800064bc`
- `0x1800074c8`
- `0x1800074d4`
- `0x18000c8f4`
- `0x18000c954`
- `0x18000c9d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800042f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004467`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800042f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004467`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000421f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000421f`

## string_xrefs

- `0x180004211`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\CompatibilityAdapter\Signatures`

## pseudocode

```c
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
0x180004194  mov     r11, rsp
0x180004197  mov     [r11+10h], rbx
0x18000419b  push    rbp
0x18000419c  push    rsi
0x18000419d  push    rdi
0x18000419e  push    r14
0x1800041a0  push    r15
0x1800041a2  lea     rbp, [r11-5Fh]
0x1800041a6  sub     rsp, 90h
0x1800041ad  mov     r14, r8
0x1800041b0  mov     r15, rdx
0x1800041b3  lea     rdi, [rcx+2]
0x1800041b7  cmp     word ptr [rcx], 5Ch ; '\'
0x1800041bb  cmovnz  rdi, rcx
0x1800041bf  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x1800041c7  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x1800041ce  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800041d2  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x1800041da  mov     [rbp+57h+hKey], 0
0x1800041e2  mov     qword ptr [r11-78h], 0
0x1800041ea  lea     rax, [rbp+57h+hKey]
0x1800041ee  mov     [r11-80h], rax
0x1800041f2  lea     rax, [rbp+57h+SecurityAttributes]
0x1800041f6  mov     [rsp+30h], rax; lpSecurityAttributes
0x1800041fb  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x180004203  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x18000420b  xor     r9d, r9d; lpClass
0x18000420e  xor     r8d, r8d; Reserved
0x180004211  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180004218  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000421f  call    cs:__imp_RegCreateKeyExW
0x180004225  mov     ebx, eax
0x180004227  test    eax, eax
0x180004229  jz      short loc_180004275
0x18000422b  lea     rdx, WPP_GLOBAL_Control
0x180004232  mov     rcx, cs:WPP_GLOBAL_Control
0x180004239  cmp     rcx, rdx
0x18000423c  jz      short loc_18000425F
0x18000423e  test    byte ptr [rcx+1Ch], 2
0x180004242  jz      short loc_18000425F
0x180004244  cmp     byte ptr [rcx+19h], 2
0x180004248  jb      short loc_18000425F
0x18000424a  mov     edx, 0Ah
0x18000424f  mov     [rsp+0B0h+dwOptions], eax
0x180004253  mov     r9, rdi
0x180004256  mov     rcx, [rcx+10h]
0x18000425a  call    WPP_SF_Sd
0x18000425f  test    ebx, ebx
0x180004261  jle     loc_1800045B6
0x180004267  movzx   ebx, bx
0x18000426a  or      ebx, 80070000h
0x180004270  jmp     loc_1800045B6
0x180004275  mov     [rbp+57h+Type], 0
0x18000427c  mov     [rbp+57h+cbData], 40h ; '@'
0x180004283  mov     ecx, 40h ; '@'; unsigned __int64
0x180004288  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000428d  mov     rsi, rax
0x180004290  test    rax, rax
0x180004293  jnz     short loc_1800042DC
0x180004295  lea     rdx, WPP_GLOBAL_Control
0x18000429c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042a3  cmp     rcx, rdx
0x1800042a6  jz      short loc_1800042CB
0x1800042a8  test    byte ptr [rcx+1Ch], 2
0x1800042ac  jz      short loc_1800042CB
0x1800042ae  cmp     byte ptr [rcx+19h], 2
0x1800042b2  jb      short loc_1800042CB
0x1800042b4  lea     edx, [rax+0Bh]
0x1800042b7  mov     r9, rdi
0x1800042ba  lea     r8, WPP_18f9f5786677348a014147273dcee318_Traceguids
0x1800042c1  mov     rcx, [rcx+10h]
0x1800042c5  call    WPP_SF_S
0x1800042ca  nop
0x1800042cb  xor     ecx, ecx; Block
0x1800042cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042d2  mov     ebx, 8007000Eh
0x1800042d7  jmp     loc_1800045B6
0x1800042dc  lea     rax, [rbp+57h+cbData]
0x1800042e0  mov     qword ptr [rsp+0B0h+samDesired], rax; lpcbData
0x1800042e5  mov     qword ptr [rsp+0B0h+dwOptions], rsi; lpData
0x1800042ea  lea     r9, [rbp+57h+Type]; lpType
0x1800042ee  xor     r8d, r8d; lpReserved
0x1800042f1  mov     rdx, rdi; lpValueName
0x1800042f4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800042f8  call    cs:__imp_RegQueryValueExW
0x1800042fe  mov     ebx, eax
0x180004300  test    eax, eax
0x180004302  jz      short loc_180004352
0x180004304  lea     rdx, WPP_GLOBAL_Control
0x18000430b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004312  cmp     rcx, rdx
0x180004315  jz      short loc_180004338
0x180004317  test    byte ptr [rcx+1Ch], 2
0x18000431b  jz      short loc_180004338
0x18000431d  cmp     byte ptr [rcx+19h], 2
0x180004321  jb      short loc_180004338
0x180004323  mov     edx, 0Ch
0x180004328  mov     [rsp+0B0h+dwOptions], eax
0x18000432c  mov     r9, rdi
0x18000432f  mov     rcx, [rcx+10h]
0x180004333  call    WPP_SF_Sd
0x180004338  test    ebx, ebx
0x18000433a  jle     short loc_180004345
0x18000433c  movzx   ebx, bx
0x18000433f  or      ebx, 80070000h
0x180004345  mov     rcx, rsi; Block
0x180004348  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000434d  jmp     loc_1800045B6
0x180004352  mov     eax, [rbp+57h+Type]
0x180004355  cmp     eax, 3
0x180004358  jz      short loc_180004390
0x18000435a  lea     rdx, WPP_GLOBAL_Control
0x180004361  mov     rcx, cs:WPP_GLOBAL_Control
0x180004368  cmp     rcx, rdx
0x18000436b  jz      short loc_1800043D5
0x18000436d  test    byte ptr [rcx+1Ch], 2
0x180004371  jz      short loc_1800043D5
0x180004373  cmp     byte ptr [rcx+19h], 2
0x180004377  jb      short loc_1800043D5
0x180004379  mov     edx, 0Dh
0x18000437e  mov     [rsp+0B0h+dwOptions], eax
0x180004382  mov     r9, rdi
0x180004385  mov     rcx, [rcx+10h]
0x180004389  call    WPP_SF_Sd
0x18000438e  jmp     short loc_1800043D5
0x180004390  mov     eax, [rbp+57h+cbData]
0x180004393  cmp     eax, 40h ; '@'
0x180004396  jz      short loc_1800043E7
0x180004398  lea     rdx, WPP_GLOBAL_Control
0x18000439f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043a6  cmp     rcx, rdx
0x1800043a9  jz      short loc_1800043D5
0x1800043ab  test    byte ptr [rcx+1Ch], 2
0x1800043af  jz      short loc_1800043D5
0x1800043b1  cmp     byte ptr [rcx+19h], 2
0x1800043b5  jb      short loc_1800043D5
0x1800043b7  mov     edx, 0Eh
0x1800043bc  mov     [rsp+0B0h+samDesired], eax
0x1800043c0  mov     [rsp+0B0h+dwOptions], 3
0x1800043c8  mov     r9, rdi
0x1800043cb  mov     rcx, [rcx+10h]
0x1800043cf  call    WPP_SF_Sdd
0x1800043d4  nop
0x1800043d5  mov     rcx, rsi; Block
0x1800043d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800043dd  mov     ebx, 8000FFFFh
0x1800043e2  jmp     loc_1800045B6
0x1800043e7  mov     [rbp+57h+var_48], 0
0x1800043ef  mov     rdx, rsi
0x1800043f2  mov     rcx, r15
0x1800043f5  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x1800043fa  mov     rdx, rdi; unsigned __int16 *
0x1800043fd  lea     rcx, [rbp+57h+var_60]; this
0x180004401  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180004406  nop
0x180004407  lea     rdx, psz; ".fp"
0x18000440e  lea     rcx, [rbp+57h+var_50]; this
0x180004412  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180004417  nop
0x180004418  lea     rdx, [rbp+57h+var_50]
0x18000441c  lea     rcx, [rbp+57h+var_60]
0x180004420  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180004425  nop
0x180004426  lea     rcx, [rbp+57h+var_50]; this
0x18000442a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000442f  mov     [rbp+57h+Type], 0
0x180004436  mov     esi, 4
0x18000443b  mov     [rbp+57h+cbData], esi
0x18000443e  mov     rax, [rbp+57h+var_60]
0x180004442  test    rax, rax
0x180004445  jz      short loc_18000444C
0x180004447  mov     rdx, [rax]
0x18000444a  jmp     short loc_18000444E
0x18000444c  xor     edx, edx; lpValueName
0x18000444e  lea     rax, [rbp+57h+cbData]
0x180004452  mov     qword ptr [rsp+0B0h+samDesired], rax; lpcbData
0x180004457  mov     qword ptr [rsp+0B0h+dwOptions], r14; lpData
0x18000445c  lea     r9, [rbp+57h+Type]; lpType
0x180004460  xor     r8d, r8d; lpReserved
0x180004463  mov     rcx, [rbp+57h+hKey]; hKey
0x180004467  call    cs:__imp_RegQueryValueExW
0x18000446d  mov     ebx, eax
0x18000446f  test    eax, eax
0x180004471  jz      short loc_1800044D6
0x180004473  cmp     eax, 2
0x180004476  jnz     short loc_180004484
0x180004478  mov     dword ptr [r14], 0
0x18000447f  jmp     loc_1800045A3
0x180004484  lea     rdx, WPP_GLOBAL_Control
0x18000448b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004492  cmp     rcx, rdx
0x180004495  jz      short loc_1800044B8
0x180004497  test    byte ptr [rcx+1Ch], 2
0x18000449b  jz      short loc_1800044B8
0x18000449d  cmp     byte ptr [rcx+19h], 2
0x1800044a1  jb      short loc_1800044B8
0x1800044a3  mov     edx, 0Fh
0x1800044a8  mov     [rsp+0B0h+dwOptions], ebx
0x1800044ac  mov     r9, rdi
0x1800044af  mov     rcx, [rcx+10h]
0x1800044b3  call    WPP_SF_Sd
0x1800044b8  test    ebx, ebx
0x1800044ba  jle     short loc_1800044C5
0x1800044bc  movzx   ebx, bx
0x1800044bf  or      ebx, 80070000h
0x1800044c5  lea     rcx, [rbp+57h+var_60]; this
0x1800044c9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800044ce  nop
0x1800044cf  xor     ecx, ecx
0x1800044d1  jmp     loc_180004348
0x1800044d6  mov     eax, [rbp+57h+Type]
0x1800044d9  cmp     eax, esi
0x1800044db  jz      short loc_180004513
0x1800044dd  lea     rdx, WPP_GLOBAL_Control
0x1800044e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044eb  cmp     rcx, rdx
0x1800044ee  jz      short loc_180004553
0x1800044f0  test    byte ptr [rcx+1Ch], 2
0x1800044f4  jz      short loc_180004553
0x1800044f6  cmp     byte ptr [rcx+19h], 2
0x1800044fa  jb      short loc_180004553
0x1800044fc  mov     edx, 10h
0x180004501  mov     [rsp+0B0h+dwOptions], eax
0x180004505  mov     r9, rdi
0x180004508  mov     rcx, [rcx+10h]
0x18000450c  call    WPP_SF_Sd
0x180004511  jmp     short loc_180004553
0x180004513  mov     eax, [rbp+57h+cbData]
0x180004516  cmp     eax, esi
0x180004518  jz      short loc_180004564
0x18000451a  lea     rdx, WPP_GLOBAL_Control
0x180004521  mov     rcx, cs:WPP_GLOBAL_Control
0x180004528  cmp     rcx, rdx
0x18000452b  jz      short loc_180004553
0x18000452d  test    byte ptr [rcx+1Ch], 2
0x180004531  jz      short loc_180004553
0x180004533  cmp     byte ptr [rcx+19h], 2
0x180004537  jb      short loc_180004553
0x180004539  mov     edx, 11h
0x18000453e  mov     [rsp+0B0h+samDesired], esi
0x180004542  mov     [rsp+0B0h+dwOptions], eax
0x180004546  mov     r9, rdi
0x180004549  mov     rcx, [rcx+10h]
0x18000454d  call    WPP_SF_Sdd
0x180004552  nop
0x180004553  lea     rcx, [rbp+57h+var_60]; this
0x180004557  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000455c  nop
0x18000455d  xor     ecx, ecx
0x18000455f  jmp     loc_1800043D8
0x180004564  lea     rdx, WPP_GLOBAL_Control
0x18000456b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004572  cmp     rcx, rdx
0x180004575  jz      short loc_1800045A3
0x180004577  test    byte ptr [rcx+1Ch], 2
0x18000457b  jz      short loc_1800045A3
0x18000457d  cmp     [rcx+19h], sil
0x180004581  jb      short loc_1800045A3
0x180004583  mov     edx, 12h
0x180004588  mov     eax, [r14]
0x18000458b  mov     [rsp+0B0h+dwOptions], eax
0x18000458f  mov     r9, rdi
0x180004592  lea     r8, WPP_18f9f5786677348a014147273dcee318_Traceguids
0x180004599  mov     rcx, [rcx+10h]
0x18000459d  call    WPP_SF_SD
0x1800045a2  nop
0x1800045a3  lea     rcx, [rbp+57h+var_60]; this
0x1800045a7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800045ac  nop
0x1800045ad  xor     ecx, ecx; Block
0x1800045af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045b4  xor     ebx, ebx
0x1800045b6  lea     rcx, [rbp+57h+hKey]; this
0x1800045ba  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800045bf  mov     eax, ebx
0x1800045c1  mov     rbx, [rsp+0B0h+arg_8]
0x1800045c9  add     rsp, 90h
0x1800045d0  pop     r15
0x1800045d2  pop     r14
0x1800045d4  pop     rdi
0x1800045d5  pop     rsi
0x1800045d6  pop     rbp
0x1800045d7  retn
```
