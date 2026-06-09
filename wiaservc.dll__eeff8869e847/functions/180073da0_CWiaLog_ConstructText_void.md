# CWiaLog::ConstructText(void)

- ea: `0x180073da0`
- end: `0x180074126`
- name: `?ConstructText@CWiaLog@@AEAAXXZ`
- size: `902`
- prototype: `void __fastcall(CWiaLog *__hidden this)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180074230`
- `0x180074b80`
- `0x180074c0c`
- `0x180074f00`
- `0x180075020`

## callees

- `0x18000f4fc`
- `0x180010d78`
- `0x180011a94`
- `0x180015a34`
- `0x180016e88`
- `0x180033cc0`
- `0x18003b75c`
- `0x18003c4d8`
- `0x180073da0`
- `0x180074db0`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x180073f56`
- `KERNEL32!GetLocalTime` at `0x180073f56`
- `KERNEL32!GetCurrentThreadId` at `0x180073e70`
- `KERNEL32!GetCurrentThreadId` at `0x180073e70`

## string_xrefs

- `0x180073e9b`: `[ Thread ] `

## pseudocode

```c
void __fastcall CWiaLog::ConstructText(CWiaLog *this)
{
  bool v2; // zf
  DWORD CurrentThreadId; // eax
  int v4; // eax
  int v5; // ebx
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int wMinute; // [rsp+20h] [rbp-E0h]
  int wSecond; // [rsp+28h] [rbp-D8h]
  int wMilliseconds; // [rsp+30h] [rbp-D0h]
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int64 *v15; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v16; // [rsp+58h] [rbp-A8h] BYREF
  __int16 *v17; // [rsp+158h] [rbp+58h]
  __int64 v18; // [rsp+160h] [rbp+60h]
  __int64 v19; // [rsp+168h] [rbp+68h]
  char v20; // [rsp+170h] [rbp+70h]
  _QWORD v21[38]; // [rsp+180h] [rbp+80h] BYREF
  const unsigned __int64 *v22; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int16 v23; // [rsp+2B8h] [rbp+1B8h] BYREF
  unsigned __int16 *v24; // [rsp+3B8h] [rbp+2B8h]
  __int64 v25; // [rsp+3C0h] [rbp+2C0h]
  __int64 v26; // [rsp+3C8h] [rbp+2C8h]
  char v27; // [rsp+3D0h] [rbp+2D0h]
  const unsigned __int64 *v28; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int16 v29; // [rsp+3E8h] [rbp+2E8h] BYREF
  unsigned __int16 *v30; // [rsp+4E8h] [rbp+3E8h]
  __int64 v31; // [rsp+4F0h] [rbp+3F0h]
  __int64 v32; // [rsp+4F8h] [rbp+3F8h]
  char v33; // [rsp+500h] [rbp+400h]
  unsigned __int16 v34[40]; // [rsp+510h] [rbp+410h] BYREF

  v33 = 0;
  v31 = 128;
  v30 = (unsigned __int16 *)&v29;
  v28 = &CSimpleStringBase<unsigned short>::`vftable';
  v29 = 0;
  v15 = &CSimpleStringBase<unsigned short>::`vftable';
  v17 = &v16;
  v32 = 16;
  v16 = 0;
  v24 = (unsigned __int16 *)&v23;
  v2 = (*((_DWORD *)this + 8) & 0x40000) == 0;
  v18 = 128;
  v19 = 16;
  v20 = 0;
  v22 = &CSimpleStringBase<unsigned short>::`vftable';
  v25 = 128;
  v26 = 16;
  v27 = 0;
  v23 = 0;
  if ( !v2 )
  {
    CurrentThreadId = GetCurrentThreadId();
    CSimpleStringBase<unsigned short>::Format(&v15, L"[%08X] ", CurrentThreadId);
    CSimpleStringBase<unsigned short>::operator+=(&v22, &v15);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v21, L"[ Thread ] ");
    CSimpleStringBase<unsigned short>::operator+=(&v28, v21);
    v21[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v21);
  }
  if ( (*((_DWORD *)this + 8) & 0x20000) != 0 )
  {
    CSimpleStringBase<unsigned short>::Format(&v15, L"%s ", (char *)this + 56);
    CSimpleStringBase<unsigned short>::operator+=(&v22, &v15);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v21, L"[  Module  ] ");
    CSimpleStringBase<unsigned short>::operator+=(&v28, v21);
    v21[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v21);
  }
  if ( (*((_DWORD *)this + 8) & 0x10000) != 0 )
  {
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    wMilliseconds = SystemTime.wMilliseconds;
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    StringCchPrintfW(v34, 0x28u, L"%02d:%02d:%02d.%03d", SystemTime.wHour, wMinute, wSecond, wMilliseconds);
    CSimpleStringBase<unsigned short>::Format(&v15, L"  %s ", v34);
    CSimpleStringBase<unsigned short>::operator+=(&v22, &v15);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v21, L"[ HH:MM:SS.ms ] ");
    CSimpleStringBase<unsigned short>::operator+=(&v28, v21);
    v21[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v21);
  }
  StringCchCopyW((unsigned __int16 *)this + 424, 0x208u, v24);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v21, (char *)this + 2408);
  v4 = CSimpleStringBase<unsigned short>::Compare((__int64)&v28, (__int64)v21);
  v21[0] = &CSimpleStringBase<unsigned short>::`vftable';
  v5 = v4;
  CSimpleStringBase<unsigned short>::DeleteStorage(v21);
  if ( v5 )
  {
    StringCchCopyW((unsigned __int16 *)this + 1204, 0x104u, v30);
    *((_WORD *)this + 1463) = 0;
    CWiaLog::WriteStringToLog(this, L" ", v6);
    CWiaLog::WriteStringToLog(
      this,
      L"=============================================================================",
      v7);
    CWiaLog::WriteStringToLog(this, (unsigned __int16 *)this + 1204, v8);
    CWiaLog::WriteStringToLog(
      this,
      L"=============================================================================",
      v9);
    CWiaLog::WriteStringToLog(this, L" ", v10);
  }
  v22 = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(&v22);
  v25 = 0;
  v15 = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(&v15);
  v18 = 0;
  v28 = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(&v28);
}

