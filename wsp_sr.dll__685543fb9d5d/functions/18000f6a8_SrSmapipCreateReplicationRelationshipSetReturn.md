# SrSmapipCreateReplicationRelationshipSetReturn

- ea: `0x18000f6a8`
- end: `0x18000fab3`
- name: `SrSmapipCreateReplicationRelationshipSetReturn`
- size: `1035`
- prototype: `__int64 __usercall@<rax>(enum _MI_Result@<ecx>, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000e848`

## callees

- `0x1800014e0`
- `0x180001e38`
- `0x18000590c`
- `0x180005cec`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000f6a8`
- `0x18000fc70`
- `0x18001bf54`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SrSmapipCreateReplicationRelationshipSetReturn(
        enum _MI_Result a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct CWMIContext *a5)
{
  char v7; // si
  char v8; // r14
  __int64 v9; // rcx
  __int32 v10; // eax
  int v11; // ebx
  __int64 v12; // rcx
  enum _MI_Result ReplicationGroupAndBuildReturnedInstance; // edi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  char v17; // r15
  MI_Instance *p_self; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  MI_Instance v23; // [rsp+50h] [rbp-B0h] BYREF
  enum _MI_Result v24; // [rsp+90h] [rbp-70h]
  char v25; // [rsp+94h] [rbp-6Ch]
  MI_Instance self; // [rsp+1A0h] [rbp+A0h] BYREF
  MI_Instance v27; // [rsp+280h] [rbp+180h] BYREF
  MI_Instance v28; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v29[32]; // [rsp+470h] [rbp+370h] BYREF

  v20 = a4;
  v21 = a3;
  v22 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  v7 = 0;
  v8 = 0;
  v23.ft = 0;
  memset_0(&v23.classDecl, 0, 0x148u);
  v27.ft = 0;
  memset_0(&v27.classDecl, 0, 0xD8u);
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0xD8u);
  v28.ft = 0;
  memset_0(&v28.classDecl, 0, 0x108u);
  v9 = *((_QWORD *)a5 + 7);
  if ( !v9 || !*(_QWORD *)v9 )
  {
    v11 = 4;
    ReplicationGroupAndBuildReturnedInstance = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_36;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v9 + 32LL))(
          v9,
          &WSP_ReplicationGroup_CreateReplicationRelationship_rtti,
          &v23);
  v11 = v10;
  if ( v10 )
  {
    ReplicationGroupAndBuildReturnedInstance = v10;
    goto LABEL_18;
  }
  v12 = *((_QWORD *)a5 + 7);
  if ( !v12 || !*(_QWORD *)v12 )
  {
    ReplicationGroupAndBuildReturnedInstance = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_18;
  }
  ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, const MI_ClassDecl *, MI_Instance *))(*(_QWORD *)v12 + 24LL))(
                                               v12,
                                               &MSFT_ReplicationGroup_rtti,
                                               &v27);
  if ( ReplicationGroupAndBuildReturnedInstance == MI_RESULT_OK )
  {
    v14 = *((_QWORD *)a5 + 7);
    if ( v14 && *(_QWORD *)v14 )
    {
      ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, const MI_ClassDecl *, MI_Instance *))(*(_QWORD *)v14 + 24LL))(
                                                   v14,
                                                   &MSFT_ReplicationGroup_rtti,
                                                   &self);
      if ( ReplicationGroupAndBuildReturnedInstance == MI_RESULT_OK )
      {
        v24 = a1;
        v25 = 1;
        v8 = 1;
        v7 = 1;
        goto LABEL_18;
      }
    }
    else
    {
      ReplicationGroupAndBuildReturnedInstance = MI_RESULT_INVALID_PARAMETER;
    }
    v7 = 1;
  }
LABEL_18:
  if ( ReplicationGroupAndBuildReturnedInstance )
    goto LABEL_36;
  v15 = *((_QWORD *)a5 + 7);
  if ( !v15 || !*(_QWORD *)v15 )
  {
    ReplicationGroupAndBuildReturnedInstance = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_36;
  }
  ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, const MI_ClassDecl *, MI_Instance *))(*(_QWORD *)v15 + 24LL))(
                                               v15,
                                               &MSFT_StorageExtendedStatus_rtti,
                                               &v28);
  if ( ReplicationGroupAndBuildReturnedInstance )
  {
LABEL_36:
    v17 = 0;
    goto LABEL_37;
  }
  ReplicationGroupAndBuildReturnedInstance = SrSmapiPopulateStorageExtendedStatus(
                                               (struct _MSFT_StorageExtendedStatus *)&v28,
                                               a1,
                                               a5);
  if ( ReplicationGroupAndBuildReturnedInstance )
    goto LABEL_33;
  p_self = &v28;
  ReplicationGroupAndBuildReturnedInstance = ((unsigned int (__fastcall *)(MI_Instance *, __int64, MI_Instance **, __int64, _DWORD))v23.ft->SetElementAt)(
                                               &v23,
                                               16,
                                               &p_self,
                                               15,
                                               0);
  if ( ReplicationGroupAndBuildReturnedInstance )
    goto LABEL_33;
  std::wstring::wstring(v29);
  ReplicationGroupAndBuildReturnedInstance = (unsigned int)SrSmapipQueryReplicationGroupAndBuildReturnedInstance(
                                                             a3,
                                                             0,
                                                             a5,
                                                             v29);
  std::wstring::_Tidy_deallocate(v29);
  if ( ReplicationGroupAndBuildReturnedInstance )
    goto LABEL_33;
  std::wstring::wstring(v29);
  ReplicationGroupAndBuildReturnedInstance = (unsigned int)SrSmapipQueryReplicationGroupAndBuildReturnedInstance(
                                                             v20,
                                                             0,
                                                             a5,
                                                             v29);
  std::wstring::_Tidy_deallocate(v29);
  if ( ReplicationGroupAndBuildReturnedInstance )
    goto LABEL_33;
  p_self = &v27;
  ReplicationGroupAndBuildReturnedInstance = ((unsigned int (__fastcall *)(MI_Instance *, __int64, MI_Instance **, __int64, _DWORD))v23.ft->SetElementAt)(
                                               &v23,
                                               12,
                                               &p_self,
                                               15,
                                               0);
  if ( ReplicationGroupAndBuildReturnedInstance )
    goto LABEL_33;
  p_self = &self;
  ReplicationGroupAndBuildReturnedInstance = ((unsigned int (__fastcall *)(MI_Instance *, __int64, MI_Instance **, __int64, _DWORD))v23.ft->SetElementAt)(
                                               &v23,
                                               13,
                                               &p_self,
                                               15,
                                               0);
  if ( ReplicationGroupAndBuildReturnedInstance )
    goto LABEL_33;
  v16 = *((_QWORD *)a5 + 7);
  if ( !v16 || !*(_QWORD *)v16 )
  {
    ReplicationGroupAndBuildReturnedInstance = MI_RESULT_INVALID_PARAMETER;
LABEL_33:
    v17 = 1;
    goto LABEL_37;
  }
  ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, MI_Instance *))(*(_QWORD *)v16 + 8LL))(
                                               v16,
                                               &v23);
  v17 = 1;
  if ( ReplicationGroupAndBuildReturnedInstance == MI_RESULT_OK )
    ReplicationGroupAndBuildReturnedInstance = a1;
LABEL_37:
  if ( v8 )
    MI_Instance_Destruct(&self);
  if ( v7 )
    MI_Instance_Destruct(&v27);
  if ( v17 )
    MI_Instance_Destruct(&v28);
  if ( !v11 )
    MI_Instance_Destruct(&v23);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids,
      (unsigned int)ReplicationGroupAndBuildReturnedInstance);
  std::wstring::_Tidy_deallocate(a3);
  std::wstring::_Tidy_deallocate(v20);
  return (unsigned int)ReplicationGroupAndBuildReturnedInstance;
}

```

