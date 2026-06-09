# CMulticastHandler::InitializeStatic(int,int)

- ea: `0x1800175ec`
- end: `0x180017807`
- name: `?InitializeStatic@CMulticastHandler@@AEAAKHH@Z`
- size: `539`
- prototype: `unsigned int __fastcall(CMulticastHandler *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800174b8`

## callees

- `0x1800175ec`
- `0x18001784c`
- `0x18001b30c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180017636`
- `ADVAPI32!RegOpenKeyExW` at `0x180017636`
- `ADVAPI32!RegCloseKey` at `0x1800177e3`
- `ADVAPI32!RegCloseKey` at `0x1800177e3`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800176f9`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180017741`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800177af`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800177c9`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800176f9`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180017741`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800177af`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800177c9`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180017670`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x1800176a2`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180017719`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180017761`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180017670`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x1800176a2`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180017719`
- `WdsServerCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180017761`

## string_xrefs

- `0x180017618`: `System\CurrentControlSet\Services\WDSServer\Parameters`

## pseudocode

```c
__int64 __fastcall CMulticastHandler::InitializeStatic(CMulticastHandler *this, int a2)
{
  unsigned int ValueSz; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int16 *v20; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int16 *v22; // [rsp+68h] [rbp+28h] BYREF

  v22 = 0;
  v20 = 0;
  hKey = 0;
  ValueSz = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
              0,
              0x20119u,
              &hKey);
  if ( !(unsigned int)ElValidateWin32_9(ValueSz, v5, v6, 154) )
  {
    if ( !a2
      || (ValueSz = CRegKey::GetValueSz((CRegKey *)&hKey, L"McStartAddr", &v22),
          !(unsigned int)ElValidateWin32_9(ValueSz, v7, v8, 163))
      && (ValueSz = CRegKey::GetValueSz((CRegKey *)&hKey, L"McEndAddr", &v20),
          !(unsigned int)ElValidateWin32_9(ValueSz, v9, v10, 167))
      && (ValueSz = CStaticMulticastLeaseHandler::Initialize((LPCRITICAL_SECTION)((char *)this + 8), 2, v22, v20),
          !(unsigned int)ElValidateWin32_9(ValueSz, v11, v12, 177)) )
    {
      if ( v22 )
      {
        WdsPrivateHpFree(v22);
        v22 = 0;
      }
      ValueSz = CRegKey::GetValueSz((CRegKey *)&hKey, L"McStartAddr6", &v22);
      if ( !(unsigned int)ElValidateWin32_9(ValueSz, v13, v14, 188) )
      {
        if ( v20 )
        {
          WdsPrivateHpFree(v20);
          v20 = 0;
        }
        ValueSz = CRegKey::GetValueSz((CRegKey *)&hKey, L"McEndAddr6", &v20);
        if ( !(unsigned int)ElValidateWin32_9(ValueSz, v15, v16, 193) )
        {
          ValueSz = CStaticMulticastLeaseHandler::Initialize((LPCRITICAL_SECTION)((char *)this + 128), 23, v22, v20);
          ElValidateWin32_9(ValueSz, v17, v18, 200);
        }
      }
    }
  }
  if ( v22 )
  {
    WdsPrivateHpFree(v22);
    v22 = 0;
  }
  if ( v20 )
  {
    WdsPrivateHpFree(v20);
    v20 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return ValueSz;
}

