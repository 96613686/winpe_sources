# UndockedComponentLoadFailedEvent::FireAsimovEvent(char const *,char const *)

- ea: `0x18000ea80`
- end: `0x18000eca5`
- name: `?FireAsimovEvent@UndockedComponentLoadFailedEvent@@UEAAJPEBD0@Z`
- size: `549`
- prototype: `__int64 __fastcall(UndockedComponentLoadFailedEvent *this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005524`

## callees

- `0x180001158`
- `0x18000ea80`
- `0x18000fc90`

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
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180021510, (int)&byte_18001C8CB, 0, 0, 0xBu, &v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ea80  mov     rax, rsp
0x18000ea83  mov     [rax+8], rbx
0x18000ea87  mov     [rax+10h], rsi
0x18000ea8b  mov     [rax+18h], rdi
0x18000ea8f  mov     [rax+20h], r14
0x18000ea93  push    rbp
0x18000ea94  lea     rbp, [rax-5Fh]
0x18000ea98  sub     rsp, 100h
0x18000ea9f  mov     rax, cs:__security_cookie
0x18000eaa6  xor     rax, rsp
0x18000eaa9  mov     [rbp+57h+var_10], rax
0x18000eaad  cmp     cs:dword_180021510, 5
0x18000eab4  mov     r10, rdx
0x18000eab7  jbe     loc_18000EC7A
0x18000eabd  mov     rdx, 800000000000h
0x18000eac7  test    cs:qword_180021520, rdx
0x18000eace  jz      loc_18000EC7A
0x18000ead4  mov     rax, cs:qword_180021528
0x18000eadb  and     rax, rdx
0x18000eade  cmp     rax, cs:qword_180021528
0x18000eae5  jnz     loc_18000EC7A
0x18000eaeb  mov     eax, [rcx+8]
0x18000eaee  xor     r14d, r14d
0x18000eaf1  mov     r9, [rcx+28h]
0x18000eaf5  mov     esi, 1
0x18000eafa  mov     r11, [rcx+20h]
0x18000eafe  mov     rbx, [rcx+18h]
0x18000eb02  mov     rdi, [rcx+10h]
0x18000eb06  mov     [rbp+57h+var_D0], eax
0x18000eb09  mov     eax, [rcx+0Ch]
0x18000eb0c  mov     [rbp+57h+var_CC], eax
0x18000eb0f  mov     eax, 81000000h
0x18000eb14  mov     [rbp+57h+var_C8], rax
0x18000eb18  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000eb1c  test    r8, r8
0x18000eb1f  jz      short loc_18000EB31
0x18000eb21  mov     rcx, rax
0x18000eb24  inc     rcx
0x18000eb27  cmp     [r8+rcx], r14b
0x18000eb2b  jnz     short loc_18000EB24
0x18000eb2d  inc     ecx
0x18000eb2f  jmp     short loc_18000EB3A
0x18000eb31  lea     r8, word_1800189A6
0x18000eb38  mov     ecx, esi
0x18000eb3a  mov     [rbp+57h+var_18], ecx
0x18000eb3d  lea     rcx, [rbp+57h+var_D0]
0x18000eb41  mov     [rbp+57h+var_20], r8
0x18000eb45  lea     r8, OutputString
0x18000eb4c  mov     [rbp+57h+var_30], rcx
0x18000eb50  mov     edx, 2
0x18000eb55  mov     [rbp+57h+var_14], r14d
0x18000eb59  mov     [rbp+57h+var_28], 4
0x18000eb61  test    r9, r9
0x18000eb64  jz      short loc_18000EB7C
0x18000eb66  mov     rcx, rax
0x18000eb69  inc     rcx
0x18000eb6c  cmp     [r9+rcx*2], r14w
0x18000eb71  jnz     short loc_18000EB69
0x18000eb73  lea     ecx, ds:2[rcx*2]
0x18000eb7a  jmp     short loc_18000EB81
0x18000eb7c  mov     r9, r8
0x18000eb7f  mov     ecx, edx
0x18000eb81  mov     [rbp+57h+var_40], r9
0x18000eb85  mov     [rbp+57h+var_38], ecx
0x18000eb88  mov     [rbp+57h+var_34], r14d
0x18000eb8c  test    r11, r11
0x18000eb8f  jz      short loc_18000EBA7
0x18000eb91  mov     rcx, rax
0x18000eb94  inc     rcx
0x18000eb97  cmp     [r11+rcx*2], r14w
0x18000eb9c  jnz     short loc_18000EB94
0x18000eb9e  lea     ecx, ds:2[rcx*2]
0x18000eba5  jmp     short loc_18000EBAC
0x18000eba7  mov     r11, r8
0x18000ebaa  mov     ecx, edx
0x18000ebac  mov     [rbp+57h+var_50], r11
0x18000ebb0  mov     [rbp+57h+var_48], ecx
0x18000ebb3  mov     [rbp+57h+var_44], r14d
0x18000ebb7  test    rbx, rbx
0x18000ebba  jz      short loc_18000EBD2
0x18000ebbc  mov     rcx, rax
0x18000ebbf  inc     rcx
0x18000ebc2  cmp     [rbx+rcx*2], r14w
0x18000ebc7  jnz     short loc_18000EBBF
0x18000ebc9  lea     ecx, ds:2[rcx*2]
0x18000ebd0  jmp     short loc_18000EBD7
0x18000ebd2  mov     rbx, r8
0x18000ebd5  mov     ecx, edx
0x18000ebd7  mov     [rbp+57h+var_60], rbx
0x18000ebdb  mov     [rbp+57h+var_58], ecx
0x18000ebde  mov     [rbp+57h+var_54], r14d
0x18000ebe2  test    rdi, rdi
0x18000ebe5  jz      short loc_18000EBFD
0x18000ebe7  mov     rcx, rax
0x18000ebea  inc     rcx
0x18000ebed  cmp     [rdi+rcx*2], r14w
0x18000ebf2  jnz     short loc_18000EBEA
0x18000ebf4  lea     edx, ds:2[rcx*2]
0x18000ebfb  jmp     short loc_18000EC00
0x18000ebfd  mov     rdi, r8
0x18000ec00  mov     [rbp+57h+var_70], rdi
0x18000ec04  lea     rcx, [rbp+57h+var_CC]
0x18000ec08  mov     [rbp+57h+var_80], rcx
0x18000ec0c  mov     [rbp+57h+var_68], edx
0x18000ec0f  mov     [rbp+57h+var_64], r14d
0x18000ec13  mov     [rbp+57h+var_78], 4
0x18000ec1b  test    r10, r10
0x18000ec1e  jz      short loc_18000EC2E
0x18000ec20  inc     rax
0x18000ec23  cmp     [r10+rax], r14b
0x18000ec27  jnz     short loc_18000EC20
0x18000ec29  lea     esi, [rax+1]
0x18000ec2c  jmp     short loc_18000EC35
0x18000ec2e  lea     r10, word_1800189A6
0x18000ec35  lea     rax, [rbp+57h+var_C8]
0x18000ec39  mov     [rbp+57h+var_90], r10
0x18000ec3d  mov     [rbp+57h+var_A0], rax
0x18000ec41  lea     rdx, byte_18001C8CB; int
0x18000ec48  lea     rax, [rbp+57h+var_C0]
0x18000ec4c  mov     [rbp+57h+var_88], esi
0x18000ec4f  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x18000ec54  lea     rcx, dword_180021510; int
0x18000ec5b  xor     r9d, r9d; int
0x18000ec5e  mov     [rsp+100h+var_E0], 0Bh; ULONG
0x18000ec66  xor     r8d, r8d; int
0x18000ec69  mov     [rbp+57h+var_84], r14d
0x18000ec6d  mov     [rbp+57h+var_98], 8
0x18000ec75  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ec7a  xor     eax, eax
0x18000ec7c  mov     rcx, [rbp+57h+var_10]
0x18000ec80  xor     rcx, rsp; StackCookie
0x18000ec83  call    __security_check_cookie
0x18000ec88  lea     r11, [rsp+100h+var_s0]
0x18000ec90  mov     rbx, [r11+10h]
0x18000ec94  mov     rsi, [r11+18h]
0x18000ec98  mov     rdi, [r11+20h]
0x18000ec9c  mov     r14, [r11+28h]
0x18000eca0  mov     rsp, r11
0x18000eca3  pop     rbp
0x18000eca4  retn
```
