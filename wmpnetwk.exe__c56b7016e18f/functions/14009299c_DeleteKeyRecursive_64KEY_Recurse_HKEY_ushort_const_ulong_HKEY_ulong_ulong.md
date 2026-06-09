# DeleteKeyRecursive_64KEY_Recurse(HKEY__ * &,ushort const *,ulong,HKEY__ * *,ulong,ulong &)

- ea: `0x14009299c`
- end: `0x140092e89`
- name: `?DeleteKeyRecursive_64KEY_Recurse@@YAJAEAPEAUHKEY__@@PEBGKPEAPEAU1@KAEAK@Z`
- size: `1261`
- prototype: `__int64 __fastcall(HKEY *, const unsigned __int16 *, unsigned int, HKEY *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, loader_planting`

## callers

- `0x14009287c`
- `0x14009299c`

## callees

- `0x14003e5f4`
- `0x14003f17c`
- `0x140045f20`
- `0x140046020`
- `0x14004639c`
- `0x140047798`
- `0x14005480c`
- `0x14009299c`
- `0x140093ad0`
- `0x140093fcc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140092a50`
- `ADVAPI32!RegOpenKeyExW` at `0x140092a50`
- `ADVAPI32!RegQueryValueExW` at `0x140092bc9`
- `ADVAPI32!RegQueryValueExW` at `0x140092bc9`
- `ADVAPI32!RegEnumKeyExW` at `0x140092d87`
- `ADVAPI32!RegEnumKeyExW` at `0x140092df0`
- `ADVAPI32!RegEnumKeyExW` at `0x140092d87`
- `ADVAPI32!RegEnumKeyExW` at `0x140092df0`
- `KERNEL32!RegQueryInfoKeyW` at `0x140092d2d`
- `KERNEL32!RegQueryInfoKeyW` at `0x140092d2d`
- `KERNEL32!RegDeleteKeyExW` at `0x140092e18`
- `KERNEL32!RegDeleteKeyExW` at `0x140092e18`
- `ntdll!NtQueryKey` at `0x140092adf`
- `ntdll!NtQueryKey` at `0x140092adf`
- `ntdll!NtDeleteKey` at `0x140092c3d`
- `ntdll!NtDeleteKey` at `0x140092c3d`

## string_xrefs

- `0x140092bb1`: `SymbolicLinkValue`

## pseudocode

