# PowerNotificationCallback(void *,ulong,void *)

- ea: `0x18000c5e0`
- end: `0x18000c7c3`
- name: `?PowerNotificationCallback@@YAKPEAXK0@Z`
- size: `483`
- prototype: `unsigned int(void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c3ac`
- `0x18000c5e0`
- `0x18000c7d0`
- `0x180018138`
- `0x18001d9a0`
- `0x18003f485`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000c74a`
- `ntdll!RtlReleaseResource` at `0x18000c74a`
- `ntdll!RtlAcquireResourceShared` at `0x18000c702`
- `ntdll!RtlAcquireResourceShared` at `0x18000c702`

## string_xrefs

- `0x18000c6bf`: `PowerNotificationCallback: Ignoring suspend notification since we were already in that state.\n`

## pseudocode

```c
__int64 __fastcall PowerNotificationCallback(void *a1, unsigned int a2, _DWORD *a3)
{
  int v5; // ebx
  char v7; // si
  __int64 i; // rdx

  if ( a2 == 32787 && a3 && !memcmp_0(a3, &GUID_LOW_POWER_EPOCH, 0x10u) && a3[4] == 4 )
  {
    v5 = a3[5];
    if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
      && _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      v7 = 0;
      for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x3Cu; i = *(_QWORD *)(i + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x3C )
        {
          v7 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
      if ( v7 )
        FileLogAdd(L"PowerNotificationCallback: Data:%d SuspendState:%d\n", v5 != 0, (unsigned int)dword_1800A3758);
    }
    if ( !v5 )
    {
      if ( _InterlockedCompareExchange(&dword_1800A3758, 0, 1) == 1 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(60) )
          FileLogAdd(L"PowerNotificationCallback: Resuming from suspend state\n");
        HandleManagerApmResumeSuspend();
      }
      else if ( (unsigned __int8)FileLogAllowEntry(60) )
      {
        FileLogAdd(L"PowerNotificationCallback: Ignoring resume notification since we never entered suspend state.\n");
      }
      return 0;
    }
    if ( _InterlockedCompareExchange(&dword_1800A3758, 1, 0) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(60) )
        FileLogAdd(L"PowerNotificationCallback: Ignoring suspend notification since we were already in that state.\n");
      return 0;
    }
    if ( (unsigned __int8)FileLogAllowEntry(60) )
      FileLogAdd(L"PowerNotificationCallback: Entering suspend state\n");
    HandleManagerApmSuspend();
    return 0;
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Unknown power notification callback. Type: 0x%08X\n", a2);
    return 87;
  }
}

