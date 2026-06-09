# UnionFs::UfsPathName::MakeShortNameCopy(_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x1400449c0`
- end: `0x140044ba3`
- name: `?MakeShortNameCopy@UfsPathName@UnionFs@@QEBAJAEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400480c4`

## callees

- `0x140043a88`
- `0x1400449c0`
- `0x140056afc`
- `0x14006a3cc`
- `0x14006a7d0`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044a04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044b31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044b73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044a04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044b31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044b73`

## string_xrefs

- `0x140044a3a`: `PUSH: Converting to short name path`
- `0x140044a4b`: `UnionFs::UfsPathName::MakeShortNameCopy`
- `0x140044aa0`: `UnionFs::UfsPathName::MakeShortNameCopy`
- `0x140044af8`: `UnionFs::UfsPathName::MakeShortNameCopy`
- `0x140044a8f`: `PUSH: Combining short name path`
- `0x140044ae7`: `PUSH: Creating short name path`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathName::MakeShortNameCopy(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        PVOID *a3,
        struct _UNICODE_STRING *a4)
{
  struct _UNICODE_STRING *v4; // rbx
  int v9; // ebx
  struct _UNICODE_STRING *v10; // rdx
  struct _UNICODE_STRING *v11; // r14
  struct _UNICODE_STRING *v12; // rdx
  struct _UNICODE_STRING *Length; // rdx
  struct _UNICODE_STRING *v14; // rdx
  int v15; // r14d
  struct _UNICODE_STRING *v16; // rdx
  struct _UNICODE_STRING *v17; // rbx
  struct _UNICODE_STRING *v18; // rbx
  const char *v20; // [rsp+28h] [rbp-40h]
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-38h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-18h] BYREF
  PVOID P; // [rsp+B0h] [rbp+48h] BYREF

  v4 = (struct _UNICODE_STRING *)*a3;
  *a3 = 0;
  if ( v4 )
  {
    if ( !LOBYTE(v4[1].Length) )
      *v4 = 0;
    FsFltWil::Details::FreeUnicodeString(v4, a2);
    ExFreePoolWithTag(v4, 0);
  }
  SourceString = *(UNICODE_STRING *)(a1 + 40);
  Source = 0;
  v9 = UnionFs::Utils::ConvertPathToShortNamePath((PFLT_INSTANCE)a2, &SourceString, &Source, (__int64)a4);
  if ( v9 >= 0 )
  {
    v11 = (struct _UNICODE_STRING *)(a1 + 24);
    UnicodeString = 0;
    v9 = UnionFs::Utils::CombinePath(v11, &Source, &UnicodeString, a4, v11);
    if ( v9 >= 0 )
    {
      Length = (struct _UNICODE_STRING *)v11->Length;
      P = 0;
      v15 = UnionFs::UfsPathName::AllocAndInit(&UnicodeString, Length, (__int64 *)&P, (__int64)a4);
      if ( v15 >= 0 )
      {
        v18 = (struct _UNICODE_STRING *)*a3;
        *a3 = P;
        if ( v18 )
        {
          if ( !LOBYTE(v18[1].Length) )
            *v18 = 0;
          FsFltWil::Details::FreeUnicodeString(v18, v14);
          ExFreePoolWithTag(v18, 0);
        }
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v14);
        v9 = 0;
      }
      else
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v15,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x5D300130158LL,
          (unsigned __int64)"UnionFs::UfsPathName::MakeShortNameCopy",
          "PUSH: Creating short name path",
          v20);
        v17 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v17, v16);
          ExFreePoolWithTag(v17, 0);
        }
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v16);
        v9 = v15;
      }
    }
    else
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v9,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x5BB00130151LL,
        (unsigned __int64)"UnionFs::UfsPathName::MakeShortNameCopy",
        "PUSH: Combining short name path",
        v20);
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v12);
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v9,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x5B800130147LL,
      (unsigned __int64)"UnionFs::UfsPathName::MakeShortNameCopy",
      "PUSH: Converting to short name path",
      v20);
  }
  FsFltWil::Details::FreeUnicodeString(&Source, v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400449c0  push    rbp
0x1400449c2  push    rbx
0x1400449c3  push    rsi
0x1400449c4  push    rdi
0x1400449c5  push    r14
0x1400449c7  push    r15
0x1400449c9  mov     rbp, rsp
0x1400449cc  sub     rsp, 68h
0x1400449d0  mov     rbx, [r8]
0x1400449d3  mov     rdi, r9
0x1400449d6  mov     qword ptr [r8], 0
0x1400449dd  mov     rsi, r8
0x1400449e0  mov     r15, rdx
0x1400449e3  mov     r14, rcx
0x1400449e6  test    rbx, rbx
0x1400449e9  jz      short loc_140044A10
0x1400449eb  cmp     byte ptr [rbx+10h], 0
0x1400449ef  jnz     short loc_1400449F7
0x1400449f1  xorps   xmm0, xmm0
0x1400449f4  movups  xmmword ptr [rbx], xmm0
0x1400449f7  mov     rcx, rbx; UnicodeString
0x1400449fa  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400449ff  xor     edx, edx; Tag
0x140044a01  mov     rcx, rbx; P
0x140044a04  call    cs:__imp_ExFreePoolWithTag
0x140044a0b  nop     dword ptr [rax+rax+00h]
0x140044a10  movups  xmm1, xmmword ptr [r14+28h]
0x140044a15  lea     r8, [rbp+Source]; UnicodeString
0x140044a19  mov     r9, rdi; int
0x140044a1c  xorps   xmm0, xmm0
0x140044a1f  lea     rdx, [rbp+SourceString]; SourceString
0x140044a23  mov     rcx, r15; Instance
0x140044a26  movdqu  xmmword ptr [rbp+SourceString.Length], xmm1
0x140044a2b  movups  xmmword ptr [rbp+Source.Length], xmm0
0x140044a2f  call    ?ConvertPathToShortNamePath@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ConvertPathToShortNamePath(_FLT_INSTANCE const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x140044a34  mov     ebx, eax
0x140044a36  test    eax, eax
0x140044a38  jns     short loc_140044A66
0x140044a3a  lea     rax, aPushConverting_4; "PUSH: Converting to short name path"
0x140044a41  mov     r8, 5B800130147h; struct UnionFs::StackEventTracer *
0x140044a4b  lea     r9, aUnionfsUfspath_26; "UnionFs::UfsPathName::MakeShortNameCopy"
0x140044a52  mov     [rsp+68h+var_48], rax; char *
0x140044a57  mov     rdx, rdi; int
0x140044a5a  mov     ecx, ebx; this
0x140044a5c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044a61  jmp     loc_140044B8A
0x140044a66  add     r14, 18h
0x140044a6a  lea     r8, [rbp+UnicodeString]; UnicodeString
0x140044a6e  xorps   xmm0, xmm0
0x140044a71  mov     [rsp+68h+var_48], r14; struct _UNICODE_STRING *
0x140044a76  mov     rcx, r14; SourceString
0x140044a79  lea     rdx, [rbp+Source]; Source
0x140044a7d  mov     r9, rdi; struct _UNICODE_STRING *
0x140044a80  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x140044a84  call    ?CombinePath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEBG@Z; UnionFs::Utils::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort const *)
0x140044a89  mov     ebx, eax
0x140044a8b  test    eax, eax
0x140044a8d  jns     short loc_140044AC4
0x140044a8f  lea     rax, aPushCombiningS_0; "PUSH: Combining short name path"
0x140044a96  mov     r8, 5BB00130151h; struct UnionFs::StackEventTracer *
0x140044aa0  lea     r9, aUnionfsUfspath_26; "UnionFs::UfsPathName::MakeShortNameCopy"
0x140044aa7  mov     [rsp+68h+var_48], rax; char *
0x140044aac  mov     rdx, rdi; int
0x140044aaf  mov     ecx, ebx; this
0x140044ab1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044ab6  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x140044aba  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044abf  jmp     loc_140044B8A
0x140044ac4  movzx   edx, word ptr [r14]
0x140044ac8  lea     r8, [rbp+P]
0x140044acc  mov     r9, rdi
0x140044acf  mov     [rbp+P], 0
0x140044ad7  lea     rcx, [rbp+UnicodeString]; SourceString
0x140044adb  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140044ae0  mov     r14d, eax
0x140044ae3  test    eax, eax
0x140044ae5  jns     short loc_140044B4B
0x140044ae7  lea     rax, aPushCreatingSh_0; "PUSH: Creating short name path"
0x140044aee  mov     r8, 5D300130158h; struct UnionFs::StackEventTracer *
0x140044af8  lea     r9, aUnionfsUfspath_26; "UnionFs::UfsPathName::MakeShortNameCopy"
0x140044aff  mov     [rsp+68h+var_48], rax; char *
0x140044b04  mov     rdx, rdi; int
0x140044b07  mov     ecx, r14d; this
0x140044b0a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140044b0f  mov     rbx, [rbp+P]
0x140044b13  test    rbx, rbx
0x140044b16  jz      short loc_140044B3D
0x140044b18  cmp     byte ptr [rbx+10h], 0
0x140044b1c  jnz     short loc_140044B24
0x140044b1e  xorps   xmm0, xmm0
0x140044b21  movups  xmmword ptr [rbx], xmm0
0x140044b24  mov     rcx, rbx; UnicodeString
0x140044b27  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044b2c  xor     edx, edx; Tag
0x140044b2e  mov     rcx, rbx; P
0x140044b31  call    cs:__imp_ExFreePoolWithTag
0x140044b38  nop     dword ptr [rax+rax+00h]
0x140044b3d  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x140044b41  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044b46  mov     ebx, r14d
0x140044b49  jmp     short loc_140044B8A
0x140044b4b  mov     rbx, [rsi]
0x140044b4e  mov     rax, [rbp+P]
0x140044b52  mov     [rsi], rax
0x140044b55  test    rbx, rbx
0x140044b58  jz      short loc_140044B7F
0x140044b5a  cmp     byte ptr [rbx+10h], 0
0x140044b5e  jnz     short loc_140044B66
0x140044b60  xorps   xmm0, xmm0
0x140044b63  movups  xmmword ptr [rbx], xmm0
0x140044b66  mov     rcx, rbx; UnicodeString
0x140044b69  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044b6e  xor     edx, edx; Tag
0x140044b70  mov     rcx, rbx; P
0x140044b73  call    cs:__imp_ExFreePoolWithTag
0x140044b7a  nop     dword ptr [rax+rax+00h]
0x140044b7f  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x140044b83  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044b88  xor     ebx, ebx
0x140044b8a  lea     rcx, [rbp+Source]; UnicodeString
0x140044b8e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140044b93  mov     eax, ebx
0x140044b95  add     rsp, 68h
0x140044b99  pop     r15
0x140044b9b  pop     r14
0x140044b9d  pop     rdi
0x140044b9e  pop     rsi
0x140044b9f  pop     rbx
0x140044ba0  pop     rbp
0x140044ba1  retn
```
