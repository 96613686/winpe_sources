# CVssRegistryKey::Open(HKEY__ *,ushort const *,...)

- ea: `0x18003a05c`
- end: `0x18003a2af`
- name: `?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ`
- size: `595`
- prototype: `bool(CVssRegistryKey *__hidden this, HKEY hKey, const unsigned __int16 *, ...)`
- caller_count: `9`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aa5c`
- `0x18000d968`
- `0x18000ffe0`
- `0x18001a0d0`
- `0x18001f898`
- `0x18002e7ec`
- `0x18002f070`
- `0x18003ced0`
- `0x18003f1f4`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180004a78`
- `0x180033a8c`
- `0x180033c78`
- `0x180037080`
- `0x180037de8`
- `0x180038330`
- `0x18003835c`
- `0x18003a05c`
- `0x18003a534`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a15e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a15e`

## string_xrefs

- `0x18003a096`: `base\stor\vss\modules\registry\registry.cxx`
- `0x18003a0a2`: `CVssRegistryKey::Open`
- `0x18003a1fd`: `RegOpenKeyExW(%ld,%s,...)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char CVssRegistryKey::Open(REGSAM *this, HKEY hKey, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v5; // rdx
  int v6; // ebx
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  HKEY v10; // rcx
  void **v11; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v13; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v14; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+60h] [rbp-A0h]
  int v17; // [rsp+64h] [rbp-9Ch]
  int v18; // [rsp+68h] [rbp-98h]
  _BYTE v19[120]; // [rsp+70h] [rbp-90h] BYREF
  int v20; // [rsp+E8h] [rbp-18h]
  LPVOID v21; // [rsp+F0h] [rbp-10h] BYREF
  int v22; // [rsp+F8h] [rbp-8h]
  WCHAR SubKey[264]; // [rsp+160h] [rbp+60h] BYREF
  va_list va; // [rsp+3D8h] [rbp+2D8h] BYREF

  va_start(va, a3);
  v13 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v14 = L"CVssRegistryKey::Open";
  v15 = L"REGREGSC";
  v16 = 127;
  v17 = 11;
  v18 = 255;
  v20 = 0x1000000;
  memset_0(v19, 0, sizeof(v19));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v21, (__int64)&v13, 0);
  v6 = StringCchVPrintfW(SubKey, v5, a3, va);
  v22 = v6;
  if ( v6 < 0 )
  {
    v13 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v14 = L"CVssRegistryKey::Open";
    v15 = L"REGREGSC";
    v16 = 139;
    v17 = 11;
    v18 = 255;
    v20 = 0x1000000;
    memset_0(v19, 0, sizeof(v19));
    CVssFunctionTracer::TranslateGenericError(&v21, &v13, (unsigned int)v6, L"StringCchVPrintfW()");
  }
  phkResult = 0;
  v11 = &CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable';
  CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>::Close(&v11);
  v7 = RegOpenKeyExW(hKey, SubKey, 0, *this, &phkResult);
  v8 = v7;
  if ( v7 == 2 )
  {
    CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::~CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>(&v11);
    CVssFunctionTracer::~CVssFunctionTracer(&v21);
    return 0;
  }
  else
  {
    if ( v7 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      v13 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v14 = L"CVssRegistryKey::Open";
      v15 = L"REGREGSC";
      v16 = 154;
      v17 = 11;
      v18 = 255;
      v20 = 0x1000000;
      memset_0(v19, 0, sizeof(v19));
      CVssFunctionTracer::TranslateGenericError(&v21, &v13, v8, L"RegOpenKeyExW(%ld,%s,...)", hKey, SubKey, 0);
    }
    CVssRegistryKey::Close((CVssRegistryKey *)this);
    CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom((__int64)(this + 4), SubKey);
    v10 = phkResult;
    phkResult = 0;
    *((_QWORD *)this + 1) = v10;
    CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::~CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>(&v11);
    CVssFunctionTracer::~CVssFunctionTracer(&v21);
    return 1;
  }
}

