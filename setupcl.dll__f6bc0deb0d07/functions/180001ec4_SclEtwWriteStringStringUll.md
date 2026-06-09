# SclEtwWriteStringStringUll

- ea: `0x180001ec4`
- end: `0x180001f68`
- name: `SclEtwWriteStringStringUll`
- size: `164`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003408`

## callees

- `0x180001ec4`
- `0x1800179e0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180001f50`
- `ntdll!EtwEventWrite` at `0x180001f50`

## pseudocode

```c
void __fastcall SclEtwWriteStringStringUll(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // [rsp+20h] [rbp-48h] BYREF
  int v9; // [rsp+28h] [rbp-40h]
  int v10; // [rsp+2Ch] [rbp-3Ch]
  __int64 v11; // [rsp+30h] [rbp-38h]
  int v12; // [rsp+38h] [rbp-30h]
  int v13; // [rsp+3Ch] [rbp-2Ch]
  char *v14; // [rsp+40h] [rbp-28h]
  __int64 v15; // [rsp+48h] [rbp-20h]

  v5 = *(_QWORD *)(a1 + 32);
  if ( v5 )
  {
    v6 = -1;
    v8 = a3;
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(a3 + 2 * v7) );
    v10 = 0;
    v9 = 2 * v7 + 2;
    v11 = a4;
    do
      ++v6;
    while ( *(_WORD *)(a4 + 2 * v6) );
    v13 = 0;
    v12 = 2 * v6 + 2;
    v15 = 8;
    v14 = &a5;
    ((void (__fastcall *)(__int64, __int64 *, __int64, __int64 *))EtwEventWrite)(v5, SclEvent_Generic_Statistic, 3, &v8);
  }
}

```

## disassembly

```asm
0x180001ec4  sub     rsp, 68h
0x180001ec8  mov     rax, cs:__security_cookie
0x180001ecf  xor     rax, rsp
0x180001ed2  mov     [rsp+68h+var_18], rax
0x180001ed7  mov     rcx, [rcx+20h]
0x180001edb  xor     r10d, r10d
0x180001ede  test    rcx, rcx
0x180001ee1  jz      short loc_180001F56
0x180001ee3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001ee7  mov     [rsp+68h+var_48], r8
0x180001eec  mov     rax, rdx
0x180001eef  inc     rax
0x180001ef2  cmp     [r8+rax*2], r10w
0x180001ef7  jnz     short loc_180001EEF
0x180001ef9  lea     eax, ds:2[rax*2]
0x180001f00  mov     [rsp+68h+var_3C], r10d
0x180001f05  mov     [rsp+68h+var_40], eax
0x180001f09  mov     [rsp+68h+var_38], r9
0x180001f0e  inc     rdx
0x180001f11  cmp     [r9+rdx*2], r10w
0x180001f16  jnz     short loc_180001F0E
0x180001f18  lea     eax, ds:2[rdx*2]
0x180001f1f  mov     [rsp+68h+var_2C], r10d
0x180001f24  mov     [rsp+68h+var_30], eax
0x180001f28  lea     r9, [rsp+68h+var_48]
0x180001f2d  lea     rax, [rsp+68h+arg_20]
0x180001f35  mov     [rsp+68h+var_20], 8
0x180001f3e  mov     r8d, 3
0x180001f44  mov     [rsp+68h+var_28], rax
0x180001f49  lea     rdx, SclEvent_Generic_Statistic
0x180001f50  call    cs:__imp_EtwEventWrite
0x180001f56  mov     rcx, [rsp+68h+var_18]
0x180001f5b  xor     rcx, rsp; StackCookie
0x180001f5e  call    __security_check_cookie
0x180001f63  add     rsp, 68h
0x180001f67  retn
```
