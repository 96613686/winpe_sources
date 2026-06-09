# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x140003254`
- end: `0x140003270`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046cc`
- `0x14000a804`
- `0x1400192b0`
- `0x14001a380`
- `0x14001a420`
- `0x14001a5ac`

## callees

- `0x140003254`
- `0x140003454`

## pseudocode

```c
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new[](a1);
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140003254  sub     rsp, 38h
0x140003258  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140003261  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140003266  jmp     short loc_14000326A
0x140003268  xor     eax, eax
0x14000326a  add     rsp, 38h
0x14000326e  retn
```
