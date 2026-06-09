# SAXWriter::elementDecl(wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041f1a0`
- end: `0x10041f311`
- name: `?elementDecl@SAXWriter@@UEAAJPEB_WH0H@Z`
- size: `369`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10041f1a0`
- `0x10041f5e0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::elementDecl(
        SAXWriter *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5)
{
  unsigned int v9; // edi
  char *v10; // rbx

  v9 = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      if ( *((_DWORD *)this + 9) == 1 )
      {
        *((_DWORD *)this + 9) = 1;
      }
      else
      {
        v9 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 4) + 40LL))((char *)this - 32, 1);
        if ( v9 )
          return v9;
      }
      v10 = (char *)this - 32;
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 60);
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 33);
      (*(void (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v10 + 80LL))(v10, L"ELEMENT");
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 32);
      (*(void (__fastcall **)(char *, const wchar_t *, _QWORD))(*(_QWORD *)v10 + 72LL))(v10, a2, a3);
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 32);
      (*(void (__fastcall **)(char *, const wchar_t *, _QWORD))(*(_QWORD *)v10 + 72LL))(v10, a4, a5);
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 62);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 56LL))(v10);
      return v9;
    }
    return (unsigned int)-2147024809;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
}

```

## disassembly

```asm
0x10041f1a0  mov     [rsp+arg_0], rbx
0x10041f1a5  mov     [rsp+arg_8], rsi
0x10041f1aa  mov     [rsp+arg_10], rdi
0x10041f1af  mov     [rsp+arg_18], r14
0x10041f1b4  push    r15
0x10041f1b6  sub     rsp, 50h
0x10041f1ba  mov     rsi, r9
0x10041f1bd  mov     r15d, r8d
0x10041f1c0  mov     r14, rdx
0x10041f1c3  mov     rbx, rcx
0x10041f1c6  xor     edi, edi
0x10041f1c8  mov     [rsp+58h+var_38], edi
0x10041f1cc  test    rdx, rdx
0x10041f1cf  jnz     short loc_10041F1DF
0x10041f1d1  mov     edi, 80070057h
0x10041f1d6  mov     [rsp+58h+var_38], edi
0x10041f1da  jmp     loc_10041F2F4
0x10041f1df  test    rsi, rsi
0x10041f1e2  jnz     short loc_10041F1F2
0x10041f1e4  mov     edi, 80070057h
0x10041f1e9  mov     [rsp+58h+var_38], edi
0x10041f1ed  jmp     loc_10041F2F4
0x10041f1f2  cmp     dword ptr [rcx+24h], 1
0x10041f1f6  jnz     short loc_10041F201
0x10041f1f8  mov     dword ptr [rcx+24h], 1
0x10041f1ff  jmp     short loc_10041F225
0x10041f201  add     rcx, 0FFFFFFFFFFFFFFE0h
0x10041f205  mov     rax, [rcx]
0x10041f208  mov     edx, 1
0x10041f20d  mov     rax, [rax+28h]
0x10041f211  call    cs:__guard_dispatch_icall_fptr
0x10041f217  mov     edi, eax
0x10041f219  mov     [rsp+58h+var_38], eax
0x10041f21d  test    eax, eax
0x10041f21f  jnz     loc_10041F2F4
0x10041f225  add     rbx, 0FFFFFFFFFFFFFFE0h
0x10041f229  mov     rax, [rbx]
0x10041f22c  mov     edx, 3Ch ; '<'
0x10041f231  mov     rcx, rbx
0x10041f234  mov     rax, [rax+58h]
0x10041f238  call    cs:__guard_dispatch_icall_fptr
0x10041f23e  mov     rax, [rbx]
0x10041f241  mov     edx, 21h ; '!'
0x10041f246  mov     rcx, rbx
0x10041f249  mov     rax, [rax+58h]
0x10041f24d  call    cs:__guard_dispatch_icall_fptr
0x10041f253  mov     rax, [rbx]
0x10041f256  lea     rdx, aElement; "ELEMENT"
0x10041f25d  mov     rcx, rbx
0x10041f260  mov     rax, [rax+50h]
0x10041f264  call    cs:__guard_dispatch_icall_fptr
0x10041f26a  mov     rax, [rbx]
0x10041f26d  mov     edx, 20h ; ' '
0x10041f272  mov     rcx, rbx
0x10041f275  mov     rax, [rax+58h]
0x10041f279  call    cs:__guard_dispatch_icall_fptr
0x10041f27f  mov     rax, [rbx]
0x10041f282  mov     r8d, r15d
0x10041f285  mov     rdx, r14
0x10041f288  mov     rcx, rbx
0x10041f28b  mov     rax, [rax+48h]
0x10041f28f  call    cs:__guard_dispatch_icall_fptr
0x10041f295  mov     rax, [rbx]
0x10041f298  mov     edx, 20h ; ' '
0x10041f29d  mov     rcx, rbx
0x10041f2a0  mov     rax, [rax+58h]
0x10041f2a4  call    cs:__guard_dispatch_icall_fptr
0x10041f2aa  mov     rax, [rbx]
0x10041f2ad  mov     r8d, [rsp+58h+arg_20]
0x10041f2b5  mov     rdx, rsi
0x10041f2b8  mov     rcx, rbx
0x10041f2bb  mov     rax, [rax+48h]
0x10041f2bf  call    cs:__guard_dispatch_icall_fptr
0x10041f2c5  mov     rax, [rbx]
0x10041f2c8  mov     edx, 3Eh ; '>'
0x10041f2cd  mov     rcx, rbx
0x10041f2d0  mov     rax, [rax+58h]
0x10041f2d4  call    cs:__guard_dispatch_icall_fptr
0x10041f2da  mov     rax, [rbx]
0x10041f2dd  mov     rcx, rbx
0x10041f2e0  mov     rax, [rax+38h]
0x10041f2e4  call    cs:__guard_dispatch_icall_fptr
0x10041f2ea  jmp     short loc_10041F2F4
0x10041f2ec  mov     edi, [rsp+58h+var_34]
0x10041f2f0  mov     [rsp+58h+var_38], edi
0x10041f2f4  mov     eax, edi
0x10041f2f6  mov     rbx, [rsp+58h+arg_0]
0x10041f2fb  mov     rsi, [rsp+58h+arg_8]
0x10041f300  mov     rdi, [rsp+58h+arg_10]
0x10041f305  mov     r14, [rsp+58h+arg_18]
0x10041f30a  add     rsp, 50h
0x10041f30e  pop     r15
0x10041f310  retn
0x10043a5c0  push    rbp
0x10043a5c2  sub     rsp, 20h
0x10043a5c6  mov     rbp, rdx
0x10043a5c9  mov     [rbp+40h], rcx
0x10043a5cd  mov     [rbp+38h], rcx
0x10043a5d1  mov     rax, [rbp+38h]
0x10043a5d5  mov     rcx, [rax]
0x10043a5d8  mov     [rbp+30h], rcx
0x10043a5dc  mov     rax, [rbp+30h]
0x10043a5e0  mov     eax, [rax]
0x10043a5e2  cmp     eax, 0C0000005h
0x10043a5e7  jz      short loc_10043A619
0x10043a5e9  add     eax, 1FFFFFFFh
0x10043a5ee  cmp     eax, 1
0x10043a5f1  ja      short loc_10043A609
0x10043a5f3  mov     rax, [rbp+30h]
0x10043a5f7  cmp     dword ptr [rax+18h], 1
0x10043a5fb  jnz     short loc_10043A609
0x10043a5fd  mov     rax, [rbp+30h]
0x10043a601  mov     ecx, [rax+20h]
0x10043a604  mov     [rbp+24h], ecx
0x10043a607  jmp     short loc_10043A610
0x10043a609  mov     dword ptr [rbp+24h], 8000FFFFh
0x10043a610  mov     dword ptr [rbp+28h], 1
0x10043a617  jmp     short loc_10043A620
0x10043a619  mov     dword ptr [rbp+28h], 0
0x10043a620  mov     eax, [rbp+28h]
0x10043a623  add     rsp, 20h
0x10043a627  pop     rbp
0x10043a628  retn
```