## disassembly

```asm
0x18000f6a8  mov     [rsp-8+arg_8], rbx
0x18000f6ad  push    rbp
0x18000f6ae  push    rsi
0x18000f6af  push    rdi
0x18000f6b0  push    r12
0x18000f6b2  push    r13
0x18000f6b4  push    r14
0x18000f6b6  push    r15
0x18000f6b8  lea     rbp, [rsp-3A0h]
0x18000f6c0  sub     rsp, 4A0h
0x18000f6c7  mov     rax, cs:__security_cookie
0x18000f6ce  xor     rax, rsp
0x18000f6d1  mov     [rbp+3D0h+var_40], rax
0x18000f6d8  mov     rax, r9
0x18000f6db  mov     [rsp+4D0h+var_498], rax
0x18000f6e0  mov     r13, r8
0x18000f6e3  mov     r12d, ecx
0x18000f6e6  mov     [rsp+4D0h+var_490], r8
0x18000f6eb  mov     [rsp+4D0h+var_488], rax
0x18000f6f0  mov     r15, [rbp+3D0h+arg_20]
0x18000f6f7  lea     rax, WPP_GLOBAL_Control
0x18000f6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f705  cmp     rcx, rax
0x18000f708  jz      short loc_18000F725
0x18000f70a  test    byte ptr [rcx+1Ch], 4
0x18000f70e  jz      short loc_18000F725
0x18000f710  mov     edx, 16h
0x18000f715  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f71c  mov     rcx, [rcx+10h]
0x18000f720  call    WPP_SF_
0x18000f725  xor     edi, edi
0x18000f727  mov     sil, dil
0x18000f72a  mov     r14b, dil
0x18000f72d  mov     [rsp+4D0h+var_480.ft], rdi
0x18000f732  xor     edx, edx; Val
0x18000f734  mov     r8d, 148h; Size
0x18000f73a  lea     rcx, [rsp+4D0h+var_480.classDecl]; void *
0x18000f73f  call    memset_0
0x18000f744  mov     [rbp+3D0h+var_250.ft], rdi
0x18000f74b  mov     ebx, 0D8h
0x18000f750  mov     r8d, ebx; Size
0x18000f753  xor     edx, edx; Val
0x18000f755  lea     rcx, [rbp+3D0h+var_250.classDecl]; void *
0x18000f75c  call    memset_0
0x18000f761  mov     [rbp+3D0h+self.ft], rdi
0x18000f768  mov     r8d, ebx; Size
0x18000f76b  xor     edx, edx; Val
0x18000f76d  lea     rcx, [rbp+3D0h+self.classDecl]; void *
0x18000f774  call    memset_0
0x18000f779  mov     [rbp+3D0h+var_170.ft], rdi
0x18000f780  xor     edx, edx; Val
0x18000f782  lea     r8d, [rbx+30h]; Size
0x18000f786  lea     rcx, [rbp+3D0h+var_170.classDecl]; void *
0x18000f78d  call    memset_0
0x18000f792  mov     rcx, [r15+38h]
0x18000f796  test    rcx, rcx
0x18000f799  jz      loc_18000F9F4
0x18000f79f  mov     rax, [rcx]
0x18000f7a2  test    rax, rax
0x18000f7a5  jz      loc_18000F9F4
0x18000f7ab  lea     r8, [rsp+4D0h+var_480]
0x18000f7b0  lea     rdx, WSP_ReplicationGroup_CreateReplicationRelationship_rtti
0x18000f7b7  mov     rax, [rax+20h]
0x18000f7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7c0  mov     ebx, eax
0x18000f7c2  test    eax, eax
0x18000f7c4  jnz     short loc_18000F843
0x18000f7c6  mov     rcx, [r15+38h]
0x18000f7ca  test    rcx, rcx
0x18000f7cd  jz      short loc_18000F83C
0x18000f7cf  mov     rax, [rcx]
0x18000f7d2  test    rax, rax
0x18000f7d5  jz      short loc_18000F83C
0x18000f7d7  lea     r8, [rbp+3D0h+var_250]
0x18000f7de  lea     rdx, MSFT_ReplicationGroup_rtti
0x18000f7e5  mov     rax, [rax+18h]
0x18000f7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7ee  mov     edi, eax
0x18000f7f0  test    eax, eax
0x18000f7f2  jnz     short loc_18000F845
0x18000f7f4  mov     rcx, [r15+38h]
0x18000f7f8  test    rcx, rcx
0x18000f7fb  jz      short loc_18000F832
0x18000f7fd  mov     rax, [rcx]
0x18000f800  test    rax, rax
0x18000f803  jz      short loc_18000F832
0x18000f805  lea     r8, [rbp+3D0h+self]
0x18000f80c  lea     rdx, MSFT_ReplicationGroup_rtti
0x18000f813  mov     rax, [rax+18h]
0x18000f817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f81c  mov     edi, eax
0x18000f81e  test    eax, eax
0x18000f820  jnz     short loc_18000F837
0x18000f822  mov     [rbp+3D0h+var_440], r12d
0x18000f826  mov     [rbp+3D0h+var_43C], 1
0x18000f82a  mov     r14b, 1
0x18000f82d  mov     sil, r14b
0x18000f830  jmp     short loc_18000F845
0x18000f832  mov     edi, 4
0x18000f837  mov     sil, 1
0x18000f83a  jmp     short loc_18000F845
0x18000f83c  mov     edi, 4
0x18000f841  jmp     short loc_18000F845
0x18000f843  mov     edi, eax
0x18000f845  test    edi, edi
0x18000f847  jnz     loc_18000F9FD
0x18000f84d  mov     rcx, [r15+38h]
0x18000f851  test    rcx, rcx
0x18000f854  jz      loc_18000F9ED
0x18000f85a  mov     rax, [rcx]
0x18000f85d  test    rax, rax
0x18000f860  jz      loc_18000F9ED
0x18000f866  lea     r8, [rbp+3D0h+var_170]
0x18000f86d  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18000f874  mov     rax, [rax+18h]
0x18000f878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f87d  mov     edi, eax
0x18000f87f  test    eax, eax
0x18000f881  jnz     loc_18000F9FD
0x18000f887  mov     r8, r15; struct CWMIContext *
0x18000f88a  mov     edx, r12d; enum _MI_Result
0x18000f88d  lea     rcx, [rbp+3D0h+var_170]; struct _MSFT_StorageExtendedStatus *
0x18000f894  call    ?SrSmapiPopulateStorageExtendedStatus@@YA?AW4_MI_Result@@PEAU_MSFT_StorageExtendedStatus@@W41@AEAVCWMIContext@@@Z; SrSmapiPopulateStorageExtendedStatus(_MSFT_StorageExtendedStatus *,_MI_Result,CWMIContext &)
0x18000f899  mov     edi, eax
0x18000f89b  test    eax, eax
0x18000f89d  jnz     loc_18000F9E8
0x18000f8a3  lea     rax, [rbp+3D0h+var_170]
0x18000f8aa  mov     [rsp+4D0h+var_4A0], rax
0x18000f8af  mov     rax, [rsp+4D0h+var_480.ft]
0x18000f8b4  mov     [rsp+4D0h+var_4B0], edi
0x18000f8b8  lea     r9d, [rdi+0Fh]
0x18000f8bc  lea     r8, [rsp+4D0h+var_4A0]
0x18000f8c1  lea     edx, [rdi+10h]
0x18000f8c4  lea     rcx, [rsp+4D0h+var_480]
0x18000f8c9  mov     rax, [rax+50h]
0x18000f8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8d2  mov     edi, eax
0x18000f8d4  test    eax, eax
0x18000f8d6  jnz     loc_18000F9E8
0x18000f8dc  lea     rcx, [rbp+3D0h+var_60]
0x18000f8e3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f8e8  nop
0x18000f8e9  lea     r9, [rbp+3D0h+var_60]
0x18000f8f0  mov     r8, r15
0x18000f8f3  xor     edx, edx
0x18000f8f5  mov     rcx, r13
0x18000f8f8  call    SrSmapipQueryReplicationGroupAndBuildReturnedInstance
0x18000f8fd  mov     edi, eax
0x18000f8ff  lea     rcx, [rbp+3D0h+var_60]
0x18000f906  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f90b  test    edi, edi
0x18000f90d  jnz     loc_18000F9E8
0x18000f913  lea     rcx, [rbp+3D0h+var_60]
0x18000f91a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f91f  nop
0x18000f920  lea     r9, [rbp+3D0h+var_60]
0x18000f927  mov     r8, r15
0x18000f92a  xor     edx, edx
0x18000f92c  mov     rcx, [rsp+4D0h+var_498]
0x18000f931  call    SrSmapipQueryReplicationGroupAndBuildReturnedInstance
0x18000f936  mov     edi, eax
0x18000f938  lea     rcx, [rbp+3D0h+var_60]
0x18000f93f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f944  test    edi, edi
0x18000f946  jnz     loc_18000F9E8
0x18000f94c  lea     rax, [rbp+3D0h+var_250]
0x18000f953  mov     [rsp+4D0h+var_4A0], rax
0x18000f958  mov     rax, [rsp+4D0h+var_480.ft]
0x18000f95d  mov     [rsp+4D0h+var_4B0], edi
0x18000f961  lea     r9d, [rdi+0Fh]
0x18000f965  lea     r8, [rsp+4D0h+var_4A0]
0x18000f96a  lea     edx, [rdi+0Ch]
0x18000f96d  lea     rcx, [rsp+4D0h+var_480]
0x18000f972  mov     rax, [rax+50h]
0x18000f976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f97b  mov     edi, eax
0x18000f97d  test    eax, eax
0x18000f97f  jnz     short loc_18000F9E8
0x18000f981  lea     rax, [rbp+3D0h+self]
0x18000f988  mov     [rsp+4D0h+var_4A0], rax
0x18000f98d  mov     rax, [rsp+4D0h+var_480.ft]
0x18000f992  mov     [rsp+4D0h+var_4B0], edi
0x18000f996  lea     r9d, [rdi+0Fh]
0x18000f99a  lea     r8, [rsp+4D0h+var_4A0]
0x18000f99f  lea     edx, [rdi+0Dh]
0x18000f9a2  lea     rcx, [rsp+4D0h+var_480]
0x18000f9a7  mov     rax, [rax+50h]
0x18000f9ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9b0  mov     edi, eax
0x18000f9b2  test    eax, eax
0x18000f9b4  jnz     short loc_18000F9E8
0x18000f9b6  mov     rcx, [r15+38h]
0x18000f9ba  test    rcx, rcx
0x18000f9bd  jz      short loc_18000F9E3
0x18000f9bf  mov     rax, [rcx]
0x18000f9c2  test    rax, rax
0x18000f9c5  jz      short loc_18000F9E3
0x18000f9c7  lea     rdx, [rsp+4D0h+var_480]
0x18000f9cc  mov     rax, [rax+8]
0x18000f9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d5  mov     edi, eax
0x18000f9d7  mov     r15b, 1
0x18000f9da  test    eax, eax
0x18000f9dc  jnz     short loc_18000FA00
0x18000f9de  mov     edi, r12d
0x18000f9e1  jmp     short loc_18000FA00
0x18000f9e3  mov     edi, 4
0x18000f9e8  mov     r15b, 1
0x18000f9eb  jmp     short loc_18000FA00
0x18000f9ed  mov     edi, 4
0x18000f9f2  jmp     short loc_18000F9FD
0x18000f9f4  mov     eax, 4
0x18000f9f9  mov     ebx, eax
0x18000f9fb  mov     edi, eax
0x18000f9fd  xor     r15b, r15b
0x18000fa00  test    r14b, r14b
0x18000fa03  jz      short loc_18000FA11
0x18000fa05  lea     rcx, [rbp+3D0h+self]; self
0x18000fa0c  call    MI_Instance_Destruct
0x18000fa11  test    sil, sil
0x18000fa14  jz      short loc_18000FA22
0x18000fa16  lea     rcx, [rbp+3D0h+var_250]; self
0x18000fa1d  call    MI_Instance_Destruct
0x18000fa22  test    r15b, r15b
0x18000fa25  jz      short loc_18000FA33
0x18000fa27  lea     rcx, [rbp+3D0h+var_170]; self
0x18000fa2e  call    MI_Instance_Destruct
0x18000fa33  test    ebx, ebx
0x18000fa35  jnz     short loc_18000FA41
0x18000fa37  lea     rcx, [rsp+4D0h+var_480]; self
0x18000fa3c  call    MI_Instance_Destruct
0x18000fa41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa48  lea     rax, WPP_GLOBAL_Control
0x18000fa4f  cmp     rcx, rax
0x18000fa52  jz      short loc_18000FA73
0x18000fa54  test    byte ptr [rcx+1Ch], 1
0x18000fa58  jz      short loc_18000FA73
0x18000fa5a  mov     edx, 17h
0x18000fa5f  mov     r9d, edi
0x18000fa62  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000fa69  mov     rcx, [rcx+10h]
0x18000fa6d  call    WPP_SF_d
0x18000fa72  nop
0x18000fa73  mov     rcx, r13
0x18000fa76  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fa7b  nop
0x18000fa7c  mov     rcx, [rsp+4D0h+var_498]
0x18000fa81  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fa86  mov     eax, edi
0x18000fa88  mov     rcx, [rbp+3D0h+var_40]
0x18000fa8f  xor     rcx, rsp; StackCookie
0x18000fa92  call    __security_check_cookie
0x18000fa97  mov     rbx, [rsp+4D0h+arg_8]
0x18000fa9f  add     rsp, 4A0h
0x18000faa6  pop     r15
0x18000faa8  pop     r14
0x18000faaa  pop     r13
0x18000faac  pop     r12
0x18000faae  pop     rdi
0x18000faaf  pop     rsi
0x18000fab0  pop     rbp
0x18000fab1  retn
```
