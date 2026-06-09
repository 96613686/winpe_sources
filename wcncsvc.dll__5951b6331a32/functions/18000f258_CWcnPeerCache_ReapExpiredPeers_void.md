# CWcnPeerCache::ReapExpiredPeers(void)

- ea: `0x18000f258`
- end: `0x18000f4d9`
- name: `?ReapExpiredPeers@CWcnPeerCache@@QEAAXXZ`
- size: `641`
- prototype: `void __fastcall(CWcnPeerCache *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000fc10`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x18000c7f8`
- `0x18000ce18`
- `0x18000eac0`
- `0x18000f258`
- `0x18000fe00`
- `0x18001daa4`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f309`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f420`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f309`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f420`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f42a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f48e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f42a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f48e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f268`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f268`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f441`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f441`

## pseudocode

```c
void __fastcall CWcnPeerCache::ReapExpiredPeers(CWcnPeerCache *this)
{
  ULONGLONG TickCount64; // r15
  const char *Indent; // rax
  __int64 v4; // r10
  _BYTE *v5; // r10
  unsigned int v6; // eax
  __int64 v7; // r10
  char v8; // r11
  __int64 *v9; // rbx
  __int64 v10; // rbp
  ULONGLONG v11; // rdi
  bool v12; // dl
  struct _GUID *v13; // rdi
  __int64 *i; // rax
  __int64 *v15; // rcx
  int v16; // eax
  __int64 v17; // r10
  __int64 v18; // rdi
  const char *v19; // rax
  __int64 v20; // r10
  const char *v21; // rax
  __int64 v22; // r10
  __int64 *v23; // [rsp+70h] [rbp+8h] BYREF

  TickCount64 = GetTickCount64();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 92, WPP_f34e634574083547aa3a426270948a29_Traceguids, Indent);
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)this + 31) != 1 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v6 = (unsigned int)GetIndent(0);
        WPP_SF_sd(*(_QWORD *)(v7 + 16), 93, (unsigned int)WPP_f34e634574083547aa3a426270948a29_Traceguids, v6, v8);
        goto LABEL_37;
      }
      goto LABEL_38;
    }
    return;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v9 = (__int64 *)**((_QWORD **)this + 10);
  while ( v9 != *((__int64 **)this + 10) )
  {
    v10 = v9[6];
    v11 = *(_QWORD *)(v10 + 280);
    if ( !*(_BYTE *)(v10 + 232) && TickCount64 > *(_QWORD *)(v10 + 272) )
      CWcnIdentity::SetDataIsStale((CWcnIdentity *)(v10 + 136));
    v12 = !*(_DWORD *)(v10 + 264) && TickCount64 > v11;
    v13 = (struct _GUID *)v9;
    if ( !*((_BYTE *)v9 + 25) )
    {
      i = (__int64 *)v9[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v9 = i;
      }
      else
      {
        v15 = (__int64 *)*i;
        if ( !*(_BYTE *)(*i + 25) )
        {
          do
          {
            v9 = v15;
            v15 = (__int64 *)*v15;
          }
          while ( !*((_BYTE *)v15 + 25) );
          goto LABEL_27;
        }
      }
      v9 = i;
    }
LABEL_27:
    if ( v12 )
    {
      CWcnPeer::CacheUnref((CWcnPeer *)v10);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v16 = (unsigned int)GetIndent(0);
        WPP_SF_s_guid_(
          *(_QWORD *)(v17 + 16),
          94,
          (int)WPP_f34e634574083547aa3a426270948a29_Traceguids,
          v16,
          (__int64)&v13[2]);
      }
      CWcnPeerCache::DeletePeerNotificationFilter((struct _RTL_CRITICAL_SECTION *)this, v13 + 2);
      std::_Tree<std::_Tmap_traits<_GUID,CWcnWfdGoPeer const *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnWfdGoPeer const *>>,0>>::erase(
        (_QWORD *)this + 10,
        &v23,
        (__int64 *)v13);
    }
  }
  v18 = *((_QWORD *)this + 11);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( !v18 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 14), 0, 0, 0);
    *((_BYTE *)this + 120) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v19 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v20 + 16), 95, WPP_f34e634574083547aa3a426270948a29_Traceguids, v19);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  _InterlockedExchange((volatile __int32 *)this + 31, 0);
LABEL_37:
  v5 = WPP_GLOBAL_Control;
LABEL_38:
  if ( v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 6u )
  {
    v21 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v22 + 16), 96, WPP_f34e634574083547aa3a426270948a29_Traceguids, v21);
  }
}

