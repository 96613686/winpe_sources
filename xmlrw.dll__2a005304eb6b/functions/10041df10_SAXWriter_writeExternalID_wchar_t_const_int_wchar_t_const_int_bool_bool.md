# SAXWriter::writeExternalID(wchar_t const *,int,wchar_t const *,int,bool,bool)

- ea: `0x10041df10`
- end: `0x10041e0b5`
- name: `?writeExternalID@SAXWriter@@IEAAJPEB_WH0H_N1@Z`
- size: `421`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, bool, bool)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x10041f7a0`
- `0x10041f960`
- `0x10041fad0`
- `0x10041fd60`

## callees

- `0x10041df10`
- `0x1004245e0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::writeExternalID(
        SAXWriter *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        bool a6,
        bool a7)
{
  unsigned int v11; // ebx
  unsigned int v12; // esi

  v11 = 0;
  if ( a3 )
  {
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 32);
    (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)this + 80LL))(this, CodeStringPtr::PUBLIC);
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 32);
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 34);
    (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)this + 72LL))(this, a2, a3);
    (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 34);
    v12 = a5;
    if ( !a7 || a5 )
    {
      if ( !a5 )
        return (unsigned int)-2147024809;
LABEL_10:
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 32);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 34);
      (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)this + 72LL))(this, a4, v12);
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 34);
    }
  }
  else
  {
    v12 = a5;
    if ( a5 )
    {
      (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 32);
      (*(void (__fastcall **)(SAXWriter *, _QWORD))(*(_QWORD *)this + 80LL))(this, CodeStringPtr::SYSTEM);
      goto LABEL_10;
    }
    if ( a6 )
      return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x10041df10  mov     [rsp+arg_0], rbx
0x10041df15  mov     [rsp+arg_8], rsi
0x10041df1a  mov     [rsp+arg_10], rdi
0x10041df1f  mov     [rsp+arg_18], r14
0x10041df24  push    r15
0x10041df26  sub     rsp, 50h
0x10041df2a  mov     r14, r9
0x10041df2d  mov     esi, r8d
0x10041df30  mov     r15, rdx
0x10041df33  mov     rdi, rcx
0x10041df36  xor     ebx, ebx
0x10041df38  mov     [rsp+58h+var_34], ebx
0x10041df3c  test    r8d, r8d
0x10041df3f  jz      loc_10041DFE5
0x10041df45  mov     rax, [rcx]
0x10041df48  lea     edx, [rbx+20h]
0x10041df4b  mov     rax, [rax+58h]
0x10041df4f  call    cs:__guard_dispatch_icall_fptr
0x10041df55  mov     rax, [rdi]
0x10041df58  mov     rdx, cs:?PUBLIC@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::PUBLIC
0x10041df5f  mov     rcx, rdi
0x10041df62  mov     rax, [rax+50h]
0x10041df66  call    cs:__guard_dispatch_icall_fptr
0x10041df6c  mov     rax, [rdi]
0x10041df6f  lea     edx, [rbx+20h]
0x10041df72  mov     rcx, rdi
0x10041df75  mov     rax, [rax+58h]
0x10041df79  call    cs:__guard_dispatch_icall_fptr
0x10041df7f  mov     rax, [rdi]
0x10041df82  lea     edx, [rbx+22h]
0x10041df85  mov     rcx, rdi
0x10041df88  mov     rax, [rax+58h]
0x10041df8c  call    cs:__guard_dispatch_icall_fptr
0x10041df92  mov     rax, [rdi]
0x10041df95  mov     r8d, esi
0x10041df98  mov     rdx, r15
0x10041df9b  mov     rcx, rdi
0x10041df9e  mov     rax, [rax+48h]
0x10041dfa2  call    cs:__guard_dispatch_icall_fptr
0x10041dfa8  mov     rax, [rdi]
0x10041dfab  lea     edx, [rbx+22h]
0x10041dfae  mov     rcx, rdi
0x10041dfb1  mov     rax, [rax+58h]
0x10041dfb5  call    cs:__guard_dispatch_icall_fptr
0x10041dfbb  mov     esi, [rsp+58h+arg_20]
0x10041dfc2  cmp     [rsp+58h+arg_30], bl
0x10041dfc9  jz      short loc_10041DFD3
0x10041dfcb  test    esi, esi
0x10041dfcd  jz      loc_10041E08E
0x10041dfd3  test    esi, esi
0x10041dfd5  jnz     short loc_10041E039
0x10041dfd7  mov     ebx, 80070057h
0x10041dfdc  mov     [rsp+58h+var_34], ebx
0x10041dfe0  jmp     loc_10041E098
0x10041dfe5  mov     esi, [rsp+58h+arg_20]
0x10041dfec  test    esi, esi
0x10041dfee  jnz     short loc_10041E010
0x10041dff0  cmp     [rsp+58h+arg_28], sil
0x10041dff8  jz      loc_10041E08E
0x10041dffe  test    esi, esi
0x10041e000  jnz     short loc_10041E010
0x10041e002  mov     ebx, 80070057h
0x10041e007  mov     [rsp+58h+var_34], ebx
0x10041e00b  jmp     loc_10041E098
0x10041e010  mov     rax, [rcx]
0x10041e013  mov     edx, 20h ; ' '
0x10041e018  mov     rax, [rax+58h]
0x10041e01c  call    cs:__guard_dispatch_icall_fptr
0x10041e022  mov     rax, [rdi]
0x10041e025  mov     rdx, cs:?SYSTEM@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::SYSTEM
0x10041e02c  mov     rcx, rdi
0x10041e02f  mov     rax, [rax+50h]
0x10041e033  call    cs:__guard_dispatch_icall_fptr
0x10041e039  mov     rax, [rdi]
0x10041e03c  mov     edx, 20h ; ' '
0x10041e041  mov     rcx, rdi
0x10041e044  mov     rax, [rax+58h]
0x10041e048  call    cs:__guard_dispatch_icall_fptr
0x10041e04e  mov     rax, [rdi]
0x10041e051  mov     edx, 22h ; '"'
0x10041e056  mov     rcx, rdi
0x10041e059  mov     rax, [rax+58h]
0x10041e05d  call    cs:__guard_dispatch_icall_fptr
0x10041e063  mov     rax, [rdi]
0x10041e066  mov     r8d, esi
0x10041e069  mov     rdx, r14
0x10041e06c  mov     rcx, rdi
0x10041e06f  mov     rax, [rax+48h]
0x10041e073  call    cs:__guard_dispatch_icall_fptr
0x10041e079  mov     rax, [rdi]
0x10041e07c  mov     edx, 22h ; '"'
0x10041e081  mov     rcx, rdi
0x10041e084  mov     rax, [rax+58h]
0x10041e088  call    cs:__guard_dispatch_icall_fptr
0x10041e08e  jmp     short loc_10041E098
0x10041e090  mov     ebx, [rsp+58h+var_38]
0x10041e094  mov     [rsp+58h+var_34], ebx
0x10041e098  mov     eax, ebx
0x10041e09a  mov     rbx, [rsp+58h+arg_0]
0x10041e09f  mov     rsi, [rsp+58h+arg_8]
0x10041e0a4  mov     rdi, [rsp+58h+arg_10]
0x10041e0a9  mov     r14, [rsp+58h+arg_18]
0x10041e0ae  add     rsp, 50h
0x10041e0b2  pop     r15
0x10041e0b4  retn
0x10043a380  push    rbp
0x10043a382  sub     rsp, 20h
0x10043a386  mov     rbp, rdx
0x10043a389  mov     [rbp+40h], rcx
0x10043a38d  mov     [rbp+38h], rcx
0x10043a391  mov     rax, [rbp+38h]
0x10043a395  mov     rcx, [rax]
0x10043a398  mov     [rbp+30h], rcx
0x10043a39c  mov     rax, [rbp+30h]
0x10043a3a0  mov     eax, [rax]
0x10043a3a2  cmp     eax, 0C0000005h
0x10043a3a7  jz      short loc_10043A3D9
0x10043a3a9  add     eax, 1FFFFFFFh
0x10043a3ae  cmp     eax, 1
0x10043a3b1  ja      short loc_10043A3C9
0x10043a3b3  mov     rax, [rbp+30h]
0x10043a3b7  cmp     dword ptr [rax+18h], 1
0x10043a3bb  jnz     short loc_10043A3C9
0x10043a3bd  mov     rax, [rbp+30h]
0x10043a3c1  mov     ecx, [rax+20h]
0x10043a3c4  mov     [rbp+20h], ecx
0x10043a3c7  jmp     short loc_10043A3D0
0x10043a3c9  mov     dword ptr [rbp+20h], 8000FFFFh
0x10043a3d0  mov     dword ptr [rbp+28h], 1
0x10043a3d7  jmp     short loc_10043A3E0
0x10043a3d9  mov     dword ptr [rbp+28h], 0
0x10043a3e0  mov     eax, [rbp+28h]
0x10043a3e3  add     rsp, 20h
0x10043a3e7  pop     rbp
0x10043a3e8  retn
```
