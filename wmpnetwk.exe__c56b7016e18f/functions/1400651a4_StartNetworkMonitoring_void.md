# StartNetworkMonitoring(void)

- ea: `0x1400651a4`
- end: `0x14006537b`
- name: `?StartNetworkMonitoring@@YAKXZ`
- size: `471`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x140052250`

## callees

- `0x140046020`
- `0x140047798`
- `0x1400651a4`
- `0x14006548c`
- `0x140065770`
- `0x1400657e8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400651d6`
- `KERNEL32!EnterCriticalSection` at `0x140065248`
- `KERNEL32!EnterCriticalSection` at `0x1400651d6`
- `KERNEL32!EnterCriticalSection` at `0x140065248`
- `KERNEL32!LeaveCriticalSection` at `0x140065230`
- `KERNEL32!LeaveCriticalSection` at `0x1400652b6`
- `KERNEL32!LeaveCriticalSection` at `0x140065230`
- `KERNEL32!LeaveCriticalSection` at `0x1400652b6`
- `KERNEL32!RegisterWaitForSingleObject` at `0x1400652e3`
- `KERNEL32!RegisterWaitForSingleObject` at `0x1400652e3`
- `KERNEL32!CreateEventW` at `0x1400651fd`
- `KERNEL32!CreateEventW` at `0x1400651fd`
- `KERNEL32!GetLastError` at `0x140065213`
- `KERNEL32!GetLastError` at `0x140065213`
- `KERNEL32!CloseHandle` at `0x14006526b`
- `KERNEL32!CloseHandle` at `0x14006526b`
- `IPHLPAPI!CancelIPChangeNotify` at `0x140065259`
- `IPHLPAPI!CancelIPChangeNotify` at `0x140065259`
- `IPHLPAPI!NotifyAddrChange` at `0x140065304`
- `IPHLPAPI!NotifyAddrChange` at `0x140065304`

## pseudocode

```c
__int64 __fastcall StartNetworkMonitoring(__int64 a1, unsigned __int64 a2)
{
  int v2; // esi
  int v3; // edi
  HANDLE EventW; // rax
  DWORD IPTable; // ebx

  if ( IsWMC(a1, a2) && (unsigned int)IsNetworkService() )
  {
    v2 = 0;
    v3 = 0;
    EnterCriticalSection(&g_cs);
    dword_1400C1430 = 0;
    *(_OWORD *)&notifyOverlapped.Internal = 0;
    *(_OWORD *)&notifyOverlapped.Offset = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    notifyOverlapped.hEvent = EventW;
    if ( EventW && RegisterWaitForSingleObject(&WaitHandle, EventW, NetworkAddressChange, 0, 0xFFFFFFFF, 0) )
    {
      v2 = 1;
      IPTable = NotifyAddrChange(&Handle, &notifyOverlapped);
      if ( IPTable == 997 )
      {
        IPTable = GetIPTable(&Block);
        if ( !IPTable )
        {
          dword_1400C142C = 1;
          goto LABEL_15;
        }
        v3 = 1;
        goto LABEL_6;
      }
    }
    else
    {
      IPTable = GetLastError();
    }
    if ( !IPTable )
    {
LABEL_15:
      LeaveCriticalSection(&g_cs);
      return IPTable;
    }
LABEL_6:
    dword_1400C1430 = 1;
    LeaveCriticalSection(&g_cs);
    if ( v2 )
      WaitHandle = 0;
    EnterCriticalSection(&g_cs);
    if ( v3 )
      CancelIPChangeNotify(&notifyOverlapped);
    if ( notifyOverlapped.hEvent )
      CloseHandle(notifyOverlapped.hEvent);
    *(_OWORD *)&notifyOverlapped.Internal = 0;
    *(_OWORD *)&notifyOverlapped.Offset = 0;
    if ( Block )
    {
      operator delete(Block);
      Block = 0;
    }
    Handle = 0;
    dword_1400C142C = 0;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_343cc604acc431267f7932ce27bec0aa_Traceguids);
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1400651a4  push    rbx
0x1400651a6  push    rsi
0x1400651a7  push    rdi
0x1400651a8  push    r14
0x1400651aa  sub     rsp, 38h
0x1400651ae  call    ?IsWMC@@YAHXZ; IsWMC(void)
0x1400651b3  test    eax, eax
0x1400651b5  jz      loc_140065338
0x1400651bb  call    ?IsNetworkService@@YAHXZ; IsNetworkService(void)
0x1400651c0  test    eax, eax
0x1400651c2  jz      loc_140065338
0x1400651c8  lea     r14, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_cs
0x1400651cf  xor     esi, esi
0x1400651d1  mov     rcx, r14; lpCriticalSection
0x1400651d4  xor     edi, edi
0x1400651d6  call    cs:__imp_EnterCriticalSection
0x1400651dc  xorps   xmm0, xmm0
0x1400651df  mov     cs:dword_1400C1430, esi
0x1400651e5  xor     r9d, r9d; lpName
0x1400651e8  xor     r8d, r8d; bInitialState
0x1400651eb  xor     edx, edx; bManualReset
0x1400651ed  xor     ecx, ecx; lpEventAttributes
0x1400651ef  movups  xmmword ptr cs:notifyOverlapped.Internal, xmm0
0x1400651f6  movups  xmmword ptr cs:notifyOverlapped.10h, xmm0
0x1400651fd  call    cs:__imp_CreateEventW
0x140065203  mov     cs:notifyOverlapped.hEvent, rax
0x14006520a  test    rax, rax
0x14006520d  jnz     loc_1400652C3
0x140065213  call    cs:__imp_GetLastError
0x140065219  mov     ebx, eax
0x14006521b  test    ebx, ebx
0x14006521d  jz      loc_1400652B3
0x140065223  mov     rcx, r14; lpCriticalSection
0x140065226  mov     cs:dword_1400C1430, 1
0x140065230  call    cs:__imp_LeaveCriticalSection
0x140065236  test    esi, esi
0x140065238  jz      short loc_140065245
0x14006523a  mov     cs:WaitHandle, 0
0x140065245  mov     rcx, r14; lpCriticalSection
0x140065248  call    cs:__imp_EnterCriticalSection
0x14006524e  test    edi, edi
0x140065250  jz      short loc_14006525F
0x140065252  lea     rcx, notifyOverlapped; notifyOverlapped
0x140065259  call    cs:__imp_CancelIPChangeNotify
0x14006525f  mov     rcx, cs:notifyOverlapped.hEvent; hObject
0x140065266  test    rcx, rcx
0x140065269  jz      short loc_140065271
0x14006526b  call    cs:__imp_CloseHandle
0x140065271  mov     rcx, cs:Block; Block
0x140065278  xorps   xmm0, xmm0
0x14006527b  movups  xmmword ptr cs:notifyOverlapped.Internal, xmm0
0x140065282  movups  xmmword ptr cs:notifyOverlapped.10h, xmm0
0x140065289  test    rcx, rcx
0x14006528c  jz      short loc_14006529E
0x14006528e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140065293  mov     cs:Block, 0
0x14006529e  mov     cs:Handle, 0
0x1400652a9  mov     cs:dword_1400C142C, 0
0x1400652b3  mov     rcx, r14; lpCriticalSection
0x1400652b6  call    cs:__imp_LeaveCriticalSection
0x1400652bc  mov     eax, ebx
0x1400652be  jmp     loc_140065371
0x1400652c3  mov     [rsp+58h+dwFlags], esi; dwFlags
0x1400652c7  lea     r8, _NetworkAddressChange; Callback
0x1400652ce  xor     r9d, r9d; Context
0x1400652d1  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1400652d9  mov     rdx, rax; hObject
0x1400652dc  lea     rcx, WaitHandle; phNewWaitObject
0x1400652e3  call    cs:__imp_RegisterWaitForSingleObject
0x1400652e9  test    eax, eax
0x1400652eb  jz      loc_140065213
0x1400652f1  lea     rdx, notifyOverlapped; overlapped
0x1400652f8  mov     esi, 1
0x1400652fd  lea     rcx, Handle; Handle
0x140065304  call    cs:__imp_NotifyAddrChange
0x14006530a  mov     ebx, eax
0x14006530c  cmp     eax, 3E5h
0x140065311  jnz     loc_14006521B
0x140065317  lea     rcx, Block
0x14006531e  call    _GetIPTable
0x140065323  mov     ebx, eax
0x140065325  test    eax, eax
0x140065327  jnz     short loc_140065331
0x140065329  mov     cs:dword_1400C142C, esi
0x14006532f  jmp     short loc_1400652B3
0x140065331  mov     edi, esi
0x140065333  jmp     loc_140065223
0x140065338  mov     rcx, cs:WPP_GLOBAL_Control
0x14006533f  lea     rax, WPP_GLOBAL_Control
0x140065346  cmp     rcx, rax
0x140065349  jz      short loc_14006536C
0x14006534b  test    byte ptr [rcx+1Ch], 4
0x14006534f  jz      short loc_14006536C
0x140065351  cmp     byte ptr [rcx+19h], 2
0x140065355  jb      short loc_14006536C
0x140065357  mov     rcx, [rcx+10h]
0x14006535b  lea     r8, WPP_343cc604acc431267f7932ce27bec0aa_Traceguids
0x140065362  mov     edx, 12h
0x140065367  call    WPP_SF_
0x14006536c  mov     eax, 8000FFFFh
0x140065371  add     rsp, 38h
0x140065375  pop     r14
0x140065377  pop     rdi
0x140065378  pop     rsi
0x140065379  pop     rbx
0x14006537a  retn
```
