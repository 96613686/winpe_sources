# ShareEnumCommonEx

- ea: `0x180008930`
- end: `0x180008c96`
- name: `ShareEnumCommonEx`
- size: `870`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, PCWSTR SourceString, PCWSTR, char, char, char, char, int)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013830`
- `0x18001fdc4`
- `0x180029220`
- `0x18002949c`
- `0x180029884`
- `0x18002a390`
- `0x18002a6e0`

## callees

- `0x180008930`
- `0x180008de0`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c60`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008993`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a91`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008993`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008a91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c81`
- `ntdll!RtlInitUnicodeString` at `0x1800089dc`
- `ntdll!RtlInitUnicodeString` at `0x1800089e9`
- `ntdll!RtlInitUnicodeString` at `0x1800089dc`
- `ntdll!RtlInitUnicodeString` at `0x1800089e9`

## pseudocode

```c
__int64 __fastcall ShareEnumCommonEx(
        unsigned int a1,
        HLOCAL *a2,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *a5,
        int *a6,
        PCWSTR SourceString,
        PCWSTR a8,
        char a9,
        char a10,
        char a11,
        char a12,
        unsigned int a13)
{
  const WCHAR *v16; // rbp
  struct _UNICODE_STRING *v17; // rax
  struct _UNICODE_STRING *v18; // rbx
  int v19; // eax
  void *v20; // rbp
  DWORD LastError; // edi
  ULONG v22; // esi
  unsigned int i; // eax
  HLOCAL v24; // rax
  DWORD v25; // eax
  int Buffer_high; // [rsp+30h] [rbp-48h]
  unsigned int v29; // [rsp+98h] [rbp+20h]

  if ( !a4 || !a5 )
    return 87;
  if ( a1 > 2 && a1 - 501 > 2 && a1 != 505 && a1 != 1005 )
    return 124;
  v16 = a8;
  if ( a8 && *a8 == 92 && a8[1] == 92 )
    v16 = a8 + 2;
  v17 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x60u);
  v18 = v17;
  if ( !v17 )
    return 8;
  *(_DWORD *)&v17[4].Length = a1;
  if ( SourceString )
    LODWORD(v17[4].Buffer) = 1;
  if ( a6 )
    v19 = *a6;
  else
    v19 = 0;
  HIDWORD(v18[5].Buffer) = v19;
  RtlInitUnicodeString(v18, SourceString);
  RtlInitUnicodeString(v18 + 1, v16);
  if ( a9 )
    LODWORD(v18[4].Buffer) = 16;
  if ( a10 )
    LODWORD(v18[4].Buffer) |= 0x40u;
  if ( a12 )
    LODWORD(v18[4].Buffer) |= 0x100u;
  if ( a11 )
    LODWORD(v18[4].Buffer) |= 0x80u;
  v20 = (void *)((__int64 (__fastcall *)(_QWORD))qword_18005E540)(a13);
  if ( v20 )
  {
    LastError = 0;
    Buffer_high = HIDWORD(v18[5].Buffer);
    if ( ((__int64)v18[4].Buffer & 1) != 0 )
    {
      v22 = 1024;
      if ( a3 <= 0x400 )
        v22 = a3;
    }
    else
    {
      v22 = a3;
      if ( a3 > 0x2000 )
        v22 = 0x2000;
    }
    *a2 = 0;
    for ( i = 0; ; i = v29 + 1 )
    {
      v29 = i;
      if ( i >= 5 )
        break;
      if ( *a2 )
        LocalFree(*a2);
      v24 = LocalAlloc(0x40u, v22);
      *a2 = v24;
      if ( !v24 )
      {
        LastError = 8;
        break;
      }
      HIDWORD(v18[5].Buffer) = Buffer_high;
      v25 = SsServerFsControlCommon(v20, 0x146033u, &v18->Length, *a2, v22);
      LastError = v25;
      if ( v25 != 2123 && v25 != 234 || v22 >= a3 )
        break;
      v22 = a3;
      if ( LODWORD(v18[5].Buffer) + 1024 < a3 )
        v22 = LODWORD(v18[5].Buffer) + 1024;
    }
    if ( *a2 && !*(_DWORD *)&v18[5].Length )
    {
      LocalFree(*a2);
      *a2 = 0;
    }
    if ( !LastError || LastError == 234 )
    {
      *a4 = *(_DWORD *)&v18[5].Length;
      *a5 = *(_DWORD *)(&v18[5].MaximumLength + 1);
      if ( *a4 )
      {
        if ( a6 )
          *a6 = HIDWORD(v18[5].Buffer);
      }
    }
    LocalFree(v18);
    ((void (__fastcall *)(void *))qword_18005E548)(v20);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 2 )
      LastError = 2114;
    LocalFree(v18);
  }
  return LastError;
}

```

## disassembly

