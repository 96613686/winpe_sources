# GetCardProperty

- ea: `0x180036b04`
- end: `0x180036c9a`
- name: `GetCardProperty`
- size: `406`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18002e6d4`
- `0x180030500`
- `0x180034854`

## callees

- `0x18000d9d0`
- `0x18002b140`
- `0x180036b04`
- `0x18003c20e`
- `0x18003d010`

## string_xrefs

- `0x180036bba`: `Read Only Mode`
- `0x180036bd1`: `Cache Mode`

## pseudocode

```c
__int64 __fastcall GetCardProperty(__int64 a1, const wchar_t *a2, _QWORD *a3, __int64 a4, int a5)
{
  size_t v9; // rbx
  _DWORD *v10; // rax
  void *v11; // rdi
  unsigned int v12; // ebx
  size_t v13; // rcx
  _DWORD *v14; // rax

  if ( !wcscmp_0(a2, L"Free Space") )
  {
    v9 = 16;
    goto LABEL_3;
  }
  if ( !wcscmp_0(a2, L"Capabilities") )
  {
    v9 = 12;
    goto LABEL_3;
  }
  if ( !wcscmp_0(a2, L"Key Sizes") )
  {
    v9 = 20;
LABEL_3:
    v10 = MIDL_user_allocate(v9);
    v11 = v10;
    if ( v10 )
    {
      *v10 = 1;
      goto LABEL_5;
    }
    return 14;
  }
  if ( !wcscmp_0(a2, L"Read Only Mode")
    || !wcscmp_0(a2, L"Cache Mode")
    || !wcscmp_0(a2, L"PIN List")
    || !wcscmp_0(a2, L"Supports Windows x.509 Enrollment") )
  {
    v13 = 4;
    LODWORD(v9) = 4;
  }
  else
  {
    if ( wcscmp_0(a2, L"Card Identifier") )
    {
      if ( wcscmp_0(a2, L"PIN Information") )
        return 160;
      LODWORD(v9) = 36;
      v14 = MIDL_user_allocate(0x24u);
      v11 = v14;
      if ( !v14 )
        return 14;
      *v14 = 6;
      goto LABEL_5;
    }
    LODWORD(v9) = 16;
    v13 = 16;
  }
  v11 = MIDL_user_allocate(v13);
  if ( !v11 )
    return 14;
LABEL_5:
  v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, void *, _QWORD, __int64, int))(a1 + 400))(
          a1,
          a2,
          v11,
          (unsigned int)v9,
          a4,
          a5);
  if ( v12 )
  {
    if ( v11 )
      CspFreeH(v11);
  }
  else
  {
    *a3 = v11;
  }
  return v12;
}

