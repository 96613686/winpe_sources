# SubscriptionConfigSnapshot::~SubscriptionConfigSnapshot(void)

- ea: `0x180003c94`
- end: `0x180003cb6`
- name: `??1SubscriptionConfigSnapshot@@UEAA@XZ`
- size: `34`
- prototype: `void __fastcall(SubscriptionConfigSnapshot *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800042d0`
- `0x180015570`

## callees

- `0x18001dbd4`

## pseudocode

```c
void __fastcall SubscriptionConfigSnapshot::~SubscriptionConfigSnapshot(SubscriptionConfigSnapshot *this)
{
  SubscriptionReadData::~SubscriptionReadData((SubscriptionConfigSnapshot *)((char *)this + 16));
  *(_QWORD *)this = &wmi::RefBase::`vftable';
}

```

## disassembly

```asm
0x180003c94  push    rbx
0x180003c96  sub     rsp, 20h
0x180003c9a  mov     rbx, rcx
0x180003c9d  add     rcx, 10h; this
0x180003ca1  call    ??1SubscriptionReadData@@QEAA@XZ; SubscriptionReadData::~SubscriptionReadData(void)
0x180003ca6  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180003cad  mov     [rbx], rax
0x180003cb0  add     rsp, 20h
0x180003cb4  pop     rbx
0x180003cb5  retn
```
