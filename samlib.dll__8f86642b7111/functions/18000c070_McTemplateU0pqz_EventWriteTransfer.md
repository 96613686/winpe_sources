# McTemplateU0pqz_EventWriteTransfer

- ea: `0x18000c070`
- end: `0x18000c11a`
- name: `McTemplateU0pqz_EventWriteTransfer`
- size: `170`
- prototype: ``
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011f0`
- `0x180001450`
- `0x180001a30`
- `0x180002530`
- `0x180002870`
- `0x1800033c0`
- `0x180003760`
- `0x1800038b0`
- `0x18000ca60`
- `0x18000e6e0`
- `0x18000e9c0`
- `0x18000f5c0`
- `0x180010830`
- `0x180010a40`
- `0x1800114c0`
- `0x1800116c0`
- `0x180011aa0`
- `0x180011cb0`
- `0x1800120d0`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000c070`

## pseudocode

```c
ULONG __fastcall McTemplateU0pqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        const wchar_t *a5)
{
  const wchar_t *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v10; // [rsp+40h] [rbp-40h]
  __int64 v11; // [rsp+48h] [rbp-38h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  const wchar_t *v14; // [rsp+60h] [rbp-20h]
  int v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+6Ch] [rbp-14h]
  __int64 v17; // [rsp+A0h] [rbp+20h] BYREF
  int v18; // [rsp+A8h] [rbp+28h] BYREF

  v18 = a4;
  v17 = a3;
  v5 = a5;
  v10 = &v17;
  v11 = 8;
  v12 = &v18;
  v13 = 4;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  v15 = v7;
  v16 = 0;
  if ( !a5 )
    v5 = L"NULL";
  v14 = v5;
  return McGenEventWrite_EventWriteTransfer((__int64)v5, a2, (__int64)L"NULL", 4u, &v9);
}

```

## disassembly

```asm
0x18000c070  mov     [rsp-8+arg_18], r9d
0x18000c075  mov     [rsp-8+arg_10], r8
0x18000c07a  push    rbp
0x18000c07b  mov     rbp, rsp
0x18000c07e  sub     rsp, 80h
0x18000c085  mov     rax, cs:__security_cookie
0x18000c08c  xor     rax, rsp
0x18000c08f  mov     [rbp+var_10], rax
0x18000c093  mov     rcx, [rbp+arg_20]
0x18000c097  lea     rax, [rbp+arg_10]
0x18000c09b  xor     r9d, r9d
0x18000c09e  mov     [rbp+var_40], rax
0x18000c0a2  mov     [rbp+var_38], 8
0x18000c0aa  lea     rax, [rbp+arg_18]
0x18000c0ae  mov     [rbp+var_30], rax
0x18000c0b2  lea     r10d, [r9+4]
0x18000c0b6  mov     [rbp+var_28], r10
0x18000c0ba  test    rcx, rcx
0x18000c0bd  jz      short loc_18000C0D6
0x18000c0bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c0c3  inc     rax
0x18000c0c6  cmp     [rcx+rax*2], r9w
0x18000c0cb  jnz     short loc_18000C0C3
0x18000c0cd  lea     eax, ds:2[rax*2]
0x18000c0d4  jmp     short loc_18000C0DB
0x18000c0d6  mov     eax, 0Ah
0x18000c0db  test    rcx, rcx
0x18000c0de  mov     [rbp+var_18], eax
0x18000c0e1  lea     r8, aNull_0; "NULL"
0x18000c0e8  mov     [rbp+var_14], r9d
0x18000c0ec  cmovz   rcx, r8
0x18000c0f0  lea     rax, [rbp+var_50]
0x18000c0f4  mov     r9d, r10d
0x18000c0f7  mov     [rbp+var_20], rcx
0x18000c0fb  mov     [rsp+80h+var_60], rax
0x18000c100  call    McGenEventWrite_EventWriteTransfer
0x18000c105  mov     rcx, [rbp+var_10]
0x18000c109  xor     rcx, rsp; StackCookie
0x18000c10c  call    __security_check_cookie
0x18000c111  add     rsp, 80h
0x18000c118  pop     rbp
0x18000c119  retn
```
