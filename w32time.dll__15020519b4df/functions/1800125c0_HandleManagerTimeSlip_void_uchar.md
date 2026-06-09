# HandleManagerTimeSlip(void *,uchar)

- ea: `0x1800125c0`
- end: `0x18001278c`
- name: `?HandleManagerTimeSlip@@YAXPEAXE@Z`
- size: `460`
- prototype: `void __fastcall(int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x1800123b0`

## callees

- `0x18000a818`
- `0x18000e758`
- `0x18000ec50`
- `0x18000f400`
- `0x180011120`
- `0x1800125c0`
- `0x1800127a0`
- `0x180018138`
- `0x18001d9a0`
- `0x18002ca84`
- `0x18004cd1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800125f5`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800126fb`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800125f5`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800126fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012730`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012730`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012679`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012679`

## string_xrefs

- `0x1800126a3`: `W32TmServiceMain: ********** Time Slip Notification **********\n`
- `0x180012763`: `Failed in handling time slip, restart service async`

## pseudocode

```c
void __fastcall HandleManagerTimeSlip(int *a1)
{
  enum TimeProvCmd v2; // ecx
  signed int updated; // edi
  BOOL v4; // esi
  unsigned int v5; // [rsp+38h] [rbp-50h]
  __int64 v6; // [rsp+40h] [rbp-48h]
  int v7; // [rsp+A0h] [rbp+18h] BYREF
  unsigned __int64 v8; // [rsp+A8h] [rbp+20h] BYREF

  v7 = 0;
  v8 = 0;
  v6 = _set_se_translator(SeTransFunc);
  if ( a1 )
    v7 = *a1;
  else
    v7 = 0;
  AccurateGetTickCount(&v8);
  LogThrottledEvent(&_W32TimeRegistrationHandle, W32TIME_OPS_TIME_RESYNC_EVENT, L"ii", 60000, v7 != 1 ? 3 : 0);
  EnterCriticalSection(&CriticalSection);
  v5 = dword_1800A468C;
  if ( (unsigned __int8)FileLogAllowEntry(63) )
    FileLogAdd(L"W32TmServiceMain: ********** Time Slip Notification **********\n");
  updated = UpdateTimerQueue2();
  if ( updated >= 0 )
  {
    updated = HandleManagerHardResync(v2, &v7);
    if ( updated >= 0 )
    {
      updated = UpdateTimerQueue1();
      if ( updated >= 0 )
      {
        _set_se_translator(v6);
        updated = 0;
      }
    }
  }
  v4 = 0;
  if ( !updated )
    v4 = DidNetlogonServiceBitsChange(dword_1800A468C, v5);
  LeaveCriticalSection(&CriticalSection);
  if ( !v4 )
  {
LABEL_15:
    if ( !updated )
      return;
    goto LABEL_16;
  }
  if ( !updated )
  {
    SetNetlogonServiceBits(dword_1800A468C);
    updated = 0;
    goto LABEL_15;
  }
LABEL_16:
  if ( (unsigned __int8)FileLogAllowEntry(73) )
    FileLogAdd(L"Failed in handling time slip, restart service async");
  NotifyShutdown(updated);
}

```

## disassembly

