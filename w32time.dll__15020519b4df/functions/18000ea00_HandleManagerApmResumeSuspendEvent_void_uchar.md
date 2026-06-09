# HandleManagerApmResumeSuspendEvent(void *,uchar)

- ea: `0x18000ea00`
- end: `0x18000ec49`
- name: `?HandleManagerApmResumeSuspendEvent@@YAXPEAXE@Z`
- size: `585`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000e620`
- `0x18000e758`
- `0x18000ea00`
- `0x18000ec50`
- `0x180010748`
- `0x180018138`
- `0x18001d9a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000ea20`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000eb9a`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000ea20`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000eb9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb21`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000eb09`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000eb09`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000ead7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000ead7`
- `ntdll!RtlReleaseResource` at `0x18000ebfb`
- `ntdll!RtlReleaseResource` at `0x18000ebfb`
- `ntdll!RtlAcquireResourceShared` at `0x18000ebc2`
- `ntdll!RtlAcquireResourceShared` at `0x18000ebc2`

## string_xrefs

- `0x18000eb85`: `W32TmServiceMain: APM resume complete successfully!\n`
- `0x18000ec0f`: `W32TmServiceMain: APM resume.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HandleManagerApmResumeSuspendEvent(void *a1)
{
  char v1; // bl
  enum TimeProvCmd v2; // ecx
  __int64 i; // rdx
  char v4; // [rsp+31h] [rbp-47h]
  int v5; // [rsp+90h] [rbp+18h] BYREF
  __int64 v6; // [rsp+98h] [rbp+20h]

  v5 = 0;
  v4 = 0;
  v6 = _set_se_translator(SeTransFunc);
  EnterCriticalSection(&CriticalSection);
  v1 = 0;
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
  {
    if ( _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x47u; i = *(_QWORD *)(i + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x47 )
        {
          v1 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    }
    if ( v1 )
      FileLogAdd(L"W32TmServiceMain: APM resume.\n");
  }
  if ( (int)HandleManagerNetTopoChange(0, 1) >= 0 && HandleManagerHardResync(v2, &v5) >= 0 )
  {
    SetNetlogonServiceBits(dword_1800A468C);
    if ( (int)AllowShutdown(0) >= 0 )
    {
      v4 = 1;
      if ( qword_1800A37A0 )
      {
        UnregisterWaitEx(qword_1800A37A0, 0);
        qword_1800A37A0 = 0;
      }
      qword_1800A37A0 = (HANDLE)RegisterWaitForSingleObjectEx(
                                  qword_1800A3738,
                                  HandleManagerApmResumeSuspendEvent,
                                  0,
                                  0xFFFFFFFFLL,
                                  8);
      if ( qword_1800A37A0 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(71) )
          FileLogAdd(L"W32TmServiceMain: APM resume complete successfully!\n");
        _set_se_translator(v6);
      }
      else
      {
        GetLastError();
      }
    }
  }
  LeaveCriticalSection(&CriticalSection);
  if ( v4 )
    AllowShutdown(1);
}

