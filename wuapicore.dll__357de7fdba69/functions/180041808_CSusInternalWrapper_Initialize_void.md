# CSusInternalWrapper::Initialize(void)

- ea: `0x180041808`
- end: `0x180041902`
- name: `?Initialize@CSusInternalWrapper@@QEAAJXZ`
- size: `250`
- prototype: `__int64 __fastcall(CSusInternalWrapper *__hidden this)`
- caller_count: `15`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006f8c`
- `0x1800216a0`
- `0x180022808`
- `0x18002839c`
- `0x18002bc38`
- `0x1800369f0`
- `0x18003b5f0`
- `0x18003f304`
- `0x18004aa0c`
- `0x180058d64`
- `0x18006adbc`
- `0x18006d954`
- `0x18007158c`
- `0x180073448`
- `0x18007fe50`

## callees

- `0x180041808`
- `0x1800422d8`
- `0x18008dcc8`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041832`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004184b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041832`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004184b`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18004187e`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18004187e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418bf`

## pseudocode

```c
__int64 __fastcall CSusInternalWrapper::Initialize(IUnknown *this)
{
  struct IUnknownVtbl *EventW; // rax
  struct IUnknownVtbl *v3; // rax
  int FreeThreadedMarshaler; // ebx
  IUnknown *v5; // r14
  signed int LastError; // eax

  EventW = (struct IUnknownVtbl *)CreateEventW(0, 1, 1, 0);
  this[2].lpVtbl = EventW;
  if ( !EventW || (v3 = (struct IUnknownVtbl *)CreateEventW(0, 1, 0, 0), (this[4].lpVtbl = v3) == 0) )
  {
    LastError = GetLastError();
    FreeThreadedMarshaler = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      FreeThreadedMarshaler = LastError;
    if ( FreeThreadedMarshaler >= 0 )
      FreeThreadedMarshaler = -2147418113;
    goto LABEL_13;
  }
  FreeThreadedMarshaler = CSupportWeakRef::Initialize((void **)&this[19].lpVtbl);
  if ( FreeThreadedMarshaler < 0 )
  {
LABEL_13:
    CSusInternalWrapper::Clear((CSusInternalWrapper *)this);
    return (unsigned int)FreeThreadedMarshaler;
  }
  v5 = this + 9;
  this[10].lpVtbl = (struct IUnknownVtbl *)this;
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(this + 7, (LPUNKNOWN *)&this[9]);
  if ( FreeThreadedMarshaler < 0 )
  {
    if ( v5->lpVtbl )
      (*((void (__fastcall **)(struct IUnknownVtbl *))v5->lpVtbl->QueryInterface + 2))(v5->lpVtbl);
    v5->lpVtbl = 0;
    this[8].lpVtbl = 0;
    this[10].lpVtbl = 0;
    goto LABEL_13;
  }
  this[8].lpVtbl = (struct IUnknownVtbl *)&this[19];
  return 0;
}

```

## disassembly

```asm
0x180041808  mov     rax, rsp
0x18004180b  mov     [rax+8], rbx
0x18004180f  mov     [rax+10h], rbp
0x180041813  mov     [rax+18h], rsi
0x180041817  mov     [rax+20h], rdi
0x18004181b  push    r14
0x18004181d  sub     rsp, 20h
0x180041821  xor     r9d, r9d; lpName
0x180041824  mov     rdi, rcx
0x180041827  xor     ecx, ecx; lpEventAttributes
0x180041829  lea     ebx, [r9+1]
0x18004182d  mov     r8d, ebx; bInitialState
0x180041830  mov     edx, ebx; bManualReset
0x180041832  call    cs:__imp_CreateEventW
0x180041838  mov     [rdi+10h], rax
0x18004183c  test    rax, rax
0x18004183f  jz      short loc_1800418BF
0x180041841  xor     r9d, r9d; lpName
0x180041844  xor     r8d, r8d; bInitialState
0x180041847  mov     edx, ebx; bManualReset
0x180041849  xor     ecx, ecx; lpEventAttributes
0x18004184b  call    cs:__imp_CreateEventW
0x180041851  mov     [rdi+20h], rax
0x180041855  test    rax, rax
0x180041858  jz      short loc_1800418BF
0x18004185a  lea     rbp, [rdi+98h]
0x180041861  mov     rcx, rbp; this
0x180041864  call    ?Initialize@CSupportWeakRef@@QEAAJXZ; CSupportWeakRef::Initialize(void)
0x180041869  mov     ebx, eax
0x18004186b  test    eax, eax
0x18004186d  js      short loc_1800418DD
0x18004186f  lea     r14, [rdi+48h]
0x180041873  mov     [rdi+50h], rdi
0x180041877  mov     rdx, r14; ppunkMarshal
0x18004187a  lea     rcx, [rdi+38h]; punkOuter
0x18004187e  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180041884  mov     ebx, eax
0x180041886  test    eax, eax
0x180041888  js      short loc_180041892
0x18004188a  mov     [rdi+40h], rbp
0x18004188e  xor     ebx, ebx
0x180041890  jmp     short loc_1800418E5
0x180041892  mov     rcx, [r14]
0x180041895  test    rcx, rcx
0x180041898  jz      short loc_1800418A6
0x18004189a  mov     rax, [rcx]
0x18004189d  mov     rax, [rax+10h]
0x1800418a1  call    _guard_dispatch_icall
0x1800418a6  mov     qword ptr [r14], 0
0x1800418ad  mov     qword ptr [rdi+40h], 0
0x1800418b5  mov     qword ptr [rdi+50h], 0
0x1800418bd  jmp     short loc_1800418DD
0x1800418bf  call    cs:__imp_GetLastError
0x1800418c5  movzx   ebx, ax
0x1800418c8  or      ebx, 80070000h
0x1800418ce  test    eax, eax
0x1800418d0  cmovle  ebx, eax
0x1800418d3  mov     eax, 8000FFFFh
0x1800418d8  test    ebx, ebx
0x1800418da  cmovns  ebx, eax
0x1800418dd  mov     rcx, rdi; this
0x1800418e0  call    ?Clear@CSusInternalWrapper@@QEAAJXZ; CSusInternalWrapper::Clear(void)
0x1800418e5  mov     rbp, [rsp+28h+arg_8]
0x1800418ea  mov     eax, ebx
0x1800418ec  mov     rbx, [rsp+28h+arg_0]
0x1800418f1  mov     rsi, [rsp+28h+arg_10]
0x1800418f6  mov     rdi, [rsp+28h+arg_18]
0x1800418fb  add     rsp, 20h
0x1800418ff  pop     r14
0x180041901  retn
```
