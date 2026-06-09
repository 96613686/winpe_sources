# EvtArchiveExportedLog

- ea: `0x180025d10`
- end: `0x180025f3d`
- name: `EvtArchiveExportedLog`
- size: `557`
- prototype: `BOOL __stdcall(EVT_HANDLE Session, LPCWSTR LogFilePath, LCID Locale, DWORD Flags)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180006aec`
- `0x180007940`
- `0x180007aa0`
- `0x18000a724`
- `0x18000bf5c`
- `0x18000c404`
- `0x180013f6c`
- `0x180023548`
- `0x180025d10`
- `0x180028960`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025f17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025f17`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __stdcall EvtArchiveExportedLog(EVT_HANDLE Session, LPCWSTR LogFilePath, LCID Locale, DWORD Flags)
{
  BOOL v7; // ebx
  DWORD v8; // edi
  struct Session *v10; // [rsp+20h] [rbp-C8h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-B0h]
  int v13; // [rsp+40h] [rbp-A8h]
  int v14; // [rsp+44h] [rbp-A4h]
  int v15; // [rsp+48h] [rbp-A0h]
  __int128 v16; // [rsp+50h] [rbp-98h] BYREF
  __int64 v17; // [rsp+60h] [rbp-88h]
  int v18; // [rsp+68h] [rbp-80h]
  int v19; // [rsp+6Ch] [rbp-7Ch]
  int v20; // [rsp+70h] [rbp-78h]
  __int128 v21; // [rsp+78h] [rbp-70h] BYREF
  __int64 v22; // [rsp+88h] [rbp-60h]
  int v23; // [rsp+90h] [rbp-58h]
  int v24; // [rsp+94h] [rbp-54h]
  int v25; // [rsp+98h] [rbp-50h]
  wchar_t *v26[4]; // [rsp+A0h] [rbp-48h] BYREF
  EvtException *v27; // [rsp+C0h] [rbp-28h] BYREF

  LastErrInfo::Reset((LastErrInfo *)Session);
  try
  {
    v7 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v12 = 0;
      v13 = 87;
      v14 = -1;
      v15 = 1293;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !LogFilePath )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      v16 = 0;
      v17 = 0;
      v18 = 87;
      v19 = -1;
      v20 = 1298;
      throw (EvtException *)&v16;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v26);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v26,
                             LogFilePath) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 14);
      }
      v21 = 0;
      v22 = 0;
      v23 = 14;
      v24 = -1;
      v25 = 1304;
      throw (EvtException *)&v21;
    }
    FullyQualifyFilePath((__int64)v26, LogFilePath);
    GetSession(&v10);
    LogHandle::LocalizeExportLog(v10, Locale, v26[0], 0);
    v8 = 0;
    wmi::AutoRef<Object>::Release(&v10);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v26);
  }
  catch ( EvtException *v27 )
  {
    v7 = 0;
    v8 = *((_DWORD *)v27 + 6);
  }
  SetLastError(v8);
  LOBYTE(v7) = v8 == 0;
  return v7;
}

```

## disassembly

