# HrEnumSubkeyComponent(HKEY__ * const,ulong * const,int,tagXW_COMPONENT_TYPE,ulong,_GUID *)

- ea: `0x18000e950`
- end: `0x18000edd2`
- name: `?HrEnumSubkeyComponent@@YAJQEAUHKEY__@@QEAKHW4tagXW_COMPONENT_TYPE@@KPEAU_GUID@@@Z`
- size: `1154`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000edd8`

## callees

- `0x18000ae04`
- `0x18000ae90`
- `0x18000e950`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec18`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ea1f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ea1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ea9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eb07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eb77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ea9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eb07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eb77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ea52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ea52`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ed2d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ed2d`

## string_xrefs

- `0x18000eb59`: `Wrapped CLSID`

## pseudocode

```c
__int64 __fastcall HrEnumSubkeyComponent(HKEY a1, _DWORD *a2, int a3, int a4, int a5, GUID *pclsid)
{
  signed int v8; // ebx
  bool v9; // zf
  int v10; // esi
  DWORD v11; // edi
  int v12; // r13d
  int v13; // r15d
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  DWORD v17; // eax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  PVOID *v20; // rcx
  PVOID *v21; // rcx
  int v22; // edx
  const OLECHAR *v23; // rcx
  HRESULT v24; // eax
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  BYTE v29[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  int v30; // [rsp+50h] [rbp-B0h]
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v33; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h]
  struct _FILETIME ftLastWriteTime; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v36; // [rsp+78h] [rbp-88h]
  WCHAR Name[40]; // [rsp+80h] [rbp-80h] BYREF
  BYTE v38[80]; // [rsp+D0h] [rbp-30h] BYREF

  v28 = a3;
  v36 = a2;
  hKey = a1;
  memset_0(Name, 0, sizeof(Name));
  memset_0(v38, 0, sizeof(v38));
  v8 = 0;
  ftLastWriteTime = 0;
  v9 = *a2 == 0;
  v30 = 0;
  v10 = 1;
  if ( !v9 )
    v10 = *a2;
LABEL_3:
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( !v28 )
    v11 = v10 - 1;
  while ( 1 )
  {
    cchName = 40;
    v14 = RegEnumKeyExW(hKey, v11, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( v14 )
    {
      if ( v14 == 259 )
      {
        v8 = 1;
        v21 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
            (unsigned int)Name,
            1);
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_59:
        if ( v12 )
          goto LABEL_3;
        goto LABEL_69;
      }
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      else
        v8 = v14;
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v22 = 14;
LABEL_49:
        WPP_SF_SD(
          (unsigned int)v21[2],
          v22,
          (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
          (unsigned int)Name,
          v8);
LABEL_50:
        v21 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      phkResult = 0;
      v15 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
      if ( !v15 )
      {
        *(_DWORD *)Data = 0;
        *(_DWORD *)v29 = 0;
        cbData = 4;
        if ( v28 )
        {
          v16 = RegQueryValueExW(phkResult, L"Ordinal", 0, 0, Data, &cbData);
          v8 = v16;
          if ( v16 > 0 )
            v8 = (unsigned __int16)v16 | 0x80070000;
          v17 = *(_DWORD *)Data;
        }
        else
        {
          v17 = v11 + 1;
          *(_DWORD *)Data = v11 + 1;
        }
        if ( v8 < 0 )
          goto LABEL_31;
        if ( v17 != v10 )
        {
LABEL_35:
          RegCloseKey(phkResult);
          goto LABEL_50;
        }
        v12 = 1;
        if ( a4 )
        {
          cbData = 4;
          v18 = RegQueryValueExW(phkResult, L"Class Type", 0, 0, v29, &cbData);
          v8 = v18;
          if ( v18 > 0 )
            v8 = (unsigned __int16)v18 | 0x80070000;
          if ( v8 < 0 )
            goto LABEL_31;
          if ( *(_DWORD *)v29 != a4 )
          {
            ++v10;
            v8 = 1;
            goto LABEL_35;
          }
        }
        v13 = 1;
        if ( a5 != 1 )
          goto LABEL_35;
        v33 = 80;
        v19 = RegQueryValueExW(phkResult, L"Wrapped CLSID", 0, 0, v38, &v33);
        v8 = v19;
        if ( v19 > 0 )
          v8 = (unsigned __int16)v19 | 0x80070000;
        if ( !v8 )
        {
          v30 = 1;
          goto LABEL_35;
        }
        if ( v8 == -2147024894 )
        {
          v8 = 0;
          goto LABEL_35;
        }
        if ( v8 >= 0 )
          goto LABEL_35;
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_35;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
LABEL_32:
          if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 4) != 0 )
            WPP_SF_SD(
              (unsigned int)v20[2],
              11,
              (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
              (unsigned int)Name,
              v8);
          goto LABEL_35;
        }
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
          (unsigned int)Name,
          v8);
LABEL_31:
        v20 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_32;
      }
      if ( v15 > 0 )
        v8 = (unsigned __int16)v15 | 0x80070000;
      else
        v8 = v15;
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v22 = 12;
        goto LABEL_49;
      }
    }
    if ( v8 )
    {
      if ( v8 != 1 )
        goto LABEL_69;
      goto LABEL_59;
    }
    if ( v13 )
      break;
    ++v11;
  }
  *v36 = v10 + 1;
  if ( !pclsid )
    goto LABEL_68;
  v23 = (const OLECHAR *)v38;
  if ( !v30 )
    v23 = Name;
  v24 = CLSIDFromString(v23, pclsid);
  v8 = v24;
  if ( v24 < 0 )
  {
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
        (unsigned int)Name,
        v24);
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
LABEL_68:
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_69:
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 0x10) != 0 )
    WPP_SF_d(v21[2], 16, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000e950  mov     [rsp-8+arg_10], rbx
0x18000e955  push    rbp
0x18000e956  push    rsi
0x18000e957  push    rdi
0x18000e958  push    r12
0x18000e95a  push    r13
0x18000e95c  push    r14
0x18000e95e  push    r15
0x18000e960  lea     rbp, [rsp-30h]
0x18000e965  sub     rsp, 130h
0x18000e96c  mov     rax, cs:__security_cookie
0x18000e973  xor     rax, rsp
0x18000e976  mov     [rbp+60h+var_40], rax
0x18000e97a  mov     r14, [rbp+60h+pclsid]
0x18000e981  mov     rdi, rdx
0x18000e984  mov     [rsp+160h+var_118], r8d
0x18000e989  mov     ebx, 50h ; 'P'
0x18000e98e  mov     [rsp+160h+var_E8], rdx
0x18000e993  mov     r8d, ebx; Size
0x18000e996  mov     [rsp+160h+hKey], rcx
0x18000e99b  xor     edx, edx; Val
0x18000e99d  lea     rcx, [rbp+60h+Name]; void *
0x18000e9a1  mov     r12d, r9d
0x18000e9a4  call    memset_0
0x18000e9a9  mov     r8d, ebx; Size
0x18000e9ac  lea     rcx, [rbp+60h+var_90]; void *
0x18000e9b0  xor     edx, edx; Val
0x18000e9b2  call    memset_0
0x18000e9b7  xor     ebx, ebx
0x18000e9b9  mov     qword ptr [rsp+160h+ftLastWriteTime.dwLowDateTime], 0
0x18000e9c2  xor     eax, eax
0x18000e9c4  cmp     [rdi], eax
0x18000e9c6  mov     [rsp+160h+var_110], eax
0x18000e9ca  lea     esi, [rbx+1]
0x18000e9cd  cmovnz  esi, [rdi]
0x18000e9d0  xor     edi, edi
0x18000e9d2  lea     eax, [rsi-1]
0x18000e9d5  xor     r13d, r13d
0x18000e9d8  xor     r15d, r15d
0x18000e9db  cmp     [rsp+160h+var_118], edi
0x18000e9df  cmovz   edi, eax
0x18000e9e2  mov     rcx, [rsp+160h+hKey]; hKey
0x18000e9e7  lea     rax, [rsp+160h+ftLastWriteTime]
0x18000e9ec  mov     [rsp+160h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000e9f1  lea     r9, [rsp+160h+cchName]; lpcchName
0x18000e9f6  mov     [rsp+160h+lpcchClass], 0; lpcchClass
0x18000e9ff  lea     r8, [rbp+60h+Name]; lpName
0x18000ea03  mov     [rsp+160h+lpClass], 0; lpClass
0x18000ea0c  mov     edx, edi; dwIndex
0x18000ea0e  mov     [rsp+160h+lpReserved], 0; lpReserved
0x18000ea17  mov     [rsp+160h+cchName], 28h ; '('
0x18000ea1f  call    cs:__imp_RegEnumKeyExW
0x18000ea25  test    eax, eax
0x18000ea27  jnz     loc_18000EC4F
0x18000ea2d  mov     rcx, [rsp+160h+hKey]; hKey
0x18000ea32  lea     rax, [rsp+160h+phkResult]
0x18000ea37  mov     r9d, 20019h; samDesired
0x18000ea3d  mov     [rsp+160h+lpReserved], rax; phkResult
0x18000ea42  xor     r8d, r8d; ulOptions
0x18000ea45  mov     [rsp+160h+phkResult], 0
0x18000ea4e  lea     rdx, [rbp+60h+Name]; lpSubKey
0x18000ea52  call    cs:__imp_RegOpenKeyExW
0x18000ea58  test    eax, eax
0x18000ea5a  jnz     loc_18000EC20
0x18000ea60  mov     dword ptr [rsp+160h+Data], eax
0x18000ea64  mov     dword ptr [rsp+160h+var_114], eax
0x18000ea68  mov     [rsp+160h+cbData], 4
0x18000ea70  cmp     [rsp+160h+var_118], eax
0x18000ea74  jz      short loc_18000EAB7
0x18000ea76  mov     rcx, [rsp+160h+phkResult]; hKey
0x18000ea7b  lea     rax, [rsp+160h+cbData]
0x18000ea80  mov     [rsp+160h+lpClass], rax; lpcbData
0x18000ea85  lea     rdx, aOrdinal; "Ordinal"
0x18000ea8c  lea     rax, [rsp+160h+Data]
0x18000ea91  xor     r9d, r9d; lpType
0x18000ea94  xor     r8d, r8d; lpReserved
0x18000ea97  mov     [rsp+160h+lpReserved], rax; lpData
0x18000ea9c  call    cs:__imp_RegQueryValueExW
0x18000eaa2  mov     ebx, eax
0x18000eaa4  test    eax, eax
0x18000eaa6  jle     short loc_18000EAB1
0x18000eaa8  movzx   ebx, ax
0x18000eaab  or      ebx, 80070000h
0x18000eab1  mov     eax, dword ptr [rsp+160h+Data]
0x18000eab5  jmp     short loc_18000EABE
0x18000eab7  lea     eax, [rdi+1]
0x18000eaba  mov     dword ptr [rsp+160h+Data], eax
0x18000eabe  test    ebx, ebx
0x18000eac0  js      loc_18000EBDD
0x18000eac6  cmp     eax, esi
0x18000eac8  jnz     loc_18000EC13
0x18000eace  mov     r13d, 1
0x18000ead4  test    r12d, r12d
0x18000ead7  jz      short loc_18000EB3A
0x18000ead9  mov     rcx, [rsp+160h+phkResult]; hKey
0x18000eade  lea     rax, [rsp+160h+cbData]
0x18000eae3  mov     [rsp+160h+lpClass], rax; lpcbData
0x18000eae8  lea     rdx, aClassType_1; "Class Type"
0x18000eaef  lea     rax, [rsp+160h+var_114]
0x18000eaf4  mov     [rsp+160h+cbData], 4
0x18000eafc  xor     r9d, r9d; lpType
0x18000eaff  mov     [rsp+160h+lpReserved], rax; lpData
0x18000eb04  xor     r8d, r8d; lpReserved
0x18000eb07  call    cs:__imp_RegQueryValueExW
0x18000eb0d  mov     ebx, eax
0x18000eb0f  test    eax, eax
0x18000eb11  jle     short loc_18000EB1C
0x18000eb13  movzx   ebx, ax
0x18000eb16  or      ebx, 80070000h
0x18000eb1c  test    ebx, ebx
0x18000eb1e  js      loc_18000EBDD
0x18000eb24  test    r12d, r12d
0x18000eb27  jz      short loc_18000EB3A
0x18000eb29  cmp     dword ptr [rsp+160h+var_114], r12d
0x18000eb2e  jz      short loc_18000EB3A
0x18000eb30  inc     esi
0x18000eb32  mov     ebx, r13d
0x18000eb35  jmp     loc_18000EC13
0x18000eb3a  mov     r15d, r13d
0x18000eb3d  cmp     [rbp+60h+arg_20], r13d
0x18000eb44  jnz     loc_18000EC13
0x18000eb4a  mov     rcx, [rsp+160h+phkResult]; hKey
0x18000eb4f  lea     rax, [rsp+160h+var_FC]
0x18000eb54  mov     [rsp+160h+lpClass], rax; lpcbData
0x18000eb59  lea     rdx, aWrappedClsid_0; "Wrapped CLSID"
0x18000eb60  lea     rax, [rbp+60h+var_90]
0x18000eb64  mov     [rsp+160h+var_FC], 50h ; 'P'
0x18000eb6c  xor     r9d, r9d; lpType
0x18000eb6f  mov     [rsp+160h+lpReserved], rax; lpData
0x18000eb74  xor     r8d, r8d; lpReserved
0x18000eb77  call    cs:__imp_RegQueryValueExW
0x18000eb7d  mov     ebx, eax
0x18000eb7f  test    eax, eax
0x18000eb81  jle     short loc_18000EB8C
0x18000eb83  movzx   ebx, ax
0x18000eb86  or      ebx, 80070000h
0x18000eb8c  test    ebx, ebx
0x18000eb8e  jnz     short loc_18000EB97
0x18000eb90  mov     [rsp+160h+var_110], r13d
0x18000eb95  jmp     short loc_18000EC13
0x18000eb97  cmp     ebx, 80070002h
0x18000eb9d  jnz     short loc_18000EBA3
0x18000eb9f  xor     ebx, ebx
0x18000eba1  jmp     short loc_18000EC13
0x18000eba3  test    ebx, ebx
0x18000eba5  jns     short loc_18000EC13
0x18000eba7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebae  lea     rax, WPP_GLOBAL_Control
0x18000ebb5  cmp     rcx, rax
0x18000ebb8  jz      short loc_18000EC13
0x18000ebba  test    byte ptr [rcx+1Ch], 4
0x18000ebbe  jz      short loc_18000EBEB
0x18000ebc0  mov     rcx, [rcx+10h]
0x18000ebc4  lea     r9, [rbp+60h+Name]
0x18000ebc8  mov     edx, 0Ah
0x18000ebcd  mov     dword ptr [rsp+160h+lpReserved], ebx
0x18000ebd1  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x18000ebd8  call    WPP_SF_SD
0x18000ebdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebe4  lea     rax, WPP_GLOBAL_Control
0x18000ebeb  cmp     rcx, rax
0x18000ebee  jz      short loc_18000EC13
0x18000ebf0  test    byte ptr [rcx+1Ch], 4
0x18000ebf4  jz      short loc_18000EC13
0x18000ebf6  mov     rcx, [rcx+10h]
0x18000ebfa  lea     r9, [rbp+60h+Name]
0x18000ebfe  mov     edx, 0Bh
0x18000ec03  mov     dword ptr [rsp+160h+lpReserved], ebx
0x18000ec07  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x18000ec0e  call    WPP_SF_SD
0x18000ec13  mov     rcx, [rsp+160h+phkResult]; hKey
0x18000ec18  call    cs:__imp_RegCloseKey
0x18000ec1e  jmp     short loc_18000EC9D
0x18000ec20  jg      short loc_18000EC26
0x18000ec22  mov     ebx, eax
0x18000ec24  jmp     short loc_18000EC2F
0x18000ec26  movzx   ebx, ax
0x18000ec29  or      ebx, 80070000h
0x18000ec2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec36  lea     rax, WPP_GLOBAL_Control
0x18000ec3d  cmp     rcx, rax
0x18000ec40  jz      short loc_18000ECA4
0x18000ec42  test    byte ptr [rcx+1Ch], 4
0x18000ec46  jz      short loc_18000ECA4
0x18000ec48  mov     edx, 0Ch
0x18000ec4d  jmp     short loc_18000EC85
0x18000ec4f  cmp     eax, 103h
0x18000ec54  jz      short loc_18000ECBF
0x18000ec56  test    eax, eax
0x18000ec58  jg      short loc_18000EC5E
0x18000ec5a  mov     ebx, eax
0x18000ec5c  jmp     short loc_18000EC67
0x18000ec5e  movzx   ebx, ax
0x18000ec61  or      ebx, 80070000h
0x18000ec67  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec6e  lea     rax, WPP_GLOBAL_Control
0x18000ec75  cmp     rcx, rax
0x18000ec78  jz      short loc_18000ECA4
0x18000ec7a  test    byte ptr [rcx+1Ch], 4
0x18000ec7e  jz      short loc_18000ECA4
0x18000ec80  mov     edx, 0Eh
0x18000ec85  mov     rcx, [rcx+10h]
0x18000ec89  lea     r9, [rbp+60h+Name]
0x18000ec8d  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x18000ec94  mov     dword ptr [rsp+160h+lpReserved], ebx
0x18000ec98  call    WPP_SF_SD
0x18000ec9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eca4  test    ebx, ebx
0x18000eca6  jnz     short loc_18000ECB4
0x18000eca8  test    r15d, r15d
0x18000ecab  jnz     short loc_18000ED0C
0x18000ecad  inc     edi
0x18000ecaf  jmp     loc_18000E9E2
0x18000ecb4  cmp     ebx, 1
0x18000ecb7  jnz     loc_18000ED7F
0x18000ecbd  jmp     short loc_18000ECFF
0x18000ecbf  mov     ebx, 1
0x18000ecc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eccb  lea     rax, WPP_GLOBAL_Control
0x18000ecd2  cmp     rcx, rax
0x18000ecd5  jz      short loc_18000ECFF
0x18000ecd7  test    byte ptr [rcx+1Ch], 10h
0x18000ecdb  jz      short loc_18000ECFF
0x18000ecdd  mov     rcx, [rcx+10h]
0x18000ece1  lea     edx, [rbx+0Ch]
0x18000ece4  lea     r9, [rbp+60h+Name]
0x18000ece8  mov     dword ptr [rsp+160h+lpReserved], ebx
0x18000ecec  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x18000ecf3  call    WPP_SF_SD
0x18000ecf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecff  test    r13d, r13d
0x18000ed02  jnz     loc_18000E9D0
0x18000ed08  test    ebx, ebx
0x18000ed0a  jnz     short loc_18000ED7F
0x18000ed0c  mov     rcx, [rsp+160h+var_E8]
0x18000ed11  lea     eax, [rsi+1]
0x18000ed14  mov     [rcx], eax
0x18000ed16  test    r14, r14
0x18000ed19  jz      short loc_18000ED78
0x18000ed1b  cmp     [rsp+160h+var_110], 0
0x18000ed20  lea     rcx, [rbp+60h+var_90]
0x18000ed24  mov     rdx, r14; pclsid
0x18000ed27  jnz     short loc_18000ED2D
0x18000ed29  lea     rcx, [rbp+60h+Name]; lpsz
0x18000ed2d  call    cs:__imp_CLSIDFromString
0x18000ed33  mov     ebx, eax
0x18000ed35  test    eax, eax
0x18000ed37  jns     short loc_18000ED78
0x18000ed39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed40  lea     rdi, WPP_GLOBAL_Control
0x18000ed47  cmp     rcx, rdi
0x18000ed4a  jz      short loc_18000EDA9
0x18000ed4c  test    byte ptr [rcx+1Ch], 4
0x18000ed50  jz      short loc_18000ED86
0x18000ed52  mov     rcx, [rcx+10h]
0x18000ed56  lea     r9, [rbp+60h+Name]
0x18000ed5a  mov     edx, 0Fh
0x18000ed5f  mov     dword ptr [rsp+160h+lpReserved], eax
0x18000ed63  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x18000ed6a  call    WPP_SF_SD
0x18000ed6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed76  jmp     short loc_18000ED86
0x18000ed78  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed7f  lea     rdi, WPP_GLOBAL_Control
0x18000ed86  cmp     rcx, rdi
0x18000ed89  jz      short loc_18000EDA9
0x18000ed8b  test    byte ptr [rcx+1Ch], 10h
0x18000ed8f  jz      short loc_18000EDA9
0x18000ed91  mov     rcx, [rcx+10h]
0x18000ed95  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x18000ed9c  mov     edx, 10h
0x18000eda1  mov     r9d, ebx
0x18000eda4  call    WPP_SF_d
0x18000eda9  mov     eax, ebx
0x18000edab  mov     rcx, [rbp+60h+var_40]
0x18000edaf  xor     rcx, rsp; StackCookie
0x18000edb2  call    __security_check_cookie
0x18000edb7  mov     rbx, [rsp+160h+arg_10]
0x18000edbf  add     rsp, 130h
0x18000edc6  pop     r15
0x18000edc8  pop     r14
0x18000edca  pop     r13
0x18000edcc  pop     r12
0x18000edce  pop     rdi
0x18000edcf  pop     rsi
0x18000edd0  pop     rbp
0x18000edd1  retn
```
