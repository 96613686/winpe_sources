# McTemplateU0z_EventWriteTransfer

- ea: `0x180008360`
- end: `0x1800083da`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `63`
- callee_count: `3`
- tags: ``

## callers

- `0x180001240`
- `0x180001a80`
- `0x180001ee0`
- `0x1800021f0`
- `0x180002908`
- `0x180002e00`
- `0x1800033b0`
- `0x180003920`
- `0x1800045b0`
- `0x180004940`
- `0x180004bc0`
- `0x180004d10`
- `0x180004ef4`
- `0x180005280`
- `0x180005560`
- `0x180005920`
- `0x1800063a0`
- `0x180006b64`
- `0x180007944`
- `0x180007a84`
- `0x18000853c`
- `0x1800093ac`
- `0x180009a00`
- `0x180009c7c`
- `0x180009dd8`
- `0x18000a0d4`
- `0x18000a270`
- `0x18000a35c`
- `0x18000a448`
- `0x18000a620`
- `0x18000afbc`
- `0x18000b2e0`
- `0x18000b9fc`
- `0x18000bc78`
- `0x18000bf68`
- `0x18000c788`
- `0x18000c8d0`
- `0x18000cba4`
- `0x18000cdd8`
- `0x18000cec8`
- `0x18000d1a0`
- `0x18000d324`
- `0x18000df30`
- `0x18000e9a0`
- `0x18000f974`
- `0x18000ff74`
- `0x1800101dc`
- `0x1800103e8`
- `0x180010634`
- `0x1800109ac`

## callees

- `0x180008360`
- `0x1800083e0`
- `0x18001bcf0`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer(a1, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180008360  sub     rsp, 68h
0x180008364  mov     rax, cs:__security_cookie
0x18000836b  xor     rax, rsp
0x18000836e  mov     [rsp+68h+var_18], rax
0x180008373  xor     r10d, r10d
0x180008376  test    r8, r8
0x180008379  jz      short loc_180008392
0x18000837b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000837f  inc     rax
0x180008382  cmp     [r8+rax*2], r10w
0x180008387  jnz     short loc_18000837F
0x180008389  lea     eax, ds:2[rax*2]
0x180008390  jmp     short loc_180008397
0x180008392  mov     eax, 0Ah
0x180008397  lea     r9, aNull; "NULL"
0x18000839e  mov     [rsp+68h+var_20], eax
0x1800083a2  test    r8, r8
0x1800083a5  mov     [rsp+68h+var_1C], r10d
0x1800083aa  lea     rax, [rsp+68h+var_38]
0x1800083af  cmovz   r8, r9
0x1800083b3  mov     [rsp+68h+var_48], rax
0x1800083b8  mov     r9d, 2
0x1800083be  mov     [rsp+68h+var_28], r8
0x1800083c3  call    McGenEventWrite_EventWriteTransfer
0x1800083c8  mov     rcx, [rsp+68h+var_18]
0x1800083cd  xor     rcx, rsp; StackCookie
0x1800083d0  call    __security_check_cookie
0x1800083d5  add     rsp, 68h
0x1800083d9  retn
```
