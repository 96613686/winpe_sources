# ScClientCanonicalizeServerName(ushort const *,ushort * *)

- ea: `0x18003af94`
- end: `0x18003b14e`
- name: `?ScClientCanonicalizeServerName@@YAKPEBGPEAPEAG@Z`
- size: `442`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b9a0`
- `0x18003ac6c`

## callees

- `0x18000a17c`
- `0x18003af94`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18003b09b`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18003b0e2`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18003b09b`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18003b0e2`
- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18003b041`
- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18003b059`
- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18003b041`
- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18003b059`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b0f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b0f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003b080`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003b0c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003b080`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003b0c7`

## pseudocode

```c
__int64 __fastcall ScClientCanonicalizeServerName(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v4; // rbx
  __int64 v6; // rsi
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r11
  DWORD nSize; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[8]; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h]
  WCHAR String1[256]; // [rsp+50h] [rbp-B0h] BYREF

  nSize = 0;
  *(_OWORD *)Buffer = 0;
  v11 = 0;
  memset_0(String1, 0, sizeof(String1));
  v4 = -1;
  *a2 = 0;
  do
    ++v4;
  while ( a1[v4] );
  if ( (_DWORD)v4 )
  {
    if ( (unsigned int)v4 >= 2 && *a1 == 92 && a1[1] == 92 )
    {
      LODWORD(v4) = v4 - 2;
      if ( !(_DWORD)v4 )
        return 1210;
      a1 += 2;
    }
    if ( _wcsicmp(a1, L"localhost") )
    {
      if ( _wcsicmp(a1, L".") )
      {
        if ( (unsigned int)v4 > 0xF
          || (nSize = 16, !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize))
          || (_DWORD)v4 != nSize
          || _wcsnicmp(Buffer, a1, (unsigned int)v4) )
        {
          v6 = (unsigned int)(v4 - 1);
          nSize = 256;
          if ( a1[v6] != 46 )
            LODWORD(v6) = v4;
          if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, String1, &nSize)
            || (_DWORD)v6 != nSize
            || _wcsnicmp(String1, a1, (unsigned int)v6) )
          {
            v7 = (unsigned __int16 *)LocalAlloc(0, 2LL * (unsigned int)(v4 + 3));
            if ( !v7 )
              return 8;
            *(_DWORD *)v7 = 6029404;
            StringCchCopyW(v7 + 2, (unsigned int)(v4 + 1), a1);
            *a2 = v8;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003af94  mov     [rsp-8+arg_10], rbx
0x18003af99  mov     [rsp-8+arg_18], rsi
0x18003af9e  push    rbp
0x18003af9f  push    rdi
0x18003afa0  push    r12
0x18003afa2  push    r14
0x18003afa4  push    r15
0x18003afa6  lea     rbp, [rsp-160h]
0x18003afae  sub     rsp, 260h
0x18003afb5  mov     rax, cs:__security_cookie
0x18003afbc  xor     rax, rsp
0x18003afbf  mov     [rbp+180h+var_30], rax
0x18003afc6  xorps   xmm0, xmm0
0x18003afc9  mov     r14, rdx
0x18003afcc  mov     rdi, rcx
0x18003afcf  xor     r15d, r15d
0x18003afd2  xor     edx, edx; Val
0x18003afd4  mov     [rsp+280h+nSize], r15d
0x18003afd9  lea     rcx, [rsp+280h+String1]; void *
0x18003afde  mov     r8d, 200h; Size
0x18003afe4  movups  xmmword ptr [rsp+280h+Buffer], xmm0
0x18003afe9  movups  [rsp+280h+var_248], xmm0
0x18003afee  call    memset_0
0x18003aff3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003aff7  mov     [r14], r15
0x18003affa  inc     rbx
0x18003affd  cmp     [rdi+rbx*2], r15w
0x18003b002  jnz     short loc_18003AFFA
0x18003b004  test    ebx, ebx
0x18003b006  jz      loc_18003B120
0x18003b00c  mov     r12d, 5Ch ; '\'
0x18003b012  cmp     ebx, 2
0x18003b015  jb      short loc_18003B037
0x18003b017  cmp     [rdi], r12w
0x18003b01b  jnz     short loc_18003B037
0x18003b01d  cmp     [rdi+2], r12w
0x18003b022  jnz     short loc_18003B037
0x18003b024  add     ebx, 0FFFFFFFEh
0x18003b027  jnz     short loc_18003B033
0x18003b029  mov     eax, 4BAh
0x18003b02e  jmp     loc_18003B123
0x18003b033  add     rdi, 4
0x18003b037  lea     rdx, aLocalhost; "localhost"
0x18003b03e  mov     rcx, rdi; String1
0x18003b041  call    cs:__imp__wcsicmp
0x18003b047  test    eax, eax
0x18003b049  jz      loc_18003B120
0x18003b04f  lea     rdx, asc_1800632BC; "."
0x18003b056  mov     rcx, rdi; String1
0x18003b059  call    cs:__imp__wcsicmp
0x18003b05f  test    eax, eax
0x18003b061  jz      loc_18003B120
0x18003b067  cmp     ebx, 0Fh
0x18003b06a  ja      short loc_18003B0A5
0x18003b06c  lea     r8, [rsp+280h+nSize]; nSize
0x18003b071  mov     [rsp+280h+nSize], 10h
0x18003b079  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x18003b07e  xor     ecx, ecx; NameType
0x18003b080  call    cs:__imp_GetComputerNameExW
0x18003b086  test    eax, eax
0x18003b088  jz      short loc_18003B0A5
0x18003b08a  cmp     ebx, [rsp+280h+nSize]
0x18003b08e  jnz     short loc_18003B0A5
0x18003b090  mov     r8d, ebx; MaxCount
0x18003b093  lea     rcx, [rsp+280h+Buffer]; String1
0x18003b098  mov     rdx, rdi; String2
0x18003b09b  call    cs:__imp__wcsnicmp
0x18003b0a1  test    eax, eax
0x18003b0a3  jz      short loc_18003B120
0x18003b0a5  lea     esi, [rbx-1]
0x18003b0a8  mov     [rsp+280h+nSize], 100h
0x18003b0b0  cmp     word ptr [rdi+rsi*2], 2Eh ; '.'
0x18003b0b5  lea     r8, [rsp+280h+nSize]; nSize
0x18003b0ba  lea     rdx, [rsp+280h+String1]; lpBuffer
0x18003b0bf  mov     ecx, 3; NameType
0x18003b0c4  cmovnz  esi, ebx
0x18003b0c7  call    cs:__imp_GetComputerNameExW
0x18003b0cd  test    eax, eax
0x18003b0cf  jz      short loc_18003B0EC
0x18003b0d1  cmp     esi, [rsp+280h+nSize]
0x18003b0d5  jnz     short loc_18003B0EC
0x18003b0d7  mov     r8d, esi; MaxCount
0x18003b0da  lea     rcx, [rsp+280h+String1]; String1
0x18003b0df  mov     rdx, rdi; String2
0x18003b0e2  call    cs:__imp__wcsnicmp
0x18003b0e8  test    eax, eax
0x18003b0ea  jz      short loc_18003B120
0x18003b0ec  lea     edx, [rbx+3]
0x18003b0ef  xor     ecx, ecx; uFlags
0x18003b0f1  add     rdx, rdx; uBytes
0x18003b0f4  call    cs:__imp_LocalAlloc
0x18003b0fa  mov     r11, rax
0x18003b0fd  test    rax, rax
0x18003b100  jnz     short loc_18003B108
0x18003b102  lea     eax, [r11+8]
0x18003b106  jmp     short loc_18003B123
0x18003b108  lea     edx, [rbx+1]; unsigned __int64
0x18003b10b  mov     dword ptr [rax], 5C005Ch
0x18003b111  lea     rcx, [rax+4]; unsigned __int16 *
0x18003b115  mov     r8, rdi; unsigned __int16 *
0x18003b118  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b11d  mov     [r14], r11
0x18003b120  mov     eax, r15d
0x18003b123  mov     rcx, [rbp+180h+var_30]
0x18003b12a  xor     rcx, rsp; StackCookie
0x18003b12d  call    __security_check_cookie
0x18003b132  lea     r11, [rsp+280h+var_20]
0x18003b13a  mov     rbx, [r11+40h]
0x18003b13e  mov     rsi, [r11+48h]
0x18003b142  mov     rsp, r11
0x18003b145  pop     r15
0x18003b147  pop     r14
0x18003b149  pop     r12
0x18003b14b  pop     rdi
0x18003b14c  pop     rbp
0x18003b14d  retn
```
