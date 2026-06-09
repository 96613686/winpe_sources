# WusaEventInstallFailure

- ea: `0x1400131a8`
- end: `0x140013275`
- name: `WusaEventInstallFailure`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000c488`

## callees

- `0x1400131a8`
- `0x140014910`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140013249`
- `ADVAPI32!EventWrite` at `0x140013249`

## pseudocode

```c
signed int __fastcall WusaEventInstallFailure(ULONGLONG a1, int a2, __int64 a3, __int64 a4)
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
  result = EventWrite(RegHandle, &WUSA_EVENT_INSTALLFAILURE, 4u, &UserData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400131a8  mov     [rsp-8+arg_0], rbx
0x1400131ad  mov     [rsp-8+arg_8], edx
0x1400131b1  push    rbp
0x1400131b2  mov     rbp, rsp
0x1400131b5  sub     rsp, 70h
0x1400131b9  mov     rax, cs:__security_cookie
0x1400131c0  xor     rax, rsp
0x1400131c3  mov     [rbp+var_10], rax
0x1400131c7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400131cb  mov     [rbp+UserData.Ptr], rcx
0x1400131cf  mov     rax, rdx
0x1400131d2  xor     ebx, ebx
0x1400131d4  inc     rax
0x1400131d7  cmp     [rcx+rax*2], bx
0x1400131db  jnz     short loc_1400131D4
0x1400131dd  lea     eax, ds:2[rax*2]
0x1400131e4  mov     dword ptr [rbp+UserData.0Ch], ebx
0x1400131e7  mov     [rbp+UserData.Size], eax
0x1400131ea  mov     ecx, 4
0x1400131ef  lea     rax, [rbp+arg_8]
0x1400131f3  mov     [rbp+var_38], rcx
0x1400131f7  mov     [rbp+var_40], rax
0x1400131fb  mov     rax, rdx
0x1400131fe  mov     [rbp+var_30], r8
0x140013202  inc     rax
0x140013205  cmp     [r8+rax*2], bx
0x14001320a  jnz     short loc_140013202
0x14001320c  lea     eax, ds:2[rax*2]
0x140013213  mov     [rbp+var_24], ebx
0x140013216  mov     [rbp+var_28], eax
0x140013219  mov     [rbp+var_20], r9
0x14001321d  inc     rdx
0x140013220  cmp     [r9+rdx*2], bx
0x140013225  jnz     short loc_14001321D
0x140013227  lea     eax, ds:2[rdx*2]
0x14001322e  mov     [rbp+var_14], ebx
0x140013231  mov     r8d, ecx; UserDataCount
0x140013234  mov     [rbp+var_18], eax
0x140013237  mov     rcx, cs:RegHandle; RegHandle
0x14001323e  lea     rdx, WUSA_EVENT_INSTALLFAILURE; EventDescriptor
0x140013245  lea     r9, [rbp+UserData]; UserData
0x140013249  call    cs:__imp_EventWrite
0x14001324f  test    eax, eax
0x140013251  jle     short loc_14001325B
0x140013253  movzx   eax, ax
0x140013256  or      eax, 80070000h
0x14001325b  mov     rcx, [rbp+var_10]
0x14001325f  xor     rcx, rsp; StackCookie
0x140013262  call    __security_check_cookie
0x140013267  mov     rbx, [rsp+70h+arg_0]
0x14001326f  add     rsp, 70h
0x140013273  pop     rbp
0x140013274  retn
```
