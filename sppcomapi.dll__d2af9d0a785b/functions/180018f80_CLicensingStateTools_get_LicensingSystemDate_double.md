# CLicensingStateTools::get_LicensingSystemDate(double *)

- ea: `0x180018f80`
- end: `0x180019102`
- name: `?get_LicensingSystemDate@CLicensingStateTools@@UEAAJPEAN@Z`
- size: `386`
- prototype: `int(CLicensingStateTools *__hidden this, double *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180003520`
- `0x180004288`
- `0x180018f80`
- `0x18003c560`

## import_xrefs

- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18001906d`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18001906d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001907d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001907d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019056`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019056`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190b8`
- `SLC!SLGetApplicationInformation` at `0x180019024`
- `SLC!SLGetApplicationInformation` at `0x180019024`
- `SLC!SLOpen` at `0x180018fe3`
- `SLC!SLOpen` at `0x180018fe3`
- `SLC!SLClose` at `0x1800190d5`
- `SLC!SLClose` at `0x1800190d5`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::get_LicensingSystemDate(CLicensingStateTools *this, double *a2)
{
  unsigned int v3; // ebx
  HRESULT v4; // eax
  __int64 v5; // rcx
  signed int LastError; // eax
  UINT pcbValue; // [rsp+30h] [rbp-40h] BYREF
  PBYTE ppbValue; // [rsp+38h] [rbp-38h] BYREF
  SLDATATYPE peDataType; // [rsp+40h] [rbp-30h] BYREF
  HSLC phSLC; // [rsp+48h] [rbp-28h] BYREF
  FILETIME FileTime; // [rsp+50h] [rbp-20h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  phSLC = 0;
  peDataType = SL_DATA_NONE;
  pcbValue = 0;
  ppbValue = 0;
  FileTime = 0;
  SystemTime = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
LABEL_14:
    v5 = v3;
    goto LABEL_15;
  }
  v4 = SLOpen(&phSLC);
  v3 = v4;
  if ( v4 < 0
    || (v4 = SLGetApplicationInformation(phSLC, &WINDOWS_SLID, L"TrustedTime", &peDataType, &pcbValue, &ppbValue),
        v3 = v4,
        v4 < 0) )
  {
    v5 = (unsigned int)v4;
LABEL_15:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_16;
  }
  if ( pcbValue != 8 )
  {
    v3 = -2147418113;
    goto LABEL_14;
  }
  FileTime = *(FILETIME *)ppbValue;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) || !SystemTimeToVariantTime(&SystemTime, a2) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    goto LABEL_14;
  }
LABEL_16:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( ppbValue )
  {
    LocalFree(ppbValue);
    ppbValue = 0;
  }
  if ( phSLC )
    SLClose(phSLC);
  return v3;
}

