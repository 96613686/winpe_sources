# CWshEnvRegistry::get_ItemW(ushort const *,ushort * *)

- ea: `0x18000c3ec`
- end: `0x18000c5b1`
- name: `?get_ItemW@CWshEnvRegistry@@AEAAJPEBGPEAPEAG@Z`
- size: `453`
- prototype: `int(CWshEnvRegistry *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000bfc0`

## callees

- `0x1800060e4`
- `0x180006124`
- `0x18000c3ec`
- `0x180010250`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000c569`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c569`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000c494`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000c494`
- `ADVAPI32!RegQueryValueExW` at `0x18000c525`
- `ADVAPI32!RegQueryValueExW` at `0x18000c525`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::get_ItemW(CWshEnvRegistry *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  HKEY v6; // rcx
  LSTATUS v7; // eax
  signed int v8; // ebx
  DWORD v9; // eax
  void *v10; // rax
  void *v11; // rdi
  BYTE *v12; // rsi
  HKEY v13; // rcx
  LSTATUS v14; // eax
  unsigned __int16 *v15; // rax
  int v16; // ecx
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  char v21; // [rsp+70h] [rbp-90h] BYREF

  *a3 = 0;
  v6 = (HKEY)*((_QWORD *)this + 9);
  Type = 0;
  cbMaxValueLen = 0;
  cbData = 0;
  v7 = RegQueryInfoKeyW(v6, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    v9 = cbMaxValueLen + 1;
    cbMaxValueLen = v9;
    if ( v9 <= 0x100 )
    {
      v11 = 0;
      v12 = (BYTE *)&v21;
    }
    else
    {
      v10 = operator new(saturated_mul(v9, 2u));
      v11 = v10;
      if ( !v10 )
        return (unsigned int)-2147024882;
      v12 = (BYTE *)v10;
      v9 = cbMaxValueLen;
    }
    v13 = (HKEY)*((_QWORD *)this + 9);
    cbData = 2 * v9;
    v14 = RegQueryValueExW(v13, a2, 0, &Type, v12, &cbData);
    v8 = v14;
    if ( v14 == 2 )
    {
      v8 = 0;
      *(_WORD *)v12 = 0;
      Type = 1;
    }
    else if ( v14 > 0 )
    {
      v8 = (unsigned __int16)v14 | 0x80070000;
    }
    if ( v8 >= 0 )
    {
      if ( Type - 1 <= 1 )
      {
        v15 = SysAllocString((const OLECHAR *)v12);
        v16 = 0;
        *a3 = v15;
        if ( !v15 )
          v16 = -2147024882;
        v8 = v16;
      }
      else
      {
        v8 = -2147467259;
      }
    }
    if ( v11 )
      operator delete(v11);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c3ec  push    rbp
0x18000c3ee  push    rbx
0x18000c3ef  push    rsi
0x18000c3f0  push    rdi
0x18000c3f1  push    r12
0x18000c3f3  push    r14
0x18000c3f5  push    r15
0x18000c3f7  lea     rbp, [rsp-180h]
0x18000c3ff  sub     rsp, 280h
0x18000c406  mov     rax, cs:__security_cookie
0x18000c40d  xor     rax, rsp
0x18000c410  mov     [rbp+1B0h+var_40], rax
0x18000c417  mov     [rsp+2B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000c420  lea     rax, [rsp+2B0h+cbMaxValueLen]
0x18000c425  mov     [rsp+2B0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18000c42e  mov     r15, r8
0x18000c431  mov     [rsp+2B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000c436  mov     r12, rdx
0x18000c439  mov     [rsp+2B0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18000c442  mov     r14, rcx
0x18000c445  mov     [rsp+2B0h+lpcValues], 0; lpcValues
0x18000c44e  xor     r9d, r9d; lpReserved
0x18000c451  mov     qword ptr [r8], 0
0x18000c458  xor     edx, edx; lpClass
0x18000c45a  mov     rcx, [rcx+48h]; hKey
0x18000c45e  xor     r8d, r8d; lpcchClass
0x18000c461  mov     [rsp+2B0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18000c46a  mov     [rsp+2B0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18000c473  mov     [rsp+2B0h+lpcSubKeys], 0; lpcSubKeys
0x18000c47c  mov     [rsp+2B0h+Type], 0
0x18000c484  mov     [rsp+2B0h+cbMaxValueLen], 0
0x18000c48c  mov     [rsp+2B0h+cbData], 0
0x18000c494  call    cs:__imp_RegQueryInfoKeyW
0x18000c49a  mov     ebx, eax
0x18000c49c  test    eax, eax
0x18000c49e  jle     short loc_18000C4A9
0x18000c4a0  movzx   ebx, ax
0x18000c4a3  or      ebx, 80070000h
0x18000c4a9  test    ebx, ebx
0x18000c4ab  js      loc_18000C58E
0x18000c4b1  mov     eax, [rsp+2B0h+cbMaxValueLen]
0x18000c4b5  inc     eax
0x18000c4b7  mov     [rsp+2B0h+cbMaxValueLen], eax
0x18000c4bb  cmp     eax, 100h
0x18000c4c0  jbe     short loc_18000C4FA
0x18000c4c2  mov     ecx, eax
0x18000c4c4  mov     eax, 2
0x18000c4c9  mul     rcx
0x18000c4cc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c4d3  cmovb   rax, rcx
0x18000c4d7  mov     rcx, rax; Size
0x18000c4da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c4df  mov     rdi, rax
0x18000c4e2  test    rax, rax
0x18000c4e5  jnz     short loc_18000C4F1
0x18000c4e7  mov     ebx, 8007000Eh
0x18000c4ec  jmp     loc_18000C58E
0x18000c4f1  mov     rsi, rax
0x18000c4f4  mov     eax, [rsp+2B0h+cbMaxValueLen]
0x18000c4f8  jmp     short loc_18000C501
0x18000c4fa  xor     edi, edi
0x18000c4fc  lea     rsi, [rsp+2B0h+var_240]
0x18000c501  mov     rcx, [r14+48h]; hKey
0x18000c505  lea     r9, [rsp+2B0h+Type]; lpType
0x18000c50a  add     eax, eax
0x18000c50c  xor     r8d, r8d; lpReserved
0x18000c50f  mov     [rsp+2B0h+cbData], eax
0x18000c513  mov     rdx, r12; lpValueName
0x18000c516  lea     rax, [rsp+2B0h+cbData]
0x18000c51b  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000c520  mov     [rsp+2B0h+lpcSubKeys], rsi; lpData
0x18000c525  call    cs:__imp_RegQueryValueExW
0x18000c52b  mov     ebx, eax
0x18000c52d  cmp     eax, 2
0x18000c530  jnz     short loc_18000C543
0x18000c532  xor     ebx, ebx
0x18000c534  xor     eax, eax
0x18000c536  mov     [rsi], ax
0x18000c539  mov     [rsp+2B0h+Type], 1
0x18000c541  jmp     short loc_18000C550
0x18000c543  test    eax, eax
0x18000c545  jle     short loc_18000C550
0x18000c547  movzx   ebx, ax
0x18000c54a  or      ebx, 80070000h
0x18000c550  test    ebx, ebx
0x18000c552  js      short loc_18000C581
0x18000c554  mov     eax, [rsp+2B0h+Type]
0x18000c558  dec     eax
0x18000c55a  cmp     eax, 1
0x18000c55d  jbe     short loc_18000C566
0x18000c55f  mov     ebx, 80004005h
0x18000c564  jmp     short loc_18000C581
0x18000c566  mov     rcx, rsi; psz
0x18000c569  call    cs:__imp_SysAllocString
0x18000c56f  xor     ecx, ecx
0x18000c571  mov     ebx, 8007000Eh
0x18000c576  test    rax, rax
0x18000c579  mov     [r15], rax
0x18000c57c  cmovz   ecx, ebx
0x18000c57f  mov     ebx, ecx
0x18000c581  test    rdi, rdi
0x18000c584  jz      short loc_18000C58E
0x18000c586  mov     rcx, rdi; Block
0x18000c589  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c58e  mov     eax, ebx
0x18000c590  mov     rcx, [rbp+1B0h+var_40]
0x18000c597  xor     rcx, rsp; StackCookie
0x18000c59a  call    __security_check_cookie
0x18000c59f  add     rsp, 280h
0x18000c5a6  pop     r15
0x18000c5a8  pop     r14
0x18000c5aa  pop     r12
0x18000c5ac  pop     rdi
0x18000c5ad  pop     rsi
0x18000c5ae  pop     rbx
0x18000c5af  pop     rbp
0x18000c5b0  retn
```
