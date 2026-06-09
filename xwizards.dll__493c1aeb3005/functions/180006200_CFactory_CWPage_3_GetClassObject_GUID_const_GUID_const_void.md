# CFactory<CWPage,3>::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180006200`
- end: `0x180006409`
- name: `?GetClassObject@?$CFactory@VCWPage@@$02@@SAJAEBU_GUID@@0PEAPEAX@Z`
- size: `521`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008ee0`

## callees

- `0x180001200`
- `0x180006200`
- `0x1800069e0`
- `0x1800085a8`
- `0x180008634`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800063bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800063bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006335`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006335`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800062f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800062f3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800062ce`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800062ce`

## pseudocode

```c
__int64 __fastcall CFactory<CWPage,3>::GetClassObject(GUID *rguid, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v5; // rax
  __int64 v6; // rax
  LSTATUS v8; // eax
  int v9; // ebx
  char *v10; // rsi
  BYTE Data[4]; // [rsp+30h] [rbp-128h] BYREF
  int v12; // [rsp+34h] [rbp-124h]
  DWORD cbData; // [rsp+38h] [rbp-120h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-118h] BYREF
  _QWORD *v15; // [rsp+48h] [rbp-110h]
  WCHAR SubKey[59]; // [rsp+60h] [rbp-F8h] BYREF
  OLECHAR sz[45]; // [rsp+D6h] [rbp-82h] BYREF

  v3 = a3;
  v15 = a3;
  hKey = 0;
  v5 = *a2 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *a2 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = a2[1] - *(_QWORD *)IID_IUnknown.Data4;
  if ( v5 )
  {
    v6 = *a2 - *(_QWORD *)&IID_IClassFactory.Data1;
    if ( *a2 == *(_QWORD *)&IID_IClassFactory.Data1 )
      v6 = a2[1] - *(_QWORD *)IID_IClassFactory.Data4;
    if ( v6 )
      return 2147500034LL;
  }
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x66u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x66u, L"Factory");
  StringCchCatW(SubKey, 0x66u, L"\\");
  StringFromGUID2(rguid, sz, 39);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 == 2 )
    {
      return (unsigned int)-2147221231;
    }
    else if ( v8 > 0 )
    {
      return (unsigned __int16)v8 | 0x80070000;
    }
  }
  else
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    v9 = RegQueryValueExW(hKey, L"Class Type", 0, 0, Data, &cbData);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v12 = v9;
    if ( v9 >= 0 )
    {
      if ( *(_DWORD *)Data == 3 )
      {
        try
        {
          *v3 = 0;
          v10 = (char *)operator new(0x20u);
          if ( v10 )
          {
            *(_QWORD *)v10 = &CFactory<CWPage,3>::`vftable';
            *((_DWORD *)v10 + 2) = 1;
            *(GUID *)(v10 + 12) = *rguid;
            CFactory<CWPage,3>::LockServer(v10);
          }
          else
          {
            v10 = 0;
          }
          *v3 = v10;
        }
        catch ( ... )
        {
          v9 = v12;
          v3 = v15;
        }
        if ( !*v3 )
          v9 = -2147024882;
      }
      else
      {
        v9 = -2147221231;
      }
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006200  mov     [rsp+arg_8], rbx
0x180006205  mov     [rsp+arg_18], rsi
0x18000620a  push    rdi
0x18000620b  push    r14
0x18000620d  push    r15
0x18000620f  sub     rsp, 140h
0x180006216  mov     rax, cs:__security_cookie
0x18000621d  xor     rax, rsp
0x180006220  mov     [rsp+158h+var_28], rax
0x180006228  mov     r14, r8
0x18000622b  mov     r15, rcx
0x18000622e  mov     [rsp+158h+var_110], r8
0x180006233  xor     edi, edi
0x180006235  mov     [rsp+158h+hKey], rdi
0x18000623a  mov     rax, [rdx]
0x18000623d  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180006244  jnz     short loc_180006251
0x180006246  mov     rax, [rdx+8]
0x18000624a  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180006251  test    rax, rax
0x180006254  jz      short loc_18000627C
0x180006256  mov     rax, [rdx]
0x180006259  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x180006260  jnz     short loc_18000626D
0x180006262  mov     rax, [rdx+8]
0x180006266  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x18000626d  test    rax, rax
0x180006270  jz      short loc_18000627C
0x180006272  mov     eax, 80004002h
0x180006277  jmp     loc_1800063E0
0x18000627c  mov     [rsp+158h+SubKey], di
0x180006281  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006288  mov     ebx, 66h ; 'f'
0x18000628d  mov     edx, ebx; unsigned __int64
0x18000628f  lea     rcx, [rsp+158h+SubKey]; unsigned __int16 *
0x180006294  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006299  lea     r8, aFactory; "Factory"
0x1800062a0  mov     edx, ebx; unsigned __int64
0x1800062a2  lea     rcx, [rsp+158h+SubKey]; unsigned __int16 *
0x1800062a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800062ac  lea     r8, asc_18003C378; "\\"
0x1800062b3  mov     edx, ebx; unsigned __int64
0x1800062b5  lea     rcx, [rsp+158h+SubKey]; unsigned __int16 *
0x1800062ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800062bf  lea     r8d, [rbx-3Fh]; cchMax
0x1800062c3  lea     rdx, [rsp+158h+sz]; lpsz
0x1800062cb  mov     rcx, r15; rguid
0x1800062ce  call    cs:__imp_StringFromGUID2
0x1800062d4  lea     rax, [rsp+158h+hKey]
0x1800062d9  mov     [rsp+158h+phkResult], rax; phkResult
0x1800062de  mov     r9d, 20019h; samDesired
0x1800062e4  xor     r8d, r8d; ulOptions
0x1800062e7  lea     rdx, [rsp+158h+SubKey]; lpSubKey
0x1800062ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800062f3  call    cs:__imp_RegOpenKeyExW
0x1800062f9  mov     ebx, eax
0x1800062fb  test    eax, eax
0x1800062fd  jnz     loc_1800063C5
0x180006303  mov     dword ptr [rsp+158h+Data], edi
0x180006307  mov     [rsp+158h+cbData], 4
0x18000630f  lea     rax, [rsp+158h+cbData]
0x180006314  mov     [rsp+158h+lpcbData], rax; lpcbData
0x180006319  lea     rax, [rsp+158h+Data]
0x18000631e  mov     [rsp+158h+phkResult], rax; lpData
0x180006323  xor     r9d, r9d; lpType
0x180006326  xor     r8d, r8d; lpReserved
0x180006329  lea     rdx, ValueName; "Class Type"
0x180006330  mov     rcx, [rsp+158h+hKey]; hKey
0x180006335  call    cs:__imp_RegQueryValueExW
0x18000633b  mov     ebx, eax
0x18000633d  test    eax, eax
0x18000633f  jle     short loc_18000634A
0x180006341  movzx   ebx, bx
0x180006344  or      ebx, 80070000h
0x18000634a  mov     [rsp+158h+var_124], ebx
0x18000634e  test    ebx, ebx
0x180006350  js      short loc_1800063B8
0x180006352  cmp     dword ptr [rsp+158h+Data], 3
0x180006357  jz      short loc_180006360
0x180006359  mov     ebx, 80040111h
0x18000635e  jmp     short loc_1800063B8
0x180006360  mov     [r14], rdi
0x180006363  mov     ecx, 20h ; ' '; Size
0x180006368  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000636d  mov     rsi, rax
0x180006370  test    rax, rax
0x180006373  jz      short loc_18000639A
0x180006375  lea     rax, ??_7?$CFactory@VCWPage@@$02@@6B@; const CFactory<CWPage,3>::`vftable'
0x18000637c  mov     [rsi], rax
0x18000637f  mov     edx, 1
0x180006384  mov     [rsi+8], edx
0x180006387  movups  xmm0, xmmword ptr [r15]
0x18000638b  movdqu  xmmword ptr [rsi+0Ch], xmm0
0x180006390  mov     rcx, rsi
0x180006393  call    ?LockServer@?$CFactory@VCWPage@@$02@@UEAAJH@Z; CFactory<CWPage,3>::LockServer(int)
0x180006398  jmp     short loc_18000639D
0x18000639a  mov     rsi, rdi
0x18000639d  mov     [r14], rsi
0x1800063a0  jmp     short loc_1800063AD
0x1800063a2  xor     edi, edi
0x1800063a4  mov     ebx, [rsp+158h+var_124]
0x1800063a8  mov     r14, [rsp+158h+var_110]
0x1800063ad  mov     eax, 8007000Eh
0x1800063b2  cmp     [r14], rdi
0x1800063b5  cmovz   ebx, eax
0x1800063b8  mov     rcx, [rsp+158h+hKey]; hKey
0x1800063bd  call    cs:__imp_RegCloseKey
0x1800063c3  jmp     short loc_1800063DE
0x1800063c5  cmp     eax, 2
0x1800063c8  jnz     short loc_1800063D1
0x1800063ca  mov     ebx, 80040111h
0x1800063cf  jmp     short loc_1800063DE
0x1800063d1  test    eax, eax
0x1800063d3  jle     short loc_1800063DE
0x1800063d5  movzx   ebx, ax
0x1800063d8  or      ebx, 80070000h
0x1800063de  mov     eax, ebx
0x1800063e0  mov     rcx, [rsp+158h+var_28]
0x1800063e8  xor     rcx, rsp; StackCookie
0x1800063eb  call    __security_check_cookie
0x1800063f0  lea     r11, [rsp+158h+var_18]
0x1800063f8  mov     rbx, [r11+28h]
0x1800063fc  mov     rsi, [r11+38h]
0x180006400  mov     rsp, r11
0x180006403  pop     r15
0x180006405  pop     r14
0x180006407  pop     rdi
0x180006408  retn
```
