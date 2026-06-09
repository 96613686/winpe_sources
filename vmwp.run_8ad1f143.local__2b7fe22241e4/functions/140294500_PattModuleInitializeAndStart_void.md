# PattModuleInitializeAndStart(void)

- ea: `0x140294500`
- end: `0x14029471f`
- name: `?PattModuleInitializeAndStart@@YAJXZ`
- size: `543`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140065650`

## callees

- `0x1400014a4`
- `0x140002a3c`
- `0x14000dc7c`
- `0x14005613c`
- `0x1402944dc`
- `0x140294500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1402945a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1402945a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140294601`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140294601`
- `ntdll!RtlAllocateHeap` at `0x140294671`
- `ntdll!RtlAllocateHeap` at `0x140294671`

## string_xrefs

- `0x140294580`: `SOFTWARE\Microsoft\Azure\PageAccessTracing`
- `0x1402945f2`: `ClientDllPath`

## pseudocode

```c
__int64 PattModuleInitializeAndStart(void)
{
  DWORD v0; // r8d
  LSTATUS v1; // eax
  signed int v2; // ebx
  BYTE *Heap; // rax
  LSTATUS v4; // eax
  unsigned int v5; // eax
  DWORD v6; // r8d
  int v7; // r9d
  DWORD Type; // [rsp+50h] [rbp+10h] BYREF
  HKEY *v10; // [rsp+58h] [rbp+18h] BYREF
  LPCWSTR v11; // [rsp+60h] [rbp+20h] BYREF

  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1403A9C50);
  if ( (unsigned int)dword_1403A9C50 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403A9C50, 1) )
  {
    Type = v0;
    v10 = &PattGlobals;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1403A9C50,
      (unsigned int)&byte_14036491F,
      0,
      0,
      (__int64)&v10,
      (__int64)&Type);
  }
  lpData = 0;
  *(_OWORD *)&PattGlobals = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Azure\\PageAccessTracing", 0, 0x20019u, &PattGlobals);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0xC0070000;
  }
  else
  {
    Heap = (BYTE *)lpData;
    while ( 1 )
    {
      Type = 0;
      v4 = RegQueryValueExW(PattGlobals, L"ClientDllPath", 0, &Type, Heap, (LPDWORD)&PattGlobals + 2);
      v2 = v4;
      if ( v4 )
      {
        if ( v4 > 0 )
          v2 = (unsigned __int16)v4 | 0xC0070000;
      }
      else
      {
        v2 = Type != 1 ? 0xC0000024 : 0;
      }
      if ( lpData && v2 != -1073282838 )
        break;
      v5 = *((_DWORD *)&PattGlobals + 2);
      if ( !*((_DWORD *)&PattGlobals + 2) )
      {
        v2 = -2147483614;
        goto LABEL_23;
      }
      if ( lpData )
      {
        PattHeapFree((void *)lpData);
        v5 = *((_DWORD *)&PattGlobals + 2);
      }
      Heap = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      lpData = (LPCWSTR)Heap;
      if ( !Heap )
      {
        v2 = -1073741801;
        goto LABEL_23;
      }
    }
    if ( v2 >= 0 )
      v2 = 0;
  }
LABEL_23:
  if ( (unsigned int)dword_1403A9C50 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403A9C50, 1) )
  {
    Type = v6;
    LODWORD(v10) = v2;
    v11 = lpData;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)lpData,
      (unsigned int)byte_14036473B,
      v6,
      v7,
      (__int64)&v11,
      (__int64)&v10,
      (__int64)&Type);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140294500  mov     [rsp-8+arg_18], rbx
0x140294505  push    rbp
0x140294506  mov     rbp, rsp
0x140294509  sub     rsp, 40h
0x14029450d  lea     rcx, dword_1403A9C50; CallbackContext
0x140294514  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140294519  mov     ecx, cs:dword_1403A9C50
0x14029451f  lea     rbx, ?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A; _PAT_THUNK_GLOBALS PattGlobals
0x140294526  mov     r8d, eax
0x140294529  cmp     ecx, 5
0x14029452c  jbe     short loc_140294576
0x14029452e  mov     edx, 1
0x140294533  lea     rcx, dword_1403A9C50
0x14029453a  call    _tlgKeywordOn
0x14029453f  test    al, al
0x140294541  jz      short loc_140294576
0x140294543  lea     rax, [rbp+Type]
0x140294547  mov     [rbp+Type], r8d
0x14029454b  mov     [rsp+40h+lpcbData], rax
0x140294550  lea     rdx, byte_14036491F
0x140294557  lea     rax, [rbp+arg_8]
0x14029455b  mov     [rbp+arg_8], rbx
0x14029455f  xor     r9d, r9d
0x140294562  mov     [rsp+40h+phkResult], rax
0x140294567  xor     r8d, r8d
0x14029456a  lea     rcx, dword_1403A9C50
0x140294571  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140294576  xorps   xmm0, xmm0
0x140294579  mov     [rsp+40h+phkResult], rbx; phkResult
0x14029457e  xor     eax, eax
0x140294580  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Azure\\PageAccessT"...
0x140294587  mov     r9d, 20019h; samDesired
0x14029458d  mov     cs:lpData, rax
0x140294594  xor     r8d, r8d; ulOptions
0x140294597  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14029459e  movups  cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A, xmm0; _PAT_THUNK_GLOBALS PattGlobals
0x1402945a5  call    cs:__imp_RegOpenKeyExW
0x1402945ac  nop     dword ptr [rax+rax+00h]
0x1402945b1  mov     ebx, eax
0x1402945b3  test    eax, eax
0x1402945b5  jz      short loc_1402945CD
0x1402945b7  jle     short loc_1402945C2
0x1402945b9  movzx   ebx, ax
0x1402945bc  or      ebx, 0C0070000h
0x1402945c2  mov     r8d, 1000h
0x1402945c8  jmp     loc_1402946B8
0x1402945cd  mov     rax, cs:lpData
0x1402945d4  lea     rcx, ?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A+8; _PAT_THUNK_GLOBALS PattGlobals
0x1402945db  mov     [rbp+Type], 0
0x1402945e2  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x1402945e7  lea     r9, [rbp+Type]; lpType
0x1402945eb  mov     rcx, qword ptr cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A; hKey
0x1402945f2  lea     rdx, aClientdllpath; "ClientDllPath"
0x1402945f9  xor     r8d, r8d; lpReserved
0x1402945fc  mov     [rsp+40h+phkResult], rax; lpData
0x140294601  call    cs:__imp_RegQueryValueExW
0x140294608  nop     dword ptr [rax+rax+00h]
0x14029460d  mov     ebx, eax
0x14029460f  test    eax, eax
0x140294611  jz      short loc_140294620
0x140294613  jle     short loc_14029462F
0x140294615  movzx   ebx, ax
0x140294618  or      ebx, 0C0070000h
0x14029461e  jmp     short loc_14029462F
0x140294620  mov     eax, [rbp+Type]
0x140294623  dec     eax
0x140294625  neg     eax
0x140294627  sbb     ebx, ebx
0x140294629  and     ebx, 0C0000024h
0x14029462f  mov     rcx, cs:lpData; void *
0x140294636  test    rcx, rcx
0x140294639  jz      short loc_140294643
0x14029463b  cmp     ebx, 0C00700EAh
0x140294641  jnz     short loc_14029469A
0x140294643  mov     rax, qword ptr cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A+8; _PAT_THUNK_GLOBALS PattGlobals
0x14029464a  test    eax, eax
0x14029464c  jz      short loc_1402946AD
0x14029464e  test    rcx, rcx
0x140294651  jz      short loc_14029465F
0x140294653  call    ?PattHeapFree@@YAXPEAX@Z; PattHeapFree(void *)
0x140294658  mov     rax, qword ptr cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A+8; _PAT_THUNK_GLOBALS PattGlobals
0x14029465f  mov     rcx, gs:60h
0x140294668  xor     edx, edx; Flags
0x14029466a  mov     r8d, eax; Size
0x14029466d  mov     rcx, [rcx+30h]; HeapHandle
0x140294671  call    cs:__imp_RtlAllocateHeap
0x140294678  nop     dword ptr [rax+rax+00h]
0x14029467d  mov     cs:lpData, rax
0x140294684  test    rax, rax
0x140294687  jnz     loc_1402945D4
0x14029468d  mov     ebx, 0C0000017h
0x140294692  mov     r8d, 3000h
0x140294698  jmp     short loc_1402946B8
0x14029469a  test    ebx, ebx
0x14029469c  jns     short loc_1402946A6
0x14029469e  mov     r8d, 4000h
0x1402946a4  jmp     short loc_1402946B8
0x1402946a6  xor     ebx, ebx
0x1402946a8  xor     r8d, r8d
0x1402946ab  jmp     short loc_1402946B8
0x1402946ad  mov     ebx, 80000022h
0x1402946b2  mov     r8d, 2000h
0x1402946b8  mov     eax, cs:dword_1403A9C50
0x1402946be  cmp     eax, 5
0x1402946c1  jbe     short loc_140294711
0x1402946c3  mov     edx, 1
0x1402946c8  lea     rcx, dword_1403A9C50
0x1402946cf  call    _tlgKeywordOn
0x1402946d4  test    al, al
0x1402946d6  jz      short loc_140294711
0x1402946d8  mov     rcx, cs:lpData
0x1402946df  lea     rax, [rbp+Type]
0x1402946e3  mov     [rsp+40h+var_10], rax
0x1402946e8  lea     rdx, byte_14036473B
0x1402946ef  lea     rax, [rbp+arg_8]
0x1402946f3  mov     [rbp+Type], r8d
0x1402946f7  mov     [rsp+40h+lpcbData], rax
0x1402946fc  lea     rax, [rbp+arg_10]
0x140294700  mov     [rsp+40h+phkResult], rax
0x140294705  mov     dword ptr [rbp+arg_8], ebx
0x140294708  mov     [rbp+arg_10], rcx
0x14029470c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140294711  mov     eax, ebx
0x140294713  mov     rbx, [rsp+40h+arg_18]
0x140294718  add     rsp, 40h
0x14029471c  pop     rbp
0x14029471d  retn
```
