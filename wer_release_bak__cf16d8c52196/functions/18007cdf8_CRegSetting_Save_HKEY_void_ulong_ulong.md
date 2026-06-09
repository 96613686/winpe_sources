# CRegSetting::Save(HKEY__ *,void *,ulong,ulong)

- ea: `0x18007cdf8`
- end: `0x18007cef6`
- name: `?Save@CRegSetting@@QEAAJPEAUHKEY__@@PEAXKK@Z`
- size: `254`
- prototype: `int(CRegSetting *__hidden this, HKEY, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007a980`

## callees

- `0x18000716c`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x18007cdf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce84`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007ce7a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007ce7a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007cece`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007cece`

## pseudocode

```c
__int64 __fastcall CRegSetting::Save(CRegSetting *this, HKEY a2, const BYTE *a3, DWORD a4, DWORD dwDisposition)
{
  bool v5; // zf
  unsigned int v9; // ebx
  HKEY *phkResult; // rax
  DWORD LastError; // eax
  __int64 i; // rcx
  DWORD v13; // r9d
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = a2;
  v5 = *((_BYTE *)this + 1) == 0;
  hKey = 0;
  dwDisposition = 0;
  if ( v5 )
  {
    v9 = -2145681405;
  }
  else
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 4), 0, 0, 0, 0x20006u, 0, phkResult, &dwDisposition) )
      goto LABEL_4;
    for ( i = 0; (unsigned int)i < 0xB; i = (unsigned int)(i + 1) )
    {
      if ( *((_DWORD *)&CRegSetting::s_typeMapping + 2 * i) == *((_DWORD *)this + 1) )
      {
        v13 = *((_DWORD *)&CRegSetting::s_typeMapping + 2 * i + 1);
        goto LABEL_11;
      }
    }
    v13 = 0;
LABEL_11:
    if ( RegSetValueExW(hKey, *((LPCWSTR *)this + 8), 0, v13, a3, a4) )
    {
LABEL_4:
      LastError = GetLastError();
      v9 = ERROR_HR_FROM_WIN32(LastError);
    }
    else
    {
      v9 = 0;
    }
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x18007cdf8  mov     rax, rsp
0x18007cdfb  mov     [rax+8], rbx
0x18007cdff  mov     [rax+18h], rsi
0x18007ce03  mov     [rax+10h], rdx
0x18007ce07  push    rdi
0x18007ce08  sub     rsp, 50h
0x18007ce0c  cmp     byte ptr [rcx+1], 0
0x18007ce10  mov     edi, r9d
0x18007ce13  mov     rsi, r8
0x18007ce16  mov     qword ptr [rax+10h], 0
0x18007ce1e  mov     rbx, rcx
0x18007ce21  mov     dword ptr [rax+28h], 0
0x18007ce28  jnz     short loc_18007CE34
0x18007ce2a  mov     ebx, 801B8003h
0x18007ce2f  jmp     loc_18007CEDA
0x18007ce34  lea     rcx, [rsp+58h+hKey]
0x18007ce39  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18007ce3e  mov     rdx, [rbx+20h]; lpSubKey
0x18007ce42  lea     rcx, [rsp+58h+dwDisposition]
0x18007ce4a  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x18007ce4f  xor     r9d, r9d; lpClass
0x18007ce52  mov     [rsp+58h+phkResult], rax; phkResult
0x18007ce57  xor     r8d, r8d; Reserved
0x18007ce5a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007ce63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007ce6a  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18007ce72  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18007ce7a  call    cs:__imp_RegCreateKeyExW
0x18007ce80  test    eax, eax
0x18007ce82  jz      short loc_18007CE95
0x18007ce84  call    cs:__imp_GetLastError
0x18007ce8a  mov     ecx, eax; unsigned int
0x18007ce8c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18007ce91  mov     ebx, eax
0x18007ce93  jmp     short loc_18007CEDA
0x18007ce95  xor     ecx, ecx
0x18007ce97  lea     rdx, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x18007ce9e  cmp     ecx, 0Bh
0x18007cea1  jnb     short loc_18007CEB6
0x18007cea3  mov     eax, [rbx+4]
0x18007cea6  cmp     [rdx+rcx*8], eax
0x18007cea9  jz      short loc_18007CEAF
0x18007ceab  inc     ecx
0x18007cead  jmp     short loc_18007CE9E
0x18007ceaf  mov     r9d, [rdx+rcx*8+4]
0x18007ceb4  jmp     short loc_18007CEB9
0x18007ceb6  xor     r9d, r9d; dwType
0x18007ceb9  mov     rdx, [rbx+40h]; lpValueName
0x18007cebd  xor     r8d, r8d; Reserved
0x18007cec0  mov     rcx, [rsp+58h+hKey]; hKey
0x18007cec5  mov     [rsp+58h+samDesired], edi; cbData
0x18007cec9  mov     qword ptr [rsp+58h+dwOptions], rsi; lpData
0x18007cece  call    cs:__imp_RegSetValueExW
0x18007ced4  test    eax, eax
0x18007ced6  jnz     short loc_18007CE84
0x18007ced8  xor     ebx, ebx
0x18007ceda  lea     rcx, [rsp+58h+hKey]
0x18007cedf  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18007cee4  mov     rsi, [rsp+58h+arg_10]
0x18007cee9  mov     eax, ebx
0x18007ceeb  mov     rbx, [rsp+58h+arg_0]
0x18007cef0  add     rsp, 50h
0x18007cef4  pop     rdi
0x18007cef5  retn
```
