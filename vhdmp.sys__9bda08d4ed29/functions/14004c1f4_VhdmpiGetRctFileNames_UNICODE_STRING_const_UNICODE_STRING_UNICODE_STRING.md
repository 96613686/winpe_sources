# VhdmpiGetRctFileNames(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14004c1f4`
- end: `0x14004c4e3`
- name: `?VhdmpiGetRctFileNames@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z`
- size: `751`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14004c81c`
- `0x14004dc10`
- `0x14004def0`

## callees

- `0x1400197b0`
- `0x140023980`
- `0x14002a528`
- `0x140036284`
- `0x14004c1f4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14004c39e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004c414`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004c39e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004c414`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004c3b5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004c42b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004c3b5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004c42b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c497`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c4ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c497`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c4ad`
- `ntoskrnl!ExAllocatePool2` at `0x14004c2a6`
- `ntoskrnl!ExAllocatePool2` at `0x14004c31d`
- `ntoskrnl!ExAllocatePool2` at `0x14004c2a6`
- `ntoskrnl!ExAllocatePool2` at `0x14004c31d`

## pseudocode

```c
__int64 __fastcall VhdmpiGetRctFileNames(
        PCUNICODE_STRING SourceString,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  USHORT Length; // cx
  int LongPathDecorationAppropriate; // ebx
  unsigned int v8; // edx
  __int64 v9; // rsi
  WCHAR *Pool2; // r15
  unsigned int v11; // edx
  WCHAR *v12; // rdi
  unsigned int v13; // edx
  unsigned int v14; // edx
  unsigned __int16 v15; // cx
  struct _UNICODE_STRING v16; // xmm1
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 v20; // [rsp+A0h] [rbp+48h] BYREF

  v20 = 0;
  Length = SourceString->Length;
  DestinationString = 0;
  Destination = 0;
  LongPathDecorationAppropriate = RtlUShortAdd(Length, 0x14u, &v20);
  if ( LongPathDecorationAppropriate < 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
      TraceEvents("VhdmpiGetRctFileNames", 0xB9u, 2u, v8, "Cleanup with status 0x%08X", LongPathDecorationAppropriate);
    return (unsigned int)LongPathDecorationAppropriate;
  }
  v9 = v20;
  Pool2 = (WCHAR *)ExAllocatePool2(256, v20, 2051295318);
  if ( !Pool2 )
  {
    LongPathDecorationAppropriate = -1073741670;
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
      TraceEvents("VhdmpiGetRctFileNames", 0xC0u, 2u, v11, "Cleanup [Status = ((NTSTATUS)0xC000009AL)]");
    return (unsigned int)LongPathDecorationAppropriate;
  }
  v12 = (WCHAR *)ExAllocatePool2(256, v9, 2051295318);
  if ( !v12 )
  {
    LongPathDecorationAppropriate = -1073741670;
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
      TraceEvents("VhdmpiGetRctFileNames", 0xC7u, 2u, v13, "Cleanup [Status = ((NTSTATUS)0xC000009AL)]");
    goto LABEL_22;
  }
  DestinationString.MaximumLength = v9;
  DestinationString.Length = 0;
  DestinationString.Buffer = Pool2;
  RtlCopyUnicodeString(&DestinationString, SourceString);
  RtlAppendUnicodeToString(&DestinationString, L".rct");
  LongPathDecorationAppropriate = VhdmpiMakeLongPathDecorationAppropriate(&DestinationString);
  if ( LongPathDecorationAppropriate >= 0 )
  {
    Destination.MaximumLength = v9;
    Destination.Length = 0;
    Destination.Buffer = v12;
    RtlCopyUnicodeString(&Destination, SourceString);
    RtlAppendUnicodeToString(&Destination, L".mrt");
    LongPathDecorationAppropriate = VhdmpiMakeLongPathDecorationAppropriate(&Destination);
    if ( LongPathDecorationAppropriate >= 0 )
    {
      v16 = Destination;
      *a2 = DestinationString;
      *a3 = v16;
      return (unsigned int)LongPathDecorationAppropriate;
    }
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
      goto LABEL_22;
    v15 = 217;
    goto LABEL_21;
  }
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
  {
    v15 = 208;
LABEL_21:
    TraceEvents("VhdmpiGetRctFileNames", v15, 2u, v14, "Cleanup with status 0x%08X", LongPathDecorationAppropriate);
  }
LABEL_22:
  ExFreePoolWithTag(Pool2, 0);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  return (unsigned int)LongPathDecorationAppropriate;
}

