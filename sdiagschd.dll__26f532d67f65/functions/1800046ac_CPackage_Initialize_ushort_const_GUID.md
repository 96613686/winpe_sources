# CPackage::Initialize(ushort * const,_GUID *)

- ea: `0x1800046ac`
- end: `0x1800048b3`
- name: `?Initialize@CPackage@@QEAAJQEAGPEAU_GUID@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(CPackage *__hidden this, unsigned __int16 *const, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007a48`

## callees

- `0x1800046ac`
- `0x180004b8c`
- `0x1800050c0`
- `0x180005260`
- `0x180005404`
- `0x180005714`
- `0x18000579c`
- `0x18000b13c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004706`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004706`

## pseudocode

```c
__int64 __fastcall CPackage::Initialize(LPVOID *this, unsigned __int16 *const a2, struct _GUID *a3)
{
  _QWORD *v6; // rdi
  HRESULT Instance; // eax
  int v8; // ebx
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int16 *v17; // r8
  int v19; // [rsp+50h] [rbp+8h] BYREF
  struct IScriptedDiagnosticInformation *v20; // [rsp+68h] [rbp+20h] BYREF

  v20 = 0;
  v19 = 0;
  if ( (Microsoft_Windows_Diagnosis_ScheduledEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(this, &SCHEDULED_DIAGNOSTICS_EVENT_INITIALIZATION_STARTED, a2);
  v6 = this + 1;
  Instance = CoCreateInstance(&CLSID_CScriptedDiag, 0, 0x15u, &IID_IScriptedDiagnosticExecution, this + 1);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v9 = 545;
    v10 = Instance;
LABEL_19:
    SdpDebugTrace(1u, L"CPackage::Initialize", v9, v10);
    if ( (Microsoft_Windows_Diagnosis_ScheduledEnableBits & 2) != 0 )
    {
      v17 = (unsigned __int16 *)*this;
      if ( !*this )
        v17 = a2;
      McTemplateU0zq_EventWriteTransfer(v16, v15, v17, (unsigned __int16)v8);
    }
    if ( *this )
      CPackage::SchdpAddSQMErrorStream(this, a3, 0, (unsigned __int16)v8);
    goto LABEL_27;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, _QWORD, _QWORD))(*(_QWORD *)*v6 + 56LL))(
          *v6,
          a2,
          0,
          0);
  v8 = v11;
  v10 = v11;
  if ( v11 < 0 )
  {
    v9 = 548;
    goto LABEL_19;
  }
  v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IScriptedDiagnosticInformation **, _QWORD))*v6)(
          *v6,
          &IID_IScriptedDiagnosticInformation,
          &v20,
          (unsigned int)v11);
  v8 = v12;
  v10 = v12;
  if ( v12 < 0 )
  {
    v9 = 552;
    goto LABEL_19;
  }
  v8 = (*(__int64 (__fastcall **)(struct IScriptedDiagnosticInformation *, int *, __int64, _QWORD))(*(_QWORD *)v20
                                                                                                  + 112LL))(
         v20,
         &v19,
         v13,
         (unsigned int)v12);
  v10 = v8;
  if ( v8 < 0 )
  {
    v9 = 555;
    goto LABEL_19;
  }
  if ( (v19 & 1) != 0 )
  {
    v8 = -2147467259;
    v9 = 558;
    v10 = -2147467259;
    goto LABEL_19;
  }
  v8 = CPackage::SchdpInitializeIdentification((CPackage *)this, v20);
  v10 = v8;
  if ( v8 < 0 )
  {
    v9 = 561;
    goto LABEL_19;
  }
  v8 = CPackage::SchdpInitializeNotification((CPackage *)this, v20);
  v10 = v8;
  if ( v8 < 0 )
  {
    v9 = 564;
    goto LABEL_19;
  }
  v8 = CPackage::SchdpInitializeRootCauses((CPackage *)this, v20);
  v10 = v8;
  if ( v8 < 0 )
  {
    v9 = 567;
    goto LABEL_19;
  }
  if ( (Microsoft_Windows_Diagnosis_ScheduledEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(v14, &SCHEDULED_DIAGNOSTICS_EVENT_INITIALIZATION_COMPLETED, *this);
LABEL_27:
  if ( v20 )
    (*(void (__fastcall **)(struct IScriptedDiagnosticInformation *))(*(_QWORD *)v20 + 16LL))(v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800046ac  mov     rax, rsp
0x1800046af  mov     [rax+10h], rbx
0x1800046b3  mov     [rax+18h], rbp
0x1800046b7  push    rsi
0x1800046b8  push    rdi
0x1800046b9  push    r14
0x1800046bb  sub     rsp, 30h
0x1800046bf  and     qword ptr [rax+20h], 0
0x1800046c4  mov     r14, r8
0x1800046c7  and     dword ptr [rax+8], 0
0x1800046cb  mov     rbp, rdx
0x1800046ce  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScheduledEnableBits, 2
0x1800046d5  mov     rsi, rcx
0x1800046d8  jz      short loc_1800046E9
0x1800046da  mov     r8, rdx
0x1800046dd  lea     rdx, SCHEDULED_DIAGNOSTICS_EVENT_INITIALIZATION_STARTED
0x1800046e4  call    McTemplateU0z_EventWriteTransfer
0x1800046e9  xor     edx, edx; pUnkOuter
0x1800046eb  lea     rdi, [rsi+8]
0x1800046ef  lea     r9, IID_IScriptedDiagnosticExecution; riid
0x1800046f6  mov     [rsp+48h+ppv], rdi; ppv
0x1800046fb  lea     rcx, CLSID_CScriptedDiag; rclsid
0x180004702  lea     r8d, [rdx+15h]; dwClsContext
0x180004706  call    cs:__imp_CoCreateInstance
0x18000470d  nop     dword ptr [rax+rax+00h]
0x180004712  mov     ebx, eax
0x180004714  test    eax, eax
0x180004716  jns     short loc_18000472B
0x180004718  mov     edi, 1
0x18000471d  mov     r8d, 221h
0x180004723  mov     r9d, eax
0x180004726  jmp     loc_18000482A
0x18000472b  mov     rcx, [rdi]
0x18000472e  xor     r9d, r9d
0x180004731  xor     r8d, r8d
0x180004734  mov     rdx, rbp
0x180004737  mov     rax, [rcx]
0x18000473a  mov     rax, [rax+38h]
0x18000473e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004743  mov     ebx, eax
0x180004745  mov     r9d, eax
0x180004748  test    eax, eax
0x18000474a  jns     short loc_18000475C
0x18000474c  mov     edi, 1
0x180004751  mov     r8d, 224h
0x180004757  jmp     loc_18000482A
0x18000475c  mov     rcx, [rdi]
0x18000475f  lea     r8, [rsp+48h+arg_18]
0x180004764  lea     rdx, IID_IScriptedDiagnosticInformation
0x18000476b  mov     rax, [rcx]
0x18000476e  mov     rax, [rax]
0x180004771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004776  mov     ebx, eax
0x180004778  mov     r9d, eax
0x18000477b  test    eax, eax
0x18000477d  jns     short loc_18000478F
0x18000477f  mov     edi, 1
0x180004784  mov     r8d, 228h
0x18000478a  jmp     loc_18000482A
0x18000478f  mov     rcx, [rsp+48h+arg_18]
0x180004794  lea     rdx, [rsp+48h+arg_0]
0x180004799  mov     rax, [rcx]
0x18000479c  mov     rax, [rax+70h]
0x1800047a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047a5  mov     ebx, eax
0x1800047a7  mov     r9d, eax
0x1800047aa  mov     edi, 1
0x1800047af  test    eax, eax
0x1800047b1  jns     short loc_1800047BB
0x1800047b3  mov     r8d, 22Bh
0x1800047b9  jmp     short loc_18000482A
0x1800047bb  test    byte ptr [rsp+48h+arg_0], dil
0x1800047c0  jz      short loc_1800047D2
0x1800047c2  mov     ebx, 80004005h
0x1800047c7  mov     r8d, 22Eh
0x1800047cd  mov     r9d, ebx
0x1800047d0  jmp     short loc_18000482A
0x1800047d2  mov     rdx, [rsp+48h+arg_18]; struct IScriptedDiagnosticInformation *
0x1800047d7  mov     rcx, rsi; this
0x1800047da  call    ?SchdpInitializeIdentification@CPackage@@AEAAJPEAUIScriptedDiagnosticInformation@@@Z; CPackage::SchdpInitializeIdentification(IScriptedDiagnosticInformation *)
0x1800047df  mov     ebx, eax
0x1800047e1  mov     r9d, eax
0x1800047e4  test    eax, eax
0x1800047e6  jns     short loc_1800047F0
0x1800047e8  mov     r8d, 231h
0x1800047ee  jmp     short loc_18000482A
0x1800047f0  mov     rdx, [rsp+48h+arg_18]; struct IScriptedDiagnosticInformation *
0x1800047f5  mov     rcx, rsi; this
0x1800047f8  call    ?SchdpInitializeNotification@CPackage@@AEAAJPEAUIScriptedDiagnosticInformation@@@Z; CPackage::SchdpInitializeNotification(IScriptedDiagnosticInformation *)
0x1800047fd  mov     ebx, eax
0x1800047ff  mov     r9d, eax
0x180004802  test    eax, eax
0x180004804  jns     short loc_18000480E
0x180004806  mov     r8d, 234h
0x18000480c  jmp     short loc_18000482A
0x18000480e  mov     rdx, [rsp+48h+arg_18]; struct IScriptedDiagnosticInformation *
0x180004813  mov     rcx, rsi; this
0x180004816  call    ?SchdpInitializeRootCauses@CPackage@@AEAAJPEAUIScriptedDiagnosticInformation@@@Z; CPackage::SchdpInitializeRootCauses(IScriptedDiagnosticInformation *)
0x18000481b  mov     ebx, eax
0x18000481d  mov     r9d, eax; int
0x180004820  test    eax, eax
0x180004822  jns     short loc_18000486F
0x180004824  mov     r8d, 237h; int
0x18000482a  lea     rdx, aCpackageInitia; "CPackage::Initialize"
0x180004831  mov     ecx, edi; Level
0x180004833  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180004838  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScheduledEnableBits, 2
0x18000483f  movzx   edi, bx
0x180004842  jz      short loc_180004856
0x180004844  mov     r8, [rsi]
0x180004847  mov     r9d, edi
0x18000484a  test    r8, r8
0x18000484d  cmovz   r8, rbp
0x180004851  call    McTemplateU0zq_EventWriteTransfer
0x180004856  cmp     qword ptr [rsi], 0
0x18000485a  jz      short loc_180004887
0x18000485c  mov     r9d, edi
0x18000485f  xor     r8d, r8d
0x180004862  mov     rdx, r14
0x180004865  mov     rcx, rsi
0x180004868  call    ?SchdpAddSQMErrorStream@CPackage@@AEAAJPEAU_GUID@@W4_SDIAGSCHD_PACKAGE_PHASE@@K@Z; CPackage::SchdpAddSQMErrorStream(_GUID *,_SDIAGSCHD_PACKAGE_PHASE,ulong)
0x18000486d  jmp     short loc_180004887
0x18000486f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScheduledEnableBits, 2
0x180004876  jz      short loc_180004887
0x180004878  mov     r8, [rsi]
0x18000487b  lea     rdx, SCHEDULED_DIAGNOSTICS_EVENT_INITIALIZATION_COMPLETED
0x180004882  call    McTemplateU0z_EventWriteTransfer
0x180004887  mov     rcx, [rsp+48h+arg_18]
0x18000488c  test    rcx, rcx
0x18000488f  jz      short loc_18000489D
0x180004891  mov     rax, [rcx]
0x180004894  mov     rax, [rax+10h]
0x180004898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489d  mov     rbp, [rsp+48h+arg_10]
0x1800048a2  mov     eax, ebx
0x1800048a4  mov     rbx, [rsp+48h+arg_8]
0x1800048a9  add     rsp, 30h
0x1800048ad  pop     r14
0x1800048af  pop     rdi
0x1800048b0  pop     rsi
0x1800048b1  retn
```
