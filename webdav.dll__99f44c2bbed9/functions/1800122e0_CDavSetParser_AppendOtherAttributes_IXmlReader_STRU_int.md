# CDavSetParser::AppendOtherAttributes(IXmlReader *,STRU *,int)

- ea: `0x1800122e0`
- end: `0x1800124ef`
- name: `?AppendOtherAttributes@CDavSetParser@@AEAAJPEAUIXmlReader@@PEAVSTRU@@H@Z`
- size: `527`
- prototype: `int(CDavSetParser *__hidden this, struct IXmlReader *, struct STRU *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012774`
- `0x180012a98`

## callees

- `0x1800122e0`
- `0x18001eb10`
- `0x1800224e6`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18001248b`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18001248b`
- `iisutil!SAFE_snwprintf` at `0x18001245d`
- `iisutil!SAFE_snwprintf` at `0x180012478`
- `iisutil!SAFE_snwprintf` at `0x18001245d`
- `iisutil!SAFE_snwprintf` at `0x180012478`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001232d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001232d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800124c8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800124c8`

## string_xrefs

- `0x18001236c`: `xmlns`
- `0x1800123e8`: `xmlns`

## pseudocode

```c
__int64 __fastcall CDavSetParser::AppendOtherAttributes(
        CDavSetParser *this,
        struct IXmlReader *a2,
        struct STRU *a3,
        int a4)
{
  int i; // eax
  int NamespaceAndName; // ebx
  __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  wchar_t *String1; // [rsp+30h] [rbp-49h] BYREF
  wchar_t *v15; // [rsp+38h] [rbp-41h] BYREF
  __int64 v16; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 *v17; // [rsp+48h] [rbp-31h] BYREF
  __int64 v18; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v19[56]; // [rsp+58h] [rbp-21h] BYREF

  String1 = 0;
  v17 = 0;
  v15 = 0;
  v16 = 0;
  v18 = 0;
  STRU::STRU((STRU *)v19);
  for ( i = ((__int64 (__fastcall *)(struct IXmlReader *))a2->lpVtbl->MoveToFirstAttribute)(a2);
        ;
        i = ((__int64 (__fastcall *)(struct IXmlReader *))a2->lpVtbl->MoveToNextAttribute)(a2) )
  {
    NamespaceAndName = i;
    if ( i < 0 )
      break;
    if ( i == 1 )
    {
      NamespaceAndName = 0;
      break;
    }
    NamespaceAndName = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, _QWORD))a2->lpVtbl->GetPrefix)(
                         a2,
                         &String1,
                         0);
    if ( NamespaceAndName < 0 )
      break;
    if ( wcscmp_0(String1, L"xmlns") && (!a4 || wcscmp_0(String1, L"xml")) )
    {
      NamespaceAndName = XmlGetNamespaceAndName(a2, (const unsigned __int16 **)&v17, (const unsigned __int16 **)&v15);
      if ( NamespaceAndName < 0 )
        break;
      NamespaceAndName = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))a2->lpVtbl->GetValue)(
                           a2,
                           &v16,
                           0);
      if ( NamespaceAndName < 0 )
        break;
      if ( *String1 || wcscmp_0(v15, L"xmlns") )
      {
        if ( v17 && *v17 )
        {
          NamespaceAndName = (*(__int64 (__fastcall **)(char *, unsigned __int16 *, __int64 *, __int64))(*((_QWORD *)this + 39) + 24LL))(
                               (char *)this + 312,
                               v17,
                               &v18,
                               1);
          if ( NamespaceAndName < 0 )
            break;
          v10 = v16;
          v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
          v12 = SAFE_snwprintf((struct STRU *)v19, L" %s:%s=\"%s\"", v11, v15, v10);
        }
        else
        {
          v12 = SAFE_snwprintf((struct STRU *)v19, L" %s=\"%s\"", v15, v16);
        }
        NamespaceAndName = v12;
        if ( v12 < 0 )
          break;
        NamespaceAndName = STRU::Append(a3, (const struct STRU *)v19);
        if ( NamespaceAndName < 0 )
          break;
      }
    }
  }
  ((void (__fastcall *)(struct IXmlReader *))a2->lpVtbl->MoveToElement)(a2);
  STRU::~STRU((STRU *)v19);
  return (unsigned int)NamespaceAndName;
}