```

## disassembly

```asm
0x1800175ec  mov     r11, rsp
0x1800175ef  mov     [r11+8], rbx
0x1800175f3  mov     [r11+10h], rsi
0x1800175f7  mov     [r11+18h], rdi
0x1800175fb  push    rbp
0x1800175fc  mov     rbp, rsp
0x1800175ff  sub     rsp, 40h
0x180017603  and     [rbp+arg_18], 0
0x180017608  lea     rax, [rbp+hKey]
0x18001760c  and     [rbp+var_10], 0
0x180017611  mov     edi, edx
0x180017613  and     [rbp+hKey], 0
0x180017618  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18001761f  mov     rsi, rcx
0x180017622  mov     [r11-28h], rax
0x180017626  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001762d  mov     r9d, 20119h; samDesired
0x180017633  xor     r8d, r8d; ulOptions
0x180017636  call    cs:__imp_RegOpenKeyExW
0x18001763d  nop     dword ptr [rax+rax+00h]
0x180017642  mov     ecx, eax
0x180017644  mov     r9d, 9Ah
0x18001764a  mov     ebx, eax
0x18001764c  call    ElValidateWin32_9
0x180017651  test    eax, eax
0x180017653  jnz     loc_1800177A6
0x180017659  test    edi, edi
0x18001765b  jz      loc_1800176F0
0x180017661  lea     r8, [rbp+arg_18]
0x180017665  lea     rdx, aMcstartaddr; "McStartAddr"
0x18001766c  lea     rcx, [rbp+hKey]
0x180017670  call    cs:__imp_?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x180017677  nop     dword ptr [rax+rax+00h]
0x18001767c  mov     ecx, eax
0x18001767e  mov     r9d, 0A3h
0x180017684  mov     ebx, eax
0x180017686  call    ElValidateWin32_9
0x18001768b  test    eax, eax
0x18001768d  jnz     loc_1800177A6
0x180017693  lea     r8, [rbp+var_10]
0x180017697  lea     rdx, aMcendaddr; "McEndAddr"
0x18001769e  lea     rcx, [rbp+hKey]
0x1800176a2  call    cs:__imp_?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x1800176a9  nop     dword ptr [rax+rax+00h]
0x1800176ae  mov     ecx, eax
0x1800176b0  mov     r9d, 0A7h
0x1800176b6  mov     ebx, eax
0x1800176b8  call    ElValidateWin32_9
0x1800176bd  test    eax, eax
0x1800176bf  jnz     loc_1800177A6
0x1800176c5  mov     r9, [rbp+var_10]; unsigned __int16 *
0x1800176c9  lea     rcx, [rsi+8]; lpCriticalSection
0x1800176cd  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x1800176d1  lea     edx, [rax+2]; int
0x1800176d4  call    ?Initialize@CStaticMulticastLeaseHandler@@QEAAKHPEBG0@Z; CStaticMulticastLeaseHandler::Initialize(int,ushort const *,ushort const *)
0x1800176d9  mov     r9d, 0B1h
0x1800176df  mov     ecx, eax
0x1800176e1  mov     ebx, eax
0x1800176e3  call    ElValidateWin32_9
0x1800176e8  test    eax, eax
0x1800176ea  jnz     loc_1800177A6
0x1800176f0  mov     rcx, [rbp+arg_18]
0x1800176f4  test    rcx, rcx
0x1800176f7  jz      short loc_18001770A
0x1800176f9  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180017700  nop     dword ptr [rax+rax+00h]
0x180017705  and     [rbp+arg_18], 0
0x18001770a  lea     r8, [rbp+arg_18]
0x18001770e  lea     rdx, aMcstartaddr6; "McStartAddr6"
0x180017715  lea     rcx, [rbp+hKey]
0x180017719  call    cs:__imp_?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x180017720  nop     dword ptr [rax+rax+00h]
0x180017725  mov     ecx, eax
0x180017727  mov     r9d, 0BCh
0x18001772d  mov     ebx, eax
0x18001772f  call    ElValidateWin32_9
0x180017734  test    eax, eax
0x180017736  jnz     short loc_1800177A6
0x180017738  mov     rcx, [rbp+var_10]
0x18001773c  test    rcx, rcx
0x18001773f  jz      short loc_180017752
0x180017741  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180017748  nop     dword ptr [rax+rax+00h]
0x18001774d  and     [rbp+var_10], 0
0x180017752  lea     r8, [rbp+var_10]
0x180017756  lea     rdx, aMcendaddr6; "McEndAddr6"
0x18001775d  lea     rcx, [rbp+hKey]
0x180017761  call    cs:__imp_?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x180017768  nop     dword ptr [rax+rax+00h]
0x18001776d  mov     ecx, eax
0x18001776f  mov     r9d, 0C1h
0x180017775  mov     ebx, eax
0x180017777  call    ElValidateWin32_9
0x18001777c  test    eax, eax
0x18001777e  jnz     short loc_1800177A6
0x180017780  mov     r9, [rbp+var_10]; unsigned __int16 *
0x180017784  lea     rcx, [rsi+80h]; lpCriticalSection
0x18001778b  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x18001778f  lea     edx, [rax+17h]; int
0x180017792  call    ?Initialize@CStaticMulticastLeaseHandler@@QEAAKHPEBG0@Z; CStaticMulticastLeaseHandler::Initialize(int,ushort const *,ushort const *)
0x180017797  mov     r9d, 0C8h
0x18001779d  mov     ecx, eax
0x18001779f  mov     ebx, eax
0x1800177a1  call    ElValidateWin32_9
0x1800177a6  mov     rcx, [rbp+arg_18]
0x1800177aa  test    rcx, rcx
0x1800177ad  jz      short loc_1800177C0
0x1800177af  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x1800177b6  nop     dword ptr [rax+rax+00h]
0x1800177bb  and     [rbp+arg_18], 0
0x1800177c0  mov     rcx, [rbp+var_10]
0x1800177c4  test    rcx, rcx
0x1800177c7  jz      short loc_1800177DA
0x1800177c9  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x1800177d0  nop     dword ptr [rax+rax+00h]
0x1800177d5  and     [rbp+var_10], 0
0x1800177da  mov     rcx, [rbp+hKey]; hKey
0x1800177de  test    rcx, rcx
0x1800177e1  jz      short loc_1800177EF
0x1800177e3  call    cs:__imp_RegCloseKey
0x1800177ea  nop     dword ptr [rax+rax+00h]
0x1800177ef  mov     rsi, [rsp+40h+arg_8]
0x1800177f4  mov     eax, ebx
0x1800177f6  mov     rbx, [rsp+40h+arg_0]
0x1800177fb  mov     rdi, [rsp+40h+arg_10]
0x180017800  add     rsp, 40h
0x180017804  pop     rbp
0x180017805  retn
```
