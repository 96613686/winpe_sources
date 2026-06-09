# CredStore::GetCredId(User const &,wmi::AutoVectorPtr<ushort> &)

- ea: `0x180072da4`
- end: `0x180072f99`
- name: `?GetCredId@CredStore@@SAJAEBVUser@@AEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(User *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180003310`

## callees

- `0x180011e40`
- `0x180027910`
- `0x18002db40`
- `0x1800301f0`
- `0x180041020`
- `0x1800423e0`
- `0x18005a2bc`
- `0x180072da4`
- `0x1800731b8`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072e4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072e4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180072ea0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180072ea0`

## string_xrefs

- `0x180072f2a`: `TaskScheduler:Task:`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CredStore::GetCredId(User *this, unsigned __int16 **a2)
{
  CredStore *v4; // rcx
  signed int SidString; // ebx
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  bool v9; // sf
  void *v10; // rax
  DWORD Type; // [rsp+30h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-61h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-59h] BYREF
  const WCHAR **v15; // [rsp+48h] [rbp-51h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-49h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-41h] BYREF
  char v18; // [rsp+60h] [rbp-39h]
  const unsigned __int16 *v19; // [rsp+68h] [rbp-31h]
  __int64 v20; // [rsp+70h] [rbp-29h]
  __int64 v21; // [rsp+78h] [rbp-21h]
  int v22; // [rsp+80h] [rbp-19h]
  __int64 v23; // [rsp+84h] [rbp-15h]
  BYTE Data[2]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v25[78]; // [rsp+92h] [rbp-7h] BYREF

  v15 = 0;
  *(_WORD *)Data = 0;
  memset_0(v25, 0, 0x4Cu);
  SidString = User::GetSidString(this, (struct _bstr_t *)&v15);
  if ( SidString >= 0 )
  {
    hKey = 0;
    SidString = CredStore::OpenCredManagerKey(v4, (struct wmi::AutoRegKey *)&hKey);
    if ( SidString >= 0 )
    {
      phkResult = 0;
      if ( v15 )
        v6 = *v15;
      else
        v6 = 0;
      v7 = RegOpenKeyExW(hKey, v6, 0, 0x20019u, &phkResult);
      SidString = v7;
      if ( v7 > 0 )
        SidString = (unsigned __int16)v7 | 0x80070000;
      if ( SidString >= 0 )
      {
        Type = 0;
        cbData = 78;
        v8 = RegQueryValueExW(phkResult, L"Index", 0, &Type, Data, &cbData);
        v9 = v8 < 0;
        if ( v8 > 0 )
          v9 = 1;
        if ( v9 || Type == 1 )
        {
          v10 = operator new(0x74u);
          wmi::AutoVectorPtr<unsigned short>::operator=(a2, v10);
          if ( !*a2 )
          {
            v18 = 0;
            v19 = &qword_1800A8718;
            v20 = 0;
            v21 = 0;
            v22 = 14;
            v23 = -1;
            pExceptionObject = &wmi::GenericException::`vftable';
            throw (wmi::OutOfMemoryException *)&pExceptionObject;
          }
          SidString = StringCchCopyW(*a2, 0x3Au, L"TaskScheduler:Task:");
          if ( SidString >= 0 )
            SidString = StringCchCopyW(*a2 + 19, 0x27u, (const unsigned __int16 *)Data);
        }
        else
        {
          SidString = -2147216623;
        }
      }
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    }
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  }
  _bstr_t::~_bstr_t((_bstr_t *)&v15);
  return (unsigned int)SidString;
}

