# wil::SvchostModule::DecrementObjectCount(void)

- ea: `0x180007ea0`
- end: `0x180007eaa`
- name: `?DecrementObjectCount@SvchostModule@wil@@UEAAKXZ`
- size: `10`
- prototype: `__int64 __fastcall(wil::SvchostModule *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180007ea3`

## pseudocode

```c
__int64 __fastcall wil::SvchostModule::DecrementObjectCount(wil::SvchostModule *this)
{
  return CoReleaseSharedService(*((unsigned int *)this + 6));
}

```

## disassembly

```asm
0x180007ea0  mov     ecx, [rcx+18h]
0x180007ea3  jmp     cs:__imp_CoReleaseSharedService
```
