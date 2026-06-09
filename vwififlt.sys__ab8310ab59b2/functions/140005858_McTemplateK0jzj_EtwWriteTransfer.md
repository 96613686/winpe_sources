# McTemplateK0jzj_EtwWriteTransfer

- ea: `0x140005858`
- end: `0x140005905`
- name: `McTemplateK0jzj_EtwWriteTransfer`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400069a0`
- `0x14000a260`

## callees

- `0x140005858`
- `0x14000590c`
- `0x14000f110`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jzj_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        __int64 a4,
        const wchar_t *a5,
        __int64 a6)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+40h] [rbp-48h]
  __int64 v12; // [rsp+48h] [rbp-40h]
  const wchar_t *v13; // [rsp+50h] [rbp-38h]
  int v14; // [rsp+58h] [rbp-30h]
  int v15; // [rsp+5Ch] [rbp-2Ch]
  __int64 v16; // [rsp+60h] [rbp-28h]
  __int64 v17; // [rsp+68h] [rbp-20h]

  v6 = a5;
  v11 = a4;
  v12 = 16;
  if ( a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a5[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v14 = v8;
  v16 = a6;
  if ( !a5 )
    v6 = L"NULL";
  v13 = v6;
  v15 = 0;
  v17 = 16;
  return McGenEventWrite_EtwWriteTransfer((__int64)v6, a2, a3, 4u, &v10);
}

```

## disassembly

```asm
0x140005858  sub     rsp, 88h
0x14000585f  mov     rax, cs:__security_cookie
0x140005866  xor     rax, rsp
0x140005869  mov     [rsp+88h+var_18], rax
0x14000586e  mov     rcx, [rsp+88h+arg_20]
0x140005876  xor     r10d, r10d
0x140005879  mov     [rsp+88h+var_48], r9
0x14000587e  mov     [rsp+88h+var_40], 10h
0x140005887  test    rcx, rcx
0x14000588a  jz      short loc_1400058FE
0x14000588c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005890  inc     rax
0x140005893  cmp     [rcx+rax*2], r10w
0x140005898  jnz     short loc_140005890
0x14000589a  lea     eax, ds:2[rax*2]
0x1400058a1  mov     [rsp+88h+var_30], eax
0x1400058a5  lea     r9, aNull_0; "NULL"
0x1400058ac  mov     rax, [rsp+88h+arg_28]
0x1400058b4  test    rcx, rcx
0x1400058b7  mov     [rsp+88h+var_28], rax
0x1400058bc  lea     rax, [rsp+88h+var_58]
0x1400058c1  cmovz   rcx, r9
0x1400058c5  mov     [rsp+88h+var_68], rax
0x1400058ca  mov     r9d, 4
0x1400058d0  mov     [rsp+88h+var_38], rcx
0x1400058d5  mov     [rsp+88h+var_2C], r10d
0x1400058da  mov     [rsp+88h+var_20], 10h
0x1400058e3  call    McGenEventWrite_EtwWriteTransfer
0x1400058e8  mov     rcx, [rsp+88h+var_18]
0x1400058ed  xor     rcx, rsp; StackCookie
0x1400058f0  call    __security_check_cookie
0x1400058f5  add     rsp, 88h
0x1400058fc  retn
0x1400058fe  mov     eax, 0Ah
0x140005903  jmp     short loc_1400058A1
```
