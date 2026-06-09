# SrSmapipCreateReplicationGroupSetReturn

- ea: `0x18000f414`
- end: `0x18000f6a1`
- name: `SrSmapipCreateReplicationGroupSetReturn`
- size: `653`
- prototype: `__int64 __fastcall(enum _MI_Result)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000e5a8`

## callees

- `0x1800014e0`
- `0x180001e38`
- `0x18000590c`
- `0x180005cec`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000f414`
- `0x18000fc70`
- `0x18001bf54`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapipCreateReplicationGroupSetReturn(
        enum _MI_Result a1,
        unsigned int a2,
        __int64 a3,
        struct CWMIContext *a4)
{
  enum _MI_Result ReplicationGroupAndBuildReturnedInstance; // ebx
  char v9; // r14
  __int64 v10; // rcx
  __int32 v11; // eax
  int v12; // edi
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _QWORD v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  MI_Instance v18; // [rsp+40h] [rbp-C0h] BYREF
  enum _MI_Result v19; // [rsp+80h] [rbp-80h]
  char v20; // [rsp+84h] [rbp-7Ch]
  MI_Instance self; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v22[4]; // [rsp+220h] [rbp+120h] BYREF

  v17[1] = a3;
  ReplicationGroupAndBuildReturnedInstance = MI_RESULT_INVALID_PARAMETER;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  v9 = 0;
  std::wstring::wstring(v22);
  v18.ft = 0;
  memset_0(&v18.classDecl, 0, 0xC0u);
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  v10 = *((_QWORD *)a4 + 7);
  if ( v10 && *(_QWORD *)v10 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v10 + 32LL))(
            v10,
            &WSP_ReplicationGroup_CreateReplicationGroup_rtti,
            &v18);
    v12 = v11;
    if ( v11 )
    {
      ReplicationGroupAndBuildReturnedInstance = v11;
    }
    else
    {
      v13 = *((_QWORD *)a4 + 7);
      if ( v13
        && *(_QWORD *)v13
        && (ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, const MI_ClassDecl *, MI_Instance *))(*(_QWORD *)v13 + 24LL))(
                                                         v13,
                                                         &MSFT_StorageExtendedStatus_rtti,
                                                         &self)) == MI_RESULT_OK )
      {
        v19 = a1;
        v20 = 1;
        v9 = 1;
      }
      else
      {
        v9 = 0;
      }
    }
    if ( ReplicationGroupAndBuildReturnedInstance == MI_RESULT_OK )
    {
      ReplicationGroupAndBuildReturnedInstance = (unsigned int)SrSmapipQueryReplicationGroupAndBuildReturnedInstance(
                                                                 a3,
                                                                 a2,
                                                                 a4,
                                                                 v22);
      if ( ReplicationGroupAndBuildReturnedInstance == MI_RESULT_OK )
      {
        v14 = v22;
        if ( v22[3] > 7u )
          v14 = (_QWORD *)v22[0];
        v17[0] = v14;
        ReplicationGroupAndBuildReturnedInstance = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, _QWORD *, _QWORD, enum _MI_Result))v18.ft->SetElementAt)(
                                                     &v18,
                                                     (unsigned int)(ReplicationGroupAndBuildReturnedInstance + 8),
                                                     v17,
                                                     (unsigned int)(ReplicationGroupAndBuildReturnedInstance + 13),
                                                     ReplicationGroupAndBuildReturnedInstance);
        if ( ReplicationGroupAndBuildReturnedInstance == MI_RESULT_OK )
        {
          ReplicationGroupAndBuildReturnedInstance = SrSmapiPopulateStorageExtendedStatus(
                                                       (struct _MSFT_StorageExtendedStatus *)&self,
                                                       a1,
                                                       a4);
          if ( ReplicationGroupAndBuildReturnedInstance == MI_RESULT_OK )
          {
            v17[0] = &self;
            ReplicationGroupAndBuildReturnedInstance = ((unsigned int (__fastcall *)(MI_Instance *, __int64, _QWORD *, __int64, _DWORD))v18.ft->SetElementAt)(
                                                         &v18,
                                                         9,
                                                         v17,
                                                         15,
                                                         0);
            if ( ReplicationGroupAndBuildReturnedInstance == MI_RESULT_OK )
            {
              v15 = *((_QWORD *)a4 + 7);
              if ( v15 && *(_QWORD *)v15 )
                ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, MI_Instance *))(*(_QWORD *)v15 + 8LL))(
                                                             v15,
                                                             &v18);
              else
                ReplicationGroupAndBuildReturnedInstance = MI_RESULT_INVALID_PARAMETER;
            }
          }
        }
      }
    }
  }
  else
  {
    v12 = 4;
  }
  if ( v9 )
    MI_Instance_Destruct(&self);
  if ( !v12 )
    MI_Instance_Destruct(&v18);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids,
      (unsigned int)ReplicationGroupAndBuildReturnedInstance);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(a3);
  return (unsigned int)ReplicationGroupAndBuildReturnedInstance;
}

```

