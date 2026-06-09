# HasTrackedPath(_UNICODE_STRING const *)

- ea: `0x140006578`
- end: `0x1400065f7`
- name: `?HasTrackedPath@@YAEPEBU_UNICODE_STRING@@@Z`
- size: `127`
- prototype: `unsigned __int8 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f6c0`

## callees

- `0x140006578`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400065d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400065d7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006594`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006594`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400065b3`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400065b3`

## pseudocode

```c
char __fastcall HasTrackedPath(PCUNICODE_STRING String2)
{
  char v2; // di
  char *i; // rbx

  v2 = 0;
  ExAcquireFastMutex(&stru_140019468);
  for ( i = (char *)qword_140019448; i; i = *(char **)i )
  {
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)(i + 8), String2, 1u) )
    {
      v2 = 1;
      break;
    }
  }
  ExReleaseFastMutex(&stru_140019468);
  return v2;
}

```

## disassembly

```asm
0x140006578  mov     [rsp+arg_0], rbx
0x14000657d  mov     [rsp+arg_8], rsi
0x140006582  push    rdi
0x140006583  sub     rsp, 20h
0x140006587  mov     rsi, rcx
0x14000658a  xor     dil, dil
0x14000658d  lea     rcx, stru_140019468; FastMutex
0x140006594  call    cs:__imp_ExAcquireFastMutex
0x14000659b  nop     dword ptr [rax+rax+00h]
0x1400065a0  mov     rbx, cs:qword_140019448
0x1400065a7  jmp     short loc_1400065C6
0x1400065a9  lea     rcx, [rbx+8]; String1
0x1400065ad  mov     r8b, 1; CaseInSensitive
0x1400065b0  mov     rdx, rsi; String2
0x1400065b3  call    cs:__imp_RtlEqualUnicodeString
0x1400065ba  nop     dword ptr [rax+rax+00h]
0x1400065bf  test    al, al
0x1400065c1  jnz     short loc_1400065CD
0x1400065c3  mov     rbx, [rbx]
0x1400065c6  test    rbx, rbx
0x1400065c9  jnz     short loc_1400065A9
0x1400065cb  jmp     short loc_1400065D0
0x1400065cd  mov     dil, 1
0x1400065d0  lea     rcx, stru_140019468; FastMutex
0x1400065d7  call    cs:__imp_ExReleaseFastMutex
0x1400065de  nop     dword ptr [rax+rax+00h]
0x1400065e3  mov     rbx, [rsp+28h+arg_0]
0x1400065e8  mov     al, dil
0x1400065eb  mov     rsi, [rsp+28h+arg_8]
0x1400065f0  add     rsp, 20h
0x1400065f4  pop     rdi
0x1400065f5  retn
```
