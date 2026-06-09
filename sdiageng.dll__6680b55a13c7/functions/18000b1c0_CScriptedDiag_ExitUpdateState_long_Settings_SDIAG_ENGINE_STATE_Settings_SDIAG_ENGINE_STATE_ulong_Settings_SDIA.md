# CScriptedDiag::ExitUpdateState(long,Settings::SDIAG_ENGINE_STATE,Settings::SDIAG_ENGINE_STATE *,ulong,Settings::SDIAG_ENGINE_STATE)

- ea: `0x18000b1c0`
- end: `0x18000b2d3`
- name: `?ExitUpdateState@CScriptedDiag@@AEAAXJW4SDIAG_ENGINE_STATE@Settings@@PEAW423@K0@Z`
- size: `275`
- prototype: `void __fastcall(__int64, int, int, enum Settings::SDIAG_ENGINE_STATE *, __int64, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000ad80`
- `0x18000cf00`
- `0x18000fcf0`
- `0x180011630`

## callees

- `0x18000a730`
- `0x18000b1c0`
- `0x18000fc10`
- `0x180010e04`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000b1db`
- `KERNEL32!EnterCriticalSection` at `0x18000b1db`
- `KERNEL32!LeaveCriticalSection` at `0x18000b2cc`

## string_xrefs

- `0x18000b232`: `CScriptedDiag::Rollback`
- `0x18000b1ec`: `CScriptedDiag::ExitUpdateState`
- `0x18000b261`: `CScriptedDiag::ExitUpdateState`
- `0x18000b298`: `CScriptedDiag::ExitUpdateState`

## pseudocode

```c
void __fastcall CScriptedDiag::ExitUpdateState(
        __int64 a1,
        int a2,
        int a3,
        enum Settings::SDIAG_ENGINE_STATE *a4,
        __int64 a5,
        int a6)
{
  int v10; // edi
  int v11; // eax
  __int64 v12; // rdx

  EnterCriticalSection(&g_CritSec);
  if ( !a4 )
  {
    SdpDebugTrace(1u, L"CScriptedDiag::ExitUpdateState", 2395, -2147024809);
    goto LABEL_16;
  }
  if ( a2 >= 0 )
  {
    v11 = CScriptedDiag::SetState(a1, a6);
    if ( v11 < 0 )
      SdpDebugTrace(2u, L"CScriptedDiag::ExitUpdateState", 2408, v11);
    goto LABEL_14;
  }
  if ( (int)CScriptedDiag::CheckState((CScriptedDiag *)a1, a4, 1u) >= 0 )
  {
    if ( !a3 )
    {
      CScriptedDiag::Reset((CScriptedDiag *)a1);
      goto LABEL_11;
    }
    if ( ((a3 - 2) & 0xFFFFFFFD) != 0 )
    {
      v10 = -2147024809;
      SdpDebugTrace(1u, L"CScriptedDiag::Rollback", 2184, -2147024809);
LABEL_9:
      SdpDebugTrace(2u, L"CScriptedDiag::ExitUpdateState", 2400, v10);
      goto LABEL_11;
    }
    v10 = CScriptedDiag::SetState(a1, a3);
    if ( v10 < 0 )
      goto LABEL_9;
  }
LABEL_11:
  *(_DWORD *)(a1 + 48) |= 0x20u;
LABEL_14:
  v12 = *(_QWORD *)(a1 + 24);
  if ( v12 )
    _InterlockedExchange((volatile __int32 *)(v12 + 60), 0);
LABEL_16:
  LeaveCriticalSection(&g_CritSec);
}

