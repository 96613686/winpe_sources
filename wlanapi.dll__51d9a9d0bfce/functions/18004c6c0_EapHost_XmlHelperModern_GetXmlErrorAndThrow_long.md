# EapHost::XmlHelperModern::GetXmlErrorAndThrow(long)

- ea: `0x18004c6c0`
- end: `0x18004c784`
- name: `?GetXmlErrorAndThrow@XmlHelperModern@EapHost@@YAXJ@Z`
- size: `196`
- prototype: `void __fastcall __noreturn(EapHost::XmlHelperModern *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004bce0`
- `0x18004cb34`
- `0x18004cea4`

## callees

- `0x18004c6c0`
- `0x18004cf90`
- `0x18004cfb0`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x18004c6fb`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18004c6fb`

## string_xrefs

- `0x18004c735`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004c772`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004c754`: `XML error: '%ls'`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall __noreturn EapHost::XmlHelperModern::GetXmlErrorAndThrow(EapHost::XmlHelperModern *this)
{
  unsigned int v1; // ebx
  HRESULT ErrorInfo; // eax
  struct IErrorInfoVtbl *lpVtbl; // rax
  int v4; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  char *v6; // [rsp+68h] [rbp+18h] BYREF
  IErrorInfo *pperrinfo; // [rsp+70h] [rbp+20h] BYREF

  v1 = (unsigned int)this;
  pperrinfo = 0;
  ErrorInfo = GetErrorInfo(0, &pperrinfo);
  if ( ErrorInfo >= 0 && ErrorInfo != 1 )
  {
    v6 = 0;
    lpVtbl = pperrinfo->lpVtbl;
    v6 = 0;
    if ( ((int (__fastcall *)(IErrorInfo *, char **))lpVtbl->GetDescription)(pperrinfo, &v6) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
        (const char *)v1,
        v4);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)v1,
      (int)"XML error: '%ls'",
      v6,
      &EapHost::EapMethodType::`vftable',
      0,
      0,
      0);
  }
  wil::details::in1diag3::Throw_Hr(
    retaddr,
    (void *)0x24,
    (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
    (const char *)v1,
    v4);
}

```

## disassembly

```asm
0x18004c6c0  mov     [rsp-8+arg_0], rbx
0x18004c6c5  push    rbp
0x18004c6c6  mov     rbp, rsp
0x18004c6c9  sub     rsp, 50h
0x18004c6cd  mov     ebx, ecx
0x18004c6cf  mov     [rbp+pperrinfo], 0
0x18004c6d7  mov     [rbp+var_18], 0
0x18004c6db  mov     [rbp+var_14], 0
0x18004c6e3  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18004c6ea  mov     [rbp+var_20], rax
0x18004c6ee  mov     [rbp+var_8], 0
0x18004c6f5  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18004c6f9  xor     ecx, ecx; dwReserved
0x18004c6fb  call    cs:__imp_GetErrorInfo
0x18004c701  test    eax, eax
0x18004c703  js      short loc_18004C76B
0x18004c705  cmp     eax, 1
0x18004c708  jz      short loc_18004C76B
0x18004c70a  mov     [rbp+arg_8], 0
0x18004c712  mov     rcx, [rbp+pperrinfo]
0x18004c716  mov     rax, [rcx]
0x18004c719  mov     [rbp+arg_8], 0
0x18004c721  lea     rdx, [rbp+arg_8]
0x18004c725  mov     rax, [rax+28h]
0x18004c729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c72e  mov     rcx, [rbp+8]; this
0x18004c732  mov     r9d, ebx; char *
0x18004c735  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004c73c  test    eax, eax
0x18004c73e  jns     short loc_18004C74B
0x18004c740  mov     edx, 2Ch ; ','; void *
0x18004c745  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c74b  mov     rax, [rbp+arg_8]
0x18004c74f  mov     [rsp+50h+var_28], rax; char *
0x18004c754  lea     rax, aXmlErrorLs; "XML error: '%ls'"
0x18004c75b  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004c760  mov     edx, 2Fh ; '/'; void *
0x18004c765  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c76b  mov     rcx, [rbp+8]; this
0x18004c76f  mov     r9d, ebx; char *
0x18004c772  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004c779  mov     edx, 24h ; '$'; void *
0x18004c77e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
