# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000a510`
- end: `0x18000a582`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a5fc`

## callees

- `0x18000163c`
- `0x18000a510`
- `0x18000e990`

## pseudocode

```c
int __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(__int64 a1, const GUID *a2)
{
  __int64 v2; // rax
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF

  LODWORD(v2) = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 > 5u )
  {
    v2 = *(_QWORD *)(a1 + 16);
    if ( (v2 & 0x200000000000LL) != 0 )
    {
      LODWORD(v2) = 0;
      if ( (*(_QWORD *)(a1 + 24) & 0x200000000000LL) == *(_QWORD *)(a1 + 24) )
        LODWORD(v2) = tlgWriteTransfer_EventWriteTransfer(a1, (unsigned __int8 *)&word_180017A6E, a2, 0, 2u, &v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000a510  sub     rsp, 68h
0x18000a514  mov     rax, cs:__security_cookie
0x18000a51b  xor     rax, rsp
0x18000a51e  mov     [rsp+68h+var_18], rax
0x18000a523  mov     eax, [rcx]
0x18000a525  mov     r8, rdx
0x18000a528  cmp     eax, 5
0x18000a52b  jbe     short loc_18000A570
0x18000a52d  mov     rdx, [rcx+18h]
0x18000a531  mov     r9, 200000000000h
0x18000a53b  mov     rax, [rcx+10h]
0x18000a53f  test    r9, rax
0x18000a542  jz      short loc_18000A570
0x18000a544  mov     rax, rdx
0x18000a547  and     rax, r9
0x18000a54a  cmp     rax, rdx
0x18000a54d  jnz     short loc_18000A570
0x18000a54f  lea     rax, [rsp+68h+var_38]
0x18000a554  xor     r9d, r9d
0x18000a557  mov     [rsp+68h+var_40], rax
0x18000a55c  lea     rdx, word_180017A6E
0x18000a563  mov     [rsp+68h+var_48], 2
0x18000a56b  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a570  mov     rcx, [rsp+68h+var_18]
0x18000a575  xor     rcx, rsp; StackCookie
0x18000a578  call    __security_check_cookie
0x18000a57d  add     rsp, 68h
0x18000a581  retn
```