```

## disassembly

```asm
0x180018f80  mov     [rsp-8+arg_0], rbx
0x180018f85  mov     [rsp-8+arg_10], rdi
0x180018f8a  push    rbp
0x180018f8b  mov     rbp, rsp
0x180018f8e  sub     rsp, 70h
0x180018f92  mov     rax, cs:__security_cookie
0x180018f99  xor     rax, rsp
0x180018f9c  mov     [rbp+var_8], rax
0x180018fa0  mov     [rbp+phSLC], 0
0x180018fa8  xorps   xmm0, xmm0
0x180018fab  mov     [rbp+peDataType], 0
0x180018fb2  mov     rdi, rdx
0x180018fb5  mov     [rbp+var_40], 0
0x180018fbc  mov     [rbp+var_38], 0
0x180018fc4  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180018fcc  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180018fd0  test    rdx, rdx
0x180018fd3  jnz     short loc_180018FDF
0x180018fd5  mov     ebx, 80070057h
0x180018fda  jmp     loc_1800190A1
0x180018fdf  lea     rcx, [rbp+phSLC]; phSLC
0x180018fe3  call    cs:__imp_SLOpen
0x180018fea  nop     dword ptr [rax+rax+00h]
0x180018fef  mov     ebx, eax
0x180018ff1  test    eax, eax
0x180018ff3  jns     short loc_180018FFC
0x180018ff5  mov     ecx, eax
0x180018ff7  jmp     loc_1800190A3
0x180018ffc  mov     rcx, [rbp+phSLC]; hSLC
0x180019000  lea     rax, [rbp+var_38]
0x180019004  mov     [rsp+70h+ppbValue], rax; ppbValue
0x180019009  lea     r9, [rbp+peDataType]; peDataType
0x18001900d  lea     rax, [rbp+var_40]
0x180019011  lea     r8, pwszValueName; "TrustedTime"
0x180019018  mov     [rsp+70h+pcbValue], rax; pcbValue
0x18001901d  lea     rdx, WINDOWS_SLID; pApplicationId
0x180019024  call    cs:__imp_SLGetApplicationInformation
0x18001902b  nop     dword ptr [rax+rax+00h]
0x180019030  mov     ebx, eax
0x180019032  test    eax, eax
0x180019034  js      short loc_180018FF5
0x180019036  cmp     [rbp+var_40], 8
0x18001903a  jz      short loc_180019043
0x18001903c  mov     ebx, 8000FFFFh
0x180019041  jmp     short loc_1800190A1
0x180019043  mov     rax, [rbp+var_38]
0x180019047  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001904b  mov     rcx, [rax]
0x18001904e  mov     qword ptr [rbp+FileTime.dwLowDateTime], rcx
0x180019052  lea     rcx, [rbp+FileTime]; lpFileTime
0x180019056  call    cs:__imp_FileTimeToSystemTime
0x18001905d  nop     dword ptr [rax+rax+00h]
0x180019062  test    eax, eax
0x180019064  jz      short loc_18001907D
0x180019066  mov     rdx, rdi; pvtime
0x180019069  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18001906d  call    cs:__imp_SystemTimeToVariantTime
0x180019074  nop     dword ptr [rax+rax+00h]
0x180019079  test    eax, eax
0x18001907b  jnz     short loc_1800190A8
0x18001907d  call    cs:__imp_GetLastError
0x180019084  nop     dword ptr [rax+rax+00h]
0x180019089  mov     ebx, eax
0x18001908b  test    eax, eax
0x18001908d  jnz     short loc_180019096
0x18001908f  mov     ebx, 80004005h
0x180019094  jmp     short loc_1800190A1
0x180019096  jle     short loc_1800190A1
0x180019098  movzx   ebx, ax
0x18001909b  or      ebx, 80070000h
0x1800190a1  mov     ecx, ebx
0x1800190a3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800190a8  mov     ecx, ebx
0x1800190aa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800190af  mov     rcx, [rbp+var_38]; hMem
0x1800190b3  test    rcx, rcx
0x1800190b6  jz      short loc_1800190CC
0x1800190b8  call    cs:__imp_LocalFree
0x1800190bf  nop     dword ptr [rax+rax+00h]
0x1800190c4  mov     [rbp+var_38], 0
0x1800190cc  mov     rcx, [rbp+phSLC]; hSLC
0x1800190d0  test    rcx, rcx
0x1800190d3  jz      short loc_1800190E1
0x1800190d5  call    cs:__imp_SLClose
0x1800190dc  nop     dword ptr [rax+rax+00h]
0x1800190e1  mov     eax, ebx
0x1800190e3  mov     rcx, [rbp+var_8]
0x1800190e7  xor     rcx, rsp; StackCookie
0x1800190ea  call    __security_check_cookie
0x1800190ef  lea     r11, [rsp+70h+var_s0]
0x1800190f4  mov     rbx, [r11+10h]
0x1800190f8  mov     rdi, [r11+20h]
0x1800190fc  mov     rsp, r11
0x1800190ff  pop     rbp
0x180019100  retn
```
