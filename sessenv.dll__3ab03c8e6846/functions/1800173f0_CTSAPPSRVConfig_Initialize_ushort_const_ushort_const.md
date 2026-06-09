# CTSAPPSRVConfig::Initialize(ushort const *,ushort const *)

- ea: `0x1800173f0`
- end: `0x18001755d`
- name: `?Initialize@CTSAPPSRVConfig@@UEAAJPEBG0@Z`
- size: `365`
- prototype: `__int64 __fastcall(CTSAPPSRVConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180003f30`
- `0x180005190`
- `0x1800173f0`
- `0x18001ec04`
- `0x18003508c`
- `0x18005d010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180017545`
- `ntdll!RtlReleaseResource` at `0x180017545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001747d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001747d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001746a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001746a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800174d9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800174d9`

## string_xrefs

- `0x180017448`: `OpenKey on machine failed 0x%08x`
- `0x18001749a`: `CreateEvent failed: 0x%x in %s`
- `0x18001751f`: `CTSAPPSRVConfig::Initialize`
- `0x180017518`: `CTSAPPSRVConfig failed on CreateThread() failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSAPPSRVConfig::Initialize(
        CTSAPPSRVConfig *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  signed int v4; // edi
  signed int v6; // eax
  __int64 i; // rbx
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v10; // rax
  signed int v11; // eax
  const unsigned __int16 *dwCreationFlags; // [rsp+20h] [rbp-28h]
  PRTL_RESOURCE Resource; // [rsp+30h] [rbp-18h] BYREF
  int v15; // [rsp+38h] [rbp-10h]
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  ThreadId = 0;
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)&Resource, (CTSAPPSRVConfig *)((char *)this + 1592));
  v6 = CRegistry::OpenKey((CTSAPPSRVConfig *)((char *)this + 1736), HKEY_LOCAL_MACHINE, a3, 0x20019u, dwCreationFlags);
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    _DbgPrintMessage(4, "OpenKey on machine failed 0x%08x", v6);
  }
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + i + 214) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
      {
        _DbgPrintMessage(8, "CreateEvent failed: 0x%x in %s", (unsigned int)v4, "CTSAPPSRVConfig::Initialize");
        goto LABEL_18;
      }
    }
  }
  (*(void (__fastcall **)(CTSAPPSRVConfig *))(*(_QWORD *)this + 8LL))(this);
  v10 = CreateThread(0, 0, CTSAPPSRVConfig::StaticMonitorThread, this, 0, &ThreadId);
  SmartHANDLE::operator=((char *)this + 1784, v10);
  if ( !*((_QWORD *)this + 223) )
  {
    (*(void (__fastcall **)(CTSAPPSRVConfig *))(*(_QWORD *)this + 16LL))(this);
    v11 = GetLastError();
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    if ( v4 < 0 )
      _DbgPrintMessage(
        8,
        "CTSAPPSRVConfig failed on CreateThread() failed: 0x%x in %s",
        (unsigned int)v4,
        "CTSAPPSRVConfig::Initialize");
  }
LABEL_18:
  if ( v15 && LODWORD(Resource[1].Lock.DebugInfo) )
    RtlReleaseResource(Resource);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800173f0  mov     rax, rsp
0x1800173f3  mov     [rax+10h], rbx
0x1800173f7  mov     [rax+18h], rsi
0x1800173fb  push    rdi
0x1800173fc  sub     rsp, 40h
0x180017400  mov     rsi, rcx
0x180017403  lea     rdx, [rcx+638h]; struct CResource *
0x18001740a  xor     edi, edi
0x18001740c  lea     rcx, [rax-18h]; this
0x180017410  mov     [rax+8], edi
0x180017413  mov     rbx, r8
0x180017416  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18001741b  lea     rcx, [rsi+6C8h]; this
0x180017422  mov     r9d, 20019h; unsigned int
0x180017428  mov     r8, rbx; unsigned __int16 *
0x18001742b  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180017432  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180017437  test    eax, eax
0x180017439  jz      short loc_180017459
0x18001743b  jle     short loc_180017445
0x18001743d  movzx   eax, ax
0x180017440  or      eax, 80070000h
0x180017445  mov     r8d, eax
0x180017448  lea     rdx, aOpenkeyOnMachi; "OpenKey on machine failed 0x%08x"
0x18001744f  mov     ecx, 4; int
0x180017454  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017459  xor     ebx, ebx
0x18001745b  cmp     ebx, 3
0x18001745e  jnb     short loc_1800174A3
0x180017460  xor     r9d, r9d; lpName
0x180017463  xor     r8d, r8d; bInitialState
0x180017466  xor     edx, edx; bManualReset
0x180017468  xor     ecx, ecx; lpEventAttributes
0x18001746a  call    cs:__imp_CreateEventW
0x180017470  mov     [rsi+rbx*8+6B0h], rax
0x180017478  test    rax, rax
0x18001747b  jnz     short loc_180017496
0x18001747d  call    cs:__imp_GetLastError
0x180017483  mov     edi, eax
0x180017485  test    eax, eax
0x180017487  jle     short loc_180017492
0x180017489  movzx   edi, ax
0x18001748c  or      edi, 80070000h
0x180017492  test    edi, edi
0x180017494  js      short loc_18001749A
0x180017496  inc     ebx
0x180017498  jmp     short loc_18001745B
0x18001749a  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x1800174a1  jmp     short loc_18001751F
0x1800174a3  mov     rax, [rsi]
0x1800174a6  mov     rcx, rsi
0x1800174a9  mov     rax, [rax+8]
0x1800174ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174b2  lea     rax, [rsp+48h+ThreadId]
0x1800174b7  mov     r9, rsi; lpParameter
0x1800174ba  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800174bf  lea     r8, ?StaticMonitorThread@CTSAPPSRVConfig@@CAKPEAX@Z; lpStartAddress
0x1800174c6  xor     edx, edx; dwStackSize
0x1800174c8  mov     dword ptr [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800174d0  xor     ecx, ecx; lpThreadAttributes
0x1800174d2  lea     rbx, [rsi+6F8h]
0x1800174d9  call    cs:__imp_CreateThread
0x1800174df  mov     rdx, rax
0x1800174e2  mov     rcx, rbx
0x1800174e5  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x1800174ea  cmp     qword ptr [rbx], 0
0x1800174ee  jnz     short loc_180017533
0x1800174f0  mov     rax, [rsi]
0x1800174f3  mov     rcx, rsi
0x1800174f6  mov     rax, [rax+10h]
0x1800174fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174ff  call    cs:__imp_GetLastError
0x180017505  mov     edi, eax
0x180017507  test    eax, eax
0x180017509  jle     short loc_180017514
0x18001750b  movzx   edi, ax
0x18001750e  or      edi, 80070000h
0x180017514  test    edi, edi
0x180017516  jns     short loc_180017533
0x180017518  lea     rdx, aCtsappsrvconfi_3; "CTSAPPSRVConfig failed on CreateThread("...
0x18001751f  lea     r9, aCtsappsrvconfi_5; "CTSAPPSRVConfig::Initialize"
0x180017526  mov     r8d, edi
0x180017529  mov     ecx, 8; int
0x18001752e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017533  cmp     [rsp+48h+var_10], 0
0x180017538  jz      short loc_18001754B
0x18001753a  mov     rcx, [rsp+48h+Resource]; Resource
0x18001753f  cmp     dword ptr [rcx+60h], 0
0x180017543  jz      short loc_18001754B
0x180017545  call    cs:__imp_RtlReleaseResource
0x18001754b  mov     rbx, [rsp+48h+arg_8]
0x180017550  mov     eax, edi
0x180017552  mov     rsi, [rsp+48h+arg_10]
0x180017557  add     rsp, 40h
0x18001755b  pop     rdi
0x18001755c  retn
```
