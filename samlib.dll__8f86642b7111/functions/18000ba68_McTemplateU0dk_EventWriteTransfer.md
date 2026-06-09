# McTemplateU0dk_EventWriteTransfer

- ea: `0x18000ba68`
- end: `0x18000baf0`
- name: `McTemplateU0dk_EventWriteTransfer`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001a30`
- `0x180001c50`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000ba68`

## pseudocode

```c
ULONG __fastcall McTemplateU0dk_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, __int64 *a4)
{
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  int *v7; // [rsp+40h] [rbp-38h]
  __int64 v8; // [rsp+48h] [rbp-30h]
  __int64 *v9; // [rsp+50h] [rbp-28h]
  int v10; // [rsp+58h] [rbp-20h]
  int v11; // [rsp+5Ch] [rbp-1Ch]
  int v12; // [rsp+90h] [rbp+18h] BYREF

  v12 = a3;
  v8 = 4;
  v7 = &v12;
  if ( a4 )
    v4 = 4 * *((unsigned __int8 *)a4 + 1) + 8;
  else
    v4 = 8;
  v10 = v4;
  v11 = 0;
  if ( !a4 )
    a4 = &qword_180020BB8;
  v9 = a4;
  return McGenEventWrite_EventWriteTransfer((__int64)&qword_180020BB8, a2, a3, 3u, &v6);
}

```

## disassembly

```asm
0x18000ba68  mov     r11, rsp
0x18000ba6b  mov     [r11+18h], r8d
0x18000ba6f  sub     rsp, 78h
0x18000ba73  mov     rax, cs:__security_cookie
0x18000ba7a  xor     rax, rsp
0x18000ba7d  mov     [rsp+78h+var_18], rax
0x18000ba82  mov     qword ptr [r11-30h], 4
0x18000ba8a  lea     rax, [r11+18h]
0x18000ba8e  mov     [r11-38h], rax
0x18000ba92  test    r9, r9
0x18000ba95  jz      short loc_18000BAA5
0x18000ba97  movzx   eax, byte ptr [r9+1]
0x18000ba9c  lea     eax, ds:8[rax*4]
0x18000baa3  jmp     short loc_18000BAAA
0x18000baa5  mov     eax, 8
0x18000baaa  test    r9, r9
0x18000baad  mov     [rsp+78h+var_20], eax
0x18000bab1  lea     rcx, qword_180020BB8
0x18000bab8  mov     [rsp+78h+var_1C], 0
0x18000bac0  cmovz   r9, rcx
0x18000bac4  lea     rax, [rsp+78h+var_48]
0x18000bac9  mov     [rsp+78h+var_28], r9
0x18000bace  mov     r9d, 3
0x18000bad4  mov     [rsp+78h+var_58], rax
0x18000bad9  call    McGenEventWrite_EventWriteTransfer
0x18000bade  mov     rcx, [rsp+78h+var_18]
0x18000bae3  xor     rcx, rsp; StackCookie
0x18000bae6  call    __security_check_cookie
0x18000baeb  add     rsp, 78h
0x18000baef  retn
```
