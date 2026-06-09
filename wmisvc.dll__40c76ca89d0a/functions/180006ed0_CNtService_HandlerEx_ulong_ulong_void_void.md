# CNtService::HandlerEx(ulong,ulong,void *,void *)

- ea: `0x180006ed0`
- end: `0x18000710f`
- name: `?HandlerEx@CNtService@@EEAAKKKPEAX0@Z`
- size: `575`
- prototype: `__int64 __fastcall(CNtService *this, int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004120`
- `0x180004c30`
- `0x180006ed0`
- `0x18000b478`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070ed`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180006f67`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180006f67`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180006fee`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180006fee`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180006f7f`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180006f7f`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x1800070d7`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x1800070d7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800070e2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800070e2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006fc3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006fc3`

## string_xrefs

- `0x180006f73`: `LastServiceStart`
- `0x1800070cb`: `LastServiceStart`
- `0x1800070f6`: `Could not SetServiceStatus`

## pseudocode

```c
__int64 __fastcall CNtService::HandlerEx(CNtService *this, int a2, unsigned int a3, void *a4)
{
  unsigned int v6; // r9d
  unsigned int v7; // ecx
  unsigned int v8; // edx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // edx
  unsigned int v13; // r10d
  unsigned __int16 *v14; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v15[24]; // [rsp+38h] [rbp-A0h] BYREF
  unsigned __int16 v16[40]; // [rsp+50h] [rbp-88h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = *((_DWORD *)this + 8);
  if ( v8 != 4 && v8 != 1 )
  {
    v6 = 1;
    v7 = 120000;
  }
  switch ( a2 )
  {
    case 1:
      goto LABEL_7;
    case 2:
      CNtService::ReportStatusToSCMgr(this, 6u, a3, 1u, 0x1D4C0u);
      (*(void (__fastcall **)(CNtService *))(*(_QWORD *)this + 40LL))(this);
      v12 = 7;
      goto LABEL_20;
    case 3:
      CNtService::ReportStatusToSCMgr(this, 5u, a3, 1u, 0x1D4C0u);
      (*(void (__fastcall **)(CNtService *))(*(_QWORD *)this + 48LL))(this);
      v12 = 4;
LABEL_20:
      CNtService::ReportStatusToSCMgr(this, v12, v11, 0, 0);
      return 0;
    case 4:
      return 0;
    case 5:
LABEL_7:
      v14 = 0;
      Registry::Registry((Registry *)v15, L"Software\\Microsoft\\WBEM\\CIMOM", 3u);
      if ( Registry::GetStr((Registry *)v15, L"LastServiceStart", &v14) != 1 )
      {
        StringCchCopyW(v16, 0x21u, v14);
        StringCchCatW(v16, v13, L" (STOP) ");
        Registry::SetStr((Registry *)v15, L"LastServiceStart", v16);
        CWin32DefaultArena::WbemMemFree(v14);
      }
      *((_DWORD *)this + 9) = *((_DWORD *)this + 6) | 5;
      *((_DWORD *)this + 8) = 3;
      *((_DWORD *)this + 10) = 0;
      *((_DWORD *)this + 12) = 1;
      v10 = 10000;
      if ( a2 != 5 )
        v10 = 120000;
      *((_DWORD *)this + 13) = v10;
      if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 7), (LPSERVICE_STATUS)this + 1) )
      {
        GetLastError();
        (*(void (__fastcall **)(CNtService *, const wchar_t *))(*(_QWORD *)this + 56LL))(
          this,
          L"Could not SetServiceStatus");
      }
      (*(void (__fastcall **)(CNtService *, bool))(*(_QWORD *)this + 16LL))(this, a2 == 5);
      Registry::~Registry((Registry *)v15);
      return 0;
  }
  CNtService::ReportStatusToSCMgr(this, v8, a3, v6, v7);
  return 120;
}

