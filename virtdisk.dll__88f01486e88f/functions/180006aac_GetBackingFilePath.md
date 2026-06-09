# GetBackingFilePath

- ea: `0x180006aac`
- end: `0x180006e30`
- name: `GetBackingFilePath`
- size: `900`
- prototype: `__int64 __fastcall(wchar_t *Str, __int64, PWSTR *, _DWORD *, PWSTR *, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002740`
- `0x18000648c`

## callees

- `0x180004ed0`
- `0x180005730`
- `0x180006038`
- `0x180006aac`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180006b24`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180006b6c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180006b24`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180006b6c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006d75`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006d75`
- `ntdll!RtlAppendUnicodeToString` at `0x180006c9f`
- `ntdll!RtlAppendUnicodeToString` at `0x180006cb7`
- `ntdll!RtlAppendUnicodeToString` at `0x180006c9f`
- `ntdll!RtlAppendUnicodeToString` at `0x180006cb7`
- `ntdll!RtlFreeHeap` at `0x180006dd5`
- `ntdll!RtlFreeHeap` at `0x180006dfa`
- `ntdll!RtlFreeHeap` at `0x180006dd5`
- `ntdll!RtlFreeHeap` at `0x180006dfa`
- `ntdll!RtlAllocateHeap` at `0x180006c4c`
- `ntdll!RtlAllocateHeap` at `0x180006d12`
- `ntdll!RtlAllocateHeap` at `0x180006c4c`
- `ntdll!RtlAllocateHeap` at `0x180006d12`

## pseudocode

```c
__int64 __fastcall GetBackingFilePath(wchar_t *Str, __int64 a2, PWSTR *a3, _DWORD *a4, PWSTR *a5, _DWORD *a6)
{
  wchar_t *v7; // r13
  const wchar_t *v8; // r12
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r14
  unsigned int v11; // ebx
  wchar_t *v12; // rax
  unsigned int v13; // r15d
  unsigned __int64 v14; // rbx
  void *v15; // rsi
  __int64 v16; // rdi
  unsigned __int64 v17; // rcx
  struct _UNICODE_STRING Destination; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v20; // [rsp+80h] [rbp-80h] BYREF
  void *Src; // [rsp+90h] [rbp-70h]
  PWSTR *v22; // [rsp+98h] [rbp-68h]
  _DWORD *v23; // [rsp+A0h] [rbp-60h]
  PWSTR *v24; // [rsp+A8h] [rbp-58h]
  _DWORD *v25; // [rsp+B0h] [rbp-50h]
  __int128 v26; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t Buffer[40]; // [rsp+D0h] [rbp-30h] BYREF

  *a3 = 0;
  Src = Str;
  *a4 = 0;
  v24 = a5;
  v25 = a6;
  *a5 = 0;
  *a6 = 0;
  v23 = a4;
  v22 = a3;
  Destination = 0;
  v20 = 0;
  v26 = 0;
  v7 = wcsrchr(Str, 0x5Cu);
  v8 = v7 + 1;
  if ( !v7 )
    v8 = Str;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  if ( v10 > 0xFFFF )
    goto LABEL_6;
  v12 = wcsrchr(v8, 0x2Eu);
  if ( v12 )
  {
    do
      ++v9;
    while ( v12[v9] );
    if ( v9 > 0xFFFF )
      goto LABEL_6;
    LOWORD(v10) = v10 - v9;
  }
  if ( (unsigned __int16)(v10 + 6) < (unsigned __int16)v10
    || (v13 = 2 * (unsigned __int16)(v10 + 6), v13 > 0xFFFF)
    || (GenerateUniqueID(&v26),
        swprintf_s(
          Buffer,
          0x26u,
          L"_%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
          (unsigned int)v26,
          WORD2(v26),
          WORD3(v26),
          BYTE8(v26),
          BYTE9(v26),
          BYTE10(v26),
          BYTE11(v26),
          BYTE12(v26),
          BYTE13(v26),
          BYTE14(v26),
          HIBYTE(v26),
          *(_QWORD *)&Destination.Length),
        LOWORD(v14) = v13 + 76,
        (unsigned __int16)(v13 + 76) < (unsigned __int16)v13) )
  {
    v11 = 534;
    goto LABEL_25;
  }
  Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)(v13 + 76));
  if ( !Destination.Buffer )
    goto LABEL_15;
  Destination.MaximumLength = v13 + 76;
  memcpy_0(Destination.Buffer, v8, 2LL * (unsigned __int16)v10);
  Destination.Length = 2 * v10;
  RtlAppendUnicodeToString(&Destination, Buffer);
  RtlAppendUnicodeToString(&Destination, L".avhdx");
  v15 = Src;
  v16 = ((char *)v7 - (_BYTE *)Src) >> 1;
  if ( !v7 || (v17 = 2 * v16 + 2, v17 <= 0xFFFF) && (v14 = v17 + Destination.MaximumLength, v14 <= 0xFFFF) )
  {
    v20.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)v14);
    if ( v20.Buffer )
    {
      v20.Length = 0;
      v20.MaximumLength = v14;
      if ( v7 )
      {
        memcpy_0(v20.Buffer, v15, 2 * v16 + 2);
        v20.Length = 2 * v16 + 2;
        memcpy_0((char *)v20.Buffer + v20.Length, Destination.Buffer, Destination.Length);
      }
      else
      {
        RtlAppendUnicodeStringToString(&v20, &Destination);
      }
      v11 = 0;
      *v22 = Destination.Buffer;
      *v23 = Destination.MaximumLength;
      *v24 = v20.Buffer;
      *v25 = v20.MaximumLength;
      return v11;
    }
LABEL_15:
    v11 = 14;
    goto LABEL_25;
  }
LABEL_6:
  v11 = 87;
LABEL_25:
  if ( Destination.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
  if ( v20.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20.Buffer);
  return v11;
}

```

