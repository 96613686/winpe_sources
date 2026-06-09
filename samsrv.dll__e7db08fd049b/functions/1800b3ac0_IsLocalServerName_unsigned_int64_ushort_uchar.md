# IsLocalServerName(unsigned __int64,ushort *,uchar *)

- ea: `0x1800b3ac0`
- end: `0x1800b3c32`
- name: `?IsLocalServerName@@YAJ_KPEAGPEAE@Z`
- size: `370`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b40e0`

## callees

- `0x18002cd80`
- `0x1800b3ac0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b3b6e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b3bb0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b3bfa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b3b6e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b3bb0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b3bfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b3b92`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b3bdc`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b3b92`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b3bdc`

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
    if ( v5 == dword_1800D5B48[i] && !(unsigned int)_o__wcsnicmp(off_1800C3810[i], v4, v5) )
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
0x1800b3ac0  push    rbx
0x1800b3ac2  push    rbp
0x1800b3ac3  push    rsi
0x1800b3ac4  push    rdi
0x1800b3ac5  push    r12
0x1800b3ac7  push    r14
0x1800b3ac9  push    r15
0x1800b3acb  sub     rsp, 250h
0x1800b3ad2  mov     rax, cs:__security_cookie
0x1800b3ad9  xor     rax, rsp
0x1800b3adc  mov     [rsp+288h+var_48], rax
0x1800b3ae4  xor     r15d, r15d
0x1800b3ae7  mov     [rsp+288h+nSize], 105h
0x1800b3aef  mov     [r8], r15b
0x1800b3af2  mov     rsi, r8
0x1800b3af5  mov     rdi, rdx
0x1800b3af8  mov     rbx, rcx
0x1800b3afb  mov     r14d, r15d
0x1800b3afe  test    rdx, rdx
0x1800b3b01  jz      loc_1800B3C09
0x1800b3b07  test    rcx, rcx
0x1800b3b0a  jz      loc_1800B3C09
0x1800b3b10  cmp     [rdx], r15w
0x1800b3b14  jz      loc_1800B3C09
0x1800b3b1a  cmp     rcx, 1
0x1800b3b1e  jbe     short loc_1800B3B42
0x1800b3b20  cmp     word ptr [rdx], 5Ch ; '\'
0x1800b3b24  jnz     short loc_1800B3B42
0x1800b3b26  cmp     word ptr [rdx+2], 5Ch ; '\'
0x1800b3b2b  jnz     short loc_1800B3B42
0x1800b3b2d  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1800b3b31  jnz     short loc_1800B3B3E
0x1800b3b33  mov     r14d, 0C0000122h
0x1800b3b39  jmp     loc_1800B3C0D
0x1800b3b3e  add     rdi, 4
0x1800b3b42  mov     ebp, r15d
0x1800b3b45  lea     r12, __ImageBase
0x1800b3b4c  cmp     ebp, 2
0x1800b3b4f  jnb     short loc_1800B3B80
0x1800b3b51  mov     ecx, ebp
0x1800b3b53  mov     eax, ds:rva dword_1800D5B48[r12+rcx*4]
0x1800b3b5b  cmp     rbx, rax
0x1800b3b5e  jnz     short loc_1800B3B7C
0x1800b3b60  mov     rcx, ds:rva off_1800C3810[r12+rcx*8]; "localhost" ...
0x1800b3b68  mov     r8, rbx
0x1800b3b6b  mov     rdx, rdi
0x1800b3b6e  call    cs:__imp__o__wcsnicmp
0x1800b3b74  test    eax, eax
0x1800b3b76  jz      loc_1800B3C04
0x1800b3b7c  inc     ebp
0x1800b3b7e  jmp     short loc_1800B3B4C
0x1800b3b80  cmp     rbx, 0Fh
0x1800b3b84  ja      short loc_1800B3BBA
0x1800b3b86  lea     r8, [rsp+288h+nSize]; nSize
0x1800b3b8b  xor     ecx, ecx; NameType
0x1800b3b8d  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x1800b3b92  call    cs:__imp_GetComputerNameExW
0x1800b3b98  test    eax, eax
0x1800b3b9a  jz      short loc_1800B3BBA
0x1800b3b9c  mov     eax, [rsp+288h+nSize]
0x1800b3ba0  cmp     rbx, rax
0x1800b3ba3  jnz     short loc_1800B3BBA
0x1800b3ba5  mov     r8, rbx
0x1800b3ba8  lea     rcx, [rsp+288h+Buffer]
0x1800b3bad  mov     rdx, rdi
0x1800b3bb0  call    cs:__imp__o__wcsnicmp
0x1800b3bb6  test    eax, eax
0x1800b3bb8  jz      short loc_1800B3C04
0x1800b3bba  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x1800b3bc0  jnz     short loc_1800B3BC5
0x1800b3bc2  dec     rbx
0x1800b3bc5  lea     r8, [rsp+288h+nSize]; nSize
0x1800b3bca  mov     [rsp+288h+nSize], 105h
0x1800b3bd2  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x1800b3bd7  mov     ecx, 3; NameType
0x1800b3bdc  call    cs:__imp_GetComputerNameExW
0x1800b3be2  test    eax, eax
0x1800b3be4  jz      short loc_1800B3C0D
0x1800b3be6  mov     eax, [rsp+288h+nSize]
0x1800b3bea  cmp     rbx, rax
0x1800b3bed  jnz     short loc_1800B3C0D
0x1800b3bef  mov     r8, rbx
0x1800b3bf2  lea     rcx, [rsp+288h+Buffer]
0x1800b3bf7  mov     rdx, rdi
0x1800b3bfa  call    cs:__imp__o__wcsnicmp
0x1800b3c00  test    eax, eax
0x1800b3c02  jnz     short loc_1800B3C0D
0x1800b3c04  mov     byte ptr [rsi], 1
0x1800b3c07  jmp     short loc_1800B3C0D
0x1800b3c09  mov     byte ptr [r8], 1
0x1800b3c0d  mov     eax, r14d
0x1800b3c10  mov     rcx, [rsp+288h+var_48]
0x1800b3c18  xor     rcx, rsp; StackCookie
0x1800b3c1b  call    __security_check_cookie
0x1800b3c20  add     rsp, 250h
0x1800b3c27  pop     r15
0x1800b3c29  pop     r14
0x1800b3c2b  pop     r12
0x1800b3c2d  pop     rdi
0x1800b3c2e  pop     rsi
0x1800b3c2f  pop     rbp
0x1800b3c30  pop     rbx
0x1800b3c31  retn
```
