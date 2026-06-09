# ConfigBase::ConfigBase(HKEY__ *,ushort const *)

- ea: `0x180014208`
- end: `0x180014309`
- name: `??0ConfigBase@@QEAA@PEAUHKEY__@@PEBG@Z`
- size: `257`
- prototype: `ConfigBase *__fastcall(ConfigBase *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007e10`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180014208`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001425c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001425c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ConfigBase *__fastcall ConfigBase::ConfigBase(ConfigBase *this, HKEY a2, const unsigned __int16 *a3)
{
  unsigned int v4; // edi
  void **pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char v7; // [rsp+38h] [rbp-40h]
  const char *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  __int64 v10; // [rsp+50h] [rbp-28h]
  unsigned int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  int v13; // [rsp+60h] [rbp-18h]

  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &SubscriptionGlobalsReader::`vftable';
  *((_QWORD *)this + 2) = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector\\Globals",
         0,
         0x20019u,
         (PHKEY)this + 2);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v4);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v9 = 0;
    v10 = 0;
    v11 = v4;
    v12 = -1;
    v13 = 76;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180014208  mov     [rsp+arg_8], rbx
0x18001420d  mov     [rsp+arg_0], rcx
0x180014212  push    rdi
0x180014213  sub     rsp, 70h
0x180014217  mov     rbx, rcx
0x18001421a  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180014221  mov     [rcx], rax
0x180014224  mov     dword ptr [rcx+8], 0
0x18001422b  lea     rax, ??_7SubscriptionGlobalsReader@@6B@; const SubscriptionGlobalsReader::`vftable'
0x180014232  mov     [rcx], rax
0x180014235  lea     rax, [rcx+10h]
0x180014239  mov     qword ptr [rax], 0
0x180014240  mov     [rsp+78h+phkResult], rax; phkResult
0x180014245  mov     r9d, 20019h; samDesired
0x18001424b  xor     r8d, r8d; ulOptions
0x18001424e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180014255  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001425c  call    cs:__imp_RegOpenKeyExW
0x180014262  mov     edi, eax
0x180014264  test    eax, eax
0x180014266  jz      loc_1800142F8
0x18001426c  lea     rax, WPP_GLOBAL_Control
0x180014273  mov     rcx, cs:WPP_GLOBAL_Control
0x18001427a  cmp     rcx, rax
0x18001427d  jz      short loc_1800142A3
0x18001427f  test    byte ptr [rcx+1Ch], 40h
0x180014283  jz      short loc_1800142A3
0x180014285  cmp     byte ptr [rcx+19h], 2
0x180014289  jb      short loc_1800142A3
0x18001428b  mov     edx, 0Dh
0x180014290  mov     r9d, edi
0x180014293  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x18001429a  mov     rcx, [rcx+10h]
0x18001429e  call    WPP_SF_D
0x1800142a3  mov     [rsp+78h+var_40], 0
0x1800142a8  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800142af  mov     [rsp+78h+var_38], rax
0x1800142b4  mov     [rsp+78h+var_30], 0
0x1800142bd  mov     [rsp+78h+var_28], 0
0x1800142c6  mov     [rsp+78h+var_20], edi
0x1800142ca  mov     [rsp+78h+var_1C], 0FFFFFFFFh
0x1800142d2  mov     [rsp+78h+var_18], 4Ch ; 'L'
0x1800142da  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800142e1  mov     [rsp+78h+pExceptionObject], rax
0x1800142e6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800142ed  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800142f2  call    _CxxThrowException_0
0x1800142f8  mov     rax, rbx
0x1800142fb  mov     rbx, [rsp+78h+arg_8]
0x180014303  add     rsp, 70h
0x180014307  pop     rdi
0x180014308  retn
```
