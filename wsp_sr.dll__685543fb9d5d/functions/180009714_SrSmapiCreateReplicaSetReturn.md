# SrSmapiCreateReplicaSetReturn

- ea: `0x180009714`
- end: `0x18000998c`
- name: `SrSmapiCreateReplicaSetReturn`
- size: `632`
- prototype: `__int64 __usercall@<rax>(enum _MI_Result@<ecx>, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000950c`

## callees

- `0x1800014e0`
- `0x180001e38`
- `0x1800029e4`
- `0x180005cec`
- `0x1800067cc`
- `0x1800067fc`
- `0x180009028`
- `0x180009714`
- `0x180014fa4`
- `0x18001bf54`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicaSetReturn(
        enum _MI_Result a1,
        __int64 a2,
        MI_Instance *a3,
        __int64 a4,
        MI_Context **a5)
{
  bool v8; // si
  MI_Result v9; // r12d
  enum _MI_Result v10; // ebx
  char v11; // di
  MI_Instance *p_self; // [rsp+30h] [rbp-D0h] BYREF
  MI_Instance *v14; // [rsp+38h] [rbp-C8h] BYREF
  MI_Instance instance; // [rsp+40h] [rbp-C0h] BYREF
  enum _MI_Result v16; // [rsp+80h] [rbp-80h]
  char v17; // [rsp+84h] [rbp-7Ch]
  MI_Instance self; // [rsp+120h] [rbp+20h] BYREF
  MI_Instance v19; // [rsp+230h] [rbp+130h] BYREF

  p_self = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  self.ft = 0;
  v8 = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  v19.ft = 0;
  memset_0(&v19.classDecl, 0, 0x108u);
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xD0u);
  v9 = MI_Context_ConstructParameters(a5[7], &WSP_ReplicationGroup_CreateReplica_rtti, &instance);
  if ( v9 )
  {
    v10 = v9;
    goto LABEL_16;
  }
  v10 = MI_Context_ConstructInstance(a5[7], &MSFT_StorageExtendedStatus_rtti, &v19);
  if ( v10 )
  {
LABEL_16:
    v11 = 0;
    goto LABEL_17;
  }
  v10 = SrSmapiPopulateStorageExtendedStatus((struct _MSFT_StorageExtendedStatus *)&v19, a1, (struct CWMIContext *)a5);
  if ( v10 == MI_RESULT_OK )
  {
    v14 = &v19;
    v10 = ((unsigned int (__fastcall *)(MI_Instance *, __int64, MI_Instance **, _QWORD, _DWORD))instance.ft->SetElementAt)(
            &instance,
            10,
            &v14,
            (unsigned int)(v9 + 15),
            0);
    if ( v10 == MI_RESULT_OK )
    {
      if ( a1
        || !a4
        || (v10 = MI_Context_ConstructInstance(a5[7], &WSP_ReplicaPeer_rtti, &self),
            v8 = v10 == MI_RESULT_OK,
            v10 == MI_RESULT_OK)
        && (v10 = (unsigned int)SrSmapiCreateReplicaPeerFromReplicationGroup(a4, a2, p_self, &self)) == MI_RESULT_OK
        && (p_self = &self,
            (v10 = ((unsigned int (__fastcall *)(MI_Instance *, __int64, MI_Instance **, _QWORD, _DWORD))instance.ft->SetElementAt)(
                     &instance,
                     8,
                     &p_self,
                     (unsigned int)(v9 + 15),
                     0)) == MI_RESULT_OK) )
      {
        v16 = a1;
        v17 = 1;
      }
    }
  }
  v11 = 1;
