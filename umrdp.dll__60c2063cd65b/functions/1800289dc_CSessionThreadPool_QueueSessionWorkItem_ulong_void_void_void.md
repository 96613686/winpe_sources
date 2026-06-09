# CSessionThreadPool::QueueSessionWorkItem(ulong,void (*)(void *),void *)

- ea: `0x1800289dc`
- end: `0x180028cf7`
- name: `?QueueSessionWorkItem@CSessionThreadPool@@QEAAJKP6AXPEAX@Z0@Z`
- size: `795`
- prototype: `int(CSessionThreadPool *__hidden this, unsigned int, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002b4c8`
- `0x18002ca80`

## callees

- `0x180007da0`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000bd04`
- `0x18001ba64`
- `0x1800288a0`
- `0x1800289dc`
- `0x180028d00`
- `0x180028e6c`
- `0x180049010`

## string_xrefs

- `0x180028a49`: `Not queuing work item since session thread is exiting`
- `0x180028b85`: `Failed to initialize CSessionThread`
- `0x180028bec`: `Failed to add CSessionThread to CSessionThreadPool's _rgThreads`
- `0x180028ac7`: `CSessionThread`
- `0x180028cae`: `CSessionThread`

## pseudocode

```c
__int64 __fastcall CSessionThreadPool::QueueSessionWorkItem(
        CSessionThreadPool *this,
        unsigned int a2,
        void (*a3)(void *),
        void *a4)
{
  int v8; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  char *v10; // rbp
  signed int v11; // esi
  _QWORD **v12; // rbx
  char *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  char *v19; // [rsp+70h] [rbp+8h] BYREF

  v19 = (char *)this + 8;
  CTSCriticalSection::Lock((CSessionThreadPool *)((char *)this + 8));
  if ( !*(_DWORD *)this )
  {
    v8 = -2147467259;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        11,
        (unsigned int)WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Not queuing work item since session thread is exiting",
        5);
    }
    goto LABEL_33;
  }
  v10 = (char *)this + 24;
  v11 = a2 % 0xFF;
  if ( *((_DWORD *)this + 9) > (unsigned int)v11 && v11 >= 0 )
  {
    _mm_lfence();
    v12 = *(_QWORD ***)(*((_QWORD *)this + 5) + 8LL * v11);
    if ( v12 )
    {
LABEL_23:
      v8 = CSessionThread::QueueWorkItem((CSessionThread *)v12, a3, a4);
      if ( v8 < 0
        && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          15,
          (unsigned int)WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids,
          v16,
          (__int64)"Failed to queue Session work item",
          v8);
      }
      goto LABEL_33;
    }
  }
  v13 = (char *)operator new(0x80u);
  v12 = (_QWORD **)v13;
  if ( v13 )
  {
    *((_DWORD *)v13 + 6) = -607474739;
    *((_QWORD *)v13 + 2) = "CSessionThread";
    *((_DWORD *)v13 + 7) = 1;
    *(_QWORD *)v13 = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v13 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
    *(_QWORD *)v13 = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v13 + 1) = &CSessionThread::`vftable'{for `CTSObject'};
    *((_DWORD *)v13 + 10) = 0;
    *((_QWORD *)v13 + 4) = v13;
    *((_QWORD *)v13 + 8) = v13 + 56;
    *((_QWORD *)v13 + 7) = v13 + 56;
    *((_DWORD *)v13 + 12) = 0;
    *((_DWORD *)v13 + 20) = 0;
    *((_QWORD *)v13 + 9) = 0;
    *((_DWORD *)v13 + 22) = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 + 4) + 8LL))(*((_QWORD *)v13 + 4));
    v8 = CSessionThread::Initialize((CSessionThread *)(v12 + 1));
    if ( v8 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          13,
          (unsigned int)WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids,
          v14,
          (__int64)"Failed to initialize CSessionThread",
          v8);
      }
LABEL_22:
      (*(void (__fastcall **)(_QWORD *))(*v12[4] + 16LL))(v12[4]);
      goto LABEL_33;
    }
    if ( !CDynamicArray<CSessionThread>::Set(v10, (unsigned int)v11, v12) )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          14,
          (unsigned int)WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids,
          v15,
          (__int64)"Failed to add CSessionThread to CSessionThreadPool's _rgThreads",
          14);
      }
      v8 = -2147024882;
      goto LABEL_22;
    }
    goto LABEL_23;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      12,
      (unsigned int)WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids,
      v17,
      (__int64)"CSessionThread");
  }
  v8 = -2147024882;
