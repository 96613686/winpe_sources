# PrintPdhCounterTableData(_iobuf *,_PDH_COUNTER_PATH_ELEMENTS_W *,ushort *,_PDH_STATISTICS,ulong,int,int,int,int,int,int)

- ea: `0x14001f4ac`
- end: `0x14001f7d2`
- name: `?PrintPdhCounterTableData@@YAXPEAU_iobuf@@PEAU_PDH_COUNTER_PATH_ELEMENTS_W@@PEAGU_PDH_STATISTICS@@KHHHHHH@Z`
- size: `806`
- prototype: `void __fastcall(struct _iobuf *, struct _PDH_COUNTER_PATH_ELEMENTS_W *, unsigned __int16 *, struct _PDH_STATISTICS *, unsigned int, int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14001f8d8`
- `0x14002ac00`

## callees

- `0x140009c78`
- `0x140013a04`
- `0x140016360`
- `0x1400164c4`
- `0x14001f4ac`
- `0x140040130`

## pseudocode

```c
void __fastcall PrintPdhCounterTableData(
        struct _iobuf *a1,
        struct _PDH_COUNTER_PATH_ELEMENTS_W *a2,
        unsigned __int16 *a3,
        struct _PDH_STATISTICS *a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11)
{
  unsigned __int16 *v14; // rsi
  double v15; // xmm6_8
  double doubleValue; // xmm9_8
  double v17; // xmm8_8
  unsigned __int16 *szParentInstance; // r9
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  unsigned __int16 v22[32]; // [rsp+20h] [rbp-B8h] BYREF

  v14 = 0;
  v15 = 0.0;
  if ( a4->max.CStatus )
    doubleValue = 0.0;
  else
    doubleValue = a4->max.doubleValue;
  if ( a4->mean.CStatus )
    v17 = 0.0;
  else
    v17 = a4->mean.doubleValue;
  if ( !a4->min.CStatus )
    v15 = a4->min.doubleValue;
  if ( a2->dwInstanceIndex - 1 <= 0xFFFFFFFD )
  {
    if ( (int)StringCchPrintfW(v22, 0x20u, L"#%d") < 0 )
      return;
    v14 = v22;
  }
  TracerptFPutws(L"\t<Item>\r\n", a1);
  if ( a6 )
  {
    TracerptFPutws(L"\t\t<Data name='displayName'>", a1);
    PrintWString(a1, 1u, 0, a3);
    TracerptFPutws(L"</Data>\r\n", a1);
    TracerptFPutws(L"\t\t<Data name='counter' visible='false'>", a1);
    PrintWString(a1, 1u, 0, a2->szCounterName);
    TracerptFPutws(L"</Data>\r\n", a1);
  }
  if ( a7 && a2->szInstanceName )
  {
    TracerptFPutws(L"\t\t<Data name='instance'>", a1);
    szParentInstance = a2->szParentInstance;
    if ( szParentInstance )
    {
      PrintWString(a1, 1u, 0, szParentInstance);
      TracerptFPutws(L"/", a1);
    }
    PrintWString(a1, 1u, 0, a2->szInstanceName);
    if ( v14 )
    {
      TracerptFPutws(L"#", a1);
      PrintWString(a1, 1u, 0, v14);
    }
    TracerptFPutws(L"</Data>\r\n", a1);
  }
  if ( a8 && a2->szMachineName )
  {
    TracerptFPutws(L"\t\t<Data name='machine'>", a1);
    PrintWString(a1, 1u, 0, a2->szMachineName);
    TracerptFPutws(L"</Data>\r\n", a1);
  }
  if ( (a5 & 0xFFFFFEFF) != 0 )
  {
    if ( a9 )
    {
      v19 = 0;
      if ( v17 < 1.1 )
        v19 = 3;
      TracerptFWPrintf(a1, L"\t\t<Data name='mean'>%1.*f</Data>\r\n", v19, v17);
    }
    if ( a10 )
    {
      v20 = 0;
      if ( v15 < 1.1 )
        v20 = 3;
      TracerptFWPrintf(a1, L"\t\t<Data name='min' >%1.*f</Data>\r\n", v20, v15);
    }
    if ( a11 )
    {
      v21 = 0;
      if ( doubleValue < 1.1 )
        v21 = 3;
      TracerptFWPrintf(a1, L"\t\t<Data name='max' >%1.*f</Data>\r\n", v21, doubleValue);
    }
  }
  else
  {
    if ( a9 )
      TracerptFWPrintf(a1, L"\t\t<Data name='mean'>%x</Data>\r\n", (unsigned int)(int)v17);
    if ( a10 )
      TracerptFWPrintf(a1, L"\t\t<Data name='min'>%x</Data>\r\n", (unsigned int)(int)v15);
    if ( a11 )
      TracerptFWPrintf(a1, L"\t\t<Data name='max'>%x</Data>\r\n", (unsigned int)(int)doubleValue);
  }
  TracerptFPutws(L"</Item>\r\n", a1);
}

```

