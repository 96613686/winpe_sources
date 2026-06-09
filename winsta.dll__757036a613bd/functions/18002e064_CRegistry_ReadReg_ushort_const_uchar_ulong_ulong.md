# CRegistry::ReadReg(ushort const *,uchar * *,ulong *,ulong)

- ea: `0x18002e064`
- end: `0x18002e182`
- name: `?ReadReg@CRegistry@@QEAAKPEBGPEAPEAEPEAKK@Z`
- size: `286`
- prototype: `unsigned int __usercall@<eax>(CRegistry *__hidden this@<rcx>, LPCWSTR lpValueName@<rdx>, unsigned __int8 **@<r8>, unsigned int *@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002e188`
- `0x18002e1d0`

## callees

- `0x18002dfa8`
- `0x18002e064`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e0aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e106`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e0aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e106`

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
0x18002e064  mov     [rsp-28h+arg_8], rbx
0x18002e069  push    rbp
0x18002e06a  push    rsi
0x18002e06b  push    rdi
0x18002e06c  push    r14
0x18002e06e  push    r15
0x18002e070  mov     rbp, rsp
0x18002e073  sub     rsp, 30h
0x18002e077  xor     r15d, r15d
0x18002e07a  lea     rax, [rbp+cbData]
0x18002e07e  mov     [r9], r15d
0x18002e081  mov     rdi, r9
0x18002e084  mov     r14, r8
0x18002e087  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002e08c  mov     rbx, rcx
0x18002e08f  mov     [rbp+Type], r15d
0x18002e093  mov     rcx, [rcx+18h]; hKey
0x18002e097  lea     r9, [rbp+Type]; lpType
0x18002e09b  xor     r8d, r8d; lpReserved
0x18002e09e  mov     [rbp+cbData], r15d
0x18002e0a2  mov     rsi, rdx
0x18002e0a5  mov     [rsp+30h+lpData], r15; lpData
0x18002e0aa  call    cs:__imp_RegQueryValueExW
0x18002e0b0  mov     edx, eax
0x18002e0b2  test    eax, eax
0x18002e0b4  jnz     loc_18002E16F
0x18002e0ba  mov     eax, [rbp+Type]
0x18002e0bd  cmp     eax, [rbp+arg_20]
0x18002e0c0  jnz     short loc_18002E11A
0x18002e0c2  mov     edx, [rbp+cbData]
0x18002e0c5  dec     eax
0x18002e0c7  cmp     eax, 1
0x18002e0ca  ja      short loc_18002E0CF
0x18002e0cc  add     edx, 2; unsigned int
0x18002e0cf  mov     rcx, rbx; this
0x18002e0d2  call    ?Allocate@CRegistry@@AEAAPEAXK@Z; CRegistry::Allocate(ulong)
0x18002e0d7  test    rax, rax
0x18002e0da  jnz     short loc_18002E0E6
0x18002e0dc  mov     eax, 0Eh
0x18002e0e1  jmp     loc_18002E171
0x18002e0e6  mov     rcx, [rbx+18h]; hKey
0x18002e0ea  lea     rax, [rbp+cbData]
0x18002e0ee  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002e0f3  lea     r9, [rbp+Type]; lpType
0x18002e0f7  mov     rax, [rbx+8]
0x18002e0fb  xor     r8d, r8d; lpReserved
0x18002e0fe  mov     rdx, rsi; lpValueName
0x18002e101  mov     [rsp+30h+lpData], rax; lpData
0x18002e106  call    cs:__imp_RegQueryValueExW
0x18002e10c  mov     edx, eax
0x18002e10e  test    eax, eax
0x18002e110  jnz     short loc_18002E16F
0x18002e112  mov     eax, [rbp+Type]
0x18002e115  cmp     eax, [rbp+arg_20]
0x18002e118  jz      short loc_18002E121
0x18002e11a  mov     edx, 0Dh
0x18002e11f  jmp     short loc_18002E16F
0x18002e121  mov     r8d, [rbp+cbData]
0x18002e125  dec     eax
0x18002e127  cmp     eax, 1
0x18002e12a  ja      short loc_18002E165
0x18002e12c  mov     r9, [rbx+8]
0x18002e130  cmp     r8d, 2
0x18002e134  jnb     short loc_18002E142
0x18002e136  mov     [r9], r15w
0x18002e13a  mov     dword ptr [rdi], 2
0x18002e140  jmp     short loc_18002E168
0x18002e142  lea     ecx, [r8-1]
0x18002e146  shr     rcx, 1
0x18002e149  cmp     [r9+rcx*2], r15w
0x18002e14e  jz      short loc_18002E165
0x18002e150  mov     rcx, r8
0x18002e153  shr     rcx, 1
0x18002e156  mov     [r9+rcx*2], r15w
0x18002e15b  mov     eax, [rbp+cbData]
0x18002e15e  add     eax, 2
0x18002e161  mov     [rdi], eax
0x18002e163  jmp     short loc_18002E168
0x18002e165  mov     [rdi], r8d
0x18002e168  mov     rax, [rbx+8]
0x18002e16c  mov     [r14], rax
0x18002e16f  mov     eax, edx
0x18002e171  mov     rbx, [rsp+30h+arg_8]
0x18002e176  add     rsp, 30h
0x18002e17a  pop     r15
0x18002e17c  pop     r14
0x18002e17e  pop     rdi
0x18002e17f  pop     rsi
0x18002e180  pop     rbp
0x18002e181  retn
```
