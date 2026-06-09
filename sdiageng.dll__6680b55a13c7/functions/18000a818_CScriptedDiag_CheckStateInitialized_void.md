# CScriptedDiag::CheckStateInitialized(void)

- ea: `0x18000a818`
- end: `0x18000a863`
- name: `?CheckStateInitialized@CScriptedDiag@@AEAAJXZ`
- size: `75`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800100b0`
- `0x180013320`
- `0x1800133d0`
- `0x1800134a0`
- `0x180013570`
- `0x180013650`
- `0x180013720`
- `0x180013820`
- `0x1800138d0`
- `0x180013a10`
- `0x180013b20`

## callees

- `0x18000a730`
- `0x18000a818`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::CheckStateInitialized(CScriptedDiag *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+38h] [rbp+10h] BYREF
  int v5; // [rsp+3Ch] [rbp+14h]

  v4 = 4;
  v5 = 2;
  v1 = CScriptedDiag::CheckState(this, (enum Settings::SDIAG_ENGINE_STATE *)&v4, 2u);
  v2 = v1;
  if ( v1 < 0 )
    SdpDebugTrace(1u, L"CScriptedDiag::CheckStateInitialized", 2282, v1);
  return v2;
}

```

## disassembly

```asm
0x18000a818  push    rbx
0x18000a81a  sub     rsp, 20h
0x18000a81e  mov     r8d, 2; unsigned int
0x18000a824  mov     [rsp+28h+arg_8], 4
0x18000a82c  lea     rdx, [rsp+28h+arg_8]; enum Settings::SDIAG_ENGINE_STATE *
0x18000a831  mov     [rsp+28h+arg_C], r8d
0x18000a836  call    ?CheckState@CScriptedDiag@@AEAAJPEAW4SDIAG_ENGINE_STATE@Settings@@K@Z; CScriptedDiag::CheckState(Settings::SDIAG_ENGINE_STATE *,ulong)
0x18000a83b  mov     ebx, eax
0x18000a83d  test    eax, eax
0x18000a83f  jns     short loc_18000A85B
0x18000a841  mov     r9d, eax; int
0x18000a844  lea     rdx, aCscripteddiagC_2; "CScriptedDiag::CheckStateInitialized"
0x18000a84b  mov     r8d, 8EAh; int
0x18000a851  mov     ecx, 1; Level
0x18000a856  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000a85b  mov     eax, ebx
0x18000a85d  add     rsp, 20h
0x18000a861  pop     rbx
0x18000a862  retn
```
