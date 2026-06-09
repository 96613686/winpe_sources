# CThemeManager::_Initialize(void)

- ea: `0x18003c0f8`
- end: `0x18003c1ec`
- name: `?_Initialize@CThemeManager@@IEAAJXZ`
- size: `244`
- prototype: `__int64 __fastcall(IUnknown *punkSite)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b2ac`

## callees

- `0x180003690`
- `0x18003c0f8`
- `0x18003c21c`
- `0x18006d010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x18003c15d`
- `SHCORE!IUnknown_SetSite` at `0x18003c1a5`
- `SHCORE!IUnknown_SetSite` at `0x18003c1da`
- `SHCORE!IUnknown_SetSite` at `0x18003c15d`
- `SHCORE!IUnknown_SetSite` at `0x18003c1a5`
- `SHCORE!IUnknown_SetSite` at `0x18003c1da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c193`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c1c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c193`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c1c8`

## pseudocode

```c
__int64 __fastcall CThemeManager::_Initialize(IUnknown *punkSite)
{
  HRESULT Instance; // ebx
  CBaseAppearancePage *v3; // rax
  CBaseAppearancePage *v4; // rax
  CBaseAppearancePage *v5; // rsi

  Instance = -2147024882;
  v3 = (CBaseAppearancePage *)operator new(0x670u);
  if ( v3 )
  {
    v4 = CBaseAppearancePage::CBaseAppearancePage(v3);
    v5 = v4;
    if ( v4 )
    {
      Instance = (**((__int64 (__fastcall ***)(__int64, GUID *, IUnknown *))v4 + 9))(
                   (__int64)v4 + 72,
                   &GUID_b34e525b_9eb4_433b_8e0f_019c4f21d7e7,
                   punkSite + 8);
      if ( Instance >= 0 )
        IUnknown_SetSite((IUnknown *)punkSite[8].lpVtbl, punkSite);
      (*(void (__fastcall **)(CBaseAppearancePage *))(*(_QWORD *)v5 + 16LL))(v5);
      if ( Instance >= 0 )
      {
        Instance = CoCreateInstance(
                     &CLSID_ScreenSaverPage,
                     0,
                     1u,
                     &GUID_b34e525b_9eb4_433b_8e0f_019c4f21d7e7,
                     (LPVOID *)&punkSite[10].lpVtbl);
        if ( Instance >= 0 )
        {
          IUnknown_SetSite((IUnknown *)punkSite[10].lpVtbl, punkSite);
          Instance = CoCreateInstance(
                       &CLSID_CDeskHtmlProp,
                       0,
                       1u,
                       &GUID_b34e525b_9eb4_433b_8e0f_019c4f21d7e7,
                       (LPVOID *)&punkSite[11].lpVtbl);
          if ( Instance >= 0 )
            IUnknown_SetSite((IUnknown *)punkSite[11].lpVtbl, punkSite);
        }
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003c0f8  push    rbx
0x18003c0fa  push    rsi
0x18003c0fb  push    rdi
0x18003c0fc  push    r14
0x18003c0fe  sub     rsp, 38h
0x18003c102  mov     rdi, rcx
0x18003c105  mov     ebx, 8007000Eh
0x18003c10a  mov     ecx, 670h; unsigned __int64
0x18003c10f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c114  mov     [rsp+58h+arg_8], rax
0x18003c119  test    rax, rax
0x18003c11c  jz      loc_18003C1E0
0x18003c122  mov     rcx, rax; this
0x18003c125  call    ??0CBaseAppearancePage@@QEAA@XZ; CBaseAppearancePage::CBaseAppearancePage(void)
0x18003c12a  mov     rsi, rax
0x18003c12d  test    rax, rax
0x18003c130  jz      loc_18003C1E0
0x18003c136  lea     rcx, [rax+48h]
0x18003c13a  mov     rax, [rcx]
0x18003c13d  lea     r8, [rdi+40h]
0x18003c141  lea     rdx, _GUID_b34e525b_9eb4_433b_8e0f_019c4f21d7e7
0x18003c148  mov     rax, [rax]
0x18003c14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c150  mov     ebx, eax
0x18003c152  test    eax, eax
0x18003c154  js      short loc_18003C163
0x18003c156  mov     rcx, [rdi+40h]; punk
0x18003c15a  mov     rdx, rdi; punkSite
0x18003c15d  call    cs:__imp_IUnknown_SetSite
0x18003c163  mov     rax, [rsi]
0x18003c166  mov     rcx, rsi
0x18003c169  mov     rax, [rax+10h]
0x18003c16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c172  test    ebx, ebx
0x18003c174  js      short loc_18003C1E0
0x18003c176  xor     edx, edx; pUnkOuter
0x18003c178  lea     rsi, [rdi+50h]
0x18003c17c  lea     r9, _GUID_b34e525b_9eb4_433b_8e0f_019c4f21d7e7; riid
0x18003c183  mov     [rsp+58h+ppv], rsi; ppv
0x18003c188  lea     rcx, CLSID_ScreenSaverPage; rclsid
0x18003c18f  lea     r8d, [rdx+1]; dwClsContext
0x18003c193  call    cs:__imp_CoCreateInstance
0x18003c199  mov     ebx, eax
0x18003c19b  test    eax, eax
0x18003c19d  js      short loc_18003C1E0
0x18003c19f  mov     rcx, [rsi]; punk
0x18003c1a2  mov     rdx, rdi; punkSite
0x18003c1a5  call    cs:__imp_IUnknown_SetSite
0x18003c1ab  xor     edx, edx; pUnkOuter
0x18003c1ad  lea     rsi, [rdi+58h]
0x18003c1b1  lea     r9, _GUID_b34e525b_9eb4_433b_8e0f_019c4f21d7e7; riid
0x18003c1b8  mov     [rsp+58h+ppv], rsi; ppv
0x18003c1bd  lea     rcx, CLSID_CDeskHtmlProp; rclsid
0x18003c1c4  lea     r8d, [rdx+1]; dwClsContext
0x18003c1c8  call    cs:__imp_CoCreateInstance
0x18003c1ce  mov     ebx, eax
0x18003c1d0  test    eax, eax
0x18003c1d2  js      short loc_18003C1E0
0x18003c1d4  mov     rcx, [rsi]; punk
0x18003c1d7  mov     rdx, rdi; punkSite
0x18003c1da  call    cs:__imp_IUnknown_SetSite
0x18003c1e0  mov     eax, ebx
0x18003c1e2  add     rsp, 38h
0x18003c1e6  pop     r14
0x18003c1e8  pop     rdi
0x18003c1e9  pop     rsi
0x18003c1ea  pop     rbx
0x18003c1eb  retn
```
