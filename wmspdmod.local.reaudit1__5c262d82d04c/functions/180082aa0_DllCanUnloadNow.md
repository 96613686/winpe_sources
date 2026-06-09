# DllCanUnloadNow

- ea: `0x180082aa0`
- end: `0x180082abe`
- name: `DllCanUnloadNow`
- size: `30`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180082aa0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( dword_18011B84C > 0 )
    LODWORD(v0) = 1;
  else
    return dword_18011B848 != 0;
  return v0;
}

```

## disassembly

```asm
0x180082aa0  cmp     cs:dword_18011B84C, 0
0x180082aa7  jg      short loc_180082AB8
0x180082aa9  mov     ecx, cs:dword_18011B848
0x180082aaf  xor     eax, eax
0x180082ab1  test    ecx, ecx
0x180082ab3  setnz   al
0x180082ab6  retn
0x180082ab8  mov     eax, 1
0x180082abd  retn
```
