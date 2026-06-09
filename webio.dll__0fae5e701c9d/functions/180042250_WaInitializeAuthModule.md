# WaInitializeAuthModule

- ea: `0x180042250`
- end: `0x180042360`
- name: `WaInitializeAuthModule`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180041758`

## callees

- `0x180042250`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042338`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042338`
- `SspiCli!FreeContextBuffer` at `0x1800422f6`
- `SspiCli!FreeContextBuffer` at `0x1800422f6`
- `SspiCli!EnumerateSecurityPackagesW` at `0x180042285`
- `SspiCli!EnumerateSecurityPackagesW` at `0x180042285`

## pseudocode

```c
__int64 WaInitializeAuthModule()
{
  unsigned int v0; // esi
  char *v1; // rcx
  unsigned int i; // edi
  __int64 v3; // r14
  __int64 v4; // rbp
  __int64 v5; // r15
  __int64 v6; // rbx
  int v8; // eax
  PVOID pvContextBuffer; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-60h] BYREF

  pvContextBuffer = 0;
  v10 = 0;
  v0 = EnumerateSecurityPackagesW(&v10, (PSecPkgInfoW *)&pvContextBuffer);
  if ( !v0 )
  {
    v0 = 0;
    v1 = (char *)pvContextBuffer;
    for ( i = 0; i < v10; ++i )
    {
      v3 = 32LL * i;
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)(*(_QWORD *)&v1[v3 + 16] + 2 * v4) );
      v5 = 0;
      v6 = 0;
      do
      {
        if ( WaAuthSchemeProperties[v6 + 2] )
        {
          if ( WaAuthSchemeProperties[v6 + 3] == v4 )
          {
            v8 = CompareStringOrdinal((LPCWCH)WaAuthSchemeProperties[v6 + 2], v4, *(LPCWCH *)&v1[v3 + 16], v4, 1);
            v1 = (char *)pvContextBuffer;
            if ( v8 == 2 )
            {
              HIDWORD(WaAuthSchemeProperties[v6 + 4]) = *(_DWORD *)((char *)pvContextBuffer + v3 + 8);
              LOBYTE(WaAuthSchemeProperties[v6 + 5]) = 1;
            }
          }
        }
        ++v5;
        v6 += 6;
      }
      while ( v5 != 6 );
    }
    FreeContextBuffer(v1);
  }
  return v0;
}

```

## disassembly

```asm
0x180042250  mov     r11, rsp
0x180042253  push    rbx
0x180042254  push    rbp
0x180042255  push    rsi
0x180042256  push    rdi
0x180042257  push    r12
0x180042259  push    r13
0x18004225b  push    r14
0x18004225d  push    r15
0x18004225f  sub     rsp, 58h
0x180042263  mov     rax, cs:__security_cookie
0x18004226a  xor     rax, rsp
0x18004226d  mov     [rsp+98h+var_58], rax
0x180042272  xor     r12d, r12d
0x180042275  lea     rdx, [r11-68h]; ppPackageInfo
0x180042279  lea     rcx, [r11-60h]; pcPackages
0x18004227d  mov     [r11-68h], r12
0x180042281  mov     [r11-60h], r12d
0x180042285  call    cs:__imp_EnumerateSecurityPackagesW
0x18004228c  nop     dword ptr [rax+rax+00h]
0x180042291  mov     esi, eax
0x180042293  test    eax, eax
0x180042295  jnz     short loc_180042302
0x180042297  mov     esi, r12d
0x18004229a  mov     rcx, [rsp+98h+pvContextBuffer]; pvContextBuffer
0x18004229f  mov     edi, r12d
0x1800422a2  cmp     [rsp+98h+var_60], r12d
0x1800422a7  jbe     short loc_1800422F6
0x1800422a9  lea     r13, WaAuthSchemeProperties
0x1800422b0  mov     r14d, edi
0x1800422b3  shl     r14, 5
0x1800422b7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800422bb  mov     rax, [r14+rcx+10h]
0x1800422c0  inc     rbp
0x1800422c3  cmp     [rax+rbp*2], r12w
0x1800422c8  jnz     short loc_1800422C0
0x1800422ca  mov     r15, r12
0x1800422cd  mov     rbx, r12
0x1800422d0  mov     rax, [rbx+r13+10h]
0x1800422d5  test    rax, rax
0x1800422d8  jz      short loc_1800422E1
0x1800422da  cmp     [rbx+r13+18h], rbp
0x1800422df  jz      short loc_180042323
0x1800422e1  inc     r15
0x1800422e4  add     rbx, 30h ; '0'
0x1800422e8  cmp     r15, 6
0x1800422ec  jnz     short loc_1800422D0
0x1800422ee  inc     edi
0x1800422f0  cmp     edi, [rsp+98h+var_60]
0x1800422f4  jb      short loc_1800422B0
0x1800422f6  call    cs:__imp_FreeContextBuffer
0x1800422fd  nop     dword ptr [rax+rax+00h]
0x180042302  mov     eax, esi
0x180042304  mov     rcx, [rsp+98h+var_58]
0x180042309  xor     rcx, rsp; StackCookie
0x18004230c  call    __security_check_cookie
0x180042311  add     rsp, 58h
0x180042315  pop     r15
0x180042317  pop     r14
0x180042319  pop     r13
0x18004231b  pop     r12
0x18004231d  pop     rdi
0x18004231e  pop     rsi
0x18004231f  pop     rbp
0x180042320  pop     rbx
0x180042321  retn
0x180042323  mov     r8, [r14+rcx+10h]; lpString2
0x180042328  mov     r9d, ebp; cchCount2
0x18004232b  mov     rcx, rax; lpString1
0x18004232e  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x180042336  mov     edx, ebp; cchCount1
0x180042338  call    cs:__imp_CompareStringOrdinal
0x18004233f  nop     dword ptr [rax+rax+00h]
0x180042344  mov     rcx, [rsp+98h+pvContextBuffer]
0x180042349  cmp     eax, 2
0x18004234c  jnz     short loc_1800422E1
0x18004234e  mov     eax, [r14+rcx+8]
0x180042353  mov     [rbx+r13+24h], eax
0x180042358  mov     byte ptr [rbx+r13+28h], 1
0x18004235e  jmp     short loc_1800422E1
```
