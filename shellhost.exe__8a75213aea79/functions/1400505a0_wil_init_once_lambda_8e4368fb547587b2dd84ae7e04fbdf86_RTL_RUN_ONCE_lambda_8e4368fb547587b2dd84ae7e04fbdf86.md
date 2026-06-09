# wil::init_once<_lambda_8e4368fb547587b2dd84ae7e04fbdf86_>(_RTL_RUN_ONCE &,_lambda_8e4368fb547587b2dd84ae7e04fbdf86_)

- ea: `0x1400505a0`
- end: `0x140050600`
- name: `??$init_once@V_lambda_8e4368fb547587b2dd84ae7e04fbdf86_@@@wil@@YA_NAEAT_RTL_RUN_ONCE@@V_lambda_8e4368fb547587b2dd84ae7e04fbdf86_@@@Z`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140057d88`

## callees

- `0x1400505a0`
- `0x140053f5c`
- `0x14005d180`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400505e4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400505e4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400505c2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400505c2`

## pseudocode

```c
char __fastcall wil::init_once<_lambda_8e4368fb547587b2dd84ae7e04fbdf86_>(__int64 a1)
{
  void *v1; // rdx
  unsigned int v2; // r8d
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  BOOL fPending; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+34h] [rbp+Ch]

  v7 = HIDWORD(a1);
  fPending = 0;
  if ( !InitOnceBeginInitialize(&FlowEndpointBase::s_initDefaultTimeoutMsOnce, 0, &fPending, 0) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v1, v2, v3);
  if ( !fPending )
    return 0;
  _lambda_8e4368fb547587b2dd84ae7e04fbdf86_::operator()();
  InitOnceComplete(&FlowEndpointBase::s_initDefaultTimeoutMsOnce, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x1400505a0  mov     qword ptr [rsp+fPending], rcx
0x1400505a5  sub     rsp, 28h
0x1400505a9  xor     r9d, r9d; lpContext
0x1400505ac  mov     [rsp+28h+fPending], 0
0x1400505b4  lea     r8, [rsp+28h+fPending]; fPending
0x1400505b9  xor     edx, edx; dwFlags
0x1400505bb  lea     rcx, ?s_initDefaultTimeoutMsOnce@FlowEndpointBase@@1T_RTL_RUN_ONCE@@A; lpInitOnce
0x1400505c2  call    cs:__imp_InitOnceBeginInitialize
0x1400505c8  test    eax, eax
0x1400505ca  jz      short loc_1400505F5
0x1400505cc  cmp     [rsp+28h+fPending], 0
0x1400505d1  jz      short loc_1400505EE
0x1400505d3  call    ??R_lambda_8e4368fb547587b2dd84ae7e04fbdf86_@@QEBA@XZ; _lambda_8e4368fb547587b2dd84ae7e04fbdf86_::operator()(void)
0x1400505d8  xor     r8d, r8d; lpContext
0x1400505db  lea     rcx, ?s_initDefaultTimeoutMsOnce@FlowEndpointBase@@1T_RTL_RUN_ONCE@@A; lpInitOnce
0x1400505e2  xor     edx, edx; dwFlags
0x1400505e4  call    cs:__imp_InitOnceComplete
0x1400505ea  mov     al, 1
0x1400505ec  jmp     short loc_1400505F0
0x1400505ee  xor     al, al
0x1400505f0  add     rsp, 28h
0x1400505f4  retn
0x1400505f5  mov     rcx, [rsp+28h]; this
0x1400505fa  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
