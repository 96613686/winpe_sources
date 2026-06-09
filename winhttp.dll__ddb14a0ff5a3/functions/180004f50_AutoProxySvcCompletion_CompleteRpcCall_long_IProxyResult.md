# AutoProxySvcCompletion::CompleteRpcCall(long,IProxyResult *)

- ea: `0x180004f50`
- end: `0x1800054a4`
- name: `?CompleteRpcCall@AutoProxySvcCompletion@@QEAAJJPEAUIProxyResult@@@Z`
- size: `1364`
- prototype: `__int64 __fastcall(AutoProxySvcCompletion *__hidden this, int, struct IProxyResult *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004d40`

## callees

- `0x1800032ac`
- `0x1800037a4`
- `0x180003eec`
- `0x180004f50`
- `0x1800054ac`
- `0x180005670`
- `0x180005770`
- `0x18001b480`
- `0x180020e40`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800d2a8c`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005340`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005443`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000544e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005443`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000544e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800050c2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800050c2`

## pseudocode

```c
__int64 __fastcall AutoProxySvcCompletion::CompleteRpcCall(
        AutoProxySvcCompletion *this,
        int a2,
        struct IProxyResult *a3)
{
  _DWORD *v6; // rax
  _BYTE *v7; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rax
  _BYTE *v10; // rax
  char *v11; // rdi
  CRpcWatchDog *v12; // rcx
  unsigned int v13; // eax
  char *v15; // rdi
  unsigned int v16; // esi
  unsigned int j; // r14d
  __int64 v18; // rax
  HANDLE *v19; // rcx
  _DWORD *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // esi
  unsigned int i; // r15d
  char *v24; // r14
  __int64 v25; // rcx
  void **v26; // [rsp+28h] [rbp-E0h]
  HANDLE hObject; // [rsp+48h] [rbp-C0h] BYREF
  int Reply; // [rsp+50h] [rbp-B8h] BYREF
  int v29; // [rsp+54h] [rbp-B4h]
  int v30; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v31[56]; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID v32[2]; // [rsp+98h] [rbp-70h] BYREF
  HANDLE v33[2]; // [rsp+A8h] [rbp-60h]
  __int128 v34; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v35; // [rsp+C8h] [rbp-40h]
  __int128 v36; // [rsp+D8h] [rbp-30h]
  __int128 v37; // [rsp+E8h] [rbp-20h]
  __int64 v38; // [rsp+F8h] [rbp-10h]

