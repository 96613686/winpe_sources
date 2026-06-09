# McTemplateU0zzzzzzzzz_EventWriteTransfer

- ea: `0x1800114a4`
- end: `0x1800116a3`
- name: `McTemplateU0zzzzzzzzz_EventWriteTransfer`
- size: `511`
- prototype: `ULONG __fastcall(__int64, __int64, const char *, const char *, const char *, const char *, const char *, const char *, const char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800105e4`

## callees

- `0x1800097d0`
- `0x180011444`
- `0x1800114a4`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzzzzzzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const char *a3,
        const char *a4,
        const char *a5,
        const char *a6,
        const char *a7,
        const char *a8,
        const char *a9,
        const char *a10)
{
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // edx
  __int64 v14; // rdx
  int v15; // edx
  const char *v16; // rdx
  __int64 v17; // r8
  int v18; // r8d
  const char *v19; // rdx
  __int64 v20; // r8
  int v21; // r8d
  const char *v22; // rdx
  __int64 v23; // r8
  int v24; // r8d
  const char *v25; // rdx
  __int64 v26; // r8
  int v27; // r8d
  const char *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r8
  const char *v31; // rdx
  bool v32; // zf
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+30h] [rbp-91h] BYREF
  const char *v35; // [rsp+40h] [rbp-81h]
  int v36; // [rsp+48h] [rbp-79h]
  int v37; // [rsp+4Ch] [rbp-75h]
  const char *v38; // [rsp+50h] [rbp-71h]
  int v39; // [rsp+58h] [rbp-69h]
  int v40; // [rsp+5Ch] [rbp-65h]
  const char *v41; // [rsp+60h] [rbp-61h]
  int v42; // [rsp+68h] [rbp-59h]
  int v43; // [rsp+6Ch] [rbp-55h]
  const char *v44; // [rsp+70h] [rbp-51h]
  int v45; // [rsp+78h] [rbp-49h]
  int v46; // [rsp+7Ch] [rbp-45h]
  const char *v47; // [rsp+80h] [rbp-41h]
  int v48; // [rsp+88h] [rbp-39h]
  int v49; // [rsp+8Ch] [rbp-35h]
  const char *v50; // [rsp+90h] [rbp-31h]
  int v51; // [rsp+98h] [rbp-29h]
  int v52; // [rsp+9Ch] [rbp-25h]
  const char *v53; // [rsp+A0h] [rbp-21h]
  int v54; // [rsp+A8h] [rbp-19h]
  int v55; // [rsp+ACh] [rbp-15h]
  const char *v56; // [rsp+B0h] [rbp-11h]
  int v57; // [rsp+B8h] [rbp-9h]
  int v58; // [rsp+BCh] [rbp-5h]
  const wchar_t *v59; // [rsp+C0h] [rbp-1h]
  __int64 v60; // [rsp+C8h] [rbp+7h]

  v10 = -1;
  v11 = 10;
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)&a3[2 * v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v13 = 10;
  }
  v36 = v13;
  v37 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v35 = a3;
  if ( a4 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&a4[2 * v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v15 = 10;
  }
  v39 = v15;
  v16 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v40 = 0;
  v38 = a4;
  if ( a5 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)&a5[2 * v17] );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v18 = 10;
  }
  v42 = v18;
  v43 = 0;
  if ( !a5 )
    v16 = L"NULL";
  v41 = v16;
  v19 = a6;
  if ( a6 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)&a6[2 * v20] );
    v21 = 2 * v20 + 2;
  }
  else
  {
    v21 = 10;
  }
  v45 = v21;
  v46 = 0;
  if ( !a6 )
    v19 = L"NULL";
  v44 = v19;
  v22 = a7;
  if ( a7 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)&a7[2 * v23] );
    v24 = 2 * v23 + 2;
  }
  else
  {
    v24 = 10;
  }
  v48 = v24;
  v49 = 0;
  if ( !a7 )
    v22 = L"NULL";
  v47 = v22;
  v25 = a8;
  if ( a8 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)&a8[2 * v26] );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v27 = 10;
  }
  v51 = v27;
  v52 = 0;
  if ( !a8 )
    v25 = L"NULL";
  v50 = v25;
  v28 = a9;
  if ( a9 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)&a9[2 * v29] );
    v30 = (unsigned int)(2 * v29 + 2);
  }
  else
  {
    v30 = 10;
  }
  v54 = v30;
  v55 = 0;
  if ( !a9 )
    v28 = L"NULL";
  v53 = v28;
  v31 = a10;
  v32 = a10 == 0;
  if ( a10 )
  {
    do
      ++v10;
    while ( *(_WORD *)&a10[2 * v10] );
    v11 = (unsigned int)(2 * v10 + 2);
    v32 = a10 == 0;
  }
  v57 = v11;
  v59 = L"Portable Device Enumerator";
  if ( v32 )
    v31 = L"NULL";
  v56 = v31;
  v58 = 0;
  v60 = 54;
  return McGenEventWrite_EventWriteTransfer(v11, (__int64)v31, v30, (__int64)a4, &v34);
}

