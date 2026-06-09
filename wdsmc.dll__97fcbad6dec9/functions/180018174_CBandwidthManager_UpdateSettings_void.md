# CBandwidthManager::UpdateSettings(void)

- ea: `0x180018174`
- end: `0x18001823a`
- name: `?UpdateSettings@CBandwidthManager@@QEAAKXZ`
- size: `198`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800053a0`
- `0x180005e28`

## callees

- `0x180018174`
- `0x18001853c`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800181f7`
- `KERNEL32!LeaveCriticalSection` at `0x180018222`
- `KERNEL32!LeaveCriticalSection` at `0x1800181f7`
- `KERNEL32!LeaveCriticalSection` at `0x180018222`
- `KERNEL32!EnterCriticalSection` at `0x180018186`
- `KERNEL32!EnterCriticalSection` at `0x1800181e7`
- `KERNEL32!EnterCriticalSection` at `0x180018186`
- `KERNEL32!EnterCriticalSection` at `0x1800181e7`

## pseudocode

```c
__int64 __fastcall CBandwidthManager::UpdateSettings(char *lpCriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG v2; // rbx
  PRTL_CRITICAL_SECTION_DEBUG v3; // rbx
  struct CBandwidthManager::Interface *v4; // rdx

  EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  memmove_0(lpCriticalSection + 40, (char *)qword_1800336E8 + 320, 0x9Cu);
  if ( *((_DWORD *)lpCriticalSection + 19) )
  {
    if ( g_ErrLibTraceFunction )
      g_ErrLibTraceFunction(L"[Bandwidth] Maximum %u%% bandwidth usage allowed.");
  }
  else if ( g_ErrLibTraceFunction )
  {
    g_ErrLibTraceFunction(L"[Bandwidth] No limit on bandwidth usage.");
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 216));
  v2 = (PRTL_CRITICAL_SECTION_DEBUG)*((_QWORD *)lpCriticalSection + 25);
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 216));
  if ( v2 )
  {
    v3 = (PRTL_CRITICAL_SECTION_DEBUG)*((_QWORD *)lpCriticalSection + 25);
    while ( v3 )
    {
      v4 = (struct CBandwidthManager::Interface *)v3;
      v3 = *(PRTL_CRITICAL_SECTION_DEBUG *)&v3[2].Type;
      CBandwidthManager::UpdateMulticastSessionGroups((LPCRITICAL_SECTION)lpCriticalSection, v4);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x180018174  mov     [rsp+arg_0], rbx
0x180018179  mov     [rsp+arg_8], rsi
0x18001817e  push    rdi
0x18001817f  sub     rsp, 20h
0x180018183  mov     rsi, rcx
0x180018186  call    cs:__imp_EnterCriticalSection
0x18001818c  mov     rdx, cs:qword_1800336E8
0x180018193  lea     rcx, [rsi+28h]; void *
0x180018197  add     rdx, 140h; Src
0x18001819e  mov     r8d, 9Ch; Size
0x1800181a4  call    memmove_0
0x1800181a9  mov     edx, [rsi+4Ch]
0x1800181ac  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800181b3  test    edx, edx
0x1800181b5  jnz     short loc_1800181CB
0x1800181b7  test    rax, rax
0x1800181ba  jz      short loc_1800181DD
0x1800181bc  lea     rcx, aBandwidthNoLim; "[Bandwidth] No limit on bandwidth usage"...
0x1800181c3  call    cs:__guard_dispatch_icall_fptr
0x1800181c9  jmp     short loc_1800181DD
0x1800181cb  test    rax, rax
0x1800181ce  jz      short loc_1800181DD
0x1800181d0  lea     rcx, aBandwidthMaxim; "[Bandwidth] Maximum %u%% bandwidth usag"...
0x1800181d7  call    cs:__guard_dispatch_icall_fptr
0x1800181dd  lea     rdi, [rsi+0D8h]
0x1800181e4  mov     rcx, rdi; lpCriticalSection
0x1800181e7  call    cs:__imp_EnterCriticalSection
0x1800181ed  mov     rbx, [rsi+0C8h]
0x1800181f4  mov     rcx, rdi; lpCriticalSection
0x1800181f7  call    cs:__imp_LeaveCriticalSection
0x1800181fd  test    rbx, rbx
0x180018200  jz      short loc_18001821F
0x180018202  mov     rbx, [rsi+0C8h]
0x180018209  jmp     short loc_18001821A
0x18001820b  mov     rdx, rbx; struct CBandwidthManager::Interface *
0x18001820e  mov     rcx, rsi; lpCriticalSection
0x180018211  mov     rbx, [rbx+60h]
0x180018215  call    ?UpdateMulticastSessionGroups@CBandwidthManager@@AEAAXPEAUInterface@1@@Z; CBandwidthManager::UpdateMulticastSessionGroups(CBandwidthManager::Interface *)
0x18001821a  test    rbx, rbx
0x18001821d  jnz     short loc_18001820B
0x18001821f  mov     rcx, rsi; lpCriticalSection
0x180018222  call    cs:__imp_LeaveCriticalSection
0x180018228  mov     rbx, [rsp+28h+arg_0]
0x18001822d  xor     eax, eax
0x18001822f  mov     rsi, [rsp+28h+arg_8]
0x180018234  add     rsp, 20h
0x180018238  pop     rdi
0x180018239  retn
```
