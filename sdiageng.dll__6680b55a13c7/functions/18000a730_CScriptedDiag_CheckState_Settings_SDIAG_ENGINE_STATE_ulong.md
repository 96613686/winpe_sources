# CScriptedDiag::CheckState(Settings::SDIAG_ENGINE_STATE *,ulong)

- ea: `0x18000a730`
- end: `0x18000a80f`
- name: `?CheckState@CScriptedDiag@@AEAAJPEAW4SDIAG_ENGINE_STATE@Settings@@K@Z`
- size: `223`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, enum Settings::SDIAG_ENGINE_STATE *, unsigned int)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a000`
- `0x18000a2f4`
- `0x18000a4e0`
- `0x18000a5b4`
- `0x18000a818`
- `0x18000ad80`
- `0x18000b1c0`
- `0x18000dbb4`
- `0x18000ec48`
- `0x18000edf8`
- `0x180013f10`

## callees

- `0x180001264`
- `0x18000a730`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a749`
- `KERNEL32!EnterCriticalSection` at `0x18000a749`
- `KERNEL32!LeaveCriticalSection` at `0x18000a7e6`
- `KERNEL32!LeaveCriticalSection` at `0x18000a7e6`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::CheckState(
        CScriptedDiag *this,
        enum Settings::SDIAG_ENGINE_STATE *a2,
        unsigned int a3)
{
  unsigned int v6; // ebx
  int v7; // r8d
  _QWORD *v8; // rax
  unsigned int v9; // ecx

  EnterCriticalSection(&g_CritSec);
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 2225;
LABEL_3:
    SdpDebugTrace(1u, L"CScriptedDiag::CheckState", v7, v6);
    goto LABEL_11;
  }
  v8 = (_QWORD *)*((_QWORD *)this + 3);
  if ( !v8 )
  {
    v8 = operator new(0x60u);
    if ( !v8 )
    {
      *((_QWORD *)this + 3) = 0;
      v7 = 2229;
      v6 = -2147024882;
      goto LABEL_3;
    }
    *v8 = 0;
    v8[1] = 0;
    v8[2] = 0;
    v8[3] = 0;
    v8[4] = 0;
    v8[5] = 0;
    v8[6] = 0;
    v8[7] = 0;
    v8[8] = 0;
    v8[9] = 0;
    v8[10] = 0;
    *((_DWORD *)v8 + 22) = 0;
    *((_QWORD *)this + 3) = v8;
  }
  v9 = 0;
  if ( a3 )
  {
    while ( *((_DWORD *)v8 + 22) != *((_DWORD *)a2 + v9) )
    {
      if ( ++v9 >= a3 )
        goto LABEL_10;
    }
    v6 = 0;
  }
  else
  {
LABEL_10:
    v6 = -2147418113;
  }
LABEL_11:
  LeaveCriticalSection(&g_CritSec);
  return v6;
}

```

## disassembly

```asm
0x18000a730  push    rbx
0x18000a732  push    rbp
0x18000a733  push    rsi
0x18000a734  push    rdi
0x18000a735  sub     rsp, 28h
0x18000a739  mov     rbx, rcx
0x18000a73c  mov     edi, r8d
0x18000a73f  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a746  mov     rsi, rdx
0x18000a749  call    cs:__imp_EnterCriticalSection
0x18000a74f  xor     ebp, ebp
0x18000a751  test    rsi, rsi
0x18000a754  jnz     short loc_18000A777
0x18000a756  mov     ebx, 80070057h
0x18000a75b  mov     r8d, 8B1h; int
0x18000a761  mov     r9d, ebx; int
0x18000a764  lea     rdx, aCscripteddiagC_1; "CScriptedDiag::CheckState"
0x18000a76b  mov     ecx, 1; Level
0x18000a770  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000a775  jmp     short loc_18000A7DF
0x18000a777  mov     rax, [rbx+18h]
0x18000a77b  test    rax, rax
0x18000a77e  jnz     short loc_18000A7C4
0x18000a780  lea     ecx, [rax+60h]; Size
0x18000a783  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a788  mov     [rsp+48h+arg_8], rax
0x18000a78d  test    rax, rax
0x18000a790  jz      short loc_18000A7F7
0x18000a792  mov     [rax], rbp
0x18000a795  mov     [rax+8], rbp
0x18000a799  mov     [rax+10h], rbp
0x18000a79d  mov     [rax+18h], rbp
0x18000a7a1  mov     [rax+20h], rbp
0x18000a7a5  mov     [rax+28h], rbp
0x18000a7a9  mov     [rax+30h], rbp
0x18000a7ad  mov     [rax+38h], rbp
0x18000a7b1  mov     [rax+40h], rbp
0x18000a7b5  mov     [rax+48h], rbp
0x18000a7b9  mov     [rax+50h], rbp
0x18000a7bd  mov     [rax+58h], ebp
0x18000a7c0  mov     [rbx+18h], rax
0x18000a7c4  mov     edx, [rax+58h]
0x18000a7c7  mov     ecx, ebp
0x18000a7c9  test    edi, edi
0x18000a7cb  jz      short loc_18000A7DA
0x18000a7cd  mov     eax, ecx
0x18000a7cf  cmp     edx, [rsi+rax*4]
0x18000a7d2  jz      short loc_18000A80B
0x18000a7d4  inc     ecx
0x18000a7d6  cmp     ecx, edi
0x18000a7d8  jb      short loc_18000A7CD
0x18000a7da  mov     ebx, 8000FFFFh
0x18000a7df  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a7e6  call    cs:__imp_LeaveCriticalSection
0x18000a7ec  mov     eax, ebx
0x18000a7ee  add     rsp, 28h
0x18000a7f2  pop     rdi
0x18000a7f3  pop     rsi
0x18000a7f4  pop     rbp
0x18000a7f5  pop     rbx
0x18000a7f6  retn
0x18000a7f7  mov     [rbx+18h], rbp
0x18000a7fb  mov     r8d, 8B5h
0x18000a801  mov     ebx, 8007000Eh
0x18000a806  jmp     loc_18000A761
0x18000a80b  mov     ebx, ebp
0x18000a80d  jmp     short loc_18000A7DF
```
