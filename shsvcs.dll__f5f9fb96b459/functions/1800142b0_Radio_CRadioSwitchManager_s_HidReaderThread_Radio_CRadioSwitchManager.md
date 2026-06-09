# Radio::CRadioSwitchManager::s_HidReaderThread(Radio::CRadioSwitchManager *)

- ea: `0x1800142b0`
- end: `0x1800147e3`
- name: `?s_HidReaderThread@CRadioSwitchManager@Radio@@CAKPEAV12@@Z`
- size: `1331`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, service_task, installer_update, broker_com_uri`

## callees

- `0x1800142b0`
- `0x180019c44`
- `0x18002b2f4`
- `0x18002b4e8`
- `0x18002b578`
- `0x180032c6a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800143f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800143f3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800144dc`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800144dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800146d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800146d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800146e4`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001453e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001453e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014471`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014471`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18001451f`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18001451f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800146ea`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014761`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800146ea`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800147c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800147c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800147c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800147c9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001433b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001433b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800143d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800143d2`
- `Rmapi!__imp_?SystemRadioChanged@@YAXW4RADIO_SWITCH_CHANGE@@@Z` at `0x18001464e`
- `Rmapi!__imp_?SystemRadioChanged@@YAXW4RADIO_SWITCH_CHANGE@@@Z` at `0x18001464e`
- `HID!HidP_GetUsages` at `0x1800145d1`
- `HID!HidP_GetUsages` at `0x1800145d1`
- `HID!HidP_MaxUsageListLength` at `0x180014395`
- `HID!HidP_MaxUsageListLength` at `0x180014395`

## pseudocode

```c
__int64 __fastcall Radio::CRadioSwitchManager::s_HidReaderThread(unsigned __int16 *Parameter)
{
  SIZE_T v1; // r14
  USHORT *v2; // rbx
  void *Report; // rdi
  __int16 v5; // r15
  SIZE_T v6; // rcx
  ULONG v7; // eax
  __int64 v8; // r12
  unsigned int v9; // ecx
  HANDLE EventW; // rax
  void *v11; // rbp
  char v12; // r13
  __int64 v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  DWORD LastError; // eax
  DWORD v17; // eax
  unsigned __int8 v18; // dl
  Radio::CRadioSwitchManager *v19; // rcx
  _QWORD *v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  HANDLE v25; // [rsp+48h] [rbp-80h]
  __int128 Handles; // [rsp+50h] [rbp-78h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-68h] BYREF
  __int16 v28; // [rsp+D0h] [rbp+8h]
  DWORD NumberOfBytesRead; // [rsp+D8h] [rbp+10h] BYREF
  ULONG UsageLength; // [rsp+E0h] [rbp+18h] BYREF
  PUSAGE UsageList; // [rsp+E8h] [rbp+20h]

  v1 = Parameter[294];
  NumberOfBytesRead = 0;
  UsageLength = 0;
  v2 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  Report = 0;
  v28 = v1;
  Handles = 0;
  v5 = 200;
  if ( *((_DWORD *)Parameter + 162) != 4 )
    v5 = 198;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37);
  }
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    if ( (_WORD)v1 )
    {
      v6 = v1;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v1) )
        goto LABEL_66;
    }
    else
    {
      v6 = 0;
    }
    Report = CoTaskMemAlloc(v6);
    if ( Report )
    {
      v7 = HidP_MaxUsageListLength(HidP_Input, 1u, *((PHIDP_PREPARSED_DATA *)Parameter + 72));
      v8 = v7;
      if ( v7 )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v7 < 2 )
          goto LABEL_62;
        v9 = 2 * v7;
        if ( 2 * (unsigned __int64)v7 > 0x7FFFFFFF )
          goto LABEL_62;
      }
      else
      {
        v9 = 0;
      }
      v2 = (USHORT *)CoTaskMemAlloc(v9);
      if ( v2 )
      {
        EventW = CreateEventW(0, 1, 1, 0);
        v25 = EventW;
        v11 = EventW;
        if ( EventW )
        {
          *((_QWORD *)&Handles + 1) = *((_QWORD *)Parameter + 160);
          v12 = 1;
          *(_QWORD *)&Handles = EventW;
          memset(&Overlapped, 0, 24);
          Overlapped.hEvent = EventW;
          UsageList = v2;
LABEL_19:
          while ( v12 )
          {
            memset_0(Report, 0, (unsigned __int16)v1);
            if ( ReadFile(*((HANDLE *)Parameter + 6), Report, (unsigned __int16)v1, &NumberOfBytesRead, &Overlapped) )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v15 = 38;
LABEL_37:
                WPP_SF_d(v14[2], v15, v13, NumberOfBytesRead);
              }
            }
            else
            {
              LastError = GetLastError();
              if ( LastError != 997 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      41,
                      WPP_8d8096123d673a836441f61c56de919a_Traceguids,
                      LastError);
                    v20 = WPP_GLOBAL_Control;
                  }
                  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 4) != 0 && *((_BYTE *)v20 + 25) >= 2u )
                    WPP_SF_(v20[2], 42);
                }
                WaitForSingleObject(*((HANDLE *)Parameter + 160), 0xFFFFFFFF);
                break;
              }
              while ( 1 )
              {
                v17 = WaitForMultipleObjectsEx(2u, (const HANDLE *)&Handles, 0, 0x1388u, 0);
                if ( !v17 )
                  break;
                if ( v17 == 1 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40);
                  }
                  v12 = 0;
                  CancelIo(*((HANDLE *)Parameter + 6));
                  goto LABEL_19;
                }
              }
              GetOverlappedResult(*((HANDLE *)Parameter + 6), &Overlapped, &NumberOfBytesRead, 0);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v15 = 39;
                goto LABEL_37;
              }
            }
            UsageLength = v8;
            memset_0(UsageList, 0, 2 * v8);
            if ( HidP_GetUsages(
                   HidP_Input,
                   1u,
                   0,
                   UsageList,
                   &UsageLength,
                   *((PHIDP_PREPARSED_DATA *)Parameter + 72),
                   (PCHAR)Report,
                   NumberOfBytesRead) == 1114112 )
            {
              v18 = 0;
              v19 = 0;
              if ( UsageLength )
              {
                do
                {
                  if ( v2[(_QWORD)v19] == v5 )
                    v18 = 1;
                  v19 = (Radio::CRadioSwitchManager *)(unsigned int)((_DWORD)v19 + 1);
                }
                while ( (_DWORD)v19 != UsageLength );
                LOWORD(v1) = v28;
                v11 = v25;
              }
              if ( *((_DWORD *)Parameter + 162) == 4 )
                Radio::CRadioSwitchManager::_UpdateIfSliderSwitchChanged(v19, v18);
              else
                SystemRadioChanged(2);
            }
            else
            {
              UsageLength = 0;
            }
          }
          CloseHandle(v11);
          CoUninitialize();
          goto LABEL_76;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_71;
        }
        v22 = 43;
        goto LABEL_70;
      }
