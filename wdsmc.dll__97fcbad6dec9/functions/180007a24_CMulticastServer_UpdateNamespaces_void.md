# CMulticastServer::UpdateNamespaces(void)

- ea: `0x180007a24`
- end: `0x180007e5d`
- name: `?UpdateNamespaces@CMulticastServer@@AEAAXXZ`
- size: `1081`
- prototype: `void __fastcall(CMulticastServer *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update`

## callers

- `0x180008c50`

## callees

- `0x1800026b8`
- `0x180002810`
- `0x1800031e4`
- `0x180003814`
- `0x180003868`
- `0x180007a24`
- `0x180008698`
- `0x180008bd8`
- `0x180008dcc`
- `0x18001a9a8`
- `0x18001b0ac`
- `0x1800226e4`
- `0x180024b0c`
- `0x180025850`
- `0x180026694`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x180007d3d`
- `KERNEL32!SystemTimeToFileTime` at `0x180007d3d`
- `KERNEL32!LeaveCriticalSection` at `0x180007cdf`
- `KERNEL32!LeaveCriticalSection` at `0x180007ce8`
- `KERNEL32!LeaveCriticalSection` at `0x180007dc0`
- `KERNEL32!LeaveCriticalSection` at `0x180007cdf`
- `KERNEL32!LeaveCriticalSection` at `0x180007ce8`
- `KERNEL32!LeaveCriticalSection` at `0x180007dc0`
- `KERNEL32!EnterCriticalSection` at `0x180007c6f`
- `KERNEL32!EnterCriticalSection` at `0x180007cbc`
- `KERNEL32!EnterCriticalSection` at `0x180007ccc`
- `KERNEL32!EnterCriticalSection` at `0x180007c6f`
- `KERNEL32!EnterCriticalSection` at `0x180007cbc`
- `KERNEL32!EnterCriticalSection` at `0x180007ccc`

## pseudocode

```c
void __fastcall CMulticastServer::UpdateNamespaces(CMulticastServer *this)
{
  int v2; // r13d
  void *v3; // r15
  unsigned int v4; // r12d
  __int64 v5; // rdi
  char *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  void (__fastcall ***v10)(_QWORD); // r14
  const char *v11; // rdx
  unsigned int v12; // esi
  int v13; // eax
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // kr00_8
  void *v18; // rax
  int v19; // ebx
  bool v20; // zf
  __int64 i; // rsi
  int v22; // ebx
  _QWORD *v23; // r12
  CMulticastNamespace *v24; // rdi
  CMulticastNamespace *v25; // rsi
  CMulticastNamespace *v26; // r15
  CMulticastNamespace *v27; // r14
  unsigned int v28; // r12d
  __int64 v29; // r13
  __int64 v30; // rsi
  struct _RTL_CRITICAL_SECTION *v31; // rbx
  signed __int32 v32; // edi
  int v33; // eax
  unsigned __int64 v34; // rbx
  unsigned int v35; // eax
  const char *v36; // rdx
  unsigned int v37; // eax
  const char *v38; // rdx
  unsigned int v39; // r9d
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+20h] [rbp-58h]
  CMRSWLock *v41; // [rsp+28h] [rbp-50h] BYREF
  int v42; // [rsp+30h] [rbp-48h]
  CMulticastNamespace *v43[2]; // [rsp+38h] [rbp-40h] BYREF
  int v44; // [rsp+4Ch] [rbp-2Ch]
  _FILETIME v45; // [rsp+50h] [rbp-28h] BYREF
  __int64 v46; // [rsp+58h] [rbp-20h]
  int v47; // [rsp+C0h] [rbp+48h]
  CMulticastNamespace *v48; // [rsp+C8h] [rbp+50h] BYREF
  _FILETIME FileTime; // [rsp+D0h] [rbp+58h] BYREF
  _QWORD *v50; // [rsp+D8h] [rbp+60h]

  v41 = this;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v45 = 0;
  v5 = 0;
  v46 = 0;
  v42 = 0;
  *(_OWORD *)v43 = 0;
  v47 = 0;
  v44 = 0;
  CAutoWriterLock::Lock((LPCRITICAL_SECTION *)&v41);
  v6 = (char *)this + 824;
  v7 = *((_QWORD *)this + 103);
  v50 = v6;
  if ( v7 )
  {
    v8 = v7;
    v9 = v7;
    do
    {
      v10 = (void (__fastcall ***)(_QWORD))(v9 & -(__int64)(v8 != 0));
      (**v10)(v10);
      v12 = 0;
      if ( (_DWORD)v5 != v4 )
        goto LABEL_18;
      v13 = v4 >> 1;
      if ( v4 >> 1 < 0x20 )
        v13 = 32;
      v14 = v4 + v13;
      v15 = -1;
      if ( v14 >= v4 )
        v15 = v14;
      v11 = v14 < v4 ? (const char *)0x80070216LL : 0LL;
      LODWORD(v48) = v15;
      if ( v14 >= v4 )
      {
        v17 = v15;
        v16 = 8LL * v15;
        if ( !is_mul_ok(v17, 8u) )
          v16 = -1;
        v18 = operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
        FileTime = (_FILETIME)v18;
        if ( !v18 )
        {
          v12 = 8;
          goto LABEL_19;
        }
        memmove_0(v18, v3, 8LL * v4);
        operator delete(v3);
        v3 = (void *)FileTime;
        v4 = (unsigned int)v48;
        v45 = FileTime;
        LODWORD(v46) = (_DWORD)v48;
      }
      else
      {
        v12 = v14 < v4 ? 0x216 : 0;
        if ( (v14 < v4 ? 0x70000 : 0) != 0x70000 )
          v12 = v14 < v4 ? 0x80070216 : 0;
      }
      if ( !v12 )
      {
LABEL_18:
        *((_QWORD *)v3 + v5) = v10;
        v5 = (unsigned int)(v5 + 1);
        HIDWORD(v46) = v5;
      }
LABEL_19:
      if ( ElValidateWin32(v12, v11, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x792u) )
      {
        v22 = v42;
        goto LABEL_64;
      }
      v7 = *(_QWORD *)(v7 + 456);
      v8 = v7;
      v9 = v7;
    }
    while ( v7 );
  }
  v19 = v42;
  if ( v42 )
  {
    v20 = v42 == 1;
    v19 = --v42;
    if ( v20 )
      CMRSWLock::WriterRelease(v41);
  }
  for ( i = 0; (unsigned int)i < (unsigned int)v5; i = (unsigned int)(i + 1) )
    CMulticastNamespace::Cleanup(*((CMulticastNamespace **)v3 + i));
  CDynArray<CMulticastNamespace *,CDeallocateRelease>::Clear(&v45);
  if ( v19 )
  {
    v22 = v19 + 1;
    v42 = v22;
  }
  else
  {
    CAutoWriterLock::Lock((LPCRITICAL_SECTION *)&v41);
    v22 = v42;
  }
  v23 = v50;
  v24 = v43[0];
  v25 = (CMulticastNamespace *)*v50;
  if ( *v50 )
  {
    v26 = v43[1];
    v48 = (CMulticastNamespace *)*v50;
    while ( 1 )
    {
      v27 = v25;
      if ( (unsigned int)CMulticastNamespace::CanDelete(v25) )
      {
        CList<CMulticastNamespace,CNoLock>::DeleteAt(v23, &v48);
        *((_QWORD *)v25 + 57) = 0;
        v43[1] = v25;
        if ( v24 )
        {
          *((_QWORD *)v25 + 58) = v26;
          *((_QWORD *)v26 + 57) = v25;
        }
        else
        {
          *((_QWORD *)v25 + 58) = 0;
          v24 = v25;
          v43[0] = v25;
        }
        v25 = v48;
        v47 = ++v2;
        v26 = v27;
        v44 = v2;
        goto LABEL_54;
      }
      v28 = 0;
      lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)v25 + 16);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v25 + 16));
      if ( *((_DWORD *)v25 + 18) != 1 && !*((_DWORD *)v25 + 35) && !*((_DWORD *)v25 + 30) && *((_DWORD *)v25 + 36) != 1 )
      {
        v29 = *((_QWORD *)v25 + 53);
        if ( v29 )
        {
          do
          {
            v30 = v29;
            v29 = *(_QWORD *)(v29 + 3080);
            EnterCriticalSection((LPCRITICAL_SECTION)v30);
            v31 = *(struct _RTL_CRITICAL_SECTION **)(v30 + 312);
            EnterCriticalSection(v31);
            v32 = _InterlockedExchangeAdd((volatile signed __int32 *)(v30 + 3056), 0);
            LeaveCriticalSection(v31);
            LeaveCriticalSection((LPCRITICAL_SECTION)v30);
            v28 += v32;
          }
          while ( v29 );
          v2 = v44;
          v25 = v48;
          v26 = v43[1];
          v24 = v43[0];
          v47 = v44;
        }
        else
        {
          v2 = v47;
        }
        v33 = *((_DWORD *)v27 + 37);
        if ( (v33 & 1) != 0 && v28 >= *((_DWORD *)v27 + 38) )
          goto LABEL_51;
        if ( (v33 & 2) == 0 )
          goto LABEL_53;
        FileTime = 0;
        SystemTimeToFileTime((const SYSTEMTIME *)((char *)v27 + 156), &FileTime);
        v34 = CDate::FileTimeToMSec(&FileTime);
        if ( v34 > CDate::FileTimeToMSec(0) )
          goto LABEL_53;
        if ( v28 )
        {
LABEL_51:
          v37 = CMulticastNamespace::MgmtStart(v27);
          v39 = 1529;
        }
        else
        {
          v35 = CWdsTptNamespaceStore::RemoveNamespace(
                  *((CWdsTptNamespaceStore **)qword_1800336E8 + 106),
                  *((const unsigned __int16 **)v27 + 10));
          ElValidateWin32(v35, v36, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x5E8u);
          v37 = CMulticastNamespace::Close(v27, 1);
          v39 = 1517;
        }
        ElValidateWin32(v37, v38, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", v39);
      }
LABEL_53:
      LeaveCriticalSection(lpCriticalSection);
      v25 = (CMulticastNamespace *)*((_QWORD *)v25 + 57);
      v23 = v50;
      v48 = v25;
LABEL_54:
      if ( !v25 )
      {
        v22 = v42;
        break;
      }
    }
  }
  if ( v22 )
  {
    if ( !--v22 )
      CMRSWLock::WriterRelease(v41);
  }
  if ( v24 )
  {
    v48 = v24;
    do
    {
      CList<CMulticastNamespace,CNoLock>::DeleteAt(v43, &v48);
      CMulticastNamespace::Shutdown(v24);
      if ( v24 )
        (*(void (__fastcall **)(CMulticastNamespace *))(*(_QWORD *)v24 + 8LL))(v24);
      v24 = v48;
    }
    while ( v48 );
  }
