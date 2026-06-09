# ForeachRegistryVar

- ea: `0x140022fa0`
- end: `0x140023039`
- name: `ForeachRegistryVar`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140023150`

## callees

- `0x140040a70`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValues` at `0x14002301f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022fe6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022fe6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140022ff7`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140022ff7`

## string_xrefs

- `0x140022fd0`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall ForeachRegistryVar(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID SystemRoutineAddress; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD v11[19]; // [rsp+40h] [rbp-98h] BYREF

  memset(v11, 0, 0x70u);
  v11[3] = a4;
  v11[0] = a2;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD *, __int64, _QWORD))SystemRoutineAddress)(
           3221225472LL,
           a1,
           v11,
           a3,
           0);
}

```

## disassembly

```asm
0x140022fa0  push    rbx
0x140022fa2  push    rbp
0x140022fa3  push    rsi
0x140022fa4  push    rdi
0x140022fa5  sub     rsp, 0B8h
0x140022fac  mov     rbx, rdx
0x140022faf  mov     rsi, r8
0x140022fb2  xor     edx, edx; Val
0x140022fb4  mov     rbp, rcx
0x140022fb7  lea     rcx, [rsp+0D8h+var_98]; void *
0x140022fbc  mov     rdi, r9
0x140022fbf  lea     r8d, [rdx+70h]; Size
0x140022fc3  call    memset
0x140022fc8  xorps   xmm0, xmm0
0x140022fcb  mov     [rsp+0D8h+var_80], rdi
0x140022fd0  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140022fd7  mov     [rsp+0D8h+var_98], rbx
0x140022fdc  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x140022fe1  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x140022fe6  call    cs:__imp_RtlInitUnicodeString
0x140022fed  nop     dword ptr [rax+rax+00h]
0x140022ff2  lea     rcx, [rsp+0D8h+DestinationString]; SystemRoutineName
0x140022ff7  call    cs:__imp_MmGetSystemRoutineAddress
0x140022ffe  nop     dword ptr [rax+rax+00h]
0x140023003  mov     r9, rsi
0x140023006  mov     [rsp+0D8h+var_B8], 0
0x14002300f  test    rax, rax
0x140023012  lea     r8, [rsp+0D8h+var_98]
0x140023017  mov     rdx, rbp
0x14002301a  mov     ecx, 0C0000000h
0x14002301f  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140023027  call    _guard_dispatch_icall
0x14002302c  add     rsp, 0B8h
0x140023033  pop     rdi
0x140023034  pop     rsi
0x140023035  pop     rbp
0x140023036  pop     rbx
0x140023037  retn
```
