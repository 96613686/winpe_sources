# CredStore::GetCredId(User const &,wmi::AutoVectorPtr<ushort> &)

- ea: `0x18006f5d0`
- end: `0x18006f7b8`
- name: `?GetCredId@CredStore@@SAJAEBVUser@@AEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(User *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18002c1b0`

## callees

- `0x18000dc30`
- `0x180021300`
- `0x18002a9e0`
- `0x180030f80`
- `0x18003f940`
- `0x1800408b0`
- `0x18005790c`
- `0x18006f5d0`
- `0x18006f99c`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f677`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f677`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f6c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f6c6`

## string_xrefs

- `0x18006f74a`: `TaskScheduler:Task:`

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
            v19 = &qword_1800A4718;
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
0x18006f5d0  mov     [rsp-8+arg_10], rbx
0x18006f5d5  mov     [rsp-8+arg_18], rdi
0x18006f5da  push    rbp
0x18006f5db  lea     rbp, [rsp-57h]
0x18006f5e0  sub     rsp, 0F0h
0x18006f5e7  mov     rax, cs:__security_cookie
0x18006f5ee  xor     rax, rsp
0x18006f5f1  mov     [rbp+57h+var_10], rax
0x18006f5f5  mov     rdi, rdx
0x18006f5f8  mov     rbx, rcx
0x18006f5fb  mov     [rbp+57h+var_A8], 0
0x18006f603  xor     eax, eax
0x18006f605  mov     word ptr [rbp+57h+Data], ax
0x18006f609  xor     edx, edx; Val
0x18006f60b  lea     r8d, [rax+4Ch]; Size
0x18006f60f  lea     rcx, [rbp+57h+var_5E]; void *
0x18006f613  call    memset_0
0x18006f618  lea     rdx, [rbp+57h+var_A8]; struct _bstr_t *
0x18006f61c  mov     rcx, rbx; this
0x18006f61f  call    ?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z; User::GetSidString(_bstr_t &)
0x18006f624  mov     ebx, eax
0x18006f626  test    eax, eax
0x18006f628  js      loc_18006F78C
0x18006f62e  mov     [rbp+57h+hKey], 0
0x18006f636  lea     rdx, [rbp+57h+hKey]; struct wmi::AutoRegKey *
0x18006f63a  call    ?OpenCredManagerKey@CredStore@@AEAAJAEAVAutoRegKey@wmi@@@Z; CredStore::OpenCredManagerKey(wmi::AutoRegKey &)
0x18006f63f  mov     ebx, eax
0x18006f641  test    eax, eax
0x18006f643  js      loc_18006F782
0x18006f649  mov     [rbp+57h+var_B8], 0
0x18006f651  mov     rax, [rbp+57h+var_A8]
0x18006f655  test    rax, rax
0x18006f658  jz      short loc_18006F65F
0x18006f65a  mov     rdx, [rax]
0x18006f65d  jmp     short loc_18006F661
0x18006f65f  xor     edx, edx; lpSubKey
0x18006f661  lea     rax, [rbp+57h+var_B8]
0x18006f665  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18006f66a  mov     r9d, 20019h; samDesired
0x18006f670  xor     r8d, r8d; ulOptions
0x18006f673  mov     rcx, [rbp+57h+hKey]; hKey
0x18006f677  call    cs:__imp_RegOpenKeyExW
0x18006f67d  mov     ebx, eax
0x18006f67f  test    eax, eax
0x18006f681  jle     short loc_18006F68C
0x18006f683  movzx   ebx, ax
0x18006f686  or      ebx, 80070000h
0x18006f68c  test    ebx, ebx
0x18006f68e  js      loc_18006F778
0x18006f694  mov     [rbp+57h+Type], 0
0x18006f69b  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x18006f6a2  lea     rax, [rbp+57h+cbData]
0x18006f6a6  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x18006f6ab  lea     rax, [rbp+57h+Data]
0x18006f6af  mov     [rsp+0F0h+phkResult], rax; lpData
0x18006f6b4  lea     r9, [rbp+57h+Type]; lpType
0x18006f6b8  xor     r8d, r8d; lpReserved
0x18006f6bb  lea     rdx, aIndex; "Index"
0x18006f6c2  mov     rcx, [rbp+57h+var_B8]; hKey
0x18006f6c6  call    cs:__imp_RegQueryValueExW
0x18006f6cc  test    eax, eax
0x18006f6ce  jle     short loc_18006F6DA
0x18006f6d0  movzx   eax, ax
0x18006f6d3  or      eax, 80070000h
0x18006f6d8  test    eax, eax
0x18006f6da  js      short loc_18006F6EC
0x18006f6dc  cmp     [rbp+57h+Type], 1
0x18006f6e0  jz      short loc_18006F6EC
0x18006f6e2  mov     ebx, 80041311h
0x18006f6e7  jmp     loc_18006F778
0x18006f6ec  mov     ecx, 74h ; 't'; dwBytes
0x18006f6f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006f6f6  mov     rdx, rax
0x18006f6f9  mov     rcx, rdi
0x18006f6fc  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x18006f701  mov     rcx, [rdi]; unsigned __int16 *
0x18006f704  test    rcx, rcx
0x18006f707  jnz     short loc_18006F74A
0x18006f709  mov     [rbp+57h+var_90], cl
0x18006f70c  lea     rax, qword_1800A4718
0x18006f713  mov     [rbp+57h+var_88], rax
0x18006f717  mov     [rbp+57h+var_80], rcx
0x18006f71b  mov     [rbp+57h+var_78], rcx
0x18006f71f  mov     [rbp+57h+var_70], 0Eh
0x18006f726  mov     [rbp+57h+var_6C], 0FFFFFFFFFFFFFFFFh
0x18006f72e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18006f735  mov     [rbp+57h+pExceptionObject], rax
0x18006f739  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18006f740  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006f744  call    _CxxThrowException_0
0x18006f74a  lea     r8, aTaskschedulerT; "TaskScheduler:Task:"
0x18006f751  mov     edx, 3Ah ; ':'; unsigned __int64
0x18006f756  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f75b  mov     ebx, eax
0x18006f75d  test    eax, eax
0x18006f75f  js      short loc_18006F778
0x18006f761  mov     rcx, [rdi]
0x18006f764  add     rcx, 26h ; '&'; unsigned __int16 *
0x18006f768  lea     r8, [rbp+57h+Data]; unsigned __int16 *
0x18006f76c  mov     edx, 27h ; '''; unsigned __int64
0x18006f771  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f776  mov     ebx, eax
0x18006f778  lea     rcx, [rbp+57h+var_B8]; this
0x18006f77c  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18006f781  nop
0x18006f782  lea     rcx, [rbp+57h+hKey]; this
0x18006f786  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18006f78b  nop
0x18006f78c  lea     rcx, [rbp+57h+var_A8]; this
0x18006f790  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18006f795  mov     eax, ebx
0x18006f797  mov     rcx, [rbp+57h+var_10]
0x18006f79b  xor     rcx, rsp; StackCookie
0x18006f79e  call    __security_check_cookie
0x18006f7a3  lea     r11, [rsp+0F0h+var_s0]
0x18006f7ab  mov     rbx, [r11+20h]
0x18006f7af  mov     rdi, [r11+28h]
0x18006f7b3  mov     rsp, r11
0x18006f7b6  pop     rbp
0x18006f7b7  retn
```
