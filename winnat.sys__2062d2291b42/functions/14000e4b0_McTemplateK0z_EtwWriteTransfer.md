# McTemplateK0z_EtwWriteTransfer

- ea: `0x14000e4b0`
- end: `0x14000e532`
- name: `McTemplateK0z_EtwWriteTransfer`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140009034`
- `0x140009b04`
- `0x14000ee98`
- `0x14000f188`
- `0x14000f2e0`
- `0x14000fce8`
- `0x1400118d0`
- `0x14001263c`
- `0x140012b08`
- `0x1400164a8`
- `0x140016760`
- `0x14001b6dc`

## callees

- `0x1400095bc`
- `0x14000e4b0`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0z_EtwWriteTransfer(REGHANDLE *a1, __int64 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-28h]
  int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v8 = a4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)WINNAT_MEMORY_ALLOCATION_FAILURE, 0, 2u, &v7);
}

```

## disassembly

```asm
0x14000e4b0  sub     rsp, 68h
0x14000e4b4  mov     rax, cs:__security_cookie
0x14000e4bb  xor     rax, rsp
0x14000e4be  mov     [rsp+68h+var_18], rax
0x14000e4c3  xor     r8d, r8d
0x14000e4c6  test    r9, r9
0x14000e4c9  jz      short loc_14000E4E2
0x14000e4cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e4cf  inc     rax
0x14000e4d2  cmp     [r9+rax*2], r8w
0x14000e4d7  jnz     short loc_14000E4CF
0x14000e4d9  lea     eax, ds:2[rax*2]
0x14000e4e0  jmp     short loc_14000E4E7
0x14000e4e2  mov     eax, 0Ah
0x14000e4e7  test    r9, r9
0x14000e4ea  mov     [rsp+68h+var_20], eax
0x14000e4ee  lea     rdx, aNull; "NULL"
0x14000e4f5  mov     [rsp+68h+var_1C], r8d
0x14000e4fa  cmovz   r9, rdx
0x14000e4fe  lea     rax, [rsp+68h+var_38]
0x14000e503  mov     [rsp+68h+var_28], r9
0x14000e508  lea     rdx, WINNAT_MEMORY_ALLOCATION_FAILURE
0x14000e50f  mov     r9d, 2
0x14000e515  mov     [rsp+68h+var_48], rax
0x14000e51a  call    McGenEventWrite_EtwWriteTransfer
0x14000e51f  mov     rcx, [rsp+68h+var_18]
0x14000e524  xor     rcx, rsp; StackCookie
0x14000e527  call    __security_check_cookie
0x14000e52c  add     rsp, 68h
0x14000e530  retn
```