```

## disassembly

```asm
0x180073da0  mov     [rsp-8+arg_8], rbx
0x180073da5  mov     [rsp-8+arg_10], rsi
0x180073daa  push    rbp
0x180073dab  push    rdi
0x180073dac  push    r14
0x180073dae  lea     rbp, [rsp-470h]
0x180073db6  sub     rsp, 570h
0x180073dbd  mov     rax, cs:__security_cookie
0x180073dc4  xor     rax, rsp
0x180073dc7  mov     [rbp+480h+var_20], rax
0x180073dce  mov     edx, 80h
0x180073dd3  mov     [rbp+480h+var_80], 0
0x180073dda  lea     rax, [rbp+480h+var_198]
0x180073de1  mov     [rbp+480h+var_90], rdx
0x180073de8  mov     [rbp+480h+var_98], rax
0x180073def  lea     r14, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180073df6  xor     eax, eax
0x180073df8  mov     [rbp+480h+var_1A0], r14
0x180073dff  mov     [rbp+480h+var_198], ax
0x180073e06  mov     rdi, rcx
0x180073e09  lea     rax, [rsp+580h+var_528]
0x180073e0e  mov     [rsp+580h+var_530], r14
0x180073e13  mov     [rbp+480h+var_428], rax
0x180073e17  lea     ecx, [rdx-70h]
0x180073e1a  xor     eax, eax
0x180073e1c  mov     [rbp+480h+var_88], rcx
0x180073e23  mov     [rsp+580h+var_528], ax
0x180073e28  lea     rax, [rbp+480h+var_2C8]
0x180073e2f  mov     [rbp+480h+var_1C8], rax
0x180073e36  xor     eax, eax
0x180073e38  test    dword ptr [rdi+20h], 40000h
0x180073e3f  mov     [rbp+480h+var_420], rdx
0x180073e43  mov     [rbp+480h+var_418], rcx
0x180073e47  mov     [rbp+480h+var_410], 0
0x180073e4b  mov     [rbp+480h+var_2D0], r14
0x180073e52  mov     [rbp+480h+var_1C0], rdx
0x180073e59  mov     [rbp+480h+var_1B8], rcx
0x180073e60  mov     [rbp+480h+var_1B0], 0
0x180073e67  mov     [rbp+480h+var_2C8], ax
0x180073e6e  jz      short loc_180073ED4
0x180073e70  call    cs:__imp_GetCurrentThreadId
0x180073e76  mov     r8d, eax
0x180073e79  lea     rdx, a08x; "[%08X] "
0x180073e80  lea     rcx, [rsp+580h+var_530]
0x180073e85  call    ?Format@?$CSimpleStringBase@G@@QEAAAEAV1@PEBGZZ; CSimpleStringBase<ushort>::Format(ushort const *,...)
0x180073e8a  lea     rdx, [rsp+580h+var_530]
0x180073e8f  lea     rcx, [rbp+480h+var_2D0]
0x180073e96  call    ??Y?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator+=(CSimpleStringBase<ushort> const &)
0x180073e9b  lea     rdx, aThread; "[ Thread ] "
0x180073ea2  lea     rcx, [rbp+480h+var_400]
0x180073ea9  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180073eae  lea     rdx, [rbp+480h+var_400]
0x180073eb5  lea     rcx, [rbp+480h+var_1A0]
0x180073ebc  call    ??Y?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator+=(CSimpleStringBase<ushort> const &)
0x180073ec1  lea     rcx, [rbp+480h+var_400]
0x180073ec8  mov     [rbp+480h+var_400], r14
0x180073ecf  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180073ed4  test    dword ptr [rdi+20h], 20000h
0x180073edb  jz      short loc_180073F3C
0x180073edd  lea     r8, [rdi+38h]
0x180073ee1  lea     rdx, aS_1; "%s "
0x180073ee8  lea     rcx, [rsp+580h+var_530]
0x180073eed  call    ?Format@?$CSimpleStringBase@G@@QEAAAEAV1@PEBGZZ; CSimpleStringBase<ushort>::Format(ushort const *,...)
0x180073ef2  lea     rdx, [rsp+580h+var_530]
0x180073ef7  lea     rcx, [rbp+480h+var_2D0]
0x180073efe  call    ??Y?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator+=(CSimpleStringBase<ushort> const &)
0x180073f03  lea     rdx, aModule; "[  Module  ] "
0x180073f0a  lea     rcx, [rbp+480h+var_400]
0x180073f11  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180073f16  lea     rdx, [rbp+480h+var_400]
0x180073f1d  lea     rcx, [rbp+480h+var_1A0]
0x180073f24  call    ??Y?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator+=(CSimpleStringBase<ushort> const &)
0x180073f29  lea     rcx, [rbp+480h+var_400]
0x180073f30  mov     [rbp+480h+var_400], r14
0x180073f37  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180073f3c  test    dword ptr [rdi+20h], 10000h
0x180073f43  jz      loc_180073FF7
0x180073f49  xorps   xmm0, xmm0
0x180073f4c  lea     rcx, [rsp+580h+SystemTime]; lpSystemTime
0x180073f51  movups  xmmword ptr [rsp+580h+SystemTime.wYear], xmm0
0x180073f56  call    cs:__imp_GetLocalTime
0x180073f5c  movzx   ecx, [rsp+580h+SystemTime.wSecond]
0x180073f61  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x180073f68  movzx   edx, [rsp+580h+SystemTime.wMinute]
0x180073f6d  movzx   eax, [rsp+580h+SystemTime.wMilliseconds]
0x180073f72  movzx   r9d, [rsp+580h+SystemTime.wHour]
0x180073f78  mov     [rsp+580h+var_550], eax
0x180073f7c  mov     [rsp+580h+var_558], ecx
0x180073f80  lea     rcx, [rbp+480h+var_70]; unsigned __int16 *
0x180073f87  mov     [rsp+580h+var_560], edx
0x180073f8b  mov     edx, 28h ; '('; unsigned __int64
0x180073f90  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180073f95  lea     r8, [rbp+480h+var_70]
0x180073f9c  lea     rdx, aS; "  %s "
0x180073fa3  lea     rcx, [rsp+580h+var_530]
0x180073fa8  call    ?Format@?$CSimpleStringBase@G@@QEAAAEAV1@PEBGZZ; CSimpleStringBase<ushort>::Format(ushort const *,...)
0x180073fad  lea     rdx, [rsp+580h+var_530]
0x180073fb2  lea     rcx, [rbp+480h+var_2D0]
0x180073fb9  call    ??Y?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator+=(CSimpleStringBase<ushort> const &)
0x180073fbe  lea     rdx, aHhMmSsMs; "[ HH:MM:SS.ms ] "
0x180073fc5  lea     rcx, [rbp+480h+var_400]
0x180073fcc  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180073fd1  lea     rdx, [rbp+480h+var_400]
0x180073fd8  lea     rcx, [rbp+480h+var_1A0]
0x180073fdf  call    ??Y?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator+=(CSimpleStringBase<ushort> const &)
0x180073fe4  lea     rcx, [rbp+480h+var_400]
0x180073feb  mov     [rbp+480h+var_400], r14
0x180073ff2  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180073ff7  mov     r8, [rbp+480h+var_1C8]; unsigned __int16 *
0x180073ffe  lea     rcx, [rdi+350h]; unsigned __int16 *
0x180074005  mov     edx, 208h; unsigned __int64
0x18007400a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007400f  lea     rsi, [rdi+968h]
0x180074016  mov     rdx, rsi
0x180074019  lea     rcx, [rbp+480h+var_400]
0x180074020  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180074025  lea     rdx, [rbp+480h+var_400]
0x18007402c  lea     rcx, [rbp+480h+var_1A0]
0x180074033  call    ?Compare@?$CSimpleStringBase@G@@QEBAHAEBV1@H@Z; CSimpleStringBase<ushort>::Compare(CSimpleStringBase<ushort> const &,int)
0x180074038  lea     rcx, [rbp+480h+var_400]
0x18007403f  mov     [rbp+480h+var_400], r14
0x180074046  mov     ebx, eax
0x180074048  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18007404d  test    ebx, ebx
0x18007404f  jz      short loc_1800740B7
0x180074051  mov     r8, [rbp+480h+var_98]; unsigned __int16 *
0x180074058  mov     edx, 104h; unsigned __int64
0x18007405d  mov     rcx, rsi; unsigned __int16 *
0x180074060  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180074065  xor     r11d, r11d
0x180074068  lea     rdx, asc_1800A15CC; " "
0x18007406f  mov     rcx, rdi; this
0x180074072  mov     [rdi+0B6Eh], r11w
0x18007407a  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x18007407f  lea     rdx, asc_1800A1530; "======================================="...
0x180074086  mov     rcx, rdi; this
0x180074089  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x18007408e  mov     rdx, rsi; unsigned __int16 *
0x180074091  mov     rcx, rdi; this
0x180074094  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x180074099  lea     rdx, asc_1800A1530; "======================================="...
0x1800740a0  mov     rcx, rdi; this
0x1800740a3  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x1800740a8  lea     rdx, asc_1800A15CC; " "
0x1800740af  mov     rcx, rdi; this
0x1800740b2  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x1800740b7  lea     rcx, [rbp+480h+var_2D0]
0x1800740be  mov     [rbp+480h+var_2D0], r14
0x1800740c5  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800740ca  lea     rcx, [rsp+580h+var_530]
0x1800740cf  mov     [rbp+480h+var_1C0], 0
0x1800740da  mov     [rsp+580h+var_530], r14
0x1800740df  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800740e4  lea     rcx, [rbp+480h+var_1A0]
0x1800740eb  mov     [rbp+480h+var_420], 0
0x1800740f3  mov     [rbp+480h+var_1A0], r14
0x1800740fa  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800740ff  mov     rcx, [rbp+480h+var_20]
0x180074106  xor     rcx, rsp; StackCookie
0x180074109  call    __security_check_cookie
0x18007410e  lea     r11, [rsp+580h+var_10]
0x180074116  mov     rbx, [r11+28h]
0x18007411a  mov     rsi, [r11+30h]
0x18007411e  mov     rsp, r11
0x180074121  pop     r14
0x180074123  pop     rdi
0x180074124  pop     rbp
0x180074125  retn
```
