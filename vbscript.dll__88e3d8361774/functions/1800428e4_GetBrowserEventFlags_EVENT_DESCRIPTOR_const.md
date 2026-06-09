# GetBrowserEventFlags(_EVENT_DESCRIPTOR const *)

- ea: `0x1800428e4`
- end: `0x18004292e`
- name: `?GetBrowserEventFlags@@YAKPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `74`
- prototype: `unsigned int __fastcall(const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001008`

## callees

- `0x1800428e4`
- `0x18007650c`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004290e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18004290e`

## pseudocode

```c
__int64 __fastcall GetBrowserEventFlags(const struct _EVENT_DESCRIPTOR *a1)
{
  unsigned int v1; // ebx

  v1 = 0;
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL)
    && (!(unsigned __int8)IEConfiguration_GetBool(536870937) || IsTelemetryInPrivate()) )
  {
    return 2;
  }
  return v1;
}

```

## disassembly

```asm
0x1800428e4  push    rbx
0x1800428e6  sub     rsp, 20h
0x1800428ea  mov     ecx, cs:_tls_index
0x1800428f0  xor     ebx, ebx
0x1800428f2  mov     rax, gs:58h
0x1800428fb  mov     edx, 8
0x180042900  mov     rax, [rax+rcx*8]
0x180042904  cmp     [rdx+rax], bl
0x180042907  jnz     short loc_180042926
0x180042909  mov     ecx, 20000019h
0x18004290e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180042914  test    al, al
0x180042916  jz      short loc_180042921
0x180042918  call    ?IsTelemetryInPrivate@@YA_NXZ; IsTelemetryInPrivate(void)
0x18004291d  test    al, al
0x18004291f  jz      short loc_180042926
0x180042921  mov     ebx, 2
0x180042926  mov     eax, ebx
0x180042928  add     rsp, 20h
0x18004292c  pop     rbx
0x18004292d  retn
```
