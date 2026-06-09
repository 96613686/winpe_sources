# wil::SvchostModule::IncrementObjectCount(void)

- ea: `0x180008a60`
- end: `0x180008a6a`
- name: `?IncrementObjectCount@SvchostModule@wil@@UEAAKXZ`
- size: `10`
- prototype: `__int64 __fastcall(wil::SvchostModule *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x180008a63`

## pseudocode

```c
__int64 __fastcall wil::SvchostModule::IncrementObjectCount(wil::SvchostModule *this)
{
  return CoAddRefSharedService(*((unsigned int *)this + 6));
}

```

## disassembly

```asm
0x180008a60  mov     ecx, [rcx+18h]
0x180008a63  jmp     cs:__imp_CoAddRefSharedService
```
