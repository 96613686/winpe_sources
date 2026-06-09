# CWbemCallSecurity::CWbemCallSecurity(CWbemCallSecurity const &)

- ea: `0x180024680`
- end: `0x180024a33`
- name: `??0CWbemCallSecurity@@AEAA@AEBV0@@Z`
- size: `947`
- prototype: `CWbemCallSecurity *__fastcall(CWbemCallSecurity *__hidden this, const struct CWbemCallSecurity *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800280c0`

## callees

- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x180024680`
- `0x18002ca74`
- `0x18002cbdc`
- `0x18002ee7c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002490d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800249c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002490d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800249c3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800247fd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800247fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800247c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800247d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800247c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800247d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800249cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800249cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800246f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002487c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800246f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002487c`

## pseudocode

```c
CWbemCallSecurity *__fastcall CWbemCallSecurity::CWbemCallSecurity(
        CWbemCallSecurity *this,
        const struct CWbemCallSecurity *a2)
{
  _WORD *v4; // r15
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdi
  unsigned __int16 *v8; // rbx
  __int64 v9; // rax
  unsigned __int64 v10; // rdi
  _WORD *v11; // rax
  _WORD *v12; // rcx
  __int64 v13; // rax
  _WORD *v14; // rdx
  _WORD *v15; // rcx
  unsigned int v16; // ebx
  HANDLE CurrentProcess; // rax
  void *v19; // rdi
  void *v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rbx
  unsigned __int16 *v24; // rax
  int v25; // eax
  unsigned int v26; // ebx
  unsigned __int16 *pExceptionObject; // [rsp+70h] [rbp+8h] BYREF
  HANDLE TargetHandle; // [rsp+78h] [rbp+10h] BYREF

  IWbemCallSecurity::IWbemCallSecurity(this);
  v4 = 0;
  *(_QWORD *)this = &CWbemCallSecurity::`vftable';
  TargetHandle = 0;
  if ( *(_QWORD *)(v5 + 16) )
  {
    CurrentProcess = GetCurrentProcess();
    v19 = (void *)*((_QWORD *)a2 + 2);
    v20 = CurrentProcess;
    v21 = GetCurrentProcess();
    if ( !DuplicateHandle(v21, v19, v20, &TargetHandle, 0, 1, 2u) )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids,
          "CX_Exception()");
      }
      throw (CX_Exception *)&pExceptionObject;
    }
  }
  v6 = *((_QWORD *)a2 + 6);
  v7 = -1;
  v8 = 0;
  pExceptionObject = 0;
  if ( v6 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v6 + 2 * v22) );
    v23 = v22 + 1;
    v24 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v22 + 1));
    pExceptionObject = v24;
    if ( !v24 )
    {
      if ( TargetHandle )
        CloseHandle(TargetHandle);
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    v25 = StringCchCopyW(v24, v23, *((const unsigned __int16 **)a2 + 6));
    v26 = v25;
    if ( v25 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v25);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids, v26);
      }
    }
    v8 = pExceptionObject;
  }
  v9 = *((_QWORD *)a2 + 7);
  if ( v9 )
  {
    do
      ++v7;
    while ( *(_WORD *)(v9 + 2 * v7) );
    v10 = v7 + 1;
    v11 = CoTaskMemAlloc(2 * v10);
    v4 = v11;
    if ( !v11 )
    {
      if ( TargetHandle )
        CloseHandle(TargetHandle);
      CoTaskMemFree(v8);
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( v10 )
    {
      if ( v10 > 0x7FFFFFFF )
      {
        v16 = -2147024809;
        *v11 = 0;
      }
      else
      {
        v12 = (_WORD *)*((_QWORD *)a2 + 7);
        v13 = 2147483646;
        v14 = v4;
        do
        {
          if ( !v13 )
            break;
          if ( !*v12 )
            break;
          *v14++ = *v12++;
          --v13;
          --v10;
        }
        while ( v10 );
        v15 = v14 - 1;
        v16 = v10 == 0 ? 0x8007007A : 0;
        if ( v10 )
          v15 = v14;
        *v15 = 0;
        if ( v10 )
          goto LABEL_15;
      }
    }
    else
    {
      v16 = -2147024809;
    }
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v16);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids, v16);
    }
  }
LABEL_15:
  *((_QWORD *)this + 2) = TargetHandle;
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
  *((_DWORD *)this + 7) = 0;
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
  *((_DWORD *)this + 9) = *((_DWORD *)a2 + 9);
  *((_DWORD *)this + 10) = *((_DWORD *)a2 + 10);
  *((_QWORD *)this + 6) = pExceptionObject;
  *((_QWORD *)this + 7) = v4;
  *((_DWORD *)this + 16) = *((_DWORD *)a2 + 16);
  return this;
}

```

## disassembly

```asm
0x180024680  mov     [rsp+arg_10], rbx
0x180024685  push    rbp
0x180024686  push    rsi
0x180024687  push    rdi
0x180024688  push    r13
0x18002468a  push    r15
0x18002468c  sub     rsp, 40h
0x180024690  mov     rbp, rdx
0x180024693  mov     rsi, rcx
0x180024696  call    ??0IWbemCallSecurity@@QEAA@XZ; IWbemCallSecurity::IWbemCallSecurity(void)
0x18002469b  xor     r15d, r15d
0x18002469e  lea     rcx, ??_7CWbemCallSecurity@@6B@; const CWbemCallSecurity::`vftable'
0x1800246a5  mov     [rsi], rcx
0x1800246a8  mov     [rsp+68h+TargetHandle], r15
0x1800246ad  cmp     [rdx+10h], r15
0x1800246b1  jnz     loc_1800247C7
0x1800246b7  mov     rcx, [rbp+30h]
0x1800246bb  lea     r13, WPP_GLOBAL_Control
0x1800246c2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800246c6  mov     rbx, r15
0x1800246c9  mov     [rsp+68h+pExceptionObject], rbx
0x1800246ce  test    rcx, rcx
0x1800246d1  jnz     loc_180024867
0x1800246d7  mov     rax, [rbp+38h]
0x1800246db  xor     r9d, r9d
0x1800246de  test    rax, rax
0x1800246e1  jz      loc_180024778
0x1800246e7  inc     rdi
0x1800246ea  cmp     [rax+rdi*2], r9w
0x1800246ef  jnz     short loc_1800246E7
0x1800246f1  inc     rdi
0x1800246f4  lea     rcx, [rdi+rdi]; cb
0x1800246f8  call    cs:__imp_CoTaskMemAlloc
0x1800246fe  xor     r9d, r9d
0x180024701  mov     r15, rax
0x180024704  test    rax, rax
0x180024707  jz      loc_1800249B9
0x18002470d  test    rdi, rdi
0x180024710  jz      loc_1800248AF
0x180024716  cmp     rdi, 7FFFFFFFh
0x18002471d  ja      loc_180024A29
0x180024723  mov     rcx, [rbp+38h]
0x180024727  mov     eax, 7FFFFFFEh
0x18002472c  mov     rdx, r15
0x18002472f  test    rax, rax
0x180024732  jz      short loc_180024753
0x180024734  movzx   r8d, word ptr [rcx]
0x180024738  test    r8w, r8w
0x18002473c  jz      short loc_180024753
0x18002473e  mov     [rdx], r8w
0x180024742  add     rcx, 2
0x180024746  add     rdx, 2
0x18002474a  dec     rax
0x18002474d  sub     rdi, 1
0x180024751  jnz     short loc_18002472F
0x180024753  mov     rax, rdi
0x180024756  lea     rcx, [rdx-2]
0x18002475a  neg     rax
0x18002475d  sbb     ebx, ebx
0x18002475f  not     ebx
0x180024761  and     ebx, 8007007Ah
0x180024767  test    rdi, rdi
0x18002476a  cmovnz  rcx, rdx
0x18002476e  mov     [rcx], r9w
0x180024772  jz      loc_1800248BD
0x180024778  mov     rax, [rsp+68h+TargetHandle]
0x18002477d  mov     rbx, [rsp+68h+arg_10]
0x180024785  mov     [rsi+10h], rax
0x180024789  mov     eax, [rbp+18h]
0x18002478c  mov     [rsi+18h], eax
0x18002478f  mov     [rsi+1Ch], r9d
0x180024793  mov     eax, [rbp+20h]
0x180024796  mov     [rsi+20h], eax
0x180024799  mov     eax, [rbp+24h]
0x18002479c  mov     [rsi+24h], eax
0x18002479f  mov     eax, [rbp+28h]
0x1800247a2  mov     [rsi+28h], eax
0x1800247a5  mov     rax, [rsp+68h+pExceptionObject]
0x1800247aa  mov     [rsi+30h], rax
0x1800247ae  mov     [rsi+38h], r15
0x1800247b2  mov     eax, [rbp+40h]
0x1800247b5  mov     [rsi+40h], eax
0x1800247b8  mov     rax, rsi
0x1800247bb  add     rsp, 40h
0x1800247bf  pop     r15
0x1800247c1  pop     r13
0x1800247c3  pop     rdi
0x1800247c4  pop     rsi
0x1800247c5  pop     rbp
0x1800247c6  retn
0x1800247c7  call    cs:__imp_GetCurrentProcess
0x1800247cd  mov     rdi, [rbp+10h]
0x1800247d1  mov     rbx, rax
0x1800247d4  call    cs:__imp_GetCurrentProcess
0x1800247da  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1800247e2  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x1800247e7  mov     rcx, rax; hSourceProcessHandle
0x1800247ea  mov     [rsp+68h+bInheritHandle], 1; bInheritHandle
0x1800247f2  mov     r8, rbx; hTargetProcessHandle
0x1800247f5  mov     [rsp+68h+dwDesiredAccess], r15d; dwDesiredAccess
0x1800247fa  mov     rdx, rdi; hSourceHandle
0x1800247fd  call    cs:__imp_DuplicateHandle
0x180024803  test    eax, eax
0x180024805  jnz     loc_1800246B7
0x18002480b  lea     edx, [rax-2]; int
0x18002480e  lea     rcx, qword_18006A9C0; this
0x180024815  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002481a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024821  lea     r13, WPP_GLOBAL_Control
0x180024828  cmp     rcx, r13
0x18002482b  jz      short loc_180024855
0x18002482d  test    byte ptr [rcx+1Ch], 1
0x180024831  jz      short loc_180024855
0x180024833  cmp     byte ptr [rcx+19h], 2
0x180024837  jb      short loc_180024855
0x180024839  mov     rcx, [rcx+10h]
0x18002483d  lea     r9, aCxException; "CX_Exception()"
0x180024844  mov     edx, 0Ah
0x180024849  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x180024850  call    WPP_SF_s
0x180024855  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18002485c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180024861  call    _CxxThrowException_0
0x180024867  mov     rax, rdi
0x18002486a  inc     rax
0x18002486d  cmp     [rcx+rax*2], r15w
0x180024872  jnz     short loc_18002486A
0x180024874  lea     rbx, [rax+1]
0x180024878  lea     rcx, [rbx+rbx]; cb
0x18002487c  call    cs:__imp_CoTaskMemAlloc
0x180024882  mov     [rsp+68h+pExceptionObject], rax
0x180024887  test    rax, rax
0x18002488a  jz      short loc_180024903
0x18002488c  mov     r8, [rbp+30h]; unsigned __int16 *
0x180024890  mov     rdx, rbx; unsigned __int64
0x180024893  mov     rcx, rax; unsigned __int16 *
0x180024896  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002489b  mov     ebx, eax
0x18002489d  test    eax, eax
0x18002489f  js      loc_18002496A
0x1800248a5  mov     rbx, [rsp+68h+pExceptionObject]
0x1800248aa  jmp     loc_1800246D7
0x1800248af  mov     ebx, 80070057h
0x1800248b4  test    rdi, rdi
0x1800248b7  jz      short loc_1800248BD
0x1800248b9  mov     [rax], r9w
0x1800248bd  mov     edx, ebx; int
0x1800248bf  lea     rcx, qword_18006A9C0; this
0x1800248c6  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800248cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248d2  cmp     rcx, r13
0x1800248d5  jz      short loc_1800248FB
0x1800248d7  test    byte ptr [rcx+1Ch], 1
0x1800248db  jz      short loc_1800248FB
0x1800248dd  cmp     byte ptr [rcx+19h], 2
0x1800248e1  jb      short loc_1800248FB
0x1800248e3  mov     rcx, [rcx+10h]
0x1800248e7  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x1800248ee  mov     edx, 0Eh
0x1800248f3  mov     r9d, ebx
0x1800248f6  call    WPP_SF_D
0x1800248fb  xor     r9d, r9d
0x1800248fe  jmp     loc_180024778
0x180024903  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x180024908  test    rcx, rcx
0x18002490b  jz      short loc_180024913
0x18002490d  call    cs:__imp_CloseHandle
0x180024913  mov     edx, 0FFFFFFFEh; int
0x180024918  lea     rcx, qword_18006A9C0; this
0x18002491f  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180024924  mov     rcx, cs:WPP_GLOBAL_Control
0x18002492b  cmp     rcx, r13
0x18002492e  jz      short loc_180024958
0x180024930  test    byte ptr [rcx+1Ch], 1
0x180024934  jz      short loc_180024958
0x180024936  cmp     byte ptr [rcx+19h], 2
0x18002493a  jb      short loc_180024958
0x18002493c  mov     rcx, [rcx+10h]
0x180024940  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180024947  mov     edx, 0Bh
0x18002494c  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x180024953  call    WPP_SF_s
0x180024958  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18002495f  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180024964  call    _CxxThrowException_0
0x18002496a  mov     edx, ebx; int
0x18002496c  lea     rcx, qword_18006A9C0; this
0x180024973  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180024978  mov     rcx, cs:WPP_GLOBAL_Control
0x18002497f  cmp     rcx, r13
0x180024982  jz      loc_1800248A5
0x180024988  test    byte ptr [rcx+1Ch], 1
0x18002498c  jz      loc_1800248A5
0x180024992  cmp     byte ptr [rcx+19h], 2
0x180024996  jb      loc_1800248A5
0x18002499c  mov     rcx, [rcx+10h]
0x1800249a0  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x1800249a7  mov     edx, 0Ch
0x1800249ac  mov     r9d, ebx
0x1800249af  call    WPP_SF_D
0x1800249b4  jmp     loc_1800248A5
0x1800249b9  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x1800249be  test    rcx, rcx
0x1800249c1  jz      short loc_1800249C9
0x1800249c3  call    cs:__imp_CloseHandle
0x1800249c9  mov     rcx, rbx; pv
0x1800249cc  call    cs:__imp_CoTaskMemFree
0x1800249d2  mov     edx, 0FFFFFFFEh; int
0x1800249d7  lea     rcx, qword_18006A9C0; this
0x1800249de  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800249e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249ea  cmp     rcx, r13
0x1800249ed  jz      short loc_180024A17
0x1800249ef  test    byte ptr [rcx+1Ch], 1
0x1800249f3  jz      short loc_180024A17
0x1800249f5  cmp     byte ptr [rcx+19h], 2
0x1800249f9  jb      short loc_180024A17
0x1800249fb  mov     rcx, [rcx+10h]
0x1800249ff  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180024a06  mov     edx, 0Dh
0x180024a0b  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x180024a12  call    WPP_SF_s
0x180024a17  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180024a1e  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180024a23  call    _CxxThrowException_0
0x180024a29  mov     ebx, 80070057h
0x180024a2e  jmp     loc_1800248B9
```