```

## disassembly

```asm
0x18000ea00  mov     rax, rsp
0x18000ea03  mov     [rax+8], rbx
0x18000ea07  push    rdi
0x18000ea08  sub     rsp, 70h
0x18000ea0c  xor     edi, edi
0x18000ea0e  mov     [rax+18h], edi
0x18000ea11  mov     [rax-48h], dil
0x18000ea15  mov     [rax-47h], dil
0x18000ea19  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18000ea20  call    cs:__imp__set_se_translator
0x18000ea27  nop     dword ptr [rax+rax+00h]
0x18000ea2c  mov     [rsp+78h+arg_18], rax
0x18000ea34  lea     rcx, CriticalSection; lpCriticalSection
0x18000ea3b  call    cs:__imp_EnterCriticalSection
0x18000ea42  nop     dword ptr [rax+rax+00h]
0x18000ea47  mov     [rsp+78h+var_44], edi
0x18000ea4b  mov     [rsp+78h+var_48], 1
0x18000ea50  xor     bl, bl
0x18000ea52  mov     [rsp+78h+var_46], bl
0x18000ea56  mov     ecx, edi
0x18000ea58  xor     eax, eax
0x18000ea5a  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x18000ea62  jnz     loc_18000EBA8
0x18000ea68  mov     r8d, 1
0x18000ea6e  movzx   edx, r8b
0x18000ea72  xor     ecx, ecx
0x18000ea74  call    ?HandleManagerNetTopoChange@@YAJPEA_K_NW4_NetTopoChangeSource@@@Z; HandleManagerNetTopoChange(unsigned __int64 *,bool,_NetTopoChangeSource)
0x18000ea79  mov     [rsp+78h+var_44], eax
0x18000ea7d  test    eax, eax
0x18000ea7f  js      loc_18000EC26
0x18000ea85  lea     rdx, [rsp+78h+arg_10]; void *
0x18000ea8d  call    ?HandleManagerHardResync@@YAJW4TimeProvCmd@@PEAX@Z; HandleManagerHardResync(TimeProvCmd,void *)
0x18000ea92  mov     [rsp+78h+var_44], eax
0x18000ea96  test    eax, eax
0x18000ea98  js      loc_18000EB5E
0x18000ea9e  mov     ecx, cs:dword_1800A468C; unsigned int
0x18000eaa4  call    ?SetNetlogonServiceBits@@YAJK@Z; SetNetlogonServiceBits(ulong)
0x18000eaa9  mov     [rsp+78h+var_44], eax
0x18000eaad  mov     [rsp+78h+var_44], edi
0x18000eab1  xor     ecx, ecx; int
0x18000eab3  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x18000eab8  mov     [rsp+78h+var_44], eax
0x18000eabc  test    eax, eax
0x18000eabe  js      loc_18000EB60
0x18000eac4  mov     [rsp+78h+var_47], 1
0x18000eac9  mov     rcx, cs:qword_1800A37A0; WaitHandle
0x18000ead0  test    rcx, rcx
0x18000ead3  jz      short loc_18000EAEA
0x18000ead5  xor     edx, edx; CompletionEvent
0x18000ead7  call    cs:__imp_UnregisterWaitEx
0x18000eade  nop     dword ptr [rax+rax+00h]
0x18000eae3  mov     cs:qword_1800A37A0, rdi
0x18000eaea  mov     [rsp+78h+var_58], 8
0x18000eaf2  mov     r9d, 0FFFFFFFFh
0x18000eaf8  xor     r8d, r8d
0x18000eafb  lea     rdx, ?HandleManagerApmResumeSuspendEvent@@YAXPEAXE@Z; HandleManagerApmResumeSuspendEvent(void *,uchar)
0x18000eb02  mov     rcx, cs:qword_1800A3738
0x18000eb09  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18000eb10  nop     dword ptr [rax+rax+00h]
0x18000eb15  mov     cs:qword_1800A37A0, rax
0x18000eb1c  test    rax, rax
0x18000eb1f  jnz     short loc_18000EB77
0x18000eb21  call    cs:__imp_GetLastError
0x18000eb28  nop     dword ptr [rax+rax+00h]
0x18000eb2d  test    eax, eax
0x18000eb2f  jle     short loc_18000EB39
0x18000eb31  movzx   eax, ax
0x18000eb34  or      eax, 80070000h
0x18000eb39  mov     [rsp+78h+var_44], eax
0x18000eb3d  cmp     [rsp+78h+var_48], 0
0x18000eb42  jnz     short loc_18000EB62
0x18000eb44  cmp     [rsp+78h+var_47], 0
0x18000eb49  jnz     loc_18000EC3A
0x18000eb4f  mov     rbx, [rsp+78h+arg_0]
0x18000eb57  add     rsp, 70h
0x18000eb5b  pop     rdi
0x18000eb5c  retn
0x18000eb5e  jmp     short loc_18000EB3D
0x18000eb60  jmp     short loc_18000EB3D
0x18000eb62  lea     rcx, CriticalSection; lpCriticalSection
0x18000eb69  call    cs:__imp_LeaveCriticalSection
0x18000eb70  nop     dword ptr [rax+rax+00h]
0x18000eb75  jmp     short loc_18000EB44
0x18000eb77  mov     ecx, 47h ; 'G'
0x18000eb7c  call    FileLogAllowEntry
0x18000eb81  test    al, al
0x18000eb83  jz      short loc_18000EB92
0x18000eb85  lea     rcx, aW32tmservicema_3; "W32TmServiceMain: APM resume complete s"...
0x18000eb8c  call    FileLogAdd
0x18000eb91  nop
0x18000eb92  mov     rcx, [rsp+78h+arg_18]
0x18000eb9a  call    cs:__imp__set_se_translator
0x18000eba1  nop     dword ptr [rax+rax+00h]
0x18000eba6  jmp     short loc_18000EB3D
0x18000eba8  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000ebaf  test    rcx, rcx
0x18000ebb2  jz      short loc_18000EC07
0x18000ebb4  cmp     [rcx+13Bh], bl
0x18000ebba  jz      short loc_18000EC07
0x18000ebbc  add     rcx, 50h ; 'P'; Resource
0x18000ebc0  mov     dl, 1; Wait
0x18000ebc2  call    cs:__imp_RtlAcquireResourceShared
0x18000ebc9  nop     dword ptr [rax+rax+00h]
0x18000ebce  test    al, al
0x18000ebd0  jz      short loc_18000EC07
0x18000ebd2  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000ebd9  mov     rdx, [r8+18h]
0x18000ebdd  test    rdx, rdx
0x18000ebe0  jz      short loc_18000EBF7
0x18000ebe2  mov     ecx, [rdx]
0x18000ebe4  cmp     ecx, 47h ; 'G'
0x18000ebe7  ja      short loc_18000EBF7
0x18000ebe9  add     ecx, [rdx+4]
0x18000ebec  cmp     ecx, 47h ; 'G'
0x18000ebef  jbe     short loc_18000EC20
0x18000ebf1  mov     bl, 1
0x18000ebf3  mov     [rsp+78h+var_46], bl
0x18000ebf7  lea     rcx, [r8+50h]; Resource
0x18000ebfb  call    cs:__imp_RtlReleaseResource
0x18000ec02  nop     dword ptr [rax+rax+00h]
0x18000ec07  test    bl, bl
0x18000ec09  jz      loc_18000EA68
0x18000ec0f  lea     rcx, aW32tmservicema_1; "W32TmServiceMain: APM resume.\n"
0x18000ec16  call    FileLogAdd
0x18000ec1b  jmp     loc_18000EA68
0x18000ec20  mov     rdx, [rdx+8]
0x18000ec24  jmp     short loc_18000EBDD
0x18000ec26  jmp     loc_18000EB3D
0x18000ec2b  jmp     loc_18000EB92
0x18000ec30  jmp     loc_18000EB92
0x18000ec35  jmp     loc_18000EB92
0x18000ec3a  mov     ecx, 1; int
0x18000ec3f  call    ?AllowShutdown@@YAJH@Z; AllowShutdown(int)
0x18000ec44  jmp     loc_18000EB4F
```
