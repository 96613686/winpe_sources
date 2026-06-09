# SetSubclassHeader(HWND__ *,SUBCLASS_HEADER *,SUBCLASS_FRAME *)

- ea: `0x180039674`
- end: `0x180039856`
- name: `?SetSubclassHeader@@YA_NPEAUHWND__@@PEAUSUBCLASS_HEADER@@PEAUSUBCLASS_FRAME@@@Z`
- size: `482`
- prototype: `bool __fastcall(HWND hWnd, HANDLE hData, struct SUBCLASS_FRAME *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180039640`
- `0x18008df70`

## callees

- `0x180039674`
- `0x180039de4`
- `0x18005d4d0`
- `0x18008cfac`
- `0x18008d0d4`
- `0x18008d1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003977f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003980a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003977f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003980a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800396d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800396d4`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800396fc`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800396fc`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18003975c`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x180039770`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x18003975c`
- `api-ms-win-core-atoms-l1-1-0!GlobalFindAtomW` at `0x180039770`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180039821`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180039821`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x180039744`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x180039744`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180039730`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180039730`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x1800397d5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x1800397d5`

## string_xrefs

- `0x1800397e9`: `SHCore.Subclass.HeaderRemoveTickCount`
- `0x1800397f7`: `SHCore.Subclass.HeaderRemoveCount`

## pseudocode

```c
bool __fastcall SetSubclassHeader(HWND hWnd, HANDLE hData, struct SUBCLASS_FRAME *a3)
{
  struct SUBCLASS_FRAME *v3; // rdi
  bool i; // r14
  DWORD LastError; // [rsp+40h] [rbp-10h] BYREF
  __int64 PropW; // [rsp+48h] [rbp-8h] BYREF
  HWND v10; // [rsp+80h] [rbp+30h] BYREF
  HANDLE v11; // [rsp+88h] [rbp+38h] BYREF
  struct SUBCLASS_FRAME *v12; // [rsp+90h] [rbp+40h] BYREF
  DWORD v13; // [rsp+98h] [rbp+48h] BYREF

  v12 = a3;
  v11 = hData;
  v10 = hWnd;
  v3 = a3;
  SHCoreTelemetry::SetSubclassHeader<HWND__ * &,SUBCLASS_HEADER * &,SUBCLASS_FRAME * &>(&v10, &v11, &v12);
  for ( i = 1; v3; v3 = (struct SUBCLASS_FRAME *)*((_QWORD *)v3 + 1) )
    *((_QWORD *)v3 + 2) = hData;
  if ( hWnd )
  {
    PropW = 1;
    SetLastError(0);
    LastError = 0;
    if ( hData )
    {
      if ( !g_originalHeaderId )
        g_originalHeaderId = GlobalAddAtomW(L"SHCore.Subclass.Data");
      if ( UpdateTelemetryCountAndTimeStamp(
             hWnd,
             L"SHCore.Subclass.HeaderAttachCount",
             L"SHCore.Subclass.HeaderAttachTickCount")
        && SetPropW(hWnd, L"SHCore.Subclass.Data", hData) )
      {
        PropW = (__int64)GetPropW(hWnd, L"SHCore.Subclass.Data");
        i = PropW == (_QWORD)hData;
        g_originalHeaderAttachCountId = GlobalFindAtomW(L"SHCore.Subclass.HeaderAttachCount");
        g_originalHeaderAttachTickCountId = GlobalFindAtomW(L"SHCore.Subclass.HeaderAttachTickCount");
      }
      else
      {
        LastError = GetLastError();
        i = 0;
      }
      LOBYTE(v13) = i;
      LOBYTE(v12) = IsWindowOnCurrentThread(hWnd);
      SHCoreTelemetry::SHSetWindowSubclassSetProp<HWND__ * &,SUBCLASS_HEADER * &,SUBCLASS_HEADER * &,unsigned int &,unsigned long &,bool &,unsigned short &,bool>(
        (unsigned int)&v10,
        (unsigned int)&v11,
        (unsigned int)&PropW,
        (_DWORD)hData,
        (__int64)&LastError,
        (__int64)&v13);
    }
    else
    {
      if ( !RemovePropW(hWnd, L"SHCore.Subclass.Data") )
        LastError = GetLastError();
      v13 = 0;
      if ( !UpdateTelemetryCountAndTimeStamp(
              hWnd,
              L"SHCore.Subclass.HeaderRemoveCount",
              L"SHCore.Subclass.HeaderRemoveTickCount") )
        v13 = GetLastError();
      LOBYTE(v12) = IsWindowOnCurrentThread(hWnd);
      LODWORD(PropW) = IsWindow(hWnd);
      SHCoreTelemetry::SHSetWindowSubclassRemoveProp<HWND__ * &,unsigned long &,unsigned long &,int,bool>(
        (unsigned int)&v10,
        (unsigned int)&LastError,
        (unsigned int)&v13,
        (unsigned int)&PropW,
        (__int64)&v12);
    }
  }
  return i;
}

```

