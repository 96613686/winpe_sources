# wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000b9d4`
- end: `0x18000b9fd`
- name: `?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `41`
- prototype: `void __fastcall(wil::details *this, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a394`
- `0x18000a5e0`
- `0x18000ba04`

## callees

- `0x18000b9d4`
- `0x18000e010`

## pseudocode

```c
void __fastcall wil::details::WilApi_RecordFeatureUsage(wil::details *this, __int64 a2, __int64 a3)
{
  void (__fastcall *v3)(wil::details *, __int64, __int64, _QWORD); // rax

  v3 = (void (__fastcall *)(wil::details *, __int64, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
  if ( g_wil_details_internalRecordFeatureUsage
    || (v3 = (void (__fastcall *)(wil::details *, __int64, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
  {
    v3(this, a2, a3, 0);
  }
}

```

## disassembly

```asm
0x18000b9d4  sub     rsp, 38h
0x18000b9d8  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000b9df  test    rax, rax
0x18000b9e2  jnz     short loc_18000B9F0
0x18000b9e4  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000b9eb  test    rax, rax
0x18000b9ee  jz      short loc_18000B9F8
0x18000b9f0  xor     r9d, r9d
0x18000b9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f8  add     rsp, 38h
0x18000b9fc  retn
```
