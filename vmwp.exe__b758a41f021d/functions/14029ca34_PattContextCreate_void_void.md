# PattContextCreate(void *,void * *)

- ea: `0x14029ca34`
- end: `0x14029cc09`
- name: `?PattContextCreate@@YAJPEAXPEAPEAX@Z`
- size: `469`
- prototype: `__int64 __fastcall(HANDLE Process, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1401fef48`

## callees

- `0x140007228`
- `0x140048c08`
- `0x140055f4c`
- `0x14011ea40`
- `0x14029ca34`
- `0x14029cea0`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14029cada`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14029cada`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14029cb24`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14029cb24`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14029ca8e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14029cb68`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14029ca8e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14029cb68`
- `ntdll!RtlGetLastNtStatus` at `0x14029caeb`
- `ntdll!RtlGetLastNtStatus` at `0x14029caeb`

## string_xrefs

- `0x14029cad3`: `PatContextCreate`

## pseudocode

```c
__int64 __fastcall PattContextCreate(HANDLE Process, void **a2)
{
  int v4; // r8d
  int v5; // r9d
  NTSTATUS ClientModule; // ebx
  int v7; // esi
  FARPROC ProcAddress; // rax
  DWORD v9; // eax
  DWORD ProcessId; // [rsp+30h] [rbp-49h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-41h] BYREF
  NTSTATUS v13; // [rsp+40h] [rbp-39h] BYREF
  __int64 v14; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+50h] [rbp-29h] BYREF
  HMODULE *p_hModule; // [rsp+70h] [rbp-9h]
  __int64 v17; // [rsp+78h] [rbp-1h]
  __int64 *v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  NTSTATUS *v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]
  DWORD *p_ProcessId; // [rsp+A0h] [rbp+27h]
  __int64 v23; // [rsp+A8h] [rbp+2Fh]

  hModule = 0;
  if ( (unsigned int)dword_1403B5D48 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403B5D48, 1) )
  {
    ProcessId = GetProcessId(Process);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1403B5D48,
      (unsigned int)byte_14036F845,
      v4,
      v5,
      (__int64)&ProcessId);
  }
  ClientModule = PattGetClientModule(&hModule);
  if ( ClientModule >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, "PatContextCreate");
    if ( ProcAddress )
    {
      ClientModule = ((__int64 (__fastcall *)(HANDLE, void **))ProcAddress)(Process, a2);
      v7 = 0;
      if ( ClientModule < 0 )
        v7 = 12288;
    }
    else
    {
      ClientModule = RtlGetLastNtStatus();
      v7 = 0x2000;
    }
  }
  else
  {
    v7 = 4096;
  }
  if ( hModule )
    FreeLibrary(hModule);
  if ( (unsigned int)dword_1403B5D48 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403B5D48, 1) )
  {
    v14 = (__int64)*a2;
    ProcessId = v7;
    v13 = ClientModule;
    v9 = GetProcessId(Process);
    v23 = 4;
    LODWORD(hModule) = v9;
    v21 = 4;
    p_ProcessId = &ProcessId;
    v19 = 8;
    v20 = &v13;
    v17 = 4;
    v18 = &v14;
    p_hModule = &hModule;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_1403B5D48, (int)&word_14036F872, 0, 0, 6u, &v15);
  }
  return (unsigned int)ClientModule;
}

```

## disassembly

