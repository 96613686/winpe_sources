# McTemplateU0s_EventWriteTransfer

- ea: `0x1800024d4`
- end: `0x180002549`
- name: `McTemplateU0s_EventWriteTransfer`
- size: `117`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *)`
- caller_count: `150`
- callee_count: `3`
- tags: ``

## callers

- `0x180002240`
- `0x180003540`
- `0x180003930`
- `0x180003a30`
- `0x180003b50`
- `0x180003c30`
- `0x18000401c`
- `0x1800042c4`
- `0x1800043a8`
- `0x1800046b0`
- `0x180004a30`
- `0x180004cf0`
- `0x180004de0`
- `0x180004f50`
- `0x180005040`
- `0x180005190`
- `0x18000550c`
- `0x1800057b4`
- `0x180005af8`
- `0x180005ce0`
- `0x180005e30`
- `0x180006088`
- `0x180006170`
- `0x180006200`
- `0x1800062c0`
- `0x1800063fc`
- `0x180006a78`
- `0x180006cd0`
- `0x180006fa0`
- `0x180007660`
- `0x1800078d8`
- `0x180007e2c`
- `0x180007f68`
- `0x180008070`
- `0x180008220`
- `0x18000855c`
- `0x180008710`
- `0x1800087e0`
- `0x180008cdc`
- `0x180008ec0`
- `0x180008f00`
- `0x180009728`
- `0x180009948`
- `0x180009bc0`
- `0x180009c70`
- `0x180009da0`
- `0x180009e60`
- `0x18000a964`
- `0x18000ab30`
- `0x18000ac18`

## callees

- `0x18000247c`
- `0x1800024d4`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0s_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const char *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = v3 + 1;
  }
  else
  {
    v4 = 5;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = "NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x1800024d4  sub     rsp, 68h
0x1800024d8  mov     rax, cs:__security_cookie
0x1800024df  xor     rax, rsp
0x1800024e2  mov     [rsp+68h+var_18], rax
0x1800024e7  test    r8, r8
0x1800024ea  jz      short loc_1800024FE
0x1800024ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800024f0  inc     rax
0x1800024f3  cmp     byte ptr [r8+rax], 0
0x1800024f8  jnz     short loc_1800024F0
0x1800024fa  inc     eax
0x1800024fc  jmp     short loc_180002503
0x1800024fe  mov     eax, 5
0x180002503  test    r8, r8
0x180002506  mov     [rsp+68h+var_20], eax
0x18000250a  lea     rcx, aNull; "NULL"
0x180002511  mov     [rsp+68h+var_1C], 0
0x180002519  cmovz   r8, rcx
0x18000251d  lea     rax, [rsp+68h+var_38]
0x180002522  mov     r9d, 2
0x180002528  mov     [rsp+68h+var_28], r8
0x18000252d  mov     [rsp+68h+var_48], rax
0x180002532  call    McGenEventWrite_EventWriteTransfer
0x180002537  mov     rcx, [rsp+68h+var_18]
0x18000253c  xor     rcx, rsp; StackCookie
0x18000253f  call    __security_check_cookie
0x180002544  add     rsp, 68h
0x180002548  retn
```
