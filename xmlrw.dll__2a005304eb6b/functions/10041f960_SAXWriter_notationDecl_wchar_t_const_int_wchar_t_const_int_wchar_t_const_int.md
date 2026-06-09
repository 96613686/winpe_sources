# SAXWriter::notationDecl(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041f960`
- end: `0x10041fac2`
- name: `?notationDecl@SAXWriter@@UEAAJPEB_WH0H0H@Z`
- size: `354`
- prototype: `int(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x10041df10`
- `0x10041f960`
- `0x10041fd60`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::notationDecl(
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
    if ( *((_DWORD *)this + 7) == 1 )
    {
      *((_DWORD *)this + 7) = 1;
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 5) + 40LL))((char *)this - 40, 1);
      if ( v11 )
        return v11;
    }
    v12 = (SAXWriter *)((char *)this - 40);
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 60);
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 33);
    (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)v12 + 80LL))(v12, CodeStringPtr::NOTATION);
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v12 + 88LL))(v12, 32);
    (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)v12 + 72LL))(v12, a2, a3);
    v11 = SAXWriter::writeExternalID(v12, a4, a5, a6, a7, 1, 1);
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
  return v11;
}

```

## disassembly

```asm
0x10041f960  mov     [rsp+arg_0], rbx
0x10041f965  mov     [rsp+arg_8], rsi
0x10041f96a  mov     [rsp+arg_10], rdi
0x10041f96f  mov     [rsp+arg_18], r14
0x10041f974  push    r15
0x10041f976  sub     rsp, 70h
0x10041f97a  mov     r14, r9
0x10041f97d  mov     r15d, r8d
0x10041f980  mov     rsi, rdx
0x10041f983  mov     rdi, rcx
0x10041f986  test    rdx, rdx
0x10041f989  jnz     short loc_10041F999
0x10041f98b  mov     ebx, 80070057h
0x10041f990  mov     [rsp+78h+var_34], ebx
0x10041f994  jmp     loc_10041FAA5
0x10041f999  cmp     dword ptr [rcx+1Ch], 1
0x10041f99d  jnz     short loc_10041F9A8
0x10041f99f  mov     dword ptr [rcx+1Ch], 1
0x10041f9a6  jmp     short loc_10041F9CC
0x10041f9a8  add     rcx, 0FFFFFFFFFFFFFFD8h
0x10041f9ac  mov     rax, [rcx]
0x10041f9af  mov     edx, 1
0x10041f9b4  mov     rax, [rax+28h]
0x10041f9b8  call    cs:__guard_dispatch_icall_fptr
0x10041f9be  mov     ebx, eax
0x10041f9c0  mov     [rsp+78h+var_34], eax
0x10041f9c4  test    eax, eax
0x10041f9c6  jnz     loc_10041FAA5
0x10041f9cc  add     rdi, 0FFFFFFFFFFFFFFD8h
0x10041f9d0  mov     rax, [rdi]
0x10041f9d3  mov     edx, 3Ch ; '<'
0x10041f9d8  mov     rcx, rdi
0x10041f9db  mov     rax, [rax+58h]
0x10041f9df  call    cs:__guard_dispatch_icall_fptr
0x10041f9e5  mov     rax, [rdi]
0x10041f9e8  mov     edx, 21h ; '!'
0x10041f9ed  mov     rcx, rdi
0x10041f9f0  mov     rax, [rax+58h]
0x10041f9f4  call    cs:__guard_dispatch_icall_fptr
0x10041f9fa  mov     rax, [rdi]
0x10041f9fd  mov     rdx, cs:?NOTATION@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::NOTATION
0x10041fa04  mov     rcx, rdi
0x10041fa07  mov     rax, [rax+50h]
0x10041fa0b  call    cs:__guard_dispatch_icall_fptr
0x10041fa11  mov     rax, [rdi]
0x10041fa14  mov     edx, 20h ; ' '
0x10041fa19  mov     rcx, rdi
0x10041fa1c  mov     rax, [rax+58h]
0x10041fa20  call    cs:__guard_dispatch_icall_fptr
0x10041fa26  mov     rax, [rdi]
0x10041fa29  mov     r8d, r15d
0x10041fa2c  mov     rdx, rsi
0x10041fa2f  mov     rcx, rdi
0x10041fa32  mov     rax, [rax+48h]
0x10041fa36  call    cs:__guard_dispatch_icall_fptr
0x10041fa3c  mov     [rsp+78h+var_48], 1; bool
0x10041fa41  mov     [rsp+78h+var_50], 1; bool
0x10041fa46  mov     eax, [rsp+78h+arg_30]
0x10041fa4d  mov     [rsp+78h+var_58], eax; int
0x10041fa51  mov     r9, [rsp+78h+arg_28]; wchar_t *
0x10041fa59  mov     r8d, [rsp+78h+arg_20]; int
0x10041fa61  mov     rdx, r14; wchar_t *
0x10041fa64  mov     rcx, rdi; this
0x10041fa67  call    ?writeExternalID@SAXWriter@@IEAAJPEB_WH0H_N1@Z; SAXWriter::writeExternalID(wchar_t const *,int,wchar_t const *,int,bool,bool)
0x10041fa6c  mov     ebx, eax
0x10041fa6e  mov     [rsp+78h+var_34], eax
0x10041fa72  test    eax, eax
0x10041fa74  jnz     short loc_10041FAA5
0x10041fa76  mov     rax, [rdi]
0x10041fa79  mov     edx, 3Eh ; '>'
0x10041fa7e  mov     rcx, rdi
0x10041fa81  mov     rax, [rax+58h]
0x10041fa85  call    cs:__guard_dispatch_icall_fptr
0x10041fa8b  mov     rax, [rdi]
0x10041fa8e  mov     rcx, rdi
0x10041fa91  mov     rax, [rax+38h]
0x10041fa95  call    cs:__guard_dispatch_icall_fptr
0x10041fa9b  jmp     short loc_10041FAA5
0x10041fa9d  mov     ebx, [rsp+78h+var_38]
0x10041faa1  mov     [rsp+78h+var_34], ebx
0x10041faa5  mov     eax, ebx
0x10041faa7  lea     r11, [rsp+78h+var_8]
0x10041faac  mov     rbx, [r11+10h]
0x10041fab0  mov     rsi, [r11+18h]
0x10041fab4  mov     rdi, [r11+20h]
0x10041fab8  mov     r14, [r11+28h]
0x10041fabc  mov     rsp, r11
0x10041fabf  pop     r15
0x10041fac1  retn
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
