# RegistryJson::_GetValueRecursive(IKvpEncoder *,HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800515a4`
- end: `0x18005194a`
- name: `?_GetValueRecursive@RegistryJson@@AEAAJPEAUIKvpEncoder@@PEAUHKEY__@@PEBG2@Z`
- size: `934`
- prototype: `__int64 __fastcall(RegistryJson *__hidden this, struct IKvpEncoder *, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180050850`
- `0x1800515a4`

## callees

- `0x180003110`
- `0x180003c88`
- `0x18000a230`
- `0x18000e5ac`
- `0x180010130`
- `0x180019d84`
- `0x18001a718`
- `0x180029c94`
- `0x18003f70c`
- `0x1800501b0`
- `0x18005132c`
- `0x1800514e8`
- `0x1800515a4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005174b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005174b`

## string_xrefs

- `0x180051677`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x180051878`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x1800518c4`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x1800518f3`: `onecore\base\flighting\common\regvalet\registryjson.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegistryJson::_GetValueRecursive(
        RegistryJson *this,
        struct IKvpEncoder *a2,
        HKEY a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int i; // edi
  unsigned __int16 v9; // cx
  HKEY v10; // r14
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // r8
  LSTATUS v14; // eax
  const unsigned __int16 *v15; // rbx
  DWORD v16; // esi
  struct IKvpEncoder *v17; // r15
  unsigned int v18; // eax
  int v19; // edi
  __int64 v20; // r8
  unsigned __int16 *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  int lpReserved; // [rsp+20h] [rbp-E0h]
  unsigned int lpReserveda; // [rsp+20h] [rbp-E0h]
  HKEY v27; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  DWORD cchName[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v32[3]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  *(_QWORD *)cchName = a2;
  if ( !*((_BYTE *)this + 54) )
  {
    for ( i = 0; ; ++i )
    {
      if ( !a4[i] )
        return RegistryJson::_GetSingleValueEncoded(this, a2, a3, a4, a5);
      if ( a4[i] == 42 && (!i || a4[i - 1] == 92) )
      {
        v9 = a4[i + 1];
        if ( v9 == 92 || !v9 )
          break;
      }
    }
    if ( i < 0 )
      return RegistryJson::_GetSingleValueEncoded(this, a2, a3, a4, a5);
    v10 = 0;
    v27 = 0;
    if ( i > 0 )
    {
      v28 = 0;
      v29 = 0;
      v30 = 0;
      v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &v28,
              a4,
              i - 1);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x106,
          (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
          (const char *)(unsigned int)v11,
          lpReserved);
LABEL_16:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v28);
LABEL_49:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
        return v12;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v27,
        0);
      v14 = RegWow64Helpers::OpenKey(a3, v28, v13, 131097, &v27);
      if ( v14 < 0 )
      {
        v12 = v14;
        goto LABEL_16;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v28);
      v10 = v27;
    }
    v15 = &a4[i + 1];
    if ( !*v15 || !v15[1] )
      v15 = 0;
    if ( !v10 )
      v10 = (HKEY)(*(__int64 (__fastcall **)(RegistryJson *))(*(_QWORD *)this + 64LL))(this);
    v16 = 0;
    v17 = *(struct IKvpEncoder **)cchName;
    while ( 1 )
    {
      memset_0(Name, 0, 0x208u);
      cchName[0] = 260;
      v18 = RegEnumKeyExW(v10, v16, Name, cchName, 0, 0, 0, 0);
      if ( v18 == 259 )
        goto LABEL_44;
      if ( v18 )
        break;
      memset(v32, 0, sizeof(v32));
      v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v32,
              Name,
              -1);
      if ( v19 < 0 )
      {
        v22 = 285;
LABEL_46:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
          (const char *)(unsigned int)v19,
          lpReserveda);
        goto LABEL_47;
      }
      if ( v15 )
      {
        v20 = -1;
        do
          ++v20;
        while ( v15[v20] );
        v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(v32, v15);
        if ( v19 < 0 )
        {
          v22 = 290;
          goto LABEL_46;
        }
      }
      v28 = 0;
      v29 = 0;
      v30 = 0;
      if ( a5 )
      {
        v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                &v28,
                a5,
                -1);
        if ( v19 < 0 )
        {
          v23 = 300;
LABEL_42:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v23,
            (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
            (const char *)(unsigned int)v19,
            lpReserveda);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v28);
