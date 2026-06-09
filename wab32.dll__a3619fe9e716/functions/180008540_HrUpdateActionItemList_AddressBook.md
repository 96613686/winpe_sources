# HrUpdateActionItemList(AddressBook *)

- ea: `0x180008540`
- end: `0x1800087a3`
- name: `?HrUpdateActionItemList@@YAJPEAVAddressBook@@@Z`
- size: `611`
- prototype: `__int64 __fastcall(struct AddressBook *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180007ff8`

## callees

- `0x180002818`
- `0x1800045e4`
- `0x180008144`
- `0x180008540`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800085c6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800085c6`
- `ADVAPI32!RegEnumValueW` at `0x180008629`
- `ADVAPI32!RegEnumValueW` at `0x1800086d8`
- `ADVAPI32!RegEnumValueW` at `0x180008629`
- `ADVAPI32!RegEnumValueW` at `0x1800086d8`
- `ADVAPI32!RegCloseKey` at `0x18000876a`
- `ADVAPI32!RegCloseKey` at `0x18000876a`
- `KERNEL32!LocalAlloc` at `0x180008682`
- `KERNEL32!LocalAlloc` at `0x180008682`
- `KERNEL32!EnterCriticalSection` at `0x180008587`
- `KERNEL32!EnterCriticalSection` at `0x180008587`
- `KERNEL32!LeaveCriticalSection` at `0x180008778`
- `KERNEL32!LeaveCriticalSection` at `0x180008778`
- `ole32!CoCreateInstance` at `0x180008707`
- `ole32!CoCreateInstance` at `0x180008707`
- `ole32!CLSIDFromString` at `0x180008670`
- `ole32!CLSIDFromString` at `0x180008670`

## pseudocode

```c
__int64 __fastcall HrUpdateActionItemList(struct AddressBook *a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // r12
  unsigned int v3; // ebx
  _QWORD *v4; // rsi
  DWORD v5; // ebx
  _QWORD *v6; // rax
  GUID v7; // xmm0
  _QWORD *v8; // rbx
  HRESULT Instance; // eax
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[264]; // [rsp+270h] [rbp+170h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 272);
  v3 = -2147467259;
  hKey = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 272));
  if ( *((_QWORD *)a1 + 89) )
    FreeActionItemList(a1);
  *((_QWORD *)a1 + 89) = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WAB\\WAB4\\ExtContext", 0, 0x20019u, &hKey) )
  {
    v4 = 0;
    memset_0(ValueName, 0, 0x208u);
    v5 = 0;
    cchValueName = 260;
    Type = 0;
    if ( !RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, 0, 0) )
    {
      do
      {
        pclsid = 0;
        memset_0(sz, 0, 0x208u);
        StringCchCopyW(sz, 0x104u, ValueName);
        if ( CLSIDFromString(sz, &pclsid) >= 0 )
        {
          v6 = LocalAlloc(0x40u, 0x30u);
          if ( !v6 )
          {
            v3 = -2147024882;
            goto LABEL_20;
          }
          v7 = pclsid;
          v6[5] = v4;
          v4 = v6;
          *(GUID *)v6 = v7;
        }
        ++v5;
        ValueName[0] = 0;
        cchValueName = 260;
      }
      while ( !RegEnumValueW(hKey, v5, ValueName, &cchValueName, 0, &Type, 0, 0) );
      if ( v4 )
      {
        v8 = v4;
        do
        {
          Instance = CoCreateInstance((const IID *const)v8, 0, 3u, &IID_IContextMenu, (LPVOID *)v8 + 2);
          if ( v8[2] && Instance >= 0 )
          {
            if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64))v8[2])(v8[2], &IID_IWABExtInit, (__int64)(v8 + 3)) < 0
              || !v8[3] )
            {
              OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(v8 + 2);
            }
          }
          else
          {
            v8[2] = 0;
          }
          v8 = (_QWORD *)v8[5];
        }
        while ( v8 );
      }
    }
    *((_QWORD *)a1 + 89) = v4;
    v3 = 0;
  }