```c
__int64 __fastcall DeleteKeyRecursive_64KEY_Recurse(
        HKEY *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        HKEY *a4,
        unsigned int a5,
        unsigned int *a6)
{
  PVOID *v10; // r10
  unsigned int v11; // ebx
  HKEY v12; // rcx
  int v13; // r8d
  unsigned int v14; // edx
  unsigned int v15; // ecx
  unsigned int v16; // eax
  DWORD v17; // eax
  BYTE *v18; // rdi
  unsigned int v19; // eax
  int v20; // edi
  unsigned int v21; // ecx
  __int64 v22; // rdx
  WCHAR *v23; // rdi
  HKEY *v24; // r13
  DWORD cbData; // [rsp+60h] [rbp-39h] BYREF
  DWORD Type; // [rsp+64h] [rbp-35h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-31h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp-29h] BYREF
  HKEY *v30; // [rsp+78h] [rbp-21h]
  __int64 KeyInformation; // [rsp+80h] [rbp-19h] BYREF
  int v32; // [rsp+88h] [rbp-11h]

  v30 = a4;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qSDdd(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (unsigned int)*a1, (__int64)a2, a3);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = 4;
  if ( *a6 >= 0x100 )
    goto LABEL_60;
  v12 = *a1;
  hKey = 0;
  v11 = RegOpenKeyExW(v12, a2, 8u, a3 | 0xF003F, &hKey);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v14 = *((unsigned __int8 *)WPP_GLOBAL_Control + 25);
    v15 = 5;
    if ( v11 )
      v15 = 2;
    if ( v14 >= v15 )
    {
      WPP_SF_DqS(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v13, v11, (char)*a1, (__int64)a2);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v11 )
    goto LABEL_60;
  a4[(*a6)++] = hKey;
  KeyInformation = 0;
  v32 = 0;
  ResultLength = 0;
  v11 = NtQueryKey(hKey, KeyFlagsInformation, &KeyInformation, 0xCu, &ResultLength);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v16 = 5;
    if ( v11 )
      v16 = 2;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v16 )
    {
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, v11, hKey);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( (v11 & 0x80000000) != 0 )
    goto LABEL_60;
  if ( (KeyInformation & 0x200000000LL) == 0 )
  {
    Type = 0;
    v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &Type, 0, 0, 0, 0, 0, 0);
    if ( !v11 )
    {
      cbData = Type + 1;
      v23 = (WCHAR *)operator new[](saturated_mul(Type + 1, 2u));
      v11 = RegEnumKeyExW(hKey, 0, v23, &cbData, 0, 0, 0, 0);
      if ( !v11 )
      {
        v24 = v30;
        do
        {
          v23[cbData] = 0;
          v11 = DeleteKeyRecursive_64KEY_Recurse(&hKey, v23, a3, v24, 0x100u, a6);
          if ( v11 )
            break;
          cbData = Type + 1;
          v11 = RegEnumKeyExW(hKey, 0, v23, &cbData, 0, 0, 0, 0);
        }
        while ( !v11 );
      }
      operator delete(v23);
      if ( v11 == 259 )
        v11 = RegDeleteKeyExW(*a1, a2, a3, 0);
    }
    goto LABEL_59;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_(v10[2], 92, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids);
  v17 = 128;
  Type = 0;
  for ( cbData = 128; ; v17 = cbData )
  {
    v18 = (BYTE *)operator new[](saturated_mul((v17 >> 1) + 1, 2u));
    v11 = RegQueryValueExW(hKey, L"SymbolicLinkValue", 0, &Type, v18, &cbData);
    if ( !v11 && Type == 6 && (cbData & 1) == 0 )
    {
      *(_WORD *)&v18[2 * ((unsigned __int64)cbData >> 1)] = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, v18);
      }
    }
    operator delete(v18);
    if ( v11 != 234 )
      break;
  }
  if ( v11 )
  {
LABEL_59:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_60;
  }
  v19 = NtDeleteKey(hKey);
  v20 = v19;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v21 = 5;
    if ( v19 )
      v21 = 2;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v21 )
    {
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, v19, hKey);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v20 < 0 )
  {
    v11 = v20;
    if ( v10 == &WPP_GLOBAL_Control )
      return v11;
    if ( (*((_BYTE *)v10 + 28) & 2) == 0 || *((_BYTE *)v10 + 25) < 4u )
      goto LABEL_60;
    v22 = 96;
    goto LABEL_47;
  }
  if ( v10 == &WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 4u )
  {
    v22 = 95;
LABEL_47:
    WPP_SF_(v10[2], v22, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids);
    goto LABEL_59;
  }
LABEL_60:
  if ( v10 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v10 + 28) & 1) != 0
    && *((unsigned __int8 *)v10 + 25) >= (unsigned int)(v11 != 0 ? 2 : 5) )
  {
    WPP_SF_d(v10[2], 97, &WPP_92b3b3424e563441648ef2499742b7fb_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x14009299c  push    rbp
0x14009299e  push    rbx
0x14009299f  push    rsi
0x1400929a0  push    rdi
0x1400929a1  push    r12
0x1400929a3  push    r13
0x1400929a5  push    r14
0x1400929a7  push    r15
0x1400929a9  lea     rbp, [rsp-0Fh]
0x1400929ae  sub     rsp, 0A8h
0x1400929b5  mov     rax, cs:__security_cookie
0x1400929bc  xor     rax, rsp
0x1400929bf  mov     [rbp+47h+var_50], rax
0x1400929c3  mov     rsi, [rbp+47h+arg_28]
0x1400929c7  mov     rdi, r9
0x1400929ca  mov     [rbp+47h+var_68], r9
0x1400929ce  mov     r12d, r8d
0x1400929d1  mov     r15, rdx
0x1400929d4  mov     r14, rcx
0x1400929d7  mov     r10, cs:WPP_GLOBAL_Control
0x1400929de  lea     rax, WPP_GLOBAL_Control
0x1400929e5  cmp     r10, rax
0x1400929e8  jz      short loc_140092A1B
0x1400929ea  test    byte ptr [r10+1Ch], 1
0x1400929ef  jz      short loc_140092A1B
0x1400929f1  cmp     byte ptr [r10+19h], 5
0x1400929f6  jb      short loc_140092A1B
0x1400929f8  mov     eax, [rsi]
0x1400929fa  mov     r9, [rcx]
0x1400929fd  mov     rcx, [r10+10h]
0x140092a01  mov     dword ptr [rsp+0E0h+lpcValues], eax
0x140092a05  mov     dword ptr [rsp+0E0h+lpcbData], r8d
0x140092a0a  mov     [rsp+0E0h+phkResult], rdx
0x140092a0f  call    WPP_SF_qSDdd
0x140092a14  mov     r10, cs:WPP_GLOBAL_Control
0x140092a1b  cmp     dword ptr [rsi], 100h
0x140092a21  mov     ebx, 4
0x140092a26  jnb     loc_140092E27
0x140092a2c  mov     rcx, [r14]; hKey
0x140092a2f  lea     rax, [rbp+47h+hKey]
0x140092a33  mov     r9d, r12d
0x140092a36  mov     [rsp+0E0h+phkResult], rax; phkResult
0x140092a3b  xor     r13d, r13d
0x140092a3e  lea     r8d, [rbx+4]; ulOptions
0x140092a42  or      r9d, 0F003Fh; samDesired
0x140092a49  mov     [rbp+47h+hKey], r13
0x140092a4d  mov     rdx, r15; lpSubKey
0x140092a50  call    cs:__imp_RegOpenKeyExW
0x140092a56  mov     ebx, eax
0x140092a58  mov     r10, cs:WPP_GLOBAL_Control
0x140092a5f  lea     rcx, WPP_GLOBAL_Control
0x140092a66  lea     eax, [r13+2]
0x140092a6a  cmp     r10, rcx
0x140092a6d  jz      short loc_140092AA6
0x140092a6f  test    [r10+1Ch], al
0x140092a73  jz      short loc_140092AA6
0x140092a75  movzx   edx, byte ptr [r10+19h]
0x140092a7a  lea     ecx, [rax+3]
0x140092a7d  test    ebx, ebx
0x140092a7f  cmovnz  ecx, eax
0x140092a82  cmp     edx, ecx
0x140092a84  jb      short loc_140092AA6
0x140092a86  mov     rax, [r14]
0x140092a89  mov     r9d, ebx
0x140092a8c  mov     rcx, [r10+10h]
0x140092a90  mov     [rsp+0E0h+lpcbData], r15
0x140092a95  mov     [rsp+0E0h+phkResult], rax
0x140092a9a  call    WPP_SF_DqS
0x140092a9f  mov     r10, cs:WPP_GLOBAL_Control
0x140092aa6  test    ebx, ebx
0x140092aa8  jnz     loc_140092E27
0x140092aae  mov     ecx, [rsi]
0x140092ab0  lea     r9d, [rbx+0Ch]; Length
0x140092ab4  mov     rax, [rbp+47h+hKey]
0x140092ab8  lea     r8, [rbp+47h+KeyInformation]; KeyInformation
0x140092abc  lea     edx, [rbx+5]; KeyInformationClass
0x140092abf  mov     [rdi+rcx*8], rax
0x140092ac3  xor     eax, eax
0x140092ac5  inc     dword ptr [rsi]
0x140092ac7  mov     rcx, [rbp+47h+hKey]; KeyHandle
0x140092acb  mov     [rbp+47h+KeyInformation], rax
0x140092acf  mov     [rbp+47h+var_58], eax
0x140092ad2  lea     rax, [rbp+47h+ResultLength]
0x140092ad6  mov     [rsp+0E0h+phkResult], rax; ResultLength
0x140092adb  mov     [rbp+47h+ResultLength], r13d
0x140092adf  call    cs:__imp_NtQueryKey
0x140092ae5  mov     ebx, eax
0x140092ae7  mov     r10, cs:WPP_GLOBAL_Control
0x140092aee  lea     rax, WPP_GLOBAL_Control
0x140092af5  mov     edi, 2
0x140092afa  cmp     r10, rax
0x140092afd  jz      short loc_140092B3C
0x140092aff  test    [r10+1Ch], dil
0x140092b03  jz      short loc_140092B3C
0x140092b05  movzx   ecx, byte ptr [r10+19h]
0x140092b0a  lea     eax, [rdi+3]
0x140092b0d  test    ebx, ebx
0x140092b0f  cmovnz  eax, edi
0x140092b12  cmp     ecx, eax
0x140092b14  jb      short loc_140092B3C
0x140092b16  mov     rax, [rbp+47h+hKey]
0x140092b1a  lea     edx, [rdi+59h]
0x140092b1d  mov     rcx, [r10+10h]
0x140092b21  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x140092b28  mov     r9d, ebx
0x140092b2b  mov     [rsp+0E0h+phkResult], rax
0x140092b30  call    WPP_SF_dq
0x140092b35  mov     r10, cs:WPP_GLOBAL_Control
0x140092b3c  test    ebx, ebx
0x140092b3e  js      loc_140092E27
0x140092b44  test    byte ptr [rbp+47h+KeyInformation+4], dil
0x140092b48  jz      loc_140092CF1
0x140092b4e  lea     r14, WPP_GLOBAL_Control
0x140092b55  mov     esi, 2
0x140092b5a  cmp     r10, r14
0x140092b5d  jz      short loc_140092B7F
0x140092b5f  test    [r10+1Ch], sil
0x140092b63  jz      short loc_140092B7F
0x140092b65  cmp     byte ptr [r10+19h], 4
0x140092b6a  jb      short loc_140092B7F
0x140092b6c  mov     rcx, [r10+10h]
0x140092b70  lea     edx, [rsi+5Ah]
0x140092b73  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x140092b7a  call    WPP_SF_
0x140092b7f  mov     eax, 80h
0x140092b84  mov     [rbp+47h+Type], r13d
0x140092b88  mov     [rbp+47h+cbData], eax
0x140092b8b  or      r13, 0FFFFFFFFFFFFFFFFh
0x140092b8f  shr     eax, 1
0x140092b91  lea     ecx, [rax+1]
0x140092b94  mov     rax, rsi
0x140092b97  mul     rcx
0x140092b9a  cmovb   rax, r13
0x140092b9e  mov     rcx, rax; unsigned __int64
0x140092ba1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140092ba6  mov     rcx, [rbp+47h+hKey]; hKey
0x140092baa  lea     r9, [rbp+47h+Type]; lpType
0x140092bae  mov     rdi, rax
0x140092bb1  lea     rdx, ValueName; "SymbolicLinkValue"
0x140092bb8  lea     rax, [rbp+47h+cbData]
0x140092bbc  xor     r8d, r8d; lpReserved
0x140092bbf  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x140092bc4  mov     [rsp+0E0h+phkResult], rdi; lpData
0x140092bc9  call    cs:__imp_RegQueryValueExW
0x140092bcf  mov     ebx, eax
0x140092bd1  test    eax, eax
0x140092bd3  jnz     short loc_140092C19
0x140092bd5  cmp     [rbp+47h+Type], 6
0x140092bd9  jnz     short loc_140092C19
0x140092bdb  test    byte ptr [rbp+47h+cbData], 1
0x140092bdf  jnz     short loc_140092C19
0x140092be1  mov     ecx, [rbp+47h+cbData]
0x140092be4  shr     rcx, 1
0x140092be7  mov     [rdi+rcx*2], ax
0x140092beb  mov     rcx, cs:WPP_GLOBAL_Control
0x140092bf2  cmp     rcx, r14
0x140092bf5  jz      short loc_140092C19
0x140092bf7  test    [rcx+1Ch], sil
0x140092bfb  jz      short loc_140092C19
0x140092bfd  cmp     byte ptr [rcx+19h], 4
0x140092c01  jb      short loc_140092C19
0x140092c03  mov     rcx, [rcx+10h]
0x140092c07  lea     edx, [rax+5Dh]
0x140092c0a  mov     r9, rdi
0x140092c0d  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x140092c14  call    WPP_SF_S
0x140092c19  mov     rcx, rdi; Block
0x140092c1c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140092c21  cmp     ebx, 0EAh
0x140092c27  jnz     short loc_140092C31
0x140092c29  mov     eax, [rbp+47h+cbData]
0x140092c2c  jmp     loc_140092B8F
0x140092c31  test    ebx, ebx
0x140092c33  jnz     loc_140092E20
0x140092c39  mov     rcx, [rbp+47h+hKey]; KeyHandle
0x140092c3d  call    cs:__imp_NtDeleteKey
0x140092c43  mov     edi, eax
0x140092c45  mov     r10, cs:WPP_GLOBAL_Control
0x140092c4c  cmp     r10, r14
0x140092c4f  jz      short loc_140092C8E
0x140092c51  test    [r10+1Ch], sil
0x140092c55  jz      short loc_140092C8E
0x140092c57  movzx   edx, byte ptr [r10+19h]
0x140092c5c  lea     ecx, [rbx+5]
0x140092c5f  test    eax, eax
0x140092c61  cmovnz  ecx, esi
0x140092c64  cmp     edx, ecx
0x140092c66  jb      short loc_140092C8E
0x140092c68  mov     rax, [rbp+47h+hKey]
0x140092c6c  lea     edx, [rbx+5Eh]
0x140092c6f  mov     rcx, [r10+10h]
0x140092c73  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x140092c7a  mov     r9d, edi
0x140092c7d  mov     [rsp+0E0h+phkResult], rax
0x140092c82  call    WPP_SF_dq
0x140092c87  mov     r10, cs:WPP_GLOBAL_Control
0x140092c8e  test    edi, edi
0x140092c90  js      short loc_140092CCA
0x140092c92  cmp     r10, r14
0x140092c95  jz      loc_140092E67
0x140092c9b  test    [r10+1Ch], sil
0x140092c9f  jz      loc_140092E27
0x140092ca5  cmp     byte ptr [r10+19h], 4
0x140092caa  jb      loc_140092E27
0x140092cb0  mov     edx, 5Fh ; '_'
0x140092cb5  mov     rcx, [r10+10h]
0x140092cb9  lea     r8, WPP_92b3b3424e563441648ef2499742b7fb_Traceguids
0x140092cc0  call    WPP_SF_
0x140092cc5  jmp     loc_140092E20
0x140092cca  mov     ebx, edi
0x140092ccc  cmp     r10, r14
0x140092ccf  jz      loc_140092E67
0x140092cd5  test    [r10+1Ch], sil
0x140092cd9  jz      loc_140092E27
0x140092cdf  cmp     byte ptr [r10+19h], 4
0x140092ce4  jb      loc_140092E27
0x140092cea  mov     edx, 60h ; '`'
0x140092cef  jmp     short loc_140092CB5
0x140092cf1  mov     rcx, [rbp+47h+hKey]; hKey
0x140092cf5  lea     rax, [rbp+47h+Type]
0x140092cf9  mov     [rsp+0E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x140092cfe  xor     r9d, r9d; lpReserved
0x140092d01  mov     [rsp+0E0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140092d06  xor     r8d, r8d; lpcchClass
0x140092d09  mov     [rsp+0E0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x140092d0e  xor     edx, edx; lpClass
0x140092d10  mov     [rsp+0E0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x140092d15  mov     [rsp+0E0h+lpcValues], r13; lpcValues
0x140092d1a  mov     [rsp+0E0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x140092d1f  mov     [rsp+0E0h+lpcbData], rax; lpcbMaxSubKeyLen
0x140092d24  mov     [rsp+0E0h+phkResult], r13; lpcSubKeys
0x140092d29  mov     [rbp+47h+Type], r13d
0x140092d2d  call    cs:__imp_RegQueryInfoKeyW
0x140092d33  mov     ebx, eax
0x140092d35  test    eax, eax
0x140092d37  jnz     loc_140092E20
0x140092d3d  mov     ecx, [rbp+47h+Type]
0x140092d40  mov     rax, rdi
0x140092d43  inc     ecx
0x140092d45  mov     r13, 0FFFFFFFFFFFFFFFFh
0x140092d4c  mov     edx, ecx
0x140092d4e  mul     rdx
0x140092d51  mov     [rbp+47h+cbData], ecx
0x140092d54  cmovb   rax, r13
0x140092d58  mov     rcx, rax; unsigned __int64
0x140092d5b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140092d60  mov     rcx, [rbp+47h+hKey]; hKey
0x140092d64  lea     r9, [rbp+47h+cbData]; lpcchName
0x140092d68  xor     r13d, r13d
0x140092d6b  mov     r8, rax; lpName
0x140092d6e  mov     [rsp+0E0h+lpcValues], r13; lpftLastWriteTime
0x140092d73  xor     edx, edx; dwIndex
0x140092d75  mov     [rsp+0E0h+lpcbMaxClassLen], r13; lpcchClass
0x140092d7a  mov     rdi, rax
0x140092d7d  mov     [rsp+0E0h+lpcbData], r13; lpClass
0x140092d82  mov     [rsp+0E0h+phkResult], r13; lpReserved
0x140092d87  call    cs:__imp_RegEnumKeyExW
0x140092d8d  mov     ebx, eax
0x140092d8f  test    eax, eax
0x140092d91  jnz     short loc_140092DFC
0x140092d93  mov     r13, [rbp+47h+var_68]
0x140092d97  mov     ecx, [rbp+47h+cbData]
0x140092d9a  xor     eax, eax
0x140092d9c  mov     [rsp+0E0h+lpcbData], rsi; unsigned int *
0x140092da1  mov     r9, r13; HKEY *
0x140092da4  mov     r8d, r12d; unsigned int
0x140092da7  mov     dword ptr [rsp+0E0h+phkResult], 100h; unsigned int
0x140092daf  mov     rdx, rdi; unsigned __int16 *
0x140092db2  mov     [rdi+rcx*2], ax
0x140092db6  lea     rcx, [rbp+47h+hKey]; HKEY *
0x140092dba  call    ?DeleteKeyRecursive_64KEY_Recurse@@YAJAEAPEAUHKEY__@@PEBGKPEAPEAU1@KAEAK@Z; DeleteKeyRecursive_64KEY_Recurse(HKEY__ * &,ushort const *,ulong,HKEY__ * *,ulong,ulong &)
0x140092dbf  xor     ecx, ecx
0x140092dc1  mov     ebx, eax
0x140092dc3  test    eax, eax
0x140092dc5  jnz     short loc_140092DFC
0x140092dc7  mov     eax, [rbp+47h+Type]
0x140092dca  lea     r9, [rbp+47h+cbData]; lpcchName
0x140092dce  mov     [rsp+0E0h+lpcValues], rcx; lpftLastWriteTime
0x140092dd3  inc     eax
0x140092dd5  mov     [rsp+0E0h+lpcbMaxClassLen], rcx; lpcchClass
0x140092dda  mov     r8, rdi; lpName
0x140092ddd  mov     [rsp+0E0h+lpcbData], rcx; lpClass
0x140092de2  xor     edx, edx; dwIndex
0x140092de4  mov     [rsp+0E0h+phkResult], rcx; lpReserved
0x140092de9  mov     rcx, [rbp+47h+hKey]; hKey
0x140092ded  mov     [rbp+47h+cbData], eax
0x140092df0  call    cs:__imp_RegEnumKeyExW
0x140092df6  mov     ebx, eax
0x140092df8  test    eax, eax
0x140092dfa  jz      short loc_140092D97
0x140092dfc  mov     rcx, rdi; Block
0x140092dff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140092e04  cmp     ebx, 103h
0x140092e0a  jnz     short loc_140092E20
0x140092e0c  mov     rcx, [r14]; hKey
0x140092e0f  xor     r9d, r9d; Reserved
0x140092e12  mov     r8d, r12d; samDesired
0x140092e15  mov     rdx, r15; lpSubKey
0x140092e18  call    cs:__imp_RegDeleteKeyExW
0x140092e1e  mov     ebx, eax
  ... truncated ...
```