```

## disassembly

```asm
0x180006ed0  push    rbx
0x180006ed2  push    rsi
0x180006ed3  push    rdi
0x180006ed4  push    r15
0x180006ed6  sub     rsp, 0B8h
0x180006edd  mov     rax, cs:__security_cookie
0x180006ee4  xor     rax, rsp
0x180006ee7  mov     [rsp+0D8h+var_38], rax
0x180006eef  mov     edi, edx
0x180006ef1  mov     rbx, rcx
0x180006ef4  xor     r9d, r9d; unsigned int
0x180006ef7  xor     ecx, ecx
0x180006ef9  mov     edx, [rbx+20h]; unsigned int
0x180006efc  mov     r15d, 1D4C0h
0x180006f02  cmp     edx, 4
0x180006f05  jnz     loc_180006FF9
0x180006f0b  mov     eax, edi
0x180006f0d  sub     eax, 1
0x180006f10  jz      short loc_180006F4C
0x180006f12  sub     eax, 1
0x180006f15  jz      loc_18000705B
0x180006f1b  sub     eax, 1
0x180006f1e  jz      loc_18000702F
0x180006f24  sub     eax, 1
0x180006f27  jnz     loc_180007010
0x180006f2d  xor     eax, eax
0x180006f2f  mov     rcx, [rsp+0D8h+var_38]
0x180006f37  xor     rcx, rsp; StackCookie
0x180006f3a  call    __security_check_cookie
0x180006f3f  add     rsp, 0B8h
0x180006f46  pop     r15
0x180006f48  pop     rdi
0x180006f49  pop     rsi
0x180006f4a  pop     rbx
0x180006f4b  retn
0x180006f4c  mov     [rsp+0D8h+var_A8], 0
0x180006f55  mov     r8d, 3
0x180006f5b  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x180006f62  lea     rcx, [rsp+0D8h+var_A0]
0x180006f67  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x180006f6d  nop
0x180006f6e  lea     r8, [rsp+0D8h+var_A8]
0x180006f73  lea     rdx, aLastservicesta; "LastServiceStart"
0x180006f7a  lea     rcx, [rsp+0D8h+var_A0]
0x180006f7f  call    cs:__imp_?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z; Registry::GetStr(ushort const *,ushort * *)
0x180006f85  cmp     eax, 1
0x180006f88  jnz     loc_18000709A
0x180006f8e  mov     eax, [rbx+18h]
0x180006f91  or      eax, 5
0x180006f94  mov     [rbx+24h], eax
0x180006f97  mov     dword ptr [rbx+20h], 3
0x180006f9e  mov     dword ptr [rbx+28h], 0
0x180006fa5  mov     dword ptr [rbx+30h], 1
0x180006fac  mov     eax, 2710h
0x180006fb1  cmp     edi, 5
0x180006fb4  cmovnz  eax, r15d
0x180006fb8  mov     [rbx+34h], eax
0x180006fbb  lea     rdx, [rbx+1Ch]; lpServiceStatus
0x180006fbf  mov     rcx, [rbx+38h]; hServiceStatus
0x180006fc3  call    cs:__imp_SetServiceStatus
0x180006fc9  test    eax, eax
0x180006fcb  jz      loc_1800070ED
0x180006fd1  mov     rax, [rbx]
0x180006fd4  xor     edx, edx
0x180006fd6  cmp     edi, 5
0x180006fd9  setz    dl
0x180006fdc  mov     rcx, rbx
0x180006fdf  mov     rax, [rax+10h]
0x180006fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe8  nop
0x180006fe9  lea     rcx, [rsp+0D8h+var_A0]
0x180006fee  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180006ff4  jmp     loc_180006F2D
0x180006ff9  cmp     edx, 1
0x180006ffc  jz      loc_180006F0B
0x180007002  mov     r9d, 1
0x180007008  mov     ecx, r15d
0x18000700b  jmp     loc_180006F0B
0x180007010  cmp     eax, 1
0x180007013  jz      loc_180006F4C
0x180007019  mov     [rsp+0D8h+var_B8], ecx; unsigned int
0x18000701d  mov     rcx, rbx; this
0x180007020  call    ?ReportStatusToSCMgr@CNtService@@IEAAKKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x180007025  mov     eax, 78h ; 'x'
0x18000702a  jmp     loc_180006F2F
0x18000702f  mov     [rsp+0D8h+var_B8], r15d; unsigned int
0x180007034  mov     edx, 5; unsigned int
0x180007039  lea     r9d, [rdx-4]; unsigned int
0x18000703d  mov     rcx, rbx; this
0x180007040  call    ?ReportStatusToSCMgr@CNtService@@IEAAKKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x180007045  mov     rax, [rbx]
0x180007048  mov     rcx, rbx
0x18000704b  mov     rax, [rax+30h]
0x18000704f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007054  mov     edx, 4
0x180007059  jmp     short loc_180007085
0x18000705b  mov     [rsp+0D8h+var_B8], r15d; unsigned int
0x180007060  mov     edx, 6; unsigned int
0x180007065  lea     r9d, [rdx-5]; unsigned int
0x180007069  mov     rcx, rbx; this
0x18000706c  call    ?ReportStatusToSCMgr@CNtService@@IEAAKKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x180007071  mov     rax, [rbx]
0x180007074  mov     rcx, rbx
0x180007077  mov     rax, [rax+28h]
0x18000707b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007080  mov     edx, 7; unsigned int
0x180007085  xor     r9d, r9d; unsigned int
0x180007088  mov     [rsp+0D8h+var_B8], r9d; unsigned int
0x18000708d  mov     rcx, rbx; this
0x180007090  call    ?ReportStatusToSCMgr@CNtService@@IEAAKKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x180007095  jmp     loc_180006F2D
0x18000709a  mov     r8, [rsp+0D8h+var_A8]; unsigned __int16 *
0x18000709f  mov     r10d, 21h ; '!'
0x1800070a5  mov     edx, r10d; unsigned __int64
0x1800070a8  lea     rcx, [rsp+0D8h+var_88]; unsigned __int16 *
0x1800070ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800070b2  lea     r8, aStop; " (STOP) "
0x1800070b9  mov     edx, r10d; unsigned __int64
0x1800070bc  lea     rcx, [rsp+0D8h+var_88]; unsigned __int16 *
0x1800070c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800070c6  lea     r8, [rsp+0D8h+var_88]
0x1800070cb  lea     rdx, aLastservicesta; "LastServiceStart"
0x1800070d2  lea     rcx, [rsp+0D8h+var_A0]
0x1800070d7  call    cs:__imp_?SetStr@Registry@@QEAAHPEBG0@Z; Registry::SetStr(ushort const *,ushort const *)
0x1800070dd  mov     rcx, [rsp+0D8h+var_A8]
0x1800070e2  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800070e8  jmp     loc_180006F8E
0x1800070ed  call    cs:__imp_GetLastError
0x1800070f3  mov     rax, [rbx]
0x1800070f6  lea     rdx, aCouldNotSetser; "Could not SetServiceStatus"
0x1800070fd  mov     rcx, rbx
0x180007100  mov     rax, [rax+38h]
0x180007104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007109  jmp     loc_180006FD1
```