LABEL_20:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x180008540  push    rbp
0x180008542  push    rbx
0x180008543  push    rsi
0x180008544  push    rdi
0x180008545  push    r12
0x180008547  push    r13
0x180008549  push    r14
0x18000854b  push    r15
0x18000854d  lea     rbp, [rsp-398h]
0x180008555  sub     rsp, 498h
0x18000855c  mov     rax, cs:__security_cookie
0x180008563  xor     rax, rsp
0x180008566  mov     [rbp+3D0h+var_50], rax
0x18000856d  lea     r12, [rcx+110h]
0x180008574  mov     rdi, rcx
0x180008577  xor     r13d, r13d
0x18000857a  mov     rcx, r12; lpCriticalSection
0x18000857d  mov     ebx, 80004005h
0x180008582  mov     [rsp+4D0h+hKey], r13
0x180008587  call    cs:__imp_EnterCriticalSection
0x18000858d  cmp     [rdi+2C8h], r13
0x180008594  jz      short loc_18000859E
0x180008596  mov     rcx, rdi; struct AddressBook *
0x180008599  call    ?FreeActionItemList@@YAXPEAVAddressBook@@@Z; FreeActionItemList(AddressBook *)
0x18000859e  lea     rax, [rsp+4D0h+hKey]
0x1800085a3  mov     [rdi+2C8h], r13
0x1800085aa  mov     r9d, 20019h; samDesired
0x1800085b0  mov     [rsp+4D0h+phkResult], rax; phkResult
0x1800085b5  xor     r8d, r8d; ulOptions
0x1800085b8  lea     rdx, SubKey; "Software\\Microsoft\\WAB\\WAB4\\ExtCont"...
0x1800085bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800085c6  call    cs:__imp_RegOpenKeyExW
0x1800085cc  test    eax, eax
0x1800085ce  jnz     loc_180008760
0x1800085d4  mov     r15d, 208h
0x1800085da  lea     rcx, [rsp+4D0h+ValueName]; void *
0x1800085df  mov     r8d, r15d; Size
0x1800085e2  xor     edx, edx; Val
0x1800085e4  mov     rsi, r13
0x1800085e7  call    memset_0
0x1800085ec  mov     rcx, [rsp+4D0h+hKey]; hKey
0x1800085f1  lea     rax, [rsp+4D0h+Type]
0x1800085f6  mov     [rsp+4D0h+lpcbData], r13; lpcbData
0x1800085fb  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180008600  mov     [rsp+4D0h+lpData], r13; lpData
0x180008605  lea     r8, [rsp+4D0h+ValueName]; lpValueName
0x18000860a  mov     [rsp+4D0h+lpType], rax; lpType
0x18000860f  mov     r14d, 104h
0x180008615  xor     edx, edx; dwIndex
0x180008617  mov     [rsp+4D0h+phkResult], r13; lpReserved
0x18000861c  mov     ebx, r13d
0x18000861f  mov     [rsp+4D0h+cchValueName], r14d
0x180008624  mov     [rsp+4D0h+Type], r13d
0x180008629  call    cs:__imp_RegEnumValueW
0x18000862f  test    eax, eax
0x180008631  jnz     loc_180008756
0x180008637  xorps   xmm0, xmm0
0x18000863a  lea     rcx, [rbp+3D0h+sz]; void *
0x180008641  mov     r8, r15; Size
0x180008644  xor     edx, edx; Val
0x180008646  movups  xmmword ptr [rsp+4D0h+pclsid.Data1], xmm0
0x18000864b  call    memset_0
0x180008650  lea     r8, [rsp+4D0h+ValueName]; unsigned __int16 *
0x180008655  mov     rdx, r14; unsigned __int64
0x180008658  lea     rcx, [rbp+3D0h+sz]; unsigned __int16 *
0x18000865f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008664  lea     rdx, [rsp+4D0h+pclsid]; pclsid
0x180008669  lea     rcx, [rbp+3D0h+sz]; lpsz
0x180008670  call    cs:__imp_CLSIDFromString
0x180008676  test    eax, eax
0x180008678  js      short loc_1800086A1
0x18000867a  mov     edx, 30h ; '0'; uBytes
0x18000867f  lea     ecx, [rdx+10h]; uFlags
0x180008682  call    cs:__imp_LocalAlloc
0x180008688  test    rax, rax
0x18000868b  jz      loc_180008743
0x180008691  movups  xmm0, xmmword ptr [rsp+4D0h+pclsid.Data1]
0x180008696  mov     [rax+28h], rsi
0x18000869a  mov     rsi, rax
0x18000869d  movdqu  xmmword ptr [rax], xmm0
0x1800086a1  mov     rcx, [rsp+4D0h+hKey]; hKey
0x1800086a6  lea     rax, [rsp+4D0h+Type]
0x1800086ab  mov     [rsp+4D0h+lpcbData], r13; lpcbData
0x1800086b0  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x1800086b5  mov     [rsp+4D0h+lpData], r13; lpData
0x1800086ba  lea     r8, [rsp+4D0h+ValueName]; lpValueName
0x1800086bf  mov     [rsp+4D0h+lpType], rax; lpType
0x1800086c4  inc     ebx
0x1800086c6  mov     edx, ebx; dwIndex
0x1800086c8  mov     [rsp+4D0h+phkResult], r13; lpReserved
0x1800086cd  mov     [rsp+4D0h+ValueName], r13w
0x1800086d3  mov     [rsp+4D0h+cchValueName], r14d
0x1800086d8  call    cs:__imp_RegEnumValueW
0x1800086de  test    eax, eax
0x1800086e0  jz      loc_180008637
0x1800086e6  test    rsi, rsi
0x1800086e9  jz      short loc_180008756
0x1800086eb  mov     rbx, rsi
0x1800086ee  xor     edx, edx; pUnkOuter
0x1800086f0  lea     r14, [rbx+10h]
0x1800086f4  lea     r9, IID_IContextMenu; riid
0x1800086fb  mov     [rsp+4D0h+phkResult], r14; ppv
0x180008700  mov     rcx, rbx; rclsid
0x180008703  lea     r8d, [rdx+3]; dwClsContext
0x180008707  call    cs:__imp_CoCreateInstance
0x18000870d  mov     rcx, [r14]
0x180008710  test    rcx, rcx
0x180008713  jz      short loc_18000874A
0x180008715  test    eax, eax
0x180008717  js      short loc_18000874A
0x180008719  mov     rax, [rcx]
0x18000871c  lea     r8, [rbx+18h]
0x180008720  lea     rdx, IID_IWABExtInit
0x180008727  mov     rax, [rax]
0x18000872a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000872f  test    eax, eax
0x180008731  js      short loc_180008739
0x180008733  cmp     [rbx+18h], r13
0x180008737  jnz     short loc_18000874D
0x180008739  mov     rcx, r14
0x18000873c  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180008741  jmp     short loc_18000874D
0x180008743  mov     ebx, 8007000Eh
0x180008748  jmp     short loc_180008760
0x18000874a  mov     [r14], r13
0x18000874d  mov     rbx, [rbx+28h]
0x180008751  test    rbx, rbx
0x180008754  jnz     short loc_1800086EE
0x180008756  mov     [rdi+2C8h], rsi
0x18000875d  mov     ebx, r13d
0x180008760  mov     rcx, [rsp+4D0h+hKey]; hKey
0x180008765  test    rcx, rcx
0x180008768  jz      short loc_180008775
0x18000876a  call    cs:__imp_RegCloseKey
0x180008770  mov     [rsp+4D0h+hKey], r13
0x180008775  mov     rcx, r12; lpCriticalSection
0x180008778  call    cs:__imp_LeaveCriticalSection
0x18000877e  mov     eax, ebx
0x180008780  mov     rcx, [rbp+3D0h+var_50]
0x180008787  xor     rcx, rsp; StackCookie
0x18000878a  call    __security_check_cookie
0x18000878f  add     rsp, 498h
0x180008796  pop     r15
0x180008798  pop     r14
0x18000879a  pop     r13
0x18000879c  pop     r12
0x18000879e  pop     rdi
0x18000879f  pop     rsi
0x1800087a0  pop     rbx
0x1800087a1  pop     rbp
0x1800087a2  retn
```