LABEL_17:
  if ( v10 == MI_RESULT_OK )
  {
    v10 = MI_Instance_Destruct((MI_Instance *)a5[7]);
    if ( v10 == MI_RESULT_OK )
      v10 = a1;
  }
  if ( v8 )
    MI_Instance_Destruct(&self);
  if ( v11 )
    MI_Instance_Destruct(&v19);
  if ( v9 == MI_RESULT_OK )
    MI_Instance_Destruct(&instance);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_97259de4980931de249eb41af43a46d5_Traceguids,
      (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009714  push    rbp
0x180009716  push    rbx
0x180009717  push    rsi
0x180009718  push    rdi
0x180009719  push    r12
0x18000971b  push    r13
0x18000971d  push    r14
0x18000971f  push    r15
0x180009721  lea     rbp, [rsp-258h]
0x180009729  sub     rsp, 358h
0x180009730  mov     rax, cs:__security_cookie
0x180009737  xor     rax, rsp
0x18000973a  mov     [rbp+290h+var_50], rax
0x180009741  mov     r15, [rbp+290h+arg_20]
0x180009748  mov     rdi, r9
0x18000974b  mov     [rsp+390h+var_360], r8
0x180009750  mov     r13, rdx
0x180009753  mov     r14d, ecx
0x180009756  mov     rcx, cs:WPP_GLOBAL_Control
0x18000975d  lea     rax, WPP_GLOBAL_Control
0x180009764  cmp     rcx, rax
0x180009767  jz      short loc_180009784
0x180009769  test    byte ptr [rcx+1Ch], 4
0x18000976d  jz      short loc_180009784
0x18000976f  mov     rcx, [rcx+10h]
0x180009773  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000977a  mov     edx, 35h ; '5'
0x18000977f  call    WPP_SF_
0x180009784  xor     r12d, r12d
0x180009787  lea     rcx, [rbp+290h+self.classDecl]; void *
0x18000978b  mov     ebx, 108h
0x180009790  mov     [rbp+290h+self.ft], r12
0x180009794  mov     r8d, ebx; Size
0x180009797  xor     edx, edx; Val
0x180009799  mov     sil, r12b
0x18000979c  call    memset_0
0x1800097a1  mov     r8d, ebx; Size
0x1800097a4  mov     [rbp+290h+var_160.ft], r12
0x1800097ab  xor     edx, edx; Val
0x1800097ad  lea     rcx, [rbp+290h+var_160.classDecl]; void *
0x1800097b4  call    memset_0
0x1800097b9  xor     edx, edx; Val
0x1800097bb  mov     [rsp+390h+instance.ft], r12
0x1800097c0  lea     r8d, [rbx-38h]; Size
0x1800097c4  lea     rcx, [rsp+390h+instance.classDecl]; void *
0x1800097c9  call    memset_0
0x1800097ce  mov     rcx, [r15+38h]; context
0x1800097d2  lea     r8, [rsp+390h+instance]; instance
0x1800097d7  lea     rdx, WSP_ReplicationGroup_CreateReplica_rtti; methodDecl
0x1800097de  call    MI_Context_ConstructParameters
0x1800097e3  mov     r12d, eax
0x1800097e6  test    eax, eax
0x1800097e8  jnz     loc_1800098E7
0x1800097ee  mov     rcx, [r15+38h]; context
0x1800097f2  lea     r8, [rbp+290h+var_160]; instance
0x1800097f9  lea     rdx, MSFT_StorageExtendedStatus_rtti; classDecl
0x180009800  call    MI_Context_ConstructInstance
0x180009805  mov     ebx, eax
0x180009807  test    eax, eax
0x180009809  jnz     loc_1800098EA
0x18000980f  mov     r8, r15; struct CWMIContext *
0x180009812  lea     rcx, [rbp+290h+var_160]; struct _MSFT_StorageExtendedStatus *
0x180009819  mov     edx, r14d; enum _MI_Result
0x18000981c  call    ?SrSmapiPopulateStorageExtendedStatus@@YA?AW4_MI_Result@@PEAU_MSFT_StorageExtendedStatus@@W41@AEAVCWMIContext@@@Z; SrSmapiPopulateStorageExtendedStatus(_MSFT_StorageExtendedStatus *,_MI_Result,CWMIContext &)
0x180009821  mov     ebx, eax
0x180009823  test    eax, eax
0x180009825  jnz     loc_1800098D8
0x18000982b  lea     rax, [rbp+290h+var_160]
0x180009832  mov     [rsp+390h+var_370], ebx
0x180009836  mov     [rsp+390h+var_358], rax
0x18000983b  lea     r9d, [r12+0Fh]
0x180009840  mov     rax, [rsp+390h+instance.ft]
0x180009845  lea     r8, [rsp+390h+var_358]
0x18000984a  lea     edx, [rbx+0Ah]
0x18000984d  lea     rcx, [rsp+390h+instance]
0x180009852  mov     rax, [rax+50h]
0x180009856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000985b  mov     ebx, eax
0x18000985d  test    eax, eax
0x18000985f  jnz     short loc_1800098D8
0x180009861  test    r14d, r14d
0x180009864  jnz     short loc_1800098DD
0x180009866  test    rdi, rdi
0x180009869  jz      short loc_1800098DD
0x18000986b  mov     rcx, [r15+38h]; context
0x18000986f  lea     r8, [rbp+290h+self]; instance
0x180009873  lea     rdx, WSP_ReplicaPeer_rtti; classDecl
0x18000987a  call    MI_Context_ConstructInstance
0x18000987f  test    eax, eax
0x180009881  mov     ebx, eax
0x180009883  setz    sil
0x180009887  test    eax, eax
0x180009889  jnz     short loc_1800098D8
0x18000988b  mov     r8, [rsp+390h+var_360]
0x180009890  lea     r9, [rbp+290h+self]
0x180009894  mov     rdx, r13
0x180009897  mov     rcx, rdi
0x18000989a  call    ?SrSmapiCreateReplicaPeerFromReplicationGroup@@YA?AW4_MI_Result@@PEBU_MSFT_ReplicaPeer@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1PEAU_WSP_ReplicaPeer@@@Z; SrSmapiCreateReplicaPeerFromReplicationGroup(_MSFT_ReplicaPeer const *,std::wstring const &,std::wstring const &,_WSP_ReplicaPeer *)
0x18000989f  mov     ebx, eax
0x1800098a1  test    eax, eax
0x1800098a3  jnz     short loc_1800098D8
0x1800098a5  lea     rax, [rbp+290h+self]
0x1800098a9  mov     [rsp+390h+var_370], ebx
0x1800098ad  mov     [rsp+390h+var_360], rax
0x1800098b2  lea     r9d, [r12+0Fh]
0x1800098b7  mov     rax, [rsp+390h+instance.ft]
0x1800098bc  lea     r8, [rsp+390h+var_360]
0x1800098c1  lea     edx, [rbx+8]
0x1800098c4  lea     rcx, [rsp+390h+instance]
0x1800098c9  mov     rax, [rax+50h]
0x1800098cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098d2  mov     ebx, eax
0x1800098d4  test    eax, eax
0x1800098d6  jz      short loc_1800098DD
0x1800098d8  mov     dil, 1
0x1800098db  jmp     short loc_1800098ED
0x1800098dd  mov     [rbp+290h+var_310], r14d
0x1800098e1  mov     [rbp+290h+var_30C], 1
0x1800098e5  jmp     short loc_1800098D8
0x1800098e7  mov     ebx, r12d
0x1800098ea  xor     dil, dil
0x1800098ed  test    ebx, ebx
0x1800098ef  jnz     short loc_180009907
0x1800098f1  mov     rcx, [r15+38h]; self
0x1800098f5  lea     rdx, [rsp+390h+instance]
0x1800098fa  call    MI_Instance_Destruct
0x1800098ff  test    eax, eax
0x180009901  mov     ebx, eax
0x180009903  cmovz   ebx, r14d
0x180009907  test    sil, sil
0x18000990a  jz      short loc_180009915
0x18000990c  lea     rcx, [rbp+290h+self]; self
0x180009910  call    MI_Instance_Destruct
0x180009915  test    dil, dil
0x180009918  jz      short loc_180009926
0x18000991a  lea     rcx, [rbp+290h+var_160]; self
0x180009921  call    MI_Instance_Destruct
0x180009926  test    r12d, r12d
0x180009929  jnz     short loc_180009935
0x18000992b  lea     rcx, [rsp+390h+instance]; self
0x180009930  call    MI_Instance_Destruct
0x180009935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000993c  lea     rax, WPP_GLOBAL_Control
0x180009943  cmp     rcx, rax
0x180009946  jz      short loc_180009966
0x180009948  test    byte ptr [rcx+1Ch], 1
0x18000994c  jz      short loc_180009966
0x18000994e  mov     rcx, [rcx+10h]
0x180009952  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x180009959  mov     edx, 36h ; '6'
0x18000995e  mov     r9d, ebx
0x180009961  call    WPP_SF_d
0x180009966  mov     eax, ebx
0x180009968  mov     rcx, [rbp+290h+var_50]
0x18000996f  xor     rcx, rsp; StackCookie
0x180009972  call    __security_check_cookie
0x180009977  add     rsp, 358h
0x18000997e  pop     r15
0x180009980  pop     r14
0x180009982  pop     r13
0x180009984  pop     r12
0x180009986  pop     rdi
0x180009987  pop     rsi
0x180009988  pop     rbx
0x180009989  pop     rbp
0x18000998a  retn
```