LABEL_62:
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v22 = 44;
LABEL_70:
      WPP_SF_(v21[2], v22);
LABEL_71:
      CoUninitialize();
LABEL_76:
      v23 = WPP_GLOBAL_Control;
      goto LABEL_77;
    }
LABEL_66:
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_71;
    }
    v22 = 45;
    goto LABEL_70;
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_81;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46);
    goto LABEL_76;
  }
LABEL_77:
  if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 4) != 0 && *((_BYTE *)v23 + 25) >= 4u )
    WPP_SF_(v23[2], 47);
LABEL_81:
  CoTaskMemFree(Report);
  CoTaskMemFree(v2);
  return 0;
}

```

## disassembly

```asm
0x1800142b0  mov     rax, rsp
0x1800142b3  push    rbx
0x1800142b4  push    rbp
0x1800142b5  push    rsi
0x1800142b6  push    rdi
0x1800142b7  push    r13
0x1800142b9  push    r14
0x1800142bb  push    r15
0x1800142bd  sub     rsp, 90h
0x1800142c4  movzx   r14d, word ptr [rcx+24Ch]
0x1800142cc  xor     ebp, ebp
0x1800142ce  xorps   xmm0, xmm0
0x1800142d1  mov     [rax+10h], ebp
0x1800142d4  mov     [rax+18h], ebp
0x1800142d7  mov     ebx, ebp
0x1800142d9  movups  xmmword ptr [rax-68h], xmm0
0x1800142dd  mov     edi, ebp
0x1800142df  mov     [rsp+0C8h+arg_0], r14w
0x1800142e8  movups  xmmword ptr [rax-58h], xmm0
0x1800142ec  mov     rsi, rcx
0x1800142ef  movups  xmmword ptr [rax-78h], xmm0
0x1800142f3  cmp     dword ptr [rcx+288h], 4
0x1800142fa  lea     r13, WPP_GLOBAL_Control
0x180014301  mov     rcx, cs:WPP_GLOBAL_Control
0x180014308  mov     eax, 0C6h
0x18001430d  mov     r15d, 0C8h
0x180014313  cmovnz  r15w, ax
0x180014318  cmp     rcx, r13
0x18001431b  jz      short loc_180014337
0x18001431d  test    byte ptr [rcx+1Ch], 4
0x180014321  jz      short loc_180014337
0x180014323  cmp     byte ptr [rcx+19h], 4
0x180014327  jb      short loc_180014337
0x180014329  mov     rcx, [rcx+10h]
0x18001432d  mov     edx, 25h ; '%'
0x180014332  call    WPP_SF_
0x180014337  xor     edx, edx; dwCoInit
0x180014339  xor     ecx, ecx; pvReserved
0x18001433b  call    cs:__imp_CoInitializeEx
0x180014341  test    eax, eax
0x180014343  js      loc_180014771
0x180014349  mov     [rsp+0C8h+var_40], r12
0x180014351  test    r14w, r14w
0x180014355  jnz     short loc_18001435C
0x180014357  mov     rcx, rbp
0x18001435a  jmp     short loc_180014375
0x18001435c  xor     edx, edx
0x18001435e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014365  div     r14
0x180014368  mov     rcx, r14; cb
0x18001436b  cmp     rax, 1
0x18001436f  jb      loc_18001473B
0x180014375  call    cs:__imp_CoTaskMemAlloc
0x18001437b  mov     rdi, rax
0x18001437e  test    rax, rax
0x180014381  jz      loc_18001473B
0x180014387  mov     r8, [rsi+240h]; PreparsedData
0x18001438e  mov     edx, 1; UsagePage
0x180014393  xor     ecx, ecx; ReportType
0x180014395  call    cs:__imp_HidP_MaxUsageListLength
0x18001439b  mov     r12d, eax
0x18001439e  test    eax, eax
0x1800143a0  jnz     short loc_1800143A7
0x1800143a2  mov     rcx, rbp
0x1800143a5  jmp     short loc_1800143D0
0x1800143a7  xor     edx, edx
0x1800143a9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800143b0  div     r12
0x1800143b3  mov     rcx, r12
0x1800143b6  cmp     rax, 2
0x1800143ba  jb      loc_18001471C
0x1800143c0  add     rcx, rcx
0x1800143c3  cmp     rcx, 7FFFFFFFh
0x1800143ca  ja      loc_18001471C
0x1800143d0  mov     ecx, ecx; cb
0x1800143d2  call    cs:__imp_CoTaskMemAlloc
0x1800143d8  mov     rbx, rax
0x1800143db  test    rax, rax
0x1800143de  jz      loc_18001471C
0x1800143e4  mov     eax, 1
0x1800143e9  xor     r9d, r9d; lpName
0x1800143ec  mov     r8d, eax; bInitialState
0x1800143ef  mov     edx, eax; bManualReset
0x1800143f1  xor     ecx, ecx; lpEventAttributes
0x1800143f3  call    cs:__imp_CreateEventW
0x1800143f9  mov     [rsp+0C8h+var_80], rax
0x1800143fe  mov     rbp, rax
0x180014401  test    rax, rax
0x180014404  jz      loc_1800146FD
0x18001440a  mov     rcx, [rsi+500h]
0x180014411  xorps   xmm0, xmm0
0x180014414  mov     [rsp+0C8h+var_70], rcx
0x180014419  mov     r13b, 1
0x18001441c  movdqu  xmmword ptr [rsp+0C8h+Overlapped.InternalHigh], xmm0
0x180014422  mov     [rsp+0C8h+Handles], rax
0x180014427  mov     [rsp+0C8h+Overlapped.Internal], 0
0x180014430  mov     [rsp+0C8h+Overlapped.hEvent], rax
0x180014435  mov     [rsp+0C8h+UsageList], rbx
0x18001443d  test    r13b, r13b
0x180014440  jz      loc_1800146DA
0x180014446  movzx   r8d, r14w; Size
0x18001444a  xor     edx, edx; Val
0x18001444c  mov     rcx, rdi; void *
0x18001444f  call    memset_0
0x180014454  mov     rcx, [rsi+30h]; hFile
0x180014458  lea     rax, [rsp+0C8h+Overlapped]
0x18001445d  movzx   r8d, r14w; nNumberOfBytesToRead
0x180014461  lea     r9, [rsp+0C8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180014469  mov     rdx, rdi; lpBuffer
0x18001446c  mov     [rsp+0C8h+lpOverlapped], rax; lpOverlapped
0x180014471  call    cs:__imp_ReadFile
0x180014477  test    eax, eax
0x180014479  jz      short loc_1800144B0
0x18001447b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014482  lea     rax, WPP_GLOBAL_Control
0x180014489  cmp     rcx, rax
0x18001448c  jz      loc_180014579
0x180014492  test    byte ptr [rcx+1Ch], 4
0x180014496  jz      loc_180014579
0x18001449c  cmp     byte ptr [rcx+19h], 4
0x1800144a0  jb      loc_180014579
0x1800144a6  mov     edx, 26h ; '&'
0x1800144ab  jmp     loc_180014568
0x1800144b0  call    cs:__imp_GetLastError
0x1800144b6  cmp     eax, 3E5h
0x1800144bb  jnz     loc_180014669
0x1800144c1  mov     r9d, 1388h; dwMilliseconds
0x1800144c7  mov     dword ptr [rsp+0C8h+lpOverlapped], 0; bAlertable
0x1800144cf  xor     r8d, r8d; bWaitAll
0x1800144d2  lea     rdx, [rsp+0C8h+Handles]; lpHandles
0x1800144d7  mov     ecx, 2; nCount
0x1800144dc  call    cs:__imp_WaitForMultipleObjectsEx
0x1800144e2  test    eax, eax
0x1800144e4  jz      short loc_18001452A
0x1800144e6  cmp     eax, 1
0x1800144e9  jnz     short loc_1800144C1
0x1800144eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144f2  lea     rax, WPP_GLOBAL_Control
0x1800144f9  cmp     rcx, rax
0x1800144fc  jz      short loc_180014518
0x1800144fe  test    byte ptr [rcx+1Ch], 4
0x180014502  jz      short loc_180014518
0x180014504  cmp     byte ptr [rcx+19h], 4
0x180014508  jb      short loc_180014518
0x18001450a  mov     rcx, [rcx+10h]
0x18001450e  mov     edx, 28h ; '('
0x180014513  call    WPP_SF_
0x180014518  mov     rcx, [rsi+30h]; hFile
0x18001451c  xor     r13b, r13b
0x18001451f  call    cs:__imp_CancelIo
0x180014525  jmp     loc_18001443D
0x18001452a  mov     rcx, [rsi+30h]; hFile
0x18001452e  lea     r8, [rsp+0C8h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x180014536  xor     r9d, r9d; bWait
0x180014539  lea     rdx, [rsp+0C8h+Overlapped]; lpOverlapped
0x18001453e  call    cs:__imp_GetOverlappedResult
0x180014544  mov     rcx, cs:WPP_GLOBAL_Control
0x18001454b  lea     rax, WPP_GLOBAL_Control
0x180014552  cmp     rcx, rax
0x180014555  jz      short loc_180014579
0x180014557  test    byte ptr [rcx+1Ch], 4
0x18001455b  jz      short loc_180014579
0x18001455d  cmp     byte ptr [rcx+19h], 5
0x180014561  jb      short loc_180014579
0x180014563  mov     edx, 27h ; '''
0x180014568  mov     r9d, [rsp+0C8h+NumberOfBytesRead]
0x180014570  mov     rcx, [rcx+10h]
0x180014574  call    WPP_SF_d
0x180014579  mov     rcx, [rsp+0C8h+UsageList]; void *
0x180014581  mov     r8, r12
0x180014584  add     r8, r8; Size
0x180014587  mov     [rsp+0C8h+UsageLength], r12d
0x18001458f  xor     edx, edx; Val
0x180014591  call    memset_0
0x180014596  mov     eax, [rsp+0C8h+NumberOfBytesRead]
0x18001459d  xor     r8d, r8d; LinkCollection
0x1800145a0  mov     r9, [rsp+0C8h+UsageList]; UsageList
0x1800145a8  mov     edx, 1; UsagePage
0x1800145ad  mov     [rsp+0C8h+ReportLength], eax; ReportLength
0x1800145b1  xor     ecx, ecx; ReportType
0x1800145b3  mov     rax, [rsi+240h]
0x1800145ba  mov     [rsp+0C8h+Report], rdi; Report
0x1800145bf  mov     [rsp+0C8h+PreparsedData], rax; PreparsedData
0x1800145c4  lea     rax, [rsp+0C8h+UsageLength]
0x1800145cc  mov     [rsp+0C8h+lpOverlapped], rax; UsageLength
0x1800145d1  call    cs:__imp_HidP_GetUsages
0x1800145d7  cmp     eax, 110000h
0x1800145dc  jnz     short loc_180014659
0x1800145de  mov     r8d, [rsp+0C8h+UsageLength]
0x1800145e6  xor     dl, dl
0x1800145e8  xor     ecx, ecx
0x1800145ea  test    r8d, r8d
0x1800145ed  jz      short loc_180014636
0x1800145ef  mov     rbp, [rsp+0C8h+UsageList]
0x1800145f7  mov     r14d, 1
0x1800145fd  cmp     [rbx+rcx*2], r15w
0x180014602  movzx   edx, dl
0x180014605  cmovz   edx, r14d; bool
0x180014609  inc     ecx; this
0x18001460b  cmp     ecx, r8d
0x18001460e  jnz     short loc_1800145FD
0x180014610  movzx   r14d, [rsp+0C8h+arg_0]
0x180014619  mov     [rsp+0C8h+UsageList], rbp
0x180014621  mov     rax, [rsp+0C8h+UsageList]
0x180014629  mov     rbp, [rsp+0C8h+var_80]
0x18001462e  mov     [rsp+0C8h+UsageList], rax
0x180014636  cmp     dword ptr [rsi+288h], 4
0x18001463d  jnz     short loc_180014649
0x18001463f  call    ?_UpdateIfSliderSwitchChanged@CRadioSwitchManager@Radio@@AEAAX_N@Z; Radio::CRadioSwitchManager::_UpdateIfSliderSwitchChanged(bool)
0x180014644  jmp     loc_18001443D
0x180014649  mov     ecx, 2
0x18001464e  call    cs:__imp_?SystemRadioChanged@@YAXW4RADIO_SWITCH_CHANGE@@@Z; SystemRadioChanged(RADIO_SWITCH_CHANGE)
0x180014654  jmp     loc_18001443D
0x180014659  mov     [rsp+0C8h+UsageLength], 0
0x180014664  jmp     loc_18001443D
0x180014669  mov     rcx, cs:WPP_GLOBAL_Control
0x180014670  lea     r13, WPP_GLOBAL_Control
0x180014677  cmp     rcx, r13
0x18001467a  jz      short loc_1800146C6
0x18001467c  test    byte ptr [rcx+1Ch], 4
0x180014680  jz      short loc_1800146A7
0x180014682  cmp     byte ptr [rcx+19h], 2
0x180014686  jb      short loc_1800146A7
0x180014688  mov     rcx, [rcx+10h]
0x18001468c  lea     r8, WPP_8d8096123d673a836441f61c56de919a_Traceguids
0x180014693  mov     edx, 29h ; ')'
0x180014698  mov     r9d, eax
0x18001469b  call    WPP_SF_D
0x1800146a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146a7  cmp     rcx, r13
0x1800146aa  jz      short loc_1800146C6
0x1800146ac  test    byte ptr [rcx+1Ch], 4
0x1800146b0  jz      short loc_1800146C6
0x1800146b2  cmp     byte ptr [rcx+19h], 2
0x1800146b6  jb      short loc_1800146C6
0x1800146b8  mov     rcx, [rcx+10h]
0x1800146bc  mov     edx, 2Ah ; '*'
0x1800146c1  call    WPP_SF_
0x1800146c6  mov     rcx, [rsi+500h]; hHandle
0x1800146cd  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800146d2  call    cs:__imp_WaitForSingleObject
0x1800146d8  jmp     short loc_1800146E1
0x1800146da  lea     r13, WPP_GLOBAL_Control
0x1800146e1  mov     rcx, rbp; hObject
0x1800146e4  call    cs:__imp_CloseHandle
0x1800146ea  call    cs:__imp_CoUninitialize
0x1800146f0  mov     r12, [rsp+0C8h+var_40]
0x1800146f8  jmp     loc_180014797
0x1800146fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180014704  cmp     rcx, r13
0x180014707  jz      short loc_180014761
0x180014709  test    byte ptr [rcx+1Ch], 4
0x18001470d  jz      short loc_180014761
0x18001470f  cmp     byte ptr [rcx+19h], 2
0x180014713  jb      short loc_180014761
0x180014715  mov     edx, 2Bh ; '+'
0x18001471a  jmp     short loc_180014758
0x18001471c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014723  cmp     rcx, r13
0x180014726  jz      short loc_180014761
0x180014728  test    byte ptr [rcx+1Ch], 4
0x18001472c  jz      short loc_180014761
0x18001472e  cmp     byte ptr [rcx+19h], 2
0x180014732  jb      short loc_180014761
0x180014734  mov     edx, 2Ch ; ','
0x180014739  jmp     short loc_180014758
0x18001473b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014742  cmp     rcx, r13
0x180014745  jz      short loc_180014761
0x180014747  test    byte ptr [rcx+1Ch], 4
0x18001474b  jz      short loc_180014761
0x18001474d  cmp     byte ptr [rcx+19h], 2
0x180014751  jb      short loc_180014761
0x180014753  mov     edx, 2Dh ; '-'
0x180014758  mov     rcx, [rcx+10h]
0x18001475c  call    WPP_SF_
0x180014761  call    cs:__imp_CoUninitialize
0x180014767  mov     r12, [rsp+0C8h+var_40]
0x18001476f  jmp     short loc_180014797
0x180014771  mov     rcx, cs:WPP_GLOBAL_Control
0x180014778  cmp     rcx, r13
0x18001477b  jz      short loc_1800147BD
0x18001477d  test    byte ptr [rcx+1Ch], 4
0x180014781  jz      short loc_18001479E
0x180014783  cmp     byte ptr [rcx+19h], 4
0x180014787  jb      short loc_18001479E
0x180014789  mov     rcx, [rcx+10h]
0x18001478d  mov     edx, 2Eh ; '.'
0x180014792  call    WPP_SF_
0x180014797  mov     rcx, cs:WPP_GLOBAL_Control
0x18001479e  cmp     rcx, r13
0x1800147a1  jz      short loc_1800147BD
0x1800147a3  test    byte ptr [rcx+1Ch], 4
0x1800147a7  jz      short loc_1800147BD
0x1800147a9  cmp     byte ptr [rcx+19h], 4
0x1800147ad  jb      short loc_1800147BD
0x1800147af  mov     rcx, [rcx+10h]
0x1800147b3  mov     edx, 2Fh ; '/'
0x1800147b8  call    WPP_SF_
0x1800147bd  mov     rcx, rdi; pv
  ... truncated ...
```
