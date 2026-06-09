# WusaEventInstallRebootInitiated

- ea: `0x14001327c`
- end: `0x140013314`
- name: `WusaEventInstallRebootInitiated`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140005b20`
- `0x140008ff8`

## callees

- `0x14001327c`
- `0x140014910`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1400132ef`
- `ADVAPI32!EventWrite` at `0x1400132ef`

## pseudocode

```c
signed int __fastcall WusaEventInstallRebootInitiated(ULONGLONG a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 v3; // rax
  signed int result; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+3Ch] [rbp-1Ch]

  v2 = -1;
  UserData.Ptr = a1;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(a1 + 2 * v3) );
  UserData.Reserved = 0;
  UserData.Size = 2 * v3 + 2;
  v6 = a2;
  do
    ++v2;
  while ( *(_WORD *)(a2 + 2 * v2) );
  v7 = 2 * v2 + 2;
  v8 = 0;
  result = EventWrite(RegHandle, &WUSA_EVENT_INSTALLREBOOTINITIATED, 2u, &UserData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14001327c  push    rbx
0x14001327e  sub     rsp, 50h
0x140013282  mov     rax, cs:__security_cookie
0x140013289  xor     rax, rsp
0x14001328c  mov     [rsp+58h+var_18], rax
0x140013291  or      r8, 0FFFFFFFFFFFFFFFFh
0x140013295  mov     [rsp+58h+UserData.Ptr], rcx
0x14001329a  mov     rax, r8
0x14001329d  xor     ebx, ebx
0x14001329f  inc     rax
0x1400132a2  cmp     [rcx+rax*2], bx
0x1400132a6  jnz     short loc_14001329F
0x1400132a8  lea     eax, ds:2[rax*2]
0x1400132af  mov     dword ptr [rsp+58h+UserData.0Ch], ebx
0x1400132b3  mov     [rsp+58h+UserData.Size], eax
0x1400132b7  mov     [rsp+58h+var_28], rdx
0x1400132bc  inc     r8
0x1400132bf  cmp     [rdx+r8*2], bx
0x1400132c4  jnz     short loc_1400132BC
0x1400132c6  mov     rcx, cs:RegHandle; RegHandle
0x1400132cd  lea     eax, ds:2[r8*2]
0x1400132d5  mov     r8d, 2; UserDataCount
0x1400132db  mov     [rsp+58h+var_20], eax
0x1400132df  lea     r9, [rsp+58h+UserData]; UserData
0x1400132e4  mov     [rsp+58h+var_1C], ebx
0x1400132e8  lea     rdx, WUSA_EVENT_INSTALLREBOOTINITIATED; EventDescriptor
0x1400132ef  call    cs:__imp_EventWrite
0x1400132f5  test    eax, eax
0x1400132f7  jle     short loc_140013301
0x1400132f9  movzx   eax, ax
0x1400132fc  or      eax, 80070000h
0x140013301  mov     rcx, [rsp+58h+var_18]
0x140013306  xor     rcx, rsp; StackCookie
0x140013309  call    __security_check_cookie
0x14001330e  add     rsp, 50h
0x140013312  pop     rbx
0x140013313  retn
```
