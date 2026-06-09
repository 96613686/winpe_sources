# HrGetWizardComponentCount(ushort * const,tagXW_COMPONENT_HIERARCHY,ulong *)

- ea: `0x18000c77c`
- end: `0x18000c9a2`
- name: `?HrGetWizardComponentCount@@YAJQEAGW4tagXW_COMPONENT_HIERARCHY@@PEAK@Z`
- size: `550`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f680`
- `0x18001516c`
- `0x180025720`

## callees

- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000c77c`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c872`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c8dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c8dd`

## string_xrefs

- `0x18000c7d2`: `Components`

## pseudocode

```c
__int64 __fastcall HrGetWizardComponentCount(const unsigned __int16 *a1, int a2, DWORD *a3)
{
  int v6; // ebx
  const unsigned __int16 *v7; // r8
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  LSTATUS InfoKeyW; // eax
  PVOID *v11; // rcx
  int v12; // edx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[120]; // [rsp+70h] [rbp-90h] BYREF

  *a3 = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x74u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x74u, L"Components");
  if ( a1 )
  {
    StringCchCatW(SubKey, 0x74u, &qword_18003C618);
    StringCchCatW(SubKey, 0x74u, a1);
    StringCchCatW(SubKey, 0x74u, &qword_18003C618);
    v6 = a2 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        goto LABEL_7;
      v7 = L"Parents";
    }
    else
    {
      v7 = L"Children";
    }
    StringCchCatW(SubKey, 0x74u, v7);
  }
LABEL_7:
  hKey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( !v8 )
  {
    InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, a3, 0, 0, 0, 0, 0, 0, 0);
    v9 = InfoKeyW;
    if ( InfoKeyW > 0 )
      v9 = (unsigned __int16)InfoKeyW | 0x80070000;
    RegCloseKey(hKey);
    goto LABEL_21;
  }
  if ( v8 == 2 )
  {
    v9 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_22;
    v12 = 68;
LABEL_20:
    WPP_SF_SD(
      (unsigned int)v11[2],
      v12,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      v9);
LABEL_21:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_22:
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x10) != 0 )
        WPP_SF_d(v11[2], 70, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v9);
      return v9;
    }
    v12 = 69;
    goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x18000c77c  mov     [rsp-8+arg_8], rbx
0x18000c781  mov     [rsp-8+arg_18], rsi
0x18000c786  push    rbp
0x18000c787  push    rdi
0x18000c788  push    r15
0x18000c78a  lea     rbp, [rsp-70h]
0x18000c78f  sub     rsp, 170h
0x18000c796  mov     rax, cs:__security_cookie
0x18000c79d  xor     rax, rsp
0x18000c7a0  mov     [rbp+80h+var_20], rax
0x18000c7a4  xor     eax, eax
0x18000c7a6  mov     dword ptr [r8], 0
0x18000c7ad  mov     rsi, r8
0x18000c7b0  mov     [rsp+180h+SubKey], ax
0x18000c7b5  mov     ebx, edx
0x18000c7b7  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c7be  mov     rdi, rcx
0x18000c7c1  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000c7c6  lea     r15d, [rax+74h]
0x18000c7ca  mov     edx, r15d; unsigned __int64
0x18000c7cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c7d2  lea     r8, aComponents; "Components"
0x18000c7d9  mov     edx, r15d; unsigned __int64
0x18000c7dc  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000c7e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c7e6  test    rdi, rdi
0x18000c7e9  jz      short loc_18000C84A
0x18000c7eb  lea     r8, qword_18003C618; unsigned __int16 *
0x18000c7f2  mov     edx, r15d; unsigned __int64
0x18000c7f5  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000c7fa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c7ff  mov     r8, rdi; unsigned __int16 *
0x18000c802  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000c807  mov     edx, r15d; unsigned __int64
0x18000c80a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c80f  lea     r8, qword_18003C618; unsigned __int16 *
0x18000c816  mov     edx, r15d; unsigned __int64
0x18000c819  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000c81e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c823  sub     ebx, 1
0x18000c826  jz      short loc_18000C836
0x18000c828  cmp     ebx, 1
0x18000c82b  jnz     short loc_18000C84A
0x18000c82d  lea     r8, aParents; "Parents"
0x18000c834  jmp     short loc_18000C83D
0x18000c836  lea     r8, aChildren; "Children"
0x18000c83d  mov     rdx, r15; unsigned __int64
0x18000c840  lea     rcx, [rsp+180h+SubKey]; unsigned __int16 *
0x18000c845  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c84a  lea     rax, [rsp+180h+hKey]
0x18000c84f  mov     [rsp+180h+hKey], 0
0x18000c858  mov     r9d, 20019h; samDesired
0x18000c85e  mov     [rsp+180h+phkResult], rax; phkResult
0x18000c863  xor     r8d, r8d; ulOptions
0x18000c866  lea     rdx, [rsp+180h+SubKey]; lpSubKey
0x18000c86b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c872  call    cs:__imp_RegOpenKeyExW
0x18000c878  lea     rdi, WPP_GLOBAL_Control
0x18000c87f  mov     ebx, eax
0x18000c881  lea     r15, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000c888  test    eax, eax
0x18000c88a  jnz     short loc_18000C8FF
0x18000c88c  mov     rcx, [rsp+180h+hKey]; hKey
0x18000c891  xor     r9d, r9d; lpReserved
0x18000c894  mov     [rsp+180h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000c89d  xor     r8d, r8d; lpcchClass
0x18000c8a0  mov     [rsp+180h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18000c8a9  xor     edx, edx; lpClass
0x18000c8ab  mov     [rsp+180h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18000c8b4  mov     [rsp+180h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18000c8bd  mov     [rsp+180h+lpcValues], 0; lpcValues
0x18000c8c6  mov     [rsp+180h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18000c8cf  mov     [rsp+180h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18000c8d8  mov     [rsp+180h+phkResult], rsi; lpcSubKeys
0x18000c8dd  call    cs:__imp_RegQueryInfoKeyW
0x18000c8e3  mov     ebx, eax
0x18000c8e5  test    eax, eax
0x18000c8e7  jle     short loc_18000C8F2
0x18000c8e9  movzx   ebx, ax
0x18000c8ec  or      ebx, 80070000h
0x18000c8f2  mov     rcx, [rsp+180h+hKey]; hKey
0x18000c8f7  call    cs:__imp_RegCloseKey
0x18000c8fd  jmp     short loc_18000C956
0x18000c8ff  cmp     eax, 2
0x18000c902  jnz     short loc_18000C91D
0x18000c904  xor     ebx, ebx
0x18000c906  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c90d  cmp     rcx, rdi
0x18000c910  jz      short loc_18000C97C
0x18000c912  test    byte ptr [rcx+1Ch], 10h
0x18000c916  jz      short loc_18000C95D
0x18000c918  lea     edx, [rax+42h]
0x18000c91b  jmp     short loc_18000C941
0x18000c91d  test    eax, eax
0x18000c91f  jle     short loc_18000C92A
0x18000c921  movzx   ebx, ax
0x18000c924  or      ebx, 80070000h
0x18000c92a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c931  cmp     rcx, rdi
0x18000c934  jz      short loc_18000C97C
0x18000c936  test    byte ptr [rcx+1Ch], 4
0x18000c93a  jz      short loc_18000C95D
0x18000c93c  mov     edx, 45h ; 'E'
0x18000c941  mov     rcx, [rcx+10h]
0x18000c945  lea     r9, [rsp+180h+SubKey]
0x18000c94a  mov     r8, r15
0x18000c94d  mov     dword ptr [rsp+180h+phkResult], ebx
0x18000c951  call    WPP_SF_SD
0x18000c956  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c95d  cmp     rcx, rdi
0x18000c960  jz      short loc_18000C97C
0x18000c962  test    byte ptr [rcx+1Ch], 10h
0x18000c966  jz      short loc_18000C97C
0x18000c968  mov     rcx, [rcx+10h]
0x18000c96c  mov     edx, 46h ; 'F'
0x18000c971  mov     r9d, ebx
0x18000c974  mov     r8, r15
0x18000c977  call    WPP_SF_d
0x18000c97c  mov     eax, ebx
0x18000c97e  mov     rcx, [rbp+80h+var_20]
0x18000c982  xor     rcx, rsp; StackCookie
0x18000c985  call    __security_check_cookie
0x18000c98a  lea     r11, [rsp+180h+var_10]
0x18000c992  mov     rbx, [r11+28h]
0x18000c996  mov     rsi, [r11+38h]
0x18000c99a  mov     rsp, r11
0x18000c99d  pop     r15
0x18000c99f  pop     rdi
0x18000c9a0  pop     rbp
0x18000c9a1  retn
```
