# VhdmpiGetRctFileNames(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14004be04`
- end: `0x14004c0f3`
- name: `?VhdmpiGetRctFileNames@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z`
- size: `751`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14004c42c`
- `0x14004d820`
- `0x14004db00`

## callees

- `0x140019310`
- `0x140023560`
- `0x14002a008`
- `0x140035e94`
- `0x14004be04`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14004bfae`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004c024`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004bfae`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004c024`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004bfc5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004c03b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004bfc5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004c03b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c0a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c0bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c0a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c0bd`
- `ntoskrnl!ExAllocatePool2` at `0x14004beb6`
- `ntoskrnl!ExAllocatePool2` at `0x14004bf2d`
- `ntoskrnl!ExAllocatePool2` at `0x14004beb6`
- `ntoskrnl!ExAllocatePool2` at `0x14004bf2d`

## pseudocode

```c
__int64 __fastcall VhdmpiGetRctFileNames(
        PCUNICODE_STRING SourceString,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  USHORT Length; // cx
  int LongPathDecorationAppropriate; // ebx
  int v8; // edx
  __int64 v9; // rsi
  WCHAR *Pool2; // r15
  int v11; // edx
  WCHAR *v12; // rdi
  int v13; // edx
  int v14; // edx
  int v15; // ecx
  struct _UNICODE_STRING v16; // xmm1
  char v18; // [rsp+28h] [rbp-30h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 v21; // [rsp+A0h] [rbp+48h] BYREF

  v21 = 0;
  Length = SourceString->Length;
  DestinationString = 0;
  Destination = 0;
  LongPathDecorationAppropriate = RtlUShortAdd(Length, 0x14u, &v21);
  if ( LongPathDecorationAppropriate < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      TraceEvents((int)"VhdmpiGetRctFileNames", 185, 2, v8, "Cleanup with status 0x%08X", LongPathDecorationAppropriate);
    return (unsigned int)LongPathDecorationAppropriate;
  }
  v9 = v21;
  Pool2 = (WCHAR *)ExAllocatePool2(256, v21, 2051295318);
  if ( !Pool2 )
  {
    LongPathDecorationAppropriate = -1073741670;
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      TraceEvents((int)"VhdmpiGetRctFileNames", 192, 2, v11, "Cleanup [Status = ((NTSTATUS)0xC000009AL)]", v18);
    return (unsigned int)LongPathDecorationAppropriate;
  }
  v12 = (WCHAR *)ExAllocatePool2(256, v9, 2051295318);
  if ( !v12 )
  {
    LongPathDecorationAppropriate = -1073741670;
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      TraceEvents((int)"VhdmpiGetRctFileNames", 199, 2, v13, "Cleanup [Status = ((NTSTATUS)0xC000009AL)]", v18);
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
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      goto LABEL_22;
    v15 = 217;
    goto LABEL_21;
  }
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
  {
    v15 = 208;
LABEL_21:
    TraceEvents((int)"VhdmpiGetRctFileNames", v15, 2, v14, "Cleanup with status 0x%08X", LongPathDecorationAppropriate);
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
0x14004be04  push    rbp
0x14004be06  push    rbx
0x14004be07  push    rsi
0x14004be08  push    rdi
0x14004be09  push    r12
0x14004be0b  push    r13
0x14004be0d  push    r14
0x14004be0f  push    r15
0x14004be11  mov     rbp, rsp
0x14004be14  sub     rsp, 58h
0x14004be18  xor     eax, eax
0x14004be1a  mov     r13, rdx
0x14004be1d  mov     r12, r8
0x14004be20  mov     [rbp+arg_0], ax
0x14004be24  mov     r14, rcx
0x14004be27  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x14004be2b  movzx   ecx, word ptr [rcx]; unsigned __int16
0x14004be2e  xorps   xmm0, xmm0
0x14004be31  xorps   xmm1, xmm1
0x14004be34  lea     edx, [rax+14h]; unsigned __int16
0x14004be37  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004be3b  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x14004be3f  call    ?RtlUShortAdd@@YAJGGPEAG@Z; RtlUShortAdd(ushort,ushort,ushort *)
0x14004be44  mov     ebx, eax
0x14004be46  test    eax, eax
0x14004be48  jns     short loc_14004BEA3
0x14004be4a  mov     ecx, cs:dword_140087708
0x14004be50  cmp     ecx, 2
0x14004be53  jbe     loc_14004C0DF
0x14004be59  mov     edx, 80000h
0x14004be5e  lea     rcx, dword_140087708
0x14004be65  call    _tlgKeywordOn
0x14004be6a  test    al, al
0x14004be6c  jz      loc_14004C0DF
0x14004be72  mov     ecx, 0B9h
0x14004be77  mov     dword ptr [rsp+58h+var_30], ebx; char
0x14004be7b  mov     r9d, edx; int
0x14004be7e  lea     rax, aCleanupWithSta_1; "Cleanup with status 0x%08X"
0x14004be85  mov     edx, ecx; int
0x14004be87  mov     [rsp+58h+var_38], rax; char *
0x14004be8c  lea     rcx, aVhdmpigetrctfi; "VhdmpiGetRctFileNames"
0x14004be93  mov     r8d, 2; int
0x14004be99  call    TraceEvents
0x14004be9e  jmp     loc_14004C0DF
0x14004bea3  movzx   esi, [rbp+arg_0]
0x14004bea7  mov     edi, 7A444856h
0x14004beac  mov     r8d, edi
0x14004beaf  mov     edx, esi
0x14004beb1  mov     ecx, 100h
0x14004beb6  call    cs:__imp_ExAllocatePool2
0x14004bebd  nop     dword ptr [rax+rax+00h]
0x14004bec2  mov     r15, rax
0x14004bec5  test    rax, rax
0x14004bec8  jnz     short loc_14004BF22
0x14004beca  mov     eax, cs:dword_140087708
0x14004bed0  mov     ebx, 0C000009Ah
0x14004bed5  cmp     eax, 2
0x14004bed8  jbe     loc_14004C0DF
0x14004bede  mov     edx, 80000h
0x14004bee3  lea     rcx, dword_140087708
0x14004beea  call    _tlgKeywordOn
0x14004beef  test    al, al
0x14004bef1  jz      loc_14004C0DF
0x14004bef7  mov     ecx, 0C0h
0x14004befc  lea     rax, aCleanupStatusN_22; "Cleanup [Status = ((NTSTATUS)0xC000009A"...
0x14004bf03  mov     r9d, edx; int
0x14004bf06  mov     [rsp+58h+var_38], rax; char *
0x14004bf0b  mov     edx, ecx; int
0x14004bf0d  lea     r8d, [r15+2]; int
0x14004bf11  lea     rcx, aVhdmpigetrctfi; "VhdmpiGetRctFileNames"
0x14004bf18  call    TraceEvents
0x14004bf1d  jmp     loc_14004C0DF
0x14004bf22  mov     r8d, edi
0x14004bf25  mov     rdx, rsi
0x14004bf28  mov     ecx, 100h
0x14004bf2d  call    cs:__imp_ExAllocatePool2
0x14004bf34  nop     dword ptr [rax+rax+00h]
0x14004bf39  mov     rdi, rax
0x14004bf3c  test    rax, rax
0x14004bf3f  jnz     short loc_14004BF99
0x14004bf41  mov     ecx, cs:dword_140087708
0x14004bf47  mov     ebx, 0C000009Ah
0x14004bf4c  cmp     ecx, 2
0x14004bf4f  jbe     loc_14004C0A2
0x14004bf55  mov     edx, 80000h
0x14004bf5a  lea     rcx, dword_140087708
0x14004bf61  call    _tlgKeywordOn
0x14004bf66  test    al, al
0x14004bf68  jz      loc_14004C0A2
0x14004bf6e  mov     ecx, 0C7h
0x14004bf73  lea     rax, aCleanupStatusN_22; "Cleanup [Status = ((NTSTATUS)0xC000009A"...
0x14004bf7a  mov     r9d, edx; int
0x14004bf7d  mov     [rsp+58h+var_38], rax; char *
0x14004bf82  mov     edx, ecx; int
0x14004bf84  lea     r8d, [rdi+2]; int
0x14004bf88  lea     rcx, aVhdmpigetrctfi; "VhdmpiGetRctFileNames"
0x14004bf8f  call    TraceEvents
0x14004bf94  jmp     loc_14004C0A2
0x14004bf99  xor     eax, eax
0x14004bf9b  mov     [rbp+DestinationString.MaximumLength], si
0x14004bf9f  mov     rdx, r14; SourceString
0x14004bfa2  mov     [rbp+DestinationString.Length], ax
0x14004bfa6  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004bfaa  mov     [rbp+DestinationString.Buffer], r15
0x14004bfae  call    cs:__imp_RtlCopyUnicodeString
0x14004bfb5  nop     dword ptr [rax+rax+00h]
0x14004bfba  lea     rdx, aRct; ".rct"
0x14004bfc1  lea     rcx, [rbp+DestinationString]; Destination
0x14004bfc5  call    cs:__imp_RtlAppendUnicodeToString
0x14004bfcc  nop     dword ptr [rax+rax+00h]
0x14004bfd1  lea     rcx, [rbp+DestinationString]
0x14004bfd5  call    VhdmpiMakeLongPathDecorationAppropriate
0x14004bfda  mov     ebx, eax
0x14004bfdc  test    eax, eax
0x14004bfde  jns     short loc_14004C00F
0x14004bfe0  mov     eax, cs:dword_140087708
0x14004bfe6  cmp     eax, 2
0x14004bfe9  jbe     loc_14004C0A2
0x14004bfef  mov     edx, 80000h
0x14004bff4  lea     rcx, dword_140087708
0x14004bffb  call    _tlgKeywordOn
0x14004c000  test    al, al
0x14004c002  jz      loc_14004C0A2
0x14004c008  mov     ecx, 0D0h
0x14004c00d  jmp     short loc_14004C07B
0x14004c00f  xor     eax, eax
0x14004c011  mov     [rbp+Destination.MaximumLength], si
0x14004c015  mov     rdx, r14; SourceString
0x14004c018  mov     [rbp+Destination.Length], ax
0x14004c01c  lea     rcx, [rbp+Destination]; DestinationString
0x14004c020  mov     [rbp+Destination.Buffer], rdi
0x14004c024  call    cs:__imp_RtlCopyUnicodeString
0x14004c02b  nop     dword ptr [rax+rax+00h]
0x14004c030  lea     rdx, aMrt; ".mrt"
0x14004c037  lea     rcx, [rbp+Destination]; Destination
0x14004c03b  call    cs:__imp_RtlAppendUnicodeToString
0x14004c042  nop     dword ptr [rax+rax+00h]
0x14004c047  lea     rcx, [rbp+Destination]
0x14004c04b  call    VhdmpiMakeLongPathDecorationAppropriate
0x14004c050  mov     ebx, eax
0x14004c052  test    eax, eax
0x14004c054  jns     short loc_14004C0CB
0x14004c056  mov     eax, cs:dword_140087708
0x14004c05c  cmp     eax, 2
0x14004c05f  jbe     short loc_14004C0A2
0x14004c061  mov     edx, 80000h
0x14004c066  lea     rcx, dword_140087708
0x14004c06d  call    _tlgKeywordOn
0x14004c072  test    al, al
0x14004c074  jz      short loc_14004C0A2
0x14004c076  mov     ecx, 0D9h
0x14004c07b  mov     r9d, edx; int
0x14004c07e  mov     dword ptr [rsp+58h+var_30], ebx; char
0x14004c082  mov     edx, ecx; int
0x14004c084  lea     rax, aCleanupWithSta_1; "Cleanup with status 0x%08X"
0x14004c08b  lea     rcx, aVhdmpigetrctfi; "VhdmpiGetRctFileNames"
0x14004c092  mov     [rsp+58h+var_38], rax; char *
0x14004c097  mov     r8d, 2; int
0x14004c09d  call    TraceEvents
0x14004c0a2  xor     edx, edx; Tag
0x14004c0a4  mov     rcx, r15; P
0x14004c0a7  call    cs:__imp_ExFreePoolWithTag
0x14004c0ae  nop     dword ptr [rax+rax+00h]
0x14004c0b3  test    rdi, rdi
0x14004c0b6  jz      short loc_14004C0DF
0x14004c0b8  xor     edx, edx; Tag
0x14004c0ba  mov     rcx, rdi; P
0x14004c0bd  call    cs:__imp_ExFreePoolWithTag
0x14004c0c4  nop     dword ptr [rax+rax+00h]
0x14004c0c9  jmp     short loc_14004C0DF
0x14004c0cb  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x14004c0cf  movups  xmm1, xmmword ptr [rbp+Destination.Length]
0x14004c0d3  movdqu  xmmword ptr [r13+0], xmm0
0x14004c0d9  movdqu  xmmword ptr [r12], xmm1
0x14004c0df  mov     eax, ebx
0x14004c0e1  add     rsp, 58h
0x14004c0e5  pop     r15
0x14004c0e7  pop     r14
0x14004c0e9  pop     r13
0x14004c0eb  pop     r12
0x14004c0ed  pop     rdi
0x14004c0ee  pop     rsi
0x14004c0ef  pop     rbx
0x14004c0f0  pop     rbp
0x14004c0f1  retn
```
