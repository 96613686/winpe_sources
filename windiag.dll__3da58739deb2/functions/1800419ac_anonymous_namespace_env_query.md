# _anonymous_namespace_::env_query

- ea: `0x1800419ac`
- end: `0x180041bf0`
- name: `_anonymous_namespace_::env_query`
- size: `580`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x180040cf0`
- `0x180040d00`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006050`
- `0x180006d40`
- `0x180007160`
- `0x18003af08`
- `0x18003b0bc`
- `0x180040d10`
- `0x180040f94`
- `0x180041564`
- `0x1800419ac`
- `0x180041e58`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180041a55`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180041a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419fe`
- `USERENV!CreateEnvironmentBlock` at `0x1800419f4`
- `USERENV!CreateEnvironmentBlock` at `0x1800419f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall anonymous_namespace_::env_query(struct lua_State *a1, char a2)
{
  DWORD LastError; // eax
  const wchar_t *v4; // rbx
  wchar_t *v5; // rax
  wchar_t *v6; // rdi
  wchar_t *v7; // rdx
  __int64 v8; // r8
  __int128 *v9; // rdx
  __int64 v10; // rax
  _QWORD *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rdx
  LPVOID Environment; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h]
  _QWORD v19[4]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v20[40]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v21[7]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v22; // [rsp+D8h] [rbp-28h]
  _BYTE pExceptionObject[1072]; // [rsp+E0h] [rbp-20h] BYREF

  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, 0, a2 != 1) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "env_query",
        18);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  v21[0] = off_18009F2F0;
  v21[1] = &Environment;
  v22 = v21;
  lua_createtable(a1, 0, 0);
  v4 = (const wchar_t *)Environment;
  if ( Environment )
  {
    do
    {
      if ( !*v4 )
        break;
      v5 = wcschr(v4, 0x3Du);
      v6 = v5;
      if ( v5 )
      {
        std::wstring::wstring(v19, v4, v5);
        v7 = v6 + 1;
        v17 = 0;
        v18 = 0;
        v8 = -1;
        do
          ++v8;
        while ( v7[v8] );
        std::wstring::_Construct<1,unsigned short const *>(&v17, v7);
        v9 = &v17;
        if ( *((_QWORD *)&v18 + 1) > 7u )
          v9 = (__int128 *)v17;
        v10 = windiag::wchar_to_string(v20, v9);
        if ( *(_QWORD *)(v10 + 24) > 0xFu )
          v10 = *(_QWORD *)v10;
        lua_pushstring(a1, (const char *)v10);
        std::string::~string(v20);
        v11 = v19;
        if ( v19[3] > 7u )
          v11 = (_QWORD *)v19[0];
        v12 = windiag::wchar_to_string(v20, v11);
        if ( *(_QWORD *)(v12 + 24) > 0xFu )
          v12 = *(_QWORD *)v12;
        lua_setfield(a1, -2, (const char *)v12);
        std::string::~string(v20);
        std::wstring::~wstring(&v17);
        std::wstring::~wstring(v19);
      }
      v13 = -1;
      do
        ++v13;
      while ( v4[v13] );
      v4 += v13 + 1;
    }
    while ( v4 );
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
    if ( v22 )
    {
      v14 = v21;
      LOBYTE(v14) = v22 != v21;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v22 + 32LL))(v22, v14);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800419ac  mov     [rsp-8+arg_8], rbx
0x1800419b1  mov     [rsp-8+arg_10], rsi
0x1800419b6  push    rbp
0x1800419b7  push    rdi
0x1800419b8  push    r14
0x1800419ba  lea     rbp, [rsp-420h]
0x1800419c2  sub     rsp, 520h
0x1800419c9  mov     rax, cs:__security_cookie
0x1800419d0  xor     rax, rsp
0x1800419d3  mov     [rbp+430h+var_20], rax
0x1800419da  mov     rsi, rcx
0x1800419dd  xor     r14d, r14d
0x1800419e0  mov     [rsp+530h+Environment], r14
0x1800419e5  movzx   r8d, dl
0x1800419e9  xor     r8d, 1; bInherit
0x1800419ed  xor     edx, edx; hToken
0x1800419ef  lea     rcx, [rsp+530h+Environment]; lpEnvironment
0x1800419f4  call    cs:__imp_CreateEnvironmentBlock
0x1800419fa  test    eax, eax
0x1800419fc  jnz     short loc_180041A0C
0x1800419fe  call    cs:__imp_GetLastError
0x180041a04  test    eax, eax
0x180041a06  jnz     loc_180041BB6
0x180041a0c  lea     rax, off_18009F2F0
0x180041a13  mov     [rbp+430h+var_490], rax
0x180041a17  lea     rax, [rsp+530h+Environment]
0x180041a1c  mov     [rbp+430h+var_488], rax
0x180041a20  lea     rax, [rbp+430h+var_490]
0x180041a24  mov     [rbp+430h+var_458], rax
0x180041a28  xor     r8d, r8d; int
0x180041a2b  xor     edx, edx; int
0x180041a2d  mov     rcx, rsi; struct lua_State *
0x180041a30  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x180041a35  mov     rbx, [rsp+530h+Environment]
0x180041a3a  test    rbx, rbx
0x180041a3d  jz      loc_180041B55
0x180041a43  cmp     [rbx], r14w
0x180041a47  jz      loc_180041B55
0x180041a4d  mov     edx, 3Dh ; '='; Ch
0x180041a52  mov     rcx, rbx; Str
0x180041a55  call    cs:__imp_wcschr
0x180041a5b  mov     rdi, rax
0x180041a5e  test    rax, rax
0x180041a61  jz      loc_180041B39
0x180041a67  mov     r8, rax
0x180041a6a  mov     rdx, rbx
0x180041a6d  lea     rcx, [rsp+530h+var_4D8]
0x180041a72  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180041a77  nop
0x180041a78  lea     rdx, [rdi+2]
0x180041a7c  xorps   xmm0, xmm0
0x180041a7f  movups  [rsp+530h+var_4F8], xmm0
0x180041a84  xorps   xmm1, xmm1
0x180041a87  movdqu  [rsp+530h+var_4E8], xmm1
0x180041a8d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180041a91  inc     r8
0x180041a94  cmp     [rdx+r8*2], r14w
0x180041a99  jnz     short loc_180041A91
0x180041a9b  lea     rcx, [rsp+530h+var_4F8]
0x180041aa0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180041aa5  nop
0x180041aa6  lea     rdx, [rsp+530h+var_4F8]
0x180041aab  cmp     qword ptr [rsp+530h+var_4E8+8], 7
0x180041ab1  cmova   rdx, qword ptr [rsp+530h+var_4F8]
0x180041ab7  lea     rcx, [rsp+530h+var_4B8]
0x180041abc  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x180041ac1  nop
0x180041ac2  cmp     qword ptr [rax+18h], 0Fh
0x180041ac7  jbe     short loc_180041ACC
0x180041ac9  mov     rax, [rax]
0x180041acc  mov     rdx, rax; char *
0x180041acf  mov     rcx, rsi; struct lua_State *
0x180041ad2  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x180041ad7  nop
0x180041ad8  lea     rcx, [rsp+530h+var_4B8]
0x180041add  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180041ae2  lea     rdx, [rsp+530h+var_4D8]
0x180041ae7  cmp     [rsp+530h+var_4C0], 7
0x180041aed  cmova   rdx, [rsp+530h+var_4D8]
0x180041af3  lea     rcx, [rsp+530h+var_4B8]
0x180041af8  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x180041afd  nop
0x180041afe  cmp     qword ptr [rax+18h], 0Fh
0x180041b03  jbe     short loc_180041B08
0x180041b05  mov     rax, [rax]
0x180041b08  mov     r8, rax; char *
0x180041b0b  mov     edx, 0FFFFFFFEh; int
0x180041b10  mov     rcx, rsi; struct lua_State *
0x180041b13  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x180041b18  nop
0x180041b19  lea     rcx, [rsp+530h+var_4B8]
0x180041b1e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180041b23  nop
0x180041b24  lea     rcx, [rsp+530h+var_4F8]
0x180041b29  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041b2e  nop
0x180041b2f  lea     rcx, [rsp+530h+var_4D8]
0x180041b34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041b39  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041b3d  inc     rax
0x180041b40  cmp     [rbx+rax*2], r14w
0x180041b45  jnz     short loc_180041B3D
0x180041b47  lea     rbx, [rbx+rax*2]
0x180041b4b  add     rbx, 2
0x180041b4f  jnz     loc_180041A43
0x180041b55  mov     rcx, [rbp+430h+var_458]
0x180041b59  test    rcx, rcx
0x180041b5c  jz      short loc_180041B8A
0x180041b5e  mov     rax, [rcx]
0x180041b61  mov     rax, [rax+10h]
0x180041b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b6a  mov     rcx, [rbp+430h+var_458]
0x180041b6e  test    rcx, rcx
0x180041b71  jz      short loc_180041B8A
0x180041b73  mov     rax, [rcx]
0x180041b76  lea     rdx, [rbp+430h+var_490]
0x180041b7a  cmp     rcx, rdx
0x180041b7d  setnz   dl
0x180041b80  mov     rax, [rax+20h]
0x180041b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b89  nop
0x180041b8a  mov     eax, 1
0x180041b8f  mov     rcx, [rbp+430h+var_20]
0x180041b96  xor     rcx, rsp; StackCookie
0x180041b99  call    __security_check_cookie
0x180041b9e  lea     r11, [rsp+530h+var_10]
0x180041ba6  mov     rbx, [r11+28h]
0x180041baa  mov     rsi, [r11+30h]
0x180041bae  mov     rsp, r11
0x180041bb1  pop     r14
0x180041bb3  pop     rdi
0x180041bb4  pop     rbp
0x180041bb5  retn
0x180041bb6  mov     edx, eax; __int64
0x180041bb8  mov     [rsp+530h+var_508], 12h
0x180041bc0  lea     rax, aEnvQuery; "env_query"
0x180041bc7  mov     [rsp+530h+var_510], rax
0x180041bcc  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180041bd3  xor     r8d, r8d; void *
0x180041bd6  lea     rcx, [rbp+430h+pExceptionObject]; this
0x180041bda  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180041bdf  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180041be6  lea     rcx, [rbp+430h+pExceptionObject]; pExceptionObject
0x180041bea  call    _CxxThrowException_0
```
