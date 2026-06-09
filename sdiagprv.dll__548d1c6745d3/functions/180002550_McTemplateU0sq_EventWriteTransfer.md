# McTemplateU0sq_EventWriteTransfer

- ea: `0x180002550`
- end: `0x1800025e4`
- name: `McTemplateU0sq_EventWriteTransfer`
- size: `148`
- prototype: `ULONG __fastcall(__int64, __int64, const char *, int)`
- caller_count: `130`
- callee_count: `3`
- tags: ``

## callers

- `0x180002240`
- `0x180003540`
- `0x180003930`
- `0x180003a30`
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
- `0x180006200`
- `0x1800062c0`
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
- `0x1800087e0`
- `0x180008cdc`
- `0x180008f00`
- `0x180009728`
- `0x180009948`
- `0x180009bc0`
- `0x180009c70`
- `0x180009e60`
- `0x18000a964`
- `0x18000ab30`
- `0x18000ac18`
- `0x18000b9f0`
- `0x18000c018`
- `0x18000c2a0`
- `0x18000c618`
- `0x18000c8b4`
- `0x18000c980`

## callees

- `0x18000247c`
- `0x180002550`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0sq_EventWriteTransfer(__int64 a1, __int64 a2, const char *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const char *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = "NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)"NULL",
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_DEBUG_FAIL,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x180002550  mov     [rsp+arg_18], r9d
0x180002555  sub     rsp, 78h
0x180002559  mov     rax, cs:__security_cookie
0x180002560  xor     rax, rsp
0x180002563  mov     [rsp+78h+var_18], rax
0x180002568  xor     edx, edx
0x18000256a  test    r8, r8
0x18000256d  jz      short loc_180002580
0x18000256f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002573  inc     rax
0x180002576  cmp     [r8+rax], dl
0x18000257a  jnz     short loc_180002573
0x18000257c  inc     eax
0x18000257e  jmp     short loc_180002585
0x180002580  mov     eax, 5
0x180002585  mov     [rsp+78h+var_30], eax
0x180002589  lea     rcx, aNull; "NULL"
0x180002590  lea     rax, [rsp+78h+arg_18]
0x180002598  mov     [rsp+78h+var_2C], edx
0x18000259c  test    r8, r8
0x18000259f  mov     [rsp+78h+var_28], rax
0x1800025a4  lea     rax, [rsp+78h+var_48]
0x1800025a9  mov     [rsp+78h+var_20], 4
0x1800025b2  cmovz   r8, rcx
0x1800025b6  mov     [rsp+78h+var_58], rax
0x1800025bb  mov     r9d, 3
0x1800025c1  mov     [rsp+78h+var_38], r8
0x1800025c6  lea     rdx, SDIAGPRV_EVENT_DEBUG_FAIL
0x1800025cd  call    McGenEventWrite_EventWriteTransfer
0x1800025d2  mov     rcx, [rsp+78h+var_18]
0x1800025d7  xor     rcx, rsp; StackCookie
0x1800025da  call    __security_check_cookie
0x1800025df  add     rsp, 78h
0x1800025e3  retn
```
