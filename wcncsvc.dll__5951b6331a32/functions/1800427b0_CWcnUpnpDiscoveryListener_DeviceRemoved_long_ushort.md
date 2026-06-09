# CWcnUpnpDiscoveryListener::DeviceRemoved(long,ushort *)

- ea: `0x1800427b0`
- end: `0x18004298b`
- name: `?DeviceRemoved@CWcnUpnpDiscoveryListener@@UEAAJJPEAG@Z`
- size: `475`
- prototype: `__int64 __fastcall(CWcnUpnpDiscoveryListener *this, __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x1800427b0`
- `0x180042a40`
- `0x180043160`
- `0x180043478`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004293c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004293c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800428da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800428da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042895`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042895`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800428e9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800428e9`

## pseudocode

```c
__int64 __fastcall CWcnUpnpDiscoveryListener::DeviceRemoved(
        CWcnUpnpDiscoveryListener *this,
        __int64 a2,
        unsigned __int16 *a3)
{
  CWcnUpnpDiscoveryListener *v4; // rdi
  const char *Indent; // rax
  __int64 v6; // r10
  char *v7; // rax
  CWcnUpnpDiscoveryListener *v8; // rcx
  _DWORD *v9; // rbx
  int PeerGuidForUdn; // eax
  int v11; // r15d
  _BYTE *v12; // r10
  RTL_SRWLOCK *v13; // r14
  unsigned int v14; // edx
  const char *v15; // rax
  __int64 v16; // r10
  __int64 v18; // rax
  _DWORD *v19; // [rsp+20h] [rbp-38h] BYREF
  RTL_SRWLOCK *v20; // [rsp+28h] [rbp-30h]
  std::bad_alloc *v21; // [rsp+30h] [rbp-28h] BYREF

  v4 = this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 33, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, Indent);
  }
  v7 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 5) = 0;
    v19 = v7;
    *(_DWORD *)v7 = 1;
    PeerGuidForUdn = CWcnUpnpDiscoveryListener::GetPeerGuidForUdn(v8, a3, (struct _GUID *)(v7 + 4));
    v11 = PeerGuidForUdn;
    if ( PeerGuidForUdn >= 0 )
    {
      v13 = (RTL_SRWLOCK *)((char *)v4 + 88);
      v20 = (RTL_SRWLOCK *)((char *)v4 + 88);
      AcquireSRWLockExclusive((PSRWLOCK)v4 + 11);
      if ( *((_QWORD *)v4 + 16) < 0x3E8u )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          std::queue<CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA *>::push((char *)v4 + 96, &v19);
          v9 = 0;
          v19 = 0;
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v21) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v18 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v21 + 8LL))(v21);
              WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, v18);
            }
            v4 = this;
            v11 = -2147024882;
            v9 = v19;
            v13 = v20;
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800428BC);
          }
        }
      }
      ReleaseSRWLockExclusive(v13);
      if ( v11 >= 0 )
        SubmitThreadpoolWork(*((PTP_WORK *)v4 + 9));
      goto LABEL_15;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids,
        (unsigned int)PeerGuidForUdn);
LABEL_15:
      v12 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v9 = 0;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids,
        "pCallbackData");
      goto LABEL_15;
    }
  }
  if ( v9 )
  {
    v14 = v9[5];
    if ( v14 )
      CWcnUpnpGit::RemoveItem(v8, v14);
    operator delete(v9);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && v12[25] >= 6u )
  {
    v15 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v16 + 16), 37, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x1800427b0  mov     [rsp+arg_8], rbx
