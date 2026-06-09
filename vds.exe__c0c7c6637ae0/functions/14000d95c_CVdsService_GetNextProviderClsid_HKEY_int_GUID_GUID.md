# CVdsService::GetNextProviderClsid(HKEY__ *,int,_GUID *,_GUID *)

- ea: `0x14000d95c`
- end: `0x14000dbb9`
- name: `?GetNextProviderClsid@CVdsService@@CAKPEAUHKEY__@@HPEAU_GUID@@1@Z`
- size: `605`
- prototype: `unsigned int __fastcall(HKEY hKey, DWORD dwIndex, LPCLSID pclsid, LPCLSID)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000a070`

## callees

- `0x14000d95c`
- `0x140013298`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000da38`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000daf0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000da38`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000daf0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000d9ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000d9ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000db89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000db89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000dace`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000dace`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000da83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000da83`
- `vdsutil!VdsTraceEx` at `0x14000da25`
- `vdsutil!VdsTraceEx` at `0x14000da53`
- `vdsutil!VdsTraceEx` at `0x14000da9e`
- `vdsutil!VdsTraceEx` at `0x14000db0b`
- `vdsutil!VdsTraceEx` at `0x14000da25`
- `vdsutil!VdsTraceEx` at `0x14000da53`
- `vdsutil!VdsTraceEx` at `0x14000da9e`
- `vdsutil!VdsTraceEx` at `0x14000db0b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000d9a2`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000d9a2`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000db95`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000db95`

## string_xrefs

- `0x14000d98d`: `CVdsService::GetNextProviderClsid()`
- `0x14000da19`: `CVdsService::GetNextProviderClsid: 1, %ld`
- `0x14000da47`: `CVdsService::GetNextProviderClsid: 2, %lX`
- `0x14000da8f`: `CVdsService::GetNextProviderClsid: 3, %ld`
- `0x14000dada`: `CVdsService::GetNextProviderClsid: 4, %ld`
- `0x14000daff`: `CVdsService::GetNextProviderClsid: 5, %ld`
- `0x14000dac2`: `Clsid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::GetNextProviderClsid(HKEY hKey, DWORD dwIndex, LPCLSID pclsid, LPCLSID a4)
{
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  HRESULT v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // ecx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  HRESULT v16; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[24]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[64]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR Data[63]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v25; // [rsp+16Eh] [rbp+6Eh]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v22, 0x5Eu, "CVdsService::GetNextProviderClsid()");
  ftLastWriteTime = 0;
  cchName = 64;
  phkResult = 0;
  cbData = 128;
  v8 = RegEnumKeyExW(hKey, dwIndex, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
  v9 = v8;
  if ( !v8 )
  {
    v10 = CLSIDFromString(Name, a4);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v14 = RegOpenKeyExW(hKey, Name, 0, 0x2000000u, &phkResult);
      v9 = v14;
      if ( v14 )
      {
        VdsTraceEx(94, 0, "CVdsService::GetNextProviderClsid: 3, %ld", v14);
        goto LABEL_14;
      }
      v15 = RegQueryValueExW(phkResult, g_wszVdsProviderClassId, 0, 0, (LPBYTE)Data, &cbData);
      v9 = v15;
      if ( v15 )
      {
        VdsTraceEx(94, 0, "CVdsService::GetNextProviderClsid: 4, %ld", v15);
        goto LABEL_14;
      }
      v25 = 0;
      v16 = CLSIDFromString(Data, pclsid);
      v11 = v16;
      if ( v16 >= 0 )
        goto LABEL_16;
      VdsTraceEx(94, 0, "CVdsService::GetNextProviderClsid: 5, %ld", v16);
      v12 = -1040187379;
      v13 = 33554440;
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsService::GetNextProviderClsid: 2, %lX", v10);
      v12 = -1040187380;
      v13 = 33554439;
    }
    VdsLogError(v12, 0, 0, v11, v13, Name, 0);
    v9 = (unsigned __int16)v11;
    if ( !(_WORD)v11 )
      goto LABEL_16;
LABEL_14:
    if ( v9 == 259 )
      goto LABEL_16;
    goto LABEL_15;
  }
  if ( v8 == 259 )
    goto LABEL_14;
  VdsTraceEx(94, 0, "CVdsService::GetNextProviderClsid: 1, %ld", v8);
LABEL_15:
  VdsLogError(0xC200000E, 0, 0, v9, 0x2000009u, Name, 0);
LABEL_16:
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
  return v9;
}

```