```

## disassembly

```asm
0x1800122e0  push    rbp
0x1800122e2  push    rbx
0x1800122e3  push    rdi
0x1800122e4  push    r12
0x1800122e6  push    r13
0x1800122e8  push    r14
0x1800122ea  push    r15
0x1800122ec  lea     rbp, [rsp-27h]
0x1800122f1  sub     rsp, 0A0h
0x1800122f8  mov     rax, cs:__security_cookie
0x1800122ff  xor     rax, rsp
0x180012302  mov     [rbp+57h+var_40], rax
0x180012306  xor     r12d, r12d
0x180012309  mov     r13, rcx
0x18001230c  lea     rcx, [rbp+57h+var_78]
0x180012310  mov     [rbp+57h+String1], r12
0x180012314  mov     [rbp+57h+var_88], r12
0x180012318  mov     r14d, r9d
0x18001231b  mov     [rbp+57h+var_98], r12
0x18001231f  mov     r15, r8
0x180012322  mov     [rbp+57h+var_90], r12
0x180012326  mov     rdi, rdx
0x180012329  mov     [rbp+57h+var_80], r12
0x18001232d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012333  mov     rax, [rdi]
0x180012336  mov     rax, [rax+40h]
0x18001233a  jmp     loc_18001249E
0x18001233f  cmp     ebx, 1
0x180012342  jz      loc_1800124B2
0x180012348  mov     rax, [rdi]
0x18001234b  lea     rdx, [rbp+57h+String1]
0x18001234f  xor     r8d, r8d
0x180012352  mov     rcx, rdi
0x180012355  mov     rax, [rax+78h]
0x180012359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001235e  mov     ebx, eax
0x180012360  test    eax, eax
0x180012362  js      loc_1800124B5
0x180012368  mov     rcx, [rbp+57h+String1]; String1
0x18001236c  lea     rdx, aXmlns_1; "xmlns"
0x180012373  call    wcscmp_0
0x180012378  test    eax, eax
0x18001237a  jz      loc_180012497
0x180012380  test    r14d, r14d
0x180012383  jz      short loc_18001239D
0x180012385  mov     rcx, [rbp+57h+String1]; String1
0x180012389  lea     rdx, aXml; "xml"
0x180012390  call    wcscmp_0
0x180012395  test    eax, eax
0x180012397  jz      loc_180012497
0x18001239d  lea     r8, [rbp+57h+var_98]; unsigned __int16 **
0x1800123a1  mov     rcx, rdi; struct IXmlReader *
0x1800123a4  lea     rdx, [rbp+57h+var_88]; unsigned __int16 **
0x1800123a8  call    ?XmlGetNamespaceAndName@@YAJPEAUIXmlReader@@PEAPEBG1@Z; XmlGetNamespaceAndName(IXmlReader *,ushort const * *,ushort const * *)
0x1800123ad  mov     ebx, eax
0x1800123af  test    eax, eax
0x1800123b1  js      loc_1800124B5
0x1800123b7  mov     rax, [rdi]
0x1800123ba  lea     rdx, [rbp+57h+var_90]
0x1800123be  xor     r8d, r8d
0x1800123c1  mov     rcx, rdi
0x1800123c4  mov     rax, [rax+80h]
0x1800123cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123d0  mov     ebx, eax
0x1800123d2  test    eax, eax
0x1800123d4  js      loc_1800124B5
0x1800123da  mov     rax, [rbp+57h+String1]
0x1800123de  cmp     [rax], r12w
0x1800123e2  jnz     short loc_1800123FC
0x1800123e4  mov     rcx, [rbp+57h+var_98]; String1
0x1800123e8  lea     rdx, aXmlns_1; "xmlns"
0x1800123ef  call    wcscmp_0
0x1800123f4  test    eax, eax
0x1800123f6  jz      loc_180012497
0x1800123fc  mov     rdx, [rbp+57h+var_88]
0x180012400  test    rdx, rdx
0x180012403  jz      short loc_180012465
0x180012405  cmp     [rdx], r12w
0x180012409  jz      short loc_180012465
0x18001240b  lea     rcx, [r13+138h]
0x180012412  mov     r9d, 1
0x180012418  mov     rax, [rcx]
0x18001241b  lea     r8, [rbp+57h+var_80]
0x18001241f  mov     rax, [rax+18h]
0x180012423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012428  mov     ebx, eax
0x18001242a  test    eax, eax
0x18001242c  js      loc_1800124B5
0x180012432  mov     rcx, [rbp+57h+var_80]
0x180012436  mov     rbx, [rbp+57h+var_90]
0x18001243a  mov     rax, [rcx]
0x18001243d  mov     rax, [rax+8]
0x180012441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012446  mov     r9, [rbp+57h+var_98]
0x18001244a  lea     rdx, aSSS; " %s:%s=\"%s\""
0x180012451  mov     r8, rax
0x180012454  mov     [rsp+0D0h+var_B0], rbx
0x180012459  lea     rcx, [rbp+57h+var_78]
0x18001245d  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180012463  jmp     short loc_18001247E
0x180012465  mov     r9, [rbp+57h+var_90]
0x180012469  lea     rdx, aSS_1; " %s=\"%s\""
0x180012470  mov     r8, [rbp+57h+var_98]
0x180012474  lea     rcx, [rbp+57h+var_78]
0x180012478  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18001247e  mov     ebx, eax
0x180012480  test    eax, eax
0x180012482  js      short loc_1800124B5
0x180012484  lea     rdx, [rbp+57h+var_78]
0x180012488  mov     rcx, r15
0x18001248b  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180012491  mov     ebx, eax
0x180012493  test    eax, eax
0x180012495  js      short loc_1800124B5
0x180012497  mov     rax, [rdi]
0x18001249a  mov     rax, [rax+48h]
0x18001249e  mov     rcx, rdi
0x1800124a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124a6  mov     ebx, eax
0x1800124a8  test    eax, eax
0x1800124aa  jns     loc_18001233F
0x1800124b0  jmp     short loc_1800124B5
0x1800124b2  mov     ebx, r12d
0x1800124b5  mov     rax, [rdi]
0x1800124b8  mov     rcx, rdi
0x1800124bb  mov     rax, [rax+58h]
0x1800124bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124c4  lea     rcx, [rbp+57h+var_78]
0x1800124c8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800124ce  mov     eax, ebx
0x1800124d0  mov     rcx, [rbp+57h+var_40]
0x1800124d4  xor     rcx, rsp; StackCookie
0x1800124d7  call    __security_check_cookie
0x1800124dc  add     rsp, 0A0h
0x1800124e3  pop     r15
0x1800124e5  pop     r14
0x1800124e7  pop     r13
0x1800124e9  pop     r12
0x1800124eb  pop     rdi
0x1800124ec  pop     rbx
0x1800124ed  pop     rbp
0x1800124ee  retn
```
