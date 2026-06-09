# RegWriteStringValue(HKEY__ *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180012b94`
- end: `0x180012c63`
- name: `?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `207`
- prototype: `unsigned int __fastcall(HKEY, const WCHAR *, __int64 *lpData)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fd88`
- `0x1800103b8`
- `0x180017510`
- `0x18001764c`
- `0x18001780c`
- `0x1800178f0`
- `0x180018bd4`
- `0x180018cdc`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180012b94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012bc1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012bc1`

## string_xrefs

- `0x180012c08`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall RegWriteStringValue(HKEY a1, const WCHAR *a2, __int64 *lpData)
{
  DWORD cbData; // eax
  unsigned int result; // eax
  unsigned int v5; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char v7; // [rsp+38h] [rbp-40h]
  const char *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  __int64 v10; // [rsp+50h] [rbp-28h]
  unsigned int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  int v13; // [rsp+60h] [rbp-18h]

  cbData = 2 * *((_DWORD *)lpData + 4) + 2;
  if ( (unsigned __int64)lpData[3] >= 8 )
    lpData = (__int64 *)*lpData;
  result = RegSetValueExW(a1, a2, 0, 1u, (const BYTE *)lpData, cbData);
  v5 = result;
  if ( result )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, result);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = 0;
    v11 = v5;
    v12 = -1;
    v13 = 212;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180012b94  push    rbx
0x180012b96  sub     rsp, 70h
0x180012b9a  cmp     qword ptr [r8+18h], 8
0x180012b9f  mov     eax, [r8+10h]
0x180012ba3  lea     eax, ds:2[rax*2]
0x180012baa  jb      short loc_180012BAF
0x180012bac  mov     r8, [r8]
0x180012baf  mov     [rsp+78h+cbData], eax; cbData
0x180012bb3  mov     r9d, 1; dwType
0x180012bb9  mov     [rsp+78h+lpData], r8; lpData
0x180012bbe  xor     r8d, r8d; Reserved
0x180012bc1  call    cs:__imp_RegSetValueExW
0x180012bc7  mov     ebx, eax
0x180012bc9  test    eax, eax
0x180012bcb  jz      loc_180012C5D
0x180012bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bd8  lea     rax, WPP_GLOBAL_Control
0x180012bdf  cmp     rcx, rax
0x180012be2  jz      short loc_180012C08
0x180012be4  test    byte ptr [rcx+1Ch], 1
0x180012be8  jz      short loc_180012C08
0x180012bea  cmp     byte ptr [rcx+19h], 2
0x180012bee  jb      short loc_180012C08
0x180012bf0  mov     rcx, [rcx+10h]
0x180012bf4  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180012bfb  mov     edx, 14h
0x180012c00  mov     r9d, ebx
0x180012c03  call    WPP_SF_D
0x180012c08  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180012c0f  mov     [rsp+78h+var_40], 0
0x180012c14  mov     [rsp+78h+var_38], rax
0x180012c19  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012c20  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012c27  mov     [rsp+78h+var_30], 0
0x180012c30  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180012c35  mov     [rsp+78h+pExceptionObject], rax
0x180012c3a  mov     [rsp+78h+var_28], 0
0x180012c43  mov     [rsp+78h+var_20], ebx
0x180012c47  mov     [rsp+78h+var_1C], 0FFFFFFFFh
0x180012c4f  mov     [rsp+78h+var_18], 0D4h
0x180012c57  call    _CxxThrowException_0
0x180012c5d  add     rsp, 70h
0x180012c61  pop     rbx
0x180012c62  retn
```
