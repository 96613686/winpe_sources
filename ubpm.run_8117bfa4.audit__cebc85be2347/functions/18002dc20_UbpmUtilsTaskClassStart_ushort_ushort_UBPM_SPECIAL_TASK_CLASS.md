# UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)

- ea: `0x18002dc20`
- end: `0x18002dea8`
- name: `?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z`
- size: `648`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *, struct _UBPM_SPECIAL_TASK_CLASS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18002deb0`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18002c768`
- `0x18002dc20`
- `0x180040222`
- `0x18004023a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dc85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dc85`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002dd8c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002dd8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002de71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002de71`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002dcdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002dcdb`

## pseudocode

```c
__int64 __fastcall UbpmUtilsTaskClassStart(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct _UBPM_SPECIAL_TASK_CLASS *a3)
{
  DWORD v3; // r15d
  unsigned int v4; // ebx
  WCHAR *v5; // r12
  __int64 v6; // rdx
  BYTE *v7; // rdi
  size_t v8; // r8
  __int64 v9; // r9
  unsigned __int64 v10; // r13
  char *v11; // r14
  DWORD v12; // esi
  wchar_t *v13; // rcx
  DWORD v14; // ebx
  DWORD v15; // edx
  char *v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-9h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-5h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-1h] BYREF
  DWORD Type; // [rsp+74h] [rbp+3h] BYREF
  DWORD v25; // [rsp+78h] [rbp+7h]
  int v26; // [rsp+7Ch] [rbp+Bh]
  HKEY hKey; // [rsp+80h] [rbp+Fh] BYREF
  DWORD cbData; // [rsp+D8h] [rbp+67h] BYREF
  int v29; // [rsp+DCh] [rbp+6Bh]
  wchar_t *String2; // [rsp+E0h] [rbp+6Fh]
  struct _UBPM_SPECIAL_TASK_CLASS *v31; // [rsp+E8h] [rbp+77h]
  DWORD cbMaxValueLen; // [rsp+F0h] [rbp+7Fh] BYREF

  v31 = a3;
  String2 = a2;
  v29 = HIDWORD(a1);
  v3 = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  cbMaxValueLen = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Ubpm", 0, 0x20019u, &hKey);
  if ( v4 )
    goto LABEL_25;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v4 )
    goto LABEL_25;
  if ( !cValues )
  {
    v4 = 0;
    goto LABEL_25;
  }
  cbMaxValueLen += 2;
  ++cbMaxValueNameLen;
  v5 = (WCHAR *)UbpmAlloc(2 * cbMaxValueNameLen);
  if ( !v5 )
  {
    v4 = 14;
    goto LABEL_25;
  }
  v7 = (BYTE *)UbpmAlloc(cbMaxValueLen);
  if ( !v7 )
  {
    v4 = 14;
    goto LABEL_23;
  }
  v10 = 0;
  v11 = 0;
  v26 = 0;
  v12 = 0;
  v25 = 0;
  if ( !cValues )
  {
LABEL_22:
    v4 = 0;
    *(_QWORD *)v31 = v11;
    goto LABEL_23;
  }
  while ( 1 )
  {
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen;
    if ( RegEnumValueW(hKey, v3, v5, &cchValueName, 0, &Type, v7, &cbData) )
      goto LABEL_21;
    if ( Type != 1 )
      goto LABEL_21;
    v13 = String2;
    v8 = -1;
    *(_WORD *)&v7[2 * (cbData >> 1) - 2] = 0;
    do
      ++v8;
    while ( v13[v8] );
    if ( cchValueName < v8 )
      goto LABEL_21;
    v14 = cbData;
    if ( cbData <= 2 || wcsncmp_0(v5, v13, v8) )
      goto LABEL_21;
    v15 = v12 + v14;
    if ( v10 < (unsigned __int64)(v12 + v14) + 2 )
      break;
LABEL_20:
    memcpy_0(&v11[v10], v7, v14);
    v10 = cbData + v26;
    v26 += cbData;
LABEL_21:
    if ( ++v3 >= cValues )
      goto LABEL_22;
  }
  v16 = v11;
  v11 = (char *)UbpmReAlloc(v11, v15 + 2);
  if ( v11 )
  {
    v14 = cbData;
    v12 = cbData + v25 + 2;
    v25 = v12;
    goto LABEL_20;
  }
  v4 = 14;
  if ( v16 )
    UBPM_MIDL_user_free(v16, v6, v8, v9);
LABEL_23:
  UBPM_MIDL_user_free(v5, v6, v8, v9);
  if ( v7 )
    UBPM_MIDL_user_free(v7, v17, v18, v19);
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18002dc20  mov     rax, rsp
0x18002dc23  mov     [rax+18h], r8
0x18002dc27  mov     [rax+10h], rdx
0x18002dc2b  mov     [rax+8], rcx
0x18002dc2f  push    rbp
0x18002dc30  push    rbx
0x18002dc31  push    rsi
0x18002dc32  push    rdi
0x18002dc33  push    r12
0x18002dc35  push    r13
0x18002dc37  push    r14
0x18002dc39  push    r15
0x18002dc3b  lea     rbp, [rax-5Fh]
0x18002dc3f  sub     rsp, 88h
0x18002dc46  xor     r15d, r15d
0x18002dc49  lea     rax, [rbp+57h+hKey]
0x18002dc4d  mov     r9d, 20019h; samDesired
0x18002dc53  mov     [rbp+57h+cValues], r15d
0x18002dc57  xor     r8d, r8d; ulOptions
0x18002dc5a  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x18002dc5e  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ubp"...
0x18002dc65  mov     [rbp+57h+cchValueName], r15d
0x18002dc69  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dc70  mov     [rbp+57h+cbMaxValueLen], r15d
0x18002dc74  mov     [rbp+57h+cbData], r15d
0x18002dc78  mov     [rbp+57h+Type], r15d
0x18002dc7c  mov     [rbp+57h+hKey], r15
0x18002dc80  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002dc85  call    cs:__imp_RegOpenKeyExW
0x18002dc8c  nop     dword ptr [rax+rax+00h]
0x18002dc91  mov     ebx, eax
0x18002dc93  test    eax, eax
0x18002dc95  jnz     loc_18002DE68
0x18002dc9b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002dc9f  lea     rax, [rbp+57h+cbMaxValueLen]
0x18002dca3  mov     [rsp+58h], r15; lpftLastWriteTime
0x18002dca8  xor     r9d, r9d; lpReserved
0x18002dcab  mov     [rsp+0C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002dcb0  xor     r8d, r8d; lpcchClass
0x18002dcb3  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18002dcb8  xor     edx, edx; lpClass
0x18002dcba  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18002dcbe  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002dcc3  lea     rax, [rbp+57h+cValues]
0x18002dcc7  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x18002dccc  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002dcd1  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002dcd6  mov     [rsp+0C0h+phkResult], r15; lpcSubKeys
0x18002dcdb  call    cs:__imp_RegQueryInfoKeyW
0x18002dce2  nop     dword ptr [rax+rax+00h]
0x18002dce7  mov     ebx, eax
0x18002dce9  test    eax, eax
0x18002dceb  jnz     loc_18002DE68
0x18002dcf1  cmp     [rbp+57h+cValues], r15d
0x18002dcf5  jnz     short loc_18002DCFF
0x18002dcf7  mov     ebx, r15d
0x18002dcfa  jmp     loc_18002DE68
0x18002dcff  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18002dd02  add     [rbp+57h+cbMaxValueLen], 2
0x18002dd06  inc     ecx
0x18002dd08  mov     [rbp+57h+cbMaxValueNameLen], ecx
0x18002dd0b  add     ecx, ecx; Size
0x18002dd0d  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002dd12  mov     r12, rax
0x18002dd15  test    rax, rax
0x18002dd18  jnz     short loc_18002DD22
0x18002dd1a  lea     ebx, [rax+0Eh]
0x18002dd1d  jmp     loc_18002DE68
0x18002dd22  mov     ecx, [rbp+57h+cbMaxValueLen]; Size
0x18002dd25  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002dd2a  mov     rdi, rax
0x18002dd2d  test    rax, rax
0x18002dd30  jnz     short loc_18002DD3A
0x18002dd32  lea     ebx, [rax+0Eh]
0x18002dd35  jmp     loc_18002DE53
0x18002dd3a  xor     ebx, ebx
0x18002dd3c  mov     r13d, r15d
0x18002dd3f  mov     r14, r15
0x18002dd42  mov     [rbp+57h+var_4C], r13d
0x18002dd46  mov     esi, r15d
0x18002dd49  mov     [rbp+57h+var_50], r15d
0x18002dd4d  cmp     [rbp+57h+cValues], ebx
0x18002dd50  jbe     loc_18002DE46
0x18002dd56  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18002dd59  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18002dd5d  mov     rcx, [rbp+57h+hKey]; hKey
0x18002dd61  mov     r8, r12; lpValueName
0x18002dd64  mov     [rbp+57h+cchValueName], eax
0x18002dd67  mov     edx, r15d; dwIndex
0x18002dd6a  mov     eax, [rbp+57h+cbMaxValueLen]
0x18002dd6d  mov     [rbp+57h+cbData], eax
0x18002dd70  lea     rax, [rbp+57h+cbData]
0x18002dd74  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x18002dd79  lea     rax, [rbp+57h+Type]
0x18002dd7d  mov     [rsp+0C0h+lpcbMaxClassLen], rdi; lpData
0x18002dd82  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x18002dd87  mov     [rsp+0C0h+phkResult], rbx; lpReserved
0x18002dd8c  call    cs:__imp_RegEnumValueW
0x18002dd93  nop     dword ptr [rax+rax+00h]
0x18002dd98  test    eax, eax
0x18002dd9a  jnz     loc_18002DE39
0x18002dda0  cmp     [rbp+57h+Type], 1
0x18002dda4  jnz     loc_18002DE39
0x18002ddaa  mov     eax, [rbp+57h+cbData]
0x18002ddad  mov     rcx, [rbp+57h+String2]
0x18002ddb1  shr     eax, 1
0x18002ddb3  dec     eax
0x18002ddb5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002ddb9  mov     [rdi+rax*2], bx
0x18002ddbd  inc     r8; MaxCount
0x18002ddc0  cmp     [rcx+r8*2], bx
0x18002ddc5  jnz     short loc_18002DDBD
0x18002ddc7  mov     eax, [rbp+57h+cchValueName]
0x18002ddca  cmp     rax, r8
0x18002ddcd  jb      short loc_18002DE39
0x18002ddcf  mov     ebx, [rbp+57h+cbData]
0x18002ddd2  cmp     ebx, 2
0x18002ddd5  jbe     short loc_18002DE37
0x18002ddd7  mov     rdx, rcx; String2
0x18002ddda  mov     rcx, r12; String1
0x18002dddd  call    wcsncmp_0
0x18002dde2  test    eax, eax
0x18002dde4  jnz     short loc_18002DE37
0x18002dde6  lea     edx, [rsi+rbx]
0x18002dde9  mov     eax, edx
0x18002ddeb  add     rax, 2
0x18002ddef  cmp     r13, rax
0x18002ddf2  jnb     short loc_18002DE1C
0x18002ddf4  add     edx, 2; Size
0x18002ddf7  mov     rcx, r14; Ptr
0x18002ddfa  mov     rsi, r14
0x18002ddfd  call    ?UbpmReAlloc@@YAPEAXPEAXK@Z; UbpmReAlloc(void *,ulong)
0x18002de02  mov     r14, rax
0x18002de05  test    rax, rax
0x18002de08  jz      loc_18002DE94
0x18002de0e  mov     esi, [rbp+57h+var_50]
0x18002de11  mov     ebx, [rbp+57h+cbData]
0x18002de14  add     esi, 2
0x18002de17  add     esi, ebx
0x18002de19  mov     [rbp+57h+var_50], esi
0x18002de1c  mov     r8d, ebx; Size
0x18002de1f  lea     rcx, [r14+r13]; void *
0x18002de23  mov     rdx, rdi; Src
0x18002de26  call    memcpy_0
0x18002de2b  mov     r13d, [rbp+57h+var_4C]
0x18002de2f  add     r13d, [rbp+57h+cbData]
0x18002de33  mov     [rbp+57h+var_4C], r13d
0x18002de37  xor     ebx, ebx
0x18002de39  inc     r15d
0x18002de3c  cmp     r15d, [rbp+57h+cValues]
0x18002de40  jb      loc_18002DD56
0x18002de46  mov     rax, [rbp+57h+arg_10]
0x18002de4a  xor     r15d, r15d
0x18002de4d  mov     ebx, r15d
0x18002de50  mov     [rax], r14
0x18002de53  mov     rcx, r12
0x18002de56  call    UBPM_MIDL_user_free
0x18002de5b  test    rdi, rdi
0x18002de5e  jz      short loc_18002DE68
0x18002de60  mov     rcx, rdi
0x18002de63  call    UBPM_MIDL_user_free
0x18002de68  mov     rcx, [rbp+57h+hKey]; hKey
0x18002de6c  test    rcx, rcx
0x18002de6f  jz      short loc_18002DE7D
0x18002de71  call    cs:__imp_RegCloseKey
0x18002de78  nop     dword ptr [rax+rax+00h]
0x18002de7d  mov     eax, ebx
0x18002de7f  add     rsp, 88h
0x18002de86  pop     r15
0x18002de88  pop     r14
0x18002de8a  pop     r13
0x18002de8c  pop     r12
0x18002de8e  pop     rdi
0x18002de8f  pop     rsi
0x18002de90  pop     rbx
0x18002de91  pop     rbp
0x18002de92  retn
0x18002de94  mov     ebx, 0Eh
0x18002de99  test    rsi, rsi
0x18002de9c  jz      short loc_18002DE53
0x18002de9e  mov     rcx, rsi
0x18002dea1  call    UBPM_MIDL_user_free
0x18002dea6  jmp     short loc_18002DE53
```
