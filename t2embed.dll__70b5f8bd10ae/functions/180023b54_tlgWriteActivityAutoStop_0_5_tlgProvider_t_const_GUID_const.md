# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180023b54`
- end: `0x180023ba4`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c53c`

## callees

- `0x1800018c8`
- `0x180023b54`
- `0x18002a590`

## pseudocode

```c
ULONG __fastcall _tlgWriteActivityAutoStop<0,5>(ULONG *a1, const GUID *a2)
{
  ULONG result; // eax
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( *a1 > 5 )
    return tlgWriteTransfer_EventWriteTransfer((__int64)a1, (unsigned __int8 *)byte_18002D891, a2, 0, 2u, &v3);
  return result;
}

```

## disassembly

```asm
0x180023b54  sub     rsp, 68h
0x180023b58  mov     rax, cs:__security_cookie
0x180023b5f  xor     rax, rsp
0x180023b62  mov     [rsp+68h+var_18], rax
0x180023b67  mov     eax, [rcx]
0x180023b69  cmp     eax, 5
0x180023b6c  jbe     short loc_180023B92
0x180023b6e  lea     rax, [rsp+68h+var_38]
0x180023b73  mov     r8, rdx
0x180023b76  mov     [rsp+68h+var_40], rax
0x180023b7b  lea     rdx, byte_18002D891
0x180023b82  xor     r9d, r9d
0x180023b85  mov     [rsp+68h+var_48], 2
0x180023b8d  call    _tlgWriteTransfer_EventWriteTransfer
0x180023b92  mov     rcx, [rsp+68h+var_18]
0x180023b97  xor     rcx, rsp; StackCookie
0x180023b9a  call    __security_check_cookie
0x180023b9f  add     rsp, 68h
0x180023ba3  retn
```
