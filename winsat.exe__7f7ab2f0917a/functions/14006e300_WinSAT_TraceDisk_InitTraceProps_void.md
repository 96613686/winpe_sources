# WinSAT::TraceDisk::InitTraceProps(void)

- ea: `0x14006e300`
- end: `0x14006e4ff`
- name: `?InitTraceProps@TraceDisk@WinSAT@@AEBAPEAU_EVENT_TRACE_PROPERTIES@@XZ`
- size: `511`
- prototype: `struct _EVENT_TRACE_PROPERTIES *__fastcall(WinSAT::TraceDisk *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14006e720`
- `0x14006e8a4`

## callees

- `0x140003611`
- `0x1400085b4`
- `0x14003ec14`
- `0x140040bf0`
- `0x14006e300`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14006e424`
- `KERNEL32!SetLastError` at `0x14006e4ed`
- `KERNEL32!SetLastError` at `0x14006e424`
- `KERNEL32!SetLastError` at `0x14006e4ed`
- `msvcrt!malloc` at `0x14006e36f`
- `msvcrt!malloc` at `0x14006e36f`
- `msvcrt!free` at `0x14006e42d`
- `msvcrt!free` at `0x14006e42d`
- `ntdll!RtlAdjustPrivilege` at `0x14006e4c0`
- `ntdll!RtlAdjustPrivilege` at `0x14006e4c0`

## string_xrefs

- `0x14006e480`: `Enabling EVENT_TRACE_FLAG_IMAGE_LOAD | EVENT_TRACE_FLAG_THREAD | EVENT_TRACE_FLAG_PROCESS`

## pseudocode

```c
struct _EVENT_TRACE_PROPERTIES *__fastcall WinSAT::TraceDisk::InitTraceProps(WinSAT::TraceDisk *this)
{
  __int64 v2; // rdx
  size_t v3; // rbx
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rdi
  DWORD v6; // ecx
  const unsigned __int16 *v7; // rbx
  _QWORD **v8; // rax
  int v9; // eax
  unsigned __int8 OldValue; // [rsp+58h] [rbp+10h] BYREF

  OldValue = 0;
  if ( **(_QWORD **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)WinSAT::TraceDisk::sc_LoggerName) > 0x104u
    || **((_QWORD **)this + 1) > 0x104u )
  {
    return 0;
  }
  v2 = **((_QWORD **)this + 1)
     + **(_QWORD **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)WinSAT::TraceDisk::sc_LoggerName);
  v3 = 2 * v2 + 124;
  if ( (unsigned __int64)(2 * v2 + 4) > 0xFF87 )
  {
    v6 = 534;
    goto LABEL_16;
  }
  v4 = (unsigned __int16 *)malloc(2 * v2 + 124);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 8;
LABEL_16:
    SetLastError(v6);
    return 0;
  }
  memset_0(v4, 0, v3);
  *(_DWORD *)v5 = v3;
  *((_DWORD *)v5 + 11) = 0x20000;
  *((_DWORD *)v5 + 10) = 1;
  *((_DWORD *)v5 + 16) = 33554433;
  *((_DWORD *)v5 + 12) = 1024;
  *((_DWORD *)v5 + 13) = 5;
  *((_DWORD *)v5 + 14) = 50;
  *((_DWORD *)v5 + 15) = 1024;
  *((_DWORD *)v5 + 17) = 0;
  *((_DWORD *)v5 + 19) = 15;
  *((_DWORD *)v5 + 29) = 120;
  *((_DWORD *)v5 + 28) = 2
                       * **(_DWORD **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)WinSAT::TraceDisk::sc_LoggerName)
                       + 122;
  v7 = *(const unsigned __int16 **)(*(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)WinSAT::TraceDisk::sc_LoggerName)
                                  + 24LL);
  v8 = (_QWORD **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)WinSAT::TraceDisk::sc_LoggerName);
  v9 = StringCchCopyW(v5 + 60, **v8 + 1LL, v7);
  if ( v9 < 0
    || (v9 = StringCchCopyW(
               (unsigned __int16 *)((char *)v5 + *((unsigned int *)v5 + 28)),
               **((_QWORD **)this + 1) + 1LL,
               *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 24LL)),
        v9 < 0) )
  {
    SetLastError((unsigned __int16)v9);
    free(v5);
    return 0;
  }
  *((_DWORD *)v5 + 18) = 256;
  if ( **(_QWORD **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_AssessmentDumpFileName) )
  {
    Log_Text_F(
      (__int64)"base\\winsat\\storage\\tracedisk.cpp",
      587,
      "Enabling EVENT_TRACE_FLAG_IMAGE_LOAD | EVENT_TRACE_FLAG_THREAD | EVENT_TRACE_FLAG_PROCESS");
    *((_DWORD *)v5 + 18) |= 7u;
    if ( App::s_Verbose )
    {
      Log_Text_F(
        (__int64)"base\\winsat\\storage\\tracedisk.cpp",
        590,
        "Enabling EVENT_TRACE_FLAG_DISK_IO_INIT - Verbose Mode");
      *((_DWORD *)v5 + 18) |= 0x400u;
    }
    if ( !RtlAdjustPrivilege(0xBu, 1u, 0, &OldValue) )
    {
      Log_Text_F((__int64)"base\\winsat\\storage\\tracedisk.cpp", 596, "Enabling EVENT_TRACE_FLAG_PROFILE");
      *((_DWORD *)v5 + 18) |= 0x1000000u;
    }
  }
  return (struct _EVENT_TRACE_PROPERTIES *)v5;
}

