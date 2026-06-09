# CWshShell::LogEvent(tagVARIANT *,ushort *,ushort *,short *)

- ea: `0x180007690`
- end: `0x180007b14`
- name: `?LogEvent@CWshShell@@UEAAJPEAUtagVARIANT@@PEAG1PEAF@Z`
- size: `1156`
- prototype: `int(CWshShell *__hidden this, struct tagVARIANT *, unsigned __int16 *, unsigned __int16 *, __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005d20`
- `0x180007690`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `msvcrt!strcat_s` at `0x180007a52`
- `msvcrt!strcat_s` at `0x180007a52`
- `msvcrt!fprintf` at `0x180007aaa`
- `msvcrt!fprintf` at `0x180007aaa`
- `msvcrt!fclose` at `0x180007ab3`
- `msvcrt!fclose` at `0x180007ab3`
- `msvcrt!fopen` at `0x180007a63`
- `msvcrt!fopen` at `0x180007a63`
- `OLEAUT32!__imp_VariantInit` at `0x180007707`
- `OLEAUT32!__imp_VariantInit` at `0x180007707`
- `OLEAUT32!__imp_VariantClear` at `0x180007ac5`
- `OLEAUT32!__imp_VariantClear` at `0x180007ac5`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007728`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007728`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800078fc`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800078fc`
- `OLEAUT32!__imp_VarDateFromUdate` at `0x1800078d2`
- `OLEAUT32!__imp_VarDateFromUdate` at `0x1800078d2`
- `ADVAPI32!DeregisterEventSource` at `0x180007841`
- `ADVAPI32!DeregisterEventSource` at `0x180007841`
- `ADVAPI32!RegisterEventSourceW` at `0x1800077b5`
- `ADVAPI32!RegisterEventSourceW` at `0x1800077b5`
- `ADVAPI32!ReportEventW` at `0x18000781d`
- `ADVAPI32!ReportEventW` at `0x18000781d`
- `KERNEL32!GetLastError` at `0x1800077c5`
- `KERNEL32!GetLastError` at `0x180007829`
- `KERNEL32!GetLastError` at `0x18000793b`
- `KERNEL32!GetLastError` at `0x1800077c5`
- `KERNEL32!GetLastError` at `0x180007829`
- `KERNEL32!GetLastError` at `0x18000793b`
- `KERNEL32!GetUserDefaultLCID` at `0x1800078e2`
- `KERNEL32!GetUserDefaultLCID` at `0x1800078e2`
- `KERNEL32!GetWindowsDirectoryA` at `0x180007a36`
- `KERNEL32!GetWindowsDirectoryA` at `0x180007a36`
- `KERNEL32!GetLocalTime` at `0x1800078b9`
- `KERNEL32!GetLocalTime` at `0x1800078b9`
- `KERNEL32!WideCharToMultiByte` at `0x18000792e`
- `KERNEL32!WideCharToMultiByte` at `0x18000799d`
- `KERNEL32!WideCharToMultiByte` at `0x1800079c4`
- `KERNEL32!WideCharToMultiByte` at `0x180007a1b`
- `KERNEL32!WideCharToMultiByte` at `0x18000792e`
- `KERNEL32!WideCharToMultiByte` at `0x18000799d`
- `KERNEL32!WideCharToMultiByte` at `0x1800079c4`
- `KERNEL32!WideCharToMultiByte` at `0x180007a1b`
- `USER32!LoadStringA` at `0x1800078af`
- `USER32!LoadStringA` at `0x1800078af`

## pseudocode

