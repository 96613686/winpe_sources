# TetheringService::ResetInactivityTimerIfNotSharing(void)

- ea: `0x18001c0dc`
- end: `0x18001c17e`
- name: `?ResetInactivityTimerIfNotSharing@TetheringService@@AEAAXXZ`
- size: `162`
- prototype: `void __fastcall(TetheringService *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180017adc`
- `0x1800182e4`
- `0x180018a60`
- `0x180018b40`
- `0x18001c75c`
- `0x18001dc08`
- `0x18001fe44`

## callees

- `0x18000bf4c`
- `0x18001c0dc`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001c13b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001c13b`

## pseudocode

```c
void __fastcall TetheringService::ResetInactivityTimerIfNotSharing(TetheringService *this)
{
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  if ( *((_DWORD *)this + 56) == 3
    && ChangeTimerQueueTimer(*((HANDLE *)this + 204), *((HANDLE *)this + 203), *((_DWORD *)this + 410), 0xFFFFFFFF) )
  {
    *((_BYTE *)this + 1644) = 1;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 323, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
}

```

## disassembly

```asm
0x18001c0dc  mov     [rsp+arg_0], rbx
0x18001c0e1  push    rdi
0x18001c0e2  sub     rsp, 20h
0x18001c0e6  mov     rbx, rcx
0x18001c0e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0f0  lea     rdi, WPP_GLOBAL_Control
0x18001c0f7  cmp     rcx, rdi
0x18001c0fa  jz      short loc_18001C117
0x18001c0fc  test    byte ptr [rcx+1Ch], 8
0x18001c100  jz      short loc_18001C117
0x18001c102  mov     rcx, [rcx+10h]
0x18001c106  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c10d  mov     edx, 142h
0x18001c112  call    WPP_SF_
0x18001c117  mov     eax, [rbx+0E0h]
0x18001c11d  cmp     eax, 3
0x18001c120  jnz     short loc_18001C14C
0x18001c122  mov     r8d, [rbx+668h]; DueTime
0x18001c129  or      r9d, 0FFFFFFFFh; Period
0x18001c12d  mov     rdx, [rbx+658h]; Timer
0x18001c134  mov     rcx, [rbx+660h]; TimerQueue
0x18001c13b  call    cs:__imp_ChangeTimerQueueTimer
0x18001c141  test    eax, eax
0x18001c143  jz      short loc_18001C14C
0x18001c145  mov     byte ptr [rbx+66Ch], 1
0x18001c14c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c153  cmp     rcx, rdi
0x18001c156  jz      short loc_18001C173
0x18001c158  test    byte ptr [rcx+1Ch], 8
0x18001c15c  jz      short loc_18001C173
0x18001c15e  mov     rcx, [rcx+10h]
0x18001c162  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c169  mov     edx, 143h
0x18001c16e  call    WPP_SF_
0x18001c173  mov     rbx, [rsp+28h+arg_0]
0x18001c178  add     rsp, 20h
0x18001c17c  pop     rdi
0x18001c17d  retn
```
