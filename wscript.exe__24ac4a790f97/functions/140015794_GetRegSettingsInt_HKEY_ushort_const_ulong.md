# GetRegSettingsInt(HKEY__ *,ushort const *,ulong *)

- ea: `0x140015794`
- end: `0x140015908`
- name: `?GetRegSettingsInt@@YAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `372`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, LPBYTE lpData)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400085ac`
- `0x14000a3f8`
- `0x140010d64`

## callees

- `0x140015794`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140015836`
- `KERNEL32!GetLastError` at `0x140015836`
- `KERNEL32!WideCharToMultiByte` at `0x140015829`
- `KERNEL32!WideCharToMultiByte` at `0x14001589e`
- `KERNEL32!WideCharToMultiByte` at `0x140015829`
- `KERNEL32!WideCharToMultiByte` at `0x14001589e`
- `ADVAPI32!RegQueryValueExA` at `0x1400158c7`
- `ADVAPI32!RegQueryValueExA` at `0x1400158c7`
- `ADVAPI32!RegQueryValueExW` at `0x1400157e7`
- `ADVAPI32!RegQueryValueExW` at `0x1400157e7`

## pseudocode

```c
signed int __fastcall GetRegSettingsInt(HKEY hKey, LPCWCH lpWideCharStr, LPBYTE lpData)
{
  signed int result; // eax
  int v7; // eax
  bool v8; // cc
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  DWORD *p_Type; // rdi
  DWORD Type; // [rsp+40h] [rbp+0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp+4h] BYREF

  Type = 0;
  cbData = 4;
  if ( Global::g_fWindowsNT )
  {
    result = RegQueryValueExW(hKey, lpWideCharStr, 0, &Type, lpData, &cbData);
  }
  else
  {
    if ( lpWideCharStr )
    {
      v7 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
      if ( !v7 )
        goto LABEL_5;
      v9 = v7 + 15LL;
      if ( v9 < v7 )
        v9 = 0xFFFFFFFFFFFFFF0LL;
      v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
      v11 = alloca(v10);
      v12 = alloca(v10);
      p_Type = &Type;
      if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, (LPSTR)&Type, v7, 0, 0) )
      {
LABEL_5:
        result = GetLastError();
        v8 = result <= 0;
        goto LABEL_6;
      }
    }
    else
    {
      p_Type = 0;
    }
    result = RegQueryValueExA(hKey, (LPCSTR)p_Type, 0, &Type, lpData, &cbData);
  }
  v8 = result <= 0;
  if ( !result )
  {
    if ( Type == 4 )
      return cbData != 4 ? 0x80040153 : 0;
    else
      return -2147221165;
  }
LABEL_6:
  if ( !v8 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140015794  push    rbp
0x140015796  push    rbx
0x140015797  push    rsi
0x140015798  push    rdi
0x140015799  push    r14
0x14001579b  sub     rsp, 50h
0x14001579f  lea     rbp, [rsp+40h]
0x1400157a4  mov     rax, cs:__security_cookie
0x1400157ab  xor     rax, rbp
0x1400157ae  mov     [rbp+30h+var_28], rax
0x1400157b2  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x1400157b9  mov     rsi, r8
0x1400157bc  mov     rbx, rdx
0x1400157bf  mov     [rbp+30h+Type], 0
0x1400157c6  mov     r14, rcx
0x1400157c9  mov     [rbp+30h+cbData], 4
0x1400157d0  jz      short loc_1400157F2
0x1400157d2  lea     rax, [rbp+30h+cbData]
0x1400157d6  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1400157db  lea     r9, [rbp+30h+Type]; lpType
0x1400157df  mov     [rsp+70h+lpData], r8; lpData
0x1400157e4  xor     r8d, r8d; lpReserved
0x1400157e7  call    cs:__imp_RegQueryValueExW
0x1400157ed  jmp     loc_1400158CD
0x1400157f2  test    rbx, rbx
0x1400157f5  jz      loc_1400158AA
0x1400157fb  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140015804  or      r9d, 0FFFFFFFFh; cchWideChar
0x140015808  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x140015811  mov     r8, rbx; lpWideCharStr
0x140015814  mov     dword ptr [rsp+70h+lpcbData], 0; cbMultiByte
0x14001581c  xor     edx, edx; dwFlags
0x14001581e  xor     ecx, ecx; CodePage
0x140015820  mov     [rsp+70h+lpData], 0; lpMultiByteStr
0x140015829  call    cs:__imp_WideCharToMultiByte
0x14001582f  movsxd  rdx, eax
0x140015832  test    eax, eax
0x140015834  jnz     short loc_140015851
0x140015836  call    cs:__imp_GetLastError
0x14001583c  test    eax, eax
0x14001583e  jle     loc_1400158F1
0x140015844  movzx   eax, ax
0x140015847  or      eax, 80070000h
0x14001584c  jmp     loc_1400158F1
0x140015851  lea     rcx, [rdx+0Fh]
0x140015855  cmp     rcx, rdx
0x140015858  ja      short loc_140015864
0x14001585a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140015864  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140015868  mov     rax, rcx
0x14001586b  call    _alloca_probe
0x140015870  sub     rsp, rcx
0x140015873  or      r9d, 0FFFFFFFFh; cchWideChar
0x140015877  mov     r8, rbx; lpWideCharStr
0x14001587a  xor     ecx, ecx; CodePage
0x14001587c  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140015885  lea     rdi, [rsp+70h+Type]
0x14001588a  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x140015893  mov     dword ptr [rsp+70h+lpcbData], edx; cbMultiByte
0x140015897  xor     edx, edx; dwFlags
0x140015899  mov     [rsp+70h+lpData], rdi; lpMultiByteStr
0x14001589e  call    cs:__imp_WideCharToMultiByte
0x1400158a4  test    eax, eax
0x1400158a6  jnz     short loc_1400158AC
0x1400158a8  jmp     short loc_140015836
0x1400158aa  xor     edi, edi
0x1400158ac  lea     rax, [rbp+30h+cbData]
0x1400158b0  xor     r8d, r8d; lpReserved
0x1400158b3  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1400158b8  lea     r9, [rbp+30h+Type]; lpType
0x1400158bc  mov     rdx, rdi; lpValueName
0x1400158bf  mov     [rsp+70h+lpData], rsi; lpData
0x1400158c4  mov     rcx, r14; hKey
0x1400158c7  call    cs:__imp_RegQueryValueExA
0x1400158cd  test    eax, eax
0x1400158cf  jnz     loc_14001583E
0x1400158d5  cmp     [rbp+30h+Type], 4
0x1400158d9  jnz     short loc_1400158EC
0x1400158db  mov     eax, [rbp+30h+cbData]
0x1400158de  sub     eax, 4
0x1400158e1  neg     eax
0x1400158e3  sbb     eax, eax
0x1400158e5  and     eax, 80040153h
0x1400158ea  jmp     short loc_1400158F1
0x1400158ec  mov     eax, 80040153h
0x1400158f1  mov     rcx, [rbp+30h+var_28]
0x1400158f5  xor     rcx, rbp; StackCookie
0x1400158f8  call    __security_check_cookie
0x1400158fd  lea     rsp, [rbp+10h]
0x140015901  pop     r14
0x140015903  pop     rdi
0x140015904  pop     rsi
0x140015905  pop     rbx
0x140015906  pop     rbp
0x140015907  retn
```