0x1800427b5  mov     [rsp+arg_10], rsi
0x1800427ba  mov     [rsp+arg_0], rcx
0x1800427bf  push    rdi
0x1800427c0  push    r14
0x1800427c2  push    r15
0x1800427c4  sub     rsp, 40h
0x1800427c8  mov     r14, r8
0x1800427cb  mov     rdi, rcx
0x1800427ce  lea     rsi, WPP_GLOBAL_Control
0x1800427d5  mov     r10, cs:WPP_GLOBAL_Control
0x1800427dc  cmp     r10, rsi
0x1800427df  jz      short loc_18004280A
0x1800427e1  cmp     byte ptr [r10+19h], 6
0x1800427e6  jb      short loc_18004280A
0x1800427e8  mov     ecx, 1; int
0x1800427ed  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800427f2  mov     edx, 21h ; '!'
0x1800427f7  mov     r9, rax
0x1800427fa  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x180042801  mov     rcx, [r10+10h]
0x180042805  call    WPP_SF_s
0x18004280a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042811  mov     ecx, 20h ; ' '; unsigned __int64
0x180042816  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004281b  mov     rbx, rax
0x18004281e  mov     [rsp+58h+arg_18], rax
0x180042823  test    rax, rax
0x180042826  jz      loc_1800428F1
0x18004282c  mov     dword ptr [rax+14h], 0
0x180042833  mov     [rsp+58h+var_38], rax
0x180042838  mov     dword ptr [rax], 1
0x18004283e  lea     r8, [rax+4]; struct _GUID *
0x180042842  mov     rdx, r14; unsigned __int16 *
0x180042845  call    ?GetPeerGuidForUdn@CWcnUpnpDiscoveryListener@@AEAAJPEBGPEAU_GUID@@@Z; CWcnUpnpDiscoveryListener::GetPeerGuidForUdn(ushort const *,_GUID *)
0x18004284a  mov     r15d, eax
0x18004284d  test    eax, eax
0x18004284f  jns     short loc_180042889
0x180042851  mov     r10, cs:WPP_GLOBAL_Control
0x180042858  cmp     r10, rsi
0x18004285b  jz      loc_180042927
0x180042861  cmp     byte ptr [r10+19h], 2
0x180042866  jb      loc_180042927
0x18004286c  mov     edx, 23h ; '#'
0x180042871  mov     r9d, eax
0x180042874  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x18004287b  mov     rcx, [r10+10h]
0x18004287f  call    WPP_SF_d
0x180042884  jmp     loc_180042920
0x180042889  lea     r14, [rdi+58h]
0x18004288d  mov     [rsp+58h+var_30], r14
0x180042892  mov     rcx, r14; SRWLock
0x180042895  call    cs:__imp_AcquireSRWLockExclusive
0x18004289b  lea     rcx, [rdi+60h]
0x18004289f  cmp     qword ptr [rcx+20h], 3E8h
0x1800428a7  jnb     short loc_1800428D7
0x1800428a9  lea     rdx, [rsp+58h+var_38]
0x1800428ae  call    ?push@?$queue@PEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@V?$deque@PEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@V?$allocator@PEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@@std@@@std@@@std@@QEAAXAEBQEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@@Z; std::queue<CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA *>::push(CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA * const &)
0x1800428b3  xor     ebx, ebx
0x1800428b5  mov     [rsp+58h+var_38], rbx
0x1800428ba  jmp     short loc_1800428D7
0x1800428bc  lea     rsi, WPP_GLOBAL_Control
0x1800428c3  mov     rdi, [rsp+58h+arg_0]
0x1800428c8  mov     r15d, dword ptr [rsp+58h+arg_18]
0x1800428cd  mov     rbx, [rsp+58h+var_38]
0x1800428d2  mov     r14, [rsp+58h+var_30]
0x1800428d7  mov     rcx, r14; SRWLock
0x1800428da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800428e0  test    r15d, r15d
0x1800428e3  js      short loc_180042920
0x1800428e5  mov     rcx, [rdi+48h]; pwk
0x1800428e9  call    cs:__imp_SubmitThreadpoolWork
0x1800428ef  jmp     short loc_180042920
0x1800428f1  xor     ebx, ebx
0x1800428f3  mov     r10, cs:WPP_GLOBAL_Control
0x1800428fa  cmp     r10, rsi
0x1800428fd  jz      short loc_180042927
0x1800428ff  cmp     byte ptr [r10+19h], 2
0x180042904  jb      short loc_180042927
0x180042906  lea     edx, [rbx+22h]
0x180042909  lea     r9, aPcallbackdata; "pCallbackData"
0x180042910  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x180042917  mov     rcx, [r10+10h]
0x18004291b  call    WPP_SF_s
0x180042920  mov     r10, cs:WPP_GLOBAL_Control
0x180042927  test    rbx, rbx
0x18004292a  jz      short loc_180042949
0x18004292c  mov     edx, [rbx+14h]; unsigned int
0x18004292f  test    edx, edx
0x180042931  jz      short loc_180042939
0x180042933  call    ?RemoveItem@CWcnUpnpGit@@QEAAXK@Z; CWcnUpnpGit::RemoveItem(ulong)
0x180042938  nop
0x180042939  mov     rcx, rbx
0x18004293c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180042942  mov     r10, cs:WPP_GLOBAL_Control
0x180042949  cmp     r10, rsi
0x18004294c  jz      short loc_180042975
0x18004294e  cmp     byte ptr [r10+19h], 6
0x180042953  jb      short loc_180042975
0x180042955  or      ecx, 0FFFFFFFFh; int
0x180042958  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004295d  mov     edx, 25h ; '%'
0x180042962  mov     r9, rax
0x180042965  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x18004296c  mov     rcx, [r10+10h]
0x180042970  call    WPP_SF_s
0x180042975  xor     eax, eax
0x180042977  mov     rbx, [rsp+58h+arg_8]
0x18004297c  mov     rsi, [rsp+58h+arg_10]
0x180042981  add     rsp, 40h
0x180042985  pop     r15
0x180042987  pop     r14
0x180042989  pop     rdi
0x18004298a  retn
```
