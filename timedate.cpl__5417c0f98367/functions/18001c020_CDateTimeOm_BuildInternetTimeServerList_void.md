# CDateTimeOm::_BuildInternetTimeServerList(void)

- ea: `0x18001c020`
- end: `0x18001c1cf`
- name: `?_BuildInternetTimeServerList@CDateTimeOm@@AEAAXXZ`
- size: `431`
- prototype: `void __fastcall(CDateTimeOm *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c300`

## callees

- `0x180001dfc`
- `0x1800089c8`
- `0x18001c020`
- `0x18001c220`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c0b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c0b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1a3`

## pseudocode

```c
void __fastcall CDateTimeOm::_BuildInternetTimeServerList(CDateTimeOm *this)
{
  __int64 v1; // rax
  CDateTimeOm *v3; // rcx
  _QWORD *v4; // rdi
  CDateTimeOm *v5; // rcx
  void *v6; // rbx
  int i; // edi
  void *v8; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-238h]
  unsigned int phkResulta; // [rsp+20h] [rbp-238h]
  HKEY hKey; // [rsp+30h] [rbp-228h] BYREF
  unsigned __int16 v12[256]; // [rsp+40h] [rbp-218h] BYREF

  v1 = *((_QWORD *)this + 61);
  hKey = 0;
  *(_DWORD *)(v1 + 1064) = 0;
  *(_QWORD *)(*((_QWORD *)this + 61) + 1056LL) = operator new(0x210u);
  if ( *(_QWORD *)(*((_QWORD *)this + 61) + 1056LL)
    && !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\DateTime\\Servers",
          0,
          0x20019u,
          &hKey) )
  {
    v4 = *(_QWORD **)(*((_QWORD *)this + 61) + 1056LL);
    if ( CDateTimeOm::_GetInternetTimeServerName(v3, hKey, 0, v12, phkResult) < 0 )
    {
      v6 = v4;
    }
    else
    {
      *(_DWORD *)(*((_QWORD *)this + 61) + 1064LL) = 1;
      **(_DWORD **)(*((_QWORD *)this + 61) + 1056LL) = 0;
      StringCchCopyW((unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 61) + 1056LL) + 4LL), 0x100u, v12);
      v6 = operator new(0x210u);
      v4[65] = v6;
    }
    for ( i = 1; CDateTimeOm::_GetInternetTimeServerName(v5, hKey, i, v12, phkResulta) >= 0; ++i )
    {
      if ( i != 1 )
      {
        v8 = operator new(0x210u);
        *((_QWORD *)v6 + 65) = v8;
        v6 = v8;
      }
      if ( v6 )
      {
        *(_DWORD *)v6 = i;
        StringCchCopyW((unsigned __int16 *)v6 + 2, 0x100u, v12);
        *((_QWORD *)v6 + 65) = 0;
      }
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18001c020  mov     [rsp+arg_8], rbx
0x18001c025  mov     [rsp+arg_10], rdi
0x18001c02a  push    r14
0x18001c02c  sub     rsp, 250h
0x18001c033  mov     rax, cs:__security_cookie
0x18001c03a  xor     rax, rsp
0x18001c03d  mov     [rsp+258h+var_18], rax
0x18001c045  mov     rax, [rcx+1E8h]
0x18001c04c  mov     rbx, rcx
0x18001c04f  mov     [rsp+258h+hKey], 0
0x18001c058  mov     r14d, 210h
0x18001c05e  mov     ecx, r14d; Size
0x18001c061  mov     dword ptr [rax+428h], 0
0x18001c06b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c070  mov     rdx, [rbx+1E8h]
0x18001c077  mov     [rdx+420h], rax
0x18001c07e  mov     rax, [rbx+1E8h]
0x18001c085  cmp     qword ptr [rax+420h], 0
0x18001c08d  jz      loc_18001C1A9
0x18001c093  lea     rax, [rsp+258h+hKey]
0x18001c098  mov     r9d, 20019h; samDesired
0x18001c09e  xor     r8d, r8d; ulOptions
0x18001c0a1  mov     qword ptr [rsp+258h+phkResult], rax; unsigned int
0x18001c0a6  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001c0ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c0b4  call    cs:__imp_RegOpenKeyExW
0x18001c0ba  test    eax, eax
0x18001c0bc  jnz     loc_18001C1A9
0x18001c0c2  mov     rax, [rbx+1E8h]
0x18001c0c9  lea     r9, [rsp+258h+var_218]; unsigned __int16 *
0x18001c0ce  mov     rdx, [rsp+258h+hKey]; HKEY
0x18001c0d3  xor     r8d, r8d; int
0x18001c0d6  mov     rdi, [rax+420h]
0x18001c0dd  call    ?_GetInternetTimeServerName@CDateTimeOm@@AEAAJPEAUHKEY__@@HPEAGK@Z; CDateTimeOm::_GetInternetTimeServerName(HKEY__ *,int,ushort *,ulong)
0x18001c0e2  test    eax, eax
0x18001c0e4  js      short loc_18001C140
0x18001c0e6  mov     rax, [rbx+1E8h]
0x18001c0ed  lea     r8, [rsp+258h+var_218]; unsigned __int16 *
0x18001c0f2  mov     edx, 100h; unsigned __int64
0x18001c0f7  mov     dword ptr [rax+428h], 1
0x18001c101  mov     rax, [rbx+1E8h]
0x18001c108  mov     rcx, [rax+420h]
0x18001c10f  mov     dword ptr [rcx], 0
0x18001c115  mov     rax, [rbx+1E8h]
0x18001c11c  mov     rcx, [rax+420h]
0x18001c123  add     rcx, 4; unsigned __int16 *
0x18001c127  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c12c  mov     ecx, r14d; Size
0x18001c12f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c134  mov     rbx, rax
0x18001c137  mov     [rdi+208h], rax
0x18001c13e  jmp     short loc_18001C143
0x18001c140  mov     rbx, rdi
0x18001c143  mov     edi, 1
0x18001c148  jmp     short loc_18001C188
0x18001c14a  cmp     edi, 1
0x18001c14d  jz      short loc_18001C161
0x18001c14f  mov     rcx, r14; Size
0x18001c152  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c157  mov     [rbx+208h], rax
0x18001c15e  mov     rbx, rax
0x18001c161  test    rbx, rbx
0x18001c164  jz      short loc_18001C186
0x18001c166  lea     rcx, [rbx+4]; unsigned __int16 *
0x18001c16a  mov     [rbx], edi
0x18001c16c  lea     r8, [rsp+258h+var_218]; unsigned __int16 *
0x18001c171  mov     edx, 100h; unsigned __int64
0x18001c176  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c17b  mov     qword ptr [rbx+208h], 0
0x18001c186  inc     edi
0x18001c188  mov     rdx, [rsp+258h+hKey]; HKEY
0x18001c18d  lea     r9, [rsp+258h+var_218]; unsigned __int16 *
0x18001c192  mov     r8d, edi; int
0x18001c195  call    ?_GetInternetTimeServerName@CDateTimeOm@@AEAAJPEAUHKEY__@@HPEAGK@Z; CDateTimeOm::_GetInternetTimeServerName(HKEY__ *,int,ushort *,ulong)
0x18001c19a  test    eax, eax
0x18001c19c  jns     short loc_18001C14A
0x18001c19e  mov     rcx, [rsp+258h+hKey]; hKey
0x18001c1a3  call    cs:__imp_RegCloseKey
0x18001c1a9  mov     rcx, [rsp+258h+var_18]
0x18001c1b1  xor     rcx, rsp; StackCookie
0x18001c1b4  call    __security_check_cookie
0x18001c1b9  lea     r11, [rsp+258h+var_8]
0x18001c1c1  mov     rbx, [r11+18h]
0x18001c1c5  mov     rdi, [r11+20h]
0x18001c1c9  mov     rsp, r11
0x18001c1cc  pop     r14
0x18001c1ce  retn
```
