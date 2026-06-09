# SclLoadStringResource

- ea: `0x180007d60`
- end: `0x180007df0`
- name: `SclLoadStringResource`
- size: `144`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *, ULONG)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180007d60`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x180007dc2`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180007dc2`
- `ntdll!RtlInitAnsiString` at `0x180007db1`
- `ntdll!RtlInitAnsiString` at `0x180007db1`
- `ntdll!RtlFindMessage` at `0x180007d91`
- `ntdll!RtlFindMessage` at `0x180007d91`
- `ntdll!RtlCreateUnicodeString` at `0x180007dd3`
- `ntdll!RtlCreateUnicodeString` at `0x180007dd3`

## pseudocode

```c
__int64 __fastcall SclLoadStringResource(void *a1, struct _UNICODE_STRING *a2, ULONG a3)
{
  NTSTATUS Message; // ebx
  _STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  PMESSAGE_RESOURCE_ENTRY MessageResourceEntry; // [rsp+68h] [rbp+20h] BYREF

  MessageResourceEntry = 0;
  DestinationString = 0;
  Message = RtlFindMessage(a1, 0xBu, 0, a3, &MessageResourceEntry);
  if ( Message >= 0 )
  {
    if ( (MessageResourceEntry->Flags & 1) != 0 )
    {
      if ( !RtlCreateUnicodeString(a2, (PCWSTR)MessageResourceEntry->Text) )
        return (unsigned int)-1073741823;
    }
    else
    {
      RtlInitAnsiString(&DestinationString, (PCSZ)MessageResourceEntry->Text);
      return (unsigned int)RtlAnsiStringToUnicodeString(a2, &DestinationString, 1u);
    }
  }
  return (unsigned int)Message;
}

```

## disassembly

```asm
0x180007d60  mov     rax, rsp
0x180007d63  mov     [rax+8], rbx
0x180007d67  push    rdi
0x180007d68  sub     rsp, 40h
0x180007d6c  mov     r9d, r8d; MessageId
0x180007d6f  mov     qword ptr [rax+20h], 0
0x180007d77  xor     r8d, r8d; Language
0x180007d7a  lea     rax, [rax+20h]
0x180007d7e  xorps   xmm0, xmm0
0x180007d81  mov     [rsp+48h+MessageResourceEntry], rax; MessageResourceEntry
0x180007d86  movups  xmmword ptr [rax-38h], xmm0
0x180007d8a  mov     rdi, rdx
0x180007d8d  lea     edx, [r8+0Bh]; Type
0x180007d91  call    cs:__imp_RtlFindMessage
0x180007d97  mov     ebx, eax
0x180007d99  test    eax, eax
0x180007d9b  js      short loc_180007DE3
0x180007d9d  mov     rdx, [rsp+48h+arg_18]
0x180007da2  test    byte ptr [rdx+2], 1
0x180007da6  jnz     short loc_180007DCC
0x180007da8  add     rdx, 4; SourceString
0x180007dac  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180007db1  call    cs:__imp_RtlInitAnsiString
0x180007db7  mov     r8b, 1; AllocateDestinationString
0x180007dba  lea     rdx, [rsp+48h+DestinationString]; SourceString
0x180007dbf  mov     rcx, rdi; DestinationString
0x180007dc2  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180007dc8  mov     ebx, eax
0x180007dca  jmp     short loc_180007DE3
0x180007dcc  add     rdx, 4; SourceString
0x180007dd0  mov     rcx, rdi; DestinationString
0x180007dd3  call    cs:__imp_RtlCreateUnicodeString
0x180007dd9  test    al, al
0x180007ddb  mov     ecx, 0C0000001h
0x180007de0  cmovz   ebx, ecx
0x180007de3  mov     eax, ebx
0x180007de5  mov     rbx, [rsp+48h+arg_0]
0x180007dea  add     rsp, 40h
0x180007dee  pop     rdi
0x180007def  retn
```
