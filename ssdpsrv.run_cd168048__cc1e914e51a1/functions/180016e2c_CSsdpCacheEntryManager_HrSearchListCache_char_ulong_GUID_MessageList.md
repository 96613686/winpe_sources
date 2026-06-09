# CSsdpCacheEntryManager::HrSearchListCache(char *,ulong,_GUID,_MessageList * *)

- ea: `0x180016e2c`
- end: `0x18001719f`
- name: `?HrSearchListCache@CSsdpCacheEntryManager@@QEAAJPEADKU_GUID@@PEAPEAU_MessageList@@@Z`
- size: `883`
- prototype: `int(CSsdpCacheEntryManager *__hidden this, char *, unsigned int, struct _GUID *__struct_ptr, struct _MessageList **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180016950`

## callees

- `0x180008190`
- `0x180009a84`
- `0x18000a9ac`
- `0x18000ae2c`
- `0x18000bbf0`
- `0x180016e2c`
- `0x180019920`
- `0x18001a1b0`
- `0x18001ad60`
- `0x180021c54`
- `0x180022f5c`
- `0x180024490`
- `0x1800271fc`
- `0x18002911c`
- `0x180031ab8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016f8c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180017018`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016f8c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180017018`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001717c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001717c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016e57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016e57`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrSearchListCache(
        struct _RTL_CRITICAL_SECTION *this,
        HashFn *a2,
        unsigned int a3,
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
  void *v29; // [rsp+38h] [rbp-79h] BYREF
  CSsdpCacheEntry *v30; // [rsp+40h] [rbp-71h] BYREF
  struct _GUID v31; // [rsp+50h] [rbp-61h] BYREF
  _BYTE v32[80]; // [rsp+60h] [rbp-51h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-1h]

  Request = 0;
  EnterCriticalSection(this);
  v10 = a5;
  v29 = 0;
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
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&p_DebugInfo, &v30) )
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
        Request = CSsdpCacheEntry::HrGetRequest(v15, a3, &v31, (struct _SSDP_REQUEST *)v32);
        if ( Request < 0 )
          goto LABEL_24;
        Request = CSsdpCacheEntry::HrAppendNetworkInfoToRequest(v15, (struct _SSDP_REQUEST *)v32);
        if ( Request < 0 || (Request = CUList<_SSDP_REQUEST>::HrPushFront(&v29, v32), Request < 0) )
        {
          FreeSsdpRequest((struct _SSDP_REQUEST *)v32);
LABEL_24:
          p_DebugInfo = &v29;
          if ( v29 )
          {
            a5 = 0;
            do
            {
              if ( (unsigned int)CUList<_SSDP_REQUEST>::Iterator::HrGetItem(&p_DebugInfo, &a5, v16, v17) )
                break;
              FreeSsdpRequest((struct _SSDP_REQUEST *)a5);
            }
            while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(&p_DebugInfo) );
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
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext(&p_DebugInfo) )
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
    p_DebugInfo = &v29;
    if ( v29 )
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
      while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(&p_DebugInfo) );
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
  if ( v29 )
    CUList<__int64>::Node::`scalar deleting destructor'(v29);
  v29 = 0;
  LeaveCriticalSection(this);
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x180016e2c  mov     [rsp-8+lpCriticalSection], rcx
0x180016e31  push    rbp
0x180016e32  push    rbx
0x180016e33  push    rsi
0x180016e34  push    rdi
0x180016e35  push    r12
0x180016e37  push    r13
0x180016e39  push    r14
0x180016e3b  push    r15
0x180016e3d  lea     rbp, [rsp-17h]
0x180016e42  sub     rsp, 0C8h
0x180016e49  mov     r13, r9
0x180016e4c  mov     r15d, r8d
0x180016e4f  mov     r14, rdx
0x180016e52  mov     rdi, rcx
0x180016e55  xor     ebx, ebx
0x180016e57  call    cs:__imp_EnterCriticalSection
0x180016e5e  nop     dword ptr [rax+rax+00h]
0x180016e63  mov     r12, [rbp+4Fh+arg_20]
0x180016e67  lea     r8d, [rbx+58h]; Size
0x180016e6b  xor     edx, edx; Val
0x180016e6d  mov     [rbp+4Fh+var_C8], rbx
0x180016e71  lea     rcx, [rbp+4Fh+var_A0]; void *
0x180016e75  mov     [r12], rbx
0x180016e79  call    memset_0
0x180016e7e  lea     rax, [rdi+28h]
0x180016e82  xor     esi, esi
0x180016e84  mov     [rsp+100h+var_D0], rax
0x180016e89  cmp     [rax], rbx
0x180016e8c  jz      loc_180016F87
0x180016e92  mov     rcx, r14; this
0x180016e95  mov     [rbp+4Fh+var_C0], rbx
0x180016e99  call    ?HashString@HashFn@@YAKPEBDK@Z; HashFn::HashString(char const *,ulong)
0x180016e9e  mov     r12d, eax
0x180016ea1  lea     rdx, [rbp+4Fh+var_C0]
0x180016ea5  lea     rcx, [rsp+100h+var_D0]
0x180016eaa  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x180016eaf  test    eax, eax
0x180016eb1  jnz     loc_180016F7F
0x180016eb7  movaps  xmm0, xmmword ptr [r13+0]
0x180016ebc  lea     r9, [rbp+4Fh+var_B0]; struct _GUID
0x180016ec0  mov     rdi, [rbp+4Fh+var_C0]
0x180016ec4  mov     r8d, r15d; unsigned int
0x180016ec7  mov     rcx, rdi; this
0x180016eca  movdqa  xmmword ptr [rbp+4Fh+var_B0.Data1], xmm0
0x180016ecf  mov     rdx, r14; Str1
0x180016ed2  mov     [rsp+100h+var_E0], r12d; unsigned int
0x180016ed7  call    ?FIsSearchMatchHash@CSsdpCacheEntry@@QEAAHPEBDKU_GUID@@K@Z; CSsdpCacheEntry::FIsSearchMatchHash(char const *,ulong,_GUID,ulong)
0x180016edc  test    eax, eax
0x180016ede  jz      loc_180016F6D
0x180016ee4  movaps  xmm0, xmmword ptr [r13+0]
0x180016ee9  lea     r9, [rbp+4Fh+var_A0]; struct _SSDP_REQUEST *
0x180016eed  lea     r8, [rbp+4Fh+var_B0]; struct _GUID
0x180016ef1  movdqa  xmmword ptr [rbp+4Fh+var_B0.Data1], xmm0
0x180016ef6  mov     edx, r15d; unsigned int
0x180016ef9  mov     rcx, rdi; this
0x180016efc  call    ?HrGetRequest@CSsdpCacheEntry@@QEAAJKU_GUID@@PEAU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrGetRequest(ulong,_GUID,_SSDP_REQUEST *)
0x180016f01  mov     ebx, eax
0x180016f03  test    eax, eax
0x180016f05  js      loc_180016FA5
0x180016f0b  lea     rdx, [rbp+4Fh+var_A0]; struct _SSDP_REQUEST *
0x180016f0f  mov     rcx, rdi; this
0x180016f12  call    ?HrAppendNetworkInfoToRequest@CSsdpCacheEntry@@QEAAJPEAU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrAppendNetworkInfoToRequest(_SSDP_REQUEST *)
0x180016f17  mov     ebx, eax
0x180016f19  test    eax, eax
0x180016f1b  js      loc_180016FB1
0x180016f21  lea     rdx, [rbp+4Fh+var_A0]
0x180016f25  lea     rcx, [rbp+4Fh+var_C8]
0x180016f29  call    ?HrPushFront@?$CUList@U_SSDP_REQUEST@@@@QEAAJAEBU_SSDP_REQUEST@@@Z; CUList<_SSDP_REQUEST>::HrPushFront(_SSDP_REQUEST const &)
0x180016f2e  mov     ebx, eax
0x180016f30  test    eax, eax
0x180016f32  js      short loc_180016FB1
0x180016f34  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f3b  lea     rax, WPP_GLOBAL_Control
0x180016f42  cmp     rcx, rax
0x180016f45  jz      short loc_180016F6B
0x180016f47  test    byte ptr [rcx+1Ch], 8
0x180016f4b  jz      short loc_180016F6B
0x180016f4d  mov     rax, [rbp+4Fh+var_50]
0x180016f51  mov     r9, r14
0x180016f54  mov     rcx, [rcx+10h]
0x180016f58  mov     rdx, [rax+30h]
0x180016f5c  mov     [rsp+100h+var_D8], rdx
0x180016f61  mov     [rsp+100h+var_E0], r15d
0x180016f66  call    WPP_SF_sds
0x180016f6b  inc     esi
0x180016f6d  lea     rcx, [rsp+100h+var_D0]
0x180016f72  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180016f77  test    eax, eax
0x180016f79  jz      loc_180016EA1
0x180016f7f  test    ebx, ebx
0x180016f81  js      short loc_180016FA5
0x180016f83  mov     r12, [rbp+4Fh+arg_20]
0x180016f87  mov     ecx, 10h; Size
0x180016f8c  call    cs:__imp_malloc
0x180016f93  nop     dword ptr [rax+rax+00h]
0x180016f98  mov     rdi, rax
0x180016f9b  test    rax, rax
0x180016f9e  jnz     short loc_180016FBC
0x180016fa0  mov     ebx, 8007000Eh
0x180016fa5  lea     r15, WPP_GLOBAL_Control
0x180016fac  jmp     loc_18001703A
0x180016fb1  lea     rcx, [rbp+4Fh+var_A0]; struct _SSDP_REQUEST *
0x180016fb5  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180016fba  jmp     short loc_180016FA5
0x180016fbc  mov     [rax], esi
0x180016fbe  mov     qword ptr [rax+8], 0
0x180016fc6  test    esi, esi
0x180016fc8  jz      loc_180017098
0x180016fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180016fd5  lea     r15, WPP_GLOBAL_Control
0x180016fdc  cmp     rcx, r15
0x180016fdf  jz      short loc_180016FFF
0x180016fe1  test    byte ptr [rcx+1Ch], 8
0x180016fe5  jz      short loc_180016FFF
0x180016fe7  mov     rcx, [rcx+10h]
0x180016feb  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180016ff2  mov     edx, 49h ; 'I'
0x180016ff7  mov     r9d, esi
0x180016ffa  call    WPP_SF_d
0x180016fff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180017006  movsxd  r14, esi
0x180017009  mov     eax, 58h ; 'X'
0x18001700e  mul     r14
0x180017011  cmovb   rax, rcx
0x180017015  mov     rcx, rax; Size
0x180017018  call    cs:__imp_malloc
0x18001701f  nop     dword ptr [rax+rax+00h]
0x180017024  mov     [rdi+8], rax
0x180017028  test    rax, rax
0x18001702b  jnz     short loc_180017088
0x18001702d  mov     rcx, rdi; void *
0x180017030  mov     ebx, 8007000Eh
0x180017035  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001703a  cmp     [rbp+4Fh+var_C8], 0
0x18001703f  lea     rax, [rbp+4Fh+var_C8]
0x180017043  mov     [rsp+100h+var_D0], rax
0x180017048  jz      loc_180017134
0x18001704e  mov     [rbp+4Fh+arg_20], 0
0x180017056  lea     rdx, [rbp+4Fh+arg_20]
0x18001705a  lea     rcx, [rsp+100h+var_D0]
0x18001705f  call    ?HrGetItem@Iterator@?$CUList@U_SSDP_REQUEST@@@@QEAAJPEAPEAU_SSDP_REQUEST@@@Z; CUList<_SSDP_REQUEST>::Iterator::HrGetItem(_SSDP_REQUEST * *)
0x180017064  test    eax, eax
0x180017066  jnz     loc_180017134
0x18001706c  mov     rcx, [rbp+4Fh+arg_20]; struct _SSDP_REQUEST *
0x180017070  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180017075  lea     rcx, [rsp+100h+var_D0]
0x18001707a  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001707f  test    eax, eax
0x180017081  jz      short loc_180017056
0x180017083  jmp     loc_180017134
0x180017088  imul    r8, r14, 58h ; 'X'; Size
0x18001708c  xor     edx, edx; Val
0x18001708e  mov     rcx, rax; void *
0x180017091  call    memset_0
0x180017096  jmp     short loc_18001709F
0x180017098  lea     r15, WPP_GLOBAL_Control
0x18001709f  mov     r8, [rdi+8]
0x1800170a3  test    r8, r8
0x1800170a6  jz      loc_180017130
0x1800170ac  cmp     [rbp+4Fh+var_C8], 0
0x1800170b1  lea     rax, [rbp+4Fh+var_C8]
0x1800170b5  mov     [rsp+100h+var_D0], rax
0x1800170ba  jz      short loc_180017130
0x1800170bc  mov     [rbp+4Fh+arg_20], 0
0x1800170c4  imul    r9d, esi, 58h ; 'X'
0x1800170c8  lea     rdx, [rbp+4Fh+arg_20]
0x1800170cc  lea     rcx, [rsp+100h+var_D0]
0x1800170d1  call    ?HrGetItem@Iterator@?$CUList@U_SSDP_REQUEST@@@@QEAAJPEAPEAU_SSDP_REQUEST@@@Z; CUList<_SSDP_REQUEST>::Iterator::HrGetItem(_SSDP_REQUEST * *)
0x1800170d6  test    eax, eax
0x1800170d8  jnz     short loc_180017130
0x1800170da  cmp     r9d, 58h ; 'X'
0x1800170de  jb      short loc_180017122
0x1800170e0  mov     rax, [rbp+4Fh+arg_20]
0x1800170e4  movups  xmm0, xmmword ptr [rax]
0x1800170e7  movups  xmmword ptr [r8], xmm0
0x1800170eb  movups  xmm1, xmmword ptr [rax+10h]
0x1800170ef  movups  xmmword ptr [r8+10h], xmm1
0x1800170f4  movups  xmm0, xmmword ptr [rax+20h]
0x1800170f8  movups  xmmword ptr [r8+20h], xmm0
0x1800170fd  movups  xmm1, xmmword ptr [rax+30h]
0x180017101  movups  xmmword ptr [r8+30h], xmm1
0x180017106  movups  xmm0, xmmword ptr [rax+40h]
0x18001710a  movups  xmmword ptr [r8+40h], xmm0
0x18001710f  movsd   xmm1, qword ptr [rax+50h]
0x180017114  movsd   qword ptr [r8+50h], xmm1
0x18001711a  add     r8, 58h ; 'X'
0x18001711e  add     r9d, 0FFFFFFA8h
0x180017122  lea     rcx, [rsp+100h+var_D0]
0x180017127  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001712c  test    eax, eax
0x18001712e  jz      short loc_1800170C8
0x180017130  mov     [r12], rdi
0x180017134  test    ebx, ebx
0x180017136  jz      short loc_180017162
0x180017138  mov     rcx, cs:WPP_GLOBAL_Control
0x18001713f  cmp     rcx, r15
0x180017142  jz      short loc_180017162
0x180017144  test    byte ptr [rcx+1Ch], 1
0x180017148  jz      short loc_180017162
0x18001714a  mov     rcx, [rcx+10h]
0x18001714e  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180017155  mov     edx, 4Ah ; 'J'
0x18001715a  mov     r9d, ebx
0x18001715d  call    WPP_SF_d
0x180017162  mov     rcx, [rbp+4Fh+var_C8]; void *
0x180017166  test    rcx, rcx
0x180017169  jz      short loc_180017170
0x18001716b  call    ??_GNode@?$CUList@_J@@QEAAPEAXI@Z; CUList<__int64>::Node::`scalar deleting destructor'(uint)
0x180017170  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x180017174  mov     [rbp+4Fh+var_C8], 0
0x18001717c  call    cs:__imp_LeaveCriticalSection
0x180017183  nop     dword ptr [rax+rax+00h]
0x180017188  mov     eax, ebx
0x18001718a  add     rsp, 0C8h
0x180017191  pop     r15
0x180017193  pop     r14
0x180017195  pop     r13
0x180017197  pop     r12
0x180017199  pop     rdi
0x18001719a  pop     rsi
0x18001719b  pop     rbx
0x18001719c  pop     rbp
0x18001719d  retn
```