```

## disassembly

```asm
0x14004c1f4  push    rbp
0x14004c1f6  push    rbx
0x14004c1f7  push    rsi
0x14004c1f8  push    rdi
0x14004c1f9  push    r12
0x14004c1fb  push    r13
0x14004c1fd  push    r14
0x14004c1ff  push    r15
0x14004c201  mov     rbp, rsp
0x14004c204  sub     rsp, 58h
0x14004c208  xor     eax, eax
0x14004c20a  mov     r13, rdx
0x14004c20d  mov     r12, r8
0x14004c210  mov     [rbp+arg_0], ax
0x14004c214  mov     r14, rcx
0x14004c217  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x14004c21b  movzx   ecx, word ptr [rcx]; unsigned __int16
0x14004c21e  xorps   xmm0, xmm0
0x14004c221  xorps   xmm1, xmm1
0x14004c224  lea     edx, [rax+14h]; unsigned __int16
0x14004c227  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004c22b  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x14004c22f  call    ?RtlUShortAdd@@YAJGGPEAG@Z; RtlUShortAdd(ushort,ushort,ushort *)
0x14004c234  mov     ebx, eax
0x14004c236  test    eax, eax
0x14004c238  jns     short loc_14004C293
0x14004c23a  mov     ecx, cs:dword_1400876D0
0x14004c240  cmp     ecx, 2
0x14004c243  jbe     loc_14004C4CF
0x14004c249  mov     edx, 80000h
0x14004c24e  lea     rcx, dword_1400876D0
0x14004c255  call    _tlgKeywordOn
0x14004c25a  test    al, al
0x14004c25c  jz      loc_14004C4CF
0x14004c262  mov     ecx, 0B9h
0x14004c267  mov     dword ptr [rsp+58h+var_30], ebx; char
0x14004c26b  mov     r9d, edx; int
0x14004c26e  lea     rax, aCleanupWithSta_1; "Cleanup with status 0x%08X"
0x14004c275  mov     edx, ecx; int
0x14004c277  mov     [rsp+58h+var_38], rax; char *
0x14004c27c  lea     rcx, aVhdmpigetrctfi; "VhdmpiGetRctFileNames"
0x14004c283  mov     r8d, 2; int
0x14004c289  call    TraceEvents
0x14004c28e  jmp     loc_14004C4CF
0x14004c293  movzx   esi, [rbp+arg_0]
0x14004c297  mov     edi, 7A444856h
0x14004c29c  mov     r8d, edi
0x14004c29f  mov     edx, esi
0x14004c2a1  mov     ecx, 100h
0x14004c2a6  call    cs:__imp_ExAllocatePool2
0x14004c2ad  nop     dword ptr [rax+rax+00h]
0x14004c2b2  mov     r15, rax
0x14004c2b5  test    rax, rax
0x14004c2b8  jnz     short loc_14004C312
0x14004c2ba  mov     eax, cs:dword_1400876D0
0x14004c2c0  mov     ebx, 0C000009Ah
0x14004c2c5  cmp     eax, 2
0x14004c2c8  jbe     loc_14004C4CF
0x14004c2ce  mov     edx, 80000h
0x14004c2d3  lea     rcx, dword_1400876D0
0x14004c2da  call    _tlgKeywordOn
0x14004c2df  test    al, al
0x14004c2e1  jz      loc_14004C4CF
0x14004c2e7  mov     ecx, 0C0h
0x14004c2ec  lea     rax, aCleanupStatusN_22; "Cleanup [Status = ((NTSTATUS)0xC000009A"...
0x14004c2f3  mov     r9d, edx; int
0x14004c2f6  mov     [rsp+58h+var_38], rax; char *
0x14004c2fb  mov     edx, ecx; int
0x14004c2fd  lea     r8d, [r15+2]; int
0x14004c301  lea     rcx, aVhdmpigetrctfi; "VhdmpiGetRctFileNames"
0x14004c308  call    TraceEvents
0x14004c30d  jmp     loc_14004C4CF
0x14004c312  mov     r8d, edi
0x14004c315  mov     rdx, rsi
0x14004c318  mov     ecx, 100h
0x14004c31d  call    cs:__imp_ExAllocatePool2
0x14004c324  nop     dword ptr [rax+rax+00h]
0x14004c329  mov     rdi, rax
0x14004c32c  test    rax, rax
0x14004c32f  jnz     short loc_14004C389
0x14004c331  mov     ecx, cs:dword_1400876D0
0x14004c337  mov     ebx, 0C000009Ah
0x14004c33c  cmp     ecx, 2
0x14004c33f  jbe     loc_14004C492
0x14004c345  mov     edx, 80000h
0x14004c34a  lea     rcx, dword_1400876D0
0x14004c351  call    _tlgKeywordOn
0x14004c356  test    al, al
0x14004c358  jz      loc_14004C492
0x14004c35e  mov     ecx, 0C7h
0x14004c363  lea     rax, aCleanupStatusN_22; "Cleanup [Status = ((NTSTATUS)0xC000009A"...
0x14004c36a  mov     r9d, edx; int
0x14004c36d  mov     [rsp+58h+var_38], rax; char *
0x14004c372  mov     edx, ecx; int
0x14004c374  lea     r8d, [rdi+2]; int
0x14004c378  lea     rcx, aVhdmpigetrctfi; "VhdmpiGetRctFileNames"
0x14004c37f  call    TraceEvents
0x14004c384  jmp     loc_14004C492
0x14004c389  xor     eax, eax
0x14004c38b  mov     [rbp+DestinationString.MaximumLength], si
0x14004c38f  mov     rdx, r14; SourceString
0x14004c392  mov     [rbp+DestinationString.Length], ax
0x14004c396  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004c39a  mov     [rbp+DestinationString.Buffer], r15
0x14004c39e  call    cs:__imp_RtlCopyUnicodeString
0x14004c3a5  nop     dword ptr [rax+rax+00h]
0x14004c3aa  lea     rdx, aRct; ".rct"
0x14004c3b1  lea     rcx, [rbp+DestinationString]; Destination
0x14004c3b5  call    cs:__imp_RtlAppendUnicodeToString
0x14004c3bc  nop     dword ptr [rax+rax+00h]
0x14004c3c1  lea     rcx, [rbp+DestinationString]
0x14004c3c5  call    VhdmpiMakeLongPathDecorationAppropriate
0x14004c3ca  mov     ebx, eax
0x14004c3cc  test    eax, eax
0x14004c3ce  jns     short loc_14004C3FF
0x14004c3d0  mov     eax, cs:dword_1400876D0
0x14004c3d6  cmp     eax, 2
0x14004c3d9  jbe     loc_14004C492
0x14004c3df  mov     edx, 80000h
0x14004c3e4  lea     rcx, dword_1400876D0
0x14004c3eb  call    _tlgKeywordOn
0x14004c3f0  test    al, al
0x14004c3f2  jz      loc_14004C492
0x14004c3f8  mov     ecx, 0D0h
0x14004c3fd  jmp     short loc_14004C46B
0x14004c3ff  xor     eax, eax
0x14004c401  mov     [rbp+Destination.MaximumLength], si
0x14004c405  mov     rdx, r14; SourceString
0x14004c408  mov     [rbp+Destination.Length], ax
0x14004c40c  lea     rcx, [rbp+Destination]; DestinationString
0x14004c410  mov     [rbp+Destination.Buffer], rdi
0x14004c414  call    cs:__imp_RtlCopyUnicodeString
0x14004c41b  nop     dword ptr [rax+rax+00h]
0x14004c420  lea     rdx, aMrt; ".mrt"
0x14004c427  lea     rcx, [rbp+Destination]; Destination
0x14004c42b  call    cs:__imp_RtlAppendUnicodeToString
0x14004c432  nop     dword ptr [rax+rax+00h]
0x14004c437  lea     rcx, [rbp+Destination]
0x14004c43b  call    VhdmpiMakeLongPathDecorationAppropriate
0x14004c440  mov     ebx, eax
0x14004c442  test    eax, eax
0x14004c444  jns     short loc_14004C4BB
0x14004c446  mov     eax, cs:dword_1400876D0
0x14004c44c  cmp     eax, 2
0x14004c44f  jbe     short loc_14004C492
0x14004c451  mov     edx, 80000h
0x14004c456  lea     rcx, dword_1400876D0
0x14004c45d  call    _tlgKeywordOn
0x14004c462  test    al, al
0x14004c464  jz      short loc_14004C492
0x14004c466  mov     ecx, 0D9h
0x14004c46b  mov     r9d, edx; int
0x14004c46e  mov     dword ptr [rsp+58h+var_30], ebx; char
0x14004c472  mov     edx, ecx; int
0x14004c474  lea     rax, aCleanupWithSta_1; "Cleanup with status 0x%08X"
0x14004c47b  lea     rcx, aVhdmpigetrctfi; "VhdmpiGetRctFileNames"
0x14004c482  mov     [rsp+58h+var_38], rax; char *
0x14004c487  mov     r8d, 2; int
0x14004c48d  call    TraceEvents
0x14004c492  xor     edx, edx; Tag
0x14004c494  mov     rcx, r15; P
0x14004c497  call    cs:__imp_ExFreePoolWithTag
0x14004c49e  nop     dword ptr [rax+rax+00h]
0x14004c4a3  test    rdi, rdi
0x14004c4a6  jz      short loc_14004C4CF
0x14004c4a8  xor     edx, edx; Tag
0x14004c4aa  mov     rcx, rdi; P
0x14004c4ad  call    cs:__imp_ExFreePoolWithTag
0x14004c4b4  nop     dword ptr [rax+rax+00h]
0x14004c4b9  jmp     short loc_14004C4CF
0x14004c4bb  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x14004c4bf  movups  xmm1, xmmword ptr [rbp+Destination.Length]
0x14004c4c3  movdqu  xmmword ptr [r13+0], xmm0
0x14004c4c9  movdqu  xmmword ptr [r12], xmm1
0x14004c4cf  mov     eax, ebx
0x14004c4d1  add     rsp, 58h
0x14004c4d5  pop     r15
0x14004c4d7  pop     r14
0x14004c4d9  pop     r13
0x14004c4db  pop     r12
0x14004c4dd  pop     rdi
0x14004c4de  pop     rsi
0x14004c4df  pop     rbx
0x14004c4e0  pop     rbp
0x14004c4e1  retn
```
