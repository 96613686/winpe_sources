# SXReader::putProperty(wchar_t const *,tagVARIANT)

- ea: `0x100404b80`
- end: `0x100404e05`
- name: `?putProperty@SXReader@@UEAAJPEB_WUtagVARIANT@@@Z`
- size: `645`
- prototype: `int(SXReader *__hidden this, const wchar_t *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x100404b80`
- `0x10040a5c0`
- `0x1004112e0`
- `0x100413780`
- `0x100423c70`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXReader::putProperty(SXReader *this, const wchar_t *a2, struct tagVARIANT *a3)
{
  unsigned int v6; // edi
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  struct IStream *v11; // rbx

  v6 = 0;
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
    v8 = *((_QWORD *)this + 3);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 3) = 0;
    }
    *((_QWORD *)this + 3) = Variant::QIForIID(a3, &IID_IMXRContentHandler);
  }
  else if ( (_DWORD)v7 == dword_100434C48 && !memcmp(a2, CodeStringPtr::sxcontentHandler, 2LL * (unsigned int)v7) )
  {
    v9 = *((_QWORD *)this + 5);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 5) = 0;
    }
    *((_QWORD *)this + 5) = Variant::QIForIID(a3, &IID_ISXFormatContentHandler);
  }
  else if ( (_DWORD)v7 == dword_100434BE8 && !memcmp(a2, CodeStringPtr::lexicalHandler, 2LL * (unsigned int)v7) )
  {
    v10 = *((_QWORD *)this + 4);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 4) = 0;
    }
    *((_QWORD *)this + 4) = Variant::QIForIID(a3, &IID_ISAXLexicalHandler);
  }
  else if ( (_DWORD)v7 == dword_100434C58 && !memcmp(a2, CodeStringPtr::sxInput, 2LL * (unsigned int)v7) )
  {
    v11 = (struct IStream *)Variant::QIForIID(a3, &IID_ISequentialStream);
    SXReadBase::SetStream((SXReader *)((char *)this - 1456), v11);
    if ( v11 )
      ((void (__fastcall *)(struct IStream *))v11->lpVtbl->Release)(v11);
  }
  else if ( (_DWORD)v7 == dword_100434BF8 && !memcmp(a2, CodeStringPtr::xmlDeclVersion, 2LL * (unsigned int)v7)
         || (_DWORD)v7 == dword_100434C18 && !memcmp(a2, CodeStringPtr::xmlDeclEncoding, 2LL * (unsigned int)v7)
         || (_DWORD)v7 == dword_100434C28 && !memcmp(a2, CodeStringPtr::xmlDeclStandalone, 2LL * (unsigned int)v7) )
  {
    return (unsigned int)-2147467259;
  }
  else if ( (_DWORD)v7 == dword_100434C38 && !memcmp(a2, CodeStringPtr::maxTokenSize, 2LL * (unsigned int)v7) )
  {
    if ( a3->vt == 19 )
      *((_DWORD *)this - 190) = a3->lVal;
    else
      return (unsigned int)-2147024809;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x100404b80  mov     rax, rsp
0x100404b83  mov     [rax+8], rbx
0x100404b87  mov     [rax+10h], rsi
0x100404b8b  mov     [rax+18h], rdi
0x100404b8f  push    r12
0x100404b91  push    r14
0x100404b93  push    r15
0x100404b95  sub     rsp, 60h
0x100404b99  mov     r15, r8
0x100404b9c  mov     rsi, rdx
0x100404b9f  mov     r14, rcx
0x100404ba2  xor     edi, edi
0x100404ba4  mov     [rax-58h], edi
0x100404ba7  mov     [rax-30h], rdi
0x100404bab  mov     [rax-28h], edi
0x100404bae  mov     [rax-30h], rdx
0x100404bb2  test    rdx, rdx
0x100404bb5  jz      short loc_100404BCC
0x100404bb7  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100404bbe  xchg    ax, ax
0x100404bc0  inc     rbx
0x100404bc3  cmp     word ptr [rdx+rbx*2], 0
0x100404bc8  jnz     short loc_100404BC0
0x100404bca  jmp     short loc_100404BCF
0x100404bcc  mov     rbx, rdi
0x100404bcf  mov     [rsp+78h+var_28], ebx
0x100404bd3  mov     r12d, ebx
0x100404bd6  cmp     ebx, cs:dword_100434BD8
0x100404bdc  jnz     short loc_100404C27
0x100404bde  lea     r8, [r12+r12]; Size
0x100404be2  mov     rdx, cs:?contentHandler@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404be9  mov     rcx, rsi; Buf1
0x100404bec  call    memcmp
0x100404bf1  test    eax, eax
0x100404bf3  jnz     short loc_100404C27
0x100404bf5  mov     rcx, [r14+18h]
0x100404bf9  test    rcx, rcx
0x100404bfc  jz      short loc_100404C0F
0x100404bfe  mov     rax, [rcx]
0x100404c01  mov     rax, [rax+10h]
0x100404c05  call    cs:__guard_dispatch_icall_fptr
0x100404c0b  mov     [r14+18h], rdi
0x100404c0f  lea     rdx, IID_IMXRContentHandler; struct _GUID *
0x100404c16  mov     rcx, r15; struct tagVARIANT *
0x100404c19  call    ?QIForIID@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@PEBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100404c1e  mov     [r14+18h], rax
0x100404c22  jmp     loc_100404DDE
0x100404c27  cmp     ebx, cs:dword_100434C48
0x100404c2d  jnz     short loc_100404C78
0x100404c2f  lea     r8, [r12+r12]; Size
0x100404c33  mov     rdx, cs:?sxcontentHandler@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404c3a  mov     rcx, rsi; Buf1
0x100404c3d  call    memcmp
0x100404c42  test    eax, eax
0x100404c44  jnz     short loc_100404C78
0x100404c46  mov     rcx, [r14+28h]
0x100404c4a  test    rcx, rcx
0x100404c4d  jz      short loc_100404C60
0x100404c4f  mov     rax, [rcx]
0x100404c52  mov     rax, [rax+10h]
0x100404c56  call    cs:__guard_dispatch_icall_fptr
0x100404c5c  mov     [r14+28h], rdi
0x100404c60  lea     rdx, IID_ISXFormatContentHandler; struct _GUID *
0x100404c67  mov     rcx, r15; struct tagVARIANT *
0x100404c6a  call    ?QIForIID@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@PEBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100404c6f  mov     [r14+28h], rax
0x100404c73  jmp     loc_100404DDE
0x100404c78  cmp     ebx, cs:dword_100434BE8
0x100404c7e  jnz     short loc_100404CCB
0x100404c80  mov     r8d, ebx
0x100404c83  add     r8, r8; Size
0x100404c86  mov     rdx, cs:?lexicalHandler@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404c8d  mov     rcx, rsi; Buf1
0x100404c90  call    memcmp
0x100404c95  test    eax, eax
0x100404c97  jnz     short loc_100404CCB
0x100404c99  mov     rcx, [r14+20h]
0x100404c9d  test    rcx, rcx
0x100404ca0  jz      short loc_100404CB3
0x100404ca2  mov     rax, [rcx]
0x100404ca5  mov     rax, [rax+10h]
0x100404ca9  call    cs:__guard_dispatch_icall_fptr
0x100404caf  mov     [r14+20h], rdi
0x100404cb3  lea     rdx, IID_ISAXLexicalHandler; struct _GUID *
0x100404cba  mov     rcx, r15; struct tagVARIANT *
0x100404cbd  call    ?QIForIID@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@PEBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100404cc2  mov     [r14+20h], rax
0x100404cc6  jmp     loc_100404DDE
0x100404ccb  cmp     ebx, cs:dword_100434C58
0x100404cd1  jnz     short loc_100404D2B
0x100404cd3  mov     r8d, ebx
0x100404cd6  add     r8, r8; Size
0x100404cd9  mov     rdx, cs:?sxInput@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404ce0  mov     rcx, rsi; Buf1
0x100404ce3  call    memcmp
0x100404ce8  test    eax, eax
0x100404cea  jnz     short loc_100404D2B
0x100404cec  lea     rdx, IID_ISequentialStream; struct _GUID *
0x100404cf3  mov     rcx, r15; struct tagVARIANT *
0x100404cf6  call    ?QIForIID@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@PEBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100404cfb  mov     rbx, rax
0x100404cfe  lea     rcx, [r14-5B0h]; this
0x100404d05  mov     rdx, rax; struct IStream *
0x100404d08  call    ?SetStream@SXReadBase@@IEAAXPEAUIStream@@@Z; SXReadBase::SetStream(IStream *)
0x100404d0d  test    rbx, rbx
0x100404d10  jz      loc_100404DDE
0x100404d16  mov     rcx, [rbx]
0x100404d19  mov     rax, [rcx+10h]
0x100404d1d  mov     rcx, rbx
0x100404d20  call    cs:__guard_dispatch_icall_fptr
0x100404d26  jmp     loc_100404DDE
0x100404d2b  cmp     ebx, cs:dword_100434BF8
0x100404d31  jnz     short loc_100404D4C
0x100404d33  mov     r8d, ebx
0x100404d36  add     r8, r8; Size
0x100404d39  mov     rdx, cs:?xmlDeclVersion@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404d40  mov     rcx, rsi; Buf1
0x100404d43  call    memcmp
0x100404d48  test    eax, eax
0x100404d4a  jz      short loc_100404D8E
0x100404d4c  cmp     ebx, cs:dword_100434C18
0x100404d52  jnz     short loc_100404D6D
0x100404d54  mov     r8d, ebx
0x100404d57  add     r8, r8; Size
0x100404d5a  mov     rdx, cs:?xmlDeclEncoding@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404d61  mov     rcx, rsi; Buf1
0x100404d64  call    memcmp
0x100404d69  test    eax, eax
0x100404d6b  jz      short loc_100404D8E
0x100404d6d  cmp     ebx, cs:dword_100434C28
0x100404d73  jnz     short loc_100404D95
0x100404d75  mov     r8d, ebx
0x100404d78  add     r8, r8; Size
0x100404d7b  mov     rdx, cs:?xmlDeclStandalone@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404d82  mov     rcx, rsi; Buf1
0x100404d85  call    memcmp
0x100404d8a  test    eax, eax
0x100404d8c  jnz     short loc_100404D95
0x100404d8e  mov     edi, 80004005h
0x100404d93  jmp     short loc_100404DDA
0x100404d95  cmp     ebx, cs:dword_100434C38
0x100404d9b  jnz     short loc_100404DD5
0x100404d9d  mov     r8d, ebx
0x100404da0  add     r8, r8; Size
0x100404da3  mov     rdx, cs:?maxTokenSize@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404daa  mov     rcx, rsi; Buf1
0x100404dad  call    memcmp
0x100404db2  test    eax, eax
0x100404db4  jnz     short loc_100404DD5
0x100404db6  cmp     word ptr [r15], 13h
0x100404dbb  jz      short loc_100404DC8
0x100404dbd  mov     edi, 80070057h
0x100404dc2  mov     [rsp+78h+var_58], edi
0x100404dc6  jmp     short loc_100404DE8
0x100404dc8  mov     eax, [r15+8]
0x100404dcc  mov     [r14-2F8h], eax
0x100404dd3  jmp     short loc_100404DDE
0x100404dd5  mov     edi, 80070057h
0x100404dda  mov     [rsp+78h+var_58], edi
0x100404dde  jmp     short loc_100404DE8
0x100404de0  mov     edi, [rsp+78h+var_54]
0x100404de4  mov     [rsp+78h+var_58], edi
0x100404de8  mov     eax, edi
0x100404dea  lea     r11, [rsp+78h+var_18]
0x100404def  mov     rbx, [r11+20h]
0x100404df3  mov     rsi, [r11+28h]
0x100404df7  mov     rdi, [r11+30h]
0x100404dfb  mov     rsp, r11
0x100404dfe  pop     r15
0x100404e00  pop     r14
0x100404e02  pop     r12
0x100404e04  retn
0x100424690  push    rbp
0x100424692  sub     rsp, 20h
0x100424696  mov     rbp, rdx
0x100424699  mov     [rbp+40h], rcx
0x10042469d  mov     [rbp+38h], rcx
0x1004246a1  mov     rax, [rbp+38h]
0x1004246a5  mov     rcx, [rax]
0x1004246a8  mov     [rbp+30h], rcx
0x1004246ac  mov     rax, [rbp+30h]
0x1004246b0  mov     eax, [rax]
0x1004246b2  cmp     eax, 0C0000005h
0x1004246b7  jz      short loc_1004246E9
0x1004246b9  add     eax, 1FFFFFFFh
0x1004246be  cmp     eax, 1
0x1004246c1  ja      short loc_1004246D9
0x1004246c3  mov     rax, [rbp+30h]
0x1004246c7  cmp     dword ptr [rax+18h], 1
0x1004246cb  jnz     short loc_1004246D9
0x1004246cd  mov     rax, [rbp+30h]
0x1004246d1  mov     ecx, [rax+20h]
0x1004246d4  mov     [rbp+24h], ecx
0x1004246d7  jmp     short loc_1004246E0
0x1004246d9  mov     dword ptr [rbp+24h], 8000FFFFh
0x1004246e0  mov     dword ptr [rbp+28h], 1
0x1004246e7  jmp     short loc_1004246F0
0x1004246e9  mov     dword ptr [rbp+28h], 0
0x1004246f0  mov     eax, [rbp+28h]
0x1004246f3  add     rsp, 20h
0x1004246f7  pop     rbp
0x1004246f8  retn
```
