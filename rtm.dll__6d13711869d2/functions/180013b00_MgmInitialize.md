# MgmInitialize

- ea: `0x180013b00`
- end: `0x1800141f6`
- name: `MgmInitialize`
- size: `1782`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180003fb0`
- `0x18000aef0`
- `0x180012100`
- `0x180013b00`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `ntdll!RtlCreateTimerQueue` at `0x180013f97`
- `ntdll!RtlCreateTimerQueue` at `0x180013f97`
- `KERNEL32!HeapAlloc` at `0x180013d0c`
- `KERNEL32!HeapAlloc` at `0x180013e5f`
- `KERNEL32!HeapAlloc` at `0x180013f3b`
- `KERNEL32!HeapAlloc` at `0x180013d0c`
- `KERNEL32!HeapAlloc` at `0x180013e5f`
- `KERNEL32!HeapAlloc` at `0x180013f3b`
- `KERNEL32!EnterCriticalSection` at `0x180013b53`
- `KERNEL32!EnterCriticalSection` at `0x180013b53`
- `KERNEL32!LeaveCriticalSection` at `0x180013bbc`
- `KERNEL32!LeaveCriticalSection` at `0x18001417d`
- `KERNEL32!LeaveCriticalSection` at `0x180013bbc`
- `KERNEL32!LeaveCriticalSection` at `0x18001417d`
- `KERNEL32!GetLastError` at `0x180013fd5`
- `KERNEL32!GetLastError` at `0x180013fd5`
- `KERNEL32!CreateSemaphoreA` at `0x180013fc3`
- `KERNEL32!CreateSemaphoreA` at `0x180013fc3`
- `rtutils!RouterLogEventA` at `0x180013baf`
- `rtutils!RouterLogEventA` at `0x180013d91`
- `rtutils!RouterLogEventA` at `0x180013baf`
- `rtutils!RouterLogEventA` at `0x180013d91`
- `rtutils!RouterLogRegisterA` at `0x180013bd3`
- `rtutils!RouterLogRegisterA` at `0x180013bd3`

## string_xrefs

- `0x180013b75`: `MgmInitialize : MGM already running`
- `0x180013fef`: `MgmInitialize : Failed to create activity count semaphore : %x`

## pseudocode

```c
__int64 __fastcall MgmInitialize(__int64 a1, _QWORD *a2)
{
  __int64 v5; // r8
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  void *v9; // rax
  DWORD dwErrorCode; // ebx
  unsigned int i; // r8d
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  void *v14; // rax
  const wchar_t *v15; // rdx
  unsigned int j; // r8d
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  unsigned __int64 v19; // rax
  void *v20; // rax
  unsigned int v21; // ebx
  DWORD LastError; // eax
  const wchar_t *v23; // rdx
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v25[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  EnterCriticalSection(&ig);
  if ( dword_18002B908 != 103 )
  {
    if ( qword_18002B8A8 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
        gMgmEtwContext,
        qword_18002B8A8,
        L"MgmInitialize : MGM already running");
    if ( (unsigned int)dword_18002BA54 >= 2 )
      RouterLogEventA(qword_18002BA58, 2u, 0xC354u, 0, 0, 0);
    LeaveCriticalSection(&ig);
    return 1003;
  }
  qword_18002BA58 = RouterLogRegisterA("IPMGM");
  if ( qword_18002B8A8 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      qword_18002B8A8,
      L"ENTERED MgmInitialize");
  qword_18002B938 = *(_QWORD *)(a1 + 16);
  qword_18002B940 = *(_QWORD *)(a1 + 24);
  qword_18002B948 = *(_QWORD *)(a1 + 32);
  qword_18002B950 = *(_QWORD *)(a1 + 40);
  v5 = *(unsigned int *)(a1 + 4);
  dword_18002B92C = *(_DWORD *)(a1 + 4);
  v6 = *(_DWORD *)(a1 + 8);
  if ( v6 + 1 < v6 )
  {
    dword_18002B930 = -1;
    goto LABEL_54;
  }
  dword_18002B930 = v6 + 1;
  v7 = *(_DWORD *)(a1 + 12);
  if ( v7 + 1 < v7 )
  {
    dword_18002B934 = -1;
LABEL_54:
    dwErrorCode = 534;
    goto LABEL_55;
  }
  dword_18002B934 = v7 + 1;
  dword_18002B958 = *(_DWORD *)(a1 + 4);
  v8 = 16;
  if ( *(_DWORD *)(a1 + 8) / 0xAu + 1 < 0x10 )
    v8 = *(_DWORD *)(a1 + 8) / 0xAu + 1;
  dword_18002B95C = v8;
  if ( *(_DWORD *)a1 <= 3u )
    dword_18002BA54 = *(_DWORD *)a1;
  dword_18002B9A0 = 0;
  qword_18002B9B0 = (__int64)&qword_18002B9A8;
  qword_18002B9A8 = (__int64)&qword_18002B9A8;
  qword_18002B9B8 = 0;
  qword_18002B9D0 = (__int64)&qword_18002B9C8;
  qword_18002B9C8 = &qword_18002B9C8;
  dword_18002B9C0 = 305419896;
  qword_18002B9D8 = 0;
  dword_18002B9E0 = 305419896;
  if ( (unsigned __int64)(32 * v5) > 0xFFFFFFFF )
    goto LABEL_54;
  v9 = HeapAlloc(hHeap, 0, (unsigned int)(32 * v5));
  qword_18002B9E8 = v9;
  if ( !v9 )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"MgmInitialize : Failed to allocate interface table : %x", 8);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v24);
    }
    goto LABEL_19;
  }
  memset_0(v9, 0, 32LL * (unsigned int)dword_18002B92C);
  for ( i = 0; i < dword_18002B92C; *(_DWORD *)((char *)qword_18002B9E8 + v12 + 24) = 305419896 )
  {
    v12 = i++;
    v12 *= 32;
    *(_QWORD *)((char *)qword_18002B9E8 + v12 + 16) = 0;
    v13 = (char *)qword_18002B9E8 + v12;
    v13[1] = v13;
    *v13 = v13;
  }
  qword_18002BA28 = (__int64)&qword_18002BA20;
  qword_18002BA20 = (__int64)&qword_18002BA20;
  qword_18002BA08 = (__int64)&qword_18002BA00;
  qword_18002BA00 = (__int64)&qword_18002BA00;
  qword_18002BA30 = 0;
  dword_18002BA38 = 305419896;
  qword_18002BA10 = 0;
  dword_18002BA18 = 305419896;
  dword_18002B9F8 = 0;
  v14 = HeapAlloc(hHeap, 0, 32LL * (unsigned int)dword_18002B930);
  qword_18002BA40 = v14;
  if ( !v14 )
  {
    if ( !qword_18002B8A8 )
      goto LABEL_19;
    v15 = L"MgmInitialize : Failed to allocate group table : %x";
    goto LABEL_26;
  }
  memset_0(v14, 0, 32LL * (unsigned int)dword_18002B930);
  for ( j = 0; j < dword_18002B930; *(_DWORD *)((char *)qword_18002BA40 + v17 + 24) = 305419896 )
  {
    v17 = j++;
    v17 *= 32;
    *(_QWORD *)((char *)qword_18002BA40 + v17 + 16) = 0;
    v18 = (char *)qword_18002BA40 + v17;
    v18[1] = v18;
    *v18 = v18;
  }
  v19 = 8LL * (unsigned int)dword_18002B95C;
  if ( v19 > 0xFFFFFFFF )
    goto LABEL_54;
  v20 = HeapAlloc(hHeap, 0, (unsigned int)v19);
  qword_18002BA48 = v20;
  if ( !v20 )
  {
    if ( !qword_18002B8A8 )
    {
LABEL_19:
      dwErrorCode = 8;
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
      goto LABEL_55;
    }
    v15 = L"MgmInitialize : Failed to allocate timer table : %x";
LABEL_26:
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, v15, 8);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v24);
    goto LABEL_19;
  }
  memset_0(v20, 0, 8LL * (unsigned int)dword_18002B95C);
  v21 = 0;
  if ( dword_18002B95C )
  {
    while ( RtlCreateTimerQueue((PHANDLE)qword_18002BA48 + v21) >= 0 )
    {
      if ( ++v21 >= dword_18002B95C )
        goto LABEL_36;
    }
    dwErrorCode = 1450;
    goto LABEL_55;
  }