```

## disassembly

```asm
0x18000c5e0  mov     [rsp+arg_8], rbx
0x18000c5e5  push    rdi
0x18000c5e6  sub     rsp, 20h
0x18000c5ea  mov     rbx, r8
0x18000c5ed  mov     edi, edx
0x18000c5ef  cmp     edx, 8013h
0x18000c5f5  jnz     loc_18000C7A0
0x18000c5fb  test    rbx, rbx
0x18000c5fe  jz      loc_18000C7A0
0x18000c604  mov     r8d, 10h; Size
0x18000c60a  lea     rdx, GUID_LOW_POWER_EPOCH; Buf2
0x18000c611  mov     rcx, rbx; Buf1
0x18000c614  call    memcmp_0
0x18000c619  test    eax, eax
0x18000c61b  jnz     loc_18000C7A0
0x18000c621  cmp     dword ptr [rbx+10h], 4
0x18000c625  jnz     loc_18000C7A0
0x18000c62b  mov     ebx, [rbx+14h]
0x18000c62e  xor     edi, edi
0x18000c630  test    ebx, ebx
0x18000c632  setnz   dil
0x18000c636  xor     ecx, ecx
0x18000c638  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x18000c640  jnz     loc_18000C6DF
0x18000c646  test    ebx, ebx
0x18000c648  jnz     short loc_18000C680
0x18000c64a  xor     ecx, ecx
0x18000c64c  mov     eax, 1
0x18000c651  lock cmpxchg cs:dword_1800A3758, ecx
0x18000c659  mov     ecx, 3Ch ; '<'
0x18000c65e  jnz     short loc_18000C6C8
0x18000c660  call    FileLogAllowEntry
0x18000c665  test    al, al
0x18000c667  jnz     loc_18000C78F
0x18000c66d  call    ?HandleManagerApmResumeSuspend@@YAJXZ; HandleManagerApmResumeSuspend(void)
0x18000c672  xor     eax, eax
0x18000c674  mov     rbx, [rsp+28h+arg_8]
0x18000c679  add     rsp, 20h
0x18000c67d  pop     rdi
0x18000c67e  retn
0x18000c680  mov     edx, 1
0x18000c685  xor     eax, eax
0x18000c687  lock cmpxchg cs:dword_1800A3758, edx
0x18000c68f  mov     ecx, 3Ch ; '<'
0x18000c694  jnz     short loc_18000C6B6
0x18000c696  call    FileLogAllowEntry
0x18000c69b  test    al, al
0x18000c69d  jnz     loc_18000C77E
0x18000c6a3  call    ?HandleManagerApmSuspend@@YAJXZ; HandleManagerApmSuspend(void)
0x18000c6a8  mov     rbx, [rsp+28h+arg_8]
0x18000c6ad  xor     eax, eax
0x18000c6af  add     rsp, 20h
0x18000c6b3  pop     rdi
0x18000c6b4  retn
0x18000c6b6  call    FileLogAllowEntry
0x18000c6bb  test    al, al
0x18000c6bd  jz      short loc_18000C672
0x18000c6bf  lea     rcx, aPowernotificat_3; "PowerNotificationCallback: Ignoring sus"...
0x18000c6c6  jmp     short loc_18000C6D8
0x18000c6c8  call    FileLogAllowEntry
0x18000c6cd  test    al, al
0x18000c6cf  jz      short loc_18000C672
0x18000c6d1  lea     rcx, aPowernotificat_0; "PowerNotificationCallback: Ignoring res"...
0x18000c6d8  call    FileLogAdd
0x18000c6dd  jmp     short loc_18000C672
0x18000c6df  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000c6e6  test    rcx, rcx
0x18000c6e9  jz      loc_18000C646
0x18000c6ef  cmp     byte ptr [rcx+13Bh], 0
0x18000c6f6  jz      loc_18000C646
0x18000c6fc  add     rcx, 50h ; 'P'; Resource
0x18000c700  mov     dl, 1; Wait
0x18000c702  call    cs:__imp_RtlAcquireResourceShared
0x18000c709  nop     dword ptr [rax+rax+00h]
0x18000c70e  test    al, al
0x18000c710  jz      loc_18000C646
0x18000c716  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000c71d  mov     [rsp+28h+arg_0], rsi
0x18000c722  xor     sil, sil
0x18000c725  mov     rdx, [r8+18h]
0x18000c729  test    rdx, rdx
0x18000c72c  jz      short loc_18000C746
0x18000c72e  mov     ecx, [rdx]
0x18000c730  cmp     ecx, 3Ch ; '<'
0x18000c733  ja      short loc_18000C746
0x18000c735  add     ecx, [rdx+4]
0x18000c738  cmp     ecx, 3Ch ; '<'
0x18000c73b  ja      short loc_18000C743
0x18000c73d  mov     rdx, [rdx+8]
0x18000c741  jmp     short loc_18000C729
0x18000c743  mov     sil, 1
0x18000c746  lea     rcx, [r8+50h]; Resource
0x18000c74a  call    cs:__imp_RtlReleaseResource
0x18000c751  nop     dword ptr [rax+rax+00h]
0x18000c756  test    sil, sil
0x18000c759  mov     rsi, [rsp+28h+arg_0]
0x18000c75e  jz      loc_18000C646
0x18000c764  mov     r8d, cs:dword_1800A3758
0x18000c76b  lea     rcx, aPowernotificat_1; "PowerNotificationCallback: Data:%d Susp"...
0x18000c772  mov     edx, edi
0x18000c774  call    FileLogAdd
0x18000c779  jmp     loc_18000C646
0x18000c77e  lea     rcx, aPowernotificat; "PowerNotificationCallback: Entering sus"...
0x18000c785  call    FileLogAdd
0x18000c78a  jmp     loc_18000C6A3
0x18000c78f  lea     rcx, aPowernotificat_2; "PowerNotificationCallback: Resuming fro"...
0x18000c796  call    FileLogAdd
0x18000c79b  jmp     loc_18000C66D
0x18000c7a0  xor     ecx, ecx
0x18000c7a2  call    FileLogAllowEntry
0x18000c7a7  test    al, al
0x18000c7a9  jz      short loc_18000C7B9
0x18000c7ab  mov     edx, edi
0x18000c7ad  lea     rcx, aUnknownPowerNo; "Unknown power notification callback. Ty"...
0x18000c7b4  call    FileLogAdd
0x18000c7b9  mov     eax, 57h ; 'W'
0x18000c7be  jmp     loc_18000C674
```
