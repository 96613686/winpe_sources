# SxspGetXMLParser(_GUID const &,void * *)

- ea: `0x18002e9e0`
- end: `0x18002ec36`
- name: `?SxspGetXMLParser@@YAHAEBU_GUID@@PEAPEAX@Z`
- size: `598`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015a80`
- `0x18002af5c`
- `0x18003e5d8`

## callees

- `0x18000dffc`
- `0x18001c2c8`
- `0x18002e98c`
- `0x18002e9e0`
- `0x18002ec3c`
- `0x18002ed00`
- `0x180030148`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18002eae2`
- `ntdll!RtlPopFrame` at `0x18002eae2`
- `ntdll!RtlPushFrame` at `0x18002ea37`
- `ntdll!RtlPushFrame` at `0x18002ea37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ea66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ebb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ebf5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ea66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ebb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ebf5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ea81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ea81`

## pseudocode

```c
__int64 __fastcall SxspGetXMLParser(const struct _GUID *a1, void **a2)
{
  const char *v3; // rcx
  XMLParser *v4; // rax
  XMLParser *v5; // rdi
  int *v6; // rax
  unsigned int v7; // esi
  int v9; // eax
  int v10; // ebx
  DWORD v11; // eax
  DWORD LastError; // ebx
  DWORD v13; // eax
  int v14; // [rsp+20h] [rbp-58h] BYREF
  int v15; // [rsp+28h] [rbp-50h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+48h] [rbp-30h]
  int v18; // [rsp+50h] [rbp-28h]
  int *v19; // [rsp+58h] [rbp-20h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006E1A8;
  v17 = 544438355;
  Frame.Previous = 0;
  v18 = 33;
  v19 = &v15;
  v15 = 0;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( !a2 )
  {
    v18 = 41;
    FusionpTraceParameterCheck(v3);
    SetLastError(0x57u);
    *v19 = 0;
    goto LABEL_7;
  }
  *a2 = 0;
  SetLastError(0);
  v4 = (XMLParser *)HeapAlloc(g_hHeap, 0, 0xC8u);
  if ( !v4 || (v5 = XMLParser::XMLParser(v4)) == 0 )
  {
    *v19 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006E188);
LABEL_7:
    v6 = v19;
    v7 = *v19;
    goto LABEL_8;
  }
  SetLastError(0);
  SetLastError(0);
  v9 = (**(__int64 (__fastcall ***)(XMLParser *, GUID *, void **))v5)(v5, &IID_IXMLParser, a2);
  v10 = v9;
  if ( v9 >= 0 )
  {
    SetLastError(0);
    *v19 = 1;
    goto LABEL_7;
  }
  FusionpTraceCOMFailure(v9, byte_18008517D);
  v14 = v10;
  FusionpConvertCOMFailure((unsigned int *)&v14);
  v11 = FusionpHRESULTToWin32(v14);
  SetLastError(v11);
  *v19 = 0;
  v7 = *v19;
  LastError = GetLastError();
  (*(void (__fastcall **)(XMLParser *, __int64))(*(_QWORD *)v5 + 248LL))(v5, 1);
  SetLastError(LastError);
  v6 = v19;
LABEL_8:
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v6 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v13 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v13, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v7;
}

```

## disassembly

