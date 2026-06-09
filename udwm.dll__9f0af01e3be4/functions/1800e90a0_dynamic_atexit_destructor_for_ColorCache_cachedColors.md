# _dynamic_atexit_destructor_for__ColorCache::_cachedColors__

- ea: `0x1800e90a0`
- end: `0x1800e9102`
- name: `_dynamic_atexit_destructor_for__ColorCache::_cachedColors__`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800e90a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800e90d7`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800e90d7`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800e90f2`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800e90f2`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800e90c5`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800e90c5`

## pseudocode

```c
_DWORD *dynamic_atexit_destructor_for__ColorCache::_cachedColors__()
{
  _DWORD *result; // rax
  _DWORD Buffer[2]; // [rsp+20h] [rbp-18h] BYREF
  char v2; // [rsp+28h] [rbp-10h]
  PVOID RestartKey; // [rsp+40h] [rbp+8h] BYREF

  while ( 1 )
  {
    RestartKey = 0;
    result = RtlEnumerateGenericTableWithoutSplaying(&ColorCache::_cachedColors, &RestartKey);
    if ( !result )
      break;
    Buffer[0] = *result;
    Buffer[1] = 0;
    v2 = 1;
    if ( !RtlDeleteElementGenericTable(&ColorCache::_cachedColors, Buffer) )
      RaiseFailFastException(0, 0, 1u);
  }
  return result;
}

```

## disassembly

```asm
0x1800e90a0  sub     rsp, 38h
0x1800e90a4  jmp     short loc_1800E90DD
0x1800e90a6  mov     eax, [rax]
0x1800e90a8  lea     rdx, [rsp+38h+Buffer]; Buffer
0x1800e90ad  lea     rcx, ?_cachedColors@ColorCache@@0V?$CGenericTableMap@W4IMMERSIVE_COLOR_TYPE@@UColorData@ColorCache@@@@A; Table
0x1800e90b4  mov     [rsp+38h+Buffer], eax
0x1800e90b8  mov     [rsp+38h+var_14], 0
0x1800e90c0  mov     [rsp+38h+var_10], 1
0x1800e90c5  call    cs:__imp_RtlDeleteElementGenericTable
0x1800e90cb  test    al, al
0x1800e90cd  jnz     short loc_1800E90DD
0x1800e90cf  xor     edx, edx; pContextRecord
0x1800e90d1  xor     ecx, ecx; pExceptionRecord
0x1800e90d3  lea     r8d, [rdx+1]; dwFlags
0x1800e90d7  call    cs:__imp_RaiseFailFastException
0x1800e90dd  lea     rdx, [rsp+38h+RestartKey]; RestartKey
0x1800e90e2  mov     [rsp+38h+RestartKey], 0
0x1800e90eb  lea     rcx, ?_cachedColors@ColorCache@@0V?$CGenericTableMap@W4IMMERSIVE_COLOR_TYPE@@UColorData@ColorCache@@@@A; Table
0x1800e90f2  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x1800e90f8  test    rax, rax
0x1800e90fb  jnz     short loc_1800E90A6
0x1800e90fd  add     rsp, 38h
0x1800e9101  retn
```
