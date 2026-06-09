# HrGetComponentInfo(_GUID const *,tagXW_COMPONENT_TYPE *,ulong *)

- ea: `0x18000c06c`
- end: `0x18000c3a3`
- name: `?HrGetComponentInfo@@YAJPEBU_GUID@@PEAW4tagXW_COMPONENT_TYPE@@PEAK@Z`
- size: `823`
- prototype: `__int64 __fastcall(GUID *rguid, LPBYTE lpData, LPBYTE)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f7e0`

## callees

- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000c06c`
- `0x18000e3c4`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c182`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c248`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c182`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c248`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c12e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c12e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c109`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c109`

## string_xrefs

- `0x18000c0d8`: `Components`

## pseudocode

```c
__int64 __fastcall HrGetComponentInfo(GUID *rguid, LPBYTE lpData, LPBYTE a3)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  int v9; // r8d
  LSTATUS v10; // eax
  int v11; // r8d
  PVOID *v12; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[62]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[50]; // [rsp+BCh] [rbp-44h] BYREF

  if ( lpData )
    *(_DWORD *)lpData = 0;
  if ( a3 )
    *(_DWORD *)a3 = 0;
  hKey = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x69u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x69u, L"Components");
  StringCchCatW(SubKey, 0x69u, &qword_18003C618);
  StringFromGUID2(rguid, sz, 39);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( !v6 )
  {
    cbData = 0;
    if ( lpData )
    {
      cbData = 4;
      v8 = RegQueryValueExW(hKey, L"Class Type", 0, 0, lpData, &cbData);
      if ( v8 )
      {
        if ( v8 == 2 )
        {
          v7 = 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              93,
              (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
              (unsigned int)SubKey,
              2);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            94,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (unsigned int)SubKey,
            v8);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_Sl(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, v9, (unsigned int)SubKey, *(_DWORD *)lpData);
      }
    }
    if ( a3 )
    {
      cbData = 4;
      v10 = RegQueryValueExW(hKey, L"Behavior", 0, 0, a3, &cbData);
      if ( v10 )
      {
        if ( v10 == 2 )
        {
          v7 = 1;
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
            v10);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_Sl(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, v11, (unsigned int)SubKey, *(_DWORD *)a3);
      }
    }
    RegCloseKey(hKey);
    goto LABEL_40;
  }
  if ( v6 == 2 )
  {
    v7 = 1;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_41;
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      98,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      2);
    goto LABEL_40;
  }
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_41:
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
        WPP_SF_d(v12[2], 100, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v7);
      return v7;
    }
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      99,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      v7);
LABEL_40:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  return v7;
}

