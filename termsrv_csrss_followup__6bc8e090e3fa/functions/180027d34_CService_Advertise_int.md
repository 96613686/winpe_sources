# CService::Advertise(int)

- ea: `0x180027d34`
- end: `0x180027f0d`
- name: `?Advertise@CService@@IEAAJH@Z`
- size: `473`
- prototype: `__int64 __fastcall(CService *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18003b8ec`
- `0x18003bc94`

## callees

- `0x180009940`
- `0x180027d34`
- `0x180028dd8`
- `0x180028e44`
- `0x180028f88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027eae`
- `ADVAPI32!SetServiceBits` at `0x180027e4d`
- `ADVAPI32!SetServiceBits` at `0x180027e9e`
- `ADVAPI32!SetServiceBits` at `0x180027e4d`
- `ADVAPI32!SetServiceBits` at `0x180027e9e`

## string_xrefs

- `0x180027dde`: `CService::Advertise`
- `0x180027ecd`: `CService::Advertise`
- `0x180027dd7`: `Registry.OpenKey failed: 0x%x in %s`
- `0x180027e28`: `Registry.ReadRegDWord failed: 0x%x in %s`
- `0x180027e80`: `SetServiceBits failed: 0x%x in %s`
- `0x180027ed7`: `SetServiceBits failed: 0x%x in %s`

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
0x180027d34  mov     [rsp-8+arg_0], rbx
0x180027d39  mov     [rsp-8+arg_10], rsi
0x180027d3e  push    rbp
0x180027d3f  mov     rbp, rsp
0x180027d42  sub     rsp, 80h
0x180027d49  mov     rsi, rcx
0x180027d4c  lea     rcx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180027d53  mov     [rbp+var_28], rcx
0x180027d57  mov     [rbp+var_20], 0
0x180027d5f  mov     [rbp+var_18], 0
0x180027d66  mov     [rbp+var_10], 0
0x180027d6e  or      eax, 0FFFFFFFFh
0x180027d71  mov     [rbp+var_8], eax
0x180027d74  mov     [rbp+var_4], eax
0x180027d77  mov     [rbp+arg_8], 0
0x180027d7e  test    edx, edx
0x180027d80  jz      loc_180027E8C
0x180027d86  mov     [rbp+var_50], rcx
0x180027d8a  mov     [rbp+var_48], 0
0x180027d92  mov     [rbp+var_40], 0
0x180027d99  mov     [rbp+var_38], 0
0x180027da1  mov     [rbp+var_30], eax
0x180027da4  mov     [rbp+var_2C], eax
0x180027da7  mov     r9d, 20019h; unsigned int
0x180027dad  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x180027db4  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180027dbb  lea     rcx, [rbp+var_28]; this
0x180027dbf  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180027dc4  mov     ebx, eax
0x180027dc6  test    eax, eax
0x180027dc8  jle     short loc_180027DD3
0x180027dca  movzx   ebx, ax
0x180027dcd  or      ebx, 80070000h
0x180027dd3  test    ebx, ebx
0x180027dd5  jns     short loc_180027E01
0x180027dd7  lea     rdx, aRegistryOpenke_0; "Registry.OpenKey failed: 0x%x in %s"
0x180027dde  lea     r9, aCserviceAdvert; "CService::Advertise"
0x180027de5  mov     r8d, ebx
0x180027de8  mov     ecx, 8; int
0x180027ded  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027df2  nop
0x180027df3  lea     rcx, [rbp+var_50]; this
0x180027df7  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180027dfc  jmp     loc_180027EEC
0x180027e01  lea     r8, [rbp+arg_8]; unsigned int *
0x180027e05  lea     rdx, aTsadvertise; "TSAdvertise"
0x180027e0c  lea     rcx, [rbp+var_28]; this
0x180027e10  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180027e15  mov     ebx, eax
0x180027e17  test    eax, eax
0x180027e19  jle     short loc_180027E24
0x180027e1b  movzx   ebx, ax
0x180027e1e  or      ebx, 80070000h
0x180027e24  test    ebx, ebx
0x180027e26  jns     short loc_180027E31
0x180027e28  lea     rdx, aRegistryReadre_0; "Registry.ReadRegDWord failed: 0x%x in %"...
0x180027e2f  jmp     short loc_180027DDE
0x180027e31  cmp     [rbp+arg_8], 0
0x180027e35  jnz     short loc_180027E3B
0x180027e37  xor     ebx, ebx
0x180027e39  jmp     short loc_180027DF3
0x180027e3b  mov     edx, 2000000h; dwServiceBits
0x180027e40  mov     r9d, 1; bUpdateImmediately
0x180027e46  mov     r8d, r9d; bSetBitsOn
0x180027e49  mov     rcx, [rsi+8]; hServiceStatus
0x180027e4d  call    cs:__imp_SetServiceBits
0x180027e54  nop     dword ptr [rax+rax+00h]
0x180027e59  test    eax, eax
0x180027e5b  jnz     short loc_180027E37
0x180027e5d  call    cs:__imp_GetLastError
0x180027e64  nop     dword ptr [rax+rax+00h]
0x180027e69  mov     ebx, eax
0x180027e6b  test    eax, eax
0x180027e6d  jle     short loc_180027E78
0x180027e6f  movzx   ebx, ax
0x180027e72  or      ebx, 80070000h
0x180027e78  test    ebx, ebx
0x180027e7a  jns     loc_180027DF3
0x180027e80  lea     rdx, aSetservicebits_0; "SetServiceBits failed: 0x%x in %s"
0x180027e87  jmp     loc_180027DDE
0x180027e8c  mov     r9d, 1; bUpdateImmediately
0x180027e92  xor     r8d, r8d; bSetBitsOn
0x180027e95  mov     edx, 2000000h; dwServiceBits
0x180027e9a  mov     rcx, [rsi+8]; hServiceStatus
0x180027e9e  call    cs:__imp_SetServiceBits
0x180027ea5  nop     dword ptr [rax+rax+00h]
0x180027eaa  test    eax, eax
0x180027eac  jnz     short loc_180027EEA
0x180027eae  call    cs:__imp_GetLastError
0x180027eb5  nop     dword ptr [rax+rax+00h]
0x180027eba  mov     ebx, eax
0x180027ebc  test    eax, eax
0x180027ebe  jle     short loc_180027EC9
0x180027ec0  movzx   ebx, ax
0x180027ec3  or      ebx, 80070000h
0x180027ec9  test    ebx, ebx
0x180027ecb  jns     short loc_180027EEC
0x180027ecd  lea     r9, aCserviceAdvert; "CService::Advertise"
0x180027ed4  mov     r8d, ebx
0x180027ed7  lea     rdx, aSetservicebits_0; "SetServiceBits failed: 0x%x in %s"
0x180027ede  mov     ecx, 8; int
0x180027ee3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027ee8  jmp     short loc_180027EEC
0x180027eea  xor     ebx, ebx
0x180027eec  lea     rcx, [rbp+var_28]; this
0x180027ef0  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180027ef5  mov     eax, ebx
0x180027ef7  lea     r11, [rsp+80h+var_s0]
0x180027eff  mov     rbx, [r11+10h]
0x180027f03  mov     rsi, [r11+20h]
0x180027f07  mov     rsp, r11
0x180027f0a  pop     rbp
0x180027f0b  retn
```
