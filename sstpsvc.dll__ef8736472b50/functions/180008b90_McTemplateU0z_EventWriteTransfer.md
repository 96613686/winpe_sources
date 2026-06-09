# McTemplateU0z_EventWriteTransfer

- ea: `0x180008b90`
- end: `0x180008c0b`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `123`
- prototype: ``
- caller_count: `63`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012b0`
- `0x180001b40`
- `0x180001fe0`
- `0x180002320`
- `0x180002aac`
- `0x180003010`
- `0x180003620`
- `0x180003bc0`
- `0x180004950`
- `0x180004d10`
- `0x180004fb0`
- `0x180005110`
- `0x18000530c`
- `0x1800056e0`
- `0x1800059f0`
- `0x180005e30`
- `0x180006960`
- `0x1800071cc`
- `0x1800080dc`
- `0x18000823c`
- `0x180008d9c`
- `0x180009c3c`
- `0x18000a300`
- `0x18000a59c`
- `0x18000a710`
- `0x18000aa44`
- `0x18000abe0`
- `0x18000accc`
- `0x18000adb8`
- `0x18000afb0`
- `0x18000b9c8`
- `0x18000bd24`
- `0x18000c4c4`
- `0x18000c768`
- `0x18000ca68`
- `0x18000d2ec`
- `0x18000d444`
- `0x18000d730`
- `0x18000d978`
- `0x18000da7c`
- `0x18000dd70`
- `0x18000df08`
- `0x18000ebd0`
- `0x18000f6e0`
- `0x18001072c`
- `0x180010d80`
- `0x180010fe8`
- `0x1800111f4`
- `0x180011444`
- `0x180011820`

## callees

- `0x180008b90`
- `0x180008c14`
- `0x18001d210`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
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
  return McGenEventWrite_EventWriteTransfer(a1, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180008b90  sub     rsp, 68h
0x180008b94  mov     rax, cs:__security_cookie
0x180008b9b  xor     rax, rsp
0x180008b9e  mov     [rsp+68h+var_18], rax
0x180008ba3  xor     r10d, r10d
0x180008ba6  test    r8, r8
0x180008ba9  jz      short loc_180008BC2
0x180008bab  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008baf  inc     rax
0x180008bb2  cmp     [r8+rax*2], r10w
0x180008bb7  jnz     short loc_180008BAF
0x180008bb9  lea     eax, ds:2[rax*2]
0x180008bc0  jmp     short loc_180008BC7
0x180008bc2  mov     eax, 0Ah
0x180008bc7  lea     r9, aNull; "NULL"
0x180008bce  mov     [rsp+68h+var_20], eax
0x180008bd2  test    r8, r8
0x180008bd5  mov     [rsp+68h+var_1C], r10d
0x180008bda  lea     rax, [rsp+68h+var_38]
0x180008bdf  cmovz   r8, r9
0x180008be3  mov     [rsp+68h+var_48], rax
0x180008be8  mov     r9d, 2
0x180008bee  mov     [rsp+68h+var_28], r8
0x180008bf3  call    McGenEventWrite_EventWriteTransfer
0x180008bf8  mov     rcx, [rsp+68h+var_18]
0x180008bfd  xor     rcx, rsp; StackCookie
0x180008c00  call    __security_check_cookie
0x180008c05  add     rsp, 68h
0x180008c09  retn
```
