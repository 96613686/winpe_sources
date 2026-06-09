# CWshShell::RegDelete(ushort *)

- ea: `0x18000cc80`
- end: `0x18000ce35`
- name: `?RegDelete@CWshShell@@UEAAJPEAG@Z`
- size: `437`
- prototype: `int(CWshShell *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800032e0`
- `0x180005d20`
- `0x18000cc80`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000ccb2`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ccb2`
- `ADVAPI32!RegDeleteKeyA` at `0x18000cdd1`
- `ADVAPI32!RegDeleteKeyA` at `0x18000cdd1`
- `ADVAPI32!RegDeleteValueA` at `0x18000cdd9`
- `ADVAPI32!RegDeleteValueA` at `0x18000cdd9`
- `ADVAPI32!RegCloseKey` at `0x18000cde4`
- `ADVAPI32!RegCloseKey` at `0x18000cde4`
- `KERNEL32!WideCharToMultiByte` at `0x18000ccf7`
- `KERNEL32!WideCharToMultiByte` at `0x18000cd51`
- `KERNEL32!WideCharToMultiByte` at `0x18000ccf7`
- `KERNEL32!WideCharToMultiByte` at `0x18000cd51`

## string_xrefs

- `0x18000cda5`: `WshShell.RegDelete`
- `0x18000cdfe`: `WshShell.RegDelete`

## pseudocode