## disassembly

```asm
0x18000f414  push    rbp
0x18000f416  push    rbx
0x18000f417  push    rsi
0x18000f418  push    rdi
0x18000f419  push    r12
0x18000f41b  push    r13
0x18000f41d  push    r14
0x18000f41f  push    r15
0x18000f421  lea     rbp, [rsp-158h]
0x18000f429  sub     rsp, 258h
0x18000f430  mov     rax, cs:__security_cookie
0x18000f437  xor     rax, rsp
0x18000f43a  mov     [rbp+190h+var_50], rax
0x18000f441  mov     rsi, r9
0x18000f444  mov     r15, r8
0x18000f447  mov     r13d, edx
0x18000f44a  mov     r12d, ecx
0x18000f44d  mov     [rsp+290h+var_258], r8
0x18000f452  lea     rax, WPP_GLOBAL_Control
0x18000f459  mov     ebx, 4
0x18000f45e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f465  cmp     rcx, rax
0x18000f468  jz      short loc_18000F482
0x18000f46a  test    [rcx+1Ch], bl
0x18000f46d  jz      short loc_18000F482
0x18000f46f  lea     edx, [rbx+10h]
0x18000f472  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f479  mov     rcx, [rcx+10h]
0x18000f47d  call    WPP_SF_
0x18000f482  xor     r14b, r14b
0x18000f485  lea     rcx, [rbp+190h+var_70]
0x18000f48c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f491  nop
0x18000f492  mov     [rsp+290h+var_250.ft], 0
0x18000f49b  xor     edx, edx; Val
0x18000f49d  mov     r8d, 0C0h; Size
0x18000f4a3  lea     rcx, [rsp+290h+var_250.classDecl]; void *
0x18000f4a8  call    memset_0
0x18000f4ad  mov     [rbp+190h+self.ft], 0
0x18000f4b5  xor     edx, edx; Val
0x18000f4b7  mov     r8d, 108h; Size
0x18000f4bd  lea     rcx, [rbp+190h+self.classDecl]; void *
0x18000f4c1  call    memset_0
0x18000f4c6  mov     rcx, [rsi+38h]
0x18000f4ca  test    rcx, rcx
0x18000f4cd  jz      loc_18000F616
0x18000f4d3  mov     rax, [rcx]
0x18000f4d6  test    rax, rax
0x18000f4d9  jz      loc_18000F616
0x18000f4df  lea     r8, [rsp+290h+var_250]
0x18000f4e4  lea     rdx, WSP_ReplicationGroup_CreateReplicationGroup_rtti
0x18000f4eb  mov     rax, [rax+20h]
0x18000f4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4f4  mov     edi, eax
0x18000f4f6  test    eax, eax
0x18000f4f8  jnz     short loc_18000F537
0x18000f4fa  mov     rcx, [rsi+38h]
0x18000f4fe  test    rcx, rcx
0x18000f501  jz      short loc_18000F532
0x18000f503  mov     rax, [rcx]
0x18000f506  test    rax, rax
0x18000f509  jz      short loc_18000F532
0x18000f50b  lea     r8, [rbp+190h+self]
0x18000f50f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18000f516  mov     rax, [rax+18h]
0x18000f51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f51f  mov     ebx, eax
0x18000f521  test    eax, eax
0x18000f523  jnz     short loc_18000F532
0x18000f525  mov     [rbp+190h+var_210], r12d
0x18000f529  mov     [rbp+190h+var_20C], 1
0x18000f52d  mov     r14b, 1
0x18000f530  jmp     short loc_18000F539
0x18000f532  xor     r14b, r14b
0x18000f535  jmp     short loc_18000F539
0x18000f537  mov     ebx, eax
0x18000f539  test    ebx, ebx
0x18000f53b  jnz     loc_18000F618
0x18000f541  lea     r9, [rbp+190h+var_70]
0x18000f548  mov     r8, rsi
0x18000f54b  mov     edx, r13d
0x18000f54e  mov     rcx, r15
0x18000f551  call    SrSmapipQueryReplicationGroupAndBuildReturnedInstance
0x18000f556  mov     ebx, eax
0x18000f558  test    eax, eax
0x18000f55a  jnz     loc_18000F618
0x18000f560  lea     rax, [rbp+190h+var_70]
0x18000f567  cmp     [rbp+190h+var_58], 7
0x18000f56f  cmova   rax, [rbp+190h+var_70]
0x18000f577  mov     [rsp+290h+var_260], rax
0x18000f57c  mov     rax, [rsp+290h+var_250.ft]
0x18000f581  mov     [rsp+290h+var_270], ebx
0x18000f585  lea     r9d, [rbx+0Dh]
0x18000f589  lea     r8, [rsp+290h+var_260]
0x18000f58e  lea     edx, [rbx+8]
0x18000f591  lea     rcx, [rsp+290h+var_250]
0x18000f596  mov     rax, [rax+50h]
0x18000f59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f59f  mov     ebx, eax
0x18000f5a1  test    eax, eax
0x18000f5a3  jnz     short loc_18000F618
0x18000f5a5  mov     r8, rsi; struct CWMIContext *
0x18000f5a8  mov     edx, r12d; enum _MI_Result
0x18000f5ab  lea     rcx, [rbp+190h+self]; struct _MSFT_StorageExtendedStatus *
0x18000f5af  call    ?SrSmapiPopulateStorageExtendedStatus@@YA?AW4_MI_Result@@PEAU_MSFT_StorageExtendedStatus@@W41@AEAVCWMIContext@@@Z; SrSmapiPopulateStorageExtendedStatus(_MSFT_StorageExtendedStatus *,_MI_Result,CWMIContext &)
0x18000f5b4  mov     ebx, eax
0x18000f5b6  test    eax, eax
0x18000f5b8  jnz     short loc_18000F618
0x18000f5ba  lea     rax, [rbp+190h+self]
0x18000f5be  mov     [rsp+290h+var_260], rax
0x18000f5c3  mov     rax, [rsp+290h+var_250.ft]
0x18000f5c8  mov     [rsp+290h+var_270], ebx
0x18000f5cc  lea     r9d, [rbx+0Fh]
0x18000f5d0  lea     r8, [rsp+290h+var_260]
0x18000f5d5  lea     edx, [rbx+9]
0x18000f5d8  lea     rcx, [rsp+290h+var_250]
0x18000f5dd  mov     rax, [rax+50h]
0x18000f5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5e6  mov     ebx, eax
0x18000f5e8  test    eax, eax
0x18000f5ea  jnz     short loc_18000F618
0x18000f5ec  mov     rcx, [rsi+38h]
0x18000f5f0  test    rcx, rcx
0x18000f5f3  jz      short loc_18000F60F
0x18000f5f5  mov     rax, [rcx]
0x18000f5f8  test    rax, rax
0x18000f5fb  jz      short loc_18000F60F
0x18000f5fd  lea     rdx, [rsp+290h+var_250]
0x18000f602  mov     rax, [rax+8]
0x18000f606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f60b  mov     ebx, eax
0x18000f60d  jmp     short loc_18000F618
0x18000f60f  mov     ebx, 4
0x18000f614  jmp     short loc_18000F618
0x18000f616  mov     edi, ebx
0x18000f618  test    r14b, r14b
0x18000f61b  jz      short loc_18000F626
0x18000f61d  lea     rcx, [rbp+190h+self]; self
0x18000f621  call    MI_Instance_Destruct
0x18000f626  test    edi, edi
0x18000f628  jnz     short loc_18000F634
0x18000f62a  lea     rcx, [rsp+290h+var_250]; self
0x18000f62f  call    MI_Instance_Destruct
0x18000f634  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f63b  lea     rax, WPP_GLOBAL_Control
0x18000f642  cmp     rcx, rax
0x18000f645  jz      short loc_18000F666
0x18000f647  test    byte ptr [rcx+1Ch], 1
0x18000f64b  jz      short loc_18000F666
0x18000f64d  mov     edx, 15h
0x18000f652  mov     r9d, ebx
0x18000f655  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f65c  mov     rcx, [rcx+10h]
0x18000f660  call    WPP_SF_d
0x18000f665  nop
0x18000f666  lea     rcx, [rbp+190h+var_70]
0x18000f66d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f672  nop
0x18000f673  mov     rcx, r15
0x18000f676  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f67b  mov     eax, ebx
0x18000f67d  mov     rcx, [rbp+190h+var_50]
0x18000f684  xor     rcx, rsp; StackCookie
0x18000f687  call    __security_check_cookie
0x18000f68c  add     rsp, 258h
0x18000f693  pop     r15
0x18000f695  pop     r14
0x18000f697  pop     r13
0x18000f699  pop     r12
0x18000f69b  pop     rdi
0x18000f69c  pop     rsi
0x18000f69d  pop     rbx
0x18000f69e  pop     rbp
0x18000f69f  retn
```
