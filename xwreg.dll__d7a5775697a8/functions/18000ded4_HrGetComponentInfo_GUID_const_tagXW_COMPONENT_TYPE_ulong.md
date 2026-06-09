# HrGetComponentInfo(_GUID const *,tagXW_COMPONENT_TYPE *,ulong *)

- ea: `0x18000ded4`
- end: `0x18000e139`
- name: `?HrGetComponentInfo@@YAJPEBU_GUID@@PEAW4tagXW_COMPONENT_TYPE@@PEAK@Z`
- size: `613`
- prototype: `__int64 __fastcall(GUID *rguid, enum tagXW_COMPONENT_TYPE *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007aa8`
- `0x180007b28`

## callees

- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ded4`
- `0x180010958`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000df65`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000df65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000df8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000df8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e077`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e077`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dfde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dfde`

## string_xrefs

- `0x18000df34`: `Components`

## pseudocode

```c
__int64 __fastcall HrGetComponentInfo(GUID *rguid, enum tagXW_COMPONENT_TYPE *a2, BYTE *a3)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  int v8; // r8d
  PVOID *v9; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[62]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[50]; // [rsp+BCh] [rbp-44h] BYREF

  if ( a3 )
    *(_DWORD *)a3 = 0;
  hKey = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x69u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x69u, L"Components");
  StringCchCatW(SubKey, 0x69u, &qword_180017630);
  StringFromGUID2(rguid, sz, 39);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( !v5 )
  {
    cbData = 0;
    if ( a3 )
    {
      cbData = 4;
      v7 = RegQueryValueExW(hKey, L"Behavior", 0, 0, a3, &cbData);
      if ( v7 )
      {
        if ( v7 == 2 )
        {
          v6 = 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              96,
              (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
              (unsigned int)SubKey,
              2);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            97,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (unsigned int)SubKey,
            v7);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_Sl(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, v8, (unsigned int)SubKey, *(_DWORD *)a3);
      }
    }
    RegCloseKey(hKey);
    goto LABEL_26;
  }
  if ( v5 == 2 )
  {
    v6 = 1;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_27;
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      98,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      2);
    goto LABEL_26;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_27:
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
        WPP_SF_D(v9[2], 100, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v6);
      return v6;
    }
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      99,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      v6);
LABEL_26:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  return v6;
}

