# CWinmmNotificationClient::OnDeviceRemoved(ushort const *)

- ea: `0x18001c0f0`
- end: `0x18001c0fb`
- name: `?OnDeviceRemoved@CWinmmNotificationClient@@UEAAJPEBG@Z`
- size: `11`
- prototype: `__int64 __fastcall(CWinmmNotificationClient *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CWinmmNotificationClient::OnDeviceRemoved(
        CWinmmNotificationClient *this,
        const unsigned __int16 *a2)
{
  _InterlockedExchange((volatile __int32 *)this + 4, 1);
  return 0;
}

```

## disassembly

```asm
0x18001c0f0  mov     eax, 1
0x18001c0f5  xchg    eax, [rcx+10h]
0x18001c0f8  xor     eax, eax
0x18001c0fa  retn
```