LABEL_36:
  dword_18002B918 = 0;
  hSemaphore = CreateSemaphoreA(0, 0, 0x7FFFFFFF, 0);
  if ( !hSemaphore )
  {
    LastError = GetLastError();
    dwErrorCode = LastError;
    if ( qword_18002B8A8 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"MgmInitialize : Failed to create activity count semaphore : %x", LastError);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v24);
    }
    if ( dword_18002BA54 )
      RouterLogEventA(qword_18002BA58, 1u, 0xC357u, 0, 0, dwErrorCode);
    goto LABEL_55;
  }
  dwErrorCode = RtmRegisterEntity(&g_reiRtmEntity, 0, RtmChangeNotificationCallback, 1, &g_rrpRtmProfile, &g_hRtmHandle);
  if ( dwErrorCode )
  {
    if ( !qword_18002B8A8 )
      goto LABEL_46;
    v23 = L"MgmInitialize : Failed to register with Rtm : %x";
    goto LABEL_45;
  }
  dwErrorCode = RtmRegisterForChangeNotification(g_hRtmHandle, 2u, 0x10002u, 0, &g_hNotificationHandle);
  if ( dwErrorCode )
  {
    if ( !qword_18002B8A8 )
    {
LABEL_46:
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC366u, 0, 0, dwErrorCode);
      goto LABEL_55;
    }
    v23 = L"MgmInitialize : Failed to register with Rtm for changenotification : %x";