```

## disassembly

```asm
0x14006e300  push    rbx
0x14006e302  push    rsi
0x14006e303  push    rdi
0x14006e304  push    r14
0x14006e306  sub     rsp, 28h
0x14006e30a  mov     rsi, rcx
0x14006e30d  mov     [rsp+48h+OldValue], 0
0x14006e312  lea     r14, ?sc_LoggerName@TraceDisk@WinSAT@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> WinSAT::TraceDisk::sc_LoggerName
0x14006e319  mov     rcx, r14
0x14006e31c  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006e321  mov     ecx, 104h
0x14006e326  mov     rdx, [rax]
0x14006e329  cmp     [rdx], rcx
0x14006e32c  ja      loc_14006E4F3
0x14006e332  mov     rax, [rsi+8]
0x14006e336  cmp     [rax], rcx
0x14006e339  ja      loc_14006E4F3
0x14006e33f  mov     rcx, r14
0x14006e342  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006e347  mov     rcx, [rax]
0x14006e34a  mov     rax, [rsi+8]
0x14006e34e  mov     rdx, [rcx]
0x14006e351  add     rdx, [rax]
0x14006e354  lea     rbx, ds:7Ch[rdx*2]
0x14006e35c  lea     rax, [rbx-78h]
0x14006e360  cmp     rax, 0FF87h
0x14006e366  ja      loc_14006E4E8
0x14006e36c  mov     rcx, rbx; Size
0x14006e36f  call    cs:__imp_malloc
0x14006e375  mov     rdi, rax
0x14006e378  test    rax, rax
0x14006e37b  jnz     short loc_14006E385
0x14006e37d  lea     ecx, [rax+8]
0x14006e380  jmp     loc_14006E4ED
0x14006e385  mov     r8, rbx; Size
0x14006e388  xor     edx, edx; Val
0x14006e38a  mov     rcx, rdi; void *
0x14006e38d  call    memset_0
0x14006e392  mov     rcx, r14
0x14006e395  mov     [rdi], ebx
0x14006e397  mov     dword ptr [rdi+2Ch], 20000h
0x14006e39e  mov     dword ptr [rdi+28h], 1
0x14006e3a5  mov     dword ptr [rdi+40h], 2000001h
0x14006e3ac  mov     dword ptr [rdi+30h], 400h
0x14006e3b3  mov     dword ptr [rdi+34h], 5
0x14006e3ba  mov     dword ptr [rdi+38h], 32h ; '2'
0x14006e3c1  mov     dword ptr [rdi+3Ch], 400h
0x14006e3c8  mov     dword ptr [rdi+44h], 0
0x14006e3cf  mov     dword ptr [rdi+4Ch], 0Fh
0x14006e3d6  mov     dword ptr [rdi+74h], 78h ; 'x'
0x14006e3dd  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006e3e2  mov     rcx, r14
0x14006e3e5  mov     rax, [rax]
0x14006e3e8  mov     edx, [rax]
0x14006e3ea  lea     edx, ds:7Ah[rdx*2]
0x14006e3f1  mov     [rdi+70h], edx
0x14006e3f4  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006e3f9  mov     rcx, r14
0x14006e3fc  mov     rdx, [rax]
0x14006e3ff  mov     rbx, [rdx+18h]
0x14006e403  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006e408  mov     r8, rbx; unsigned __int16 *
0x14006e40b  mov     rcx, [rax]
0x14006e40e  mov     rdx, [rcx]
0x14006e411  lea     rcx, [rdi+78h]; unsigned __int16 *
0x14006e415  inc     rdx; unsigned __int64
0x14006e418  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14006e41d  test    eax, eax
0x14006e41f  jns     short loc_14006E438
0x14006e421  movzx   ecx, ax; dwErrCode
0x14006e424  call    cs:__imp_SetLastError
0x14006e42a  mov     rcx, rdi; Block
0x14006e42d  call    cs:__imp_free
0x14006e433  jmp     loc_14006E4F3
0x14006e438  mov     r8, [rsi+8]
0x14006e43c  mov     ecx, [rdi+70h]
0x14006e43f  add     rcx, rdi; unsigned __int16 *
0x14006e442  mov     rdx, [r8]
0x14006e445  mov     r8, [r8+18h]; unsigned __int16 *
0x14006e449  inc     rdx; unsigned __int64
0x14006e44c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14006e451  test    eax, eax
0x14006e453  js      short loc_14006E421
0x14006e455  lea     rcx, ?s_AssessmentDumpFileName@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_AssessmentDumpFileName
0x14006e45c  mov     dword ptr [rdi+48h], 100h
0x14006e463  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006e468  mov     rcx, [rax]
0x14006e46b  cmp     qword ptr [rcx], 0
0x14006e46f  jz      short loc_14006E4E3
0x14006e471  lea     rbx, aBaseWinsatStor_0; "base\\winsat\\storage\\tracedisk.cpp"
0x14006e478  mov     edx, 24Bh
0x14006e47d  mov     rcx, rbx
0x14006e480  lea     r8, aEnablingEventT_0; "Enabling EVENT_TRACE_FLAG_IMAGE_LOAD | "...
0x14006e487  call    Log_Text_F
0x14006e48c  or      dword ptr [rdi+48h], 7
0x14006e490  cmp     cs:?s_Verbose@App@@2_NA, 0; bool App::s_Verbose
0x14006e497  jz      short loc_14006E4B2
0x14006e499  lea     r8, aEnablingEventT_1; "Enabling EVENT_TRACE_FLAG_DISK_IO_INIT "...
0x14006e4a0  mov     edx, 24Eh
0x14006e4a5  mov     rcx, rbx
0x14006e4a8  call    Log_Text_F
0x14006e4ad  bts     dword ptr [rdi+48h], 0Ah
0x14006e4b2  xor     r8d, r8d; ForThread
0x14006e4b5  lea     r9, [rsp+48h+OldValue]; OldValue
0x14006e4ba  mov     dl, 1; NewValue
0x14006e4bc  lea     ecx, [r8+0Bh]; Privilege
0x14006e4c0  call    cs:__imp_RtlAdjustPrivilege
0x14006e4c6  test    eax, eax
0x14006e4c8  jnz     short loc_14006E4E3
0x14006e4ca  lea     r8, aEnablingEventT; "Enabling EVENT_TRACE_FLAG_PROFILE"
0x14006e4d1  mov     edx, 254h
0x14006e4d6  mov     rcx, rbx
0x14006e4d9  call    Log_Text_F
0x14006e4de  bts     dword ptr [rdi+48h], 18h
0x14006e4e3  mov     rax, rdi
0x14006e4e6  jmp     short loc_14006E4F5
0x14006e4e8  mov     ecx, 216h; dwErrCode
0x14006e4ed  call    cs:__imp_SetLastError
0x14006e4f3  xor     eax, eax
0x14006e4f5  add     rsp, 28h
0x14006e4f9  pop     r14
0x14006e4fb  pop     rdi
0x14006e4fc  pop     rsi
0x14006e4fd  pop     rbx
0x14006e4fe  retn
```
