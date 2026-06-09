# SAXWriter::printf(wchar_t const *,...)

- ea: `0x10041dcc0`
- end: `0x10041ddc4`
- name: `?printf@SAXWriter@@IEAAJPEB_WZZ`
- size: `260`
- prototype: `int(SAXWriter *__hidden this, const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10041e0c0`

## callees

- `0x10041bf40`
- `0x10041dcc0`
- `0x10042d618`
- `0x100439df0`

## pseudocode

```c
__int64 SAXWriter::printf(SAXWriter *this, const wchar_t *a2, ...)
{
  wchar_t *v4; // rsi
  wchar_t *v5; // r14
  unsigned int v6; // edi
  unsigned __int64 *v7; // rax
  const wchar_t *v8; // r9
  __int64 v9; // rbx
  int v10; // eax
  va_list va; // [rsp+C0h] [rbp+18h] BYREF

  va_start(va, a2);
  v4 = 0;
  v5 = (wchar_t *)((char *)this + 228);
  v6 = 0;
  v7 = _local_stdio_printf_options();
  v8 = a2;
  v9 = 127;
  v10 = _stdio_common_vswprintf(*v7 | 1, v5, 0x7Fu, v8, 0, va);
  if ( v10 < 0 )
    v10 = -1;
  if ( v10 < 0 || (unsigned __int64)v10 > 0x7F )
  {
    v6 = -2147024774;
    goto LABEL_8;
  }
  if ( v10 == 127 )
  {
LABEL_8:
    v5[127] = 0;
    goto LABEL_9;
  }
  v9 = v10;
LABEL_9:
  if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147024774 )
    v4 = &v5[v9];
  if ( !v6 )
  {
    (*(void (__fastcall **)(SAXWriter *, wchar_t *, signed __int64))(*(_QWORD *)this + 72LL))(
      this,
      v5,
      ((char *)v4 - (char *)this - 228) >> 1);
    (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 56LL))(this);
  }
  return v6;
}

```

## disassembly

```asm
0x10041dcc0  mov     rax, rsp
0x10041dcc3  mov     [rax+10h], rdx
0x10041dcc7  mov     [rax+18h], r8
0x10041dccb  mov     [rax+20h], r9
0x10041dccf  push    rbx
0x10041dcd0  push    rsi
0x10041dcd1  push    rdi
0x10041dcd2  push    r12
0x10041dcd4  push    r13
0x10041dcd6  push    r14
0x10041dcd8  push    r15
0x10041dcda  sub     rsp, 70h
0x10041dcde  mov     rbx, rdx
0x10041dce1  mov     r15, rcx
0x10041dce4  xor     r13d, r13d
0x10041dce7  mov     esi, r13d
0x10041dcea  mov     [rax-68h], r13
0x10041dcee  lea     r12, [rax+18h]
0x10041dcf2  lea     r14, [rcx+0E4h]
0x10041dcf9  mov     edi, r13d
0x10041dcfc  call    __local_stdio_printf_options
0x10041dd01  mov     rcx, [rax]
0x10041dd04  or      rcx, 1; Options
0x10041dd08  mov     [rsp+0A8h+ArgList], r12; ArgList
0x10041dd0d  mov     [rsp+0A8h+Locale], r13; Locale
0x10041dd12  mov     r9, rbx; Format
0x10041dd15  mov     ebx, 7Fh
0x10041dd1a  mov     r8d, ebx; BufferCount
0x10041dd1d  mov     rdx, r14; Buffer
0x10041dd20  call    __stdio_common_vswprintf
0x10041dd25  mov     ecx, 0FFFFFFFFh
0x10041dd2a  test    eax, eax
0x10041dd2c  cmovs   eax, ecx
0x10041dd2f  test    eax, eax
0x10041dd31  js      short loc_10041DD41
0x10041dd33  cdqe
0x10041dd35  cmp     rax, rbx
0x10041dd38  ja      short loc_10041DD41
0x10041dd3a  jz      short loc_10041DD46
0x10041dd3c  mov     rbx, rax
0x10041dd3f  jmp     short loc_10041DD4E
0x10041dd41  mov     edi, 8007007Ah
0x10041dd46  mov     [r14+0FEh], r13w
0x10041dd4e  mov     [rsp+0A8h+var_58], rbx
0x10041dd53  lea     rcx, [r14+rbx*2]
0x10041dd57  mov     edx, 80000000h
0x10041dd5c  lea     eax, [rdi+rdx]
0x10041dd5f  test    edx, eax
0x10041dd61  jnz     short loc_10041DD6B
0x10041dd63  cmp     edi, 8007007Ah
0x10041dd69  jnz     short loc_10041DD73
0x10041dd6b  mov     rsi, rcx
0x10041dd6e  mov     [rsp+0A8h+var_68], rcx
0x10041dd73  test    edi, edi
0x10041dd75  jnz     short loc_10041DDB2
0x10041dd77  mov     [rsp+0A8h+var_50], r13
0x10041dd7c  mov     rax, [r15]
0x10041dd7f  sub     rsi, r15
0x10041dd82  lea     r8, [rsi-0E4h]
0x10041dd89  sar     r8, 1
0x10041dd8c  mov     rdx, r14
0x10041dd8f  mov     rcx, r15
0x10041dd92  mov     rax, [rax+48h]
0x10041dd96  call    cs:__guard_dispatch_icall_fptr
0x10041dd9c  mov     rax, [r15]
0x10041dd9f  mov     rcx, r15
0x10041dda2  mov     rax, [rax+38h]
0x10041dda6  call    cs:__guard_dispatch_icall_fptr
0x10041ddac  jmp     short loc_10041DDB2
0x10041ddae  mov     edi, [rsp+0A8h+var_78]
0x10041ddb2  mov     eax, edi
0x10041ddb4  add     rsp, 70h
0x10041ddb8  pop     r15
0x10041ddba  pop     r14
0x10041ddbc  pop     r13
0x10041ddbe  pop     r12
0x10041ddc0  pop     rdi
0x10041ddc1  pop     rsi
0x10041ddc2  pop     rbx
0x10041ddc3  retn
0x10043a310  push    rbp
0x10043a312  sub     rsp, 30h
0x10043a316  mov     rbp, rdx
0x10043a319  mov     [rbp+60h], rcx
0x10043a31d  mov     [rbp+48h], rcx
0x10043a321  mov     rax, [rbp+48h]
0x10043a325  mov     rcx, [rax]
0x10043a328  mov     [rbp+38h], rcx
0x10043a32c  mov     rax, [rbp+38h]
0x10043a330  mov     eax, [rax]
0x10043a332  cmp     eax, 0C0000005h
0x10043a337  jz      short loc_10043A369
0x10043a339  add     eax, 1FFFFFFFh
0x10043a33e  cmp     eax, 1
0x10043a341  ja      short loc_10043A359
0x10043a343  mov     rax, [rbp+38h]
0x10043a347  cmp     dword ptr [rax+18h], 1
0x10043a34b  jnz     short loc_10043A359
0x10043a34d  mov     rax, [rbp+38h]
0x10043a351  mov     ecx, [rax+20h]
0x10043a354  mov     [rbp+30h], ecx
0x10043a357  jmp     short loc_10043A360
0x10043a359  mov     dword ptr [rbp+30h], 8000FFFFh
0x10043a360  mov     dword ptr [rbp+34h], 1
0x10043a367  jmp     short loc_10043A370
0x10043a369  mov     dword ptr [rbp+34h], 0
0x10043a370  mov     eax, [rbp+34h]
0x10043a373  add     rsp, 30h
0x10043a377  pop     rbp
0x10043a378  retn
```
