# PattContextCreate(void *,void * *)

- ea: `0x140294024`
- end: `0x1402941f9`
- name: `?PattContextCreate@@YAJPEAXPEAPEAX@Z`
- size: `469`
- prototype: `__int64 __fastcall(HANDLE Process, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14020d6dc`

## callees

- `0x140007250`
- `0x14004a028`
- `0x14005613c`
- `0x140132960`
- `0x140294024`
- `0x140294490`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140294114`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140294114`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1402940ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1402940ca`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14029407e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140294158`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14029407e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140294158`
- `ntdll!RtlGetLastNtStatus` at `0x1402940db`
- `ntdll!RtlGetLastNtStatus` at `0x1402940db`

## string_xrefs

- `0x1402940c3`: `PatContextCreate`

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
  if ( (unsigned int)dword_1403A9C50 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403A9C50, 1) )
  {
    ProcessId = GetProcessId(Process);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1403A9C50,
      (unsigned int)byte_1403648A5,
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
  if ( (unsigned int)dword_1403A9C50 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403A9C50, 1) )
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
    tlgWriteTransfer_EventWriteTransfer((int)&dword_1403A9C50, (int)&byte_14036484D, 0, 0, 6u, &v15);
  }
  return (unsigned int)ClientModule;
}

```

## disassembly

```asm
0x140294024  mov     [rsp-8+arg_10], rbx
0x140294029  mov     [rsp-8+arg_18], rsi
0x14029402e  push    rbp
0x14029402f  push    r14
0x140294031  push    r15
0x140294033  lea     rbp, [rsp-47h]
0x140294038  sub     rsp, 0C0h
0x14029403f  mov     rax, cs:__security_cookie
0x140294046  xor     rax, rsp
0x140294049  mov     [rbp+57h+var_20], rax
0x14029404d  mov     eax, cs:dword_1403A9C50
0x140294053  mov     r15, rdx
0x140294056  mov     [rbp+57h+hModule], 0
0x14029405e  mov     r14, rcx
0x140294061  cmp     eax, 5
0x140294064  jbe     short loc_1402940A9
0x140294066  mov     edx, 1
0x14029406b  lea     rcx, dword_1403A9C50
0x140294072  call    _tlgKeywordOn
0x140294077  test    al, al
0x140294079  jz      short loc_1402940A9
0x14029407b  mov     rcx, r14; Process
0x14029407e  call    cs:__imp_GetProcessId
0x140294085  nop     dword ptr [rax+rax+00h]
0x14029408a  mov     [rbp+57h+var_A0], eax
0x14029408d  lea     rdx, byte_1403648A5
0x140294094  lea     rax, [rbp+57h+var_A0]
0x140294098  lea     rcx, dword_1403A9C50
0x14029409f  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1402940a4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1402940a9  lea     rcx, [rbp+57h+hModule]; HINSTANCE *
0x1402940ad  call    ?PattGetClientModule@@YAJPEAPEAUHINSTANCE__@@@Z; PattGetClientModule(HINSTANCE__ * *)
0x1402940b2  mov     ebx, eax
0x1402940b4  test    eax, eax
0x1402940b6  jns     short loc_1402940BF
0x1402940b8  mov     esi, 1000h
0x1402940bd  jmp     short loc_140294109
0x1402940bf  mov     rcx, [rbp+57h+hModule]; hModule
0x1402940c3  lea     rdx, aPatcontextcrea; "PatContextCreate"
0x1402940ca  call    cs:__imp_GetProcAddress
0x1402940d1  nop     dword ptr [rax+rax+00h]
0x1402940d6  test    rax, rax
0x1402940d9  jnz     short loc_1402940F0
0x1402940db  call    cs:__imp_RtlGetLastNtStatus
0x1402940e2  nop     dword ptr [rax+rax+00h]
0x1402940e7  mov     ebx, eax
0x1402940e9  mov     esi, 2000h
0x1402940ee  jmp     short loc_140294109
0x1402940f0  mov     rdx, r15
0x1402940f3  mov     rcx, r14
0x1402940f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402940fb  mov     ebx, eax
0x1402940fd  xor     esi, esi
0x1402940ff  test    ebx, ebx
0x140294101  mov     eax, 3000h
0x140294106  cmovs   esi, eax
0x140294109  cmp     [rbp+57h+hModule], 0
0x14029410e  jz      short loc_140294120
0x140294110  mov     rcx, [rbp+57h+hModule]; hLibModule
0x140294114  call    cs:__imp_FreeLibrary
0x14029411b  nop     dword ptr [rax+rax+00h]
0x140294120  mov     eax, cs:dword_1403A9C50
0x140294126  cmp     eax, 5
0x140294129  jbe     loc_1402941D1
0x14029412f  mov     edx, 1
0x140294134  lea     rcx, dword_1403A9C50
0x14029413b  call    _tlgKeywordOn
0x140294140  test    al, al
0x140294142  jz      loc_1402941D1
0x140294148  mov     rax, [r15]
0x14029414b  mov     rcx, r14; Process
0x14029414e  mov     [rbp+57h+var_88], rax
0x140294152  mov     [rbp+57h+var_A0], esi
0x140294155  mov     [rbp+57h+var_90], ebx
0x140294158  call    cs:__imp_GetProcessId
0x14029415f  nop     dword ptr [rax+rax+00h]
0x140294164  xor     r9d, r9d; int
0x140294167  mov     [rbp+57h+var_28], 4
0x14029416f  mov     dword ptr [rbp+57h+hModule], eax
0x140294172  lea     rdx, byte_14036484D; int
0x140294179  lea     rax, [rbp+57h+var_A0]
0x14029417d  mov     [rbp+57h+var_38], 4
0x140294185  mov     [rbp+57h+var_30], rax
0x140294189  lea     rcx, dword_1403A9C50; int
0x140294190  lea     rax, [rbp+57h+var_90]
0x140294194  mov     [rbp+57h+var_48], 8
0x14029419c  mov     [rbp+57h+var_40], rax
0x1402941a0  xor     r8d, r8d; int
0x1402941a3  lea     rax, [rbp+57h+var_88]
0x1402941a7  mov     [rbp+57h+var_58], 4
0x1402941af  mov     [rbp+57h+var_50], rax
0x1402941b3  lea     rax, [rbp+57h+hModule]
0x1402941b7  mov     [rbp+57h+var_60], rax
0x1402941bb  lea     rax, [rbp+57h+var_80]
0x1402941bf  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x1402941c4  mov     [rsp+0D0h+var_B0], 6; ULONG
0x1402941cc  call    _tlgWriteTransfer_EventWriteTransfer
0x1402941d1  mov     eax, ebx
0x1402941d3  mov     rcx, [rbp+57h+var_20]
0x1402941d7  xor     rcx, rsp; StackCookie
0x1402941da  call    __security_check_cookie
0x1402941df  lea     r11, [rsp+0D0h+var_10]
0x1402941e7  mov     rbx, [r11+30h]
0x1402941eb  mov     rsi, [r11+38h]
0x1402941ef  mov     rsp, r11
0x1402941f2  pop     r15
0x1402941f4  pop     r14
0x1402941f6  pop     rbp
0x1402941f7  retn
```
