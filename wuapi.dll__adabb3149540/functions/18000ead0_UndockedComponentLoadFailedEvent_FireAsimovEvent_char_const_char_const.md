# UndockedComponentLoadFailedEvent::FireAsimovEvent(char const *,char const *)

- ea: `0x18000ead0`
- end: `0x18000ecf5`
- name: `?FireAsimovEvent@UndockedComponentLoadFailedEvent@@UEAAJPEBD0@Z`
- size: `549`
- prototype: `__int64 __fastcall(UndockedComponentLoadFailedEvent *__hidden this, const char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007308`

## callees

- `0x18000140c`
- `0x18000ead0`
- `0x18000fce0`

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

  if ( (unsigned int)dword_180021510 > 5
    && (qword_180021520 & 0x800000000000LL) != 0
    && (qword_180021528 & 0x800000000000LL) == qword_180021528 )
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
      a3 = &word_1800189A6;
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
      a2 = &word_1800189A6;
    }
    v27 = a2;
    v25 = &v23;
    v28 = v5;
    v29 = 0;
    v26 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180021510, (unsigned __int8 *)&byte_18001C8CB, 0, 0, 0xBu, &v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ead0  mov     rax, rsp
0x18000ead3  mov     [rax+8], rbx
0x18000ead7  mov     [rax+10h], rsi
0x18000eadb  mov     [rax+18h], rdi
0x18000eadf  mov     [rax+20h], r14
0x18000eae3  push    rbp
0x18000eae4  lea     rbp, [rax-5Fh]
0x18000eae8  sub     rsp, 100h
0x18000eaef  mov     rax, cs:__security_cookie
0x18000eaf6  xor     rax, rsp
0x18000eaf9  mov     [rbp+57h+var_10], rax
0x18000eafd  cmp     cs:dword_180021510, 5
0x18000eb04  mov     r10, rdx
0x18000eb07  jbe     loc_18000ECCA
0x18000eb0d  mov     rdx, 800000000000h
0x18000eb17  test    cs:qword_180021520, rdx
0x18000eb1e  jz      loc_18000ECCA
0x18000eb24  mov     rax, cs:qword_180021528
0x18000eb2b  and     rax, rdx
0x18000eb2e  cmp     rax, cs:qword_180021528
0x18000eb35  jnz     loc_18000ECCA
0x18000eb3b  mov     eax, [rcx+8]
0x18000eb3e  xor     r14d, r14d
0x18000eb41  mov     r9, [rcx+28h]
0x18000eb45  mov     esi, 1
0x18000eb4a  mov     r11, [rcx+20h]
0x18000eb4e  mov     rbx, [rcx+18h]
0x18000eb52  mov     rdi, [rcx+10h]
0x18000eb56  mov     [rbp+57h+var_D0], eax
0x18000eb59  mov     eax, [rcx+0Ch]
0x18000eb5c  mov     [rbp+57h+var_CC], eax
0x18000eb5f  mov     eax, 81000000h
0x18000eb64  mov     [rbp+57h+var_C8], rax
0x18000eb68  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000eb6c  test    r8, r8
0x18000eb6f  jz      short loc_18000EB81
0x18000eb71  mov     rcx, rax
0x18000eb74  inc     rcx
0x18000eb77  cmp     [r8+rcx], r14b
0x18000eb7b  jnz     short loc_18000EB74
0x18000eb7d  inc     ecx
0x18000eb7f  jmp     short loc_18000EB8A
0x18000eb81  lea     r8, word_1800189A6
0x18000eb88  mov     ecx, esi
0x18000eb8a  mov     [rbp+57h+var_18], ecx
0x18000eb8d  lea     rcx, [rbp+57h+var_D0]
0x18000eb91  mov     [rbp+57h+var_20], r8
0x18000eb95  lea     r8, OutputString
0x18000eb9c  mov     [rbp+57h+var_30], rcx
0x18000eba0  mov     edx, 2
0x18000eba5  mov     [rbp+57h+var_14], r14d
0x18000eba9  mov     [rbp+57h+var_28], 4
0x18000ebb1  test    r9, r9
0x18000ebb4  jz      short loc_18000EBCC
0x18000ebb6  mov     rcx, rax
0x18000ebb9  inc     rcx
0x18000ebbc  cmp     [r9+rcx*2], r14w
0x18000ebc1  jnz     short loc_18000EBB9
0x18000ebc3  lea     ecx, ds:2[rcx*2]
0x18000ebca  jmp     short loc_18000EBD1
0x18000ebcc  mov     r9, r8
0x18000ebcf  mov     ecx, edx
0x18000ebd1  mov     [rbp+57h+var_40], r9
0x18000ebd5  mov     [rbp+57h+var_38], ecx
0x18000ebd8  mov     [rbp+57h+var_34], r14d
0x18000ebdc  test    r11, r11
0x18000ebdf  jz      short loc_18000EBF7
0x18000ebe1  mov     rcx, rax
0x18000ebe4  inc     rcx
0x18000ebe7  cmp     [r11+rcx*2], r14w
0x18000ebec  jnz     short loc_18000EBE4
0x18000ebee  lea     ecx, ds:2[rcx*2]
0x18000ebf5  jmp     short loc_18000EBFC
0x18000ebf7  mov     r11, r8
0x18000ebfa  mov     ecx, edx
0x18000ebfc  mov     [rbp+57h+var_50], r11
0x18000ec00  mov     [rbp+57h+var_48], ecx
0x18000ec03  mov     [rbp+57h+var_44], r14d
0x18000ec07  test    rbx, rbx
0x18000ec0a  jz      short loc_18000EC22
0x18000ec0c  mov     rcx, rax
0x18000ec0f  inc     rcx
0x18000ec12  cmp     [rbx+rcx*2], r14w
0x18000ec17  jnz     short loc_18000EC0F
0x18000ec19  lea     ecx, ds:2[rcx*2]
0x18000ec20  jmp     short loc_18000EC27
0x18000ec22  mov     rbx, r8
0x18000ec25  mov     ecx, edx
0x18000ec27  mov     [rbp+57h+var_60], rbx
0x18000ec2b  mov     [rbp+57h+var_58], ecx
0x18000ec2e  mov     [rbp+57h+var_54], r14d
0x18000ec32  test    rdi, rdi
0x18000ec35  jz      short loc_18000EC4D
0x18000ec37  mov     rcx, rax
0x18000ec3a  inc     rcx
0x18000ec3d  cmp     [rdi+rcx*2], r14w
0x18000ec42  jnz     short loc_18000EC3A
0x18000ec44  lea     edx, ds:2[rcx*2]
0x18000ec4b  jmp     short loc_18000EC50
0x18000ec4d  mov     rdi, r8
0x18000ec50  mov     [rbp+57h+var_70], rdi
0x18000ec54  lea     rcx, [rbp+57h+var_CC]
0x18000ec58  mov     [rbp+57h+var_80], rcx
0x18000ec5c  mov     [rbp+57h+var_68], edx
0x18000ec5f  mov     [rbp+57h+var_64], r14d
0x18000ec63  mov     [rbp+57h+var_78], 4
0x18000ec6b  test    r10, r10
0x18000ec6e  jz      short loc_18000EC7E
0x18000ec70  inc     rax
0x18000ec73  cmp     [r10+rax], r14b
0x18000ec77  jnz     short loc_18000EC70
0x18000ec79  lea     esi, [rax+1]
0x18000ec7c  jmp     short loc_18000EC85
0x18000ec7e  lea     r10, word_1800189A6
0x18000ec85  lea     rax, [rbp+57h+var_C8]
0x18000ec89  mov     [rbp+57h+var_90], r10
0x18000ec8d  mov     [rbp+57h+var_A0], rax
0x18000ec91  lea     rdx, byte_18001C8CB; int
0x18000ec98  lea     rax, [rbp+57h+var_C0]
0x18000ec9c  mov     [rbp+57h+var_88], esi
0x18000ec9f  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x18000eca4  lea     rcx, dword_180021510; int
0x18000ecab  xor     r9d, r9d; int
0x18000ecae  mov     [rsp+100h+var_E0], 0Bh; ULONG
0x18000ecb6  xor     r8d, r8d; int
0x18000ecb9  mov     [rbp+57h+var_84], r14d
0x18000ecbd  mov     [rbp+57h+var_98], 8
0x18000ecc5  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ecca  xor     eax, eax
0x18000eccc  mov     rcx, [rbp+57h+var_10]
0x18000ecd0  xor     rcx, rsp; StackCookie
0x18000ecd3  call    __security_check_cookie
0x18000ecd8  lea     r11, [rsp+100h+var_s0]
0x18000ece0  mov     rbx, [r11+10h]
0x18000ece4  mov     rsi, [r11+18h]
0x18000ece8  mov     rdi, [r11+20h]
0x18000ecec  mov     r14, [r11+28h]
0x18000ecf0  mov     rsp, r11
0x18000ecf3  pop     rbp
0x18000ecf4  retn
```
