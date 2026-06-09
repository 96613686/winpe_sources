# RegistryKeyEnumerator::GetCurrentSubKey(ulong)

- ea: `0x180011e68`
- end: `0x180011f38`
- name: `?GetCurrentSubKey@RegistryKeyEnumerator@@QEBAPEAUHKEY__@@K@Z`
- size: `208`
- prototype: `HKEY __fastcall(RegistryKeyEnumerator *this, REGSAM)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800155e8`
- `0x180015b88`
- `0x180015f78`
- `0x18001764c`
- `0x18001ab58`
- `0x18001b998`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180011e68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e93`

## string_xrefs

- `0x180011eda`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY __fastcall RegistryKeyEnumerator::GetCurrentSubKey(RegistryKeyEnumerator *this, REGSAM a2)
{
  unsigned int v2; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char v5; // [rsp+38h] [rbp-38h]
  const char *v6; // [rsp+40h] [rbp-30h]
  __int64 v7; // [rsp+48h] [rbp-28h]
  __int64 v8; // [rsp+50h] [rbp-20h]
  unsigned int v9; // [rsp+58h] [rbp-18h]
  int v10; // [rsp+5Ch] [rbp-14h]
  int v11; // [rsp+60h] [rbp-10h]
  HKEY phkResult; // [rsp+80h] [rbp+10h] BYREF

  phkResult = 0;
  v2 = RegOpenKeyExW(*(HKEY *)this, *((LPCWSTR *)this + 5), 0, a2, &phkResult);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v2);
    }
    v5 = 0;
    v6 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v8 = 0;
    v9 = v2;
    v10 = -1;
    v11 = 563;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return phkResult;
}

```

## disassembly

```asm
0x180011e68  mov     [rsp-8+arg_8], rbx
0x180011e6d  push    rbp
0x180011e6e  mov     rbp, rsp
0x180011e71  sub     rsp, 70h
0x180011e75  mov     r9d, edx; samDesired
0x180011e78  mov     [rbp+arg_0], 0
0x180011e80  mov     rdx, [rcx+28h]; lpSubKey
0x180011e84  lea     rax, [rbp+arg_0]
0x180011e88  mov     rcx, [rcx]; hKey
0x180011e8b  xor     r8d, r8d; ulOptions
0x180011e8e  mov     [rsp+70h+phkResult], rax; phkResult
0x180011e93  call    cs:__imp_RegOpenKeyExW
0x180011e99  mov     ebx, eax
0x180011e9b  test    eax, eax
0x180011e9d  jz      loc_180011F26
0x180011ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011eaa  lea     rax, WPP_GLOBAL_Control
0x180011eb1  cmp     rcx, rax
0x180011eb4  jz      short loc_180011EDA
0x180011eb6  test    byte ptr [rcx+1Ch], 1
0x180011eba  jz      short loc_180011EDA
0x180011ebc  cmp     byte ptr [rcx+19h], 2
0x180011ec0  jb      short loc_180011EDA
0x180011ec2  mov     rcx, [rcx+10h]
0x180011ec6  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180011ecd  mov     edx, 1Dh
0x180011ed2  mov     r9d, ebx
0x180011ed5  call    WPP_SF_D
0x180011eda  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180011ee1  mov     [rbp+var_38], 0
0x180011ee5  mov     [rbp+var_30], rax
0x180011ee9  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180011ef0  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180011ef7  mov     [rbp+var_28], 0
0x180011eff  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011f03  mov     [rbp+pExceptionObject], rax
0x180011f07  mov     [rbp+var_20], 0
0x180011f0f  mov     [rbp+var_18], ebx
0x180011f12  mov     [rbp+var_14], 0FFFFFFFFh
0x180011f19  mov     [rbp+var_10], 233h
0x180011f20  call    _CxxThrowException_0
0x180011f26  mov     rax, [rbp+arg_0]
0x180011f2a  mov     rbx, [rsp+70h+arg_8]
0x180011f32  add     rsp, 70h
0x180011f36  pop     rbp
0x180011f37  retn
```
