# CFactory<CWHost,1>::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180005fec`
- end: `0x1800061f9`
- name: `?GetClassObject@?$CFactory@VCWHost@@$00@@SAJAEBU_GUID@@0PEAPEAX@Z`
- size: `525`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008ee0`

## callees

- `0x180001200`
- `0x180005fec`
- `0x1800069c0`
- `0x1800085a8`
- `0x180008634`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006121`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006121`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800060df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800060df`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800060ba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800060ba`

## pseudocode

```c
__int64 __fastcall CFactory<CWHost,1>::GetClassObject(GUID *rguid, _QWORD *a2, _QWORD *a3)
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
      if ( *(_DWORD *)Data == 1 )
      {
        try
        {
          *v3 = 0;
          v10 = (char *)operator new(0x20u);
          if ( v10 )
          {
            *(_QWORD *)v10 = &CFactory<CWHost,1>::`vftable';
            *((_DWORD *)v10 + 2) = 1;
            *(GUID *)(v10 + 12) = *rguid;
            CFactory<CWHost,1>::LockServer(v10, 1);
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
0x180005fec  mov     [rsp+arg_8], rbx
0x180005ff1  mov     [rsp+arg_18], rsi
0x180005ff6  push    rdi
0x180005ff7  push    r14
0x180005ff9  push    r15
0x180005ffb  sub     rsp, 140h
0x180006002  mov     rax, cs:__security_cookie
0x180006009  xor     rax, rsp
0x18000600c  mov     [rsp+158h+var_28], rax
0x180006014  mov     r14, r8
0x180006017  mov     r15, rcx
0x18000601a  mov     [rsp+158h+var_110], r8
0x18000601f  xor     edi, edi
0x180006021  mov     [rsp+158h+hKey], rdi
0x180006026  mov     rax, [rdx]
0x180006029  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180006030  jnz     short loc_18000603D
0x180006032  mov     rax, [rdx+8]
0x180006036  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000603d  test    rax, rax
0x180006040  jz      short loc_180006068
0x180006042  mov     rax, [rdx]
0x180006045  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000604c  jnz     short loc_180006059
0x18000604e  mov     rax, [rdx+8]
0x180006052  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x180006059  test    rax, rax
0x18000605c  jz      short loc_180006068
0x18000605e  mov     eax, 80004002h
0x180006063  jmp     loc_1800061D0
0x180006068  mov     [rsp+158h+SubKey], di
0x18000606d  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006074  mov     ebx, 66h ; 'f'
0x180006079  mov     edx, ebx; unsigned __int64
0x18000607b  lea     rcx, [rsp+158h+SubKey]; unsigned __int16 *
0x180006080  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006085  lea     r8, aFactory; "Factory"
0x18000608c  mov     edx, ebx; unsigned __int64
0x18000608e  lea     rcx, [rsp+158h+SubKey]; unsigned __int16 *
0x180006093  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006098  lea     r8, asc_18003C378; "\\"
0x18000609f  mov     edx, ebx; unsigned __int64
0x1800060a1  lea     rcx, [rsp+158h+SubKey]; unsigned __int16 *
0x1800060a6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800060ab  lea     r8d, [rbx-3Fh]; cchMax
0x1800060af  lea     rdx, [rsp+158h+sz]; lpsz
0x1800060b7  mov     rcx, r15; rguid
0x1800060ba  call    cs:__imp_StringFromGUID2
0x1800060c0  lea     rax, [rsp+158h+hKey]
0x1800060c5  mov     [rsp+158h+phkResult], rax; phkResult
0x1800060ca  mov     r9d, 20019h; samDesired
0x1800060d0  xor     r8d, r8d; ulOptions
0x1800060d3  lea     rdx, [rsp+158h+SubKey]; lpSubKey
0x1800060d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800060df  call    cs:__imp_RegOpenKeyExW
0x1800060e5  mov     ebx, eax
0x1800060e7  test    eax, eax
0x1800060e9  jnz     loc_1800061B5
0x1800060ef  mov     dword ptr [rsp+158h+Data], edi
0x1800060f3  mov     [rsp+158h+cbData], 4
0x1800060fb  lea     rax, [rsp+158h+cbData]
0x180006100  mov     [rsp+158h+lpcbData], rax; lpcbData
0x180006105  lea     rax, [rsp+158h+Data]
0x18000610a  mov     [rsp+158h+phkResult], rax; lpData
0x18000610f  xor     r9d, r9d; lpType
0x180006112  xor     r8d, r8d; lpReserved
0x180006115  lea     rdx, ValueName; "Class Type"
0x18000611c  mov     rcx, [rsp+158h+hKey]; hKey
0x180006121  call    cs:__imp_RegQueryValueExW
0x180006127  mov     ebx, eax
0x180006129  test    eax, eax
0x18000612b  jle     short loc_180006136
0x18000612d  movzx   ebx, bx
0x180006130  or      ebx, 80070000h
0x180006136  mov     [rsp+158h+var_124], ebx
0x18000613a  test    ebx, ebx
0x18000613c  js      short loc_1800061A8
0x18000613e  cmp     dword ptr [rsp+158h+Data], 1
0x180006143  jz      short loc_18000614C
0x180006145  mov     ebx, 80040111h
0x18000614a  jmp     short loc_1800061A8
0x18000614c  mov     [r14], rdi
0x18000614f  mov     ecx, 20h ; ' '; Size
0x180006154  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006159  mov     rsi, rax
0x18000615c  test    rax, rax
0x18000615f  jz      short loc_18000618A
0x180006161  lea     rax, ??_7?$CFactory@VCWHost@@$00@@6B@; const CFactory<CWHost,1>::`vftable'
0x180006168  mov     [rsi], rax
0x18000616b  mov     dword ptr [rsi+8], 1
0x180006172  movups  xmm0, xmmword ptr [r15]
0x180006176  movdqu  xmmword ptr [rsi+0Ch], xmm0
0x18000617b  mov     edx, 1
0x180006180  mov     rcx, rsi
0x180006183  call    ?LockServer@?$CFactory@VCWHost@@$00@@UEAAJH@Z; CFactory<CWHost,1>::LockServer(int)
0x180006188  jmp     short loc_18000618D
0x18000618a  mov     rsi, rdi
0x18000618d  mov     [r14], rsi
0x180006190  jmp     short loc_18000619D
0x180006192  xor     edi, edi
0x180006194  mov     ebx, [rsp+158h+var_124]
0x180006198  mov     r14, [rsp+158h+var_110]
0x18000619d  mov     eax, 8007000Eh
0x1800061a2  cmp     [r14], rdi
0x1800061a5  cmovz   ebx, eax
0x1800061a8  mov     rcx, [rsp+158h+hKey]; hKey
0x1800061ad  call    cs:__imp_RegCloseKey
0x1800061b3  jmp     short loc_1800061CE
0x1800061b5  cmp     eax, 2
0x1800061b8  jnz     short loc_1800061C1
0x1800061ba  mov     ebx, 80040111h
0x1800061bf  jmp     short loc_1800061CE
0x1800061c1  test    eax, eax
0x1800061c3  jle     short loc_1800061CE
0x1800061c5  movzx   ebx, ax
0x1800061c8  or      ebx, 80070000h
0x1800061ce  mov     eax, ebx
0x1800061d0  mov     rcx, [rsp+158h+var_28]
0x1800061d8  xor     rcx, rsp; StackCookie
0x1800061db  call    __security_check_cookie
0x1800061e0  lea     r11, [rsp+158h+var_18]
0x1800061e8  mov     rbx, [r11+28h]
0x1800061ec  mov     rsi, [r11+38h]
0x1800061f0  mov     rsp, r11
0x1800061f3  pop     r15
0x1800061f5  pop     r14
0x1800061f7  pop     rdi
0x1800061f8  retn
```
