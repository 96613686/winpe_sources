# SignatureStore::Save(ushort const *,uchar *,ulong)

- ea: `0x1800047f0`
- end: `0x180004a30`
- name: `?Save@SignatureStore@@SAJPEBGPEAEK@Z`
- size: `576`
- prototype: `__int64 __fastcall(const unsigned __int16 *, BYTE *lpData, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b218`
- `0x18000dca8`

## callees

- `0x180003480`
- `0x180003600`
- `0x1800047f0`
- `0x1800050d0`
- `0x180005150`
- `0x1800068e4`
- `0x18000d190`
- `0x18000d214`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004873`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004873`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800048af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000496e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800048af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000496e`

## string_xrefs

- `0x180004865`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\CompatibilityAdapter\Signatures`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800047f0  mov     r11, rsp
0x1800047f3  mov     [r11+10h], rbx
0x1800047f7  mov     [r11+18h], r8d
0x1800047fb  push    rbp
0x1800047fc  push    rsi
0x1800047fd  push    rdi
0x1800047fe  mov     rbp, rsp
0x180004801  sub     rsp, 70h
0x180004805  mov     rsi, rdx
0x180004808  lea     rdi, [rcx+2]
0x18000480c  cmp     word ptr [rcx], 5Ch ; '\'
0x180004810  cmovnz  rdi, rcx
0x180004814  mov     [rbp+var_18], 18h
0x18000481c  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x180004823  mov     [rbp+var_10], rax
0x180004827  mov     [rbp+var_8], 0
0x18000482f  mov     [rbp+hKey], 0
0x180004837  mov     qword ptr [r11-48h], 0
0x18000483f  lea     rax, [rbp+hKey]
0x180004843  mov     [r11-50h], rax
0x180004847  lea     rax, [rbp+var_18]
0x18000484b  mov     [r11-58h], rax
0x18000484f  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x180004857  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18000485f  xor     r9d, r9d; lpClass
0x180004862  xor     r8d, r8d; Reserved
0x180004865  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000486c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004873  call    cs:__imp_RegCreateKeyExW
0x18000487a  nop     dword ptr [rax+rax+00h]
0x18000487f  mov     ebx, eax
0x180004881  test    eax, eax
0x180004883  jz      short loc_180004890
0x180004885  jle     loc_180004A14
0x18000488b  movzx   ebx, ax
0x18000488e  jmp     short loc_180004902
0x180004890  mov     [rsp+70h+samDesired], 40h ; '@'; cbData
0x180004898  mov     qword ptr [rsp+70h+dwOptions], rsi; lpData
0x18000489d  mov     esi, 3
0x1800048a2  mov     r9d, esi; dwType
0x1800048a5  xor     r8d, r8d; Reserved
0x1800048a8  mov     rdx, rdi; lpValueName
0x1800048ab  mov     rcx, [rbp+hKey]; hKey
0x1800048af  call    cs:__imp_RegSetValueExW
0x1800048b6  nop     dword ptr [rax+rax+00h]
0x1800048bb  mov     ebx, eax
0x1800048bd  test    eax, eax
0x1800048bf  jz      short loc_18000490D
0x1800048c1  lea     rax, WPP_GLOBAL_Control
0x1800048c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048cf  cmp     rcx, rax
0x1800048d2  jz      short loc_1800048F7
0x1800048d4  test    byte ptr [rcx+1Ch], 2
0x1800048d8  jz      short loc_1800048F7
0x1800048da  cmp     byte ptr [rcx+19h], 2
0x1800048de  jb      short loc_1800048F7
0x1800048e0  lea     edx, [rsi+10h]
0x1800048e3  mov     [rsp+70h+samDesired], ebx
0x1800048e7  mov     [rsp+70h+dwOptions], esi
0x1800048eb  mov     r9, rdi
0x1800048ee  mov     rcx, [rcx+10h]
0x1800048f2  call    WPP_SF_Sdd
0x1800048f7  test    ebx, ebx
0x1800048f9  jle     loc_180004A14
0x1800048ff  movzx   ebx, bx
0x180004902  or      ebx, 80070000h
0x180004908  jmp     loc_180004A14
0x18000490d  mov     rdx, rdi; unsigned __int16 *
0x180004910  lea     rcx, [rbp+arg_0]; this
0x180004914  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180004919  nop
0x18000491a  lea     rdx, psz; ".fp"
0x180004921  lea     rcx, [rbp+var_20]; this
0x180004925  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000492a  nop
0x18000492b  lea     rdx, [rbp+var_20]
0x18000492f  lea     rcx, [rbp+arg_0]
0x180004933  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180004938  nop
0x180004939  lea     rcx, [rbp+var_20]; this
0x18000493d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004942  mov     rax, [rbp+arg_0]
0x180004946  test    rax, rax
0x180004949  jz      short loc_180004950
0x18000494b  mov     rdx, [rax]
0x18000494e  jmp     short loc_180004952
0x180004950  xor     edx, edx; lpValueName
0x180004952  mov     esi, 4
0x180004957  mov     [rsp+70h+samDesired], esi; cbData
0x18000495b  lea     rax, [rbp+Data]
0x18000495f  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180004964  mov     r9d, esi; dwType
0x180004967  xor     r8d, r8d; Reserved
0x18000496a  mov     rcx, [rbp+hKey]; hKey
0x18000496e  call    cs:__imp_RegSetValueExW
0x180004975  nop     dword ptr [rax+rax+00h]
0x18000497a  mov     ebx, eax
0x18000497c  test    eax, eax
0x18000497e  jz      short loc_1800049CA
0x180004980  lea     rax, WPP_GLOBAL_Control
0x180004987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000498e  cmp     rcx, rax
0x180004991  jz      short loc_1800049B2
0x180004993  test    byte ptr [rcx+1Ch], 2
0x180004997  jz      short loc_1800049B2
0x180004999  cmp     byte ptr [rcx+19h], 2
0x18000499d  jb      short loc_1800049B2
0x18000499f  lea     edx, [rsi+10h]
0x1800049a2  mov     [rsp+70h+dwOptions], ebx
0x1800049a6  mov     r9, rdi
0x1800049a9  mov     rcx, [rcx+10h]
0x1800049ad  call    WPP_SF_Sd
0x1800049b2  test    ebx, ebx
0x1800049b4  jle     short loc_1800049BF
0x1800049b6  movzx   ebx, bx
0x1800049b9  or      ebx, 80070000h
0x1800049bf  lea     rcx, [rbp+arg_0]; this
0x1800049c3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800049c8  jmp     short loc_180004A14
0x1800049ca  lea     rax, WPP_GLOBAL_Control
0x1800049d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049d8  cmp     rcx, rax
0x1800049db  jz      short loc_180004A09
0x1800049dd  test    byte ptr [rcx+1Ch], 2
0x1800049e1  jz      short loc_180004A09
0x1800049e3  cmp     [rcx+19h], sil
0x1800049e7  jb      short loc_180004A09
0x1800049e9  mov     edx, 15h
0x1800049ee  mov     eax, [rbp+Data]
0x1800049f1  mov     [rsp+70h+dwOptions], eax
0x1800049f5  mov     r9, rdi
0x1800049f8  lea     r8, WPP_18f9f5786677348a014147273dcee318_Traceguids
0x1800049ff  mov     rcx, [rcx+10h]
0x180004a03  call    WPP_SF_SD
0x180004a08  nop
0x180004a09  lea     rcx, [rbp+arg_0]; this
0x180004a0d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004a12  xor     ebx, ebx
0x180004a14  lea     rcx, [rbp+hKey]; this
0x180004a18  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180004a1d  mov     eax, ebx
0x180004a1f  mov     rbx, [rsp+70h+arg_8]
0x180004a27  add     rsp, 70h
0x180004a2b  pop     rdi
0x180004a2c  pop     rsi
0x180004a2d  pop     rbp
0x180004a2e  retn
```
