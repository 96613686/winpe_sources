# _DbgpGetTraceMappingName(void)

- ea: `0x180036310`
- end: `0x180036358`
- name: `?_DbgpGetTraceMappingName@@YAPEBGXZ`
- size: `72`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180036360`
- `0x180036720`

## callees

- `0x180013364`
- `0x180036310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036326`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036326`

## pseudocode

```c
wchar_t *_DbgpGetTraceMappingName(void)
{
  DWORD CurrentProcessId; // [rsp+20h] [rbp-18h]

  if ( !Buffer )
  {
    word_180046606 = 0;
    CurrentProcessId = GetCurrentProcessId();
    snwprintf_s(&Buffer, 0x104u, 0x103u, L"Debug.Trace.Memory.%x", CurrentProcessId);
  }
  return &Buffer;
}

```

## disassembly

```asm
0x180036310  sub     rsp, 38h
0x180036314  xor     eax, eax
0x180036316  cmp     cs:Buffer, ax
0x18003631d  jnz     short loc_18003634C
0x18003631f  mov     cs:word_180046606, ax
0x180036326  call    cs:__imp_GetCurrentProcessId
0x18003632c  mov     edx, 104h; BufferCount
0x180036331  lea     r9, aDebugTraceMemo; "Debug.Trace.Memory.%x"
0x180036338  lea     rcx, Buffer; Buffer
0x18003633f  mov     [rsp+38h+var_18], eax
0x180036343  lea     r8d, [rdx-1]; MaxCount
0x180036347  call    _snwprintf_s
0x18003634c  lea     rax, Buffer
0x180036353  add     rsp, 38h
0x180036357  retn
```
