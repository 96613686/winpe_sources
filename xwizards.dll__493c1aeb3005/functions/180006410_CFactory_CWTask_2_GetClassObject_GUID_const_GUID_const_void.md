# CFactory<CWTask,2>::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180006410`
- end: `0x180006619`
- name: `?GetClassObject@?$CFactory@VCWTask@@$01@@SAJAEBU_GUID@@0PEAPEAX@Z`
- size: `521`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008ee0`

## callees

- `0x180001200`
- `0x180006410`
- `0x180006a00`
- `0x1800085a8`
- `0x180008634`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006545`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006545`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006503`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006503`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800064de`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800064de`

## pseudocode

```c
__int64 __fastcall CFactory<CWTask,2>::GetClassObject(GUID *rguid, _QWORD *a2, HKEY a3)
{
  __int64 v5; // rax
  __int64 v6; // rax
  LSTATUS v8; // eax
  int v9; // ebx
  char *v10; // rsi
  BYTE Data[4]; // [rsp+30h] [rbp-128h] BYREF
  int v12; // [rsp+34h] [rbp-124h]
  DWORD cbData; // [rsp+38h] [rbp-120h] BYREF
  HKEY hKey[4]; // [rsp+40h] [rbp-118h] BYREF
  WCHAR SubKey[59]; // [rsp+60h] [rbp-F8h] BYREF
  OLECHAR sz[45]; // [rsp+D6h] [rbp-82h] BYREF

  hKey[1] = a3;
  hKey[0] = 0;
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
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, hKey);
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
    v9 = RegQueryValueExW(hKey[0], L"Class Type", 0, 0, Data, &cbData);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v12 = v9;
    if ( v9 >= 0 )
    {
      if ( *(_DWORD *)Data == 2 )
      {
        *(_QWORD *)a3 = 0;
        v10 = (char *)operator new(0x20u);
        if ( v10 )
        {
          *(_QWORD *)v10 = &CFactory<CWTask,2>::`vftable';
          *((_DWORD *)v10 + 2) = 1;
          *(GUID *)(v10 + 12) = *rguid;
          CFactory<CWTask,2>::LockServer(v10);
        }
        else
        {
          v10 = 0;
        }
        *(_QWORD *)a3 = v10;
        if ( !*(_QWORD *)a3 )
          v9 = -2147024882;
      }
      else
      {
        v9 = -2147221231;
      }
    }
    RegCloseKey(hKey[0]);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006410  mov     [rsp+arg_8], rbx
0x180006415  mov     [rsp+arg_18], rsi
0x18000641a  push    rdi
0x18000641b  push    r14
0x18000641d  push    r15
0x18000641f  sub     rsp, 140h
0x180006426  mov     rax, cs:__security_cookie
0x18000642d  xor     rax, rsp
0x180006430  mov     [rsp+158h+var_28], rax
0x180006438  mov     r14, r8
0x18000643b  mov     r15, rcx
0x18000643e  mov     [rsp+158h+var_110], r8
0x180006443  xor     edi, edi
0x180006445  mov     [rsp+158h+hKey], rdi
0x18000644a  mov     rax, [rdx]
0x18000644d  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180006454  jnz     short loc_180006461
0x180006456  mov     rax, [rdx+8]
0x18000645a  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180006461  test    rax, rax
0x180006464  jz      short loc_18000648C
0x180006466  mov     rax, [rdx]
0x180006469  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x180006470  jnz     short loc_18000647D
0x180006472  mov     rax, [rdx+8]
0x180006476  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x18000647d  test    rax, rax
0x180006480  jz      short loc_18000648C
0x180006482  mov     eax, 80004002h
0x180006487  jmp     loc_1800065F0
0x18000648c  mov     [rsp+158h+SubKey], di
0x180006491  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006498  mov     ebx, 66h ; 'f'
0x18000649d  mov     edx, ebx; unsigned __int64
0x18000649f  lea     rcx, [rsp+158h+SubKey]; unsigned __int16 *
0x1800064a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800064a9  lea     r8, aFactory; "Factory"
0x1800064b0  mov     edx, ebx; unsigned __int64
0x1800064b2  lea     rcx, [rsp+158h+SubKey]; unsigned __int16 *
0x1800064b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800064bc  lea     r8, asc_18003C378; "\\"
0x1800064c3  mov     edx, ebx; unsigned __int64
0x1800064c5  lea     rcx, [rsp+158h+SubKey]; unsigned __int16 *
0x1800064ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800064cf  lea     r8d, [rbx-3Fh]; cchMax
0x1800064d3  lea     rdx, [rsp+158h+sz]; lpsz
0x1800064db  mov     rcx, r15; rguid
0x1800064de  call    cs:__imp_StringFromGUID2
0x1800064e4  lea     rax, [rsp+158h+hKey]
0x1800064e9  mov     [rsp+158h+phkResult], rax; phkResult
0x1800064ee  mov     r9d, 20019h; samDesired
0x1800064f4  xor     r8d, r8d; ulOptions
0x1800064f7  lea     rdx, [rsp+158h+SubKey]; lpSubKey
0x1800064fc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006503  call    cs:__imp_RegOpenKeyExW
0x180006509  mov     ebx, eax
0x18000650b  test    eax, eax
0x18000650d  jnz     loc_1800065D5
0x180006513  mov     dword ptr [rsp+158h+Data], edi
0x180006517  mov     [rsp+158h+cbData], 4
0x18000651f  lea     rax, [rsp+158h+cbData]
0x180006524  mov     [rsp+158h+lpcbData], rax; lpcbData
0x180006529  lea     rax, [rsp+158h+Data]
0x18000652e  mov     [rsp+158h+phkResult], rax; lpData
0x180006533  xor     r9d, r9d; lpType
0x180006536  xor     r8d, r8d; lpReserved
0x180006539  lea     rdx, ValueName; "Class Type"
0x180006540  mov     rcx, [rsp+158h+hKey]; hKey
0x180006545  call    cs:__imp_RegQueryValueExW
0x18000654b  mov     ebx, eax
0x18000654d  test    eax, eax
0x18000654f  jle     short loc_18000655A
0x180006551  movzx   ebx, bx
0x180006554  or      ebx, 80070000h
0x18000655a  mov     [rsp+158h+var_124], ebx
0x18000655e  test    ebx, ebx
0x180006560  js      short loc_1800065C8
0x180006562  cmp     dword ptr [rsp+158h+Data], 2
0x180006567  jz      short loc_180006570
0x180006569  mov     ebx, 80040111h
0x18000656e  jmp     short loc_1800065C8
0x180006570  mov     [r14], rdi
0x180006573  mov     ecx, 20h ; ' '; Size
0x180006578  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000657d  mov     rsi, rax
0x180006580  test    rax, rax
0x180006583  jz      short loc_1800065AA
0x180006585  lea     rax, ??_7?$CFactory@VCWTask@@$01@@6B@; const CFactory<CWTask,2>::`vftable'
0x18000658c  mov     [rsi], rax
0x18000658f  mov     edx, 1
0x180006594  mov     [rsi+8], edx
0x180006597  movups  xmm0, xmmword ptr [r15]
0x18000659b  movdqu  xmmword ptr [rsi+0Ch], xmm0
0x1800065a0  mov     rcx, rsi
0x1800065a3  call    ?LockServer@?$CFactory@VCWTask@@$01@@UEAAJH@Z; CFactory<CWTask,2>::LockServer(int)
0x1800065a8  jmp     short loc_1800065AD
0x1800065aa  mov     rsi, rdi
0x1800065ad  mov     [r14], rsi
0x1800065b0  jmp     short loc_1800065BD
0x1800065b2  xor     edi, edi
0x1800065b4  mov     ebx, [rsp+158h+var_124]
0x1800065b8  mov     r14, [rsp+158h+var_110]
0x1800065bd  mov     eax, 8007000Eh
0x1800065c2  cmp     [r14], rdi
0x1800065c5  cmovz   ebx, eax
0x1800065c8  mov     rcx, [rsp+158h+hKey]; hKey
0x1800065cd  call    cs:__imp_RegCloseKey
0x1800065d3  jmp     short loc_1800065EE
0x1800065d5  cmp     eax, 2
0x1800065d8  jnz     short loc_1800065E1
0x1800065da  mov     ebx, 80040111h
0x1800065df  jmp     short loc_1800065EE
0x1800065e1  test    eax, eax
0x1800065e3  jle     short loc_1800065EE
0x1800065e5  movzx   ebx, ax
0x1800065e8  or      ebx, 80070000h
0x1800065ee  mov     eax, ebx
0x1800065f0  mov     rcx, [rsp+158h+var_28]
0x1800065f8  xor     rcx, rsp; StackCookie
0x1800065fb  call    __security_check_cookie
0x180006600  lea     r11, [rsp+158h+var_18]
0x180006608  mov     rbx, [r11+28h]
0x18000660c  mov     rsi, [r11+38h]
0x180006610  mov     rsp, r11
0x180006613  pop     r15
0x180006615  pop     r14
0x180006617  pop     rdi
0x180006618  retn
```
