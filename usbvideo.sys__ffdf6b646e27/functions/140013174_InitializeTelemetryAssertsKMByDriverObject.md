# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x140013174`
- end: `0x140013270`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14005e078`

## callees

- `0x140013174`
- `0x140019030`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400131ad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400131ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131f3`
- `ntoskrnl!RtlFreeAnsiString` at `0x140013256`
- `ntoskrnl!RtlFreeAnsiString` at `0x140013256`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400131df`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400131df`
- `ntoskrnl!RtlInitAnsiString` at `0x140013232`
- `ntoskrnl!RtlInitAnsiString` at `0x140013232`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400131c0`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400131c0`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 i; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
  struct _STRING v7; // [rsp+40h] [rbp-20h] BYREF
  struct _STRING v8; // [rsp+50h] [rbp-10h] BYREF

  AnsiString = 0;
  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return 0;
  RtlInitUnicodeString(&DestinationString, 0);
  result = IoQueryFullDriverPath(a1, &DestinationString);
  if ( (int)result >= 0 )
  {
    v3 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    if ( v3 >= 0 )
    {
      for ( i = (unsigned int)AnsiString.Length - 1; (_DWORD)i; i = (unsigned int)(i - 1) )
      {
        if ( AnsiString.Buffer[i] == 92 )
        {
          if ( (_DWORD)i != AnsiString.Length )
          {
            v7 = 0;
            RtlInitAnsiString(&v7, &AnsiString.Buffer[(unsigned int)(i + 1)]);
            v8 = v7;
            v3 = InitializeTelemetryAssertsKMWorkerInternal(&v8);
          }
          break;
        }
      }
      RtlFreeAnsiString(&AnsiString);
    }
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x140013174  mov     [rsp-8+arg_0], rbx
0x140013179  push    rbp
0x14001317a  mov     rbp, rsp
0x14001317d  sub     rsp, 60h
0x140013181  xorps   xmm0, xmm0
0x140013184  xorps   xmm1, xmm1
0x140013187  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x14001318b  mov     rbx, rcx
0x14001318e  xor     eax, eax
0x140013190  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140013194  lock xadd cs:g_AssertsOperational, eax
0x14001319c  test    eax, eax
0x14001319e  jz      short loc_1400131A7
0x1400131a0  xor     eax, eax
0x1400131a2  jmp     loc_140013264
0x1400131a7  xor     edx, edx; SourceString
0x1400131a9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400131ad  call    cs:__imp_RtlInitUnicodeString
0x1400131b4  nop     dword ptr [rax+rax+00h]
0x1400131b9  lea     rdx, [rbp+DestinationString]
0x1400131bd  mov     rcx, rbx
0x1400131c0  call    cs:__imp_IoQueryFullDriverPath
0x1400131c7  nop     dword ptr [rax+rax+00h]
0x1400131cc  test    eax, eax
0x1400131ce  js      loc_140013264
0x1400131d4  mov     r8b, 1; AllocateDestinationString
0x1400131d7  lea     rdx, [rbp+DestinationString]; SourceString
0x1400131db  lea     rcx, [rbp+AnsiString]; DestinationString
0x1400131df  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1400131e6  nop     dword ptr [rax+rax+00h]
0x1400131eb  mov     rcx, [rbp+DestinationString.Buffer]; P
0x1400131ef  xor     edx, edx; Tag
0x1400131f1  mov     ebx, eax
0x1400131f3  call    cs:__imp_ExFreePoolWithTag
0x1400131fa  nop     dword ptr [rax+rax+00h]
0x1400131ff  test    ebx, ebx
0x140013201  js      short loc_140013262
0x140013203  movzx   edx, [rbp+AnsiString.Length]
0x140013207  mov     r8, [rbp+AnsiString.Buffer]
0x14001320b  lea     ecx, [rdx-1]
0x14001320e  test    ecx, ecx
0x140013210  jz      short loc_140013252
0x140013212  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140013217  jz      short loc_14001321D
0x140013219  dec     ecx
0x14001321b  jmp     short loc_14001320E
0x14001321d  cmp     ecx, edx
0x14001321f  jz      short loc_140013252
0x140013221  lea     edx, [rcx+1]
0x140013224  xorps   xmm0, xmm0
0x140013227  add     rdx, r8; SourceString
0x14001322a  lea     rcx, [rbp+var_20]; DestinationString
0x14001322e  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140013232  call    cs:__imp_RtlInitAnsiString
0x140013239  nop     dword ptr [rax+rax+00h]
0x14001323e  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x140013242  lea     rcx, [rbp+var_10]
0x140013246  movdqa  [rbp+var_10], xmm0
0x14001324b  call    InitializeTelemetryAssertsKMWorkerInternal
0x140013250  mov     ebx, eax
0x140013252  lea     rcx, [rbp+AnsiString]; AnsiString
0x140013256  call    cs:__imp_RtlFreeAnsiString
0x14001325d  nop     dword ptr [rax+rax+00h]
0x140013262  mov     eax, ebx
0x140013264  mov     rbx, [rsp+60h+arg_0]
0x140013269  add     rsp, 60h
0x14001326d  pop     rbp
0x14001326e  retn
```
