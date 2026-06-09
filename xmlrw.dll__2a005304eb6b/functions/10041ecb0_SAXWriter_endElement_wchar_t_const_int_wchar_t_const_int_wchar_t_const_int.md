# SAXWriter::endElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041ecb0`
- end: `0x10041edeb`
- name: `?endElement@SAXWriter@@UEAAJPEB_WH0H0H@Z`
- size: `315`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10041ecb0`
- `0x10041f5e0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::endElement(
        SAXWriter *this,
        const wchar_t *a2,
        __int64 a3,
        const wchar_t *a4,
        int a5,
        const wchar_t *a6,
        unsigned int a7)
{
  unsigned int v8; // ebx
  int v9; // r15d
  __int64 v10; // rax
  char *v11; // rcx
  int v12; // eax
  unsigned int v14; // [rsp+20h] [rbp-38h]

  v8 = 0;
  v14 = 0;
  v9 = *((_DWORD *)this + 3);
  if ( a2 )
  {
    if ( a4 )
    {
      if ( a6 )
      {
        if ( v9 == 1 )
        {
          *((_DWORD *)this + 3) = 3;
        }
        else
        {
          v8 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 7) + 40LL))((char *)this - 56, 3);
          v14 = v8;
          if ( v8 )
            return v8;
        }
        if ( (*(int (__fastcall **)(char *))(*((_QWORD *)this - 7) + 200LL))((char *)this - 56) > 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this - 7) + 192LL))((char *)this - 56, 0xFFFFFFFFLL);
          v8 = v14;
        }
        v10 = *((_QWORD *)this - 7);
        v11 = (char *)this - 56;
        if ( v9 == 2 )
          (*(void (__fastcall **)(char *))(v10 + 120))(v11);
        else
          (*(void (__fastcall **)(char *, const wchar_t *, _QWORD))(v10 + 104))(v11, a6, a7);
        v12 = 1;
        if ( *((_BYTE *)this + 161) )
          v12 = 8;
        *((_DWORD *)this + 3) = v12;
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
  return v8;
}

```

## disassembly

```asm
0x10041ecb0  mov     [rsp+arg_0], rbx
0x10041ecb5  mov     [rsp+arg_8], rsi
0x10041ecba  mov     [rsp+arg_10], rdi
0x10041ecbf  push    r15
0x10041ecc1  sub     rsp, 50h
0x10041ecc5  mov     rsi, rcx
0x10041ecc8  xor     ebx, ebx
0x10041ecca  mov     [rsp+58h+var_38], ebx
0x10041ecce  mov     r15d, [rcx+0Ch]
0x10041ecd2  test    rdx, rdx
0x10041ecd5  jnz     short loc_10041ECE5
0x10041ecd7  mov     ebx, 80070057h
0x10041ecdc  mov     [rsp+58h+var_38], ebx
0x10041ece0  jmp     loc_10041EDD3
0x10041ece5  test    r9, r9
0x10041ece8  jnz     short loc_10041ECF8
0x10041ecea  mov     ebx, 80070057h
0x10041ecef  mov     [rsp+58h+var_38], ebx
0x10041ecf3  jmp     loc_10041EDD3
0x10041ecf8  cmp     [rsp+58h+arg_28], 0
0x10041ed01  jnz     short loc_10041ED11
0x10041ed03  mov     ebx, 80070057h
0x10041ed08  mov     [rsp+58h+var_38], ebx
0x10041ed0c  jmp     loc_10041EDD3
0x10041ed11  cmp     r15d, 1
0x10041ed15  jnz     short loc_10041ED20
0x10041ed17  mov     dword ptr [rcx+0Ch], 3
0x10041ed1e  jmp     short loc_10041ED44
0x10041ed20  add     rcx, 0FFFFFFFFFFFFFFC8h
0x10041ed24  mov     rax, [rcx]
0x10041ed27  mov     edx, 3
0x10041ed2c  mov     rax, [rax+28h]
0x10041ed30  call    cs:__guard_dispatch_icall_fptr
0x10041ed36  mov     ebx, eax
0x10041ed38  mov     [rsp+58h+var_38], eax
0x10041ed3c  test    eax, eax
0x10041ed3e  jnz     loc_10041EDD3
0x10041ed44  mov     rax, [rsi-38h]
0x10041ed48  lea     rcx, [rsi-38h]
0x10041ed4c  mov     rax, [rax+0C8h]
0x10041ed53  call    cs:__guard_dispatch_icall_fptr
0x10041ed59  test    eax, eax
0x10041ed5b  jle     short loc_10041ED7E
0x10041ed5d  lfence
0x10041ed60  mov     rax, [rsi-38h]
0x10041ed64  mov     edx, 0FFFFFFFFh
0x10041ed69  lea     rcx, [rsi-38h]
0x10041ed6d  mov     rax, [rax+0C0h]
0x10041ed74  call    cs:__guard_dispatch_icall_fptr
0x10041ed7a  mov     ebx, [rsp+58h+var_38]
0x10041ed7e  mov     rax, [rsi-38h]
0x10041ed82  lea     rcx, [rsi-38h]
0x10041ed86  cmp     r15d, 2
0x10041ed8a  jz      short loc_10041EDA8
0x10041ed8c  mov     r8d, [rsp+58h+arg_30]
0x10041ed94  mov     rdx, [rsp+58h+arg_28]
0x10041ed9c  mov     rax, [rax+68h]
0x10041eda0  call    cs:__guard_dispatch_icall_fptr
0x10041eda6  jmp     short loc_10041EDB2
0x10041eda8  mov     rax, [rax+78h]
0x10041edac  call    cs:__guard_dispatch_icall_fptr
0x10041edb2  mov     eax, 1
0x10041edb7  mov     ecx, 8
0x10041edbc  cmp     byte ptr [rsi+0A1h], 0
0x10041edc3  cmovnz  eax, ecx
0x10041edc6  mov     [rsi+0Ch], eax
0x10041edc9  jmp     short loc_10041EDD3
0x10041edcb  mov     ebx, [rsp+58h+var_34]
0x10041edcf  mov     [rsp+58h+var_38], ebx
0x10041edd3  mov     eax, ebx
0x10041edd5  mov     rbx, [rsp+58h+arg_0]
0x10041edda  mov     rsi, [rsp+58h+arg_8]
0x10041eddf  mov     rdi, [rsp+58h+arg_10]
0x10041ede4  add     rsp, 50h
0x10041ede8  pop     r15
0x10041edea  retn
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
