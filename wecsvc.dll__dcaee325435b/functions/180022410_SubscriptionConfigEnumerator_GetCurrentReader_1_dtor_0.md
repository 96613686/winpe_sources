# _SubscriptionConfigEnumerator::GetCurrentReader_::_1_::dtor$0

- ea: `0x180022410`
- end: `0x180022436`
- name: `_SubscriptionConfigEnumerator::GetCurrentReader_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180003ad4`
- `0x180022410`

## pseudocode

```c
__int64 __fastcall SubscriptionConfigEnumerator::GetCurrentReader_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return wmi::AutoRef<SubscriptionConfigSnapshot>::~AutoRef<SubscriptionConfigSnapshot>(*(_QWORD *)(a2 + 72));
  }
  return result;
}

```

## disassembly

```asm
0x180022410  push    rbp
0x180022412  sub     rsp, 20h
0x180022416  mov     rbp, rdx
0x180022419  mov     eax, [rbp+20h]
0x18002241c  and     eax, 1
0x18002241f  test    eax, eax
0x180022421  jz      short loc_180022430
0x180022423  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180022427  mov     rcx, [rbp+48h]
0x18002242b  call    ??1?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAA@XZ
0x180022430  add     rsp, 20h
0x180022434  pop     rbp
0x180022435  retn
```
