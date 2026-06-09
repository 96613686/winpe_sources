# SAXWriter::startDTD(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041fd60`
- end: `0x10041fed7`
- name: `?startDTD@SAXWriter@@UEAAJPEB_WH0H0H@Z`
- size: `375`
- prototype: `int(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10041df10`
- `0x10041fd60`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::startDTD(
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

  if ( a2 )
  {
    if ( *((_DWORD *)this + 11) == 1 )
    {
      *((_DWORD *)this + 11) = 1;
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 3) + 40LL))((char *)this - 24, 1);
      if ( v11 )
        return v11;
    }
    v12 = (SAXWriter *)((char *)this - 24);
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 60);
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 33);
    (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)v12 + 80LL))(v12, CodeStringPtr::DOCTYPE);
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 32);
    (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)v12 + 72LL))(v12, a2, a3);
    v11 = SAXWriter::writeExternalID(v12, a4, a5, a6, a7, 0, 0);
    if ( !v11 )
    {
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 32);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 91);
      (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)v12 + 56LL))(v12);
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
0x10041fd60  mov     [rsp+arg_0], rbx
0x10041fd65  mov     [rsp+arg_8], rsi
0x10041fd6a  mov     [rsp+arg_10], rdi
0x10041fd6f  mov     [rsp+arg_18], r14
0x10041fd74  push    r15
0x10041fd76  sub     rsp, 70h
0x10041fd7a  mov     r14, r9
0x10041fd7d  mov     r15d, r8d
0x10041fd80  mov     rsi, rdx
0x10041fd83  mov     rdi, rcx
0x10041fd86  test    rdx, rdx
0x10041fd89  jnz     short loc_10041FD99
0x10041fd8b  mov     ebx, 80070057h
0x10041fd90  mov     [rsp+78h+var_34], ebx
0x10041fd94  jmp     loc_10041FEBA
0x10041fd99  cmp     dword ptr [rcx+2Ch], 1
0x10041fd9d  jnz     short loc_10041FDA8
0x10041fd9f  mov     dword ptr [rcx+2Ch], 1
0x10041fda6  jmp     short loc_10041FDCC
0x10041fda8  add     rcx, 0FFFFFFFFFFFFFFE8h
0x10041fdac  mov     rax, [rcx]
0x10041fdaf  mov     edx, 1
0x10041fdb4  mov     rax, [rax+28h]
0x10041fdb8  call    cs:__guard_dispatch_icall_fptr
0x10041fdbe  mov     ebx, eax
0x10041fdc0  mov     [rsp+78h+var_34], eax
0x10041fdc4  test    eax, eax
0x10041fdc6  jnz     loc_10041FEBA
0x10041fdcc  add     rdi, 0FFFFFFFFFFFFFFE8h
0x10041fdd0  mov     rax, [rdi]
0x10041fdd3  mov     edx, 3Ch ; '<'
0x10041fdd8  mov     rcx, rdi
0x10041fddb  mov     rax, [rax+58h]
0x10041fddf  call    cs:__guard_dispatch_icall_fptr
0x10041fde5  mov     rax, [rdi]
0x10041fde8  mov     edx, 21h ; '!'
0x10041fded  mov     rcx, rdi
0x10041fdf0  mov     rax, [rax+58h]
0x10041fdf4  call    cs:__guard_dispatch_icall_fptr
0x10041fdfa  mov     rax, [rdi]
0x10041fdfd  mov     rdx, cs:?DOCTYPE@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::DOCTYPE
0x10041fe04  mov     rcx, rdi
0x10041fe07  mov     rax, [rax+50h]
0x10041fe0b  call    cs:__guard_dispatch_icall_fptr
0x10041fe11  mov     rax, [rdi]
0x10041fe14  mov     edx, 20h ; ' '
0x10041fe19  mov     rcx, rdi
0x10041fe1c  mov     rax, [rax+58h]
0x10041fe20  call    cs:__guard_dispatch_icall_fptr
0x10041fe26  mov     rax, [rdi]
0x10041fe29  mov     r8d, r15d
0x10041fe2c  mov     rdx, rsi
0x10041fe2f  mov     rcx, rdi
0x10041fe32  mov     rax, [rax+48h]
0x10041fe36  call    cs:__guard_dispatch_icall_fptr
0x10041fe3c  mov     [rsp+78h+var_48], 0; bool
0x10041fe41  mov     [rsp+78h+var_50], 0; bool
0x10041fe46  mov     eax, [rsp+78h+arg_30]
0x10041fe4d  mov     [rsp+78h+var_58], eax; int
0x10041fe51  mov     r9, [rsp+78h+arg_28]; wchar_t *
0x10041fe59  mov     r8d, [rsp+78h+arg_20]; int
0x10041fe61  mov     rdx, r14; wchar_t *
0x10041fe64  mov     rcx, rdi; this
0x10041fe67  call    ?writeExternalID@SAXWriter@@IEAAJPEB_WH0H_N1@Z; SAXWriter::writeExternalID(wchar_t const *,int,wchar_t const *,int,bool,bool)
0x10041fe6c  mov     ebx, eax
0x10041fe6e  mov     [rsp+78h+var_34], eax
0x10041fe72  test    eax, eax
0x10041fe74  jnz     short loc_10041FEBA
0x10041fe76  mov     rax, [rdi]
0x10041fe79  mov     edx, 20h ; ' '
0x10041fe7e  mov     rcx, rdi
0x10041fe81  mov     rax, [rax+58h]
0x10041fe85  call    cs:__guard_dispatch_icall_fptr
0x10041fe8b  mov     rax, [rdi]
0x10041fe8e  mov     edx, 5Bh ; '['
0x10041fe93  mov     rcx, rdi
0x10041fe96  mov     rax, [rax+58h]
0x10041fe9a  call    cs:__guard_dispatch_icall_fptr
0x10041fea0  mov     rax, [rdi]
0x10041fea3  mov     rcx, rdi
0x10041fea6  mov     rax, [rax+38h]
0x10041feaa  call    cs:__guard_dispatch_icall_fptr
0x10041feb0  jmp     short loc_10041FEBA
0x10041feb2  mov     ebx, [rsp+78h+var_38]
0x10041feb6  mov     [rsp+78h+var_34], ebx
0x10041feba  mov     eax, ebx
0x10041febc  lea     r11, [rsp+78h+var_8]
0x10041fec1  mov     rbx, [r11+10h]
0x10041fec5  mov     rsi, [r11+18h]
0x10041fec9  mov     rdi, [r11+20h]
0x10041fecd  mov     r14, [r11+28h]
0x10041fed1  mov     rsp, r11
0x10041fed4  pop     r15
0x10041fed6  retn
0x10043a710  push    rbp
0x10043a712  sub     rsp, 40h
0x10043a716  mov     rbp, rdx
0x10043a719  mov     [rbp+60h], rcx
0x10043a71d  mov     [rbp+58h], rcx
0x10043a721  mov     rax, [rbp+58h]
0x10043a725  mov     rcx, [rax]
0x10043a728  mov     [rbp+50h], rcx
0x10043a72c  mov     rax, [rbp+50h]
0x10043a730  mov     eax, [rax]
0x10043a732  cmp     eax, 0C0000005h
0x10043a737  jz      short loc_10043A769
0x10043a739  add     eax, 1FFFFFFFh
0x10043a73e  cmp     eax, 1
0x10043a741  ja      short loc_10043A759
0x10043a743  mov     rax, [rbp+50h]
0x10043a747  cmp     dword ptr [rax+18h], 1
0x10043a74b  jnz     short loc_10043A759
0x10043a74d  mov     rax, [rbp+50h]
0x10043a751  mov     ecx, [rax+20h]
0x10043a754  mov     [rbp+40h], ecx
0x10043a757  jmp     short loc_10043A760
0x10043a759  mov     dword ptr [rbp+40h], 8000FFFFh
0x10043a760  mov     dword ptr [rbp+48h], 1
0x10043a767  jmp     short loc_10043A770
0x10043a769  mov     dword ptr [rbp+48h], 0
0x10043a770  mov     eax, [rbp+48h]
0x10043a773  add     rsp, 40h
0x10043a777  pop     rbp
0x10043a778  retn
```
