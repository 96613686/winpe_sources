# DAV_WEB_CONFIG_VALIDATOR::Initialize(void)

- ea: `0x180011514`
- end: `0x180011703`
- name: `?Initialize@DAV_WEB_CONFIG_VALIDATOR@@QEAAJXZ`
- size: `495`
- prototype: `__int64 __fastcall(DAV_WEB_CONFIG_VALIDATOR *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800119c4`

## callees

- `0x1800043b0`
- `0x180005604`
- `0x180011514`
- `0x180019a30`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800115df`
- `msvcrt!_wcsicmp` at `0x1800115df`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800116c2`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800116c2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011625`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011666`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011625`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011666`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001153e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011548`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001153e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011548`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001157b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011585`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011635`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001163f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011677`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011681`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800116d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800116df`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001157b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011585`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011635`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001163f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011677`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011681`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800116d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800116df`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180011655`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180011698`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180011655`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180011698`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001156b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001156b`

## string_xrefs

- `0x1800116a9`: `web.config.tmp`

## pseudocode

```c
__int64 __fastcall DAV_WEB_CONFIG_VALIDATOR::Initialize(DAV_WEB_CONFIG_VALIDATOR *this)
{
  const unsigned __int16 *v2; // rdx
  __int64 v3; // r8
  int v4; // edi
  __int64 v6; // rax
  const wchar_t *v7; // rax
  int v8; // r8d
  STRU *v9; // rdi
  int v10; // esi
  int v11; // r14d
  int TempFileName; // ebx
  _BYTE v13[32]; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 *v14; // [rsp+50h] [rbp-39h]
  _BYTE v15[56]; // [rsp+68h] [rbp-21h] BYREF

  STRU::STRU((STRU *)v13);
  STRU::STRU((STRU *)v15);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  v4 = STRU::Copy((STRU *)v13, v2, v3 - 10);
  if ( v4 < 0
    || (v4 = BuildMetaPathForUri(
               *((struct IHttpContext **)this + 1),
               0,
               v14,
               (DAV_WEB_CONFIG_VALIDATOR *)((char *)this + 160),
               0),
        v4 < 0) )
  {
    STRU::~STRU((STRU *)v15);
    STRU::~STRU((STRU *)v13);
    return (unsigned int)v4;
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
    v7 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    if ( _wcsicmp(*((const wchar_t **)this + 24), v7) )
    {
      if ( STATIC_WSTRING_HASH::FindKey(*((STATIC_WSTRING_HASH **)this + 3), v14, v8) )
        *((_DWORD *)this + 54) = 5;
      else
        *((_DWORD *)this + 54) = 0;
    }
    else
    {
      *((_DWORD *)this + 54) = 4;
    }
    v9 = (DAV_WEB_CONFIG_VALIDATOR *)((char *)this + 48);
    v10 = STRU::Copy((DAV_WEB_CONFIG_VALIDATOR *)((char *)this + 48), *((const unsigned __int16 **)this + 4));
    if ( v10 >= 0 )
    {
      STRU::SetLen((DAV_WEB_CONFIG_VALIDATOR *)((char *)this + 48), *((_DWORD *)this + 24) - 10);
      v11 = STRU::Copy((DAV_WEB_CONFIG_VALIDATOR *)((char *)this + 104), *((const unsigned __int16 **)this + 5));
      if ( v11 >= 0 )
      {
        STRU::SetLen((DAV_WEB_CONFIG_VALIDATOR *)((char *)this + 104), *((_DWORD *)this + 38) - 10);
        TempFileName = CreateTempFileName(
                         *((struct IBaseFileSystem **)this + 2),
                         L"web.config.tmp",
                         (DAV_WEB_CONFIG_VALIDATOR *)((char *)this + 104),
                         (struct STRU *)v15);
        if ( TempFileName >= 0 )
        {
          TempFileName = STRU::Append(v9, (const struct STRU *)v15);
          if ( TempFileName >= 0 )
            TempFileName = 0;
        }
        STRU::~STRU((STRU *)v15);
        STRU::~STRU((STRU *)v13);
        return (unsigned int)TempFileName;
      }
      else
      {
        STRU::~STRU((STRU *)v15);
        STRU::~STRU((STRU *)v13);
        return (unsigned int)v11;
      }
    }
    else
    {
      STRU::~STRU((STRU *)v15);
      STRU::~STRU((STRU *)v13);
      return (unsigned int)v10;
    }
  }
}

