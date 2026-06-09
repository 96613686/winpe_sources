# CRegistry::ReadReg(ushort const *,uchar * *,ulong *,ulong)

- ea: `0x180030a5c`
- end: `0x180030b87`
- name: `?ReadReg@CRegistry@@QEAAKPEBGPEAPEAEPEAKK@Z`
- size: `299`
- prototype: `unsigned int __usercall@<eax>(CRegistry *__hidden this@<rcx>, LPCWSTR lpValueName@<rdx>, unsigned __int8 **@<r8>, unsigned int *@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180030b90`
- `0x180030bd8`

## callees

- `0x180030990`
- `0x180030a5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030aa2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030b04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030aa2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030b04`

## pseudocode

```c
__int64 __fastcall CRegistry::ReadReg(
        CRegistry *this,
        LPCWSTR lpValueName,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned int a5)
{
  HKEY v8; // rcx
  unsigned int v10; // edx
  DWORD v11; // edx
  _WORD *v13; // r9
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF

  *a4 = 0;
  Type = 0;
  v8 = (HKEY)*((_QWORD *)this + 3);
  cbData = 0;
  v10 = RegQueryValueExW(v8, lpValueName, 0, &Type, 0, &cbData);
  if ( v10 )
    return v10;
  if ( Type != a5 )
    return 13;
  v11 = cbData;
  if ( Type - 1 <= 1 )
    v11 = cbData + 2;
  if ( !CRegistry::Allocate(this, v11) )
    return 14;
  v10 = RegQueryValueExW(*((HKEY *)this + 3), lpValueName, 0, &Type, *((LPBYTE *)this + 1), &cbData);
  if ( !v10 )
  {
    if ( Type != a5 )
      return 13;
    if ( Type - 1 <= 1 )
    {
      v13 = (_WORD *)*((_QWORD *)this + 1);
      if ( cbData < 2 )
      {
        *v13 = 0;
        *a4 = 2;
LABEL_16:
        *a3 = (unsigned __int8 *)*((_QWORD *)this + 1);
        return v10;
      }
      if ( v13[(unsigned __int64)(cbData - 1) >> 1] )
      {
        v13[(unsigned __int64)cbData >> 1] = 0;
        *a4 = cbData + 2;
        goto LABEL_16;
      }
    }
    *a4 = cbData;
    goto LABEL_16;
  }
  return v10;
}

```

## disassembly

```asm
0x180030a5c  mov     [rsp-28h+arg_8], rbx
0x180030a61  push    rbp
0x180030a62  push    rsi
0x180030a63  push    rdi
0x180030a64  push    r14
0x180030a66  push    r15
0x180030a68  mov     rbp, rsp
0x180030a6b  sub     rsp, 30h
0x180030a6f  xor     r15d, r15d
0x180030a72  lea     rax, [rbp+cbData]
0x180030a76  mov     [r9], r15d
0x180030a79  mov     rdi, r9
0x180030a7c  mov     r14, r8
0x180030a7f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180030a84  mov     rbx, rcx
0x180030a87  mov     [rbp+Type], r15d
0x180030a8b  mov     rcx, [rcx+18h]; hKey
0x180030a8f  lea     r9, [rbp+Type]; lpType
0x180030a93  xor     r8d, r8d; lpReserved
0x180030a96  mov     [rbp+cbData], r15d
0x180030a9a  mov     rsi, rdx
0x180030a9d  mov     [rsp+30h+lpData], r15; lpData
0x180030aa2  call    cs:__imp_RegQueryValueExW
0x180030aa9  nop     dword ptr [rax+rax+00h]
0x180030aae  mov     edx, eax
0x180030ab0  test    eax, eax
0x180030ab2  jnz     loc_180030B73
0x180030ab8  mov     eax, [rbp+Type]
0x180030abb  cmp     eax, [rbp+arg_20]
0x180030abe  jnz     short loc_180030B1E
0x180030ac0  mov     edx, [rbp+cbData]
0x180030ac3  dec     eax
0x180030ac5  cmp     eax, 1
0x180030ac8  ja      short loc_180030ACD
0x180030aca  add     edx, 2; unsigned int
0x180030acd  mov     rcx, rbx; this
0x180030ad0  call    ?Allocate@CRegistry@@AEAAPEAXK@Z; CRegistry::Allocate(ulong)
0x180030ad5  test    rax, rax
0x180030ad8  jnz     short loc_180030AE4
0x180030ada  mov     eax, 0Eh
0x180030adf  jmp     loc_180030B75
0x180030ae4  mov     rcx, [rbx+18h]; hKey
0x180030ae8  lea     rax, [rbp+cbData]
0x180030aec  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180030af1  lea     r9, [rbp+Type]; lpType
0x180030af5  mov     rax, [rbx+8]
0x180030af9  xor     r8d, r8d; lpReserved
0x180030afc  mov     rdx, rsi; lpValueName
0x180030aff  mov     [rsp+30h+lpData], rax; lpData
0x180030b04  call    cs:__imp_RegQueryValueExW
0x180030b0b  nop     dword ptr [rax+rax+00h]
0x180030b10  mov     edx, eax
0x180030b12  test    eax, eax
0x180030b14  jnz     short loc_180030B73
0x180030b16  mov     eax, [rbp+Type]
0x180030b19  cmp     eax, [rbp+arg_20]
0x180030b1c  jz      short loc_180030B25
0x180030b1e  mov     edx, 0Dh
0x180030b23  jmp     short loc_180030B73
0x180030b25  mov     r8d, [rbp+cbData]
0x180030b29  dec     eax
0x180030b2b  cmp     eax, 1
0x180030b2e  ja      short loc_180030B69
0x180030b30  mov     r9, [rbx+8]
0x180030b34  cmp     r8d, 2
0x180030b38  jnb     short loc_180030B46
0x180030b3a  mov     [r9], r15w
0x180030b3e  mov     dword ptr [rdi], 2
0x180030b44  jmp     short loc_180030B6C
0x180030b46  lea     ecx, [r8-1]
0x180030b4a  shr     rcx, 1
0x180030b4d  cmp     [r9+rcx*2], r15w
0x180030b52  jz      short loc_180030B69
0x180030b54  mov     rcx, r8
0x180030b57  shr     rcx, 1
0x180030b5a  mov     [r9+rcx*2], r15w
0x180030b5f  mov     eax, [rbp+cbData]
0x180030b62  add     eax, 2
0x180030b65  mov     [rdi], eax
0x180030b67  jmp     short loc_180030B6C
0x180030b69  mov     [rdi], r8d
0x180030b6c  mov     rax, [rbx+8]
0x180030b70  mov     [r14], rax
0x180030b73  mov     eax, edx
0x180030b75  mov     rbx, [rsp+30h+arg_8]
0x180030b7a  add     rsp, 30h
0x180030b7e  pop     r15
0x180030b80  pop     r14
0x180030b82  pop     rdi
0x180030b83  pop     rsi
0x180030b84  pop     rbp
0x180030b85  retn
```
