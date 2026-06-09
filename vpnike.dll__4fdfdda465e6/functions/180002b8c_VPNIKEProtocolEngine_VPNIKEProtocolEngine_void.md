# VPNIKEProtocolEngine::~VPNIKEProtocolEngine(void)

- ea: `0x180002b8c`
- end: `0x180002cb5`
- name: `??1VPNIKEProtocolEngine@@MEAA@XZ`
- size: `297`
- prototype: `void __fastcall(PTP_WORK *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002cc0`

## callees

- `0x180002b8c`
- `0x180007794`
- `0x18005e008`
- `0x1800768d4`
- `0x180076b60`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002c5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002c5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180002c4e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180002c4e`

## string_xrefs

- `0x180002c22`: `VPNIKEProtocolEngine::~VPNIKEProtocolEngine`

## pseudocode

```c
void __fastcall VPNIKEProtocolEngine::~VPNIKEProtocolEngine(PTP_WORK *this)
{
  PVOID *v2; // rcx
  __int64 v3; // [rsp+20h] [rbp-48h] BYREF
  __int128 v4; // [rsp+28h] [rbp-40h]
  __int128 v5; // [rsp+38h] [rbp-30h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+50h] [rbp-18h]
  int v8; // [rsp+54h] [rbp-14h]

  *this = (PTP_WORK)&VPNIKEProtocolEngine::`vftable';
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = 0;
  v3 = 0;
  v5 = 0;
  v6 = 0;
  v7 = -1;
  v8 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v3,
      L"VPNIKEProtocolEngine::~VPNIKEProtocolEngine",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( this[17] )
  {
    WaitForThreadpoolWorkCallbacks(this[17], 1);
    CloseThreadpoolWork(this[17]);
    this[17] = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 107, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v3);
  BaseProtocolEngine::~BaseProtocolEngine((BaseProtocolEngine *)this);
}

```

## disassembly

```asm
0x180002b8c  mov     [rsp+arg_0], rbx
0x180002b91  push    rsi
0x180002b92  sub     rsp, 60h
0x180002b96  mov     rbx, rcx
0x180002b99  lea     rax, ??_7VPNIKEProtocolEngine@@6B@; const VPNIKEProtocolEngine::`vftable'
0x180002ba0  mov     [rcx], rax
0x180002ba3  lea     rsi, WPP_GLOBAL_Control
0x180002baa  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bb1  cmp     rcx, rsi
0x180002bb4  jz      short loc_180002BDE
0x180002bb6  test    byte ptr [rcx+1Ch], 1
0x180002bba  jz      short loc_180002BDE
0x180002bbc  cmp     byte ptr [rcx+19h], 6
0x180002bc0  jb      short loc_180002BDE
0x180002bc2  mov     edx, 6Ah ; 'j'
0x180002bc7  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180002bce  mov     rcx, [rcx+10h]
0x180002bd2  call    WPP_SF_
0x180002bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bde  xorps   xmm0, xmm0
0x180002be1  movdqu  [rsp+68h+var_40], xmm0
0x180002be7  mov     [rsp+68h+var_48], 0
0x180002bf0  movdqu  [rsp+68h+var_30], xmm0
0x180002bf6  mov     [rsp+68h+var_20], 0
0x180002bff  mov     [rsp+68h+var_18], 0FFFFFFFFh
0x180002c07  mov     [rsp+68h+var_14], 0
0x180002c0f  test    cs:byte_1800AA941, 8
0x180002c16  jz      short loc_180002C3A
0x180002c18  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180002c1f  xor     r8d, r8d; unsigned int *
0x180002c22  lea     rdx, aVpnikeprotocol; "VPNIKEProtocolEngine::~VPNIKEProtocolEn"...
0x180002c29  lea     rcx, [rsp+68h+var_48]; this
0x180002c2e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180002c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c3a  mov     rax, [rbx+88h]
0x180002c41  test    rax, rax
0x180002c44  jz      short loc_180002C73
0x180002c46  mov     edx, 1; fCancelPendingCallbacks
0x180002c4b  mov     rcx, rax; pwk
0x180002c4e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180002c54  mov     rcx, [rbx+88h]; pwk
0x180002c5b  call    cs:__imp_CloseThreadpoolWork
0x180002c61  mov     qword ptr [rbx+88h], 0
0x180002c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c73  cmp     rcx, rsi
0x180002c76  jz      short loc_180002C99
0x180002c78  test    byte ptr [rcx+1Ch], 1
0x180002c7c  jz      short loc_180002C99
0x180002c7e  cmp     byte ptr [rcx+19h], 6
0x180002c82  jb      short loc_180002C99
0x180002c84  mov     edx, 6Bh ; 'k'
0x180002c89  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180002c90  mov     rcx, [rcx+10h]
0x180002c94  call    WPP_SF_
0x180002c99  lea     rcx, [rsp+68h+var_48]; this
0x180002c9e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180002ca3  mov     rcx, rbx; this
0x180002ca6  mov     rbx, [rsp+68h+arg_0]
0x180002cab  add     rsp, 60h
0x180002caf  pop     rsi
0x180002cb0  jmp     ??1BaseProtocolEngine@@MEAA@XZ; BaseProtocolEngine::~BaseProtocolEngine(void)
```
