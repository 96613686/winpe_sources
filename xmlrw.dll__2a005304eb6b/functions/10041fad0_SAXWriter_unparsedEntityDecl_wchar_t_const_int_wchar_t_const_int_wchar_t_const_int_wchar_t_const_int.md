# SAXWriter::unparsedEntityDecl(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041fad0`
- end: `0x10041fcc9`
- name: `?unparsedEntityDecl@SAXWriter@@UEAAJPEB_WH0H0H0H@Z`
- size: `505`
- prototype: `int(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10041df10`
- `0x10041fad0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::unparsedEntityDecl(
        SAXWriter *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        wchar_t *a6,
        unsigned int a7,
        const wchar_t *a8,
        unsigned int a9)
{
  unsigned int v13; // ebx
  SAXWriter *v14; // rdi

  if ( a2 )
  {
    if ( a6 )
    {
      if ( a8 )
      {
        if ( *((_DWORD *)this + 7) == 1 )
        {
          *((_DWORD *)this + 7) = 1;
        }
        else
        {
          v13 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 5) + 40LL))((char *)this - 40, 1);
          if ( v13 )
            return v13;
        }
        v14 = (SAXWriter *)((char *)this - 40);
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v14 + 88LL))(v14, 60);
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v14 + 88LL))(v14, 33);
        (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)v14 + 80LL))(v14, CodeStringPtr::ENTITY);
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v14 + 88LL))(v14, 32);
        (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)v14 + 72LL))(v14, a2, a3);
        v13 = SAXWriter::writeExternalID(v14, a4, a5, a6, a7, 1, 0);
        if ( !v13 )
        {
          (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v14 + 88LL))(v14, 32);
          (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)v14 + 80LL))(v14, CodeStringPtr::NDATA);
          (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v14 + 88LL))(v14, 32);
          (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)v14 + 72LL))(v14, a8, a9);
          (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v14 + 88LL))(v14, 62);
          (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)v14 + 56LL))(v14);
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
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v13;
}

```

## disassembly

