# SingletonHelpers::details::_tip_SingletonHelperRedirectionTest::evaluate(void)

- ea: `0x14005dbc4`
- end: `0x14005dd41`
- name: `?evaluate@_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@QEAAXXZ`
- size: `381`
- prototype: `void __fastcall(SingletonHelpers::details::_tip_SingletonHelperRedirectionTest *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14005dbb0`

## callees

- `0x140046a30`
- `0x14005dbc4`
- `0x14005e9c4`

## string_xrefs

- `0x14005dcb5`: `reason::other_instance_not_ready`
- `0x14005dd2f`: `shellcommon\internal\shell\inc\SingletonHelpers.h`

## pseudocode

```c
void __fastcall SingletonHelpers::details::_tip_SingletonHelperRedirectionTest::evaluate(
        SingletonHelpers::details::_tip_SingletonHelperRedirectionTest *this,
        const char *a2)
{
  __int64 v2; // r8
  char v3; // r10
  const char *v4; // rax
  __int64 v5; // r8
  char v6; // r9
  const char *v7; // rax
  __int64 v8; // r8
  __int16 v9; // r9
  const char *v10; // rdx
  const char *v11; // rdx
  char v12; // r9
  char v13; // r9
  char v14; // r9
  char v15; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_QWORD *)this + 1);
  if ( (*(_DWORD *)(v2 + 56) & 0x200) == 0 )
  {
    if ( !*(_BYTE *)(v2 + 152) )
    {
      *(_BYTE *)(v2 + 152) = 3;
      *(_WORD *)(v2 + 154) = 16385;
      *(_QWORD *)(v2 + 160) = 0;
    }
    return;
  }
  v3 = *((_BYTE *)this + 48);
  if ( v3 )
  {
    if ( *((_BYTE *)this + 49) )
    {
      v4 = tip2::details::reason_string((tip2::details *)"reason::claimed_singleton", a2);
      if ( *(_BYTE *)(v5 + 152) != v6 )
        return;
      *(_WORD *)(v5 + 154) = 5;
LABEL_24:
      *(_QWORD *)(v5 + 160) = v4;
      *(_BYTE *)(v5 + 152) = 1;
      return;
    }
    if ( !*((_BYTE *)this + 50) )
    {
      v7 = tip2::details::reason_string((tip2::details *)"reason::could_not_find_other_instance", a2);
      if ( *(_BYTE *)(v8 + 152) != (_BYTE)v9 )
        return;
      *(_WORD *)(v8 + 154) = v9;
      goto LABEL_11;
    }
  }
  v10 = (const char *)*((unsigned int *)this + 13);
  if ( !(_DWORD)v10 )
  {
    v4 = tip2::details::reason_string((tip2::details *)"reason::redirected_to_other_instance", v10);
    if ( *(_BYTE *)(v5 + 152) != v15 )
      return;
    *(_WORD *)(v5 + 154) = 4;
    goto LABEL_24;
  }
  v11 = (const char *)(unsigned int)((_DWORD)v10 - 1);
  if ( !(_DWORD)v11 )
  {
    if ( !v3 )
    {
      v4 = tip2::details::reason_string((tip2::details *)"reason::did_not_redirect", v11);
      if ( *(_BYTE *)(v5 + 152) != v14 )
        return;
      *(_WORD *)(v5 + 154) = 3;
      goto LABEL_24;
    }
    v7 = tip2::details::reason_string((tip2::details *)"reason::other_instance_not_ready", v11);
    if ( *(_BYTE *)(v8 + 152) != v13 )
      return;
    *(_WORD *)(v8 + 154) = 1;
LABEL_11:
    *(_BYTE *)(v8 + 152) = 3;
    *(_QWORD *)(v8 + 160) = v7;
    return;
  }
  if ( (_DWORD)v11 != 1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x7F,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
      0);
  v7 = tip2::details::reason_string((tip2::details *)"reason::timed_out_sending_message", v11);
  if ( *(_BYTE *)(v8 + 152) == v12 )
  {
    *(_WORD *)(v8 + 154) = 2;
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x14005dbc4  sub     rsp, 28h
0x14005dbc8  mov     r8, [rcx+8]
0x14005dbcc  xor     r9d, r9d; char *
0x14005dbcf  test    dword ptr [r8+38h], 200h
0x14005dbd7  jnz     short loc_14005DC04
0x14005dbd9  cmp     [r8+98h], r9b
0x14005dbe0  jnz     loc_14005DD25
0x14005dbe6  mov     byte ptr [r8+98h], 3
0x14005dbee  mov     word ptr [r8+9Ah], 4001h
0x14005dbf8  mov     [r8+0A0h], r9
0x14005dbff  jmp     loc_14005DD25
0x14005dc04  mov     r10b, [rcx+30h]
0x14005dc08  test    r10b, r10b
0x14005dc0b  jz      short loc_14005DC76
0x14005dc0d  cmp     [rcx+31h], r9b
0x14005dc11  jz      short loc_14005DC3B
0x14005dc13  lea     rcx, aReasonClaimedS; "reason::claimed_singleton"
0x14005dc1a  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14005dc1f  cmp     [r8+98h], r9b
0x14005dc26  jnz     loc_14005DD25
0x14005dc2c  mov     word ptr [r8+9Ah], 5
0x14005dc36  jmp     loc_14005DD16
0x14005dc3b  cmp     [rcx+32h], r9b
0x14005dc3f  jnz     short loc_14005DC76
0x14005dc41  lea     rcx, aReasonCouldNot; "reason::could_not_find_other_instance"
0x14005dc48  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14005dc4d  cmp     [r8+98h], r9b
0x14005dc54  jnz     loc_14005DD25
0x14005dc5a  mov     [r8+9Ah], r9w
0x14005dc62  mov     byte ptr [r8+98h], 3
0x14005dc6a  mov     [r8+0A0h], rax
0x14005dc71  jmp     loc_14005DD25
0x14005dc76  mov     edx, [rcx+34h]; char *
0x14005dc79  test    edx, edx
0x14005dc7b  jz      short loc_14005DCF7
0x14005dc7d  sub     edx, 1; char *
0x14005dc80  jz      short loc_14005DCB0
0x14005dc82  cmp     edx, 1
0x14005dc85  jnz     loc_14005DD2A
0x14005dc8b  lea     rcx, aReasonTimedOut; "reason::timed_out_sending_message"
0x14005dc92  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14005dc97  cmp     [r8+98h], r9b
0x14005dc9e  jnz     loc_14005DD25
0x14005dca4  mov     word ptr [r8+9Ah], 2
0x14005dcae  jmp     short loc_14005DC62
0x14005dcb0  test    r10b, r10b
0x14005dcb3  jz      short loc_14005DCD6
0x14005dcb5  lea     rcx, aReasonOtherIns; "reason::other_instance_not_ready"
0x14005dcbc  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14005dcc1  cmp     [r8+98h], r9b
0x14005dcc8  jnz     short loc_14005DD25
0x14005dcca  mov     word ptr [r8+9Ah], 1
0x14005dcd4  jmp     short loc_14005DC62
0x14005dcd6  lea     rcx, aReasonDidNotRe; "reason::did_not_redirect"
0x14005dcdd  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14005dce2  cmp     [r8+98h], r9b
0x14005dce9  jnz     short loc_14005DD25
0x14005dceb  mov     word ptr [r8+9Ah], 3
0x14005dcf5  jmp     short loc_14005DD16
0x14005dcf7  lea     rcx, aReasonRedirect; "reason::redirected_to_other_instance"
0x14005dcfe  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x14005dd03  cmp     [r8+98h], r9b
0x14005dd0a  jnz     short loc_14005DD25
0x14005dd0c  mov     word ptr [r8+9Ah], 4
0x14005dd16  mov     [r8+0A0h], rax
0x14005dd1d  mov     byte ptr [r8+98h], 1
0x14005dd25  add     rsp, 28h
0x14005dd29  retn
0x14005dd2a  mov     rcx, [rsp+28h]; this
0x14005dd2f  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Sing"...
0x14005dd36  mov     edx, 7Fh; void *
0x14005dd3b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
