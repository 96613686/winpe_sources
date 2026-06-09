# SAXWriter::externalEntityDecl(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041f7a0`
- end: `0x10041f95a`
- name: `?externalEntityDecl@SAXWriter@@UEAAJPEB_WH0H0H@Z`
- size: `442`
- prototype: `int(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x10041df10`
- `0x10041f7a0`
- `0x10041fad0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::externalEntityDecl(
        SAXWriter *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        wchar_t *a6,
        unsigned int a7)
{
  unsigned int v11; // ebx
  SAXWriter *v12; // rdi
  __int64 v13; // r8
  const wchar_t *v14; // rdx

  if ( a2 )
  {
    if ( a6 )
    {
      if ( *((_DWORD *)this + 9) == 1 )
      {
        *((_DWORD *)this + 9) = 1;
      }
      else
      {
        v11 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 4) + 40LL))((char *)this - 32, 1);
        if ( v11 )
          return v11;
      }
      v12 = (SAXWriter *)((char *)this - 32);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 60);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 33);
      (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)v12 + 80LL))(v12, CodeStringPtr::ENTITY);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 32);
      if ( a3 && *a2 == 37 )
      {
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 37);
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 32);
        v13 = a3 - 1;
        v14 = a2 + 1;
      }
      else
      {
        v13 = a3;
        v14 = a2;
      }
      (*(void (__fastcall **)(SAXWriter *, const wchar_t *, __int64))(*(_QWORD *)v12 + 72LL))(v12, v14, v13);
      v11 = SAXWriter::writeExternalID(v12, a4, a5, a6, a7, 1, 0);
      if ( !v11 )
      {
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 62);
        (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)v12 + 56LL))(v12);
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x10041f7a0  mov     [rsp+arg_0], rbx
0x10041f7a5  mov     [rsp+arg_8], rsi
0x10041f7aa  mov     [rsp+arg_10], rdi
0x10041f7af  mov     [rsp+arg_18], r12
0x10041f7b4  push    r15
0x10041f7b6  sub     rsp, 70h
0x10041f7ba  mov     r12, r9
0x10041f7bd  mov     r15d, r8d
0x10041f7c0  mov     rsi, rdx
0x10041f7c3  mov     rdi, rcx
0x10041f7c6  test    rdx, rdx
0x10041f7c9  jnz     short loc_10041F7D9
0x10041f7cb  mov     ebx, 80070057h
0x10041f7d0  mov     [rsp+78h+var_38], ebx
0x10041f7d4  jmp     loc_10041F93D
0x10041f7d9  cmp     [rsp+78h+arg_28], 0
0x10041f7e2  jnz     short loc_10041F7F2
0x10041f7e4  mov     ebx, 80070057h
0x10041f7e9  mov     [rsp+78h+var_38], ebx
0x10041f7ed  jmp     loc_10041F93D
0x10041f7f2  cmp     dword ptr [rcx+24h], 1
0x10041f7f6  jnz     short loc_10041F801
0x10041f7f8  mov     dword ptr [rcx+24h], 1
0x10041f7ff  jmp     short loc_10041F825
0x10041f801  add     rcx, 0FFFFFFFFFFFFFFE0h
0x10041f805  mov     rax, [rcx]
0x10041f808  mov     edx, 1
0x10041f80d  mov     rax, [rax+28h]
0x10041f811  call    cs:__guard_dispatch_icall_fptr
0x10041f817  mov     ebx, eax
0x10041f819  mov     [rsp+78h+var_38], eax
0x10041f81d  test    eax, eax
0x10041f81f  jnz     loc_10041F93D
0x10041f825  add     rdi, 0FFFFFFFFFFFFFFE0h
0x10041f829  mov     rax, [rdi]
0x10041f82c  mov     edx, 3Ch ; '<'
0x10041f831  mov     rcx, rdi
0x10041f834  mov     rax, [rax+58h]
0x10041f838  call    cs:__guard_dispatch_icall_fptr
0x10041f83e  mov     rax, [rdi]
0x10041f841  mov     edx, 21h ; '!'
0x10041f846  mov     rcx, rdi
0x10041f849  mov     rax, [rax+58h]
0x10041f84d  call    cs:__guard_dispatch_icall_fptr
0x10041f853  mov     rax, [rdi]
0x10041f856  mov     rdx, cs:?ENTITY@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::ENTITY
0x10041f85d  mov     rcx, rdi
0x10041f860  mov     rax, [rax+50h]
0x10041f864  call    cs:__guard_dispatch_icall_fptr
0x10041f86a  mov     rax, [rdi]
0x10041f86d  mov     edx, 20h ; ' '
0x10041f872  mov     rcx, rdi
0x10041f875  mov     rax, [rax+58h]
0x10041f879  call    cs:__guard_dispatch_icall_fptr
0x10041f87f  test    r15d, r15d
0x10041f882  jz      short loc_10041F8BE
0x10041f884  cmp     word ptr [rsi], 25h ; '%'
0x10041f888  jnz     short loc_10041F8BE
0x10041f88a  mov     rax, [rdi]
0x10041f88d  mov     edx, 25h ; '%'
0x10041f892  mov     rcx, rdi
0x10041f895  mov     rax, [rax+58h]
0x10041f899  call    cs:__guard_dispatch_icall_fptr
0x10041f89f  mov     rax, [rdi]
0x10041f8a2  mov     edx, 20h ; ' '
0x10041f8a7  mov     rcx, rdi
0x10041f8aa  mov     rax, [rax+58h]
0x10041f8ae  call    cs:__guard_dispatch_icall_fptr
0x10041f8b4  lea     r8d, [r15-1]
0x10041f8b8  lea     rdx, [rsi+2]
0x10041f8bc  jmp     short loc_10041F8C4
0x10041f8be  mov     r8d, r15d
0x10041f8c1  mov     rdx, rsi
0x10041f8c4  mov     rax, [rdi]
0x10041f8c7  mov     rcx, rdi
0x10041f8ca  mov     rax, [rax+48h]
0x10041f8ce  call    cs:__guard_dispatch_icall_fptr
0x10041f8d4  mov     [rsp+78h+var_48], 0; bool
0x10041f8d9  mov     [rsp+78h+var_50], 1; bool
0x10041f8de  mov     eax, [rsp+78h+arg_30]
0x10041f8e5  mov     [rsp+78h+var_58], eax; int
0x10041f8e9  mov     r9, [rsp+78h+arg_28]; wchar_t *
0x10041f8f1  mov     r8d, [rsp+78h+arg_20]; int
0x10041f8f9  mov     rdx, r12; wchar_t *
0x10041f8fc  mov     rcx, rdi; this
0x10041f8ff  call    ?writeExternalID@SAXWriter@@IEAAJPEB_WH0H_N1@Z; SAXWriter::writeExternalID(wchar_t const *,int,wchar_t const *,int,bool,bool)
0x10041f904  mov     ebx, eax
0x10041f906  mov     [rsp+78h+var_38], eax
0x10041f90a  test    eax, eax
0x10041f90c  jnz     short loc_10041F93D
0x10041f90e  mov     rax, [rdi]
0x10041f911  mov     edx, 3Eh ; '>'
0x10041f916  mov     rcx, rdi
0x10041f919  mov     rax, [rax+58h]
0x10041f91d  call    cs:__guard_dispatch_icall_fptr
0x10041f923  mov     rax, [rdi]
0x10041f926  mov     rcx, rdi
0x10041f929  mov     rax, [rax+38h]
0x10041f92d  call    cs:__guard_dispatch_icall_fptr
0x10041f933  jmp     short loc_10041F93D
0x10041f935  mov     ebx, [rsp+78h+var_34]
0x10041f939  mov     [rsp+78h+var_38], ebx
0x10041f93d  mov     eax, ebx
0x10041f93f  lea     r11, [rsp+78h+var_8]
0x10041f944  mov     rbx, [r11+10h]
0x10041f948  mov     rsi, [r11+18h]
0x10041f94c  mov     rdi, [r11+20h]
0x10041f950  mov     r12, [r11+28h]
0x10041f954  mov     rsp, r11
0x10041f957  pop     r15
0x10041f959  retn
0x10043a6a0  push    rbp
0x10043a6a2  sub     rsp, 40h
0x10043a6a6  mov     rbp, rdx
0x10043a6a9  mov     [rbp+60h], rcx
0x10043a6ad  mov     [rbp+58h], rcx
0x10043a6b1  mov     rax, [rbp+58h]
0x10043a6b5  mov     rcx, [rax]
0x10043a6b8  mov     [rbp+50h], rcx
0x10043a6bc  mov     rax, [rbp+50h]
0x10043a6c0  mov     eax, [rax]
0x10043a6c2  cmp     eax, 0C0000005h
0x10043a6c7  jz      short loc_10043A6F9
0x10043a6c9  add     eax, 1FFFFFFFh
0x10043a6ce  cmp     eax, 1
0x10043a6d1  ja      short loc_10043A6E9
0x10043a6d3  mov     rax, [rbp+50h]
0x10043a6d7  cmp     dword ptr [rax+18h], 1
0x10043a6db  jnz     short loc_10043A6E9
0x10043a6dd  mov     rax, [rbp+50h]
0x10043a6e1  mov     ecx, [rax+20h]
0x10043a6e4  mov     [rbp+44h], ecx
0x10043a6e7  jmp     short loc_10043A6F0
0x10043a6e9  mov     dword ptr [rbp+44h], 8000FFFFh
0x10043a6f0  mov     dword ptr [rbp+48h], 1
0x10043a6f7  jmp     short loc_10043A700
0x10043a6f9  mov     dword ptr [rbp+48h], 0
0x10043a700  mov     eax, [rbp+48h]
0x10043a703  add     rsp, 40h
0x10043a707  pop     rbp
0x10043a708  retn
```
