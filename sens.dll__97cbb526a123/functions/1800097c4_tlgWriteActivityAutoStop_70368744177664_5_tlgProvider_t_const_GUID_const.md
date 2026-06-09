# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1800097c4`
- end: `0x180009823`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006f9c`

## callees

- `0x1800068b8`
- `0x180007da0`
- `0x1800097c4`
- `0x18000a7a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // r8
  __int64 v4; // r10
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(a1, a2, a2);
    if ( (_BYTE)result )
      return tlgWriteTransfer_EventWriteTransfer(v4, byte_18000E291, v3, 0, 2, v5);
  }
  return result;
}

```

## disassembly

```asm
0x1800097c4  sub     rsp, 68h
0x1800097c8  mov     rax, cs:__security_cookie
0x1800097cf  xor     rax, rsp
0x1800097d2  mov     [rsp+68h+var_18], rax
0x1800097d7  mov     eax, [rcx]
0x1800097d9  mov     r8, rdx
0x1800097dc  mov     r10, rcx
0x1800097df  cmp     eax, 5
0x1800097e2  jbe     short loc_180009811
0x1800097e4  call    _tlgKeywordOn
0x1800097e9  test    al, al
0x1800097eb  jz      short loc_180009811
0x1800097ed  lea     rax, [rsp+68h+var_38]
0x1800097f2  xor     r9d, r9d
0x1800097f5  mov     [rsp+68h+var_40], rax
0x1800097fa  lea     rdx, byte_18000E291
0x180009801  mov     rcx, r10
0x180009804  mov     [rsp+68h+var_48], 2
0x18000980c  call    _tlgWriteTransfer_EventWriteTransfer
0x180009811  mov     rcx, [rsp+68h+var_18]
0x180009816  xor     rcx, rsp; StackCookie
0x180009819  call    __security_check_cookie
0x18000981e  add     rsp, 68h
0x180009822  retn
```
