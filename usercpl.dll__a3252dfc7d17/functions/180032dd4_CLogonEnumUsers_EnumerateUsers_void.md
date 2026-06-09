# CLogonEnumUsers::_EnumerateUsers(void)

- ea: `0x180032dd4`
- end: `0x1800332a9`
- name: `?_EnumerateUsers@CLogonEnumUsers@@AEAAJXZ`
- size: `1237`
- prototype: `__int64 __fastcall(CLogonEnumUsers *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180033318`
- `0x180034200`
- `0x180034250`

## callees

- `0x18002c814`
- `0x180030930`
- `0x1800327a0`
- `0x180032dd4`
- `0x180034f50`
- `0x180035448`
- `0x180063810`
- `0x1800639c0`
- `0x180063b30`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032eac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032eac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032f6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032fd9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032f6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032fd9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180033159`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180033159`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003327d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003327d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033092`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033092`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800330c7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180033203`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800330c7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180033203`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003321b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003321b`
- `KERNEL32!lstrcmpiW` at `0x18003316b`
- `KERNEL32!lstrcmpiW` at `0x18003316b`
- `KERNEL32!GetComputerNameW` at `0x180033058`
- `KERNEL32!GetComputerNameW` at `0x180033058`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18003310a`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18003310a`

## pseudocode

```c
__int64 __fastcall CLogonEnumUsers::_EnumerateUsers(CLogonEnumUsers *this)
{
  DWORD v1; // ebx
  CLogonEnumUsers *v2; // rdi
  unsigned int Logon; // eax
  struct _DPA *v5; // rcx
  struct _DPA *v6; // rsi
  unsigned int v7; // r14d
  char *v8; // r15
  DWORD i; // r12d
  unsigned int v10; // r9d
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rcx
  bool v14; // bl
  bool v15; // bl
  DWORD v16; // ebx
  unsigned int v17; // ebx
  struct _DPA *v18; // rsi
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  void *p; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  DWORD nSize; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchReferencedDomainName; // [rsp+68h] [rbp-98h] BYREF
  DWORD v26; // [rsp+6Ch] [rbp-94h] BYREF
  void *v27; // [rsp+70h] [rbp-90h] BYREF
  CLogonEnumUsers *v28; // [rsp+78h] [rbp-88h]
  WCHAR Buffer[16]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pvData[80]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR v33[264]; // [rsp+320h] [rbp+220h] BYREF

  v28 = this;
  v1 = 0;
  v2 = this;
  cchName = 0;
  hMem = 0;
  if ( *((_DWORD *)this + 22) )
  {
    Logon = CUserList::GetLogon((bool)this, &cchName, (struct GINA_USER_INFORMATION **)&hMem);
  }
  else
  {
    if ( *((_DWORD *)this + 23) )
    {
      Logon = 0;
      goto LABEL_7;
    }
    Logon = CUserList::Get(0, &cchName, (struct GINA_USER_INFORMATION **)&hMem);
  }
  v1 = cchName;
LABEL_7:
  if ( Logon == 5 )
  {
    Logon = ShellGetFakeLogonUserList(&cchName, (struct GINA_USER_INFORMATION **)&hMem);
    v1 = cchName;
  }
  if ( Logon && Logon != 234 )
    return 2147500037LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 48));
  if ( *((_QWORD *)v2 + 5) )
  {
    v5 = (struct _DPA *)_InterlockedExchange64((volatile __int64 *)v2 + 5, 0);
    if ( v5 )
      g_pfn_DPA_DestroyCallback(v5, ReleaseLogonUserCallback, 0);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 48));
  v6 = g_pfn_DPA_Create(v1);
  if ( v6 )
  {
    v7 = 1;
    if ( v1 )
    {
      v8 = (char *)hMem;
      for ( i = 0; i < v1; ++i )
      {
        v10 = *((_DWORD *)v8 + 7);
        v11 = (const unsigned __int16 *)*((_QWORD *)v8 + 1);
        v12 = (const unsigned __int16 *)*((_QWORD *)v8 + 2);
        v13 = *(const unsigned __int16 **)v8;
        p = 0;
        if ( (int)CLogonUser::Create(v13, v12, v11, v10, &GUID_01c8ac33_bdcd_401b_a7d8_e680f4da87ff, &p) >= 0 )
        {
          if ( DPA_InsertPtr(v6, 0x7FFFFFFF, p) == -1 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
          else
            v7 = 0;
        }
        v8 += 32;
      }
      v2 = v28;
    }
    p = 0;
    if ( CoCreateInstance(
           &GUID_548968f5_17f7_4751_a581_ff0f1c732995,
           0,
           1u,
           &GUID_291de1ae_393e_4244_885a_6233a0d7da21,
           &p) >= 0 )
    {
      cchName = 0;
      v14 = 0;
      if ( (*(int (__fastcall **)(void *, DWORD *))(*(_QWORD *)p + 32LL))(p, &cchName) >= 0 )
        v14 = cchName != 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
      if ( v14 )
        goto LABEL_56;
    }
    p = 0;
    if ( CoCreateInstance(
           &GUID_548968f5_17f7_4751_a581_ff0f1c732995,
           0,
           1u,
           &GUID_291de1ae_393e_4244_885a_6233a0d7da21,
           &p) >= 0 )
    {
      cchName = 0;
      v15 = 0;
      if ( (*(int (__fastcall **)(void *, DWORD *))(*(_QWORD *)p + 40LL))(p, &cchName) >= 0 )
        v15 = cchName != 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
      if ( v15 )
      {
LABEL_56:
        if ( !*((_DWORD *)v2 + 22) )
        {
          p = 0;
          cchName = 260;
          nSize = 16;
          if ( !GetComputerNameW(Buffer, &nSize) )
            Buffer[0] = 0;
          if ( *((_DWORD *)v2 + 23) )
          {
            v17 = (unsigned int)EnumerateUsersInGroup(1, Buffer, v6) != 0 ? v7 : 0;
            v7 = (unsigned int)EnumerateUsersInGroup(3, Buffer, v6) != 0 ? v17 : 0;
          }
          else if ( !RegOpenKeyExW(
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
                       0,
                       8u,
                       (PHKEY)&p) )
          {
            v16 = 0;
            if ( !RegEnumKeyExW((HKEY)p, 0, Name, &cchName, 0, 0, 0, 0) )
            {
              do
              {
                pcbData = 80;
                if ( !SHGetValueW((HKEY)p, Name, L"Sid", 0, pvData, &pcbData) )
                {
                  v26 = 257;
                  cchReferencedDomainName = 16;
                  peUse = 0;
                  if ( LookupAccountSidW(0, pvData, v33, &v26, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
                  {
                    if ( lstrcmpiW(Buffer, ReferencedDomainName) )
                    {
                      if ( peUse == SidTypeUser )
                      {
                        v27 = 0;
                        if ( (int)CLogonUser::Create(
                                    v33,
                                    0,
                                    ReferencedDomainName,
                                    0xFFFFFFFF,
                                    &GUID_01c8ac33_bdcd_401b_a7d8_e680f4da87ff,
                                    &v27) >= 0 )
                        {
                          if ( DPA_InsertPtr(v6, 0x7FFFFFFF, v27) == -1 )
                            (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
                          else
                            v7 = 0;
                        }
                      }
                    }
                  }
                }
                ++v16;
                cchName = 260;
              }
              while ( !RegEnumKeyExW((HKEY)p, v16, Name, &cchName, 0, 0, 0, 0) );
              v2 = v28;
            }
            RegCloseKey((HKEY)p);
          }
        }
      }
    }
    v18 = (struct _DPA *)_InterlockedExchange64((volatile __int64 *)v2 + 5, (__int64)v6);
    if ( v18 )
      g_pfn_DPA_DestroyCallback(v18, ReleaseLogonUserCallback, 0);
  }
  else
  {
    v7 = -2147024882;
  }
  LocalFree(hMem);
  return v7;
}

```

## disassembly

```asm
0x180032dd4  push    rbp
0x180032dd6  push    rbx
0x180032dd7  push    rsi
0x180032dd8  push    rdi
0x180032dd9  push    r12
0x180032ddb  push    r13
0x180032ddd  push    r14
0x180032ddf  push    r15
0x180032de1  lea     rbp, [rsp-448h]
0x180032de9  sub     rsp, 548h
0x180032df0  mov     rax, cs:__security_cookie
0x180032df7  xor     rax, rsp
0x180032dfa  mov     [rbp+480h+var_50], rax
0x180032e01  xor     r13d, r13d
0x180032e04  mov     [rsp+580h+var_508], rcx
0x180032e09  mov     ebx, r13d
0x180032e0c  mov     rdi, rcx
0x180032e0f  mov     [rsp+580h+cchName], ebx
0x180032e13  mov     [rsp+580h+hMem], r13
0x180032e18  cmp     [rcx+58h], r13d
0x180032e1c  jnz     short loc_180032E3C
0x180032e1e  cmp     [rcx+5Ch], r13d
0x180032e22  jnz     short loc_180032E37
0x180032e24  lea     r8, [rsp+580h+hMem]; struct GINA_USER_INFORMATION **
0x180032e29  xor     ecx, ecx; bool
0x180032e2b  lea     rdx, [rsp+580h+cchName]; unsigned int *
0x180032e30  call    ?Get@CUserList@@SAJ_NPEAKPEAPEAUGINA_USER_INFORMATION@@@Z; CUserList::Get(bool,ulong *,GINA_USER_INFORMATION * *)
0x180032e35  jmp     short loc_180032E4B
0x180032e37  mov     eax, r13d
0x180032e3a  jmp     short loc_180032E4F
0x180032e3c  lea     r8, [rsp+580h+hMem]; struct GINA_USER_INFORMATION **
0x180032e41  lea     rdx, [rsp+580h+cchName]; unsigned int *
0x180032e46  call    ?GetLogon@CUserList@@SAJ_NPEAKPEAPEAUGINA_USER_INFORMATION@@@Z; CUserList::GetLogon(bool,ulong *,GINA_USER_INFORMATION * *)
0x180032e4b  mov     ebx, [rsp+580h+cchName]
0x180032e4f  cmp     eax, 5
0x180032e52  jnz     short loc_180032E67
0x180032e54  lea     rdx, [rsp+580h+hMem]; struct GINA_USER_INFORMATION **
0x180032e59  lea     rcx, [rsp+580h+cchName]; unsigned int *
0x180032e5e  call    ?ShellGetFakeLogonUserList@@YAKPEAKPEAPEAUGINA_USER_INFORMATION@@@Z; ShellGetFakeLogonUserList(ulong *,GINA_USER_INFORMATION * *)
0x180032e63  mov     ebx, [rsp+580h+cchName]
0x180032e67  test    eax, eax
0x180032e69  jz      short loc_180032E7C
0x180032e6b  cmp     eax, 0EAh
0x180032e70  jz      short loc_180032E7C
0x180032e72  mov     eax, 80004005h
0x180032e77  jmp     loc_180033286
0x180032e7c  lea     rcx, [rdi+30h]; lpCriticalSection
0x180032e80  call    cs:__imp_EnterCriticalSection
0x180032e86  cmp     [rdi+28h], r13
0x180032e8a  jz      short loc_180032EA8
0x180032e8c  mov     rcx, r13
0x180032e8f  xchg    rcx, [rdi+28h]; hdpa
0x180032e93  test    rcx, rcx
0x180032e96  jz      short loc_180032EA8
0x180032e98  xor     r8d, r8d; pData
0x180032e9b  lea     rdx, ReleaseLogonUserCallback; pfnCB
0x180032ea2  call    cs:g_pfn_DPA_DestroyCallback
0x180032ea8  lea     rcx, [rdi+30h]; lpCriticalSection
0x180032eac  call    cs:__imp_LeaveCriticalSection
0x180032eb2  mov     ecx, ebx; cItemGrow
0x180032eb4  call    cs:g_pfn_DPA_Create
0x180032eba  mov     rsi, rax
0x180032ebd  test    rax, rax
0x180032ec0  jz      loc_180033272
0x180032ec6  mov     r14d, 1
0x180032ecc  test    ebx, ebx
0x180032ece  jz      short loc_180032F4A
0x180032ed0  mov     r15, [rsp+580h+hMem]
0x180032ed5  lea     rdi, _GUID_01c8ac33_bdcd_401b_a7d8_e680f4da87ff
0x180032edc  mov     r12d, r13d
0x180032edf  mov     r9d, [r15+1Ch]; unsigned int
0x180032ee3  lea     rax, [rsp+580h+p]
0x180032ee8  mov     r8, [r15+8]; unsigned __int16 *
0x180032eec  mov     rdx, [r15+10h]; unsigned __int16 *
0x180032ef0  mov     rcx, [r15]; unsigned __int16 *
0x180032ef3  mov     [rsp+580h+lpClass], rax; void **
0x180032ef8  mov     [rsp+580h+ppv], rdi; struct _GUID *
0x180032efd  mov     [rsp+580h+p], r13
0x180032f02  call    ?Create@CLogonUser@@SAJPEBG00KAEBU_GUID@@PEAPEAX@Z; CLogonUser::Create(ushort const *,ushort const *,ushort const *,ulong,_GUID const &,void * *)
0x180032f07  test    eax, eax
0x180032f09  js      short loc_180032F39
0x180032f0b  mov     r8, [rsp+580h+p]; p
0x180032f10  mov     edx, 7FFFFFFFh; i
0x180032f15  mov     rcx, rsi; hdpa
0x180032f18  call    cs:__imp_DPA_InsertPtr
0x180032f1e  cmp     eax, 0FFFFFFFFh
0x180032f21  jz      short loc_180032F28
0x180032f23  mov     r14d, r13d
0x180032f26  jmp     short loc_180032F39
0x180032f28  mov     rcx, [rsp+580h+p]
0x180032f2d  mov     rax, [rcx]
0x180032f30  mov     rax, [rax+10h]
0x180032f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f39  inc     r12d
0x180032f3c  add     r15, 20h ; ' '
0x180032f40  cmp     r12d, ebx
0x180032f43  jb      short loc_180032EDF
0x180032f45  mov     rdi, [rsp+580h+var_508]
0x180032f4a  xor     edx, edx; pUnkOuter
0x180032f4c  mov     [rsp+580h+p], r13
0x180032f51  lea     rax, [rsp+580h+p]
0x180032f56  lea     r9, _GUID_291de1ae_393e_4244_885a_6233a0d7da21; riid
0x180032f5d  mov     [rsp+580h+ppv], rax; ppv
0x180032f62  lea     rcx, _GUID_548968f5_17f7_4751_a581_ff0f1c732995; rclsid
0x180032f69  lea     r8d, [rdx+1]; dwClsContext
0x180032f6d  call    cs:__imp_CoCreateInstance
0x180032f73  test    eax, eax
0x180032f75  js      short loc_180032FB6
0x180032f77  mov     rcx, [rsp+580h+p]
0x180032f7c  lea     rdx, [rsp+580h+cchName]
0x180032f81  mov     [rsp+580h+cchName], r13d
0x180032f86  mov     bl, r13b
0x180032f89  mov     rax, [rcx]
0x180032f8c  mov     rax, [rax+20h]
0x180032f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f95  test    eax, eax
0x180032f97  js      short loc_180032FA1
0x180032f99  cmp     [rsp+580h+cchName], r13d
0x180032f9e  setnz   bl
0x180032fa1  mov     rcx, [rsp+580h+p]
0x180032fa6  mov     rax, [rcx]
0x180032fa9  mov     rax, [rax+10h]
0x180032fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fb2  test    bl, bl
0x180032fb4  jnz     short loc_18003302A
0x180032fb6  xor     edx, edx; pUnkOuter
0x180032fb8  mov     [rsp+580h+p], r13
0x180032fbd  lea     rax, [rsp+580h+p]
0x180032fc2  lea     r9, _GUID_291de1ae_393e_4244_885a_6233a0d7da21; riid
0x180032fc9  mov     [rsp+580h+ppv], rax; ppv
0x180032fce  lea     rcx, _GUID_548968f5_17f7_4751_a581_ff0f1c732995; rclsid
0x180032fd5  lea     r8d, [rdx+1]; dwClsContext
0x180032fd9  call    cs:__imp_CoCreateInstance
0x180032fdf  test    eax, eax
0x180032fe1  js      loc_180033254
0x180032fe7  mov     rcx, [rsp+580h+p]
0x180032fec  lea     rdx, [rsp+580h+cchName]
0x180032ff1  mov     [rsp+580h+cchName], r13d
0x180032ff6  mov     bl, r13b
0x180032ff9  mov     rax, [rcx]
0x180032ffc  mov     rax, [rax+28h]
0x180033000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033005  test    eax, eax
0x180033007  js      short loc_180033011
0x180033009  cmp     [rsp+580h+cchName], r13d
0x18003300e  setnz   bl
0x180033011  mov     rcx, [rsp+580h+p]
0x180033016  mov     rax, [rcx]
0x180033019  mov     rax, [rax+10h]
0x18003301d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033022  test    bl, bl
0x180033024  jz      loc_180033254
0x18003302a  cmp     [rdi+58h], r13d
0x18003302e  jnz     loc_180033254
0x180033034  mov     r15d, 104h
0x18003303a  mov     [rsp+580h+p], r13
0x18003303f  mov     r12d, 10h
0x180033045  mov     [rsp+580h+cchName], r15d
0x18003304a  lea     rdx, [rsp+580h+nSize]; nSize
0x18003304f  mov     [rsp+580h+nSize], r12d
0x180033054  lea     rcx, [rbp+480h+Buffer]; lpBuffer
0x180033058  call    cs:__imp_GetComputerNameW
0x18003305e  test    eax, eax
0x180033060  jnz     short loc_180033067
0x180033062  mov     [rbp+480h+Buffer], r13w
0x180033067  cmp     [rdi+5Ch], r13d
0x18003306b  jnz     loc_180033223
0x180033071  lea     rax, [rsp+580h+p]
0x180033076  mov     r9d, 8; samDesired
0x18003307c  xor     r8d, r8d; ulOptions
0x18003307f  mov     [rsp+580h+ppv], rax; phkResult
0x180033084  lea     rdx, pszDir; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003308b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033092  call    cs:__imp_RegOpenKeyExW
0x180033098  test    eax, eax
0x18003309a  jnz     loc_180033254
0x1800330a0  mov     rcx, [rsp+580h+p]; hKey
0x1800330a5  lea     r9, [rsp+580h+cchName]; lpcchName
0x1800330aa  mov     [rsp+580h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800330af  lea     r8, [rbp+480h+Name]; lpName
0x1800330b3  mov     [rsp+580h+lpcchClass], r13; lpcchClass
0x1800330b8  xor     edx, edx; dwIndex
0x1800330ba  mov     [rsp+580h+lpClass], r13; lpClass
0x1800330bf  mov     ebx, r13d
0x1800330c2  mov     [rsp+580h+ppv], r13; lpReserved
0x1800330c7  call    cs:__imp_RegEnumKeyExW
0x1800330cd  test    eax, eax
0x1800330cf  jnz     loc_180033216
0x1800330d5  lea     rdi, _GUID_01c8ac33_bdcd_401b_a7d8_e680f4da87ff
0x1800330dc  mov     rcx, [rsp+580h+p]; hkey
0x1800330e1  lea     rax, [rsp+580h+pcbData]
0x1800330e6  mov     [rsp+580h+lpClass], rax; pcbData
0x1800330eb  lea     r8, aSid; "Sid"
0x1800330f2  lea     rax, [rbp+480h+pvData]
0x1800330f6  mov     [rsp+580h+pcbData], 50h ; 'P'
0x1800330fe  xor     r9d, r9d; pdwType
0x180033101  mov     [rsp+580h+ppv], rax; pvData
0x180033106  lea     rdx, [rbp+480h+Name]; pszSubKey
0x18003310a  call    cs:__imp_SHGetValueW
0x180033110  test    eax, eax
0x180033112  jnz     loc_1800331D8
0x180033118  lea     rax, [rsp+580h+peUse]
0x18003311d  mov     [rsp+580h+var_514], 101h
0x180033125  mov     [rsp+580h+lpcchClass], rax; peUse
0x18003312a  lea     r9, [rsp+580h+var_514]; cchName
0x18003312f  lea     rax, [rsp+580h+cchReferencedDomainName]
0x180033134  mov     [rsp+580h+cchReferencedDomainName], r12d
0x180033139  mov     [rsp+580h+lpClass], rax; cchReferencedDomainName
0x18003313e  lea     r8, [rbp+480h+var_260]; Name
0x180033145  lea     rax, [rbp+480h+ReferencedDomainName]
0x180033149  mov     [rsp+580h+peUse], r13d
0x18003314e  lea     rdx, [rbp+480h+pvData]; Sid
0x180033152  mov     [rsp+580h+ppv], rax; ReferencedDomainName
0x180033157  xor     ecx, ecx; lpSystemName
0x180033159  call    cs:__imp_LookupAccountSidW
0x18003315f  test    eax, eax
0x180033161  jz      short loc_1800331D8
0x180033163  lea     rdx, [rbp+480h+ReferencedDomainName]; lpString2
0x180033167  lea     rcx, [rbp+480h+Buffer]; lpString1
0x18003316b  call    cs:__imp_lstrcmpiW
0x180033171  test    eax, eax
0x180033173  jz      short loc_1800331D8
0x180033175  cmp     [rsp+580h+peUse], 1
0x18003317a  jnz     short loc_1800331D8
0x18003317c  lea     rax, [rsp+580h+var_510]
0x180033181  mov     [rsp+580h+var_510], r13
0x180033186  mov     [rsp+580h+lpClass], rax; void **
0x18003318b  lea     r8, [rbp+480h+ReferencedDomainName]; unsigned __int16 *
0x18003318f  or      r9d, 0FFFFFFFFh; unsigned int
0x180033193  mov     [rsp+580h+ppv], rdi; struct _GUID *
0x180033198  xor     edx, edx; unsigned __int16 *
0x18003319a  lea     rcx, [rbp+480h+var_260]; unsigned __int16 *
0x1800331a1  call    ?Create@CLogonUser@@SAJPEBG00KAEBU_GUID@@PEAPEAX@Z; CLogonUser::Create(ushort const *,ushort const *,ushort const *,ulong,_GUID const &,void * *)
0x1800331a6  test    eax, eax
0x1800331a8  js      short loc_1800331D8
0x1800331aa  mov     r8, [rsp+580h+var_510]; p
0x1800331af  mov     edx, 7FFFFFFFh; i
0x1800331b4  mov     rcx, rsi; hdpa
0x1800331b7  call    cs:__imp_DPA_InsertPtr
0x1800331bd  cmp     eax, 0FFFFFFFFh
0x1800331c0  jz      short loc_1800331C7
0x1800331c2  mov     r14d, r13d
0x1800331c5  jmp     short loc_1800331D8
0x1800331c7  mov     rcx, [rsp+580h+var_510]
0x1800331cc  mov     rax, [rcx]
0x1800331cf  mov     rax, [rax+10h]
0x1800331d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331d8  mov     rcx, [rsp+580h+p]; hKey
0x1800331dd  lea     r9, [rsp+580h+cchName]; lpcchName
0x1800331e2  mov     [rsp+580h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800331e7  lea     r8, [rbp+480h+Name]; lpName
0x1800331eb  mov     [rsp+580h+lpcchClass], r13; lpcchClass
0x1800331f0  inc     ebx
0x1800331f2  mov     [rsp+580h+lpClass], r13; lpClass
0x1800331f7  mov     edx, ebx; dwIndex
0x1800331f9  mov     [rsp+580h+ppv], r13; lpReserved
0x1800331fe  mov     [rsp+580h+cchName], r15d
0x180033203  call    cs:__imp_RegEnumKeyExW
0x180033209  test    eax, eax
0x18003320b  jz      loc_1800330DC
0x180033211  mov     rdi, [rsp+580h+var_508]
0x180033216  mov     rcx, [rsp+580h+p]; hKey
0x18003321b  call    cs:__imp_RegCloseKey
0x180033221  jmp     short loc_180033254
0x180033223  mov     r8, rsi
0x180033226  lea     rdx, [rbp+480h+Buffer]
0x18003322a  mov     ecx, 1
0x18003322f  call    ?EnumerateUsersInGroup@@YAJW4GROUPNAME_MAP_ENTRIES@@PEBGPEAU_DPA@@@Z; EnumerateUsersInGroup(GROUPNAME_MAP_ENTRIES,ushort const *,_DPA *)
0x180033234  neg     eax
0x180033236  lea     rdx, [rbp+480h+Buffer]
0x18003323a  mov     r8, rsi
0x18003323d  mov     ecx, 3
0x180033242  sbb     ebx, ebx
0x180033244  and     ebx, r14d
0x180033247  call    ?EnumerateUsersInGroup@@YAJW4GROUPNAME_MAP_ENTRIES@@PEBGPEAU_DPA@@@Z; EnumerateUsersInGroup(GROUPNAME_MAP_ENTRIES,ushort const *,_DPA *)
0x18003324c  neg     eax
0x18003324e  sbb     r14d, r14d
0x180033251  and     r14d, ebx
0x180033254  xchg    rsi, [rdi+28h]
0x180033258  test    rsi, rsi
0x18003325b  jz      short loc_180033278
0x18003325d  xor     r8d, r8d; pData
0x180033260  lea     rdx, ReleaseLogonUserCallback; pfnCB
0x180033267  mov     rcx, rsi; hdpa
0x18003326a  call    cs:g_pfn_DPA_DestroyCallback
0x180033270  jmp     short loc_180033278
0x180033272  mov     r14d, 8007000Eh
0x180033278  mov     rcx, [rsp+580h+hMem]; hMem
0x18003327d  call    cs:__imp_LocalFree
0x180033283  mov     eax, r14d
0x180033286  mov     rcx, [rbp+480h+var_50]
0x18003328d  xor     rcx, rsp; StackCookie
0x180033290  call    __security_check_cookie
0x180033295  add     rsp, 548h
0x18003329c  pop     r15
0x18003329e  pop     r14
0x1800332a0  pop     r13
0x1800332a2  pop     r12
0x1800332a4  pop     rdi
0x1800332a5  pop     rsi
  ... truncated ...
```
