# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000d0d8`
- end: `0x18000d143`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `107`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d14c`

## callees

- `0x180001350`
- `0x18000d0d8`
- `0x180010310`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(__int64 a1, int a2)
{
  __int64 result; // rax
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+30h] [rbp-38h] BYREF

  if ( *(_DWORD *)a1 > 5u && (*(_QWORD *)(a1 + 16) & 0x400000000000LL) != 0 )
  {
    result = *(_QWORD *)(a1 + 24) & 0x400000000000LL;
    if ( result == *(_QWORD *)(a1 + 24) )
      return tlgWriteTransfer_EventWriteTransfer(a1, (int)&word_18001AF96, a2, 0, 2u, &v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000d0d8  sub     rsp, 68h
0x18000d0dc  mov     rax, cs:__security_cookie
0x18000d0e3  xor     rax, rsp
0x18000d0e6  mov     [rsp+68h+var_18], rax
0x18000d0eb  cmp     dword ptr [rcx], 5
0x18000d0ee  jbe     short loc_18000D131
0x18000d0f0  mov     r8, 400000000000h
0x18000d0fa  test    [rcx+10h], r8
0x18000d0fe  jz      short loc_18000D131
0x18000d100  mov     rax, [rcx+18h]
0x18000d104  and     rax, r8
0x18000d107  cmp     rax, [rcx+18h]
0x18000d10b  jnz     short loc_18000D131
0x18000d10d  lea     rax, [rsp+68h+var_38]
0x18000d112  mov     r8, rdx; int
0x18000d115  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x18000d11a  lea     rdx, word_18001AF96; int
0x18000d121  xor     r9d, r9d; int
0x18000d124  mov     [rsp+68h+var_48], 2; ULONG
0x18000d12c  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d131  mov     rcx, [rsp+68h+var_18]
0x18000d136  xor     rcx, rsp; StackCookie
0x18000d139  call    __security_check_cookie
0x18000d13e  add     rsp, 68h
0x18000d142  retn
```
