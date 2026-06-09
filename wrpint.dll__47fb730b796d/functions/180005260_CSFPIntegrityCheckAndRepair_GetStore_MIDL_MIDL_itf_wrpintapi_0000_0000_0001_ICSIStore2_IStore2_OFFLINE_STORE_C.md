# CSFPIntegrityCheckAndRepair::GetStore(__MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *,ICSIStore2 * *,IStore2 * *,_OFFLINE_STORE_CREATION_PARAMETERS * *,int *,ushort * *)

- ea: `0x180005260`
- end: `0x1800054e7`
- name: `?GetStore@CSFPIntegrityCheckAndRepair@@EEAAJPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0001@@PEAPEAUICSIStore2@@PEAPEAUIStore2@@PEAPEAU_OFFLINE_STORE_CREATION_PARAMETERS@@PEAHPEAPEAG@Z`
- size: `647`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *__hidden this, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *, struct ICSIStore2 **, struct IStore2 **, struct _OFFLINE_STORE_CREATION_PARAMETERS **, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800012f4`
- `0x180001de0`
- `0x180005260`
- `0x180006344`
- `0x180010de4`
- `0x180011248`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::GetStore(
        CSFPIntegrityCheckAndRepair *this,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *a2,
        struct ICSIStore2 **a3,
        struct IStore2 **a4,
        struct _OFFLINE_STORE_CREATION_PARAMETERS **a5,
        int *a6,
        unsigned __int16 **a7)
{
  __int64 v9; // rsi
  unsigned __int16 *v10; // rdi
  __int64 v11; // rdx
  int v12; // ebx
  struct IMalloc *v13; // r8
  void *v14; // rdx
  struct _OFFLINE_STORE_CREATION_PARAMETERS *v15; // rax
  CSFPIntegrityCheckAndRepair *v16; // rcx
  unsigned __int16 *v18; // [rsp+30h] [rbp-51h] BYREF
  __int64 v19; // [rsp+38h] [rbp-49h] BYREF
  CSFPIntegrityCheckAndRepair *v20; // [rsp+40h] [rbp-41h]
  int *v21; // [rsp+48h] [rbp-39h]
  struct ICSIStore2 **v22; // [rsp+50h] [rbp-31h]
  void *Block; // [rsp+58h] [rbp-29h] BYREF
  CSFPIntegrityCheckAndRepair *v24; // [rsp+60h] [rbp-21h] BYREF
  int v25; // [rsp+68h] [rbp-19h] BYREF

  v21 = a6;
  *a3 = 0;
  v9 = 0;
  *a4 = 0;
  v10 = 0;
  v22 = a3;
  v20 = this;
  v19 = 0;
  v18 = 0;
  Block = 0;
  v24 = 0;
  if ( !a2 )
  {
    v12 = ((__int64 (__fastcall *)(_QWORD, GUID *, CSFPIntegrityCheckAndRepair **))vpfnGetSystemStore)(
            0,
            &GUID_465f1ec1_7f1d_4a85_a30b_ae1090f212db,
            &v24);
    if ( v12 < 0 )
      goto LABEL_12;
    v12 = ((__int64 (__fastcall *)(_QWORD, GUID *, struct IStore2 **))vpfnGetSystemStore)(
            0,
            &GUID_a817521b_2b43_489f_8b84_67aceeab24a8,
            a4);
    if ( v12 < 0 )
      goto LABEL_12;
    v12 = SczAllocFromSz(&v18, 2147352624);
    if ( v12 >= 0 )
    {
      v12 = SczEnsureBackslashTerminated(&v18);
      if ( v12 >= 0 )
      {
        *a7 = v18;
        goto LABEL_28;
      }
    }
LABEL_11:
    v10 = v18;
    goto LABEL_12;
  }
  *a5 = 0;
  v11 = *(_QWORD *)a2;
  v25 = 0;
  v12 = SczAllocFromSz(&v19, v11);
  if ( v12 < 0 || (v12 = SczEnsureBackslashTerminated(&v19), v12 < 0) )
  {
    v9 = v19;
    goto LABEL_12;
  }
  v12 = SczAllocFromSz(&v18, *((_QWORD *)a2 + 1));
  if ( v12 < 0 || (v12 = SczEnsureBackslashTerminated(&v18), v12 < 0) )
  {
    v9 = v19;
    goto LABEL_11;
  }
  v10 = v18;
  v9 = v19;
  v12 = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, _QWORD, __int64, unsigned __int16 *, void **))(*(_QWORD *)v20 + 48LL))(
          v20,
          0,
          v19,
          v18,
          &Block);
  if ( v12 >= 0 )
  {
    v14 = Block;
    *v21 = 1;
    v12 = ((__int64 (__fastcall *)(_QWORD, void *, GUID *, CSFPIntegrityCheckAndRepair **, int *))vpfnOpenExistingOfflineStore)(
            0,
            v14,
            &GUID_465f1ec1_7f1d_4a85_a30b_ae1090f212db,
            &v24,
            &v25);
    if ( v12 >= 0 )
    {
      v12 = ((__int64 (__fastcall *)(_QWORD, void *, GUID *, struct IStore2 **, int *))vpfnOpenExistingOfflineStore)(
              0,
              Block,
              &GUID_a817521b_2b43_489f_8b84_67aceeab24a8,
              a4,
              &v25);
      if ( v12 >= 0 )
      {
        v15 = (struct _OFFLINE_STORE_CREATION_PARAMETERS *)Block;
        *a7 = v10;
        *a5 = v15;
        Block = 0;
LABEL_28:
        v10 = 0;
        v12 = (**(__int64 (__fastcall ***)(CSFPIntegrityCheckAndRepair *, GUID *, struct ICSIStore2 **))v24)(
                v24,
                &GUID_567f1ec1_7f1d_4a85_b03a_fb1090f212ea,
                v22);
      }
    }
  }
LABEL_12:
  v16 = v24;
  if ( v24 )
    (*(void (__fastcall **)(CSFPIntegrityCheckAndRepair *))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v10 )
    operator delete(v10 - 4);
  if ( v9 )
    operator delete((void *)(v9 - 8));
  if ( Block )
  {
    CSFPIntegrityCheckAndRepair::ReleaseOfflineStoreCreationParametersInternals(
      v16,
      (struct _OFFLINE_STORE_CREATION_PARAMETERS *)Block,
      v13);
    if ( Block )
      operator delete(Block);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180005260  push    rbp
0x180005262  push    rbx
0x180005263  push    rsi
0x180005264  push    rdi
0x180005265  push    r12
0x180005267  push    r13
0x180005269  push    r14
0x18000526b  push    r15
0x18000526d  lea     rbp, [rsp-7]
0x180005272  sub     rsp, 88h
0x180005279  mov     rax, cs:__security_cookie
0x180005280  xor     rax, rsp
0x180005283  mov     [rbp+3Fh+var_50], rax
0x180005287  mov     rax, [rbp+3Fh+arg_28]
0x18000528b  mov     r13, r9
0x18000528e  mov     r12, [rbp+3Fh+arg_20]
0x180005292  mov     r14, rdx
0x180005295  mov     r15, [rbp+3Fh+arg_30]
0x180005299  mov     [rbp+3Fh+var_78], rax
0x18000529d  xor     eax, eax
0x18000529f  mov     [r8], rax
0x1800052a2  mov     esi, eax
0x1800052a4  mov     [r9], rax
0x1800052a7  mov     edi, eax
0x1800052a9  mov     [rbp+3Fh+var_70], r8
0x1800052ad  mov     [rbp+3Fh+var_80], rcx
0x1800052b1  mov     [rbp+3Fh+var_88], rax
0x1800052b5  mov     [rbp+3Fh+var_90], rax
0x1800052b9  mov     [rbp+3Fh+Block], rax
0x1800052bd  mov     [rbp+3Fh+var_60], rax
0x1800052c1  test    rdx, rdx
0x1800052c4  jz      loc_18000544D
0x1800052ca  mov     [r12], rax
0x1800052ce  lea     rcx, [rbp+3Fh+var_88]
0x1800052d2  mov     rdx, [rdx]
0x1800052d5  mov     [rbp+3Fh+var_58], eax
0x1800052d8  call    SczAllocFromSz
0x1800052dd  mov     ebx, eax
0x1800052df  test    eax, eax
0x1800052e1  js      loc_180005447
0x1800052e7  lea     rcx, [rbp+3Fh+var_88]
0x1800052eb  call    SczEnsureBackslashTerminated
0x1800052f0  mov     ebx, eax
0x1800052f2  test    eax, eax
0x1800052f4  js      loc_180005447
0x1800052fa  mov     rdx, [r14+8]
0x1800052fe  lea     rcx, [rbp+3Fh+var_90]
0x180005302  call    SczAllocFromSz
0x180005307  mov     ebx, eax
0x180005309  test    eax, eax
0x18000530b  js      loc_1800053D0
0x180005311  lea     rcx, [rbp+3Fh+var_90]
0x180005315  call    SczEnsureBackslashTerminated
0x18000531a  mov     ebx, eax
0x18000531c  test    eax, eax
0x18000531e  js      loc_1800053D0
0x180005324  mov     rcx, [rbp+3Fh+var_80]
0x180005328  lea     rdx, [rbp+3Fh+Block]
0x18000532c  mov     rdi, [rbp+3Fh+var_90]
0x180005330  mov     rsi, [rbp+3Fh+var_88]
0x180005334  mov     r9, rdi
0x180005337  mov     [rsp+0C0h+var_A0], rdx
0x18000533c  mov     r8, rsi
0x18000533f  mov     rax, [rcx]
0x180005342  xor     edx, edx
0x180005344  mov     rax, [rax+30h]
0x180005348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000534d  mov     ebx, eax
0x18000534f  test    eax, eax
0x180005351  js      loc_1800053D8
0x180005357  mov     rax, [rbp+3Fh+var_78]
0x18000535b  lea     r9, [rbp+3Fh+var_60]
0x18000535f  mov     rdx, [rbp+3Fh+Block]
0x180005363  lea     r8, _GUID_465f1ec1_7f1d_4a85_a30b_ae1090f212db
0x18000536a  xor     ecx, ecx
0x18000536c  mov     dword ptr [rax], 1
0x180005372  lea     rax, [rbp+3Fh+var_58]
0x180005376  mov     [rsp+0C0h+var_A0], rax
0x18000537b  mov     rax, cs:?vpfnOpenExistingOfflineStore@@3P6AJKPEBU_OFFLINE_STORE_CREATION_PARAMETERS@@AEBU_GUID@@PEAPEAUIUnknown@@PEAK@ZEA; long (*vpfnOpenExistingOfflineStore)(ulong,_OFFLINE_STORE_CREATION_PARAMETERS const *,_GUID const &,IUnknown * *,ulong *)
0x180005382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005387  mov     ebx, eax
0x180005389  test    eax, eax
0x18000538b  js      short loc_1800053D8
0x18000538d  mov     rdx, [rbp+3Fh+Block]
0x180005391  lea     rax, [rbp+3Fh+var_58]
0x180005395  mov     [rsp+0C0h+var_A0], rax
0x18000539a  lea     r8, _GUID_a817521b_2b43_489f_8b84_67aceeab24a8
0x1800053a1  mov     rax, cs:?vpfnOpenExistingOfflineStore@@3P6AJKPEBU_OFFLINE_STORE_CREATION_PARAMETERS@@AEBU_GUID@@PEAPEAUIUnknown@@PEAK@ZEA; long (*vpfnOpenExistingOfflineStore)(ulong,_OFFLINE_STORE_CREATION_PARAMETERS const *,_GUID const &,IUnknown * *,ulong *)
0x1800053a8  mov     r9, r13
0x1800053ab  xor     ecx, ecx
0x1800053ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b2  mov     ebx, eax
0x1800053b4  test    eax, eax
0x1800053b6  js      short loc_1800053D8
0x1800053b8  mov     rax, [rbp+3Fh+Block]
0x1800053bc  mov     [r15], rdi
0x1800053bf  mov     [r12], rax
0x1800053c3  mov     [rbp+3Fh+Block], 0
0x1800053cb  jmp     loc_1800054C4
0x1800053d0  mov     rsi, [rbp+3Fh+var_88]
0x1800053d4  mov     rdi, [rbp+3Fh+var_90]
0x1800053d8  mov     rcx, [rbp+3Fh+var_60]
0x1800053dc  test    rcx, rcx
0x1800053df  jz      short loc_1800053ED
0x1800053e1  mov     rax, [rcx]
0x1800053e4  mov     rax, [rax+10h]
0x1800053e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ed  test    rdi, rdi
0x1800053f0  jz      short loc_1800053FB
0x1800053f2  lea     rcx, [rdi-8]; Block
0x1800053f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800053fb  test    rsi, rsi
0x1800053fe  jz      short loc_180005409
0x180005400  lea     rcx, [rsi-8]; Block
0x180005404  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005409  mov     rdx, [rbp+3Fh+Block]; struct _OFFLINE_STORE_CREATION_PARAMETERS *
0x18000540d  test    rdx, rdx
0x180005410  jz      short loc_180005425
0x180005412  call    ?ReleaseOfflineStoreCreationParametersInternals@CSFPIntegrityCheckAndRepair@@AEAAJPEAU_OFFLINE_STORE_CREATION_PARAMETERS@@PEAUIMalloc@@@Z; CSFPIntegrityCheckAndRepair::ReleaseOfflineStoreCreationParametersInternals(_OFFLINE_STORE_CREATION_PARAMETERS *,IMalloc *)
0x180005417  mov     rcx, [rbp+3Fh+Block]; Block
0x18000541b  test    rcx, rcx
0x18000541e  jz      short loc_180005425
0x180005420  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005425  mov     eax, ebx
0x180005427  mov     rcx, [rbp+3Fh+var_50]
0x18000542b  xor     rcx, rsp; StackCookie
0x18000542e  call    __security_check_cookie
0x180005433  add     rsp, 88h
0x18000543a  pop     r15
0x18000543c  pop     r14
0x18000543e  pop     r13
0x180005440  pop     r12
0x180005442  pop     rdi
0x180005443  pop     rsi
0x180005444  pop     rbx
0x180005445  pop     rbp
0x180005446  retn
0x180005447  mov     rsi, [rbp+3Fh+var_88]
0x18000544b  jmp     short loc_1800053D8
0x18000544d  mov     rax, cs:?vpfnGetSystemStore@@3P6AJKAEBU_GUID@@PEAPEAUIUnknown@@@ZEA; long (*vpfnGetSystemStore)(ulong,_GUID const &,IUnknown * *)
0x180005454  lea     r8, [rbp+3Fh+var_60]
0x180005458  lea     rdx, _GUID_465f1ec1_7f1d_4a85_a30b_ae1090f212db
0x18000545f  xor     ecx, ecx
0x180005461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005466  mov     ebx, eax
0x180005468  test    eax, eax
0x18000546a  js      loc_1800053D8
0x180005470  mov     rax, cs:?vpfnGetSystemStore@@3P6AJKAEBU_GUID@@PEAPEAUIUnknown@@@ZEA; long (*vpfnGetSystemStore)(ulong,_GUID const &,IUnknown * *)
0x180005477  lea     rdx, _GUID_a817521b_2b43_489f_8b84_67aceeab24a8
0x18000547e  mov     r8, r13
0x180005481  xor     ecx, ecx
0x180005483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005488  mov     ebx, eax
0x18000548a  test    eax, eax
0x18000548c  js      loc_1800053D8
0x180005492  mov     edx, 7FFE0030h
0x180005497  lea     rcx, [rbp+3Fh+var_90]
0x18000549b  call    SczAllocFromSz
0x1800054a0  mov     ebx, eax
0x1800054a2  test    eax, eax
0x1800054a4  js      loc_1800053D4
0x1800054aa  lea     rcx, [rbp+3Fh+var_90]
0x1800054ae  call    SczEnsureBackslashTerminated
0x1800054b3  mov     ebx, eax
0x1800054b5  test    eax, eax
0x1800054b7  js      loc_1800053D4
0x1800054bd  mov     rax, [rbp+3Fh+var_90]
0x1800054c1  mov     [r15], rax
0x1800054c4  xor     edi, edi
0x1800054c6  mov     rcx, [rbp+3Fh+var_60]
0x1800054ca  lea     rdx, _GUID_567f1ec1_7f1d_4a85_b03a_fb1090f212ea
0x1800054d1  mov     r8, [rbp+3Fh+var_70]
0x1800054d5  mov     rax, [rcx]
0x1800054d8  mov     rax, [rax]
0x1800054db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e0  mov     ebx, eax
0x1800054e2  jmp     loc_1800053D8
```
