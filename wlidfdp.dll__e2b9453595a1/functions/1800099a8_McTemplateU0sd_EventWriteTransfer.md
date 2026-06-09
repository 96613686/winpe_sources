# McTemplateU0sd_EventWriteTransfer

- ea: `0x1800099a8`
- end: `0x180009a37`
- name: `McTemplateU0sd_EventWriteTransfer`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800054dc`
- `0x180008f6c`
- `0x180008fd4`

## callees

- `0x1800027f0`
- `0x180009950`
- `0x1800099a8`

## pseudocode

```c
ULONG __fastcall McTemplateU0sd_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x1800099a8  mov     [rsp+arg_18], r9d
0x1800099ad  sub     rsp, 78h
0x1800099b1  mov     rax, cs:__security_cookie
0x1800099b8  xor     rax, rsp
0x1800099bb  mov     [rsp+78h+var_18], rax
0x1800099c0  xor     r9d, r9d
0x1800099c3  test    r8, r8
0x1800099c6  jz      short loc_1800099D9
0x1800099c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800099cc  inc     rax
0x1800099cf  cmp     [r8+rax], r9b
0x1800099d3  jnz     short loc_1800099CC
0x1800099d5  inc     eax
0x1800099d7  jmp     short loc_1800099DE
0x1800099d9  mov     eax, 5
0x1800099de  mov     [rsp+78h+var_30], eax
0x1800099e2  lea     rcx, aNull; "NULL"
0x1800099e9  lea     rax, [rsp+78h+arg_18]
0x1800099f1  mov     [rsp+78h+var_2C], r9d
0x1800099f6  test    r8, r8
0x1800099f9  mov     [rsp+78h+var_28], rax
0x1800099fe  lea     rax, [rsp+78h+var_48]
0x180009a03  mov     [rsp+78h+var_20], 4
0x180009a0c  cmovz   r8, rcx
0x180009a10  mov     [rsp+78h+var_58], rax
0x180009a15  mov     r9d, 3
0x180009a1b  mov     [rsp+78h+var_38], r8
0x180009a20  call    McGenEventWrite_EventWriteTransfer
0x180009a25  mov     rcx, [rsp+78h+var_18]
0x180009a2a  xor     rcx, rsp; StackCookie
0x180009a2d  call    __security_check_cookie
0x180009a32  add     rsp, 78h
0x180009a36  retn
```
