# SAXWriter::internalEntityDecl(wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041f5e0`
- end: `0x10041f78f`
- name: `?internalEntityDecl@SAXWriter@@UEAAJPEB_WH0H@Z`
- size: `431`
- prototype: `int(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10041e430`
- `0x10041f5e0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::internalEntityDecl(
        SAXWriter *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        int a5)
{
  unsigned int v9; // ebx
  SAXWriter *v10; // rdi
  __int64 v11; // r8
  const wchar_t *v12; // rdx

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
      v10 = (SAXWriter *)((char *)this - 32);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 60);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 33);
      (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)v10 + 80LL))(v10, CodeStringPtr::ENTITY);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 32);
      if ( a3 && *a2 == 37 )
      {
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 37);
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 32);
        v11 = a3 - 1;
        v12 = a2 + 1;
      }
      else
      {
        v11 = a3;
        v12 = a2;
      }
      (*(void (__fastcall **)(SAXWriter *, const wchar_t *, __int64))(*(_QWORD *)v10 + 72LL))(v10, v12, v11);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 32);
      v9 = SAXWriter::writeDTDQuoted(v10, a4, a5, 0);
      if ( !v9 )
      {
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v10 + 88LL))(v10, 62);
        (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)v10 + 56LL))(v10);
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
  return v9;
}

```

## disassembly

