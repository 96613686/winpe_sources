# CSrmFunctionTracer::TranslateComErrorNoThrow(CSrmDebugInfo,ushort const *,...)

- ea: `0x180019850`
- end: `0x18001989f`
- name: `?TranslateComErrorNoThrow@CSrmFunctionTracer@@QEAAJUCSrmDebugInfo@@PEBGZZ`
- size: `79`
- prototype: `void __noreturn(_QWORD, const struct CSrmDebugInfo *, __int64, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017ad0`

## callees

- `0x180016170`
- `0x1800198e0`

## pseudocode

```c
void __noreturn CSrmFunctionTracer::TranslateComErrorNoThrow(
        _QWORD a1,
        const struct CSrmDebugInfo *a2,
        __int64 a3,
        ...)
{
  CSrmDebugInfo *v3; // rax
  __int64 v4; // r10
  _QWORD v5[3]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v6[160]; // [rsp+38h] [rbp-A0h] BYREF

  try
  {
    v5[1] = 0;
    v5[2] = v6;
    v3 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v6, a2);
    CSrmFunctionTracer::TranslateComErrorV(v4, v3, a3);
  }
  catch ( long v5 )
  {
    JUMPOUT(0x1800198A0LL);
  }
  catch ( std::bad_alloc )
  {
    JUMPOUT(0x1800198A6LL);
  }
  catch ( exception )
  {
    JUMPOUT(0x1800198BCLL);
  }
}

```

## disassembly

```asm
0x180019850  mov     rax, rsp
0x180019853  mov     [rax+18h], r8
0x180019857  mov     [rax+10h], rdx
0x18001985b  mov     [rax+20h], r9
0x18001985f  push    rbx
0x180019860  sub     rsp, 0D0h
0x180019867  mov     r10, rcx
0x18001986a  mov     [rsp+0D8h+var_B0], 0
0x180019873  lea     r9, [rax+20h]
0x180019877  lea     rax, [rsp+0D8h+var_A0]
0x18001987c  mov     [rsp+0D8h+var_A8], rax
0x180019881  lea     rcx, [rsp+0D8h+var_A0]; this
0x180019886  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x18001988b  nop
0x18001988c  mov     r8, [rsp+0D8h+arg_10]
0x180019894  mov     rdx, rax
0x180019897  mov     rcx, r10
0x18001989a  call    ?TranslateComErrorV@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGPEAD@Z; CSrmFunctionTracer::TranslateComErrorV(CSrmDebugInfo,ushort const *,char *)
```
