# McTemplateU0z_EtwEventWriteTransfer

- ea: `0x1800120b0`
- end: `0x18001212a`
- name: `McTemplateU0z_EtwEventWriteTransfer`
- size: `122`
- prototype: `__int64 __fastcall(__int64, int, const wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008d20`
- `0x180009bc4`
- `0x180009d70`

## callees

- `0x18000f970`
- `0x1800120b0`
- `0x180018970`

## pseudocode

```c
__int64 __fastcall McTemplateU0z_EtwEventWriteTransfer(__int64 a1, int a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  _BYTE v6[16]; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EtwEventWriteTransfer((unsigned int)L"NULL", a2, (_DWORD)a3, 2, (__int64)v6);
}

```

## disassembly

```asm
0x1800120b0  sub     rsp, 68h
0x1800120b4  mov     rax, cs:__security_cookie
0x1800120bb  xor     rax, rsp
0x1800120be  mov     [rsp+68h+var_18], rax
0x1800120c3  xor     r9d, r9d
0x1800120c6  test    r8, r8
0x1800120c9  jz      short loc_1800120E2
0x1800120cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800120cf  inc     rax
0x1800120d2  cmp     [r8+rax*2], r9w
0x1800120d7  jnz     short loc_1800120CF
0x1800120d9  lea     eax, ds:2[rax*2]
0x1800120e0  jmp     short loc_1800120E7
0x1800120e2  mov     eax, 0Ah
0x1800120e7  test    r8, r8
0x1800120ea  mov     [rsp+68h+var_20], eax
0x1800120ee  lea     rcx, aNull; "NULL"
0x1800120f5  mov     [rsp+68h+var_1C], r9d
0x1800120fa  cmovz   r8, rcx
0x1800120fe  lea     rax, [rsp+68h+var_38]
0x180012103  mov     r9d, 2
0x180012109  mov     [rsp+68h+var_28], r8
0x18001210e  mov     [rsp+68h+var_48], rax
0x180012113  call    McGenEventWrite_EtwEventWriteTransfer
0x180012118  mov     rcx, [rsp+68h+var_18]
0x18001211d  xor     rcx, rsp; StackCookie
0x180012120  call    __security_check_cookie
0x180012125  add     rsp, 68h
0x180012129  retn
```
