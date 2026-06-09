# CUwfStaticConfiguration::FindRegKeyExclusion(ushort const *)

- ea: `0x180007850`
- end: `0x180007996`
- name: `?FindRegKeyExclusion@CUwfStaticConfiguration@@QEAAJPEBG@Z`
- size: `326`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180018390`

## callees

- `0x180001384`
- `0x180007850`
- `0x180011a30`
- `0x180011b90`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000795b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000797b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000795b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000797b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800078ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000792e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800078ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000792e`

## string_xrefs

- `0x180007887`: `RegistryExceptionsUserDefined`
- `0x180007910`: `RegistryExceptionsUserDefined`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::FindRegKeyExclusion(CUwfStaticConfiguration *this, wchar_t *a2)
{
  void *v2; // rsi
  signed int v5; // ebx
  HKEY v6; // rcx
  LSTATUS ValueW; // eax
  void *pvData; // rdi
  bool v9; // cc
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF
  DWORD pdwType; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    goto LABEL_14;
  }
  v6 = (HKEY)*((_QWORD *)this + 2);
  pdwType = 0;
  pcbData = 0;
  ValueW = RegGetValueW(v6, 0, L"RegistryExceptionsUserDefined", 0x20u, &pdwType, 0, &pcbData);
  v5 = ValueW;
  if ( ValueW )
  {
    pvData = 0;
    v9 = ValueW <= 0;
LABEL_5:
    if ( !v9 )
      v5 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_12;
  }
  pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
  if ( pvData )
  {
    ValueW = RegGetValueW(*((HKEY *)this + 2), 0, L"RegistryExceptionsUserDefined", 0x20u, &pdwType, pvData, &pcbData);
    v5 = ValueW;
    v9 = ValueW <= 0;
    if ( !ValueW )
    {
      v2 = (void *)MultiSzAlloc(pvData);
      v5 = -2147024882;
      if ( v2 )
        v5 = 0;
      goto LABEL_12;
    }
    goto LABEL_5;
  }
  v5 = -2147024882;
LABEL_12:
  operator delete[](pvData);
  if ( v5 >= 0 )
    v5 = MultiSzFind(a2);
LABEL_14:
  operator delete[](v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007850  mov     [rsp+arg_0], rbx
0x180007855  mov     [rsp+arg_18], rbp
0x18000785a  push    rsi
0x18000785b  push    rdi
0x18000785c  push    r14
0x18000785e  sub     rsp, 40h
0x180007862  xor     esi, esi
0x180007864  mov     rbp, rdx
0x180007867  mov     r14, rcx
0x18000786a  test    rdx, rdx
0x18000786d  jnz     short loc_180007879
0x18000786f  mov     ebx, 80004003h
0x180007874  jmp     loc_180007978
0x180007879  mov     rcx, [rcx+10h]; hkey
0x18000787d  lea     rax, [rsp+58h+arg_8]
0x180007882  mov     [rsp+58h+pcbData], rax; pcbData
0x180007887  lea     r8, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x18000788e  lea     rax, [rsp+58h+arg_10]
0x180007893  mov     [rsp+58h+pvData], rsi; pvData
0x180007898  mov     r9d, 20h ; ' '; dwFlags
0x18000789e  mov     [rsp+58h+pdwType], rax; pdwType
0x1800078a3  xor     edx, edx; lpSubKey
0x1800078a5  mov     [rsp+58h+arg_10], esi
0x1800078a9  mov     [rsp+58h+arg_8], esi
0x1800078ad  call    cs:__imp_RegGetValueW
0x1800078b3  mov     ebx, eax
0x1800078b5  test    eax, eax
0x1800078b7  jz      short loc_1800078D1
0x1800078b9  xor     edi, edi
0x1800078bb  test    eax, eax
0x1800078bd  jle     loc_180007958
0x1800078c3  movzx   ebx, ax
0x1800078c6  or      ebx, 80070000h
0x1800078cc  jmp     loc_180007958
0x1800078d1  mov     ecx, [rsp+58h+arg_8]
0x1800078d5  mov     eax, 2
0x1800078da  shr     rcx, 1
0x1800078dd  mul     rcx
0x1800078e0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800078e7  cmovb   rax, rcx
0x1800078eb  mov     rcx, rax; unsigned __int64
0x1800078ee  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800078f3  mov     rdi, rax
0x1800078f6  test    rax, rax
0x1800078f9  jnz     short loc_180007902
0x1800078fb  mov     ebx, 8007000Eh
0x180007900  jmp     short loc_180007958
0x180007902  mov     rcx, [r14+10h]; hkey
0x180007906  lea     rax, [rsp+58h+arg_8]
0x18000790b  mov     [rsp+58h+pcbData], rax; pcbData
0x180007910  lea     r8, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x180007917  lea     rax, [rsp+58h+arg_10]
0x18000791c  mov     [rsp+58h+pvData], rdi; pvData
0x180007921  mov     r9d, 20h ; ' '; dwFlags
0x180007927  mov     [rsp+58h+pdwType], rax; pdwType
0x18000792c  xor     edx, edx; lpSubKey
0x18000792e  call    cs:__imp_RegGetValueW
0x180007934  mov     ebx, eax
0x180007936  test    eax, eax
0x180007938  jnz     short loc_1800078BD
0x18000793a  mov     edx, [rsp+58h+arg_8]
0x18000793e  mov     rcx, rdi; Src
0x180007941  shr     edx, 1
0x180007943  call    MultiSzAlloc
0x180007948  mov     rsi, rax
0x18000794b  mov     ebx, 8007000Eh
0x180007950  xor     eax, eax
0x180007952  test    rsi, rsi
0x180007955  cmovnz  ebx, eax
0x180007958  mov     rcx, rdi
0x18000795b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007961  test    ebx, ebx
0x180007963  js      short loc_180007978
0x180007965  xor     r9d, r9d
0x180007968  xor     r8d, r8d
0x18000796b  mov     rdx, rsi
0x18000796e  mov     rcx, rbp; String2
0x180007971  call    MultiSzFind
0x180007976  mov     ebx, eax
0x180007978  mov     rcx, rsi
0x18000797b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007981  mov     rbp, [rsp+58h+arg_18]
0x180007986  mov     eax, ebx
0x180007988  mov     rbx, [rsp+58h+arg_0]
0x18000798d  add     rsp, 40h
0x180007991  pop     r14
0x180007993  pop     rdi
0x180007994  pop     rsi
0x180007995  retn
```
