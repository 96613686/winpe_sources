# KmclpCreateInstanceName

- ea: `0x14001e038`
- end: `0x14001e18a`
- name: `KmclpCreateInstanceName`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001e370`

## callees

- `0x14000ec34`
- `0x140010760`
- `0x140011ed0`
- `0x14001e038`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e166`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e166`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001e09b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001e0d0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001e09b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001e0d0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001e0ba`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001e100`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001e0ba`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001e100`
- `ntoskrnl!RtlStringFromGUID` at `0x14001e0e7`
- `ntoskrnl!RtlStringFromGUID` at `0x14001e0e7`

## pseudocode

```c
__int64 __fastcall KmclpCreateInstanceName(__int64 a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS v4; // esi
  USHORT Length; // dx
  PWSTR Buffer; // rax
  unsigned __int64 v7; // rcx
  WCHAR *v8; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+40h] [rbp-10h] BYREF
  __int16 v12; // [rsp+70h] [rbp+20h] BYREF

  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  v12 = 0;
  GuidString = 0;
  KmclpGetInstanceNameLength();
  if ( *(_BYTE *)(a1 + 1728) )
  {
    (*(void (__fastcall **)(_QWORD, struct _UNICODE_STRING *, __int16 *, _QWORD))(a1 + 2576))(
      *(_QWORD *)(a1 + 2368),
      a2,
      &v12,
      0);
    RtlAppendUnicodeToString(a2, L":");
  }
  if ( *(_QWORD *)(a1 + 2192) )
  {
    RtlAppendUnicodeStringToString(a2, (PCUNICODE_STRING)(a1 + 2184));
    RtlAppendUnicodeToString(a2, L"-");
  }
  v4 = RtlStringFromGUID((const GUID *const)(a1 + 2752), &GuidString);
  if ( v4 >= 0 )
  {
    RtlAppendUnicodeStringToString(a2, &GuidString);
    if ( *(_WORD *)(a1 + 3280) )
    {
      Length = a2->Length;
      Buffer = a2->Buffer;
      v7 = (unsigned __int64)a2->Length >> 1;
      DestinationString.Length = 0;
      v8 = &Buffer[v7];
      LOWORD(Buffer) = a2->MaximumLength - Length;
      DestinationString.Buffer = v8;
      DestinationString.MaximumLength = (unsigned __int16)Buffer;
      RtlUnicodeStringPrintf(&DestinationString, L"-%04x");
      a2->Length += DestinationString.Length;
    }
    v4 = 0;
  }
  if ( GuidString.Buffer )
    ExFreePoolWithTag(GuidString.Buffer, 0x636D6B56u);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001e038  mov     [rsp-18h+arg_8], rbx
0x14001e03d  mov     [rsp-18h+arg_10], rsi
0x14001e042  push    rbp
0x14001e043  push    rdi
0x14001e044  push    r14
0x14001e046  mov     rbp, rsp
0x14001e049  sub     rsp, 50h
0x14001e04d  xor     r14d, r14d
0x14001e050  xorps   xmm0, xmm0
0x14001e053  mov     dword ptr [rbp+DestinationString+4], r14d
0x14001e057  mov     rdi, rdx
0x14001e05a  mov     [rbp+arg_0], r14w
0x14001e05f  mov     rbx, rcx
0x14001e062  movups  xmmword ptr [rbp+GuidString.Length], xmm0
0x14001e066  call    KmclpGetInstanceNameLength
0x14001e06b  cmp     [rbx+6C0h], r14b
0x14001e072  jz      short loc_14001E0A7
0x14001e074  mov     rax, [rbx+0A10h]
0x14001e07b  lea     r8, [rbp+arg_0]
0x14001e07f  mov     rcx, [rbx+940h]
0x14001e086  xor     r9d, r9d
0x14001e089  mov     rdx, rdi
0x14001e08c  call    _guard_dispatch_icall
0x14001e091  lea     rdx, asc_1400147B0; ":"
0x14001e098  mov     rcx, rdi; Destination
0x14001e09b  call    cs:__imp_RtlAppendUnicodeToString
0x14001e0a2  nop     dword ptr [rax+rax+00h]
0x14001e0a7  cmp     [rbx+890h], r14
0x14001e0ae  jz      short loc_14001E0DC
0x14001e0b0  lea     rdx, [rbx+888h]; Source
0x14001e0b7  mov     rcx, rdi; Destination
0x14001e0ba  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001e0c1  nop     dword ptr [rax+rax+00h]
0x14001e0c6  lea     rdx, asc_1400147B4; "-"
0x14001e0cd  mov     rcx, rdi; Destination
0x14001e0d0  call    cs:__imp_RtlAppendUnicodeToString
0x14001e0d7  nop     dword ptr [rax+rax+00h]
0x14001e0dc  lea     rcx, [rbx+0AC0h]; Guid
0x14001e0e3  lea     rdx, [rbp+GuidString]; GuidString
0x14001e0e7  call    cs:__imp_RtlStringFromGUID
0x14001e0ee  nop     dword ptr [rax+rax+00h]
0x14001e0f3  mov     esi, eax
0x14001e0f5  test    eax, eax
0x14001e0f7  js      short loc_14001E158
0x14001e0f9  lea     rdx, [rbp+GuidString]; Source
0x14001e0fd  mov     rcx, rdi; Destination
0x14001e100  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001e107  nop     dword ptr [rax+rax+00h]
0x14001e10c  movzx   r8d, word ptr [rbx+0CD0h]
0x14001e114  test    r8w, r8w
0x14001e118  jz      short loc_14001E155
0x14001e11a  movzx   edx, word ptr [rdi]
0x14001e11d  mov     rax, [rdi+8]
0x14001e121  mov     ecx, edx
0x14001e123  shr     rcx, 1
0x14001e126  mov     [rbp+DestinationString.Length], r14w
0x14001e12b  lea     rcx, [rax+rcx*2]
0x14001e12f  movzx   eax, word ptr [rdi+2]
0x14001e133  sub     ax, dx
0x14001e136  mov     [rbp+DestinationString.Buffer], rcx
0x14001e13a  lea     rdx, a04x; "-%04x"
0x14001e141  mov     [rbp+DestinationString.MaximumLength], ax
0x14001e145  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001e149  call    RtlUnicodeStringPrintf
0x14001e14e  movzx   eax, [rbp+DestinationString.Length]
0x14001e152  add     [rdi], ax
0x14001e155  mov     esi, r14d
0x14001e158  mov     rcx, [rbp+GuidString.Buffer]; P
0x14001e15c  test    rcx, rcx
0x14001e15f  jz      short loc_14001E172
0x14001e161  mov     edx, 636D6B56h; Tag
0x14001e166  call    cs:__imp_ExFreePoolWithTag
0x14001e16d  nop     dword ptr [rax+rax+00h]
0x14001e172  lea     r11, [rsp+50h+var_s0]
0x14001e177  mov     eax, esi
0x14001e179  mov     rbx, [r11+28h]
0x14001e17d  mov     rsi, [r11+30h]
0x14001e181  mov     rsp, r11
0x14001e184  pop     r14
0x14001e186  pop     rdi
0x14001e187  pop     rbp
0x14001e188  retn
```