  Reply = 0;
  v38 = 0;
  v29 = 0;
  hObject = 0;
  *(_OWORD *)v32 = 0;
  v30 = 0;
  *(_OWORD *)v33 = 0;
  memset(v31, 0, sizeof(v31));
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qdqDl(
      (_DWORD)this,
      a2,
      (_DWORD)a3,
      (_DWORD)this,
      a2,
      (__int64)a3,
      *((_DWORD *)this + 79),
      *((_DWORD *)this + 78));
  v6 = (_DWORD *)*((_QWORD *)this + 23);
  if ( v6 )
    *v6 = 0;
  v7 = (_BYTE *)*((_QWORD *)this + 24);
  if ( v7 )
  {
    v8 = 56;
    do
    {
      *v7++ = 0;
      --v8;
    }
    while ( v8 );
  }
  v9 = (_QWORD *)*((_QWORD *)this + 25);
  if ( v9 )
    *v9 = 0;
  v10 = (_BYTE *)*((_QWORD *)this + 31);
  if ( v10 )
  {
    v25 = 72;
    do
    {
      *v10++ = 0;
      --v25;
    }
    while ( v25 );
  }
  if ( !*((_DWORD *)this + 78) )
  {
    Reply = AutoProxySvcCompletion::ProcessProxyResult(this, a2, a3, (struct _PROXY_RESULT *)v32, &hObject);
    if ( Reply < 0 )
    {
      v29 = 4013;
      goto LABEL_14;
    }
    *(LPVOID *)v31 = v32[0];
    *(_OWORD *)&v31[8] = __PAIR128__((unsigned __int64)v33[0], (unsigned __int64)v32[1]);
    *(HANDLE *)&v31[24] = v33[1];
    *(_OWORD *)v32 = 0;
    *(_OWORD *)v33 = 0;
    if ( a3 )
    {
      (*(void (__fastcall **)(struct IProxyResult *, int *))(*(_QWORD *)a3 + 80LL))(a3, &v30);
      *(_DWORD *)&v31[32] = v30;
    }
    if ( *((_QWORD *)this + 31) )
    {
      Reply = AutoProxySvcCompletion::ProcessProxySettingsExResult(
                this,
                (struct _PROXY_CONFIG_INFO *)v31,
                a3,
                (struct _PROXY_SETTINGS_EX *)&v34);
      if ( Reply < 0 )
      {
        v29 = 4030;
        goto LABEL_14;
      }
    }
    goto LABEL_32;
  }
  if ( *((_DWORD *)this + 79) )
  {
    Reply = AutoProxySvcCompletion::ProcessAggregatedProxyConfigResult(this, (struct _PROXY_CONFIG_INFO *)v31, &hObject);
    if ( Reply < 0 )
    {
      v29 = 4051;
LABEL_14:
      if ( hObject )
        CloseHandle(hObject);
      goto LABEL_16;
    }
    *(_DWORD *)&v31[48] = IsProxySettingsPerUser();
LABEL_32:
    v18 = *((_QWORD *)this + 24);
    if ( v18 )
    {
      *(_OWORD *)v18 = *(_OWORD *)v31;
      *(_OWORD *)(v18 + 16) = *(_OWORD *)&v31[16];
      *(_OWORD *)(v18 + 32) = *(_OWORD *)&v31[32];
      *(_QWORD *)(v18 + 48) = *(_QWORD *)&v31[48];
      memset(v31, 0, sizeof(v31));
    }
    v19 = (HANDLE *)*((_QWORD *)this + 25);
    if ( v19 )
    {
      *v19 = hObject;
      hObject = 0;
    }
    v20 = (_DWORD *)*((_QWORD *)this + 23);
    if ( v20 )
      *v20 = *((_DWORD *)this + 65);
    v21 = *((_QWORD *)this + 31);
    if ( v21 )
    {
      *(_OWORD *)v21 = v34;
      *(_OWORD *)(v21 + 16) = v35;
      *(_OWORD *)(v21 + 32) = v36;
      *(_OWORD *)(v21 + 48) = v37;
      *(_QWORD *)(v21 + 64) = v38;
      memset_0(&v34, 0, 0x48u);
    }
    goto LABEL_14;
  }
  Reply = a2;
  if ( a2 >= 0 )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_q(1029, 133, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids);
    Reply = -2147023728;
    v29 = 4047;
  }
  else
  {
    v29 = 4039;
  }
LABEL_16:
  v11 = (char *)v32[1];
  if ( v33[0] )
    CloseHandle(v33[0]);
  if ( v11 )
  {
    v22 = 0;
    for ( i = (unsigned int)v32[0]; v22 < i; ++v22 )
    {
      v24 = &v11[32 * v22];
      if ( v24 )
      {
        WxFreeHeapEx(v24 + 16);
        *(_OWORD *)v24 = 0;
        *((_OWORD *)v24 + 1) = 0;
      }
    }
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v11);
    else
      HeapFree(g_hWxProcessHeap, 0, v11);
  }
  if ( *((_DWORD *)this + 79) )
  {
    v15 = *(char **)&v31[40];
    v16 = *(_DWORD *)&v31[36];
    FreeProxyResultEx<WxHeapAllocator>(v31);
    memset(v31, 0, sizeof(v31));
    if ( v15 )
    {
      for ( j = 0; j < v16; ++j )
        FreeProxyResultEx<WxHeapAllocator>(&v15[40 * j]);
      if ( g_fWxHeapExtensionInitialized )
        g_WxHeapExtensionInterfaces(v15);
      else
        HeapFree(g_hWxProcessHeap, 0, v15);
    }
  }
  FreeProxySettingsEx<_PROXY_SETTINGS_EX,WxHeapAllocator>(&v34);
  CRpcWatchDog::RemoveEntry(v12, (AutoProxySvcCompletion *)((char *)this + 280));
  v13 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)this + 22), &Reply);
  if ( v13 && (xmmword_180107A50 & 0x20) != 0 )
    WPP_SF_d(517, 134, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, v13, v26);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 135, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)Reply, v26);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180004f50  mov     r11, rsp
