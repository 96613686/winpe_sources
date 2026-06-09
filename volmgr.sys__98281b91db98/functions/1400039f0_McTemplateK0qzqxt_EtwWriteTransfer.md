# McTemplateK0qzqxt_EtwWriteTransfer

- ea: `0x1400039f0`
- end: `0x140003af3`
- name: `McTemplateK0qzqxt_EtwWriteTransfer`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e888`

## callees

- `0x1400039f0`
- `0x140003bf0`
- `0x140005050`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qzqxt_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        const wchar_t *a5,
        char a6,
        char a7,
        char a8)
{
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  int v11; // eax
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-78h] BYREF
  int *v14; // [rsp+40h] [rbp-68h]
  __int64 v15; // [rsp+48h] [rbp-60h]
  const wchar_t *v16; // [rsp+50h] [rbp-58h]
  int v17; // [rsp+58h] [rbp-50h]
  int v18; // [rsp+5Ch] [rbp-4Ch]
  char *v19; // [rsp+60h] [rbp-48h]
  __int64 v20; // [rsp+68h] [rbp-40h]
  char *v21; // [rsp+70h] [rbp-38h]
  __int64 v22; // [rsp+78h] [rbp-30h]
  char *v23; // [rsp+80h] [rbp-28h]
  __int64 v24; // [rsp+88h] [rbp-20h]
  int v25; // [rsp+C8h] [rbp+20h] BYREF

  v25 = a4;
  v8 = a5;
  v14 = &v25;
  v15 = 4;
  if ( a5 )
  {
    v9 = -1;
    while ( a5[++v9] != 0 )
      ;
    v11 = 2 * v9 + 2;
  }
  else
  {
    v11 = 10;
  }
  v17 = v11;
  v18 = 0;
  v19 = &a6;
  v20 = 4;
  v21 = &a7;
  if ( !a5 )
    v8 = L"NULL";
  v16 = v8;
  v23 = &a8;
  v22 = 8;
  v24 = 4;
  return McGenEventWrite_EtwWriteTransfer((__int64)v8, (const EVENT_DESCRIPTOR *)VolumeRemoved, 0, 6u, &v13);
}

```

## disassembly

```asm
0x1400039f0  mov     r11, rsp
0x1400039f3  mov     [r11+20h], r9d
0x1400039f7  sub     rsp, 0A8h
0x1400039fe  mov     rax, cs:__security_cookie
0x140003a05  xor     rax, rsp
0x140003a08  mov     [rsp+0A8h+var_18], rax
0x140003a10  mov     rcx, [rsp+0A8h+arg_20]
0x140003a18  lea     rax, [r11+20h]
0x140003a1c  xor     r8d, r8d
0x140003a1f  mov     [r11-68h], rax
0x140003a23  mov     qword ptr [r11-60h], 4
0x140003a2b  test    rcx, rcx
0x140003a2e  jz      short loc_140003A55
0x140003a30  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140003a37  nop     word ptr [rax+rax+00000000h]
0x140003a40  cmp     [rcx+rax*2+2], r8w
0x140003a46  lea     rax, [rax+1]
0x140003a4a  jnz     short loc_140003A40
0x140003a4c  lea     eax, ds:2[rax*2]
0x140003a53  jmp     short loc_140003A5A
0x140003a55  mov     eax, 0Ah
0x140003a5a  mov     [rsp+0A8h+var_50], eax
0x140003a5e  lea     rdx, aNull; "NULL"
0x140003a65  lea     rax, [rsp+0A8h+arg_28]
0x140003a6d  mov     [rsp+0A8h+var_4C], r8d
0x140003a72  mov     [rsp+0A8h+var_48], rax
0x140003a77  test    rcx, rcx
0x140003a7a  lea     rax, [rsp+0A8h+arg_30]
0x140003a82  mov     [rsp+0A8h+var_40], 4
0x140003a8b  mov     [rsp+0A8h+var_38], rax
0x140003a90  cmovz   rcx, rdx
0x140003a94  lea     rax, [rsp+0A8h+arg_38]
0x140003a9c  mov     [rsp+0A8h+var_58], rcx
0x140003aa1  mov     [rsp+0A8h+var_28], rax
0x140003aa9  lea     rdx, VolumeRemoved
0x140003ab0  lea     rax, [rsp+0A8h+var_78]
0x140003ab5  mov     [rsp+0A8h+var_30], 8
0x140003abe  mov     r9d, 6
0x140003ac4  mov     [rsp+0A8h+var_88], rax
0x140003ac9  mov     [rsp+0A8h+var_20], 4
0x140003ad5  call    McGenEventWrite_EtwWriteTransfer
0x140003ada  mov     rcx, [rsp+0A8h+var_18]
0x140003ae2  xor     rcx, rsp; StackCookie
0x140003ae5  call    __security_check_cookie
0x140003aea  add     rsp, 0A8h
0x140003af1  retn
```
