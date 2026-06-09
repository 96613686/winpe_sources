# CRegSetting::Save(HKEY__ *,void *,ulong,ulong)

- ea: `0x1800806a0`
- end: `0x1800807b1`
- name: `?Save@CRegSetting@@QEAAJPEAUHKEY__@@PEAXKK@Z`
- size: `273`
- prototype: `int(CRegSetting *__hidden this, HKEY, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007e000`

## callees

- `0x18001c368`
- `0x18001cb20`
- `0x1800201f0`
- `0x1800806a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080732`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180080722`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180080722`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180080782`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180080782`

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
0x1800806a0  mov     rax, rsp
0x1800806a3  mov     [rax+8], rbx
0x1800806a7  mov     [rax+18h], rsi
0x1800806ab  mov     [rax+10h], rdx
0x1800806af  push    rdi
0x1800806b0  sub     rsp, 50h
0x1800806b4  cmp     byte ptr [rcx+1], 0
0x1800806b8  mov     edi, r9d
0x1800806bb  mov     rsi, r8
0x1800806be  mov     qword ptr [rax+10h], 0
0x1800806c6  mov     rbx, rcx
0x1800806c9  mov     dword ptr [rax+28h], 0
0x1800806d0  jnz     short loc_1800806DC
0x1800806d2  mov     ebx, 801B8003h
0x1800806d7  jmp     loc_180080794
0x1800806dc  lea     rcx, [rsp+58h+hKey]
0x1800806e1  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800806e6  mov     rdx, [rbx+20h]; lpSubKey
0x1800806ea  lea     rcx, [rsp+58h+dwDisposition]
0x1800806f2  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x1800806f7  xor     r9d, r9d; lpClass
0x1800806fa  mov     [rsp+58h+phkResult], rax; phkResult
0x1800806ff  xor     r8d, r8d; Reserved
0x180080702  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008070b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180080712  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18008071a  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180080722  call    cs:__imp_RegCreateKeyExW
0x180080729  nop     dword ptr [rax+rax+00h]
0x18008072e  test    eax, eax
0x180080730  jz      short loc_180080749
0x180080732  call    cs:__imp_GetLastError
0x180080739  nop     dword ptr [rax+rax+00h]
0x18008073e  mov     ecx, eax; unsigned int
0x180080740  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180080745  mov     ebx, eax
0x180080747  jmp     short loc_180080794
0x180080749  xor     ecx, ecx
0x18008074b  lea     rdx, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x180080752  cmp     ecx, 0Bh
0x180080755  jnb     short loc_18008076A
0x180080757  mov     eax, [rbx+4]
0x18008075a  cmp     [rdx+rcx*8], eax
0x18008075d  jz      short loc_180080763
0x18008075f  inc     ecx
0x180080761  jmp     short loc_180080752
0x180080763  mov     r9d, [rdx+rcx*8+4]
0x180080768  jmp     short loc_18008076D
0x18008076a  xor     r9d, r9d; dwType
0x18008076d  mov     rdx, [rbx+40h]; lpValueName
0x180080771  xor     r8d, r8d; Reserved
0x180080774  mov     rcx, [rsp+58h+hKey]; hKey
0x180080779  mov     [rsp+58h+samDesired], edi; cbData
0x18008077d  mov     qword ptr [rsp+58h+dwOptions], rsi; lpData
0x180080782  call    cs:__imp_RegSetValueExW
0x180080789  nop     dword ptr [rax+rax+00h]
0x18008078e  test    eax, eax
0x180080790  jnz     short loc_180080732
0x180080792  xor     ebx, ebx
0x180080794  lea     rcx, [rsp+58h+hKey]
0x180080799  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18008079e  mov     rsi, [rsp+58h+arg_10]
0x1800807a3  mov     eax, ebx
0x1800807a5  mov     rbx, [rsp+58h+arg_0]
0x1800807aa  add     rsp, 50h
0x1800807ae  pop     rdi
0x1800807af  retn
```
