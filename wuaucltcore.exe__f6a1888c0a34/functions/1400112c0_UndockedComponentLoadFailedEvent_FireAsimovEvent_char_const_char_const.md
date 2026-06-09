# UndockedComponentLoadFailedEvent::FireAsimovEvent(char const *,char const *)

- ea: `0x1400112c0`
- end: `0x1400114e5`
- name: `?FireAsimovEvent@UndockedComponentLoadFailedEvent@@UEAAJPEBD0@Z`
- size: `549`
- prototype: `__int64 __fastcall(UndockedComponentLoadFailedEvent *__hidden this, const char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400074c8`

## callees

- `0x1400015b4`
- `0x1400112c0`
- `0x14001aa60`

## pseudocode

```c
__int64 __fastcall UndockedComponentLoadFailedEvent::FireAsimovEvent(
        UndockedComponentLoadFailedEvent *this,
        const wchar_t *a2,
        const wchar_t *a3)
{
  const WCHAR *v4; // r9
  int v5; // esi
  const WCHAR *v6; // r11
  const WCHAR *v7; // rbx
  const WCHAR *v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // edx
  __int64 v13; // rcx
  int v14; // ecx
  __int64 v15; // rcx
  int v16; // ecx
  __int64 v17; // rcx
  int v18; // ecx
  __int64 v19; // rcx
  int v21; // [rsp+38h] [rbp-79h] BYREF
  int v22; // [rsp+3Ch] [rbp-75h] BYREF
  __int64 v23; // [rsp+40h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+48h] [rbp-69h] BYREF
  __int64 *v25; // [rsp+68h] [rbp-49h]
  __int64 v26; // [rsp+70h] [rbp-41h]
  const wchar_t *v27; // [rsp+78h] [rbp-39h]
  int v28; // [rsp+80h] [rbp-31h]
  int v29; // [rsp+84h] [rbp-2Dh]
  int *v30; // [rsp+88h] [rbp-29h]
  __int64 v31; // [rsp+90h] [rbp-21h]
  const WCHAR *v32; // [rsp+98h] [rbp-19h]
  int v33; // [rsp+A0h] [rbp-11h]
  int v34; // [rsp+A4h] [rbp-Dh]
  const WCHAR *v35; // [rsp+A8h] [rbp-9h]
  int v36; // [rsp+B0h] [rbp-1h]
  int v37; // [rsp+B4h] [rbp+3h]
  const WCHAR *v38; // [rsp+B8h] [rbp+7h]
  int v39; // [rsp+C0h] [rbp+Fh]
  int v40; // [rsp+C4h] [rbp+13h]
  const WCHAR *v41; // [rsp+C8h] [rbp+17h]
  int v42; // [rsp+D0h] [rbp+1Fh]
  int v43; // [rsp+D4h] [rbp+23h]
  int *v44; // [rsp+D8h] [rbp+27h]
  __int64 v45; // [rsp+E0h] [rbp+2Fh]
  const wchar_t *v46; // [rsp+E8h] [rbp+37h]
  int v47; // [rsp+F0h] [rbp+3Fh]
  int v48; // [rsp+F4h] [rbp+43h]

  if ( (unsigned int)dword_14002E4E0 > 5
    && (qword_14002E4F0 & 0x800000000000LL) != 0
    && (qword_14002E4F8 & 0x800000000000LL) == qword_14002E4F8 )
  {
    v4 = (const WCHAR *)*((_QWORD *)this + 5);
    v5 = 1;
    v6 = (const WCHAR *)*((_QWORD *)this + 4);
    v7 = (const WCHAR *)*((_QWORD *)this + 3);
    v8 = (const WCHAR *)*((_QWORD *)this + 2);
    v21 = *((_DWORD *)this + 2);
    v22 = *((_DWORD *)this + 3);
    v23 = 2164260864LL;
    v9 = -1;
    if ( a3 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_BYTE *)a3 + v10) );
      v11 = v10 + 1;
    }
    else
    {
      a3 = &qword_140023E40;
      v11 = 1;
    }
    v47 = v11;
    v46 = a3;
    v44 = &v21;
    v12 = 2;
    v48 = 0;
    v45 = 4;
    if ( v4 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v4[v13] );
      v14 = 2 * v13 + 2;
    }
    else
    {
      v4 = &OutputString;
      v14 = 2;
    }
    v41 = v4;
    v42 = v14;
    v43 = 0;
    if ( v6 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v6[v15] );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v6 = &OutputString;
      v16 = 2;
    }
    v38 = v6;
    v39 = v16;
    v40 = 0;
    if ( v7 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v7[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v7 = &OutputString;
      v18 = 2;
    }
    v35 = v7;
    v36 = v18;
    v37 = 0;
    if ( v8 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v8[v19] );
      v12 = 2 * v19 + 2;
    }
    else
    {
      v8 = &OutputString;
    }
    v32 = v8;
    v30 = &v22;
    v33 = v12;
    v34 = 0;
    v31 = 4;
    if ( a2 )
    {
      do
        ++v9;
      while ( *((_BYTE *)a2 + v9) );
      v5 = v9 + 1;
    }
    else
    {
      a2 = &qword_140023E40;
    }
    v27 = a2;
    v25 = &v23;
    v28 = v5;
    v29 = 0;
    v26 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002E4E0, (unsigned __int8 *)&byte_1400286CB, 0, 0, 0xBu, &v24);
  }
  return 0;
}

```

