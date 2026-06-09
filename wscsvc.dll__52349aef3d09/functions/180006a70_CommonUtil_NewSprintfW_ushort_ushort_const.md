# CommonUtil::NewSprintfW(ushort * *,ushort const *,...)

- ea: `0x180006a70`
- end: `0x180006c46`
- name: `?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ`
- size: `470`
- prototype: `__int64(CommonUtil *this, wchar_t *, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800062d0`
- `0x180017c60`
- `0x18001c218`
- `0x18003a2b4`

## callees

- `0x180006a70`
- `0x18001bd80`
- `0x18001fd40`
- `0x180029e74`
- `0x18002a756`
- `0x18002b1ac`
- `0x18003fc30`

## import_xrefs

- `msvcrt!_vscwprintf` at `0x180006bb0`
- `msvcrt!_vscwprintf` at `0x180006bb0`
- `msvcrt!_vsnwprintf` at `0x180006acf`
- `msvcrt!_vsnwprintf` at `0x180006acf`

## pseudocode

```c
__int64 CommonUtil::NewSprintfW(CommonUtil *this, wchar_t *a2, const unsigned __int16 *a3, ...)
{
  void *v5; // rbx
  unsigned int v6; // eax
  __int64 v7; // rax
  unsigned __int64 v9; // rdi
  size_t v10; // rax
  void *v11; // rax
  unsigned int v13; // ebp
  unsigned __int64 v14; // rbp
  int v15; // eax
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  char *v20; // [rsp+28h] [rbp-270h]
  unsigned __int64 v21; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int16 v22[4]; // [rsp+38h] [rbp-260h] BYREF
  wchar_t Buffer[259]; // [rsp+40h] [rbp-258h] BYREF
  __int16 v24; // [rsp+246h] [rbp-52h]
  const unsigned __int16 *v25; // [rsp+2B0h] [rbp+18h] BYREF

  v25 = a3;
  *(_QWORD *)this = 0;
  v5 = 0;
  v21 = 0;
  v6 = _vsnwprintf(Buffer, 0x103u, a2, (va_list)&v25);
  if ( v6 >= 0x104 )
  {
    v24 = 0;
    *(_QWORD *)v22 = 0;
    v14 = 0;
    v15 = _vscwprintf(a2, (va_list)&v25);
    v16 = 260;
    if ( v15 >= 0 )
    {
      v17 = v15 + 1LL;
      if ( v17 > 0x104 )
        v14 = v17;
      *(_QWORD *)v22 = v14;
    }
    while ( 1 )
    {
      if ( v16 >= v14 )
        v16 = (3 * v16) >> 1;
      else
        v16 = v14;
      if ( v16 > 0x7FFFFFFF )
      {
        v13 = -2147024774;
        goto LABEL_11;
      }
      v18 = CommonUtil::CNewSprintfPolicy<unsigned short>::ReAllocateNoCopy(&v21, v16);
      v5 = (void *)v21;
      v13 = v18;
      if ( v18 < 0 )
        goto LABEL_11;
      v19 = MpUtilsExports::MpStringCchVPrintfWImpl(
              (MpUtilsExports *)v16,
              v21,
              v22,
              (unsigned __int64 *)a2,
              (const unsigned __int16 *)&v25,
              v20);
      v13 = v19;
      if ( v19 != -2147024774 )
        break;
      v14 = *(_QWORD *)v22;
    }
    if ( v19 < 0 )
      goto LABEL_11;
    goto LABEL_10;
  }
  if ( v6 == 259 )
    v24 = 0;
  v7 = -1;
  while ( Buffer[++v7] != 0 )
    ;
  v9 = v7 + 1;
  operator delete(0);
  v10 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v10 = -1;
  v11 = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v11;
  if ( v11 )
  {
    memcpy_0(v11, Buffer, 2 * v9);
LABEL_10:
    *(_QWORD *)this = v5;
    return 0;
  }
  v13 = -2147024882;
LABEL_11:
  if ( v5 )
    operator delete(v5);
  return v13;
}

```

## disassembly

