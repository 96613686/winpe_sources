# CWshEnvRegistry::GetEnvStringFromRegW(HKEY__ *,long,ushort * *)

- ea: `0x18000b50c`
- end: `0x18000b729`
- name: `?GetEnvStringFromRegW@CWshEnvRegistry@@CAJPEAUHKEY__@@JPEAPEAG@Z`
- size: `541`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD dwIndex, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000bc60`

## callees

- `0x1800060e4`
- `0x180006124`
- `0x18000b50c`
- `0x180010250`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b6c8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b6c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6f7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000b591`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000b591`
- `ADVAPI32!RegEnumValueW` at `0x18000b63f`
- `ADVAPI32!RegEnumValueW` at `0x18000b699`
- `ADVAPI32!RegEnumValueW` at `0x18000b63f`
- `ADVAPI32!RegEnumValueW` at `0x18000b699`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::GetEnvStringFromRegW(HKEY hKey, DWORD dwIndex, unsigned __int16 **a3)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  DWORD v8; // eax
  DWORD v9; // edx
  void *v10; // rax
  void *v11; // rsi
  WCHAR *v12; // rdi
  LSTATUS v13; // eax
  bool v14; // cc
  unsigned __int16 *v15; // rax
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  char v20; // [rsp+70h] [rbp-90h] BYREF

  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  Type = 0;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_22;
  }
  v8 = cbMaxValueNameLen;
  if ( cbMaxValueNameLen > 0x400 || cbMaxValueLen > 0x2000 )
    goto LABEL_21;
  v9 = cbMaxValueLen + cbMaxValueNameLen + 2;
  if ( v9 > 0x200 )
  {
    v10 = operator new(saturated_mul(v9, 2u));
    v11 = v10;
    if ( v10 )
    {
      v12 = (WCHAR *)v10;
      v8 = cbMaxValueNameLen;
      goto LABEL_10;
    }
LABEL_21:
    v7 = -2147024882;
    goto LABEL_22;
  }
  v11 = 0;
  v12 = (WCHAR *)&v20;
LABEL_10:
  cbMaxValueNameLen = v8 + 1;
  v13 = RegEnumValueW(hKey, dwIndex, v12, &cbMaxValueNameLen, 0, 0, 0, 0);
  v7 = v13;
  v14 = v13 <= 0;
  if ( v13
    || (++cbMaxValueNameLen,
        v13 = RegEnumValueW(
                hKey,
                dwIndex,
                v12,
                &cbMaxValueNameLen,
                0,
                &Type,
                (LPBYTE)&v12[cbMaxValueNameLen],
                &cbMaxValueLen),
        v7 = v13,
        v14 = v13 <= 0,
        v13) )
  {
    if ( !v14 )
      v7 = (unsigned __int16)v13 | 0x80070000;
  }
  else
  {
    v12[cbMaxValueNameLen] = 61;
    if ( Type - 1 > 1 )
      v12[cbMaxValueNameLen + 1] = 0;
    v15 = SysAllocString(v12);
    if ( v15 )
    {
      *a3 = v15;
      v7 = 0;
    }
    else
    {
      v7 = -2147024882;
    }
  }
  if ( v11 )
    operator delete(v11);
LABEL_22:
  SysFreeString(0);
  return v7;
}

```

## disassembly

