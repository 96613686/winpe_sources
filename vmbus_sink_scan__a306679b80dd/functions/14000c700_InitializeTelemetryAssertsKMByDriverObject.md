# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x14000c700`
- end: `0x14000c7fc`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003003c`

## callees

- `0x14000c700`
- `0x14000c804`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c77f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c77f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c739`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c739`
- `ntoskrnl!RtlInitAnsiString` at `0x14000c7be`
- `ntoskrnl!RtlInitAnsiString` at `0x14000c7be`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14000c76b`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14000c76b`
- `ntoskrnl!RtlFreeAnsiString` at `0x14000c7e2`
- `ntoskrnl!RtlFreeAnsiString` at `0x14000c7e2`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14000c74c`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14000c74c`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  int v3; // ebx
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
            v3 = InitializeTelemetryAssertsKMWorkerInternal((const void **)&v8);
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
0x14000c700  mov     [rsp-8+arg_0], rbx
0x14000c705  push    rbp
0x14000c706  mov     rbp, rsp
0x14000c709  sub     rsp, 60h
0x14000c70d  xorps   xmm0, xmm0
0x14000c710  xorps   xmm1, xmm1
0x14000c713  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x14000c717  mov     rbx, rcx
0x14000c71a  xor     eax, eax
0x14000c71c  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14000c720  lock xadd cs:g_AssertsOperational, eax
0x14000c728  test    eax, eax
0x14000c72a  jz      short loc_14000C733
0x14000c72c  xor     eax, eax
0x14000c72e  jmp     loc_14000C7F0
0x14000c733  xor     edx, edx; SourceString
0x14000c735  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000c739  call    cs:__imp_RtlInitUnicodeString
0x14000c740  nop     dword ptr [rax+rax+00h]
0x14000c745  lea     rdx, [rbp+DestinationString]
0x14000c749  mov     rcx, rbx
0x14000c74c  call    cs:__imp_IoQueryFullDriverPath
0x14000c753  nop     dword ptr [rax+rax+00h]
0x14000c758  test    eax, eax
0x14000c75a  js      loc_14000C7F0
0x14000c760  mov     r8b, 1; AllocateDestinationString
0x14000c763  lea     rdx, [rbp+DestinationString]; SourceString
0x14000c767  lea     rcx, [rbp+AnsiString]; DestinationString
0x14000c76b  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14000c772  nop     dword ptr [rax+rax+00h]
0x14000c777  mov     rcx, [rbp+DestinationString.Buffer]; P
0x14000c77b  xor     edx, edx; Tag
0x14000c77d  mov     ebx, eax
0x14000c77f  call    cs:__imp_ExFreePoolWithTag
0x14000c786  nop     dword ptr [rax+rax+00h]
0x14000c78b  test    ebx, ebx
0x14000c78d  js      short loc_14000C7EE
0x14000c78f  movzx   edx, [rbp+AnsiString.Length]
0x14000c793  mov     r8, [rbp+AnsiString.Buffer]
0x14000c797  lea     ecx, [rdx-1]
0x14000c79a  test    ecx, ecx
0x14000c79c  jz      short loc_14000C7DE
0x14000c79e  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14000c7a3  jz      short loc_14000C7A9
0x14000c7a5  dec     ecx
0x14000c7a7  jmp     short loc_14000C79A
0x14000c7a9  cmp     ecx, edx
0x14000c7ab  jz      short loc_14000C7DE
0x14000c7ad  lea     edx, [rcx+1]
0x14000c7b0  xorps   xmm0, xmm0
0x14000c7b3  add     rdx, r8; SourceString
0x14000c7b6  lea     rcx, [rbp+var_20]; DestinationString
0x14000c7ba  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14000c7be  call    cs:__imp_RtlInitAnsiString
0x14000c7c5  nop     dword ptr [rax+rax+00h]
0x14000c7ca  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x14000c7ce  lea     rcx, [rbp+var_10]
0x14000c7d2  movdqa  [rbp+var_10], xmm0
0x14000c7d7  call    InitializeTelemetryAssertsKMWorkerInternal
0x14000c7dc  mov     ebx, eax
0x14000c7de  lea     rcx, [rbp+AnsiString]; AnsiString
0x14000c7e2  call    cs:__imp_RtlFreeAnsiString
0x14000c7e9  nop     dword ptr [rax+rax+00h]
0x14000c7ee  mov     eax, ebx
0x14000c7f0  mov     rbx, [rsp+60h+arg_0]
0x14000c7f5  add     rsp, 60h
0x14000c7f9  pop     rbp
0x14000c7fa  retn
```