LABEL_33:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800289dc  push    rbx
0x1800289de  push    rbp
0x1800289df  push    rsi
0x1800289e0  push    rdi
0x1800289e1  push    r14
0x1800289e3  push    r15
0x1800289e5  sub     rsp, 38h
0x1800289e9  mov     rbx, rcx
0x1800289ec  mov     r14, r9
0x1800289ef  add     rcx, 8; this
0x1800289f3  mov     r15, r8
0x1800289f6  mov     [rsp+68h+arg_0], rcx
0x1800289fb  mov     esi, edx
0x1800289fd  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180028a02  cmp     dword ptr [rbx], 0
0x180028a05  jnz     short loc_180028A74
0x180028a07  mov     edi, 80004005h
0x180028a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a13  lea     rax, WPP_GLOBAL_Control
0x180028a1a  cmp     rcx, rax
0x180028a1d  jz      loc_180028CDE
0x180028a23  test    byte ptr [rcx+1Ch], 8
0x180028a27  jz      loc_180028CDE
0x180028a2d  cmp     byte ptr [rcx+19h], 2
0x180028a31  jb      loc_180028CDE
0x180028a37  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028a3c  mov     edx, 0Bh
0x180028a41  mov     [rsp+68h+var_40], 80004005h
0x180028a49  lea     rcx, aNotQueuingWork; "Not queuing work item since session thr"...
0x180028a50  mov     [rsp+68h+var_48], rcx
0x180028a55  lea     r8, WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids
0x180028a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a63  mov     r9d, eax
0x180028a66  mov     rcx, [rcx+10h]
0x180028a6a  call    WPP_SF_DsD
0x180028a6f  jmp     loc_180028CDE
0x180028a74  mov     eax, 80808081h
0x180028a79  lea     rbp, [rbx+18h]
0x180028a7d  mul     esi
0x180028a7f  shr     edx, 7
0x180028a82  imul    eax, edx, 0FFh
0x180028a88  sub     esi, eax
0x180028a8a  cmp     [rbp+0Ch], esi
0x180028a8d  jbe     short loc_180028AAA
0x180028a8f  test    esi, esi
0x180028a91  js      short loc_180028AAA
0x180028a93  lfence
0x180028a96  mov     rax, [rbp+10h]
0x180028a9a  movsxd  rcx, esi
0x180028a9d  mov     rbx, [rax+rcx*8]
0x180028aa1  test    rbx, rbx
0x180028aa4  jnz     loc_180028C39
0x180028aaa  mov     ecx, 80h; Size
0x180028aaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028ab4  mov     rbx, rax
0x180028ab7  test    rax, rax
0x180028aba  jz      loc_180028C8A
0x180028ac0  mov     dword ptr [rax+18h], 0DBCAABCDh
0x180028ac7  lea     rcx, aCsessionthread; "CSessionThread"
0x180028ace  mov     [rax+10h], rcx
0x180028ad2  mov     dword ptr [rax+1Ch], 1
0x180028ad9  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x180028ae0  mov     [rbx], rax
0x180028ae3  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180028aea  mov     [rbx+8], rax
0x180028aee  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x180028af5  mov     [rbx], rax
0x180028af8  lea     rax, ??_7CSessionThread@@6BCTSObject@@@; const CSessionThread::`vftable'{for `CTSObject'}
0x180028aff  mov     [rbx+8], rax
0x180028b03  lea     rax, [rbx+38h]
0x180028b07  mov     dword ptr [rbx+28h], 0
0x180028b0e  mov     [rbx+20h], rbx
0x180028b12  mov     [rbx+40h], rax
0x180028b16  mov     [rax], rax
0x180028b19  mov     dword ptr [rbx+30h], 0
0x180028b20  mov     dword ptr [rbx+50h], 0
0x180028b27  mov     qword ptr [rbx+48h], 0
0x180028b2f  mov     dword ptr [rbx+58h], 0
0x180028b36  mov     rcx, [rbx+20h]
0x180028b3a  mov     rax, [rcx]
0x180028b3d  mov     rax, [rax+8]
0x180028b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b46  lea     rcx, [rbx+8]; this
0x180028b4a  call    ?Initialize@CSessionThread@@UEAAJXZ; CSessionThread::Initialize(void)
0x180028b4f  mov     edi, eax
0x180028b51  test    eax, eax
0x180028b53  jns     short loc_180028BB6
0x180028b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b5c  lea     rax, WPP_GLOBAL_Control
0x180028b63  cmp     rcx, rax
0x180028b66  jz      loc_180028C24
0x180028b6c  test    byte ptr [rcx+1Ch], 8
0x180028b70  jz      loc_180028C24
0x180028b76  cmp     byte ptr [rcx+19h], 2
0x180028b7a  jb      loc_180028C24
0x180028b80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028b85  lea     rcx, aFailedToInitia; "Failed to initialize CSessionThread"
0x180028b8c  mov     [rsp+68h+var_40], edi
0x180028b90  mov     [rsp+68h+var_48], rcx
0x180028b95  lea     r8, WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids
0x180028b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ba3  mov     edx, 0Dh
0x180028ba8  mov     r9d, eax
0x180028bab  mov     rcx, [rcx+10h]
0x180028baf  call    WPP_SF_DsD
0x180028bb4  jmp     short loc_180028C24
0x180028bb6  mov     r8, rbx
0x180028bb9  mov     edx, esi
0x180028bbb  mov     rcx, rbp
0x180028bbe  call    ?Set@?$CDynamicArray@VCSessionThread@@@@QEAAPEAVCSessionThread@@HPEAV2@@Z; CDynamicArray<CSessionThread>::Set(int,CSessionThread *)
0x180028bc3  test    rax, rax
0x180028bc6  jnz     short loc_180028C39
0x180028bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bcf  lea     rax, WPP_GLOBAL_Control
0x180028bd6  cmp     rcx, rax
0x180028bd9  jz      short loc_180028C1F
0x180028bdb  test    byte ptr [rcx+1Ch], 8
0x180028bdf  jz      short loc_180028C1F
0x180028be1  cmp     byte ptr [rcx+19h], 2
0x180028be5  jb      short loc_180028C1F
0x180028be7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028bec  lea     rcx, aFailedToAddCse; "Failed to add CSessionThread to CSessio"...
0x180028bf3  mov     [rsp+68h+var_40], 8007000Eh
0x180028bfb  mov     [rsp+68h+var_48], rcx
0x180028c00  lea     r8, WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids
0x180028c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c0e  mov     edx, 0Eh
0x180028c13  mov     r9d, eax
0x180028c16  mov     rcx, [rcx+10h]
0x180028c1a  call    WPP_SF_DsD
0x180028c1f  mov     edi, 8007000Eh
0x180028c24  mov     rcx, [rbx+20h]
0x180028c28  mov     rax, [rcx]
0x180028c2b  mov     rax, [rax+10h]
0x180028c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c34  jmp     loc_180028CDE
0x180028c39  mov     r8, r14; void *
0x180028c3c  mov     rdx, r15; void (*)(void *)
0x180028c3f  mov     rcx, rbx; this
0x180028c42  call    ?QueueWorkItem@CSessionThread@@QEAAJP6AXPEAX@Z0@Z; CSessionThread::QueueWorkItem(void (*)(void *),void *)
0x180028c47  mov     edi, eax
0x180028c49  test    eax, eax
0x180028c4b  jns     loc_180028CDE
0x180028c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c58  lea     rax, WPP_GLOBAL_Control
0x180028c5f  cmp     rcx, rax
0x180028c62  jz      short loc_180028CDE
0x180028c64  test    byte ptr [rcx+1Ch], 8
0x180028c68  jz      short loc_180028CDE
0x180028c6a  cmp     byte ptr [rcx+19h], 2
0x180028c6e  jb      short loc_180028CDE
0x180028c70  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028c75  mov     edx, 0Fh
0x180028c7a  mov     [rsp+68h+var_40], edi
0x180028c7e  lea     rcx, aFailedToQueueS; "Failed to queue Session work item"
0x180028c85  jmp     loc_180028A50
0x180028c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c91  lea     rax, WPP_GLOBAL_Control
0x180028c98  cmp     rcx, rax
0x180028c9b  jz      short loc_180028CD9
0x180028c9d  test    byte ptr [rcx+1Ch], 8
0x180028ca1  jz      short loc_180028CD9
0x180028ca3  cmp     byte ptr [rcx+19h], 2
0x180028ca7  jb      short loc_180028CD9
0x180028ca9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028cae  lea     rcx, aCsessionthread; "CSessionThread"
0x180028cb5  mov     edx, 0Ch
0x180028cba  mov     [rsp+68h+var_48], rcx
0x180028cbf  lea     r8, WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids
0x180028cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ccd  mov     r9d, eax
0x180028cd0  mov     rcx, [rcx+10h]
0x180028cd4  call    WPP_SF_Ds
0x180028cd9  mov     edi, 8007000Eh
0x180028cde  lea     rcx, [rsp+68h+arg_0]; this
0x180028ce3  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180028ce8  mov     eax, edi
0x180028cea  add     rsp, 38h
0x180028cee  pop     r15
0x180028cf0  pop     r14
0x180028cf2  pop     rdi
0x180028cf3  pop     rsi
0x180028cf4  pop     rbp
0x180028cf5  pop     rbx
0x180028cf6  retn
```
