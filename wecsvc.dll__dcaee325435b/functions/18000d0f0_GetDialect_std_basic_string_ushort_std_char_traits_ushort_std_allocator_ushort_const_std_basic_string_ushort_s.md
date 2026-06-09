# GetDialect(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000d0f0`
- end: `0x18000d153`
- name: `?GetDialect@@YAPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `99`
- prototype: `const wchar_t *__fastcall(_QWORD *, const wchar_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009a10`
- `0x18000c724`

## callees

- `0x18000d0f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d124`
- `msvcrt!_wcsicmp` at `0x18000d124`

## string_xrefs

- `0x18000d11a`: `http://schemas.microsoft.com/wbem/wsman/1/windows/EventLog`
- `0x18000d12e`: `http://schemas.microsoft.com/win/2004/08/events/eventquery`

## pseudocode

```c
const wchar_t *__fastcall GetDialect(_QWORD *a1, const wchar_t *a2)
{
  const wchar_t *v2; // rax
  const wchar_t *v4; // rcx
  const wchar_t *result; // rax

  v2 = a2;
  if ( *((_QWORD *)a2 + 3) < 8u )
    v4 = a2;
  else
    v4 = *(const wchar_t **)a2;
  if ( !v4 )
    goto LABEL_9;
  if ( *((_QWORD *)a2 + 3) >= 8u )
    v2 = *(const wchar_t **)a2;
  if ( _wcsicmp(v2, L"http://schemas.microsoft.com/wbem/wsman/1/windows/EventLog") )
LABEL_9:
    result = 0;
  else
    result = L"http://schemas.microsoft.com/win/2004/08/events/eventquery";
  if ( a1[2] )
  {
    if ( a1[3] >= 8u )
      return (const wchar_t *)*a1;
    return (const wchar_t *)a1;
  }
  return result;
}

```

## disassembly

```asm
0x18000d0f0  push    rbx
0x18000d0f2  sub     rsp, 20h
0x18000d0f6  cmp     qword ptr [rdx+18h], 8
0x18000d0fb  mov     rax, rdx
0x18000d0fe  mov     rbx, rcx
0x18000d101  jb      short loc_18000D108
0x18000d103  mov     rcx, [rdx]
0x18000d106  jmp     short loc_18000D10B
0x18000d108  mov     rcx, rdx
0x18000d10b  test    rcx, rcx
0x18000d10e  jz      short loc_18000D137
0x18000d110  cmp     qword ptr [rdx+18h], 8
0x18000d115  jb      short loc_18000D11A
0x18000d117  mov     rax, [rdx]
0x18000d11a  lea     rdx, aHttpSchemasMic_0; "http://schemas.microsoft.com/wbem/wsman"...
0x18000d121  mov     rcx, rax; String1
0x18000d124  call    cs:__imp__wcsicmp
0x18000d12a  test    eax, eax
0x18000d12c  jnz     short loc_18000D137
0x18000d12e  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/win/2004/0"...
0x18000d135  jmp     short loc_18000D139
0x18000d137  xor     eax, eax
0x18000d139  cmp     qword ptr [rbx+10h], 0
0x18000d13e  jz      short loc_18000D14D
0x18000d140  cmp     qword ptr [rbx+18h], 8
0x18000d145  jb      short loc_18000D14A
0x18000d147  mov     rbx, [rbx]
0x18000d14a  mov     rax, rbx
0x18000d14d  add     rsp, 20h
0x18000d151  pop     rbx
0x18000d152  retn
```
