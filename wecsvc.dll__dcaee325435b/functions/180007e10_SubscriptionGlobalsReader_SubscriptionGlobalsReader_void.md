# SubscriptionGlobalsReader::SubscriptionGlobalsReader(void)

- ea: `0x180007e10`
- end: `0x180007e31`
- name: `??0SubscriptionGlobalsReader@@QEAA@XZ`
- size: `33`
- prototype: `SubscriptionGlobalsReader *__fastcall(SubscriptionGlobalsReader *this, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007844`
- `0x180007c00`

## callees

- `0x180014208`

## pseudocode

```c
SubscriptionGlobalsReader *__fastcall SubscriptionGlobalsReader::SubscriptionGlobalsReader(
        SubscriptionGlobalsReader *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  ConfigBase::ConfigBase(this, a2, a3);
  *(_QWORD *)this = &SubscriptionGlobalsReader::`vftable';
  return this;
}

```

## disassembly

```asm
0x180007e10  push    rbx
0x180007e12  sub     rsp, 20h
0x180007e16  mov     rbx, rcx
0x180007e19  call    ??0ConfigBase@@QEAA@PEAUHKEY__@@PEBG@Z; ConfigBase::ConfigBase(HKEY__ *,ushort const *)
0x180007e1e  lea     rax, ??_7SubscriptionGlobalsReader@@6B@; const SubscriptionGlobalsReader::`vftable'
0x180007e25  mov     [rbx], rax
0x180007e28  mov     rax, rbx
0x180007e2b  add     rsp, 20h
0x180007e2f  pop     rbx
0x180007e30  retn
```
