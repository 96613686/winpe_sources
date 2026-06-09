# CWerComReport::_get_ReportInformation(_WER_REPORT_DETAILS *)

- ea: `0x1800108f4`
- end: `0x180010b20`
- name: `?_get_ReportInformation@CWerComReport@@QEAAJPEAU_WER_REPORT_DETAILS@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, struct _WER_REPORT_DETAILS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011920`

## callees

- `0x180006c9c`
- `0x18000e35c`
- `0x1800108f4`

## import_xrefs

- `wer!WerpGetReportInformation` at `0x180010972`
- `wer!WerpGetReportInformation` at `0x180010972`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_ReportInformation(CWerComReport *this, struct _WER_REPORT_DETAILS *a2)
{
  int WerApiLock; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  _WORD *v8; // rbx
  _WORD *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  _WORD *v13; // r9
  _WORD *v14; // rcx
  __int64 v15; // r9
  _WORD *v16; // r10
  __int64 v17; // r8
  _WORD *v18; // rax
  __int64 v19; // rcx
  bool v20; // zf
  _WORD *v21; // rcx
  _WORD *v22; // r10
  __int64 v23; // r8
  _WORD *v24; // rax
  __int64 v25; // rcx
  _WORD *v26; // rcx
  _WORD *v27; // r10
  __int64 v28; // r8
  _WORD *v29; // rax
  __int64 v30; // rcx
  _WORD *v31; // rcx
  _WORD *v32; // rax
  _WORD *v33; // rcx
  _WORD *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // [rsp+50h] [rbp+18h] BYREF
  _WORD *v37; // [rsp+58h] [rbp+20h] BYREF

  v37 = 0;
  v36 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v36, this);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 53;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  WerApiLock = WerpGetReportInformation(*((_QWORD *)this + 4), &v37);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 54;
      goto LABEL_5;
    }
LABEL_6:
    if ( v36 )
      _InterlockedExchange((volatile __int32 *)(v36 + 48), 0);
    return (unsigned int)WerApiLock;
  }
  v8 = v37;
  v9 = (_WORD *)((char *)a2 + 4);
  v10 = 64;
  v11 = 2147483646;
  v12 = 2147483646;
  v13 = v37 + 8;
  do
  {
    if ( !v12 )
      break;
    if ( !*v13 )
      break;
    *v9++ = *v13++;
    --v12;
    --v10;
  }
  while ( v10 );
  v14 = v9 - 1;
  v15 = 128;
  v16 = v8 + 200;
  if ( v10 )
    v14 = v9;
  v17 = 128;
  v18 = (_WORD *)((char *)a2 + 388);
  *v14 = 0;
  v19 = 2147483646;
  do
  {
    if ( !v19 )
      break;
    if ( !*v16 )
      break;
    *v18++ = *v16++;
    --v19;
    --v17;
  }
  while ( v17 );
  v20 = v17 == 0;
  v21 = v18 - 1;
  v22 = v8 + 328;
  v23 = 260;
  if ( !v20 )
    v21 = v18;
  v24 = (_WORD *)((char *)a2 + 644);
  *v21 = 0;
  v25 = 2147483646;
  do
  {
    if ( !v25 )
      break;
    if ( !*v22 )
      break;
    *v24++ = *v22++;
    --v25;
    --v23;
  }
  while ( v23 );
  v20 = v23 == 0;
  v26 = v24 - 1;
  v27 = v8 + 588;
  v28 = 512;
  if ( !v20 )
    v26 = v24;
  v29 = (_WORD *)((char *)a2 + 1164);
  *v26 = 0;
  v30 = 2147483646;
  do
  {
    if ( !v30 )
      break;
    if ( !*v27 )
      break;
    *v29++ = *v27++;
    --v30;
    --v28;
  }
  while ( v28 );
  v31 = v29 - 1;
  if ( v28 )
    v31 = v29;
  v32 = (_WORD *)((char *)a2 + 132);
  *v31 = 0;
  v33 = v8 + 72;
  do
  {
    if ( !v11 )
      break;
    if ( !*v33 )
      break;
    *v32++ = *v33++;
    --v11;
    --v15;
  }
  while ( v15 );
  v34 = v32 - 1;
  if ( v15 )
    v34 = v32;
  v35 = v36;
  *v34 = 0;
  if ( v35 )
    _InterlockedExchange((volatile __int32 *)(v35 + 48), 0);
  return 0;
}

