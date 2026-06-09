# SXReader::getProperty(wchar_t const *,tagVARIANT *)

- ea: `0x1004048f0`
- end: `0x100404b79`
- name: `?getProperty@SXReader@@UEAAJPEB_WPEAUtagVARIANT@@@Z`
- size: `649`
- prototype: `int(SXReader *__hidden this, const wchar_t *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1004048f0`
- `0x100423c70`
- `0x100424580`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x100404a3e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x100404a3e`

## pseudocode

```c
__int64 __fastcall SXReader::getProperty(SXReader *this, const wchar_t *a2, struct tagVARIANT *a3)
{
  unsigned int v3; // ebp
  __int64 v7; // rbx
  LONGLONG v8; // rcx
  size_t v9; // r15
  __int64 v10; // rcx
  unsigned int v11; // eax
  UINT v12; // edx
  const OLECHAR *v13; // rcx
  BSTR v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax

  v3 = 0;
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  if ( (_DWORD)v7 == dword_100434BD8 && !memcmp(a2, CodeStringPtr::contentHandler, 2LL * (unsigned int)v7) )
  {
    a3->vt = 13;
    v8 = *((_QWORD *)this + 3);
    if ( v8 )
    {
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v8 + 8LL))(v8);
      v8 = *((_QWORD *)this + 3);
    }
    a3->llVal = v8;
    return v3;
  }
  v9 = 2LL * (unsigned int)v7;
  if ( (_DWORD)v7 == dword_100434BE8 && !memcmp(a2, CodeStringPtr::lexicalHandler, v9) )
  {
    a3->vt = 13;
    v10 = *((_QWORD *)this + 4);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      a3->llVal = *((_QWORD *)this + 4);
    }
    else
    {
      a3->llVal = 0;
    }
    return v3;
  }
  if ( (_DWORD)v7 == dword_100434BF8 && !memcmp(a2, CodeStringPtr::xmlDeclVersion, v9) )
  {
    a3->vt = 8;
    v11 = *((_DWORD *)this - 210);
    if ( v11 == dword_100434C08 && !memcmp(*((const void **)this - 106), CodeStringPtr::empty, 2LL * v11) )
      goto LABEL_20;
    v12 = *((_DWORD *)this - 210);
    v13 = (const OLECHAR *)*((_QWORD *)this - 106);
  }
  else if ( (_DWORD)v7 == dword_100434C18 && !memcmp(a2, CodeStringPtr::xmlDeclEncoding, v9) )
  {
    a3->vt = 8;
    v15 = *((_DWORD *)this - 206);
    if ( v15 == dword_100434C08 && !memcmp(*((const void **)this - 104), CodeStringPtr::empty, 2LL * v15) )
      goto LABEL_20;
    v12 = *((_DWORD *)this - 206);
    v13 = (const OLECHAR *)*((_QWORD *)this - 104);
  }
  else
  {
    if ( (_DWORD)v7 != dword_100434C28 || memcmp(a2, CodeStringPtr::xmlDeclStandalone, v9) )
    {
      if ( (_DWORD)v7 == dword_100434C38 && !memcmp(a2, CodeStringPtr::maxTokenSize, v9) )
      {
        a3->vt = 19;
        a3->lVal = *((_DWORD *)this - 190);
      }
      else
      {
        return (unsigned int)-2147024809;
      }
      return v3;
    }
    a3->vt = 8;
    v16 = *((_DWORD *)this - 202);
    if ( v16 == dword_100434C08 && !memcmp(*((const void **)this - 102), CodeStringPtr::empty, 2LL * v16) )
    {
LABEL_20:
      a3->llVal = 0;
      return v3;
    }
    v12 = *((_DWORD *)this - 202);
    v13 = (const OLECHAR *)*((_QWORD *)this - 102);
  }
  v14 = SysAllocStringLen(v13, v12);
  a3->llVal = (LONGLONG)v14;
  if ( !v14 )
    return (unsigned int)-2147024882;
  return v3;
}

