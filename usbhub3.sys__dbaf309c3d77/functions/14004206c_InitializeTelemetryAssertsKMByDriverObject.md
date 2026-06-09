# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x14004206c`
- end: `0x14004216b`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14009403c`

## callees

- `0x14004206c`
- `0x140042174`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400420eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400420eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400420a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400420a5`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400420b8`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400420b8`
- `ntoskrnl!RtlFreeAnsiString` at `0x140042151`
- `ntoskrnl!RtlFreeAnsiString` at `0x140042151`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400420d7`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400420d7`
- `ntoskrnl!RtlInitAnsiString` at `0x14004212d`
- `ntoskrnl!RtlInitAnsiString` at `0x14004212d`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 v4; // rcx
  bool v5; // zf
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
  struct _STRING v8; // [rsp+40h] [rbp-20h] BYREF
  struct _STRING v9; // [rsp+50h] [rbp-10h] BYREF

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
      v4 = (unsigned int)AnsiString.Length - 1;
      if ( AnsiString.Length != 1 )
      {
        while ( AnsiString.Buffer[v4] != 92 )
        {
          v5 = (_DWORD)v4 == 1;
          v4 = (unsigned int)(v4 - 1);
          if ( v5 )
            goto LABEL_11;
        }
        if ( (_DWORD)v4 != AnsiString.Length )
        {
          v8 = 0;
          RtlInitAnsiString(&v8, &AnsiString.Buffer[(unsigned int)(v4 + 1)]);
          v9 = v8;
          v3 = InitializeTelemetryAssertsKMWorkerInternal(&v9);
        }
      }
LABEL_11:
      RtlFreeAnsiString(&AnsiString);
    }
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x14004206c  mov     [rsp-8+arg_0], rbx
0x140042071  push    rbp
0x140042072  mov     rbp, rsp
0x140042075  sub     rsp, 60h
0x140042079  xorps   xmm0, xmm0
0x14004207c  xorps   xmm1, xmm1
0x14004207f  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x140042083  mov     rbx, rcx
0x140042086  xor     eax, eax
0x140042088  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14004208c  lock xadd cs:g_AssertsOperational, eax
0x140042094  test    eax, eax
0x140042096  jz      short loc_14004209F
0x140042098  xor     eax, eax
0x14004209a  jmp     loc_14004215F
0x14004209f  xor     edx, edx; SourceString
0x1400420a1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400420a5  call    cs:__imp_RtlInitUnicodeString
0x1400420ac  nop     dword ptr [rax+rax+00h]
0x1400420b1  lea     rdx, [rbp+DestinationString]
0x1400420b5  mov     rcx, rbx
0x1400420b8  call    cs:__imp_IoQueryFullDriverPath
0x1400420bf  nop     dword ptr [rax+rax+00h]
0x1400420c4  test    eax, eax
0x1400420c6  js      loc_14004215F
0x1400420cc  mov     r8b, 1; AllocateDestinationString
0x1400420cf  lea     rdx, [rbp+DestinationString]; SourceString
0x1400420d3  lea     rcx, [rbp+AnsiString]; DestinationString
0x1400420d7  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1400420de  nop     dword ptr [rax+rax+00h]
0x1400420e3  mov     rcx, [rbp+DestinationString.Buffer]; P
0x1400420e7  xor     edx, edx; Tag
0x1400420e9  mov     ebx, eax
0x1400420eb  call    cs:__imp_ExFreePoolWithTag
0x1400420f2  nop     dword ptr [rax+rax+00h]
0x1400420f7  test    ebx, ebx
0x1400420f9  js      short loc_14004215D
0x1400420fb  movzx   edx, [rbp+AnsiString.Length]
0x1400420ff  lea     ecx, [rdx-1]
0x140042102  test    ecx, ecx
0x140042104  jz      short loc_14004214D
0x140042106  mov     r8, [rbp+AnsiString.Buffer]
0x14004210a  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14004210f  jz      short loc_140042118
0x140042111  add     ecx, 0FFFFFFFFh
0x140042114  jnz     short loc_14004210A
0x140042116  jmp     short loc_14004214D
0x140042118  cmp     ecx, edx
0x14004211a  jz      short loc_14004214D
0x14004211c  lea     edx, [rcx+1]
0x14004211f  xorps   xmm0, xmm0
0x140042122  add     rdx, r8; SourceString
0x140042125  lea     rcx, [rbp+var_20]; DestinationString
0x140042129  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14004212d  call    cs:__imp_RtlInitAnsiString
0x140042134  nop     dword ptr [rax+rax+00h]
0x140042139  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x14004213d  lea     rcx, [rbp+var_10]
0x140042141  movdqa  [rbp+var_10], xmm0
0x140042146  call    InitializeTelemetryAssertsKMWorkerInternal
0x14004214b  mov     ebx, eax
0x14004214d  lea     rcx, [rbp+AnsiString]; AnsiString
0x140042151  call    cs:__imp_RtlFreeAnsiString
0x140042158  nop     dword ptr [rax+rax+00h]
0x14004215d  mov     eax, ebx
0x14004215f  mov     rbx, [rsp+60h+arg_0]
0x140042164  add     rsp, 60h
0x140042168  pop     rbp
0x140042169  retn
```
