# ComputeService::ContainerDevice::GetSerialDeviceSymlinksFromRegistry(std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x1400dba30`
- end: `0x1400dbde3`
- name: `?GetSerialDeviceSymlinksFromRegistry@ContainerDevice@ComputeService@@YAJAEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1400c8adc`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x140006098`
- `0x1400068e0`
- `0x140008760`
- `0x14001e4f4`
- `0x1400db414`
- `0x1400dba30`
- `0x1400dbdec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400dbade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400dbb72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400dbdd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400dbade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400dbb72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400dbdd6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400dbce9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400dbce9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400dbca4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400dbca4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400dbb4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400dbbd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400dbb4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400dbbd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400dbaa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400dbaa0`

## string_xrefs

- `0x1400dba92`: `HARDWARE\DEVICEMAP\SERIALCOMM`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ComputeService::ContainerDevice::GetSerialDeviceSymlinksFromRegistry(__int64 a1)
{
  int v1; // r13d
  unsigned int v2; // r14d
  void *v3; // rbx
  void *v4; // rdi
  unsigned __int64 v5; // rdx
  LSTATUS v6; // ecx
  int v8; // r14d
  unsigned int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // ebx
  DWORD v12; // r15d
  unsigned int v13; // eax
  unsigned int v14; // r8d
  unsigned __int64 v15; // rsi
  void *v16; // r12
  unsigned __int64 v17; // rdx
  void *v18; // rcx
  unsigned __int64 v19; // rsi
  void *v20; // r13
  unsigned __int64 v21; // rdx
  void *v22; // rcx
  LSTATUS ValueW; // eax
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // rdx
  unsigned int v27; // esi
  unsigned int phkResult; // [rsp+20h] [rbp-A9h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A9h]
  int v30; // [rsp+60h] [rbp-69h]
  int v31; // [rsp+60h] [rbp-69h]
  __int128 v33; // [rsp+80h] [rbp-49h] BYREF
  __int64 v34; // [rsp+90h] [rbp-39h]
  __int64 v35; // [rsp+98h] [rbp-31h]
  __int128 v36; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-19h]
  __int64 v38; // [rsp+B8h] [rbp-11h]
  DWORD cbMaxValueLen; // [rsp+C0h] [rbp-9h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+C4h] [rbp-5h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp-1h] BYREF
  DWORD cValues; // [rsp+D0h] [rbp+7h] BYREF
  DWORD Type; // [rsp+D4h] [rbp+Bh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v1 = 0;
  v2 = 0;
  cValues = 0;
  v3 = 0;
  cbMaxValueLen = 0;
  v4 = 0;
  cbMaxValueNameLen = 0;
  Type = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"HARDWARE\\DEVICEMAP\\SERIALCOMM", 0, 1u, &hKey);
  if ( (unsigned int)(v6 - 2) <= 1 )
    goto LABEL_5;
  if ( v6 )
  {
    if ( v6 > 0 )
    {
      v8 = (unsigned __int16)v6;
LABEL_13:
      v2 = v8 | 0x80070000;
    }
    else
    {
      v2 = v6;
    }
    goto LABEL_5;
  }
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  if ( v9 )
  {
    v11 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x1E5, v10, (const char *)v9, phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v11;
  }
  v12 = 0;
  if ( !cValues )
  {
LABEL_5:
    if ( v4 )
      operator delete(v4, v5);
    if ( v3 )
      operator delete(v3, v5);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  while ( 1 )
  {
    v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    if ( v13 )
      break;
    ++cbMaxValueNameLen;
    cbMaxValueLen += 2;
    v15 = saturated_mul(cbMaxValueNameLen, 2u);
    v16 = operator new[](v15);
    memset_0(v16, 0, v15);
    v30 = v1 | 1;
    v18 = v4;
    v4 = v16;
    if ( v18 )
      operator delete(v18, v17);
    v19 = saturated_mul((unsigned __int64)cbMaxValueLen >> 1, 2u);
    v20 = operator new[](v19);
    memset_0(v20, 0, v19);
    v31 = v30 | 2;
    v22 = v3;
    v3 = v20;
    if ( v22 )
      operator delete(v22, v21);
    ValueW = RegEnumValueW(hKey, v12, (LPWSTR)v16, &cbMaxValueNameLen, 0, &Type, 0, 0);
    if ( ValueW != 234 )
    {
      if ( ValueW )
      {
        if ( ValueW <= 0 )
          goto LABEL_39;
LABEL_41:
        v8 = (unsigned __int16)ValueW;
        goto LABEL_13;
      }
      if ( Type == 1 )
      {
        ValueW = RegGetValueW(hKey, 0, (LPCWSTR)v16, 2u, 0, v20, &cbMaxValueLen);
        if ( ValueW == 234 )
          goto LABEL_20;
        if ( ValueW )
        {
          if ( ValueW <= 0 )
          {
LABEL_39:
            v2 = ValueW;
            goto LABEL_5;
          }
          goto LABEL_41;
        }
        v33 = 0;
        v34 = 0;
        v35 = 0;
        v24 = -1;
        do
          ++v24;
        while ( *((_WORD *)v20 + v24) );
        std::wstring::_Construct<1,unsigned short const *>((__int64)&v33, v20, v24);
        v36 = 0;
        v37 = 0;
        v38 = 0;
        v25 = -1;
        do
          ++v25;
        while ( *((_WORD *)v16 + v25) );
        std::wstring::_Construct<1,unsigned short const *>((__int64)&v36, v16, v25);
        std::vector<std::pair<std::wstring,std::wstring>>::emplace_back<std::pair<std::wstring,std::wstring>>(a1, &v33);
        std::wstring::~wstring(&v36);
        std::wstring::~wstring(&v33);
      }
      if ( ++v12 >= cValues )
        goto LABEL_5;
    }
LABEL_20:
    v1 = v31;
  }
  v27 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x1EE, v14, (const char *)v13, phkResulta);
  if ( v4 )
    operator delete(v4, v26);
  if ( v3 )
    operator delete(v3, v26);
  if ( hKey )
    RegCloseKey(hKey);
  return v27;
}

```

