# UnionFs::Utils::ReplaceFirstSubstring(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x140076308`
- end: `0x140076659`
- name: `?ReplaceFirstSubstring@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@00AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `849`
- prototype: `__int64 __usercall@<rax>(UnionFs::Rtl *this@<rcx>, struct _UNICODE_STRING *@<rdx>, PCUNICODE_STRING Source@<r8>, int)`
- caller_count: `6`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140025168`
- `0x14003ff88`
- `0x140043ef4`
- `0x140044c04`
- `0x140044cd4`
- `0x140076da4`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x14006df24`
- `0x140076308`
- `0x140079c48`
- `0x140079d0c`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400764ca`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140076510`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007655b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400765f7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400764ca`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140076510`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007655b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400765f7`

## string_xrefs

- `0x1400763a4`: `UnionFs::Utils::ReplaceFirstSubstring`
- `0x14007641d`: `UnionFs::Utils::ReplaceFirstSubstring`
- `0x140076483`: `UnionFs::Utils::ReplaceFirstSubstring`
- `0x1400764f1`: `UnionFs::Utils::ReplaceFirstSubstring`
- `0x1400764dc`: `API: Copying prefix into destination`
- `0x14007656d`: `API: Copying whack into destination`
- `0x140076522`: `API: Copying substring into destination`
- `0x140076609`: `API: Copying suffix into destination`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::ReplaceFirstSubstring(
        PWSTR *this,
        struct _UNICODE_STRING *a2,
        PCUNICODE_STRING Source,
        struct _UNICODE_STRING *a4,
        int a5)
{
  unsigned int Length; // edx
  bool v8; // r12
  PCUNICODE_STRING v9; // rsi
  unsigned __int64 v10; // rcx
  PWSTR Buffer; // rax
  bool v12; // di
  unsigned __int16 *UnicodeSubstring; // r13
  NTSTATUS appended; // ebx
  PWSTR v15; // rbx
  __int64 v16; // rdx
  unsigned __int16 v17; // ax
  __int64 v18; // r8
  struct _UNICODE_STRING *v19; // rdx
  __int64 v20; // r13
  const char *v21; // rax
  __int64 v22; // r8
  USHORT v23; // dx
  __int16 v24; // cx
  __int64 v25; // rdx
  __int16 v26; // ax
  USHORT v27; // cx
  PWSTR v28; // rax
  struct _UNICODE_STRING v29; // xmm1
  const char *v31; // [rsp+28h] [rbp-48h]
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING Sourcea; // [rsp+40h] [rbp-30h] BYREF
  UNICODE_STRING v34; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING v35; // [rsp+60h] [rbp-10h] BYREF
  int v36; // [rsp+B8h] [rbp+48h] BYREF
  struct _UNICODE_STRING *v37; // [rsp+C8h] [rbp+58h]

  v37 = a4;
  Length = a2->Length;
  v8 = 0;
  v9 = Source;
  v10 = (unsigned __int64)Source->Length >> 1;
  Buffer = Source->Buffer;
  if ( a2->Buffer[((unsigned __int64)Length >> 1) - 1] == 92 )
  {
    v12 = Buffer[v10 - 1] != 92;
  }
  else
  {
    v12 = 0;
    if ( Buffer[v10 - 1] == 92 )
      v8 = *(_WORD *)this != (unsigned __int16)Length;
  }
  LOBYTE(Source) = 1;
  UnicodeSubstring = UnionFs::Rtl::FindUnicodeSubstring((UnionFs::Rtl *)this, a2, Source, (unsigned __int8)a4);
  if ( UnicodeSubstring )
  {
    v15 = this[1];
    v16 = *(unsigned __int16 *)this;
    if ( v9->Length != a2->Length )
    {
      if ( (unsigned __int16)v16 < a2->Length )
        MicrosoftTelemetryAssertTriggeredMsgKM("Source.Length >= OldSubstr.Length");
      if ( *(_WORD *)this < a2->Length )
      {
        v18 = 0xD800210773LL;
        goto LABEL_13;
      }
      v17 = *(_WORD *)this - a2->Length;
      v16 = v17;
      LOWORD(v16) = v9->Length + v17;
      if ( (unsigned __int16)v16 < v17 )
      {
        v18 = 0xD900210778LL;
LABEL_13:
        appended = -1073741675;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)0xC0000095LL,
          a5,
          (struct UnionFs::StackEventTracer *)v18,
          (unsigned __int64)"UnionFs::Utils::ReplaceFirstSubstring",
          "API: Arithmetic error",
          v31);
        return (unsigned int)appended;
      }
    }
    if ( v12 )
    {
      LOWORD(v16) = v16 + 2;
    }
    else if ( v8 )
    {
      LOWORD(v16) = v16 - 2;
    }
    FsFltWil::MakeUniqueUnicodeString(&Destination, v16, 1279685446);
    if ( !Destination.Buffer )
    {
      appended = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        a5,
        (struct UnionFs::StackEventTracer *)0xDA00210790LL,
        (unsigned __int64)"UnionFs::Utils::ReplaceFirstSubstring",
        "ORIGIN: Allocating destination string",
        v31);