LABEL_47:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v32);
          v12 = v19;
          goto LABEL_49;
        }
        v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
                &v28,
                L"%c%s",
                92,
                Name);
        if ( v19 < 0 )
        {
          v23 = 303;
          goto LABEL_42;
        }
        v21 = v28;
      }
      else
      {
        v21 = Name;
      }
      if ( (int)RegistryJson::_GetValueRecursive(this, v17, v10, v32[0], v21) >= 0
        && (*(unsigned __int8 (__fastcall **)(struct IKvpEncoder *))(*(_QWORD *)v17 + 48LL))(v17) )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v28);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v32);
LABEL_44:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
        return 0;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v28);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v32);
      ++v16;
    }
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x119,
            (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
            (const char *)v18,
            lpReserveda);
    goto LABEL_49;
  }
  return RegistryJson::_GetSingleValueEncoded(this, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800515a4  push    rbp
0x1800515a6  push    rbx
0x1800515a7  push    rsi
0x1800515a8  push    rdi
0x1800515a9  push    r12
0x1800515ab  push    r13
0x1800515ad  push    r14
0x1800515af  push    r15
0x1800515b1  lea     rbp, [rsp-1A8h]
0x1800515b9  sub     rsp, 2A8h
0x1800515c0  mov     rax, cs:__security_cookie
0x1800515c7  xor     rax, rsp
0x1800515ca  mov     [rbp+1E0h+var_50], rax
0x1800515d1  mov     rsi, r9
0x1800515d4  mov     r15, r8
0x1800515d7  mov     qword ptr [rsp+2E0h+cchName], rdx
0x1800515dc  mov     r12, rcx
0x1800515df  mov     r13, [rbp+1E0h+arg_20]
0x1800515e6  xor     r8d, r8d
0x1800515e9  cmp     [rcx+36h], r8b
0x1800515ed  jnz     loc_180051914
0x1800515f3  mov     edi, r8d
0x1800515f6  lea     r9d, [r8+5Ch]
0x1800515fa  movsxd  rax, edi
0x1800515fd  cmp     [rsi+rax*2], r8w
0x180051602  jz      loc_180051914
0x180051608  cmp     word ptr [rsi+rax*2], 2Ah ; '*'
0x18005160d  jnz     short loc_18005162B
0x18005160f  test    edi, edi
0x180051611  jz      short loc_18005161B
0x180051613  cmp     [rsi+rax*2-2], r9w
0x180051619  jnz     short loc_18005162B
0x18005161b  movzx   ecx, word ptr [rsi+rax*2+2]
0x180051620  cmp     cx, r9w
0x180051624  jz      short loc_18005162F
0x180051626  test    cx, cx
0x180051629  jz      short loc_18005162F
0x18005162b  inc     edi
0x18005162d  jmp     short loc_1800515FA
0x18005162f  test    edi, edi
0x180051631  js      loc_180051914
0x180051637  mov     r14, r8
0x18005163a  mov     [rsp+2E0h+var_2A0], r8
0x18005163f  jle     loc_1800516D7
0x180051645  mov     [rsp+2E0h+var_298], r8
0x18005164a  mov     [rsp+2E0h+var_290], r8
0x18005164f  mov     [rsp+2E0h+var_288], r8
0x180051654  lea     eax, [rdi-1]
0x180051657  movsxd  r8, eax
0x18005165a  mov     rdx, rsi
0x18005165d  lea     rcx, [rsp+2E0h+var_298]
0x180051662  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180051667  mov     ebx, eax
0x180051669  test    eax, eax
0x18005166b  jns     short loc_18005168A
0x18005166d  mov     rcx, [rbp+1E8h]; this
0x180051674  mov     r9d, eax; char *
0x180051677  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\common\\regva"...
0x18005167e  mov     edx, 106h; void *
0x180051683  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051688  jmp     short loc_1800516B9
0x18005168a  xor     edx, edx
0x18005168c  lea     rcx, [rsp+2E0h+var_2A0]
0x180051691  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180051696  lea     rax, [rsp+2E0h+var_2A0]
0x18005169b  mov     [rsp+2E0h+lpReserved], rax; PHKEY
0x1800516a0  mov     r9d, 20019h; unsigned int
0x1800516a6  mov     rdx, [rsp+2E0h+var_298]; unsigned __int16 *
0x1800516ab  mov     rcx, r15; HKEY
0x1800516ae  call    ?OpenKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKPEAPEAU2@@Z; RegWow64Helpers::OpenKey(HKEY__ * const,ushort const * const,ulong,ulong,HKEY__ * *)
0x1800516b3  test    eax, eax
0x1800516b5  jns     short loc_1800516C8
0x1800516b7  mov     ebx, eax
0x1800516b9  lea     rcx, [rsp+2E0h+var_298]
0x1800516be  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800516c3  jmp     loc_180051906
0x1800516c8  lea     rcx, [rsp+2E0h+var_298]
0x1800516cd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800516d2  mov     r14, [rsp+2E0h+var_2A0]
0x1800516d7  movsxd  rbx, edi
0x1800516da  inc     rbx
0x1800516dd  lea     rbx, [rsi+rbx*2]
0x1800516e1  xor     edi, edi
0x1800516e3  cmp     [rbx], di
0x1800516e6  jz      short loc_1800516EE
0x1800516e8  cmp     [rbx+2], di
0x1800516ec  jnz     short loc_1800516F1
0x1800516ee  mov     rbx, rdi
0x1800516f1  test    r14, r14
0x1800516f4  jnz     short loc_180051709
0x1800516f6  mov     rax, [r12]
0x1800516fa  mov     rcx, r12
0x1800516fd  mov     rax, [rax+40h]
0x180051701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051706  mov     r14, rax
0x180051709  mov     esi, edi
0x18005170b  mov     r15, qword ptr [rsp+2E0h+cchName]
0x180051710  xor     edx, edx; Val
0x180051712  mov     r8d, 208h; Size
0x180051718  lea     rcx, [rbp+1E0h+Name]; void *
0x18005171c  call    memset_0
0x180051721  mov     [rsp+2E0h+cchName], 104h
0x180051729  mov     [rsp+2E0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18005172e  mov     [rsp+2E0h+lpcchClass], rdi; lpcchClass
0x180051733  mov     [rsp+2E0h+lpClass], rdi; lpClass
0x180051738  mov     [rsp+2E0h+lpReserved], rdi; unsigned int
0x18005173d  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180051742  lea     r8, [rbp+1E0h+Name]; lpName
0x180051746  mov     edx, esi; dwIndex
0x180051748  mov     rcx, r14; hKey
0x18005174b  call    cs:__imp_RegEnumKeyExW
0x180051751  cmp     eax, 103h
0x180051756  jz      loc_1800518B1
0x18005175c  test    eax, eax
0x18005175e  jnz     loc_1800518E9
0x180051764  mov     [rsp+2E0h+var_278], rdi
0x180051769  mov     [rsp+2E0h+var_270], rdi
0x18005176e  mov     [rsp+2E0h+var_268], rdi
0x180051773  or      r8, 0FFFFFFFFFFFFFFFFh
0x180051777  lea     rdx, [rbp+1E0h+Name]
0x18005177b  lea     rcx, [rsp+2E0h+var_278]
0x180051780  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180051785  mov     edi, eax
0x180051787  test    eax, eax
0x180051789  js      loc_1800518BF
0x18005178f  xor     edi, edi
0x180051791  test    rbx, rbx
0x180051794  jz      short loc_1800517BD
0x180051796  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005179a  inc     r8
0x18005179d  cmp     [rbx+r8*2], di
0x1800517a2  jnz     short loc_18005179A
0x1800517a4  mov     rdx, rbx
0x1800517a7  lea     rcx, [rsp+2E0h+var_278]
0x1800517ac  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800517b1  mov     edi, eax
0x1800517b3  test    eax, eax
0x1800517b5  js      loc_180051865
0x1800517bb  xor     edi, edi
0x1800517bd  mov     [rsp+2E0h+var_298], rdi
0x1800517c2  mov     [rsp+2E0h+var_290], rdi
0x1800517c7  mov     [rsp+2E0h+var_288], rdi
0x1800517cc  test    r13, r13
0x1800517cf  jz      short loc_180051816
0x1800517d1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800517d5  mov     rdx, r13
0x1800517d8  lea     rcx, [rsp+2E0h+var_298]
0x1800517dd  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800517e2  mov     edi, eax
0x1800517e4  test    eax, eax
0x1800517e6  js      loc_180051873
0x1800517ec  lea     r9, [rbp+1E0h+Name]
0x1800517f0  mov     r8d, 5Ch ; '\'
0x1800517f6  lea     rdx, aCS; "%c%s"
0x1800517fd  lea     rcx, [rsp+2E0h+var_298]
0x180051802  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180051807  mov     edi, eax
0x180051809  test    eax, eax
0x18005180b  js      short loc_18005186C
0x18005180d  mov     rax, [rsp+2E0h+var_298]
0x180051812  xor     edi, edi
0x180051814  jmp     short loc_18005181A
0x180051816  lea     rax, [rbp+1E0h+Name]
0x18005181a  mov     [rsp+2E0h+lpReserved], rax; unsigned __int16 *
0x18005181f  mov     r9, [rsp+2E0h+var_278]; unsigned __int16 *
0x180051824  mov     r8, r14; HKEY
0x180051827  mov     rdx, r15; struct IKvpEncoder *
0x18005182a  mov     rcx, r12; this
0x18005182d  call    ?_GetValueRecursive@RegistryJson@@AEAAJPEAUIKvpEncoder@@PEAUHKEY__@@PEBG2@Z; RegistryJson::_GetValueRecursive(IKvpEncoder *,HKEY__ *,ushort const *,ushort const *)
0x180051832  test    eax, eax
0x180051834  js      short loc_180051849
0x180051836  mov     rax, [r15]
0x180051839  mov     rcx, r15
0x18005183c  mov     rax, [rax+30h]
0x180051840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051845  test    al, al
0x180051847  jnz     short loc_18005189B
0x180051849  lea     rcx, [rsp+2E0h+var_298]
0x18005184e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180051853  nop
0x180051854  lea     rcx, [rsp+2E0h+var_278]
0x180051859  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005185e  inc     esi
0x180051860  jmp     loc_180051710
0x180051865  mov     edx, 122h
0x18005186a  jmp     short loc_1800518C4
0x18005186c  mov     edx, 12Fh
0x180051871  jmp     short loc_180051878
0x180051873  mov     edx, 12Ch; void *
0x180051878  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\common\\regva"...
0x18005187f  mov     r9d, edi; char *
0x180051882  mov     rcx, [rbp+1E8h]; this
0x180051889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005188e  nop
0x18005188f  lea     rcx, [rsp+2E0h+var_298]
0x180051894  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180051899  jmp     short loc_1800518DB
0x18005189b  lea     rcx, [rsp+2E0h+var_298]
0x1800518a0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800518a5  nop
0x1800518a6  lea     rcx, [rsp+2E0h+var_278]
0x1800518ab  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800518b0  nop
0x1800518b1  lea     rcx, [rsp+2E0h+var_2A0]
0x1800518b6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800518bb  xor     eax, eax
0x1800518bd  jmp     short loc_180051927
0x1800518bf  mov     edx, 11Dh; void *
0x1800518c4  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\common\\regva"...
0x1800518cb  mov     r9d, edi; char *
0x1800518ce  mov     rcx, [rbp+1E8h]; this
0x1800518d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800518da  nop
0x1800518db  lea     rcx, [rsp+2E0h+var_278]
0x1800518e0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800518e5  mov     ebx, edi
0x1800518e7  jmp     short loc_180051906
0x1800518e9  mov     rcx, [rbp+1E8h]; this
0x1800518f0  mov     r9d, eax; char *
0x1800518f3  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\common\\regva"...
0x1800518fa  mov     edx, 119h; void *
0x1800518ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180051904  mov     ebx, eax
0x180051906  lea     rcx, [rsp+2E0h+var_2A0]
0x18005190b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180051910  mov     eax, ebx
0x180051912  jmp     short loc_180051927
0x180051914  mov     [rsp+2E0h+lpReserved], r13; unsigned __int16 *
0x180051919  mov     r9, rsi; unsigned __int16 *
0x18005191c  mov     r8, r15; HKEY
0x18005191f  mov     rcx, r12; this
0x180051922  call    ?_GetSingleValueEncoded@RegistryJson@@AEAAJPEAUIKvpEncoder@@PEAUHKEY__@@PEBG2@Z; RegistryJson::_GetSingleValueEncoded(IKvpEncoder *,HKEY__ *,ushort const *,ushort const *)
0x180051927  mov     rcx, [rbp+1E0h+var_50]
0x18005192e  xor     rcx, rsp; StackCookie
0x180051931  call    __security_check_cookie
0x180051936  add     rsp, 2A8h
0x18005193d  pop     r15
0x18005193f  pop     r14
0x180051941  pop     r13
0x180051943  pop     r12
0x180051945  pop     rdi
0x180051946  pop     rsi
0x180051947  pop     rbx
0x180051948  pop     rbp
0x180051949  retn
```
