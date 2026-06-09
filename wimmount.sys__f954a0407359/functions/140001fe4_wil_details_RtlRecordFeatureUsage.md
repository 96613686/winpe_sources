# wil_details_RtlRecordFeatureUsage

- ea: `0x140001fe4`
- end: `0x140002048`
- name: `wil_details_RtlRecordFeatureUsage`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001d98`

## callees

- `0x140001fe4`
- `0x140002c90`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140002019`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140002019`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_RtlRecordFeatureUsage(__int64 a1, __int64 a2))(__int64, __int64)
{
  __int64 (__fastcall *result)(__int64, __int64); // rax
  struct _UNICODE_STRING v5; // [rsp+20h] [rbp-18h] BYREF

  result = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_pfnRtlRecordFeatureUsage;
  if ( g_wil_details_pfnRtlRecordFeatureUsage )
    return (__int64 (__fastcall *)(__int64, __int64))result(a1, a2);
  *(_QWORD *)&v5.Length = 2883626;
  v5.Buffer = L"RtlRecordFeatureUsage";
  result = (__int64 (__fastcall *)(__int64, __int64))MmGetSystemRoutineAddress(&v5);
  g_wil_details_pfnRtlRecordFeatureUsage = (__int64)result;
  if ( result )
    return (__int64 (__fastcall *)(__int64, __int64))result(a1, a2);
  return result;
}

```

## disassembly

```asm
0x140001fe4  mov     r11, rsp
0x140001fe7  mov     [r11+8], rbx
0x140001feb  push    rdi
0x140001fec  sub     rsp, 30h
0x140001ff0  mov     rax, cs:g_wil_details_pfnRtlRecordFeatureUsage
0x140001ff7  mov     rbx, rdx
0x140001ffa  mov     rdi, rcx
0x140001ffd  test    rax, rax
0x140002000  jnz     short loc_140002031
0x140002002  lea     rax, aRtlrecordfeatu; "RtlRecordFeatureUsage"
0x140002009  mov     qword ptr [r11-18h], 2C002Ah
0x140002011  lea     rcx, [r11-18h]; SystemRoutineName
0x140002015  mov     [r11-10h], rax
0x140002019  call    cs:__imp_MmGetSystemRoutineAddress
0x140002020  nop     dword ptr [rax+rax+00h]
0x140002025  mov     cs:g_wil_details_pfnRtlRecordFeatureUsage, rax
0x14000202c  test    rax, rax
0x14000202f  jz      short loc_14000203C
0x140002031  mov     rdx, rbx
0x140002034  mov     rcx, rdi
0x140002037  call    _guard_dispatch_icall
0x14000203c  mov     rbx, [rsp+38h+arg_0]
0x140002041  add     rsp, 30h
0x140002045  pop     rdi
0x140002046  retn
```
