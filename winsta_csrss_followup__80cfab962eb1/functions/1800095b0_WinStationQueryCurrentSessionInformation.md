# WinStationQueryCurrentSessionInformation

- ea: `0x1800095b0`
- end: `0x1800096ac`
- name: `WinStationQueryCurrentSessionInformation`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180002464`
- `0x180004558`
- `0x180005b40`
- `0x180006000`
- `0x180006b20`
- `0x180008640`
- `0x1800095b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000960f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009655`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000960f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009655`

## string_xrefs

- `0x180009631`: `GetCurrentSessionConfigData failed: 0x%x in %s`

## pseudocode

```c
char __fastcall WinStationQueryCurrentSessionInformation(
        int a1,
        struct _WINSTATIONCONFIGW *a2,
        unsigned int a3,
        unsigned int *a4)
{
  char v4; // bl
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int CurrentSessionConfigData; // ebx
  DWORD v10; // eax

  v4 = 0;
  if ( !a2 || !a4 )
    goto LABEL_10;
  *a4 = 0;
  v5 = a1 - 1;
  if ( !v5 )
  {
    CurrentSessionConfigData = GetCurrentSessionConfigData(a2, a3, a4);
    if ( CurrentSessionConfigData >= 0 )
      return 1;
    _DbgPrintMessage(
      8,
      "GetCurrentSessionConfigData failed: 0x%x in %s",
      (unsigned int)CurrentSessionConfigData,
      "WinStationQueryCurrentSessionInformation");
    goto LABEL_13;
  }
  v6 = v5 - 5;
  if ( !v6 )
  {
    CurrentSessionConfigData = GetCurrentSessionClientData(a2, a3, a4);
    if ( CurrentSessionConfigData >= 0 )
      return 1;
    _DbgPrintMessage(
      8,
      "GetCurrentSessionClientData failed: 0x%x in %s",
      (unsigned int)CurrentSessionConfigData,
      "WinStationQueryCurrentSessionInformation");
    goto LABEL_13;
  }
  v7 = v6 - 2;
  if ( v7 )
  {
    if ( v7 != 31 )
    {
LABEL_10:
      SetLastError(0x57u);
      return v4;
    }
    CurrentSessionConfigData = GetCurrentSessionWinStationType((unsigned int *)a2, a3, a4);
    if ( CurrentSessionConfigData >= 0 )
      return 1;
    _DbgPrintMessage(
      8,
      "GetCurrentSessionWinStationType failed: 0x%x in %s",
      (unsigned int)CurrentSessionConfigData,
      "WinStationQueryCurrentSessionInformation");
LABEL_13:
    v10 = ConvertHRESULT2WIN32(CurrentSessionConfigData);
    SetLastError(v10);
    return 0;
  }
  CurrentSessionConfigData = GetCurrentSessionInformation((struct _WINSTATIONINFORMATIONW *)a2, a3, a4);
  if ( CurrentSessionConfigData < 0 )
  {
    _DbgPrintMessage(
      8,
      "GetCurrentSessionInformation failed: 0x%x in %s",
      (unsigned int)CurrentSessionConfigData,
      "WinStationQueryCurrentSessionInformation");
    goto LABEL_13;
  }
  return 1;
}

```

## disassembly