```asm
0x18002e9e0  mov     r11, rsp
0x18002e9e3  push    rsi
0x18002e9e4  sub     rsp, 70h
0x18002e9e8  mov     rax, cs:__security_cookie
0x18002e9ef  xor     rax, rsp
0x18002e9f2  mov     [rsp+78h+var_18], rax
0x18002e9f7  mov     [rsp+78h+Frame.Flags], 1
0x18002e9ff  lea     rax, qword_18006E1A8
0x18002ea06  mov     [r11-38h], rax
0x18002ea0a  lea     rcx, [r11-48h]; Frame
0x18002ea0e  xor     esi, esi
0x18002ea10  mov     qword ptr [r11-30h], 20737853h
0x18002ea18  lea     rax, [r11-50h]
0x18002ea1c  mov     [r11-40h], rsi
0x18002ea20  mov     [r11+8], rbx
0x18002ea24  mov     rbx, rdx
0x18002ea27  mov     [rsp+78h+var_28], 21h ; '!'
0x18002ea2f  mov     [r11-20h], rax
0x18002ea33  mov     [rsp+78h+var_50], esi
0x18002ea37  call    cs:__imp_RtlPushFrame
0x18002ea3e  nop     dword ptr [rax+rax+00h]
0x18002ea43  cmp     cs:g_FusionEnterExitTracingEnabled, sil
0x18002ea4a  jnz     loc_18002EB04
0x18002ea50  mov     [rsp+78h+arg_10], rdi
0x18002ea58  test    rbx, rbx
0x18002ea5b  jz      loc_18002EB0E
0x18002ea61  xor     ecx, ecx; dwErrCode
0x18002ea63  mov     [rbx], rsi
0x18002ea66  call    cs:__imp_SetLastError
0x18002ea6d  nop     dword ptr [rax+rax+00h]
0x18002ea72  mov     rcx, cs:g_hHeap; hHeap
0x18002ea79  xor     edx, edx; dwFlags
0x18002ea7b  mov     r8d, 0C8h; dwBytes
0x18002ea81  call    cs:__imp_HeapAlloc
0x18002ea88  nop     dword ptr [rax+rax+00h]
0x18002ea8d  test    rax, rax
0x18002ea90  jz      short loc_18002EAA6
0x18002ea92  mov     rcx, rax; this
0x18002ea95  call    ??0XMLParser@@QEAA@XZ; XMLParser::XMLParser(void)
0x18002ea9a  mov     rdi, rax
0x18002ea9d  test    rax, rax
0x18002eaa0  jnz     loc_18002EB35
0x18002eaa6  mov     rax, [rsp+78h+var_20]
0x18002eaab  lea     rcx, off_18006E188; struct _CALL_SITE_INFO *
0x18002eab2  mov     [rax], esi
0x18002eab4  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002eab9  mov     rax, [rsp+78h+var_20]
0x18002eabe  mov     esi, [rax]
0x18002eac0  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18002eac7  mov     rdi, [rsp+78h+arg_10]
0x18002eacf  mov     rbx, [rsp+78h+arg_0]
0x18002ead7  jnz     loc_18002EC0B
0x18002eadd  lea     rcx, [rsp+78h+Frame]; Frame
0x18002eae2  call    cs:__imp_RtlPopFrame
0x18002eae9  nop     dword ptr [rax+rax+00h]
0x18002eaee  mov     eax, esi
0x18002eaf0  mov     rcx, [rsp+78h+var_18]
0x18002eaf5  xor     rcx, rsp; StackCookie
0x18002eaf8  call    __security_check_cookie
0x18002eafd  add     rsp, 70h
0x18002eb01  pop     rsi
0x18002eb02  retn
0x18002eb04  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18002eb09  jmp     loc_18002EA50
0x18002eb0e  mov     [rsp+78h+var_28], 29h ; ')'
0x18002eb16  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18002eb1b  mov     ecx, 57h ; 'W'; dwErrCode
0x18002eb20  call    cs:__imp_SetLastError
0x18002eb27  nop     dword ptr [rax+rax+00h]
0x18002eb2c  mov     rax, [rsp+78h+var_20]
0x18002eb31  mov     [rax], esi
0x18002eb33  jmp     short loc_18002EAB9
0x18002eb35  xor     ecx, ecx; dwErrCode
0x18002eb37  call    cs:__imp_SetLastError
0x18002eb3e  nop     dword ptr [rax+rax+00h]
0x18002eb43  xor     ecx, ecx; dwErrCode
0x18002eb45  call    cs:__imp_SetLastError
0x18002eb4c  nop     dword ptr [rax+rax+00h]
0x18002eb51  mov     rax, [rdi]
0x18002eb54  lea     rdx, IID_IXMLParser
0x18002eb5b  mov     r8, rbx
0x18002eb5e  mov     rcx, rdi
0x18002eb61  mov     rax, [rax]
0x18002eb64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb69  mov     ebx, eax
0x18002eb6b  test    eax, eax
0x18002eb6d  js      short loc_18002EB8D
0x18002eb6f  xor     ecx, ecx; dwErrCode
0x18002eb71  call    cs:__imp_SetLastError
0x18002eb78  nop     dword ptr [rax+rax+00h]
0x18002eb7d  mov     rax, [rsp+78h+var_20]
0x18002eb82  mov     dword ptr [rax], 1
0x18002eb88  jmp     loc_18002EAB9
0x18002eb8d  lea     rdx, byte_18008517D; char *
0x18002eb94  mov     ecx, ebx; int
0x18002eb96  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18002eb9b  lea     rcx, [rsp+78h+var_58]; int *
0x18002eba0  mov     [rsp+78h+var_58], ebx
0x18002eba4  call    ?FusionpConvertCOMFailure@@YAXAEAJ@Z; FusionpConvertCOMFailure(long &)
0x18002eba9  mov     ecx, [rsp+78h+var_58]; int
0x18002ebad  call    ?FusionpHRESULTToWin32@@YAKJ@Z; FusionpHRESULTToWin32(long)
0x18002ebb2  mov     ecx, eax; dwErrCode
0x18002ebb4  call    cs:__imp_SetLastError
0x18002ebbb  nop     dword ptr [rax+rax+00h]
0x18002ebc0  mov     rax, [rsp+78h+var_20]
0x18002ebc5  mov     [rax], esi
0x18002ebc7  mov     rax, [rsp+78h+var_20]
0x18002ebcc  mov     esi, [rax]
0x18002ebce  call    cs:__imp_GetLastError
0x18002ebd5  nop     dword ptr [rax+rax+00h]
0x18002ebda  mov     edx, 1
0x18002ebdf  mov     rcx, rdi
0x18002ebe2  mov     ebx, eax
0x18002ebe4  mov     rax, [rdi]
0x18002ebe7  mov     rax, [rax+0F8h]
0x18002ebee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebf3  mov     ecx, ebx; dwErrCode
0x18002ebf5  call    cs:__imp_SetLastError
0x18002ebfc  nop     dword ptr [rax+rax+00h]
0x18002ec01  mov     rax, [rsp+78h+var_20]
0x18002ec06  jmp     loc_18002EAC0
0x18002ec0b  cmp     dword ptr [rax], 0
0x18002ec0e  jz      short loc_18002EC1C
0x18002ec10  xor     ecx, ecx; char *
0x18002ec12  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18002ec17  jmp     loc_18002EADD
0x18002ec1c  call    cs:__imp_GetLastError
0x18002ec23  nop     dword ptr [rax+rax+00h]
0x18002ec28  mov     ecx, eax; unsigned int
0x18002ec2a  xor     edx, edx; Format
0x18002ec2c  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18002ec31  jmp     loc_18002EADD
```
