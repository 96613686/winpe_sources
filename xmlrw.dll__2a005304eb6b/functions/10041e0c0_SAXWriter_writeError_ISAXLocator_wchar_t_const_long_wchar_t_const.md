# SAXWriter::writeError(ISAXLocator *,wchar_t const *,long,wchar_t const *)

- ea: `0x10041e0c0`
- end: `0x10041e41c`
- name: `?writeError@SAXWriter@@IEAAJPEAUISAXLocator@@PEB_WJ1@Z`
- size: `860`
- prototype: `__int64 __usercall@<rax>(SAXWriter *__hidden this@<rcx>, struct ISAXLocator *@<rdx>, const wchar_t *@<r8>, int@<r9d>, const wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x10041fcd0`
- `0x10041fd00`
- `0x10041fd30`

## callees

- `0x10041dcc0`
- `0x10041e0c0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::writeError(
        SAXWriter *this,
        struct ISAXLocator *a2,
        const wchar_t *a3,
        unsigned int a4,
        const wchar_t *a5)
{
  unsigned int v9; // edi
  void (__fastcall *v10)(SAXWriter *, const wchar_t *); // rax
  __int64 v11; // rdi
  __int64 v12; // r8
  void (__fastcall *v13)(SAXWriter *, const wchar_t *); // rax
  const wchar_t *v14; // rdx
  unsigned int v16; // [rsp+34h] [rbp-64h] BYREF
  _DWORD v17[6]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v18; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v19[5]; // [rsp+58h] [rbp-40h] BYREF

  if ( *((_DWORD *)this + 17) == 1 )
  {
    *((_DWORD *)this + 17) = 1;
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 40LL))(this, 1);
    if ( v9 )
      goto LABEL_25;
  }
  (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 56LL))(this);
  (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, a5);
  (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L":");
  (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 56LL))(this);
  if ( a2 )
  {
    v9 = ((__int64 (__fastcall *)(struct ISAXLocator *, unsigned int *))a2->lpVtbl->getLineNumber)(a2, &v16);
    if ( v9 )
      goto LABEL_25;
    v9 = ((__int64 (__fastcall *)(struct ISAXLocator *, _DWORD *))a2->lpVtbl->getColumnNumber)(a2, v17);
    if ( v9 )
      goto LABEL_25;
    v9 = ((__int64 (__fastcall *)(struct ISAXLocator *, __int64 *))a2->lpVtbl->getSystemId)(a2, &v18);
    if ( v9 )
      goto LABEL_25;
    v9 = ((__int64 (__fastcall *)(struct ISAXLocator *, _QWORD *))a2->lpVtbl->getPublicId)(a2, v19);
    if ( v9 )
      goto LABEL_25;
    v9 = SAXWriter::printf(this, L"Line Number: %d", v16);
    if ( v9 )
      goto LABEL_25;
    v9 = SAXWriter::printf(this, L"Column Number: %d", v17[0]);
    if ( v9 )
      goto LABEL_25;
    (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L"SystemId: ");
    v10 = *(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL);
    if ( v18 )
    {
      v10(this, L"\"");
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(v18 + 2 * v12) );
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 72LL))(this, v18);
      (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L"\"");
    }
    else
    {
      v10(this, L"NULL");
      v11 = -1;
    }
    (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 56LL))(this);
    (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L"PublicId: ");
    v13 = *(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL);
    if ( v19[0] )
    {
      v13(this, L"\"");
      do
        ++v11;
      while ( *(_WORD *)(v19[0] + 2 * v11) );
      (*(void (__fastcall **)(SAXWriter *, _QWORD, __int64))(*(_QWORD *)this + 72LL))(this, v19[0], v11);
      (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L"\"");
    }
    else
    {
      v13(this, L"NULL");
    }
    (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 56LL))(this);
  }
  (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L"Description: ");
  v14 = a3;
  if ( !a3 )
    v14 = L"NULL";
  (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, v14);
  (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 56LL))(this);
  v9 = SAXWriter::printf(this, L"Error Code: %d", a4);
LABEL_25:
  if ( *((_QWORD *)this + 13) )
    (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 184LL))(this);
  return v9;
}

```

