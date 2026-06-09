# WinStationQueryCurrentSessionInformation

- ea: `0x18000b2b0`
- end: `0x18000b39b`
- name: `WinStationQueryCurrentSessionInformation`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180004a30`
- `0x180005fcc`
- `0x1800063e0`
- `0x180007890`
- `0x180007d10`
- `0x180009da0`
- `0x18000b2b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b30a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b34a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b30a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b34a`

## string_xrefs

- `0x18000b326`: `GetCurrentSessionConfigData failed: 0x%x in %s`

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
0x18000b2b0  push    rbx
0x18000b2b2  sub     rsp, 20h
0x18000b2b6  xor     bl, bl
0x18000b2b8  mov     r11d, r8d
0x18000b2bb  mov     r10, rdx
0x18000b2be  test    rdx, rdx
0x18000b2c1  jz      short loc_18000B305
0x18000b2c3  test    r9, r9
0x18000b2c6  jz      short loc_18000B305
0x18000b2c8  mov     dword ptr [r9], 0
0x18000b2cf  sub     ecx, 1
0x18000b2d2  jz      short loc_18000B312
0x18000b2d4  sub     ecx, 5
0x18000b2d7  jz      short loc_18000B354
0x18000b2d9  sub     ecx, 2
0x18000b2dc  jnz     short loc_18000B300
0x18000b2de  mov     r8, r9; unsigned int *
0x18000b2e1  mov     edx, r11d; unsigned int
0x18000b2e4  mov     rcx, r10; struct _WINSTATIONINFORMATIONW *
0x18000b2e7  call    ?GetCurrentSessionInformation@@YAJPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z; GetCurrentSessionInformation(_WINSTATIONINFORMATIONW *,ulong,ulong *)
0x18000b2ec  mov     ebx, eax
0x18000b2ee  test    eax, eax
0x18000b2f0  js      loc_18000B392
0x18000b2f6  mov     bl, 1
0x18000b2f8  mov     al, bl
0x18000b2fa  add     rsp, 20h
0x18000b2fe  pop     rbx
0x18000b2ff  retn
0x18000b300  cmp     ecx, 1Fh
0x18000b303  jz      short loc_18000B371
0x18000b305  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b30a  call    cs:__imp_SetLastError
0x18000b310  jmp     short loc_18000B2F8
0x18000b312  mov     r8, r9; unsigned int *
0x18000b315  mov     edx, r11d; unsigned int
0x18000b318  mov     rcx, r10; struct _WINSTATIONCONFIGW *
0x18000b31b  call    ?GetCurrentSessionConfigData@@YAJPEAU_WINSTATIONCONFIGW@@KPEAK@Z; GetCurrentSessionConfigData(_WINSTATIONCONFIGW *,ulong,ulong *)
0x18000b320  mov     ebx, eax
0x18000b322  test    eax, eax
0x18000b324  jns     short loc_18000B2F6
0x18000b326  lea     rdx, aGetcurrentsess; "GetCurrentSessionConfigData failed: 0x%"...
0x18000b32d  mov     r8d, ebx
0x18000b330  lea     r9, aWinstationquer_10; "WinStationQueryCurrentSessionInformatio"...
0x18000b337  mov     ecx, 8; int
0x18000b33c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b341  mov     ecx, ebx; int
0x18000b343  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000b348  mov     ecx, eax; dwErrCode
0x18000b34a  call    cs:__imp_SetLastError
0x18000b350  xor     bl, bl
0x18000b352  jmp     short loc_18000B2F8
0x18000b354  mov     r8, r9; unsigned int *
0x18000b357  mov     edx, r11d; unsigned int
0x18000b35a  mov     rcx, r10; struct _WINSTATIONCLIENTW *
0x18000b35d  call    ?GetCurrentSessionClientData@@YAJPEAU_WINSTATIONCLIENTW@@KPEAK@Z; GetCurrentSessionClientData(_WINSTATIONCLIENTW *,ulong,ulong *)
0x18000b362  mov     ebx, eax
0x18000b364  test    eax, eax
0x18000b366  jns     short loc_18000B2F6
0x18000b368  lea     rdx, aGetcurrentsess_0; "GetCurrentSessionClientData failed: 0x%"...
0x18000b36f  jmp     short loc_18000B32D
0x18000b371  mov     r8, r9; unsigned int *
0x18000b374  mov     edx, r11d; unsigned int
0x18000b377  mov     rcx, r10; unsigned int *
0x18000b37a  call    ?GetCurrentSessionWinStationType@@YAJPEAKK0@Z; GetCurrentSessionWinStationType(ulong *,ulong,ulong *)
0x18000b37f  mov     ebx, eax
0x18000b381  test    eax, eax
0x18000b383  jns     loc_18000B2F6
0x18000b389  lea     rdx, aGetcurrentsess_6; "GetCurrentSessionWinStationType failed:"...
0x18000b390  jmp     short loc_18000B32D
0x18000b392  lea     rdx, aGetcurrentsess_1; "GetCurrentSessionInformation failed: 0x"...
0x18000b399  jmp     short loc_18000B32D
```
