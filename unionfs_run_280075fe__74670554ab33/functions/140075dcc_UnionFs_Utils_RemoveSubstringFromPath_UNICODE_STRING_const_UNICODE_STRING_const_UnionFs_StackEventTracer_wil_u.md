# UnionFs::Utils::RemoveSubstringFromPath(_UNICODE_STRING const &,_UNICODE_STRING const &,UnionFs::StackEventTracer &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &)

- ea: `0x140075dcc`
- end: `0x140075fd1`
- name: `?RemoveSubstringFromPath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAVStackEventTracer@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@Z`
- size: `517`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400206a0`
- `0x140025168`
- `0x14005c500`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x14006df24`
- `0x140075dcc`
- `0x140079c48`
- `0x140079d0c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140075ed5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140075f4d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140075ed5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140075f4d`

## string_xrefs

- `0x140075df2`: `ORIGIN: Substring is entire FullPath.`
- `0x140075e33`: `ORIGIN: Could not find Substring in FullPath.`
- `0x140075e10`: `UnionFs::Utils::RemoveSubstringFromPath`
- `0x140075e8b`: `UnionFs::Utils::RemoveSubstringFromPath`
- `0x140075ef8`: `UnionFs::Utils::RemoveSubstringFromPath`
- `0x140075fa6`: `UnionFs::Utils::RemoveSubstringFromPath`
- `0x140075ee7`: `API: Copying prefix into final`
- `0x140075f5f`: `API: Copying suffix into final`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::RemoveSubstringFromPath(
        PWSTR *a1,
        const struct _UNICODE_STRING *a2,
        const struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  int v5; // edi
  const char *v8; // rax
  __int64 v9; // r8
  unsigned int appended; // ebx
  unsigned __int16 *UnicodeSubstring; // r15
  __int64 v12; // rdx
  PWSTR v13; // rbx
  struct _UNICODE_STRING *v14; // rdx
  __int64 v15; // r15
  const char *v16; // rax
  __int64 v17; // r8
  __int16 v18; // cx
  __int64 v19; // rdx
  __int16 v20; // ax
  USHORT v21; // cx
  PWSTR v22; // rax
  struct _UNICODE_STRING v23; // xmm0
  const char *v25; // [rsp+28h] [rbp-38h]
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-30h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING v28; // [rsp+50h] [rbp-10h] BYREF

  v5 = (int)a3;
  if ( *(_WORD *)a1 != a2->Length )
  {
    LOBYTE(a3) = 1;
    UnicodeSubstring = UnionFs::Rtl::FindUnicodeSubstring((UnionFs::Rtl *)a1, a2, a3, (unsigned __int8)a4);
    if ( !UnicodeSubstring )
    {
      v8 = "ORIGIN: Could not find Substring in FullPath.";
      v9 = 0x37400210380LL;
      appended = -1073741275;
      goto LABEL_3;
    }
    v12 = *(unsigned __int16 *)a1;
    if ( (unsigned __int16)v12 < a2->Length )
    {
      appended = -1073741675;
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        v5,
        (struct UnionFs::StackEventTracer *)0x3750021038ALL,
        (unsigned __int64)"UnionFs::Utils::RemoveSubstringFromPath",
        "API: Arithmetic error",
        v25);
      return appended;
    }
    v13 = a1[1];
    LOWORD(v12) = v12 - a2->Length;
    FsFltWil::MakeUniqueUnicodeString(&Destination, v12, 1279685446);
    if ( Destination.Buffer )
    {
      Source = 0;
      v15 = UnicodeSubstring - v13;
      Source.MaximumLength = 2 * v15;
      Source.Length = 2 * v15;
      Source.Buffer = a1[1];
      appended = RtlAppendUnicodeStringToString(&Destination, &Source);
      if ( (appended & 0x80000000) == 0 )
      {
        v18 = *(_WORD *)a1;
        v19 = (unsigned __int16)(v15 + (a2->Length >> 1));
        v20 = v15 + (a2->Length >> 1);
        v28 = 0;
        v21 = v18 - 2 * v20;
        v22 = a1[1];
        v28.MaximumLength = v21;
        v28.Length = v21;
        v28.Buffer = &v22[v19];
        appended = RtlAppendUnicodeStringToString(&Destination, &v28);
        if ( (appended & 0x80000000) == 0 )
        {
          appended = 0;
          v23 = Destination;
          Destination = *a4;
          *a4 = v23;
          goto LABEL_15;
        }
        v16 = "API: Copying suffix into final";
        v17 = 0x378002103ACLL;
      }
      else
      {
        v16 = "API: Copying prefix into final";
        v17 = 0x377002103A0LL;
      }
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)appended,
        v5,
        (struct UnionFs::StackEventTracer *)v17,
        (unsigned __int64)"UnionFs::Utils::RemoveSubstringFromPath",
        v16,
        v25);
    }
    else
    {
      appended = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        v5,
        (struct UnionFs::StackEventTracer *)0x37600210394LL,
        (unsigned __int64)"UnionFs::Utils::RemoveSubstringFromPath",
        "ORIGIN: Allocating final string",
        v25);
    }
