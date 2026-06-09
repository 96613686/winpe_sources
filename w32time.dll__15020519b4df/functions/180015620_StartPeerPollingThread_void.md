# StartPeerPollingThread(void)

- ea: `0x180015620`
- end: `0x1800158ee`
- name: `?StartPeerPollingThread@@YAJXZ`
- size: `718`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015020`
- `0x1800301f8`

## callees

- `0x1800151a0`
- `0x180015620`
- `0x1800165a0`
- `0x180017240`
- `0x180018138`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001584a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001584a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015668`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001581e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001581e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800157a1`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800157a1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800156a5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800156a5`
- `ntdll!RtlReleaseResource` at `0x1800158c9`
- `ntdll!RtlReleaseResource` at `0x1800158c9`
- `ntdll!RtlAcquireResourceShared` at `0x18001588c`
- `ntdll!RtlAcquireResourceShared` at `0x18001588c`

## string_xrefs

- `0x1800158dd`: `StartPeerPollingThread completed!\n`

## pseudocode

```c
__int64 StartPeerPollingThread(void)
{
  struct _RTL_CRITICAL_SECTION *v0; // rdi
  signed int updated; // ebx
  unsigned int v2; // ebx
  __int64 v3; // rax
  signed int v5; // eax
  signed int LastError; // eax
  char v7; // bl
  __int64 i; // rdx
  _DWORD v9[2]; // [rsp+40h] [rbp-68h]
  __int64 v10; // [rsp+48h] [rbp-60h]
  char *v11; // [rsp+50h] [rbp-58h]
  void (__fastcall *v12)(void *); // [rsp+58h] [rbp-50h]
  int v13; // [rsp+60h] [rbp-48h]
  __int64 v14; // [rsp+68h] [rbp-40h]
  char *v15; // [rsp+70h] [rbp-38h]
  void (__fastcall *v16)(void *); // [rsp+78h] [rbp-30h]
  int v17; // [rsp+80h] [rbp-28h]
  __int64 v18; // [rsp+88h] [rbp-20h]
  char *v19; // [rsp+90h] [rbp-18h]
  void (__fastcall *v20)(void *); // [rsp+98h] [rbp-10h]

  if ( *((_QWORD *)g_pnpstate + 14) || *((_QWORD *)g_pnpstate + 15) || *((_QWORD *)g_pnpstate + 16) )
    return 2147943647LL;
  v0 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)g_pnpstate + 17);
  EnterCriticalSection(v0);
  if ( v0[1].DebugInfo )
  {
    updated = -2147023649;
    LeaveCriticalSection(v0);
  }
  else
  {
    if ( CreateTimerQueueTimer(
           (PHANDLE)&v0[1].DebugInfo,
           0,
           (WAITORTIMERCALLBACK)HandlePeerPollingThreadTimeout,
           0,
           0xFFFFFFFE,
           0xFFFFFFFE,
           0) )
    {
      LeaveCriticalSection(v0);
    }
    else
    {
      LastError = GetLastError();
      updated = LastError;
      if ( LastError > 0 )
        updated = (unsigned __int16)LastError | 0x80070000;
      LeaveCriticalSection(v0);
      if ( updated < 0 )
        goto LABEL_23;
    }
    UpdatePeerListTimes();
    updated = UpdatePeerPollingThreadTimerQueue1();
    if ( updated >= 0 )
    {
      v2 = 0;
      v9[0] = 8;
      v13 = 0;
      v17 = 0;
      v10 = *((_QWORD *)g_pnpstate + 11);
      v11 = (char *)g_pnpstate + 112;
      v12 = HandlePeerPollingThreadStopEvent;
      v14 = *((_QWORD *)g_pnpstate + 58);
      v15 = (char *)g_pnpstate + 120;
      v16 = HandlePeerPollingThreadPeerListUpdated;
      v18 = *((_QWORD *)g_pnpstate + 12);
      v19 = (char *)g_pnpstate + 128;
      v20 = HandlePeerPollingThreadDomHierRoleChangeEvent;
      while ( 1 )
      {
        if ( v2 >= 3 )
        {
          if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
            && _pflstate
            && *((_BYTE *)_pflstate + 315)
            && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
          {
            v7 = 0;
            for ( i = *((_QWORD *)_pflstate + 3); i && !*(_DWORD *)i; i = *(_QWORD *)(i + 8) )
            {
              if ( *(_DWORD *)(i + 4) )
              {
                v7 = 1;
                break;
              }
            }
            RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
            if ( v7 )
              FileLogAdd(L"StartPeerPollingThread completed!\n");
          }
          return 0;
        }
        v3 = RegisterWaitForSingleObjectEx(*(&v10 + 4 * (int)v2), *(&v12 + 4 * (int)v2), 0, 0xFFFFFFFFLL, v9[8 * v2]);
        *(_QWORD *)(&v11)[4 * (int)v2] = v3;
        if ( !v3 )
          break;
        ++v2;
      }
      v5 = GetLastError();
      updated = v5;
      if ( v5 > 0 )
        updated = (unsigned __int16)v5 | 0x80070000;
      if ( updated < 0 )
        goto LABEL_23;
      return (unsigned int)updated;
    }
  }
LABEL_23:
  StopPeerPollingThread();
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180015620  mov     r11, rsp
0x180015623  push    rbx
0x180015624  sub     rsp, 0A0h
0x18001562b  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180015632  cmp     qword ptr [rax+70h], 0
0x180015637  jnz     loc_1800157EC
0x18001563d  cmp     qword ptr [rax+78h], 0
0x180015642  jnz     loc_1800157EC
0x180015648  cmp     qword ptr [rax+80h], 0
0x180015650  jnz     loc_1800157EC
0x180015656  mov     [r11+10h], rdi
0x18001565a  mov     rdi, [rax+88h]
0x180015661  mov     rcx, rdi; lpCriticalSection
0x180015664  mov     [r11+8], rsi
0x180015668  call    cs:__imp_EnterCriticalSection
0x18001566f  nop     dword ptr [rax+rax+00h]
0x180015674  cmp     qword ptr [rdi+28h], 0
0x180015679  lea     rcx, [rdi+28h]; phNewTimer
0x18001567d  jnz     loc_180015842
0x180015683  xor     esi, esi
0x180015685  lea     r8, ?HandlePeerPollingThreadTimeout@@YAXPEAXE@Z; Callback
0x18001568c  mov     [rsp+0A8h+Flags], esi; Flags
0x180015690  xor     r9d, r9d; Parameter
0x180015693  mov     [rsp+0A8h+Period], 0FFFFFFFEh; Period
0x18001569b  xor     edx, edx; TimerQueue
0x18001569d  mov     [rsp+0A8h+DueTime], 0FFFFFFFEh; DueTime
0x1800156a5  call    cs:__imp_CreateTimerQueueTimer
0x1800156ac  nop     dword ptr [rax+rax+00h]
0x1800156b1  test    eax, eax
0x1800156b3  jz      loc_18001581E
0x1800156b9  mov     rcx, rdi; lpCriticalSection
0x1800156bc  call    cs:__imp_LeaveCriticalSection
0x1800156c3  nop     dword ptr [rax+rax+00h]
0x1800156c8  jmp     short loc_1800156E1
0x1800156ca  mov     rcx, rdi; lpCriticalSection
0x1800156cd  call    cs:__imp_LeaveCriticalSection
0x1800156d4  nop     dword ptr [rax+rax+00h]
0x1800156d9  test    ebx, ebx
0x1800156db  js      loc_180015856
0x1800156e1  call    ?UpdatePeerListTimes@@YAXXZ; UpdatePeerListTimes(void)
0x1800156e6  call    ?UpdatePeerPollingThreadTimerQueue1@@YAJXZ; UpdatePeerPollingThreadTimerQueue1(void)
0x1800156eb  mov     ebx, eax
0x1800156ed  test    eax, eax
0x1800156ef  js      loc_180015856
0x1800156f5  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800156fc  mov     ebx, esi
0x1800156fe  mov     [rsp+0A8h+var_68], 8
0x180015706  mov     [rsp+0A8h+var_48], esi
0x18001570a  mov     [rsp+0A8h+var_28], esi
0x180015711  mov     rax, [rcx+58h]
0x180015715  mov     [rsp+0A8h+var_60], rax
0x18001571a  lea     rax, [rcx+70h]
0x18001571e  mov     [rsp+0A8h+var_58], rax
0x180015723  lea     rax, ?HandlePeerPollingThreadStopEvent@@YAXPEAXE@Z; HandlePeerPollingThreadStopEvent(void *,uchar)
0x18001572a  mov     [rsp+0A8h+var_50], rax
0x18001572f  mov     rax, [rcx+1D0h]
0x180015736  mov     [rsp+0A8h+var_40], rax
0x18001573b  lea     rax, [rcx+78h]
0x18001573f  mov     [rsp+0A8h+var_38], rax
0x180015744  lea     rax, ?HandlePeerPollingThreadPeerListUpdated@@YAXPEAXE@Z; HandlePeerPollingThreadPeerListUpdated(void *,uchar)
0x18001574b  mov     [rsp+0A8h+var_30], rax
0x180015750  mov     rax, [rcx+60h]
0x180015754  mov     [rsp+0A8h+var_20], rax
0x18001575c  lea     rax, [rcx+80h]
0x180015763  mov     [rsp+0A8h+var_18], rax
0x18001576b  lea     rax, ?HandlePeerPollingThreadDomHierRoleChangeEvent@@YAXPEAXE@Z; HandlePeerPollingThreadDomHierRoleChangeEvent(void *,uchar)
0x180015772  mov     [rsp+0A8h+var_10], rax
0x18001577a  cmp     ebx, 3
0x18001577d  jnb     short loc_1800157BE
0x18001577f  movsxd  rdi, ebx
0x180015782  mov     r9d, 0FFFFFFFFh
0x180015788  shl     rdi, 5
0x18001578c  xor     r8d, r8d
0x18001578f  mov     eax, [rsp+rdi+0A8h+var_68]
0x180015793  mov     rdx, [rsp+rdi+0A8h+var_50]
0x180015798  mov     rcx, [rsp+rdi+0A8h+var_60]
0x18001579d  mov     [rsp+0A8h+DueTime], eax
0x1800157a1  call    cs:__imp_RegisterWaitForSingleObjectEx
0x1800157a8  nop     dword ptr [rax+rax+00h]
0x1800157ad  mov     rcx, [rsp+rdi+0A8h+var_58]
0x1800157b2  mov     [rcx], rax
0x1800157b5  test    rax, rax
0x1800157b8  jz      short loc_1800157FB
0x1800157ba  inc     ebx
0x1800157bc  jmp     short loc_18001577A
0x1800157be  mov     ecx, esi
0x1800157c0  xor     eax, eax
0x1800157c2  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x1800157ca  jnz     loc_180015869
0x1800157d0  mov     eax, esi
0x1800157d2  mov     rsi, [rsp+0A8h+arg_0]
0x1800157da  mov     rdi, [rsp+0A8h+arg_8]
0x1800157e2  add     rsp, 0A0h
0x1800157e9  pop     rbx
0x1800157ea  retn
0x1800157ec  mov     eax, 800704DFh
0x1800157f1  add     rsp, 0A0h
0x1800157f8  pop     rbx
0x1800157f9  retn
0x1800157fb  call    cs:__imp_GetLastError
0x180015802  nop     dword ptr [rax+rax+00h]
0x180015807  mov     ebx, eax
0x180015809  test    eax, eax
0x18001580b  jle     short loc_180015816
0x18001580d  movzx   ebx, ax
0x180015810  or      ebx, 80070000h
0x180015816  test    ebx, ebx
0x180015818  js      short loc_180015856
0x18001581a  mov     eax, ebx
0x18001581c  jmp     short loc_1800157D2
0x18001581e  call    cs:__imp_GetLastError
0x180015825  nop     dword ptr [rax+rax+00h]
0x18001582a  mov     ebx, eax
0x18001582c  test    eax, eax
0x18001582e  jle     loc_1800156CA
0x180015834  movzx   ebx, ax
0x180015837  or      ebx, 80070000h
0x18001583d  jmp     loc_1800156CA
0x180015842  mov     rcx, rdi; lpCriticalSection
0x180015845  mov     ebx, 800704DFh
0x18001584a  call    cs:__imp_LeaveCriticalSection
0x180015851  nop     dword ptr [rax+rax+00h]
0x180015856  call    ?StopPeerPollingThread@@YAJXZ; StopPeerPollingThread(void)
0x18001585b  test    eax, eax
0x18001585d  jns     short loc_18001581A
0x18001585f  test    ebx, ebx
0x180015861  jns     loc_1800157D2
0x180015867  jmp     short loc_18001581A
0x180015869  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180015870  test    rcx, rcx
0x180015873  jz      loc_1800157D0
0x180015879  cmp     [rcx+13Bh], sil
0x180015880  jz      loc_1800157D0
0x180015886  add     rcx, 50h ; 'P'; Resource
0x18001588a  mov     dl, 1; Wait
0x18001588c  call    cs:__imp_RtlAcquireResourceShared
0x180015893  nop     dword ptr [rax+rax+00h]
0x180015898  test    al, al
0x18001589a  jz      loc_1800157D0
0x1800158a0  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x1800158a7  xor     bl, bl
0x1800158a9  mov     rdx, [r8+18h]
0x1800158ad  test    rdx, rdx
0x1800158b0  jz      short loc_1800158C5
0x1800158b2  mov     ecx, [rdx]
0x1800158b4  test    ecx, ecx
0x1800158b6  jnz     short loc_1800158C5
0x1800158b8  add     ecx, [rdx+4]
0x1800158bb  jnz     short loc_1800158C3
0x1800158bd  mov     rdx, [rdx+8]
0x1800158c1  jmp     short loc_1800158AD
0x1800158c3  mov     bl, 1
0x1800158c5  lea     rcx, [r8+50h]; Resource
0x1800158c9  call    cs:__imp_RtlReleaseResource
0x1800158d0  nop     dword ptr [rax+rax+00h]
0x1800158d5  test    bl, bl
0x1800158d7  jz      loc_1800157D0
0x1800158dd  lea     rcx, aStartpeerpolli; "StartPeerPollingThread completed!\n"
0x1800158e4  call    FileLogAdd
0x1800158e9  jmp     loc_1800157D0
```