```

## disassembly

```asm
0x180072da4  mov     [rsp-8+arg_10], rbx
0x180072da9  mov     [rsp-8+arg_18], rdi
0x180072dae  push    rbp
0x180072daf  lea     rbp, [rsp-57h]
0x180072db4  sub     rsp, 0F0h
0x180072dbb  mov     rax, cs:__security_cookie
0x180072dc2  xor     rax, rsp
0x180072dc5  mov     [rbp+57h+var_10], rax
0x180072dc9  mov     rdi, rdx
0x180072dcc  mov     rbx, rcx
0x180072dcf  mov     [rbp+57h+var_A8], 0
0x180072dd7  xor     eax, eax
0x180072dd9  mov     word ptr [rbp+57h+Data], ax
0x180072ddd  xor     edx, edx; Val
0x180072ddf  lea     r8d, [rax+4Ch]; Size
0x180072de3  lea     rcx, [rbp+57h+var_5E]; void *
0x180072de7  call    memset_0
0x180072dec  lea     rdx, [rbp+57h+var_A8]; struct _bstr_t *
0x180072df0  mov     rcx, rbx; this
0x180072df3  call    ?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z; User::GetSidString(_bstr_t &)
0x180072df8  mov     ebx, eax
0x180072dfa  test    eax, eax
0x180072dfc  js      loc_180072F6C
0x180072e02  mov     [rbp+57h+hKey], 0
0x180072e0a  lea     rdx, [rbp+57h+hKey]; struct wmi::AutoRegKey *
0x180072e0e  call    ?OpenCredManagerKey@CredStore@@AEAAJAEAVAutoRegKey@wmi@@@Z; CredStore::OpenCredManagerKey(wmi::AutoRegKey &)
0x180072e13  mov     ebx, eax
0x180072e15  test    eax, eax
0x180072e17  js      loc_180072F62
0x180072e1d  mov     [rbp+57h+var_B8], 0
0x180072e25  mov     rax, [rbp+57h+var_A8]
0x180072e29  test    rax, rax
0x180072e2c  jz      short loc_180072E33
0x180072e2e  mov     rdx, [rax]
0x180072e31  jmp     short loc_180072E35
0x180072e33  xor     edx, edx; lpSubKey
0x180072e35  lea     rax, [rbp+57h+var_B8]
0x180072e39  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180072e3e  mov     r9d, 20019h; samDesired
0x180072e44  xor     r8d, r8d; ulOptions
0x180072e47  mov     rcx, [rbp+57h+hKey]; hKey
0x180072e4b  call    cs:__imp_RegOpenKeyExW
0x180072e52  nop     dword ptr [rax+rax+00h]
0x180072e57  mov     ebx, eax
0x180072e59  test    eax, eax
0x180072e5b  jle     short loc_180072E66
0x180072e5d  movzx   ebx, ax
0x180072e60  or      ebx, 80070000h
0x180072e66  test    ebx, ebx
0x180072e68  js      loc_180072F58
0x180072e6e  mov     [rbp+57h+Type], 0
0x180072e75  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x180072e7c  lea     rax, [rbp+57h+cbData]
0x180072e80  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x180072e85  lea     rax, [rbp+57h+Data]
0x180072e89  mov     [rsp+0F0h+phkResult], rax; lpData
0x180072e8e  lea     r9, [rbp+57h+Type]; lpType
0x180072e92  xor     r8d, r8d; lpReserved
0x180072e95  lea     rdx, aIndex; "Index"
0x180072e9c  mov     rcx, [rbp+57h+var_B8]; hKey
0x180072ea0  call    cs:__imp_RegQueryValueExW
0x180072ea7  nop     dword ptr [rax+rax+00h]
0x180072eac  test    eax, eax
0x180072eae  jle     short loc_180072EBA
0x180072eb0  movzx   eax, ax
0x180072eb3  or      eax, 80070000h
0x180072eb8  test    eax, eax
0x180072eba  js      short loc_180072ECC
0x180072ebc  cmp     [rbp+57h+Type], 1
0x180072ec0  jz      short loc_180072ECC
0x180072ec2  mov     ebx, 80041311h
0x180072ec7  jmp     loc_180072F58
0x180072ecc  mov     ecx, 74h ; 't'; dwBytes
0x180072ed1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072ed6  mov     rdx, rax
0x180072ed9  mov     rcx, rdi
0x180072edc  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x180072ee1  mov     rcx, [rdi]; unsigned __int16 *
0x180072ee4  test    rcx, rcx
0x180072ee7  jnz     short loc_180072F2A
0x180072ee9  mov     [rbp+57h+var_90], cl
0x180072eec  lea     rax, qword_1800A8718
0x180072ef3  mov     [rbp+57h+var_88], rax
0x180072ef7  mov     [rbp+57h+var_80], rcx
0x180072efb  mov     [rbp+57h+var_78], rcx
0x180072eff  mov     [rbp+57h+var_70], 0Eh
0x180072f06  mov     [rbp+57h+var_6C], 0FFFFFFFFFFFFFFFFh
0x180072f0e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180072f15  mov     [rbp+57h+pExceptionObject], rax
0x180072f19  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180072f20  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180072f24  call    _CxxThrowException_0
0x180072f2a  lea     r8, aTaskschedulerT; "TaskScheduler:Task:"
0x180072f31  mov     edx, 3Ah ; ':'; unsigned __int64
0x180072f36  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072f3b  mov     ebx, eax
0x180072f3d  test    eax, eax
0x180072f3f  js      short loc_180072F58
0x180072f41  mov     rcx, [rdi]
0x180072f44  add     rcx, 26h ; '&'; unsigned __int16 *
0x180072f48  lea     r8, [rbp+57h+Data]; unsigned __int16 *
0x180072f4c  mov     edx, 27h ; '''; unsigned __int64
0x180072f51  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072f56  mov     ebx, eax
0x180072f58  lea     rcx, [rbp+57h+var_B8]; this
0x180072f5c  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180072f61  nop
0x180072f62  lea     rcx, [rbp+57h+hKey]; this
0x180072f66  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180072f6b  nop
0x180072f6c  lea     rcx, [rbp+57h+var_A8]; this
0x180072f70  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180072f75  mov     eax, ebx
0x180072f77  mov     rcx, [rbp+57h+var_10]
0x180072f7b  xor     rcx, rsp; StackCookie
0x180072f7e  call    __security_check_cookie
0x180072f83  lea     r11, [rsp+0F0h+var_s0]
0x180072f8b  mov     rbx, [r11+20h]
0x180072f8f  mov     rdi, [r11+28h]
0x180072f93  mov     rsp, r11
0x180072f96  pop     rbp
0x180072f97  retn
```
