# WFDSConMgr::CDevQueryHelper::StartQuery(WFDSConMgr::IDevQueryCompleteListener *,bool)

- ea: `0x180028d00`
- end: `0x180029000`
- name: `?StartQuery@CDevQueryHelper@WFDSConMgr@@QEAAXPEAVIDevQueryCompleteListener@2@_N@Z`
- size: `768`
- prototype: `void __fastcall(WFDSConMgr::CDevQueryHelper *__hidden this, struct WFDSConMgr::IDevQueryCompleteListener *, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180025708`
- `0x180042e4c`

## callees

- `0x18000421c`
- `0x180004f38`
- `0x1800059c0`
- `0x18000665c`
- `0x180006740`
- `0x18002315c`
- `0x180023ebc`
- `0x180027e54`
- `0x180028d00`
- `0x18002948c`
- `0x18005c888`
- `0x18005d6c0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f7f`

## string_xrefs

- `0x180028fd5`: `Query already running`
- `0x180028ec5`: `DevCreateObjectQueryFromIdEx failed`
- `0x180028f3c`: `DevCreateObjectQueryEx failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WFDSConMgr::CDevQueryHelper::StartQuery(
        WFDSConMgr::CDevQueryHelper *this,
        struct WFDSConMgr::IDevQueryCompleteListener *a2,
        char a3)
{
  __int64 v6; // rax
  __int64 v7; // r8
  int v8; // edx
  __int64 v9; // rbx
  int v10; // ebp
  __int64 v11; // r14
  unsigned int v12; // r15d
  __int64 v13; // rax
  __int64 v14; // r11
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // r9d
  __int64 v18; // r10
  int v19; // eax
  int v20; // eax
  WFDSConMgr::CDevQueryHelper::CResultWaiter *v21; // [rsp+A0h] [rbp+8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
  }
  WFDSConMgr::CDevQueryHelper::Initialize(this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 56);
    WPP_SF_qDSlq(*(_QWORD *)(v7 + 16), v8, v7, (_DWORD)this, *((_DWORD *)this + 30), v6, a3, (char)a2);
  }
  WFDSConMgr::CriticalSection::Lock((char *)this + 176, &lpCriticalSection);
  if ( (unsigned int)(*((_DWORD *)this + 88) - 2) <= 1 )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CDevQueryHelper::StartQuery",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\devqueryhelper.cpp",
      197,
      L"Query already running",
      this);
  *((_BYTE *)this + 336) = a3;
  if ( a2 )
  {
    v21 = (WFDSConMgr::CDevQueryHelper::CResultWaiter *)operator new(0xA8u);
    v21 = WFDSConMgr::CDevQueryHelper::CResultWaiter::CResultWaiter(
            v21,
            (WFDSConMgr::CDevQueryHelper *)((char *)this + 216),
            this,
            a2);
    std::unique_ptr<WFDSConMgr::IResourceToken>::operator=<std::default_delete<WFDSConMgr::IResourceToken>,0>(
      (__int64 *)this + 19,
      (__int64 *)&v21);
    std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(&v21);
    WFDSConMgr::SingleObjectWaiter::Wait(*((WFDSConMgr::SingleObjectWaiter **)this + 19), *((void **)this + 46));
  }
  v9 = *((_QWORD *)this + 4);
  v10 = *((_DWORD *)this + 6);
  v11 = *((_QWORD *)this + 2);
  v12 = *((_DWORD *)this + 2);
  if ( *((_BYTE *)this + 124) )
  {
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 56);
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, unsigned int, __int64, int, __int64, int, __int64, void (*)(struct HDEVQUERY__ *, void *, const struct _DEV_QUERY_RESULT_ACTION_DATA *), WFDSConMgr::CDevQueryHelper *, __int64))(v14 + 8))(
            v18,
            *((unsigned int *)this + 30),
            v13,
            1,
            v12,
            v11,
            v10,
            v9,
            v17,
            v16,
            WFDSConMgr::CDevQueryHelper::DevQueryCallback,
            this,
            v15);
    if ( v19 < 0 )
      WFDSConMgr::CException::Throw(
        v19,
        "WFDSConMgr::CDevQueryHelper::StartQuery",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\devqueryhelper.cpp",
        225,
        L"DevCreateObjectQueryFromIdEx failed",
        this);
  }
  else
  {
    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, int, __int64, _DWORD, _QWORD, void (*)(struct HDEVQUERY__ *, void *, const struct _DEV_QUERY_RESULT_ACTION_DATA *), WFDSConMgr::CDevQueryHelper *, char *))(**((_QWORD **)this + 20) + 16LL))(
            *((_QWORD *)this + 20),
            *((unsigned int *)this + 30),
            1,
            v12,
            v11,
            v10,
            v9,
            *((_DWORD *)this + 10),
            *((_QWORD *)this + 6),
            WFDSConMgr::CDevQueryHelper::DevQueryCallback,
            this,
            (char *)this + 344);
    if ( v20 < 0 )
      WFDSConMgr::CException::Throw(
        v20,
        "WFDSConMgr::CDevQueryHelper::StartQuery",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\devqueryhelper.cpp",
        241,
        L"DevCreateObjectQueryEx failed",
        this);
  }
  *((_DWORD *)this + 88) = 3 - (a2 != 0);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
  }
}

```

