# CRegSetting::Save(HKEY__ *,void *,ulong,ulong)

- ea: `0x14000a098`
- end: `0x14000a1a3`
- name: `?Save@CRegSetting@@QEAAJPEAUHKEY__@@PEAXKK@Z`
- size: `267`
- prototype: `__int64 __fastcall(CRegSetting *this, HKEY, const BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000964c`

## callees

- `0x14000470c`
- `0x14000a098`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a11e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a11e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a190`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000a114`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000a114`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000a17a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000a17a`

## pseudocode

```c
__int64 __fastcall CRegSetting::Save(CRegSetting *this, HKEY a2, const BYTE *a3, DWORD a4)
{
  bool v4; // zf
  HKEY *phkResult; // rax
  signed int LastError; // eax
  signed int v10; // ebx
  __int64 v11; // rax
  DWORD v12; // r9d
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp+20h] BYREF

  dwDisposition = a4;
  hKey = a2;
  v4 = *((_BYTE *)this + 1) == 0;
  hKey = 0;
  dwDisposition = 0;
  if ( v4 )
    return 2149285891LL;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 4), 0, 0, 0, 0x20006u, 0, phkResult, &dwDisposition) )
    goto LABEL_4;
  v11 = 0;
  while ( *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v11) != *((_DWORD *)this + 1) )
  {
    v11 = (unsigned int)(v11 + 1);
    if ( (unsigned int)v11 >= 0xB )
    {
      v12 = 0;
      goto LABEL_14;
    }
  }
  v12 = *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v11 + 1);
LABEL_14:
  if ( RegSetValueExW(hKey, *((LPCWSTR *)this + 8), 0, v12, a3, 4u) )
  {
LABEL_4:
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147467259;
  }
  else
  {
    v10 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000a098  mov     rax, rsp
0x14000a09b  mov     [rax+8], rbx
0x14000a09f  mov     [rax+20h], r9d
0x14000a0a3  mov     [rax+10h], rdx
0x14000a0a7  push    rdi
0x14000a0a8  sub     rsp, 50h
0x14000a0ac  cmp     byte ptr [rcx+1], 0
0x14000a0b0  mov     rdi, r8
0x14000a0b3  mov     rbx, rcx
0x14000a0b6  mov     qword ptr [rax+10h], 0
0x14000a0be  mov     dword ptr [rax+20h], 0
0x14000a0c5  jnz     short loc_14000A0D1
0x14000a0c7  mov     eax, 801B8003h
0x14000a0cc  jmp     loc_14000A198
0x14000a0d1  lea     rcx, [rsp+58h+hKey]
0x14000a0d6  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14000a0db  mov     rdx, [rbx+20h]; lpSubKey
0x14000a0df  lea     rcx, [rsp+58h+dwDisposition]
0x14000a0e4  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x14000a0e9  xor     r9d, r9d; lpClass
0x14000a0ec  mov     [rsp+58h+phkResult], rax; phkResult
0x14000a0f1  xor     r8d, r8d; Reserved
0x14000a0f4  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000a0fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a104  mov     [rsp+58h+samDesired], 20006h; samDesired
0x14000a10c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14000a114  call    cs:__imp_RegCreateKeyExW
0x14000a11a  test    eax, eax
0x14000a11c  jz      short loc_14000A13F
0x14000a11e  call    cs:__imp_GetLastError
0x14000a124  mov     ebx, eax
0x14000a126  test    eax, eax
0x14000a128  jle     short loc_14000A133
0x14000a12a  movzx   ebx, ax
0x14000a12d  or      ebx, 80070000h
0x14000a133  test    ebx, ebx
0x14000a135  mov     eax, 80004005h
0x14000a13a  cmovns  ebx, eax
0x14000a13d  jmp     short loc_14000A186
0x14000a13f  mov     ecx, [rbx+4]
0x14000a142  lea     rdx, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x14000a149  xor     eax, eax
0x14000a14b  cmp     [rdx+rax*8], ecx
0x14000a14e  jz      short loc_14000A15C
0x14000a150  inc     eax
0x14000a152  cmp     eax, 0Bh
0x14000a155  jb      short loc_14000A14B
0x14000a157  xor     r9d, r9d
0x14000a15a  jmp     short loc_14000A161
0x14000a15c  mov     r9d, [rdx+rax*8+4]; dwType
0x14000a161  mov     rdx, [rbx+40h]; lpValueName
0x14000a165  xor     r8d, r8d; Reserved
0x14000a168  mov     rcx, [rsp+58h+hKey]; hKey
0x14000a16d  mov     [rsp+58h+samDesired], 4; cbData
0x14000a175  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x14000a17a  call    cs:__imp_RegSetValueExW
0x14000a180  test    eax, eax
0x14000a182  jnz     short loc_14000A11E
0x14000a184  xor     ebx, ebx
0x14000a186  mov     rcx, [rsp+58h+hKey]; hKey
0x14000a18b  test    rcx, rcx
0x14000a18e  jz      short loc_14000A196
0x14000a190  call    cs:__imp_RegCloseKey
0x14000a196  mov     eax, ebx
0x14000a198  mov     rbx, [rsp+58h+arg_0]
0x14000a19d  add     rsp, 50h
0x14000a1a1  pop     rdi
0x14000a1a2  retn
```
