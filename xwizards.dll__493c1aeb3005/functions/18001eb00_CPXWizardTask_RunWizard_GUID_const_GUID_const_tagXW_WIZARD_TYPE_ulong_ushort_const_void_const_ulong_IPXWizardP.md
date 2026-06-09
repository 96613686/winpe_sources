# CPXWizardTask::RunWizard(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,void * const,ulong,IPXWizardPropertyBag * const)

- ea: `0x18001eb00`
- end: `0x18001efa8`
- name: `?RunWizard@CPXWizardTask@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGQEAXKQEAUIPXWizardPropertyBag@@@Z`
- size: `1192`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004370`
- `0x180008634`
- `0x18000addc`
- `0x18000ae04`
- `0x18000ae44`
- `0x18001d854`
- `0x18001e180`
- `0x18001eb00`
- `0x18001f608`
- `0x18001f65c`
- `0x1800316b8`
- `0x180032a02`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ecc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ed18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ecc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ed18`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ed5a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ed5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ee65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ee65`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001ee5d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001ee5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eed1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eed1`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x18001ee40`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x18001ee40`

## pseudocode

```c
__int64 __fastcall CPXWizardTask::RunWizard(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        int a4,
        int a5,
        unsigned __int16 *a6,
        __int64 a7,
        unsigned int a8,
        __int64 a9)
{
  _OWORD *v11; // rsi
  __int64 v13; // rax
  __int64 v15; // rax
  PVOID *v16; // rcx
  unsigned int v17; // ebp
  int v18; // r12d
  struct tag_WIZARD_TASK_DATA *v19; // rax
  struct tag_WIZARD_TASK_DATA *v20; // rdi
  unsigned __int16 *v21; // r15
  int v22; // r11d
  __int64 v23; // rax
  __int64 v24; // r12
  _WORD *v25; // rax
  DWORD v26; // ecx
  int v27; // r15d
  _DWORD *Value; // rax
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // rax
  unsigned int started; // edi
  DWORD ThreadId; // esi
  DWORD CurrentThreadId; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r8
  unsigned int LastErrorHRESULT; // eax
  HANDLE *p_Thread; // [rsp+20h] [rbp-58h]
  HANDLE Thread; // [rsp+88h] [rbp+10h] BYREF
  struct tag_WIZARD_TASK_DATA *v42; // [rsp+90h] [rbp+18h] BYREF
  int v43; // [rsp+98h] [rbp+20h]

  v11 = a2;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
  v13 = *a3 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *a3 == *(_QWORD *)&GUID_NULL.Data1 )
    v13 = a3[1] - *(_QWORD *)GUID_NULL.Data4;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, 2147500035LL);
    return 2147500035LL;
  }
  if ( g_dwTLSThreadInstanceIndex == -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, 2147942414LL);
    return 2147942414LL;
  }
  if ( !a2 )
    goto LABEL_24;
  v15 = *a2 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *a2 == *(_QWORD *)&GUID_NULL.Data1 )
    v15 = a2[1] - *(_QWORD *)GUID_NULL.Data4;
  if ( v15 )
  {
LABEL_24:
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = 0;
  }
  v17 = a8;
  if ( a8 && (a8 & 0xFFECEEC8) != 0 )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 )
      WPP_SF_DD(v16[2], 52, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, a8, -2147024809);
    return 2147942487LL;
  }
  v18 = 32;
  if ( a4 )
    v18 = a4;
  v43 = v18;
  v19 = (struct tag_WIZARD_TASK_DATA *)CoTaskMemAlloc(0x60u);
  v42 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, 2147942414LL);
    goto LABEL_70;
  }
  memset_0(v19, 0, 0x60u);
  v21 = a6;
  v22 = 0;
  if ( a6 )
  {
    v23 = -1;
    do
      ++v23;
    while ( a6[v23] );
    v24 = (unsigned int)(v23 + 1);
    v25 = CoTaskMemAlloc(2 * v24);
    *((_QWORD *)v20 + 6) = v25;
    if ( v25 )
    {
      *v25 = 0;
      StringCchCopyW(*((unsigned __int16 **)v20 + 6), (unsigned int)v24, v21);
      v18 = v43;
      goto LABEL_39;
    }
LABEL_70:
    CPXWizardTask::FreeTaskDataElement(&v42);
    return 2147942414LL;
  }
LABEL_39:
  v26 = g_dwTLSThreadInstanceIndex;
  v27 = v22;
  *((_DWORD *)v20 + 17) = v17 & 1;
  Value = TlsGetValue(v26);
  if ( Value )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v29, *(unsigned int *)a3, Value[6]);
    v27 = 1;
    *((_DWORD *)v20 + 17) = 1;
  }
  *(_QWORD *)v20 = a1[8];
  if ( v11 )
    *(_OWORD *)((char *)v20 + 8) = *v11;
  v30 = a5;
  v31 = a9;
  *(_OWORD *)((char *)v20 + 24) = *(_OWORD *)a3;
  *((_DWORD *)v20 + 10) = v18;
  *((_DWORD *)v20 + 11) = v30;
  v32 = a7;
  *((_DWORD *)v20 + 16) = v17;
  *((_QWORD *)v20 + 7) = v32;
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
  *((_QWORD *)v20 + 10) = v31;
  *((_QWORD *)v20 + 9) = a1;
  (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  *((_QWORD *)v20 + 11) = a1[13];
  if ( *((_DWORD *)v20 + 17) )
  {
    Thread = 0;
    p_Thread = &Thread;
    if ( SHCreateThreadWithHandle((WCHAR)CPXWizardTask::HrStartNewWizardThread) )
    {
      started = 0;
      if ( v27 )
      {
        ThreadId = GetThreadId(Thread);
        CurrentThreadId = GetCurrentThreadId();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          LODWORD(p_Thread) = CurrentThreadId;
          WPP_SF_LLLL(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, v37, CurrentThreadId, p_Thread, ThreadId, ThreadId);
        }
        WindowWaitForThreadToTerminate(&Thread);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, v38, ThreadId, ThreadId);
      }
      CloseHandle(Thread);
    }
    else
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      started = LastErrorHRESULT;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
          LastErrorHRESULT);
      CPXWizardTask::FreeTaskDataElement(&v42);
    }
  }
  else
  {
    started = CPXWizardTask::HrStartNewWizardThread(v20);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, started);
  return started;
}

```

