# WEBHOST_PROTOCOL_MANAGER::AddRef(void)

- ea: `0x180001aa0`
- end: `0x180001aad`
- name: `?AddRef@WEBHOST_PROTOCOL_MANAGER@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001ac0`
- `0x180001ad0`
- `0x180001ae0`
- `0x180001af0`
- `0x180001b00`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::AddRef(WEBHOST_PROTOCOL_MANAGER *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 13);
}

```

## disassembly

```asm
0x180001aa0  mov     eax, 1
0x180001aa5  lock xadd [rcx+34h], eax
0x180001aaa  inc     eax
0x180001aac  retn
```
