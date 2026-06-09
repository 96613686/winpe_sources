# EfiApiGetProcedureAddress

- ea: `0x180014040`
- end: `0x18001408e`
- name: `EfiApiGetProcedureAddress`
- size: `78`
- prototype: `PVOID __fastcall(PVOID BaseAddress, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014094`

## callees

- `0x180014040`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x18001405f`
- `ntdll!RtlInitAnsiString` at `0x18001405f`
- `ntdll!LdrGetProcedureAddress` at `0x180014075`
- `ntdll!LdrGetProcedureAddress` at `0x180014075`

## pseudocode

```c
PVOID __fastcall EfiApiGetProcedureAddress(PVOID BaseAddress, const char *a2)
{
  struct _STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  PVOID ProcedureAddress; // [rsp+50h] [rbp+18h] BYREF

  ProcedureAddress = 0;
  DestinationString = 0;
  RtlInitAnsiString(&DestinationString, a2);
  if ( LdrGetProcedureAddress(BaseAddress, &DestinationString, 0, &ProcedureAddress) >= 0 )
    return ProcedureAddress;
  else
    return 0;
}

```

## disassembly

```asm
0x180014040  push    rbx
0x180014042  sub     rsp, 30h
0x180014046  mov     rbx, rcx
0x180014049  mov     [rsp+38h+ProcedureAddress], 0
0x180014052  xorps   xmm0, xmm0
0x180014055  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x18001405a  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x18001405f  call    cs:__imp_RtlInitAnsiString
0x180014065  lea     r9, [rsp+38h+ProcedureAddress]; ProcedureAddress
0x18001406a  xor     r8d, r8d; Ordinal
0x18001406d  lea     rdx, [rsp+38h+DestinationString]; Name
0x180014072  mov     rcx, rbx; BaseAddress
0x180014075  call    cs:__imp_LdrGetProcedureAddress
0x18001407b  test    eax, eax
0x18001407d  jns     short loc_180014083
0x18001407f  xor     eax, eax
0x180014081  jmp     short loc_180014088
0x180014083  mov     rax, [rsp+38h+ProcedureAddress]
0x180014088  add     rsp, 30h
0x18001408c  pop     rbx
0x18001408d  retn
```
