# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x1400185f0`
- end: `0x1400186ec`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140035078`

## callees

- `0x1400185f0`
- `0x1400186f4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140018629`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018629`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001866f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001866f`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14001863c`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14001863c`
- `ntoskrnl!RtlFreeAnsiString` at `0x1400186d2`
- `ntoskrnl!RtlFreeAnsiString` at `0x1400186d2`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14001865b`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14001865b`
- `ntoskrnl!RtlInitAnsiString` at `0x1400186ae`
- `ntoskrnl!RtlInitAnsiString` at `0x1400186ae`

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
0x1400185f0  mov     [rsp-8+arg_0], rbx
0x1400185f5  push    rbp
0x1400185f6  mov     rbp, rsp
0x1400185f9  sub     rsp, 60h
0x1400185fd  xorps   xmm0, xmm0
0x140018600  xorps   xmm1, xmm1
0x140018603  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x140018607  mov     rbx, rcx
0x14001860a  xor     eax, eax
0x14001860c  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140018610  lock xadd cs:g_AssertsOperational, eax
0x140018618  test    eax, eax
0x14001861a  jz      short loc_140018623
0x14001861c  xor     eax, eax
0x14001861e  jmp     loc_1400186E0
0x140018623  xor     edx, edx; SourceString
0x140018625  lea     rcx, [rbp+DestinationString]; DestinationString
0x140018629  call    cs:__imp_RtlInitUnicodeString
0x140018630  nop     dword ptr [rax+rax+00h]
0x140018635  lea     rdx, [rbp+DestinationString]
0x140018639  mov     rcx, rbx
0x14001863c  call    cs:__imp_IoQueryFullDriverPath
0x140018643  nop     dword ptr [rax+rax+00h]
0x140018648  test    eax, eax
0x14001864a  js      loc_1400186E0
0x140018650  mov     r8b, 1; AllocateDestinationString
0x140018653  lea     rdx, [rbp+DestinationString]; SourceString
0x140018657  lea     rcx, [rbp+AnsiString]; DestinationString
0x14001865b  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140018662  nop     dword ptr [rax+rax+00h]
0x140018667  mov     rcx, [rbp+DestinationString.Buffer]; P
0x14001866b  xor     edx, edx; Tag
0x14001866d  mov     ebx, eax
0x14001866f  call    cs:__imp_ExFreePoolWithTag
0x140018676  nop     dword ptr [rax+rax+00h]
0x14001867b  test    ebx, ebx
0x14001867d  js      short loc_1400186DE
0x14001867f  movzx   edx, [rbp+AnsiString.Length]
0x140018683  mov     r8, [rbp+AnsiString.Buffer]
0x140018687  lea     ecx, [rdx-1]
0x14001868a  test    ecx, ecx
0x14001868c  jz      short loc_1400186CE
0x14001868e  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140018693  jz      short loc_140018699
0x140018695  dec     ecx
0x140018697  jmp     short loc_14001868A
0x140018699  cmp     ecx, edx
0x14001869b  jz      short loc_1400186CE
0x14001869d  lea     edx, [rcx+1]
0x1400186a0  xorps   xmm0, xmm0
0x1400186a3  add     rdx, r8; SourceString
0x1400186a6  lea     rcx, [rbp+var_20]; DestinationString
0x1400186aa  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x1400186ae  call    cs:__imp_RtlInitAnsiString
0x1400186b5  nop     dword ptr [rax+rax+00h]
0x1400186ba  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x1400186be  lea     rcx, [rbp+var_10]
0x1400186c2  movdqa  [rbp+var_10], xmm0
0x1400186c7  call    InitializeTelemetryAssertsKMWorkerInternal
0x1400186cc  mov     ebx, eax
0x1400186ce  lea     rcx, [rbp+AnsiString]; AnsiString
0x1400186d2  call    cs:__imp_RtlFreeAnsiString
0x1400186d9  nop     dword ptr [rax+rax+00h]
0x1400186de  mov     eax, ebx
0x1400186e0  mov     rbx, [rsp+60h+arg_0]
0x1400186e5  add     rsp, 60h
0x1400186e9  pop     rbp
0x1400186ea  retn
```
