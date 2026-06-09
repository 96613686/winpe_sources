# SrSmapipCreateReplicationRelationshipSetReturn

- ea: `0x18000f6d4`
- end: `0x18000fade`
- name: `SrSmapipCreateReplicationRelationshipSetReturn`
- size: `1034`
- prototype: `__int64 __usercall@<rax>(enum _MI_Result@<ecx>, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000e874`

## callees

- `0x1800014e0`
- `0x180001e08`
- `0x1800058d4`
- `0x180005cac`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x18000f6d4`
- `0x18000fc98`
- `0x18001bedc`
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
  ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v12 + 24LL))(
                                               v12,
                                               &MSFT_ReplicationGroup_rtti,
                                               &v27);
  if ( ReplicationGroupAndBuildReturnedInstance == MI_RESULT_OK )
  {
    v14 = *((_QWORD *)a5 + 7);
    if ( v14 && *(_QWORD *)v14 )
    {
      ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v14 + 24LL))(
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
  ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v15 + 24LL))(
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
  std::wstring::wstring((__int64)v29);
  ReplicationGroupAndBuildReturnedInstance = (unsigned int)SrSmapipQueryReplicationGroupAndBuildReturnedInstance(
                                                             a3,
                                                             0,
                                                             a5,
                                                             v29);
  std::wstring::_Tidy_deallocate((__int64)v29);
  if ( ReplicationGroupAndBuildReturnedInstance )
    goto LABEL_33;
  std::wstring::wstring((__int64)v29);
  ReplicationGroupAndBuildReturnedInstance = (unsigned int)SrSmapipQueryReplicationGroupAndBuildReturnedInstance(
                                                             v20,
                                                             0,
                                                             a5,
                                                             v29);
  std::wstring::_Tidy_deallocate((__int64)v29);
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
0x18000f6d4  mov     [rsp-8+arg_8], rbx
0x18000f6d9  push    rbp
0x18000f6da  push    rsi
0x18000f6db  push    rdi
0x18000f6dc  push    r12
0x18000f6de  push    r13
0x18000f6e0  push    r14
0x18000f6e2  push    r15
0x18000f6e4  lea     rbp, [rsp-3A0h]
0x18000f6ec  sub     rsp, 4A0h
0x18000f6f3  mov     rax, cs:__security_cookie
0x18000f6fa  xor     rax, rsp
0x18000f6fd  mov     [rbp+3D0h+var_40], rax
0x18000f704  mov     rax, r9
0x18000f707  mov     [rsp+4D0h+var_498], rax
0x18000f70c  mov     r13, r8
0x18000f70f  mov     r12d, ecx
0x18000f712  mov     [rsp+4D0h+var_490], r8
0x18000f717  mov     [rsp+4D0h+var_488], rax
0x18000f71c  mov     r15, [rbp+3D0h+arg_20]
0x18000f723  lea     rax, WPP_GLOBAL_Control
0x18000f72a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f731  cmp     rcx, rax
0x18000f734  jz      short loc_18000F751
0x18000f736  test    byte ptr [rcx+1Ch], 4
0x18000f73a  jz      short loc_18000F751
0x18000f73c  mov     edx, 16h
0x18000f741  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f748  mov     rcx, [rcx+10h]
0x18000f74c  call    WPP_SF_
0x18000f751  xor     edi, edi
0x18000f753  mov     sil, dil
0x18000f756  mov     r14b, dil
0x18000f759  mov     [rsp+4D0h+var_480.ft], rdi
0x18000f75e  xor     edx, edx; Val
0x18000f760  mov     r8d, 148h; Size
0x18000f766  lea     rcx, [rsp+4D0h+var_480.classDecl]; void *
0x18000f76b  call    memset_0
0x18000f770  mov     [rbp+3D0h+var_250.ft], rdi
0x18000f777  mov     ebx, 0D8h
0x18000f77c  mov     r8d, ebx; Size
0x18000f77f  xor     edx, edx; Val
0x18000f781  lea     rcx, [rbp+3D0h+var_250.classDecl]; void *
0x18000f788  call    memset_0
0x18000f78d  mov     [rbp+3D0h+self.ft], rdi
0x18000f794  mov     r8d, ebx; Size
0x18000f797  xor     edx, edx; Val
0x18000f799  lea     rcx, [rbp+3D0h+self.classDecl]; void *
0x18000f7a0  call    memset_0
0x18000f7a5  mov     [rbp+3D0h+var_170.ft], rdi
0x18000f7ac  xor     edx, edx; Val
0x18000f7ae  lea     r8d, [rbx+30h]; Size
0x18000f7b2  lea     rcx, [rbp+3D0h+var_170.classDecl]; void *
0x18000f7b9  call    memset_0
0x18000f7be  mov     rcx, [r15+38h]
0x18000f7c2  test    rcx, rcx
0x18000f7c5  jz      loc_18000FA20
0x18000f7cb  mov     rax, [rcx]
0x18000f7ce  test    rax, rax
0x18000f7d1  jz      loc_18000FA20
0x18000f7d7  lea     r8, [rsp+4D0h+var_480]
0x18000f7dc  lea     rdx, WSP_ReplicationGroup_CreateReplicationRelationship_rtti
0x18000f7e3  mov     rax, [rax+20h]
0x18000f7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7ec  mov     ebx, eax
0x18000f7ee  test    eax, eax
0x18000f7f0  jnz     short loc_18000F86F
0x18000f7f2  mov     rcx, [r15+38h]
0x18000f7f6  test    rcx, rcx
0x18000f7f9  jz      short loc_18000F868
0x18000f7fb  mov     rax, [rcx]
0x18000f7fe  test    rax, rax
0x18000f801  jz      short loc_18000F868
0x18000f803  lea     r8, [rbp+3D0h+var_250]
0x18000f80a  lea     rdx, MSFT_ReplicationGroup_rtti
0x18000f811  mov     rax, [rax+18h]
0x18000f815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f81a  mov     edi, eax
0x18000f81c  test    eax, eax
0x18000f81e  jnz     short loc_18000F871
0x18000f820  mov     rcx, [r15+38h]
0x18000f824  test    rcx, rcx
0x18000f827  jz      short loc_18000F85E
0x18000f829  mov     rax, [rcx]
0x18000f82c  test    rax, rax
0x18000f82f  jz      short loc_18000F85E
0x18000f831  lea     r8, [rbp+3D0h+self]
0x18000f838  lea     rdx, MSFT_ReplicationGroup_rtti
0x18000f83f  mov     rax, [rax+18h]
0x18000f843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f848  mov     edi, eax
0x18000f84a  test    eax, eax
0x18000f84c  jnz     short loc_18000F863
0x18000f84e  mov     [rbp+3D0h+var_440], r12d
0x18000f852  mov     [rbp+3D0h+var_43C], 1
0x18000f856  mov     r14b, 1
0x18000f859  mov     sil, r14b
0x18000f85c  jmp     short loc_18000F871
0x18000f85e  mov     edi, 4
0x18000f863  mov     sil, 1
0x18000f866  jmp     short loc_18000F871
0x18000f868  mov     edi, 4
0x18000f86d  jmp     short loc_18000F871
0x18000f86f  mov     edi, eax
0x18000f871  test    edi, edi
0x18000f873  jnz     loc_18000FA29
0x18000f879  mov     rcx, [r15+38h]
0x18000f87d  test    rcx, rcx
0x18000f880  jz      loc_18000FA19
0x18000f886  mov     rax, [rcx]
0x18000f889  test    rax, rax
0x18000f88c  jz      loc_18000FA19
0x18000f892  lea     r8, [rbp+3D0h+var_170]
0x18000f899  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18000f8a0  mov     rax, [rax+18h]
0x18000f8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8a9  mov     edi, eax
0x18000f8ab  test    eax, eax
0x18000f8ad  jnz     loc_18000FA29
0x18000f8b3  mov     r8, r15; struct CWMIContext *
0x18000f8b6  mov     edx, r12d; enum _MI_Result
0x18000f8b9  lea     rcx, [rbp+3D0h+var_170]; struct _MSFT_StorageExtendedStatus *
0x18000f8c0  call    ?SrSmapiPopulateStorageExtendedStatus@@YA?AW4_MI_Result@@PEAU_MSFT_StorageExtendedStatus@@W41@AEAVCWMIContext@@@Z; SrSmapiPopulateStorageExtendedStatus(_MSFT_StorageExtendedStatus *,_MI_Result,CWMIContext &)
0x18000f8c5  mov     edi, eax
0x18000f8c7  test    eax, eax
0x18000f8c9  jnz     loc_18000FA14
0x18000f8cf  lea     rax, [rbp+3D0h+var_170]
0x18000f8d6  mov     [rsp+4D0h+var_4A0], rax
0x18000f8db  mov     rax, [rsp+4D0h+var_480.ft]
0x18000f8e0  mov     [rsp+4D0h+var_4B0], edi
0x18000f8e4  lea     r9d, [rdi+0Fh]
0x18000f8e8  lea     r8, [rsp+4D0h+var_4A0]
0x18000f8ed  lea     edx, [rdi+10h]
0x18000f8f0  lea     rcx, [rsp+4D0h+var_480]
0x18000f8f5  mov     rax, [rax+50h]
0x18000f8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8fe  mov     edi, eax
0x18000f900  test    eax, eax
0x18000f902  jnz     loc_18000FA14
0x18000f908  lea     rcx, [rbp+3D0h+var_60]
0x18000f90f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f914  nop
0x18000f915  lea     r9, [rbp+3D0h+var_60]
0x18000f91c  mov     r8, r15
0x18000f91f  xor     edx, edx
0x18000f921  mov     rcx, r13
0x18000f924  call    SrSmapipQueryReplicationGroupAndBuildReturnedInstance
0x18000f929  mov     edi, eax
0x18000f92b  lea     rcx, [rbp+3D0h+var_60]
0x18000f932  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f937  test    edi, edi
0x18000f939  jnz     loc_18000FA14
0x18000f93f  lea     rcx, [rbp+3D0h+var_60]
0x18000f946  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f94b  nop
0x18000f94c  lea     r9, [rbp+3D0h+var_60]
0x18000f953  mov     r8, r15
0x18000f956  xor     edx, edx
0x18000f958  mov     rcx, [rsp+4D0h+var_498]
0x18000f95d  call    SrSmapipQueryReplicationGroupAndBuildReturnedInstance
0x18000f962  mov     edi, eax
0x18000f964  lea     rcx, [rbp+3D0h+var_60]
0x18000f96b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f970  test    edi, edi
0x18000f972  jnz     loc_18000FA14
0x18000f978  lea     rax, [rbp+3D0h+var_250]
0x18000f97f  mov     [rsp+4D0h+var_4A0], rax
0x18000f984  mov     rax, [rsp+4D0h+var_480.ft]
0x18000f989  mov     [rsp+4D0h+var_4B0], edi
0x18000f98d  lea     r9d, [rdi+0Fh]
0x18000f991  lea     r8, [rsp+4D0h+var_4A0]
0x18000f996  lea     edx, [rdi+0Ch]
0x18000f999  lea     rcx, [rsp+4D0h+var_480]
0x18000f99e  mov     rax, [rax+50h]
0x18000f9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9a7  mov     edi, eax
0x18000f9a9  test    eax, eax
0x18000f9ab  jnz     short loc_18000FA14
0x18000f9ad  lea     rax, [rbp+3D0h+self]
0x18000f9b4  mov     [rsp+4D0h+var_4A0], rax
0x18000f9b9  mov     rax, [rsp+4D0h+var_480.ft]
0x18000f9be  mov     [rsp+4D0h+var_4B0], edi
0x18000f9c2  lea     r9d, [rdi+0Fh]
0x18000f9c6  lea     r8, [rsp+4D0h+var_4A0]
0x18000f9cb  lea     edx, [rdi+0Dh]
0x18000f9ce  lea     rcx, [rsp+4D0h+var_480]
0x18000f9d3  mov     rax, [rax+50h]
0x18000f9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9dc  mov     edi, eax
0x18000f9de  test    eax, eax
0x18000f9e0  jnz     short loc_18000FA14
0x18000f9e2  mov     rcx, [r15+38h]
0x18000f9e6  test    rcx, rcx
0x18000f9e9  jz      short loc_18000FA0F
0x18000f9eb  mov     rax, [rcx]
0x18000f9ee  test    rax, rax
0x18000f9f1  jz      short loc_18000FA0F
0x18000f9f3  lea     rdx, [rsp+4D0h+var_480]
0x18000f9f8  mov     rax, [rax+8]
0x18000f9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa01  mov     edi, eax
0x18000fa03  mov     r15b, 1
0x18000fa06  test    eax, eax
0x18000fa08  jnz     short loc_18000FA2C
0x18000fa0a  mov     edi, r12d
0x18000fa0d  jmp     short loc_18000FA2C
0x18000fa0f  mov     edi, 4
0x18000fa14  mov     r15b, 1
0x18000fa17  jmp     short loc_18000FA2C
0x18000fa19  mov     edi, 4
0x18000fa1e  jmp     short loc_18000FA29
0x18000fa20  mov     eax, 4
0x18000fa25  mov     ebx, eax
0x18000fa27  mov     edi, eax
0x18000fa29  xor     r15b, r15b
0x18000fa2c  test    r14b, r14b
0x18000fa2f  jz      short loc_18000FA3D
0x18000fa31  lea     rcx, [rbp+3D0h+self]; self
0x18000fa38  call    MI_Instance_Destruct
0x18000fa3d  test    sil, sil
0x18000fa40  jz      short loc_18000FA4E
0x18000fa42  lea     rcx, [rbp+3D0h+var_250]; self
0x18000fa49  call    MI_Instance_Destruct
0x18000fa4e  test    r15b, r15b
0x18000fa51  jz      short loc_18000FA5F
0x18000fa53  lea     rcx, [rbp+3D0h+var_170]; self
0x18000fa5a  call    MI_Instance_Destruct
0x18000fa5f  test    ebx, ebx
0x18000fa61  jnz     short loc_18000FA6D
0x18000fa63  lea     rcx, [rsp+4D0h+var_480]; self
0x18000fa68  call    MI_Instance_Destruct
0x18000fa6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa74  lea     rax, WPP_GLOBAL_Control
0x18000fa7b  cmp     rcx, rax
0x18000fa7e  jz      short loc_18000FA9F
0x18000fa80  test    byte ptr [rcx+1Ch], 1
0x18000fa84  jz      short loc_18000FA9F
0x18000fa86  mov     edx, 17h
0x18000fa8b  mov     r9d, edi
0x18000fa8e  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000fa95  mov     rcx, [rcx+10h]
0x18000fa99  call    WPP_SF_d
0x18000fa9e  nop
0x18000fa9f  mov     rcx, r13
0x18000faa2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000faa7  nop
0x18000faa8  mov     rcx, [rsp+4D0h+var_498]
0x18000faad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fab2  mov     eax, edi
0x18000fab4  mov     rcx, [rbp+3D0h+var_40]
0x18000fabb  xor     rcx, rsp; StackCookie
0x18000fabe  call    __security_check_cookie
0x18000fac3  mov     rbx, [rsp+4D0h+arg_8]
0x18000facb  add     rsp, 4A0h
0x18000fad2  pop     r15
0x18000fad4  pop     r14
0x18000fad6  pop     r13
0x18000fad8  pop     r12
0x18000fada  pop     rdi
0x18000fadb  pop     rsi
0x18000fadc  pop     rbp
0x18000fadd  retn
```
