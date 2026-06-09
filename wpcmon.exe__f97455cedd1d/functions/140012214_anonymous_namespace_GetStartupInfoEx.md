# _anonymous_namespace_::GetStartupInfoEx

- ea: `0x140012214`
- end: `0x140012612`
- name: `_anonymous_namespace_::GetStartupInfoEx`
- size: `1022`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14000e4ac`
- `0x14000edf0`

## callees

- `0x1400050b0`
- `0x1400050c0`
- `0x1400057f0`
- `0x140006308`
- `0x140006314`
- `0x140006338`
- `0x14000a13c`
- `0x140012214`
- `0x14001f6b4`
- `0x140060f58`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!UpdateProcThreadAttribute` at `0x1400123f0`
- `KERNEL32!UpdateProcThreadAttribute` at `0x1400123f0`
- `KERNEL32!GetLastError` at `0x14001233b`
- `KERNEL32!GetLastError` at `0x14001248a`
- `KERNEL32!GetLastError` at `0x1400124ec`
- `KERNEL32!GetLastError` at `0x14001254e`
- `KERNEL32!GetLastError` at `0x1400125b0`
- `KERNEL32!GetLastError` at `0x14001233b`
- `KERNEL32!GetLastError` at `0x14001248a`
- `KERNEL32!GetLastError` at `0x1400124ec`
- `KERNEL32!GetLastError` at `0x14001254e`
- `KERNEL32!GetLastError` at `0x1400125b0`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x140012335`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1400123b1`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x140012335`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1400123b1`
- `KERNEL32!SetHandleInformation` at `0x14001230a`
- `KERNEL32!SetHandleInformation` at `0x14001230a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall anonymous_namespace_::GetStartupInfoEx(_QWORD *a1, HANDLE **a2)
{
  char *v4; // rdi
  HANDLE *v5; // rsi
  __int64 trivial_8; // rax
  HANDLE *v7; // rax
  HANDLE *v8; // r12
  size_t v9; // rbx
  HANDLE *v10; // rbx
  HANDLE *v11; // rsi
  struct _PROC_THREAD_ATTRIBUTE_LIST **v12; // rsi
  __int64 v13; // r12
  __int64 v14; // rdx
  ULONG_PTR v15; // rcx
  ULONG_PTR v16; // rax
  ULONG_PTR v17; // rbx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v18; // rcx
  signed int v20; // eax
  unsigned int v21; // ebx
  signed int LastError; // eax
  unsigned int v23; // ebx
  signed int v24; // eax
  unsigned int v25; // ebx
  signed int v26; // eax
  unsigned int v27; // ebx
  _BYTE pExceptionObject[88]; // [rsp+68h] [rbp-1h] BYREF
  ULONG_PTR Size; // [rsp+D8h] [rbp+6Fh] BYREF
  char *v30; // [rsp+E0h] [rbp+77h]

  v4 = (char *)operator new(0x98u);
  v30 = v4;
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *(_QWORD *)v4 = ___7___Ref_count_obj2_UStartupInfo__1__GetStartupInfoEx__A0xb64ffc07__YA_AV__shared_ref_U_STARTUPINFOEXW___stdext__AEAV__vector_PEAXV__allocator_PEAX_std___std___Z__std__6B_;
  memset_0(v4 + 20, 0, 0x6Cu);
  *((_QWORD *)v4 + 16) = 0;
  *((_QWORD *)v4 + 17) = 0;
  *((_QWORD *)v4 + 18) = 0;
  *((_DWORD *)v4 + 4) = 112;
  v5 = a2[1];
  trivial_8 = _std_find_trivial_8(*a2, v5, 0);
  if ( (HANDLE *)trivial_8 != v5 )
  {
    v7 = (HANDLE *)_std_remove_8(trivial_8, v5, 0);
    v8 = v7;
    if ( v7 != v5 )
    {
      v9 = (char *)a2[1] - (char *)v5;
      memmove_0(v7, v5, v9);
      a2[1] = (HANDLE *)((char *)v8 + v9);
    }
  }
  v10 = *a2;
  v11 = a2[1];
  while ( v10 != v11 )
  {
    if ( !SetHandleInformation(*v10, 1u, 1u) )
    {
      LastError = GetLastError();
      v23 = LastError;
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v23);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v23);
      throw (ErrorCodeException *)pExceptionObject;
    }
    ++v10;
  }
  Size = 0;
  InitializeProcThreadAttributeList(0, 1u, 0, &Size);
  if ( GetLastError() != 122 )
  {
    v20 = GetLastError();
    v21 = v20;
    if ( v20 > 0 )
      v21 = (unsigned __int16)v20 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v21);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v21);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v12 = (struct _PROC_THREAD_ATTRIBUTE_LIST **)(v4 + 128);
  v13 = *((_QWORD *)v4 + 17);
  v14 = *((_QWORD *)v4 + 16);
  v15 = v13 - v14;
  if ( Size >= v13 - v14 )
  {
    if ( Size <= v15 )
      goto LABEL_16;
    if ( Size > *((_QWORD *)v4 + 18) - v14 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v4 + 128, Size);
      goto LABEL_16;
    }
    v17 = Size - v15;
    memset_0(*((void **)v4 + 17), 0, Size - v15);
    v16 = v17 + v13;
  }
  else
  {
    v16 = v14 + Size;
  }
  *((_QWORD *)v4 + 17) = v16;
LABEL_16:
  v18 = *v12;
  *((_QWORD *)v4 + 15) = *v12;
  if ( !InitializeProcThreadAttributeList(v18, 1u, 0, &Size) )
  {
    v24 = GetLastError();
    v25 = v24;
    if ( v24 > 0 )
      v25 = (unsigned __int16)v24 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v25);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v25);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( !UpdateProcThreadAttribute(
          *((LPPROC_THREAD_ATTRIBUTE_LIST *)v4 + 15),
          0,
          0x20002u,
          *a2,
          ((char *)a2[1] - (char *)*a2) & 0xFFFFFFFFFFFFFFF8uLL,
          0,
          0) )
  {
    v26 = GetLastError();
    v27 = v26;
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids, v27);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v27);
    throw (ErrorCodeException *)pExceptionObject;
  }
  _InterlockedAdd((volatile signed __int32 *)v4 + 2, 1u);
  *a1 = v4 + 16;
  a1[1] = v4;
  if ( v4 == (char *)-16LL )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v4)(v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  }
  return a1;
}

```