LABEL_36:
      FsFltWil::Details::FreeUnicodeString(&Destination, v19);
      return (unsigned int)appended;
    }
    Sourcea = 0;
    v20 = UnicodeSubstring - v15;
    Sourcea.MaximumLength = 2 * v20;
    Sourcea.Length = 2 * v20;
    Sourcea.Buffer = this[1];
    appended = RtlAppendUnicodeStringToString(&Destination, &Sourcea);
    if ( appended >= 0 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, v9);
      if ( appended >= 0 )
      {
        if ( v12 )
        {
          v36 = *(_DWORD *)L"\\";
          *(_QWORD *)&v34.Length = 262146;
          v34.Buffer = (PWSTR)&v36;
          appended = RtlAppendUnicodeStringToString(&Destination, &v34);
          if ( appended < 0 )
          {
            v21 = "API: Copying whack into destination";
            v22 = 0xDD002107ABLL;
            goto LABEL_23;
          }
        }
        else if ( v8 )
        {
          v23 = Destination.Length;
          if ( Destination.Buffer[((unsigned __int64)Destination.Length >> 1) - 1] != 92 )
          {
            MicrosoftTelemetryAssertTriggeredMsgKM("We expect a terminal \\ here.");
            v23 = Destination.Length;
          }
          Destination.Length = v23 - 2;
        }
        v24 = *(_WORD *)this;
        v25 = (unsigned __int16)(v20 + (a2->Length >> 1));
        v26 = v20 + (a2->Length >> 1);
        v35 = 0;
        v27 = v24 - 2 * v26;
        v28 = this[1];
        v35.MaximumLength = v27;
        v35.Length = v27;
        v35.Buffer = &v28[v25];
        appended = RtlAppendUnicodeStringToString(&Destination, &v35);
        if ( appended >= 0 )
        {
          appended = 0;
          v29 = *v37;
          *v37 = Destination;
          Destination = v29;
          goto LABEL_36;
        }
        v21 = "API: Copying suffix into destination";
        v22 = 0xDE002107BELL;
        goto LABEL_23;
      }
      v21 = "API: Copying substring into destination";
      v22 = 0xDC002107A1LL;
    }
    else
    {
      v21 = "API: Copying prefix into destination";
      v22 = 0xDB0021079BLL;
    }
LABEL_23:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)appended,
      a5,
      (struct UnionFs::StackEventTracer *)v22,
      (unsigned __int64)"UnionFs::Utils::ReplaceFirstSubstring",
      v21,
      v31);
    goto LABEL_36;
  }
  appended = -1073741275;
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC0000225LL,
    a5,
    (struct UnionFs::StackEventTracer *)0xD70021075FLL,
    (unsigned __int64)"UnionFs::Utils::ReplaceFirstSubstring",
    "ORIGIN: Could not find old substring in source.",
    v31);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140076308  mov     [rsp-38h+arg_0], rbx
