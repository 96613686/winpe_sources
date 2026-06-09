# CService::Advertise(int)

- ea: `0x18002693c`
- end: `0x180026af8`
- name: `?Advertise@CService@@IEAAJH@Z`
- size: `444`
- prototype: `__int64 __fastcall(CService *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18003986c`
- `0x180039bf0`

## callees

- `0x18000a210`
- `0x18002693c`
- `0x1800279a8`
- `0x180027a04`
- `0x180027b44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026aa0`
- `ADVAPI32!SetServiceBits` at `0x180026a55`
- `ADVAPI32!SetServiceBits` at `0x180026a96`
- `ADVAPI32!SetServiceBits` at `0x180026a55`
- `ADVAPI32!SetServiceBits` at `0x180026a96`

## string_xrefs

- `0x1800269e6`: `CService::Advertise`
- `0x180026ab9`: `CService::Advertise`
- `0x1800269df`: `Registry.OpenKey failed: 0x%x in %s`
- `0x180026a30`: `Registry.ReadRegDWord failed: 0x%x in %s`
- `0x180026a78`: `SetServiceBits failed: 0x%x in %s`
- `0x180026ac3`: `SetServiceBits failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CService::Advertise(SERVICE_STATUS_HANDLE *this, int a2)
{
  int v3; // eax
  signed int v4; // ebx
  int v5; // eax
  signed int LastError; // eax
  signed int v7; // eax
  const unsigned __int16 *v9; // [rsp+20h] [rbp-60h]
  _QWORD v10[2]; // [rsp+30h] [rbp-50h] BYREF
  int v11; // [rsp+40h] [rbp-40h]
  __int64 v12; // [rsp+48h] [rbp-38h]
  int v13; // [rsp+50h] [rbp-30h]
  int v14; // [rsp+54h] [rbp-2Ch]
  _QWORD v15[2]; // [rsp+58h] [rbp-28h] BYREF
  int v16; // [rsp+68h] [rbp-18h]
  __int64 v17; // [rsp+70h] [rbp-10h]
  int v18; // [rsp+78h] [rbp-8h]
  int v19; // [rsp+7Ch] [rbp-4h]
  unsigned int v20; // [rsp+98h] [rbp+18h] BYREF

  v15[0] = &CRegistry::`vftable';
  v15[1] = 0;
  v16 = 0;
  v17 = 0;
  v18 = -1;
  v19 = -1;
  v20 = 0;
  if ( a2 )
  {
    v10[0] = &CRegistry::`vftable';
    v10[1] = 0;
    v11 = 0;
    v12 = 0;
    v13 = -1;
    v14 = -1;
    v3 = CRegistry::OpenKey(
           (CRegistry *)v15,
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Terminal Server",
           0x20019u,
           v9);
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( v4 >= 0 )
    {
      v5 = CRegistry::ReadRegDWord((CRegistry *)v15, L"TSAdvertise", &v20);
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      if ( v4 >= 0 )
      {
        if ( !v20 || SetServiceBits(this[1], 0x2000000u, 1, 1) )
        {
          v4 = 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          if ( v4 < 0 )
            _DbgPrintMessage(8, "SetServiceBits failed: 0x%x in %s", (unsigned int)v4, "CService::Advertise");
        }
      }
      else
      {
        _DbgPrintMessage(8, "Registry.ReadRegDWord failed: 0x%x in %s", (unsigned int)v4, "CService::Advertise");
      }
    }
    else
    {
      _DbgPrintMessage(8, "Registry.OpenKey failed: 0x%x in %s", (unsigned int)v4, "CService::Advertise");
    }
    CRegistry::~CRegistry((CRegistry *)v10);
  }
  else if ( SetServiceBits(this[1], 0x2000000u, 0, 1) )
  {
    v4 = 0;
  }
  else
  {
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 < 0 )
      _DbgPrintMessage(8, "SetServiceBits failed: 0x%x in %s", v4, "CService::Advertise");
  }
  CRegistry::~CRegistry((CRegistry *)v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002693c  mov     [rsp-8+arg_0], rbx
0x180026941  mov     [rsp-8+arg_10], rsi
0x180026946  push    rbp
0x180026947  mov     rbp, rsp
0x18002694a  sub     rsp, 80h
0x180026951  mov     rsi, rcx
0x180026954  lea     rcx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18002695b  mov     [rbp+var_28], rcx
0x18002695f  mov     [rbp+var_20], 0
0x180026967  mov     [rbp+var_18], 0
0x18002696e  mov     [rbp+var_10], 0
0x180026976  or      eax, 0FFFFFFFFh
0x180026979  mov     [rbp+var_8], eax
0x18002697c  mov     [rbp+var_4], eax
0x18002697f  mov     [rbp+arg_8], 0
0x180026986  test    edx, edx
0x180026988  jz      loc_180026A84
0x18002698e  mov     [rbp+var_50], rcx
0x180026992  mov     [rbp+var_48], 0
0x18002699a  mov     [rbp+var_40], 0
0x1800269a1  mov     [rbp+var_38], 0
0x1800269a9  mov     [rbp+var_30], eax
0x1800269ac  mov     [rbp+var_2C], eax
0x1800269af  mov     r9d, 20019h; unsigned int
0x1800269b5  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800269bc  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800269c3  lea     rcx, [rbp+var_28]; this
0x1800269c7  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x1800269cc  mov     ebx, eax
0x1800269ce  test    eax, eax
0x1800269d0  jle     short loc_1800269DB
0x1800269d2  movzx   ebx, ax
0x1800269d5  or      ebx, 80070000h
0x1800269db  test    ebx, ebx
0x1800269dd  jns     short loc_180026A09
0x1800269df  lea     rdx, aRegistryOpenke_0; "Registry.OpenKey failed: 0x%x in %s"
0x1800269e6  lea     r9, aCserviceAdvert; "CService::Advertise"
0x1800269ed  mov     r8d, ebx
0x1800269f0  mov     ecx, 8; int
0x1800269f5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800269fa  nop
0x1800269fb  lea     rcx, [rbp+var_50]; this
0x1800269ff  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180026a04  jmp     loc_180026AD8
0x180026a09  lea     r8, [rbp+arg_8]; unsigned int *
0x180026a0d  lea     rdx, aTsadvertise; "TSAdvertise"
0x180026a14  lea     rcx, [rbp+var_28]; this
0x180026a18  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180026a1d  mov     ebx, eax
0x180026a1f  test    eax, eax
0x180026a21  jle     short loc_180026A2C
0x180026a23  movzx   ebx, ax
0x180026a26  or      ebx, 80070000h
0x180026a2c  test    ebx, ebx
0x180026a2e  jns     short loc_180026A39
0x180026a30  lea     rdx, aRegistryReadre_0; "Registry.ReadRegDWord failed: 0x%x in %"...
0x180026a37  jmp     short loc_1800269E6
0x180026a39  cmp     [rbp+arg_8], 0
0x180026a3d  jnz     short loc_180026A43
0x180026a3f  xor     ebx, ebx
0x180026a41  jmp     short loc_1800269FB
0x180026a43  mov     edx, 2000000h; dwServiceBits
0x180026a48  mov     r9d, 1; bUpdateImmediately
0x180026a4e  mov     r8d, r9d; bSetBitsOn
0x180026a51  mov     rcx, [rsi+8]; hServiceStatus
0x180026a55  call    cs:__imp_SetServiceBits
0x180026a5b  test    eax, eax
0x180026a5d  jnz     short loc_180026A3F
0x180026a5f  call    cs:__imp_GetLastError
0x180026a65  mov     ebx, eax
0x180026a67  test    eax, eax
0x180026a69  jle     short loc_180026A74
0x180026a6b  movzx   ebx, ax
0x180026a6e  or      ebx, 80070000h
0x180026a74  test    ebx, ebx
0x180026a76  jns     short loc_1800269FB
0x180026a78  lea     rdx, aSetservicebits_0; "SetServiceBits failed: 0x%x in %s"
0x180026a7f  jmp     loc_1800269E6
0x180026a84  mov     r9d, 1; bUpdateImmediately
0x180026a8a  xor     r8d, r8d; bSetBitsOn
0x180026a8d  mov     edx, 2000000h; dwServiceBits
0x180026a92  mov     rcx, [rsi+8]; hServiceStatus
0x180026a96  call    cs:__imp_SetServiceBits
0x180026a9c  test    eax, eax
0x180026a9e  jnz     short loc_180026AD6
0x180026aa0  call    cs:__imp_GetLastError
0x180026aa6  mov     ebx, eax
0x180026aa8  test    eax, eax
0x180026aaa  jle     short loc_180026AB5
0x180026aac  movzx   ebx, ax
0x180026aaf  or      ebx, 80070000h
0x180026ab5  test    ebx, ebx
0x180026ab7  jns     short loc_180026AD8
0x180026ab9  lea     r9, aCserviceAdvert; "CService::Advertise"
0x180026ac0  mov     r8d, ebx
0x180026ac3  lea     rdx, aSetservicebits_0; "SetServiceBits failed: 0x%x in %s"
0x180026aca  mov     ecx, 8; int
0x180026acf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180026ad4  jmp     short loc_180026AD8
0x180026ad6  xor     ebx, ebx
0x180026ad8  lea     rcx, [rbp+var_28]; this
0x180026adc  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180026ae1  mov     eax, ebx
0x180026ae3  lea     r11, [rsp+80h+var_s0]
0x180026aeb  mov     rbx, [r11+10h]
0x180026aef  mov     rsi, [r11+20h]
0x180026af3  mov     rsp, r11
0x180026af6  pop     rbp
0x180026af7  retn
```
