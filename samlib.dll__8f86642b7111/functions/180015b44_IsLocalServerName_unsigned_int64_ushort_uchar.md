# IsLocalServerName(unsigned __int64,ushort *,uchar *)

- ea: `0x180015b44`
- end: `0x180015cb6`
- name: `?IsLocalServerName@@YAJ_KPEAGPEAE@Z`
- size: `370`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int16 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015ee8`
- `0x1800163d0`

## callees

- `0x180006620`
- `0x180015b44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180015bf2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180015c34`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180015c7e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180015bf2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180015c34`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180015c7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180015c16`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180015c60`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180015c16`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180015c60`

## pseudocode

```c
__int64 __fastcall IsLocalServerName(unsigned __int64 a1, unsigned __int16 *a2, unsigned __int8 *a3)
{
  unsigned __int16 *v4; // rdi
  unsigned __int64 v5; // rbx
  unsigned int v6; // r14d
  unsigned int i; // ebp
  DWORD nSize[4]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-258h] BYREF

  nSize[0] = 261;
  *a3 = 0;
  v4 = a2;
  v5 = a1;
  v6 = 0;
  if ( !a2 || !a1 || !*a2 )
  {
    *a3 = 1;
    return v6;
  }
  if ( a1 > 1 && *a2 == 92 && a2[1] == 92 )
  {
    v5 = a1 - 2;
    if ( a1 == 2 )
      return (unsigned int)-1073741534;
    v4 = a2 + 2;
  }
  for ( i = 0; i < 2; ++i )
  {
    if ( v5 == dword_180020CF8[i] && !(unsigned int)_o__wcsnicmp(off_1800190E0[i], v4, v5) )
      goto LABEL_24;
  }
  if ( v5 <= 0xF
    && GetComputerNameExW(ComputerNameNetBIOS, Buffer, nSize)
    && v5 == nSize[0]
    && !(unsigned int)_o__wcsnicmp(Buffer, v4, v5) )
  {
    goto LABEL_24;
  }
  if ( v4[v5 - 1] == 46 )
    --v5;
  nSize[0] = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, nSize) )
  {
    if ( v5 == nSize[0] && !(unsigned int)_o__wcsnicmp(Buffer, v4, v5) )
LABEL_24:
      *a3 = 1;
  }
  return v6;
}

```

## disassembly

```asm
0x180015b44  push    rbx
0x180015b46  push    rbp
0x180015b47  push    rsi
0x180015b48  push    rdi
0x180015b49  push    r12
0x180015b4b  push    r14
0x180015b4d  push    r15
0x180015b4f  sub     rsp, 250h
0x180015b56  mov     rax, cs:__security_cookie
0x180015b5d  xor     rax, rsp
0x180015b60  mov     [rsp+288h+var_48], rax
0x180015b68  xor     r15d, r15d
0x180015b6b  mov     [rsp+288h+nSize], 105h
0x180015b73  mov     [r8], r15b
0x180015b76  mov     rsi, r8
0x180015b79  mov     rdi, rdx
0x180015b7c  mov     rbx, rcx
0x180015b7f  mov     r14d, r15d
0x180015b82  test    rdx, rdx
0x180015b85  jz      loc_180015C8D
0x180015b8b  test    rcx, rcx
0x180015b8e  jz      loc_180015C8D
0x180015b94  cmp     [rdx], r15w
0x180015b98  jz      loc_180015C8D
0x180015b9e  cmp     rcx, 1
0x180015ba2  jbe     short loc_180015BC6
0x180015ba4  cmp     word ptr [rdx], 5Ch ; '\'
0x180015ba8  jnz     short loc_180015BC6
0x180015baa  cmp     word ptr [rdx+2], 5Ch ; '\'
0x180015baf  jnz     short loc_180015BC6
0x180015bb1  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180015bb5  jnz     short loc_180015BC2
0x180015bb7  mov     r14d, 0C0000122h
0x180015bbd  jmp     loc_180015C91
0x180015bc2  add     rdi, 4
0x180015bc6  mov     ebp, r15d
0x180015bc9  lea     r12, __ImageBase
0x180015bd0  cmp     ebp, 2
0x180015bd3  jnb     short loc_180015C04
0x180015bd5  mov     ecx, ebp
0x180015bd7  mov     eax, ds:rva dword_180020CF8[r12+rcx*4]
0x180015bdf  cmp     rbx, rax
0x180015be2  jnz     short loc_180015C00
0x180015be4  mov     rcx, ds:rva off_1800190E0[r12+rcx*8]; "localhost" ...
0x180015bec  mov     r8, rbx
0x180015bef  mov     rdx, rdi
0x180015bf2  call    cs:__imp__o__wcsnicmp
0x180015bf8  test    eax, eax
0x180015bfa  jz      loc_180015C88
0x180015c00  inc     ebp
0x180015c02  jmp     short loc_180015BD0
0x180015c04  cmp     rbx, 0Fh
0x180015c08  ja      short loc_180015C3E
0x180015c0a  lea     r8, [rsp+288h+nSize]; nSize
0x180015c0f  xor     ecx, ecx; NameType
0x180015c11  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x180015c16  call    cs:__imp_GetComputerNameExW
0x180015c1c  test    eax, eax
0x180015c1e  jz      short loc_180015C3E
0x180015c20  mov     eax, [rsp+288h+nSize]
0x180015c24  cmp     rbx, rax
0x180015c27  jnz     short loc_180015C3E
0x180015c29  mov     r8, rbx
0x180015c2c  lea     rcx, [rsp+288h+Buffer]
0x180015c31  mov     rdx, rdi
0x180015c34  call    cs:__imp__o__wcsnicmp
0x180015c3a  test    eax, eax
0x180015c3c  jz      short loc_180015C88
0x180015c3e  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x180015c44  jnz     short loc_180015C49
0x180015c46  dec     rbx
0x180015c49  lea     r8, [rsp+288h+nSize]; nSize
0x180015c4e  mov     [rsp+288h+nSize], 105h
0x180015c56  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x180015c5b  mov     ecx, 3; NameType
0x180015c60  call    cs:__imp_GetComputerNameExW
0x180015c66  test    eax, eax
0x180015c68  jz      short loc_180015C91
0x180015c6a  mov     eax, [rsp+288h+nSize]
0x180015c6e  cmp     rbx, rax
0x180015c71  jnz     short loc_180015C91
0x180015c73  mov     r8, rbx
0x180015c76  lea     rcx, [rsp+288h+Buffer]
0x180015c7b  mov     rdx, rdi
0x180015c7e  call    cs:__imp__o__wcsnicmp
0x180015c84  test    eax, eax
0x180015c86  jnz     short loc_180015C91
0x180015c88  mov     byte ptr [rsi], 1
0x180015c8b  jmp     short loc_180015C91
0x180015c8d  mov     byte ptr [r8], 1
0x180015c91  mov     eax, r14d
0x180015c94  mov     rcx, [rsp+288h+var_48]
0x180015c9c  xor     rcx, rsp; StackCookie
0x180015c9f  call    __security_check_cookie
0x180015ca4  add     rsp, 250h
0x180015cab  pop     r15
0x180015cad  pop     r14
0x180015caf  pop     r12
0x180015cb1  pop     rdi
0x180015cb2  pop     rsi
0x180015cb3  pop     rbp
0x180015cb4  pop     rbx
0x180015cb5  retn
```