```

## disassembly

```asm
0x18000c06c  mov     [rsp-8+arg_18], rbx
0x18000c071  push    rbp
0x18000c072  push    rsi
0x18000c073  push    rdi
0x18000c074  push    r13
0x18000c076  push    r14
0x18000c078  lea     rbp, [rsp-30h]
0x18000c07d  sub     rsp, 130h
0x18000c084  mov     rax, cs:__security_cookie
0x18000c08b  xor     rax, rsp
0x18000c08e  mov     [rbp+50h+var_30], rax
0x18000c092  mov     r14, r8
0x18000c095  mov     rsi, rdx
0x18000c098  mov     rbx, rcx
0x18000c09b  test    rdx, rdx
0x18000c09e  jz      short loc_18000C0A6
0x18000c0a0  mov     dword ptr [rdx], 0
0x18000c0a6  test    r14, r14
0x18000c0a9  jz      short loc_18000C0B2
0x18000c0ab  mov     dword ptr [r8], 0
0x18000c0b2  xor     eax, eax
0x18000c0b4  mov     [rsp+150h+hKey], 0
0x18000c0bd  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c0c4  mov     [rsp+150h+SubKey], ax
0x18000c0c9  lea     rcx, [rsp+150h+SubKey]; unsigned __int16 *
0x18000c0ce  lea     edi, [rax+69h]
0x18000c0d1  mov     edx, edi; unsigned __int64
0x18000c0d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c0d8  lea     r8, aComponents; "Components"
0x18000c0df  mov     edx, edi; unsigned __int64
0x18000c0e1  lea     rcx, [rsp+150h+SubKey]; unsigned __int16 *
0x18000c0e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c0eb  lea     r8, qword_18003C618; unsigned __int16 *
0x18000c0f2  mov     edx, edi; unsigned __int64
0x18000c0f4  lea     rcx, [rsp+150h+SubKey]; unsigned __int16 *
0x18000c0f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c0fe  lea     r8d, [rdi-42h]; cchMax
0x18000c102  mov     rcx, rbx; rguid
0x18000c105  lea     rdx, [rbp+50h+sz]; lpsz
0x18000c109  call    cs:__imp_StringFromGUID2
0x18000c10f  lea     rax, [rsp+150h+hKey]
0x18000c114  mov     r9d, 20019h; samDesired
0x18000c11a  xor     r8d, r8d; ulOptions
0x18000c11d  mov     [rsp+150h+phkResult], rax; phkResult
0x18000c122  lea     rdx, [rsp+150h+SubKey]; lpSubKey
0x18000c127  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c12e  call    cs:__imp_RegOpenKeyExW
0x18000c134  lea     r13, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000c13b  mov     ebx, eax
0x18000c13d  test    eax, eax
0x18000c13f  jnz     loc_18000C2EA
0x18000c145  mov     [rsp+150h+cbData], eax
0x18000c149  lea     rdi, WPP_GLOBAL_Control
0x18000c150  test    rsi, rsi
0x18000c153  jz      loc_18000C216
0x18000c159  mov     rcx, [rsp+150h+hKey]; hKey
0x18000c15e  lea     rax, [rsp+150h+cbData]
0x18000c163  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18000c168  lea     rdx, aClassType_0; "Class Type"
0x18000c16f  xor     r9d, r9d; lpType
0x18000c172  mov     [rsp+150h+phkResult], rsi; lpData
0x18000c177  xor     r8d, r8d; lpReserved
0x18000c17a  mov     [rsp+150h+cbData], 4
0x18000c182  call    cs:__imp_RegQueryValueExW
0x18000c188  test    eax, eax
0x18000c18a  jnz     short loc_18000C1B7
0x18000c18c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c193  cmp     rcx, rdi
0x18000c196  jz      short loc_18000C216
0x18000c198  test    byte ptr [rcx+1Ch], 10h
0x18000c19c  jz      short loc_18000C216
0x18000c19e  mov     eax, [rsi]
0x18000c1a0  lea     edx, [rbx+5Ch]
0x18000c1a3  mov     rcx, [rcx+10h]
0x18000c1a7  lea     r9, [rsp+150h+SubKey]
0x18000c1ac  mov     dword ptr [rsp+150h+phkResult], eax
0x18000c1b0  call    WPP_SF_Sl
0x18000c1b5  jmp     short loc_18000C216
0x18000c1b7  cmp     eax, 2
0x18000c1ba  jnz     short loc_18000C1DE
0x18000c1bc  lea     ebx, [rax-1]
0x18000c1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1c6  cmp     rcx, rdi
0x18000c1c9  jz      short loc_18000C216
0x18000c1cb  test    byte ptr [rcx+1Ch], 10h
0x18000c1cf  jz      short loc_18000C216
0x18000c1d1  lea     edx, [rax+5Bh]
0x18000c1d4  mov     dword ptr [rsp+150h+phkResult], 80070002h
0x18000c1dc  jmp     short loc_18000C205
0x18000c1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1e5  cmp     rcx, rdi
0x18000c1e8  jz      short loc_18000C216
0x18000c1ea  test    byte ptr [rcx+1Ch], 4
0x18000c1ee  jz      short loc_18000C216
0x18000c1f0  test    eax, eax
0x18000c1f2  jle     short loc_18000C1FC
0x18000c1f4  movzx   eax, ax
0x18000c1f7  or      eax, 80070000h
0x18000c1fc  mov     edx, 5Eh ; '^'
0x18000c201  mov     dword ptr [rsp+150h+phkResult], eax
0x18000c205  mov     rcx, [rcx+10h]
0x18000c209  lea     r9, [rsp+150h+SubKey]
0x18000c20e  mov     r8, r13
0x18000c211  call    WPP_SF_SD
0x18000c216  test    r14, r14
0x18000c219  jz      loc_18000C2DD
0x18000c21f  mov     rcx, [rsp+150h+hKey]; hKey
0x18000c224  lea     rax, [rsp+150h+cbData]
0x18000c229  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18000c22e  lea     rdx, aBehavior_0; "Behavior"
0x18000c235  xor     r9d, r9d; lpType
0x18000c238  mov     [rsp+150h+phkResult], r14; lpData
0x18000c23d  xor     r8d, r8d; lpReserved
0x18000c240  mov     [rsp+150h+cbData], 4
0x18000c248  call    cs:__imp_RegQueryValueExW
0x18000c24e  test    eax, eax
0x18000c250  jnz     short loc_18000C27E
0x18000c252  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c259  cmp     rcx, rdi
0x18000c25c  jz      short loc_18000C2DD
0x18000c25e  test    byte ptr [rcx+1Ch], 10h
0x18000c262  jz      short loc_18000C2DD
0x18000c264  mov     rcx, [rcx+10h]
0x18000c268  lea     edx, [rax+5Fh]
0x18000c26b  mov     eax, [r14]
0x18000c26e  lea     r9, [rsp+150h+SubKey]
0x18000c273  mov     dword ptr [rsp+150h+phkResult], eax
0x18000c277  call    WPP_SF_Sl
0x18000c27c  jmp     short loc_18000C2DD
0x18000c27e  cmp     eax, 2
0x18000c281  jnz     short loc_18000C2A5
0x18000c283  lea     ebx, [rax-1]
0x18000c286  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c28d  cmp     rcx, rdi
0x18000c290  jz      short loc_18000C2DD
0x18000c292  test    byte ptr [rcx+1Ch], 10h
0x18000c296  jz      short loc_18000C2DD
0x18000c298  lea     edx, [rax+5Eh]
0x18000c29b  mov     dword ptr [rsp+150h+phkResult], 80070002h
0x18000c2a3  jmp     short loc_18000C2CC
0x18000c2a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2ac  cmp     rcx, rdi
0x18000c2af  jz      short loc_18000C2DD
0x18000c2b1  test    byte ptr [rcx+1Ch], 4
0x18000c2b5  jz      short loc_18000C2DD
0x18000c2b7  test    eax, eax
0x18000c2b9  jle     short loc_18000C2C3
0x18000c2bb  movzx   eax, ax
0x18000c2be  or      eax, 80070000h
0x18000c2c3  mov     edx, 61h ; 'a'
0x18000c2c8  mov     dword ptr [rsp+150h+phkResult], eax
0x18000c2cc  mov     rcx, [rcx+10h]
0x18000c2d0  lea     r9, [rsp+150h+SubKey]
0x18000c2d5  mov     r8, r13
0x18000c2d8  call    WPP_SF_SD
0x18000c2dd  mov     rcx, [rsp+150h+hKey]; hKey
0x18000c2e2  call    cs:__imp_RegCloseKey
0x18000c2e8  jmp     short loc_18000C358
0x18000c2ea  cmp     eax, 2
0x18000c2ed  jnz     short loc_18000C318
0x18000c2ef  lea     ebx, [rax-1]
0x18000c2f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2f9  lea     rdi, WPP_GLOBAL_Control
0x18000c300  cmp     rcx, rdi
0x18000c303  jz      short loc_18000C37E
0x18000c305  test    byte ptr [rcx+1Ch], 10h
0x18000c309  jz      short loc_18000C35F
0x18000c30b  lea     edx, [rax+60h]
0x18000c30e  mov     dword ptr [rsp+150h+phkResult], 80070002h
0x18000c316  jmp     short loc_18000C347
0x18000c318  test    eax, eax
0x18000c31a  jle     short loc_18000C325
0x18000c31c  movzx   ebx, ax
0x18000c31f  or      ebx, 80070000h
0x18000c325  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c32c  lea     rdi, WPP_GLOBAL_Control
0x18000c333  cmp     rcx, rdi
0x18000c336  jz      short loc_18000C37E
0x18000c338  test    byte ptr [rcx+1Ch], 4
0x18000c33c  jz      short loc_18000C35F
0x18000c33e  mov     edx, 63h ; 'c'
0x18000c343  mov     dword ptr [rsp+150h+phkResult], ebx
0x18000c347  mov     rcx, [rcx+10h]
0x18000c34b  lea     r9, [rsp+150h+SubKey]
0x18000c350  mov     r8, r13
0x18000c353  call    WPP_SF_SD
0x18000c358  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c35f  cmp     rcx, rdi
0x18000c362  jz      short loc_18000C37E
0x18000c364  test    byte ptr [rcx+1Ch], 10h
0x18000c368  jz      short loc_18000C37E
0x18000c36a  mov     rcx, [rcx+10h]
0x18000c36e  mov     edx, 64h ; 'd'
0x18000c373  mov     r9d, ebx
0x18000c376  mov     r8, r13
0x18000c379  call    WPP_SF_d
0x18000c37e  mov     eax, ebx
0x18000c380  mov     rcx, [rbp+50h+var_30]
0x18000c384  xor     rcx, rsp; StackCookie
0x18000c387  call    __security_check_cookie
0x18000c38c  mov     rbx, [rsp+150h+arg_18]
0x18000c394  add     rsp, 130h
0x18000c39b  pop     r14
0x18000c39d  pop     r13
0x18000c39f  pop     rdi
0x18000c3a0  pop     rsi
0x18000c3a1  pop     rbp
0x18000c3a2  retn
```