```asm
0x180008930  mov     dword ptr [rsp+uBytes], r8d
0x180008935  push    rdi
0x180008936  push    r12
0x180008938  push    r14
0x18000893a  push    r15
0x18000893c  sub     rsp, 58h
0x180008940  mov     r15, r9
0x180008943  mov     r14, rdx
0x180008946  mov     edi, ecx
0x180008948  test    r9, r9
0x18000894b  jz      loc_180008C8C
0x180008951  mov     r12, [rsp+78h+arg_20]
0x180008959  test    r12, r12
0x18000895c  jz      loc_180008C8C
0x180008962  cmp     ecx, 2
0x180008965  ja      loc_180008B80
0x18000896b  mov     [rsp+78h+arg_0], rbx
0x180008973  mov     [rsp+78h+var_28], rbp
0x180008978  mov     rbp, [rsp+78h+arg_38]
0x180008980  test    rbp, rbp
0x180008983  jnz     loc_180008C0A
0x180008989  mov     edx, 60h ; '`'; uBytes
0x18000898e  mov     ecx, 40h ; '@'; uFlags
0x180008993  call    cs:__imp_LocalAlloc
0x180008999  mov     rbx, rax
0x18000899c  test    rax, rax
0x18000899f  jz      loc_180008C29
0x1800089a5  mov     rdx, [rsp+78h+SourceString]; SourceString
0x1800089ad  mov     [rsp+78h+var_30], rsi
0x1800089b2  mov     [rsp+78h+var_38], r13
0x1800089b7  mov     [rax+40h], edi
0x1800089ba  test    rdx, rdx
0x1800089bd  jnz     loc_180008C33
0x1800089c3  mov     r13, [rsp+78h+arg_28]
0x1800089cb  test    r13, r13
0x1800089ce  jnz     loc_180008BAE
0x1800089d4  xor     eax, eax
0x1800089d6  mov     rcx, rbx; DestinationString
0x1800089d9  mov     [rbx+5Ch], eax
0x1800089dc  call    cs:__imp_RtlInitUnicodeString
0x1800089e2  lea     rcx, [rbx+10h]; DestinationString
0x1800089e6  mov     rdx, rbp; SourceString
0x1800089e9  call    cs:__imp_RtlInitUnicodeString
0x1800089ef  cmp     [rsp+78h+arg_40], 0
0x1800089f7  jnz     loc_180008B4C
0x1800089fd  cmp     [rsp+78h+arg_48], 0
0x180008a05  jnz     loc_180008C3F
0x180008a0b  cmp     [rsp+78h+arg_58], 0
0x180008a13  jnz     loc_180008C48
0x180008a19  cmp     [rsp+78h+arg_50], 0
0x180008a21  jnz     loc_180008C54
0x180008a27  mov     ecx, [rsp+78h+arg_60]
0x180008a2e  mov     rax, cs:qword_18005E540
0x180008a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a3a  mov     rbp, rax
0x180008a3d  test    rax, rax
0x180008a40  jz      loc_180008C60
0x180008a46  mov     eax, [rbx+5Ch]
0x180008a49  xor     edi, edi
0x180008a4b  test    byte ptr [rbx+48h], 1
0x180008a4f  mov     [rsp+78h+var_48], eax
0x180008a53  jz      loc_180008B58
0x180008a59  mov     esi, 400h
0x180008a5e  cmp     dword ptr [rsp+78h+uBytes], esi
0x180008a65  cmovbe  esi, dword ptr [rsp+78h+uBytes]
0x180008a6d  mov     [r14], rdi
0x180008a70  xor     eax, eax
0x180008a72  mov     [rsp+78h+arg_18], eax
0x180008a79  cmp     eax, 5
0x180008a7c  jnb     short loc_180008AD9
0x180008a7e  mov     rcx, [r14]; hMem
0x180008a81  test    rcx, rcx
0x180008a84  jnz     loc_180008C81
0x180008a8a  mov     edx, esi; uBytes
0x180008a8c  mov     ecx, 40h ; '@'; uFlags
0x180008a91  call    cs:__imp_LocalAlloc
0x180008a97  mov     [r14], rax
0x180008a9a  test    rax, rax
0x180008a9d  jz      loc_180008C00
0x180008aa3  mov     eax, [rsp+78h+var_48]
0x180008aa7  mov     r8, rbx; hMem
0x180008aaa  mov     [rbx+5Ch], eax
0x180008aad  mov     edx, 146033h; FsControlCode
0x180008ab2  mov     r9, [r14]; OutputBuffer
0x180008ab5  mov     rcx, rbp; FileHandle
0x180008ab8  mov     [rsp+78h+var_58], esi; ULONG
0x180008abc  call    SsServerFsControlCommon
0x180008ac1  mov     edi, eax
0x180008ac3  cmp     eax, 84Bh
0x180008ac8  jz      loc_180008BC3
0x180008ace  cmp     eax, 0EAh
0x180008ad3  jz      loc_180008BC3
0x180008ad9  mov     rcx, [r14]; hMem
0x180008adc  test    rcx, rcx
0x180008adf  jz      short loc_180008AEB
0x180008ae1  cmp     dword ptr [rbx+50h], 0
0x180008ae5  jz      loc_180008B6E
0x180008aeb  test    edi, edi
0x180008aed  jnz     loc_180008BEF
0x180008af3  mov     eax, [rbx+50h]
0x180008af6  mov     [r15], eax
0x180008af9  mov     eax, [rbx+54h]
0x180008afc  mov     [r12], eax
0x180008b00  cmp     dword ptr [r15], 0
0x180008b04  jbe     short loc_180008B0F
0x180008b06  test    r13, r13
0x180008b09  jnz     loc_180008BB7
0x180008b0f  mov     rcx, rbx; hMem
0x180008b12  call    cs:__imp_LocalFree
0x180008b18  mov     rax, cs:qword_18005E548
0x180008b1f  mov     rcx, rbp
0x180008b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b27  mov     rsi, [rsp+78h+var_30]
0x180008b2c  mov     eax, edi
0x180008b2e  mov     r13, [rsp+78h+var_38]
0x180008b33  mov     rbx, [rsp+78h+arg_0]
0x180008b3b  mov     rbp, [rsp+78h+var_28]
0x180008b40  add     rsp, 58h
0x180008b44  pop     r15
0x180008b46  pop     r14
0x180008b48  pop     r12
0x180008b4a  pop     rdi
0x180008b4b  retn
0x180008b4c  mov     dword ptr [rbx+48h], 10h
0x180008b53  jmp     loc_1800089FD
0x180008b58  mov     esi, dword ptr [rsp+78h+uBytes]
0x180008b5f  mov     ecx, 2000h
0x180008b64  cmp     esi, ecx
0x180008b66  cmova   esi, ecx
0x180008b69  jmp     loc_180008A6D
0x180008b6e  call    cs:__imp_LocalFree
0x180008b74  mov     qword ptr [r14], 0
0x180008b7b  jmp     loc_180008AEB
0x180008b80  lea     eax, [rcx-1F5h]
0x180008b86  cmp     eax, 2
0x180008b89  jbe     loc_18000896B
0x180008b8f  cmp     edi, 1F9h
0x180008b95  jz      loc_18000896B
0x180008b9b  cmp     edi, 3EDh
0x180008ba1  jz      loc_18000896B
0x180008ba7  mov     eax, 7Ch ; '|'
0x180008bac  jmp     short loc_180008B40
0x180008bae  mov     eax, [r13+0]
0x180008bb2  jmp     loc_1800089D6
0x180008bb7  mov     eax, [rbx+5Ch]
0x180008bba  mov     [r13+0], eax
0x180008bbe  jmp     loc_180008B0F
0x180008bc3  mov     ecx, dword ptr [rsp+78h+uBytes]
0x180008bca  cmp     esi, ecx
0x180008bcc  jnb     loc_180008AD9
0x180008bd2  mov     eax, [rbx+58h]
0x180008bd5  mov     esi, ecx
0x180008bd7  add     eax, 400h
0x180008bdc  cmp     eax, ecx
0x180008bde  cmovb   esi, eax
0x180008be1  mov     eax, [rsp+78h+arg_18]
0x180008be8  inc     eax
0x180008bea  jmp     loc_180008A72
0x180008bef  cmp     edi, 0EAh
0x180008bf5  jz      loc_180008AF3
0x180008bfb  jmp     loc_180008B0F
0x180008c00  mov     edi, 8
0x180008c05  jmp     loc_180008AD9
0x180008c0a  cmp     word ptr [rbp+0], 5Ch ; '\'
0x180008c0f  jnz     loc_180008989
0x180008c15  cmp     word ptr [rbp+2], 5Ch ; '\'
0x180008c1a  jnz     loc_180008989
0x180008c20  add     rbp, 4
0x180008c24  jmp     loc_180008989
0x180008c29  mov     eax, 8
0x180008c2e  jmp     loc_180008B33
0x180008c33  mov     dword ptr [rax+48h], 1
0x180008c3a  jmp     loc_1800089C3
0x180008c3f  or      dword ptr [rbx+48h], 40h
0x180008c43  jmp     loc_180008A0B
0x180008c48  or      dword ptr [rbx+48h], 100h
0x180008c4f  jmp     loc_180008A19
0x180008c54  or      dword ptr [rbx+48h], 80h
0x180008c5b  jmp     loc_180008A27
0x180008c60  call    cs:__imp_GetLastError
0x180008c66  mov     edi, eax
0x180008c68  mov     rcx, rbx; hMem
0x180008c6b  cmp     edi, 2
0x180008c6e  mov     eax, 842h
0x180008c73  cmovz   edi, eax
0x180008c76  call    cs:__imp_LocalFree
0x180008c7c  jmp     loc_180008B27
0x180008c81  call    cs:__imp_LocalFree
0x180008c87  jmp     loc_180008A8A
0x180008c8c  mov     eax, 57h ; 'W'
0x180008c91  jmp     loc_180008B40
```