```

## disassembly

```asm
0x18003a05c  mov     [rsp-8+arg_10], r8
0x18003a061  mov     qword ptr [rsp-8+arg_18], r9
0x18003a066  push    rbp
0x18003a067  push    rbx
0x18003a068  push    rsi
0x18003a069  push    rdi
0x18003a06a  push    r12
0x18003a06c  push    r13
0x18003a06e  push    r15
0x18003a070  lea     rbp, [rsp-280h]
0x18003a078  sub     rsp, 380h
0x18003a07f  mov     rax, cs:__security_cookie
0x18003a086  xor     rax, rsp
0x18003a089  mov     [rbp+2B0h+var_40], rax
0x18003a090  mov     rsi, rdx
0x18003a093  mov     rdi, rcx
0x18003a096  lea     r15, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x18003a09d  mov     [rsp+3B0h+var_368], r15
0x18003a0a2  lea     r12, aCvssregistryke; "CVssRegistryKey::Open"
0x18003a0a9  mov     [rsp+3B0h+var_360], r12
0x18003a0ae  lea     r13, aRegregsc; "REGREGSC"
0x18003a0b5  mov     [rsp+3B0h+var_358], r13
0x18003a0ba  mov     [rsp+3B0h+var_350], 7Fh
0x18003a0c2  mov     [rsp+3B0h+var_34C], 0Bh
0x18003a0ca  mov     [rsp+3B0h+var_348], 0FFh
0x18003a0d2  mov     [rbp+2B0h+var_2C8], 1000000h
0x18003a0d9  xor     edx, edx; Val
0x18003a0db  lea     r8d, [rdx+78h]; Size
0x18003a0df  lea     rcx, [rsp+3B0h+var_340]; void *
0x18003a0e4  call    memset_0
0x18003a0e9  xor     r8d, r8d
0x18003a0ec  lea     rdx, [rsp+3B0h+var_368]
0x18003a0f1  lea     rcx, [rbp+2B0h+var_2C0]
0x18003a0f5  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003a0fa  nop
0x18003a0fb  mov     [rsp+3B0h+var_380], 0
0x18003a104  lea     r9, [rbp+2B0h+arg_18]; char *
0x18003a10b  mov     r8, [rbp+2B0h+arg_10]; unsigned __int16 *
0x18003a112  lea     rcx, [rbp+2B0h+SubKey]; unsigned __int16 *
0x18003a116  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18003a11b  mov     ebx, eax
0x18003a11d  mov     [rbp+2B0h+var_2B8], eax
0x18003a120  test    eax, eax
0x18003a122  js      loc_18003A258
0x18003a128  mov     [rsp+3B0h+var_370], 0
0x18003a131  lea     rax, ??_7?$CVssAuto@PEAUHKEY__@@V?$CVssAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@6B@; const CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable'
0x18003a138  mov     [rsp+3B0h+var_378], rax
0x18003a13d  lea     rcx, [rsp+3B0h+var_378]
0x18003a142  call    ?Close@?$CVssAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>::Close(void)
0x18003a147  lea     rax, [rsp+3B0h+var_370]
0x18003a14c  mov     [rsp+3B0h+phkResult], rax; phkResult
0x18003a151  mov     r9d, [rdi]; samDesired
0x18003a154  xor     r8d, r8d; ulOptions
0x18003a157  lea     rdx, [rbp+2B0h+SubKey]; lpSubKey
0x18003a15b  mov     rcx, rsi; hKey
0x18003a15e  call    cs:__imp_RegOpenKeyExW
0x18003a164  mov     ebx, eax
0x18003a166  cmp     eax, 2
0x18003a169  jnz     short loc_18003A1A2
0x18003a16b  lea     rcx, [rsp+3B0h+var_378]
0x18003a170  call    ??1?$CVssAuto@PEAUHKEY__@@V?$CVssAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@UEAA@XZ; CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::~CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>(void)
0x18003a175  nop
0x18003a176  lea     rcx, [rbp+2B0h+var_2C0]; this
0x18003a17a  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003a17f  xor     al, al
0x18003a181  mov     rcx, [rbp+2B0h+var_40]
0x18003a188  xor     rcx, rsp; StackCookie
0x18003a18b  call    __security_check_cookie
0x18003a190  add     rsp, 380h
0x18003a197  pop     r15
0x18003a199  pop     r13
0x18003a19b  pop     r12
0x18003a19d  pop     rdi
0x18003a19e  pop     rsi
0x18003a19f  pop     rbx
0x18003a1a0  pop     rbp
0x18003a1a1  retn
0x18003a1a2  test    eax, eax
0x18003a1a4  jz      short loc_18003A216
0x18003a1a6  jle     short loc_18003A1B1
0x18003a1a8  movzx   ebx, ax
0x18003a1ab  or      ebx, 80070000h
0x18003a1b1  mov     [rsp+3B0h+var_368], r15
0x18003a1b6  mov     [rsp+3B0h+var_360], r12
0x18003a1bb  mov     [rsp+3B0h+var_358], r13
0x18003a1c0  mov     [rsp+3B0h+var_350], 9Ah
0x18003a1c8  mov     [rsp+3B0h+var_34C], 0Bh
0x18003a1d0  mov     [rsp+3B0h+var_348], 0FFh
0x18003a1d8  mov     [rbp+2B0h+var_2C8], 1000000h
0x18003a1df  xor     edx, edx; Val
0x18003a1e1  lea     r8d, [rdx+78h]; Size
0x18003a1e5  lea     rcx, [rsp+3B0h+var_340]; void *
0x18003a1ea  call    memset_0
0x18003a1ef  lea     rax, [rbp+2B0h+SubKey]
0x18003a1f3  mov     [rsp+3B0h+var_388], rax
0x18003a1f8  mov     [rsp+3B0h+phkResult], rsi
0x18003a1fd  lea     r9, aRegopenkeyexwL; "RegOpenKeyExW(%ld,%s,...)"
0x18003a204  mov     r8d, ebx
0x18003a207  lea     rdx, [rsp+3B0h+var_368]
0x18003a20c  lea     rcx, [rbp+2B0h+var_2C0]
0x18003a210  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003a216  mov     rcx, rdi; this
0x18003a219  call    ?Close@CVssRegistryKey@@QEAAXXZ; CVssRegistryKey::Close(void)
0x18003a21e  lea     rcx, [rdi+10h]
0x18003a222  lea     rdx, [rbp+2B0h+SubKey]
0x18003a226  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x18003a22b  mov     rcx, [rsp+3B0h+var_370]
0x18003a230  mov     [rsp+3B0h+var_370], 0
0x18003a239  mov     [rdi+8], rcx
0x18003a23d  lea     rcx, [rsp+3B0h+var_378]
0x18003a242  call    ??1?$CVssAuto@PEAUHKEY__@@V?$CVssAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@UEAA@XZ; CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::~CVssAuto<HKEY__ *,CVssAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>(void)
0x18003a247  nop
0x18003a248  lea     rcx, [rbp+2B0h+var_2C0]; this
0x18003a24c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003a251  mov     al, 1
0x18003a253  jmp     loc_18003A181
0x18003a258  mov     [rsp+3B0h+var_368], r15
0x18003a25d  mov     [rsp+3B0h+var_360], r12
0x18003a262  mov     [rsp+3B0h+var_358], r13
0x18003a267  mov     [rsp+3B0h+var_350], 8Bh
0x18003a26f  mov     [rsp+3B0h+var_34C], 0Bh
0x18003a277  mov     [rsp+3B0h+var_348], 0FFh
0x18003a27f  mov     [rbp+2B0h+var_2C8], 1000000h
0x18003a286  xor     edx, edx; Val
0x18003a288  lea     r8d, [rdx+78h]; Size
0x18003a28c  lea     rcx, [rsp+3B0h+var_340]; void *
0x18003a291  call    memset_0
0x18003a296  lea     r9, aStringcchvprin; "StringCchVPrintfW()"
0x18003a29d  mov     r8d, ebx
0x18003a2a0  lea     rdx, [rsp+3B0h+var_368]
0x18003a2a5  lea     rcx, [rbp+2B0h+var_2C0]
0x18003a2a9  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```
