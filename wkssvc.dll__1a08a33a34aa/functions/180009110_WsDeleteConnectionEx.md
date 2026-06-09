# WsDeleteConnectionEx

- ea: `0x180009110`
- end: `0x1800091ce`
- name: `WsDeleteConnectionEx`
- size: `190`
- prototype: `__int64 __fastcall(PLUID SourceLuid, HANDLE Handle)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800012a0`
- `0x180001750`
- `0x18002bd5c`
- `0x18002be90`
- `0x18002cac8`

## callees

- `0x180008f50`
- `0x180009110`
- `0x18001fbd0`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180009167`
- `ntdll!RtlCopyLuid` at `0x180009167`
- `ntdll!NtClose` at `0x1800091aa`
- `ntdll!NtClose` at `0x1800091aa`

## pseudocode

```c
__int64 __fastcall WsDeleteConnectionEx(PLUID SourceLuid, HANDLE Handle, DWORD a3, char a4)
{
  unsigned int v6; // ebx
  struct _LUID DestinationLuid[2]; // [rsp+40h] [rbp-48h] BYREF
  __int128 v9; // [rsp+50h] [rbp-38h]
  int v10; // [rsp+60h] [rbp-28h]

  v10 = 0;
  *(_OWORD *)&DestinationLuid[0].LowPart = 0;
  v9 = 0;
  if ( !a3 || a3 == 2 )
    DestinationLuid[1].LowPart = a3;
  DestinationLuid[0].HighPart = 6;
  RtlCopyLuid((PLUID)&DestinationLuid[1].HighPart, SourceLuid);
  v6 = WsRedirFsControl(Handle, 1311148, DestinationLuid, 36, 0, 0);
  if ( !v6 && a4 )
    NtClose(Handle);
  return v6;
}

```

## disassembly

```asm
0x180009110  push    rbx
0x180009112  push    rsi
0x180009113  push    rdi
0x180009114  sub     rsp, 70h
0x180009118  mov     rax, cs:__security_cookie
0x18000911f  xor     rax, rsp
0x180009122  mov     [rsp+88h+var_20], rax
0x180009127  xor     eax, eax
0x180009129  xorps   xmm0, xmm0
0x18000912c  mov     [rsp+88h+var_28], eax
0x180009130  mov     eax, r8d
0x180009133  mov     sil, r9b
0x180009136  mov     rdi, rdx
0x180009139  movups  xmmword ptr [rsp+88h+DestinationLuid.LowPart], xmm0
0x18000913e  movups  [rsp+88h+var_38], xmm0
0x180009143  test    r8d, r8d
0x180009146  jz      short loc_180009152
0x180009148  sub     eax, 1
0x18000914b  jz      short loc_180009157
0x18000914d  cmp     eax, 1
0x180009150  jnz     short loc_180009157
0x180009152  mov     [rsp+88h+DestinationLuid.LowPart+8], r8d
0x180009157  mov     rdx, rcx; SourceLuid
0x18000915a  mov     [rsp+88h+DestinationLuid.HighPart], 6
0x180009162  lea     rcx, [rsp+88h+DestinationLuid.HighPart+8]; DestinationLuid
0x180009167  call    cs:__imp_RtlCopyLuid
0x18000916e  nop     dword ptr [rax+rax+00h]
0x180009173  mov     r9d, 24h ; '$'
0x180009179  mov     [rsp+88h+var_60], 0
0x180009181  lea     r8, [rsp+88h+DestinationLuid]
0x180009186  mov     [rsp+88h+var_68], 0
0x18000918f  mov     edx, 1401ACh
0x180009194  mov     rcx, rdi
0x180009197  call    WsRedirFsControl
0x18000919c  mov     ebx, eax
0x18000919e  test    eax, eax
0x1800091a0  jnz     short loc_1800091B6
0x1800091a2  test    sil, sil
0x1800091a5  jz      short loc_1800091B6
0x1800091a7  mov     rcx, rdi; Handle
0x1800091aa  call    cs:__imp_NtClose
0x1800091b1  nop     dword ptr [rax+rax+00h]
0x1800091b6  mov     eax, ebx
0x1800091b8  mov     rcx, [rsp+88h+var_20]
0x1800091bd  xor     rcx, rsp; StackCookie
0x1800091c0  call    __security_check_cookie
0x1800091c5  add     rsp, 70h
0x1800091c9  pop     rdi
0x1800091ca  pop     rsi
0x1800091cb  pop     rbx
0x1800091cc  retn
```
