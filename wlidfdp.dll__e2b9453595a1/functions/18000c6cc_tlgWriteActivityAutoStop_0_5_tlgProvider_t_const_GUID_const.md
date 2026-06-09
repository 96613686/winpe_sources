# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000c6cc`
- end: `0x18000c71c`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c7c4`

## callees

- `0x180002018`
- `0x1800027f0`
- `0x18000c6cc`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<0,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  _BYTE v3[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
    return tlgWriteTransfer_EventWriteTransfer(a1, byte_18001BACD, a2, 0, 2, v3);
  return result;
}

```

## disassembly

```asm
0x18000c6cc  sub     rsp, 68h
0x18000c6d0  mov     rax, cs:__security_cookie
0x18000c6d7  xor     rax, rsp
0x18000c6da  mov     [rsp+68h+var_18], rax
0x18000c6df  mov     eax, [rcx]
0x18000c6e1  cmp     eax, 5
0x18000c6e4  jbe     short loc_18000C70A
0x18000c6e6  lea     rax, [rsp+68h+var_38]
0x18000c6eb  mov     r8, rdx
0x18000c6ee  mov     [rsp+68h+var_40], rax
0x18000c6f3  lea     rdx, byte_18001BACD
0x18000c6fa  xor     r9d, r9d
0x18000c6fd  mov     [rsp+68h+var_48], 2
0x18000c705  call    _tlgWriteTransfer_EventWriteTransfer
0x18000c70a  mov     rcx, [rsp+68h+var_18]
0x18000c70f  xor     rcx, rsp; StackCookie
0x18000c712  call    __security_check_cookie
0x18000c717  add     rsp, 68h
0x18000c71b  retn
```
