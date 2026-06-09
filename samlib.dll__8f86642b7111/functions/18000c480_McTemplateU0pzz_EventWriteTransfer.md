# McTemplateU0pzz_EventWriteTransfer

- ea: `0x18000c480`
- end: `0x18000c54b`
- name: `McTemplateU0pzz_EventWriteTransfer`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c50`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000c480`

## pseudocode

```c
ULONG __fastcall McTemplateU0pzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  const wchar_t *v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v13; // [rsp+40h] [rbp-40h]
  __int64 v14; // [rsp+48h] [rbp-38h]
  const wchar_t *v15; // [rsp+50h] [rbp-30h]
  int v16; // [rsp+58h] [rbp-28h]
  int v17; // [rsp+5Ch] [rbp-24h]
  const wchar_t *v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+6Ch] [rbp-14h]
  __int64 v21; // [rsp+A0h] [rbp+20h] BYREF

  v21 = a3;
  v14 = 8;
  v13 = &v21;
  v5 = -1;
  v6 = 10;
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
  v16 = v8;
  v9 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v17 = 0;
  v15 = a4;
  v10 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v6 = 2 * v5 + 2;
    v10 = a5 == 0;
  }
  if ( v10 )
    v9 = L"NULL";
  v19 = v6;
  v18 = v9;
  v20 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v9,
           (const EVENT_DESCRIPTOR *)SamLookupDomainInSamServerEntry,
           0,
           4u,
           &v12);
}

```

## disassembly

```asm
0x18000c480  mov     [rsp-8+arg_10], r8
0x18000c485  push    rbp
0x18000c486  mov     rbp, rsp
0x18000c489  sub     rsp, 80h
0x18000c490  mov     rax, cs:__security_cookie
0x18000c497  xor     rax, rsp
0x18000c49a  mov     [rbp+var_10], rax
0x18000c49e  lea     rax, [rbp+arg_10]
0x18000c4a2  mov     [rbp+var_38], 8
0x18000c4aa  xor     r8d, r8d
0x18000c4ad  mov     [rbp+var_40], rax
0x18000c4b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c4b5  lea     edx, [r8+0Ah]
0x18000c4b9  test    r9, r9
0x18000c4bc  jz      short loc_18000C4D4
0x18000c4be  mov     rcx, rax
0x18000c4c1  inc     rcx
0x18000c4c4  cmp     [r9+rcx*2], r8w
0x18000c4c9  jnz     short loc_18000C4C1
0x18000c4cb  lea     ecx, ds:2[rcx*2]
0x18000c4d2  jmp     short loc_18000C4D6
0x18000c4d4  mov     ecx, edx
0x18000c4d6  test    r9, r9
0x18000c4d9  mov     [rbp+var_28], ecx
0x18000c4dc  mov     rcx, [rbp+arg_20]
0x18000c4e0  lea     r10, aNull_0; "NULL"
0x18000c4e7  cmovz   r9, r10
0x18000c4eb  mov     [rbp+var_24], r8d
0x18000c4ef  mov     [rbp+var_30], r9
0x18000c4f3  test    rcx, rcx
0x18000c4f6  jz      short loc_18000C50C
0x18000c4f8  inc     rax
0x18000c4fb  cmp     [rcx+rax*2], r8w
0x18000c500  jnz     short loc_18000C4F8
0x18000c502  lea     edx, ds:2[rax*2]
0x18000c509  test    rcx, rcx
0x18000c50c  cmovz   rcx, r10
0x18000c510  mov     [rbp+var_18], edx
0x18000c513  lea     rax, [rbp+var_50]
0x18000c517  mov     [rbp+var_20], rcx
0x18000c51b  lea     rdx, SamLookupDomainInSamServerEntry
0x18000c522  mov     [rsp+80h+var_60], rax
0x18000c527  mov     r9d, 4
0x18000c52d  mov     [rbp+var_14], r8d
0x18000c531  call    McGenEventWrite_EventWriteTransfer
0x18000c536  mov     rcx, [rbp+var_10]
0x18000c53a  xor     rcx, rsp; StackCookie
0x18000c53d  call    __security_check_cookie
0x18000c542  add     rsp, 80h
0x18000c549  pop     rbp
0x18000c54a  retn
```
