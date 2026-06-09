# RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)

- ea: `0x180092084`
- end: `0x1800921e3`
- name: `?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z`
- size: `351`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007478`
- `0x180059074`
- `0x18005acf0`
- `0x18008de50`
- `0x180099ae8`

## callees

- `0x1800819c0`
- `0x180081a38`
- `0x180091d18`
- `0x180092084`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092101`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092101`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800921c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800921c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009212b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009217f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009212b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009217f`

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
0x180092084  push    rbp
0x180092086  push    rbx
0x180092087  push    rsi
0x180092088  push    rdi
0x180092089  push    r12
0x18009208b  push    r14
0x18009208d  push    r15
0x18009208f  mov     rbp, rsp
0x180092092  sub     rsp, 50h
0x180092096  mov     rax, cs:__security_cookie
0x18009209d  xor     rax, rsp
0x1800920a0  mov     [rbp+var_8], rax
0x1800920a4  xor     r12d, r12d
0x1800920a7  mov     [rbp+samDesired], 1
0x1800920ae  mov     [rbp+Type], r12d
0x1800920b2  mov     rdi, r9
0x1800920b5  mov     [rbp+hKey], r12
0x1800920b9  mov     rsi, r8
0x1800920bc  mov     [rbp+cbData], r12d
0x1800920c0  mov     r15, rdx
0x1800920c3  mov     r14, rcx
0x1800920c6  test    r9, r9
0x1800920c9  jnz     short loc_1800920D5
0x1800920cb  mov     eax, 80070057h
0x1800920d0  jmp     loc_1800921C8
0x1800920d5  lea     rdx, [rbp+samDesired]
0x1800920d9  mov     [r9], r12
0x1800920dc  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x1800920e1  mov     ebx, eax
0x1800920e3  test    eax, eax
0x1800920e5  js      loc_1800921AC
0x1800920eb  mov     r9d, [rbp+samDesired]; samDesired
0x1800920ef  lea     rax, [rbp+hKey]
0x1800920f3  xor     r8d, r8d; ulOptions
0x1800920f6  mov     [rsp+50h+phkResult], rax; phkResult
0x1800920fb  mov     rdx, r15; lpSubKey
0x1800920fe  mov     rcx, r14; hKey
0x180092101  call    cs:__imp_RegOpenKeyExW
0x180092107  test    eax, eax
0x180092109  jnz     loc_18009219A
0x18009210f  mov     rcx, [rbp+hKey]; hKey
0x180092113  lea     rax, [rbp+cbData]
0x180092117  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18009211c  lea     r9, [rbp+Type]; lpType
0x180092120  xor     r8d, r8d; lpReserved
0x180092123  mov     [rsp+50h+phkResult], r12; lpData
0x180092128  mov     rdx, rsi; lpValueName
0x18009212b  call    cs:__imp_RegQueryValueExW
0x180092131  test    eax, eax
0x180092133  jnz     short loc_18009219A
0x180092135  mov     ecx, [rbp+cbData]
0x180092138  test    ecx, ecx
0x18009213a  jz      short loc_18009219A
0x18009213c  cmp     [rbp+Type], 1
0x180092140  jz      short loc_180092149
0x180092142  mov     ebx, 8007000Dh
0x180092147  jmp     short loc_1800921AC
0x180092149  add     ecx, 2; unsigned __int64
0x18009214c  mov     [rbp+cbData], ecx
0x18009214f  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x180092154  mov     [rdi], rax
0x180092157  test    rax, rax
0x18009215a  jnz     short loc_180092163
0x18009215c  mov     ebx, 8007000Eh
0x180092161  jmp     short loc_1800921AC
0x180092163  lea     rcx, [rbp+cbData]
0x180092167  xor     r8d, r8d; lpReserved
0x18009216a  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18009216f  lea     r9, [rbp+Type]; lpType
0x180092173  mov     rcx, [rbp+hKey]; hKey
0x180092177  mov     rdx, rsi; lpValueName
0x18009217a  mov     [rsp+50h+phkResult], rax; lpData
0x18009217f  call    cs:__imp_RegQueryValueExW
0x180092185  test    eax, eax
0x180092187  jnz     short loc_18009219A
0x180092189  mov     ecx, [rbp+cbData]
0x18009218c  mov     rax, [rdi]
0x18009218f  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180092193  mov     [rcx+rax], r12w
0x180092198  jmp     short loc_1800921B7
0x18009219a  movzx   ebx, ax
0x18009219d  or      ebx, 80070000h
0x1800921a3  test    eax, eax
0x1800921a5  cmovle  ebx, eax
0x1800921a8  test    ebx, ebx
0x1800921aa  jns     short loc_1800921B7
0x1800921ac  mov     rcx, [rdi]; lpMem
0x1800921af  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800921b4  mov     [rdi], r12
0x1800921b7  mov     rcx, [rbp+hKey]; hKey
0x1800921bb  test    rcx, rcx
0x1800921be  jz      short loc_1800921C6
0x1800921c0  call    cs:__imp_RegCloseKey
0x1800921c6  mov     eax, ebx
0x1800921c8  mov     rcx, [rbp+var_8]
0x1800921cc  xor     rcx, rsp; StackCookie
0x1800921cf  call    __security_check_cookie
0x1800921d4  add     rsp, 50h
0x1800921d8  pop     r15
0x1800921da  pop     r14
0x1800921dc  pop     r12
0x1800921de  pop     rdi
0x1800921df  pop     rsi
0x1800921e0  pop     rbx
0x1800921e1  pop     rbp
0x1800921e2  retn
```
