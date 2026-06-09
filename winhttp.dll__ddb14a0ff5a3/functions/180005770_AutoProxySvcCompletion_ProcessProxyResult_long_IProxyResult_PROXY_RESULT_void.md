# AutoProxySvcCompletion::ProcessProxyResult(long,IProxyResult *,_PROXY_RESULT *,void * *)

- ea: `0x180005770`
- end: `0x180005f16`
- name: `?ProcessProxyResult@AutoProxySvcCompletion@@QEAAJJPEAUIProxyResult@@PEAU_PROXY_RESULT@@PEAPEAX@Z`
- size: `1958`
- prototype: `__int64 __fastcall(AutoProxySvcCompletion *__hidden this, int, struct IProxyResult *, struct _PROXY_RESULT *, void **)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800032ac`
- `0x180004f50`

## callees

- `0x180005770`
- `0x180007614`
- `0x180007a80`
- `0x18001b480`
- `0x180069854`
- `0x18008bfc4`
- `0x180091f14`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800cf34c`
- `0x1800cf4c4`
- `0x1800d23ec`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800db758`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800059ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800059ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800059e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005a5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800059e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005a5e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005ed4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005ed4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005cf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005cf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ee2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005eed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ee2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005eed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058d4`

## pseudocode

```c
__int64 __fastcall AutoProxySvcCompletion::ProcessProxyResult(
        AutoProxySvcCompletion *this,
        int a2,
        struct IProxyResult *a3,
        struct _PROXY_RESULT *a4,
        void **a5)
{
  struct _PROXY_RESULT *v6; // rax
  void *v9; // r13
  __int64 v10; // rcx
  int v11; // ebx
  HANDLE v12; // rcx
  char *v13; // rsi
  unsigned int v14; // r15d
  void *v15; // rcx
  int v17; // edx
  int v18; // r8d
  char v19; // al
  __int64 v20; // r14
  int v21; // r15d
  RTL_SRWLOCK *v22; // r12
  int v23; // eax
  unsigned int v24; // esi
  int v25; // ecx
  __int128 v26; // xmm1
  char *v27; // r15
  struct _PROXY_RESULT *v28; // rax
  __int128 v29; // xmm1
  int v30; // eax
  unsigned int i; // edi
  char *v32; // r14
  unsigned int v33; // r12d
  char *v34; // r14
  void *v35; // [rsp+20h] [rbp-E8h]
  int v36; // [rsp+40h] [rbp-C8h]
  void *v37; // [rsp+48h] [rbp-C0h] BYREF
  int v38; // [rsp+54h] [rbp-B4h]
  RTL_SRWLOCK *v39; // [rsp+58h] [rbp-B0h]
  struct _PROXY_RESULT *v40; // [rsp+60h] [rbp-A8h]
  void **v41; // [rsp+68h] [rbp-A0h]
  HANDLE hObject; // [rsp+70h] [rbp-98h] BYREF
  __int64 v43; // [rsp+78h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-88h] BYREF
  LPVOID lpMem[2]; // [rsp+88h] [rbp-80h] BYREF
  HANDLE v46[2]; // [rsp+98h] [rbp-70h]
  LPVOID v47[2]; // [rsp+A8h] [rbp-60h] BYREF
  HANDLE v48[2]; // [rsp+B8h] [rbp-50h]

  v6 = a4;
  v41 = a5;
  v40 = a4;
  pv = 0;
  v9 = 0;
  hObject = 0;
  v43 = 0;
  v37 = 0;
  *(_OWORD *)lpMem = 0;
  *(_OWORD *)v46 = 0;
  if ( a4 )
  {
    v10 = 32;
    do
    {
      *(_BYTE *)v6 = 0;
      v6 = (struct _PROXY_RESULT *)((char *)v6 + 1);
      --v10;
    }
    while ( v10 );
  }
  if ( a5 )
    *a5 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qlq(1029, 117, (unsigned int)WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (_DWORD)this, a2, (__int64)a3);
  if ( !a3 )
    goto LABEL_9;
  v11 = (**(__int64 (__fastcall ***)(struct IProxyResult *, GUID *, __int64 *))a3)(a3, &IID_ICmProxyResult, &v43);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v43 + 120LL))(v43, &hObject);
    if ( v11 < 0 )
      goto LABEL_10;
  }
  v30 = v11;
  v11 = 0;
  if ( v30 != -2147467262 )
    v11 = v30;
  if ( a2 >= 0 )
  {
    if ( v11 < 0 )
      goto LABEL_10;
  }
  else
  {
LABEL_9:
    v11 = a2;
    if ( a2 < 0 )
      goto LABEL_10;
    if ( !a3 )
    {
      if ( (xmmword_180107A60 & 0x20) != 0 )
        WPP_SF_q(1029, 118, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids);
      v11 = -2147023728;
      goto LABEL_10;
    }
  }
  v11 = (*(__int64 (__fastcall **)(struct IProxyResult *, LPVOID *))(*(_QWORD *)a3 + 72LL))(a3, &pv);
  if ( v11 >= 0 )
  {
    v19 = xmmword_180107A60;
    if ( (xmmword_180107A60 & 0x20) != 0 )
    {
      WPP_SF_SlllD(
        *(_DWORD *)(*((_QWORD *)this + 5) + 20LL),
        v17,
        v18,
        (_DWORD)pv,
        *((_DWORD *)this + 65),
        *((_DWORD *)this + 66),
        *((_DWORD *)this + 64),
        *(_DWORD *)(*((_QWORD *)this + 5) + 20LL));
      v19 = xmmword_180107A60;
    }
    v20 = *((_QWORD *)this + 2);
    v21 = *((_DWORD *)this + 13);
    v38 = 0;
    *(_OWORD *)v47 = 0;
    v22 = (RTL_SRWLOCK *)(v20 + 32);
    v36 = 0;
    v39 = (RTL_SRWLOCK *)(v20 + 32);
    *(_OWORD *)v48 = 0;
    if ( (v19 & 0x20) != 0 )
      WPP_SF_qlq(1029, 88, (unsigned int)WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, v20, v21, (__int64)a3);
    *(_OWORD *)lpMem = 0;
    *(_OWORD *)v46 = 0;
    v23 = ConvertIProxyResultToProxyResult<WxHeapAllocator>((__int64)a3, v47);
    v24 = 0;
    v25 = 0;
    if ( v23 != -2147023728 )
      v25 = v23;
    v11 = v25;
    if ( v25 < 0 )
    {
      v38 = 2339;
    }
    else
    {
      AcquireSRWLockShared((PSRWLOCK)(v20 + 32));
      v36 = 1;
      if ( *(_DWORD *)(v20 + 84) )
      {
        v11 = 0;
        if ( *(_DWORD *)(v20 + 112) )
        {
          if ( (xmmword_180107A60 & 0x20) != 0 )
            WPP_SF_(1029, 89, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids);
          v21 = 0;
        }
        ProxySorter::ProcessAndSort((PSRWLOCK)(v20 + 176), v21, (struct _PROXY_RESULT *)v47);
        ReleaseSRWLockShared((PSRWLOCK)(v20 + 32));
        v36 = 0;
        v26 = *(_OWORD *)v48;
        *(_OWORD *)lpMem = *(_OWORD *)v47;
        *(_OWORD *)v47 = 0;
        *(_OWORD *)v48 = 0;
        *(_OWORD *)v46 = v26;
      }
      else
      {
        v11 = -2146685199;
        v38 = 2344;
      }
    }
    v27 = (char *)v47[1];
    if ( v48[0] )
      CloseHandle(v48[0]);
    if ( v27 )
    {
      v33 = (unsigned int)v47[0];
      if ( LODWORD(v47[0]) )
      {
        do
        {
          v34 = &v27[32 * v24];
          if ( v34 )
          {
            WxFreeHeapEx(v34 + 16);
            *(_OWORD *)v34 = 0;
            *((_OWORD *)v34 + 1) = 0;
          }
          ++v24;
        }
        while ( v24 < v33 );
      }
      if ( g_fWxHeapExtensionInitialized )
        g_WxHeapExtensionInterfaces(v27);
      else
        HeapFree(g_hWxProcessHeap, 0, v27);
      v22 = v39;
    }
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_d(1029, 90, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)v11, v35);
    if ( v36 )
      ReleaseSRWLockShared(v22);
    if ( v11 >= 0 )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 5) + 20LL) )
      {
        if ( (xmmword_180107A60 & 0x20) != 0 )
        {
          LODWORD(v35) = *(_DWORD *)(*((_QWORD *)this + 5) + 20LL);
          WPP_SF_Dd(1029, 120, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, LODWORD(v46[1]));
        }
        LODWORD(v46[1]) = *(_DWORD *)(*((_QWORD *)this + 5) + 20LL);
      }
      if ( *((_DWORD *)this + 66)
        || !*((_DWORD *)this + 65) && !v43
        || (v11 = IndicateToFirewall(
                    **((const unsigned __int16 ***)this + 4),
                    (const struct _PROXY_RESULT *)lpMem,
                    (const unsigned __int16 *)pv),
            v11 >= 0) )
      {
        if ( (*((_DWORD *)this + 65) || v43)
          && ((unsigned int)AUTOPROXY_RPC_SERVER::IsEdpEnforcementLevelActive(*((AUTOPROXY_RPC_SERVER **)this + 2))
           || hObject
           || *((_DWORD *)this + 64)) )
        {
          v11 = SetProxyDetectionHandle(
                  0,
                  *(_DWORD *)(*((_QWORD *)this + 5) + 20LL),
                  (const struct _PROXY_RESULT *)lpMem,
                  *(unsigned __int16 **)(*((_QWORD *)this + 4) + 8LL),
                  hObject,
                  &v37);
          if ( v11 < 0 )
          {
            v9 = v37;
            goto LABEL_10;
          }
          if ( hObject )
          {
            CloseHandle(hObject);
            hObject = 0;
          }
          v9 = v37;
        }
        v28 = v40;
        v29 = *(_OWORD *)v46;
        *(_OWORD *)v40 = *(_OWORD *)lpMem;
        *((_OWORD *)v28 + 1) = v29;
        *(_OWORD *)lpMem = 0;
        *v41 = v9;
        v9 = 0;
        *(_OWORD *)v46 = 0;
      }
    }
  }