## disassembly

```asm
0x18001eb00  mov     [rsp+arg_0], rbx
0x18001eb05  push    rbp
0x18001eb06  push    rsi
0x18001eb07  push    rdi
0x18001eb08  push    r12
0x18001eb0a  push    r13
0x18001eb0c  push    r14
0x18001eb0e  push    r15
0x18001eb10  sub     rsp, 40h
0x18001eb14  xor     r15d, r15d
0x18001eb17  mov     edi, r9d
0x18001eb1a  mov     r14, r8
0x18001eb1d  mov     rsi, rdx
0x18001eb20  mov     r13, rcx
0x18001eb23  test    r8, r8
0x18001eb26  jnz     short loc_18001EB68
0x18001eb28  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb2f  lea     rbx, WPP_GLOBAL_Control
0x18001eb36  cmp     rcx, rbx
0x18001eb39  jz      loc_18001ECA6
0x18001eb3f  test    byte ptr [rcx+1Ch], 8
0x18001eb43  jz      loc_18001ECA6
0x18001eb49  mov     rcx, [rcx+10h]
0x18001eb4d  lea     edx, [r8+30h]
0x18001eb51  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001eb58  mov     r9d, 80070057h
0x18001eb5e  call    WPP_SF_d
0x18001eb63  jmp     loc_18001ECA6
0x18001eb68  mov     rax, [r8]
0x18001eb6b  mov     rdx, qword ptr cs:GUID_NULL.Data1
0x18001eb72  mov     rcx, qword ptr cs:GUID_NULL.Data4
0x18001eb79  sub     rax, rdx
0x18001eb7c  jnz     short loc_18001EB85
0x18001eb7e  mov     rax, [r8+8]
0x18001eb82  sub     rax, rcx
0x18001eb85  test    rax, rax
0x18001eb88  jnz     short loc_18001EBC6
0x18001eb8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb91  lea     rbx, WPP_GLOBAL_Control
0x18001eb98  cmp     rcx, rbx
0x18001eb9b  jz      short loc_18001EBBC
0x18001eb9d  test    byte ptr [rcx+1Ch], 8
0x18001eba1  jz      short loc_18001EBBC
0x18001eba3  mov     rcx, [rcx+10h]
0x18001eba7  lea     edx, [rax+31h]
0x18001ebaa  mov     r9d, 80004003h
0x18001ebb0  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001ebb7  call    WPP_SF_d
0x18001ebbc  mov     eax, 80004003h
0x18001ebc1  jmp     loc_18001EF90
0x18001ebc6  cmp     cs:?g_dwTLSThreadInstanceIndex@@3KA, 0FFFFFFFFh; ulong g_dwTLSThreadInstanceIndex
0x18001ebcd  jnz     short loc_18001EC10
0x18001ebcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebd6  lea     rbx, WPP_GLOBAL_Control
0x18001ebdd  cmp     rcx, rbx
0x18001ebe0  jz      loc_18001EF8B
0x18001ebe6  test    byte ptr [rcx+1Ch], 8
0x18001ebea  jz      loc_18001EF8B
0x18001ebf0  mov     rcx, [rcx+10h]
0x18001ebf4  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001ebfb  mov     edx, 32h ; '2'
0x18001ec00  mov     r9d, 8007000Eh
0x18001ec06  call    WPP_SF_d
0x18001ec0b  jmp     loc_18001EF8B
0x18001ec10  lea     rbx, WPP_GLOBAL_Control
0x18001ec17  test    rsi, rsi
0x18001ec1a  jz      short loc_18001EC61
0x18001ec1c  mov     rax, [rsi]
0x18001ec1f  sub     rax, rdx
0x18001ec22  jnz     short loc_18001EC2B
0x18001ec24  mov     rax, [rsi+8]
0x18001ec28  sub     rax, rcx
0x18001ec2b  test    rax, rax
0x18001ec2e  jnz     short loc_18001EC61
0x18001ec30  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec37  cmp     rcx, rbx
0x18001ec3a  jz      short loc_18001EC5C
0x18001ec3c  test    byte ptr [rcx+1Ch], 10h
0x18001ec40  jz      short loc_18001EC5C
0x18001ec42  mov     rcx, [rcx+10h]
0x18001ec46  lea     edx, [rax+33h]
0x18001ec49  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001ec50  call    WPP_SF_
0x18001ec55  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec5c  mov     rsi, r15
0x18001ec5f  jmp     short loc_18001EC68
0x18001ec61  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec68  mov     ebp, [rsp+78h+arg_38]
0x18001ec6f  test    ebp, ebp
0x18001ec71  jz      short loc_18001ECB0
0x18001ec73  test    ebp, 0FFECEEC8h
0x18001ec79  jz      short loc_18001ECB0
0x18001ec7b  cmp     rcx, rbx
0x18001ec7e  jz      short loc_18001ECA6
0x18001ec80  test    byte ptr [rcx+1Ch], 8
0x18001ec84  jz      short loc_18001ECA6
0x18001ec86  mov     rcx, [rcx+10h]
0x18001ec8a  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001ec91  mov     edx, 34h ; '4'
0x18001ec96  mov     dword ptr [rsp+78h+var_58], 80070057h
0x18001ec9e  mov     r9d, ebp
0x18001eca1  call    WPP_SF_DD
0x18001eca6  mov     eax, 80070057h
0x18001ecab  jmp     loc_18001EF90
0x18001ecb0  test    edi, edi
0x18001ecb2  mov     r12d, 20h ; ' '
0x18001ecb8  mov     ecx, 60h ; '`'; cb
0x18001ecbd  cmovnz  r12d, edi
0x18001ecc1  mov     [rsp+78h+arg_18], r12d
0x18001ecc9  call    cs:__imp_CoTaskMemAlloc
0x18001eccf  mov     [rsp+78h+arg_10], rax
0x18001ecd7  mov     rdi, rax
0x18001ecda  test    rax, rax
0x18001ecdd  jz      loc_18001EF51
0x18001ece3  xor     edx, edx; Val
0x18001ece5  mov     rcx, rax; void *
0x18001ece8  lea     r8d, [rdx+60h]; Size
0x18001ecec  call    memset_0
0x18001ecf1  mov     r15, [rsp+78h+arg_28]
0x18001ecf9  xor     r11d, r11d
0x18001ecfc  test    r15, r15
0x18001ecff  jz      short loc_18001ED49
0x18001ed01  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ed05  inc     rax
0x18001ed08  cmp     [r15+rax*2], r11w
0x18001ed0d  jnz     short loc_18001ED05
0x18001ed0f  inc     eax
0x18001ed11  mov     r12d, eax
0x18001ed14  lea     rcx, [rax+rax]; cb
0x18001ed18  call    cs:__imp_CoTaskMemAlloc
0x18001ed1e  xor     r11d, r11d
0x18001ed21  mov     [rdi+30h], rax
0x18001ed25  test    rax, rax
0x18001ed28  jz      loc_18001EF7E
0x18001ed2e  mov     [rax], r11w
0x18001ed32  mov     r8, r15; unsigned __int16 *
0x18001ed35  mov     rcx, [rdi+30h]; unsigned __int16 *
0x18001ed39  mov     edx, r12d; unsigned __int64
0x18001ed3c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ed41  mov     r12d, [rsp+78h+arg_18]
0x18001ed49  mov     ecx, cs:?g_dwTLSThreadInstanceIndex@@3KA; dwTlsIndex
0x18001ed4f  mov     eax, ebp
0x18001ed51  and     eax, 1
0x18001ed54  mov     r15d, r11d
0x18001ed57  mov     [rdi+44h], eax
0x18001ed5a  call    cs:__imp_TlsGetValue
0x18001ed60  test    rax, rax
0x18001ed63  jz      short loc_18001ED99
0x18001ed65  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed6c  cmp     rcx, rbx
0x18001ed6f  jz      short loc_18001ED8F
0x18001ed71  test    byte ptr [rcx+1Ch], 8
0x18001ed75  jz      short loc_18001ED8F
0x18001ed77  mov     eax, [rax+18h]
0x18001ed7a  mov     edx, 36h ; '6'
0x18001ed7f  mov     r9d, [r14]
0x18001ed82  mov     rcx, [rcx+10h]
0x18001ed86  mov     dword ptr [rsp+78h+var_58], eax
0x18001ed8a  call    WPP_SF_LL
0x18001ed8f  mov     r15d, 1
0x18001ed95  mov     [rdi+44h], r15d
0x18001ed99  mov     rax, [r13+40h]
0x18001ed9d  mov     [rdi], rax
0x18001eda0  test    rsi, rsi
0x18001eda3  jz      short loc_18001EDAD
0x18001eda5  movups  xmm0, xmmword ptr [rsi]
0x18001eda8  movdqu  xmmword ptr [rdi+8], xmm0
0x18001edad  movups  xmm0, xmmword ptr [r14]
0x18001edb1  mov     eax, [rsp+78h+arg_20]
0x18001edb8  mov     rsi, [rsp+78h+arg_40]
0x18001edc0  movdqu  xmmword ptr [rdi+18h], xmm0
0x18001edc5  mov     [rdi+28h], r12d
0x18001edc9  mov     [rdi+2Ch], eax
0x18001edcc  mov     rax, [rsp+78h+arg_30]
0x18001edd4  mov     [rdi+40h], ebp
0x18001edd7  xor     ebp, ebp
0x18001edd9  mov     [rdi+38h], rax
0x18001eddd  test    rsi, rsi
0x18001ede0  jz      short loc_18001EDF1
0x18001ede2  mov     rax, [rsi]
0x18001ede5  mov     rcx, rsi
0x18001ede8  mov     rax, [rax+8]
0x18001edec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edf1  mov     [rdi+50h], rsi
0x18001edf5  mov     rcx, r13
0x18001edf8  mov     [rdi+48h], r13
0x18001edfc  mov     rax, [r13+0]
0x18001ee00  mov     rax, [rax+8]
0x18001ee04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee09  mov     rax, [r13+68h]
0x18001ee0d  mov     [rdi+58h], rax
0x18001ee11  cmp     [rdi+44h], ebp
0x18001ee14  jz      loc_18001EF19
0x18001ee1a  xor     r9d, r9d
0x18001ee1d  mov     [rsp+78h+Thread], rbp
0x18001ee25  lea     rax, [rsp+78h+Thread]
0x18001ee2d  mov     rdx, rdi
0x18001ee30  lea     rcx, ?HrStartNewWizardThread@CPXWizardTask@@CAKPEAX@Z; ch
0x18001ee37  mov     [rsp+78h+var_58], rax
0x18001ee3c  lea     r8d, [r9+4]
0x18001ee40  call    cs:__imp_SHCreateThreadWithHandle
0x18001ee46  test    eax, eax
0x18001ee48  jz      loc_18001EED9
0x18001ee4e  mov     edi, ebp
0x18001ee50  test    r15d, r15d
0x18001ee53  jz      short loc_18001EEC9
0x18001ee55  mov     rcx, [rsp+78h+Thread]; Thread
0x18001ee5d  call    cs:__imp_GetThreadId
0x18001ee63  mov     esi, eax
0x18001ee65  call    cs:__imp_GetCurrentThreadId
0x18001ee6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee72  cmp     rcx, rbx
0x18001ee75  jz      short loc_18001EE95
0x18001ee77  test    byte ptr [rcx+1Ch], 8
0x18001ee7b  jz      short loc_18001EE95
0x18001ee7d  mov     rcx, [rcx+10h]
0x18001ee81  mov     r9d, eax
0x18001ee84  mov     [rsp+78h+var_48], esi
0x18001ee88  mov     [rsp+78h+var_50], esi
0x18001ee8c  mov     dword ptr [rsp+78h+var_58], eax
0x18001ee90  call    WPP_SF_LLLL
0x18001ee95  lea     rcx, [rsp+78h+Thread]; pHandles
0x18001ee9d  call    ?WindowWaitForThreadToTerminate@@YAXPEAPEAX@Z; WindowWaitForThreadToTerminate(void * *)
0x18001eea2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eea9  cmp     rcx, rbx
0x18001eeac  jz      short loc_18001EEC9
0x18001eeae  test    byte ptr [rcx+1Ch], 8
0x18001eeb2  jz      short loc_18001EEC9
0x18001eeb4  mov     rcx, [rcx+10h]
0x18001eeb8  mov     edx, 38h ; '8'
0x18001eebd  mov     r9d, esi
0x18001eec0  mov     dword ptr [rsp+78h+var_58], esi
0x18001eec4  call    WPP_SF_LL
0x18001eec9  mov     rcx, [rsp+78h+Thread]; hObject
0x18001eed1  call    cs:__imp_CloseHandle
0x18001eed7  jmp     short loc_18001EF23
0x18001eed9  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001eede  mov     edi, eax
0x18001eee0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eee7  cmp     rcx, rbx
0x18001eeea  jz      short loc_18001EF0A
0x18001eeec  test    byte ptr [rcx+1Ch], 4
0x18001eef0  jz      short loc_18001EF0A
0x18001eef2  mov     rcx, [rcx+10h]
0x18001eef6  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001eefd  mov     edx, 39h ; '9'
0x18001ef02  mov     r9d, eax
0x18001ef05  call    WPP_SF_d
0x18001ef0a  lea     rcx, [rsp+78h+arg_10]; struct tag_WIZARD_TASK_DATA **
0x18001ef12  call    ?FreeTaskDataElement@CPXWizardTask@@CAXPEAPEAUtag_WIZARD_TASK_DATA@@@Z; CPXWizardTask::FreeTaskDataElement(tag_WIZARD_TASK_DATA * *)
0x18001ef17  jmp     short loc_18001EF23
0x18001ef19  mov     rcx, rdi; lpTlsValue
0x18001ef1c  call    ?HrStartNewWizardThread@CPXWizardTask@@CAKPEAX@Z; CPXWizardTask::HrStartNewWizardThread(void *)
0x18001ef21  mov     edi, eax
0x18001ef23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef2a  cmp     rcx, rbx
0x18001ef2d  jz      short loc_18001EF4D
0x18001ef2f  test    byte ptr [rcx+1Ch], 10h
0x18001ef33  jz      short loc_18001EF4D
0x18001ef35  mov     rcx, [rcx+10h]
0x18001ef39  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001ef40  mov     edx, 3Ah ; ':'
0x18001ef45  mov     r9d, edi
0x18001ef48  call    WPP_SF_d
0x18001ef4d  mov     eax, edi
0x18001ef4f  jmp     short loc_18001EF90
0x18001ef51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef58  cmp     rcx, rbx
0x18001ef5b  jz      short loc_18001EF7E
0x18001ef5d  test    byte ptr [rcx+1Ch], 8
0x18001ef61  jz      short loc_18001EF7E
0x18001ef63  mov     rcx, [rcx+10h]
0x18001ef67  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001ef6e  mov     edx, 35h ; '5'
0x18001ef73  mov     r9d, 8007000Eh
0x18001ef79  call    WPP_SF_d
0x18001ef7e  lea     rcx, [rsp+78h+arg_10]; struct tag_WIZARD_TASK_DATA **
0x18001ef86  call    ?FreeTaskDataElement@CPXWizardTask@@CAXPEAPEAUtag_WIZARD_TASK_DATA@@@Z; CPXWizardTask::FreeTaskDataElement(tag_WIZARD_TASK_DATA * *)
0x18001ef8b  mov     eax, 8007000Eh
0x18001ef90  mov     rbx, [rsp+78h+arg_0]
0x18001ef98  add     rsp, 40h
0x18001ef9c  pop     r15
0x18001ef9e  pop     r14
0x18001efa0  pop     r13
0x18001efa2  pop     r12
0x18001efa4  pop     rdi
0x18001efa5  pop     rsi
0x18001efa6  pop     rbp
0x18001efa7  retn
```
