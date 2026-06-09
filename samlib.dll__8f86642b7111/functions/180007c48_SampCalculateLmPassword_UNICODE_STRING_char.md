# SampCalculateLmPassword(_UNICODE_STRING *,char * *)

- ea: `0x180007c48`
- end: `0x180007ceb`
- name: `?SampCalculateLmPassword@@YAJPEAU_UNICODE_STRING@@PEAPEAD@Z`
- size: `163`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, char **)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007e00`
- `0x18000b1c4`
- `0x18000ccb0`

## callees

- `0x180007c48`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007c76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007c76`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x180007caf`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x180007caf`

## pseudocode

```c
__int64 __fastcall SampCalculateLmPassword(PCUNICODE_STRING SourceString, char **a2)
{
  __int64 v2; // rbx
  CHAR *v5; // rax
  NTSTATUS v7; // ecx
  PCHAR Buffer; // rax
  _STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  v2 = 15;
  *a2 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v5 = (CHAR *)LocalAlloc(0x40u, 0xFu);
  DestinationString.Buffer = v5;
  if ( !v5 )
    return 3221225626LL;
  *(_DWORD *)&DestinationString.Length = 983055;
  *(_QWORD *)v5 = 0;
  *((_DWORD *)v5 + 2) = 0;
  *((_WORD *)v5 + 6) = 0;
  v5[14] = 0;
  v7 = RtlUpcaseUnicodeStringToOemString(&DestinationString, SourceString, 0);
  if ( v7 < 0 )
  {
    Buffer = DestinationString.Buffer;
    v7 = 1073741837;
    do
    {
      *Buffer++ = 0;
      --v2;
    }
    while ( v2 );
  }
  *a2 = DestinationString.Buffer;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007c48  mov     [rsp+arg_0], rbx
0x180007c4d  mov     [rsp+arg_8], rsi
0x180007c52  push    rdi
0x180007c53  sub     rsp, 30h
0x180007c57  mov     ebx, 0Fh
0x180007c5c  mov     qword ptr [rdx], 0
0x180007c63  mov     rdi, rdx
0x180007c66  mov     rsi, rcx
0x180007c69  xorps   xmm0, xmm0
0x180007c6c  mov     edx, ebx; uBytes
0x180007c6e  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180007c73  lea     ecx, [rbx+31h]; uFlags
0x180007c76  call    cs:__imp_LocalAlloc
0x180007c7c  mov     [rsp+38h+DestinationString.Buffer], rax
0x180007c81  test    rax, rax
0x180007c84  jnz     short loc_180007C8D
0x180007c86  mov     eax, 0C000009Ah
0x180007c8b  jmp     short loc_180007CDB
0x180007c8d  xor     ecx, ecx
0x180007c8f  mov     dword ptr [rsp+38h+DestinationString.Length], 0F000Fh
0x180007c97  mov     [rax], rcx
0x180007c9a  xor     r8d, r8d; AllocateDestinationString
0x180007c9d  mov     [rax+8], ecx
0x180007ca0  mov     rdx, rsi; SourceString
0x180007ca3  mov     [rax+0Ch], cx
0x180007ca7  mov     [rax+0Eh], cl
0x180007caa  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180007caf  call    cs:__imp_RtlUpcaseUnicodeStringToOemString
0x180007cb5  mov     ecx, eax
0x180007cb7  test    eax, eax
0x180007cb9  jns     short loc_180007CD1
0x180007cbb  mov     rax, [rsp+38h+DestinationString.Buffer]
0x180007cc0  mov     ecx, 4000000Dh
0x180007cc5  mov     byte ptr [rax], 0
0x180007cc8  inc     rax
0x180007ccb  sub     rbx, 1
0x180007ccf  jnz     short loc_180007CC5
0x180007cd1  mov     rax, [rsp+38h+DestinationString.Buffer]
0x180007cd6  mov     [rdi], rax
0x180007cd9  mov     eax, ecx
0x180007cdb  mov     rbx, [rsp+38h+arg_0]
0x180007ce0  mov     rsi, [rsp+38h+arg_8]
0x180007ce5  add     rsp, 30h
0x180007ce9  pop     rdi
0x180007cea  retn
```