## disassembly

```asm
0x180006aac  mov     [rsp-8+arg_8], rbx
0x180006ab1  push    rbp
0x180006ab2  push    rsi
0x180006ab3  push    rdi
0x180006ab4  push    r12
0x180006ab6  push    r13
0x180006ab8  push    r14
0x180006aba  push    r15
0x180006abc  lea     rbp, [rsp-30h]
0x180006ac1  sub     rsp, 130h
0x180006ac8  mov     rax, cs:__security_cookie
0x180006acf  xor     rax, rsp
0x180006ad2  mov     [rbp+60h+var_40], rax
0x180006ad6  mov     rdx, [rbp+60h+arg_28]
0x180006add  xor     r15d, r15d
0x180006ae0  mov     [r8], r15
0x180006ae3  mov     rbx, rcx
0x180006ae6  mov     [rbp+60h+Src], rcx
0x180006aea  xorps   xmm0, xmm0
0x180006aed  mov     rcx, [rbp+60h+arg_20]
0x180006af4  xorps   xmm1, xmm1
0x180006af7  mov     [r9], r15d
0x180006afa  mov     [rbp+60h+var_B8], rcx
0x180006afe  mov     [rbp+60h+var_B0], rdx
0x180006b02  mov     [rcx], r15
0x180006b05  mov     rcx, rbx; Str
0x180006b08  mov     [rdx], r15d
0x180006b0b  lea     edx, [r15+5Ch]; Ch
0x180006b0f  mov     [rbp+60h+var_C0], r9
0x180006b13  mov     [rbp+60h+var_C8], r8
0x180006b17  movups  xmmword ptr [rsp+160h+Destination.Length], xmm0
0x180006b1c  movups  xmmword ptr [rbp+60h+var_E0.Length], xmm1
0x180006b20  movups  [rbp+60h+var_A8], xmm0
0x180006b24  call    cs:__imp_wcsrchr
0x180006b2b  nop     dword ptr [rax+rax+00h]
0x180006b30  mov     r13, rax
0x180006b33  lea     r12, [rax+2]
0x180006b37  test    rax, rax
0x180006b3a  jnz     short loc_180006B3F
0x180006b3c  mov     r12, rbx
0x180006b3f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006b43  mov     r14, rbx
0x180006b46  inc     r14
0x180006b49  cmp     [r12+r14*2], r15w
0x180006b4e  jnz     short loc_180006B46
0x180006b50  mov     edi, 0FFFFh
0x180006b55  cmp     r14, rdi
0x180006b58  jbe     short loc_180006B64
0x180006b5a  mov     ebx, 57h ; 'W'
0x180006b5f  jmp     loc_180006DBA
0x180006b64  mov     edx, 2Eh ; '.'; Ch
0x180006b69  mov     rcx, r12; Str
0x180006b6c  call    cs:__imp_wcsrchr
0x180006b73  nop     dword ptr [rax+rax+00h]
0x180006b78  test    rax, rax
0x180006b7b  jz      short loc_180006B90
0x180006b7d  inc     rbx
0x180006b80  cmp     [rax+rbx*2], r15w
0x180006b85  jnz     short loc_180006B7D
0x180006b87  cmp     rbx, rdi
0x180006b8a  ja      short loc_180006B5A
0x180006b8c  sub     r14w, bx
0x180006b90  lea     eax, [r14+6]
0x180006b94  cmp     ax, r14w
0x180006b98  jb      loc_180006DB5
0x180006b9e  movzx   r15d, ax
0x180006ba2  add     r15d, r15d
0x180006ba5  cmp     r15d, edi
0x180006ba8  ja      loc_180006DB2
0x180006bae  lea     rcx, [rbp+60h+var_A8]
0x180006bb2  call    GenerateUniqueID
0x180006bb7  movzx   ecx, byte ptr [rbp+60h+var_A8+0Eh]
0x180006bbb  movzx   edx, byte ptr [rbp+60h+var_A8+0Dh]
0x180006bbf  movzx   r8d, byte ptr [rbp+60h+var_A8+0Ch]
0x180006bc4  movzx   r9d, byte ptr [rbp+60h+var_A8+0Bh]
0x180006bc9  movzx   eax, byte ptr [rbp+60h+var_A8+0Fh]
0x180006bcd  movzx   r10d, byte ptr [rbp+60h+var_A8+0Ah]
0x180006bd2  movzx   r11d, byte ptr [rbp+60h+var_A8+9]
0x180006bd7  movzx   ebx, byte ptr [rbp+60h+var_A8+8]
0x180006bdb  movzx   edi, word ptr [rbp+60h+var_A8+6]
0x180006bdf  movzx   esi, word ptr [rbp+60h+var_A8+4]
0x180006be3  mov     [rsp+160h+var_F8], eax
0x180006be7  mov     [rsp+160h+var_100], ecx
0x180006beb  lea     rcx, [rbp+60h+Buffer]; Buffer
0x180006bef  mov     [rsp+160h+var_108], edx
0x180006bf3  mov     edx, 26h ; '&'; BufferCount
0x180006bf8  mov     [rsp+160h+var_110], r8d
0x180006bfd  lea     r8, a08lx04x04x02x0; "_%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180006c04  mov     [rsp+160h+var_118], r9d
0x180006c09  mov     r9d, dword ptr [rbp+60h+var_A8]
0x180006c0d  mov     [rsp+160h+var_120], r10d
0x180006c12  mov     [rsp+160h+var_128], r11d
0x180006c17  mov     [rsp+160h+var_130], ebx
0x180006c1b  mov     [rsp+160h+var_138], edi
0x180006c1f  mov     [rsp+160h+var_140], esi
0x180006c23  call    swprintf_s
0x180006c28  lea     ebx, [r15+4Ch]
0x180006c2c  cmp     bx, r15w
0x180006c30  jb      loc_180006DB2
0x180006c36  mov     rcx, gs:60h
0x180006c3f  mov     edx, 8; Flags
0x180006c44  movzx   r8d, bx; Size
0x180006c48  mov     rcx, [rcx+30h]; HeapHandle
0x180006c4c  call    cs:__imp_RtlAllocateHeap
0x180006c53  nop     dword ptr [rax+rax+00h]
0x180006c58  xor     r15d, r15d
0x180006c5b  mov     [rsp+160h+Destination.Buffer], rax
0x180006c60  mov     rcx, rax; void *
0x180006c63  test    rax, rax
0x180006c66  jnz     short loc_180006C72
0x180006c68  mov     ebx, 0Eh
0x180006c6d  jmp     loc_180006DBA
0x180006c72  movzx   r8d, r14w
0x180006c76  mov     rdx, r12; Src
0x180006c79  add     r8, r8; Size
0x180006c7c  mov     [rsp+160h+Destination.Length], r15w
0x180006c82  mov     [rsp+160h+Destination.MaximumLength], bx
0x180006c87  call    memcpy_0
0x180006c8c  add     r14w, r14w
0x180006c90  lea     rdx, [rbp+60h+Buffer]; Source
0x180006c94  add     [rsp+160h+Destination.Length], r14w
0x180006c9a  lea     rcx, [rsp+160h+Destination]; Destination
0x180006c9f  call    cs:__imp_RtlAppendUnicodeToString
0x180006ca6  nop     dword ptr [rax+rax+00h]
0x180006cab  lea     rdx, Source; ".avhdx"
0x180006cb2  lea     rcx, [rsp+160h+Destination]; Destination
0x180006cb7  call    cs:__imp_RtlAppendUnicodeToString
0x180006cbe  nop     dword ptr [rax+rax+00h]
0x180006cc3  mov     rsi, [rbp+60h+Src]
0x180006cc7  mov     rdi, r13
0x180006cca  sub     rdi, rsi
0x180006ccd  sar     rdi, 1
0x180006cd0  test    r13, r13
0x180006cd3  jz      short loc_180006CFC
0x180006cd5  lea     rcx, ds:2[rdi*2]
0x180006cdd  mov     edx, 0FFFFh
0x180006ce2  cmp     rcx, rdx
0x180006ce5  ja      loc_180006B5A
0x180006ceb  movzx   ebx, [rsp+160h+Destination.MaximumLength]
0x180006cf0  add     rbx, rcx
0x180006cf3  cmp     rbx, rdx
0x180006cf6  ja      loc_180006B5A
0x180006cfc  mov     rcx, gs:60h
0x180006d05  mov     edx, 8; Flags
0x180006d0a  movzx   r8d, bx; Size
0x180006d0e  mov     rcx, [rcx+30h]; HeapHandle
0x180006d12  call    cs:__imp_RtlAllocateHeap
0x180006d19  nop     dword ptr [rax+rax+00h]
0x180006d1e  mov     [rbp+60h+var_E0.Buffer], rax
0x180006d22  mov     rcx, rax; void *
0x180006d25  test    rax, rax
0x180006d28  jz      loc_180006C68
0x180006d2e  mov     [rbp+60h+var_E0.Length], r15w
0x180006d33  mov     [rbp+60h+var_E0.MaximumLength], bx
0x180006d37  test    r13, r13
0x180006d3a  jz      short loc_180006D6C
0x180006d3c  lea     rbx, ds:2[rdi*2]
0x180006d44  mov     rdx, rsi; Src
0x180006d47  mov     r8, rbx; Size
0x180006d4a  call    memcpy_0
0x180006d4f  movzx   r8d, [rsp+160h+Destination.Length]; Size
0x180006d55  mov     rdx, [rsp+160h+Destination.Buffer]; Src
0x180006d5a  movzx   ecx, bx
0x180006d5d  mov     [rbp+60h+var_E0.Length], cx
0x180006d61  add     rcx, [rbp+60h+var_E0.Buffer]; void *
0x180006d65  call    memcpy_0
0x180006d6a  jmp     short loc_180006D81
0x180006d6c  lea     rdx, [rsp+160h+Destination]; Source
0x180006d71  lea     rcx, [rbp+60h+var_E0]; Destination
0x180006d75  call    cs:__imp_RtlAppendUnicodeStringToString
0x180006d7c  nop     dword ptr [rax+rax+00h]
0x180006d81  mov     rax, [rsp+160h+Destination.Buffer]
0x180006d86  mov     ebx, r15d
0x180006d89  mov     rcx, [rbp+60h+var_C8]
0x180006d8d  mov     [rcx], rax
0x180006d90  mov     rcx, [rbp+60h+var_C0]
0x180006d94  movzx   eax, [rsp+160h+Destination.MaximumLength]
0x180006d99  mov     [rcx], eax
0x180006d9b  mov     rcx, [rbp+60h+var_B8]
0x180006d9f  mov     rax, [rbp+60h+var_E0.Buffer]
0x180006da3  mov     [rcx], rax
0x180006da6  mov     rcx, [rbp+60h+var_B0]
0x180006daa  movzx   eax, [rbp+60h+var_E0.MaximumLength]
0x180006dae  mov     [rcx], eax
0x180006db0  jmp     short loc_180006E06
0x180006db2  xor     r15d, r15d
0x180006db5  mov     ebx, 216h
0x180006dba  cmp     [rsp+160h+Destination.Buffer], r15
0x180006dbf  jz      short loc_180006DE1
0x180006dc1  mov     rcx, gs:60h
0x180006dca  xor     edx, edx; Flags
0x180006dcc  mov     r8, [rsp+160h+Destination.Buffer]; P
0x180006dd1  mov     rcx, [rcx+30h]; HeapHandle
0x180006dd5  call    cs:__imp_RtlFreeHeap
0x180006ddc  nop     dword ptr [rax+rax+00h]
0x180006de1  cmp     [rbp+60h+var_E0.Buffer], r15
0x180006de5  jz      short loc_180006E06
0x180006de7  mov     rcx, gs:60h
0x180006df0  xor     edx, edx; Flags
0x180006df2  mov     r8, [rbp+60h+var_E0.Buffer]; P
0x180006df6  mov     rcx, [rcx+30h]; HeapHandle
0x180006dfa  call    cs:__imp_RtlFreeHeap
0x180006e01  nop     dword ptr [rax+rax+00h]
0x180006e06  mov     eax, ebx
0x180006e08  mov     rcx, [rbp+60h+var_40]
0x180006e0c  xor     rcx, rsp; StackCookie
0x180006e0f  call    __security_check_cookie
0x180006e14  mov     rbx, [rsp+160h+arg_8]
0x180006e1c  add     rsp, 130h
0x180006e23  pop     r15
0x180006e25  pop     r14
0x180006e27  pop     r13
0x180006e29  pop     r12
0x180006e2b  pop     rdi
0x180006e2c  pop     rsi
0x180006e2d  pop     rbp
0x180006e2e  retn
```
