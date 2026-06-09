# com::application_reputation_static::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000b470`
- end: `0x18000b47d`
- name: `?GetRuntimeClassName@application_reputation_static@com@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `13`
- prototype: `__int64 __fastcall(com::application_reputation_static *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000b490`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::GetRuntimeClassName(
        com::application_reputation_static *this,
        HSTRING *a2)
{
  *a2 = 0;
  return 2147483662LL;
}

```

## disassembly

```asm
0x18000b470  mov     qword ptr [rdx], 0
0x18000b477  mov     eax, 8000000Eh
0x18000b47c  retn
```
