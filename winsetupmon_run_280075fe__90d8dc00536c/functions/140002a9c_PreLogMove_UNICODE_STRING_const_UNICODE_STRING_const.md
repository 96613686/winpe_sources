# PreLogMove(_UNICODE_STRING const *,_UNICODE_STRING const *)

- ea: `0x140002a9c`
- end: `0x140002b92`
- name: `?PreLogMove@@YAJPEBU_UNICODE_STRING@@0@Z`
- size: `246`
- prototype: `__int64 __fastcall(PCUNICODE_STRING StringIn, PCUNICODE_STRING)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e808`

## callees

- `0x140002488`
- `0x140002a9c`
- `0x140003944`

## import_xrefs

- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140002b2b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140002b5c`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140002b2b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140002b5c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140002b13`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140002b44`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140002b13`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140002b44`
- `ntoskrnl!KeReleaseMutex` at `0x140002b73`
- `ntoskrnl!KeReleaseMutex` at `0x140002b73`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002ac9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002ac9`

## pseudocode

```c
__int64 __fastcall PreLogMove(PCUNICODE_STRING StringIn, PCUNICODE_STRING a2)
{
  __int64 v4; // rdx
  NTSTATUS v5; // ebx

  KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
  if ( !byte_140019588 )
  {
    WriteLogMessage(1, L"Log location moving from %wZ to %wZ; will switch to in-memory logging", StringIn, a2);
    LOBYTE(v4) = 1;
    v5 = CloseLog(0, v4);
    if ( v5 < 0 )
      goto LABEL_6;
    byte_140019588 = 1;
  }
  RtlFreeUnicodeString(&StringOut);
  v5 = RtlDuplicateUnicodeString(0, StringIn, &StringOut);
  if ( v5 >= 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    v5 = RtlDuplicateUnicodeString(0, a2, &UnicodeString);
  }
LABEL_6:
  KeReleaseMutex(&Object, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140002a9c  mov     [rsp+arg_0], rbx
0x140002aa1  mov     [rsp+arg_8], rsi
0x140002aa6  push    rdi
0x140002aa7  sub     rsp, 30h
0x140002aab  mov     rdi, rdx
0x140002aae  mov     [rsp+38h+Timeout], 0; Timeout
0x140002ab7  mov     rsi, rcx
0x140002aba  xor     edx, edx; WaitReason
0x140002abc  lea     rcx, Object; Object
0x140002ac3  xor     r9d, r9d; Alertable
0x140002ac6  xor     r8d, r8d; WaitMode
0x140002ac9  call    cs:__imp_KeWaitForSingleObject
0x140002ad0  nop     dword ptr [rax+rax+00h]
0x140002ad5  mov     al, cs:byte_140019588
0x140002adb  test    al, al
0x140002add  jnz     short loc_140002B0C
0x140002adf  mov     r9, rdi
0x140002ae2  lea     rdx, aLogLocationMov_0; "Log location moving from %wZ to %wZ; wi"...
0x140002ae9  mov     r8, rsi
0x140002aec  mov     ecx, 1
0x140002af1  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140002af6  mov     dl, 1
0x140002af8  xor     ecx, ecx
0x140002afa  call    CloseLog
0x140002aff  mov     ebx, eax
0x140002b01  test    eax, eax
0x140002b03  js      short loc_140002B6A
0x140002b05  mov     cs:byte_140019588, 1
0x140002b0c  lea     rcx, StringOut; UnicodeString
0x140002b13  call    cs:__imp_RtlFreeUnicodeString
0x140002b1a  nop     dword ptr [rax+rax+00h]
0x140002b1f  lea     r8, StringOut; StringOut
0x140002b26  mov     rdx, rsi; StringIn
0x140002b29  xor     ecx, ecx; Flags
0x140002b2b  call    cs:__imp_RtlDuplicateUnicodeString
0x140002b32  nop     dword ptr [rax+rax+00h]
0x140002b37  mov     ebx, eax
0x140002b39  test    eax, eax
0x140002b3b  js      short loc_140002B6A
0x140002b3d  lea     rcx, UnicodeString; UnicodeString
0x140002b44  call    cs:__imp_RtlFreeUnicodeString
0x140002b4b  nop     dword ptr [rax+rax+00h]
0x140002b50  lea     r8, UnicodeString; StringOut
0x140002b57  mov     rdx, rdi; StringIn
0x140002b5a  xor     ecx, ecx; Flags
0x140002b5c  call    cs:__imp_RtlDuplicateUnicodeString
0x140002b63  nop     dword ptr [rax+rax+00h]
0x140002b68  mov     ebx, eax
0x140002b6a  xor     edx, edx; Wait
0x140002b6c  lea     rcx, Object; Mutex
0x140002b73  call    cs:__imp_KeReleaseMutex
0x140002b7a  nop     dword ptr [rax+rax+00h]
0x140002b7f  mov     rsi, [rsp+38h+arg_8]
0x140002b84  mov     eax, ebx
0x140002b86  mov     rbx, [rsp+38h+arg_0]
0x140002b8b  add     rsp, 30h
0x140002b8f  pop     rdi
0x140002b90  retn
```