```

## disassembly

```asm
0x1800108f4  mov     rax, rsp
0x1800108f7  mov     [rax+8], rbx
0x1800108fb  push    rbp
0x1800108fc  push    rsi
0x1800108fd  push    rdi
0x1800108fe  sub     rsp, 20h
0x180010902  mov     rsi, rdx
0x180010905  mov     rdi, rcx
0x180010908  mov     rdx, rcx; struct CWerComReport *
0x18001090b  xor     ebp, ebp
0x18001090d  lea     rcx, [rax+18h]; this
0x180010911  mov     [rax+20h], rbp
0x180010915  mov     [rax+18h], rbp
0x180010919  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18001091e  mov     ebx, eax
0x180010920  test    eax, eax
0x180010922  jns     short loc_180010969
0x180010924  mov     rcx, cs:WPP_GLOBAL_Control
0x18001092b  lea     rdx, WPP_GLOBAL_Control
0x180010932  cmp     rcx, rdx
0x180010935  jz      short loc_180010953
0x180010937  test    byte ptr [rcx+1Ch], 1
0x18001093b  jz      short loc_180010953
0x18001093d  lea     edx, [rbp+35h]
0x180010940  mov     rcx, [rcx+10h]
0x180010944  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18001094b  mov     r9d, ebx
0x18001094e  call    WPP_SF_d
0x180010953  mov     rax, [rsp+38h+arg_10]
0x180010958  test    rax, rax
0x18001095b  jz      short loc_180010962
0x18001095d  mov     ecx, ebp
0x18001095f  xchg    ecx, [rax+30h]
0x180010962  mov     eax, ebx
0x180010964  jmp     loc_180010B13
0x180010969  mov     rcx, [rdi+20h]
0x18001096d  lea     rdx, [rsp+38h+arg_18]
0x180010972  call    cs:__imp_WerpGetReportInformation
0x180010978  mov     ebx, eax
0x18001097a  test    eax, eax
0x18001097c  jns     short loc_18001099E
0x18001097e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010985  lea     rdx, WPP_GLOBAL_Control
0x18001098c  cmp     rcx, rdx
0x18001098f  jz      short loc_180010953
0x180010991  test    byte ptr [rcx+1Ch], 1
0x180010995  jz      short loc_180010953
0x180010997  mov     edx, 36h ; '6'
0x18001099c  jmp     short loc_180010940
0x18001099e  mov     rbx, [rsp+38h+arg_18]
0x1800109a3  lea     rax, [rsi+4]
0x1800109a7  mov     r8d, 40h ; '@'
0x1800109ad  mov     edx, 7FFFFFFEh
0x1800109b2  mov     ecx, edx
0x1800109b4  lea     r9, [rbx+10h]
0x1800109b8  lea     edi, [r8-3Eh]
0x1800109bc  test    rcx, rcx
0x1800109bf  jz      short loc_1800109DE
0x1800109c1  movzx   r10d, word ptr [r9]
0x1800109c5  test    r10w, r10w
0x1800109c9  jz      short loc_1800109DE
0x1800109cb  mov     [rax], r10w
0x1800109cf  add     r9, rdi
0x1800109d2  add     rax, rdi
0x1800109d5  dec     rcx
0x1800109d8  sub     r8, 1
0x1800109dc  jnz     short loc_1800109BC
0x1800109de  test    r8, r8
0x1800109e1  lea     rcx, [rax-2]
0x1800109e5  mov     r9d, 80h
0x1800109eb  lea     r10, [rbx+190h]
0x1800109f2  cmovnz  rcx, rax
0x1800109f6  mov     r8d, r9d
0x1800109f9  lea     rax, [rsi+184h]
0x180010a00  mov     [rcx], bp
0x180010a03  mov     rcx, rdx
0x180010a06  test    rcx, rcx
0x180010a09  jz      short loc_180010A28
0x180010a0b  movzx   r11d, word ptr [r10]
0x180010a0f  test    r11w, r11w
0x180010a13  jz      short loc_180010A28
0x180010a15  mov     [rax], r11w
0x180010a19  add     r10, rdi
0x180010a1c  add     rax, rdi
0x180010a1f  dec     rcx
0x180010a22  sub     r8, 1
0x180010a26  jnz     short loc_180010A06
0x180010a28  test    r8, r8
0x180010a2b  lea     rcx, [rax-2]
0x180010a2f  lea     r10, [rbx+290h]
0x180010a36  mov     r8d, 104h
0x180010a3c  cmovnz  rcx, rax
0x180010a40  lea     rax, [rsi+284h]
0x180010a47  mov     [rcx], bp
0x180010a4a  mov     rcx, rdx
0x180010a4d  test    rcx, rcx
0x180010a50  jz      short loc_180010A6F
0x180010a52  movzx   r11d, word ptr [r10]
0x180010a56  test    r11w, r11w
0x180010a5a  jz      short loc_180010A6F
0x180010a5c  mov     [rax], r11w
0x180010a60  add     r10, rdi
0x180010a63  add     rax, rdi
0x180010a66  dec     rcx
0x180010a69  sub     r8, 1
0x180010a6d  jnz     short loc_180010A4D
0x180010a6f  test    r8, r8
0x180010a72  lea     rcx, [rax-2]
0x180010a76  lea     r10, [rbx+498h]
0x180010a7d  mov     r8d, 200h
0x180010a83  cmovnz  rcx, rax
0x180010a87  lea     rax, [rsi+48Ch]
0x180010a8e  mov     [rcx], bp
0x180010a91  mov     rcx, rdx
0x180010a94  test    rcx, rcx
0x180010a97  jz      short loc_180010AB6
0x180010a99  movzx   r11d, word ptr [r10]
0x180010a9d  test    r11w, r11w
0x180010aa1  jz      short loc_180010AB6
0x180010aa3  mov     [rax], r11w
0x180010aa7  add     r10, rdi
0x180010aaa  add     rax, rdi
0x180010aad  dec     rcx
0x180010ab0  sub     r8, 1
0x180010ab4  jnz     short loc_180010A94
0x180010ab6  lea     rcx, [rax-2]
0x180010aba  test    r8, r8
0x180010abd  cmovnz  rcx, rax
0x180010ac1  lea     rax, [rsi+84h]
0x180010ac8  mov     [rcx], bp
0x180010acb  lea     rcx, [rbx+90h]
0x180010ad2  test    rdx, rdx
0x180010ad5  jz      short loc_180010AF4
0x180010ad7  movzx   r8d, word ptr [rcx]
0x180010adb  test    r8w, r8w
0x180010adf  jz      short loc_180010AF4
0x180010ae1  mov     [rax], r8w
0x180010ae5  add     rcx, rdi
0x180010ae8  add     rax, rdi
0x180010aeb  dec     rdx
0x180010aee  sub     r9, 1
0x180010af2  jnz     short loc_180010AD2
0x180010af4  test    r9, r9
0x180010af7  lea     rcx, [rax-2]
0x180010afb  cmovnz  rcx, rax
0x180010aff  mov     rax, [rsp+38h+arg_10]
0x180010b04  mov     [rcx], bp
0x180010b07  test    rax, rax
0x180010b0a  jz      short loc_180010B11
0x180010b0c  mov     ecx, ebp
0x180010b0e  xchg    ecx, [rax+30h]
0x180010b11  xor     eax, eax
0x180010b13  mov     rbx, [rsp+38h+arg_0]
0x180010b18  add     rsp, 20h
0x180010b1c  pop     rdi
0x180010b1d  pop     rsi
0x180010b1e  pop     rbp
0x180010b1f  retn
```
