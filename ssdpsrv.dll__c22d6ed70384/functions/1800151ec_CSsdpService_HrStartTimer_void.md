# CSsdpService::HrStartTimer(void)

- ea: `0x1800151ec`
- end: `0x180015283`
- name: `?HrStartTimer@CSsdpService@@QEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800161b4`

## callees

- `0x1800140e0`
- `0x1800151ec`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001526b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001526b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001520a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001520a`

## pseudocode

```c
__int64 __fastcall CSsdpService::HrStartTimer(char *Parameter)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v3; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 224);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 224));
  if ( (Parameter[264] & 2) != 0 || (v3 = CTimerBase::HrSetTimer(Parameter, 0), v3 >= 0) )
    **((_QWORD **)Parameter + 34) = Parameter;
  if ( v3 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids, (unsigned int)v3);
  LeaveCriticalSection(v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800151ec  mov     [rsp+arg_0], rbx
0x1800151f1  mov     [rsp+arg_8], rsi
0x1800151f6  push    rdi
0x1800151f7  sub     rsp, 20h
0x1800151fb  lea     rsi, [rcx+0E0h]
0x180015202  mov     rdi, rcx
0x180015205  mov     rcx, rsi; lpCriticalSection
0x180015208  xor     ebx, ebx
0x18001520a  call    cs:__imp_EnterCriticalSection
0x180015210  test    byte ptr [rdi+108h], 2
0x180015217  jnz     short loc_180015229
0x180015219  xor     edx, edx; DueTime
0x18001521b  mov     rcx, rdi; Parameter
0x18001521e  call    ?HrSetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrSetTimer(ulong)
0x180015223  mov     ebx, eax
0x180015225  test    eax, eax
0x180015227  js      short loc_180015233
0x180015229  mov     rcx, [rdi+110h]
0x180015230  mov     [rcx], rdi
0x180015233  test    ebx, ebx
0x180015235  jz      short loc_180015268
0x180015237  mov     rcx, cs:WPP_GLOBAL_Control
0x18001523e  lea     rax, WPP_GLOBAL_Control
0x180015245  cmp     rcx, rax
0x180015248  jz      short loc_180015268
0x18001524a  test    byte ptr [rcx+1Ch], 1
0x18001524e  jz      short loc_180015268
0x180015250  mov     rcx, [rcx+10h]
0x180015254  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x18001525b  mov     edx, 12h
0x180015260  mov     r9d, ebx
0x180015263  call    WPP_SF_d
0x180015268  mov     rcx, rsi; lpCriticalSection
0x18001526b  call    cs:__imp_LeaveCriticalSection
0x180015271  mov     rsi, [rsp+28h+arg_8]
0x180015276  mov     eax, ebx
0x180015278  mov     rbx, [rsp+28h+arg_0]
0x18001527d  add     rsp, 20h
0x180015281  pop     rdi
0x180015282  retn
```