LABEL_15:
    FsFltWil::Details::FreeUnicodeString(&Destination, v14);
    return appended;
  }
  v8 = "ORIGIN: Substring is entire FullPath.";
  v9 = 0x41000210375LL;
  appended = -1073741811;
LABEL_3:
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)appended,
    v5,
    (struct UnionFs::StackEventTracer *)v9,
    (unsigned __int64)"UnionFs::Utils::RemoveSubstringFromPath",
    v8,
    v25);
  return appended;
}

```

## disassembly

```asm
0x140075dcc  push    rbp
0x140075dce  push    rbx
0x140075dcf  push    rsi
0x140075dd0  push    rdi
0x140075dd1  push    r12
0x140075dd3  push    r14
0x140075dd5  push    r15
0x140075dd7  mov     rbp, rsp
0x140075dda  sub     rsp, 60h
0x140075dde  movzx   eax, word ptr [rdx]
0x140075de1  mov     r12, r9
0x140075de4  mov     rdi, r8
0x140075de7  mov     r14, rdx
0x140075dea  mov     rsi, rcx
0x140075ded  cmp     [rcx], ax
0x140075df0  jnz     short loc_140075E23
0x140075df2  lea     rax, aOriginSubstrin; "ORIGIN: Substring is entire FullPath."
0x140075df9  mov     r8, 41000210375h; struct UnionFs::StackEventTracer *
0x140075e03  mov     ebx, 0C000000Dh
0x140075e08  mov     rdx, rdi; int
0x140075e0b  mov     [rsp+60h+var_40], rax; char *
0x140075e10  lea     r9, aUnionfsUtilsRe_3; "UnionFs::Utils::RemoveSubstringFromPath"
0x140075e17  mov     ecx, ebx; this
0x140075e19  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075e1e  jmp     loc_140075FBF
0x140075e23  mov     r8b, 1; struct _UNICODE_STRING *
0x140075e26  call    ?FindUnicodeSubstring@Rtl@UnionFs@@YAPEAGPEBU_UNICODE_STRING@@0E@Z; UnionFs::Rtl::FindUnicodeSubstring(_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x140075e2b  mov     r15, rax
0x140075e2e  test    rax, rax
0x140075e31  jnz     short loc_140075E4B
0x140075e33  lea     rax, aOriginCouldNot_3; "ORIGIN: Could not find Substring in Ful"...
0x140075e3a  mov     r8, 37400210380h
0x140075e44  mov     ebx, 0C0000225h
0x140075e49  jmp     short loc_140075E08
0x140075e4b  movzx   eax, word ptr [r14]
0x140075e4f  movzx   edx, word ptr [rsi]
0x140075e52  cmp     dx, ax
0x140075e55  jb      loc_140075F93
0x140075e5b  mov     rbx, [rsi+8]
0x140075e5f  lea     rcx, [rbp+Destination]
0x140075e63  sub     dx, ax
0x140075e66  mov     r8d, 4C467346h
0x140075e6c  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140075e71  cmp     [rbp+Destination.Buffer], 0
0x140075e76  jnz     short loc_140075EA9
0x140075e78  lea     rax, aOriginAllocati_2; "ORIGIN: Allocating final string"
0x140075e7f  mov     ebx, 0C000009Ah
0x140075e84  mov     ecx, ebx; this
0x140075e86  mov     [rsp+60h+var_40], rax; char *
0x140075e8b  lea     r9, aUnionfsUtilsRe_3; "UnionFs::Utils::RemoveSubstringFromPath"
0x140075e92  mov     r8, 37600210394h; struct UnionFs::StackEventTracer *
0x140075e9c  mov     rdx, rdi; int
0x140075e9f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075ea4  jmp     loc_140075F88
0x140075ea9  xorps   xmm0, xmm0
0x140075eac  lea     rdx, [rbp+Source]; Source
0x140075eb0  movups  xmmword ptr [rbp+Source.Length], xmm0
0x140075eb4  sub     r15, rbx
0x140075eb7  lea     rcx, [rbp+Destination]; Destination
0x140075ebb  sar     r15, 1
0x140075ebe  movzx   eax, r15w
0x140075ec2  add     ax, ax
0x140075ec5  mov     [rbp+Source.MaximumLength], ax
0x140075ec9  mov     [rbp+Source.Length], ax
0x140075ecd  mov     rax, [rsi+8]
0x140075ed1  mov     [rbp+Source.Buffer], rax
0x140075ed5  call    cs:__imp_RtlAppendUnicodeStringToString
0x140075edc  nop     dword ptr [rax+rax+00h]
0x140075ee1  mov     ebx, eax
0x140075ee3  test    eax, eax
0x140075ee5  jns     short loc_140075F10
0x140075ee7  lea     rax, aApiCopyingPref; "API: Copying prefix into final"
0x140075eee  mov     r8, 377002103A0h; struct UnionFs::StackEventTracer *
0x140075ef8  lea     r9, aUnionfsUtilsRe_3; "UnionFs::Utils::RemoveSubstringFromPath"
0x140075eff  mov     [rsp+60h+var_40], rax; char *
0x140075f04  mov     rdx, rdi; int
0x140075f07  mov     ecx, ebx; this
0x140075f09  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075f0e  jmp     short loc_140075F88
0x140075f10  movzx   eax, word ptr [r14]
0x140075f14  xorps   xmm0, xmm0
0x140075f17  movzx   ecx, word ptr [rsi]
0x140075f1a  shr     ax, 1
0x140075f1d  add     ax, r15w
0x140075f21  movzx   edx, ax
0x140075f24  movzx   eax, dx
0x140075f27  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x140075f2b  add     ax, ax
0x140075f2e  sub     cx, ax
0x140075f31  mov     rax, [rsi+8]
0x140075f35  mov     [rbp+var_10.MaximumLength], cx
0x140075f39  mov     [rbp+var_10.Length], cx
0x140075f3d  lea     rcx, [rax+rdx*2]
0x140075f41  mov     [rbp+var_10.Buffer], rcx
0x140075f45  lea     rdx, [rbp+var_10]; Source
0x140075f49  lea     rcx, [rbp+Destination]; Destination
0x140075f4d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140075f54  nop     dword ptr [rax+rax+00h]
0x140075f59  mov     ebx, eax
0x140075f5b  test    eax, eax
0x140075f5d  jns     short loc_140075F72
0x140075f5f  lea     rax, aApiCopyingSuff; "API: Copying suffix into final"
0x140075f66  mov     r8, 378002103ACh
0x140075f70  jmp     short loc_140075EF8
0x140075f72  movups  xmm1, xmmword ptr [r12]
0x140075f77  xor     ebx, ebx
0x140075f79  movaps  xmm0, xmmword ptr [rbp+Destination.Length]
0x140075f7d  movdqa  xmmword ptr [rbp+Destination.Length], xmm1
0x140075f82  movdqu  xmmword ptr [r12], xmm0
0x140075f88  lea     rcx, [rbp+Destination]; UnicodeString
0x140075f8c  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140075f91  jmp     short loc_140075FBF
0x140075f93  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140075f9a  mov     ebx, 0C0000095h
0x140075f9f  mov     ecx, ebx; this
0x140075fa1  mov     [rsp+60h+var_40], rax; char *
0x140075fa6  lea     r9, aUnionfsUtilsRe_3; "UnionFs::Utils::RemoveSubstringFromPath"
0x140075fad  mov     r8, 3750021038Ah; struct UnionFs::StackEventTracer *
0x140075fb7  mov     rdx, rdi; int
0x140075fba  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075fbf  mov     eax, ebx
0x140075fc1  add     rsp, 60h
0x140075fc5  pop     r15
0x140075fc7  pop     r14
0x140075fc9  pop     r12
0x140075fcb  pop     rdi
0x140075fcc  pop     rsi
0x140075fcd  pop     rbx
0x140075fce  pop     rbp
0x140075fcf  retn
```