```c
__int64 __fastcall CWshShell::RegDelete(CWshShell *this, unsigned __int16 *a2)
{
  __int64 v4; // rbx
  int v5; // eax
  unsigned __int64 cbMultiByte; // rdx
  __int64 v7; // rax
  void *v8; // rsp
  __int64 v9; // rax
  int v10; // ebx
  int v11; // edi
  HKEY v12; // rdi
  LSTATUS v13; // eax
  signed int v14; // ebx
  bool v15; // sf
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+8h]

  hKey = 0;
  *(_QWORD *)MultiByteStr = 0;
  if ( !SysStringLen(a2) )
    return 2147942487LL;
  v4 = -1;
  v5 = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
  cbMultiByte = v5;
  if ( !v5 )
    return 2147942414LL;
  v7 = v5 + 15LL;
  if ( cbMultiByte + 15 < cbMultiByte )
    v7 = 0xFFFFFFFFFFFFFF0LL;
  v8 = alloca(v7 & 0xFFFFFFFFFFFFFFF0uLL);
  WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, cbMultiByte, 0, 0);
  if ( !MultiByteStr )
    return 2147942414LL;
  do
    ++v4;
  while ( MultiByteStr[v4] );
  v9 = (unsigned int)(v4 - 1);
  if ( MultiByteStr[v9] == 92 )
  {
    v10 = 1;
    MultiByteStr[v9] = 0;
  }
  else
  {
    v10 = 0;
  }
  v11 = parse_key((unsigned __int8 *)MultiByteStr, 0x20006u, 0);
  if ( v11 >= 0 )
  {
    v12 = hKey;
    if ( v10 )
      v13 = RegDeleteKeyA(hKey, *(LPCSTR *)MultiByteStr);
    else
      v13 = RegDeleteValueA(hKey, *(LPCSTR *)MultiByteStr);
    v14 = v13;
    RegCloseKey(v12);
    v15 = v14 < 0;
    if ( v14 > 0 )
    {
      v14 = (unsigned __int16)v14 | 0x80070000;
      v15 = v14 < 0;
    }
    if ( v15 )
      Signal_Exception(&IID_IWshEnvironment, L"WshShell.RegDelete", 0x100Du, a2);
    return (unsigned int)v14;
  }
  else
  {
    Signal_Exception(&IID_IWshEnvironment, L"WshShell.RegDelete", 0x100Eu, a2);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x18000cc80  push    rbp
0x18000cc82  push    rbx
0x18000cc83  push    rsi
0x18000cc84  push    rdi
0x18000cc85  sub     rsp, 68h
0x18000cc89  lea     rbp, [rsp+40h]
0x18000cc8e  mov     rax, cs:__security_cookie
0x18000cc95  xor     rax, rbp
0x18000cc98  mov     [rbp+40h+var_30], rax
0x18000cc9c  mov     rcx, rdx; pbstr
0x18000cc9f  mov     [rbp+40h+hKey], 0
0x18000cca7  mov     rsi, rdx
0x18000ccaa  mov     qword ptr [rbp+40h+MultiByteStr], 0
0x18000ccb2  call    cs:__imp_SysStringLen
0x18000ccb8  test    eax, eax
0x18000ccba  jnz     short loc_18000CCC6
0x18000ccbc  mov     eax, 80070057h
0x18000ccc1  jmp     loc_18000CE20
0x18000ccc6  mov     [rsp+80h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000cccf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ccd3  mov     [rsp+80h+lpDefaultChar], 0; lpDefaultChar
0x18000ccdc  mov     r9d, ebx; cchWideChar
0x18000ccdf  mov     [rsp+80h+cbMultiByte], 0; cbMultiByte
0x18000cce7  mov     r8, rsi; lpWideCharStr
0x18000ccea  xor     edx, edx; dwFlags
0x18000ccec  mov     [rsp+80h+lpMultiByteStr], 0; lpMultiByteStr
0x18000ccf5  xor     ecx, ecx; CodePage
0x18000ccf7  call    cs:__imp_WideCharToMultiByte
0x18000ccfd  movsxd  rdx, eax
0x18000cd00  test    eax, eax
0x18000cd02  jz      loc_18000CE1B
0x18000cd08  lea     rax, [rdx+0Fh]
0x18000cd0c  cmp     rax, rdx
0x18000cd0f  ja      short loc_18000CD1B
0x18000cd11  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000cd1b  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000cd1f  call    _alloca_probe
0x18000cd24  sub     rsp, rax
0x18000cd27  mov     r9d, ebx; cchWideChar
0x18000cd2a  mov     r8, rsi; lpWideCharStr
0x18000cd2d  xor     ecx, ecx; CodePage
0x18000cd2f  mov     [rsp+80h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000cd38  lea     rdi, [rsp+80h+MultiByteStr]
0x18000cd3d  mov     [rsp+80h+lpDefaultChar], 0; lpDefaultChar
0x18000cd46  mov     [rsp+80h+cbMultiByte], edx; cbMultiByte
0x18000cd4a  xor     edx, edx; dwFlags
0x18000cd4c  mov     [rsp+80h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000cd51  call    cs:__imp_WideCharToMultiByte
0x18000cd57  test    rdi, rdi
0x18000cd5a  jz      loc_18000CE1B
0x18000cd60  inc     rbx
0x18000cd63  cmp     byte ptr [rdi+rbx], 0
0x18000cd67  jnz     short loc_18000CD60
0x18000cd69  lea     eax, [rbx-1]
0x18000cd6c  cmp     byte ptr [rax+rdi], 5Ch ; '\'
0x18000cd70  jz      short loc_18000CD76
0x18000cd72  xor     ebx, ebx
0x18000cd74  jmp     short loc_18000CD7F
0x18000cd76  mov     ebx, 1
0x18000cd7b  mov     byte ptr [rax+rdi], 0
0x18000cd7f  lea     r9, [rbp+40h+MultiByteStr]
0x18000cd83  mov     dword ptr [rsp+80h+lpMultiByteStr], 0; int
0x18000cd8b  lea     r8, [rbp+40h+hKey]
0x18000cd8f  mov     edx, 20006h; samDesired
0x18000cd94  mov     rcx, rdi; Str1
0x18000cd97  call    parse_key
0x18000cd9c  mov     edi, eax
0x18000cd9e  test    eax, eax
0x18000cda0  jns     short loc_18000CDC2
0x18000cda2  mov     r9, rsi
0x18000cda5  lea     rdx, aWshshellRegdel; "WshShell.RegDelete"
0x18000cdac  mov     r8d, 100Eh; unsigned int
0x18000cdb2  lea     rcx, IID_IWshEnvironment; struct _GUID *
0x18000cdb9  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x18000cdbe  mov     eax, edi
0x18000cdc0  jmp     short loc_18000CE20
0x18000cdc2  mov     rdi, [rbp+40h+hKey]
0x18000cdc6  mov     rdx, qword ptr [rbp+40h+MultiByteStr]; lpValueName
0x18000cdca  mov     rcx, rdi; hKey
0x18000cdcd  test    ebx, ebx
0x18000cdcf  jz      short loc_18000CDD9
0x18000cdd1  call    cs:__imp_RegDeleteKeyA
0x18000cdd7  jmp     short loc_18000CDDF
0x18000cdd9  call    cs:__imp_RegDeleteValueA
0x18000cddf  mov     rcx, rdi; hKey
0x18000cde2  mov     ebx, eax
0x18000cde4  call    cs:__imp_RegCloseKey
0x18000cdea  test    ebx, ebx
0x18000cdec  jle     short loc_18000CDF9
0x18000cdee  movzx   ebx, bx
0x18000cdf1  or      ebx, 80070000h
0x18000cdf7  test    ebx, ebx
0x18000cdf9  jns     short loc_18000CE17
0x18000cdfb  mov     r9, rsi
0x18000cdfe  lea     rdx, aWshshellRegdel; "WshShell.RegDelete"
0x18000ce05  mov     r8d, 100Dh; unsigned int
0x18000ce0b  lea     rcx, IID_IWshEnvironment; struct _GUID *
0x18000ce12  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x18000ce17  mov     eax, ebx
0x18000ce19  jmp     short loc_18000CE20
0x18000ce1b  mov     eax, 8007000Eh
0x18000ce20  mov     rcx, [rbp+40h+var_30]
0x18000ce24  xor     rcx, rbp; StackCookie
0x18000ce27  call    __security_check_cookie
0x18000ce2c  lea     rsp, [rbp+28h]
0x18000ce30  pop     rdi
0x18000ce31  pop     rsi
0x18000ce32  pop     rbx
0x18000ce33  pop     rbp
0x18000ce34  retn
```
