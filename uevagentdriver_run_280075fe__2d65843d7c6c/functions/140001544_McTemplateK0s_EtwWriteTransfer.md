# McTemplateK0s_EtwWriteTransfer

- ea: `0x140001544`
- end: `0x1400015ba`
- name: `McTemplateK0s_EtwWriteTransfer`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001118`
- `0x140001168`
- `0x1400011b0`
- `0x140001298`

## callees

- `0x140001030`
- `0x140001544`
- `0x140001a30`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0s_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, const char *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-38h] BYREF
  const char *v8; // [rsp+40h] [rbp-28h]
  int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  v9 = v5;
  v10 = 0;
  if ( !a4 )
    a4 = "NULL";
  v8 = a4;
  return McGenEventWrite_EtwWriteTransfer((__int64)"NULL", a2, a3, 2u, &v7);
}

```

## disassembly

```asm
0x140001544  sub     rsp, 68h
0x140001548  mov     rax, cs:__security_cookie
0x14000154f  xor     rax, rsp
0x140001552  mov     [rsp+68h+var_18], rax
0x140001557  test    r9, r9
0x14000155a  jz      short loc_14000156E
0x14000155c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001560  inc     rax
0x140001563  cmp     byte ptr [r9+rax], 0
0x140001568  jnz     short loc_140001560
0x14000156a  inc     eax
0x14000156c  jmp     short loc_140001573
0x14000156e  mov     eax, 5
0x140001573  test    r9, r9
0x140001576  mov     [rsp+68h+var_20], eax
0x14000157a  lea     rcx, aNull; "NULL"
0x140001581  mov     [rsp+68h+var_1C], 0
0x140001589  cmovz   r9, rcx
0x14000158d  lea     rax, [rsp+68h+var_38]
0x140001592  mov     [rsp+68h+var_28], r9
0x140001597  mov     r9d, 2
0x14000159d  mov     [rsp+68h+var_48], rax
0x1400015a2  call    McGenEventWrite_EtwWriteTransfer
0x1400015a7  mov     rcx, [rsp+68h+var_18]
0x1400015ac  xor     rcx, rsp; StackCookie
0x1400015af  call    __security_check_cookie
0x1400015b4  add     rsp, 68h
0x1400015b8  retn
```
