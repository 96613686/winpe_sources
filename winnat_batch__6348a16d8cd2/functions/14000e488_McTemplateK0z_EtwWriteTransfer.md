# McTemplateK0z_EtwWriteTransfer

- ea: `0x14000e488`
- end: `0x14000e50a`
- name: `McTemplateK0z_EtwWriteTransfer`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x140009034`
- `0x140009b04`
- `0x14000ee40`
- `0x14000f130`
- `0x14000f288`
- `0x14000fc88`
- `0x140011870`
- `0x140011cfc`
- `0x1400121c8`
- `0x140015b28`
- `0x14001b1fc`

## callees

- `0x1400095bc`
- `0x14000e488`
- `0x14001ede0`

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
0x14000e488  sub     rsp, 68h
0x14000e48c  mov     rax, cs:__security_cookie
0x14000e493  xor     rax, rsp
0x14000e496  mov     [rsp+68h+var_18], rax
0x14000e49b  xor     r8d, r8d
0x14000e49e  test    r9, r9
0x14000e4a1  jz      short loc_14000E4BA
0x14000e4a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e4a7  inc     rax
0x14000e4aa  cmp     [r9+rax*2], r8w
0x14000e4af  jnz     short loc_14000E4A7
0x14000e4b1  lea     eax, ds:2[rax*2]
0x14000e4b8  jmp     short loc_14000E4BF
0x14000e4ba  mov     eax, 0Ah
0x14000e4bf  test    r9, r9
0x14000e4c2  mov     [rsp+68h+var_20], eax
0x14000e4c6  lea     rdx, aNull; "NULL"
0x14000e4cd  mov     [rsp+68h+var_1C], r8d
0x14000e4d2  cmovz   r9, rdx
0x14000e4d6  lea     rax, [rsp+68h+var_38]
0x14000e4db  mov     [rsp+68h+var_28], r9
0x14000e4e0  lea     rdx, WINNAT_MEMORY_ALLOCATION_FAILURE
0x14000e4e7  mov     r9d, 2
0x14000e4ed  mov     [rsp+68h+var_48], rax
0x14000e4f2  call    McGenEventWrite_EtwWriteTransfer
0x14000e4f7  mov     rcx, [rsp+68h+var_18]
0x14000e4fc  xor     rcx, rsp; StackCookie
0x14000e4ff  call    __security_check_cookie
0x14000e504  add     rsp, 68h
0x14000e508  retn
```