## disassembly

```asm
0x10041e0c0  mov     [rsp+arg_8], rbx
0x10041e0c5  mov     [rsp+arg_10], rsi
0x10041e0ca  mov     [rsp+arg_0], rcx
0x10041e0cf  push    rdi
0x10041e0d0  push    r14
0x10041e0d2  push    r15
0x10041e0d4  sub     rsp, 80h
0x10041e0db  mov     r15d, r9d
0x10041e0de  mov     r14, r8
0x10041e0e1  mov     rsi, rdx
0x10041e0e4  mov     rbx, rcx
0x10041e0e7  cmp     dword ptr [rcx+44h], 1
0x10041e0eb  jnz     short loc_10041E0F6
0x10041e0ed  mov     dword ptr [rcx+44h], 1
0x10041e0f4  jmp     short loc_10041E116
0x10041e0f6  mov     rax, [rcx]
0x10041e0f9  mov     edx, 1
0x10041e0fe  mov     rax, [rax+28h]
0x10041e102  call    cs:__guard_dispatch_icall_fptr
0x10041e108  mov     edi, eax
0x10041e10a  mov     [rsp+98h+var_78], eax
0x10041e10e  test    eax, eax
0x10041e110  jnz     loc_10041E3E1
0x10041e116  mov     rax, [rbx]
0x10041e119  mov     rcx, rbx
0x10041e11c  mov     rax, [rax+38h]
0x10041e120  call    cs:__guard_dispatch_icall_fptr
0x10041e126  mov     rax, [rbx]
0x10041e129  mov     rdx, [rsp+98h+arg_20]
0x10041e131  mov     rcx, rbx
0x10041e134  mov     rax, [rax+50h]
0x10041e138  call    cs:__guard_dispatch_icall_fptr
0x10041e13e  mov     rax, [rbx]
0x10041e141  lea     rdx, asc_100448098; ":"
0x10041e148  mov     rcx, rbx
0x10041e14b  mov     rax, [rax+50h]
0x10041e14f  call    cs:__guard_dispatch_icall_fptr
0x10041e155  mov     rax, [rbx]
0x10041e158  mov     rcx, rbx
0x10041e15b  mov     rax, [rax+38h]
0x10041e15f  call    cs:__guard_dispatch_icall_fptr
0x10041e165  test    rsi, rsi
0x10041e168  jz      loc_10041E36D
0x10041e16e  mov     rax, [rsi]
0x10041e171  lea     rdx, [rsp+98h+var_64]
0x10041e176  mov     rcx, rsi
0x10041e179  mov     rax, [rax+20h]
0x10041e17d  call    cs:__guard_dispatch_icall_fptr
0x10041e183  mov     edi, eax
0x10041e185  mov     [rsp+98h+var_78], eax
0x10041e189  test    eax, eax
0x10041e18b  jnz     loc_10041E3E1
0x10041e191  mov     rax, [rsi]
0x10041e194  lea     rdx, [rsp+98h+var_60]
0x10041e199  mov     rcx, rsi
0x10041e19c  mov     rax, [rax+18h]
0x10041e1a0  call    cs:__guard_dispatch_icall_fptr
0x10041e1a6  mov     edi, eax
0x10041e1a8  mov     [rsp+98h+var_78], eax
0x10041e1ac  test    eax, eax
0x10041e1ae  jnz     loc_10041E3E1
0x10041e1b4  mov     rax, [rsi]
0x10041e1b7  lea     rdx, [rsp+98h+var_48]
0x10041e1bc  mov     rcx, rsi
0x10041e1bf  mov     rax, [rax+30h]
0x10041e1c3  call    cs:__guard_dispatch_icall_fptr
0x10041e1c9  mov     edi, eax
0x10041e1cb  mov     [rsp+98h+var_78], eax
0x10041e1cf  test    eax, eax
0x10041e1d1  jnz     loc_10041E3E1
0x10041e1d7  mov     rax, [rsi]
0x10041e1da  lea     rdx, [rsp+98h+var_40]
0x10041e1df  mov     rcx, rsi
0x10041e1e2  mov     rax, [rax+28h]
0x10041e1e6  call    cs:__guard_dispatch_icall_fptr
0x10041e1ec  mov     edi, eax
0x10041e1ee  mov     [rsp+98h+var_78], eax
0x10041e1f2  test    eax, eax
0x10041e1f4  jnz     loc_10041E3E1
0x10041e1fa  mov     r8d, [rsp+98h+var_64]
0x10041e1ff  lea     rdx, aLineNumberD; "Line Number: %d"
0x10041e206  mov     rcx, rbx; this
0x10041e209  call    ?printf@SAXWriter@@IEAAJPEB_WZZ; SAXWriter::printf(wchar_t const *,...)
0x10041e20e  mov     edi, eax
0x10041e210  mov     [rsp+98h+var_78], eax
0x10041e214  test    eax, eax
0x10041e216  jnz     loc_10041E3E1
0x10041e21c  mov     r8d, [rsp+98h+var_60]
0x10041e221  lea     rdx, aColumnNumberD; "Column Number: %d"
0x10041e228  mov     rcx, rbx; this
0x10041e22b  call    ?printf@SAXWriter@@IEAAJPEB_WZZ; SAXWriter::printf(wchar_t const *,...)
0x10041e230  mov     edi, eax
0x10041e232  mov     [rsp+98h+var_78], eax
0x10041e236  test    eax, eax
0x10041e238  jnz     loc_10041E3E1
0x10041e23e  mov     rax, [rbx]
0x10041e241  lea     rdx, aSystemid; "SystemId: "
0x10041e248  mov     rcx, rbx
0x10041e24b  mov     rax, [rax+50h]
0x10041e24f  call    cs:__guard_dispatch_icall_fptr
0x10041e255  mov     rax, [rbx]
0x10041e258  mov     rax, [rax+50h]
0x10041e25c  mov     rcx, rbx
0x10041e25f  cmp     [rsp+98h+var_48], 0
0x10041e265  jz      short loc_10041E2C1
0x10041e267  lea     rdx, asc_100448100; "\""
0x10041e26e  call    cs:__guard_dispatch_icall_fptr
0x10041e274  mov     rax, [rbx]
0x10041e277  mov     rdx, [rsp+98h+var_48]
0x10041e27c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x10041e283  mov     r8, rdi
0x10041e286  nop     word ptr [rax+rax+00000000h]
0x10041e290  inc     r8
0x10041e293  cmp     word ptr [rdx+r8*2], 0
0x10041e299  jnz     short loc_10041E290
0x10041e29b  mov     rcx, rbx
0x10041e29e  mov     rax, [rax+48h]
0x10041e2a2  call    cs:__guard_dispatch_icall_fptr
0x10041e2a8  mov     rax, [rbx]
0x10041e2ab  lea     rdx, asc_100448100; "\""
0x10041e2b2  mov     rcx, rbx
0x10041e2b5  mov     rax, [rax+50h]
0x10041e2b9  call    cs:__guard_dispatch_icall_fptr
0x10041e2bf  jmp     short loc_10041E2D5
0x10041e2c1  lea     rdx, aNull_1; "NULL"
0x10041e2c8  call    cs:__guard_dispatch_icall_fptr
0x10041e2ce  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x10041e2d5  mov     rax, [rbx]
0x10041e2d8  mov     rcx, rbx
0x10041e2db  mov     rax, [rax+38h]
0x10041e2df  call    cs:__guard_dispatch_icall_fptr
0x10041e2e5  mov     rax, [rbx]
0x10041e2e8  lea     rdx, aPublicid; "PublicId: "
0x10041e2ef  mov     rcx, rbx
0x10041e2f2  mov     rax, [rax+50h]
0x10041e2f6  call    cs:__guard_dispatch_icall_fptr
0x10041e2fc  mov     rax, [rbx]
0x10041e2ff  mov     rax, [rax+50h]
0x10041e303  mov     rcx, rbx
0x10041e306  cmp     [rsp+98h+var_40], 0
0x10041e30c  jz      short loc_10041E350
0x10041e30e  lea     rdx, asc_100448100; "\""
0x10041e315  call    cs:__guard_dispatch_icall_fptr
0x10041e31b  mov     rax, [rbx]
0x10041e31e  mov     rdx, [rsp+98h+var_40]
0x10041e323  inc     rdi
0x10041e326  cmp     word ptr [rdx+rdi*2], 0
0x10041e32b  jnz     short loc_10041E323
0x10041e32d  mov     r8, rdi
0x10041e330  mov     rcx, rbx
0x10041e333  mov     rax, [rax+48h]
0x10041e337  call    cs:__guard_dispatch_icall_fptr
0x10041e33d  mov     rax, [rbx]
0x10041e340  lea     rdx, asc_100448100; "\""
0x10041e347  mov     rcx, rbx
0x10041e34a  mov     rax, [rax+50h]
0x10041e34e  jmp     short loc_10041E357
0x10041e350  lea     rdx, aNull_1; "NULL"
0x10041e357  call    cs:__guard_dispatch_icall_fptr
0x10041e35d  mov     rax, [rbx]
0x10041e360  mov     rcx, rbx
0x10041e363  mov     rax, [rax+38h]
0x10041e367  call    cs:__guard_dispatch_icall_fptr
0x10041e36d  mov     rax, [rbx]
0x10041e370  lea     rdx, aDescription; "Description: "
0x10041e377  mov     rcx, rbx
0x10041e37a  mov     rax, [rax+50h]
0x10041e37e  call    cs:__guard_dispatch_icall_fptr
0x10041e384  mov     rax, [rbx]
0x10041e387  mov     rax, [rax+50h]
0x10041e38b  mov     rcx, rbx
0x10041e38e  test    r14, r14
0x10041e391  mov     rdx, r14
0x10041e394  jnz     short loc_10041E39D
0x10041e396  lea     rdx, aNull_1; "NULL"
0x10041e39d  call    cs:__guard_dispatch_icall_fptr
0x10041e3a3  mov     rax, [rbx]
0x10041e3a6  mov     rcx, rbx
0x10041e3a9  mov     rax, [rax+38h]
0x10041e3ad  call    cs:__guard_dispatch_icall_fptr
0x10041e3b3  mov     r8d, r15d
0x10041e3b6  lea     rdx, aErrorCodeD; "Error Code: %d"
0x10041e3bd  mov     rcx, rbx; this
0x10041e3c0  call    ?printf@SAXWriter@@IEAAJPEB_WZZ; SAXWriter::printf(wchar_t const *,...)
0x10041e3c5  mov     edi, eax
0x10041e3c7  mov     [rsp+98h+var_78], eax
0x10041e3cb  test    eax, eax
0x10041e3cd  jnz     short loc_10041E3E1
0x10041e3cf  jmp     short loc_10041E3E1
0x10041e3d1  mov     edi, [rsp+98h+var_74]
0x10041e3d5  mov     [rsp+98h+var_78], edi
0x10041e3d9  mov     rbx, [rsp+98h+arg_0]
0x10041e3e1  cmp     qword ptr [rbx+68h], 0
0x10041e3e6  jz      short loc_10041E401
0x10041e3e8  mov     rax, [rbx]
0x10041e3eb  mov     rcx, rbx
0x10041e3ee  mov     rax, [rax+0B8h]
0x10041e3f5  call    cs:__guard_dispatch_icall_fptr
0x10041e3fb  jmp     short loc_10041E401
0x10041e3fd  mov     edi, [rsp+98h+var_70]
0x10041e401  mov     eax, edi
0x10041e403  lea     r11, [rsp+98h+var_18]
0x10041e40b  mov     rbx, [r11+28h]
0x10041e40f  mov     rsi, [r11+30h]
0x10041e413  mov     rsp, r11
0x10041e416  pop     r15
0x10041e418  pop     r14
0x10041e41a  pop     rdi
0x10041e41b  retn
0x10043a3f0  push    rbp
0x10043a3f2  sub     rsp, 20h
0x10043a3f6  mov     rbp, rdx
0x10043a3f9  mov     [rbp+70h], rcx
0x10043a3fd  mov     [rbp+60h], rcx
0x10043a401  mov     rax, [rbp+60h]
0x10043a405  mov     rcx, [rax]
0x10043a408  mov     [rbp+40h], rcx
0x10043a40c  mov     rax, [rbp+40h]
0x10043a410  mov     eax, [rax]
0x10043a412  cmp     eax, 0C0000005h
0x10043a417  jz      short loc_10043A449
0x10043a419  add     eax, 1FFFFFFFh
0x10043a41e  cmp     eax, 1
0x10043a421  ja      short loc_10043A439
0x10043a423  mov     rax, [rbp+40h]
0x10043a427  cmp     dword ptr [rax+18h], 1
0x10043a42b  jnz     short loc_10043A439
0x10043a42d  mov     rax, [rbp+40h]
0x10043a431  mov     ecx, [rax+20h]
0x10043a434  mov     [rbp+24h], ecx
0x10043a437  jmp     short loc_10043A440
0x10043a439  mov     dword ptr [rbp+24h], 8000FFFFh
0x10043a440  mov     dword ptr [rbp+2Ch], 1
0x10043a447  jmp     short loc_10043A450
0x10043a449  mov     dword ptr [rbp+2Ch], 0
0x10043a450  mov     eax, [rbp+2Ch]
0x10043a453  add     rsp, 20h
0x10043a457  pop     rbp
0x10043a458  retn
0x10043a45a  push    rbp
0x10043a45c  sub     rsp, 20h
0x10043a460  mov     rbp, rdx
0x10043a463  mov     [rbp+78h], rcx
0x10043a467  mov     [rbp+68h], rcx
0x10043a46b  mov     rax, [rbp+68h]
0x10043a46f  mov     rcx, [rax]
0x10043a472  mov     [rbp+48h], rcx
0x10043a476  mov     rax, [rbp+48h]
0x10043a47a  mov     eax, [rax]
0x10043a47c  cmp     eax, 0C0000005h
0x10043a481  jz      short loc_10043A4B3
0x10043a483  add     eax, 1FFFFFFFh
0x10043a488  cmp     eax, 1
0x10043a48b  ja      short loc_10043A4A3
0x10043a48d  mov     rax, [rbp+48h]
0x10043a491  cmp     dword ptr [rax+18h], 1
0x10043a495  jnz     short loc_10043A4A3
0x10043a497  mov     rax, [rbp+48h]
0x10043a49b  mov     ecx, [rax+20h]
0x10043a49e  mov     [rbp+28h], ecx
0x10043a4a1  jmp     short loc_10043A4AA
0x10043a4a3  mov     dword ptr [rbp+28h], 8000FFFFh
0x10043a4aa  mov     dword ptr [rbp+30h], 1
0x10043a4b1  jmp     short loc_10043A4BA
0x10043a4b3  mov     dword ptr [rbp+30h], 0
0x10043a4ba  mov     eax, [rbp+30h]
0x10043a4bd  add     rsp, 20h
0x10043a4c1  pop     rbp
0x10043a4c2  retn
```
