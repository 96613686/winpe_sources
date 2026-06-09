# Feature_PackagedComElevationSupport__private_IsEnabledNoReportingNoInline

- ea: `0x180006630`
- end: `0x180006658`
- name: `Feature_PackagedComElevationSupport__private_IsEnabledNoReportingNoInline`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004e88`

## callees

- `0x18000661c`
- `0x180006630`

## pseudocode

```c
__int64 Feature_PackagedComElevationSupport__private_IsEnabledNoReportingNoInline()
{
  if ( (Feature_PackagedComElevationSupport__private_featureState & 2) != 0 )
    return Feature_PackagedComElevationSupport__private_featureState & 1;
  else
    return Feature_PackagedComElevationSupport__private_IsEnabledFallback(
             (unsigned int)Feature_PackagedComElevationSupport__private_featureState,
             0);
}

```

## disassembly

```asm
0x180006630  mov     eax, cs:Feature_PackagedComElevationSupport__private_featureState
0x180006636  mov     [rsp+arg_0], 0
0x18000663f  mov     dword ptr [rsp+arg_0], eax
0x180006643  test    al, 2
0x180006645  jz      short loc_18000664C
0x180006647  and     eax, 1
0x18000664a  retn
0x18000664c  mov     rcx, [rsp+arg_0]
0x180006651  xor     edx, edx
0x180006653  jmp     Feature_PackagedComElevationSupport__private_IsEnabledFallback
```