```asm
0x14029ca34  mov     [rsp-8+arg_10], rbx
0x14029ca39  mov     [rsp-8+arg_18], rsi
0x14029ca3e  push    rbp
0x14029ca3f  push    r14
0x14029ca41  push    r15
0x14029ca43  lea     rbp, [rsp-47h]
0x14029ca48  sub     rsp, 0C0h
0x14029ca4f  mov     rax, cs:__security_cookie
0x14029ca56  xor     rax, rsp
0x14029ca59  mov     [rbp+57h+var_20], rax
0x14029ca5d  mov     eax, cs:dword_1403B5D48
0x14029ca63  mov     r15, rdx
0x14029ca66  mov     [rbp+57h+hModule], 0
0x14029ca6e  mov     r14, rcx
0x14029ca71  cmp     eax, 5
0x14029ca74  jbe     short loc_14029CAB9
0x14029ca76  mov     edx, 1
0x14029ca7b  lea     rcx, dword_1403B5D48
0x14029ca82  call    _tlgKeywordOn
0x14029ca87  test    al, al
0x14029ca89  jz      short loc_14029CAB9
0x14029ca8b  mov     rcx, r14; Process
0x14029ca8e  call    cs:__imp_GetProcessId
0x14029ca95  nop     dword ptr [rax+rax+00h]
0x14029ca9a  mov     [rbp+57h+var_A0], eax
0x14029ca9d  lea     rdx, byte_14036F845
0x14029caa4  lea     rax, [rbp+57h+var_A0]
0x14029caa8  lea     rcx, dword_1403B5D48
0x14029caaf  mov     qword ptr [rsp+0D0h+var_B0], rax
0x14029cab4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x14029cab9  lea     rcx, [rbp+57h+hModule]; HINSTANCE *
0x14029cabd  call    ?PattGetClientModule@@YAJPEAPEAUHINSTANCE__@@@Z; PattGetClientModule(HINSTANCE__ * *)
0x14029cac2  mov     ebx, eax
0x14029cac4  test    eax, eax
0x14029cac6  jns     short loc_14029CACF
0x14029cac8  mov     esi, 1000h
0x14029cacd  jmp     short loc_14029CB19
0x14029cacf  mov     rcx, [rbp+57h+hModule]; hModule
0x14029cad3  lea     rdx, aPatcontextcrea; "PatContextCreate"
0x14029cada  call    cs:__imp_GetProcAddress
0x14029cae1  nop     dword ptr [rax+rax+00h]
0x14029cae6  test    rax, rax
0x14029cae9  jnz     short loc_14029CB00
0x14029caeb  call    cs:__imp_RtlGetLastNtStatus
0x14029caf2  nop     dword ptr [rax+rax+00h]
0x14029caf7  mov     ebx, eax
0x14029caf9  mov     esi, 2000h
0x14029cafe  jmp     short loc_14029CB19
0x14029cb00  mov     rdx, r15
0x14029cb03  mov     rcx, r14
0x14029cb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14029cb0b  mov     ebx, eax
0x14029cb0d  xor     esi, esi
0x14029cb0f  test    ebx, ebx
0x14029cb11  mov     eax, 3000h
0x14029cb16  cmovs   esi, eax
0x14029cb19  cmp     [rbp+57h+hModule], 0
0x14029cb1e  jz      short loc_14029CB30
0x14029cb20  mov     rcx, [rbp+57h+hModule]; hLibModule
0x14029cb24  call    cs:__imp_FreeLibrary
0x14029cb2b  nop     dword ptr [rax+rax+00h]
0x14029cb30  mov     eax, cs:dword_1403B5D48
0x14029cb36  cmp     eax, 5
0x14029cb39  jbe     loc_14029CBE1
0x14029cb3f  mov     edx, 1
0x14029cb44  lea     rcx, dword_1403B5D48
0x14029cb4b  call    _tlgKeywordOn
0x14029cb50  test    al, al
0x14029cb52  jz      loc_14029CBE1
0x14029cb58  mov     rax, [r15]
0x14029cb5b  mov     rcx, r14; Process
0x14029cb5e  mov     [rbp+57h+var_88], rax
0x14029cb62  mov     [rbp+57h+var_A0], esi
0x14029cb65  mov     [rbp+57h+var_90], ebx
0x14029cb68  call    cs:__imp_GetProcessId
0x14029cb6f  nop     dword ptr [rax+rax+00h]
0x14029cb74  xor     r9d, r9d; int
0x14029cb77  mov     [rbp+57h+var_28], 4
0x14029cb7f  mov     dword ptr [rbp+57h+hModule], eax
0x14029cb82  lea     rdx, word_14036F872; int
0x14029cb89  lea     rax, [rbp+57h+var_A0]
0x14029cb8d  mov     [rbp+57h+var_38], 4
0x14029cb95  mov     [rbp+57h+var_30], rax
0x14029cb99  lea     rcx, dword_1403B5D48; int
0x14029cba0  lea     rax, [rbp+57h+var_90]
0x14029cba4  mov     [rbp+57h+var_48], 8
0x14029cbac  mov     [rbp+57h+var_40], rax
0x14029cbb0  xor     r8d, r8d; int
0x14029cbb3  lea     rax, [rbp+57h+var_88]
0x14029cbb7  mov     [rbp+57h+var_58], 4
0x14029cbbf  mov     [rbp+57h+var_50], rax
0x14029cbc3  lea     rax, [rbp+57h+hModule]
0x14029cbc7  mov     [rbp+57h+var_60], rax
0x14029cbcb  lea     rax, [rbp+57h+var_80]
0x14029cbcf  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x14029cbd4  mov     [rsp+0D0h+var_B0], 6; ULONG
0x14029cbdc  call    _tlgWriteTransfer_EventWriteTransfer
0x14029cbe1  mov     eax, ebx
0x14029cbe3  mov     rcx, [rbp+57h+var_20]
0x14029cbe7  xor     rcx, rsp; StackCookie
0x14029cbea  call    __security_check_cookie
0x14029cbef  lea     r11, [rsp+0D0h+var_10]
0x14029cbf7  mov     rbx, [r11+30h]
0x14029cbfb  mov     rsi, [r11+38h]
0x14029cbff  mov     rsp, r11
0x14029cc02  pop     r15
0x14029cc04  pop     r14
0x14029cc06  pop     rbp
0x14029cc07  retn
```
