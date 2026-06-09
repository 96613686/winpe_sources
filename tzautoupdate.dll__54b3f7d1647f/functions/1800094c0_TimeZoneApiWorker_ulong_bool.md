# TimeZoneApiWorker(ulong,bool)

- ea: `0x1800094c0`
- end: `0x1800096ad`
- name: `?TimeZoneApiWorker@@YAJK_N@Z`
- size: `493`
- prototype: `signed int __fastcall(unsigned int, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000bc10`
- `0x18000bc20`

## callees

- `0x180001010`
- `0x180001120`
- `0x180001510`
- `0x1800015c0`
- `0x18000166c`
- `0x180002050`
- `0x180004018`
- `0x18000885c`
- `0x1800094c0`
- `0x18000acdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800094e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800094e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094f2`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800095e8`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800095e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000968e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000968e`

## string_xrefs

- `0x18000956a`: `TZ auto update API failed to initialize.`
- `0x180009670`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x180009615`: `TZ auto update API timed out.`

## pseudocode

```c
signed int __fastcall TimeZoneApiWorker(unsigned int a1, bool a2)
{
  signed int result; // eax
  TzautoupdateWorker *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  HRESULT v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  int lpdwindex; // [rsp+20h] [rbp-50h]
  HANDLE pHandles; // [rsp+40h] [rbp-30h] BYREF
  __int64 v24; // [rsp+48h] [rbp-28h] BYREF
  __int64 v25; // [rsp+50h] [rbp-20h] BYREF
  HANDLE *p_pHandles; // [rsp+58h] [rbp-18h] BYREF
  char v27; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  DWORD dwindex; // [rsp+90h] [rbp+20h] BYREF
  const char *v30; // [rsp+98h] [rbp+28h] BYREF

  pHandles = CreateEventW(0, 1, 0, 0);
  if ( pHandles )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
    p_pHandles = &pHandles;
    v27 = 1;
    v5 = (TzautoupdateWorker *)operator new(0x1B0u);
    v30 = (const char *)v5;
    if ( v5 )
      v5 = TzautoupdateWorker::TzautoupdateWorker(v5, a1, a2, pHandles);
    p_pHandles = (HANDLE *)v5;
    if ( v5 )
    {
      v12 = a1 + 1;
      if ( (unsigned int)v12 >= a1 )
      {
        if ( (unsigned __int64)(1000 * v12) <= 0xFFFFFFFF )
        {
          dwindex = 0;
          v11 = CoWaitForMultipleHandles(0x18u, 1000 * v12, 1u, &pHandles, &dwindex);
          if ( v11 >= 0 )
          {
            v11 = 0;
          }
          else
          {
            if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL, v15) )
            {
              LODWORD(v30) = v11;
              v24 = (__int64)"TZ auto update API timed out.";
              v25 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v16,
                (unsigned int)byte_180028051,
                v17,
                v18,
                (__int64)&v25,
                (__int64)&v24,
                (__int64)&v30);
            }
            if ( v11 == -2147417835 )
              v11 = -2147024638;
          }
          goto LABEL_24;
        }
        v13 = 75;
      }
      else
      {
        v13 = 70;
      }
      v11 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
        (const char *)0x80070216LL,
        lpdwindex);
    }
    else
    {
      if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
      {
        v30 = "TZ auto update API failed to initialize.";
        v24 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          v8,
          (unsigned int)&unk_180028560,
          v9,
          v10,
          (__int64)&v24,
          (__int64)&v30);
      }
      v11 = -2147024882;
    }
LABEL_24:
    std::unique_ptr<TzautoupdateWorker>::_Delete(&p_pHandles);
    CloseHandle(pHandles);
    TraceLoggingUnregister_EventUnregister(v20, v19, v21);
    return v11;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800094c0  mov     [rsp-8+arg_0], rbx