```asm
0x1800095b0  push    rbx
0x1800095b2  sub     rsp, 20h
0x1800095b6  xor     bl, bl
0x1800095b8  mov     r11d, r8d
0x1800095bb  mov     r10, rdx
0x1800095be  test    rdx, rdx
0x1800095c1  jz      short loc_18000960A
0x1800095c3  test    r9, r9
0x1800095c6  jz      short loc_18000960A
0x1800095c8  mov     dword ptr [r9], 0
0x1800095cf  sub     ecx, 1
0x1800095d2  jz      short loc_18000961D
0x1800095d4  sub     ecx, 5
0x1800095d7  jz      loc_180009665
0x1800095dd  sub     ecx, 2
0x1800095e0  jnz     short loc_180009605
0x1800095e2  mov     r8, r9; unsigned int *
0x1800095e5  mov     edx, r11d; unsigned int
0x1800095e8  mov     rcx, r10; struct _WINSTATIONINFORMATIONW *
0x1800095eb  call    ?GetCurrentSessionInformation@@YAJPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z; GetCurrentSessionInformation(_WINSTATIONINFORMATIONW *,ulong,ulong *)
0x1800095f0  mov     ebx, eax
0x1800095f2  test    eax, eax
0x1800095f4  js      loc_1800096A3
0x1800095fa  mov     bl, 1
0x1800095fc  mov     al, bl
0x1800095fe  add     rsp, 20h
0x180009602  pop     rbx
0x180009603  retn
0x180009605  cmp     ecx, 1Fh
0x180009608  jz      short loc_180009682
0x18000960a  mov     ecx, 57h ; 'W'; dwErrCode
0x18000960f  call    cs:__imp_SetLastError
0x180009616  nop     dword ptr [rax+rax+00h]
0x18000961b  jmp     short loc_1800095FC
0x18000961d  mov     r8, r9; unsigned int *
0x180009620  mov     edx, r11d; unsigned int
0x180009623  mov     rcx, r10; struct _WINSTATIONCONFIGW *
0x180009626  call    ?GetCurrentSessionConfigData@@YAJPEAU_WINSTATIONCONFIGW@@KPEAK@Z; GetCurrentSessionConfigData(_WINSTATIONCONFIGW *,ulong,ulong *)
0x18000962b  mov     ebx, eax
0x18000962d  test    eax, eax
0x18000962f  jns     short loc_1800095FA
0x180009631  lea     rdx, aGetcurrentsess; "GetCurrentSessionConfigData failed: 0x%"...
0x180009638  mov     r8d, ebx
0x18000963b  lea     r9, aWinstationquer_10; "WinStationQueryCurrentSessionInformatio"...
0x180009642  mov     ecx, 8; int
0x180009647  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000964c  mov     ecx, ebx; int
0x18000964e  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180009653  mov     ecx, eax; dwErrCode
0x180009655  call    cs:__imp_SetLastError
0x18000965c  nop     dword ptr [rax+rax+00h]
0x180009661  xor     bl, bl
0x180009663  jmp     short loc_1800095FC
0x180009665  mov     r8, r9; unsigned int *
0x180009668  mov     edx, r11d; unsigned int
0x18000966b  mov     rcx, r10; struct _WINSTATIONCLIENTW *
0x18000966e  call    ?GetCurrentSessionClientData@@YAJPEAU_WINSTATIONCLIENTW@@KPEAK@Z; GetCurrentSessionClientData(_WINSTATIONCLIENTW *,ulong,ulong *)
0x180009673  mov     ebx, eax
0x180009675  test    eax, eax
0x180009677  jns     short loc_1800095FA
0x180009679  lea     rdx, aGetcurrentsess_0; "GetCurrentSessionClientData failed: 0x%"...
0x180009680  jmp     short loc_180009638
0x180009682  mov     r8, r9; unsigned int *
0x180009685  mov     edx, r11d; unsigned int
0x180009688  mov     rcx, r10; unsigned int *
0x18000968b  call    ?GetCurrentSessionWinStationType@@YAJPEAKK0@Z; GetCurrentSessionWinStationType(ulong *,ulong,ulong *)
0x180009690  mov     ebx, eax
0x180009692  test    eax, eax
0x180009694  jns     loc_1800095FA
0x18000969a  lea     rdx, aGetcurrentsess_6; "GetCurrentSessionWinStationType failed:"...
0x1800096a1  jmp     short loc_180009638
0x1800096a3  lea     rdx, aGetcurrentsess_1; "GetCurrentSessionInformation failed: 0x"...
0x1800096aa  jmp     short loc_180009638
```
