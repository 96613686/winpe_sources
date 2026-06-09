# CWshEnvRegistry::GetEnvStringFromRegA(HKEY__ *,long,ushort * *)

- ea: `0x18000b2f8`
- end: `0x18000b504`
- name: `?GetEnvStringFromRegA@CWshEnvRegistry@@CAJPEAUHKEY__@@JPEAPEAG@Z`
- size: `524`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD dwIndex, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18000bc60`

## callees

- `0x1800060e4`
- `0x180006124`
- `0x180009b40`
- `0x18000b2f8`
- `0x180010250`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000b4d2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4d2`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18000b381`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18000b381`
- `ADVAPI32!RegEnumValueA` at `0x18000b410`
- `ADVAPI32!RegEnumValueA` at `0x18000b46d`
- `ADVAPI32!RegEnumValueA` at `0x18000b410`
- `ADVAPI32!RegEnumValueA` at `0x18000b46d`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::GetEnvStringFromRegA(HKEY hKey, DWORD dwIndex, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // r14
  LSTATUS v7; // eax
  signed int v8; // ebx
  DWORD v9; // edx
  void *v10; // rax
  void *v11; // rsi
  CHAR *v12; // rdi
  LSTATUS v13; // eax
  bool v14; // cc
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v19; // [rsp+70h] [rbp-90h] BYREF
  char v20; // [rsp+80h] [rbp-80h] BYREF

  cbMaxValueNameLen = 0;
  v6 = 0;
  cbMaxValueLen = 0;
  Type = 0;
  v19 = 0;
  v7 = RegQueryInfoKeyA(hKey, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_22;
  }
  if ( cbMaxValueNameLen > 0x400 || cbMaxValueLen > 0x2000 )
    goto LABEL_21;
  v9 = cbMaxValueLen + cbMaxValueNameLen + 2;
  if ( v9 > 0x200 )
  {
    v10 = operator new(v9);
    v11 = v10;
    if ( v10 )
    {
      v12 = (CHAR *)v10;
      goto LABEL_10;
    }
LABEL_21:
    v8 = -2147024882;
    goto LABEL_22;
  }
  v11 = 0;
  v12 = &v20;
LABEL_10:
  v13 = RegEnumValueA(hKey, dwIndex, v12, &cbMaxValueNameLen, 0, 0, 0, 0);
  v8 = v13;
  v14 = v13 <= 0;
  if ( v13
    || (++cbMaxValueNameLen,
        v13 = RegEnumValueA(
                hKey,
                dwIndex,
                v12,
                &cbMaxValueNameLen,
                0,
                &Type,
                (LPBYTE)&v12[cbMaxValueNameLen + 1],
                &cbMaxValueLen),
        v8 = v13,
        v14 = v13 <= 0,
        v13) )
  {
    if ( !v14 )
      v8 = (unsigned __int16)v13 | 0x80070000;
  }
  else
  {
    v12[cbMaxValueNameLen] = 61;
    if ( Type - 1 > 1 )
      v12[cbMaxValueNameLen + 1] = 0;
    v8 = PSZToBSTR(v12, &v19);
    if ( v8 < 0 )
    {
      v6 = v19;
    }
    else
    {
      v8 = 0;
      *a3 = v19;
    }
  }
  if ( v11 )
    operator delete(v11);
LABEL_22:
  SysFreeString(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b2f8  mov     [rsp-8+arg_18], rbx
0x18000b2fd  push    rbp
0x18000b2fe  push    rsi
0x18000b2ff  push    rdi
0x18000b300  push    r12
0x18000b302  push    r13
0x18000b304  push    r14
0x18000b306  push    r15
0x18000b308  lea     rbp, [rsp-190h]
0x18000b310  sub     rsp, 290h
0x18000b317  mov     rax, cs:__security_cookie
0x18000b31e  xor     rax, rsp
0x18000b321  mov     [rbp+1C0h+var_40], rax
0x18000b328  xor     edi, edi
0x18000b32a  lea     rax, [rsp+2C0h+cbMaxValueLen]
0x18000b32f  mov     [rsp+2C0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18000b334  mov     r13, r8
0x18000b337  mov     [rsp+2C0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18000b33c  mov     r12d, edx
0x18000b33f  mov     [rsp+2C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000b344  xor     r9d, r9d; lpReserved
0x18000b347  lea     rax, [rsp+2C0h+cbMaxValueNameLen]
0x18000b34c  mov     [rsp+2C0h+cbMaxValueNameLen], edi
0x18000b350  mov     [rsp+2C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000b355  xor     r8d, r8d; lpcchClass
0x18000b358  mov     [rsp+2C0h+lpcValues], rdi; lpcValues
0x18000b35d  xor     edx, edx; lpClass
0x18000b35f  mov     [rsp+2C0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18000b364  mov     r15, rcx
0x18000b367  mov     [rsp+2C0h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x18000b36c  mov     r14d, edi
0x18000b36f  mov     [rsp+2C0h+lpcSubKeys], rdi; lpcSubKeys
0x18000b374  mov     [rsp+2C0h+cbMaxValueLen], edi
0x18000b378  mov     [rsp+2C0h+Type], edi
0x18000b37c  mov     [rsp+2C0h+var_250], rdi
0x18000b381  call    cs:__imp_RegQueryInfoKeyA
0x18000b387  mov     ebx, eax
0x18000b389  test    eax, eax
0x18000b38b  jz      short loc_18000B3A1
0x18000b38d  jle     loc_18000B4CF
0x18000b393  movzx   ebx, ax
0x18000b396  or      ebx, 80070000h
0x18000b39c  jmp     loc_18000B4CF
0x18000b3a1  mov     eax, [rsp+2C0h+cbMaxValueNameLen]
0x18000b3a5  cmp     eax, 400h
0x18000b3aa  ja      loc_18000B4CA
0x18000b3b0  mov     ecx, [rsp+2C0h+cbMaxValueLen]
0x18000b3b4  cmp     ecx, 2000h
0x18000b3ba  ja      loc_18000B4CA
0x18000b3c0  lea     edx, [rax+2]
0x18000b3c3  add     edx, ecx
0x18000b3c5  cmp     edx, 200h
0x18000b3cb  jbe     short loc_18000B3E5
0x18000b3cd  mov     ecx, edx; Size
0x18000b3cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b3d4  mov     rsi, rax
0x18000b3d7  test    rax, rax
0x18000b3da  jz      loc_18000B4CA
0x18000b3e0  mov     rdi, rax
0x18000b3e3  jmp     short loc_18000B3EC
0x18000b3e5  mov     rsi, rdi
0x18000b3e8  lea     rdi, [rbp+1C0h+var_240]
0x18000b3ec  xor     eax, eax
0x18000b3ee  lea     r9, [rsp+2C0h+cbMaxValueNameLen]; lpcchValueName
0x18000b3f3  mov     [rsp+2C0h+lpcValues], rax; lpcbData
0x18000b3f8  mov     r8, rdi; lpValueName
0x18000b3fb  mov     [rsp+2C0h+lpcbMaxClassLen], rax; lpData
0x18000b400  mov     edx, r12d; dwIndex
0x18000b403  mov     [rsp+2C0h+lpcbMaxSubKeyLen], rax; lpType
0x18000b408  mov     rcx, r15; hKey
0x18000b40b  mov     [rsp+2C0h+lpcSubKeys], rax; lpReserved
0x18000b410  call    cs:__imp_RegEnumValueA
0x18000b416  mov     ebx, eax
0x18000b418  test    eax, eax
0x18000b41a  jz      short loc_18000B430
0x18000b41c  jle     loc_18000B4BB
0x18000b422  movzx   ebx, ax
0x18000b425  or      ebx, 80070000h
0x18000b42b  jmp     loc_18000B4BB
0x18000b430  mov     eax, [rsp+2C0h+cbMaxValueNameLen]
0x18000b434  lea     r9, [rsp+2C0h+cbMaxValueNameLen]; lpcchValueName
0x18000b439  inc     eax
0x18000b43b  mov     edx, r12d; dwIndex
0x18000b43e  mov     [rsp+2C0h+cbMaxValueNameLen], eax
0x18000b442  mov     rcx, r15; hKey
0x18000b445  lea     r8d, [rax+1]
0x18000b449  add     r8, rdi
0x18000b44c  lea     rax, [rsp+2C0h+cbMaxValueLen]
0x18000b451  mov     [rsp+2C0h+lpcValues], rax; lpcbData
0x18000b456  lea     rax, [rsp+2C0h+Type]
0x18000b45b  mov     [rsp+2C0h+lpcbMaxClassLen], r8; lpData
0x18000b460  mov     r8, rdi; lpValueName
0x18000b463  mov     [rsp+2C0h+lpcbMaxSubKeyLen], rax; lpType
0x18000b468  mov     [rsp+2C0h+lpcSubKeys], r14; lpReserved
0x18000b46d  call    cs:__imp_RegEnumValueA
0x18000b473  mov     ebx, eax
0x18000b475  test    eax, eax
0x18000b477  jnz     short loc_18000B41C
0x18000b479  mov     eax, [rsp+2C0h+cbMaxValueNameLen]
0x18000b47d  mov     byte ptr [rax+rdi], 3Dh ; '='
0x18000b481  mov     eax, [rsp+2C0h+Type]
0x18000b485  dec     eax
0x18000b487  cmp     eax, 1
0x18000b48a  jbe     short loc_18000B496
0x18000b48c  mov     eax, [rsp+2C0h+cbMaxValueNameLen]
0x18000b490  inc     eax
0x18000b492  mov     [rax+rdi], r14b
0x18000b496  lea     rdx, [rsp+2C0h+var_250]; unsigned __int16 **
0x18000b49b  mov     rcx, rdi; lpMultiByteStr
0x18000b49e  call    ?PSZToBSTR@@YAJPEBDPEAPEAG@Z; PSZToBSTR(char const *,ushort * *)
0x18000b4a3  mov     ebx, eax
0x18000b4a5  test    eax, eax
0x18000b4a7  js      short loc_18000B4B6
0x18000b4a9  mov     rax, [rsp+2C0h+var_250]
0x18000b4ae  xor     ebx, ebx
0x18000b4b0  mov     [r13+0], rax
0x18000b4b4  jmp     short loc_18000B4BB
0x18000b4b6  mov     r14, [rsp+2C0h+var_250]
0x18000b4bb  test    rsi, rsi
0x18000b4be  jz      short loc_18000B4CF
0x18000b4c0  mov     rcx, rsi; Block
0x18000b4c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b4c8  jmp     short loc_18000B4CF
0x18000b4ca  mov     ebx, 8007000Eh
0x18000b4cf  mov     rcx, r14; bstrString
0x18000b4d2  call    cs:__imp_SysFreeString
0x18000b4d8  mov     eax, ebx
0x18000b4da  mov     rcx, [rbp+1C0h+var_40]
0x18000b4e1  xor     rcx, rsp; StackCookie
0x18000b4e4  call    __security_check_cookie
0x18000b4e9  mov     rbx, [rsp+2C0h+arg_18]
0x18000b4f1  add     rsp, 290h
0x18000b4f8  pop     r15
0x18000b4fa  pop     r14
0x18000b4fc  pop     r13
0x18000b4fe  pop     r12
0x18000b500  pop     rdi
0x18000b501  pop     rsi
0x18000b502  pop     rbp
0x18000b503  retn
```
