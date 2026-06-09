# Reporter::AddTimeToReport(IXMLDOMElement *,IXMLDOMDocument2 *)

- ea: `0x18002114c`
- end: `0x180021463`
- name: `?AddTimeToReport@Reporter@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMDocument2@@@Z`
- size: `791`
- prototype: `__int64 __fastcall(Reporter *this, struct IXMLDOMElement *, struct IXMLDOMDocument2 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180021ec4`
- `0x180022174`

## callees

- `0x1800012a4`
- `0x180005ffc`
- `0x180010e70`
- `0x18001e6c0`
- `0x18002114c`
- `0x180026fa0`
- `0x18002827c`
- `0x1800291e0`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetTimeFormatEx` at `0x1800212ed`
- `KERNEL32!GetTimeFormatEx` at `0x1800212ed`
- `KERNEL32!GetLastError` at `0x180021248`
- `KERNEL32!GetLastError` at `0x1800212fa`
- `KERNEL32!GetLastError` at `0x180021248`
- `KERNEL32!GetLastError` at `0x1800212fa`
- `KERNEL32!GetDateFormatEx` at `0x18002123e`
- `KERNEL32!GetDateFormatEx` at `0x18002123e`
- `KERNEL32!GetLocalTime` at `0x18002120d`
- `KERNEL32!GetLocalTime` at `0x18002120d`

## pseudocode

```c
__int64 __fastcall Reporter::AddTimeToReport(Reporter *this, struct IXMLDOMElement *a2, struct IXMLDOMDocument2 *a3)
{
  unsigned __int16 *v5; // rsi
  struct IXMLDOMElement *v6; // rdi
  int v7; // r8d
  int v8; // r9d
  signed int v9; // ebx
  Settings *v10; // rcx
  int Locale; // eax
  int v12; // r8d
  signed int LastError; // eax
  int v14; // r9d
  int v15; // eax
  __int64 v16; // rax
  signed int v17; // eax
  int v18; // eax
  int v19; // eax
  LPCWSTR lpLocaleName; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMElement *v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v23; // [rsp+50h] [rbp-B0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR DateStr[1024]; // [rsp+70h] [rbp-90h] BYREF

  lpLocaleName = 0;
  v23 = 0;
  v22 = 0;
  v5 = 0;
  v6 = 0;
  SystemTime = 0;
  if ( !a2 )
  {
    v7 = 661;
LABEL_3:
    v8 = -2147024809;
    v9 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"Reporter::AddTimeToReport", v7, v8);
    return (unsigned int)v9;
  }
  if ( !a3 )
  {
    v7 = 662;
    goto LABEL_3;
  }
  v10 = (Settings *)*((_QWORD *)this + 6);
  if ( !v10 )
  {
    v9 = -2147467261;
    v7 = 664;
    v8 = -2147467261;
    goto LABEL_4;
  }
  Locale = Settings::get_Locale(v10, (unsigned __int16 **)&lpLocaleName);
  v9 = Locale;
  if ( Locale < 0 )
  {
    v12 = 666;
LABEL_35:
    v14 = Locale;
LABEL_36:
    SdpDebugTrace(1u, L"Reporter::AddTimeToReport", v12, v14);
    goto LABEL_37;
  }
  GetLocalTime(&SystemTime);
  if ( !GetDateFormatEx(lpLocaleName, 2u, &SystemTime, 0, DateStr, 1024, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v12 = 690;
    if ( v9 >= 0 )
      v9 = -2147467259;
    v14 = v9;
    goto LABEL_36;
  }
  v15 = StringCchCatW(DateStr, 0x400u, L" ");
  v9 = v15;
  if ( v15 >= 0 )
  {
    v16 = -1;
    do
      ++v16;
    while ( DateStr[v16] );
    if ( !GetTimeFormatEx(lpLocaleName, 0, &SystemTime, 0, &DateStr[v16], 1024 - v16) )
    {
      v17 = GetLastError();
      v9 = v17;
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
      v12 = 700;
      if ( v9 >= 0 )
        v9 = -2147467259;
      v14 = v9;
      goto LABEL_36;
    }
    v18 = SdpXmlCreateNode(a3, a2, L"Data", DateStr, &v22);
    v9 = v18;
    if ( v18 >= 0 )
    {
      v6 = v22;
      Locale = SdpXmlSetAttribute(0, v22, L"id", L"Time");
      v9 = Locale;
      if ( Locale < 0 )
      {
        v12 = 721;
        goto LABEL_35;
      }
      v19 = SdpLoadString(0, 0x73u, &v23);
      v9 = v19;
      if ( v19 >= 0 )
      {
        v5 = v23;
        Locale = SdpXmlSetAttribute(0, v6, L"name", v23);
        v9 = Locale;
        if ( Locale < 0 )
        {
          v12 = 727;
          goto LABEL_35;
        }
      }
      else
      {
        SdpDebugTrace(1u, L"Reporter::AddTimeToReport", 724, v19);
        v5 = v23;
      }
    }
    else
    {
      SdpDebugTrace(1u, L"Reporter::AddTimeToReport", 715, v18);
      v6 = v22;
    }
  }
  else
  {
    SdpDebugTrace(1u, L"Reporter::AddTimeToReport", 693, v15);
  }
LABEL_37:
  if ( lpLocaleName )
    operator delete((void *)lpLocaleName);
  if ( v5 )
    operator delete(v5);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002114c  push    rbp
0x18002114e  push    rbx
0x18002114f  push    rsi
0x180021150  push    rdi
0x180021151  push    r12
0x180021153  push    r13
0x180021155  push    r14
0x180021157  lea     rbp, [rsp-780h]
0x18002115f  sub     rsp, 880h
0x180021166  mov     rax, cs:__security_cookie
0x18002116d  xor     rax, rsp
0x180021170  mov     [rbp+7B0h+var_40], rax
0x180021177  xor     r14d, r14d
0x18002117a  xorps   xmm0, xmm0
0x18002117d  mov     [rsp+8B0h+lpLocaleName], r14
0x180021182  mov     r12, r8
0x180021185  mov     [rsp+8B0h+var_860], r14
0x18002118a  mov     r13, rdx
0x18002118d  mov     [rsp+8B0h+var_868], r14
0x180021192  mov     esi, r14d
0x180021195  mov     edi, r14d
0x180021198  movups  xmmword ptr [rsp+8B0h+SystemTime.wYear], xmm0
0x18002119d  test    rdx, rdx
0x1800211a0  jnz     short loc_1800211C7
0x1800211a2  mov     r8d, 295h; int
0x1800211a8  mov     r9d, 80070057h; int
0x1800211ae  mov     ebx, r9d
0x1800211b1  lea     rdx, aReporterAddtim; "Reporter::AddTimeToReport"
0x1800211b8  mov     ecx, 1; Level
0x1800211bd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800211c2  jmp     loc_180021440
0x1800211c7  test    r12, r12
0x1800211ca  jnz     short loc_1800211D4
0x1800211cc  mov     r8d, 296h
0x1800211d2  jmp     short loc_1800211A8
0x1800211d4  mov     rcx, [rcx+30h]; this
0x1800211d8  test    rcx, rcx
0x1800211db  jnz     short loc_1800211ED
0x1800211dd  mov     ebx, 80004003h
0x1800211e2  mov     r8d, 298h
0x1800211e8  mov     r9d, ebx
0x1800211eb  jmp     short loc_1800211B1
0x1800211ed  lea     rdx, [rsp+8B0h+lpLocaleName]; unsigned __int16 **
0x1800211f2  call    ?get_Locale@Settings@@QEAAJPEAPEAG@Z; Settings::get_Locale(ushort * *)
0x1800211f7  mov     ebx, eax
0x1800211f9  test    eax, eax
0x1800211fb  jns     short loc_180021208
0x1800211fd  mov     r8d, 29Ah
0x180021203  jmp     loc_1800213FA
0x180021208  lea     rcx, [rsp+8B0h+SystemTime]; lpSystemTime
0x18002120d  call    cs:__imp_GetLocalTime
0x180021213  mov     rcx, [rsp+8B0h+lpLocaleName]; lpLocaleName
0x180021218  lea     rax, [rsp+8B0h+DateStr]
0x18002121d  mov     [rsp+8B0h+lpCalendar], r14; lpCalendar
0x180021222  lea     r8, [rsp+8B0h+SystemTime]; lpDate
0x180021227  xor     r9d, r9d; lpFormat
0x18002122a  mov     r14d, 400h
0x180021230  mov     [rsp+8B0h+cchDate], r14d; cchDate
0x180021235  mov     [rsp+8B0h+lpDateStr], rax; lpDateStr
0x18002123a  lea     edx, [r9+2]; dwFlags
0x18002123e  call    cs:__imp_GetDateFormatEx
0x180021244  test    eax, eax
0x180021246  jnz     short loc_180021278
0x180021248  call    cs:__imp_GetLastError
0x18002124e  xor     r14d, r14d
0x180021251  mov     ebx, eax
0x180021253  test    eax, eax
0x180021255  jle     short loc_180021260
0x180021257  movzx   ebx, ax
0x18002125a  or      ebx, 80070000h
0x180021260  test    ebx, ebx
0x180021262  mov     eax, 80004005h
0x180021267  mov     r8d, 2B2h
0x18002126d  cmovns  ebx, eax
0x180021270  mov     r9d, ebx
0x180021273  jmp     loc_1800213FD
0x180021278  lea     r8, asc_18003283C; " "
0x18002127f  mov     rdx, r14; unsigned __int64
0x180021282  lea     rcx, [rsp+8B0h+DateStr]; unsigned __int16 *
0x180021287  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002128c  xor     ecx, ecx
0x18002128e  mov     ebx, eax
0x180021290  test    eax, eax
0x180021292  jns     short loc_1800212B6
0x180021294  mov     r9d, eax; int
0x180021297  lea     rdx, aReporterAddtim; "Reporter::AddTimeToReport"
0x18002129e  mov     r8d, 2B5h; int
0x1800212a4  mov     ecx, 1; Level
0x1800212a9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800212ae  xor     r14d, r14d
0x1800212b1  jmp     loc_18002140E
0x1800212b6  lea     rdx, [rsp+8B0h+DateStr]
0x1800212bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800212bf  inc     rax
0x1800212c2  cmp     [rdx+rax*2], cx
0x1800212c6  jnz     short loc_1800212BF
0x1800212c8  sub     r14d, eax
0x1800212cb  lea     rcx, [rsp+8B0h+DateStr]
0x1800212d0  lea     rax, [rcx+rax*2]
0x1800212d4  mov     [rsp+8B0h+cchDate], r14d; cchTime
0x1800212d9  mov     rcx, [rsp+8B0h+lpLocaleName]; lpLocaleName
0x1800212de  lea     r8, [rsp+8B0h+SystemTime]; lpTime
0x1800212e3  xor     r9d, r9d; lpFormat
0x1800212e6  mov     [rsp+8B0h+lpDateStr], rax; lpTimeStr
0x1800212eb  xor     edx, edx; dwFlags
0x1800212ed  call    cs:__imp_GetTimeFormatEx
0x1800212f3  xor     r14d, r14d
0x1800212f6  test    eax, eax
0x1800212f8  jnz     short loc_180021327
0x1800212fa  call    cs:__imp_GetLastError
0x180021300  mov     ebx, eax
0x180021302  test    eax, eax
0x180021304  jle     short loc_18002130F
0x180021306  movzx   ebx, ax
0x180021309  or      ebx, 80070000h
0x18002130f  test    ebx, ebx
0x180021311  mov     eax, 80004005h
0x180021316  mov     r8d, 2BCh
0x18002131c  cmovns  ebx, eax
0x18002131f  mov     r9d, ebx
0x180021322  jmp     loc_1800213FD
0x180021327  lea     rax, [rsp+8B0h+var_868]
0x18002132c  mov     rdx, r13; struct IXMLDOMElement *
0x18002132f  lea     r9, [rsp+8B0h+DateStr]; unsigned __int16 *
0x180021334  mov     [rsp+8B0h+lpDateStr], rax; struct IXMLDOMElement **
0x180021339  lea     r8, aData; "Data"
0x180021340  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180021343  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021348  mov     ebx, eax
0x18002134a  test    eax, eax
0x18002134c  jns     short loc_180021372
0x18002134e  mov     r9d, eax; int
0x180021351  lea     rdx, aReporterAddtim; "Reporter::AddTimeToReport"
0x180021358  mov     r8d, 2CBh; int
0x18002135e  mov     ecx, 1; Level
0x180021363  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021368  mov     rdi, [rsp+8B0h+var_868]
0x18002136d  jmp     loc_18002140E
0x180021372  mov     rdi, [rsp+8B0h+var_868]
0x180021377  lea     r9, aTime; "Time"
0x18002137e  mov     rdx, rdi; struct IXMLDOMElement *
0x180021381  lea     r8, aId_0; "id"
0x180021388  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18002138a  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18002138f  mov     ebx, eax
0x180021391  test    eax, eax
0x180021393  jns     short loc_18002139D
0x180021395  mov     r8d, 2D1h
0x18002139b  jmp     short loc_1800213FA
0x18002139d  lea     r8, [rsp+8B0h+var_860]; unsigned __int16 **
0x1800213a2  mov     edx, 73h ; 's'; unsigned int
0x1800213a7  xor     ecx, ecx; unsigned __int16 *
0x1800213a9  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x1800213ae  mov     ebx, eax
0x1800213b0  test    eax, eax
0x1800213b2  jns     short loc_1800213D5
0x1800213b4  mov     r9d, eax; int
0x1800213b7  lea     rdx, aReporterAddtim; "Reporter::AddTimeToReport"
0x1800213be  mov     r8d, 2D4h; int
0x1800213c4  mov     ecx, 1; Level
0x1800213c9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800213ce  mov     rsi, [rsp+8B0h+var_860]
0x1800213d3  jmp     short loc_18002140E
0x1800213d5  mov     rsi, [rsp+8B0h+var_860]
0x1800213da  lea     r8, aName_0; "name"
0x1800213e1  mov     r9, rsi; unsigned __int16 *
0x1800213e4  mov     rdx, rdi; struct IXMLDOMElement *
0x1800213e7  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x1800213e9  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800213ee  mov     ebx, eax
0x1800213f0  test    eax, eax
0x1800213f2  jns     short loc_18002140E
0x1800213f4  mov     r8d, 2D7h; int
0x1800213fa  mov     r9d, eax; int
0x1800213fd  lea     rdx, aReporterAddtim; "Reporter::AddTimeToReport"
0x180021404  mov     ecx, 1; Level
0x180021409  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002140e  cmp     [rsp+8B0h+lpLocaleName], r14
0x180021413  jz      short loc_18002141F
0x180021415  mov     rcx, [rsp+8B0h+lpLocaleName]; Block
0x18002141a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002141f  test    rsi, rsi
0x180021422  jz      short loc_18002142C
0x180021424  mov     rcx, rsi; Block
0x180021427  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002142c  test    rdi, rdi
0x18002142f  jz      short loc_180021440
0x180021431  mov     rax, [rdi]
0x180021434  mov     rcx, rdi
0x180021437  mov     rax, [rax+10h]
0x18002143b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021440  mov     eax, ebx
0x180021442  mov     rcx, [rbp+7B0h+var_40]
0x180021449  xor     rcx, rsp; StackCookie
0x18002144c  call    __security_check_cookie
0x180021451  add     rsp, 880h
0x180021458  pop     r14
0x18002145a  pop     r13
0x18002145c  pop     r12
0x18002145e  pop     rdi
0x18002145f  pop     rsi
0x180021460  pop     rbx
0x180021461  pop     rbp
0x180021462  retn
```