## disassembly

```asm
0x14001f4ac  mov     rax, rsp
0x14001f4af  push    rbx
0x14001f4b0  push    rbp
0x14001f4b1  push    rsi
0x14001f4b2  push    rdi
0x14001f4b3  push    r14
0x14001f4b5  sub     rsp, 0B0h
0x14001f4bc  movaps  xmmword ptr [rax-38h], xmm6
0x14001f4c0  movaps  xmmword ptr [rax-48h], xmm7
0x14001f4c4  movaps  xmmword ptr [rax-58h], xmm8
0x14001f4c9  movaps  xmmword ptr [rax-68h], xmm9
0x14001f4ce  mov     rax, cs:__security_cookie
0x14001f4d5  xor     rax, rsp
0x14001f4d8  mov     [rsp+0D8h+var_78], rax
0x14001f4dd  xor     r14d, r14d
0x14001f4e0  mov     rbp, r8
0x14001f4e3  mov     rdi, rdx
0x14001f4e6  mov     rbx, rcx
0x14001f4e9  mov     esi, r14d
0x14001f4ec  xorps   xmm6, xmm6
0x14001f4ef  cmp     [r9+18h], r14d
0x14001f4f3  jnz     short loc_14001F4FD
0x14001f4f5  movsd   xmm9, qword ptr [r9+20h]
0x14001f4fb  jmp     short loc_14001F501
0x14001f4fd  xorps   xmm9, xmm9
0x14001f501  cmp     [r9+28h], r14d
0x14001f505  jnz     short loc_14001F50F
0x14001f507  movsd   xmm8, qword ptr [r9+30h]
0x14001f50d  jmp     short loc_14001F513
0x14001f50f  xorps   xmm8, xmm8
0x14001f513  cmp     [r9+8], r14d
0x14001f517  jnz     short loc_14001F51F
0x14001f519  movsd   xmm6, qword ptr [r9+10h]
0x14001f51f  mov     r9d, [rdx+20h]
0x14001f523  lea     eax, [r9-1]
0x14001f527  cmp     eax, 0FFFFFFFDh
0x14001f52a  ja      short loc_14001F54F
0x14001f52c  lea     r8, aD_5; "#%d"
0x14001f533  mov     edx, 20h ; ' '; unsigned __int64
0x14001f538  lea     rcx, [rsp+0D8h+var_B8]; unsigned __int16 *
0x14001f53d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001f542  test    eax, eax
0x14001f544  js      loc_14001F79F
0x14001f54a  lea     rsi, [rsp+0D8h+var_B8]
0x14001f54f  mov     rdx, rbx; struct _iobuf *
0x14001f552  lea     rcx, aItem_0; "\t<Item>\r\n"
0x14001f559  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f55e  cmp     [rsp+0D8h+arg_28], r14d
0x14001f566  jz      short loc_14001F5C5
0x14001f568  mov     rdx, rbx; struct _iobuf *
0x14001f56b  lea     rcx, aDataNameDispla; "\t\t<Data name='displayName'>"
0x14001f572  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f577  mov     r9, rbp; unsigned __int16 *
0x14001f57a  xor     r8d, r8d; unsigned __int8
0x14001f57d  mov     dl, 1; unsigned __int8
0x14001f57f  mov     rcx, rbx; struct _iobuf *
0x14001f582  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14001f587  mov     rdx, rbx; struct _iobuf *
0x14001f58a  lea     rcx, aData; "</Data>\r\n"
0x14001f591  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f596  mov     rdx, rbx; struct _iobuf *
0x14001f599  lea     rcx, aDataNameCounte_0; "\t\t<Data name='counter' visible='false"...
0x14001f5a0  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f5a5  mov     r9, [rdi+28h]; unsigned __int16 *
0x14001f5a9  xor     r8d, r8d; unsigned __int8
0x14001f5ac  mov     dl, 1; unsigned __int8
0x14001f5ae  mov     rcx, rbx; struct _iobuf *
0x14001f5b1  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14001f5b6  mov     rdx, rbx; struct _iobuf *
0x14001f5b9  lea     rcx, aData; "</Data>\r\n"
0x14001f5c0  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f5c5  cmp     [rsp+0D8h+arg_30], r14d
0x14001f5cd  jz      short loc_14001F64D
0x14001f5cf  cmp     [rdi+10h], r14
0x14001f5d3  jz      short loc_14001F64D
0x14001f5d5  mov     rdx, rbx; struct _iobuf *
0x14001f5d8  lea     rcx, aDataNameInstan_0; "\t\t<Data name='instance'>"
0x14001f5df  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f5e4  mov     r9, [rdi+18h]; unsigned __int16 *
0x14001f5e8  test    r9, r9
0x14001f5eb  jz      short loc_14001F609
0x14001f5ed  xor     r8d, r8d; unsigned __int8
0x14001f5f0  mov     dl, 1; unsigned __int8
0x14001f5f2  mov     rcx, rbx; struct _iobuf *
0x14001f5f5  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14001f5fa  mov     rdx, rbx; struct _iobuf *
0x14001f5fd  lea     rcx, asc_140043194; "/"
0x14001f604  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f609  mov     r9, [rdi+10h]; unsigned __int16 *
0x14001f60d  xor     r8d, r8d; unsigned __int8
0x14001f610  mov     dl, 1; unsigned __int8
0x14001f612  mov     rcx, rbx; struct _iobuf *
0x14001f615  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14001f61a  test    rsi, rsi
0x14001f61d  jz      short loc_14001F63E
0x14001f61f  mov     rdx, rbx; struct _iobuf *
0x14001f622  lea     rcx, asc_14004A9C4; "#"
0x14001f629  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f62e  mov     r9, rsi; unsigned __int16 *
0x14001f631  xor     r8d, r8d; unsigned __int8
0x14001f634  mov     dl, 1; unsigned __int8
0x14001f636  mov     rcx, rbx; struct _iobuf *
0x14001f639  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14001f63e  mov     rdx, rbx; struct _iobuf *
0x14001f641  lea     rcx, aData; "</Data>\r\n"
0x14001f648  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f64d  cmp     [rsp+0D8h+arg_38], r14d
0x14001f655  jz      short loc_14001F68A
0x14001f657  cmp     [rdi], r14
0x14001f65a  jz      short loc_14001F68A
0x14001f65c  mov     rdx, rbx; struct _iobuf *
0x14001f65f  lea     rcx, aDataNameMachin_0; "\t\t<Data name='machine'>"
0x14001f666  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f66b  mov     r9, [rdi]; unsigned __int16 *
0x14001f66e  xor     r8d, r8d; unsigned __int8
0x14001f671  mov     dl, 1; unsigned __int8
0x14001f673  mov     rcx, rbx; struct _iobuf *
0x14001f676  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14001f67b  mov     rdx, rbx; struct _iobuf *
0x14001f67e  lea     rcx, aData; "</Data>\r\n"
0x14001f685  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f68a  test    [rsp+0D8h+arg_20], 0FFFFFEFFh
0x14001f695  jz      loc_14001F736
0x14001f69b  mov     edi, 3
0x14001f6a0  movsd   xmm7, cs:__real@3ff199999999999a
0x14001f6a8  cmp     [rsp+0D8h+arg_40], r14d
0x14001f6b0  jz      short loc_14001F6D6
0x14001f6b2  comisd  xmm7, xmm8
0x14001f6b7  mov     r8d, r14d
0x14001f6ba  lea     rdx, aDataNameMean1F; "\t\t<Data name='mean'>%1.*f</Data>\r\n"
0x14001f6c1  mov     rcx, rbx; struct _iobuf *
0x14001f6c4  movaps  xmm3, xmm8
0x14001f6c8  movq    r9, xmm3
0x14001f6cd  cmova   r8d, edi
0x14001f6d1  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001f6d6  cmp     [rsp+0D8h+arg_48], r14d
0x14001f6de  jz      short loc_14001F702
0x14001f6e0  comisd  xmm7, xmm6
0x14001f6e4  mov     r8d, r14d
0x14001f6e7  lea     rdx, aDataNameMin1FD; "\t\t<Data name='min' >%1.*f</Data>\r\n"
0x14001f6ee  mov     rcx, rbx; struct _iobuf *
0x14001f6f1  movaps  xmm3, xmm6
0x14001f6f4  movq    r9, xmm6
0x14001f6f9  cmova   r8d, edi
0x14001f6fd  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001f702  cmp     [rsp+0D8h+arg_50], r14d
0x14001f70a  jz      loc_14001F790
0x14001f710  comisd  xmm7, xmm9
0x14001f715  mov     r8d, r14d
0x14001f718  lea     rdx, aDataNameMax1FD; "\t\t<Data name='max' >%1.*f</Data>\r\n"
0x14001f71f  mov     rcx, rbx; struct _iobuf *
0x14001f722  movaps  xmm3, xmm9
0x14001f726  movq    r9, xmm3
0x14001f72b  cmova   r8d, edi
0x14001f72f  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001f734  jmp     short loc_14001F790
0x14001f736  cmp     [rsp+0D8h+arg_40], r14d
0x14001f73e  jz      short loc_14001F754
0x14001f740  cvttsd2si r8d, xmm8
0x14001f745  lea     rdx, aDataNameMeanXD; "\t\t<Data name='mean'>%x</Data>\r\n"
0x14001f74c  mov     rcx, rbx; struct _iobuf *
0x14001f74f  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001f754  cmp     [rsp+0D8h+arg_48], r14d
0x14001f75c  jz      short loc_14001F772
0x14001f75e  cvttsd2si r8d, xmm6
0x14001f763  lea     rdx, aDataNameMinXDa; "\t\t<Data name='min'>%x</Data>\r\n"
0x14001f76a  mov     rcx, rbx; struct _iobuf *
0x14001f76d  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001f772  cmp     [rsp+0D8h+arg_50], r14d
0x14001f77a  jz      short loc_14001F790
0x14001f77c  cvttsd2si r8d, xmm9
0x14001f781  lea     rdx, aDataNameMaxXDa; "\t\t<Data name='max'>%x</Data>\r\n"
0x14001f788  mov     rcx, rbx; struct _iobuf *
0x14001f78b  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001f790  mov     rdx, rbx; struct _iobuf *
0x14001f793  lea     rcx, aItem_2; "</Item>\r\n"
0x14001f79a  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001f79f  mov     rcx, [rsp+0D8h+var_78]
0x14001f7a4  xor     rcx, rsp; StackCookie
0x14001f7a7  call    __security_check_cookie
0x14001f7ac  lea     r11, [rsp+0D8h+var_28]
0x14001f7b4  movaps  xmm6, xmmword ptr [r11-10h]
0x14001f7b9  movaps  xmm7, xmmword ptr [r11-20h]
0x14001f7be  movaps  xmm8, xmmword ptr [r11-30h]
0x14001f7c3  movaps  xmm9, xmmword ptr [r11-40h]
0x14001f7c8  mov     rsp, r11
0x14001f7cb  pop     r14
0x14001f7cd  pop     rdi
0x14001f7ce  pop     rsi
0x14001f7cf  pop     rbp
0x14001f7d0  pop     rbx
0x14001f7d1  retn
```