```

## disassembly

```asm
0x18000b1c0  push    rbx
0x18000b1c2  push    rbp
0x18000b1c3  push    rsi
0x18000b1c4  push    rdi
0x18000b1c5  sub     rsp, 28h
0x18000b1c9  mov     rbx, rcx
0x18000b1cc  mov     rbp, r9
0x18000b1cf  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b1d6  mov     edi, r8d
0x18000b1d9  mov     esi, edx
0x18000b1db  call    cs:__imp_EnterCriticalSection
0x18000b1e1  test    rbp, rbp
0x18000b1e4  jnz     short loc_18000B206
0x18000b1e6  mov     r9d, 80070057h; int
0x18000b1ec  lea     rdx, aCscripteddiagE; "CScriptedDiag::ExitUpdateState"
0x18000b1f3  mov     r8d, 95Bh; int
0x18000b1f9  lea     ecx, [rbp+1]; Level
0x18000b1fc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b201  jmp     loc_18000B2BD
0x18000b206  mov     rcx, rbx; this
0x18000b209  test    esi, esi
0x18000b20b  jns     short loc_18000B288
0x18000b20d  mov     r8d, 1; unsigned int
0x18000b213  mov     rdx, rbp; enum Settings::SDIAG_ENGINE_STATE *
0x18000b216  call    ?CheckState@CScriptedDiag@@AEAAJPEAW4SDIAG_ENGINE_STATE@Settings@@K@Z; CScriptedDiag::CheckState(Settings::SDIAG_ENGINE_STATE *,ulong)
0x18000b21b  test    eax, eax
0x18000b21d  js      short loc_18000B282
0x18000b21f  test    edi, edi
0x18000b221  jz      short loc_18000B27A
0x18000b223  lea     eax, [rdi-2]
0x18000b226  test    eax, 0FFFFFFFDh
0x18000b22b  jz      short loc_18000B24E
0x18000b22d  mov     edi, 80070057h
0x18000b232  lea     rdx, aCscripteddiagR; "CScriptedDiag::Rollback"
0x18000b239  mov     r9d, edi; int
0x18000b23c  mov     r8d, 888h; int
0x18000b242  mov     ecx, 1; Level
0x18000b247  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b24c  jmp     short loc_18000B25E
0x18000b24e  mov     edx, edi
0x18000b250  mov     rcx, rbx
0x18000b253  call    ?SetState@CScriptedDiag@@AEAAJW4SDIAG_ENGINE_STATE@Settings@@@Z; CScriptedDiag::SetState(Settings::SDIAG_ENGINE_STATE)
0x18000b258  mov     edi, eax
0x18000b25a  test    eax, eax
0x18000b25c  jns     short loc_18000B282
0x18000b25e  mov     r9d, edi; int
0x18000b261  lea     rdx, aCscripteddiagE; "CScriptedDiag::ExitUpdateState"
0x18000b268  mov     r8d, 960h; int
0x18000b26e  mov     ecx, 2; Level
0x18000b273  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b278  jmp     short loc_18000B282
0x18000b27a  mov     rcx, rbx; this
0x18000b27d  call    ?Reset@CScriptedDiag@@AEAAXXZ; CScriptedDiag::Reset(void)
0x18000b282  or      dword ptr [rbx+30h], 20h
0x18000b286  jmp     short loc_18000B2AF
0x18000b288  mov     edx, [rsp+48h+arg_28]
0x18000b28c  call    ?SetState@CScriptedDiag@@AEAAJW4SDIAG_ENGINE_STATE@Settings@@@Z; CScriptedDiag::SetState(Settings::SDIAG_ENGINE_STATE)
0x18000b291  test    eax, eax
0x18000b293  jns     short loc_18000B2AF
0x18000b295  mov     r9d, eax; int
0x18000b298  lea     rdx, aCscripteddiagE; "CScriptedDiag::ExitUpdateState"
0x18000b29f  mov     r8d, 968h; int
0x18000b2a5  mov     ecx, 2; Level
0x18000b2aa  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b2af  mov     rdx, [rbx+18h]
0x18000b2b3  test    rdx, rdx
0x18000b2b6  jz      short loc_18000B2BD
0x18000b2b8  xor     eax, eax
0x18000b2ba  xchg    eax, [rdx+3Ch]
0x18000b2bd  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CritSec
0x18000b2c4  add     rsp, 28h
0x18000b2c8  pop     rdi
0x18000b2c9  pop     rsi
0x18000b2ca  pop     rbp
0x18000b2cb  pop     rbx
0x18000b2cc  jmp     cs:__imp_LeaveCriticalSection
```