```

## disassembly

```asm
0x18000f258  push    rbx
0x18000f25a  push    rbp
0x18000f25b  push    rsi
0x18000f25c  push    rdi
0x18000f25d  push    r14
0x18000f25f  push    r15
0x18000f261  sub     rsp, 38h
0x18000f265  mov     rsi, rcx
0x18000f268  call    cs:__imp_GetTickCount64
0x18000f26e  mov     r15, rax
0x18000f271  mov     r10, cs:WPP_GLOBAL_Control
0x18000f278  lea     rbp, WPP_GLOBAL_Control
0x18000f27f  cmp     r10, rbp
0x18000f282  jz      short loc_18000F2AD
0x18000f284  cmp     byte ptr [r10+19h], 6
0x18000f289  jb      short loc_18000F2AD
0x18000f28b  mov     ecx, 1; int
0x18000f290  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f295  mov     rcx, [r10+10h]
0x18000f299  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f2a0  mov     edx, 5Ch ; '\'
0x18000f2a5  mov     r9, rax
0x18000f2a8  call    WPP_SF_s
0x18000f2ad  mov     r11d, 1
0x18000f2b3  lock xadd [rsi+7Ch], r11d
0x18000f2b9  inc     r11d
0x18000f2bc  cmp     r11d, 1
0x18000f2c0  jz      short loc_18000F306
0x18000f2c2  mov     r10, cs:WPP_GLOBAL_Control
0x18000f2c9  cmp     r10, rbp
0x18000f2cc  jz      loc_18000F4CC
0x18000f2d2  cmp     byte ptr [r10+19h], 3
0x18000f2d7  jb      loc_18000F4A0
0x18000f2dd  xor     ecx, ecx; int
0x18000f2df  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f2e4  mov     rcx, [r10+10h]
0x18000f2e8  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f2ef  mov     edx, 5Dh ; ']'
0x18000f2f4  mov     dword ptr [rsp+68h+var_48], r11d
0x18000f2f9  mov     r9, rax
0x18000f2fc  call    WPP_SF_sd
0x18000f301  jmp     loc_18000F499
0x18000f306  mov     rcx, rsi; lpCriticalSection
0x18000f309  call    cs:__imp_EnterCriticalSection
0x18000f30f  lea     r14, [rsi+50h]
0x18000f313  mov     rbx, [r14]
0x18000f316  mov     rbx, [rbx]
0x18000f319  cmp     rbx, [r14]
0x18000f31c  jz      loc_18000F418
0x18000f322  mov     rbp, [rbx+30h]
0x18000f326  mov     rdi, [rbp+118h]
0x18000f32d  lea     rcx, [rbp+88h]; this
0x18000f334  cmp     byte ptr [rcx+60h], 0
0x18000f338  jnz     short loc_18000F348
0x18000f33a  cmp     r15, [rbp+110h]
0x18000f341  jbe     short loc_18000F348
0x18000f343  call    ?SetDataIsStale@CWcnIdentity@@QEAAXXZ; CWcnIdentity::SetDataIsStale(void)
0x18000f348  mov     eax, [rbp+108h]
0x18000f34e  test    eax, eax
0x18000f350  jnz     short loc_18000F35B
0x18000f352  cmp     r15, rdi
0x18000f355  jbe     short loc_18000F35B
0x18000f357  mov     dl, 1
0x18000f359  jmp     short loc_18000F35D
0x18000f35b  xor     dl, dl
0x18000f35d  cmp     byte ptr [rbx+19h], 0
0x18000f361  mov     rdi, rbx
0x18000f364  jnz     short loc_18000F3A6
0x18000f366  mov     rax, [rbx+10h]
0x18000f36a  cmp     byte ptr [rax+19h], 0
0x18000f36e  jnz     short loc_18000F38A
0x18000f370  mov     rcx, [rax]
0x18000f373  cmp     byte ptr [rcx+19h], 0
0x18000f377  jnz     short loc_18000F3A3
0x18000f379  mov     rax, [rcx]
0x18000f37c  mov     rbx, rcx
0x18000f37f  mov     rcx, rax
0x18000f382  cmp     byte ptr [rax+19h], 0
0x18000f386  jz      short loc_18000F379
0x18000f388  jmp     short loc_18000F3A6
0x18000f38a  mov     rax, [rbx+8]
0x18000f38e  jmp     short loc_18000F39D
0x18000f390  cmp     rbx, [rax+10h]
0x18000f394  jnz     short loc_18000F3A3
0x18000f396  mov     rbx, rax
0x18000f399  mov     rax, [rax+8]
0x18000f39d  cmp     byte ptr [rax+19h], 0
0x18000f3a1  jz      short loc_18000F390
0x18000f3a3  mov     rbx, rax
0x18000f3a6  test    dl, dl
0x18000f3a8  jz      loc_18000F319
0x18000f3ae  mov     rcx, rbp; this
0x18000f3b1  call    ?CacheUnref@CWcnPeer@@QEAAXXZ; CWcnPeer::CacheUnref(void)
0x18000f3b6  lea     rbp, [rdi+20h]
0x18000f3ba  mov     r10, cs:WPP_GLOBAL_Control
0x18000f3c1  lea     rax, WPP_GLOBAL_Control
0x18000f3c8  cmp     r10, rax
0x18000f3cb  jz      short loc_18000F3F8
0x18000f3cd  cmp     byte ptr [r10+19h], 5
0x18000f3d2  jb      short loc_18000F3F8
0x18000f3d4  xor     ecx, ecx; int
0x18000f3d6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f3db  mov     rcx, [r10+10h]
0x18000f3df  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f3e6  mov     edx, 5Eh ; '^'
0x18000f3eb  mov     [rsp+68h+var_48], rbp
0x18000f3f0  mov     r9, rax
0x18000f3f3  call    WPP_SF_s_guid_
0x18000f3f8  mov     rdx, rbp; struct _GUID *
0x18000f3fb  mov     rcx, rsi; this
0x18000f3fe  call    ?DeletePeerNotificationFilter@CWcnPeerCache@@AEAAJPEBU_GUID@@@Z; CWcnPeerCache::DeletePeerNotificationFilter(_GUID const *)
0x18000f403  mov     r8, rdi
0x18000f406  lea     rdx, [rsp+68h+arg_0]
0x18000f40b  mov     rcx, r14
0x18000f40e  call    ?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@PEBVCWcnWfdGoPeer@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnWfdGoPeer const *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnWfdGoPeer const *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CWcnWfdGoPeer const *>>>>)
0x18000f413  jmp     loc_18000F319
0x18000f418  mov     rdi, [rsi+58h]
0x18000f41c  lea     rcx, [rsi+28h]; lpCriticalSection
0x18000f420  call    cs:__imp_EnterCriticalSection
0x18000f426  lea     rcx, [rsi+28h]; lpCriticalSection
0x18000f42a  call    cs:__imp_LeaveCriticalSection
0x18000f430  test    rdi, rdi
0x18000f433  jnz     short loc_18000F484
0x18000f435  mov     rcx, [rsi+70h]; pti
0x18000f439  xor     r9d, r9d; msWindowLength
0x18000f43c  xor     r8d, r8d; msPeriod
0x18000f43f  xor     edx, edx; pftDueTime
0x18000f441  call    cs:__imp_SetThreadpoolTimer
0x18000f447  mov     [rsi+78h], dil
0x18000f44b  mov     r10, cs:WPP_GLOBAL_Control
0x18000f452  lea     rbp, WPP_GLOBAL_Control
0x18000f459  cmp     r10, rbp
0x18000f45c  jz      short loc_18000F48B
0x18000f45e  cmp     byte ptr [r10+19h], 4
0x18000f463  jb      short loc_18000F48B
0x18000f465  xor     ecx, ecx; int
0x18000f467  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f46c  mov     rcx, [r10+10h]
0x18000f470  lea     edx, [rdi+5Fh]
0x18000f473  mov     r9, rax
0x18000f476  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f47d  call    WPP_SF_s
0x18000f482  jmp     short loc_18000F48B
0x18000f484  lea     rbp, WPP_GLOBAL_Control
0x18000f48b  mov     rcx, rsi; lpCriticalSection
0x18000f48e  call    cs:__imp_LeaveCriticalSection
0x18000f494  xor     eax, eax
0x18000f496  xchg    eax, [rsi+7Ch]
0x18000f499  mov     r10, cs:WPP_GLOBAL_Control
0x18000f4a0  cmp     r10, rbp
0x18000f4a3  jz      short loc_18000F4CC
0x18000f4a5  cmp     byte ptr [r10+19h], 6
0x18000f4aa  jb      short loc_18000F4CC
0x18000f4ac  or      ecx, 0FFFFFFFFh; int
0x18000f4af  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f4b4  mov     rcx, [r10+10h]
0x18000f4b8  lea     r8, WPP_f34e634574083547aa3a426270948a29_Traceguids
0x18000f4bf  mov     edx, 60h ; '`'
0x18000f4c4  mov     r9, rax
0x18000f4c7  call    WPP_SF_s
0x18000f4cc  add     rsp, 38h
0x18000f4d0  pop     r15
0x18000f4d2  pop     r14
0x18000f4d4  pop     rdi
0x18000f4d5  pop     rsi
0x18000f4d6  pop     rbp
0x18000f4d7  pop     rbx
0x18000f4d8  retn
```