```asm
0x10041fad0  mov     [rsp+arg_0], rbx
0x10041fad5  mov     [rsp+arg_8], rdi
0x10041fada  mov     [rsp+arg_10], r12
0x10041fadf  mov     [rsp+arg_18], r13
0x10041fae4  push    r15
0x10041fae6  sub     rsp, 70h
0x10041faea  mov     r12, r9
0x10041faed  mov     r13d, r8d
0x10041faf0  mov     r15, rdx
0x10041faf3  mov     rdi, rcx
0x10041faf6  test    rdx, rdx
0x10041faf9  jnz     short loc_10041FB09
0x10041fafb  mov     ebx, 80070057h
0x10041fb00  mov     [rsp+78h+var_38], ebx
0x10041fb04  jmp     loc_10041FCAC
0x10041fb09  cmp     [rsp+78h+arg_28], 0
0x10041fb12  jnz     short loc_10041FB22
0x10041fb14  mov     ebx, 80070057h
0x10041fb19  mov     [rsp+78h+var_38], ebx
0x10041fb1d  jmp     loc_10041FCAC
0x10041fb22  cmp     [rsp+78h+arg_38], 0
0x10041fb2b  jnz     short loc_10041FB3B
0x10041fb2d  mov     ebx, 80070057h
0x10041fb32  mov     [rsp+78h+var_38], ebx
0x10041fb36  jmp     loc_10041FCAC
0x10041fb3b  cmp     dword ptr [rcx+1Ch], 1
0x10041fb3f  jnz     short loc_10041FB4A
0x10041fb41  mov     dword ptr [rcx+1Ch], 1
0x10041fb48  jmp     short loc_10041FB6E
0x10041fb4a  add     rcx, 0FFFFFFFFFFFFFFD8h
0x10041fb4e  mov     rax, [rcx]
0x10041fb51  mov     edx, 1
0x10041fb56  mov     rax, [rax+28h]
0x10041fb5a  call    cs:__guard_dispatch_icall_fptr
0x10041fb60  mov     ebx, eax
0x10041fb62  mov     [rsp+78h+var_38], eax
0x10041fb66  test    eax, eax
0x10041fb68  jnz     loc_10041FCAC
0x10041fb6e  add     rdi, 0FFFFFFFFFFFFFFD8h
0x10041fb72  mov     rax, [rdi]
0x10041fb75  mov     edx, 3Ch ; '<'
0x10041fb7a  mov     rcx, rdi
0x10041fb7d  mov     rax, [rax+58h]
0x10041fb81  call    cs:__guard_dispatch_icall_fptr
0x10041fb87  mov     rax, [rdi]
0x10041fb8a  mov     edx, 21h ; '!'
0x10041fb8f  mov     rcx, rdi
0x10041fb92  mov     rax, [rax+58h]
0x10041fb96  call    cs:__guard_dispatch_icall_fptr
0x10041fb9c  mov     rax, [rdi]
0x10041fb9f  mov     rdx, cs:?ENTITY@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::ENTITY
0x10041fba6  mov     rcx, rdi
0x10041fba9  mov     rax, [rax+50h]
0x10041fbad  call    cs:__guard_dispatch_icall_fptr
0x10041fbb3  mov     rax, [rdi]
0x10041fbb6  mov     edx, 20h ; ' '
0x10041fbbb  mov     rcx, rdi
0x10041fbbe  mov     rax, [rax+58h]
0x10041fbc2  call    cs:__guard_dispatch_icall_fptr
0x10041fbc8  mov     rax, [rdi]
0x10041fbcb  mov     r8d, r13d
0x10041fbce  mov     rdx, r15
0x10041fbd1  mov     rcx, rdi
0x10041fbd4  mov     rax, [rax+48h]
0x10041fbd8  call    cs:__guard_dispatch_icall_fptr
0x10041fbde  mov     [rsp+78h+var_48], 0; bool
0x10041fbe3  mov     [rsp+78h+var_50], 1; bool
0x10041fbe8  mov     eax, [rsp+78h+arg_30]
0x10041fbef  mov     [rsp+78h+var_58], eax; int
0x10041fbf3  mov     r9, [rsp+78h+arg_28]; wchar_t *
0x10041fbfb  mov     r8d, [rsp+78h+arg_20]; int
0x10041fc03  mov     rdx, r12; wchar_t *
0x10041fc06  mov     rcx, rdi; this
0x10041fc09  call    ?writeExternalID@SAXWriter@@IEAAJPEB_WH0H_N1@Z; SAXWriter::writeExternalID(wchar_t const *,int,wchar_t const *,int,bool,bool)
0x10041fc0e  mov     ebx, eax
0x10041fc10  mov     [rsp+78h+var_38], eax
0x10041fc14  test    eax, eax
0x10041fc16  jnz     loc_10041FCAC
0x10041fc1c  mov     rax, [rdi]
0x10041fc1f  mov     edx, 20h ; ' '
0x10041fc24  mov     rcx, rdi
0x10041fc27  mov     rax, [rax+58h]
0x10041fc2b  call    cs:__guard_dispatch_icall_fptr
0x10041fc31  mov     rax, [rdi]
0x10041fc34  mov     rdx, cs:?NDATA@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::NDATA
0x10041fc3b  mov     rcx, rdi
0x10041fc3e  mov     rax, [rax+50h]
0x10041fc42  call    cs:__guard_dispatch_icall_fptr
0x10041fc48  mov     rax, [rdi]
0x10041fc4b  mov     edx, 20h ; ' '
0x10041fc50  mov     rcx, rdi
0x10041fc53  mov     rax, [rax+58h]
0x10041fc57  call    cs:__guard_dispatch_icall_fptr
0x10041fc5d  mov     rax, [rdi]
0x10041fc60  mov     r8d, [rsp+78h+arg_40]
0x10041fc68  mov     rdx, [rsp+78h+arg_38]
0x10041fc70  mov     rcx, rdi
0x10041fc73  mov     rax, [rax+48h]
0x10041fc77  call    cs:__guard_dispatch_icall_fptr
0x10041fc7d  mov     rax, [rdi]
0x10041fc80  mov     edx, 3Eh ; '>'
0x10041fc85  mov     rcx, rdi
0x10041fc88  mov     rax, [rax+58h]
0x10041fc8c  call    cs:__guard_dispatch_icall_fptr
0x10041fc92  mov     rax, [rdi]
0x10041fc95  mov     rcx, rdi
0x10041fc98  mov     rax, [rax+38h]
0x10041fc9c  call    cs:__guard_dispatch_icall_fptr
0x10041fca2  jmp     short loc_10041FCAC
0x10041fca4  mov     ebx, [rsp+78h+var_34]
0x10041fca8  mov     [rsp+78h+var_38], ebx
0x10041fcac  mov     eax, ebx
0x10041fcae  lea     r11, [rsp+78h+var_8]
0x10041fcb3  mov     rbx, [r11+10h]
0x10041fcb7  mov     rdi, [r11+18h]
0x10041fcbb  mov     r12, [r11+20h]
0x10041fcbf  mov     r13, [r11+28h]
0x10041fcc3  mov     rsp, r11
0x10041fcc6  pop     r15
0x10041fcc8  retn
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
