# SrSmapiCreateReplicaSetReturn

- ea: `0x180009554`
- end: `0x18000983d`
- name: `SrSmapiCreateReplicaSetReturn`
- size: `745`
- prototype: `__int64 __usercall@<rax>(enum _MI_Result@<ecx>, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000934c`

## callees

- `0x1800014e0`
- `0x180001e08`
- `0x180005cac`
- `0x180006778`
- `0x1800067a0`
- `0x180009554`
- `0x1800150f0`
- `0x18001bedc`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicaSetReturn(
        enum _MI_Result a1,
        MI_Instance *a2,
        _QWORD *a3,
        __int64 a4,
        struct CWMIContext *a5)
{
  enum _MI_Result v7; // edi
  bool v8; // r15
  char v9; // si
  __int64 v10; // rcx
  enum _MI_Result ReplicaPeerFromReplicationGroup; // eax
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  MI_Instance *p_self; // [rsp+30h] [rbp-D0h] BYREF
  MI_Instance *v18; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v19; // [rsp+40h] [rbp-C0h]
  MI_Instance v20; // [rsp+50h] [rbp-B0h] BYREF
  enum _MI_Result v21; // [rsp+90h] [rbp-70h]
  char v22; // [rsp+94h] [rbp-6Ch]
  MI_Instance self; // [rsp+130h] [rbp+30h] BYREF
  MI_Instance v24; // [rsp+240h] [rbp+140h] BYREF

