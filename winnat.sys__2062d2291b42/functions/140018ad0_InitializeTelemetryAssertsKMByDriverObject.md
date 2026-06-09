# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x140018ad0`
- end: `0x140018bcc`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140036078`

## callees

- `0x140018ad0`
- `0x140018bd4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140018b09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018b09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b4f`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140018b1c`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140018b1c`
- `ntoskrnl!RtlFreeAnsiString` at `0x140018bb2`
- `ntoskrnl!RtlFreeAnsiString` at `0x140018bb2`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140018b3b`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140018b3b`
- `ntoskrnl!RtlInitAnsiString` at `0x140018b8e`
- `ntoskrnl!RtlInitAnsiString` at `0x140018b8e`

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
0x140018ad0  mov     [rsp-8+arg_0], rbx
0x140018ad5  push    rbp
0x140018ad6  mov     rbp, rsp
0x140018ad9  sub     rsp, 60h
0x140018add  xorps   xmm0, xmm0
0x140018ae0  xorps   xmm1, xmm1
0x140018ae3  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x140018ae7  mov     rbx, rcx
0x140018aea  xor     eax, eax
0x140018aec  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140018af0  lock xadd cs:g_AssertsOperational, eax
0x140018af8  test    eax, eax
0x140018afa  jz      short loc_140018B03
0x140018afc  xor     eax, eax
0x140018afe  jmp     loc_140018BC0
0x140018b03  xor     edx, edx; SourceString
0x140018b05  lea     rcx, [rbp+DestinationString]; DestinationString
0x140018b09  call    cs:__imp_RtlInitUnicodeString
0x140018b10  nop     dword ptr [rax+rax+00h]
0x140018b15  lea     rdx, [rbp+DestinationString]
0x140018b19  mov     rcx, rbx
0x140018b1c  call    cs:__imp_IoQueryFullDriverPath
0x140018b23  nop     dword ptr [rax+rax+00h]
0x140018b28  test    eax, eax
0x140018b2a  js      loc_140018BC0
0x140018b30  mov     r8b, 1; AllocateDestinationString
0x140018b33  lea     rdx, [rbp+DestinationString]; SourceString
0x140018b37  lea     rcx, [rbp+AnsiString]; DestinationString
0x140018b3b  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140018b42  nop     dword ptr [rax+rax+00h]
0x140018b47  mov     rcx, [rbp+DestinationString.Buffer]; P
0x140018b4b  xor     edx, edx; Tag
0x140018b4d  mov     ebx, eax
0x140018b4f  call    cs:__imp_ExFreePoolWithTag
0x140018b56  nop     dword ptr [rax+rax+00h]
0x140018b5b  test    ebx, ebx
0x140018b5d  js      short loc_140018BBE
0x140018b5f  movzx   edx, [rbp+AnsiString.Length]
0x140018b63  mov     r8, [rbp+AnsiString.Buffer]
0x140018b67  lea     ecx, [rdx-1]
0x140018b6a  test    ecx, ecx
0x140018b6c  jz      short loc_140018BAE
0x140018b6e  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140018b73  jz      short loc_140018B79
0x140018b75  dec     ecx
0x140018b77  jmp     short loc_140018B6A
0x140018b79  cmp     ecx, edx
0x140018b7b  jz      short loc_140018BAE
0x140018b7d  lea     edx, [rcx+1]
0x140018b80  xorps   xmm0, xmm0
0x140018b83  add     rdx, r8; SourceString
0x140018b86  lea     rcx, [rbp+var_20]; DestinationString
0x140018b8a  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140018b8e  call    cs:__imp_RtlInitAnsiString
0x140018b95  nop     dword ptr [rax+rax+00h]
0x140018b9a  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x140018b9e  lea     rcx, [rbp+var_10]
0x140018ba2  movdqa  [rbp+var_10], xmm0
0x140018ba7  call    InitializeTelemetryAssertsKMWorkerInternal
0x140018bac  mov     ebx, eax
0x140018bae  lea     rcx, [rbp+AnsiString]; AnsiString
0x140018bb2  call    cs:__imp_RtlFreeAnsiString
0x140018bb9  nop     dword ptr [rax+rax+00h]
0x140018bbe  mov     eax, ebx
0x140018bc0  mov     rbx, [rsp+60h+arg_0]
0x140018bc5  add     rsp, 60h
0x140018bc9  pop     rbp
0x140018bca  retn
```
