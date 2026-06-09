# McTemplateK0qzqx_EtwWriteTransfer

- ea: `0x140003b00`
- end: `0x140003be0`
- name: `McTemplateK0qzqx_EtwWriteTransfer`
- size: `224`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e484`
- `0x140010ad8`
- `0x140010d7c`

## callees

- `0x140003b00`
- `0x140003bf0`
- `0x140005050`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qzqx_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        const wchar_t *a5,
        char a6,
        char a7)
{
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-68h] BYREF
  int *v13; // [rsp+40h] [rbp-58h]
  __int64 v14; // [rsp+48h] [rbp-50h]
  const wchar_t *v15; // [rsp+50h] [rbp-48h]
  int v16; // [rsp+58h] [rbp-40h]
  int v17; // [rsp+5Ch] [rbp-3Ch]
  char *v18; // [rsp+60h] [rbp-38h]
  __int64 v19; // [rsp+68h] [rbp-30h]
  char *v20; // [rsp+70h] [rbp-28h]
  __int64 v21; // [rsp+78h] [rbp-20h]
  int v22; // [rsp+B8h] [rbp+20h] BYREF

  v22 = a4;
  v7 = a5;
  v13 = &v22;
  v14 = 4;
  if ( a5 )
  {
    v8 = -1;
    while ( a5[++v8] != 0 )
      ;
    v10 = 2 * v8 + 2;
  }
  else
  {
    v10 = 10;
  }
  v16 = v10;
  v17 = 0;
  v18 = &a6;
  v19 = 4;
  v20 = &a7;
  if ( !a5 )
    v7 = L"NULL";
  v15 = v7;
  v21 = 8;
  return McGenEventWrite_EtwWriteTransfer((__int64)v7, a2, (__int64)L"NULL", 5u, &v12);
}

```

## disassembly

```asm
0x140003b00  mov     r11, rsp
0x140003b03  mov     [r11+20h], r9d
0x140003b07  sub     rsp, 98h
0x140003b0e  mov     rax, cs:__security_cookie
0x140003b15  xor     rax, rsp
0x140003b18  mov     [rsp+98h+var_18], rax
0x140003b20  mov     rcx, [rsp+98h+arg_20]
0x140003b28  lea     rax, [r11+20h]
0x140003b2c  xor     r9d, r9d
0x140003b2f  mov     [r11-58h], rax
0x140003b33  mov     qword ptr [r11-50h], 4
0x140003b3b  test    rcx, rcx
0x140003b3e  jz      short loc_140003B65
0x140003b40  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140003b47  nop     word ptr [rax+rax+00000000h]
0x140003b50  cmp     [rcx+rax*2+2], r9w
0x140003b56  lea     rax, [rax+1]
0x140003b5a  jnz     short loc_140003B50
0x140003b5c  lea     eax, ds:2[rax*2]
0x140003b63  jmp     short loc_140003B6A
0x140003b65  mov     eax, 0Ah
0x140003b6a  mov     [rsp+98h+var_40], eax
0x140003b6e  lea     r8, aNull; "NULL"
0x140003b75  lea     rax, [rsp+98h+arg_28]
0x140003b7d  mov     [rsp+98h+var_3C], r9d
0x140003b82  mov     [rsp+98h+var_38], rax
0x140003b87  test    rcx, rcx
0x140003b8a  lea     rax, [rsp+98h+arg_30]
0x140003b92  mov     [rsp+98h+var_30], 4
0x140003b9b  mov     [rsp+98h+var_28], rax
0x140003ba0  cmovz   rcx, r8
0x140003ba4  lea     rax, [rsp+98h+var_68]
0x140003ba9  mov     [rsp+98h+var_48], rcx
0x140003bae  mov     r9d, 5
0x140003bb4  mov     [rsp+98h+var_78], rax
0x140003bb9  mov     [rsp+98h+var_20], 8
0x140003bc2  call    McGenEventWrite_EtwWriteTransfer
0x140003bc7  mov     rcx, [rsp+98h+var_18]
0x140003bcf  xor     rcx, rsp; StackCookie
0x140003bd2  call    __security_check_cookie
0x140003bd7  add     rsp, 98h
0x140003bde  retn
```