## disassembly

```asm
0x140012214  mov     [rsp-8+arg_18], rbx
0x140012219  mov     [rsp-8+arg_0], rcx
0x14001221e  push    rbp
0x14001221f  push    rsi
0x140012220  push    rdi
0x140012221  push    r12
0x140012223  push    r13
0x140012225  push    r14
0x140012227  push    r15
0x140012229  lea     rbp, [rsp-27h]
0x14001222e  sub     rsp, 90h
0x140012235  mov     r15, rdx
0x140012238  mov     r13, rcx
0x14001223b  mov     ecx, 98h; Size
0x140012240  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012245  mov     rdi, rax
0x140012248  mov     [rbp+57h+arg_10], rax
0x14001224c  xorps   xmm0, xmm0
0x14001224f  movups  xmmword ptr [rax], xmm0
0x140012252  mov     r12d, 1
0x140012258  mov     [rax+8], r12d
0x14001225c  mov     [rax+0Ch], r12d
0x140012260  lea     rax, ??_7?$_Ref_count_obj2@UStartupInfo@?1??GetStartupInfoEx@?A0xb64ffc07@@YA?AV?$shared_ref@U_STARTUPINFOEXW@@@stdext@@AEAV?$vector@PEAXV?$allocator@PEAX@std@@@std@@@Z@@std@@6B@; const std::_Ref_count_obj2<``anonymous namespace'::GetStartupInfoEx(std::vector<void *> &)'::`2'::StartupInfo>::`vftable'
0x140012267  mov     [rdi], rax
0x14001226a  lea     r14, [rdi+10h]
0x14001226e  lea     rcx, [r14+4]; void *
0x140012272  xor     edx, edx; Val
0x140012274  lea     r8d, [r12+6Bh]; Size
0x140012279  call    memset_0
0x14001227e  mov     qword ptr [r14+70h], 0
0x140012286  mov     qword ptr [r14+78h], 0
0x14001228e  mov     qword ptr [r14+80h], 0
0x140012299  mov     dword ptr [r14], 70h ; 'p'
0x1400122a0  mov     [rbp+57h+var_78], r14
0x1400122a4  mov     [rbp+57h+var_70], rdi
0x1400122a8  mov     rsi, [r15+8]
0x1400122ac  xor     r8d, r8d
0x1400122af  mov     rdx, rsi
0x1400122b2  mov     rcx, [r15]
0x1400122b5  call    __std_find_trivial_8
0x1400122ba  cmp     rax, rsi
0x1400122bd  jz      short loc_1400122F8
0x1400122bf  xor     r8d, r8d
0x1400122c2  mov     rdx, rsi
0x1400122c5  mov     rcx, rax
0x1400122c8  call    __std_remove_8
0x1400122cd  mov     r12, rax
0x1400122d0  cmp     rax, rsi
0x1400122d3  jz      short loc_1400122F2
0x1400122d5  mov     rbx, [r15+8]
0x1400122d9  sub     rbx, rsi
0x1400122dc  mov     r8, rbx; Size
0x1400122df  mov     rdx, rsi; Src
0x1400122e2  mov     rcx, rax; void *
0x1400122e5  call    memmove_0
0x1400122ea  lea     rax, [r12+rbx]
0x1400122ee  mov     [r15+8], rax
0x1400122f2  mov     r12d, 1
0x1400122f8  mov     rbx, [r15]
0x1400122fb  mov     rsi, [r15+8]
0x1400122ff  jmp     short loc_14001231C
0x140012301  mov     r8d, r12d; dwFlags
0x140012304  mov     edx, r12d; dwMask
0x140012307  mov     rcx, [rbx]; hObject
0x14001230a  call    cs:__imp_SetHandleInformation
0x140012310  test    eax, eax
0x140012312  jz      loc_1400124EC
0x140012318  add     rbx, 8
0x14001231c  cmp     rbx, rsi
0x14001231f  jnz     short loc_140012301
0x140012321  mov     [rbp+57h+Size], 0
0x140012329  lea     r9, [rbp+57h+Size]; lpSize
0x14001232d  xor     r8d, r8d; dwFlags
0x140012330  mov     edx, r12d; dwAttributeCount
0x140012333  xor     ecx, ecx; lpAttributeList
0x140012335  call    cs:__imp_InitializeProcThreadAttributeList
0x14001233b  call    cs:__imp_GetLastError
0x140012341  cmp     eax, 7Ah ; 'z'
0x140012344  jnz     loc_14001248A
0x14001234a  lea     rsi, [r14+70h]
0x14001234e  mov     rbx, [rbp+57h+Size]
0x140012352  mov     r12, [rsi+8]
0x140012356  mov     rdx, [rsi]
0x140012359  mov     rcx, r12
0x14001235c  sub     rcx, rdx
0x14001235f  cmp     rbx, rcx
0x140012362  jnb     short loc_14001236A
0x140012364  lea     rax, [rdx+rbx]
0x140012368  jmp     short loc_140012399
0x14001236a  jbe     short loc_14001239D
0x14001236c  mov     rax, [rsi+10h]
0x140012370  sub     rax, rdx
0x140012373  cmp     rbx, rax
0x140012376  jbe     short loc_140012385
0x140012378  mov     rdx, rbx
0x14001237b  mov     rcx, rsi
0x14001237e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140012383  jmp     short loc_14001239D
0x140012385  sub     rbx, rcx
0x140012388  mov     r8, rbx; Size
0x14001238b  xor     edx, edx; Val
0x14001238d  mov     rcx, r12; void *
0x140012390  call    memset_0
0x140012395  lea     rax, [rbx+r12]
0x140012399  mov     [rsi+8], rax
0x14001239d  mov     rcx, [rsi]; lpAttributeList
0x1400123a0  mov     [r14+68h], rcx
0x1400123a4  lea     r9, [rbp+57h+Size]; lpSize
0x1400123a8  xor     r8d, r8d; dwFlags
0x1400123ab  lea     esi, [r8+1]
0x1400123af  mov     edx, esi; dwAttributeCount
0x1400123b1  call    cs:__imp_InitializeProcThreadAttributeList
0x1400123b7  test    eax, eax
0x1400123b9  jz      loc_14001254E
0x1400123bf  mov     rax, [r15+8]
0x1400123c3  sub     rax, [r15]
0x1400123c6  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400123ca  mov     [rsp+0C0h+lpReturnSize], 0; lpReturnSize
0x1400123d3  mov     [rsp+0C0h+lpPreviousValue], 0; lpPreviousValue
0x1400123dc  mov     [rsp+0C0h+cbSize], rax; cbSize
0x1400123e1  mov     r9, [r15]; lpValue
0x1400123e4  xor     edx, edx; dwFlags
0x1400123e6  mov     r8d, 20002h; Attribute
0x1400123ec  mov     rcx, [r14+68h]; lpAttributeList
0x1400123f0  call    cs:__imp_UpdateProcThreadAttribute
0x1400123f6  test    eax, eax
0x1400123f8  jz      loc_1400125B0
0x1400123fe  lock add [rdi+8], esi
0x140012402  mov     [r13+0], r14
0x140012406  mov     [r13+8], rdi
0x14001240a  xorps   xmm0, xmm0
0x14001240d  movdqu  [rbp+57h+var_68], xmm0
0x140012412  test    r14, r14
0x140012415  jz      short loc_14001246B
0x140012417  or      ebx, 0FFFFFFFFh
0x14001241a  mov     eax, ebx
0x14001241c  lock xadd [rdi+8], eax
0x140012421  add     eax, ebx
0x140012423  jnz     short loc_14001244D
0x140012425  mov     rax, [rdi]
0x140012428  mov     rcx, rdi
0x14001242b  mov     rax, [rax]
0x14001242e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012433  mov     eax, ebx
0x140012435  lock xadd [rdi+0Ch], eax
0x14001243a  add     eax, ebx
0x14001243c  jnz     short loc_14001244D
0x14001243e  mov     rax, [rdi]
0x140012441  mov     rcx, rdi
0x140012444  mov     rax, [rax+8]
0x140012448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001244d  mov     rax, r13
0x140012450  mov     rbx, [rsp+0C0h+arg_18]
0x140012458  add     rsp, 90h
0x14001245f  pop     r15
0x140012461  pop     r14
0x140012463  pop     r13
0x140012465  pop     r12
0x140012467  pop     rdi
0x140012468  pop     rsi
0x140012469  pop     rbp
0x14001246a  retn
0x14001246b  mov     edx, 8000FFFFh; int
0x140012470  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140012474  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140012479  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140012480  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140012484  call    _CxxThrowException_0
0x14001248a  call    cs:__imp_GetLastError
0x140012490  mov     ebx, eax
0x140012492  test    eax, eax
0x140012494  jle     short loc_14001249F
0x140012496  movzx   ebx, ax
0x140012499  or      ebx, 80070000h
0x14001249f  lea     rax, WPP_GLOBAL_Control
0x1400124a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400124ad  cmp     rcx, rax
0x1400124b0  jz      short loc_1400124D0
0x1400124b2  test    [rcx+1Ch], r12b
0x1400124b6  jz      short loc_1400124D0
0x1400124b8  mov     edx, 13h
0x1400124bd  mov     r9d, ebx
0x1400124c0  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x1400124c7  mov     rcx, [rcx+10h]
0x1400124cb  call    WPP_SF_d
0x1400124d0  mov     edx, ebx; int
0x1400124d2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400124d6  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400124db  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400124e2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400124e6  call    _CxxThrowException_0
0x1400124ec  call    cs:__imp_GetLastError
0x1400124f2  mov     ebx, eax
0x1400124f4  test    eax, eax
0x1400124f6  jle     short loc_140012501
0x1400124f8  movzx   ebx, ax
0x1400124fb  or      ebx, 80070000h
0x140012501  lea     rax, WPP_GLOBAL_Control
0x140012508  mov     rcx, cs:WPP_GLOBAL_Control
0x14001250f  cmp     rcx, rax
0x140012512  jz      short loc_140012532
0x140012514  test    [rcx+1Ch], r12b
0x140012518  jz      short loc_140012532
0x14001251a  mov     edx, 12h
0x14001251f  mov     r9d, ebx
0x140012522  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x140012529  mov     rcx, [rcx+10h]
0x14001252d  call    WPP_SF_d
0x140012532  mov     edx, ebx; int
0x140012534  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140012538  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14001253d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140012544  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140012548  call    _CxxThrowException_0
0x14001254e  call    cs:__imp_GetLastError
0x140012554  mov     ebx, eax
0x140012556  test    eax, eax
0x140012558  jle     short loc_140012563
0x14001255a  movzx   ebx, ax
0x14001255d  or      ebx, 80070000h
0x140012563  lea     rax, WPP_GLOBAL_Control
0x14001256a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012571  cmp     rcx, rax
0x140012574  jz      short loc_140012594
0x140012576  test    [rcx+1Ch], sil
0x14001257a  jz      short loc_140012594
0x14001257c  mov     edx, 14h
0x140012581  mov     r9d, ebx
0x140012584  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x14001258b  mov     rcx, [rcx+10h]
0x14001258f  call    WPP_SF_d
0x140012594  mov     edx, ebx; int
0x140012596  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001259a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14001259f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400125a6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400125aa  call    _CxxThrowException_0
0x1400125b0  call    cs:__imp_GetLastError
0x1400125b6  mov     ebx, eax
0x1400125b8  test    eax, eax
0x1400125ba  jle     short loc_1400125C5
0x1400125bc  movzx   ebx, ax
0x1400125bf  or      ebx, 80070000h
0x1400125c5  lea     rax, WPP_GLOBAL_Control
0x1400125cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400125d3  cmp     rcx, rax
0x1400125d6  jz      short loc_1400125F6
0x1400125d8  test    [rcx+1Ch], sil
0x1400125dc  jz      short loc_1400125F6
0x1400125de  mov     edx, 15h
0x1400125e3  mov     r9d, ebx
0x1400125e6  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x1400125ed  mov     rcx, [rcx+10h]
0x1400125f1  call    WPP_SF_d
0x1400125f6  mov     edx, ebx; int
0x1400125f8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400125fc  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140012601  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140012608  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001260c  call    _CxxThrowException_0
```
