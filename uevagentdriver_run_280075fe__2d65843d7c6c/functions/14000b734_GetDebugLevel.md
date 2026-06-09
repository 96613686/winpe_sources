# GetDebugLevel

- ea: `0x14000b734`
- end: `0x14000b766`
- name: `GetDebugLevel`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000c614`

## callees

- `0x14000b734`
- `0x14000b854`

## pseudocode

```c
__int64 GetDebugLevel()
{
  __int64 result; // rax

  result = ReadRegistryDword((struct _UNICODE_STRING *)L"xz", (struct _UNICODE_STRING *)L" \"", &g_DebugLevel);
  if ( (int)result < 0 )
    g_DebugLevel = 1;
  return result;
}

```

## disassembly

```asm
0x14000b734  sub     rsp, 28h
0x14000b738  lea     r8, g_DebugLevel
0x14000b73f  lea     rdx, asc_140004070; " \""
0x14000b746  lea     rcx, aXz; "xz"
0x14000b74d  call    ReadRegistryDword
0x14000b752  test    eax, eax
0x14000b754  jns     short loc_14000B760
0x14000b756  mov     cs:g_DebugLevel, 1
0x14000b760  add     rsp, 28h
0x14000b764  retn
```