## disassembly

```asm
0x1400dba30  push    rbp
0x1400dba32  push    rbx
0x1400dba33  push    rsi
0x1400dba34  push    rdi
0x1400dba35  push    r12
0x1400dba37  push    r13
0x1400dba39  push    r14
0x1400dba3b  push    r15
0x1400dba3d  lea     rbp, [rsp-1Fh]
0x1400dba42  sub     rsp, 0E8h
0x1400dba49  mov     rax, cs:__security_cookie
0x1400dba50  xor     rax, rsp
0x1400dba53  mov     [rbp+57h+var_48], rax
0x1400dba57  mov     [rbp+57h+var_A8], rcx
0x1400dba5b  xor     esi, esi
0x1400dba5d  mov     r13d, esi
0x1400dba60  mov     [rbp+57h+var_C0], esi
0x1400dba63  mov     r14d, esi
0x1400dba66  mov     [rbp+57h+cValues], esi
0x1400dba69  mov     ebx, esi
0x1400dba6b  mov     [rbp+57h+var_B0], rbx
0x1400dba6f  mov     [rbp+57h+cbMaxValueLen], esi
0x1400dba72  mov     edi, esi
0x1400dba74  mov     [rbp+57h+var_B8], rsi
0x1400dba78  mov     [rbp+57h+cbMaxValueNameLen], esi
0x1400dba7b  mov     [rbp+57h+Type], esi
0x1400dba7e  mov     [rbp+57h+hKey], rsi
0x1400dba82  lea     rax, [rbp+57h+hKey]
0x1400dba86  mov     [rsp+120h+phkResult], rax; phkResult
0x1400dba8b  lea     r9d, [rsi+1]; samDesired
0x1400dba8f  xor     r8d, r8d; ulOptions
0x1400dba92  lea     rdx, aHardwareDevice; "HARDWARE\\DEVICEMAP\\SERIALCOMM"
0x1400dba99  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400dbaa0  call    cs:__imp_RegOpenKeyExW
0x1400dbaa6  mov     ecx, eax
0x1400dbaa8  add     eax, 0FFFFFFFEh
0x1400dbaab  cmp     eax, 1
0x1400dbaae  jbe     short loc_1400DBAB9
0x1400dbab0  test    ecx, ecx
0x1400dbab2  jz      short loc_1400DBB14
0x1400dbab4  jg      short loc_1400DBB07
0x1400dbab6  mov     r14d, ecx
0x1400dbab9  test    rdi, rdi
0x1400dbabc  jz      short loc_1400DBAC7
0x1400dbabe  mov     rcx, rdi; void *
0x1400dbac1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400dbac6  nop
0x1400dbac7  test    rbx, rbx
0x1400dbaca  jz      short loc_1400DBAD5
0x1400dbacc  mov     rcx, rbx; void *
0x1400dbacf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400dbad4  nop
0x1400dbad5  mov     rcx, [rbp+57h+hKey]; hKey
0x1400dbad9  test    rcx, rcx
0x1400dbadc  jz      short loc_1400DBAE4
0x1400dbade  call    cs:__imp_RegCloseKey
0x1400dbae4  mov     eax, r14d
0x1400dbae7  mov     rcx, [rbp+57h+var_48]
0x1400dbaeb  xor     rcx, rsp; StackCookie
0x1400dbaee  call    __security_check_cookie
0x1400dbaf3  add     rsp, 0E8h
0x1400dbafa  pop     r15
0x1400dbafc  pop     r14
0x1400dbafe  pop     r13
0x1400dbb00  pop     r12
0x1400dbb02  pop     rdi
0x1400dbb03  pop     rsi
0x1400dbb04  pop     rbx
0x1400dbb05  pop     rbp
0x1400dbb06  retn
0x1400dbb07  movzx   r14d, cx
0x1400dbb0b  or      r14d, 80070000h
0x1400dbb12  jmp     short loc_1400DBAB9
0x1400dbb14  mov     [rsp+120h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1400dbb19  mov     [rsp+120h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1400dbb1e  mov     [rsp+120h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1400dbb23  mov     [rsp+120h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1400dbb28  lea     rax, [rbp+57h+cValues]
0x1400dbb2c  mov     [rsp+120h+lpcValues], rax; lpcValues
0x1400dbb31  mov     [rsp+120h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1400dbb36  mov     [rsp+120h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x1400dbb3b  mov     [rsp+120h+phkResult], rsi; unsigned int
0x1400dbb40  xor     r9d, r9d; lpReserved
0x1400dbb43  xor     r8d, r8d; lpcchClass
0x1400dbb46  xor     edx, edx; lpClass
0x1400dbb48  mov     rcx, [rbp+57h+hKey]; hKey
0x1400dbb4c  call    cs:__imp_RegQueryInfoKeyW
0x1400dbb52  test    eax, eax
0x1400dbb54  jz      short loc_1400DBB7F
0x1400dbb56  mov     rcx, [rbp+5Fh]; this
0x1400dbb5a  mov     r9d, eax; char *
0x1400dbb5d  mov     edx, 1E5h; void *
0x1400dbb62  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400dbb67  mov     ebx, eax
0x1400dbb69  mov     rcx, [rbp+57h+hKey]; hKey
0x1400dbb6d  test    rcx, rcx
0x1400dbb70  jz      short loc_1400DBB78
0x1400dbb72  call    cs:__imp_RegCloseKey
0x1400dbb78  mov     eax, ebx
0x1400dbb7a  jmp     loc_1400DBAE7
0x1400dbb7f  mov     r15d, esi
0x1400dbb82  cmp     [rbp+57h+cValues], esi
0x1400dbb85  jbe     loc_1400DBAB9
0x1400dbb8b  jmp     short loc_1400DBB91
0x1400dbb8d  mov     r13d, [rbp+57h+var_C0]
0x1400dbb91  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400dbb95  mov     [rsp+120h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1400dbb9a  mov     [rsp+120h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1400dbb9f  lea     rax, [rbp+57h+cbMaxValueLen]
0x1400dbba3  mov     [rsp+120h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1400dbba8  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1400dbbac  mov     [rsp+120h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1400dbbb1  mov     [rsp+120h+lpcValues], rsi; lpcValues
0x1400dbbb6  mov     [rsp+120h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1400dbbbb  mov     [rsp+120h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x1400dbbc0  mov     [rsp+120h+phkResult], rsi; unsigned int
0x1400dbbc5  xor     r9d, r9d; lpReserved
0x1400dbbc8  xor     r8d, r8d; lpcchClass
0x1400dbbcb  xor     edx, edx; lpClass
0x1400dbbcd  mov     rcx, [rbp+57h+hKey]; hKey
0x1400dbbd1  call    cs:__imp_RegQueryInfoKeyW
0x1400dbbd7  test    eax, eax
0x1400dbbd9  jnz     loc_1400DBD9E
0x1400dbbdf  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1400dbbe2  inc     eax
0x1400dbbe4  mov     [rbp+57h+cbMaxValueNameLen], eax
0x1400dbbe7  mov     ecx, eax
0x1400dbbe9  add     [rbp+57h+cbMaxValueLen], 2
0x1400dbbed  lea     eax, [r12+3]
0x1400dbbf2  mul     rcx
0x1400dbbf5  mov     rsi, rax
0x1400dbbf8  cmovb   rsi, r12
0x1400dbbfc  mov     rcx, rsi; unsigned __int64
0x1400dbbff  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400dbc04  mov     r12, rax
0x1400dbc07  mov     r8, rsi; Size
0x1400dbc0a  xor     edx, edx; Val
0x1400dbc0c  mov     rcx, rax; void *
0x1400dbc0f  call    memset_0
0x1400dbc14  or      r13d, 1
0x1400dbc18  mov     [rbp+57h+var_C0], r13d
0x1400dbc1c  mov     rcx, rdi; void *
0x1400dbc1f  mov     rdi, r12
0x1400dbc22  mov     [rbp+57h+var_B8], r12
0x1400dbc26  test    rcx, rcx
0x1400dbc29  jz      short loc_1400DBC30
0x1400dbc2b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400dbc30  mov     ecx, [rbp+57h+cbMaxValueLen]
0x1400dbc33  shr     rcx, 1
0x1400dbc36  mov     eax, 2
0x1400dbc3b  mul     rcx
0x1400dbc3e  mov     rsi, rax
0x1400dbc41  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400dbc48  cmovb   rsi, rax
0x1400dbc4c  mov     rcx, rsi; unsigned __int64
0x1400dbc4f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400dbc54  mov     r13, rax
0x1400dbc57  mov     r8, rsi; Size
0x1400dbc5a  xor     edx, edx; Val
0x1400dbc5c  mov     rcx, rax; void *
0x1400dbc5f  call    memset_0
0x1400dbc64  or      [rbp+57h+var_C0], 2
0x1400dbc68  mov     rcx, rbx; void *
0x1400dbc6b  mov     rbx, r13
0x1400dbc6e  mov     [rbp+57h+var_B0], rbx
0x1400dbc72  xor     esi, esi
0x1400dbc74  test    rcx, rcx
0x1400dbc77  jz      short loc_1400DBC7E
0x1400dbc79  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400dbc7e  mov     [rsp+120h+lpcValues], rsi; lpcbData
0x1400dbc83  mov     [rsp+120h+lpcbMaxClassLen], rsi; lpData
0x1400dbc88  lea     rax, [rbp+57h+Type]
0x1400dbc8c  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpType
0x1400dbc91  mov     [rsp+120h+phkResult], rsi; lpReserved
0x1400dbc96  lea     r9, [rbp+57h+cbMaxValueNameLen]; lpcchValueName
0x1400dbc9a  mov     r8, r12; lpValueName
0x1400dbc9d  mov     edx, r15d; dwIndex
0x1400dbca0  mov     rcx, [rbp+57h+hKey]; hKey
0x1400dbca4  call    cs:__imp_RegEnumValueW
0x1400dbcaa  cmp     eax, 0EAh
0x1400dbcaf  jz      loc_1400DBB8D
0x1400dbcb5  test    eax, eax
0x1400dbcb7  jnz     loc_1400DBD93
0x1400dbcbd  cmp     [rbp+57h+Type], 1
0x1400dbcc1  jnz     loc_1400DBD77
0x1400dbcc7  lea     rax, [rbp+57h+cbMaxValueLen]
0x1400dbccb  mov     [rsp+120h+lpcbMaxClassLen], rax; pcbData
0x1400dbcd0  mov     [rsp+120h+lpcbMaxSubKeyLen], r13; pvData
0x1400dbcd5  mov     [rsp+120h+phkResult], rsi; pdwType
0x1400dbcda  mov     r9d, 2; dwFlags
0x1400dbce0  mov     r8, r12; lpValue
0x1400dbce3  xor     edx, edx; lpSubKey
0x1400dbce5  mov     rcx, [rbp+57h+hKey]; hkey
0x1400dbce9  call    cs:__imp_RegGetValueW
0x1400dbcef  cmp     eax, 0EAh
0x1400dbcf4  jz      loc_1400DBB8D
0x1400dbcfa  test    eax, eax
0x1400dbcfc  jnz     loc_1400DBD89
0x1400dbd02  xorps   xmm0, xmm0
0x1400dbd05  movups  [rbp+57h+var_A0], xmm0
0x1400dbd09  mov     [rbp+57h+var_90], rsi
0x1400dbd0d  mov     [rbp+57h+var_88], rsi
0x1400dbd11  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400dbd15  inc     r8
0x1400dbd18  cmp     [r13+r8*2+0], si
0x1400dbd1e  jnz     short loc_1400DBD15
0x1400dbd20  mov     rdx, r13
0x1400dbd23  lea     rcx, [rbp+57h+var_A0]
0x1400dbd27  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400dbd2c  nop
0x1400dbd2d  xorps   xmm0, xmm0
0x1400dbd30  movups  [rbp+57h+var_80], xmm0
0x1400dbd34  mov     [rbp+57h+var_70], rsi
0x1400dbd38  mov     [rbp+57h+var_68], rsi
0x1400dbd3c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400dbd40  inc     r8
0x1400dbd43  cmp     [r12+r8*2], si
0x1400dbd48  jnz     short loc_1400DBD40
0x1400dbd4a  mov     rdx, r12
0x1400dbd4d  lea     rcx, [rbp+57h+var_80]
0x1400dbd51  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400dbd56  nop
0x1400dbd57  lea     rdx, [rbp+57h+var_A0]
0x1400dbd5b  mov     rcx, [rbp+57h+var_A8]
0x1400dbd5f  call    ??$emplace_back@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@$$QEAU21@@Z; std::vector<std::pair<std::wstring,std::wstring>>::emplace_back<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> &&)
0x1400dbd64  nop
0x1400dbd65  lea     rcx, [rbp+57h+var_80]; void *
0x1400dbd69  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400dbd6e  lea     rcx, [rbp+57h+var_A0]; void *
0x1400dbd72  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400dbd77  inc     r15d
0x1400dbd7a  cmp     r15d, [rbp+57h+cValues]
0x1400dbd7e  jnb     loc_1400DBAB9
0x1400dbd84  jmp     loc_1400DBB8D
0x1400dbd89  jg      short loc_1400DBD95
0x1400dbd8b  mov     r14d, eax
0x1400dbd8e  jmp     loc_1400DBAB9
0x1400dbd93  jle     short loc_1400DBD8B
0x1400dbd95  movzx   r14d, ax
0x1400dbd99  jmp     loc_1400DBB0B
0x1400dbd9e  mov     rcx, [rbp+5Fh]; this
0x1400dbda2  mov     r9d, eax; char *
0x1400dbda5  mov     edx, 1EEh; void *
0x1400dbdaa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400dbdaf  mov     esi, eax
0x1400dbdb1  test    rdi, rdi
0x1400dbdb4  jz      short loc_1400DBDBF
0x1400dbdb6  mov     rcx, rdi; void *
0x1400dbdb9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400dbdbe  nop
0x1400dbdbf  test    rbx, rbx
0x1400dbdc2  jz      short loc_1400DBDCD
0x1400dbdc4  mov     rcx, rbx; void *
0x1400dbdc7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400dbdcc  nop
0x1400dbdcd  mov     rcx, [rbp+57h+hKey]; hKey
0x1400dbdd1  test    rcx, rcx
0x1400dbdd4  jz      short loc_1400DBDDC
0x1400dbdd6  call    cs:__imp_RegCloseKey
0x1400dbddc  mov     eax, esi
0x1400dbdde  jmp     loc_1400DBAE7
```
