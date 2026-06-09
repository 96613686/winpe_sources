# CViewStatePropertyBag::_PruneMRUTree(void)

- ea: `0x180029ea4`
- end: `0x180029fa7`
- name: `?_PruneMRUTree@CViewStatePropertyBag@@AEAAXXZ`
- size: `259`
- prototype: `void __fastcall(CViewStatePropertyBag *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800046bc`

## callees

- `0x180004a38`
- `0x18000d280`
- `0x180012550`
- `0x180029ea4`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029ee6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029ee6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029f7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029f7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029f13`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029f13`

## pseudocode

```c
void __fastcall CViewStatePropertyBag::_PruneMRUTree(CViewStatePropertyBag *this)
{
  HKEY ViewStateKey; // rdi
  int (__fastcall *v3)(LPVOID, _QWORD, HKEY, const wchar_t *); // rbx
  unsigned int MRUSize; // eax
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF

  ViewStateKey = CViewStatePropertyBag::_GetViewStateKey(this, *((_DWORD *)this + 14), 0x10u);
  if ( ViewStateKey )
  {
    AcquireSRWLockExclusive(&g_srwBags);
    ppv = 0;
    if ( CoCreateInstance(&CLSID_MruPidlList, 0, 1u, &GUID_2fb499a3_cfce_480f_a5f3_2453db7a2b7a, &ppv) >= 0 )
    {
      v3 = *(int (__fastcall **)(LPVOID, _QWORD, HKEY, const wchar_t *))(*(_QWORD *)ppv + 24LL);
      MRUSize = CViewStatePropertyBag::s_GetMRUSize(ViewStateKey);
      if ( v3(ppv, MRUSize, ViewStateKey, L"BagMRU") >= 0 )
        (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 48LL))(ppv, *((_QWORD *)this + 4));
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    ReleaseSRWLockExclusive(&g_srwBags);
    RegCloseKey(ViewStateKey);
  }
}

```

## disassembly

```asm
0x180029ea4  mov     [rsp+arg_8], rbx
0x180029ea9  mov     [rsp+arg_10], rsi
0x180029eae  push    rdi
0x180029eaf  sub     rsp, 40h
0x180029eb3  mov     rax, cs:__security_cookie
0x180029eba  xor     rax, rsp
0x180029ebd  mov     [rsp+48h+var_10], rax
0x180029ec2  mov     edx, [rcx+38h]; unsigned int
0x180029ec5  mov     r8d, 10h; unsigned int
0x180029ecb  mov     rsi, rcx
0x180029ece  call    ?_GetViewStateKey@CViewStatePropertyBag@@AEAAPEAUHKEY__@@KK@Z; CViewStatePropertyBag::_GetViewStateKey(ulong,ulong)
0x180029ed3  mov     rdi, rax
0x180029ed6  test    rax, rax
0x180029ed9  jz      loc_180029F8A
0x180029edf  lea     rcx, ?g_srwBags@@3U_RTL_SRWLOCK@@A; SRWLock
0x180029ee6  call    cs:__imp_AcquireSRWLockExclusive
0x180029eec  xor     edx, edx; pUnkOuter
0x180029eee  mov     [rsp+48h+var_18], 0
0x180029ef7  lea     rax, [rsp+48h+var_18]
0x180029efc  lea     r9, _GUID_2fb499a3_cfce_480f_a5f3_2453db7a2b7a; riid
0x180029f03  mov     [rsp+48h+ppv], rax; ppv
0x180029f08  lea     rcx, CLSID_MruPidlList; rclsid
0x180029f0f  lea     r8d, [rdx+1]; dwClsContext
0x180029f13  call    cs:__imp_CoCreateInstance
0x180029f19  test    eax, eax
0x180029f1b  js      short loc_180029F74
0x180029f1d  mov     rax, [rsp+48h+var_18]
0x180029f22  mov     rcx, [rax]
0x180029f25  mov     rbx, [rcx+18h]
0x180029f29  mov     rcx, rdi; HKEY
0x180029f2c  call    ?s_GetMRUSize@CViewStatePropertyBag@@SAKPEAUHKEY__@@@Z; CViewStatePropertyBag::s_GetMRUSize(HKEY__ *)
0x180029f31  mov     rcx, [rsp+48h+var_18]
0x180029f36  lea     r9, aBagmru; "BagMRU"
0x180029f3d  mov     edx, eax
0x180029f3f  mov     r8, rdi
0x180029f42  mov     rax, rbx
0x180029f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f4a  test    eax, eax
0x180029f4c  js      short loc_180029F63
0x180029f4e  mov     rcx, [rsp+48h+var_18]
0x180029f53  mov     rdx, [rsi+20h]
0x180029f57  mov     rax, [rcx]
0x180029f5a  mov     rax, [rax+30h]
0x180029f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f63  mov     rcx, [rsp+48h+var_18]
0x180029f68  mov     rax, [rcx]
0x180029f6b  mov     rax, [rax+10h]
0x180029f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f74  lea     rcx, ?g_srwBags@@3U_RTL_SRWLOCK@@A; SRWLock
0x180029f7b  call    cs:__imp_ReleaseSRWLockExclusive
0x180029f81  mov     rcx, rdi; hKey
0x180029f84  call    cs:__imp_RegCloseKey
0x180029f8a  mov     rcx, [rsp+48h+var_10]
0x180029f8f  xor     rcx, rsp; StackCookie
0x180029f92  call    __security_check_cookie
0x180029f97  mov     rbx, [rsp+48h+arg_8]
0x180029f9c  mov     rsi, [rsp+48h+arg_10]
0x180029fa1  add     rsp, 40h
0x180029fa5  pop     rdi
0x180029fa6  retn
```
