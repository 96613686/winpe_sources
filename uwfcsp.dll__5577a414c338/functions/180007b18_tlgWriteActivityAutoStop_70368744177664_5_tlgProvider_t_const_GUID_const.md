# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180007b18`
- end: `0x180007b8a`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007ccc`

## callees

- `0x180001ecc`
- `0x180007b18`
- `0x18001a210`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rdx
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    v4 = *((_QWORD *)a1 + 3);
    result = *((_QWORD *)a1 + 2);
    if ( (result & 0x400000000000LL) != 0 )
    {
      result = v4 & 0x400000000000LL;
      if ( (v4 & 0x400000000000LL) == v4 )
        return tlgWriteTransfer_EventWriteTransfer(a1, word_180022BA2, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007b18  sub     rsp, 68h
0x180007b1c  mov     rax, cs:__security_cookie
0x180007b23  xor     rax, rsp
0x180007b26  mov     [rsp+68h+var_18], rax
0x180007b2b  mov     eax, [rcx]
0x180007b2d  mov     r8, rdx
0x180007b30  cmp     eax, 5
0x180007b33  jbe     short loc_180007B78
0x180007b35  mov     rdx, [rcx+18h]
0x180007b39  mov     r9, 400000000000h
0x180007b43  mov     rax, [rcx+10h]
0x180007b47  test    r9, rax
0x180007b4a  jz      short loc_180007B78
0x180007b4c  mov     rax, rdx
0x180007b4f  and     rax, r9
0x180007b52  cmp     rax, rdx
0x180007b55  jnz     short loc_180007B78
0x180007b57  lea     rax, [rsp+68h+var_38]
0x180007b5c  xor     r9d, r9d
0x180007b5f  mov     [rsp+68h+var_40], rax
0x180007b64  lea     rdx, word_180022BA2
0x180007b6b  mov     [rsp+68h+var_48], 2
0x180007b73  call    _tlgWriteTransfer_EventWriteTransfer
0x180007b78  mov     rcx, [rsp+68h+var_18]
0x180007b7d  xor     rcx, rsp; StackCookie
0x180007b80  call    __security_check_cookie
0x180007b85  add     rsp, 68h
0x180007b89  retn
```
