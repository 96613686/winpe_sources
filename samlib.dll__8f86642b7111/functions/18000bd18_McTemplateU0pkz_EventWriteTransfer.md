# McTemplateU0pkz_EventWriteTransfer

- ea: `0x18000bd18`
- end: `0x18000bddb`
- name: `McTemplateU0pkz_EventWriteTransfer`
- size: `195`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c650`
- `0x1800110c0`
- `0x1800112c0`

## callees

- `0x1800061d0`
- `0x180006620`
- `0x18000bd18`

## pseudocode

```c
ULONG __fastcall McTemplateU0pkz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 *a4,
        const wchar_t *a5)
{
  int v5; // eax
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v11; // [rsp+40h] [rbp-40h]
  __int64 v12; // [rsp+48h] [rbp-38h]
  __int64 *v13; // [rsp+50h] [rbp-30h]
  int v14; // [rsp+58h] [rbp-28h]
  int v15; // [rsp+5Ch] [rbp-24h]
  const wchar_t *v16; // [rsp+60h] [rbp-20h]
  int v17; // [rsp+68h] [rbp-18h]
  int v18; // [rsp+6Ch] [rbp-14h]
  __int64 v19; // [rsp+A0h] [rbp+20h] BYREF

  v19 = a3;
  v11 = &v19;
  v5 = 8;
  v12 = 8;
  if ( a4 )
    v5 = 4 * *((unsigned __int8 *)a4 + 1) + 8;
  v14 = v5;
  v15 = 0;
  if ( !a4 )
    a4 = &qword_180020BB8;
  v6 = a5;
  v13 = a4;
  if ( a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a5[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v17 = v8;
  v18 = 0;
  if ( !a5 )
    v6 = L"NULL";
  v16 = v6;
  return McGenEventWrite_EventWriteTransfer((__int64)v6, a2, (__int64)L"NULL", 4u, &v10);
}

```

## disassembly

```asm
0x18000bd18  mov     [rsp-8+arg_10], r8
0x18000bd1d  push    rbp
0x18000bd1e  mov     rbp, rsp
0x18000bd21  sub     rsp, 80h
0x18000bd28  mov     rax, cs:__security_cookie
0x18000bd2f  xor     rax, rsp
0x18000bd32  mov     [rbp+var_10], rax
0x18000bd36  lea     rax, [rbp+arg_10]
0x18000bd3a  xor     r10d, r10d
0x18000bd3d  mov     [rbp+var_40], rax
0x18000bd41  mov     eax, 8
0x18000bd46  mov     [rbp+var_38], rax
0x18000bd4a  test    r9, r9
0x18000bd4d  jz      short loc_18000BD5B
0x18000bd4f  movzx   eax, byte ptr [r9+1]
0x18000bd54  lea     eax, ds:8[rax*4]
0x18000bd5b  test    r9, r9
0x18000bd5e  mov     [rbp+var_28], eax
0x18000bd61  lea     rcx, qword_180020BB8
0x18000bd68  mov     [rbp+var_24], r10d
0x18000bd6c  cmovz   r9, rcx
0x18000bd70  mov     rcx, [rbp+arg_20]
0x18000bd74  mov     [rbp+var_30], r9
0x18000bd78  test    rcx, rcx
0x18000bd7b  jz      short loc_18000BD94
0x18000bd7d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bd81  inc     rax
0x18000bd84  cmp     [rcx+rax*2], r10w
0x18000bd89  jnz     short loc_18000BD81
0x18000bd8b  lea     eax, ds:2[rax*2]
0x18000bd92  jmp     short loc_18000BD99
0x18000bd94  mov     eax, 0Ah
0x18000bd99  test    rcx, rcx
0x18000bd9c  mov     [rbp+var_18], eax
0x18000bd9f  lea     r8, aNull_0; "NULL"
0x18000bda6  mov     [rbp+var_14], r10d
0x18000bdaa  cmovz   rcx, r8
0x18000bdae  lea     rax, [rbp+var_50]
0x18000bdb2  mov     r9d, 4
0x18000bdb8  mov     [rbp+var_20], rcx
0x18000bdbc  mov     [rsp+80h+var_60], rax
0x18000bdc1  call    McGenEventWrite_EventWriteTransfer
0x18000bdc6  mov     rcx, [rbp+var_10]
0x18000bdca  xor     rcx, rsp; StackCookie
0x18000bdcd  call    __security_check_cookie
0x18000bdd2  add     rsp, 80h
0x18000bdd9  pop     rbp
0x18000bdda  retn
```
