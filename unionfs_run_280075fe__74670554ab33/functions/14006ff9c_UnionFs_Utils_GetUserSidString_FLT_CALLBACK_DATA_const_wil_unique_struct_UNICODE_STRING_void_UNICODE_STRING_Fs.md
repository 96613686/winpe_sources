# UnionFs::Utils::GetUserSidString(_FLT_CALLBACK_DATA const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x14006ff9c`
- end: `0x1400700c0`
- name: `?GetUserSidString@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `292`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013bb0`
- `0x1400156a8`
- `0x1400414c8`
- `0x140068770`
- `0x14006dfb0`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x14006ff9c`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14007005d`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14007005d`
- `ntoskrnl!SeQueryInformationToken` at `0x140070014`
- `ntoskrnl!SeQueryInformationToken` at `0x140070014`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400700a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400700a1`

## string_xrefs

- `0x14006ffbb`: `ORIGIN: Need SubjectSecurityContext in Cbd`
- `0x14006ffce`: `UnionFs::Utils::GetUserSidString`
- `0x140070037`: `UnionFs::Utils::GetUserSidString`
- `0x140070080`: `UnionFs::Utils::GetUserSidString`
- `0x14007006f`: `API: Convert SID to string`
- `0x140070026`: `API: Getting caller's SID`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::GetUserSidString(__int64 a1, struct _UNICODE_STRING *a2, int a3)
{
  __int64 v3; // rax
  NTSTATUS v6; // ebx
  __int64 v7; // rdx
  void *v8; // rcx
  const char *v10; // [rsp+28h] [rbp-10h]
  PVOID TokenInformation; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  if ( *(_BYTE *)(v3 + 4) )
  {
    v6 = -1073741811;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      a3,
      (struct UnionFs::StackEventTracer *)0x23F00211816LL,
      (unsigned __int64)"UnionFs::Utils::GetUserSidString",
      "ORIGIN: Need SubjectSecurityContext in Cbd",
      v10);
  }
  else
  {
    v7 = *(_QWORD *)(*(_QWORD *)(v3 + 24) + 8LL);
    v8 = *(void **)(v7 + 32);
    if ( !v8 )
      v8 = *(void **)(v7 + 48);
    TokenInformation = 0;
    v6 = SeQueryInformationToken(v8, TokenUser, &TokenInformation);
    if ( v6 >= 0 )
    {
      v6 = RtlConvertSidToUnicodeString(a2, *(PSID *)TokenInformation, 1u);
      if ( v6 >= 0 )
        v6 = 0;
      else
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v6,
          a3,
          (struct UnionFs::StackEventTracer *)0x2380021182DLL,
          (unsigned __int64)"UnionFs::Utils::GetUserSidString",
          "API: Convert SID to string",
          v10);
      ExFreePoolWithTag(TokenInformation, 0);
    }
    else
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v6,
        a3,
        (struct UnionFs::StackEventTracer *)0x23700211824LL,
        (unsigned __int64)"UnionFs::Utils::GetUserSidString",
        "API: Getting caller's SID",
        v10);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14006ff9c  mov     [rsp+arg_8], rbx
0x14006ffa1  mov     [rsp+arg_10], rsi
0x14006ffa6  push    rdi
0x14006ffa7  sub     rsp, 30h
0x14006ffab  mov     rax, [rcx+10h]
0x14006ffaf  mov     rdi, r8
0x14006ffb2  mov     rsi, rdx
0x14006ffb5  cmp     byte ptr [rax+4], 0
0x14006ffb9  jz      short loc_14006FFEC
0x14006ffbb  lea     rax, aOriginNeedSubj; "ORIGIN: Need SubjectSecurityContext in "...
0x14006ffc2  mov     ebx, 0C000000Dh
0x14006ffc7  mov     ecx, ebx; this
0x14006ffc9  mov     [rsp+38h+var_18], rax; char *
0x14006ffce  lea     r9, aUnionfsUtilsGe_5; "UnionFs::Utils::GetUserSidString"
0x14006ffd5  mov     r8, 23F00211816h; struct UnionFs::StackEventTracer *
0x14006ffdf  mov     rdx, rdi; int
0x14006ffe2  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006ffe7  jmp     loc_1400700AD
0x14006ffec  mov     rax, [rax+18h]
0x14006fff0  mov     rdx, [rax+8]
0x14006fff4  mov     rcx, [rdx+20h]
0x14006fff8  test    rcx, rcx
0x14006fffb  jnz     short loc_140070001
0x14006fffd  mov     rcx, [rdx+30h]; Token
0x140070001  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x140070006  mov     [rsp+38h+TokenInformation], 0
0x14007000f  mov     edx, 1; TokenInformationClass
0x140070014  call    cs:__imp_SeQueryInformationToken
0x14007001b  nop     dword ptr [rax+rax+00h]
0x140070020  mov     ebx, eax
0x140070022  test    eax, eax
0x140070024  jns     short loc_14007004F
0x140070026  lea     rax, aApiGettingCall; "API: Getting caller's SID"
0x14007002d  mov     r8, 23700211824h; struct UnionFs::StackEventTracer *
0x140070037  lea     r9, aUnionfsUtilsGe_5; "UnionFs::Utils::GetUserSidString"
0x14007003e  mov     [rsp+38h+var_18], rax; char *
0x140070043  mov     rdx, rdi; int
0x140070046  mov     ecx, ebx; this
0x140070048  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007004d  jmp     short loc_1400700AD
0x14007004f  mov     rdx, [rsp+38h+TokenInformation]
0x140070054  mov     r8b, 1; AllocateDestinationString
0x140070057  mov     rcx, rsi; UnicodeString
0x14007005a  mov     rdx, [rdx]; Sid
0x14007005d  call    cs:__imp_RtlConvertSidToUnicodeString
0x140070064  nop     dword ptr [rax+rax+00h]
0x140070069  mov     ebx, eax
0x14007006b  test    eax, eax
0x14007006d  jns     short loc_140070098
0x14007006f  lea     rax, aApiConvertSidT; "API: Convert SID to string"
0x140070076  mov     r8, 2380021182Dh; struct UnionFs::StackEventTracer *
0x140070080  lea     r9, aUnionfsUtilsGe_5; "UnionFs::Utils::GetUserSidString"
0x140070087  mov     [rsp+38h+var_18], rax; char *
0x14007008c  mov     rdx, rdi; int
0x14007008f  mov     ecx, ebx; this
0x140070091  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070096  jmp     short loc_14007009A
0x140070098  xor     ebx, ebx
0x14007009a  mov     rcx, [rsp+38h+TokenInformation]; P
0x14007009f  xor     edx, edx; Tag
0x1400700a1  call    cs:__imp_ExFreePoolWithTag
0x1400700a8  nop     dword ptr [rax+rax+00h]
0x1400700ad  mov     rsi, [rsp+38h+arg_10]
0x1400700b2  mov     eax, ebx
0x1400700b4  mov     rbx, [rsp+38h+arg_8]
0x1400700b9  add     rsp, 30h
0x1400700bd  pop     rdi
0x1400700be  retn
```
