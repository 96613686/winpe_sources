# SignatureStore::Save(ushort const *,uchar *,ulong)

- ea: `0x1800045e0`
- end: `0x18000480d`
- name: `?Save@SignatureStore@@SAJPEBGPEAEK@Z`
- size: `557`
- prototype: `__int64 __fastcall(const unsigned __int16 *, BYTE *lpData, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ac28`
- `0x18000d414`

## callees

- `0x180003300`
- `0x180003470`
- `0x1800045e0`
- `0x180004e50`
- `0x180004ec0`
- `0x1800064bc`
- `0x18000c954`
- `0x18000c9d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004663`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004663`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004699`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004752`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004699`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004752`

## string_xrefs

- `0x180004655`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\CompatibilityAdapter\Signatures`

## pseudocode

```c
__int64 __fastcall SignatureStore::Save(const unsigned __int16 *a1, BYTE *lpData, int a3)
{
  const WCHAR *v4; // rdi
  LSTATUS v5; // eax
  int v6; // ebx
  int v7; // r8d
  const WCHAR *v8; // rdx
  int v9; // r8d
  _BYTE v11[8]; // [rsp+50h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES v12; // [rsp+58h] [rbp-18h] BYREF
  const WCHAR **v13; // [rsp+90h] [rbp+20h] BYREF
  int Data; // [rsp+A0h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+38h] BYREF

  Data = a3;
  v4 = a1 + 1;
  if ( *a1 != 92 )
    v4 = a1;
  *(_QWORD *)&v12.nLength = 24;
  v12.lpSecurityDescriptor = tsched::StoreSecurity::g_pRestrictedKeySecurity;
  *(_QWORD *)&v12.bInheritHandle = 0;
  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CompatibilityAdapter\\Signatures",
         0,
         0,
         0,
         0x2001Fu,
         &v12,
         &hKey,
         0);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
    {
      v6 = (unsigned __int16)v5;
LABEL_13:
      v6 |= 0x80070000;
    }
  }
  else
  {
    v6 = RegSetValueExW(hKey, v4, 0, 3u, lpData, 0x40u);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v7, (_DWORD)v4, 3, v6);
      }
      if ( v6 > 0 )
      {
        v6 = (unsigned __int16)v6;
        goto LABEL_13;
      }
    }
    else
    {
      _bstr_t::_bstr_t((_bstr_t *)&v13, v4);
      _bstr_t::_bstr_t((_bstr_t *)v11, L".fp");
      _bstr_t::operator+=(&v13, v11);
      _bstr_t::~_bstr_t((_bstr_t *)v11);
      if ( v13 )
        v8 = *v13;
      else
        v8 = 0;
      v6 = RegSetValueExW(hKey, v8, 0, 4u, (const BYTE *)&Data, 4u);
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v9, (_DWORD)v4, v6);
        }
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        _bstr_t::~_bstr_t((_bstr_t *)&v13);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)WPP_18f9f5786677348a014147273dcee318_Traceguids,
            (_DWORD)v4,
            Data);
        }
        _bstr_t::~_bstr_t((_bstr_t *)&v13);
        v6 = 0;
      }
    }
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800045e0  mov     r11, rsp
0x1800045e3  mov     [r11+10h], rbx
0x1800045e7  mov     [r11+18h], r8d
0x1800045eb  push    rbp
0x1800045ec  push    rsi
0x1800045ed  push    rdi
0x1800045ee  mov     rbp, rsp
0x1800045f1  sub     rsp, 70h
0x1800045f5  mov     rsi, rdx
0x1800045f8  lea     rdi, [rcx+2]
0x1800045fc  cmp     word ptr [rcx], 5Ch ; '\'
0x180004600  cmovnz  rdi, rcx
0x180004604  mov     [rbp+var_18], 18h
0x18000460c  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x180004613  mov     [rbp+var_10], rax
0x180004617  mov     [rbp+var_8], 0
0x18000461f  mov     [rbp+hKey], 0
0x180004627  mov     qword ptr [r11-48h], 0
0x18000462f  lea     rax, [rbp+hKey]
0x180004633  mov     [r11-50h], rax
0x180004637  lea     rax, [rbp+var_18]
0x18000463b  mov     [r11-58h], rax
0x18000463f  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x180004647  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18000464f  xor     r9d, r9d; lpClass
0x180004652  xor     r8d, r8d; Reserved
0x180004655  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000465c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004663  call    cs:__imp_RegCreateKeyExW
0x180004669  mov     ebx, eax
0x18000466b  test    eax, eax
0x18000466d  jz      short loc_18000467A
0x18000466f  jle     loc_1800047F2
0x180004675  movzx   ebx, ax
0x180004678  jmp     short loc_1800046E6
0x18000467a  mov     [rsp+70h+samDesired], 40h ; '@'; cbData
0x180004682  mov     qword ptr [rsp+70h+dwOptions], rsi; lpData
0x180004687  mov     esi, 3
0x18000468c  mov     r9d, esi; dwType
0x18000468f  xor     r8d, r8d; Reserved
0x180004692  mov     rdx, rdi; lpValueName
0x180004695  mov     rcx, [rbp+hKey]; hKey
0x180004699  call    cs:__imp_RegSetValueExW
0x18000469f  mov     ebx, eax
0x1800046a1  test    eax, eax
0x1800046a3  jz      short loc_1800046F1
0x1800046a5  lea     rax, WPP_GLOBAL_Control
0x1800046ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046b3  cmp     rcx, rax
0x1800046b6  jz      short loc_1800046DB
0x1800046b8  test    byte ptr [rcx+1Ch], 2
0x1800046bc  jz      short loc_1800046DB
0x1800046be  cmp     byte ptr [rcx+19h], 2
0x1800046c2  jb      short loc_1800046DB
0x1800046c4  lea     edx, [rsi+10h]
0x1800046c7  mov     [rsp+70h+samDesired], ebx
0x1800046cb  mov     [rsp+70h+dwOptions], esi
0x1800046cf  mov     r9, rdi
0x1800046d2  mov     rcx, [rcx+10h]
0x1800046d6  call    WPP_SF_Sdd
0x1800046db  test    ebx, ebx
0x1800046dd  jle     loc_1800047F2
0x1800046e3  movzx   ebx, bx
0x1800046e6  or      ebx, 80070000h
0x1800046ec  jmp     loc_1800047F2
0x1800046f1  mov     rdx, rdi; unsigned __int16 *
0x1800046f4  lea     rcx, [rbp+arg_0]; this
0x1800046f8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800046fd  nop
0x1800046fe  lea     rdx, psz; ".fp"
0x180004705  lea     rcx, [rbp+var_20]; this
0x180004709  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000470e  nop
0x18000470f  lea     rdx, [rbp+var_20]
0x180004713  lea     rcx, [rbp+arg_0]
0x180004717  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18000471c  nop
0x18000471d  lea     rcx, [rbp+var_20]; this
0x180004721  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004726  mov     rax, [rbp+arg_0]
0x18000472a  test    rax, rax
0x18000472d  jz      short loc_180004734
0x18000472f  mov     rdx, [rax]
0x180004732  jmp     short loc_180004736
0x180004734  xor     edx, edx; lpValueName
0x180004736  mov     esi, 4
0x18000473b  mov     [rsp+70h+samDesired], esi; cbData
0x18000473f  lea     rax, [rbp+Data]
0x180004743  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180004748  mov     r9d, esi; dwType
0x18000474b  xor     r8d, r8d; Reserved
0x18000474e  mov     rcx, [rbp+hKey]; hKey
0x180004752  call    cs:__imp_RegSetValueExW
0x180004758  mov     ebx, eax
0x18000475a  test    eax, eax
0x18000475c  jz      short loc_1800047A8
0x18000475e  lea     rax, WPP_GLOBAL_Control
0x180004765  mov     rcx, cs:WPP_GLOBAL_Control
0x18000476c  cmp     rcx, rax
0x18000476f  jz      short loc_180004790
0x180004771  test    byte ptr [rcx+1Ch], 2
0x180004775  jz      short loc_180004790
0x180004777  cmp     byte ptr [rcx+19h], 2
0x18000477b  jb      short loc_180004790
0x18000477d  lea     edx, [rsi+10h]
0x180004780  mov     [rsp+70h+dwOptions], ebx
0x180004784  mov     r9, rdi
0x180004787  mov     rcx, [rcx+10h]
0x18000478b  call    WPP_SF_Sd
0x180004790  test    ebx, ebx
0x180004792  jle     short loc_18000479D
0x180004794  movzx   ebx, bx
0x180004797  or      ebx, 80070000h
0x18000479d  lea     rcx, [rbp+arg_0]; this
0x1800047a1  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800047a6  jmp     short loc_1800047F2
0x1800047a8  lea     rax, WPP_GLOBAL_Control
0x1800047af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047b6  cmp     rcx, rax
0x1800047b9  jz      short loc_1800047E7
0x1800047bb  test    byte ptr [rcx+1Ch], 2
0x1800047bf  jz      short loc_1800047E7
0x1800047c1  cmp     [rcx+19h], sil
0x1800047c5  jb      short loc_1800047E7
0x1800047c7  mov     edx, 15h
0x1800047cc  mov     eax, [rbp+Data]
0x1800047cf  mov     [rsp+70h+dwOptions], eax
0x1800047d3  mov     r9, rdi
0x1800047d6  lea     r8, WPP_18f9f5786677348a014147273dcee318_Traceguids
0x1800047dd  mov     rcx, [rcx+10h]
0x1800047e1  call    WPP_SF_SD
0x1800047e6  nop
0x1800047e7  lea     rcx, [rbp+arg_0]; this
0x1800047eb  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800047f0  xor     ebx, ebx
0x1800047f2  lea     rcx, [rbp+hKey]; this
0x1800047f6  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800047fb  mov     eax, ebx
0x1800047fd  mov     rbx, [rsp+70h+arg_8]
0x180004805  add     rsp, 70h
0x180004809  pop     rdi
0x18000480a  pop     rsi
0x18000480b  pop     rbp
0x18000480c  retn
```
