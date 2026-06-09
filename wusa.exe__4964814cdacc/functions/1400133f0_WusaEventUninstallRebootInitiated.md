# WusaEventUninstallRebootInitiated

- ea: `0x1400133f0`
- end: `0x140013488`
- name: `WusaEventUninstallRebootInitiated`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140005b20`
- `0x140008ff8`

## callees

- `0x1400133f0`
- `0x140014910`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140013463`
- `ADVAPI32!EventWrite` at `0x140013463`

## pseudocode

```c
signed int __fastcall WusaEventUninstallRebootInitiated(ULONGLONG a1, __int64 a2)
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
  result = EventWrite(RegHandle, &WUSA_EVENT_UNINSTALLREBOOTINITIATED, 2u, &UserData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400133f0  push    rbx
0x1400133f2  sub     rsp, 50h
0x1400133f6  mov     rax, cs:__security_cookie
0x1400133fd  xor     rax, rsp
0x140013400  mov     [rsp+58h+var_18], rax
0x140013405  or      r8, 0FFFFFFFFFFFFFFFFh
0x140013409  mov     [rsp+58h+UserData.Ptr], rcx
0x14001340e  mov     rax, r8
0x140013411  xor     ebx, ebx
0x140013413  inc     rax
0x140013416  cmp     [rcx+rax*2], bx
0x14001341a  jnz     short loc_140013413
0x14001341c  lea     eax, ds:2[rax*2]
0x140013423  mov     dword ptr [rsp+58h+UserData.0Ch], ebx
0x140013427  mov     [rsp+58h+UserData.Size], eax
0x14001342b  mov     [rsp+58h+var_28], rdx
0x140013430  inc     r8
0x140013433  cmp     [rdx+r8*2], bx
0x140013438  jnz     short loc_140013430
0x14001343a  mov     rcx, cs:RegHandle; RegHandle
0x140013441  lea     eax, ds:2[r8*2]
0x140013449  mov     r8d, 2; UserDataCount
0x14001344f  mov     [rsp+58h+var_20], eax
0x140013453  lea     r9, [rsp+58h+UserData]; UserData
0x140013458  mov     [rsp+58h+var_1C], ebx
0x14001345c  lea     rdx, WUSA_EVENT_UNINSTALLREBOOTINITIATED; EventDescriptor
0x140013463  call    cs:__imp_EventWrite
0x140013469  test    eax, eax
0x14001346b  jle     short loc_140013475
0x14001346d  movzx   eax, ax
0x140013470  or      eax, 80070000h
0x140013475  mov     rcx, [rsp+58h+var_18]
0x14001347a  xor     rcx, rsp; StackCookie
0x14001347d  call    __security_check_cookie
0x140013482  add     rsp, 50h
0x140013486  pop     rbx
0x140013487  retn
```
