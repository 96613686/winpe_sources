# TdxExtractProtocolNumberFromDeviceString

- ea: `0x140012594`
- end: `0x140012619`
- name: `TdxExtractProtocolNumberFromDeviceString`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000bab0`

## callees

- `0x140012594`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400125e6`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400125e6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400125cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400125cd`

## pseudocode

```c
__int64 __fastcall TdxExtractProtocolNumberFromDeviceString(__int64 a1, _WORD *a2)
{
  bool v2; // cf
  __int64 v4; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  ULONG Value; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_WORD *)a1 < 4u;
  DestinationString = 0;
  Value = 0;
  if ( v2 )
    return 3221225473LL;
  v4 = *(_QWORD *)(a1 + 8);
  if ( *(_WORD *)v4 != 92 )
    return 3221225473LL;
  if ( !*(_WORD *)(v4 + 2) )
    return 3221225473LL;
  RtlInitUnicodeString(&DestinationString, (PCWSTR)(v4 + 2));
  if ( RtlUnicodeStringToInteger(&DestinationString, 0xAu, &Value) < 0 || Value > 0x100 )
    return 3221225473LL;
  *a2 = Value;
  return 0;
}

```

## disassembly

```asm
0x140012594  mov     [rsp+arg_8], rbx
0x140012599  push    rdi
0x14001259a  sub     rsp, 30h
0x14001259e  xor     edi, edi
0x1400125a0  xorps   xmm0, xmm0
0x1400125a3  cmp     word ptr [rcx], 4
0x1400125a7  mov     rbx, rdx
0x1400125aa  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400125af  mov     [rsp+38h+Value], edi
0x1400125b3  jb      short loc_140012608
0x1400125b5  mov     rax, [rcx+8]
0x1400125b9  cmp     word ptr [rax], 5Ch ; '\'
0x1400125bd  jnz     short loc_140012608
0x1400125bf  lea     rdx, [rax+2]; SourceString
0x1400125c3  cmp     [rdx], di
0x1400125c6  jz      short loc_140012608
0x1400125c8  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400125cd  call    cs:__imp_RtlInitUnicodeString
0x1400125d4  nop     dword ptr [rax+rax+00h]
0x1400125d9  lea     r8, [rsp+38h+Value]; Value
0x1400125de  lea     edx, [rdi+0Ah]; Base
0x1400125e1  lea     rcx, [rsp+38h+DestinationString]; String
0x1400125e6  call    cs:__imp_RtlUnicodeStringToInteger
0x1400125ed  nop     dword ptr [rax+rax+00h]
0x1400125f2  test    eax, eax
0x1400125f4  js      short loc_140012608
0x1400125f6  mov     eax, [rsp+38h+Value]
0x1400125fa  cmp     eax, 100h
0x1400125ff  ja      short loc_140012608
0x140012601  mov     [rbx], ax
0x140012604  xor     eax, eax
0x140012606  jmp     short loc_14001260D
0x140012608  mov     eax, 0C0000001h
0x14001260d  mov     rbx, [rsp+38h+arg_8]
0x140012612  add     rsp, 30h
0x140012616  pop     rdi
0x140012617  retn
```
