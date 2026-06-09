# WusaEventUninstallFailure

- ea: `0x14001331c`
- end: `0x1400133e9`
- name: `WusaEventUninstallFailure`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000c488`

## callees

- `0x14001331c`
- `0x140014910`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1400133bd`
- `ADVAPI32!EventWrite` at `0x1400133bd`

## pseudocode

```c
signed int __fastcall WusaEventUninstallFailure(ULONGLONG a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rax
  signed int result; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-50h] BYREF
  int *v9; // [rsp+30h] [rbp-40h]
  __int64 v10; // [rsp+38h] [rbp-38h]
  __int64 v11; // [rsp+40h] [rbp-30h]
  int v12; // [rsp+48h] [rbp-28h]
  int v13; // [rsp+4Ch] [rbp-24h]
  __int64 v14; // [rsp+50h] [rbp-20h]
  int v15; // [rsp+58h] [rbp-18h]
  int v16; // [rsp+5Ch] [rbp-14h]
  int v17; // [rsp+88h] [rbp+18h] BYREF

  v17 = a2;
  v4 = -1;
  UserData.Ptr = a1;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  UserData.Reserved = 0;
  UserData.Size = 2 * v5 + 2;
  v10 = 4;
  v9 = &v17;
  v6 = -1;
  v11 = a3;
  do
    ++v6;
  while ( *(_WORD *)(a3 + 2 * v6) );
  v13 = 0;
  v12 = 2 * v6 + 2;
  v14 = a4;
  do
    ++v4;
  while ( *(_WORD *)(a4 + 2 * v4) );
  v16 = 0;
  v15 = 2 * v4 + 2;
  result = EventWrite(RegHandle, &WUSA_EVENT_UNINSTALLFAILURE, 4u, &UserData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14001331c  mov     [rsp-8+arg_0], rbx
0x140013321  mov     [rsp-8+arg_8], edx
0x140013325  push    rbp
0x140013326  mov     rbp, rsp
0x140013329  sub     rsp, 70h
0x14001332d  mov     rax, cs:__security_cookie
0x140013334  xor     rax, rsp
0x140013337  mov     [rbp+var_10], rax
0x14001333b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001333f  mov     [rbp+UserData.Ptr], rcx
0x140013343  mov     rax, rdx
0x140013346  xor     ebx, ebx
0x140013348  inc     rax
0x14001334b  cmp     [rcx+rax*2], bx
0x14001334f  jnz     short loc_140013348
0x140013351  lea     eax, ds:2[rax*2]
0x140013358  mov     dword ptr [rbp+UserData.0Ch], ebx
0x14001335b  mov     [rbp+UserData.Size], eax
0x14001335e  mov     ecx, 4
0x140013363  lea     rax, [rbp+arg_8]
0x140013367  mov     [rbp+var_38], rcx
0x14001336b  mov     [rbp+var_40], rax
0x14001336f  mov     rax, rdx
0x140013372  mov     [rbp+var_30], r8
0x140013376  inc     rax
0x140013379  cmp     [r8+rax*2], bx
0x14001337e  jnz     short loc_140013376
0x140013380  lea     eax, ds:2[rax*2]
0x140013387  mov     [rbp+var_24], ebx
0x14001338a  mov     [rbp+var_28], eax
0x14001338d  mov     [rbp+var_20], r9
0x140013391  inc     rdx
0x140013394  cmp     [r9+rdx*2], bx
0x140013399  jnz     short loc_140013391
0x14001339b  lea     eax, ds:2[rdx*2]
0x1400133a2  mov     [rbp+var_14], ebx
0x1400133a5  mov     r8d, ecx; UserDataCount
0x1400133a8  mov     [rbp+var_18], eax
0x1400133ab  mov     rcx, cs:RegHandle; RegHandle
0x1400133b2  lea     rdx, WUSA_EVENT_UNINSTALLFAILURE; EventDescriptor
0x1400133b9  lea     r9, [rbp+UserData]; UserData
0x1400133bd  call    cs:__imp_EventWrite
0x1400133c3  test    eax, eax
0x1400133c5  jle     short loc_1400133CF
0x1400133c7  movzx   eax, ax
0x1400133ca  or      eax, 80070000h
0x1400133cf  mov     rcx, [rbp+var_10]
0x1400133d3  xor     rcx, rsp; StackCookie
0x1400133d6  call    __security_check_cookie
0x1400133db  mov     rbx, [rsp+70h+arg_0]
0x1400133e3  add     rsp, 70h
0x1400133e7  pop     rbp
0x1400133e8  retn
```
