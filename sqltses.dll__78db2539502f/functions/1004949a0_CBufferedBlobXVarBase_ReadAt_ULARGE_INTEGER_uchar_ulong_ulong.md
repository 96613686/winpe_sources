# CBufferedBlobXVarBase::ReadAt(_ULARGE_INTEGER,uchar *,ulong,ulong *)

- ea: `0x1004949a0`
- end: `0x100494b9c`
- name: `?ReadAt@CBufferedBlobXVarBase@@UEAAJT_ULARGE_INTEGER@@PEAEKPEAK@Z`
- size: `508`
- prototype: `__int64 __fastcall(union _ULARGE_INTEGER *this, union _ULARGE_INTEGER, unsigned __int8 *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x100401cc0`
- `0x1004949a0`

## import_xrefs

- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004949f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100494a54`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100494a81`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100494b0f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100494b71`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004949f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100494a54`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100494a81`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100494b0f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100494b71`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100494ac7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100494ac7`

## string_xrefs

- `0x100494b6a`: `cbLengthInput == cbLobReadActual`
- `0x100494b08`: `ulStartReadOffset.QuadPart >= m_ullStreamOffset`
- `0x100494a4d`: `m_ullStreamOffset - ulStartReadOffset.QuadPart < ULONG_MAX`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBufferedBlobXVarBase::ReadAt(
        union _ULARGE_INTEGER *this,
        union _ULARGE_INTEGER a2,
        unsigned __int8 *a3,
        DWORD a4,
        unsigned int *a5)
{
  unsigned int *v5; // r12
  unsigned __int8 *v7; // r15
  unsigned int v10; // r14d
  union _ULARGE_INTEGER v11; // rdx
  union _ULARGE_INTEGER v12; // rcx
  DWORD v13; // edi
  __int64 v14; // rcx
  union _ULARGE_INTEGER v15; // rcx
  union _ULARGE_INTEGER v16; // r9
  DWORD v17; // edi
  unsigned int v19; // [rsp+78h] [rbp+20h] BYREF

  v5 = a5;
  v7 = a3;
  v10 = 0;
  *a5 = 0;
  if ( !a3 )
    utassert_fail(1u, "pbNew != nullptr", "bufdstream.cpp", 332, 0);
  if ( !a4 )
    return 0;
  v11 = this[14];
  if ( v11.QuadPart + this[2].LowPart - this[4].LowPart <= a2.QuadPart )
    return 0;
  if ( a2.QuadPart >= v11.QuadPart )
  {
LABEL_16:
    v15 = this[14];
    v16 = v15;
    if ( a2.QuadPart < v15.QuadPart )
    {
      utassert_fail(1u, "ulStartReadOffset.QuadPart >= m_ullStreamOffset", "bufdstream.cpp", 389, 0);
      v15.LowPart = this[14].LowPart;
      v16 = this[14];
    }
    v17 = v15.LowPart - this[4].LowPart - a2.LowPart + this[2].LowPart;
    if ( a4 < v17 )
      v17 = a4;
    memmove(v7, (const void *)(a2.QuadPart + this[1].QuadPart - v16.QuadPart), v17);
    *v5 += v17;
    return v10;
  }
  if ( v11.QuadPart - a2.QuadPart >= 0xFFFFFFFF )
    utassert_fail(1u, "m_ullStreamOffset - ulStartReadOffset.QuadPart < ULONG_MAX", "bufdstream.cpp", 353, 0);
  v12 = this[13];
  if ( !v12.QuadPart )
  {
    utassert_fail(1u, "m_apilbOut", "bufdstream.cpp", 354, 0);
    v12 = this[13];
  }
  v13 = a4;
  if ( this[14].LowPart - a2.LowPart < a4 )
    v13 = this[14].LowPart - a2.LowPart;
  v10 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER, union _ULARGE_INTEGER, unsigned __int8 *, _QWORD, unsigned int *))(*(_QWORD *)v12.QuadPart + 24LL))(
          v12,
          a2,
          v7,
          v13,
          &v19);
  if ( v10 )
    ex_raise(71, 2, 20, 99);
  v14 = v19;
  *v5 = v19;
  if ( a4 > v13 )
  {
    v7 += v14;
    a2.QuadPart += v14;
    a4 -= v14;
    if ( a4 )
      goto LABEL_16;
    return v10;
  }
  if ( a4 == (_DWORD)v14 )
    return v10;
  utassert_fail(1u, "cbLengthInput == cbLobReadActual", "bufdstream.cpp", 376, 0);
  return v10;
}

```

## disassembly