```asm
0x10041f5e0  mov     [rsp+arg_0], rbx
0x10041f5e5  mov     [rsp+arg_8], rsi
0x10041f5ea  mov     [rsp+arg_10], rdi
0x10041f5ef  mov     [rsp+arg_18], r14
0x10041f5f4  push    r15
0x10041f5f6  sub     rsp, 50h
0x10041f5fa  mov     r14, r9
0x10041f5fd  mov     r15d, r8d
0x10041f600  mov     rsi, rdx
0x10041f603  mov     rdi, rcx
0x10041f606  test    rdx, rdx
0x10041f609  jnz     short loc_10041F619
0x10041f60b  mov     ebx, 80070057h
0x10041f610  mov     [rsp+58h+var_38], ebx
0x10041f614  jmp     loc_10041F772
0x10041f619  test    r14, r14
0x10041f61c  jnz     short loc_10041F62C
0x10041f61e  mov     ebx, 80070057h
0x10041f623  mov     [rsp+58h+var_38], ebx
0x10041f627  jmp     loc_10041F772
0x10041f62c  cmp     dword ptr [rcx+24h], 1
0x10041f630  jnz     short loc_10041F63B
0x10041f632  mov     dword ptr [rcx+24h], 1
0x10041f639  jmp     short loc_10041F65F
0x10041f63b  add     rcx, 0FFFFFFFFFFFFFFE0h
0x10041f63f  mov     rax, [rcx]
0x10041f642  mov     edx, 1
0x10041f647  mov     rax, [rax+28h]
0x10041f64b  call    cs:__guard_dispatch_icall_fptr
0x10041f651  mov     ebx, eax
0x10041f653  mov     [rsp+58h+var_38], eax
0x10041f657  test    eax, eax
0x10041f659  jnz     loc_10041F772
0x10041f65f  add     rdi, 0FFFFFFFFFFFFFFE0h
0x10041f663  mov     rax, [rdi]
0x10041f666  mov     edx, 3Ch ; '<'
0x10041f66b  mov     rcx, rdi
0x10041f66e  mov     rax, [rax+58h]
0x10041f672  call    cs:__guard_dispatch_icall_fptr
0x10041f678  mov     rax, [rdi]
0x10041f67b  mov     edx, 21h ; '!'
0x10041f680  mov     rcx, rdi
0x10041f683  mov     rax, [rax+58h]
0x10041f687  call    cs:__guard_dispatch_icall_fptr
0x10041f68d  mov     rax, [rdi]
0x10041f690  mov     rdx, cs:?ENTITY@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::ENTITY
0x10041f697  mov     rcx, rdi
0x10041f69a  mov     rax, [rax+50h]
0x10041f69e  call    cs:__guard_dispatch_icall_fptr
0x10041f6a4  mov     rax, [rdi]
0x10041f6a7  mov     edx, 20h ; ' '
0x10041f6ac  mov     rcx, rdi
0x10041f6af  mov     rax, [rax+58h]
0x10041f6b3  call    cs:__guard_dispatch_icall_fptr
0x10041f6b9  test    r15d, r15d
0x10041f6bc  jz      short loc_10041F6F8
0x10041f6be  cmp     word ptr [rsi], 25h ; '%'
0x10041f6c2  jnz     short loc_10041F6F8
0x10041f6c4  mov     rax, [rdi]
0x10041f6c7  mov     edx, 25h ; '%'
0x10041f6cc  mov     rcx, rdi
0x10041f6cf  mov     rax, [rax+58h]
0x10041f6d3  call    cs:__guard_dispatch_icall_fptr
0x10041f6d9  mov     rax, [rdi]
0x10041f6dc  mov     edx, 20h ; ' '
0x10041f6e1  mov     rcx, rdi
0x10041f6e4  mov     rax, [rax+58h]
0x10041f6e8  call    cs:__guard_dispatch_icall_fptr
0x10041f6ee  lea     r8d, [r15-1]
0x10041f6f2  lea     rdx, [rsi+2]
0x10041f6f6  jmp     short loc_10041F6FE
0x10041f6f8  mov     r8d, r15d
0x10041f6fb  mov     rdx, rsi
0x10041f6fe  mov     rax, [rdi]
0x10041f701  mov     rcx, rdi
0x10041f704  mov     rax, [rax+48h]
0x10041f708  call    cs:__guard_dispatch_icall_fptr
0x10041f70e  mov     rax, [rdi]
0x10041f711  mov     edx, 20h ; ' '
0x10041f716  mov     rcx, rdi
0x10041f719  mov     rax, [rax+58h]
0x10041f71d  call    cs:__guard_dispatch_icall_fptr
0x10041f723  xor     r9d, r9d; bool
0x10041f726  mov     r8d, [rsp+58h+arg_20]; int
0x10041f72e  mov     rdx, r14; wchar_t *
0x10041f731  mov     rcx, rdi; this
0x10041f734  call    ?writeDTDQuoted@SAXWriter@@IEAAJPEB_WH_N@Z; SAXWriter::writeDTDQuoted(wchar_t const *,int,bool)
0x10041f739  mov     ebx, eax
0x10041f73b  mov     [rsp+58h+var_38], eax
0x10041f73f  test    eax, eax
0x10041f741  jnz     short loc_10041F772
0x10041f743  mov     rax, [rdi]
0x10041f746  mov     edx, 3Eh ; '>'
0x10041f74b  mov     rcx, rdi
0x10041f74e  mov     rax, [rax+58h]
0x10041f752  call    cs:__guard_dispatch_icall_fptr
0x10041f758  mov     rax, [rdi]
0x10041f75b  mov     rcx, rdi
0x10041f75e  mov     rax, [rax+38h]
0x10041f762  call    cs:__guard_dispatch_icall_fptr
0x10041f768  jmp     short loc_10041F772
0x10041f76a  mov     ebx, [rsp+58h+var_34]
0x10041f76e  mov     [rsp+58h+var_38], ebx
0x10041f772  mov     eax, ebx
0x10041f774  mov     rbx, [rsp+58h+arg_0]
0x10041f779  mov     rsi, [rsp+58h+arg_8]
0x10041f77e  mov     rdi, [rsp+58h+arg_10]
0x10041f783  mov     r14, [rsp+58h+arg_18]
0x10041f788  add     rsp, 50h
0x10041f78c  pop     r15
0x10041f78e  retn
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
