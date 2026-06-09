# CWerComStore::_LoadReport(ushort *,IWerReport * *)

- ea: `0x18000fb0c`
- end: `0x18000fd4c`
- name: `?_LoadReport@CWerComStore@@QEAAJPEAGPEAPEAUIWerReport@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(CWerComStore *__hidden this, unsigned __int16 *, struct IWerReport **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000bd90`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800073d4`
- `0x18000bc4c`
- `0x18000e3fc`
- `0x18000fb0c`
- `0x180013010`

## import_xrefs

- `wer!WerReportCloseHandle` at `0x18000fd2c`
- `wer!WerReportCloseHandle` at `0x18000fd2c`
- `wer!WerpLoadReport` at `0x18000fba1`
- `wer!WerpLoadReport` at `0x18000fba1`

## pseudocode

```c
__int64 __fastcall CWerComStore::_LoadReport(CWerComStore *this, unsigned __int16 *a2, struct IWerReport **a3)
{
  int WerStoreApiLock; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  CManagedObj *v10; // rax
  CManagedObj *v11; // rdi
  int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v16; // [rsp+30h] [rbp-38h] BYREF
  HREPORT v17[6]; // [rsp+38h] [rbp-30h] BYREF
  HREPORT hReportHandle; // [rsp+88h] [rbp+20h] BYREF

  v16 = 0;
  WerStoreApiLock = CWerStoreApiAutoLock::TryGetWerStoreApiLock((CWerStoreApiAutoLock *)&v16, this);
  v7 = WerStoreApiLock;
  if ( WerStoreApiLock < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)WerStoreApiLock);
    goto LABEL_26;
  }
  v8 = *((_QWORD *)this + 4);
  hReportHandle = 0;
  v9 = WerpLoadReport(v8, a2, &hReportHandle, 1);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)v9);
    goto LABEL_24;
  }
  v10 = (CManagedObj *)operator new(0x38u);
  v11 = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    goto LABEL_24;
  }
  CManagedObj::CManagedObj(v10);
  *((_QWORD *)v11 + 5) = 0;
  *(_QWORD *)v11 = &CWerComReport::`vftable'{for `CManagedObj'};
  *((_QWORD *)v11 + 3) = &CWerComReport::`vftable'{for `IWerReport'};
  *((_QWORD *)v11 + 4) = 0;
  *((_DWORD *)v11 + 12) = 0;
  _InterlockedIncrement((volatile signed __int32 *)v11 + 2);
  v17[0] = hReportHandle;
  hReportHandle = 0;
  v12 = CWerComReport::Init(v11, v17, this);
  v7 = v12;
  if ( v12 >= 0 )
  {
    v12 = (**(__int64 (__fastcall ***)(CManagedObj *, GUID *, struct IWerReport **))v11)(v11, &IID_IWerReport, a3);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v7 = 0;
      goto LABEL_20;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v14 = 93;
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v14 = 92;
  }
  WPP_SF_d(v13[2], v14, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)v12);
LABEL_20:
  (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_24:
  if ( hReportHandle )
    WerReportCloseHandle(hReportHandle);
LABEL_26:
  if ( v16 )
    _InterlockedExchange((volatile __int32 *)(v16 + 40), 0);
  return v7;
}

