# McTemplateU0z_EventWriteTransfer

- ea: `0x18000fcf8`
- end: `0x18000fd5d`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f594`

## callees

- `0x1800027f0`
- `0x180009950`
- `0x18000fcf8`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2)
{
  __int64 v2; // rax
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  WCHAR *v5; // [rsp+40h] [rbp-28h]
  int v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+4Ch] [rbp-1Ch]

  v2 = -1;
  do
    ++v2;
  while ( *(&Filename + v2) );
  v5 = &Filename;
  v6 = 2 * v2 + 2;
  v7 = 0;
  return McGenEventWrite_EventWriteTransfer(0, a2, (__int64)&Filename, 2u, &v4);
}

```

## disassembly

```asm
0x18000fcf8  sub     rsp, 68h
0x18000fcfc  mov     rax, cs:__security_cookie
0x18000fd03  xor     rax, rsp
0x18000fd06  mov     [rsp+68h+var_18], rax
0x18000fd0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fd0f  lea     r8, Filename
0x18000fd16  xor     ecx, ecx
0x18000fd18  inc     rax
0x18000fd1b  cmp     [r8+rax*2], cx
0x18000fd20  jnz     short loc_18000FD18
0x18000fd22  lea     eax, ds:2[rax*2]
0x18000fd29  mov     [rsp+68h+var_28], r8
0x18000fd2e  mov     [rsp+68h+var_20], eax
0x18000fd32  mov     r9d, 2
0x18000fd38  lea     rax, [rsp+68h+var_38]
0x18000fd3d  mov     [rsp+68h+var_1C], ecx
0x18000fd41  mov     [rsp+68h+var_48], rax
0x18000fd46  call    McGenEventWrite_EventWriteTransfer
0x18000fd4b  mov     rcx, [rsp+68h+var_18]
0x18000fd50  xor     rcx, rsp; StackCookie
0x18000fd53  call    __security_check_cookie
0x18000fd58  add     rsp, 68h
0x18000fd5c  retn
```
