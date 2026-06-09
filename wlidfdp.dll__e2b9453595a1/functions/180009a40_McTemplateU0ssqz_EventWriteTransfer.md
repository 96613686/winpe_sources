# McTemplateU0ssqz_EventWriteTransfer

- ea: `0x180009a40`
- end: `0x180009b16`
- name: `McTemplateU0ssqz_EventWriteTransfer`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008edc`

## callees

- `0x1800027f0`
- `0x180009950`
- `0x180009a40`

## pseudocode

```c
ULONG __fastcall McTemplateU0ssqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const char *a3,
        const char *a4,
        char a5)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-19h] BYREF
  const char *v11; // [rsp+40h] [rbp-9h]
  int v12; // [rsp+48h] [rbp-1h]
  int v13; // [rsp+4Ch] [rbp+3h]
  const char *v14; // [rsp+50h] [rbp+7h]
  int v15; // [rsp+58h] [rbp+Fh]
  int v16; // [rsp+5Ch] [rbp+13h]
  char *v17; // [rsp+60h] [rbp+17h]
  __int64 v18; // [rsp+68h] [rbp+1Fh]
  const wchar_t *v19; // [rsp+70h] [rbp+27h]
  __int64 v20; // [rsp+78h] [rbp+2Fh]

  v5 = -1;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = (unsigned int)(v6 + 1);
  }
  else
  {
    v7 = 5;
  }
  v12 = v7;
  v13 = 0;
  if ( !a3 )
    a3 = "NULL";
  v11 = a3;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v8 = v5 + 1;
  }
  else
  {
    v8 = 5;
  }
  v15 = v8;
  v16 = 0;
  v17 = &a5;
  if ( !a4 )
    a4 = "NULL";
  v14 = a4;
  v19 = L"NULL";
  v18 = 4;
  v20 = 10;
  return McGenEventWrite_EventWriteTransfer(v7, a2, (__int64)a3, 5u, &v10);
}

```

## disassembly

```asm
0x180009a40  mov     [rsp-8+arg_0], rbx
0x180009a45  push    rbp
0x180009a46  lea     rbp, [rsp-47h]
0x180009a4b  sub     rsp, 90h
0x180009a52  mov     rax, cs:__security_cookie
0x180009a59  xor     rax, rsp
0x180009a5c  mov     [rbp+47h+var_10], rax
0x180009a60  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a64  xor     r10d, r10d
0x180009a67  mov     r11d, 5
0x180009a6d  test    r8, r8
0x180009a70  jz      short loc_180009A82
0x180009a72  mov     rcx, rax
0x180009a75  inc     rcx
0x180009a78  cmp     [r8+rcx], r10b
0x180009a7c  jnz     short loc_180009A75
0x180009a7e  inc     ecx
0x180009a80  jmp     short loc_180009A85
0x180009a82  mov     ecx, r11d
0x180009a85  test    r8, r8
0x180009a88  mov     [rbp+47h+var_48], ecx
0x180009a8b  lea     rbx, aNull; "NULL"
0x180009a92  mov     [rbp+47h+var_44], r10d
0x180009a96  cmovz   r8, rbx
0x180009a9a  mov     [rbp+47h+var_50], r8
0x180009a9e  test    r9, r9
0x180009aa1  jz      short loc_180009AB0
0x180009aa3  inc     rax
0x180009aa6  cmp     [r9+rax], r10b
0x180009aaa  jnz     short loc_180009AA3
0x180009aac  inc     eax
0x180009aae  jmp     short loc_180009AB3
0x180009ab0  mov     eax, r11d
0x180009ab3  mov     [rbp+47h+var_38], eax
0x180009ab6  test    r9, r9
0x180009ab9  lea     rax, [rbp+47h+arg_20]
0x180009abd  mov     [rbp+47h+var_34], r10d
0x180009ac1  mov     [rbp+47h+var_30], rax
0x180009ac5  cmovz   r9, rbx
0x180009ac9  lea     rax, aNull_0; "NULL"
0x180009ad0  mov     [rbp+47h+var_40], r9
0x180009ad4  mov     [rbp+47h+var_20], rax
0x180009ad8  mov     r9d, r11d
0x180009adb  lea     rax, [rbp+47h+var_60]
0x180009adf  mov     [rbp+47h+var_28], 4
0x180009ae7  mov     [rsp+90h+var_70], rax
0x180009aec  mov     [rbp+47h+var_18], 0Ah
0x180009af4  call    McGenEventWrite_EventWriteTransfer
0x180009af9  mov     rcx, [rbp+47h+var_10]
0x180009afd  xor     rcx, rsp; StackCookie
0x180009b00  call    __security_check_cookie
0x180009b05  mov     rbx, [rsp+90h+arg_0]
0x180009b0d  add     rsp, 90h
0x180009b14  pop     rbp
0x180009b15  retn
```
