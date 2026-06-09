# CreateInprocAdviseRouterInstance

- ea: `0x180022848`
- end: `0x180022913`
- name: `CreateInprocAdviseRouterInstance`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180022650`

## callees

- `0x180022544`
- `0x180022848`
- `0x18002995c`
- `0x180071b08`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022864`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800228b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800228b9`

## pseudocode

```c
__int64 __fastcall CreateInprocAdviseRouterInstance(_QWORD *a1)
{
  HANDLE v2; // rdi
  int v3; // eax
  __int64 v4; // r8
  unsigned int v5; // ebx
  __int64 v6; // rbx
  void *v7; // rcx
  signed int LastError; // eax
  __int64 v10; // r8
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF
  HANDLE EventW; // [rsp+50h] [rbp+18h] BYREF

  EventW = CreateEventW(0, 0, 0, 0);
  v2 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    Log_UnistoreHREvent_12(v5, 0, v10, 39);
    return v5;
  }
  v11 = 0;
  v3 = ATL::CComObject<AdviseRouter>::CreateInstance(&v11);
  v5 = v3;
  if ( v3 < 0 )
  {
    Log_UnistoreHREvent_12((unsigned int)v3, 1, v4, 44);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&EventW);
    return v5;
  }
  v6 = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v7 = *(void **)(v6 + 80);
  *(_QWORD *)(v6 + 80) = v2;
  *a1 = v6;
  if ( v7 )
    CloseHandle(v7);
  return 0;
}

```

## disassembly

```asm
0x180022848  mov     [rsp+arg_0], rbx
0x18002284d  mov     [rsp+arg_18], rsi
0x180022852  push    rdi
0x180022853  sub     rsp, 30h
0x180022857  mov     rsi, rcx
0x18002285a  xor     r9d, r9d; lpName
0x18002285d  xor     ecx, ecx; lpEventAttributes
0x18002285f  xor     r8d, r8d; bInitialState
0x180022862  xor     edx, edx; bManualReset
0x180022864  call    cs:__imp_CreateEventW
0x18002286a  mov     [rsp+38h+arg_10], rax
0x18002286f  mov     rdi, rax
0x180022872  test    rax, rax
0x180022875  jz      short loc_1800228D1
0x180022877  lea     rcx, [rsp+38h+arg_8]
0x18002287c  mov     [rsp+38h+arg_8], 0
0x180022885  call    ?CreateInstance@?$CComObject@VAdviseRouter@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<AdviseRouter>::CreateInstance(ATL::CComObject<AdviseRouter> * *)
0x18002288a  mov     ebx, eax
0x18002288c  test    eax, eax
0x18002288e  js      short loc_1800228F7
0x180022890  mov     rbx, [rsp+38h+arg_8]
0x180022895  test    rbx, rbx
0x180022898  jz      short loc_1800228A9
0x18002289a  mov     rax, [rbx]
0x18002289d  mov     rcx, rbx
0x1800228a0  mov     rax, [rax+8]
0x1800228a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228a9  mov     rcx, [rbx+50h]; hObject
0x1800228ad  mov     [rbx+50h], rdi
0x1800228b1  mov     [rsi], rbx
0x1800228b4  test    rcx, rcx
0x1800228b7  jz      short loc_1800228BF
0x1800228b9  call    cs:__imp_CloseHandle
0x1800228bf  xor     eax, eax
0x1800228c1  mov     rbx, [rsp+38h+arg_0]
0x1800228c6  mov     rsi, [rsp+38h+arg_18]
0x1800228cb  add     rsp, 30h
0x1800228cf  pop     rdi
0x1800228d0  retn
0x1800228d1  call    cs:__imp_GetLastError
0x1800228d7  mov     ebx, eax
0x1800228d9  test    eax, eax
0x1800228db  jle     short loc_1800228E6
0x1800228dd  movzx   ebx, ax
0x1800228e0  or      ebx, 80070000h
0x1800228e6  xor     edx, edx
0x1800228e8  mov     ecx, ebx
0x1800228ea  lea     r9d, [rdx+27h]
0x1800228ee  call    Log_UnistoreHREvent_12
0x1800228f3  mov     eax, ebx
0x1800228f5  jmp     short loc_1800228C1
0x1800228f7  mov     edx, 1
0x1800228fc  mov     ecx, ebx
0x1800228fe  lea     r9d, [rdx+2Bh]
0x180022902  call    Log_UnistoreHREvent_12
0x180022907  lea     rcx, [rsp+38h+arg_10]
0x18002290c  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180022911  jmp     short loc_1800228F3
```
