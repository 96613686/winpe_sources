# GetBrowserEventFlags(_EVENT_DESCRIPTOR const *)

- ea: `0x180043f64`
- end: `0x180043fb5`
- name: `?GetBrowserEventFlags@@YAKPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `81`
- prototype: `unsigned int __fastcall(const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001008`

## callees

- `0x180043f64`
- `0x1800791d4`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180043f8e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180043f8e`

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
0x180043f64  push    rbx
0x180043f66  sub     rsp, 20h
0x180043f6a  mov     ecx, cs:_tls_index
0x180043f70  xor     ebx, ebx
0x180043f72  mov     rax, gs:58h
0x180043f7b  mov     edx, 8
0x180043f80  mov     rax, [rax+rcx*8]
0x180043f84  cmp     [rdx+rax], bl
0x180043f87  jnz     short loc_180043FAC
0x180043f89  mov     ecx, 20000019h
0x180043f8e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180043f95  nop     dword ptr [rax+rax+00h]
0x180043f9a  test    al, al
0x180043f9c  jz      short loc_180043FA7
0x180043f9e  call    ?IsTelemetryInPrivate@@YA_NXZ; IsTelemetryInPrivate(void)
0x180043fa3  test    al, al
0x180043fa5  jz      short loc_180043FAC
0x180043fa7  mov     ebx, 2
0x180043fac  mov     eax, ebx
0x180043fae  add     rsp, 20h
0x180043fb2  pop     rbx
0x180043fb3  retn
```