```asm
0x180006a70  mov     r11, rsp
0x180006a73  mov     [r11+10h], rdx
0x180006a77  mov     [r11+18h], r8
0x180006a7b  mov     [r11+20h], r9
0x180006a7f  push    rbx
0x180006a80  push    rbp
0x180006a81  push    rsi
0x180006a82  push    rdi
0x180006a83  push    r12
0x180006a85  push    r14
0x180006a87  push    r15
0x180006a89  sub     rsp, 260h
0x180006a90  mov     rax, cs:__security_cookie
0x180006a97  xor     rax, rsp
0x180006a9a  mov     [rsp+298h+var_48], rax
0x180006aa2  xor     r15d, r15d
0x180006aa5  lea     r12, [r11+18h]
0x180006aa9  mov     [rcx], r15
0x180006aac  mov     rdi, rdx
0x180006aaf  mov     rsi, rcx
0x180006ab2  mov     [rsp+298h+var_268], r15
0x180006ab7  mov     r8, rdx; Format
0x180006aba  lea     rcx, [rsp+298h+Buffer]; Buffer
0x180006abf  mov     ebx, r15d
0x180006ac2  mov     r9, r12; Args
0x180006ac5  mov     edx, 103h; BufferCount
0x180006aca  mov     [rsp+298h+var_268], rbx
0x180006acf  call    cs:__imp__vsnwprintf
0x180006ad5  test    eax, eax
0x180006ad7  js      loc_180006B99
0x180006add  cmp     eax, 103h
0x180006ae2  ja      loc_180006B99
0x180006ae8  jz      loc_180006B84
0x180006aee  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180006af5  lea     rcx, [rsp+298h+Buffer]
0x180006afa  mov     rax, rbx
0x180006afd  nop     dword ptr [rax]
0x180006b00  cmp     [rcx+rax*2+2], r15w
0x180006b06  lea     rax, [rax+1]
0x180006b0a  jnz     short loc_180006B00
0x180006b0c  xor     ecx, ecx; Block
0x180006b0e  lea     rdi, [rax+1]
0x180006b12  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006b17  mov     eax, 2
0x180006b1c  mul     rdi
0x180006b1f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006b26  cmovb   rax, rbx
0x180006b2a  mov     rcx, rax; unsigned __int64
0x180006b2d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006b32  mov     rbx, rax
0x180006b35  test    rax, rax
0x180006b38  jz      short loc_180006B92
0x180006b3a  lea     r8, [rdi+rdi]; Size
0x180006b3e  mov     rcx, rax; void *
0x180006b41  lea     rdx, [rsp+298h+Buffer]; Src
0x180006b46  call    memcpy_0
0x180006b4b  mov     [rsi], rbx
0x180006b4e  mov     eax, r15d
0x180006b51  mov     rcx, [rsp+298h+var_48]
0x180006b59  xor     rcx, rsp; StackCookie
0x180006b5c  call    __security_check_cookie
0x180006b61  add     rsp, 260h
0x180006b68  pop     r15
0x180006b6a  pop     r14
0x180006b6c  pop     r12
0x180006b6e  pop     rdi
0x180006b6f  pop     rsi
0x180006b70  pop     rbp
0x180006b71  pop     rbx
0x180006b72  retn
0x180006b73  test    rbx, rbx
0x180006b76  jz      short loc_180006B80
0x180006b78  mov     rcx, rbx; Block
0x180006b7b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006b80  mov     eax, ebp
0x180006b82  jmp     short loc_180006B51
0x180006b84  mov     [rsp+298h+var_52], r15w
0x180006b8d  jmp     loc_180006AEE
0x180006b92  mov     ebp, 8007000Eh
0x180006b97  jmp     short loc_180006B73
0x180006b99  mov     rdx, r12; ArgList
0x180006b9c  mov     [rsp+298h+var_52], r15w
0x180006ba5  mov     rcx, rdi; Format
0x180006ba8  mov     qword ptr [rsp+298h+var_260], r15
0x180006bad  mov     rbp, r15
0x180006bb0  call    cs:__imp__vscwprintf
0x180006bb6  mov     r14d, 104h
0x180006bbc  test    eax, eax
0x180006bbe  js      short loc_180006BD1
0x180006bc0  cdqe
0x180006bc2  inc     rax
0x180006bc5  cmp     rax, r14
0x180006bc8  cmova   rbp, rax
0x180006bcc  mov     qword ptr [rsp+298h+var_260], rbp
0x180006bd1  cmp     r14, rbp
0x180006bd4  jnb     short loc_180006BDB
0x180006bd6  mov     r14, rbp
0x180006bd9  jmp     short loc_180006BE2
0x180006bdb  lea     r14, [r14+r14*2]
0x180006bdf  shr     r14, 1
0x180006be2  cmp     r14, 7FFFFFFFh
0x180006be9  ja      short loc_180006C3C
0x180006beb  mov     rdx, r14
0x180006bee  lea     rcx, [rsp+298h+var_268]
0x180006bf3  call    ?ReAllocateNoCopy@?$CNewSprintfPolicy@G@CommonUtil@@SAJPEAPEAG_K@Z; CommonUtil::CNewSprintfPolicy<ushort>::ReAllocateNoCopy(ushort * *,unsigned __int64)
0x180006bf8  mov     rbx, [rsp+298h+var_268]
0x180006bfd  mov     ebp, eax
0x180006bff  test    eax, eax
0x180006c01  js      loc_180006B73
0x180006c07  mov     r9, rdi; unsigned __int64 *
0x180006c0a  mov     [rsp+298h+var_278], r12; unsigned __int16 *
0x180006c0f  lea     r8, [rsp+298h+var_260]; unsigned __int16 *
0x180006c14  mov     rdx, rbx; unsigned __int64
0x180006c17  mov     rcx, r14; this
0x180006c1a  call    ?MpStringCchVPrintfWImpl@MpUtilsExports@@YAJ_KPEAGPEA_KPEBGPEAD@Z; MpUtilsExports::MpStringCchVPrintfWImpl(unsigned __int64,ushort *,unsigned __int64 *,ushort const *,char *)
0x180006c1f  mov     ebp, eax
0x180006c21  cmp     eax, 8007007Ah
0x180006c26  jnz     short loc_180006C2F
0x180006c28  mov     rbp, qword ptr [rsp+298h+var_260]
0x180006c2d  jmp     short loc_180006BD1
0x180006c2f  test    eax, eax
0x180006c31  js      loc_180006B73
0x180006c37  jmp     loc_180006B4B
0x180006c3c  mov     ebp, 8007007Ah
0x180006c41  jmp     loc_180006B73
```