```

## disassembly

```asm
0x18000fb0c  push    rbx
0x18000fb0e  push    rbp
0x18000fb0f  push    rsi
0x18000fb10  push    rdi
0x18000fb11  sub     rsp, 48h
0x18000fb15  mov     rdi, rdx
0x18000fb18  mov     [rsp+68h+var_38], 0
0x18000fb21  mov     rdx, rcx; struct CWerComStore *
0x18000fb24  mov     rsi, rcx
0x18000fb27  lea     rcx, [rsp+68h+var_38]; this
0x18000fb2c  mov     rbp, r8
0x18000fb2f  call    ?TryGetWerStoreApiLock@CWerStoreApiAutoLock@@QEAAJPEAVCWerComStore@@@Z; CWerStoreApiAutoLock::TryGetWerStoreApiLock(CWerComStore *)
0x18000fb34  mov     ebx, eax
0x18000fb36  test    eax, eax
0x18000fb38  jns     short loc_18000FB78
0x18000fb3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb41  lea     rdx, WPP_GLOBAL_Control
0x18000fb48  cmp     rcx, rdx
0x18000fb4b  jz      loc_18000FD32
0x18000fb51  test    byte ptr [rcx+1Ch], 1
0x18000fb55  jz      loc_18000FD32
0x18000fb5b  mov     rcx, [rcx+10h]
0x18000fb5f  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000fb66  mov     edx, 59h ; 'Y'
0x18000fb6b  mov     r9d, eax
0x18000fb6e  call    WPP_SF_d
0x18000fb73  jmp     loc_18000FD32
0x18000fb78  mov     rcx, [rsi+20h]
0x18000fb7c  lea     r8, [rsp+68h+hReportHandle]
0x18000fb84  mov     r9d, 1
0x18000fb8a  mov     [rsp+68h+hReportHandle], 0
0x18000fb96  mov     rdx, rdi
0x18000fb99  mov     [rsp+68h+var_48], 0
0x18000fba1  call    cs:__imp_WerpLoadReport
0x18000fba7  mov     ebx, eax
0x18000fba9  test    eax, eax
0x18000fbab  jns     short loc_18000FBEB
0x18000fbad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbb4  lea     rdx, WPP_GLOBAL_Control
0x18000fbbb  cmp     rcx, rdx
0x18000fbbe  jz      loc_18000FD1F
0x18000fbc4  test    byte ptr [rcx+1Ch], 1
0x18000fbc8  jz      loc_18000FD1F
0x18000fbce  mov     rcx, [rcx+10h]
0x18000fbd2  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000fbd9  mov     edx, 5Ah ; 'Z'
0x18000fbde  mov     r9d, eax
0x18000fbe1  call    WPP_SF_d
0x18000fbe6  jmp     loc_18000FD1F
0x18000fbeb  mov     ecx, 38h ; '8'; Size
0x18000fbf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fbf5  mov     rdi, rax
0x18000fbf8  test    rax, rax
0x18000fbfb  jz      loc_18000FCEC
0x18000fc01  mov     rcx, rax; this
0x18000fc04  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x18000fc09  lea     rax, ??_7CWerComReport@@6BCManagedObj@@@; const CWerComReport::`vftable'{for `CManagedObj'}
0x18000fc10  mov     qword ptr [rdi+28h], 0
0x18000fc18  mov     [rdi], rax
0x18000fc1b  lea     rax, ??_7CWerComReport@@6BIWerReport@@@; const CWerComReport::`vftable'{for `IWerReport'}
0x18000fc22  mov     [rdi+18h], rax
0x18000fc26  mov     qword ptr [rdi+20h], 0
0x18000fc2e  mov     dword ptr [rdi+30h], 0
0x18000fc35  lock inc dword ptr [rdi+8]
0x18000fc39  mov     rax, [rsp+68h+hReportHandle]
0x18000fc41  lea     rdx, [rsp+68h+var_30]
0x18000fc46  mov     r8, rsi
0x18000fc49  mov     [rsp+68h+var_30], rax
0x18000fc4e  mov     rcx, rdi
0x18000fc51  mov     [rsp+68h+hReportHandle], 0
0x18000fc5d  call    ?Init@CWerComReport@@QEAAJV?$unique_any@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@Z$0A@@tlx@@@tlx@@PEAVCWerComStore@@@Z; CWerComReport::Init(tlx::unique_any<tlx::handle_traits<void *,long (void *),&WerReportCloseHandle(void *),0>>,CWerComStore *)
0x18000fc62  mov     ebx, eax
0x18000fc64  test    eax, eax
0x18000fc66  jns     short loc_18000FC9B
0x18000fc68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc6f  lea     rdx, WPP_GLOBAL_Control
0x18000fc76  cmp     rcx, rdx
0x18000fc79  jz      short loc_18000FCDB
0x18000fc7b  test    byte ptr [rcx+1Ch], 1
0x18000fc7f  jz      short loc_18000FCDB
0x18000fc81  mov     edx, 5Ch ; '\'
0x18000fc86  mov     rcx, [rcx+10h]
0x18000fc8a  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000fc91  mov     r9d, eax
0x18000fc94  call    WPP_SF_d
0x18000fc99  jmp     short loc_18000FCDB
0x18000fc9b  mov     rax, [rdi]
0x18000fc9e  lea     rdx, IID_IWerReport
0x18000fca5  mov     r8, rbp
0x18000fca8  mov     rcx, rdi
0x18000fcab  mov     rax, [rax]
0x18000fcae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcb3  mov     ebx, eax
0x18000fcb5  test    eax, eax
0x18000fcb7  jns     short loc_18000FCD9
0x18000fcb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcc0  lea     rdx, WPP_GLOBAL_Control
0x18000fcc7  cmp     rcx, rdx
0x18000fcca  jz      short loc_18000FCDB
0x18000fccc  test    byte ptr [rcx+1Ch], 1
0x18000fcd0  jz      short loc_18000FCDB
0x18000fcd2  mov     edx, 5Dh ; ']'
0x18000fcd7  jmp     short loc_18000FC86
0x18000fcd9  xor     ebx, ebx
0x18000fcdb  mov     rax, [rdi]
0x18000fcde  mov     rcx, rdi
0x18000fce1  mov     rax, [rax+10h]
0x18000fce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcea  jmp     short loc_18000FD1F
0x18000fcec  mov     ebx, 8007000Eh
0x18000fcf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcf8  lea     rdx, WPP_GLOBAL_Control
0x18000fcff  cmp     rcx, rdx
0x18000fd02  jz      short loc_18000FD1F
0x18000fd04  test    byte ptr [rcx+1Ch], 1
0x18000fd08  jz      short loc_18000FD1F
0x18000fd0a  mov     rcx, [rcx+10h]
0x18000fd0e  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000fd15  mov     edx, 5Bh ; '['
0x18000fd1a  call    WPP_SF_
0x18000fd1f  mov     rcx, [rsp+68h+hReportHandle]; hReportHandle
0x18000fd27  test    rcx, rcx
0x18000fd2a  jz      short loc_18000FD32
0x18000fd2c  call    cs:__imp_WerReportCloseHandle
0x18000fd32  mov     rax, [rsp+68h+var_38]
0x18000fd37  test    rax, rax
0x18000fd3a  jz      short loc_18000FD41
0x18000fd3c  xor     ecx, ecx
0x18000fd3e  xchg    ecx, [rax+28h]
0x18000fd41  mov     eax, ebx
0x18000fd43  add     rsp, 48h
0x18000fd47  pop     rdi
0x18000fd48  pop     rsi
0x18000fd49  pop     rbp
0x18000fd4a  pop     rbx
0x18000fd4b  retn
```
