# CSWbemSink::CSWbemSink(void)

- ea: `0x180026e70`
- end: `0x180026fe5`
- name: `??0CSWbemSink@@QEAA@XZ`
- size: `373`
- prototype: `CSWbemSink *__fastcall(CSWbemSink *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180010c90`

## callees

- `0x1800126c0`
- `0x180026c9c`
- `0x180026e70`
- `0x180036010`

## import_xrefs

- `msvcrt!malloc` at `0x180026f3f`
- `msvcrt!malloc` at `0x180026f3f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180026f8e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180026f8e`

## string_xrefs

- `0x180026f19`: `SWbemSink`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CSWbemSink *__fastcall CSWbemSink::CSWbemSink(CSWbemSink *this)
{
  char *v2; // rcx
  void *v3; // rax
  int i; // edx
  __int64 v5; // rcx
  CConnectionPoint *v6; // rax
  const struct _GUID *v7; // r8
  CConnectionPoint *v8; // rax
  GUID v10; // [rsp+30h] [rbp-28h] BYREF
  GUID v11; // [rsp+40h] [rbp-18h] BYREF

  *(_QWORD *)this = &CSWbemSink::`vftable'{for `ISWbemSink'};
  *((_QWORD *)this + 1) = &CSWbemSink::`vftable'{for `IConnectionPointContainer'};
  *((_QWORD *)this + 2) = &CSWbemSink::`vftable'{for `IProvideClassInfo2'};
  *((_QWORD *)this + 3) = &CSWbemSink::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 4) = &CSWbemSink::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 5) = &CSWbemSink::`vftable'{for `ISWbemPrivateSinkLocator'};
  v2 = (char *)this + 48;
  *(_QWORD *)v2 = &CDispatchHelp::`vftable';
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 4) = 0;
  *((_QWORD *)v2 + 5) = 0;
  *((_QWORD *)v2 + 1) = 0;
  *((_DWORD *)v2 + 4) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 18) = 2;
  *((_DWORD *)this + 40) = 0;
  v10 = CLSID_SWbemSink;
  v11 = IID_ISWbemSink;
  CDispatchHelp::SetObj((CDispatchHelp *)v2, (struct IDispatch *)this, &v11, &v10, L"SWbemSink");
  v3 = malloc(16LL * *((int *)this + 36));
  *((_QWORD *)this + 17) = v3;
  if ( v3 )
  {
    for ( i = 0; i < *((_DWORD *)this + 36); ++i )
    {
      v5 = 2LL * i;
      *(_QWORD *)(*((_QWORD *)this + 17) + 8 * v5) = 0;
      *(_QWORD *)(*((_QWORD *)this + 17) + 8 * v5 + 8) = 0;
    }
  }
  *((_QWORD *)this + 16) = 0;
  v6 = (CConnectionPoint *)CWin32DefaultArena::WbemMemAlloc(0x48u);
  if ( v6 )
  {
    v8 = CConnectionPoint::CConnectionPoint(v6, this, v7);
    *((_QWORD *)this + 16) = v8;
    if ( v8 )
      (*(void (__fastcall **)(CConnectionPoint *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  else
  {
    *((_QWORD *)this + 16) = 0;
  }
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180026e70  mov     r11, rsp
0x180026e73  mov     [r11+18h], rbx
0x180026e77  mov     [r11+8], rcx
0x180026e7b  push    rsi
0x180026e7c  sub     rsp, 50h
0x180026e80  mov     rbx, rcx
0x180026e83  lea     rax, ??_7CSWbemSink@@6BISWbemSink@@@; const CSWbemSink::`vftable'{for `ISWbemSink'}
0x180026e8a  mov     [rcx], rax
0x180026e8d  lea     rax, ??_7CSWbemSink@@6BIConnectionPointContainer@@@; const CSWbemSink::`vftable'{for `IConnectionPointContainer'}
0x180026e94  mov     [rcx+8], rax
0x180026e98  lea     rax, ??_7CSWbemSink@@6BIProvideClassInfo2@@@; const CSWbemSink::`vftable'{for `IProvideClassInfo2'}
0x180026e9f  mov     [rcx+10h], rax
0x180026ea3  lea     rax, ??_7CSWbemSink@@6BIObjectSafety@@@; const CSWbemSink::`vftable'{for `IObjectSafety'}
0x180026eaa  mov     [rcx+18h], rax
0x180026eae  lea     rax, ??_7CSWbemSink@@6BISupportErrorInfo@@@; const CSWbemSink::`vftable'{for `ISupportErrorInfo'}
0x180026eb5  mov     [rcx+20h], rax
0x180026eb9  lea     rax, ??_7CSWbemSink@@6BISWbemPrivateSinkLocator@@@; const CSWbemSink::`vftable'{for `ISWbemPrivateSinkLocator'}
0x180026ec0  mov     [rcx+28h], rax
0x180026ec4  add     rcx, 30h ; '0'; this
0x180026ec8  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x180026ecf  mov     [rcx], rax
0x180026ed2  xor     esi, esi
0x180026ed4  mov     [rcx+18h], rsi
0x180026ed8  mov     [rcx+20h], rsi
0x180026edc  mov     [rcx+28h], rsi
0x180026ee0  mov     [rcx+8], rsi
0x180026ee4  mov     [rcx+10h], esi
0x180026ee7  mov     [rbx+98h], rsi
0x180026eee  mov     qword ptr [rbx+90h], 2
0x180026ef9  mov     [rbx+0A0h], esi
0x180026eff  movups  xmm0, xmmword ptr cs:CLSID_SWbemSink.Data1
0x180026f06  movdqu  [rsp+58h+var_28], xmm0
0x180026f0c  movups  xmm1, xmmword ptr cs:IID_ISWbemSink.Data1
0x180026f13  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm1
0x180026f19  lea     rax, aSwbemsink; "SWbemSink"
0x180026f20  mov     [r11-38h], rax
0x180026f24  lea     r9, [r11-28h]; struct _GUID *
0x180026f28  lea     r8, [r11-18h]; struct _GUID *
0x180026f2c  mov     rdx, rbx; struct IDispatch *
0x180026f2f  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x180026f34  movsxd  rcx, dword ptr [rbx+90h]
0x180026f3b  shl     rcx, 4; Size
0x180026f3f  call    cs:__imp_malloc
0x180026f45  mov     [rbx+88h], rax
0x180026f4c  test    rax, rax
0x180026f4f  jz      short loc_180026F82
0x180026f51  mov     edx, esi
0x180026f53  cmp     [rbx+90h], esi
0x180026f59  jle     short loc_180026F82
0x180026f5b  movsxd  rcx, edx
0x180026f5e  add     rcx, rcx
0x180026f61  mov     rax, [rbx+88h]
0x180026f68  mov     [rax+rcx*8], rsi
0x180026f6c  mov     rax, [rbx+88h]
0x180026f73  mov     [rax+rcx*8+8], rsi
0x180026f78  inc     edx
0x180026f7a  cmp     edx, [rbx+90h]
0x180026f80  jl      short loc_180026F5B
0x180026f82  mov     [rbx+80h], rsi
0x180026f89  mov     ecx, 48h ; 'H'
0x180026f8e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180026f94  mov     [rsp+58h+arg_8], rax
0x180026f99  test    rax, rax
0x180026f9c  jz      short loc_180026FC9
0x180026f9e  mov     rdx, rbx; struct CSWbemSink *
0x180026fa1  mov     rcx, rax; this
0x180026fa4  call    ??0CConnectionPoint@@QEAA@PEAVCSWbemSink@@AEBU_GUID@@@Z; CConnectionPoint::CConnectionPoint(CSWbemSink *,_GUID const &)
0x180026fa9  mov     rdx, rax
0x180026fac  mov     [rbx+80h], rax
0x180026fb3  test    rax, rax
0x180026fb6  jz      short loc_180026FD0
0x180026fb8  mov     rcx, [rax]
0x180026fbb  mov     rax, [rcx+8]
0x180026fbf  mov     rcx, rdx
0x180026fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fc7  jmp     short loc_180026FD0
0x180026fc9  mov     [rbx+80h], rsi
0x180026fd0  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180026fd7  mov     rax, rbx
0x180026fda  mov     rbx, [rsp+58h+arg_10]
0x180026fdf  add     rsp, 50h
0x180026fe3  pop     rsi
0x180026fe4  retn
```