LABEL_45:
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, v23, dwErrorCode);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v24);
    goto LABEL_46;
  }
  *a2 = DeleteFromForwarder;
  a2[1] = MgmNewPacketReceived;
  a2[2] = WrongIfFromForwarder;
  a2[3] = MgmBlockGroups;
  a2[4] = MgmUnBlockGroups;
  dword_18002B908 = 101;
LABEL_55:
  LeaveCriticalSection(&ig);
  if ( qword_18002B8A8 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"LEAVING MgmInitialize : %x\n", dwErrorCode);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v24);
  }
  if ( dwErrorCode )
    MgmDeInitialize();
  return dwErrorCode;
}

```

## disassembly

```asm
0x180013b00  mov     [rsp-8+arg_10], rbx
0x180013b05  push    rbp
0x180013b06  push    rsi
0x180013b07  push    rdi
0x180013b08  push    r14
0x180013b0a  push    r15
0x180013b0c  lea     rbp, [rsp-740h]
0x180013b14  sub     rsp, 840h
0x180013b1b  mov     rax, cs:__security_cookie
0x180013b22  xor     rax, rsp
0x180013b25  mov     [rbp+760h+var_30], rax
0x180013b2c  mov     rsi, rdx
0x180013b2f  mov     rbx, rcx
0x180013b32  xor     r14d, r14d
0x180013b35  lea     rcx, [rsp+860h+var_82C]; void *
0x180013b3a  xor     edx, edx; Val
0x180013b3c  mov     [rsp+860h+var_830], r14d
0x180013b41  mov     r8d, 7FCh; Size
0x180013b47  call    memset_0
0x180013b4c  lea     rcx, ig; lpCriticalSection
0x180013b53  call    cs:__imp_EnterCriticalSection
0x180013b59  cmp     cs:dword_18002B908, 67h ; 'g'
0x180013b60  jz      short loc_180013BCC
0x180013b62  mov     rdx, cs:qword_18002B8A8
0x180013b69  test    rdx, rdx
0x180013b6c  jz      short loc_180013B88
0x180013b6e  mov     rcx, cs:gMgmEtwContext
0x180013b75  lea     r8, aMgminitializeM; "MgmInitialize : MGM already running"
0x180013b7c  mov     rax, cs:gMgmTemplateFunc
0x180013b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b88  cmp     cs:dword_18002BA54, 2
0x180013b8f  jb      short loc_180013BB5
0x180013b91  mov     rcx, cs:qword_18002BA58; hLogHandle
0x180013b98  xor     r9d, r9d; dwSubStringCount
0x180013b9b  mov     [rsp+860h+dwErrorCode], r14d; dwErrorCode
0x180013ba0  mov     r8d, 0C354h; dwMessageId
0x180013ba6  mov     [rsp+860h+plpszSubStringArray], r14; plpszSubStringArray
0x180013bab  lea     edx, [r9+2]; dwEventType
0x180013baf  call    cs:__imp_RouterLogEventA
0x180013bb5  lea     rcx, ig; lpCriticalSection
0x180013bbc  call    cs:__imp_LeaveCriticalSection
0x180013bc2  mov     eax, 3EBh
0x180013bc7  jmp     loc_1800141D0
0x180013bcc  lea     rcx, aIpmgm; "IPMGM"
0x180013bd3  call    cs:__imp_RouterLogRegisterA
0x180013bd9  mov     rdx, cs:qword_18002B8A8
0x180013be0  mov     cs:qword_18002BA58, rax
0x180013be7  test    rdx, rdx
0x180013bea  jz      short loc_180013C06
0x180013bec  mov     rcx, cs:gMgmEtwContext
0x180013bf3  lea     r8, aEnteredMgminit; "ENTERED MgmInitialize"
0x180013bfa  mov     rax, cs:gMgmTemplateFunc
0x180013c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c06  mov     rax, [rbx+10h]
0x180013c0a  mov     cs:qword_18002B938, rax
0x180013c11  mov     rax, [rbx+18h]
0x180013c15  mov     cs:qword_18002B940, rax
0x180013c1c  mov     rax, [rbx+20h]
0x180013c20  mov     cs:qword_18002B948, rax
0x180013c27  mov     rax, [rbx+28h]
0x180013c2b  mov     cs:qword_18002B950, rax
0x180013c32  mov     r8d, [rbx+4]
0x180013c36  mov     cs:dword_18002B92C, r8d
0x180013c3d  mov     eax, [rbx+8]
0x180013c40  lea     ecx, [rax+1]
0x180013c43  cmp     ecx, eax
0x180013c45  jb      loc_180014166
0x180013c4b  mov     cs:dword_18002B930, ecx
0x180013c51  mov     eax, [rbx+0Ch]
0x180013c54  lea     ecx, [rax+1]
0x180013c57  cmp     ecx, eax
0x180013c59  jb      loc_180014159
0x180013c5f  mov     cs:dword_18002B934, ecx
0x180013c65  mov     eax, [rbx+4]
0x180013c68  mov     cs:dword_18002B958, eax
0x180013c6e  mov     eax, 0CCCCCCCDh
0x180013c73  mul     dword ptr [rbx+8]
0x180013c76  mov     eax, 10h
0x180013c7b  shr     edx, 3
0x180013c7e  inc     edx
0x180013c80  cmp     edx, eax
0x180013c82  cmovb   eax, edx
0x180013c85  mov     cs:dword_18002B95C, eax
0x180013c8b  mov     eax, [rbx]
0x180013c8d  cmp     eax, 3
0x180013c90  ja      short loc_180013C98
0x180013c92  mov     cs:dword_18002BA54, eax
0x180013c98  lea     rax, qword_18002B9A8
0x180013c9f  mov     cs:dword_18002B9A0, r14d
0x180013ca6  mov     cs:qword_18002B9B0, rax
0x180013cad  mov     r15d, 12345678h
0x180013cb3  mov     cs:qword_18002B9A8, rax
0x180013cba  mov     ebx, 0FFFFFFFFh
0x180013cbf  lea     rax, qword_18002B9C8
0x180013cc6  mov     cs:qword_18002B9B8, r14
0x180013ccd  mov     cs:qword_18002B9D0, rax
0x180013cd4  mov     cs:qword_18002B9C8, rax
0x180013cdb  mov     rax, r8
0x180013cde  shl     rax, 5
0x180013ce2  mov     cs:dword_18002B9C0, r15d
0x180013ce9  mov     cs:qword_18002B9D8, r14
0x180013cf0  mov     cs:dword_18002B9E0, r15d
0x180013cf7  cmp     rax, rbx
0x180013cfa  ja      loc_180014171
0x180013d00  mov     rcx, cs:hHeap; hHeap
0x180013d07  xor     edx, edx; dwFlags
0x180013d09  mov     r8d, eax; dwBytes
0x180013d0c  call    cs:__imp_HeapAlloc
0x180013d12  mov     cs:qword_18002B9E8, rax
0x180013d19  test    rax, rax
0x180013d1c  jnz     short loc_180013D9C
0x180013d1e  cmp     cs:qword_18002B8A8, r14
0x180013d25  lea     esi, [rax+8]
0x180013d28  jz      short loc_180013D63
0x180013d2a  mov     r8d, esi
0x180013d2d  mov     word ptr [rsp+860h+var_830], r14w
0x180013d33  lea     rdx, aMgminitializeF_2; "MgmInitialize : Failed to allocate inte"...
0x180013d3a  lea     rcx, [rsp+860h+var_830]
0x180013d3f  call    FormatRRASErrorString
0x180013d44  mov     rdx, cs:qword_18002B8A8
0x180013d4b  lea     r8, [rsp+860h+var_830]
0x180013d50  mov     rcx, cs:gMgmEtwContext
0x180013d57  mov     rax, cs:gMgmTemplateFunc
0x180013d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d63  mov     edi, 1
0x180013d68  cmp     cs:dword_18002BA54, edi
0x180013d6e  mov     ebx, esi
0x180013d70  jb      loc_180014176
0x180013d76  mov     [rsp+860h+dwErrorCode], esi; dwErrorCode
0x180013d7a  mov     r8d, 0C353h; dwMessageId
0x180013d80  mov     rcx, cs:qword_18002BA58; hLogHandle
0x180013d87  xor     r9d, r9d; dwSubStringCount
0x180013d8a  mov     edx, edi; dwEventType
0x180013d8c  mov     [rsp+860h+plpszSubStringArray], r14; plpszSubStringArray
0x180013d91  call    cs:__imp_RouterLogEventA
0x180013d97  jmp     loc_180014176
0x180013d9c  mov     r8d, cs:dword_18002B92C
0x180013da3  xor     edx, edx; Val
0x180013da5  shl     r8, 5; Size
0x180013da9  mov     rcx, rax; void *
0x180013dac  call    memset_0
0x180013db1  cmp     cs:dword_18002B92C, r14d
0x180013db8  mov     r8d, r14d
0x180013dbb  mov     edi, 1
0x180013dc0  jbe     short loc_180013DFE
0x180013dc2  mov     rax, cs:qword_18002B9E8
0x180013dc9  mov     edx, r8d
0x180013dcc  add     r8d, edi
0x180013dcf  shl     rdx, 5
0x180013dd3  mov     [rdx+rax+10h], r14
0x180013dd8  mov     rcx, cs:qword_18002B9E8
0x180013ddf  add     rcx, rdx
0x180013de2  mov     [rcx+8], rcx
0x180013de6  mov     [rcx], rcx
0x180013de9  mov     rax, cs:qword_18002B9E8
0x180013df0  mov     [rdx+rax+18h], r15d
0x180013df5  cmp     r8d, cs:dword_18002B92C
0x180013dfc  jb      short loc_180013DC2
0x180013dfe  mov     r8d, cs:dword_18002B930
0x180013e05  lea     rax, qword_18002BA20
0x180013e0c  mov     rcx, cs:hHeap; hHeap
0x180013e13  xor     edx, edx; dwFlags
0x180013e15  mov     cs:qword_18002BA28, rax
0x180013e1c  mov     cs:qword_18002BA20, rax
0x180013e23  lea     rax, qword_18002BA00
0x180013e2a  shl     r8, 5; dwBytes
0x180013e2e  mov     cs:qword_18002BA08, rax
0x180013e35  mov     cs:qword_18002BA00, rax
0x180013e3c  mov     cs:qword_18002BA30, r14
0x180013e43  mov     cs:dword_18002BA38, r15d
0x180013e4a  mov     cs:qword_18002BA10, r14
0x180013e51  mov     cs:dword_18002BA18, r15d
0x180013e58  mov     cs:dword_18002B9F8, r14d
0x180013e5f  call    cs:__imp_HeapAlloc
0x180013e65  mov     cs:qword_18002BA40, rax
0x180013e6c  test    rax, rax
0x180013e6f  jnz     short loc_180013EBF
0x180013e71  cmp     cs:qword_18002B8A8, r14
0x180013e78  lea     esi, [rax+8]
0x180013e7b  jz      loc_180013D68
0x180013e81  lea     rdx, aMgminitializeF_3; "MgmInitialize : Failed to allocate grou"...
0x180013e88  mov     r8d, esi
0x180013e8b  mov     word ptr [rsp+860h+var_830], r14w
0x180013e91  lea     rcx, [rsp+860h+var_830]
0x180013e96  call    FormatRRASErrorString
0x180013e9b  mov     rdx, cs:qword_18002B8A8
0x180013ea2  lea     r8, [rsp+860h+var_830]
0x180013ea7  mov     rcx, cs:gMgmEtwContext
0x180013eae  mov     rax, cs:gMgmTemplateFunc
0x180013eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eba  jmp     loc_180013D68
0x180013ebf  mov     r8d, cs:dword_18002B930
0x180013ec6  xor     edx, edx; Val
0x180013ec8  shl     r8, 5; Size
0x180013ecc  mov     rcx, rax; void *
0x180013ecf  call    memset_0
0x180013ed4  cmp     cs:dword_18002B930, r14d
0x180013edb  mov     r8d, r14d
0x180013ede  jbe     short loc_180013F1C
0x180013ee0  mov     rax, cs:qword_18002BA40
0x180013ee7  mov     edx, r8d
0x180013eea  add     r8d, edi
0x180013eed  shl     rdx, 5
0x180013ef1  mov     [rdx+rax+10h], r14
0x180013ef6  mov     rcx, cs:qword_18002BA40
0x180013efd  add     rcx, rdx
0x180013f00  mov     [rcx+8], rcx
0x180013f04  mov     [rcx], rcx
0x180013f07  mov     rax, cs:qword_18002BA40
0x180013f0e  mov     [rdx+rax+18h], r15d
0x180013f13  cmp     r8d, cs:dword_18002B930
0x180013f1a  jb      short loc_180013EE0
0x180013f1c  mov     eax, cs:dword_18002B95C
0x180013f22  shl     rax, 3
0x180013f26  cmp     rax, rbx
0x180013f29  ja      loc_180014171
0x180013f2f  mov     rcx, cs:hHeap; hHeap
0x180013f36  xor     edx, edx; dwFlags
0x180013f38  mov     r8d, eax; dwBytes
0x180013f3b  call    cs:__imp_HeapAlloc
0x180013f41  mov     cs:qword_18002BA48, rax
0x180013f48  test    rax, rax
0x180013f4b  jnz     short loc_180013F69
0x180013f4d  cmp     cs:qword_18002B8A8, r14
0x180013f54  lea     esi, [rax+8]
0x180013f57  jz      loc_180013D68
0x180013f5d  lea     rdx, aMgminitializeF_0; "MgmInitialize : Failed to allocate time"...
0x180013f64  jmp     loc_180013E88
0x180013f69  mov     r8d, cs:dword_18002B95C
0x180013f70  xor     edx, edx; Val
0x180013f72  shl     r8, 3; Size
0x180013f76  mov     rcx, rax; void *
0x180013f79  call    memset_0
0x180013f7e  cmp     cs:dword_18002B95C, r14d
0x180013f85  mov     ebx, r14d
0x180013f88  jbe     short loc_180013FAF
0x180013f8a  mov     rax, cs:qword_18002BA48
0x180013f91  mov     ecx, ebx
0x180013f93  lea     rcx, [rax+rcx*8]; TimerQueue
0x180013f97  call    cs:__imp_RtlCreateTimerQueue
0x180013f9d  test    eax, eax
0x180013f9f  js      loc_18001403A
0x180013fa5  add     ebx, edi
0x180013fa7  cmp     ebx, cs:dword_18002B95C
0x180013fad  jb      short loc_180013F8A
0x180013faf  xor     r9d, r9d; lpName
0x180013fb2  mov     cs:dword_18002B918, r14d
0x180013fb9  xor     edx, edx; lInitialCount
0x180013fbb  xor     ecx, ecx; lpSemaphoreAttributes
0x180013fbd  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180013fc3  call    cs:__imp_CreateSemaphoreA
0x180013fc9  mov     cs:hSemaphore, rax
0x180013fd0  test    rax, rax
0x180013fd3  jnz     short loc_180014044
0x180013fd5  call    cs:__imp_GetLastError
0x180013fdb  cmp     cs:qword_18002B8A8, r14
0x180013fe2  mov     ebx, eax
0x180013fe4  jz      short loc_18001401F
0x180013fe6  mov     r8d, eax
0x180013fe9  mov     word ptr [rsp+860h+var_830], r14w
0x180013fef  lea     rdx, aMgminitializeF_4; "MgmInitialize : Failed to create activi"...
0x180013ff6  lea     rcx, [rsp+860h+var_830]
0x180013ffb  call    FormatRRASErrorString
0x180014000  mov     rdx, cs:qword_18002B8A8
0x180014007  lea     r8, [rsp+860h+var_830]
0x18001400c  mov     rcx, cs:gMgmEtwContext
0x180014013  mov     rax, cs:gMgmTemplateFunc
0x18001401a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001401f  cmp     cs:dword_18002BA54, edi
0x180014025  jb      loc_180014176
0x18001402b  mov     [rsp+860h+dwErrorCode], ebx
0x18001402f  mov     r8d, 0C357h
0x180014035  jmp     loc_180013D80
0x18001403a  mov     ebx, 5AAh
0x18001403f  jmp     loc_180014176
0x180014044  lea     rax, g_hRtmHandle
0x18001404b  mov     r9d, edi; ReserveOpaquePointer
0x18001404e  mov     qword ptr [rsp+860h+dwErrorCode], rax; RtmRegHandle
0x180014053  lea     r8, RtmChangeNotificationCallback; EventCallback
0x18001405a  lea     rax, g_rrpRtmProfile
0x180014061  xor     edx, edx; ExportMethods
0x180014063  lea     rcx, g_reiRtmEntity; RtmEntityInfo
0x18001406a  mov     [rsp+860h+plpszSubStringArray], rax; RtmRegProfile
0x18001406f  call    RtmRegisterEntity
0x180014074  mov     ebx, eax
0x180014076  test    eax, eax
0x180014078  jz      short loc_1800140D7
0x18001407a  cmp     cs:qword_18002B8A8, r14
0x180014081  jz      short loc_1800140BC
0x180014083  lea     rdx, aMgminitializeF; "MgmInitialize : Failed to register with"...
0x18001408a  mov     r8d, ebx
0x18001408d  mov     word ptr [rsp+860h+var_830], r14w
0x180014093  lea     rcx, [rsp+860h+var_830]
0x180014098  call    FormatRRASErrorString
0x18001409d  mov     rdx, cs:qword_18002B8A8
0x1800140a4  lea     r8, [rsp+860h+var_830]
0x1800140a9  mov     rcx, cs:gMgmEtwContext
0x1800140b0  mov     rax, cs:gMgmTemplateFunc
0x1800140b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140bc  cmp     cs:dword_18002BA54, edi
  ... truncated ...
```