```asm
0x18000b50c  mov     [rsp-8+arg_18], rbx
0x18000b511  push    rbp
0x18000b512  push    rsi
0x18000b513  push    rdi
0x18000b514  push    r12
0x18000b516  push    r13
0x18000b518  push    r14
0x18000b51a  push    r15
0x18000b51c  lea     rbp, [rsp-380h]
0x18000b524  sub     rsp, 480h
0x18000b52b  mov     rax, cs:__security_cookie
0x18000b532  xor     rax, rsp
0x18000b535  mov     [rbp+3B0h+var_40], rax
0x18000b53c  xor     r13d, r13d
0x18000b53f  lea     rax, [rsp+4B0h+cbMaxValueLen]
0x18000b544  mov     [rsp+4B0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000b549  mov     r12, r8
0x18000b54c  mov     [rsp+4B0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000b551  mov     r15d, edx
0x18000b554  mov     [rsp+4B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000b559  xor     r9d, r9d; lpReserved
0x18000b55c  lea     rax, [rsp+4B0h+cbMaxValueNameLen]
0x18000b561  mov     [rsp+4B0h+cbMaxValueNameLen], r13d
0x18000b566  mov     [rsp+4B0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000b56b  xor     r8d, r8d; lpcchClass
0x18000b56e  mov     [rsp+4B0h+lpcValues], r13; lpcValues
0x18000b573  xor     edx, edx; lpClass
0x18000b575  mov     [rsp+4B0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000b57a  mov     r14, rcx
0x18000b57d  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18000b582  mov     [rsp+4B0h+lpcSubKeys], r13; lpcSubKeys
0x18000b587  mov     [rsp+4B0h+cbMaxValueLen], r13d
0x18000b58c  mov     [rsp+4B0h+Type], r13d
0x18000b591  call    cs:__imp_RegQueryInfoKeyW
0x18000b597  mov     ebx, eax
0x18000b599  test    eax, eax
0x18000b59b  jz      short loc_18000B5B1
0x18000b59d  jle     loc_18000B6F5
0x18000b5a3  movzx   ebx, ax
0x18000b5a6  or      ebx, 80070000h
0x18000b5ac  jmp     loc_18000B6F5
0x18000b5b1  mov     eax, [rsp+4B0h+cbMaxValueNameLen]
0x18000b5b5  cmp     eax, 400h
0x18000b5ba  ja      loc_18000B6F0
0x18000b5c0  mov     ecx, [rsp+4B0h+cbMaxValueLen]
0x18000b5c4  cmp     ecx, 2000h
0x18000b5ca  ja      loc_18000B6F0
0x18000b5d0  lea     edx, [rax+2]
0x18000b5d3  add     edx, ecx
0x18000b5d5  cmp     edx, 200h
0x18000b5db  jbe     short loc_18000B60F
0x18000b5dd  mov     ecx, edx
0x18000b5df  mov     eax, 2
0x18000b5e4  mul     rcx
0x18000b5e7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b5ee  cmovb   rax, rcx
0x18000b5f2  mov     rcx, rax; Size
0x18000b5f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b5fa  mov     rsi, rax
0x18000b5fd  test    rax, rax
0x18000b600  jz      loc_18000B6F0
0x18000b606  mov     rdi, rax
0x18000b609  mov     eax, [rsp+4B0h+cbMaxValueNameLen]
0x18000b60d  jmp     short loc_18000B617
0x18000b60f  mov     rsi, r13
0x18000b612  lea     rdi, [rsp+4B0h+var_440]
0x18000b617  mov     [rsp+4B0h+lpcValues], r13; lpcbData
0x18000b61c  lea     r9, [rsp+4B0h+cbMaxValueNameLen]; lpcchValueName
0x18000b621  mov     [rsp+4B0h+lpcbMaxClassLen], r13; lpData
0x18000b626  inc     eax
0x18000b628  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r13; lpType
0x18000b62d  mov     r8, rdi; lpValueName
0x18000b630  mov     edx, r15d; dwIndex
0x18000b633  mov     [rsp+4B0h+lpcSubKeys], r13; lpReserved
0x18000b638  mov     rcx, r14; hKey
0x18000b63b  mov     [rsp+4B0h+cbMaxValueNameLen], eax
0x18000b63f  call    cs:__imp_RegEnumValueW
0x18000b645  mov     ebx, eax
0x18000b647  test    eax, eax
0x18000b649  jz      short loc_18000B65F
0x18000b64b  jle     loc_18000B6E1
0x18000b651  movzx   ebx, ax
0x18000b654  or      ebx, 80070000h
0x18000b65a  jmp     loc_18000B6E1
0x18000b65f  mov     eax, [rsp+4B0h+cbMaxValueNameLen]
0x18000b663  lea     r9, [rsp+4B0h+cbMaxValueNameLen]; lpcchValueName
0x18000b668  inc     eax
0x18000b66a  mov     edx, r15d; dwIndex
0x18000b66d  mov     [rsp+4B0h+cbMaxValueNameLen], eax
0x18000b671  mov     rcx, r14; hKey
0x18000b674  lea     r8, [rdi+rax*2]
0x18000b678  lea     rax, [rsp+4B0h+cbMaxValueLen]
0x18000b67d  mov     [rsp+4B0h+lpcValues], rax; lpcbData
0x18000b682  lea     rax, [rsp+4B0h+Type]
0x18000b687  mov     [rsp+4B0h+lpcbMaxClassLen], r8; lpData
0x18000b68c  mov     r8, rdi; lpValueName
0x18000b68f  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rax; lpType
0x18000b694  mov     [rsp+4B0h+lpcSubKeys], r13; lpReserved
0x18000b699  call    cs:__imp_RegEnumValueW
0x18000b69f  mov     ebx, eax
0x18000b6a1  test    eax, eax
0x18000b6a3  jnz     short loc_18000B64B
0x18000b6a5  mov     eax, [rsp+4B0h+cbMaxValueNameLen]
0x18000b6a9  mov     word ptr [rdi+rax*2], 3Dh ; '='
0x18000b6af  mov     eax, [rsp+4B0h+Type]
0x18000b6b3  dec     eax
0x18000b6b5  cmp     eax, 1
0x18000b6b8  jbe     short loc_18000B6C5
0x18000b6ba  mov     eax, [rsp+4B0h+cbMaxValueNameLen]
0x18000b6be  inc     eax
0x18000b6c0  mov     [rdi+rax*2], r13w
0x18000b6c5  mov     rcx, rdi; psz
0x18000b6c8  call    cs:__imp_SysAllocString
0x18000b6ce  test    rax, rax
0x18000b6d1  jnz     short loc_18000B6DA
0x18000b6d3  mov     ebx, 8007000Eh
0x18000b6d8  jmp     short loc_18000B6E1
0x18000b6da  mov     [r12], rax
0x18000b6de  mov     ebx, r13d
0x18000b6e1  test    rsi, rsi
0x18000b6e4  jz      short loc_18000B6F5
0x18000b6e6  mov     rcx, rsi; Block
0x18000b6e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b6ee  jmp     short loc_18000B6F5
0x18000b6f0  mov     ebx, 8007000Eh
0x18000b6f5  xor     ecx, ecx; bstrString
0x18000b6f7  call    cs:__imp_SysFreeString
0x18000b6fd  mov     eax, ebx
0x18000b6ff  mov     rcx, [rbp+3B0h+var_40]
0x18000b706  xor     rcx, rsp; StackCookie
0x18000b709  call    __security_check_cookie
0x18000b70e  mov     rbx, [rsp+4B0h+arg_18]
0x18000b716  add     rsp, 480h
0x18000b71d  pop     r15
0x18000b71f  pop     r14
0x18000b721  pop     r13
0x18000b723  pop     r12
0x18000b725  pop     rdi
0x18000b726  pop     rsi
0x18000b727  pop     rbp
0x18000b728  retn
```
