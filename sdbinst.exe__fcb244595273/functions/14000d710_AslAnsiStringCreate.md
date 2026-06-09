# AslAnsiStringCreate

- ea: `0x14000d710`
- end: `0x14000d7af`
- name: `AslAnsiStringCreate`
- size: `159`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000c1a0`

## callees

- `0x14000d710`
- `0x14001008c`
- `0x140010f80`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x14000d77d`
- `ntdll!RtlInitAnsiString` at `0x14000d77d`
- `ntdll!RtlFreeHeap` at `0x14000d79c`
- `ntdll!RtlFreeHeap` at `0x14000d79c`

## string_xrefs

- `0x14000d758`: `AslAnsiStringCreate`

## pseudocode

```c
__int64 __fastcall AslAnsiStringCreate(PANSI_STRING DestinationString)
{
  int v2; // eax
  unsigned int v3; // ebx
  char *v4; // r8
  PCSZ SourceString; // [rsp+48h] [rbp+10h] BYREF

  SourceString = 0;
  *DestinationString = 0;
  v2 = AslStringDuplicateA(&SourceString);
  v3 = v2;
  if ( v2 >= 0 )
  {
    RtlInitAnsiString(DestinationString, SourceString);
    v4 = 0;
    v3 = 0;
  }
  else
  {
    AslLogCallPrintf(
      1,
      "AslAnsiStringCreate",
      1039,
      "AslStringDuplicate failed with \"%s\" [%x]",
      (const char *)&dword_1400326D4,
      v2);
    v4 = (char *)SourceString;
  }
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return v3;
}

```

## disassembly

```asm
0x14000d710  mov     rax, rsp
0x14000d713  mov     [rax+8], rbx
0x14000d717  mov     [rax+10h], rdx
0x14000d71b  push    rdi
0x14000d71c  sub     rsp, 30h
0x14000d720  xorps   xmm0, xmm0
0x14000d723  mov     qword ptr [rax+10h], 0
0x14000d72b  movups  xmmword ptr [rcx], xmm0
0x14000d72e  mov     rdi, rcx
0x14000d731  lea     rcx, [rax+10h]
0x14000d735  call    AslStringDuplicateA
0x14000d73a  mov     ebx, eax
0x14000d73c  test    eax, eax
0x14000d73e  jns     short loc_14000D775
0x14000d740  mov     [rsp+38h+var_10], eax
0x14000d744  lea     r9, aAslstringdupli; "AslStringDuplicate failed with \"%s\" ["...
0x14000d74b  lea     rax, dword_1400326D4
0x14000d752  mov     r8d, 40Fh
0x14000d758  lea     rdx, aAslansistringc; "AslAnsiStringCreate"
0x14000d75f  mov     [rsp+38h+var_18], rax
0x14000d764  mov     ecx, 1
0x14000d769  call    AslLogCallPrintf
0x14000d76e  mov     r8, [rsp+38h+SourceString]
0x14000d773  jmp     short loc_14000D788
0x14000d775  mov     rdx, [rsp+38h+SourceString]; SourceString
0x14000d77a  mov     rcx, rdi; DestinationString
0x14000d77d  call    cs:__imp_RtlInitAnsiString
0x14000d783  xor     r8d, r8d; P
0x14000d786  xor     ebx, ebx
0x14000d788  test    r8, r8
0x14000d78b  jz      short loc_14000D7A2
0x14000d78d  mov     rcx, gs:60h
0x14000d796  xor     edx, edx; Flags
0x14000d798  mov     rcx, [rcx+30h]; HeapHandle
0x14000d79c  call    cs:__imp_RtlFreeHeap
0x14000d7a2  mov     eax, ebx
0x14000d7a4  mov     rbx, [rsp+38h+arg_0]
0x14000d7a9  add     rsp, 30h
0x14000d7ad  pop     rdi
0x14000d7ae  retn
```