```

## disassembly

```asm
0x180036b04  push    rbx
0x180036b06  push    rbp
0x180036b07  push    rsi
0x180036b08  push    rdi
0x180036b09  push    r14
0x180036b0b  push    r15
0x180036b0d  sub     rsp, 48h
0x180036b11  mov     rsi, rdx
0x180036b14  mov     rbp, rcx
0x180036b17  mov     rcx, rsi; String1
0x180036b1a  lea     rdx, aFreeSpace; "Free Space"
0x180036b21  mov     r15, r9
0x180036b24  mov     r14, r8
0x180036b27  call    wcscmp_0
0x180036b2c  test    eax, eax
0x180036b2e  jnz     short loc_180036B87
0x180036b30  lea     ebx, [rax+10h]
0x180036b33  mov     rcx, rbx; size
0x180036b36  call    MIDL_user_allocate
0x180036b3b  mov     rdi, rax
0x180036b3e  test    rax, rax
0x180036b41  jz      loc_180036C37
0x180036b47  mov     dword ptr [rax], 1
0x180036b4d  mov     ecx, [rsp+78h+arg_20]
0x180036b54  mov     r9d, ebx
0x180036b57  mov     rax, [rbp+190h]
0x180036b5e  mov     r8, rdi
0x180036b61  mov     [rsp+78h+var_50], ecx
0x180036b65  mov     rdx, rsi
0x180036b68  mov     rcx, rbp
0x180036b6b  mov     [rsp+78h+var_58], r15
0x180036b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b75  mov     ebx, eax
0x180036b77  test    eax, eax
0x180036b79  jnz     loc_180036C7E
0x180036b7f  mov     [r14], rdi
0x180036b82  jmp     loc_180036C8B
0x180036b87  lea     rdx, aCapabilities; "Capabilities"
0x180036b8e  mov     rcx, rsi; String1
0x180036b91  call    wcscmp_0
0x180036b96  test    eax, eax
0x180036b98  jnz     short loc_180036B9F
0x180036b9a  lea     ebx, [rax+0Ch]
0x180036b9d  jmp     short loc_180036B33
0x180036b9f  lea     rdx, aKeySizes; "Key Sizes"
0x180036ba6  mov     rcx, rsi; String1
0x180036ba9  call    wcscmp_0
0x180036bae  test    eax, eax
0x180036bb0  jnz     short loc_180036BBA
0x180036bb2  lea     ebx, [rax+14h]
0x180036bb5  jmp     loc_180036B33
0x180036bba  lea     rdx, aReadOnlyMode; "Read Only Mode"
0x180036bc1  mov     rcx, rsi; String1
0x180036bc4  call    wcscmp_0
0x180036bc9  test    eax, eax
0x180036bcb  jz      loc_180036C75
0x180036bd1  lea     rdx, aCacheMode; "Cache Mode"
0x180036bd8  mov     rcx, rsi; String1
0x180036bdb  call    wcscmp_0
0x180036be0  test    eax, eax
0x180036be2  jz      loc_180036C75
0x180036be8  lea     rdx, aPinList; "PIN List"
0x180036bef  mov     rcx, rsi; String1
0x180036bf2  call    wcscmp_0
0x180036bf7  test    eax, eax
0x180036bf9  jz      short loc_180036C75
0x180036bfb  lea     rdx, aSupportsWindow; "Supports Windows x.509 Enrollment"
0x180036c02  mov     rcx, rsi; String1
0x180036c05  call    wcscmp_0
0x180036c0a  test    eax, eax
0x180036c0c  jz      short loc_180036C75
0x180036c0e  lea     rdx, aCardIdentifier; "Card Identifier"
0x180036c15  mov     rcx, rsi; String1
0x180036c18  call    wcscmp_0
0x180036c1d  test    eax, eax
0x180036c1f  jnz     short loc_180036C3E
0x180036c21  lea     ebx, [rax+10h]
0x180036c24  mov     ecx, ebx; size
0x180036c26  call    MIDL_user_allocate
0x180036c2b  mov     rdi, rax
0x180036c2e  test    rax, rax
0x180036c31  jnz     loc_180036B4D
0x180036c37  mov     ebx, 0Eh
0x180036c3c  jmp     short loc_180036C8B
0x180036c3e  lea     rdx, aPinInformation; "PIN Information"
0x180036c45  mov     rcx, rsi; String1
0x180036c48  call    wcscmp_0
0x180036c4d  test    eax, eax
0x180036c4f  jnz     short loc_180036C6E
0x180036c51  lea     ebx, [rax+24h]
0x180036c54  mov     ecx, ebx; size
0x180036c56  call    MIDL_user_allocate
0x180036c5b  mov     rdi, rax
0x180036c5e  test    rax, rax
0x180036c61  jz      short loc_180036C37
0x180036c63  mov     dword ptr [rax], 6
0x180036c69  jmp     loc_180036B4D
0x180036c6e  mov     ebx, 0A0h
0x180036c73  jmp     short loc_180036C8B
0x180036c75  mov     ecx, 4
0x180036c7a  mov     ebx, ecx
0x180036c7c  jmp     short loc_180036C26
0x180036c7e  test    rdi, rdi
0x180036c81  jz      short loc_180036C8B
0x180036c83  mov     rcx, rdi
0x180036c86  call    CspFreeH
0x180036c8b  mov     eax, ebx
0x180036c8d  add     rsp, 48h
0x180036c91  pop     r15
0x180036c93  pop     r14
0x180036c95  pop     rdi
0x180036c96  pop     rsi
0x180036c97  pop     rbp
0x180036c98  pop     rbx
0x180036c99  retn
```
