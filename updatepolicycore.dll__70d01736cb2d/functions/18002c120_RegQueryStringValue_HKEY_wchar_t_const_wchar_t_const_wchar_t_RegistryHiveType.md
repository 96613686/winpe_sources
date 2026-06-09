# RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)

- ea: `0x18002c120`
- end: `0x18002c27f`
- name: `?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180022a48`
- `0x180027144`

## callees

- `0x18002bee8`
- `0x18002c120`
- `0x18002d238`
- `0x18002d264`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c19d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c19d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c25c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c25c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c1c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c21b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c1c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c21b`

## pseudocode

```c
__int64 __fastcall RegQueryStringValue(HKEY a1, const WCHAR *a2, const WCHAR *a3, void **a4)
{
  signed int v9; // ebx
  LSTATUS v10; // eax
  BYTE *v11; // rax
  REGSAM samDesired; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  DWORD Type; // [rsp+40h] [rbp-10h] BYREF

  samDesired = 1;
  Type = 0;
  hKey = 0;
  cbData = 0;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v9 = SetRegistryType(a1, &samDesired);
  if ( v9 < 0 )
    goto LABEL_16;
  v10 = RegOpenKeyExW(a1, a2, 0, samDesired, &hKey);
  if ( v10 )
    goto LABEL_13;
  v10 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
  if ( v10 || !cbData )
    goto LABEL_13;
  if ( Type != 1 )
  {
    v9 = -2147024883;
LABEL_16:
    SusFree(*a4);
    *a4 = 0;
    goto LABEL_17;
  }
  cbData += 2;
  v11 = (BYTE *)SusAlloc(cbData);
  *a4 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    goto LABEL_16;
  }
  v10 = RegQueryValueExW(hKey, a3, 0, &Type, v11, &cbData);
  if ( v10 )
  {
LABEL_13:
    v9 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      v9 = v10;
    if ( v9 >= 0 )
      goto LABEL_17;
    goto LABEL_16;
  }
  *(_WORD *)((char *)*a4 + (cbData & 0xFFFFFFFE)) = 0;
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002c120  push    rbp
0x18002c122  push    rbx
0x18002c123  push    rsi
0x18002c124  push    rdi
0x18002c125  push    r12
0x18002c127  push    r14
0x18002c129  push    r15
0x18002c12b  mov     rbp, rsp
0x18002c12e  sub     rsp, 50h
0x18002c132  mov     rax, cs:__security_cookie
0x18002c139  xor     rax, rsp
0x18002c13c  mov     [rbp+var_8], rax
0x18002c140  xor     r12d, r12d
0x18002c143  mov     [rbp+samDesired], 1
0x18002c14a  mov     [rbp+Type], r12d
0x18002c14e  mov     rdi, r9
0x18002c151  mov     [rbp+hKey], r12
0x18002c155  mov     rsi, r8
0x18002c158  mov     [rbp+cbData], r12d
0x18002c15c  mov     r15, rdx
0x18002c15f  mov     r14, rcx
0x18002c162  test    r9, r9
0x18002c165  jnz     short loc_18002C171
0x18002c167  mov     eax, 80070057h
0x18002c16c  jmp     loc_18002C264
0x18002c171  lea     rdx, [rbp+samDesired]
0x18002c175  mov     [r9], r12
0x18002c178  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18002c17d  mov     ebx, eax
0x18002c17f  test    eax, eax
0x18002c181  js      loc_18002C248
0x18002c187  mov     r9d, [rbp+samDesired]; samDesired
0x18002c18b  lea     rax, [rbp+hKey]
0x18002c18f  xor     r8d, r8d; ulOptions
0x18002c192  mov     [rsp+50h+phkResult], rax; phkResult
0x18002c197  mov     rdx, r15; lpSubKey
0x18002c19a  mov     rcx, r14; hKey
0x18002c19d  call    cs:__imp_RegOpenKeyExW
0x18002c1a3  test    eax, eax
0x18002c1a5  jnz     loc_18002C236
0x18002c1ab  mov     rcx, [rbp+hKey]; hKey
0x18002c1af  lea     rax, [rbp+cbData]
0x18002c1b3  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002c1b8  lea     r9, [rbp+Type]; lpType
0x18002c1bc  xor     r8d, r8d; lpReserved
0x18002c1bf  mov     [rsp+50h+phkResult], r12; lpData
0x18002c1c4  mov     rdx, rsi; lpValueName
0x18002c1c7  call    cs:__imp_RegQueryValueExW
0x18002c1cd  test    eax, eax
0x18002c1cf  jnz     short loc_18002C236
0x18002c1d1  mov     ecx, [rbp+cbData]
0x18002c1d4  test    ecx, ecx
0x18002c1d6  jz      short loc_18002C236
0x18002c1d8  cmp     [rbp+Type], 1
0x18002c1dc  jz      short loc_18002C1E5
0x18002c1de  mov     ebx, 8007000Dh
0x18002c1e3  jmp     short loc_18002C248
0x18002c1e5  add     ecx, 2; unsigned __int64
0x18002c1e8  mov     [rbp+cbData], ecx
0x18002c1eb  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x18002c1f0  mov     [rdi], rax
0x18002c1f3  test    rax, rax
0x18002c1f6  jnz     short loc_18002C1FF
0x18002c1f8  mov     ebx, 8007000Eh
0x18002c1fd  jmp     short loc_18002C248
0x18002c1ff  lea     rcx, [rbp+cbData]
0x18002c203  xor     r8d, r8d; lpReserved
0x18002c206  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18002c20b  lea     r9, [rbp+Type]; lpType
0x18002c20f  mov     rcx, [rbp+hKey]; hKey
0x18002c213  mov     rdx, rsi; lpValueName
0x18002c216  mov     [rsp+50h+phkResult], rax; lpData
0x18002c21b  call    cs:__imp_RegQueryValueExW
0x18002c221  test    eax, eax
0x18002c223  jnz     short loc_18002C236
0x18002c225  mov     ecx, [rbp+cbData]
0x18002c228  mov     rax, [rdi]
0x18002c22b  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18002c22f  mov     [rcx+rax], r12w
0x18002c234  jmp     short loc_18002C253
0x18002c236  movzx   ebx, ax
0x18002c239  or      ebx, 80070000h
0x18002c23f  test    eax, eax
0x18002c241  cmovle  ebx, eax
0x18002c244  test    ebx, ebx
0x18002c246  jns     short loc_18002C253
0x18002c248  mov     rcx, [rdi]; lpMem
0x18002c24b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18002c250  mov     [rdi], r12
0x18002c253  mov     rcx, [rbp+hKey]; hKey
0x18002c257  test    rcx, rcx
0x18002c25a  jz      short loc_18002C262
0x18002c25c  call    cs:__imp_RegCloseKey
0x18002c262  mov     eax, ebx
0x18002c264  mov     rcx, [rbp+var_8]
0x18002c268  xor     rcx, rsp; StackCookie
0x18002c26b  call    __security_check_cookie
0x18002c270  add     rsp, 50h
0x18002c274  pop     r15
0x18002c276  pop     r14
0x18002c278  pop     r12
0x18002c27a  pop     rdi
0x18002c27b  pop     rsi
0x18002c27c  pop     rbx
0x18002c27d  pop     rbp
0x18002c27e  retn
```