```asm
0x180025d10  mov     [rsp+arg_0], rbx
0x180025d15  mov     [rsp+arg_8], rsi
0x180025d1a  push    rdi
0x180025d1b  push    r14
0x180025d1d  push    r15
0x180025d1f  sub     rsp, 0D0h
0x180025d26  mov     esi, r9d
0x180025d29  mov     r15d, r8d
0x180025d2c  mov     rdi, rdx
0x180025d2f  mov     r14, rcx
0x180025d32  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x180025d37  xor     ebx, ebx
0x180025d39  test    esi, esi
0x180025d3b  jz      short loc_180025DAA
0x180025d3d  lea     rax, WPP_GLOBAL_Control
0x180025d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d4b  cmp     rcx, rax
0x180025d4e  jz      short loc_180025D73
0x180025d50  test    byte ptr [rcx+1Ch], 1
0x180025d54  jz      short loc_180025D73
0x180025d56  cmp     byte ptr [rcx+19h], 2
0x180025d5a  jb      short loc_180025D73
0x180025d5c  lea     edx, [rbx+28h]
0x180025d5f  lea     r9d, [rbx+57h]
0x180025d63  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180025d6a  mov     rcx, [rcx+10h]
0x180025d6e  call    WPP_SF_D
0x180025d73  xorps   xmm0, xmm0
0x180025d76  movdqu  [rsp+0E8h+pExceptionObject], xmm0
0x180025d7c  mov     [rsp+0E8h+var_B0], rbx
0x180025d81  mov     [rsp+0E8h+var_A8], 57h ; 'W'
0x180025d89  mov     [rsp+0E8h+var_A4], 0FFFFFFFFh
0x180025d91  mov     [rsp+0E8h+var_A0], 50Dh
0x180025d99  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180025da0  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180025da5  call    _CxxThrowException_0
0x180025daa  test    rdi, rdi
0x180025dad  jnz     short loc_180025E1C
0x180025daf  lea     rax, WPP_GLOBAL_Control
0x180025db6  mov     rcx, cs:WPP_GLOBAL_Control
0x180025dbd  cmp     rcx, rax
0x180025dc0  jz      short loc_180025DE5
0x180025dc2  test    byte ptr [rcx+1Ch], 1
0x180025dc6  jz      short loc_180025DE5
0x180025dc8  cmp     byte ptr [rcx+19h], 2
0x180025dcc  jb      short loc_180025DE5
0x180025dce  lea     edx, [rdi+29h]
0x180025dd1  lea     r9d, [rdi+57h]
0x180025dd5  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180025ddc  mov     rcx, [rcx+10h]
0x180025de0  call    WPP_SF_D
0x180025de5  xorps   xmm0, xmm0
0x180025de8  movdqu  [rsp+0E8h+var_98], xmm0
0x180025dee  mov     [rsp+0E8h+var_88], rbx
0x180025df3  mov     [rsp+0E8h+var_80], 57h ; 'W'
0x180025dfb  mov     [rsp+0E8h+var_7C], 0FFFFFFFFh
0x180025e03  mov     [rsp+0E8h+var_78], 512h
0x180025e0b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180025e12  lea     rcx, [rsp+0E8h+var_98]; pExceptionObject
0x180025e17  call    _CxxThrowException_0
0x180025e1c  lea     rcx, [rsp+0E8h+var_48]
0x180025e24  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180025e29  nop
0x180025e2a  mov     rdx, rdi
0x180025e2d  lea     rcx, [rsp+0E8h+var_48]
0x180025e35  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180025e3a  test    al, al
0x180025e3c  jnz     short loc_180025EB9
0x180025e3e  lea     rax, WPP_GLOBAL_Control
0x180025e45  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e4c  cmp     rcx, rax
0x180025e4f  jz      short loc_180025E76
0x180025e51  test    byte ptr [rcx+1Ch], 1
0x180025e55  jz      short loc_180025E76
0x180025e57  cmp     byte ptr [rcx+19h], 2
0x180025e5b  jb      short loc_180025E76
0x180025e5d  mov     edx, 2Ah ; '*'
0x180025e62  lea     r9d, [rdx-1Ch]
0x180025e66  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180025e6d  mov     rcx, [rcx+10h]
0x180025e71  call    WPP_SF_D
0x180025e76  xorps   xmm0, xmm0
0x180025e79  movdqu  [rsp+0E8h+var_70], xmm0
0x180025e7f  mov     [rsp+0E8h+var_60], rbx
0x180025e87  mov     [rsp+0E8h+var_58], 0Eh
0x180025e92  mov     [rsp+0E8h+var_54], 0FFFFFFFFh
0x180025e9d  mov     [rsp+0E8h+var_50], 518h
0x180025ea8  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180025eaf  lea     rcx, [rsp+0E8h+var_70]; pExceptionObject
0x180025eb4  call    _CxxThrowException_0
0x180025eb9  mov     rdx, rdi
0x180025ebc  lea     rcx, [rsp+0E8h+var_48]
0x180025ec4  call    FullyQualifyFilePath
0x180025ec9  mov     rdx, r14
0x180025ecc  lea     rcx, [rsp+0E8h+var_C8]; void *
0x180025ed1  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x180025ed6  nop
0x180025ed7  xor     r9d, r9d; unsigned int
0x180025eda  mov     r8, [rsp+0E8h+var_48]; wchar_t *
0x180025ee2  mov     edx, r15d; unsigned int
0x180025ee5  mov     rcx, [rsp+0E8h+var_C8]; this
0x180025eea  call    ?LocalizeExportLog@LogHandle@@SAXPEAVSession@@KPEB_WK@Z; LogHandle::LocalizeExportLog(Session *,ulong,wchar_t const *,ulong)
0x180025eef  mov     edi, ebx
0x180025ef1  lea     rcx, [rsp+0E8h+var_C8]; void *
0x180025ef6  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180025efb  nop
0x180025efc  lea     rcx, [rsp+0E8h+var_48]
0x180025f04  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180025f09  nop
0x180025f0a  jmp     short loc_180025F15
0x180025f0c  xor     ebx, ebx
0x180025f0e  mov     edi, [rsp+0E8h+arg_18]
0x180025f15  mov     ecx, edi; dwErrCode
0x180025f17  call    cs:__imp_SetLastError
0x180025f1d  test    edi, edi
0x180025f1f  setz    bl
0x180025f22  mov     eax, ebx
0x180025f24  lea     r11, [rsp+0E8h+var_18]
0x180025f2c  mov     rbx, [r11+20h]
0x180025f30  mov     rsi, [r11+28h]
0x180025f34  mov     rsp, r11
0x180025f37  pop     r15
0x180025f39  pop     r14
0x180025f3b  pop     rdi
0x180025f3c  retn
```