## disassembly

```asm
0x1400112c0  mov     rax, rsp
0x1400112c3  mov     [rax+8], rbx
0x1400112c7  mov     [rax+10h], rsi
0x1400112cb  mov     [rax+18h], rdi
0x1400112cf  mov     [rax+20h], r14
0x1400112d3  push    rbp
0x1400112d4  lea     rbp, [rax-5Fh]
0x1400112d8  sub     rsp, 100h
0x1400112df  mov     rax, cs:__security_cookie
0x1400112e6  xor     rax, rsp
0x1400112e9  mov     [rbp+57h+var_10], rax
0x1400112ed  cmp     cs:dword_14002E4E0, 5
0x1400112f4  mov     r10, rdx
0x1400112f7  jbe     loc_1400114BA
0x1400112fd  mov     rdx, 800000000000h
0x140011307  test    cs:qword_14002E4F0, rdx
0x14001130e  jz      loc_1400114BA
0x140011314  mov     rax, cs:qword_14002E4F8
0x14001131b  and     rax, rdx
0x14001131e  cmp     rax, cs:qword_14002E4F8
0x140011325  jnz     loc_1400114BA
0x14001132b  mov     eax, [rcx+8]
0x14001132e  xor     r14d, r14d
0x140011331  mov     r9, [rcx+28h]
0x140011335  mov     esi, 1
0x14001133a  mov     r11, [rcx+20h]
0x14001133e  mov     rbx, [rcx+18h]
0x140011342  mov     rdi, [rcx+10h]
0x140011346  mov     [rbp+57h+var_D0], eax
0x140011349  mov     eax, [rcx+0Ch]
0x14001134c  mov     [rbp+57h+var_CC], eax
0x14001134f  mov     eax, 81000000h
0x140011354  mov     [rbp+57h+var_C8], rax
0x140011358  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001135c  test    r8, r8
0x14001135f  jz      short loc_140011371
0x140011361  mov     rcx, rax
0x140011364  inc     rcx
0x140011367  cmp     [r8+rcx], r14b
0x14001136b  jnz     short loc_140011364
0x14001136d  inc     ecx
0x14001136f  jmp     short loc_14001137A
0x140011371  lea     r8, qword_140023E40
0x140011378  mov     ecx, esi
0x14001137a  mov     [rbp+57h+var_18], ecx
0x14001137d  lea     rcx, [rbp+57h+var_D0]
0x140011381  mov     [rbp+57h+var_20], r8
0x140011385  lea     r8, OutputString
0x14001138c  mov     [rbp+57h+var_30], rcx
0x140011390  mov     edx, 2
0x140011395  mov     [rbp+57h+var_14], r14d
0x140011399  mov     [rbp+57h+var_28], 4
0x1400113a1  test    r9, r9
0x1400113a4  jz      short loc_1400113BC
0x1400113a6  mov     rcx, rax
0x1400113a9  inc     rcx
0x1400113ac  cmp     [r9+rcx*2], r14w
0x1400113b1  jnz     short loc_1400113A9
0x1400113b3  lea     ecx, ds:2[rcx*2]
0x1400113ba  jmp     short loc_1400113C1
0x1400113bc  mov     r9, r8
0x1400113bf  mov     ecx, edx
0x1400113c1  mov     [rbp+57h+var_40], r9
0x1400113c5  mov     [rbp+57h+var_38], ecx
0x1400113c8  mov     [rbp+57h+var_34], r14d
0x1400113cc  test    r11, r11
0x1400113cf  jz      short loc_1400113E7
0x1400113d1  mov     rcx, rax
0x1400113d4  inc     rcx
0x1400113d7  cmp     [r11+rcx*2], r14w
0x1400113dc  jnz     short loc_1400113D4
0x1400113de  lea     ecx, ds:2[rcx*2]
0x1400113e5  jmp     short loc_1400113EC
0x1400113e7  mov     r11, r8
0x1400113ea  mov     ecx, edx
0x1400113ec  mov     [rbp+57h+var_50], r11
0x1400113f0  mov     [rbp+57h+var_48], ecx
0x1400113f3  mov     [rbp+57h+var_44], r14d
0x1400113f7  test    rbx, rbx
0x1400113fa  jz      short loc_140011412
0x1400113fc  mov     rcx, rax
0x1400113ff  inc     rcx
0x140011402  cmp     [rbx+rcx*2], r14w
0x140011407  jnz     short loc_1400113FF
0x140011409  lea     ecx, ds:2[rcx*2]
0x140011410  jmp     short loc_140011417
0x140011412  mov     rbx, r8
0x140011415  mov     ecx, edx
0x140011417  mov     [rbp+57h+var_60], rbx
0x14001141b  mov     [rbp+57h+var_58], ecx
0x14001141e  mov     [rbp+57h+var_54], r14d
0x140011422  test    rdi, rdi
0x140011425  jz      short loc_14001143D
0x140011427  mov     rcx, rax
0x14001142a  inc     rcx
0x14001142d  cmp     [rdi+rcx*2], r14w
0x140011432  jnz     short loc_14001142A
0x140011434  lea     edx, ds:2[rcx*2]
0x14001143b  jmp     short loc_140011440
0x14001143d  mov     rdi, r8
0x140011440  mov     [rbp+57h+var_70], rdi
0x140011444  lea     rcx, [rbp+57h+var_CC]
0x140011448  mov     [rbp+57h+var_80], rcx
0x14001144c  mov     [rbp+57h+var_68], edx
0x14001144f  mov     [rbp+57h+var_64], r14d
0x140011453  mov     [rbp+57h+var_78], 4
0x14001145b  test    r10, r10
0x14001145e  jz      short loc_14001146E
0x140011460  inc     rax
0x140011463  cmp     [r10+rax], r14b
0x140011467  jnz     short loc_140011460
0x140011469  lea     esi, [rax+1]
0x14001146c  jmp     short loc_140011475
0x14001146e  lea     r10, qword_140023E40
0x140011475  lea     rax, [rbp+57h+var_C8]
0x140011479  mov     [rbp+57h+var_90], r10
0x14001147d  mov     [rbp+57h+var_A0], rax
0x140011481  lea     rdx, byte_1400286CB; int
0x140011488  lea     rax, [rbp+57h+var_C0]
0x14001148c  mov     [rbp+57h+var_88], esi
0x14001148f  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140011494  lea     rcx, dword_14002E4E0; int
0x14001149b  xor     r9d, r9d; int
0x14001149e  mov     [rsp+100h+var_E0], 0Bh; ULONG
0x1400114a6  xor     r8d, r8d; int
0x1400114a9  mov     [rbp+57h+var_84], r14d
0x1400114ad  mov     [rbp+57h+var_98], 8
0x1400114b5  call    _tlgWriteTransfer_EventWriteTransfer
0x1400114ba  xor     eax, eax
0x1400114bc  mov     rcx, [rbp+57h+var_10]
0x1400114c0  xor     rcx, rsp; StackCookie
0x1400114c3  call    __security_check_cookie
0x1400114c8  lea     r11, [rsp+100h+var_s0]
0x1400114d0  mov     rbx, [r11+10h]
0x1400114d4  mov     rsi, [r11+18h]
0x1400114d8  mov     rdi, [r11+20h]
0x1400114dc  mov     r14, [r11+28h]
0x1400114e0  mov     rsp, r11
0x1400114e3  pop     rbp
0x1400114e4  retn
```
