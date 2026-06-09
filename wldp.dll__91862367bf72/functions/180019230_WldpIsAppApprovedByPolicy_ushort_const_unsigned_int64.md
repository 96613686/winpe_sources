# WldpIsAppApprovedByPolicy(ushort const *,unsigned __int64)

- ea: `0x180019230`
- end: `0x180019290`
- name: `?WldpIsAppApprovedByPolicy@@YAJPEBG_K@Z`
- size: `96`
- prototype: `__int64 __fastcall(PCWSTR SourceString, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180019230`
- `0x18002a318`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180019254`
- `ntdll!RtlInitUnicodeString` at `0x180019254`
- `WINTRUST!ConfigCiPackageFamilyNameCheck` at `0x180019262`
- `WINTRUST!ConfigCiPackageFamilyNameCheck` at `0x180019262`

## pseudocode

```c
__int64 __fastcall WldpIsAppApprovedByPolicy(PCWSTR SourceString, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  struct _UNICODE_STRING v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  RtlInitUnicodeString(&v7, SourceString);
  v4 = ConfigCiPackageFamilyNameCheck(&v7, a2);
  v5 = v4;
  if ( v4 < 0 )
    WldpTraceLoggingIsAppApprovedByPolicy(SourceString, a2, (unsigned int)v4);
  return v5;
}

```

## disassembly

```asm
0x180019230  mov     rax, rsp
0x180019233  mov     [rax+8], rbx
0x180019237  mov     [rax+10h], rsi
0x18001923b  push    rdi
0x18001923c  sub     rsp, 30h
0x180019240  mov     rdi, rdx
0x180019243  mov     rsi, rcx
0x180019246  mov     rdx, rcx; SourceString
0x180019249  xorps   xmm0, xmm0
0x18001924c  lea     rcx, [rax-18h]; DestinationString
0x180019250  movups  xmmword ptr [rax-18h], xmm0
0x180019254  call    cs:__imp_RtlInitUnicodeString
0x18001925a  mov     rdx, rdi
0x18001925d  lea     rcx, [rsp+38h+var_18]
0x180019262  call    cs:__imp_ConfigCiPackageFamilyNameCheck
0x180019268  mov     ebx, eax
0x18001926a  test    eax, eax
0x18001926c  js      short loc_180019280
0x18001926e  mov     rsi, [rsp+38h+arg_8]
0x180019273  mov     eax, ebx
0x180019275  mov     rbx, [rsp+38h+arg_0]
0x18001927a  add     rsp, 30h
0x18001927e  pop     rdi
0x18001927f  retn
0x180019280  mov     r8d, ebx
0x180019283  mov     rdx, rdi
0x180019286  mov     rcx, rsi
0x180019289  call    WldpTraceLoggingIsAppApprovedByPolicy
0x18001928e  jmp     short loc_18001926E
```
