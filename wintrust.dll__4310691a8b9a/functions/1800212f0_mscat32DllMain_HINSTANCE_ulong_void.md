# mscat32DllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x1800212f0`
- end: `0x180021371`
- name: `?mscat32DllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `129`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800265e8`

## callees

- `0x1800212f0`
- `0x180021378`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021356`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021369`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021356`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021369`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002133a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002133a`

## pseudocode

```c
__int64 __fastcall mscat32DllMain(HINSTANCE a1, unsigned int a2, void *a3)
{
  int v5; // edi
  unsigned int v6; // ebx

  v5 = 0;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      InitializeCriticalSection(&MSCAT_CriticalSection);
      v5 = 1;
    }
  }
  else
  {
    DeleteCriticalSection(&MSCAT_CriticalSection);
  }
  v6 = CatAdminDllMain(a1, a2, a3);
  if ( !v6 && v5 )
    DeleteCriticalSection(&MSCAT_CriticalSection);
  return v6;
}

```

## disassembly

```asm
0x1800212f0  mov     [rsp+arg_0], rbx
0x1800212f5  mov     [rsp+arg_8], rsi
0x1800212fa  push    rdi
0x1800212fb  sub     rsp, 30h
0x1800212ff  mov     rsi, r8
0x180021302  mov     ebx, edx
0x180021304  xor     edi, edi
0x180021306  mov     eax, edx
0x180021308  test    edx, edx
0x18002130a  jz      short loc_18002134F
0x18002130c  cmp     eax, 1
0x18002130f  jz      short loc_180021333
0x180021311  mov     r8, rsi
0x180021314  mov     edx, ebx
0x180021316  call    CatAdminDllMain
0x18002131b  mov     ebx, eax
0x18002131d  test    eax, eax
0x18002131f  jz      short loc_18002135E
0x180021321  mov     eax, ebx
0x180021323  mov     rbx, [rsp+38h+arg_0]
0x180021328  mov     rsi, [rsp+38h+arg_8]
0x18002132d  add     rsp, 30h
0x180021331  pop     rdi
0x180021332  retn
0x180021333  lea     rcx, ?MSCAT_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002133a  call    cs:__imp_InitializeCriticalSection
0x180021340  mov     edi, 1
0x180021345  mov     [rsp+38h+var_18], edi
0x180021349  jmp     short loc_180021311
0x18002134b  xor     ebx, ebx
0x18002134d  jmp     short loc_180021321
0x18002134f  lea     rcx, ?MSCAT_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021356  call    cs:__imp_DeleteCriticalSection
0x18002135c  jmp     short loc_180021311
0x18002135e  test    edi, edi
0x180021360  jz      short loc_180021321
0x180021362  lea     rcx, ?MSCAT_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180021369  call    cs:__imp_DeleteCriticalSection
0x18002136f  jmp     short loc_180021321
```
