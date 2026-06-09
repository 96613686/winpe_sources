# SHClearViewStatePropertyBag

- ea: `0x18002c060`
- end: `0x18002c295`
- name: `SHClearViewStatePropertyBag`
- size: `565`
- prototype: `__int64 __fastcall(struct _ITEMIDLIST_ABSOLUTE *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000492c`
- `0x180004e64`
- `0x180005220`
- `0x180007660`
- `0x18000d280`
- `0x180012550`
- `0x18002c060`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c0ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c0ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c17e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c17e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c249`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c252`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c249`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c252`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c1e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c1e4`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18002c1b3`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18002c220`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18002c1b3`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18002c220`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c117`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c117`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18002c23a`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18002c23a`

## pseudocode

```c
__int64 __fastcall SHClearViewStatePropertyBag(struct _ITEMIDLIST_ABSOLUTE *a1, unsigned __int16 *a2, int a3)
{
  unsigned int i; // esi
  HKEY v7; // rdi
  int (__fastcall *v8)(LPVOID, _QWORD, HKEY, const wchar_t *); // rbx
  unsigned int MRUSize; // eax
  DWORD v10; // ebx
  DWORD j; // edx
  unsigned int v13; // [rsp+30h] [rbp-D0h]
  _DWORD v14[2]; // [rsp+40h] [rbp-C0h]
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[20]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszSubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  v14[0] = 33;
  v14[1] = 17;
  for ( i = 0; i < 2; ++i )
  {
    v7 = SHGetShellKeyEx(v14[i], 0, 1, 0x20019u);
    if ( v7 )
    {
      if ( a1 )
      {
        if ( a3 )
        {
          AcquireSRWLockExclusive(&g_srwBags);
          ppv = 0;
          if ( CoCreateInstance(&CLSID_MruPidlList, 0, 1u, &GUID_2fb499a3_cfce_480f_a5f3_2453db7a2b7a, &ppv) >= 0 )
          {
            v8 = *(int (__fastcall **)(LPVOID, _QWORD, HKEY, const wchar_t *))(*(_QWORD *)ppv + 24LL);
            MRUSize = CViewStatePropertyBag::s_GetMRUSize(v7);
            if ( v8(ppv, MRUSize, v7, L"BagMRU") >= 0 )
              (*(void (__fastcall **)(LPVOID, struct _ITEMIDLIST_ABSOLUTE *))(*(_QWORD *)ppv + 48LL))(ppv, a1);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          ReleaseSRWLockExclusive(&g_srwBags);
        }
        if ( CViewStatePropertyBag::s_GetRegKey(a1, a2, 4u, 0, v7, pszSubKey, v13) >= 0 )
          SHDeleteKeyW(v7, pszSubKey);
      }
      else
      {
        phkResult = 0;
        if ( !RegOpenKeyExW(v7, L"Bags", 0, 0x3001Fu, &phkResult) )
        {
          v10 = 0;
          for ( j = 0; !RegEnumKeyW(phkResult, j, Name, 0xFu); j = v10 )
          {
            if ( (int)StringCchPrintfW(pszSubKey, 0x104u, L"%s\\%s", Name, a2) >= 0 )
              SHDeleteKeyW(phkResult, pszSubKey);
            ++v10;
          }
          RegCloseKey(phkResult);
        }
      }
      RegCloseKey(v7);
    }
  }
  FreeViewStatePropertyBagCache();
  return 0;
}

```

## disassembly

```asm
0x18002c060  mov     [rsp-8+arg_10], rbx
0x18002c065  mov     [rsp-8+arg_18], rsi
0x18002c06a  push    rbp
0x18002c06b  push    rdi
0x18002c06c  push    r12
0x18002c06e  push    r14
0x18002c070  push    r15
0x18002c072  lea     rbp, [rsp-1A0h]
0x18002c07a  sub     rsp, 2A0h
0x18002c081  mov     rax, cs:__security_cookie
0x18002c088  xor     rax, rsp
0x18002c08b  mov     [rbp+1C0h+var_30], rax
0x18002c092  mov     r12d, r8d
0x18002c095  mov     [rsp+2C0h+var_280], 21h ; '!'
0x18002c09d  mov     r15, rdx
0x18002c0a0  mov     [rsp+2C0h+var_27C], 11h
0x18002c0a8  mov     r14, rcx
0x18002c0ab  xor     esi, esi
0x18002c0ad  movsxd  rcx, esi
0x18002c0b0  xor     edx, edx
0x18002c0b2  mov     r9d, 20019h
0x18002c0b8  mov     ecx, [rsp+rcx*4+2C0h+var_280]
0x18002c0bc  lea     r8d, [rdx+1]
0x18002c0c0  call    SHGetShellKeyEx
0x18002c0c5  mov     rdi, rax
0x18002c0c8  test    rax, rax
0x18002c0cb  jz      loc_18002C258
0x18002c0d1  test    r14, r14
0x18002c0d4  jz      loc_18002C1BE
0x18002c0da  test    r12d, r12d
0x18002c0dd  jz      loc_18002C184
0x18002c0e3  lea     rcx, ?g_srwBags@@3U_RTL_SRWLOCK@@A; SRWLock
0x18002c0ea  call    cs:__imp_AcquireSRWLockExclusive
0x18002c0f0  xor     edx, edx; pUnkOuter
0x18002c0f2  mov     [rsp+2C0h+var_278], 0
0x18002c0fb  lea     rax, [rsp+2C0h+var_278]
0x18002c100  lea     r9, _GUID_2fb499a3_cfce_480f_a5f3_2453db7a2b7a; riid
0x18002c107  mov     [rsp+2C0h+ppv], rax; ppv
0x18002c10c  lea     rcx, CLSID_MruPidlList; rclsid
0x18002c113  lea     r8d, [rdx+1]; dwClsContext
0x18002c117  call    cs:__imp_CoCreateInstance
0x18002c11d  test    eax, eax
0x18002c11f  js      short loc_18002C177
0x18002c121  mov     rax, [rsp+2C0h+var_278]
0x18002c126  mov     rcx, [rax]
0x18002c129  mov     rbx, [rcx+18h]
0x18002c12d  mov     rcx, rdi; HKEY
0x18002c130  call    ?s_GetMRUSize@CViewStatePropertyBag@@SAKPEAUHKEY__@@@Z; CViewStatePropertyBag::s_GetMRUSize(HKEY__ *)
0x18002c135  mov     rcx, [rsp+2C0h+var_278]
0x18002c13a  lea     r9, aBagmru; "BagMRU"
0x18002c141  mov     edx, eax
0x18002c143  mov     r8, rdi
0x18002c146  mov     rax, rbx
0x18002c149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c14e  test    eax, eax
0x18002c150  js      short loc_18002C166
0x18002c152  mov     rcx, [rsp+2C0h+var_278]
0x18002c157  mov     rdx, r14
0x18002c15a  mov     rax, [rcx]
0x18002c15d  mov     rax, [rax+30h]
0x18002c161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c166  mov     rcx, [rsp+2C0h+var_278]
0x18002c16b  mov     rax, [rcx]
0x18002c16e  mov     rax, [rax+10h]
0x18002c172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c177  lea     rcx, ?g_srwBags@@3U_RTL_SRWLOCK@@A; SRWLock
0x18002c17e  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c184  xor     r9d, r9d; unsigned int
0x18002c187  lea     rax, [rbp+1C0h+pszSubKey]
0x18002c18b  mov     [rsp+2C0h+var_298], rax; unsigned __int16 *
0x18002c190  mov     rdx, r15; unsigned __int16 *
0x18002c193  mov     rcx, r14; struct _ITEMIDLIST_ABSOLUTE *
0x18002c196  mov     [rsp+2C0h+ppv], rdi; HKEY
0x18002c19b  lea     r8d, [r9+4]; unsigned int
0x18002c19f  call    ?s_GetRegKey@CViewStatePropertyBag@@SAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGKKPEAUHKEY__@@PEAGI@Z; CViewStatePropertyBag::s_GetRegKey(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ulong,ulong,HKEY__ *,ushort *,uint)
0x18002c1a4  test    eax, eax
0x18002c1a6  js      loc_18002C24F
0x18002c1ac  lea     rdx, [rbp+1C0h+pszSubKey]; pszSubKey
0x18002c1b0  mov     rcx, rdi; hkey
0x18002c1b3  call    cs:__imp_SHDeleteKeyW
0x18002c1b9  jmp     loc_18002C24F
0x18002c1be  lea     rax, [rsp+2C0h+phkResult]
0x18002c1c3  mov     [rsp+2C0h+phkResult], 0
0x18002c1cc  mov     r9d, 3001Fh; samDesired
0x18002c1d2  mov     [rsp+2C0h+ppv], rax; phkResult
0x18002c1d7  xor     r8d, r8d; ulOptions
0x18002c1da  lea     rdx, aBags; "Bags"
0x18002c1e1  mov     rcx, rdi; hKey
0x18002c1e4  call    cs:__imp_RegOpenKeyExW
0x18002c1ea  test    eax, eax
0x18002c1ec  jnz     short loc_18002C24F
0x18002c1ee  xor     ebx, ebx
0x18002c1f0  xor     edx, edx
0x18002c1f2  jmp     short loc_18002C22A
0x18002c1f4  lea     r9, [rsp+2C0h+Name]
0x18002c1f9  mov     [rsp+2C0h+ppv], r15
0x18002c1fe  lea     r8, aSS_0; "%s\\%s"
0x18002c205  mov     edx, 104h; unsigned __int64
0x18002c20a  lea     rcx, [rbp+1C0h+pszSubKey]; unsigned __int16 *
0x18002c20e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c213  test    eax, eax
0x18002c215  js      short loc_18002C226
0x18002c217  mov     rcx, [rsp+2C0h+phkResult]; hkey
0x18002c21c  lea     rdx, [rbp+1C0h+pszSubKey]; pszSubKey
0x18002c220  call    cs:__imp_SHDeleteKeyW
0x18002c226  inc     ebx
0x18002c228  mov     edx, ebx; dwIndex
0x18002c22a  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x18002c22f  lea     r8, [rsp+2C0h+Name]; lpName
0x18002c234  mov     r9d, 0Fh; cchName
0x18002c23a  call    cs:__imp_RegEnumKeyW
0x18002c240  test    eax, eax
0x18002c242  jz      short loc_18002C1F4
0x18002c244  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x18002c249  call    cs:__imp_RegCloseKey
0x18002c24f  mov     rcx, rdi; hKey
0x18002c252  call    cs:__imp_RegCloseKey
0x18002c258  inc     esi
0x18002c25a  cmp     esi, 2
0x18002c25d  jb      loc_18002C0AD
0x18002c263  call    ?FreeViewStatePropertyBagCache@@YAXXZ; FreeViewStatePropertyBagCache(void)
0x18002c268  xor     eax, eax
0x18002c26a  mov     rcx, [rbp+1C0h+var_30]
0x18002c271  xor     rcx, rsp; StackCookie
0x18002c274  call    __security_check_cookie
0x18002c279  lea     r11, [rsp+2C0h+var_20]
0x18002c281  mov     rbx, [r11+40h]
0x18002c285  mov     rsi, [r11+48h]
0x18002c289  mov     rsp, r11
0x18002c28c  pop     r15
0x18002c28e  pop     r14
0x18002c290  pop     r12
0x18002c292  pop     rdi
0x18002c293  pop     rbp
0x18002c294  retn
```