LABEL_10:
  if ( hObject )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_qqD(
        1029,
        121,
        (unsigned int)WPP_641a94d440413893505b2c7b2413b0bb_Traceguids,
        (_DWORD)this,
        (__int64)hObject);
    SetEvent(hObject);
  }
  if ( v9 )
    CloseHandle(v9);
  v12 = v46[0];
  v13 = (char *)lpMem[1];
  v14 = (unsigned int)lpMem[0];
  *(_OWORD *)lpMem = 0;
  *(_OWORD *)v46 = 0;
  if ( v12 )
    CloseHandle(v12);
  if ( v13 )
  {
    for ( i = 0; i < v14; ++i )
    {
      v32 = &v13[32 * i];
      if ( v32 )
      {
        WxFreeHeapEx(v32 + 16);
        *(_OWORD *)v32 = 0;
        *((_OWORD *)v32 + 1) = 0;
      }
    }
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v13);
    else
      HeapFree(g_hWxProcessHeap, 0, v13);
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 122, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)v11, v35);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v15 = pv;
  if ( pv )
  {
    pv = 0;
    CoTaskMemFree(v15);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005770  mov     r11, rsp
0x180005773  push    rbx
0x180005774  push    rsi
0x180005775  push    rdi
0x180005776  push    r12
0x180005778  push    r13
0x18000577a  push    r14
0x18000577c  push    r15
0x18000577e  sub     rsp, 0D0h
0x180005785  mov     rax, cs:__security_cookie
0x18000578c  xor     rax, rsp
0x18000578f  mov     [rsp+108h+var_40], rax
0x180005797  xor     r12d, r12d
0x18000579a  xorps   xmm0, xmm0
0x18000579d  mov     [rsp+108h+var_C4], r12d
0x1800057a2  mov     r14d, edx
0x1800057a5  mov     rdx, [rsp+108h+arg_20]
0x1800057ad  mov     rax, r9
0x1800057b0  mov     [rsp+108h+var_A0], rdx
0x1800057b5  mov     rsi, r8
0x1800057b8  mov     [rsp+108h+var_A8], rax
0x1800057bd  mov     rdi, rcx
0x1800057c0  mov     [r11-88h], r12
0x1800057c7  mov     r13d, r12d
0x1800057ca  mov     [rsp+108h+hObject], r12
0x1800057cf  mov     [rsp+108h+var_90], r12
0x1800057d4  mov     [rsp+108h+var_C0], r12
0x1800057d9  movups  xmmword ptr [r11-80h], xmm0
0x1800057de  movups  xmmword ptr [r11-70h], xmm0
0x1800057e3  test    r9, r9
0x1800057e6  jz      short loc_1800057F9
0x1800057e8  lea     ecx, [r12+20h]
0x1800057ed  mov     [rax], r12b
0x1800057f0  inc     rax
0x1800057f3  sub     rcx, 1
0x1800057f7  jnz     short loc_1800057ED
0x1800057f9  test    rdx, rdx
0x1800057fc  jz      short loc_180005801
0x1800057fe  mov     [rdx], r12
0x180005801  test    byte ptr cs:xmmword_180107A60, 20h
0x180005808  jnz     loc_180005D54
0x18000580e  test    rsi, rsi
0x180005811  jnz     loc_180005AF8
0x180005817  mov     ebx, r14d
0x18000581a  test    r14d, r14d
0x18000581d  jns     loc_1800058FF
0x180005823  mov     [rsp+108h+var_C4], 0D5Ah
0x18000582b  mov     rax, [rsp+108h+hObject]
0x180005830  test    rax, rax
0x180005833  jnz     loc_180005EA4
0x180005839  test    r13, r13
0x18000583c  jnz     loc_180005EDF
0x180005842  mov     rcx, [rsp+108h+var_70]; hObject
0x18000584a  xorps   xmm0, xmm0
0x18000584d  mov     rsi, [rsp+108h+lpMem+8]
0x180005855  mov     r15d, dword ptr [rsp+108h+lpMem]
0x18000585d  movups  xmmword ptr [rsp+108h+lpMem], xmm0
0x180005865  movups  xmmword ptr [rsp+108h+var_70], xmm0
0x18000586d  test    rcx, rcx
0x180005870  jnz     loc_180005EED
0x180005876  test    rsi, rsi
0x180005879  jnz     loc_180005BF3
0x18000587f  test    byte ptr cs:xmmword_180107A60, 20h
0x180005886  jnz     loc_180005EF8
0x18000588c  mov     rcx, [rsp+108h+var_90]
0x180005891  test    rcx, rcx
0x180005894  jz      short loc_1800058A7
0x180005896  mov     rax, [rcx]
0x180005899  mov     rax, [rax+10h]
0x18000589d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a2  mov     [rsp+108h+var_90], r12
0x1800058a7  mov     rax, [rsp+108h+hObject]
0x1800058ac  test    rax, rax
0x1800058af  jz      short loc_1800058BF
0x1800058b1  mov     rcx, rax; hObject
0x1800058b4  call    cs:__imp_CloseHandle
0x1800058ba  mov     [rsp+108h+hObject], r12
0x1800058bf  mov     rcx, [rsp+108h+pv]; pv
0x1800058c7  test    rcx, rcx
0x1800058ca  jz      short loc_1800058DA
0x1800058cc  mov     [rsp+108h+pv], r12
0x1800058d4  call    cs:__imp_CoTaskMemFree
0x1800058da  mov     eax, ebx
0x1800058dc  mov     rcx, [rsp+108h+var_40]
0x1800058e4  xor     rcx, rsp; StackCookie
0x1800058e7  call    __security_check_cookie
0x1800058ec  add     rsp, 0D0h
0x1800058f3  pop     r15
0x1800058f5  pop     r14
0x1800058f7  pop     r13
0x1800058f9  pop     r12
0x1800058fb  pop     rdi
0x1800058fc  pop     rsi
0x1800058fd  pop     rbx
0x1800058fe  retn
0x1800058ff  test    rsi, rsi
0x180005902  jz      loc_180005D16
0x180005908  mov     rax, [rsi]
0x18000590b  lea     rdx, [rsp+108h+pv]
0x180005913  mov     rcx, rsi
0x180005916  mov     rax, [rax+48h]
0x18000591a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000591f  mov     ebx, eax
0x180005921  test    eax, eax
0x180005923  js      loc_180005D97
0x180005929  mov     al, byte ptr cs:xmmword_180107A60
0x18000592f  test    al, 20h
0x180005931  jnz     loc_180005DA4
0x180005937  mov     r14, [rdi+10h]
0x18000593b  xorps   xmm0, xmm0
0x18000593e  mov     r15d, [rdi+34h]
0x180005942  mov     [rsp+108h+var_B4], r12d
0x180005947  movups  xmmword ptr [rsp+108h+var_60], xmm0
0x18000594f  lea     r12, [r14+20h]
0x180005953  mov     [rsp+108h+var_C8], r13d
0x180005958  mov     [rsp+108h+var_B0], r12
0x18000595d  movups  xmmword ptr [rsp+108h+var_50], xmm0
0x180005965  test    al, 20h
0x180005967  jnz     loc_180005DE5
0x18000596d  xorps   xmm0, xmm0
0x180005970  lea     rdx, [rsp+108h+var_60]
0x180005978  mov     rcx, rsi
0x18000597b  movups  xmmword ptr [rsp+108h+lpMem], xmm0
0x180005983  movups  xmmword ptr [rsp+108h+var_70], xmm0
0x18000598b  call    ??$ConvertIProxyResultToProxyResult@VWxHeapAllocator@@@@YAJPEAUIProxyResult@@PEAU_PROXY_RESULT@@@Z; ConvertIProxyResultToProxyResult<WxHeapAllocator>(IProxyResult *,_PROXY_RESULT *)
0x180005990  xor     esi, esi
0x180005992  mov     ebx, 80070490h
0x180005997  cmp     eax, ebx
0x180005999  mov     ecx, esi
0x18000599b  cmovnz  ecx, eax
0x18000599e  mov     ebx, ecx
0x1800059a0  test    ecx, ecx
0x1800059a2  js      loc_180005C9A
0x1800059a8  mov     rcx, r12; SRWLock
0x1800059ab  call    cs:__imp_AcquireSRWLockShared
0x1800059b1  mov     [rsp+108h+var_C8], 1
0x1800059b9  cmp     [r14+54h], esi
0x1800059bd  jz      loc_180005D42
0x1800059c3  mov     ebx, esi
0x1800059c5  cmp     [r14+70h], esi
0x1800059c9  jnz     loc_180005E0D
0x1800059cf  lea     rcx, [r14+0B0h]; SRWLock
0x1800059d6  mov     edx, r15d; int
0x1800059d9  lea     r8, [rsp+108h+var_60]; struct _PROXY_RESULT *
0x1800059e1  call    ?ProcessAndSort@ProxySorter@@QEAAXHPEAU_PROXY_RESULT@@@Z; ProxySorter::ProcessAndSort(int,_PROXY_RESULT *)
0x1800059e6  mov     rcx, r12; SRWLock
0x1800059e9  call    cs:__imp_ReleaseSRWLockShared
0x1800059ef  movups  xmm0, xmmword ptr [rsp+108h+var_60]
0x1800059f7  mov     [rsp+108h+var_C8], esi
0x1800059fb  movups  xmm1, xmmword ptr [rsp+108h+var_50]
0x180005a03  movups  xmmword ptr [rsp+108h+lpMem], xmm0
0x180005a0b  xorps   xmm0, xmm0
0x180005a0e  movups  xmmword ptr [rsp+108h+var_60], xmm0
0x180005a16  movups  xmmword ptr [rsp+108h+var_50], xmm0
0x180005a1e  movups  xmmword ptr [rsp+108h+var_70], xmm1
0x180005a26  mov     rcx, [rsp+108h+var_50]; hObject
0x180005a2e  mov     r15, [rsp+108h+var_60+8]
0x180005a36  test    rcx, rcx
0x180005a39  jnz     loc_180005E34
0x180005a3f  test    r15, r15
0x180005a42  jnz     loc_180005CA7
0x180005a48  test    byte ptr cs:xmmword_180107A60, 20h
0x180005a4f  jnz     loc_180005E3F
0x180005a55  cmp     [rsp+108h+var_C8], esi
0x180005a59  jz      short loc_180005A64
0x180005a5b  mov     rcx, r12; SRWLock
0x180005a5e  call    cs:__imp_ReleaseSRWLockShared
0x180005a64  xor     r12d, r12d
0x180005a67  test    ebx, ebx
0x180005a69  js      loc_180005E5D
0x180005a6f  mov     rax, [rdi+28h]
0x180005a73  mov     r8d, [rax+14h]
0x180005a77  test    r8d, r8d
0x180005a7a  jnz     loc_180005C7A
0x180005a80  cmp     [rdi+108h], r12d
0x180005a87  jnz     short loc_180005AA1
0x180005a89  cmp     [rdi+104h], r12d
0x180005a90  jnz     loc_180005C47
0x180005a96  cmp     [rsp+108h+var_90], r12
0x180005a9b  jnz     loc_180005C47
0x180005aa1  cmp     [rdi+104h], r12d
0x180005aa8  jnz     loc_180005B47
0x180005aae  cmp     [rsp+108h+var_90], r12
0x180005ab3  jnz     loc_180005B47
0x180005ab9  mov     rax, [rsp+108h+var_A8]
0x180005abe  movups  xmm0, xmmword ptr [rsp+108h+lpMem]
0x180005ac6  movups  xmm1, xmmword ptr [rsp+108h+var_70]
0x180005ace  movups  xmmword ptr [rax], xmm0
0x180005ad1  movups  xmmword ptr [rax+10h], xmm1
0x180005ad5  mov     rax, [rsp+108h+var_A0]
0x180005ada  xorps   xmm0, xmm0
0x180005add  movups  xmmword ptr [rsp+108h+lpMem], xmm0
0x180005ae5  mov     [rax], r13
0x180005ae8  mov     r13, r12
0x180005aeb  movups  xmmword ptr [rsp+108h+var_70], xmm0
0x180005af3  jmp     loc_18000582B
0x180005af8  mov     rax, [rsi]
0x180005afb  lea     r8, [rsp+108h+var_90]
0x180005b00  lea     rdx, IID_ICmProxyResult
0x180005b07  mov     rcx, rsi
0x180005b0a  mov     rax, [rax]
0x180005b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b12  mov     ebx, eax
0x180005b14  test    eax, eax
0x180005b16  jns     loc_180005BC6
0x180005b1c  mov     eax, ebx
0x180005b1e  mov     ebx, r12d
0x180005b21  cmp     eax, 80004002h
0x180005b26  cmovnz  ebx, eax
0x180005b29  test    r14d, r14d
0x180005b2c  js      loc_180005817
0x180005b32  test    ebx, ebx
0x180005b34  jns     loc_180005908
0x180005b3a  mov     [rsp+108h+var_C4], 0D56h
0x180005b42  jmp     loc_18000582B
0x180005b47  mov     rcx, [rdi+10h]; this
0x180005b4b  call    ?IsEdpEnforcementLevelActive@AUTOPROXY_RPC_SERVER@@QEAAHXZ; AUTOPROXY_RPC_SERVER::IsEdpEnforcementLevelActive(void)
0x180005b50  test    eax, eax
0x180005b52  jnz     short loc_180005B68
0x180005b54  cmp     [rsp+108h+hObject], r12
0x180005b59  jnz     short loc_180005B68
0x180005b5b  cmp     [rdi+100h], r12d
0x180005b62  jz      loc_180005AB9
0x180005b68  mov     r9, [rdi+20h]
0x180005b6c  lea     rax, [rsp+108h+var_C0]
0x180005b71  mov     rdx, [rdi+28h]
0x180005b75  lea     r8, [rsp+108h+lpMem]; struct _PROXY_RESULT *
0x180005b7d  mov     [rsp+108h+var_E0], rax; void **
0x180005b82  xor     ecx, ecx; unsigned __int64
0x180005b84  mov     rax, [rsp+108h+hObject]
0x180005b89  mov     r9, [r9+8]; unsigned __int16 *
0x180005b8d  mov     edx, [rdx+14h]; unsigned int
0x180005b90  mov     [rsp+108h+var_E8], rax; void *
0x180005b95  call    ?SetProxyDetectionHandle@@YAJ_KKPEBU_PROXY_RESULT@@PEAGPEAXPEAPEAX@Z; SetProxyDetectionHandle(unsigned __int64,ulong,_PROXY_RESULT const *,ushort *,void *,void * *)
0x180005b9a  mov     ebx, eax
0x180005b9c  test    eax, eax
0x180005b9e  js      loc_180005E92
0x180005ba4  mov     rax, [rsp+108h+hObject]
0x180005ba9  test    rax, rax
0x180005bac  jz      short loc_180005BBC
0x180005bae  mov     rcx, rax; hObject
0x180005bb1  call    cs:__imp_CloseHandle
0x180005bb7  mov     [rsp+108h+hObject], r12
0x180005bbc  mov     r13, [rsp+108h+var_C0]
0x180005bc1  jmp     loc_180005AB9
0x180005bc6  mov     rcx, [rsp+108h+var_90]
0x180005bcb  lea     rdx, [rsp+108h+hObject]
0x180005bd0  mov     rax, [rcx]
0x180005bd3  mov     rax, [rax+78h]
0x180005bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bdc  mov     ebx, eax
0x180005bde  test    eax, eax
0x180005be0  jns     loc_180005B1C
0x180005be6  mov     [rsp+108h+var_C4], 0D49h
0x180005bee  jmp     loc_18000582B
0x180005bf3  mov     edi, r12d
0x180005bf6  test    r15d, r15d
0x180005bf9  jz      short loc_180005C23
0x180005bfb  mov     r14d, edi
0x180005bfe  shl     r14, 5
0x180005c02  add     r14, rsi
0x180005c05  jz      short loc_180005C1C
0x180005c07  lea     rcx, [r14+10h]
0x180005c0b  call    WxFreeHeapEx
0x180005c10  xorps   xmm0, xmm0
0x180005c13  movups  xmmword ptr [r14], xmm0
0x180005c17  movups  xmmword ptr [r14+10h], xmm0
0x180005c1c  inc     edi
0x180005c1e  cmp     edi, r15d
0x180005c21  jb      short loc_180005BFB
0x180005c23  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r12d; int g_fWxHeapExtensionInitialized
0x180005c2a  jnz     loc_180005D02
0x180005c30  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180005c37  mov     r8, rsi; lpMem
0x180005c3a  xor     edx, edx; dwFlags
0x180005c3c  call    cs:__imp_HeapFree
0x180005c42  jmp     loc_18000587F
0x180005c47  mov     rcx, [rdi+20h]
0x180005c4b  lea     rdx, [rsp+108h+lpMem]; struct _PROXY_RESULT *
0x180005c53  mov     r8, [rsp+108h+pv]; unsigned __int16 *
0x180005c5b  mov     rcx, [rcx]; unsigned __int16 *
0x180005c5e  call    ?IndicateToFirewall@@YAJPEBGPEBU_PROXY_RESULT@@0@Z; IndicateToFirewall(ushort const *,_PROXY_RESULT const *,ushort const *)
0x180005c63  mov     ebx, eax
0x180005c65  test    eax, eax
0x180005c67  jns     loc_180005AA1
0x180005c6d  mov     [rsp+108h+var_C4], 0D96h
0x180005c75  jmp     loc_18000582B
0x180005c7a  test    byte ptr cs:xmmword_180107A60, 20h
0x180005c81  jnz     loc_180005E6A
0x180005c87  mov     rax, [rdi+28h]
0x180005c8b  mov     ecx, [rax+14h]
0x180005c8e  mov     dword ptr [rsp+108h+var_70+8], ecx
0x180005c95  jmp     loc_180005A80
0x180005c9a  mov     [rsp+108h+var_B4], 923h
0x180005ca2  jmp     loc_180005A26
0x180005ca7  mov     r12d, dword ptr [rsp+108h+var_60]
0x180005caf  test    r12d, r12d
0x180005cb2  jz      short loc_180005CDC
0x180005cb4  mov     r14d, esi
0x180005cb7  shl     r14, 5
  ... truncated ...
```
