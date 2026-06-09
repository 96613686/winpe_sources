# WFDSConMgr::Timer::CreateTimer(WFDSConMgr::CThreadpoolEnvironment *)

- ea: `0x18005e22c`
- end: `0x18005e317`
- name: `?CreateTimer@Timer@WFDSConMgr@@QEAAXPEAVCThreadpoolEnvironment@2@@Z`
- size: `235`
- prototype: `void __fastcall(PVOID pv, struct WFDSConMgr::CThreadpoolEnvironment *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005e124`

## callees

- `0x180006740`
- `0x18005c800`
- `0x18005e22c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e275`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005e266`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005e266`

## string_xrefs

- `0x18005e287`: `CreateThreadpoolTimer failed`
- `0x18005e2ec`: `CreateTimer() called on a Timer which had already been initialized`
- `0x18005e2a2`: `WFDSConMgr::Timer::CreateTimer`
- `0x18005e305`: `WFDSConMgr::Timer::CreateTimer`

## pseudocode

```c
void __fastcall WFDSConMgr::Timer::CreateTimer(_QWORD *pv, struct WFDSConMgr::CThreadpoolEnvironment *a2)
{
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax

  if ( pv[4] || pv[3] )
    WFDSConMgr::CException::Throw(
      -2147023649,
      "WFDSConMgr::Timer::CreateTimer",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\timer.cpp",
      45,
      L"CreateTimer() called on a Timer which had already been initialized");
  pv[4] = a2;
  ThreadpoolTimer = CreateThreadpoolTimer(
                      WFDSConMgr::Timer::StartRoutine,
                      pv,
                      (PTP_CALLBACK_ENVIRON)(((unsigned __int64)a2 + 16) & -(__int64)(a2 != 0)));
  pv[3] = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WFDSConMgr::CException::Throw(
      LastError,
      "WFDSConMgr::Timer::CreateTimer",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\timer.cpp",
      38,
      L"CreateThreadpoolTimer failed");
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_621daf02e21a36dfd02ebab89b470631_Traceguids, pv);
  }
}

```

## disassembly

```asm
0x18005e22c  push    rbx
0x18005e22e  sub     rsp, 30h
0x18005e232  cmp     qword ptr [rcx+20h], 0
0x18005e237  mov     rbx, rcx
0x18005e23a  jnz     loc_18005E2EC
0x18005e240  cmp     qword ptr [rcx+18h], 0
0x18005e245  jnz     loc_18005E2EC
0x18005e24b  mov     [rcx+20h], rdx
0x18005e24f  lea     rax, [rdx+10h]
0x18005e253  neg     rdx
0x18005e256  mov     rdx, rcx; pv
0x18005e259  lea     rcx, ?StartRoutine@Timer@WFDSConMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAV12@PEAU_TP_TIMER@@@Z; pfnti
0x18005e260  sbb     r8, r8
0x18005e263  and     r8, rax; pcbe
0x18005e266  call    cs:__imp_CreateThreadpoolTimer
0x18005e26c  mov     [rbx+18h], rax
0x18005e270  test    rax, rax
0x18005e273  jnz     short loc_18005E2AF
0x18005e275  call    cs:__imp_GetLastError
0x18005e27b  test    eax, eax
0x18005e27d  jle     short loc_18005E287
0x18005e27f  movzx   eax, ax
0x18005e282  or      eax, 80070000h
0x18005e287  lea     rcx, aCreatethreadpo_0; "CreateThreadpoolTimer failed"
0x18005e28e  mov     r9d, 26h ; '&'; char
0x18005e294  mov     [rsp+38h+var_18], rcx; unsigned __int16 *
0x18005e299  lea     r8, aOnecoreuapNetW_24; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005e2a0  mov     ecx, eax; int
0x18005e2a2  lea     rdx, aWfdsconmgrTime; "WFDSConMgr::Timer::CreateTimer"
0x18005e2a9  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18005e2af  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e2b6  lea     rax, WPP_GLOBAL_Control
0x18005e2bd  cmp     rcx, rax
0x18005e2c0  jz      short loc_18005E2E6
0x18005e2c2  cmp     byte ptr [rcx+19h], 4
0x18005e2c6  jb      short loc_18005E2E6
0x18005e2c8  test    byte ptr [rcx+1Ch], 1
0x18005e2cc  jz      short loc_18005E2E6
0x18005e2ce  mov     rcx, [rcx+10h]
0x18005e2d2  lea     r8, WPP_621daf02e21a36dfd02ebab89b470631_Traceguids
0x18005e2d9  mov     edx, 0Ah
0x18005e2de  mov     r9, rbx
0x18005e2e1  call    WPP_SF_q
0x18005e2e6  add     rsp, 30h
0x18005e2ea  pop     rbx
0x18005e2eb  retn
0x18005e2ec  lea     rax, aCreatetimerCal; "CreateTimer() called on a Timer which h"...
0x18005e2f3  mov     r9d, 2Dh ; '-'; char
0x18005e2f9  lea     r8, aOnecoreuapNetW_24; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005e300  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18005e305  lea     rdx, aWfdsconmgrTime; "WFDSConMgr::Timer::CreateTimer"
0x18005e30c  mov     ecx, 800704DFh; int
0x18005e311  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
```