```

## disassembly

```asm
0x1004048f0  mov     [rsp+arg_8], rbx
0x1004048f5  mov     [rsp+arg_10], rbp
0x1004048fa  push    rsi
0x1004048fb  push    rdi
0x1004048fc  push    r14
0x1004048fe  sub     rsp, 20h
0x100404902  xor     ebp, ebp
0x100404904  mov     rdi, r8
0x100404907  mov     r14, rdx
0x10040490a  mov     rsi, rcx
0x10040490d  test    rdx, rdx
0x100404910  jz      short loc_10040492B
0x100404912  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100404919  nop     dword ptr [rax+00000000h]
0x100404920  inc     rbx
0x100404923  cmp     [rdx+rbx*2], bp
0x100404927  jnz     short loc_100404920
0x100404929  jmp     short loc_10040492D
0x10040492b  mov     ebx, ebp
0x10040492d  cmp     ebx, cs:dword_100434BD8
0x100404933  mov     [rsp+38h+arg_0], r15
0x100404938  mov     r15d, ebx
0x10040493b  jnz     short loc_10040497F
0x10040493d  mov     rdx, cs:?contentHandler@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404944  lea     r8, [r15+r15]; Size
0x100404948  mov     rcx, r14; Buf1
0x10040494b  call    memcmp
0x100404950  test    eax, eax
0x100404952  jnz     short loc_10040497F
0x100404954  mov     eax, 0Dh
0x100404959  mov     [rdi], ax
0x10040495c  mov     rcx, [rsi+18h]
0x100404960  test    rcx, rcx
0x100404963  jz      short loc_100404976
0x100404965  mov     rax, [rcx]
0x100404968  mov     rax, [rax+8]
0x10040496c  call    cs:__guard_dispatch_icall_fptr
0x100404972  mov     rcx, [rsi+18h]
0x100404976  mov     [rdi+8], rcx
0x10040497a  jmp     loc_100404B5F
0x10040497f  add     r15, r15
0x100404982  cmp     ebx, cs:dword_100434BE8
0x100404988  jnz     short loc_1004049D7
0x10040498a  mov     rdx, cs:?lexicalHandler@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404991  mov     r8, r15; Size
0x100404994  mov     rcx, r14; Buf1
0x100404997  call    memcmp
0x10040499c  test    eax, eax
0x10040499e  jnz     short loc_1004049D7
0x1004049a0  mov     eax, 0Dh
0x1004049a5  mov     [rdi], ax
0x1004049a8  mov     rcx, [rsi+20h]
0x1004049ac  test    rcx, rcx
0x1004049af  jnz     short loc_1004049BD
0x1004049b1  mov     rax, rbp
0x1004049b4  mov     [rdi+8], rax
0x1004049b8  jmp     loc_100404B5F
0x1004049bd  mov     rax, [rcx]
0x1004049c0  mov     rax, [rax+8]
0x1004049c4  call    cs:__guard_dispatch_icall_fptr
0x1004049ca  mov     rax, [rsi+20h]
0x1004049ce  mov     [rdi+8], rax
0x1004049d2  jmp     loc_100404B5F
0x1004049d7  cmp     ebx, cs:dword_100434BF8
0x1004049dd  jnz     short loc_100404A5B
0x1004049df  mov     rdx, cs:?xmlDeclVersion@CodeStringPtr@@2UStringPtr@@A; Buf2
0x1004049e6  mov     r8, r15; Size
0x1004049e9  mov     rcx, r14; Buf1
0x1004049ec  call    memcmp
0x1004049f1  test    eax, eax
0x1004049f3  jnz     short loc_100404A5B
0x1004049f5  mov     eax, 8
0x1004049fa  mov     [rdi], ax
0x1004049fd  mov     eax, [rsi-348h]
0x100404a03  cmp     eax, cs:dword_100434C08
0x100404a09  jnz     short loc_100404A31
0x100404a0b  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404a12  mov     r8d, eax
0x100404a15  mov     rcx, [rsi-350h]; Buf1
0x100404a1c  add     r8, r8; Size
0x100404a1f  call    memcmp
0x100404a24  test    eax, eax
0x100404a26  jnz     short loc_100404A31
0x100404a28  mov     [rdi+8], rbp
0x100404a2c  jmp     loc_100404B5F
0x100404a31  mov     edx, [rsi-348h]; ui
0x100404a37  mov     rcx, [rsi-350h]; strIn
0x100404a3e  call    cs:__imp_SysAllocStringLen
0x100404a44  mov     [rdi+8], rax
0x100404a48  test    rax, rax
0x100404a4b  jnz     loc_100404B5F
0x100404a51  mov     ebp, 8007000Eh
0x100404a56  jmp     loc_100404B5F
0x100404a5b  cmp     ebx, cs:dword_100434C18
0x100404a61  jnz     short loc_100404AC2
0x100404a63  mov     rdx, cs:?xmlDeclEncoding@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404a6a  mov     r8, r15; Size
0x100404a6d  mov     rcx, r14; Buf1
0x100404a70  call    memcmp
0x100404a75  test    eax, eax
0x100404a77  jnz     short loc_100404AC2
0x100404a79  mov     eax, 8
0x100404a7e  mov     [rdi], ax
0x100404a81  mov     eax, [rsi-338h]
0x100404a87  cmp     eax, cs:dword_100434C08
0x100404a8d  jnz     short loc_100404AB0
0x100404a8f  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404a96  mov     r8d, eax
0x100404a99  mov     rcx, [rsi-340h]; Buf1
0x100404aa0  add     r8, r8; Size
0x100404aa3  call    memcmp
0x100404aa8  test    eax, eax
0x100404aaa  jz      loc_100404A28
0x100404ab0  mov     edx, [rsi-338h]
0x100404ab6  mov     rcx, [rsi-340h]
0x100404abd  jmp     loc_100404A3E
0x100404ac2  cmp     ebx, cs:dword_100434C28
0x100404ac8  jnz     short loc_100404B29
0x100404aca  mov     rdx, cs:?xmlDeclStandalone@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404ad1  mov     r8, r15; Size
0x100404ad4  mov     rcx, r14; Buf1
0x100404ad7  call    memcmp
0x100404adc  test    eax, eax
0x100404ade  jnz     short loc_100404B29
0x100404ae0  mov     eax, 8
0x100404ae5  mov     [rdi], ax
0x100404ae8  mov     eax, [rsi-328h]
0x100404aee  cmp     eax, cs:dword_100434C08
0x100404af4  jnz     short loc_100404B17
0x100404af6  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404afd  mov     r8d, eax
0x100404b00  mov     rcx, [rsi-330h]; Buf1
0x100404b07  add     r8, r8; Size
0x100404b0a  call    memcmp
0x100404b0f  test    eax, eax
0x100404b11  jz      loc_100404A28
0x100404b17  mov     edx, [rsi-328h]
0x100404b1d  mov     rcx, [rsi-330h]
0x100404b24  jmp     loc_100404A3E
0x100404b29  cmp     ebx, cs:dword_100434C38
0x100404b2f  jnz     short loc_100404B5A
0x100404b31  mov     rdx, cs:?maxTokenSize@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404b38  mov     r8, r15; Size
0x100404b3b  mov     rcx, r14; Buf1
0x100404b3e  call    memcmp
0x100404b43  test    eax, eax
0x100404b45  jnz     short loc_100404B5A
0x100404b47  mov     eax, 13h
0x100404b4c  mov     [rdi], ax
0x100404b4f  mov     eax, [rsi-2F8h]
0x100404b55  mov     [rdi+8], eax
0x100404b58  jmp     short loc_100404B5F
0x100404b5a  mov     ebp, 80070057h
0x100404b5f  mov     r15, [rsp+38h+arg_0]
0x100404b64  mov     eax, ebp
0x100404b66  mov     rbp, [rsp+38h+arg_10]
0x100404b6b  mov     rbx, [rsp+38h+arg_8]
0x100404b70  add     rsp, 20h
0x100404b74  pop     r14
0x100404b76  pop     rdi
0x100404b77  pop     rsi
0x100404b78  retn
```