```

## disassembly

```asm
0x180011514  push    rbp
0x180011516  push    rbx
0x180011517  push    rsi
0x180011518  push    rdi
0x180011519  push    r14
0x18001151b  push    r15
0x18001151d  lea     rbp, [rsp-2Fh]
0x180011522  sub     rsp, 0B8h
0x180011529  mov     rax, cs:__security_cookie
0x180011530  xor     rax, rsp
0x180011533  mov     [rbp+57h+var_40], rax
0x180011537  mov     rbx, rcx
0x18001153a  lea     rcx, [rbp+57h+var_B0]
0x18001153e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011544  lea     rcx, [rbp+57h+var_78]
0x180011548  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001154e  mov     rdx, [rbx+20h]
0x180011552  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011556  xor     r15d, r15d
0x180011559  inc     r8
0x18001155c  cmp     [rdx+r8*2], r15w
0x180011561  jnz     short loc_180011559
0x180011563  add     r8d, 0FFFFFFF6h
0x180011567  lea     rcx, [rbp+57h+var_B0]
0x18001156b  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180011571  mov     edi, eax
0x180011573  test    eax, eax
0x180011575  jns     short loc_180011592
0x180011577  lea     rcx, [rbp+57h+var_78]
0x18001157b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011581  lea     rcx, [rbp+57h+var_B0]
0x180011585  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001158b  mov     eax, edi
0x18001158d  jmp     loc_1800116E7
0x180011592  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x180011596  lea     r9, [rbx+0A0h]; struct STRU *
0x18001159d  mov     rcx, [rbx+8]; struct IHttpContext *
0x1800115a1  xor     edx, edx; struct INativeConfigurationSystem *
0x1800115a3  mov     [rsp+0E0h+var_C0], r15; struct INativeSectionException **
0x1800115a8  call    ?BuildMetaPathForUri@@YAJPEAVIHttpContext@@PEAVINativeConfigurationSystem@@PEBGPEAVSTRU@@PEAPEAVINativeSectionException@@@Z; BuildMetaPathForUri(IHttpContext *,INativeConfigurationSystem *,ushort const *,STRU *,INativeSectionException * *)
0x1800115ad  mov     edi, eax
0x1800115af  test    eax, eax
0x1800115b1  js      short loc_180011577
0x1800115b3  mov     rcx, [rbx+8]
0x1800115b7  mov     rax, [rcx]
0x1800115ba  mov     rax, [rax+8]
0x1800115be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115c3  mov     rdx, rax
0x1800115c6  mov     rcx, [rax]
0x1800115c9  mov     rax, [rcx+10h]
0x1800115cd  mov     rcx, rdx
0x1800115d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115d5  mov     rcx, [rbx+0C0h]; String1
0x1800115dc  mov     rdx, rax; String2
0x1800115df  call    cs:__imp__wcsicmp
0x1800115e5  test    eax, eax
0x1800115e7  jnz     short loc_1800115F5
0x1800115e9  mov     dword ptr [rbx+0D8h], 4
0x1800115f3  jmp     short loc_18001161A
0x1800115f5  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x1800115f9  mov     rcx, [rbx+18h]; this
0x1800115fd  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180011602  test    rax, rax
0x180011605  jnz     short loc_180011610
0x180011607  mov     [rbx+0D8h], r15d
0x18001160e  jmp     short loc_18001161A
0x180011610  mov     dword ptr [rbx+0D8h], 5
0x18001161a  mov     rdx, [rbx+20h]
0x18001161e  lea     rdi, [rbx+30h]
0x180011622  mov     rcx, rdi
0x180011625  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001162b  mov     esi, eax
0x18001162d  test    eax, eax
0x18001162f  jns     short loc_18001164C
0x180011631  lea     rcx, [rbp+57h+var_78]
0x180011635  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001163b  lea     rcx, [rbp+57h+var_B0]
0x18001163f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011645  mov     eax, esi
0x180011647  jmp     loc_1800116E7
0x18001164c  mov     edx, [rbx+60h]
0x18001164f  mov     rcx, rdi
0x180011652  sub     edx, 0Ah
0x180011655  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001165b  mov     rdx, [rbx+28h]
0x18001165f  lea     rsi, [rbx+68h]
0x180011663  mov     rcx, rsi
0x180011666  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001166c  mov     r14d, eax
0x18001166f  test    eax, eax
0x180011671  jns     short loc_18001168C
0x180011673  lea     rcx, [rbp+57h+var_78]
0x180011677  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001167d  lea     rcx, [rbp+57h+var_B0]
0x180011681  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011687  mov     eax, r14d
0x18001168a  jmp     short loc_1800116E7
0x18001168c  mov     edx, [rbx+98h]
0x180011692  mov     rcx, rsi
0x180011695  sub     edx, 0Ah
0x180011698  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001169e  mov     rcx, [rbx+10h]; struct IBaseFileSystem *
0x1800116a2  lea     r9, [rbp+57h+var_78]; struct STRU *
0x1800116a6  mov     r8, rsi; struct STRU *
0x1800116a9  lea     rdx, aWebConfigTmp; "web.config.tmp"
0x1800116b0  call    ?CreateTempFileName@@YAJPEAVIBaseFileSystem@@PEBGPEAVSTRU@@2@Z; CreateTempFileName(IBaseFileSystem *,ushort const *,STRU *,STRU *)
0x1800116b5  mov     ebx, eax
0x1800116b7  test    eax, eax
0x1800116b9  js      short loc_1800116D1
0x1800116bb  lea     rdx, [rbp+57h+var_78]
0x1800116bf  mov     rcx, rdi
0x1800116c2  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800116c8  mov     ebx, eax
0x1800116ca  test    eax, eax
0x1800116cc  js      short loc_1800116D1
0x1800116ce  mov     ebx, r15d
0x1800116d1  lea     rcx, [rbp+57h+var_78]
0x1800116d5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800116db  lea     rcx, [rbp+57h+var_B0]
0x1800116df  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800116e5  mov     eax, ebx
0x1800116e7  mov     rcx, [rbp+57h+var_40]
0x1800116eb  xor     rcx, rsp; StackCookie
0x1800116ee  call    __security_check_cookie
0x1800116f3  add     rsp, 0B8h
0x1800116fa  pop     r15
0x1800116fc  pop     r14
0x1800116fe  pop     rdi
0x1800116ff  pop     rsi
0x180011700  pop     rbx
0x180011701  pop     rbp
0x180011702  retn
```