0x180004f53  push    rbp
0x180004f54  lea     rbp, [r11-48h]
0x180004f58  sub     rsp, 140h
0x180004f5f  mov     rax, cs:__security_cookie
0x180004f66  xor     rax, rsp
0x180004f69  mov     [rbp+40h+var_40], rax
0x180004f6d  xorps   xmm0, xmm0
0x180004f70  mov     [r11-10h], rbx
0x180004f74  xorps   xmm1, xmm1
0x180004f77  mov     [r11-18h], rsi
0x180004f7b  mov     [r11-20h], rdi
0x180004f7f  mov     esi, edx
0x180004f81  mov     [r11-28h], r12
0x180004f85  mov     rdi, r8
0x180004f88  xor     r12d, r12d
0x180004f8b  mov     rbx, rcx
0x180004f8e  xor     eax, eax
0x180004f90  mov     [rsp+140h+Reply], r12d
0x180004f95  mov     [rbp+40h+var_50], rax
0x180004f99  mov     [rsp+140h+var_F4], r12d
0x180004f9e  mov     [rsp+140h+hObject], r12
0x180004fa3  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x180004fa7  mov     dword ptr [rsp+140h+var_F0], r12d
0x180004fac  movups  xmmword ptr [rbp+40h+var_A0], xmm0
0x180004fb0  mov     qword ptr [rsp+140h+var_F0+8], r12
0x180004fb5  movups  [rsp+140h+var_E0], xmm0
0x180004fba  movups  [rsp+140h+var_D0], xmm0
0x180004fbf  movups  xmmword ptr [rbp+40h+lpMem], xmm0
0x180004fc3  movups  [rbp+40h+var_90], xmm1
0x180004fc7  movups  [rbp+40h+var_80], xmm1
0x180004fcb  movups  [rbp+40h+var_70], xmm1
0x180004fcf  movups  [rbp+40h+var_60], xmm1
0x180004fd3  test    byte ptr cs:xmmword_180107A60, 20h
0x180004fda  jnz     loc_1800053C6
0x180004fe0  mov     rax, [rbx+0B8h]
0x180004fe7  test    rax, rax
0x180004fea  jz      short loc_180004FEF
0x180004fec  mov     [rax], r12d
0x180004fef  mov     rax, [rbx+0C0h]
0x180004ff6  test    rax, rax
0x180004ff9  jz      short loc_18000500D
0x180004ffb  mov     ecx, 38h ; '8'
0x180005000  mov     [rax], r12b
0x180005003  lea     rax, [rax+1]
0x180005007  sub     rcx, 1
0x18000500b  jnz     short loc_180005000
0x18000500d  mov     rax, [rbx+0C8h]
0x180005014  test    rax, rax
0x180005017  jz      short loc_18000501C
0x180005019  mov     [rax], r12
0x18000501c  mov     rax, [rbx+0F8h]
0x180005023  test    rax, rax
0x180005026  jnz     loc_1800053F0
0x18000502c  cmp     [rbx+138h], r12d
0x180005033  jnz     loc_18000534B
0x180005039  lea     rax, [rsp+140h+hObject]
0x18000503e  mov     r8, rdi; struct IProxyResult *
0x180005041  lea     r9, [rbp+40h+var_B0]; struct _PROXY_RESULT *
0x180005045  mov     [rsp+140h+var_120], rax; void **
0x18000504a  mov     edx, esi; int
0x18000504c  mov     rcx, rbx; this
0x18000504f  call    ?ProcessProxyResult@AutoProxySvcCompletion@@QEAAJJPEAUIProxyResult@@PEAU_PROXY_RESULT@@PEAPEAX@Z; AutoProxySvcCompletion::ProcessProxyResult(long,IProxyResult *,_PROXY_RESULT *,void * *)
0x180005054  mov     [rsp+140h+Reply], eax
0x180005058  test    eax, eax
0x18000505a  jns     loc_180005194
0x180005060  mov     [rsp+140h+var_F4], 0FADh
0x180005068  mov     rcx, [rsp+140h+hObject]; hObject
0x18000506d  test    rcx, rcx
0x180005070  jnz     loc_180005443
0x180005076  mov     rcx, [rbp+40h+var_A0]; hObject
0x18000507a  mov     rdi, [rbp+40h+var_B0+8]
0x18000507e  test    rcx, rcx
0x180005081  jnz     loc_18000544E
0x180005087  mov     [rsp+140h+var_28], r14
0x18000508f  test    rdi, rdi
0x180005092  jnz     loc_1800052E7
0x180005098  cmp     [rbx+13Ch], r12d
0x18000509f  jnz     short loc_18000511E
0x1800050a1  lea     rcx, [rbp+40h+var_90]
0x1800050a5  call    ??$FreeProxySettingsEx@U_PROXY_SETTINGS_EX@@VWxHeapAllocator@@@@YAXPEAU_PROXY_SETTINGS_EX@@@Z; FreeProxySettingsEx<_PROXY_SETTINGS_EX,WxHeapAllocator>(_PROXY_SETTINGS_EX *)
0x1800050aa  lea     rdx, [rbx+118h]; struct _WatchDogEntry *
0x1800050b1  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x1800050b6  mov     rcx, [rbx+0B0h]; pAsync
0x1800050bd  lea     rdx, [rsp+140h+Reply]; Reply
0x1800050c2  call    cs:__imp_RpcAsyncCompleteCall
0x1800050c8  mov     r14, [rsp+140h+var_28]
0x1800050d0  mov     r12, [rsp+140h+var_20]
0x1800050d8  mov     rdi, [rsp+140h+var_18]
0x1800050e0  mov     rsi, [rsp+140h+var_10]
0x1800050e8  mov     rbx, [rsp+138h]
0x1800050f0  test    eax, eax
0x1800050f2  jnz     loc_180005459
0x1800050f8  test    byte ptr cs:xmmword_180107A60, 20h
0x1800050ff  jnz     loc_180005484
0x180005105  mov     eax, [rsp+140h+Reply]
0x180005109  mov     rcx, [rbp+40h+var_40]
0x18000510d  xor     rcx, rsp; StackCookie
0x180005110  call    __security_check_cookie
0x180005115  add     rsp, 140h
0x18000511c  pop     rbp
0x18000511d  retn
0x18000511e  mov     rdi, [rbp+40h+lpMem]
0x180005122  lea     rcx, [rsp+140h+var_F0+8]
0x180005127  mov     esi, dword ptr [rsp+140h+var_D0+0Ch]
0x18000512b  call    ??$FreeProxyResultEx@VWxHeapAllocator@@@@YAXPEAU_PROXY_RESULT@@@Z; FreeProxyResultEx<WxHeapAllocator>(_PROXY_RESULT *)
0x180005130  xorps   xmm0, xmm0
0x180005133  xor     eax, eax
0x180005135  mov     [rbp+40h+lpMem+8], rax
0x180005139  movups  [rsp+140h+var_F0+8], xmm0
0x18000513e  movups  [rsp+140h+var_E0+8], xmm0
0x180005143  movups  [rsp+140h+var_D0+8], xmm0
0x180005148  test    rdi, rdi
0x18000514b  jz      loc_1800050A1
0x180005151  mov     r14d, r12d
0x180005154  test    esi, esi
0x180005156  jz      short loc_180005170
0x180005158  mov     eax, r14d
0x18000515b  lea     rcx, [rax+rax*4]
0x18000515f  lea     rcx, [rdi+rcx*8]
0x180005163  call    ??$FreeProxyResultEx@VWxHeapAllocator@@@@YAXPEAU_PROXY_RESULT@@@Z; FreeProxyResultEx<WxHeapAllocator>(_PROXY_RESULT *)
0x180005168  inc     r14d
0x18000516b  cmp     r14d, esi
0x18000516e  jb      short loc_180005158
0x180005170  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r12d; int g_fWxHeapExtensionInitialized
0x180005177  jnz     loc_1800053A0
0x18000517d  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180005184  mov     r8, rdi; lpMem
0x180005187  xor     edx, edx; dwFlags
0x180005189  call    cs:__imp_HeapFree
0x18000518f  jmp     loc_1800050A1
0x180005194  mov     eax, dword ptr [rbp+40h+var_B0]
0x180005197  xorps   xmm0, xmm0
0x18000519a  mov     dword ptr [rsp+140h+var_F0+8], eax
0x18000519e  mov     eax, dword ptr [rbp+40h+var_B0+4]
0x1800051a1  mov     dword ptr [rsp+140h+var_F0+0Ch], eax
0x1800051a5  mov     rax, [rbp+40h+var_B0+8]
0x1800051a9  mov     qword ptr [rsp+140h+var_E0], rax
0x1800051ae  mov     rax, [rbp+40h+var_A0]
0x1800051b2  mov     qword ptr [rsp+140h+var_E0+8], rax
0x1800051b7  mov     rax, [rbp+40h+var_A0+8]
0x1800051bb  mov     qword ptr [rsp+140h+var_D0], rax
0x1800051c0  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x1800051c4  movups  xmmword ptr [rbp+40h+var_A0], xmm0
0x1800051c8  test    rdi, rdi
0x1800051cb  jz      short loc_1800051E9
0x1800051cd  mov     rax, [rdi]
0x1800051d0  lea     rdx, [rsp+140h+var_F0]
0x1800051d5  mov     rcx, rdi
0x1800051d8  mov     rax, [rax+50h]
0x1800051dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051e1  mov     eax, dword ptr [rsp+140h+var_F0]
0x1800051e5  mov     dword ptr [rsp+140h+var_D0+8], eax
0x1800051e9  cmp     [rbx+0F8h], r12
0x1800051f0  jnz     loc_1800052BA
0x1800051f6  mov     rax, [rbx+0C0h]
0x1800051fd  test    rax, rax
0x180005200  jz      short loc_18000523E
0x180005202  movups  xmm0, [rsp+140h+var_F0+8]
0x180005207  movups  xmmword ptr [rax], xmm0
0x18000520a  movups  xmm1, [rsp+140h+var_E0+8]
0x18000520f  movups  xmmword ptr [rax+10h], xmm1
0x180005213  movups  xmm0, [rsp+140h+var_D0+8]
0x180005218  movups  xmmword ptr [rax+20h], xmm0
0x18000521c  movsd   xmm1, [rbp+40h+lpMem+8]
0x180005221  xorps   xmm0, xmm0
0x180005224  movsd   qword ptr [rax+30h], xmm1
0x180005229  xor     eax, eax
0x18000522b  mov     [rbp+40h+lpMem+8], rax
0x18000522f  movups  [rsp+140h+var_F0+8], xmm0
0x180005234  movups  [rsp+140h+var_E0+8], xmm0
0x180005239  movups  [rsp+140h+var_D0+8], xmm0
0x18000523e  mov     rcx, [rbx+0C8h]
0x180005245  test    rcx, rcx
0x180005248  jz      short loc_180005257
0x18000524a  mov     rax, [rsp+140h+hObject]
0x18000524f  mov     [rcx], rax
0x180005252  mov     [rsp+140h+hObject], r12
0x180005257  mov     rcx, [rbx+0B8h]
0x18000525e  test    rcx, rcx
0x180005261  jz      short loc_18000526B
0x180005263  mov     eax, [rbx+104h]
0x180005269  mov     [rcx], eax
0x18000526b  mov     rax, [rbx+0F8h]
0x180005272  test    rax, rax
0x180005275  jz      loc_180005068
0x18000527b  movaps  xmm0, [rbp+40h+var_90]
0x18000527f  lea     rcx, [rbp+40h+var_90]; void *
0x180005283  movups  xmmword ptr [rax], xmm0
0x180005286  xor     edx, edx; Val
0x180005288  mov     r8d, 48h ; 'H'; Size
0x18000528e  movaps  xmm1, [rbp+40h+var_80]
0x180005292  movups  xmmword ptr [rax+10h], xmm1
0x180005296  movaps  xmm0, [rbp+40h+var_70]
0x18000529a  movups  xmmword ptr [rax+20h], xmm0
0x18000529e  movaps  xmm1, [rbp+40h+var_60]
0x1800052a2  movups  xmmword ptr [rax+30h], xmm1
0x1800052a6  movsd   xmm0, [rbp+40h+var_50]
0x1800052ab  movsd   qword ptr [rax+40h], xmm0
0x1800052b0  call    memset_0
0x1800052b5  jmp     loc_180005068
0x1800052ba  lea     r9, [rbp+40h+var_90]; struct _PROXY_SETTINGS_EX *
0x1800052be  mov     r8, rdi; struct IProxyResult *
0x1800052c1  lea     rdx, [rsp+140h+var_F0+8]; struct _PROXY_CONFIG_INFO *
0x1800052c6  mov     rcx, rbx; this
0x1800052c9  call    ?ProcessProxySettingsExResult@AutoProxySvcCompletion@@QEAAJPEAU_PROXY_CONFIG_INFO@@PEAUIProxyResult@@PEAU_PROXY_SETTINGS_EX@@@Z; AutoProxySvcCompletion::ProcessProxySettingsExResult(_PROXY_CONFIG_INFO *,IProxyResult *,_PROXY_SETTINGS_EX *)
0x1800052ce  mov     [rsp+140h+Reply], eax
0x1800052d2  test    eax, eax
0x1800052d4  jns     loc_1800051F6
0x1800052da  mov     [rsp+140h+var_F4], 0FBEh
0x1800052e2  jmp     loc_180005068
0x1800052e7  mov     [rsp+140h+var_30], r15
0x1800052ef  mov     esi, r12d
0x1800052f2  mov     r15d, dword ptr [rbp+40h+var_B0]
0x1800052f6  test    r15d, r15d
0x1800052f9  jz      short loc_180005323
0x1800052fb  mov     r14d, esi
0x1800052fe  shl     r14, 5
0x180005302  add     r14, rdi
0x180005305  jz      short loc_18000531C
0x180005307  lea     rcx, [r14+10h]
0x18000530b  call    WxFreeHeapEx
0x180005310  xorps   xmm0, xmm0
0x180005313  movups  xmmword ptr [r14], xmm0
0x180005317  movups  xmmword ptr [r14+10h], xmm0
0x18000531c  inc     esi
0x18000531e  cmp     esi, r15d
0x180005321  jb      short loc_1800052FB
0x180005323  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r12d; int g_fWxHeapExtensionInitialized
0x18000532a  mov     r15, [rsp+140h+var_30]
0x180005332  jnz     short loc_18000538C
0x180005334  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18000533b  mov     r8, rdi; lpMem
0x18000533e  xor     edx, edx; dwFlags
0x180005340  call    cs:__imp_HeapFree
0x180005346  jmp     loc_180005098
0x18000534b  cmp     [rbx+13Ch], r12d
0x180005352  jz      loc_1800053F7
0x180005358  lea     r8, [rsp+140h+hObject]; void **
0x18000535d  mov     rcx, rbx; this
0x180005360  lea     rdx, [rsp+140h+var_F0+8]; struct _PROXY_CONFIG_INFO *
0x180005365  call    ?ProcessAggregatedProxyConfigResult@AutoProxySvcCompletion@@QEAAJPEAU_PROXY_CONFIG_INFO@@PEAPEAX@Z; AutoProxySvcCompletion::ProcessAggregatedProxyConfigResult(_PROXY_CONFIG_INFO *,void * *)
0x18000536a  mov     [rsp+140h+Reply], eax
0x18000536e  test    eax, eax
0x180005370  js      short loc_18000537F
0x180005372  call    ?IsProxySettingsPerUser@@YAHXZ; IsProxySettingsPerUser(void)
0x180005377  mov     dword ptr [rbp+40h+lpMem+8], eax
0x18000537a  jmp     loc_1800051F6
0x18000537f  mov     [rsp+140h+var_F4], 0FD3h
0x180005387  jmp     loc_180005068
0x18000538c  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180005393  mov     rcx, rdi
0x180005396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539b  jmp     loc_180005098
0x1800053a0  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x1800053a7  mov     rcx, rdi
0x1800053aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053af  jmp     loc_1800050A1
0x1800053b4  mov     [rax], r12b
0x1800053b7  lea     rax, [rax+1]
0x1800053bb  sub     rcx, 1
0x1800053bf  jnz     short loc_1800053B4
0x1800053c1  jmp     loc_18000502C
0x1800053c6  mov     eax, [rcx+138h]
0x1800053cc  mov     r9, rbx
0x1800053cf  mov     dword ptr [rsp+140h+var_108], eax
0x1800053d3  mov     eax, [rcx+13Ch]
0x1800053d9  mov     [rsp+140h+var_110], eax
0x1800053dd  mov     qword ptr [rsp+140h+var_118], rdi
0x1800053e2  mov     dword ptr [rsp+140h+var_120], esi
0x1800053e6  call    WPP_SF_qdqDl
0x1800053eb  jmp     loc_180004FE0
0x1800053f0  mov     ecx, 48h ; 'H'
0x1800053f5  jmp     short loc_1800053B4
0x1800053f7  mov     [rsp+140h+Reply], esi
0x1800053fb  test    esi, esi
0x1800053fd  jns     short loc_18000540C
0x1800053ff  mov     [rsp+140h+var_F4], 0FC7h
0x180005407  jmp     loc_180005076
0x18000540c  test    byte ptr cs:xmmword_180107A60, 20h
0x180005413  jz      short loc_18000542E
0x180005415  mov     edx, 85h
0x18000541a  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x180005421  mov     ecx, 405h
0x180005426  mov     r9, rbx
0x180005429  call    WPP_SF_q
0x18000542e  mov     [rsp+140h+Reply], 80070490h
0x180005436  mov     [rsp+140h+var_F4], 0FCFh
0x18000543e  jmp     loc_180005076
0x180005443  call    cs:__imp_CloseHandle
0x180005449  jmp     loc_180005076
0x18000544e  call    cs:__imp_CloseHandle
0x180005454  jmp     loc_180005087
0x180005459  test    byte ptr cs:xmmword_180107A50, 20h
0x180005460  jz      loc_1800050F8
0x180005466  mov     edx, 86h
0x18000546b  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x180005472  mov     ecx, 205h
0x180005477  mov     r9d, eax
0x18000547a  call    WPP_SF_d
  ... truncated ...
```
