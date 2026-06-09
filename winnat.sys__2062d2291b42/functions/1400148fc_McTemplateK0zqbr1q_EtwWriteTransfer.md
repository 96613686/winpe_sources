# McTemplateK0zqbr1q_EtwWriteTransfer

- ea: `0x1400148fc`
- end: `0x1400149b5`
- name: `McTemplateK0zqbr1q_EtwWriteTransfer`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140031808`
- `0x140032604`

## callees

- `0x1400095bc`
- `0x1400148fc`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zqbr1q_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4,
        int a5,
        __int64 a6,
        char a7)
{
  __int64 v7; // rax
  int v8; // eax
  int v10; // [rsp+30h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-21h] BYREF
  const wchar_t *v12; // [rsp+50h] [rbp-11h]
  int v13; // [rsp+58h] [rbp-9h]
  int v14; // [rsp+5Ch] [rbp-5h]
  int *v15; // [rsp+60h] [rbp-1h]
  __int64 v16; // [rsp+68h] [rbp+7h]
  __int64 v17; // [rsp+70h] [rbp+Fh]
  __int64 v18; // [rsp+78h] [rbp+17h]
  char *v19; // [rsp+80h] [rbp+1Fh]
  __int64 v20; // [rsp+88h] [rbp+27h]

  v10 = 16;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v13 = v8;
  v14 = 0;
  v16 = 4;
  v15 = &v10;
  if ( !a4 )
    a4 = L"NULL";
  v17 = a6;
  v19 = &a7;
  v12 = a4;
  v18 = 16;
  v20 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, (__int64)L"NULL", 5u, &v11);
}

```

## disassembly

```asm
0x1400148fc  push    rbp
0x1400148fe  lea     rbp, [rsp-3Fh]
0x140014903  sub     rsp, 0A0h
0x14001490a  mov     rax, cs:__security_cookie
0x140014911  xor     rax, rsp
0x140014914  mov     [rbp+3Fh+var_10], rax
0x140014918  xor     r10d, r10d
0x14001491b  mov     r11d, 10h
0x140014921  mov     [rbp+3Fh+var_70], r11d
0x140014925  test    r9, r9
0x140014928  jz      short loc_140014941
0x14001492a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001492e  inc     rax
0x140014931  cmp     [r9+rax*2], r10w
0x140014936  jnz     short loc_14001492E
0x140014938  lea     eax, ds:2[rax*2]
0x14001493f  jmp     short loc_140014946
0x140014941  mov     eax, 0Ah
0x140014946  mov     [rbp+3Fh+var_48], eax
0x140014949  lea     r8, aNull; "NULL"
0x140014950  test    r9, r9
0x140014953  mov     [rbp+3Fh+var_44], r10d
0x140014957  lea     rax, [rbp+3Fh+var_70]
0x14001495b  mov     [rbp+3Fh+var_38], 4
0x140014963  mov     [rbp+3Fh+var_40], rax
0x140014967  cmovz   r9, r8
0x14001496b  mov     rax, [rbp+3Fh+arg_28]
0x14001496f  mov     [rbp+3Fh+var_30], rax
0x140014973  lea     rax, [rbp+3Fh+arg_30]
0x140014977  mov     [rbp+3Fh+var_20], rax
0x14001497b  lea     rax, [rbp+3Fh+var_60]
0x14001497f  mov     [rbp+3Fh+var_50], r9
0x140014983  mov     r9d, 5
0x140014989  mov     [rsp+0A0h+var_80], rax
0x14001498e  mov     [rbp+3Fh+var_28], r11
0x140014992  mov     [rbp+3Fh+var_18], 4
0x14001499a  call    McGenEventWrite_EtwWriteTransfer
0x14001499f  mov     rcx, [rbp+3Fh+var_10]
0x1400149a3  xor     rcx, rsp; StackCookie
0x1400149a6  call    __security_check_cookie
0x1400149ab  add     rsp, 0A0h
0x1400149b2  pop     rbp
0x1400149b3  retn
```
