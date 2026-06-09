# SXWriter::docType(wchar_t *,int,wchar_t *,int,wchar_t *,int,wchar_t *,int)

- ea: `0x100408bb0`
- end: `0x100408cf7`
- name: `?docType@SXWriter@@UEAAJPEA_WH0H0H0H@Z`
- size: `327`
- prototype: `int(SXWriter *__hidden this, wchar_t *, int, wchar_t *, int, wchar_t *, int, wchar_t *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100408bb0`
- `0x1004091f0`
- `0x100409740`

## pseudocode

```c
__int64 __fastcall SXWriter::docType(
        SXWriter *this,
        wchar_t *a2,
        unsigned int a3,
        wchar_t *a4,
        int a5,
        wchar_t *a6,
        int a7,
        wchar_t *a8,
        int a9)
{
  SXWriter *v12; // rbx
  unsigned int v14; // [rsp+30h] [rbp-38h]

  v14 = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      if ( a6 )
      {
        if ( a8 )
        {
          v12 = (SXWriter *)((char *)this - 24);
          SXWriter::WriteByte((SXWriter *)((char *)this - 24), 252);
          SXWriter::WriteTextData(v12, 0, a2, a3);
          if ( a7 > 0 )
          {
            _mm_lfence();
            SXWriter::WriteByte(v12, 251);
            SXWriter::WriteTextData(v12, 0, a6, a7);
          }
          if ( a5 > 0 )
          {
            _mm_lfence();
            SXWriter::WriteByte(v12, 250);
            SXWriter::WriteTextData(v12, 0, a4, a5);
          }
          if ( a9 > 0 )
          {
            _mm_lfence();
            SXWriter::WriteByte(v12, 249);
            SXWriter::WriteTextData(v12, 0, a8, a9);
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
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v14;
}

```

## disassembly

```asm
0x100408bb0  mov     [rsp+arg_0], rbx
0x100408bb5  mov     [rsp+arg_8], rdi
0x100408bba  mov     [rsp+arg_10], r12
0x100408bbf  mov     [rsp+arg_18], r14
0x100408bc4  push    r15
0x100408bc6  sub     rsp, 60h
0x100408bca  mov     r14, r9
0x100408bcd  mov     r12d, r8d
0x100408bd0  mov     r15, rdx
0x100408bd3  mov     [rsp+68h+var_38], 0
0x100408bdb  test    rdx, rdx
0x100408bde  jnz     short loc_100408BED
0x100408be0  mov     [rsp+68h+var_38], 80070057h
0x100408be8  jmp     loc_100408CD8
0x100408bed  test    r14, r14
0x100408bf0  jnz     short loc_100408BFF
0x100408bf2  mov     [rsp+68h+var_38], 80070057h
0x100408bfa  jmp     loc_100408CD8
0x100408bff  mov     rdi, [rsp+68h+arg_28]
0x100408c07  test    rdi, rdi
0x100408c0a  jnz     short loc_100408C19
0x100408c0c  mov     [rsp+68h+var_38], 80070057h
0x100408c14  jmp     loc_100408CD8
0x100408c19  cmp     [rsp+68h+arg_38], 0
0x100408c22  jnz     short loc_100408C31
0x100408c24  mov     [rsp+68h+var_38], 80070057h
0x100408c2c  jmp     loc_100408CD8
0x100408c31  lea     rbx, [rcx-18h]
0x100408c35  mov     dl, 0FCh; unsigned __int8
0x100408c37  mov     rcx, rbx; this
0x100408c3a  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100408c3f  mov     r9d, r12d; int
0x100408c42  mov     r8, r15; wchar_t *
0x100408c45  xor     edx, edx; bool
0x100408c47  mov     rcx, rbx; this
0x100408c4a  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x100408c4f  mov     r15d, [rsp+68h+arg_30]
0x100408c57  test    r15d, r15d
0x100408c5a  jle     short loc_100408C79
0x100408c5c  lfence
0x100408c5f  mov     dl, 0FBh; unsigned __int8
0x100408c61  mov     rcx, rbx; this
0x100408c64  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100408c69  mov     r9d, r15d; int
0x100408c6c  mov     r8, rdi; wchar_t *
0x100408c6f  xor     edx, edx; bool
0x100408c71  mov     rcx, rbx; this
0x100408c74  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x100408c79  mov     edi, [rsp+68h+arg_20]
0x100408c80  test    edi, edi
0x100408c82  jle     short loc_100408CA1
0x100408c84  lfence
0x100408c87  mov     dl, 0FAh; unsigned __int8
0x100408c89  mov     rcx, rbx; this
0x100408c8c  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100408c91  mov     r9d, edi; int
0x100408c94  mov     r8, r14; wchar_t *
0x100408c97  xor     edx, edx; bool
0x100408c99  mov     rcx, rbx; this
0x100408c9c  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x100408ca1  mov     edi, [rsp+68h+arg_40]
0x100408ca8  test    edi, edi
0x100408caa  jle     short loc_100408CCE
0x100408cac  lfence
0x100408caf  mov     dl, 0F9h; unsigned __int8
0x100408cb1  mov     rcx, rbx; this
0x100408cb4  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100408cb9  mov     r9d, edi; int
0x100408cbc  mov     r8, [rsp+68h+arg_38]; wchar_t *
0x100408cc4  xor     edx, edx; bool
0x100408cc6  mov     rcx, rbx; this
0x100408cc9  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x100408cce  jmp     short loc_100408CD8
0x100408cd0  mov     eax, [rsp+68h+var_34]
0x100408cd4  mov     [rsp+68h+var_38], eax
0x100408cd8  mov     eax, [rsp+68h+var_38]
0x100408cdc  lea     r11, [rsp+68h+var_8]
0x100408ce1  mov     rbx, [r11+10h]
0x100408ce5  mov     rdi, [r11+18h]
0x100408ce9  mov     r12, [r11+20h]
0x100408ced  mov     r14, [r11+28h]
0x100408cf1  mov     rsp, r11
0x100408cf4  pop     r15
0x100408cf6  retn
0x1004247e0  push    rbp
0x1004247e2  sub     rsp, 30h
0x1004247e6  mov     rbp, rdx
0x1004247e9  mov     [rbp+50h], rcx
0x1004247ed  mov     [rbp+48h], rcx
0x1004247f1  mov     rax, [rbp+48h]
0x1004247f5  mov     rcx, [rax]
0x1004247f8  mov     [rbp+40h], rcx
0x1004247fc  mov     rax, [rbp+40h]
0x100424800  mov     eax, [rax]
0x100424802  cmp     eax, 0C0000005h
0x100424807  jz      short loc_100424839
0x100424809  add     eax, 1FFFFFFFh
0x10042480e  cmp     eax, 1
0x100424811  ja      short loc_100424829
0x100424813  mov     rax, [rbp+40h]
0x100424817  cmp     dword ptr [rax+18h], 1
0x10042481b  jnz     short loc_100424829
0x10042481d  mov     rax, [rbp+40h]
0x100424821  mov     ecx, [rax+20h]
0x100424824  mov     [rbp+34h], ecx
0x100424827  jmp     short loc_100424830
0x100424829  mov     dword ptr [rbp+34h], 8000FFFFh
0x100424830  mov     dword ptr [rbp+38h], 1
0x100424837  jmp     short loc_100424840
0x100424839  mov     dword ptr [rbp+38h], 0
0x100424840  mov     eax, [rbp+38h]
0x100424843  add     rsp, 30h
0x100424847  pop     rbp
0x100424848  retn
```
