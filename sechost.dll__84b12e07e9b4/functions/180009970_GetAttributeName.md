# GetAttributeName

- ea: `0x180009970`
- end: `0x180009be6`
- name: `GetAttributeName`
- size: `630`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800092d0`

## callees

- `0x180009970`
- `0x180021e20`
- `0x180022454`
- `0x18004f902`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800099a6`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800099f2`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009a7b`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009aba`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009af6`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009b35`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800099a6`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800099f2`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009a7b`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009aba`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009af6`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009b35`
- `api-ms-win-core-crt-l1-1-0!iswctype` at `0x180009a31`
- `api-ms-win-core-crt-l1-1-0!iswctype` at `0x180009a31`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009b67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009b67`

## string_xrefs

- `0x180009aec`: `@TOKEN.`

## pseudocode

```c
__int64 __fastcall GetAttributeName(wchar_t *String1, __int64 a2, unsigned int *a3)
{
  const wchar_t *v5; // rsi
  unsigned int v6; // edi
  unsigned int v7; // ebx
  int v8; // ecx
  wint_t v9; // bx
  unsigned int i; // ecx
  SIZE_T v11; // rdx
  void *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  v16 = 0;
  v5 = String1;
  v6 = 0;
  if ( _wcsnicmp(String1, L"@", 1u) )
  {
    while ( 1 )
    {
      v9 = v5[v6];
      if ( v9 > 0xFFu )
        break;
      if ( !iswctype(v9, 0x107u) )
      {
        for ( i = 0; i < 5; ++i )
        {
          if ( LegalAttributeChar[i] == v9 )
            goto LABEL_15;
        }
        break;
      }
LABEL_15:
      if ( !v5[v6] )
        break;
      ++v6;
    }
  }
  else
  {
    if ( !(unsigned __int8)IsLegalAttributeChar2(*v5) )
      return 1336;
    do
    {
      if ( !v5[v6] )
        break;
      ++v6;
    }
    while ( (unsigned __int8)IsLegalAttributeChar2(v5[v6]) );
  }
  v7 = 8;
  if ( v6 >= 8 && !_wcsnicmp(v5, L"@DEVICE.", 8u) )
  {
    if ( v6 != 8 )
    {
      v8 = 2 * v6 - 16;
      v5 += 8;
      *(_BYTE *)(*(_QWORD *)a2 + 1LL) = -5;
      goto LABEL_32;
    }
    return 1336;
  }
  if ( v6 < 0xA )
  {
    if ( v6 < 6 )
      goto LABEL_25;
    goto LABEL_22;
  }
  if ( _wcsnicmp(v5, L"@RESOURCE.", 0xAu) )
  {
LABEL_22:
    if ( !_wcsnicmp(v5, L"@USER.", 6u) )
    {
      if ( v6 == 6 )
        return 1336;
      v8 = 2 * v6 - 12;
      v5 += 6;
      *(_BYTE *)(*(_QWORD *)a2 + 1LL) = -7;
      goto LABEL_32;
    }
LABEL_25:
    if ( v6 < 7 )
    {
      if ( !v6 )
        return 1336;
    }
    else if ( !_wcsnicmp(v5, L"@TOKEN.", 7u) )
    {
      if ( v6 == 7 )
        return 1336;
      v8 = 2 * v6 - 14;
      v5 += 7;
      *(_BYTE *)(*(_QWORD *)a2 + 1LL) = -4;
      goto LABEL_32;
    }
    if ( !_wcsnicmp(v5, L"@", 1u) )
      return 1336;
    v8 = 2 * v6;
    *(_BYTE *)(*(_QWORD *)a2 + 1LL) = -8;
    goto LABEL_32;
  }
  if ( v6 == 10 )
    return 1336;
  v8 = 2 * v6 - 20;
  v5 += 10;
  *(_BYTE *)(*(_QWORD *)a2 + 1LL) = -6;
LABEL_32:
  *(_DWORD *)(*(_QWORD *)a2 + 4LL) = v8;
  *a3 = v6;
  v11 = *(unsigned int *)(*(_QWORD *)a2 + 4LL);
  if ( *(_BYTE *)(*(_QWORD *)a2 + 1LL) == 0xF8 )
  {
    *(_QWORD *)(*(_QWORD *)a2 + 8LL) = LocalAlloc(0x40u, v11);
    v12 = *(void **)(*(_QWORD *)a2 + 8LL);
    if ( v12 )
    {
      v7 = 0;
      memcpy_0(v12, v5, *(unsigned int *)(*(_QWORD *)a2 + 4LL));
    }
  }
  else
  {
    v7 = DecodeAttributeName(v5, v11, &v16);
    if ( !v7 )
    {
      v13 = v16;
      *(_QWORD *)(*(_QWORD *)a2 + 8LL) = v16;
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(v13 + 2 * v14) );
      *(_DWORD *)(*(_QWORD *)a2 + 4LL) = 2 * v14;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180009970  mov     [rsp+arg_0], rbx
0x180009975  mov     [rsp+arg_8], rbp
0x18000997a  push    rsi
0x18000997b  push    rdi
0x18000997c  push    r12
0x18000997e  push    r14
0x180009980  push    r15
0x180009982  sub     rsp, 20h
0x180009986  xor     r12d, r12d
0x180009989  mov     r15, r8
0x18000998c  mov     r14, rdx
0x18000998f  mov     [rsp+48h+arg_18], r12
0x180009994  lea     rdx, asc_18005FD14; "@"
0x18000999b  mov     rsi, rcx
0x18000999e  mov     edi, r12d
0x1800099a1  lea     r8d, [r12+1]; MaxCount
0x1800099a6  call    cs:__imp__wcsnicmp
0x1800099ac  test    eax, eax
0x1800099ae  jnz     short loc_180009A1B
0x1800099b0  movzx   ecx, word ptr [rsi]
0x1800099b3  call    IsLegalAttributeChar2
0x1800099b8  test    al, al
0x1800099ba  jz      loc_180009BC8
0x1800099c0  mov     eax, edi
0x1800099c2  cmp     [rsi+rax*2], r12w
0x1800099c7  jz      short loc_1800099D8
0x1800099c9  inc     edi
0x1800099cb  movzx   ecx, word ptr [rsi+rdi*2]
0x1800099cf  call    IsLegalAttributeChar2
0x1800099d4  test    al, al
0x1800099d6  jnz     short loc_1800099C0
0x1800099d8  mov     ebx, 8
0x1800099dd  cmp     edi, ebx
0x1800099df  jb      loc_180009A66
0x1800099e5  mov     r8d, ebx; MaxCount
0x1800099e8  lea     rdx, aDevice; "@DEVICE."
0x1800099ef  mov     rcx, rsi; String1
0x1800099f2  call    cs:__imp__wcsnicmp
0x1800099f8  test    eax, eax
0x1800099fa  jnz     short loc_180009A66
0x1800099fc  cmp     edi, ebx
0x1800099fe  jz      loc_180009BC8
0x180009a04  mov     rax, [r14]
0x180009a07  lea     ecx, ds:0FFFFFFFFFFFFFFF0h[rdi*2]
0x180009a0e  add     rsi, 10h
0x180009a12  mov     byte ptr [rax+1], 0FBh
0x180009a16  jmp     loc_180009B4D
0x180009a1b  mov     ebp, edi
0x180009a1d  mov     eax, 0FFh
0x180009a22  movzx   ebx, word ptr [rsi+rbp*2]
0x180009a26  cmp     bx, ax
0x180009a29  ja      short loc_1800099D8
0x180009a2b  lea     edx, [rax+8]; Type
0x180009a2e  movzx   ecx, bx; C
0x180009a31  call    cs:__imp_iswctype
0x180009a37  test    eax, eax
0x180009a39  jnz     short loc_180009A57
0x180009a3b  mov     ecx, r12d
0x180009a3e  cmp     ecx, 5
0x180009a41  jnb     short loc_1800099D8
0x180009a43  movsxd  rax, ecx
0x180009a46  lea     rdx, LegalAttributeChar; ":./_@"
0x180009a4d  cmp     [rdx+rax*2], bx
0x180009a51  jz      short loc_180009A57
0x180009a53  inc     ecx
0x180009a55  jmp     short loc_180009A3E
0x180009a57  cmp     [rsi+rbp*2], r12w
0x180009a5c  jz      loc_1800099D8
0x180009a62  inc     edi
0x180009a64  jmp     short loc_180009A1B
0x180009a66  cmp     edi, 0Ah
0x180009a69  jb      short loc_180009AA5
0x180009a6b  mov     r8d, 0Ah; MaxCount
0x180009a71  lea     rdx, aResource; "@RESOURCE."
0x180009a78  mov     rcx, rsi; String1
0x180009a7b  call    cs:__imp__wcsnicmp
0x180009a81  test    eax, eax
0x180009a83  jnz     short loc_180009AAA
0x180009a85  cmp     edi, 0Ah
0x180009a88  jz      loc_180009BC8
0x180009a8e  mov     rax, [r14]
0x180009a91  lea     ecx, ds:0FFFFFFFFFFFFFFECh[rdi*2]
0x180009a98  add     rsi, 14h
0x180009a9c  mov     byte ptr [rax+1], 0FAh
0x180009aa0  jmp     loc_180009B4D
0x180009aa5  cmp     edi, 6
0x180009aa8  jb      short loc_180009AE1
0x180009aaa  mov     r8d, 6; MaxCount
0x180009ab0  lea     rdx, aUser; "@USER."
0x180009ab7  mov     rcx, rsi; String1
0x180009aba  call    cs:__imp__wcsnicmp
0x180009ac0  test    eax, eax
0x180009ac2  jnz     short loc_180009AE1
0x180009ac4  cmp     edi, 6
0x180009ac7  jz      loc_180009BC8
0x180009acd  mov     rax, [r14]
0x180009ad0  lea     ecx, ds:0FFFFFFFFFFFFFFF4h[rdi*2]
0x180009ad7  add     rsi, 0Ch
0x180009adb  mov     byte ptr [rax+1], 0F9h
0x180009adf  jmp     short loc_180009B4D
0x180009ae1  cmp     edi, 7
0x180009ae4  jb      short loc_180009B1D
0x180009ae6  mov     r8d, 7; MaxCount
0x180009aec  lea     rdx, aToken; "@TOKEN."
0x180009af3  mov     rcx, rsi; String1
0x180009af6  call    cs:__imp__wcsnicmp
0x180009afc  test    eax, eax
0x180009afe  jnz     short loc_180009B25
0x180009b00  cmp     edi, 7
0x180009b03  jz      loc_180009BC8
0x180009b09  mov     rax, [r14]
0x180009b0c  lea     ecx, ds:0FFFFFFFFFFFFFFF2h[rdi*2]
0x180009b13  add     rsi, 0Eh
0x180009b17  mov     byte ptr [rax+1], 0FCh
0x180009b1b  jmp     short loc_180009B4D
0x180009b1d  test    edi, edi
0x180009b1f  jz      loc_180009BC8
0x180009b25  mov     r8d, 1; MaxCount
0x180009b2b  lea     rdx, asc_18005FD14; "@"
0x180009b32  mov     rcx, rsi; String1
0x180009b35  call    cs:__imp__wcsnicmp
0x180009b3b  test    eax, eax
0x180009b3d  jz      loc_180009BC8
0x180009b43  mov     rax, [r14]
0x180009b46  lea     ecx, [rdi+rdi]
0x180009b49  mov     byte ptr [rax+1], 0F8h
0x180009b4d  mov     rax, [r14]
0x180009b50  mov     [rax+4], ecx
0x180009b53  mov     [r15], edi
0x180009b56  mov     rax, [r14]
0x180009b59  cmp     byte ptr [rax+1], 0F8h
0x180009b5d  mov     edx, [rax+4]; uBytes
0x180009b60  jnz     short loc_180009B91
0x180009b62  mov     ecx, 40h ; '@'; uFlags
0x180009b67  call    cs:__imp_LocalAlloc
0x180009b6d  mov     rcx, [r14]
0x180009b70  mov     [rcx+8], rax
0x180009b74  mov     rax, [r14]
0x180009b77  mov     rcx, [rax+8]; void *
0x180009b7b  test    rcx, rcx
0x180009b7e  jz      short loc_180009BCD
0x180009b80  mov     r8d, [rax+4]; Size
0x180009b84  mov     rdx, rsi; Src
0x180009b87  mov     ebx, r12d
0x180009b8a  call    memcpy_0
0x180009b8f  jmp     short loc_180009BCD
0x180009b91  lea     r8, [rsp+48h+arg_18]
0x180009b96  mov     rcx, rsi
0x180009b99  call    DecodeAttributeName
0x180009b9e  mov     ebx, eax
0x180009ba0  test    eax, eax
0x180009ba2  jnz     short loc_180009BCD
0x180009ba4  mov     rcx, [r14]
0x180009ba7  mov     rax, [rsp+48h+arg_18]
0x180009bac  mov     [rcx+8], rax
0x180009bb0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009bb4  inc     rcx
0x180009bb7  cmp     [rax+rcx*2], r12w
0x180009bbc  jnz     short loc_180009BB4
0x180009bbe  mov     rax, [r14]
0x180009bc1  add     ecx, ecx
0x180009bc3  mov     [rax+4], ecx
0x180009bc6  jmp     short loc_180009BCD
0x180009bc8  mov     ebx, 538h
0x180009bcd  mov     rbp, [rsp+48h+arg_8]
0x180009bd2  mov     eax, ebx
0x180009bd4  mov     rbx, [rsp+48h+arg_0]
0x180009bd9  add     rsp, 20h
0x180009bdd  pop     r15
0x180009bdf  pop     r14
0x180009be1  pop     r12
0x180009be3  pop     rdi
0x180009be4  pop     rsi
0x180009be5  retn
```