```c
HRESULT __fastcall CWshShell::LogEvent(
        CWshShell *this,
        struct tagVARIANT *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int16 *a5)
{
  DWORD v5; // edi
  HRESULT result; // eax
  SHORT iVal; // r14
  int v11; // ecx
  HANDLE v12; // rsi
  signed int v13; // eax
  int v14; // ebx
  signed int LastError; // eax
  UINT v16; // edx
  LCID UserDefaultLCID; // eax
  int v18; // eax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  int v23; // eax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  FILE *v28; // rax
  FILE *v29; // rdi
  __int64 v30; // [rsp+0h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp+0h] BYREF
  VARIANTARG pvargDest; // [rsp+68h] [rbp+18h] BYREF
  UDATE Strings; // [rsp+80h] [rbp+30h] BYREF
  CHAR Destination[272]; // [rsp+A0h] [rbp+50h] BYREF
  CHAR Buffer[1024]; // [rsp+1B0h] [rbp+160h] BYREF

  v5 = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
    return -2147467261;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  memset(&pvargDest, 0, sizeof(pvargDest));
  result = VariantChangeType(&pvargDest, a2, 0, 2u);
  if ( result < 0 )
    return result;
  iVal = pvargDest.iVal;
  if ( pvargDest.uiVal <= 0x10u )
  {
    v11 = 65815;
    if ( _bittest(&v11, pvargDest.uiVal) )
    {
      Strings.st = 0;
      if ( Global::g_fWindowsNT )
      {
        if ( pvargDest.iVal )
        {
          switch ( pvargDest.uiVal )
          {
            case 1u:
              v5 = -1073741823;
              break;
            case 2u:
              v5 = -2147483646;
              break;
            case 4u:
              v5 = 1073741828;
              break;
            case 8u:
              v5 = 8;
              break;
            case 0x10u:
              v5 = -1073741808;
              break;
          }
        }
        v12 = RegisterEventSourceW(a4, L"WSH");
        if ( v12 )
        {
          v14 = 0;
          *(_QWORD *)&Strings.st.wHour = 0;
          *(_QWORD *)&Strings.st.wYear = a3;
          if ( !ReportEventW(v12, iVal, 0, v5, 0, 1u, 0, (LPCWSTR *)&Strings, 0) )
          {
            LastError = GetLastError();
            v14 = LastError;
            if ( LastError > 0 )
              v14 = (unsigned __int16)LastError | 0x80070000;
          }
          DeregisterEventSource(v12);
          goto LABEL_58;
        }
        v13 = GetLastError();
        goto LABEL_22;
      }
      v16 = 0;
      Strings.wDayOfYear = 0;
      if ( pvargDest.iVal )
      {
        switch ( pvargDest.uiVal )
        {
          case 1u:
            v16 = 4201;
            break;
          case 2u:
            v16 = 4202;
            break;
          case 4u:
            v16 = 4204;
            break;
          case 8u:
            v16 = 4208;
            break;
          case 0x10u:
            v16 = 4216;
            break;
        }
      }
      else
      {
        v16 = 4200;
      }
      LoadStringA(Global::g_hResource, v16, Buffer, 1024);
      GetLocalTime(&Strings.st);
      pvarg.vt = 7;
      v14 = VarDateFromUdate(&Strings, 0, &pvarg.dblVal);
      if ( v14 < 0 )
        goto LABEL_58;
      UserDefaultLCID = GetUserDefaultLCID();
      v14 = VariantChangeTypeEx(&pvarg, &pvarg, UserDefaultLCID, 0, 8u);
      if ( v14 < 0 )
        goto LABEL_58;
      v18 = WideCharToMultiByte(0, 0, pvarg.bstrVal, -1, 0, 0, 0, 0);
      if ( !v18 )
      {
LABEL_43:
        v13 = GetLastError();
LABEL_22:
        v14 = v13;
        if ( v13 > 0 )
          v14 = (unsigned __int16)v13 | 0x80070000;
        goto LABEL_58;
      }
      v19 = v18 + 15LL;
      if ( v19 < v18 )
        v19 = 0xFFFFFFFFFFFFFF0LL;
      v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
      v21 = alloca(v20);
      v22 = alloca(v20);
      if ( &pvarg )
      {
        if ( !WideCharToMultiByte(0, 0, pvarg.bstrVal, -1, (LPSTR)&pvarg, v18, 0, 0) )
          goto LABEL_43;
        v23 = WideCharToMultiByte(0, 0, a3, -1, 0, 0, 0, 0);
        if ( !v23 )
          goto LABEL_43;
        v24 = v23 + 15LL;
        if ( v24 < v23 )
          v24 = 0xFFFFFFFFFFFFFF0LL;
        v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
        v26 = alloca(v25);
        v27 = alloca(v25);
        if ( &v30 != (__int64 *)-80LL )
        {
          if ( WideCharToMultiByte(0, 0, a3, -1, (LPSTR)&pvarg, v23, 0, 0) && GetWindowsDirectoryA(Destination, 0x104u) )
          {
            strcat_s(Destination, 0x104u, "\\wsh.log");
            v28 = fopen(Destination, "a");
            v29 = v28;
            if ( v28 )
            {
              fprintf(v28, "%s\t%s: %s\n", (const char *)&pvarg, Buffer, (const char *)&pvarg);
              fclose(v29);
            }
            else
            {
              Signal_Exception(&IID_IWshShell3, L"WshShell.LogEvent", 0x1010u);
              v14 = -2147352567;
            }
            goto LABEL_58;
          }
          goto LABEL_43;
        }
      }
      v14 = -2147024882;
LABEL_58:
      VariantClear(&pvarg);
      *a5 = (v14 < 0) - 1;
      return v14;
    }
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180007690  push    rbp
0x180007692  push    rsi
0x180007693  push    rdi
0x180007694  push    r12
0x180007696  push    r13
0x180007698  push    r14
0x18000769a  push    r15
0x18000769c  sub     rsp, 5C0h
0x1800076a3  lea     rbp, [rsp+50h]
0x1800076a8  mov     [rbp+5A0h+arg_0], rbx
0x1800076af  mov     rax, cs:__security_cookie
0x1800076b6  xor     rax, rbp
0x1800076b9  mov     [rbp+5A0h+var_40], rax
0x1800076c0  mov     r13, [rbp+5A0h+arg_20]
0x1800076c7  xor     edi, edi
0x1800076c9  mov     r15, r9
0x1800076cc  mov     r12, r8
0x1800076cf  mov     rbx, rdx
0x1800076d2  test    rdx, rdx
0x1800076d5  jz      loc_180007AE6
0x1800076db  test    r8, r8
0x1800076de  jz      loc_180007AE6
0x1800076e4  test    r9, r9
0x1800076e7  jz      loc_180007AE6
0x1800076ed  test    r13, r13
0x1800076f0  jz      loc_180007AE6
0x1800076f6  xorps   xmm0, xmm0
0x1800076f9  lea     rcx, [rbp+5A0h+pvarg]; pvarg
0x1800076fd  xor     eax, eax
0x1800076ff  movups  xmmword ptr [rbp+5A0h+pvarg], xmm0
0x180007703  mov     qword ptr [rbp+5A0h+pvarg+10h], rax
0x180007707  call    cs:__imp_VariantInit
0x18000770d  xorps   xmm0, xmm0
0x180007710  lea     r9d, [rdi+2]; vt
0x180007714  xor     eax, eax
0x180007716  lea     rcx, [rbp+5A0h+pvargDest]; pvargDest
0x18000771a  xor     r8d, r8d; wFlags
0x18000771d  mov     qword ptr [rbp+5A0h+pvargDest+10h], rax
0x180007721  mov     rdx, rbx; pvarSrc
0x180007724  movups  xmmword ptr [rbp+5A0h+pvargDest], xmm0
0x180007728  call    cs:__imp_VariantChangeType
0x18000772e  test    eax, eax
0x180007730  js      loc_180007AEB
0x180007736  movzx   r14d, word ptr [rbp+5A0h+pvargDest+8]
0x18000773b  cmp     r14d, 10h
0x18000773f  ja      loc_180007ADF
0x180007745  mov     ecx, 10117h
0x18000774a  bt      ecx, r14d
0x18000774e  jnb     loc_180007ADF
0x180007754  cmp     cs:?g_fWindowsNT@Global@@2_NA, dil; bool Global::g_fWindowsNT
0x18000775b  xorps   xmm0, xmm0
0x18000775e  movups  xmmword ptr [rbp+5A0h+Strings], xmm0
0x180007762  mov     ecx, r14d
0x180007765  jz      loc_18000784C
0x18000776b  test    ecx, ecx
0x18000776d  jz      short loc_1800077AB
0x18000776f  sub     ecx, 1
0x180007772  jz      short loc_1800077A6
0x180007774  sub     ecx, 1
0x180007777  jz      short loc_18000779F
0x180007779  sub     ecx, 2
0x18000777c  jz      short loc_180007798
0x18000777e  sub     ecx, 4
0x180007781  jz      short loc_180007791
0x180007783  lea     esi, [rdi+8]
0x180007786  cmp     ecx, esi
0x180007788  jnz     short loc_1800077AB
0x18000778a  mov     edi, 0C0000010h
0x18000778f  jmp     short loc_1800077AB
0x180007791  mov     edi, 8
0x180007796  jmp     short loc_1800077AB
0x180007798  mov     edi, 40000004h
0x18000779d  jmp     short loc_1800077AB
0x18000779f  mov     edi, 80000002h
0x1800077a4  jmp     short loc_1800077AB
0x1800077a6  mov     edi, 0C0000001h
0x1800077ab  lea     rdx, SourceName; "WSH"
0x1800077b2  mov     rcx, r15; lpUNCServerName
0x1800077b5  call    cs:__imp_RegisterEventSourceW
0x1800077bb  xor     ecx, ecx
0x1800077bd  mov     rsi, rax
0x1800077c0  test    rax, rax
0x1800077c3  jnz     short loc_1800077E5
0x1800077c5  call    cs:__imp_GetLastError
0x1800077cb  xor     edi, edi
0x1800077cd  mov     ebx, eax
0x1800077cf  test    eax, eax
0x1800077d1  jle     loc_180007ABB
0x1800077d7  movzx   ebx, ax
0x1800077da  or      ebx, 80070000h
0x1800077e0  jmp     loc_180007ABB
0x1800077e5  mov     [rsp+5F0h+lpRawData], rcx; lpRawData
0x1800077ea  lea     rax, [rbp+5A0h+Strings]
0x1800077ee  mov     [rsp+5F0h+lpStrings], rax; lpStrings
0x1800077f3  xor     r8d, r8d; wCategory
0x1800077f6  mov     [rsp+5F0h+dwDataSize], ecx; dwDataSize
0x1800077fa  mov     ebx, ecx
0x1800077fc  mov     [rbp+5A0h+Strings+8], rcx
0x180007800  mov     r9d, edi; dwEventID
0x180007803  movzx   edx, r14w; wType
0x180007807  mov     [rbp+5A0h+Strings], r12
0x18000780b  lea     r15d, [r8+1]
0x18000780f  mov     [rsp+5F0h+wNumStrings], r15w; wNumStrings
0x180007815  mov     [rsp+5F0h+lpUserSid], rcx; lpUserSid
0x18000781a  mov     rcx, rsi; hEventLog
0x18000781d  call    cs:__imp_ReportEventW
0x180007823  xor     edi, edi
0x180007825  test    eax, eax
0x180007827  jnz     short loc_18000783E
0x180007829  call    cs:__imp_GetLastError
0x18000782f  mov     ebx, eax
0x180007831  test    eax, eax
0x180007833  jle     short loc_18000783E
0x180007835  movzx   ebx, ax
0x180007838  or      ebx, 80070000h
0x18000783e  mov     rcx, rsi; hEventLog
0x180007841  call    cs:__imp_DeregisterEventSource
0x180007847  jmp     loc_180007AC1
0x18000784c  xor     eax, eax
0x18000784e  mov     edx, edi
0x180007850  mov     [rbp+5A0h+var_560], ax
0x180007854  lea     esi, [rax+8]
0x180007857  test    ecx, ecx
0x180007859  jz      short loc_180007896
0x18000785b  sub     ecx, 1
0x18000785e  jz      short loc_18000788F
0x180007860  sub     ecx, 1
0x180007863  jz      short loc_180007888
0x180007865  sub     ecx, 2
0x180007868  jz      short loc_180007881
0x18000786a  sub     ecx, 4
0x18000786d  jz      short loc_18000787A
0x18000786f  cmp     ecx, esi
0x180007871  jnz     short loc_18000789B
0x180007873  mov     edx, 1078h
0x180007878  jmp     short loc_18000789B
0x18000787a  mov     edx, 1070h
0x18000787f  jmp     short loc_18000789B
0x180007881  mov     edx, 106Ch
0x180007886  jmp     short loc_18000789B
0x180007888  mov     edx, 106Ah
0x18000788d  jmp     short loc_18000789B
0x18000788f  mov     edx, 1069h
0x180007894  jmp     short loc_18000789B
0x180007896  mov     edx, 1068h; uID
0x18000789b  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x1800078a2  lea     r8, [rbp+5A0h+Buffer]; lpBuffer
0x1800078a9  mov     r9d, 400h; cchBufferMax
0x1800078af  call    cs:__imp_LoadStringA
0x1800078b5  lea     rcx, [rbp+5A0h+Strings]; lpSystemTime
0x1800078b9  call    cs:__imp_GetLocalTime
0x1800078bf  mov     eax, 7
0x1800078c4  lea     r8, [rbp+5A0h+pvarg+8]; pdateOut
0x1800078c8  xor     edx, edx; dwFlags
0x1800078ca  mov     word ptr [rbp+5A0h+pvarg], ax
0x1800078ce  lea     rcx, [rbp+5A0h+Strings]; pudateIn
0x1800078d2  call    cs:__imp_VarDateFromUdate
0x1800078d8  mov     ebx, eax
0x1800078da  test    eax, eax
0x1800078dc  js      loc_180007ABB
0x1800078e2  call    cs:__imp_GetUserDefaultLCID
0x1800078e8  movzx   r9d, di; wFlags
0x1800078ec  mov     word ptr [rsp+5F0h+lpUserSid], si; vt
0x1800078f1  mov     r8d, eax; lcid
0x1800078f4  lea     rdx, [rbp+5A0h+pvarg]; pvarSrc
0x1800078f8  lea     rcx, [rbp+5A0h+pvarg]; pvargDest
0x1800078fc  call    cs:__imp_VariantChangeTypeEx
0x180007902  mov     ebx, eax
0x180007904  test    eax, eax
0x180007906  js      loc_180007ABB
0x18000790c  mov     r8, qword ptr [rbp+5A0h+pvarg+8]; lpWideCharStr
0x180007910  or      r15d, 0FFFFFFFFh
0x180007914  mov     [rsp+5F0h+lpStrings], rdi; lpUsedDefaultChar
0x180007919  mov     r9d, r15d; cchWideChar
0x18000791c  mov     qword ptr [rsp+5F0h+dwDataSize], rdi; lpDefaultChar
0x180007921  xor     edx, edx; dwFlags
0x180007923  mov     dword ptr [rsp+5F0h+wNumStrings], edi; cbMultiByte
0x180007927  xor     ecx, ecx; CodePage
0x180007929  mov     [rsp+5F0h+lpUserSid], rdi; lpMultiByteStr
0x18000792e  call    cs:__imp_WideCharToMultiByte
0x180007934  movsxd  rdx, eax
0x180007937  test    eax, eax
0x180007939  jnz     short loc_180007946
0x18000793b  call    cs:__imp_GetLastError
0x180007941  jmp     loc_1800077CD
0x180007946  lea     rcx, [rdx+0Fh]
0x18000794a  mov     rsi, 0FFFFFFFFFFFFFF0h
0x180007954  cmp     rcx, rdx
0x180007957  ja      short loc_18000795C
0x180007959  mov     rcx, rsi
0x18000795c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180007960  mov     rax, rcx
0x180007963  call    _alloca_probe
0x180007968  sub     rsp, rcx
0x18000796b  lea     r14, [rsp+5F0h+pvarg]
0x180007970  test    r14, r14
0x180007973  jnz     short loc_18000797F
0x180007975  mov     ebx, 8007000Eh
0x18000797a  jmp     loc_180007ABB
0x18000797f  mov     r8, qword ptr [rbp+5A0h+pvarg+8]; lpWideCharStr
0x180007983  mov     r9d, r15d; cchWideChar
0x180007986  mov     [rsp+5F0h+lpStrings], rdi; lpUsedDefaultChar
0x18000798b  xor     ecx, ecx; CodePage
0x18000798d  mov     qword ptr [rsp+5F0h+dwDataSize], rdi; lpDefaultChar
0x180007992  mov     dword ptr [rsp+5F0h+wNumStrings], edx; cbMultiByte
0x180007996  xor     edx, edx; dwFlags
0x180007998  mov     [rsp+5F0h+lpUserSid], r14; lpMultiByteStr
0x18000799d  call    cs:__imp_WideCharToMultiByte
0x1800079a3  test    eax, eax
0x1800079a5  jz      short loc_18000793B
0x1800079a7  mov     [rsp+5F0h+lpStrings], rdi; lpUsedDefaultChar
0x1800079ac  mov     r9d, r15d; cchWideChar
0x1800079af  mov     qword ptr [rsp+5F0h+dwDataSize], rdi; lpDefaultChar
0x1800079b4  mov     r8, r12; lpWideCharStr
0x1800079b7  mov     dword ptr [rsp+5F0h+wNumStrings], edi; cbMultiByte
0x1800079bb  xor     edx, edx; dwFlags
0x1800079bd  xor     ecx, ecx; CodePage
0x1800079bf  mov     [rsp+5F0h+lpUserSid], rdi; lpMultiByteStr
0x1800079c4  call    cs:__imp_WideCharToMultiByte
0x1800079ca  movsxd  rdx, eax
0x1800079cd  test    eax, eax
0x1800079cf  jz      loc_18000793B
0x1800079d5  lea     rcx, [rdx+0Fh]
0x1800079d9  cmp     rcx, rdx
0x1800079dc  ja      short loc_1800079E1
0x1800079de  mov     rcx, rsi
0x1800079e1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800079e5  mov     rax, rcx
0x1800079e8  call    _alloca_probe
0x1800079ed  sub     rsp, rcx
0x1800079f0  lea     rsi, [rsp+5F0h+pvarg]
0x1800079f5  test    rsi, rsi
0x1800079f8  jz      loc_180007975
0x1800079fe  mov     [rsp+5F0h+lpStrings], rdi; lpUsedDefaultChar
0x180007a03  mov     r9d, r15d; cchWideChar
0x180007a06  mov     qword ptr [rsp+5F0h+dwDataSize], rdi; lpDefaultChar
0x180007a0b  mov     r8, r12; lpWideCharStr
0x180007a0e  mov     dword ptr [rsp+5F0h+wNumStrings], edx; cbMultiByte
0x180007a12  xor     ecx, ecx; CodePage
0x180007a14  xor     edx, edx; dwFlags
0x180007a16  mov     [rsp+5F0h+lpUserSid], rsi; lpMultiByteStr
0x180007a1b  call    cs:__imp_WideCharToMultiByte
0x180007a21  test    eax, eax
0x180007a23  jz      loc_18000793B
0x180007a29  mov     r15d, 104h
0x180007a2f  lea     rcx, [rbp+5A0h+Destination]; lpBuffer
0x180007a33  mov     edx, r15d; uSize
0x180007a36  call    cs:__imp_GetWindowsDirectoryA
0x180007a3c  test    eax, eax
0x180007a3e  jz      loc_18000793B
0x180007a44  lea     r8, Source; "\\wsh.log"
0x180007a4b  mov     edx, r15d; SizeInBytes
0x180007a4e  lea     rcx, [rbp+5A0h+Destination]; Destination
0x180007a52  call    cs:__imp_strcat_s
0x180007a58  lea     rdx, Mode; "a"
0x180007a5f  lea     rcx, [rbp+5A0h+Destination]; FileName
0x180007a63  call    cs:__imp_fopen
0x180007a69  mov     rdi, rax
0x180007a6c  test    rax, rax
0x180007a6f  jnz     short loc_180007A91
0x180007a71  mov     r8d, 1010h; unsigned int
0x180007a77  lea     rdx, aWshshellLogeve; "WshShell.LogEvent"
0x180007a7e  lea     rcx, IID_IWshShell3; struct _GUID *
0x180007a85  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x180007a8a  mov     ebx, 80020009h
0x180007a8f  jmp     short loc_180007AB9
0x180007a91  lea     r9, [rbp+5A0h+Buffer]
0x180007a98  mov     [rsp+5F0h+lpUserSid], rsi
0x180007a9d  mov     r8, r14
0x180007aa0  lea     rdx, aSSS; "%s\t%s: %s\n"
0x180007aa7  mov     rcx, rdi; Stream
0x180007aaa  call    cs:__imp_fprintf
0x180007ab0  mov     rcx, rdi; Stream
0x180007ab3  call    cs:__imp_fclose
0x180007ab9  xor     edi, edi
0x180007abb  mov     r15d, 1
0x180007ac1  lea     rcx, [rbp+5A0h+pvarg]; pvarg
0x180007ac5  call    cs:__imp_VariantClear
0x180007acb  mov     eax, edi
0x180007acd  test    ebx, ebx
0x180007acf  sets    al
0x180007ad2  sub     ax, r15w
0x180007ad6  mov     [r13+0], ax
0x180007adb  mov     eax, ebx
0x180007add  jmp     short loc_180007AEB
0x180007adf  mov     eax, 80070057h
0x180007ae4  jmp     short loc_180007AEB
0x180007ae6  mov     eax, 80004003h
0x180007aeb  mov     rcx, [rbp+5A0h+var_40]
0x180007af2  xor     rcx, rbp; StackCookie
0x180007af5  call    __security_check_cookie
0x180007afa  mov     rbx, [rbp+5A0h+arg_0]
0x180007b01  lea     rsp, [rbp+570h]
0x180007b08  pop     r15
0x180007b0a  pop     r14
0x180007b0c  pop     r13
0x180007b0e  pop     r12
0x180007b10  pop     rdi
0x180007b11  pop     rsi
0x180007b12  pop     rbp
  ... truncated ...
```
