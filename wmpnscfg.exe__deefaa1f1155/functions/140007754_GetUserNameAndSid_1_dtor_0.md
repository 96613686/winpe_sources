# _GetUserNameAndSid_::_1_::dtor$0

- ea: `0x140007754`
- end: `0x140007760`
- name: `_GetUserNameAndSid_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140006c7c`

## pseudocode

```c
void __fastcall GetUserNameAndSid_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CSid::~CSid((ATL::CSid *)(a2 + 48));
}

```

## disassembly

```asm
0x140007754  lea     rcx, [rdx+30h]; this
0x14000775b  jmp     ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
```
