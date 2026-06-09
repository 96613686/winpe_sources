# W32TimeServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x18000e080`
- end: `0x18000e617`
- name: `?W32TimeServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `1431`
- prototype: `unsigned int __fastcall(unsigned int, unsigned int, void *, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000c3ac`
- `0x18000c7d0`
- `0x18000e080`
- `0x18000e620`
- `0x180018138`
- `0x180018dfc`
- `0x18001d9a0`
- `0x18003119c`
- `0x18004cd1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000e09d`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000e102`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000e09d`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000e102`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e439`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e439`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e272`
- `ntdll!RtlReleaseResource` at `0x18000e24d`
- `ntdll!RtlReleaseResource` at `0x18000e2e9`
- `ntdll!RtlReleaseResource` at `0x18000e57a`
- `ntdll!RtlReleaseResource` at `0x18000e24d`
- `ntdll!RtlReleaseResource` at `0x18000e2e9`
- `ntdll!RtlReleaseResource` at `0x18000e57a`
- `ntdll!RtlAcquireResourceShared` at `0x18000e210`
- `ntdll!RtlAcquireResourceShared` at `0x18000e2ae`
- `ntdll!RtlAcquireResourceShared` at `0x18000e541`
- `ntdll!RtlAcquireResourceShared` at `0x18000e210`
- `ntdll!RtlAcquireResourceShared` at `0x18000e2ae`
- `ntdll!RtlAcquireResourceShared` at `0x18000e541`

## string_xrefs

- `0x18000e323`: `SERVICE_CONTROL_STOP\n`
- `0x18000e378`: `shutdown in service control handler, w/o restart service async`
- `0x18000e3ae`: `SERVICE_CONTROL_PAUSE\n`
- `0x18000e3cc`: `SERVICE_CONTROL_CONTINUE\n`
- `0x18000e19e`: `SERVICE_CONTROL_INTERROGATE\n`
- `0x18000e3e6`: `SERVICE_CONTROL_SHUTDOWN\n`
- `0x18000e426`: `SERVICE_CONTROL_PARAMCHANGE\n`
- `0x18000e464`: `SERVICE_CONTROL_NETBINDADD\n`
- `0x18000e261`: `SERVICE_CONTROL_NETBINDREMOVE\n`
- `0x18000e482`: `SERVICE_CONTROL_NETBINDENABLE\n`
- `0x18000e4a0`: `SERVICE_CONTROL_NETBINDDISABLE\n`
- `0x18000e4c3`: `SERVICE_CONTROL_DEVICEEVENT(0x%08X, 0x%p)\n`
- `0x18000e4eb`: `SERVICE_CONTROL_HARDWAREPROFILECHANGE(0x%08X, 0x%p)\n`
- `0x18000e593`: `SERVICE_CONTROL_POWEREVENT(0x%08X, 0x%p)\n`
- `0x18000e516`: `unknown service control (0x%08X, 0x%08X, 0x%p)\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall W32TimeServiceCtrlHandler(unsigned int a1, unsigned int a2, void *a3, void *a4)
{
  char v7; // di
  char v8; // bl
  char v10; // bl
  __int64 j; // rdx
  __int64 i; // rdx
  __int64 k; // rdx
  char v14; // [rsp+20h] [rbp-78h]
  __int64 v15; // [rsp+30h] [rbp-68h]

  v15 = _set_se_translator(SeTransFunc);
  if ( (int)AllowShutdown(0) < 0 )
    return 0;
  v14 = 1;
  v7 = 0;
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
  {
    if ( _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x3Cu; i = *(_QWORD *)(i + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x3C )
        {
          v7 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    }
    if ( v7 )
      FileLogAdd(L"W32TimeHandler called: ");
  }
  if ( a1 == 8 )
  {
    v8 = 0;
    if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
    {
      if ( _pflstate
        && *((_BYTE *)_pflstate + 315)
        && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
      {
        for ( j = *((_QWORD *)_pflstate + 3); j && *(_DWORD *)j <= 0x3Cu; j = *(_QWORD *)(j + 8) )
        {
          if ( (unsigned int)(*(_DWORD *)(j + 4) + *(_DWORD *)j) > 0x3C )
          {
            v8 = 1;
            break;
          }
        }
        RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
      }
      if ( v8 )
        FileLogAppend(L"SERVICE_CONTROL_NETBINDREMOVE\n");
    }
LABEL_5:
    _set_se_translator(v15);
    goto LABEL_6;
  }
  if ( a1 != 13 )
  {
    switch ( a1 )
    {
      case 1u:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_STOP\n");
        if ( (int)AllowShutdown(1) < 0 )
          goto LABEL_6;
        v14 = 0;
        if ( (int)MySetServiceStatus(3u, 0x3E8u, 0) < 0 )
          return 0;
        if ( (unsigned __int8)FileLogAllowEntry(73) )
          FileLogAdd(L"shutdown in service control handler, w/o restart service async");
        if ( (int)NotifyShutdown(0) < 0 )
          return 0;
        goto LABEL_5;
      case 2u:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_PAUSE\n");
        goto LABEL_5;
      case 3u:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_CONTINUE\n");
        goto LABEL_5;
      case 4u:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_INTERROGATE\n");
        goto LABEL_5;
      case 5u:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_SHUTDOWN\n");
        if ( (int)AllowShutdown(1) < 0 )
          goto LABEL_6;
        v14 = 0;
        HandleManagerSystemShutdown();
        goto LABEL_5;
      case 6u:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_PARAMCHANGE\n");
        if ( SetEvent(qword_1800A36F0) )
          goto LABEL_5;
        GetLastError();
        goto LABEL_6;
      case 7u:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_NETBINDADD\n");
        goto LABEL_5;
      case 9u:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_NETBINDENABLE\n");
        goto LABEL_5;
      case 0xAu:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_NETBINDDISABLE\n");
        goto LABEL_5;
      case 0xBu:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_DEVICEEVENT(0x%08X, 0x%p)\n", a2, a3);
        goto LABEL_5;
      case 0xCu:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"SERVICE_CONTROL_HARDWAREPROFILECHANGE(0x%08X, 0x%p)\n", a2, a3);
        goto LABEL_5;
      default:
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAppend(L"unknown service control (0x%08X, 0x%08X, 0x%p)\n", a1, a2, a3);
        goto LABEL_5;
    }
  }
  v10 = 0;
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
  {
    if ( _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      for ( k = *((_QWORD *)_pflstate + 3); k && *(_DWORD *)k <= 0x3Cu; k = *(_QWORD *)(k + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(k + 4) + *(_DWORD *)k) > 0x3C )
        {
          v10 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    }
    if ( v10 )
      FileLogAppend(L"SERVICE_CONTROL_POWEREVENT(0x%08X, 0x%p)\n", a2, a3);
  }
  if ( a2 == 10 )
    goto LABEL_5;
  if ( a2 != 7 )
  {
    switch ( a2 )
    {
      case 0u:
      case 2u:
      case 9u:
      case 0xBu:
        goto LABEL_5;
      case 4u:
        if ( (int)HandleManagerApmSuspend() >= 0 )
          goto LABEL_5;
        break;
      case 6u:
      case 0x12u:
        goto LABEL_13;
      default:
        goto LABEL_6;
    }
    goto LABEL_6;
  }
LABEL_13:
  if ( (int)HandleManagerApmResumeSuspend() >= 0 )
    goto LABEL_5;
LABEL_6:
  if ( v14 )
    AllowShutdown(1);
  return 0;
}

```

## disassembly

```asm
0x18000e080  push    rbx
0x18000e082  push    rsi
0x18000e083  push    rdi
0x18000e084  push    r14
0x18000e086  sub     rsp, 78h
0x18000e08a  mov     r14, r8
0x18000e08d  mov     esi, edx
0x18000e08f  mov     ebx, ecx
0x18000e091  mov     [rsp+98h+var_78], 0
0x18000e096  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18000e09d  call    cs:__imp__set_se_translator
0x18000e0a4  nop     dword ptr [rax+rax+00h]
0x18000e0a9  mov     [rsp+98h+var_68], rax
0x18000e0ae  xor     ecx, ecx; int
0x18000e0b0  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x18000e0b5  mov     [rsp+98h+var_74], eax
0x18000e0b9  test    eax, eax
0x18000e0bb  js      loc_18000E15B
0x18000e0c1  mov     [rsp+98h+var_78], 1
0x18000e0c6  xor     dil, dil
0x18000e0c9  mov     [rsp+98h+var_70], dil
0x18000e0ce  xor     ecx, ecx
0x18000e0d0  xor     eax, eax
0x18000e0d2  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x18000e0da  jnz     loc_18000E293
0x18000e0e0  cmp     ebx, 8
0x18000e0e3  jnz     short loc_18000E122
0x18000e0e5  xor     bl, bl
0x18000e0e7  mov     [rsp+98h+var_6E], bl
0x18000e0eb  xor     ecx, ecx
0x18000e0ed  xor     eax, eax
0x18000e0ef  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x18000e0f7  jnz     loc_18000E1F6
0x18000e0fd  mov     rcx, [rsp+98h+var_68]; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e102  call    cs:__imp__set_se_translator
0x18000e109  nop     dword ptr [rax+rax+00h]
0x18000e10e  cmp     [rsp+98h+var_78], 0
0x18000e113  jnz     short loc_18000E15D
0x18000e115  xor     eax, eax
0x18000e117  add     rsp, 78h
0x18000e11b  pop     r14
0x18000e11d  pop     rdi
0x18000e11e  pop     rsi
0x18000e11f  pop     rbx
0x18000e120  retn
0x18000e122  cmp     ebx, 0Dh
0x18000e125  jnz     short loc_18000E169
0x18000e127  xor     bl, bl
0x18000e129  mov     [rsp+98h+var_6F], bl
0x18000e12d  xor     ecx, ecx
0x18000e12f  xor     eax, eax
0x18000e131  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x18000e139  jnz     loc_18000E527
0x18000e13f  cmp     esi, 0Ah
0x18000e142  jz      short loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e144  cmp     esi, 7
0x18000e147  jnz     short loc_18000E1AA
0x18000e149  call    ?HandleManagerApmResumeSuspend@@YAJXZ; jumptable 000000018000E1C8 cases 6,18
0x18000e14e  mov     [rsp+98h+var_74], eax
0x18000e152  test    eax, eax
0x18000e154  jns     short loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e156  jmp     loc_18000E1F1
0x18000e15b  jmp     short loc_18000E115
0x18000e15d  mov     ecx, 1; int
0x18000e162  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x18000e167  jmp     short loc_18000E115
0x18000e169  lea     eax, [rbx-1]; switch 12 cases
0x18000e16c  cmp     eax, 0Bh
0x18000e16f  ja      def_18000E186; jumptable 000000018000E186 default case, case 8
0x18000e175  lea     rdx, __ImageBase
0x18000e17c  mov     eax, ds:(jpt_18000E186 - 180000000h)[rdx+rax*4]
0x18000e183  add     rax, rdx
0x18000e186  jmp     rax; switch jump
0x18000e18c  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 4
0x18000e191  call    FileLogAllowEntry
0x18000e196  test    al, al
0x18000e198  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e19e  lea     rcx, aServiceControl_5; "SERVICE_CONTROL_INTERROGATE\n"
0x18000e1a5  jmp     loc_18000E268
0x18000e1aa  cmp     esi, 12h; switch 19 cases
0x18000e1ad  ja      short def_18000E1C8; jumptable 000000018000E1C8 default case, cases 1,3,5,7,8,10,12-17
0x18000e1af  lea     rdx, __ImageBase
0x18000e1b6  movzx   eax, ds:(byte_18000E604 - 180000000h)[rdx+rsi]
0x18000e1be  mov     ecx, ds:(jpt_18000E1C8 - 180000000h)[rdx+rax*4]
0x18000e1c5  add     rcx, rdx
0x18000e1c8  jmp     rcx; switch jump
0x18000e1ce  call    ?HandleManagerApmSuspend@@YAJXZ; jumptable 000000018000E1C8 case 4
0x18000e1d3  mov     [rsp+98h+var_74], eax
0x18000e1d7  test    eax, eax
0x18000e1d9  jns     loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e1df  jmp     loc_18000E10E
0x18000e1e4  mov     [rsp+98h+var_74], 80070057h; jumptable 000000018000E1C8 default case, cases 1,3,5,7,8,10,12-17
0x18000e1ec  jmp     loc_18000E10E
0x18000e1f1  jmp     loc_18000E10E
0x18000e1f6  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000e1fd  test    rcx, rcx
0x18000e200  jz      short loc_18000E259
0x18000e202  cmp     [rcx+13Bh], bl
0x18000e208  jz      short loc_18000E259
0x18000e20a  add     rcx, 50h ; 'P'; Resource
0x18000e20e  mov     dl, 1; Wait
0x18000e210  call    cs:__imp_RtlAcquireResourceShared
0x18000e217  nop     dword ptr [rax+rax+00h]
0x18000e21c  test    al, al
0x18000e21e  jz      short loc_18000E259
0x18000e220  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000e227  mov     rdx, [r8+18h]
0x18000e22b  test    rdx, rdx
0x18000e22e  jz      short loc_18000E249
0x18000e230  mov     ecx, [rdx]
0x18000e232  cmp     ecx, 3Ch ; '<'
0x18000e235  ja      short loc_18000E249
0x18000e237  add     ecx, [rdx+4]
0x18000e23a  cmp     ecx, 3Ch ; '<'
0x18000e23d  jbe     loc_18000E5AA
0x18000e243  mov     bl, 1
0x18000e245  mov     [rsp+98h+var_6E], bl
0x18000e249  lea     rcx, [r8+50h]; Resource
0x18000e24d  call    cs:__imp_RtlReleaseResource
0x18000e254  nop     dword ptr [rax+rax+00h]
0x18000e259  test    bl, bl
0x18000e25b  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e261  lea     rcx, aServiceControl_8; "SERVICE_CONTROL_NETBINDREMOVE\n"
0x18000e268  call    FileLogAppend
0x18000e26d  jmp     loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e272  call    cs:__imp_GetLastError
0x18000e279  nop     dword ptr [rax+rax+00h]
0x18000e27e  test    eax, eax
0x18000e280  jle     short loc_18000E28A
0x18000e282  movzx   eax, ax
0x18000e285  or      eax, 80070000h
0x18000e28a  mov     [rsp+98h+var_74], eax
0x18000e28e  jmp     loc_18000E10E
0x18000e293  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000e29a  test    rcx, rcx
0x18000e29d  jz      short loc_18000E2F5
0x18000e29f  cmp     [rcx+13Bh], dil
0x18000e2a6  jz      short loc_18000E2F5
0x18000e2a8  add     rcx, 50h ; 'P'; Resource
0x18000e2ac  mov     dl, 1; Wait
0x18000e2ae  call    cs:__imp_RtlAcquireResourceShared
0x18000e2b5  nop     dword ptr [rax+rax+00h]
0x18000e2ba  test    al, al
0x18000e2bc  jz      short loc_18000E2F5
0x18000e2be  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000e2c5  mov     rdx, [r8+18h]
0x18000e2c9  test    rdx, rdx
0x18000e2cc  jz      short loc_18000E2E5
0x18000e2ce  mov     ecx, [rdx]
0x18000e2d0  cmp     ecx, 3Ch ; '<'
0x18000e2d3  ja      short loc_18000E2E5
0x18000e2d5  add     ecx, [rdx+4]
0x18000e2d8  cmp     ecx, 3Ch ; '<'
0x18000e2db  jbe     short loc_18000E30F
0x18000e2dd  mov     dil, 1
0x18000e2e0  mov     [rsp+98h+var_70], dil
0x18000e2e5  lea     rcx, [r8+50h]; Resource
0x18000e2e9  call    cs:__imp_RtlReleaseResource
0x18000e2f0  nop     dword ptr [rax+rax+00h]
0x18000e2f5  test    dil, dil
0x18000e2f8  jz      loc_18000E0E0
0x18000e2fe  lea     rcx, aW32timehandler; "W32TimeHandler called: "
0x18000e305  call    FileLogAdd
0x18000e30a  jmp     loc_18000E0E0
0x18000e30f  mov     rdx, [rdx+8]
0x18000e313  jmp     short loc_18000E2C9
0x18000e315  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 1
0x18000e31a  call    FileLogAllowEntry
0x18000e31f  test    al, al
0x18000e321  jz      short loc_18000E32F
0x18000e323  lea     rcx, aServiceControl_7; "SERVICE_CONTROL_STOP\n"
0x18000e32a  call    FileLogAppend
0x18000e32f  mov     ecx, 1; int
0x18000e334  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x18000e339  mov     [rsp+98h+var_74], eax
0x18000e33d  test    eax, eax
0x18000e33f  jns     short loc_18000E346
0x18000e341  jmp     loc_18000E10E
0x18000e346  mov     [rsp+98h+var_78], 0
0x18000e34b  xor     r8d, r8d; unsigned int
0x18000e34e  mov     edx, 3E8h; unsigned int
0x18000e353  mov     ecx, 3; unsigned int
0x18000e358  call    ?MySetServiceStatus@@YAJKKK@Z; MySetServiceStatus(ulong,ulong,ulong)
0x18000e35d  mov     [rsp+98h+var_74], eax
0x18000e361  test    eax, eax
0x18000e363  jns     short loc_18000E36A
0x18000e365  jmp     loc_18000E115
0x18000e36a  mov     ecx, 49h ; 'I'
0x18000e36f  call    FileLogAllowEntry
0x18000e374  test    al, al
0x18000e376  jz      short loc_18000E384
0x18000e378  lea     rcx, aShutdownInServ; "shutdown in service control handler, w/"...
0x18000e37f  call    FileLogAdd
0x18000e384  xor     ecx, ecx; unsigned int
0x18000e386  call    ?NotifyShutdown@@YAJK@Z; NotifyShutdown(ulong)
0x18000e38b  mov     [rsp+98h+var_74], eax
0x18000e38f  test    eax, eax
0x18000e391  jns     loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e397  jmp     loc_18000E115
0x18000e39c  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 2
0x18000e3a1  call    FileLogAllowEntry
0x18000e3a6  test    al, al
0x18000e3a8  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e3ae  lea     rcx, aServiceControl_3; "SERVICE_CONTROL_PAUSE\n"
0x18000e3b5  jmp     loc_18000E268
0x18000e3ba  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 3
0x18000e3bf  call    FileLogAllowEntry
0x18000e3c4  test    al, al
0x18000e3c6  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e3cc  lea     rcx, aServiceControl_4; "SERVICE_CONTROL_CONTINUE\n"
0x18000e3d3  jmp     loc_18000E268
0x18000e3d8  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 5
0x18000e3dd  call    FileLogAllowEntry
0x18000e3e2  test    al, al
0x18000e3e4  jz      short loc_18000E3F2
0x18000e3e6  lea     rcx, aServiceControl_11; "SERVICE_CONTROL_SHUTDOWN\n"
0x18000e3ed  call    FileLogAppend
0x18000e3f2  mov     ecx, 1; int
0x18000e3f7  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x18000e3fc  mov     [rsp+98h+var_74], eax
0x18000e400  test    eax, eax
0x18000e402  jns     short loc_18000E409
0x18000e404  jmp     loc_18000E10E
0x18000e409  mov     [rsp+98h+var_78], 0
0x18000e40e  call    ?HandleManagerSystemShutdown@@YAXXZ; HandleManagerSystemShutdown(void)
0x18000e413  jmp     loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e418  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 6
0x18000e41d  call    FileLogAllowEntry
0x18000e422  test    al, al
0x18000e424  jz      short loc_18000E432
0x18000e426  lea     rcx, aServiceControl_0; "SERVICE_CONTROL_PARAMCHANGE\n"
0x18000e42d  call    FileLogAppend
0x18000e432  mov     rcx, cs:qword_1800A36F0; hEvent
0x18000e439  call    cs:__imp_SetEvent
0x18000e440  nop     dword ptr [rax+rax+00h]
0x18000e445  test    eax, eax
0x18000e447  jnz     loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e44d  jmp     loc_18000E272
0x18000e452  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 7
0x18000e457  call    FileLogAllowEntry
0x18000e45c  test    al, al
0x18000e45e  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e464  lea     rcx, aServiceControl_10; "SERVICE_CONTROL_NETBINDADD\n"
0x18000e46b  jmp     loc_18000E268
0x18000e470  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 9
0x18000e475  call    FileLogAllowEntry
0x18000e47a  test    al, al
0x18000e47c  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e482  lea     rcx, aServiceControl; "SERVICE_CONTROL_NETBINDENABLE\n"
0x18000e489  jmp     loc_18000E268
0x18000e48e  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 10
0x18000e493  call    FileLogAllowEntry
0x18000e498  test    al, al
0x18000e49a  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e4a0  lea     rcx, aServiceControl_9; "SERVICE_CONTROL_NETBINDDISABLE\n"
0x18000e4a7  jmp     loc_18000E268
0x18000e4ac  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 11
0x18000e4b1  call    FileLogAllowEntry
0x18000e4b6  test    al, al
0x18000e4b8  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e4be  mov     r8, r14
0x18000e4c1  mov     edx, esi
0x18000e4c3  lea     rcx, aServiceControl_2; "SERVICE_CONTROL_DEVICEEVENT(0x%08X, 0x%"...
0x18000e4ca  call    FileLogAppend
0x18000e4cf  jmp     loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e4d4  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 case 12
0x18000e4d9  call    FileLogAllowEntry
0x18000e4de  test    al, al
0x18000e4e0  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e4e6  mov     r8, r14
0x18000e4e9  mov     edx, esi
0x18000e4eb  lea     rcx, aServiceControl_1; "SERVICE_CONTROL_HARDWAREPROFILECHANGE(0"...
0x18000e4f2  call    FileLogAppend
0x18000e4f7  jmp     loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e4fc  mov     ecx, 3Ch ; '<'; jumptable 000000018000E186 default case, case 8
0x18000e501  call    FileLogAllowEntry
0x18000e506  test    al, al
0x18000e508  jz      loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e50e  mov     r9, r14
0x18000e511  mov     r8d, esi
0x18000e514  mov     edx, ebx
0x18000e516  lea     rcx, aUnknownService; "unknown service control (0x%08X, 0x%08X"...
0x18000e51d  call    FileLogAppend
0x18000e522  jmp     loc_18000E0FD; jumptable 000000018000E1C8 cases 0,2,9,11
0x18000e527  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000e52e  test    rcx, rcx
0x18000e531  jz      short loc_18000E586
0x18000e533  cmp     [rcx+13Bh], bl
0x18000e539  jz      short loc_18000E586
0x18000e53b  add     rcx, 50h ; 'P'; Resource
0x18000e53f  mov     dl, 1; Wait
0x18000e541  call    cs:__imp_RtlAcquireResourceShared
0x18000e548  nop     dword ptr [rax+rax+00h]
0x18000e54d  test    al, al
0x18000e54f  jz      short loc_18000E586
0x18000e551  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000e558  mov     rdx, [r8+18h]
0x18000e55c  test    rdx, rdx
0x18000e55f  jz      short loc_18000E576
0x18000e561  mov     ecx, [rdx]
  ... truncated ...
```
