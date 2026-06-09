# SrSmapipCreateReplicationGroupSetReturn

- ea: `0x18000f440`
- end: `0x18000f6cc`
- name: `SrSmapipCreateReplicationGroupSetReturn`
- size: `652`
- prototype: `__int64 __fastcall(enum _MI_Result)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000e5d4`

## callees

- `0x1800014e0`
- `0x180001e08`
- `0x1800058d4`
- `0x180005cac`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x18000f440`
- `0x18000fc98`
- `0x18001bedc`
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
  std::wstring::wstring((__int64)v22);
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
        && (ReplicationGroupAndBuildReturnedInstance = (*(unsigned int (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v13 + 24LL))(
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
  std::wstring::_Tidy_deallocate((__int64)v22);
  std::wstring::_Tidy_deallocate(a3);
  return (unsigned int)ReplicationGroupAndBuildReturnedInstance;
}

```

## disassembly

```asm
0x18000f440  push    rbp
0x18000f442  push    rbx
0x18000f443  push    rsi
0x18000f444  push    rdi
0x18000f445  push    r12
0x18000f447  push    r13
0x18000f449  push    r14
0x18000f44b  push    r15
0x18000f44d  lea     rbp, [rsp-158h]
0x18000f455  sub     rsp, 258h
0x18000f45c  mov     rax, cs:__security_cookie
0x18000f463  xor     rax, rsp
0x18000f466  mov     [rbp+190h+var_50], rax
0x18000f46d  mov     rsi, r9
0x18000f470  mov     r15, r8
0x18000f473  mov     r13d, edx
0x18000f476  mov     r12d, ecx
0x18000f479  mov     [rsp+290h+var_258], r8
0x18000f47e  lea     rax, WPP_GLOBAL_Control
0x18000f485  mov     ebx, 4
0x18000f48a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f491  cmp     rcx, rax
0x18000f494  jz      short loc_18000F4AE
0x18000f496  test    [rcx+1Ch], bl
0x18000f499  jz      short loc_18000F4AE
0x18000f49b  lea     edx, [rbx+10h]
0x18000f49e  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f4a5  mov     rcx, [rcx+10h]
0x18000f4a9  call    WPP_SF_
0x18000f4ae  xor     r14b, r14b
0x18000f4b1  lea     rcx, [rbp+190h+var_70]
0x18000f4b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f4bd  nop
0x18000f4be  mov     [rsp+290h+var_250.ft], 0
0x18000f4c7  xor     edx, edx; Val
0x18000f4c9  mov     r8d, 0C0h; Size
0x18000f4cf  lea     rcx, [rsp+290h+var_250.classDecl]; void *
0x18000f4d4  call    memset_0
0x18000f4d9  mov     [rbp+190h+self.ft], 0
0x18000f4e1  xor     edx, edx; Val
0x18000f4e3  mov     r8d, 108h; Size
0x18000f4e9  lea     rcx, [rbp+190h+self.classDecl]; void *
0x18000f4ed  call    memset_0
0x18000f4f2  mov     rcx, [rsi+38h]
0x18000f4f6  test    rcx, rcx
0x18000f4f9  jz      loc_18000F642
0x18000f4ff  mov     rax, [rcx]
0x18000f502  test    rax, rax
0x18000f505  jz      loc_18000F642
0x18000f50b  lea     r8, [rsp+290h+var_250]
0x18000f510  lea     rdx, WSP_ReplicationGroup_CreateReplicationGroup_rtti
0x18000f517  mov     rax, [rax+20h]
0x18000f51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f520  mov     edi, eax
0x18000f522  test    eax, eax
0x18000f524  jnz     short loc_18000F563
0x18000f526  mov     rcx, [rsi+38h]
0x18000f52a  test    rcx, rcx
0x18000f52d  jz      short loc_18000F55E
0x18000f52f  mov     rax, [rcx]
0x18000f532  test    rax, rax
0x18000f535  jz      short loc_18000F55E
0x18000f537  lea     r8, [rbp+190h+self]
0x18000f53b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18000f542  mov     rax, [rax+18h]
0x18000f546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f54b  mov     ebx, eax
0x18000f54d  test    eax, eax
0x18000f54f  jnz     short loc_18000F55E
0x18000f551  mov     [rbp+190h+var_210], r12d
0x18000f555  mov     [rbp+190h+var_20C], 1
0x18000f559  mov     r14b, 1
0x18000f55c  jmp     short loc_18000F565
0x18000f55e  xor     r14b, r14b
0x18000f561  jmp     short loc_18000F565
0x18000f563  mov     ebx, eax
0x18000f565  test    ebx, ebx
0x18000f567  jnz     loc_18000F644
0x18000f56d  lea     r9, [rbp+190h+var_70]
0x18000f574  mov     r8, rsi
0x18000f577  mov     edx, r13d
0x18000f57a  mov     rcx, r15
0x18000f57d  call    SrSmapipQueryReplicationGroupAndBuildReturnedInstance
0x18000f582  mov     ebx, eax
0x18000f584  test    eax, eax
0x18000f586  jnz     loc_18000F644
0x18000f58c  lea     rax, [rbp+190h+var_70]
0x18000f593  cmp     [rbp+190h+var_58], 7
0x18000f59b  cmova   rax, [rbp+190h+var_70]
0x18000f5a3  mov     [rsp+290h+var_260], rax
0x18000f5a8  mov     rax, [rsp+290h+var_250.ft]
0x18000f5ad  mov     [rsp+290h+var_270], ebx
0x18000f5b1  lea     r9d, [rbx+0Dh]
0x18000f5b5  lea     r8, [rsp+290h+var_260]
0x18000f5ba  lea     edx, [rbx+8]
0x18000f5bd  lea     rcx, [rsp+290h+var_250]
0x18000f5c2  mov     rax, [rax+50h]
0x18000f5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5cb  mov     ebx, eax
0x18000f5cd  test    eax, eax
0x18000f5cf  jnz     short loc_18000F644
0x18000f5d1  mov     r8, rsi; struct CWMIContext *
0x18000f5d4  mov     edx, r12d; enum _MI_Result
0x18000f5d7  lea     rcx, [rbp+190h+self]; struct _MSFT_StorageExtendedStatus *
0x18000f5db  call    ?SrSmapiPopulateStorageExtendedStatus@@YA?AW4_MI_Result@@PEAU_MSFT_StorageExtendedStatus@@W41@AEAVCWMIContext@@@Z; SrSmapiPopulateStorageExtendedStatus(_MSFT_StorageExtendedStatus *,_MI_Result,CWMIContext &)
0x18000f5e0  mov     ebx, eax
0x18000f5e2  test    eax, eax
0x18000f5e4  jnz     short loc_18000F644
0x18000f5e6  lea     rax, [rbp+190h+self]
0x18000f5ea  mov     [rsp+290h+var_260], rax
0x18000f5ef  mov     rax, [rsp+290h+var_250.ft]
0x18000f5f4  mov     [rsp+290h+var_270], ebx
0x18000f5f8  lea     r9d, [rbx+0Fh]
0x18000f5fc  lea     r8, [rsp+290h+var_260]
0x18000f601  lea     edx, [rbx+9]
0x18000f604  lea     rcx, [rsp+290h+var_250]
0x18000f609  mov     rax, [rax+50h]
0x18000f60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f612  mov     ebx, eax
0x18000f614  test    eax, eax
0x18000f616  jnz     short loc_18000F644
0x18000f618  mov     rcx, [rsi+38h]
0x18000f61c  test    rcx, rcx
0x18000f61f  jz      short loc_18000F63B
0x18000f621  mov     rax, [rcx]
0x18000f624  test    rax, rax
0x18000f627  jz      short loc_18000F63B
0x18000f629  lea     rdx, [rsp+290h+var_250]
0x18000f62e  mov     rax, [rax+8]
0x18000f632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f637  mov     ebx, eax
0x18000f639  jmp     short loc_18000F644
0x18000f63b  mov     ebx, 4
0x18000f640  jmp     short loc_18000F644
0x18000f642  mov     edi, ebx
0x18000f644  test    r14b, r14b
0x18000f647  jz      short loc_18000F652
0x18000f649  lea     rcx, [rbp+190h+self]; self
0x18000f64d  call    MI_Instance_Destruct
0x18000f652  test    edi, edi
0x18000f654  jnz     short loc_18000F660
0x18000f656  lea     rcx, [rsp+290h+var_250]; self
0x18000f65b  call    MI_Instance_Destruct
0x18000f660  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f667  lea     rax, WPP_GLOBAL_Control
0x18000f66e  cmp     rcx, rax
0x18000f671  jz      short loc_18000F692
0x18000f673  test    byte ptr [rcx+1Ch], 1
0x18000f677  jz      short loc_18000F692
0x18000f679  mov     edx, 15h
0x18000f67e  mov     r9d, ebx
0x18000f681  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f688  mov     rcx, [rcx+10h]
0x18000f68c  call    WPP_SF_d
0x18000f691  nop
0x18000f692  lea     rcx, [rbp+190h+var_70]
0x18000f699  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f69e  nop
0x18000f69f  mov     rcx, r15
0x18000f6a2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f6a7  mov     eax, ebx
0x18000f6a9  mov     rcx, [rbp+190h+var_50]
0x18000f6b0  xor     rcx, rsp; StackCookie
0x18000f6b3  call    __security_check_cookie
0x18000f6b8  add     rsp, 258h
0x18000f6bf  pop     r15
0x18000f6c1  pop     r14
0x18000f6c3  pop     r13
0x18000f6c5  pop     r12
0x18000f6c7  pop     rdi
0x18000f6c8  pop     rsi
0x18000f6c9  pop     rbx
0x18000f6ca  pop     rbp
0x18000f6cb  retn
```