## disassembly

```asm
0x180039674  mov     [rsp-28h+arg_10], r8
0x180039679  mov     [rsp-28h+arg_8], rdx
0x18003967e  mov     [rsp-28h+arg_0], rcx
0x180039683  push    rbp
0x180039684  push    rbx
0x180039685  push    rsi
0x180039686  push    rdi
0x180039687  push    r14
0x180039689  mov     rbp, rsp
0x18003968c  sub     rsp, 50h
0x180039690  mov     rdi, r8
0x180039693  mov     rsi, rdx
0x180039696  mov     rbx, rcx
0x180039699  lea     r8, [rbp+arg_10]
0x18003969d  lea     rdx, [rbp+arg_8]
0x1800396a1  lea     rcx, [rbp+arg_0]
0x1800396a5  call    ??$SetSubclassHeader@AEAPEAUHWND__@@AEAPEAUSUBCLASS_HEADER@@AEAPEAUSUBCLASS_FRAME@@@SHCoreTelemetry@@SAXAEAPEAUHWND__@@AEAPEAUSUBCLASS_HEADER@@AEAPEAUSUBCLASS_FRAME@@@Z; SHCoreTelemetry::SetSubclassHeader<HWND__ * &,SUBCLASS_HEADER * &,SUBCLASS_FRAME * &>(HWND__ * &,SUBCLASS_HEADER * &,SUBCLASS_FRAME * &)
0x1800396aa  mov     r14d, 1
0x1800396b0  test    rdi, rdi
0x1800396b3  jz      short loc_1800396C5
0x1800396b5  mov     [rdi+10h], rsi
0x1800396b9  mov     rax, [rdi+8]
0x1800396bd  mov     rdi, rax
0x1800396c0  test    rax, rax
0x1800396c3  jnz     short loc_1800396B5
0x1800396c5  test    rbx, rbx
0x1800396c8  jz      loc_180039848
0x1800396ce  xor     ecx, ecx; dwErrCode
0x1800396d0  mov     [rbp+var_8], r14
0x1800396d4  call    cs:__imp_SetLastError
0x1800396da  mov     [rbp+var_10], 0
0x1800396e1  test    rsi, rsi
0x1800396e4  jz      loc_1800397CB
0x1800396ea  xor     eax, eax
0x1800396ec  cmp     ax, cs:?g_originalHeaderId@@3GA; ushort g_originalHeaderId
0x1800396f3  jnz     short loc_180039709
0x1800396f5  lea     rcx, aShcoreSubclass_5; "SHCore.Subclass.Data"
0x1800396fc  call    cs:__imp_GlobalAddAtomW
0x180039702  mov     cs:?g_originalHeaderId@@3GA, ax; ushort g_originalHeaderId
0x180039709  lea     r8, aShcoreSubclass_4; "SHCore.Subclass.HeaderAttachTickCount"
0x180039710  mov     rcx, rbx; hWnd
0x180039713  lea     rdx, aShcoreSubclass_1; "SHCore.Subclass.HeaderAttachCount"
0x18003971a  call    ?UpdateTelemetryCountAndTimeStamp@@YA_NPEAUHWND__@@PEBG1@Z; UpdateTelemetryCountAndTimeStamp(HWND__ *,ushort const *,ushort const *)
0x18003971f  test    al, al
0x180039721  jz      short loc_18003977F
0x180039723  mov     r8, rsi; hData
0x180039726  lea     rdx, aShcoreSubclass_5; "SHCore.Subclass.Data"
0x18003972d  mov     rcx, rbx; hWnd
0x180039730  call    cs:__imp_SetPropW
0x180039736  test    eax, eax
0x180039738  jz      short loc_18003977F
0x18003973a  lea     rdx, aShcoreSubclass_5; "SHCore.Subclass.Data"
0x180039741  mov     rcx, rbx; hWnd
0x180039744  call    cs:__imp_GetPropW
0x18003974a  cmp     rax, rsi
0x18003974d  mov     [rbp+var_8], rax
0x180039751  lea     rcx, aShcoreSubclass_1; "SHCore.Subclass.HeaderAttachCount"
0x180039758  setz    r14b
0x18003975c  call    cs:__imp_GlobalFindAtomW
0x180039762  lea     rcx, aShcoreSubclass_4; "SHCore.Subclass.HeaderAttachTickCount"
0x180039769  mov     cs:?g_originalHeaderAttachCountId@@3GA, ax; ushort g_originalHeaderAttachCountId
0x180039770  call    cs:__imp_GlobalFindAtomW
0x180039776  mov     cs:?g_originalHeaderAttachTickCountId@@3GA, ax; ushort g_originalHeaderAttachTickCountId
0x18003977d  jmp     short loc_18003978B
0x18003977f  call    cs:__imp_GetLastError
0x180039785  mov     [rbp+var_10], eax
0x180039788  xor     r14b, r14b
0x18003978b  mov     rcx, rbx; hWnd
0x18003978e  mov     byte ptr [rbp+arg_18], r14b
0x180039792  call    ?IsWindowOnCurrentThread@@YA_NPEAUHWND__@@@Z; IsWindowOnCurrentThread(HWND__ *)
0x180039797  mov     byte ptr [rbp+arg_10], al
0x18003979a  lea     r8, [rbp+var_8]
0x18003979e  lea     rax, [rbp+arg_10]
0x1800397a2  mov     r9, rsi
0x1800397a5  mov     [rsp+50h+var_18], rax
0x1800397aa  lea     rdx, [rbp+arg_8]
0x1800397ae  lea     rax, [rbp+arg_18]
0x1800397b2  mov     [rsp+50h+var_28], rax
0x1800397b7  lea     rcx, [rbp+arg_0]
0x1800397bb  lea     rax, [rbp+var_10]
0x1800397bf  mov     [rsp+50h+var_30], rax
0x1800397c4  call    ??$SHSetWindowSubclassSetProp@AEAPEAUHWND__@@AEAPEAUSUBCLASS_HEADER@@AEAPEAU2@AEAIAEAKAEA_NAEAG_N@SHCoreTelemetry@@SAXAEAPEAUHWND__@@AEAPEAUSUBCLASS_HEADER@@1AEAIAEAKAEA_NAEAG$$QEA_N@Z; SHCoreTelemetry::SHSetWindowSubclassSetProp<HWND__ * &,SUBCLASS_HEADER * &,SUBCLASS_HEADER * &,uint &,ulong &,bool &,ushort &,bool>(HWND__ * &,SUBCLASS_HEADER * &,SUBCLASS_HEADER * &,uint &,ulong &,bool &,ushort &,bool &&)
0x1800397c9  jmp     short loc_180039848
0x1800397cb  lea     rdx, aShcoreSubclass_5; "SHCore.Subclass.Data"
0x1800397d2  mov     rcx, rbx; hWnd
0x1800397d5  call    cs:__imp_RemovePropW
0x1800397db  test    rax, rax
0x1800397de  jnz     short loc_1800397E9
0x1800397e0  call    cs:__imp_GetLastError
0x1800397e6  mov     [rbp+var_10], eax
0x1800397e9  lea     r8, aShcoreSubclass; "SHCore.Subclass.HeaderRemoveTickCount"
0x1800397f0  mov     [rbp+arg_18], 0
0x1800397f7  lea     rdx, aShcoreSubclass_2; "SHCore.Subclass.HeaderRemoveCount"
0x1800397fe  mov     rcx, rbx; hWnd
0x180039801  call    ?UpdateTelemetryCountAndTimeStamp@@YA_NPEAUHWND__@@PEBG1@Z; UpdateTelemetryCountAndTimeStamp(HWND__ *,ushort const *,ushort const *)
0x180039806  test    al, al
0x180039808  jnz     short loc_180039813
0x18003980a  call    cs:__imp_GetLastError
0x180039810  mov     [rbp+arg_18], eax
0x180039813  mov     rcx, rbx; hWnd
0x180039816  call    ?IsWindowOnCurrentThread@@YA_NPEAUHWND__@@@Z; IsWindowOnCurrentThread(HWND__ *)
0x18003981b  mov     rcx, rbx; hWnd
0x18003981e  mov     byte ptr [rbp+arg_10], al
0x180039821  call    cs:__imp_IsWindow
0x180039827  mov     dword ptr [rbp+var_8], eax
0x18003982a  lea     r9, [rbp+var_8]
0x18003982e  lea     rax, [rbp+arg_10]
0x180039832  lea     r8, [rbp+arg_18]
0x180039836  mov     [rsp+50h+var_30], rax
0x18003983b  lea     rdx, [rbp+var_10]
0x18003983f  lea     rcx, [rbp+arg_0]
0x180039843  call    ??$SHSetWindowSubclassRemoveProp@AEAPEAUHWND__@@AEAKAEAKH_N@SHCoreTelemetry@@SAXAEAPEAUHWND__@@AEAK1$$QEAH$$QEA_N@Z; SHCoreTelemetry::SHSetWindowSubclassRemoveProp<HWND__ * &,ulong &,ulong &,int,bool>(HWND__ * &,ulong &,ulong &,int &&,bool &&)
0x180039848  mov     al, r14b
0x18003984b  add     rsp, 50h
0x18003984f  pop     r14
0x180039851  pop     rdi
0x180039852  pop     rsi
0x180039853  pop     rbx
0x180039854  pop     rbp
0x180039855  retn
```