LABEL_64:
  if ( v22 == 1 )
    CMRSWLock::WriterRelease(v41);
  CDynArray<CMulticastNamespace *,CDeallocateRelease>::Clear(&v45);
}

```

## disassembly

```asm
0x180007a24  push    rbp
0x180007a26  push    rbx
0x180007a27  push    rsi
0x180007a28  push    rdi
0x180007a29  push    r12
0x180007a2b  push    r13
0x180007a2d  push    r14
0x180007a2f  push    r15
0x180007a31  mov     rbp, rsp
0x180007a34  sub     rsp, 78h
0x180007a38  mov     rbx, rcx
0x180007a3b  mov     [rbp+var_50], rcx
0x180007a3f  xorps   xmm0, xmm0
0x180007a42  lea     rcx, [rbp+var_50]; this
0x180007a46  xor     r13d, r13d
0x180007a49  xor     r15d, r15d
0x180007a4c  xor     r12d, r12d
0x180007a4f  mov     [rbp+var_28], r15
0x180007a53  xor     edi, edi
0x180007a55  mov     [rbp+var_20], r12
0x180007a59  and     [rbp+var_48], edi
0x180007a5c  xor     r14d, r14d
0x180007a5f  movdqu  xmmword ptr [rbp+var_40], xmm0
0x180007a64  mov     [rbp+arg_0], r13d
0x180007a68  mov     [rbp+var_2C], r13d
0x180007a6c  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180007a71  lea     rax, [rbx+338h]
0x180007a78  mov     rbx, [rax]
0x180007a7b  mov     [rbp+arg_18], rax
0x180007a7f  test    rbx, rbx
0x180007a82  jz      loc_180007B86
0x180007a88  mov     rax, rbx
0x180007a8b  mov     rcx, rbx
0x180007a8e  neg     rax
0x180007a91  sbb     r14, r14
0x180007a94  and     r14, rcx
0x180007a97  mov     rcx, r14
0x180007a9a  mov     rax, [r14]
0x180007a9d  mov     rax, [rax]
0x180007aa0  call    cs:__guard_dispatch_icall_fptr
0x180007aa6  xor     esi, esi
0x180007aa8  cmp     edi, r12d
0x180007aab  jnz     loc_180007B4F
0x180007ab1  lea     ecx, [rsi+20h]
0x180007ab4  mov     eax, r12d
0x180007ab7  shr     eax, 1
0x180007ab9  cmp     eax, ecx
0x180007abb  cmovb   eax, ecx
0x180007abe  lea     ecx, [r12+rax]
0x180007ac2  or      eax, 0FFFFFFFFh
0x180007ac5  cmp     ecx, r12d
0x180007ac8  cmovnb  eax, ecx
0x180007acb  sbb     edx, edx
0x180007acd  and     edx, 80070216h
0x180007ad3  mov     dword ptr [rbp+arg_8], eax
0x180007ad6  cmp     ecx, r12d
0x180007ad9  jnb     short loc_180007AEF
0x180007adb  mov     eax, edx
0x180007add  movzx   esi, dx
0x180007ae0  and     eax, 1FFF0000h
0x180007ae5  cmp     eax, 70000h
0x180007aea  cmovnz  esi, edx
0x180007aed  jmp     short loc_180007B4B
0x180007aef  mov     ecx, eax
0x180007af1  mov     eax, 8
0x180007af6  mul     rcx
0x180007af9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007b00  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007b07  cmovo   rax, rcx
0x180007b0b  mov     rcx, rax; unsigned __int64
0x180007b0e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007b13  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x180007b17  test    rax, rax
0x180007b1a  jnz     short loc_180007B21
0x180007b1c  lea     esi, [rax+8]
0x180007b1f  jmp     short loc_180007B58
0x180007b21  mov     r8d, r12d
0x180007b24  mov     rdx, r15; Src
0x180007b27  shl     r8, 3; Size
0x180007b2b  mov     rcx, rax; void *
0x180007b2e  call    memmove_0
0x180007b33  mov     rcx, r15; void *
0x180007b36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b3b  mov     r15, qword ptr [rbp+FileTime.dwLowDateTime]
0x180007b3f  mov     r12d, dword ptr [rbp+arg_8]
0x180007b43  mov     [rbp+var_28], r15
0x180007b47  mov     dword ptr [rbp+var_20], r12d
0x180007b4b  test    esi, esi
0x180007b4d  jnz     short loc_180007B58
0x180007b4f  mov     [r15+rdi*8], r14
0x180007b53  inc     edi
0x180007b55  mov     dword ptr [rbp+var_20+4], edi
0x180007b58  mov     r9d, 792h; unsigned int
0x180007b5e  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180007b65  mov     ecx, esi; unsigned int
0x180007b67  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180007b6c  test    eax, eax
0x180007b6e  jnz     short loc_180007BD5
0x180007b70  mov     rbx, [rbx+1C8h]
0x180007b77  mov     rax, rbx
0x180007b7a  mov     rcx, rbx
0x180007b7d  test    rbx, rbx
0x180007b80  jnz     loc_180007A8E
0x180007b86  mov     ebx, [rbp+var_48]
0x180007b89  test    ebx, ebx
0x180007b8b  jz      short loc_180007B9E
0x180007b8d  add     ebx, 0FFFFFFFFh
0x180007b90  mov     [rbp+var_48], ebx
0x180007b93  jnz     short loc_180007B9E
0x180007b95  mov     rcx, [rbp+var_50]; this
0x180007b99  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180007b9e  xor     esi, esi
0x180007ba0  test    edi, edi
0x180007ba2  jz      short loc_180007BBA
0x180007ba4  cmp     esi, edi
0x180007ba6  jnb     short loc_180007BAC
0x180007ba8  mov     r14, [r15+rsi*8]
0x180007bac  mov     rcx, r14; this
0x180007baf  call    ?Cleanup@CMulticastNamespace@@QEAAXXZ; CMulticastNamespace::Cleanup(void)
0x180007bb4  inc     esi
0x180007bb6  cmp     esi, edi
0x180007bb8  jb      short loc_180007BA8
0x180007bba  lea     rcx, [rbp+var_28]
0x180007bbe  call    ?Clear@?$CDynArray@PEAVCMulticastNamespace@@VCDeallocateRelease@@@@QEAAXXZ; CDynArray<CMulticastNamespace *,CDeallocateRelease>::Clear(void)
0x180007bc3  test    ebx, ebx
0x180007bc5  jnz     short loc_180007BDD
0x180007bc7  lea     rcx, [rbp+var_50]; this
0x180007bcb  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180007bd0  mov     ebx, [rbp+var_48]
0x180007bd3  jmp     short loc_180007BE2
0x180007bd5  mov     ebx, [rbp+var_48]
0x180007bd8  jmp     loc_180007E2F
0x180007bdd  inc     ebx
0x180007bdf  mov     [rbp+var_48], ebx
0x180007be2  mov     r12, [rbp+arg_18]
0x180007be6  mov     rdi, [rbp+var_40]
0x180007bea  mov     rsi, [r12]
0x180007bee  test    rsi, rsi
0x180007bf1  jz      loc_180007DE1
0x180007bf7  mov     r15, [rbp+var_40+8]
0x180007bfb  mov     [rbp+arg_8], rsi
0x180007bff  mov     rcx, rsi; this
0x180007c02  mov     r14, rsi
0x180007c05  call    ?CanDelete@CMulticastNamespace@@QEAAHXZ; CMulticastNamespace::CanDelete(void)
0x180007c0a  test    eax, eax
0x180007c0c  jz      short loc_180007C61
0x180007c0e  lea     rdx, [rbp+arg_8]
0x180007c12  mov     rcx, r12
0x180007c15  call    ?DeleteAt@?$CList@VCMulticastNamespace@@VCNoLock@@@@QEAAPEAVCMulticastNamespace@@AEAPEAX@Z; CList<CMulticastNamespace,CNoLock>::DeleteAt(void * &)
0x180007c1a  and     qword ptr [rsi+1C8h], 0
0x180007c22  mov     [rbp+var_40+8], rsi
0x180007c26  test    rdi, rdi
0x180007c29  jnz     short loc_180007C3C
0x180007c2b  and     qword ptr [rsi+1D0h], 0
0x180007c33  mov     rdi, rsi
0x180007c36  mov     [rbp+var_40], rsi
0x180007c3a  jmp     short loc_180007C4A
0x180007c3c  mov     [rsi+1D0h], r15
0x180007c43  mov     [r15+1C8h], r14
0x180007c4a  mov     rsi, [rbp+arg_8]
0x180007c4e  inc     r13d
0x180007c51  mov     [rbp+arg_0], r13d
0x180007c55  mov     r15, r14
0x180007c58  mov     [rbp+var_2C], r13d
0x180007c5c  jmp     loc_180007DD5
0x180007c61  lea     rax, [rsi+10h]
0x180007c65  xor     r12d, r12d
0x180007c68  mov     rcx, rax; lpCriticalSection
0x180007c6b  mov     [rbp+lpCriticalSection], rax
0x180007c6f  call    cs:__imp_EnterCriticalSection
0x180007c75  cmp     dword ptr [rsi+48h], 1
0x180007c79  jz      loc_180007DBC
0x180007c7f  cmp     [rsi+8Ch], r12d
0x180007c86  jnz     loc_180007DBC
0x180007c8c  cmp     [rsi+78h], r12d
0x180007c90  jnz     loc_180007DBC
0x180007c96  cmp     dword ptr [rsi+90h], 1
0x180007c9d  jz      loc_180007DBC
0x180007ca3  mov     r13, [rsi+1A8h]
0x180007caa  test    r13, r13
0x180007cad  jz      short loc_180007D0C
0x180007caf  mov     rsi, r13
0x180007cb2  mov     r13, [r13+0C08h]
0x180007cb9  mov     rcx, rsi; lpCriticalSection
0x180007cbc  call    cs:__imp_EnterCriticalSection
0x180007cc2  mov     rbx, [rsi+138h]
0x180007cc9  mov     rcx, rbx; lpCriticalSection
0x180007ccc  call    cs:__imp_EnterCriticalSection
0x180007cd2  xor     edi, edi
0x180007cd4  lock xadd [rsi+0BF0h], edi
0x180007cdc  mov     rcx, rbx; lpCriticalSection
0x180007cdf  call    cs:__imp_LeaveCriticalSection
0x180007ce5  mov     rcx, rsi; lpCriticalSection
0x180007ce8  call    cs:__imp_LeaveCriticalSection
0x180007cee  add     r12d, edi
0x180007cf1  test    r13, r13
0x180007cf4  jnz     short loc_180007CAF
0x180007cf6  mov     r13d, [rbp+var_2C]
0x180007cfa  mov     rsi, [rbp+arg_8]
0x180007cfe  mov     r15, [rbp+var_40+8]
0x180007d02  mov     rdi, [rbp+var_40]
0x180007d06  mov     [rbp+arg_0], r13d
0x180007d0a  jmp     short loc_180007D10
0x180007d0c  mov     r13d, [rbp+arg_0]
0x180007d10  mov     eax, [r14+94h]
0x180007d17  test    al, 1
0x180007d19  jz      short loc_180007D24
0x180007d1b  cmp     r12d, [r14+98h]
0x180007d22  jnb     short loc_180007DA0
0x180007d24  test    al, 2
0x180007d26  jz      loc_180007DBC
0x180007d2c  xor     eax, eax
0x180007d2e  lea     rcx, [r14+9Ch]; lpSystemTime
0x180007d35  lea     rdx, [rbp+FileTime]; lpFileTime
0x180007d39  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x180007d3d  call    cs:__imp_SystemTimeToFileTime
0x180007d43  lea     rcx, [rbp+FileTime]; struct _FILETIME *
0x180007d47  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x180007d4c  xor     ecx, ecx; struct _FILETIME *
0x180007d4e  mov     rbx, rax
0x180007d51  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x180007d56  cmp     rbx, rax
0x180007d59  ja      short loc_180007DBC
0x180007d5b  test    r12d, r12d
0x180007d5e  jnz     short loc_180007DA0
0x180007d60  mov     rcx, cs:qword_1800336E8
0x180007d67  mov     rdx, [r14+50h]; unsigned __int16 *
0x180007d6b  mov     rcx, [rcx+350h]; this
0x180007d72  call    ?RemoveNamespace@CWdsTptNamespaceStore@@QEAAKPEBG@Z; CWdsTptNamespaceStore::RemoveNamespace(ushort const *)
0x180007d77  mov     ecx, eax; unsigned int
0x180007d79  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180007d80  mov     r9d, 5E8h; unsigned int
0x180007d86  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180007d8b  lea     edx, [r12+1]; int
0x180007d90  mov     rcx, r14; this
0x180007d93  call    ?Close@CMulticastNamespace@@QEAAKH@Z; CMulticastNamespace::Close(int)
0x180007d98  mov     r9d, 5EDh
0x180007d9e  jmp     short loc_180007DAE
0x180007da0  mov     rcx, r14; this
0x180007da3  call    ?MgmtStart@CMulticastNamespace@@QEAAKXZ; CMulticastNamespace::MgmtStart(void)
0x180007da8  mov     r9d, 5F9h; unsigned int
0x180007dae  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180007db5  mov     ecx, eax; unsigned int
0x180007db7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180007dbc  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180007dc0  call    cs:__imp_LeaveCriticalSection
0x180007dc6  mov     rsi, [rsi+1C8h]
0x180007dcd  mov     r12, [rbp+arg_18]
0x180007dd1  mov     [rbp+arg_8], rsi
0x180007dd5  test    rsi, rsi
0x180007dd8  jnz     loc_180007BFF
0x180007dde  mov     ebx, [rbp+var_48]
0x180007de1  test    ebx, ebx
0x180007de3  jz      short loc_180007DF3
0x180007de5  add     ebx, 0FFFFFFFFh
0x180007de8  jnz     short loc_180007DF3
0x180007dea  mov     rcx, [rbp+var_50]; this
0x180007dee  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180007df3  test    rdi, rdi
0x180007df6  jz      short loc_180007E2F
0x180007df8  mov     [rbp+arg_8], rdi
0x180007dfc  lea     rdx, [rbp+arg_8]
0x180007e00  lea     rcx, [rbp+var_40]
0x180007e04  call    ?DeleteAt@?$CList@VCMulticastNamespace@@VCNoLock@@@@QEAAPEAVCMulticastNamespace@@AEAPEAX@Z; CList<CMulticastNamespace,CNoLock>::DeleteAt(void * &)
0x180007e09  mov     rcx, rdi; this
0x180007e0c  call    ?Shutdown@CMulticastNamespace@@QEAAKXZ; CMulticastNamespace::Shutdown(void)
0x180007e11  test    rdi, rdi
0x180007e14  jz      short loc_180007E26
0x180007e16  mov     rax, [rdi]
0x180007e19  mov     rcx, rdi
0x180007e1c  mov     rax, [rax+8]
0x180007e20  call    cs:__guard_dispatch_icall_fptr
0x180007e26  mov     rdi, [rbp+arg_8]
0x180007e2a  test    rdi, rdi
0x180007e2d  jnz     short loc_180007DFC
0x180007e2f  test    ebx, ebx
0x180007e31  jz      short loc_180007E43
0x180007e33  lea     eax, [rbx-1]
0x180007e36  test    eax, eax
0x180007e38  jnz     short loc_180007E43
0x180007e3a  mov     rcx, [rbp+var_50]; this
0x180007e3e  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180007e43  lea     rcx, [rbp+var_28]
0x180007e47  call    ?Clear@?$CDynArray@PEAVCMulticastNamespace@@VCDeallocateRelease@@@@QEAAXXZ; CDynArray<CMulticastNamespace *,CDeallocateRelease>::Clear(void)
0x180007e4c  add     rsp, 78h
0x180007e50  pop     r15
0x180007e52  pop     r14
0x180007e54  pop     r13
0x180007e56  pop     r12
0x180007e58  pop     rdi
0x180007e59  pop     rsi
0x180007e5a  pop     rbx
0x180007e5b  pop     rbp
0x180007e5c  retn
```