```

## disassembly

```asm
0x18000ded4  mov     [rsp-8+arg_8], rbx
0x18000ded9  mov     [rsp-8+arg_18], rsi
0x18000dede  push    rbp
0x18000dedf  push    rdi
0x18000dee0  push    r15
0x18000dee2  lea     rbp, [rsp-30h]
0x18000dee7  sub     rsp, 130h
0x18000deee  mov     rax, cs:__security_cookie
0x18000def5  xor     rax, rsp
0x18000def8  mov     [rbp+40h+var_20], rax
0x18000defc  mov     rsi, r8
0x18000deff  mov     rbx, rcx
0x18000df02  test    r8, r8
0x18000df05  jz      short loc_18000DF0E
0x18000df07  mov     dword ptr [r8], 0
0x18000df0e  xor     eax, eax
0x18000df10  mov     [rsp+140h+hKey], 0
0x18000df19  lea     r8, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000df20  mov     [rsp+140h+SubKey], ax
0x18000df25  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000df2a  lea     edi, [rax+69h]
0x18000df2d  mov     edx, edi; unsigned __int64
0x18000df2f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000df34  lea     r8, aComponents_0; "Components"
0x18000df3b  mov     edx, edi; unsigned __int64
0x18000df3d  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000df42  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000df47  lea     r8, qword_180017630; unsigned __int16 *
0x18000df4e  mov     edx, edi; unsigned __int64
0x18000df50  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x18000df55  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000df5a  lea     r8d, [rdi-42h]; cchMax
0x18000df5e  mov     rcx, rbx; rguid
0x18000df61  lea     rdx, [rbp+40h+sz]; lpsz
0x18000df65  call    cs:__imp_StringFromGUID2
0x18000df6b  lea     rax, [rsp+140h+hKey]
0x18000df70  mov     r9d, 20019h; samDesired
0x18000df76  xor     r8d, r8d; ulOptions
0x18000df79  mov     [rsp+140h+phkResult], rax; phkResult
0x18000df7e  lea     rdx, [rsp+140h+SubKey]; lpSubKey
0x18000df83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000df8a  call    cs:__imp_RegOpenKeyExW
0x18000df90  lea     r15, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000df97  mov     ebx, eax
0x18000df99  test    eax, eax
0x18000df9b  jnz     loc_18000E07F
0x18000dfa1  mov     [rsp+140h+cbData], eax
0x18000dfa5  lea     rdi, WPP_GLOBAL_Control
0x18000dfac  test    rsi, rsi
0x18000dfaf  jz      loc_18000E072
0x18000dfb5  mov     rcx, [rsp+140h+hKey]; hKey
0x18000dfba  lea     rax, [rsp+140h+cbData]
0x18000dfbf  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18000dfc4  lea     rdx, aBehavior_0; "Behavior"
0x18000dfcb  xor     r9d, r9d; lpType
0x18000dfce  mov     [rsp+140h+phkResult], rsi; lpData
0x18000dfd3  xor     r8d, r8d; lpReserved
0x18000dfd6  mov     [rsp+140h+cbData], 4
0x18000dfde  call    cs:__imp_RegQueryValueExW
0x18000dfe4  test    eax, eax
0x18000dfe6  jnz     short loc_18000E013
0x18000dfe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfef  cmp     rcx, rdi
0x18000dff2  jz      short loc_18000E072
0x18000dff4  test    byte ptr [rcx+1Ch], 10h
0x18000dff8  jz      short loc_18000E072
0x18000dffa  mov     eax, [rsi]
0x18000dffc  lea     edx, [rbx+5Fh]
0x18000dfff  mov     rcx, [rcx+10h]
0x18000e003  lea     r9, [rsp+140h+SubKey]
0x18000e008  mov     dword ptr [rsp+140h+phkResult], eax
0x18000e00c  call    WPP_SF_Sl
0x18000e011  jmp     short loc_18000E072
0x18000e013  cmp     eax, 2
0x18000e016  jnz     short loc_18000E03A
0x18000e018  lea     ebx, [rax-1]
0x18000e01b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e022  cmp     rcx, rdi
0x18000e025  jz      short loc_18000E072
0x18000e027  test    byte ptr [rcx+1Ch], 10h
0x18000e02b  jz      short loc_18000E072
0x18000e02d  lea     edx, [rax+5Eh]
0x18000e030  mov     dword ptr [rsp+140h+phkResult], 80070002h
0x18000e038  jmp     short loc_18000E061
0x18000e03a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e041  cmp     rcx, rdi
0x18000e044  jz      short loc_18000E072
0x18000e046  test    byte ptr [rcx+1Ch], 4
0x18000e04a  jz      short loc_18000E072
0x18000e04c  test    eax, eax
0x18000e04e  jle     short loc_18000E058
0x18000e050  movzx   eax, ax
0x18000e053  or      eax, 80070000h
0x18000e058  mov     edx, 61h ; 'a'
0x18000e05d  mov     dword ptr [rsp+140h+phkResult], eax
0x18000e061  mov     rcx, [rcx+10h]
0x18000e065  lea     r9, [rsp+140h+SubKey]
0x18000e06a  mov     r8, r15
0x18000e06d  call    WPP_SF_SD
0x18000e072  mov     rcx, [rsp+140h+hKey]; hKey
0x18000e077  call    cs:__imp_RegCloseKey
0x18000e07d  jmp     short loc_18000E0ED
0x18000e07f  cmp     eax, 2
0x18000e082  jnz     short loc_18000E0AD
0x18000e084  lea     ebx, [rax-1]
0x18000e087  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e08e  lea     rdi, WPP_GLOBAL_Control
0x18000e095  cmp     rcx, rdi
0x18000e098  jz      short loc_18000E113
0x18000e09a  test    byte ptr [rcx+1Ch], 10h
0x18000e09e  jz      short loc_18000E0F4
0x18000e0a0  lea     edx, [rax+60h]
0x18000e0a3  mov     dword ptr [rsp+140h+phkResult], 80070002h
0x18000e0ab  jmp     short loc_18000E0DC
0x18000e0ad  test    eax, eax
0x18000e0af  jle     short loc_18000E0BA
0x18000e0b1  movzx   ebx, ax
0x18000e0b4  or      ebx, 80070000h
0x18000e0ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0c1  lea     rdi, WPP_GLOBAL_Control
0x18000e0c8  cmp     rcx, rdi
0x18000e0cb  jz      short loc_18000E113
0x18000e0cd  test    byte ptr [rcx+1Ch], 4
0x18000e0d1  jz      short loc_18000E0F4
0x18000e0d3  mov     edx, 63h ; 'c'
0x18000e0d8  mov     dword ptr [rsp+140h+phkResult], ebx
0x18000e0dc  mov     rcx, [rcx+10h]
0x18000e0e0  lea     r9, [rsp+140h+SubKey]
0x18000e0e5  mov     r8, r15
0x18000e0e8  call    WPP_SF_SD
0x18000e0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0f4  cmp     rcx, rdi
0x18000e0f7  jz      short loc_18000E113
0x18000e0f9  test    byte ptr [rcx+1Ch], 10h
0x18000e0fd  jz      short loc_18000E113
0x18000e0ff  mov     rcx, [rcx+10h]
0x18000e103  mov     edx, 64h ; 'd'
0x18000e108  mov     r9d, ebx
0x18000e10b  mov     r8, r15
0x18000e10e  call    WPP_SF_D
0x18000e113  mov     eax, ebx
0x18000e115  mov     rcx, [rbp+40h+var_20]
0x18000e119  xor     rcx, rsp; StackCookie
0x18000e11c  call    __security_check_cookie
0x18000e121  lea     r11, [rsp+140h+var_10]
0x18000e129  mov     rbx, [r11+28h]
0x18000e12d  mov     rsi, [r11+38h]
0x18000e131  mov     rsp, r11
0x18000e134  pop     r15
0x18000e136  pop     rdi
0x18000e137  pop     rbp
0x18000e138  retn
```