```asm
0x1004949a0  mov     [rsp+arg_8], rbx
0x1004949a5  mov     [rsp+arg_10], rbp
0x1004949aa  push    rsi
0x1004949ab  push    r12
0x1004949ad  push    r13
0x1004949af  push    r14
0x1004949b1  push    r15
0x1004949b3  sub     rsp, 30h
0x1004949b7  mov     r12, [rsp+58h+arg_20]
0x1004949bf  xor     r13d, r13d
0x1004949c2  mov     ebp, r9d
0x1004949c5  mov     r15, r8
0x1004949c8  mov     rbx, rdx
0x1004949cb  mov     rsi, rcx
0x1004949ce  mov     r14d, r13d
0x1004949d1  mov     [r12], r13d
0x1004949d5  test    r8, r8
0x1004949d8  jnz     short loc_1004949FD
0x1004949da  mov     r9d, 14Ch
0x1004949e0  mov     [rsp+58h+var_38], r13
0x1004949e5  lea     r8, aBufdstreamCpp; "bufdstream.cpp"
0x1004949ec  lea     rdx, aPbnewNullptr; "pbNew != nullptr"
0x1004949f3  lea     ecx, [r15+1]
0x1004949f7  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004949fd  test    ebp, ebp
0x1004949ff  jz      loc_100494B82
0x100494a05  mov     ecx, [rsi+10h]
0x100494a08  sub     ecx, [rsi+20h]
0x100494a0b  mov     rdx, [rsi+70h]
0x100494a0f  add     rcx, rdx
0x100494a12  cmp     rcx, rbx
0x100494a15  jbe     loc_100494B82
0x100494a1b  mov     [rsp+58h+arg_0], rdi
0x100494a20  cmp     rbx, rdx
0x100494a23  jnb     loc_100494AE5
0x100494a29  sub     rdx, rbx
0x100494a2c  mov     eax, 0FFFFFFFFh
0x100494a31  cmp     rdx, rax
0x100494a34  jb      short loc_100494A5A
0x100494a36  mov     r9d, 161h
0x100494a3c  mov     [rsp+58h+var_38], r13
0x100494a41  lea     r8, aBufdstreamCpp; "bufdstream.cpp"
0x100494a48  mov     ecx, 1
0x100494a4d  lea     rdx, aMUllstreamoffs; "m_ullStreamOffset - ulStartReadOffset.Q"...
0x100494a54  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100494a5a  mov     rcx, [rsi+68h]
0x100494a5e  test    rcx, rcx
0x100494a61  jnz     short loc_100494A8B
0x100494a63  mov     r9d, 162h
0x100494a69  mov     [rsp+58h+var_38], r13
0x100494a6e  lea     r8, aBufdstreamCpp; "bufdstream.cpp"
0x100494a75  mov     ecx, 1
0x100494a7a  lea     rdx, aMApilbout; "m_apilbOut"
0x100494a81  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100494a87  mov     rcx, [rsi+68h]
0x100494a8b  mov     eax, [rsi+70h]
0x100494a8e  lea     rdx, [rsp+58h+arg_18]
0x100494a93  sub     eax, ebx
0x100494a95  mov     [rsp+58h+var_38], rdx
0x100494a9a  cmp     eax, ebp
0x100494a9c  mov     edi, ebp
0x100494a9e  mov     r8, r15
0x100494aa1  mov     rdx, rbx
0x100494aa4  cmovb   edi, eax
0x100494aa7  mov     rax, [rcx]
0x100494aaa  mov     r9d, edi
0x100494aad  call    qword ptr [rax+18h]
0x100494ab0  mov     r14d, eax
0x100494ab3  test    eax, eax
0x100494ab5  jz      short loc_100494ACD
0x100494ab7  mov     edx, 2
0x100494abc  lea     ecx, [rdx+45h]
0x100494abf  lea     r9d, [rdx+61h]
0x100494ac3  lea     r8d, [rdx+12h]
0x100494ac7  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100494acd  mov     ecx, [rsp+58h+arg_18]
0x100494ad1  mov     [r12], ecx
0x100494ad5  cmp     ebp, edi
0x100494ad7  jbe     short loc_100494B4F
0x100494ad9  lea     r15, [rcx+r15]
0x100494add  lea     rbx, [rcx+rbx]
0x100494ae1  sub     ebp, ecx
0x100494ae3  jz      short loc_100494B44
0x100494ae5  mov     rcx, [rsi+70h]
0x100494ae9  mov     r9, rcx
0x100494aec  cmp     rbx, rcx
0x100494aef  jnb     short loc_100494B1C
0x100494af1  mov     r9d, 185h
0x100494af7  mov     [rsp+58h+var_38], r13
0x100494afc  lea     r8, aBufdstreamCpp; "bufdstream.cpp"
0x100494b03  mov     ecx, 1
0x100494b08  lea     rdx, aUlstartreadoff; "ulStartReadOffset.QuadPart >= m_ullStre"...
0x100494b0f  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100494b15  mov     ecx, [rsi+70h]
0x100494b18  mov     r9, [rsi+70h]
0x100494b1c  sub     ecx, [rsi+20h]
0x100494b1f  mov     edi, [rsi+10h]
0x100494b22  sub     ecx, ebx
0x100494b24  mov     rdx, [rsi+8]
0x100494b28  add     edi, ecx
0x100494b2a  cmp     ebp, edi
0x100494b2c  mov     rcx, r15; void *
0x100494b2f  cmovb   edi, ebp
0x100494b32  sub     rdx, r9
0x100494b35  add     rdx, rbx; Src
0x100494b38  mov     r8d, edi; Size
0x100494b3b  call    memmove
0x100494b40  add     [r12], edi
0x100494b44  mov     rdi, [rsp+58h+arg_0]
0x100494b49  mov     eax, r14d
0x100494b4c  jmp     short loc_100494B84
0x100494b4f  cmp     ebp, ecx
0x100494b51  jz      short loc_100494B44
0x100494b53  mov     r9d, 178h
0x100494b59  mov     [rsp+58h+var_38], r13
0x100494b5e  lea     r8, aBufdstreamCpp; "bufdstream.cpp"
0x100494b65  mov     ecx, 1
0x100494b6a  lea     rdx, aCblengthinputC; "cbLengthInput == cbLobReadActual"
0x100494b71  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100494b77  mov     rdi, [rsp+58h+arg_0]
0x100494b7c  mov     eax, r14d
0x100494b7f  jmp     short loc_100494B84
0x100494b82  xor     eax, eax
0x100494b84  mov     rbx, [rsp+58h+arg_8]
0x100494b89  mov     rbp, [rsp+58h+arg_10]
0x100494b8e  add     rsp, 30h
0x100494b92  pop     r15
0x100494b94  pop     r14
0x100494b96  pop     r13
0x100494b98  pop     r12
0x100494b9a  pop     rsi
0x100494b9b  retn
```
