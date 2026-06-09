# LogErrorPopup

- ea: `0x18000d870`
- end: `0x18000d91b`
- name: `LogErrorPopup`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dda0`

## callees

- `0x18000d870`
- `0x1800138f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000d8fc`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000d8fc`

## pseudocode

```c
ULONG __fastcall LogErrorPopup(__int64 *a1, __int64 *a2)
{
  __int64 *v2; // r8
  __int64 *v3; // r9
  __int64 v4; // rcx
  __int64 v5; // rax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-38h] BYREF
  __int64 *v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+38h] [rbp-20h]
  int v10; // [rsp+3Ch] [rbp-1Ch]

  v2 = &qword_180017108;
  v3 = &qword_180017108;
  if ( a1 )
    v3 = a1;
  UserData.Ptr = (ULONGLONG)v3;
  if ( a2 )
    v2 = a2;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)v3 + v5) );
  UserData.Reserved = 0;
  UserData.Size = 2 * v5 + 2;
  v8 = v2;
  do
    ++v4;
  while ( *((_WORD *)v2 + v4) );
  v10 = 0;
  v9 = 2 * v4 + 2;
  return EventWrite(gEventSource, &PopupEvent, 2u, &UserData);
}

```

## disassembly

```asm
0x18000d870  sub     rsp, 58h
0x18000d874  mov     rax, cs:__security_cookie
0x18000d87b  xor     rax, rsp
0x18000d87e  mov     [rsp+58h+var_18], rax
0x18000d883  xor     r10d, r10d
0x18000d886  lea     r8, qword_180017108
0x18000d88d  test    rcx, rcx
0x18000d890  mov     r9, r8
0x18000d893  cmovnz  r9, rcx
0x18000d897  test    rdx, rdx
0x18000d89a  mov     [rsp+58h+UserData.Ptr], r9
0x18000d89f  cmovnz  r8, rdx
0x18000d8a3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d8a7  mov     rax, rcx
0x18000d8aa  inc     rax
0x18000d8ad  cmp     [r9+rax*2], r10w
0x18000d8b2  jnz     short loc_18000D8AA
0x18000d8b4  lea     eax, ds:2[rax*2]
0x18000d8bb  mov     dword ptr [rsp+58h+UserData.0Ch], r10d
0x18000d8c0  mov     [rsp+58h+UserData.Size], eax
0x18000d8c4  mov     [rsp+58h+var_28], r8
0x18000d8c9  inc     rcx
0x18000d8cc  cmp     [r8+rcx*2], r10w
0x18000d8d1  jnz     short loc_18000D8C9
0x18000d8d3  lea     eax, ds:2[rcx*2]
0x18000d8da  mov     [rsp+58h+var_1C], r10d
0x18000d8df  mov     rcx, cs:gEventSource; RegHandle
0x18000d8e6  lea     r9, [rsp+58h+UserData]; UserData
0x18000d8eb  mov     r8d, 2; UserDataCount
0x18000d8f1  mov     [rsp+58h+var_20], eax
0x18000d8f5  lea     rdx, PopupEvent; EventDescriptor
0x18000d8fc  call    cs:__imp_EventWrite
0x18000d903  nop     dword ptr [rax+rax+00h]
0x18000d908  mov     rcx, [rsp+58h+var_18]
0x18000d90d  xor     rcx, rsp; StackCookie
0x18000d910  call    __security_check_cookie
0x18000d915  add     rsp, 58h
0x18000d919  retn
```
