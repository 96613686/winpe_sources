# SclEtwWriteString

- ea: `0x180005a20`
- end: `0x180005a85`
- name: `SclEtwWriteString`
- size: `101`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006024`
- `0x18000b738`
- `0x180010f44`
- `0x1800111bc`

## callees

- `0x180005a20`
- `0x1800179e0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180005a6d`
- `ntdll!EtwEventWrite` at `0x180005a6d`

## pseudocode

```c
void __fastcall SclEtwWriteString(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+28h] [rbp-20h]
  int v7; // [rsp+2Ch] [rbp-1Ch]

  v3 = *(_QWORD *)(a1 + 32);
  if ( v3 )
  {
    v5 = a3;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(a3 + 2 * v4) );
    v7 = 0;
    v6 = 2 * v4 + 2;
    ((void (__fastcall *)(__int64, __int64, __int64, __int64 *))EtwEventWrite)(v3, a2, 1, &v5);
  }
}

```

## disassembly

```asm
0x180005a20  sub     rsp, 48h
0x180005a24  mov     rax, cs:__security_cookie
0x180005a2b  xor     rax, rsp
0x180005a2e  mov     [rsp+48h+var_18], rax
0x180005a33  mov     rcx, [rcx+20h]
0x180005a37  xor     r9d, r9d
0x180005a3a  test    rcx, rcx
0x180005a3d  jz      short loc_180005A73
0x180005a3f  mov     [rsp+48h+var_28], r8
0x180005a44  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005a48  inc     rax
0x180005a4b  cmp     [r8+rax*2], r9w
0x180005a50  jnz     short loc_180005A48
0x180005a52  lea     eax, ds:2[rax*2]
0x180005a59  mov     [rsp+48h+var_1C], r9d
0x180005a5e  lea     r9, [rsp+48h+var_28]
0x180005a63  mov     [rsp+48h+var_20], eax
0x180005a67  mov     r8d, 1
0x180005a6d  call    cs:__imp_EtwEventWrite
0x180005a73  mov     rcx, [rsp+48h+var_18]
0x180005a78  xor     rcx, rsp; StackCookie
0x180005a7b  call    __security_check_cookie
0x180005a80  add     rsp, 48h
0x180005a84  retn
```
