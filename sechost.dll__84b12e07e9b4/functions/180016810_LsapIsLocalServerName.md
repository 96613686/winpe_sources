# LsapIsLocalServerName

- ea: `0x180016810`
- end: `0x180016982`
- name: `LsapIsLocalServerName`
- size: `370`
- prototype: `__int64 __fastcall(size_t MaxCount, wchar_t *String2)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014d30`
- `0x180016aec`

## callees

- `0x180016810`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800168be`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180016900`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18001694a`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800168be`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180016900`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18001694a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800168e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001692c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800168e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001692c`

## pseudocode

```c
__int64 __fastcall LsapIsLocalServerName(size_t MaxCount, wchar_t *String2, _BYTE *a3)
{
  const wchar_t *v4; // rdi
  size_t v5; // rbx
  unsigned int v6; // r14d
  unsigned int i; // ebp
  DWORD nSize[4]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-258h] BYREF

  nSize[0] = 261;
  *a3 = 0;
  v4 = String2;
  v5 = MaxCount;
  v6 = 0;
  if ( !String2 || !MaxCount || !*String2 )
  {
    *a3 = 1;
    return v6;
  }
  if ( MaxCount > 1 && *String2 == 92 && String2[1] == 92 )
  {
    v5 = MaxCount - 2;
    if ( MaxCount == 2 )
      return (unsigned int)-1073741534;
    v4 = String2 + 2;
  }
  for ( i = 0; i < 2; ++i )
  {
    if ( v5 == dword_180064790[i] && !_wcsnicmp(off_180054030[i], v4, v5) )
      goto LABEL_24;
  }
  if ( v5 <= 0xF
    && GetComputerNameExW(ComputerNameNetBIOS, Buffer, nSize)
    && v5 == nSize[0]
    && !_wcsnicmp(Buffer, v4, v5) )
  {
    goto LABEL_24;
  }
  if ( v4[v5 - 1] == 46 )
    --v5;
  nSize[0] = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, nSize) )
  {
    if ( v5 == nSize[0] && !_wcsnicmp(Buffer, v4, v5) )
LABEL_24:
      *a3 = 1;
  }
  return v6;
}

```

## disassembly

```asm
0x180016810  push    rbx
0x180016812  push    rbp
0x180016813  push    rsi
0x180016814  push    rdi
0x180016815  push    r12
0x180016817  push    r14
0x180016819  push    r15
0x18001681b  sub     rsp, 250h
0x180016822  mov     rax, cs:__security_cookie
0x180016829  xor     rax, rsp
0x18001682c  mov     [rsp+288h+var_48], rax
0x180016834  xor     r15d, r15d
0x180016837  mov     [rsp+288h+nSize], 105h
0x18001683f  mov     [r8], r15b
0x180016842  mov     rsi, r8
0x180016845  mov     rdi, rdx
0x180016848  mov     rbx, rcx
0x18001684b  mov     r14d, r15d
0x18001684e  test    rdx, rdx
0x180016851  jz      loc_180016959
0x180016857  test    rcx, rcx
0x18001685a  jz      loc_180016959
0x180016860  cmp     [rdx], r15w
0x180016864  jz      loc_180016959
0x18001686a  cmp     rcx, 1
0x18001686e  jbe     short loc_180016892
0x180016870  cmp     word ptr [rdx], 5Ch ; '\'
0x180016874  jnz     short loc_180016892
0x180016876  cmp     word ptr [rdx+2], 5Ch ; '\'
0x18001687b  jnz     short loc_180016892
0x18001687d  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180016881  jnz     short loc_18001688E
0x180016883  mov     r14d, 0C0000122h
0x180016889  jmp     loc_18001695D
0x18001688e  add     rdi, 4
0x180016892  mov     ebp, r15d
0x180016895  lea     r12, __ImageBase
0x18001689c  cmp     ebp, 2
0x18001689f  jnb     short loc_1800168D0
0x1800168a1  mov     ecx, ebp
0x1800168a3  mov     eax, ds:rva dword_180064790[r12+rcx*4]
0x1800168ab  cmp     rbx, rax
0x1800168ae  jnz     short loc_1800168CC
0x1800168b0  mov     rcx, ds:rva off_180054030[r12+rcx*8]; String1
0x1800168b8  mov     r8, rbx; MaxCount
0x1800168bb  mov     rdx, rdi; String2
0x1800168be  call    cs:__imp__wcsnicmp
0x1800168c4  test    eax, eax
0x1800168c6  jz      loc_180016954
0x1800168cc  inc     ebp
0x1800168ce  jmp     short loc_18001689C
0x1800168d0  cmp     rbx, 0Fh
0x1800168d4  ja      short loc_18001690A
0x1800168d6  lea     r8, [rsp+288h+nSize]; nSize
0x1800168db  xor     ecx, ecx; NameType
0x1800168dd  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x1800168e2  call    cs:__imp_GetComputerNameExW
0x1800168e8  test    eax, eax
0x1800168ea  jz      short loc_18001690A
0x1800168ec  mov     eax, [rsp+288h+nSize]
0x1800168f0  cmp     rbx, rax
0x1800168f3  jnz     short loc_18001690A
0x1800168f5  mov     r8, rbx; MaxCount
0x1800168f8  lea     rcx, [rsp+288h+Buffer]; String1
0x1800168fd  mov     rdx, rdi; String2
0x180016900  call    cs:__imp__wcsnicmp
0x180016906  test    eax, eax
0x180016908  jz      short loc_180016954
0x18001690a  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x180016910  jnz     short loc_180016915
0x180016912  dec     rbx
0x180016915  lea     r8, [rsp+288h+nSize]; nSize
0x18001691a  mov     [rsp+288h+nSize], 105h
0x180016922  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x180016927  mov     ecx, 3; NameType
0x18001692c  call    cs:__imp_GetComputerNameExW
0x180016932  test    eax, eax
0x180016934  jz      short loc_18001695D
0x180016936  mov     eax, [rsp+288h+nSize]
0x18001693a  cmp     rbx, rax
0x18001693d  jnz     short loc_18001695D
0x18001693f  mov     r8, rbx; MaxCount
0x180016942  lea     rcx, [rsp+288h+Buffer]; String1
0x180016947  mov     rdx, rdi; String2
0x18001694a  call    cs:__imp__wcsnicmp
0x180016950  test    eax, eax
0x180016952  jnz     short loc_18001695D
0x180016954  mov     byte ptr [rsi], 1
0x180016957  jmp     short loc_18001695D
0x180016959  mov     byte ptr [r8], 1
0x18001695d  mov     eax, r14d
0x180016960  mov     rcx, [rsp+288h+var_48]
0x180016968  xor     rcx, rsp; StackCookie
0x18001696b  call    __security_check_cookie
0x180016970  add     rsp, 250h
0x180016977  pop     r15
0x180016979  pop     r14
0x18001697b  pop     r12
0x18001697d  pop     rdi
0x18001697e  pop     rsi
0x18001697f  pop     rbp
0x180016980  pop     rbx
0x180016981  retn
```