  v19 = a3;
  p_self = a2;
  v7 = MI_RESULT_INVALID_PARAMETER;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  self.ft = 0;
  v8 = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  v24.ft = 0;
  v9 = 0;
  memset_0(&v24.classDecl, 0, 0x108u);
  v20.ft = 0;
  memset_0(&v20.classDecl, 0, 0xD0u);
  v10 = *((_QWORD *)a5 + 7);
  if ( !v10 || !*(_QWORD *)v10 )
  {
    v12 = 4;
    ReplicaPeerFromReplicationGroup = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_32;
  }
  ReplicaPeerFromReplicationGroup = (*(unsigned int (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v10 + 32LL))(
                                      v10,
                                      &WSP_ReplicationGroup_CreateReplica_rtti,
                                      &v20);
  v12 = ReplicaPeerFromReplicationGroup;
  if ( ReplicaPeerFromReplicationGroup )
    goto LABEL_32;
  v13 = *((_QWORD *)a5 + 7);
  if ( !v13 || !*(_QWORD *)v13 )
  {
    ReplicaPeerFromReplicationGroup = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_24;
  }
  ReplicaPeerFromReplicationGroup = (*(unsigned int (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v13 + 24LL))(
                                      v13,
                                      &MSFT_StorageExtendedStatus_rtti,
                                      &v24);
  if ( ReplicaPeerFromReplicationGroup )
  {
LABEL_32:
    v7 = ReplicaPeerFromReplicationGroup;
    goto LABEL_33;
  }
  ReplicaPeerFromReplicationGroup = SrSmapiPopulateStorageExtendedStatus(
                                      (struct _MSFT_StorageExtendedStatus *)&v24,
                                      a1,
                                      a5);
  if ( ReplicaPeerFromReplicationGroup == MI_RESULT_OK )
  {
    v18 = &v24;
    ReplicaPeerFromReplicationGroup = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, MI_Instance **, _QWORD, int))v20.ft->SetElementAt)(
                                        &v20,
                                        (unsigned int)(v12 + 10),
                                        &v18,
                                        (unsigned int)(v12 + 15),
                                        v12);
    if ( ReplicaPeerFromReplicationGroup == MI_RESULT_OK )
    {
      if ( a1
        || !a4
        || ((v14 = *((_QWORD *)a5 + 7)) == 0 || !*(_QWORD *)v14
          ? (ReplicaPeerFromReplicationGroup = MI_RESULT_INVALID_PARAMETER)
          : (ReplicaPeerFromReplicationGroup = (*(unsigned int (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v14 + 24LL))(
                                                 v14,
                                                 &WSP_ReplicaPeer_rtti,
                                                 &self)),
            (v8 = ReplicaPeerFromReplicationGroup == MI_RESULT_OK, ReplicaPeerFromReplicationGroup == MI_RESULT_OK)
         && (ReplicaPeerFromReplicationGroup = (unsigned int)SrSmapiCreateReplicaPeerFromReplicationGroup(
                                                               a4,
                                                               p_self,
                                                               v19,
                                                               (__int64)&self)) == MI_RESULT_OK
         && (p_self = &self,
             (ReplicaPeerFromReplicationGroup = ((unsigned int (__fastcall *)(MI_Instance *, __int64, MI_Instance **, _QWORD, _DWORD))v20.ft->SetElementAt)(
                                                  &v20,
                                                  8,
                                                  &p_self,
                                                  (unsigned int)(v12 + 15),
                                                  0)) == MI_RESULT_OK)) )
      {
        v21 = a1;
        v22 = 1;
      }
    }
  }
  v9 = 1;
LABEL_24:
  if ( ReplicaPeerFromReplicationGroup )
    goto LABEL_32;
  v15 = *((_QWORD *)a5 + 7);
  if ( v15 && *(_QWORD *)v15 )
    v7 = (*(unsigned int (__fastcall **)(__int64, MI_Instance *))(*(_QWORD *)v15 + 8LL))(v15, &v20);
  if ( v7 == MI_RESULT_OK )
    v7 = a1;
LABEL_33:
  if ( v8 )
    MI_Instance_Destruct(&self);
  if ( v9 )
    MI_Instance_Destruct(&v24);
  if ( !v12 )
    MI_Instance_Destruct(&v20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009554  push    rbp
0x180009556  push    rbx
0x180009557  push    rsi
0x180009558  push    rdi
0x180009559  push    r12
0x18000955b  push    r13
0x18000955d  push    r14
0x18000955f  push    r15
0x180009561  lea     rbp, [rsp-268h]
0x180009569  sub     rsp, 368h
0x180009570  mov     rax, cs:__security_cookie
0x180009577  xor     rax, rsp
0x18000957a  mov     [rbp+2A0h+var_50], rax
0x180009581  mov     r14, [rbp+2A0h+arg_20]
0x180009588  mov     r13, r9
0x18000958b  mov     [rsp+3A0h+var_360], r8
0x180009590  mov     r12d, ecx
0x180009593  mov     [rsp+3A0h+var_370], rdx
0x180009598  mov     rcx, cs:WPP_GLOBAL_Control
0x18000959f  lea     rax, WPP_GLOBAL_Control
0x1800095a6  mov     edi, 4
0x1800095ab  cmp     rcx, rax
0x1800095ae  jz      short loc_1800095C9
0x1800095b0  test    [rcx+1Ch], dil
0x1800095b4  jz      short loc_1800095C9
0x1800095b6  mov     rcx, [rcx+10h]
0x1800095ba  lea     edx, [rdi+31h]
0x1800095bd  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x1800095c4  call    WPP_SF_
0x1800095c9  mov     ebx, 108h
0x1800095ce  mov     [rbp+2A0h+self.ft], 0
0x1800095d6  mov     r8d, ebx; Size
0x1800095d9  lea     rcx, [rbp+2A0h+self.classDecl]; void *
0x1800095dd  xor     edx, edx; Val
0x1800095df  xor     r15b, r15b
0x1800095e2  call    memset_0
0x1800095e7  mov     r8d, ebx; Size
0x1800095ea  mov     [rbp+2A0h+var_160.ft], 0
0x1800095f5  xor     edx, edx; Val
0x1800095f7  lea     rcx, [rbp+2A0h+var_160.classDecl]; void *
0x1800095fe  xor     sil, sil
0x180009601  call    memset_0
0x180009606  xor     edx, edx; Val
0x180009608  mov     [rsp+3A0h+var_350.ft], 0
0x180009611  lea     r8d, [rbx-38h]; Size
0x180009615  lea     rcx, [rsp+3A0h+var_350.classDecl]; void *
0x18000961a  call    memset_0
0x18000961f  mov     rcx, [r14+38h]
0x180009623  test    rcx, rcx
0x180009626  jz      loc_1800097B4
0x18000962c  mov     rax, [rcx]
0x18000962f  test    rax, rax
0x180009632  jz      loc_1800097B4
0x180009638  mov     rax, [rax+20h]
0x18000963c  lea     r8, [rsp+3A0h+var_350]
0x180009641  lea     rdx, WSP_ReplicationGroup_CreateReplica_rtti
0x180009648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000964d  mov     ebx, eax
0x18000964f  test    eax, eax
0x180009651  jnz     loc_1800097B8
0x180009657  mov     rcx, [r14+38h]
0x18000965b  test    rcx, rcx
0x18000965e  jz      loc_180009785
0x180009664  mov     rax, [rcx]
0x180009667  test    rax, rax
0x18000966a  jz      loc_180009785
0x180009670  mov     rax, [rax+18h]
0x180009674  lea     r8, [rbp+2A0h+var_160]
0x18000967b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180009682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009687  test    eax, eax
0x180009689  jnz     loc_1800097B8
0x18000968f  mov     r8, r14; struct CWMIContext *
0x180009692  lea     rcx, [rbp+2A0h+var_160]; struct _MSFT_StorageExtendedStatus *
0x180009699  mov     edx, r12d; enum _MI_Result
0x18000969c  call    ?SrSmapiPopulateStorageExtendedStatus@@YA?AW4_MI_Result@@PEAU_MSFT_StorageExtendedStatus@@W41@AEAVCWMIContext@@@Z; SrSmapiPopulateStorageExtendedStatus(_MSFT_StorageExtendedStatus *,_MI_Result,CWMIContext &)
0x1800096a1  test    eax, eax
0x1800096a3  jnz     loc_180009776
0x1800096a9  lea     rax, [rbp+2A0h+var_160]
0x1800096b0  mov     [rsp+3A0h+var_380], ebx
0x1800096b4  mov     [rsp+3A0h+var_368], rax
0x1800096b9  lea     esi, [rbx+0Fh]
0x1800096bc  mov     rax, [rsp+3A0h+var_350.ft]
0x1800096c1  lea     r8, [rsp+3A0h+var_368]
0x1800096c6  mov     r9d, esi
0x1800096c9  lea     edx, [rbx+0Ah]
0x1800096cc  lea     rcx, [rsp+3A0h+var_350]
0x1800096d1  mov     rax, [rax+50h]
0x1800096d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096da  test    eax, eax
0x1800096dc  jnz     loc_180009776
0x1800096e2  test    r12d, r12d
0x1800096e5  jnz     loc_18000977B
0x1800096eb  test    r13, r13
0x1800096ee  jz      loc_18000977B
0x1800096f4  mov     rcx, [r14+38h]
0x1800096f8  test    rcx, rcx
0x1800096fb  jz      short loc_18000971B
0x1800096fd  mov     rax, [rcx]
0x180009700  test    rax, rax
0x180009703  jz      short loc_18000971B
0x180009705  mov     rax, [rax+18h]
0x180009709  lea     r8, [rbp+2A0h+self]
0x18000970d  lea     rdx, WSP_ReplicaPeer_rtti
0x180009714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009719  jmp     short loc_18000971D
0x18000971b  mov     eax, edi
0x18000971d  test    eax, eax
0x18000971f  setz    r15b
0x180009723  test    eax, eax
0x180009725  jnz     short loc_180009776
0x180009727  mov     r8, [rsp+3A0h+var_360]
0x18000972c  lea     r9, [rbp+2A0h+self]
0x180009730  mov     rdx, [rsp+3A0h+var_370]
0x180009735  mov     rcx, r13
0x180009738  call    ?SrSmapiCreateReplicaPeerFromReplicationGroup@@YA?AW4_MI_Result@@PEBU_MSFT_ReplicaPeer@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1PEAU_WSP_ReplicaPeer@@@Z; SrSmapiCreateReplicaPeerFromReplicationGroup(_MSFT_ReplicaPeer const *,std::wstring const &,std::wstring const &,_WSP_ReplicaPeer *)
0x18000973d  test    eax, eax
0x18000973f  jnz     short loc_180009776
0x180009741  lea     rax, [rbp+2A0h+self]
0x180009745  mov     [rsp+3A0h+var_380], 0
0x18000974d  mov     [rsp+3A0h+var_370], rax
0x180009752  lea     r8, [rsp+3A0h+var_370]
0x180009757  mov     rax, [rsp+3A0h+var_350.ft]
0x18000975c  lea     rcx, [rsp+3A0h+var_350]
0x180009761  mov     r9d, esi
0x180009764  mov     edx, 8
0x180009769  mov     rax, [rax+50h]
0x18000976d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009772  test    eax, eax
0x180009774  jz      short loc_18000977B
0x180009776  mov     sil, 1
0x180009779  jmp     short loc_180009787
0x18000977b  mov     [rbp+2A0h+var_310], r12d
0x18000977f  mov     [rbp+2A0h+var_30C], 1
0x180009783  jmp     short loc_180009776
0x180009785  mov     eax, edi
0x180009787  test    eax, eax
0x180009789  jnz     short loc_1800097B8
0x18000978b  mov     rcx, [r14+38h]
0x18000978f  test    rcx, rcx
0x180009792  jz      short loc_1800097AC
0x180009794  mov     rax, [rcx]
0x180009797  test    rax, rax
0x18000979a  jz      short loc_1800097AC
0x18000979c  mov     rax, [rax+8]
0x1800097a0  lea     rdx, [rsp+3A0h+var_350]
0x1800097a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097aa  mov     edi, eax
0x1800097ac  test    edi, edi
0x1800097ae  cmovz   edi, r12d
0x1800097b2  jmp     short loc_1800097BA
0x1800097b4  mov     ebx, edi
0x1800097b6  mov     eax, edi
0x1800097b8  mov     edi, eax
0x1800097ba  test    r15b, r15b
0x1800097bd  jz      short loc_1800097C8
0x1800097bf  lea     rcx, [rbp+2A0h+self]; self
0x1800097c3  call    MI_Instance_Destruct
0x1800097c8  test    sil, sil
0x1800097cb  jz      short loc_1800097D9
0x1800097cd  lea     rcx, [rbp+2A0h+var_160]; self
0x1800097d4  call    MI_Instance_Destruct
0x1800097d9  test    ebx, ebx
0x1800097db  jnz     short loc_1800097E7
0x1800097dd  lea     rcx, [rsp+3A0h+var_350]; self
0x1800097e2  call    MI_Instance_Destruct
0x1800097e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097ee  lea     rax, WPP_GLOBAL_Control
0x1800097f5  cmp     rcx, rax
0x1800097f8  jz      short loc_180009818
0x1800097fa  test    byte ptr [rcx+1Ch], 1
0x1800097fe  jz      short loc_180009818
0x180009800  mov     rcx, [rcx+10h]
0x180009804  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000980b  mov     edx, 36h ; '6'
0x180009810  mov     r9d, edi
0x180009813  call    WPP_SF_d
0x180009818  mov     eax, edi
0x18000981a  mov     rcx, [rbp+2A0h+var_50]
0x180009821  xor     rcx, rsp; StackCookie
0x180009824  call    __security_check_cookie
0x180009829  add     rsp, 368h
0x180009830  pop     r15
0x180009832  pop     r14
0x180009834  pop     r13
0x180009836  pop     r12
0x180009838  pop     rdi
0x180009839  pop     rsi
0x18000983a  pop     rbx
0x18000983b  pop     rbp
0x18000983c  retn
```
