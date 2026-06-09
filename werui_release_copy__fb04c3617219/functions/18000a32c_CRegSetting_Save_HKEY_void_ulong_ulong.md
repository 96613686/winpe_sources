# CRegSetting::Save(HKEY__ *,void *,ulong,ulong)

- ea: `0x18000a32c`
- end: `0x18000a423`
- name: `?Save@CRegSetting@@QEAAJPEAUHKEY__@@PEAXKK@Z`
- size: `247`
- prototype: `int(CRegSetting *__hidden this, HKEY, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a8f4`

## callees

- `0x180003fe4`
- `0x1800098f8`
- `0x180009a78`
- `0x18000a32c`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18000a3a8`
- `ADVAPI32!RegCreateKeyExW` at `0x18000a3a8`
- `ADVAPI32!RegSetValueExW` at `0x18000a400`
- `ADVAPI32!RegSetValueExW` at `0x18000a400`
- `KERNEL32!GetLastError` at `0x18000a3b2`
- `KERNEL32!GetLastError` at `0x18000a3b2`

## pseudocode

```c
__int64 __fastcall CRegSetting::Save(CRegSetting *this, HKEY a2, const BYTE *a3, DWORD a4)
{
  bool v4; // zf
  unsigned int v7; // ebx
  HKEY *phkResult; // rax
  DWORD LastError; // eax
  __int64 i; // rcx
  DWORD v11; // r9d
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp+20h] BYREF

  dwDisposition = a4;
  hKey = a2;
  v4 = *((_BYTE *)this + 1) == 0;
  hKey = 0;
  dwDisposition = 0;
  if ( v4 )
  {
    v7 = -2145681405;
  }
  else
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( RegCreateKeyExW(HKEY_CURRENT_USER, *((LPCWSTR *)this + 4), 0, 0, 0, 0x20006u, 0, phkResult, &dwDisposition) )
      goto LABEL_4;
    for ( i = 0; (unsigned int)i < 0xB; i = (unsigned int)(i + 1) )
    {
      if ( *((_DWORD *)&CRegSetting::s_typeMapping + 2 * i) == *((_DWORD *)this + 1) )
      {
        v11 = *((_DWORD *)&CRegSetting::s_typeMapping + 2 * i + 1);
        goto LABEL_11;
      }
    }
    v11 = 0;
LABEL_11:
    if ( RegSetValueExW(hKey, *((LPCWSTR *)this + 8), 0, v11, a3, 4u) )
    {
LABEL_4:
      LastError = GetLastError();
      v7 = ERROR_HR_FROM_WIN32(LastError);
    }
    else
    {
      v7 = 0;
    }
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v7;
}

```

## disassembly

```asm
0x18000a32c  mov     rax, rsp
0x18000a32f  mov     [rax+8], rbx
0x18000a333  mov     [rax+20h], r9d
0x18000a337  mov     [rax+10h], rdx
0x18000a33b  push    rdi
0x18000a33c  sub     rsp, 50h
0x18000a340  cmp     byte ptr [rcx+1], 0
0x18000a344  mov     rdi, r8
0x18000a347  mov     rbx, rcx
0x18000a34a  mov     qword ptr [rax+10h], 0
0x18000a352  mov     dword ptr [rax+20h], 0
0x18000a359  jnz     short loc_18000A365
0x18000a35b  mov     ebx, 801B8003h
0x18000a360  jmp     loc_18000A40C
0x18000a365  lea     rcx, [rsp+58h+hKey]
0x18000a36a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000a36f  mov     rdx, [rbx+20h]; lpSubKey
0x18000a373  lea     rcx, [rsp+58h+dwDisposition]
0x18000a378  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x18000a37d  xor     r9d, r9d; lpClass
0x18000a380  mov     [rsp+58h+phkResult], rax; phkResult
0x18000a385  xor     r8d, r8d; Reserved
0x18000a388  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a391  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000a398  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18000a3a0  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000a3a8  call    cs:__imp_RegCreateKeyExW
0x18000a3ae  test    eax, eax
0x18000a3b0  jz      short loc_18000A3C3
0x18000a3b2  call    cs:__imp_GetLastError
0x18000a3b8  mov     ecx, eax; unsigned int
0x18000a3ba  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000a3bf  mov     ebx, eax
0x18000a3c1  jmp     short loc_18000A40C
0x18000a3c3  xor     ecx, ecx
0x18000a3c5  lea     rdx, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x18000a3cc  cmp     ecx, 0Bh
0x18000a3cf  jnb     short loc_18000A3E4
0x18000a3d1  mov     eax, [rbx+4]
0x18000a3d4  cmp     [rdx+rcx*8], eax
0x18000a3d7  jz      short loc_18000A3DD
0x18000a3d9  inc     ecx
0x18000a3db  jmp     short loc_18000A3CC
0x18000a3dd  mov     r9d, [rdx+rcx*8+4]
0x18000a3e2  jmp     short loc_18000A3E7
0x18000a3e4  xor     r9d, r9d; dwType
0x18000a3e7  mov     rdx, [rbx+40h]; lpValueName
0x18000a3eb  xor     r8d, r8d; Reserved
0x18000a3ee  mov     rcx, [rsp+58h+hKey]; hKey
0x18000a3f3  mov     [rsp+58h+samDesired], 4; cbData
0x18000a3fb  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x18000a400  call    cs:__imp_RegSetValueExW
0x18000a406  test    eax, eax
0x18000a408  jnz     short loc_18000A3B2
0x18000a40a  xor     ebx, ebx
0x18000a40c  lea     rcx, [rsp+58h+hKey]
0x18000a411  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18000a416  mov     eax, ebx
0x18000a418  mov     rbx, [rsp+58h+arg_0]
0x18000a41d  add     rsp, 50h
0x18000a421  pop     rdi
0x18000a422  retn
```