## disassembly

```asm
0x14000d95c  push    rbp
0x14000d95e  push    rbx
0x14000d95f  push    rsi
0x14000d960  push    rdi
0x14000d961  push    r12
0x14000d963  push    r14
0x14000d965  lea     rbp, [rsp-88h]
0x14000d96d  sub     rsp, 188h
0x14000d974  mov     rax, cs:__security_cookie
0x14000d97b  xor     rax, rsp
0x14000d97e  mov     [rbp+0B0h+var_40], rax
0x14000d982  mov     rdi, r9
0x14000d985  mov     r14, r8
0x14000d988  mov     ebx, edx
0x14000d98a  mov     rsi, rcx
0x14000d98d  lea     r8, aCvdsserviceGet_14; "CVdsService::GetNextProviderClsid()"
0x14000d994  mov     r12d, 5Eh ; '^'
0x14000d99a  mov     edx, r12d
0x14000d99d  lea     rcx, [rsp+1B0h+var_158]
0x14000d9a2  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000d9a8  nop
0x14000d9a9  mov     qword ptr [rsp+1B0h+ftLastWriteTime.dwLowDateTime], 0
0x14000d9b2  mov     [rsp+1B0h+cchName], 40h ; '@'
0x14000d9ba  mov     [rsp+1B0h+phkResult], 0
0x14000d9c3  mov     [rsp+1B0h+cbData], 80h
0x14000d9cb  lea     rax, [rsp+1B0h+ftLastWriteTime]
0x14000d9d0  mov     [rsp+1B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14000d9d5  mov     [rsp+1B0h+lpcchClass], 0; lpcchClass
0x14000d9de  mov     [rsp+1B0h+lpClass], 0; lpClass
0x14000d9e7  mov     [rsp+1B0h+lpReserved], 0; lpReserved
0x14000d9f0  lea     r9, [rsp+1B0h+cchName]; lpcchName
0x14000d9f5  lea     r8, [rsp+1B0h+Name]; lpName
0x14000d9fa  mov     edx, ebx; dwIndex
0x14000d9fc  mov     rcx, rsi; hKey
0x14000d9ff  call    cs:__imp_RegEnumKeyExW
0x14000da05  mov     ebx, eax
0x14000da07  test    eax, eax
0x14000da09  jz      short loc_14000DA30
0x14000da0b  cmp     eax, 103h
0x14000da10  jz      loc_14000DB45
0x14000da16  mov     r9d, eax
0x14000da19  lea     r8, aCvdsserviceGet_98; "CVdsService::GetNextProviderClsid: 1, %"...
0x14000da20  xor     edx, edx
0x14000da22  mov     ecx, r12d
0x14000da25  call    cs:__imp_VdsTraceEx
0x14000da2b  jmp     loc_14000DB4D
0x14000da30  mov     rdx, rdi; pclsid
0x14000da33  lea     rcx, [rsp+1B0h+Name]; lpsz
0x14000da38  call    cs:__imp_CLSIDFromString
0x14000da3e  mov     edi, eax
0x14000da40  test    eax, eax
0x14000da42  jns     short loc_14000DA68
0x14000da44  mov     r9d, eax
0x14000da47  lea     r8, aCvdsserviceGet_114; "CVdsService::GetNextProviderClsid: 2, %"...
0x14000da4e  xor     edx, edx
0x14000da50  mov     ecx, r12d
0x14000da53  call    cs:__imp_VdsTraceEx
0x14000da59  mov     ecx, 0C200000Ch
0x14000da5e  mov     eax, 2000007h
0x14000da63  jmp     loc_14000DB1B
0x14000da68  lea     rax, [rsp+1B0h+phkResult]
0x14000da6d  mov     [rsp+1B0h+lpReserved], rax; phkResult
0x14000da72  mov     r9d, 2000000h; samDesired
0x14000da78  xor     r8d, r8d; ulOptions
0x14000da7b  lea     rdx, [rsp+1B0h+Name]; lpSubKey
0x14000da80  mov     rcx, rsi; hKey
0x14000da83  call    cs:__imp_RegOpenKeyExW
0x14000da89  mov     ebx, eax
0x14000da8b  test    eax, eax
0x14000da8d  jz      short loc_14000DAA9
0x14000da8f  lea     r8, aCvdsserviceGet_93; "CVdsService::GetNextProviderClsid: 3, %"...
0x14000da96  mov     r9d, eax
0x14000da99  xor     edx, edx
0x14000da9b  mov     ecx, r12d
0x14000da9e  call    cs:__imp_VdsTraceEx
0x14000daa4  jmp     loc_14000DB45
0x14000daa9  lea     rax, [rsp+1B0h+cbData]
0x14000daae  mov     [rsp+1B0h+lpClass], rax; lpcbData
0x14000dab3  lea     rax, [rbp+0B0h+Data]
0x14000dab7  mov     [rsp+1B0h+lpReserved], rax; lpData
0x14000dabc  xor     r9d, r9d; lpType
0x14000dabf  xor     r8d, r8d; lpReserved
0x14000dac2  lea     rdx, ?g_wszVdsProviderClassId@@3PAGA; "Clsid"
0x14000dac9  mov     rcx, [rsp+1B0h+phkResult]; hKey
0x14000dace  call    cs:__imp_RegQueryValueExW
0x14000dad4  mov     ebx, eax
0x14000dad6  test    eax, eax
0x14000dad8  jz      short loc_14000DAE3
0x14000dada  lea     r8, aCvdsserviceGet_61; "CVdsService::GetNextProviderClsid: 4, %"...
0x14000dae1  jmp     short loc_14000DA96
0x14000dae3  xor     eax, eax
0x14000dae5  mov     [rbp+0B0h+var_42], ax
0x14000dae9  mov     rdx, r14; pclsid
0x14000daec  lea     rcx, [rbp+0B0h+Data]; lpsz
0x14000daf0  call    cs:__imp_CLSIDFromString
0x14000daf6  mov     edi, eax
0x14000daf8  test    eax, eax
0x14000dafa  jns     short loc_14000DB7A
0x14000dafc  mov     r9d, eax
0x14000daff  lea     r8, aCvdsserviceGet_120; "CVdsService::GetNextProviderClsid: 5, %"...
0x14000db06  xor     edx, edx
0x14000db08  mov     ecx, r12d
0x14000db0b  call    cs:__imp_VdsTraceEx
0x14000db11  mov     ecx, 0C200000Dh; unsigned int
0x14000db16  mov     eax, 2000008h
0x14000db1b  xor     edx, edx; unsigned int
0x14000db1d  xor     r8d, r8d; void *
0x14000db20  xor     r11d, r11d
0x14000db23  lea     r10, [rsp+1B0h+Name]
0x14000db28  mov     r9d, edi; unsigned int
0x14000db2b  mov     [rsp+1B0h+lpcchClass], r11
0x14000db30  mov     [rsp+1B0h+lpClass], r10; unsigned __int16 *
0x14000db35  mov     dword ptr [rsp+1B0h+lpReserved], eax; unsigned int
0x14000db39  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000db3e  movzx   ebx, di
0x14000db41  test    ebx, ebx
0x14000db43  jz      short loc_14000DB7A
0x14000db45  cmp     ebx, 103h
0x14000db4b  jz      short loc_14000DB7A
0x14000db4d  mov     [rsp+1B0h+lpcchClass], 0
0x14000db56  lea     rax, [rsp+1B0h+Name]
0x14000db5b  mov     [rsp+1B0h+lpClass], rax; unsigned __int16 *
0x14000db60  mov     dword ptr [rsp+1B0h+lpReserved], 2000009h; unsigned int
0x14000db68  mov     r9d, ebx; unsigned int
0x14000db6b  xor     r8d, r8d; void *
0x14000db6e  xor     edx, edx; unsigned int
0x14000db70  mov     ecx, 0C200000Eh; unsigned int
0x14000db75  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14000db7a  mov     rcx, [rsp+1B0h+phkResult]; hKey
0x14000db7f  lea     rax, [rcx-1]
0x14000db83  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000db87  ja      short loc_14000DB90
0x14000db89  call    cs:__imp_RegCloseKey
0x14000db8f  nop
0x14000db90  lea     rcx, [rsp+1B0h+var_158]
0x14000db95  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000db9b  mov     eax, ebx
0x14000db9d  mov     rcx, [rbp+0B0h+var_40]
0x14000dba1  xor     rcx, rsp; StackCookie
0x14000dba4  call    __security_check_cookie
0x14000dba9  add     rsp, 188h
0x14000dbb0  pop     r14
0x14000dbb2  pop     r12
0x14000dbb4  pop     rdi
0x14000dbb5  pop     rsi
0x14000dbb6  pop     rbx
0x14000dbb7  pop     rbp
0x14000dbb8  retn
```
