# PattModuleInitializeAndStart(void)

- ea: `0x14029cf10`
- end: `0x14029d12f`
- name: `?PattModuleInitializeAndStart@@YAJXZ`
- size: `543`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400735fc`

## callees

- `0x1400014a4`
- `0x140002a14`
- `0x14000e200`
- `0x140055f4c`
- `0x14029ceec`
- `0x14029cf10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14029d011`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14029d011`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14029cfb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14029cfb5`
- `ntdll!RtlAllocateHeap` at `0x14029d081`
- `ntdll!RtlAllocateHeap` at `0x14029d081`

## string_xrefs

- `0x14029d002`: `ClientDllPath`
- `0x14029cf90`: `SOFTWARE\Microsoft\Azure\PageAccessTracing`

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

  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1403B5D48);
  if ( (unsigned int)dword_1403B5D48 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403B5D48, 1) )
  {
    Type = v0;
    v10 = &PattGlobals;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1403B5D48,
      (unsigned int)byte_14036F951,
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
  if ( (unsigned int)dword_1403B5D48 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403B5D48, 1) )
  {
    Type = v6;
    LODWORD(v10) = v2;
    v11 = lpData;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)lpData,
      (unsigned int)byte_14036F9DD,
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
0x14029cf10  mov     [rsp-8+arg_18], rbx
0x14029cf15  push    rbp
0x14029cf16  mov     rbp, rsp
0x14029cf19  sub     rsp, 40h
0x14029cf1d  lea     rcx, dword_1403B5D48; CallbackContext
0x14029cf24  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14029cf29  mov     ecx, cs:dword_1403B5D48
0x14029cf2f  lea     rbx, ?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A; _PAT_THUNK_GLOBALS PattGlobals
0x14029cf36  mov     r8d, eax
0x14029cf39  cmp     ecx, 5
0x14029cf3c  jbe     short loc_14029CF86
0x14029cf3e  mov     edx, 1
0x14029cf43  lea     rcx, dword_1403B5D48
0x14029cf4a  call    _tlgKeywordOn
0x14029cf4f  test    al, al
0x14029cf51  jz      short loc_14029CF86
0x14029cf53  lea     rax, [rbp+Type]
0x14029cf57  mov     [rbp+Type], r8d
0x14029cf5b  mov     [rsp+40h+lpcbData], rax
0x14029cf60  lea     rdx, byte_14036F951
0x14029cf67  lea     rax, [rbp+arg_8]
0x14029cf6b  mov     [rbp+arg_8], rbx
0x14029cf6f  xor     r9d, r9d
0x14029cf72  mov     [rsp+40h+phkResult], rax
0x14029cf77  xor     r8d, r8d
0x14029cf7a  lea     rcx, dword_1403B5D48
0x14029cf81  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14029cf86  xorps   xmm0, xmm0
0x14029cf89  mov     [rsp+40h+phkResult], rbx; phkResult
0x14029cf8e  xor     eax, eax
0x14029cf90  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Azure\\PageAccessT"...
0x14029cf97  mov     r9d, 20019h; samDesired
0x14029cf9d  mov     cs:lpData, rax
0x14029cfa4  xor     r8d, r8d; ulOptions
0x14029cfa7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14029cfae  movups  cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A, xmm0; _PAT_THUNK_GLOBALS PattGlobals
0x14029cfb5  call    cs:__imp_RegOpenKeyExW
0x14029cfbc  nop     dword ptr [rax+rax+00h]
0x14029cfc1  mov     ebx, eax
0x14029cfc3  test    eax, eax
0x14029cfc5  jz      short loc_14029CFDD
0x14029cfc7  jle     short loc_14029CFD2
0x14029cfc9  movzx   ebx, ax
0x14029cfcc  or      ebx, 0C0070000h
0x14029cfd2  mov     r8d, 1000h
0x14029cfd8  jmp     loc_14029D0C8
0x14029cfdd  mov     rax, cs:lpData
0x14029cfe4  lea     rcx, ?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A+8; _PAT_THUNK_GLOBALS PattGlobals
0x14029cfeb  mov     [rbp+Type], 0
0x14029cff2  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x14029cff7  lea     r9, [rbp+Type]; lpType
0x14029cffb  mov     rcx, qword ptr cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A; hKey
0x14029d002  lea     rdx, aClientdllpath; "ClientDllPath"
0x14029d009  xor     r8d, r8d; lpReserved
0x14029d00c  mov     [rsp+40h+phkResult], rax; lpData
0x14029d011  call    cs:__imp_RegQueryValueExW
0x14029d018  nop     dword ptr [rax+rax+00h]
0x14029d01d  mov     ebx, eax
0x14029d01f  test    eax, eax
0x14029d021  jz      short loc_14029D030
0x14029d023  jle     short loc_14029D03F
0x14029d025  movzx   ebx, ax
0x14029d028  or      ebx, 0C0070000h
0x14029d02e  jmp     short loc_14029D03F
0x14029d030  mov     eax, [rbp+Type]
0x14029d033  dec     eax
0x14029d035  neg     eax
0x14029d037  sbb     ebx, ebx
0x14029d039  and     ebx, 0C0000024h
0x14029d03f  mov     rcx, cs:lpData; void *
0x14029d046  test    rcx, rcx
0x14029d049  jz      short loc_14029D053
0x14029d04b  cmp     ebx, 0C00700EAh
0x14029d051  jnz     short loc_14029D0AA
0x14029d053  mov     rax, qword ptr cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A+8; _PAT_THUNK_GLOBALS PattGlobals
0x14029d05a  test    eax, eax
0x14029d05c  jz      short loc_14029D0BD
0x14029d05e  test    rcx, rcx
0x14029d061  jz      short loc_14029D06F
0x14029d063  call    ?PattHeapFree@@YAXPEAX@Z; PattHeapFree(void *)
0x14029d068  mov     rax, qword ptr cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A+8; _PAT_THUNK_GLOBALS PattGlobals
0x14029d06f  mov     rcx, gs:60h
0x14029d078  xor     edx, edx; Flags
0x14029d07a  mov     r8d, eax; Size
0x14029d07d  mov     rcx, [rcx+30h]; HeapHandle
0x14029d081  call    cs:__imp_RtlAllocateHeap
0x14029d088  nop     dword ptr [rax+rax+00h]
0x14029d08d  mov     cs:lpData, rax
0x14029d094  test    rax, rax
0x14029d097  jnz     loc_14029CFE4
0x14029d09d  mov     ebx, 0C0000017h
0x14029d0a2  mov     r8d, 3000h
0x14029d0a8  jmp     short loc_14029D0C8
0x14029d0aa  test    ebx, ebx
0x14029d0ac  jns     short loc_14029D0B6
0x14029d0ae  mov     r8d, 4000h
0x14029d0b4  jmp     short loc_14029D0C8
0x14029d0b6  xor     ebx, ebx
0x14029d0b8  xor     r8d, r8d
0x14029d0bb  jmp     short loc_14029D0C8
0x14029d0bd  mov     ebx, 80000022h
0x14029d0c2  mov     r8d, 2000h
0x14029d0c8  mov     eax, cs:dword_1403B5D48
0x14029d0ce  cmp     eax, 5
0x14029d0d1  jbe     short loc_14029D121
0x14029d0d3  mov     edx, 1
0x14029d0d8  lea     rcx, dword_1403B5D48
0x14029d0df  call    _tlgKeywordOn
0x14029d0e4  test    al, al
0x14029d0e6  jz      short loc_14029D121
0x14029d0e8  mov     rcx, cs:lpData
0x14029d0ef  lea     rax, [rbp+Type]
0x14029d0f3  mov     [rsp+40h+var_10], rax
0x14029d0f8  lea     rdx, byte_14036F9DD
0x14029d0ff  lea     rax, [rbp+arg_8]
0x14029d103  mov     [rbp+Type], r8d
0x14029d107  mov     [rsp+40h+lpcbData], rax
0x14029d10c  lea     rax, [rbp+arg_10]
0x14029d110  mov     [rsp+40h+phkResult], rax
0x14029d115  mov     dword ptr [rbp+arg_8], ebx
0x14029d118  mov     [rbp+arg_10], rcx
0x14029d11c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14029d121  mov     eax, ebx
0x14029d123  mov     rbx, [rsp+40h+arg_18]
0x14029d128  add     rsp, 40h
0x14029d12c  pop     rbp
0x14029d12d  retn
```