## disassembly

```asm
0x180028d00  mov     [rsp+arg_8], rbx
0x180028d05  push    rbp
0x180028d06  push    rsi
0x180028d07  push    rdi
0x180028d08  push    r14
0x180028d0a  push    r15
0x180028d0c  sub     rsp, 70h
0x180028d10  movzx   ebx, r8b
0x180028d14  mov     rsi, rdx
0x180028d17  mov     rdi, rcx
0x180028d1a  lea     rbp, WPP_GLOBAL_Control
0x180028d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d28  cmp     rcx, rbp
0x180028d2b  jz      short loc_180028D51
0x180028d2d  cmp     byte ptr [rcx+19h], 4
0x180028d31  jb      short loc_180028D51
0x180028d33  test    byte ptr [rcx+1Ch], 1
0x180028d37  jz      short loc_180028D51
0x180028d39  mov     edx, 0Ch
0x180028d3e  mov     r9, rdi
0x180028d41  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180028d48  mov     rcx, [rcx+10h]
0x180028d4c  call    WPP_SF_q
0x180028d51  mov     rcx, rdi; this
0x180028d54  call    ?Initialize@CDevQueryHelper@WFDSConMgr@@AEAAXXZ; WFDSConMgr::CDevQueryHelper::Initialize(void)
0x180028d59  mov     r8, cs:WPP_GLOBAL_Control
0x180028d60  cmp     r8, rbp
0x180028d63  jz      short loc_180028D9D
0x180028d65  cmp     byte ptr [r8+19h], 4
0x180028d6a  jb      short loc_180028D9D
0x180028d6c  test    byte ptr [r8+1Ch], 1
0x180028d71  jz      short loc_180028D9D
0x180028d73  lea     rcx, [rdi+38h]
0x180028d77  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028d7c  mov     [rsp+98h+var_60], rsi
0x180028d81  mov     dword ptr [rsp+98h+var_68], ebx
0x180028d85  mov     [rsp+98h+var_70], rax
0x180028d8a  mov     eax, [rdi+78h]
0x180028d8d  mov     dword ptr [rsp+98h+var_78], eax
0x180028d91  mov     r9, rdi
0x180028d94  mov     rcx, [r8+10h]
0x180028d98  call    WPP_SF_qDSlq
0x180028d9d  lea     rcx, [rdi+0B0h]
0x180028da4  lea     rdx, [rsp+98h+lpCriticalSection]
0x180028dac  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x180028db1  nop
0x180028db2  mov     eax, [rdi+160h]
0x180028db8  sub     eax, 2
0x180028dbb  cmp     eax, 1
0x180028dbe  jbe     loc_180028FD0
0x180028dc4  mov     [rdi+150h], bl
0x180028dca  test    rsi, rsi
0x180028dcd  jz      short loc_180028E32
0x180028dcf  mov     ecx, 0A8h; Size
0x180028dd4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028dd9  mov     [rsp+98h+arg_0], rax
0x180028de1  mov     r9, rsi; struct WFDSConMgr::IDevQueryCompleteListener *
0x180028de4  mov     r8, rdi; struct WFDSConMgr::CDevQueryHelper *
0x180028de7  lea     rdx, [rdi+0D8h]; struct WFDSConMgr::CThreadpoolEnvironment *
0x180028dee  mov     rcx, rax; this
0x180028df1  call    ??0CResultWaiter@CDevQueryHelper@WFDSConMgr@@QEAA@PEAVCThreadpoolEnvironment@2@PEAV12@PEAVIDevQueryCompleteListener@2@@Z; WFDSConMgr::CDevQueryHelper::CResultWaiter::CResultWaiter(WFDSConMgr::CThreadpoolEnvironment *,WFDSConMgr::CDevQueryHelper *,WFDSConMgr::IDevQueryCompleteListener *)
0x180028df6  nop
0x180028df7  mov     [rsp+98h+arg_0], rax
0x180028dff  lea     rbx, [rdi+98h]
0x180028e06  lea     rdx, [rsp+98h+arg_0]
0x180028e0e  mov     rcx, rbx
0x180028e11  call    ??$?4U?$default_delete@VIResourceToken@WFDSConMgr@@@std@@$0A@@?$unique_ptr@VIResourceToken@WFDSConMgr@@U?$default_delete@VIResourceToken@WFDSConMgr@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<WFDSConMgr::IResourceToken>::operator=<std::default_delete<WFDSConMgr::IResourceToken>,0>(std::unique_ptr<WFDSConMgr::IResourceToken> &&)
0x180028e16  lea     rcx, [rsp+98h+arg_0]
0x180028e1e  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x180028e23  mov     rdx, [rdi+170h]; void *
0x180028e2a  mov     rcx, [rbx]; this
0x180028e2d  call    ?Wait@SingleObjectWaiter@WFDSConMgr@@QEAAXPEAXK@Z; WFDSConMgr::SingleObjectWaiter::Wait(void *,ulong)
0x180028e32  lea     rdx, [rdi+158h]
0x180028e39  mov     r10, [rdi+0A0h]
0x180028e40  mov     r11, [r10]
0x180028e43  mov     r8, [rdi+30h]
0x180028e47  mov     r9d, [rdi+28h]
0x180028e4b  mov     rbx, [rdi+20h]
0x180028e4f  mov     ebp, [rdi+18h]
0x180028e52  mov     r14, [rdi+10h]
0x180028e56  mov     r15d, [rdi+8]
0x180028e5a  cmp     byte ptr [rdi+7Ch], 0
0x180028e5e  jz      loc_180028EED
0x180028e64  lea     rcx, [rdi+38h]
0x180028e68  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028e6d  mov     [rsp+98h+var_38], rdx
0x180028e72  mov     [rsp+98h+var_40], rdi
0x180028e77  lea     rcx, ?DevQueryCallback@CDevQueryHelper@WFDSConMgr@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; WFDSConMgr::CDevQueryHelper::DevQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180028e7e  mov     [rsp+98h+var_48], rcx
0x180028e83  mov     [rsp+98h+var_50], r8
0x180028e88  mov     dword ptr [rsp+98h+var_58], r9d
0x180028e8d  mov     [rsp+98h+var_60], rbx
0x180028e92  mov     dword ptr [rsp+98h+var_68], ebp
0x180028e96  mov     [rsp+98h+var_70], r14
0x180028e9b  mov     dword ptr [rsp+98h+var_78], r15d
0x180028ea0  mov     r9d, 1
0x180028ea6  mov     r8, rax
0x180028ea9  mov     edx, [rdi+78h]
0x180028eac  mov     rcx, r10
0x180028eaf  mov     rax, [r11+8]
0x180028eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eb8  test    eax, eax
0x180028eba  jns     loc_180028F64
0x180028ec0  mov     [rsp+98h+var_70], rdi; void *
0x180028ec5  lea     rcx, aDevcreateobjec_0; "DevCreateObjectQueryFromIdEx failed"
0x180028ecc  mov     [rsp+98h+var_78], rcx; unsigned __int16 *
0x180028ed1  mov     r9d, 0E1h; char
0x180028ed7  lea     r8, aOnecoreuapNetW_27; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180028ede  lea     rdx, aWfdsconmgrCdev_14; "WFDSConMgr::CDevQueryHelper::StartQuery"
0x180028ee5  mov     ecx, eax; char
0x180028ee7  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180028eed  mov     [rsp+98h+var_40], rdx
0x180028ef2  mov     [rsp+98h+var_48], rdi
0x180028ef7  lea     rcx, ?DevQueryCallback@CDevQueryHelper@WFDSConMgr@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; WFDSConMgr::CDevQueryHelper::DevQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180028efe  mov     [rsp+98h+var_50], rcx
0x180028f03  mov     [rsp+98h+var_58], r8
0x180028f08  mov     dword ptr [rsp+98h+var_60], r9d
0x180028f0d  mov     [rsp+98h+var_68], rbx
0x180028f12  mov     dword ptr [rsp+98h+var_70], ebp
0x180028f16  mov     [rsp+98h+var_78], r14
0x180028f1b  mov     r9d, r15d
0x180028f1e  mov     r8d, 1
0x180028f24  mov     edx, [rdi+78h]
0x180028f27  mov     rcx, r10
0x180028f2a  mov     rax, [r11+10h]
0x180028f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f33  test    eax, eax
0x180028f35  jns     short loc_180028F64
0x180028f37  mov     [rsp+98h+var_70], rdi; void *
0x180028f3c  lea     rcx, aDevcreateobjec; "DevCreateObjectQueryEx failed"
0x180028f43  mov     [rsp+98h+var_78], rcx; unsigned __int16 *
0x180028f48  mov     r9d, 0F1h; char
0x180028f4e  lea     r8, aOnecoreuapNetW_27; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180028f55  lea     rdx, aWfdsconmgrCdev_14; "WFDSConMgr::CDevQueryHelper::StartQuery"
0x180028f5c  mov     ecx, eax; char
0x180028f5e  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180028f64  neg     rsi
0x180028f67  sbb     eax, eax
0x180028f69  add     eax, 3
0x180028f6c  mov     [rdi+160h], eax
0x180028f72  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x180028f7a  test    rcx, rcx
0x180028f7d  jz      short loc_180028F85
0x180028f7f  call    cs:__imp_LeaveCriticalSection
0x180028f85  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f8c  lea     rax, WPP_GLOBAL_Control
0x180028f93  cmp     rcx, rax
0x180028f96  jz      short loc_180028FBC
0x180028f98  cmp     byte ptr [rcx+19h], 4
0x180028f9c  jb      short loc_180028FBC
0x180028f9e  test    byte ptr [rcx+1Ch], 1
0x180028fa2  jz      short loc_180028FBC
0x180028fa4  mov     edx, 0Eh
0x180028fa9  mov     r9, rdi
0x180028fac  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180028fb3  mov     rcx, [rcx+10h]
0x180028fb7  call    WPP_SF_q
0x180028fbc  mov     rbx, [rsp+98h+arg_8]
0x180028fc4  add     rsp, 70h
0x180028fc8  pop     r15
0x180028fca  pop     r14
0x180028fcc  pop     rdi
0x180028fcd  pop     rsi
0x180028fce  pop     rbp
0x180028fcf  retn
0x180028fd0  mov     [rsp+98h+var_70], rdi; void *
0x180028fd5  lea     rax, aQueryAlreadyRu; "Query already running"
0x180028fdc  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x180028fe1  mov     r9d, 0C5h; char
0x180028fe7  lea     r8, aOnecoreuapNetW_27; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180028fee  lea     rdx, aWfdsconmgrCdev_14; "WFDSConMgr::CDevQueryHelper::StartQuery"
0x180028ff5  mov     ecx, 8007139Fh; char
0x180028ffa  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
