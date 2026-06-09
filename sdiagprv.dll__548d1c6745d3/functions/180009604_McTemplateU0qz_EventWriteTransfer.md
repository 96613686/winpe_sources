# McTemplateU0qz_EventWriteTransfer

- ea: `0x180009604`
- end: `0x180009695`
- name: `McTemplateU0qz_EventWriteTransfer`
- size: `145`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, int, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008f00`
- `0x1800125e8`

## callees

- `0x18000247c`
- `0x180009604`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qz_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, int a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  int *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const wchar_t *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  v9 = 4;
  v8 = &v13;
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
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v10 = a4;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, 0, 3u, &v7);
}

```

## disassembly

```asm
0x180009604  mov     r11, rsp
0x180009607  mov     [r11+18h], r8d
0x18000960b  sub     rsp, 78h
0x18000960f  mov     rax, cs:__security_cookie
0x180009616  xor     rax, rsp
0x180009619  mov     [rsp+78h+var_18], rax
0x18000961e  xor     r8d, r8d
0x180009621  mov     qword ptr [r11-30h], 4
0x180009629  lea     rax, [r11+18h]
0x18000962d  mov     [r11-38h], rax
0x180009631  test    r9, r9
0x180009634  jz      short loc_18000964D
0x180009636  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000963a  inc     rax
0x18000963d  cmp     [r9+rax*2], r8w
0x180009642  jnz     short loc_18000963A
0x180009644  lea     eax, ds:2[rax*2]
0x18000964b  jmp     short loc_180009652
0x18000964d  mov     eax, 0Ah
0x180009652  test    r9, r9
0x180009655  mov     [rsp+78h+var_20], eax
0x180009659  lea     rcx, aNull_0; "NULL"
0x180009660  mov     [rsp+78h+var_1C], r8d
0x180009665  cmovz   r9, rcx
0x180009669  lea     rax, [rsp+78h+var_48]
0x18000966e  mov     [rsp+78h+var_28], r9
0x180009673  mov     r9d, 3
0x180009679  mov     [rsp+78h+var_58], rax
0x18000967e  call    McGenEventWrite_EventWriteTransfer
0x180009683  mov     rcx, [rsp+78h+var_18]
0x180009688  xor     rcx, rsp; StackCookie
0x18000968b  call    __security_check_cookie
0x180009690  add     rsp, 78h
0x180009694  retn
```