```asm
0x1800125c0  mov     r11, rsp
0x1800125c3  mov     [r11+8], rbx
0x1800125c7  mov     [r11+10h], rsi
0x1800125cb  push    rdi
0x1800125cc  sub     rsp, 80h
0x1800125d3  mov     rdi, rcx
0x1800125d6  xor     ebx, ebx
0x1800125d8  mov     [rsp+88h+var_54], ebx
0x1800125dc  mov     [r11+18h], ebx
0x1800125e0  mov     eax, cs:dword_1800A468C
0x1800125e6  mov     [rsp+88h+var_50], eax
0x1800125ea  mov     [r11+20h], rbx
0x1800125ee  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800125f5  call    cs:__imp__set_se_translator
0x1800125fc  nop     dword ptr [rax+rax+00h]
0x180012601  mov     [rsp+88h+var_48], rax
0x180012606  test    rdi, rdi
0x180012609  jnz     short loc_180012614
0x18001260b  mov     [rsp+88h+arg_10], ebx
0x180012612  jmp     short loc_18001261D
0x180012614  mov     eax, [rdi]
0x180012616  mov     [rsp+88h+arg_10], eax
0x18001261d  lea     rcx, [rsp+88h+arg_18]; unsigned __int64 *
0x180012625  call    ?AccurateGetTickCount@@YAXPEA_K@Z; AccurateGetTickCount(unsigned __int64 *)
0x18001262a  mov     edi, 1
0x18001262f  mov     eax, edi
0x180012631  sub     eax, [rsp+88h+arg_10]
0x180012638  neg     eax
0x18001263a  sbb     rcx, rcx
0x18001263d  and     ecx, 3
0x180012640  mov     rax, [rsp+88h+arg_18]
0x180012648  mov     [rsp+88h+var_60], rax
0x18001264d  mov     [rsp+88h+var_68], rcx
0x180012652  mov     r9d, 0EA60h
0x180012658  lea     r8, aIi; "ii"
0x18001265f  lea     rdx, W32TIME_OPS_TIME_RESYNC_EVENT
0x180012666  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18001266d  call    LogThrottledEvent
0x180012672  lea     rcx, CriticalSection; lpCriticalSection
0x180012679  call    cs:__imp_EnterCriticalSection
0x180012680  nop     dword ptr [rax+rax+00h]
0x180012685  mov     [rsp+88h+var_58], ebx
0x180012689  mov     [rsp+88h+var_54], edi
0x18001268d  mov     eax, cs:dword_1800A468C
0x180012693  mov     [rsp+88h+var_50], eax
0x180012697  lea     ecx, [rdi+3Eh]
0x18001269a  call    FileLogAllowEntry
0x18001269f  test    al, al
0x1800126a1  jz      short loc_1800126AF
0x1800126a3  lea     rcx, aW32tmservicema_12; "W32TmServiceMain: ********** Time Slip "...
0x1800126aa  call    FileLogAdd
0x1800126af  call    ?UpdateTimerQueue2@@YAJXZ; UpdateTimerQueue2(void)
0x1800126b4  mov     edi, eax
0x1800126b6  mov     [rsp+88h+var_58], eax
0x1800126ba  test    eax, eax
0x1800126bc  jns     short loc_1800126C0
0x1800126be  jmp     short loc_180012712
0x1800126c0  lea     rdx, [rsp+88h+arg_10]; void *
0x1800126c8  call    ?HandleManagerHardResync@@YAJW4TimeProvCmd@@PEAX@Z; HandleManagerHardResync(TimeProvCmd,void *)
0x1800126cd  mov     edi, eax
0x1800126cf  mov     [rsp+88h+var_58], eax
0x1800126d3  test    eax, eax
0x1800126d5  jns     short loc_1800126D9
0x1800126d7  jmp     short loc_180012712
0x1800126d9  call    ?UpdateTimerQueue1@@YAJXZ; UpdateTimerQueue1(void)
0x1800126de  mov     edi, eax
0x1800126e0  mov     [rsp+88h+var_58], eax
0x1800126e4  test    eax, eax
0x1800126e6  jns     short loc_1800126EA
0x1800126e8  jmp     short loc_180012712
0x1800126ea  jmp     short loc_1800126F6
0x1800126ec  jmp     short loc_1800126F0
0x1800126ee  jmp     short $+2
0x1800126f0  xor     ebx, ebx
0x1800126f2  mov     edi, [rsp+88h+var_58]
0x1800126f6  mov     rcx, [rsp+88h+var_48]
0x1800126fb  call    cs:__imp__set_se_translator
0x180012702  nop     dword ptr [rax+rax+00h]
0x180012707  test    edi, edi
0x180012709  cmovns  edi, ebx
0x18001270c  cmp     [rsp+88h+var_54], ebx
0x180012710  jz      short loc_180012751
0x180012712  mov     esi, ebx
0x180012714  test    edi, edi
0x180012716  jnz     short loc_180012729
0x180012718  mov     edx, [rsp+88h+var_50]; unsigned int
0x18001271c  mov     ecx, cs:dword_1800A468C; unsigned int
0x180012722  call    ?DidNetlogonServiceBitsChange@@YAHKK@Z; DidNetlogonServiceBitsChange(ulong,ulong)
0x180012727  mov     esi, eax
0x180012729  lea     rcx, CriticalSection; lpCriticalSection
0x180012730  call    cs:__imp_LeaveCriticalSection
0x180012737  nop     dword ptr [rax+rax+00h]
0x18001273c  test    esi, esi
0x18001273e  jz      short loc_180012751
0x180012740  test    edi, edi
0x180012742  jnz     short loc_180012755
0x180012744  mov     ecx, cs:dword_1800A468C; unsigned int
0x18001274a  call    ?SetNetlogonServiceBits@@YAJK@Z; SetNetlogonServiceBits(ulong)
0x18001274f  mov     edi, ebx
0x180012751  test    edi, edi
0x180012753  jz      short loc_180012776
0x180012755  mov     ecx, 49h ; 'I'
0x18001275a  call    FileLogAllowEntry
0x18001275f  test    al, al
0x180012761  jz      short loc_18001276F
0x180012763  lea     rcx, aFailedInHandli_3; "Failed in handling time slip, restart s"...
0x18001276a  call    FileLogAdd
0x18001276f  mov     ecx, edi; unsigned int
0x180012771  call    ?NotifyShutdown@@YAJK@Z; NotifyShutdown(ulong)
0x180012776  lea     r11, [rsp+88h+var_8]
0x18001277e  mov     rbx, [r11+10h]
0x180012782  mov     rsi, [r11+18h]
0x180012786  mov     rsp, r11
0x180012789  pop     rdi
0x18001278a  retn
```
