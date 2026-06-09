# GetRegSettingsBool(HKEY__ *,ushort const *,bool *)

- ea: `0x18000bbdc`
- end: `0x18000be61`
- name: `?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z`
- size: `645`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000adfc`

## callees

- `0x1800038f8`
- `0x18000b240`
- `0x18000bbdc`
- `0x18000d1c0`
- `0x18000d250`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000bce0`
- `KERNEL32!GetLastError` at `0x18000bce0`
- `KERNEL32!MultiByteToWideChar` at `0x18000bdd1`
- `KERNEL32!MultiByteToWideChar` at `0x18000bdd1`
- `KERNEL32!WideCharToMultiByte` at `0x18000bcd3`
- `KERNEL32!WideCharToMultiByte` at `0x18000bd3e`
- `KERNEL32!WideCharToMultiByte` at `0x18000bcd3`
- `KERNEL32!WideCharToMultiByte` at `0x18000bd3e`
- `ADVAPI32!RegQueryValueExA` at `0x18000bd6e`
- `ADVAPI32!RegQueryValueExA` at `0x18000bd6e`
- `ADVAPI32!RegQueryValueExW` at `0x18000bc58`
- `ADVAPI32!RegQueryValueExW` at `0x18000bc58`

## pseudocode

```c
signed int __fastcall GetRegSettingsBool(HKEY hKey, const unsigned __int16 *a2, bool *a3)
{
  bool v5; // bl
  signed int result; // eax
  unsigned __int64 v7; // r8
  bool v8; // cc
  BYTE *v9; // rdi
  int v10; // eax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  DWORD v15; // ecx
  __int64 v16; // rax
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r8
  DWORD cbData; // [rsp+40h] [rbp+0h] BYREF
  DWORD Type[3]; // [rsp+44h] [rbp+4h] BYREF
  BYTE lpData[1024]; // [rsp+50h] [rbp+10h] BYREF
  WCHAR Data[1024]; // [rsp+450h] [rbp+410h] BYREF

  Type[0] = 0;
  cbData = 0;
  v5 = 1;
  if ( Global::g_fWindowsNT )
  {
    cbData = 1024;
    result = RegQueryValueExW(hKey, L"DisplayLogo", 0, Type, (LPBYTE)Data, &cbData);
    v8 = result <= 0;
    if ( result )
      goto LABEL_3;
    v9 = (BYTE *)Data;
    goto LABEL_19;
  }
  v10 = WideCharToMultiByte(0, 0, L"DisplayLogo", -1, 0, 0, 0, 0);
  if ( !v10 )
    goto LABEL_8;
  v11 = v10 + 15LL;
  if ( v11 < v10 )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  if ( !WideCharToMultiByte(0, 0, L"DisplayLogo", -1, (LPSTR)&cbData, v10, 0, 0) )
    goto LABEL_8;
  cbData = 1024;
  result = RegQueryValueExA(hKey, (LPCSTR)&cbData, 0, Type, lpData, &cbData);
  v8 = result <= 0;
  if ( result )
  {
LABEL_3:
    if ( !v8 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v15 = cbData;
  if ( !cbData )
    return -2147467259;
  v16 = cbData - 1;
  if ( (unsigned int)v16 >= 0x400 )
    _report_rangecheckfailure();
  lpData[v16] = 0;
  if ( Type[0] - 1 > 1 )
  {
    v9 = lpData;
    goto LABEL_20;
  }
  v9 = 0;
  if ( !MultiByteToWideChar(0, 0, (LPCCH)lpData, -1, Data, 1024) )
  {
LABEL_8:
    result = GetLastError();
    v8 = result <= 0;
    goto LABEL_3;
  }
LABEL_19:
  v15 = cbData;
LABEL_20:
  if ( Type[0] == 1 || Type[0] == 2 )
  {
    *a3 = 1;
    if ( !(unsigned int)CompareStrsCaseInsensitive(Data, L"0", v7)
      || !(unsigned int)CompareStrsCaseInsensitive(Data, L"no", v17)
      || !(unsigned int)CompareStrsCaseInsensitive(Data, L"false", v18) )
    {
      v5 = 0;
    }
  }
  else
  {
    if ( Type[0] != 4 || v15 != 4 )
      return -2147221165;
    v5 = *(_DWORD *)v9 != 0;
  }
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000bbdc  push    rbp
0x18000bbde  push    rdi
0x18000bbdf  push    r14
0x18000bbe1  sub     rsp, 0C60h
0x18000bbe8  lea     rbp, [rsp+40h]
0x18000bbed  mov     [rbp+0C30h+arg_8], rbx
0x18000bbf4  mov     [rbp+0C30h+arg_18], rsi
0x18000bbfb  mov     rax, cs:__security_cookie
0x18000bc02  xor     rax, rbp
0x18000bc05  mov     [rbp+0C30h+var_20], rax
0x18000bc0c  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000bc13  mov     rsi, r8
0x18000bc16  mov     rdi, rcx
0x18000bc19  mov     [rbp+0C30h+Type], 0
0x18000bc20  mov     [rbp+0C30h+cbData], 0
0x18000bc27  mov     ebx, 1
0x18000bc2c  jz      short loc_18000BCA1
0x18000bc2e  lea     rax, [rbp+0C30h+cbData]
0x18000bc32  mov     [rbp+0C30h+cbData], 400h
0x18000bc39  mov     [rsp+0C70h+lpcbData], rax; lpcbData
0x18000bc3e  lea     r9, [rbp+0C30h+Type]; lpType
0x18000bc42  lea     rax, [rbp+0C30h+Data]
0x18000bc49  xor     r8d, r8d; lpReserved
0x18000bc4c  lea     rdx, aDisplaylogo; "DisplayLogo"
0x18000bc53  mov     [rsp+0C70h+lpData], rax; lpData
0x18000bc58  call    cs:__imp_RegQueryValueExW
0x18000bc5e  test    eax, eax
0x18000bc60  jz      short loc_18000BC95
0x18000bc62  jle     short loc_18000BC6C
0x18000bc64  movzx   eax, ax
0x18000bc67  or      eax, 80070000h
0x18000bc6c  mov     rcx, [rbp+0C30h+var_20]
0x18000bc73  xor     rcx, rbp; StackCookie
0x18000bc76  call    __security_check_cookie
0x18000bc7b  mov     rbx, [rbp+0C30h+arg_8]
0x18000bc82  mov     rsi, [rbp+0C30h+arg_18]
0x18000bc89  lea     rsp, [rbp+0C20h]
0x18000bc90  pop     r14
0x18000bc92  pop     rdi
0x18000bc93  pop     rbp
0x18000bc94  retn
0x18000bc95  lea     rdi, [rbp+0C30h+Data]
0x18000bc9c  jmp     loc_18000BDDF
0x18000bca1  mov     [rsp+0C70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000bcaa  lea     r8, aDisplaylogo; "DisplayLogo"
0x18000bcb1  mov     [rsp+0C70h+lpDefaultChar], 0; lpDefaultChar
0x18000bcba  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000bcbe  mov     dword ptr [rsp+0C70h+lpcbData], 0; cbMultiByte
0x18000bcc6  xor     edx, edx; dwFlags
0x18000bcc8  xor     ecx, ecx; CodePage
0x18000bcca  mov     [rsp+0C70h+lpData], 0; lpMultiByteStr
0x18000bcd3  call    cs:__imp_WideCharToMultiByte
0x18000bcd9  movsxd  rdx, eax
0x18000bcdc  test    eax, eax
0x18000bcde  jnz     short loc_18000BCED
0x18000bce0  call    cs:__imp_GetLastError
0x18000bce6  test    eax, eax
0x18000bce8  jmp     loc_18000BC62
0x18000bced  lea     rcx, [rdx+0Fh]
0x18000bcf1  cmp     rcx, rdx
0x18000bcf4  ja      short loc_18000BD00
0x18000bcf6  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000bd00  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000bd04  mov     rax, rcx
0x18000bd07  call    _alloca_probe
0x18000bd0c  sub     rsp, rcx
0x18000bd0f  lea     r8, aDisplaylogo; "DisplayLogo"
0x18000bd16  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000bd1a  xor     ecx, ecx; CodePage
0x18000bd1c  mov     [rsp+0C70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000bd25  lea     r14, [rsp+0C70h+cbData]
0x18000bd2a  mov     [rsp+0C70h+lpDefaultChar], 0; lpDefaultChar
0x18000bd33  mov     dword ptr [rsp+0C70h+lpcbData], edx; cbMultiByte
0x18000bd37  xor     edx, edx; dwFlags
0x18000bd39  mov     [rsp+0C70h+lpData], r14; lpMultiByteStr
0x18000bd3e  call    cs:__imp_WideCharToMultiByte
0x18000bd44  test    eax, eax
0x18000bd46  jz      short loc_18000BCE0
0x18000bd48  lea     rax, [rbp+0C30h+cbData]
0x18000bd4c  mov     [rbp+0C30h+cbData], 400h
0x18000bd53  mov     [rsp+0C70h+lpcbData], rax; lpcbData
0x18000bd58  lea     r9, [rbp+0C30h+Type]; lpType
0x18000bd5c  lea     rax, [rbp+0C30h+var_C20]
0x18000bd60  xor     r8d, r8d; lpReserved
0x18000bd63  mov     rdx, r14; lpValueName
0x18000bd66  mov     [rsp+0C70h+lpData], rax; lpData
0x18000bd6b  mov     rcx, rdi; hKey
0x18000bd6e  call    cs:__imp_RegQueryValueExA
0x18000bd74  test    eax, eax
0x18000bd76  jnz     loc_18000BC62
0x18000bd7c  mov     ecx, [rbp+0C30h+cbData]
0x18000bd7f  test    ecx, ecx
0x18000bd81  jnz     short loc_18000BD8D
0x18000bd83  mov     eax, 80004005h
0x18000bd88  jmp     loc_18000BC6C
0x18000bd8d  lea     eax, [rcx-1]
0x18000bd90  cmp     eax, 400h
0x18000bd95  jnb     loc_18000BE5B
0x18000bd9b  mov     [rbp+rax+0C30h+var_C20], 0
0x18000bda0  mov     eax, [rbp+0C30h+Type]
0x18000bda3  dec     eax
0x18000bda5  cmp     eax, ebx
0x18000bda7  jbe     short loc_18000BDAF
0x18000bda9  lea     rdi, [rbp+0C30h+var_C20]
0x18000bdad  jmp     short loc_18000BDE2
0x18000bdaf  lea     rax, [rbp+0C30h+Data]
0x18000bdb6  mov     dword ptr [rsp+0C70h+lpcbData], 400h; cchWideChar
0x18000bdbe  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000bdc2  mov     [rsp+0C70h+lpData], rax; lpWideCharStr
0x18000bdc7  lea     r8, [rbp+0C30h+var_C20]; lpMultiByteStr
0x18000bdcb  xor     edx, edx; dwFlags
0x18000bdcd  xor     ecx, ecx; CodePage
0x18000bdcf  xor     edi, edi
0x18000bdd1  call    cs:__imp_MultiByteToWideChar
0x18000bdd7  test    eax, eax
0x18000bdd9  jz      loc_18000BCE0
0x18000bddf  mov     ecx, [rbp+0C30h+cbData]
0x18000bde2  mov     eax, [rbp+0C30h+Type]
0x18000bde5  sub     eax, ebx
0x18000bde7  jz      short loc_18000BE09
0x18000bde9  sub     eax, ebx
0x18000bdeb  jz      short loc_18000BE09
0x18000bded  cmp     eax, 2
0x18000bdf0  jnz     short loc_18000BDFF
0x18000bdf2  cmp     ecx, 4
0x18000bdf5  jnz     short loc_18000BDFF
0x18000bdf7  cmp     dword ptr [rdi], 0
0x18000bdfa  setnz   bl
0x18000bdfd  jmp     short loc_18000BE52
0x18000bdff  mov     eax, 80040153h
0x18000be04  jmp     loc_18000BC6C
0x18000be09  lea     rdx, a0; "0"
0x18000be10  mov     [rsi], bl
0x18000be12  lea     rcx, [rbp+0C30h+Data]; unsigned __int16 *
0x18000be19  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x18000be1e  test    eax, eax
0x18000be20  jz      short loc_18000BE50
0x18000be22  lea     rdx, aNo_0; "no"
0x18000be29  lea     rcx, [rbp+0C30h+Data]; unsigned __int16 *
0x18000be30  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x18000be35  test    eax, eax
0x18000be37  jz      short loc_18000BE50
0x18000be39  lea     rdx, aFalse; "false"
0x18000be40  lea     rcx, [rbp+0C30h+Data]; unsigned __int16 *
0x18000be47  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x18000be4c  test    eax, eax
0x18000be4e  jnz     short loc_18000BE52
0x18000be50  xor     bl, bl
0x18000be52  mov     [rsi], bl
0x18000be54  xor     eax, eax
0x18000be56  jmp     loc_18000BC6C
0x18000be5b  call    __report_rangecheckfailure
```