0x1800094c5  mov     [rsp-8+arg_8], rdi
0x1800094ca  push    rbp
0x1800094cb  mov     rbp, rsp
0x1800094ce  sub     rsp, 70h
0x1800094d2  mov     dil, dl
0x1800094d5  mov     ebx, ecx
0x1800094d7  xor     r9d, r9d; lpName
0x1800094da  xor     r8d, r8d; bInitialState
0x1800094dd  lea     edx, [r9+1]; bManualReset
0x1800094e1  xor     ecx, ecx; lpEventAttributes
0x1800094e3  call    cs:__imp_CreateEventW
0x1800094e9  mov     [rbp+pHandles], rax
0x1800094ed  test    rax, rax
0x1800094f0  jnz     short loc_18000950D
0x1800094f2  call    cs:__imp_GetLastError
0x1800094f8  test    eax, eax
0x1800094fa  jle     loc_18000969B
0x180009500  movzx   eax, ax
0x180009503  or      eax, 80070000h
0x180009508  jmp     loc_18000969B
0x18000950d  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180009512  lea     rax, [rbp+pHandles]
0x180009516  mov     [rbp+var_18], rax
0x18000951a  mov     [rbp+var_10], 1
0x18000951e  mov     ecx, 1B0h; Size
0x180009523  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009528  mov     [rbp+arg_18], rax
0x18000952c  test    rax, rax
0x18000952f  jz      short loc_180009543
0x180009531  mov     r9, [rbp+pHandles]; void *
0x180009535  mov     r8b, dil; bool
0x180009538  mov     edx, ebx; unsigned int
0x18000953a  mov     rcx, rax; this
0x18000953d  call    ??0TzautoupdateWorker@@QEAA@K_NPEAX@Z; TzautoupdateWorker::TzautoupdateWorker(ulong,bool,void *)
0x180009542  nop
0x180009543  mov     [rbp+var_18], rax
0x180009547  test    rax, rax
0x18000954a  jnz     short loc_1800095A5
0x18000954c  mov     eax, cs:dword_180030000
0x180009552  cmp     eax, 5
0x180009555  jbe     short loc_18000959B
0x180009557  mov     rdx, 400000000000h
0x180009561  call    _tlgKeywordOn
0x180009566  test    al, al
0x180009568  jz      short loc_18000959B
0x18000956a  lea     rax, aTzAutoUpdateAp; "TZ auto update API failed to initialize"...
0x180009571  mov     [rbp+arg_18], rax
0x180009575  mov     [rbp+var_28], 1000000h
0x18000957d  lea     rax, [rbp+arg_18]
0x180009581  mov     [rsp+70h+var_48], rax
0x180009586  lea     rax, [rbp+var_28]
0x18000958a  mov     [rsp+70h+lpdwindex], rax
0x18000958f  lea     rdx, unk_180028560
0x180009596  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18000959b  mov     ebx, 8007000Eh
0x1800095a0  jmp     loc_180009680
0x1800095a5  lea     eax, [rbx+1]
0x1800095a8  cmp     eax, ebx
0x1800095aa  jnb     short loc_1800095B6
0x1800095ac  mov     edx, 46h ; 'F'
0x1800095b1  jmp     loc_180009668
0x1800095b6  imul    rdx, rax, 3E8h; dwTimeout
0x1800095bd  mov     eax, 0FFFFFFFFh
0x1800095c2  cmp     rdx, rax
0x1800095c5  ja      loc_180009663
0x1800095cb  mov     [rbp+dwindex], 0
0x1800095d2  lea     rax, [rbp+dwindex]
0x1800095d6  mov     [rsp+70h+lpdwindex], rax; lpdwindex
0x1800095db  lea     r9, [rbp+pHandles]; pHandles
0x1800095df  mov     ecx, 18h; dwFlags
0x1800095e4  lea     r8d, [rcx-17h]; cHandles
0x1800095e8  call    cs:__imp_CoWaitForMultipleHandles
0x1800095ee  mov     ebx, eax
0x1800095f0  test    eax, eax
0x1800095f2  jns     short loc_18000965F
0x1800095f4  mov     eax, cs:dword_180030000
0x1800095fa  cmp     eax, 5
0x1800095fd  jbe     short loc_18000964F
0x1800095ff  mov     rdx, 400000000000h
0x180009609  call    _tlgKeywordOn
0x18000960e  test    al, al
0x180009610  jz      short loc_18000964F
0x180009612  mov     dword ptr [rbp+arg_18], ebx
0x180009615  lea     rax, aTzAutoUpdateAp_0; "TZ auto update API timed out."
0x18000961c  mov     [rbp+var_28], rax
0x180009620  mov     [rbp+var_20], 1000000h
0x180009628  lea     rax, [rbp+arg_18]
0x18000962c  mov     [rsp+70h+var_40], rax
0x180009631  lea     rax, [rbp+var_28]
0x180009635  mov     [rsp+70h+var_48], rax
0x18000963a  lea     rax, [rbp+var_20]
0x18000963e  mov     [rsp+70h+lpdwindex], rax
0x180009643  lea     rdx, byte_180028051
0x18000964a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000964f  mov     eax, 80070102h
0x180009654  cmp     ebx, 80010115h
0x18000965a  cmovz   ebx, eax
0x18000965d  jmp     short loc_180009680
0x18000965f  xor     ebx, ebx
0x180009661  jmp     short loc_180009680
0x180009663  mov     edx, 4Bh ; 'K'; void *
0x180009668  mov     ebx, 80070216h
0x18000966d  mov     r9d, ebx; char *
0x180009670  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180009677  mov     rcx, [rbp+8]; this
0x18000967b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009680  lea     rcx, [rbp+var_18]
0x180009684  call    ?_Delete@?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@AEAAXXZ; std::unique_ptr<TzautoupdateWorker>::_Delete(void)
0x180009689  nop
0x18000968a  mov     rcx, [rbp+pHandles]; hObject
0x18000968e  call    cs:__imp_CloseHandle
0x180009694  call    TraceLoggingUnregister_EventUnregister
0x180009699  mov     eax, ebx
0x18000969b  lea     r11, [rsp+70h+var_s0]
0x1800096a0  mov     rbx, [r11+10h]
0x1800096a4  mov     rdi, [r11+18h]
0x1800096a8  mov     rsp, r11
0x1800096ab  pop     rbp
0x1800096ac  retn
```