0x14007630d  mov     [rsp-38h+arg_18], r9
0x140076312  push    rbp
0x140076313  push    rsi
0x140076314  push    rdi
0x140076315  push    r12
0x140076317  push    r13
0x140076319  push    r14
0x14007631b  push    r15
0x14007631d  mov     rbp, rsp
0x140076320  sub     rsp, 70h
0x140076324  mov     r15, rdx
0x140076327  mov     r14, rcx
0x14007632a  movzx   edx, word ptr [rdx]
0x14007632d  xor     r12b, r12b
0x140076330  movzx   ecx, word ptr [r8]
0x140076334  mov     r10d, edx
0x140076337  shr     r10, 1
0x14007633a  mov     rsi, r8
0x14007633d  mov     rax, [r15+8]
0x140076341  shr     rcx, 1
0x140076344  cmp     word ptr [rax+r10*2-2], 5Ch ; '\'
0x14007634b  mov     rax, [r8+8]
0x14007634f  jnz     short loc_140076363
0x140076351  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140076357  jz      short loc_14007635E
0x140076359  mov     dil, 1
0x14007635c  jmp     short loc_140076377
0x14007635e  xor     dil, dil
0x140076361  jmp     short loc_140076377
0x140076363  xor     dil, dil
0x140076366  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14007636c  jnz     short loc_140076377
0x14007636e  cmp     [r14], dx
0x140076372  jz      short loc_140076377
0x140076374  mov     r12b, 1
0x140076377  mov     r8b, 1; struct _UNICODE_STRING *
0x14007637a  mov     rdx, r15; struct _UNICODE_STRING *
0x14007637d  mov     rcx, r14; this
0x140076380  call    ?FindUnicodeSubstring@Rtl@UnionFs@@YAPEAGPEBU_UNICODE_STRING@@0E@Z; UnionFs::Rtl::FindUnicodeSubstring(_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x140076385  mov     r13, rax
0x140076388  test    rax, rax
0x14007638b  jnz     short loc_1400763BF
0x14007638d  mov     rdx, qword ptr [rbp+arg_20]; int
0x140076391  lea     rax, aOriginCouldNot_1; "ORIGIN: Could not find old substring in"...
0x140076398  mov     ebx, 0C0000225h
0x14007639d  mov     [rsp+70h+var_50], rax; char *
0x1400763a2  mov     ecx, ebx; this
0x1400763a4  lea     r9, aUnionfsUtilsRe; "UnionFs::Utils::ReplaceFirstSubstring"
0x1400763ab  mov     r8, 0D70021075Fh; struct UnionFs::StackEventTracer *
0x1400763b5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400763ba  jmp     loc_14007663E
0x1400763bf  movzx   eax, word ptr [r15]
0x1400763c3  mov     rbx, [r14+8]
0x1400763c7  movzx   edx, word ptr [r14]
0x1400763cb  cmp     [rsi], ax
0x1400763ce  jz      short loc_14007643A
0x1400763d0  cmp     dx, ax
0x1400763d3  jnb     short loc_1400763E1
0x1400763d5  lea     rcx, aSourceLengthOl; "Source.Length >= OldSubstr.Length"
0x1400763dc  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400763e1  movzx   ecx, word ptr [r15]
0x1400763e5  movzx   eax, word ptr [r14]
0x1400763e9  cmp     ax, cx
0x1400763ec  jb      short loc_14007642E
0x1400763ee  sub     ax, cx
0x1400763f1  movzx   edx, ax
0x1400763f4  add     dx, [rsi]
0x1400763f7  cmp     dx, ax
0x1400763fa  jnb     short loc_14007643A
0x1400763fc  mov     r8, 0D900210778h; struct UnionFs::StackEventTracer *
0x140076406  mov     rdx, qword ptr [rbp+arg_20]; int
0x14007640a  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140076411  mov     ebx, 0C0000095h
0x140076416  mov     [rsp+70h+var_50], rax; char *
0x14007641b  mov     ecx, ebx; this
0x14007641d  lea     r9, aUnionfsUtilsRe; "UnionFs::Utils::ReplaceFirstSubstring"
0x140076424  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076429  jmp     loc_14007663E
0x14007642e  mov     r8, 0D800210773h
0x140076438  jmp     short loc_140076406
0x14007643a  mov     ecx, 2
0x14007643f  mov     eax, 0FFFEh
0x140076444  test    dil, dil
0x140076447  jz      short loc_14007644E
0x140076449  add     dx, cx
0x14007644c  jmp     short loc_140076456
0x14007644e  test    r12b, r12b
0x140076451  jz      short loc_140076456
0x140076453  add     dx, ax
0x140076456  mov     r8d, 4C467346h
0x14007645c  lea     rcx, [rbp+Destination]
0x140076460  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140076465  cmp     [rbp+Destination.Buffer], 0
0x14007646a  jnz     short loc_14007649E
0x14007646c  mov     rdx, qword ptr [rbp+arg_20]; int
0x140076470  lea     rax, aOriginAllocati_24; "ORIGIN: Allocating destination string"
0x140076477  mov     ebx, 0C000009Ah
0x14007647c  mov     [rsp+70h+var_50], rax; char *
0x140076481  mov     ecx, ebx; this
0x140076483  lea     r9, aUnionfsUtilsRe; "UnionFs::Utils::ReplaceFirstSubstring"
0x14007648a  mov     r8, 0DA00210790h; struct UnionFs::StackEventTracer *
0x140076494  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076499  jmp     loc_140076635
0x14007649e  xorps   xmm0, xmm0
0x1400764a1  lea     rdx, [rbp+Source]; Source
0x1400764a5  movups  xmmword ptr [rbp+Source.Length], xmm0
0x1400764a9  sub     r13, rbx
0x1400764ac  lea     rcx, [rbp+Destination]; Destination
0x1400764b0  sar     r13, 1
0x1400764b3  movzx   eax, r13w
0x1400764b7  add     ax, ax
0x1400764ba  mov     [rbp+Source.MaximumLength], ax
0x1400764be  mov     [rbp+Source.Length], ax
0x1400764c2  mov     rax, [r14+8]
0x1400764c6  mov     [rbp+Source.Buffer], rax
0x1400764ca  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400764d1  nop     dword ptr [rax+rax+00h]
0x1400764d6  mov     ebx, eax
0x1400764d8  test    eax, eax
0x1400764da  jns     short loc_140076509
0x1400764dc  lea     rax, aApiCopyingPref_0; "API: Copying prefix into destination"
0x1400764e3  mov     r8, 0DB0021079Bh; struct UnionFs::StackEventTracer *
0x1400764ed  mov     rdx, qword ptr [rbp+arg_20]; int
0x1400764f1  lea     r9, aUnionfsUtilsRe; "UnionFs::Utils::ReplaceFirstSubstring"
0x1400764f8  mov     ecx, ebx; this
0x1400764fa  mov     [rsp+70h+var_50], rax; char *
0x1400764ff  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076504  jmp     loc_140076635
0x140076509  mov     rdx, rsi; Source
0x14007650c  lea     rcx, [rbp+Destination]; Destination
0x140076510  call    cs:__imp_RtlAppendUnicodeStringToString
0x140076517  nop     dword ptr [rax+rax+00h]
0x14007651c  mov     ebx, eax
0x14007651e  test    eax, eax
0x140076520  jns     short loc_140076535
0x140076522  lea     rax, aApiCopyingSubs; "API: Copying substring into destination"
0x140076529  mov     r8, 0DC002107A1h
0x140076533  jmp     short loc_1400764ED
0x140076535  test    dil, dil
0x140076538  jz      short loc_140076583
0x14007653a  mov     eax, dword ptr cs:Source; "\\"
0x140076540  lea     rdx, [rbp+var_20]; Source
0x140076544  mov     [rbp+arg_8], eax
0x140076547  lea     rcx, [rbp+Destination]; Destination
0x14007654b  lea     rax, [rbp+arg_8]
0x14007654f  mov     qword ptr [rbp+var_20.Length], 40002h
0x140076557  mov     [rbp+var_20.Buffer], rax
0x14007655b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140076562  nop     dword ptr [rax+rax+00h]
0x140076567  mov     ebx, eax
0x140076569  test    eax, eax
0x14007656b  jns     short loc_1400765B9
0x14007656d  lea     rax, aApiCopyingWhac; "API: Copying whack into destination"
0x140076574  mov     r8, 0DD002107ABh
0x14007657e  jmp     loc_1400764ED
0x140076583  test    r12b, r12b
0x140076586  jz      short loc_1400765B9
0x140076588  movzx   edx, [rbp+Destination.Length]
0x14007658c  mov     rax, [rbp+Destination.Buffer]
0x140076590  mov     ecx, edx
0x140076592  shr     rcx, 1
0x140076595  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14007659b  jz      short loc_1400765AD
0x14007659d  lea     rcx, aWeExpectATermi; "We expect a terminal \\ here."
0x1400765a4  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400765a9  movzx   edx, [rbp+Destination.Length]
0x1400765ad  mov     eax, 0FFFEh
0x1400765b2  add     dx, ax
0x1400765b5  mov     [rbp+Destination.Length], dx
0x1400765b9  movzx   eax, word ptr [r15]
0x1400765bd  xorps   xmm0, xmm0
0x1400765c0  movzx   ecx, word ptr [r14]
0x1400765c4  shr     ax, 1
0x1400765c7  add     ax, r13w
0x1400765cb  movzx   edx, ax
0x1400765ce  movzx   eax, dx
0x1400765d1  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x1400765d5  add     ax, ax
0x1400765d8  sub     cx, ax
0x1400765db  mov     rax, [r14+8]
0x1400765df  mov     [rbp+var_10.MaximumLength], cx
0x1400765e3  mov     [rbp+var_10.Length], cx
0x1400765e7  lea     rcx, [rax+rdx*2]
0x1400765eb  mov     [rbp+var_10.Buffer], rcx
0x1400765ef  lea     rdx, [rbp+var_10]; Source
0x1400765f3  lea     rcx, [rbp+Destination]; Destination
0x1400765f7  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400765fe  nop     dword ptr [rax+rax+00h]
0x140076603  mov     ebx, eax
0x140076605  test    eax, eax
0x140076607  jns     short loc_14007661F
0x140076609  lea     rax, aApiCopyingSuff_0; "API: Copying suffix into destination"
0x140076610  mov     r8, 0DE002107BEh
0x14007661a  jmp     loc_1400764ED
0x14007661f  mov     rax, [rbp+arg_18]
0x140076623  xor     ebx, ebx
0x140076625  movaps  xmm0, xmmword ptr [rbp+Destination.Length]
0x140076629  movups  xmm1, xmmword ptr [rax]
0x14007662c  movdqu  xmmword ptr [rax], xmm0
0x140076630  movdqa  xmmword ptr [rbp+Destination.Length], xmm1
0x140076635  lea     rcx, [rbp+Destination]; UnicodeString
0x140076639  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14007663e  mov     eax, ebx
0x140076640  mov     rbx, [rsp+70h+arg_0]
0x140076648  add     rsp, 70h
0x14007664c  pop     r15
0x14007664e  pop     r14
0x140076650  pop     r13
0x140076652  pop     r12
0x140076654  pop     rdi
0x140076655  pop     rsi
0x140076656  pop     rbp
0x140076657  retn
```
