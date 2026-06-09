# CSsdpCacheEntryManager::HrSearchListCache(char *,ulong,_GUID,_MessageList * *)

- ea: `0x180014868`
- end: `0x180014bc2`
- name: `?HrSearchListCache@CSsdpCacheEntryManager@@QEAAJPEADKU_GUID@@PEAPEAU_MessageList@@@Z`
- size: `858`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, HashFn *, int, struct _GUID *, struct _MessageList **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1800143e0`

## callees

- `0x180006d70`
- `0x1800084e0`
- `0x18000936c`
- `0x18000a6b8`
- `0x180014868`
- `0x180015d70`
- `0x1800186a0`
- `0x180018fe0`
- `0x180019c70`
- `0x1800203f8`
- `0x180021720`
- `0x180022a80`
- `0x1800255a8`
- `0x18002735c`
- `0x18002f7cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800149c2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180014a48`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800149c2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180014a48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ba6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ba6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014893`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014893`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrSearchListCache(
        struct _RTL_CRITICAL_SECTION *this,
        HashFn *a2,
        int a3,
        struct _GUID *a4,
        struct _MessageList **a5)
{
  int Request; // ebx
  struct _MessageList **v10; // r12
  const char *v11; // rdx
  unsigned int v12; // r8d
  unsigned int v13; // esi
  unsigned int v14; // r12d
  CSsdpCacheEntry *v15; // rdi
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // r8d
  _QWORD *v19; // rax
  _QWORD *v20; // rdi
  void *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // r8
  unsigned int v25; // r9d
  struct _MessageList **v26; // rax
  void **p_DebugInfo; // [rsp+30h] [rbp-81h] BYREF
  void *Block; // [rsp+38h] [rbp-79h] BYREF
  CSsdpCacheEntry *v30; // [rsp+40h] [rbp-71h] BYREF
  struct _GUID v31; // [rsp+50h] [rbp-61h] BYREF
  struct _NETWORK_LOCATION_INFO *v32[10]; // [rsp+60h] [rbp-51h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-1h]

  Request = 0;
  EnterCriticalSection(this);
  v10 = a5;
  Block = 0;
  *a5 = 0;
  memset_0(v32, 0, 0x58u);
  v13 = 0;
  p_DebugInfo = (void **)&this[1].DebugInfo;
  if ( this[1].DebugInfo )
  {
    v30 = 0;
    v14 = HashFn::HashString(a2, v11, v12);
    while ( 1 )
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&p_DebugInfo, &v30) )
      {
LABEL_13:
        v10 = a5;
        break;
      }
      v15 = v30;
      v31 = *a4;
      if ( (unsigned int)CSsdpCacheEntry::FIsSearchMatchHash(v30, (const char *)a2, a3, &v31, v14) )
      {
        v31 = *a4;
        Request = CSsdpCacheEntry::HrGetRequest(v15, a3, &v31, v32);
        if ( Request < 0 )
          goto LABEL_24;
        Request = CSsdpCacheEntry::HrAppendNetworkInfoToRequest(v15, (struct _SSDP_REQUEST *)v32);
        if ( Request < 0 || (Request = CUList<_SSDP_REQUEST>::HrPushFront(&Block, v32), Request < 0) )
        {
          FreeSsdpRequest((struct _SSDP_REQUEST *)v32);
LABEL_24:
          p_DebugInfo = &Block;
          if ( Block )
          {
            a5 = 0;
            do
            {
              if ( (unsigned int)CUList<_SSDP_REQUEST>::Iterator::HrGetItem(&p_DebugInfo, &a5, v16, v17) )
                break;
              FreeSsdpRequest((struct _SSDP_REQUEST *)a5);
            }
            while ( !(unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&p_DebugInfo) );
          }
          goto LABEL_38;
        }
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
          WPP_SF_sds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(_QWORD *)(v33 + 48),
            v18,
            (_DWORD)a2,
            a3,
            *(_QWORD *)(v33 + 48));
        ++v13;
      }
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&p_DebugInfo) )
        goto LABEL_13;
    }
  }
  v19 = malloc(0x10u);
  v20 = v19;
  if ( !v19 )
  {
    Request = -2147024882;
    goto LABEL_24;
  }
  *(_DWORD *)v19 = v13;
  v19[1] = 0;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v13);
    v21 = malloc(saturated_mul((int)v13, 0x58u));
    v20[1] = v21;
    if ( !v21 )
    {
      Request = -2147024882;
      operator delete(v20);
      goto LABEL_24;
    }
    memset_0(v21, 0, 88LL * (int)v13);
  }
  v22 = v20[1];
  if ( v22 )
  {
    p_DebugInfo = &Block;
    if ( Block )
    {
      a5 = 0;
      v23 = 88 * v13;
      do
      {
        if ( (unsigned int)CUList<_SSDP_REQUEST>::Iterator::HrGetItem(&p_DebugInfo, &a5, v22, v23) )
          break;
        if ( v25 >= 0x58 )
        {
          v26 = a5;
          *(_OWORD *)v24 = *(_OWORD *)a5;
          *(_OWORD *)(v24 + 16) = *((_OWORD *)v26 + 1);
          *(_OWORD *)(v24 + 32) = *((_OWORD *)v26 + 2);
          *(_OWORD *)(v24 + 48) = *((_OWORD *)v26 + 3);
          *(_OWORD *)(v24 + 64) = *((_OWORD *)v26 + 4);
          *(_QWORD *)(v24 + 80) = v26[10];
        }
      }
      while ( !(unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&p_DebugInfo) );
    }
  }
  *v10 = (struct _MessageList *)v20;
LABEL_38:
  if ( Request && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
      (unsigned int)Request);
  if ( Block )
    CUList<__int64>::Node::`scalar deleting destructor'(Block);
  Block = 0;
  LeaveCriticalSection(this);
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x180014868  mov     [rsp-8+lpCriticalSection], rcx
0x18001486d  push    rbp
0x18001486e  push    rbx
0x18001486f  push    rsi
0x180014870  push    rdi
0x180014871  push    r12
0x180014873  push    r13
0x180014875  push    r14
0x180014877  push    r15
0x180014879  lea     rbp, [rsp-17h]
0x18001487e  sub     rsp, 0C8h
0x180014885  mov     r13, r9
0x180014888  mov     r15d, r8d
0x18001488b  mov     r14, rdx
0x18001488e  mov     rdi, rcx
0x180014891  xor     ebx, ebx
0x180014893  call    cs:__imp_EnterCriticalSection
0x180014899  mov     r12, [rbp+4Fh+arg_20]
0x18001489d  lea     r8d, [rbx+58h]; Size
0x1800148a1  xor     edx, edx; Val
0x1800148a3  mov     [rbp+4Fh+Block], rbx
0x1800148a7  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1800148ab  mov     [r12], rbx
0x1800148af  call    memset_0
0x1800148b4  lea     rax, [rdi+28h]
0x1800148b8  xor     esi, esi
0x1800148ba  mov     [rsp+100h+var_D0], rax
0x1800148bf  cmp     [rax], rbx
0x1800148c2  jz      loc_1800149BD
0x1800148c8  mov     rcx, r14; this
0x1800148cb  mov     [rbp+4Fh+var_C0], rbx
0x1800148cf  call    ?HashString@HashFn@@YAKPEBDK@Z; HashFn::HashString(char const *,ulong)
0x1800148d4  mov     r12d, eax
0x1800148d7  lea     rdx, [rbp+4Fh+var_C0]
0x1800148db  lea     rcx, [rsp+100h+var_D0]
0x1800148e0  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x1800148e5  test    eax, eax
0x1800148e7  jnz     loc_1800149B5
0x1800148ed  movaps  xmm0, xmmword ptr [r13+0]
0x1800148f2  lea     r9, [rbp+4Fh+var_B0]; struct _GUID
0x1800148f6  mov     rdi, [rbp+4Fh+var_C0]
0x1800148fa  mov     r8d, r15d; unsigned int
0x1800148fd  mov     rcx, rdi; this
0x180014900  movdqa  xmmword ptr [rbp+4Fh+var_B0.Data1], xmm0
0x180014905  mov     rdx, r14; Str1
0x180014908  mov     [rsp+100h+var_E0], r12d; unsigned int
0x18001490d  call    ?FIsSearchMatchHash@CSsdpCacheEntry@@QEAAHPEBDKU_GUID@@K@Z; CSsdpCacheEntry::FIsSearchMatchHash(char const *,ulong,_GUID,ulong)
0x180014912  test    eax, eax
0x180014914  jz      loc_1800149A3
0x18001491a  movaps  xmm0, xmmword ptr [r13+0]
0x18001491f  lea     r9, [rbp+4Fh+var_A0]; struct _SSDP_REQUEST *
0x180014923  lea     r8, [rbp+4Fh+var_B0]; struct _GUID
0x180014927  movdqa  xmmword ptr [rbp+4Fh+var_B0.Data1], xmm0
0x18001492c  mov     edx, r15d; unsigned int
0x18001492f  mov     rcx, rdi; this
0x180014932  call    ?HrGetRequest@CSsdpCacheEntry@@QEAAJKU_GUID@@PEAU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrGetRequest(ulong,_GUID,_SSDP_REQUEST *)
0x180014937  mov     ebx, eax
0x180014939  test    eax, eax
0x18001493b  js      loc_1800149D5
0x180014941  lea     rdx, [rbp+4Fh+var_A0]; struct _SSDP_REQUEST *
0x180014945  mov     rcx, rdi; this
0x180014948  call    ?HrAppendNetworkInfoToRequest@CSsdpCacheEntry@@QEAAJPEAU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrAppendNetworkInfoToRequest(_SSDP_REQUEST *)
0x18001494d  mov     ebx, eax
0x18001494f  test    eax, eax
0x180014951  js      loc_1800149E1
0x180014957  lea     rdx, [rbp+4Fh+var_A0]
0x18001495b  lea     rcx, [rbp+4Fh+Block]
0x18001495f  call    ?HrPushFront@?$CUList@U_SSDP_REQUEST@@@@QEAAJAEBU_SSDP_REQUEST@@@Z; CUList<_SSDP_REQUEST>::HrPushFront(_SSDP_REQUEST const &)
0x180014964  mov     ebx, eax
0x180014966  test    eax, eax
0x180014968  js      short loc_1800149E1
0x18001496a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014971  lea     rax, WPP_GLOBAL_Control
0x180014978  cmp     rcx, rax
0x18001497b  jz      short loc_1800149A1
0x18001497d  test    byte ptr [rcx+1Ch], 8
0x180014981  jz      short loc_1800149A1
0x180014983  mov     rax, [rbp+4Fh+var_50]
0x180014987  mov     r9, r14
0x18001498a  mov     rcx, [rcx+10h]
0x18001498e  mov     rdx, [rax+30h]
0x180014992  mov     [rsp+100h+var_D8], rdx
0x180014997  mov     [rsp+100h+var_E0], r15d
0x18001499c  call    WPP_SF_sds
0x1800149a1  inc     esi
0x1800149a3  lea     rcx, [rsp+100h+var_D0]
0x1800149a8  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x1800149ad  test    eax, eax
0x1800149af  jz      loc_1800148D7
0x1800149b5  test    ebx, ebx
0x1800149b7  js      short loc_1800149D5
0x1800149b9  mov     r12, [rbp+4Fh+arg_20]
0x1800149bd  mov     ecx, 10h; Size
0x1800149c2  call    cs:__imp_malloc
0x1800149c8  mov     rdi, rax
0x1800149cb  test    rax, rax
0x1800149ce  jnz     short loc_1800149EC
0x1800149d0  mov     ebx, 8007000Eh
0x1800149d5  lea     r15, WPP_GLOBAL_Control
0x1800149dc  jmp     loc_180014A64
0x1800149e1  lea     rcx, [rbp+4Fh+var_A0]; struct _SSDP_REQUEST *
0x1800149e5  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x1800149ea  jmp     short loc_1800149D5
0x1800149ec  mov     [rax], esi
0x1800149ee  mov     qword ptr [rax+8], 0
0x1800149f6  test    esi, esi
0x1800149f8  jz      loc_180014AC2
0x1800149fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a05  lea     r15, WPP_GLOBAL_Control
0x180014a0c  cmp     rcx, r15
0x180014a0f  jz      short loc_180014A2F
0x180014a11  test    byte ptr [rcx+1Ch], 8
0x180014a15  jz      short loc_180014A2F
0x180014a17  mov     rcx, [rcx+10h]
0x180014a1b  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180014a22  mov     edx, 49h ; 'I'
0x180014a27  mov     r9d, esi
0x180014a2a  call    WPP_SF_d
0x180014a2f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014a36  movsxd  r14, esi
0x180014a39  mov     eax, 58h ; 'X'
0x180014a3e  mul     r14
0x180014a41  cmovb   rax, rcx
0x180014a45  mov     rcx, rax; Size
0x180014a48  call    cs:__imp_malloc
0x180014a4e  mov     [rdi+8], rax
0x180014a52  test    rax, rax
0x180014a55  jnz     short loc_180014AB2
0x180014a57  mov     rcx, rdi; void *
0x180014a5a  mov     ebx, 8007000Eh
0x180014a5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014a64  cmp     [rbp+4Fh+Block], 0
0x180014a69  lea     rax, [rbp+4Fh+Block]
0x180014a6d  mov     [rsp+100h+var_D0], rax
0x180014a72  jz      loc_180014B5E
0x180014a78  mov     [rbp+4Fh+arg_20], 0
0x180014a80  lea     rdx, [rbp+4Fh+arg_20]
0x180014a84  lea     rcx, [rsp+100h+var_D0]
0x180014a89  call    ?HrGetItem@Iterator@?$CUList@U_SSDP_REQUEST@@@@QEAAJPEAPEAU_SSDP_REQUEST@@@Z; CUList<_SSDP_REQUEST>::Iterator::HrGetItem(_SSDP_REQUEST * *)
0x180014a8e  test    eax, eax
0x180014a90  jnz     loc_180014B5E
0x180014a96  mov     rcx, [rbp+4Fh+arg_20]; struct _SSDP_REQUEST *
0x180014a9a  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180014a9f  lea     rcx, [rsp+100h+var_D0]
0x180014aa4  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180014aa9  test    eax, eax
0x180014aab  jz      short loc_180014A80
0x180014aad  jmp     loc_180014B5E
0x180014ab2  imul    r8, r14, 58h ; 'X'; Size
0x180014ab6  xor     edx, edx; Val
0x180014ab8  mov     rcx, rax; void *
0x180014abb  call    memset_0
0x180014ac0  jmp     short loc_180014AC9
0x180014ac2  lea     r15, WPP_GLOBAL_Control
0x180014ac9  mov     r8, [rdi+8]
0x180014acd  test    r8, r8
0x180014ad0  jz      loc_180014B5A
0x180014ad6  cmp     [rbp+4Fh+Block], 0
0x180014adb  lea     rax, [rbp+4Fh+Block]
0x180014adf  mov     [rsp+100h+var_D0], rax
0x180014ae4  jz      short loc_180014B5A
0x180014ae6  mov     [rbp+4Fh+arg_20], 0
0x180014aee  imul    r9d, esi, 58h ; 'X'
0x180014af2  lea     rdx, [rbp+4Fh+arg_20]
0x180014af6  lea     rcx, [rsp+100h+var_D0]
0x180014afb  call    ?HrGetItem@Iterator@?$CUList@U_SSDP_REQUEST@@@@QEAAJPEAPEAU_SSDP_REQUEST@@@Z; CUList<_SSDP_REQUEST>::Iterator::HrGetItem(_SSDP_REQUEST * *)
0x180014b00  test    eax, eax
0x180014b02  jnz     short loc_180014B5A
0x180014b04  cmp     r9d, 58h ; 'X'
0x180014b08  jb      short loc_180014B4C
0x180014b0a  mov     rax, [rbp+4Fh+arg_20]
0x180014b0e  movups  xmm0, xmmword ptr [rax]
0x180014b11  movups  xmmword ptr [r8], xmm0
0x180014b15  movups  xmm1, xmmword ptr [rax+10h]
0x180014b19  movups  xmmword ptr [r8+10h], xmm1
0x180014b1e  movups  xmm0, xmmword ptr [rax+20h]
0x180014b22  movups  xmmword ptr [r8+20h], xmm0
0x180014b27  movups  xmm1, xmmword ptr [rax+30h]
0x180014b2b  movups  xmmword ptr [r8+30h], xmm1
0x180014b30  movups  xmm0, xmmword ptr [rax+40h]
0x180014b34  movups  xmmword ptr [r8+40h], xmm0
0x180014b39  movsd   xmm1, qword ptr [rax+50h]
0x180014b3e  movsd   qword ptr [r8+50h], xmm1
0x180014b44  add     r8, 58h ; 'X'
0x180014b48  add     r9d, 0FFFFFFA8h
0x180014b4c  lea     rcx, [rsp+100h+var_D0]
0x180014b51  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180014b56  test    eax, eax
0x180014b58  jz      short loc_180014AF2
0x180014b5a  mov     [r12], rdi
0x180014b5e  test    ebx, ebx
0x180014b60  jz      short loc_180014B8C
0x180014b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b69  cmp     rcx, r15
0x180014b6c  jz      short loc_180014B8C
0x180014b6e  test    byte ptr [rcx+1Ch], 1
0x180014b72  jz      short loc_180014B8C
0x180014b74  mov     rcx, [rcx+10h]
0x180014b78  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180014b7f  mov     edx, 4Ah ; 'J'
0x180014b84  mov     r9d, ebx
0x180014b87  call    WPP_SF_d
0x180014b8c  mov     rcx, [rbp+4Fh+Block]; Block
0x180014b90  test    rcx, rcx
0x180014b93  jz      short loc_180014B9A
0x180014b95  call    ??_GNode@?$CUList@_J@@QEAAPEAXI@Z; CUList<__int64>::Node::`scalar deleting destructor'(uint)
0x180014b9a  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x180014b9e  mov     [rbp+4Fh+Block], 0
0x180014ba6  call    cs:__imp_LeaveCriticalSection
0x180014bac  mov     eax, ebx
0x180014bae  add     rsp, 0C8h
0x180014bb5  pop     r15
0x180014bb7  pop     r14
0x180014bb9  pop     r13
0x180014bbb  pop     r12
0x180014bbd  pop     rdi
0x180014bbe  pop     rsi
0x180014bbf  pop     rbx
0x180014bc0  pop     rbp
0x180014bc1  retn
```
