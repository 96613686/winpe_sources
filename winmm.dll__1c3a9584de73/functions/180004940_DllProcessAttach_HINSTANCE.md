# DllProcessAttach(HINSTANCE__ *)

- ea: `0x180004940`
- end: `0x180004a1d`
- name: `?DllProcessAttach@@YAHPEAUHINSTANCE__@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004774`

## callees

- `0x180004940`
- `0x180004a24`
- `0x180004ac0`
- `0x180004d5c`
- `0x18000b6d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800049a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800049a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180004983`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180004983`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180004963`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180004963`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180004944`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180004944`

## pseudocode

```c
__int64 __fastcall DllProcessAttach(HINSTANCE a1)
{
  int v1; // edx
  struct _RTL_CRITICAL_SECTION **v2; // rcx
  int v4; // edx
  struct _RTL_CRITICAL_SECTION **v5; // rcx

  DisableThreadLibraryCalls(a1);
  hHeap = NtCurrentPeb()->ProcessHeap;
  if ( !hHeap )
    return 0;
  gTlsIndex = TlsAlloc();
  if ( gTlsIndex == -1 )
    return 0;
  if ( !(unsigned int)mmInitializeMultipleCriticalSections(v2, v1) )
  {
LABEL_4:
    TlsFree(gTlsIndex);
    gTlsIndex = -1;
    return 0;
  }
  hEventApiInit = CreateEventW(0, 1, 0, 0);
  if ( !hEventApiInit )
  {
    hEventApiInit = 0;
    mmDeleteMultipleCriticalSections(v5, v4);
    goto LABEL_4;
  }
  gfValidCS = 1;
  if ( !(unsigned int)TimeInit()
    && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b9c43a85d2863af168ea09e2fa4a4263_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x180004940  sub     rsp, 28h
0x180004944  call    cs:__imp_DisableThreadLibraryCalls
0x18000494a  mov     rax, gs:60h
0x180004953  mov     rcx, [rax+30h]
0x180004957  mov     cs:hHeap, rcx
0x18000495e  test    rcx, rcx
0x180004961  jz      short loc_180004993
0x180004963  call    cs:__imp_TlsAlloc
0x180004969  mov     cs:gTlsIndex, eax
0x18000496f  cmp     eax, 0FFFFFFFFh
0x180004972  jz      short loc_180004993
0x180004974  call    ?mmInitializeMultipleCriticalSections@@YAHPEAPEAU_RTL_CRITICAL_SECTION@@J@Z; mmInitializeMultipleCriticalSections(_RTL_CRITICAL_SECTION * *,long)
0x180004979  test    eax, eax
0x18000497b  jnz     short loc_18000499A
0x18000497d  mov     ecx, cs:gTlsIndex; dwTlsIndex
0x180004983  call    cs:__imp_TlsFree
0x180004989  mov     cs:gTlsIndex, 0FFFFFFFFh
0x180004993  xor     eax, eax
0x180004995  add     rsp, 28h
0x180004999  retn
0x18000499a  xor     r9d, r9d; lpName
0x18000499d  xor     r8d, r8d; bInitialState
0x1800049a0  xor     ecx, ecx; lpEventAttributes
0x1800049a2  lea     edx, [r9+1]; bManualReset
0x1800049a6  call    cs:__imp_CreateEventW
0x1800049ac  mov     cs:hEventApiInit, rax
0x1800049b3  test    rax, rax
0x1800049b6  jz      short loc_1800049D2
0x1800049b8  mov     cs:?gfValidCS@@3HA, 1; int gfValidCS
0x1800049c2  call    TimeInit
0x1800049c7  test    eax, eax
0x1800049c9  jz      short loc_1800049E4
0x1800049cb  mov     eax, 1
0x1800049d0  jmp     short loc_180004995
0x1800049d2  mov     cs:hEventApiInit, 0
0x1800049dd  call    ?mmDeleteMultipleCriticalSections@@YAXPEAPEAU_RTL_CRITICAL_SECTION@@J@Z; mmDeleteMultipleCriticalSections(_RTL_CRITICAL_SECTION * *,long)
0x1800049e2  jmp     short loc_18000497D
0x1800049e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049eb  lea     rax, WPP_GLOBAL_Control
0x1800049f2  cmp     rcx, rax
0x1800049f5  jz      short loc_1800049CB
0x1800049f7  test    dword ptr [rcx+1Ch], 400000h
0x1800049fe  jz      short loc_1800049CB
0x180004a00  cmp     byte ptr [rcx+19h], 2
0x180004a04  jb      short loc_1800049CB
0x180004a06  mov     rcx, [rcx+10h]
0x180004a0a  lea     r8, WPP_b9c43a85d2863af168ea09e2fa4a4263_Traceguids
0x180004a11  mov     edx, 0Bh
0x180004a16  call    WPP_SF_
0x180004a1b  jmp     short loc_1800049CB
```