```

## disassembly

```asm
0x1800114a4  push    rbp
0x1800114a6  lea     rbp, [rsp-1Fh]
0x1800114ab  sub     rsp, 0E0h
0x1800114b2  mov     rax, cs:__security_cookie
0x1800114b9  xor     rax, rsp
0x1800114bc  mov     [rbp+1Fh+var_10], rax
0x1800114c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800114c4  xor     r10d, r10d
0x1800114c7  mov     ecx, 0Ah
0x1800114cc  test    r8, r8
0x1800114cf  jz      short loc_1800114E7
0x1800114d1  mov     rdx, rax
0x1800114d4  inc     rdx
0x1800114d7  cmp     [r8+rdx*2], r10w
0x1800114dc  jnz     short loc_1800114D4
0x1800114de  lea     edx, ds:2[rdx*2]
0x1800114e5  jmp     short loc_1800114E9
0x1800114e7  mov     edx, ecx
0x1800114e9  test    r8, r8
0x1800114ec  mov     [rbp+1Fh+var_98], edx
0x1800114ef  lea     r11, aNull_0; "NULL"
0x1800114f6  mov     [rbp+1Fh+var_94], r10d
0x1800114fa  cmovz   r8, r11
0x1800114fe  mov     [rsp+0E0h+var_A0], r8
0x180011503  test    r9, r9
0x180011506  jz      short loc_18001151E
0x180011508  mov     rdx, rax
0x18001150b  inc     rdx
0x18001150e  cmp     [r9+rdx*2], r10w
0x180011513  jnz     short loc_18001150B
0x180011515  lea     edx, ds:2[rdx*2]
0x18001151c  jmp     short loc_180011520
0x18001151e  mov     edx, ecx
0x180011520  test    r9, r9
0x180011523  mov     [rbp+1Fh+var_88], edx
0x180011526  mov     rdx, [rbp+1Fh+arg_20]
0x18001152a  cmovz   r9, r11; int
0x18001152e  mov     [rbp+1Fh+var_84], r10d
0x180011532  mov     [rbp+1Fh+var_90], r9
0x180011536  test    rdx, rdx
0x180011539  jz      short loc_180011552
0x18001153b  mov     r8, rax
0x18001153e  inc     r8
0x180011541  cmp     [rdx+r8*2], r10w
0x180011546  jnz     short loc_18001153E
0x180011548  lea     r8d, ds:2[r8*2]
0x180011550  jmp     short loc_180011555
0x180011552  mov     r8d, ecx
0x180011555  test    rdx, rdx
0x180011558  mov     [rbp+1Fh+var_78], r8d
0x18001155c  mov     [rbp+1Fh+var_74], r10d
0x180011560  cmovz   rdx, r11
0x180011564  mov     [rbp+1Fh+var_80], rdx
0x180011568  mov     rdx, [rbp+1Fh+arg_28]
0x18001156c  test    rdx, rdx
0x18001156f  jz      short loc_180011588
0x180011571  mov     r8, rax
0x180011574  inc     r8
0x180011577  cmp     [rdx+r8*2], r10w
0x18001157c  jnz     short loc_180011574
0x18001157e  lea     r8d, ds:2[r8*2]
0x180011586  jmp     short loc_18001158B
0x180011588  mov     r8d, ecx
0x18001158b  test    rdx, rdx
0x18001158e  mov     [rbp+1Fh+var_68], r8d
0x180011592  mov     [rbp+1Fh+var_64], r10d
0x180011596  cmovz   rdx, r11
0x18001159a  mov     [rbp+1Fh+var_70], rdx
0x18001159e  mov     rdx, [rbp+1Fh+arg_30]
0x1800115a2  test    rdx, rdx
0x1800115a5  jz      short loc_1800115BE
0x1800115a7  mov     r8, rax
0x1800115aa  inc     r8
0x1800115ad  cmp     [rdx+r8*2], r10w
0x1800115b2  jnz     short loc_1800115AA
0x1800115b4  lea     r8d, ds:2[r8*2]
0x1800115bc  jmp     short loc_1800115C1
0x1800115be  mov     r8d, ecx
0x1800115c1  test    rdx, rdx
0x1800115c4  mov     [rbp+1Fh+var_58], r8d
0x1800115c8  mov     [rbp+1Fh+var_54], r10d
0x1800115cc  cmovz   rdx, r11
0x1800115d0  mov     [rbp+1Fh+var_60], rdx
0x1800115d4  mov     rdx, [rbp+1Fh+arg_38]
0x1800115d8  test    rdx, rdx
0x1800115db  jz      short loc_1800115F4
0x1800115dd  mov     r8, rax
0x1800115e0  inc     r8
0x1800115e3  cmp     [rdx+r8*2], r10w
0x1800115e8  jnz     short loc_1800115E0
0x1800115ea  lea     r8d, ds:2[r8*2]
0x1800115f2  jmp     short loc_1800115F7
0x1800115f4  mov     r8d, ecx
0x1800115f7  test    rdx, rdx
0x1800115fa  mov     [rbp+1Fh+var_48], r8d
0x1800115fe  mov     [rbp+1Fh+var_44], r10d
0x180011602  cmovz   rdx, r11
0x180011606  mov     [rbp+1Fh+var_50], rdx
0x18001160a  mov     rdx, [rbp+1Fh+arg_40]
0x18001160e  test    rdx, rdx
0x180011611  jz      short loc_18001162A
0x180011613  mov     r8, rax
0x180011616  inc     r8
0x180011619  cmp     [rdx+r8*2], r10w
0x18001161e  jnz     short loc_180011616
0x180011620  lea     r8d, ds:2[r8*2]
0x180011628  jmp     short loc_18001162D
0x18001162a  mov     r8d, ecx; int
0x18001162d  test    rdx, rdx
0x180011630  mov     [rbp+1Fh+var_38], r8d
0x180011634  mov     [rbp+1Fh+var_34], r10d
0x180011638  cmovz   rdx, r11
0x18001163c  mov     [rbp+1Fh+var_40], rdx
0x180011640  mov     rdx, [rbp+1Fh+arg_48]
0x180011644  test    rdx, rdx
0x180011647  jz      short loc_18001165D
0x180011649  inc     rax
0x18001164c  cmp     [rdx+rax*2], r10w
0x180011651  jnz     short loc_180011649
0x180011653  lea     ecx, ds:2[rax*2]; int
0x18001165a  test    rdx, rdx
0x18001165d  lea     rax, aPortableDevice; "Portable Device Enumerator"
0x180011664  mov     [rbp+1Fh+var_28], ecx
0x180011667  mov     [rbp+1Fh+var_20], rax
0x18001166b  cmovz   rdx, r11; int
0x18001166f  lea     rax, [rsp+0E0h+var_B0]
0x180011674  mov     [rbp+1Fh+var_30], rdx
0x180011678  mov     [rsp+0E0h+var_C0], rax; PEVENT_DATA_DESCRIPTOR
0x18001167d  mov     [rbp+1Fh+var_24], r10d
0x180011681  mov     [rbp+1Fh+var_18], 36h ; '6'
0x180011689  call    McGenEventWrite_EventWriteTransfer
0x18001168e  mov     rcx, [rbp+1Fh+var_10]
0x180011692  xor     rcx, rsp; StackCookie
0x180011695  call    __security_check_cookie
0x18001169a  add     rsp, 0E0h
0x1800116a1  pop     rbp
0x1800116a2  retn
```
