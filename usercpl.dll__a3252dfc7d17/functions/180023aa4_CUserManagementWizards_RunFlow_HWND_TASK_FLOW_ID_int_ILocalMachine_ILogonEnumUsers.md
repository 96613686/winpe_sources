# CUserManagementWizards::_RunFlow(HWND__ *,TASK_FLOW_ID,int,ILocalMachine *,ILogonEnumUsers *)

- ea: `0x180023aa4`
- end: `0x180023de9`
- name: `?_RunFlow@CUserManagementWizards@@AEAAJPEAUHWND__@@W4TASK_FLOW_ID@@HPEAUILocalMachine@@PEAUILogonEnumUsers@@@Z`
- size: `837`
- prototype: `int __high(HWND, enum TASK_FLOW_ID, int, struct ILocalMachine *, struct ILogonEnumUsers *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180023970`

## callees

- `0x180007968`
- `0x18000eb70`
- `0x18000ebc0`
- `0x18000eccc`
- `0x180022f7c`
- `0x180023aa4`
- `0x180023df0`
- `0x1800606f0`
- `0x180067360`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023cb4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023cb4`
- `DUI70!UnInitProcessPriv` at `0x180023dba`
- `DUI70!UnInitProcessPriv` at `0x180023dba`
- `DUI70!UnInitThread` at `0x180023dad`
- `DUI70!UnInitThread` at `0x180023dad`
- `DUI70!InitThread` at `0x180023b1e`
- `DUI70!InitThread` at `0x180023b1e`
- `DUI70!InitProcessPriv` at `0x180023afa`
- `DUI70!InitProcessPriv` at `0x180023afa`

## pseudocode

```c
__int64 __fastcall CUserManagementWizards::_RunFlow(__int64 a1, HWND a2, __int64 a3, int a4, _QWORD *a5, _QWORD *a6)
{
  int v7; // edi
  int inited; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // r8
  int NonElevatedObjects; // eax
  void (__fastcall **v14)(_QWORD, GUID *, HWND *); // rax
  void (__fastcall **v15)(_QWORD, GUID *, __int64 *); // rax
  __int64 v16; // r8
  LPVOID v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // edi
  __int64 v21; // rcx
  int v22; // eax
  LPVOID v23; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-79h] BYREF
  HWND v26; // [rsp+38h] [rbp-71h] BYREF
  __int64 v27; // [rsp+40h] [rbp-69h] BYREF
  int v28; // [rsp+48h] [rbp-61h] BYREF
  __int64 v29; // [rsp+50h] [rbp-59h] BYREF
  GUID v30; // [rsp+60h] [rbp-49h] BYREF
  GUID *v31; // [rsp+70h] [rbp-39h]
  void (__fastcall ***v32)(_QWORD, GUID *, HWND *); // [rsp+78h] [rbp-31h]
  char v33; // [rsp+80h] [rbp-29h]
  GUID v34; // [rsp+88h] [rbp-21h]
  GUID *v35; // [rsp+98h] [rbp-11h]
  void (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp-9h]
  char v37; // [rsp+A8h] [rbp-1h]

  v7 = a3;
  v26 = a2;
  LOBYTE(a3) = 1;
  inited = InitProcessPriv(14, &_ImageBase, a3);
  if ( inited >= 0 )
  {
    if ( !a4 || (v10 = 0, v7) )
      v10 = 65538;
    inited = InitThread(v10);
    if ( inited < 0 )
      goto LABEL_45;
    inited = CNavigateButton::Register();
    if ( inited >= 0 )
      inited = UserTile::Register();
    if ( inited < 0 )
    {
LABEL_44:
      UnInitThread(v11);
LABEL_45:
      UnInitProcessPriv(&_ImageBase);
      return (unsigned int)inited;
    }
    v32 = 0;
    v31 = &IID_ILocalMachine;
    v33 = 0;
    v35 = &IID_ILogonEnumUsers;
    v36 = 0;
    v37 = 0;
    v30 = CLSID_ShellLocalMachine;
    v34 = CLSID_ShellLogonEnumUsers;
    if ( a5 )
    {
      v14 = (void (__fastcall **)(_QWORD, GUID *, HWND *))*a5;
      v32 = (void (__fastcall ***)(_QWORD, GUID *, HWND *))a5;
      ((void (__fastcall *)(_QWORD *))v14[1])(a5);
      v15 = (void (__fastcall **)(_QWORD, GUID *, __int64 *))*a6;
      v36 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))a6;
      ((void (__fastcall *)(_QWORD *))v15[1])(a6);
    }
    else
    {
      if ( v7 )
        NonElevatedObjects = CUserCplInitializer::s_CreateNonElevatedObjects((struct INNER_OBJ_INFO *const)&v30, 2u);
      else
        NonElevatedObjects = CUserCplInitializer::s_CreateElevatedObjects(a2, (struct INNER_OBJ_INFO *const)&v30, v12);
      inited = NonElevatedObjects;
      if ( NonElevatedObjects < 0 )
        goto LABEL_44;
    }
    ppv = 0;
    inited = Microsoft::WRL::Details::MakeAndInitialize<CUserManager,CUserManager,HWND__ * &>(&ppv, &v26);
    if ( inited < 0 )
    {
LABEL_43:
      CUserCplInitializer::s_CleanInnerObjectArray((struct INNER_OBJ_INFO *const)&v30, 2u);
      goto LABEL_44;
    }
    v26 = 0;
    if ( v32 )
      (**v32)(v32, &GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461, &v26);
    v16 = 0;
    v29 = 0;
    if ( v36 )
    {
      (**v36)(v36, &GUID_3ee328ab_8f69_420a_9b86_7080f22af38b, &v29);
      v16 = v29;
    }
    v17 = ppv;
    inited = (*(__int64 (__fastcall **)(LPVOID, HWND, __int64, _QWORD, _DWORD))(*(_QWORD *)ppv + 24LL))(
               ppv,
               v26,
               v16,
               0,
               0);
    if ( inited >= 0 )
    {
      if ( v7 )
      {
        v19 = 6;
        v20 = v7 - 6;
        if ( v20 )
        {
          if ( v20 == 1 )
          {
            ppv = 0;
            if ( CoCreateInstance(
                   &GUID_228826af_02e1_4226_a9e0_99a855e455a6,
                   0,
                   0x404u,
                   &GUID_9767060c_9476_42e2_8f7b_2f10fd13765c,
                   &ppv) >= 0 )
            {
              v27 = 0;
              if ( (*(int (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, &v27) >= 0 )
              {
                v28 = 0;
                (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 48LL))(v27, &v28);
              }
              v21 = v27;
              if ( v27 )
              {
                v27 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              }
            }
            v22 = CUserManagementWizards::_TaskFlowHelper(v21, 7, a2, v17);
            v23 = ppv;
            inited = v22;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
            }
          }
          else
          {
            inited = -2147024809;
          }
          goto LABEL_37;
        }
        goto LABEL_36;
      }
      if ( !a4 )
      {
        v19 = 0;
LABEL_36:
        inited = CUserManagementWizards::_TaskFlowHelper(v18, v19, a2, v17);
        goto LABEL_37;
      }
      AddNewAccount(a2, v17);
    }
LABEL_37:
    if ( v17 )
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v17 + 144LL))(v17, 1);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v26 )
      (*(void (__fastcall **)(HWND))(*(_QWORD *)v26 + 16LL))(v26);
    goto LABEL_43;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180023aa4  mov     [rsp-8+arg_0], rbx
0x180023aa9  push    rbp
0x180023aaa  push    rsi
0x180023aab  push    rdi
0x180023aac  push    r12
0x180023aae  push    r13
0x180023ab0  push    r14
0x180023ab2  push    r15
0x180023ab4  lea     rbp, [rsp-17h]
0x180023ab9  sub     rsp, 0C0h
0x180023ac0  mov     rax, cs:__security_cookie
0x180023ac7  xor     rax, rsp
0x180023aca  mov     [rbp+47h+var_40], rax
0x180023ace  mov     rsi, [rbp+47h+arg_20]
0x180023ad2  mov     r12d, r9d
0x180023ad5  mov     r15, [rbp+47h+arg_28]
0x180023ad9  mov     r9b, 1
0x180023adc  mov     edi, r8d
0x180023adf  mov     [rbp+47h+var_B8], rdx
0x180023ae3  mov     r14, rdx
0x180023ae6  mov     byte ptr [rsp+0F0h+ppv], 1
0x180023aeb  mov     r8b, r9b
0x180023aee  lea     rdx, __ImageBase
0x180023af5  mov     ecx, 0Eh
0x180023afa  call    cs:__imp_InitProcessPriv
0x180023b00  xor     r13d, r13d
0x180023b03  mov     ebx, eax
0x180023b05  test    eax, eax
0x180023b07  js      loc_180023DC0
0x180023b0d  test    r12d, r12d
0x180023b10  jz      short loc_180023B19
0x180023b12  mov     ecx, r13d
0x180023b15  test    edi, edi
0x180023b17  jz      short loc_180023B1E
0x180023b19  mov     ecx, 10002h
0x180023b1e  call    cs:__imp_InitThread
0x180023b24  mov     ebx, eax
0x180023b26  test    eax, eax
0x180023b28  js      loc_180023DB3
0x180023b2e  call    ?Register@CNavigateButton@@SAJXZ; CNavigateButton::Register(void)
0x180023b33  mov     ebx, eax
0x180023b35  test    eax, eax
0x180023b37  js      short loc_180023B40
0x180023b39  call    ?Register@UserTile@@SAJXZ; UserTile::Register(void)
0x180023b3e  mov     ebx, eax
0x180023b40  test    ebx, ebx
0x180023b42  js      loc_180023DAD
0x180023b48  mov     [rbp+47h+var_78], r13
0x180023b4c  lea     rax, IID_ILocalMachine
0x180023b53  mov     [rbp+47h+var_80], rax
0x180023b57  lea     rax, IID_ILogonEnumUsers
0x180023b5e  mov     [rbp+47h+var_70], r13b
0x180023b62  mov     [rbp+47h+var_58], rax
0x180023b66  mov     [rbp+47h+var_50], r13
0x180023b6a  mov     [rbp+47h+var_48], r13b
0x180023b6e  movups  xmm0, xmmword ptr cs:CLSID_ShellLocalMachine.Data1
0x180023b75  movdqu  [rbp+47h+var_90], xmm0
0x180023b7a  movups  xmm0, xmmword ptr cs:CLSID_ShellLogonEnumUsers.Data1
0x180023b81  movdqu  [rbp+47h+var_68], xmm0
0x180023b86  test    rsi, rsi
0x180023b89  jnz     short loc_180023BB6
0x180023b8b  test    edi, edi
0x180023b8d  jnz     short loc_180023B9D
0x180023b8f  lea     rdx, [rbp+47h+var_90]; struct INNER_OBJ_INFO *
0x180023b93  mov     rcx, r14; hWnd
0x180023b96  call    ?s_CreateElevatedObjects@CUserCplInitializer@@SAJPEAUHWND__@@QEAUINNER_OBJ_INFO@@_K@Z; CUserCplInitializer::s_CreateElevatedObjects(HWND__ *,INNER_OBJ_INFO * const,unsigned __int64)
0x180023b9b  jmp     short loc_180023BAB
0x180023b9d  mov     edx, 2; unsigned __int64
0x180023ba2  lea     rcx, [rbp+47h+var_90]; struct INNER_OBJ_INFO *
0x180023ba6  call    ?s_CreateNonElevatedObjects@CUserCplInitializer@@SAJQEAUINNER_OBJ_INFO@@_K@Z; CUserCplInitializer::s_CreateNonElevatedObjects(INNER_OBJ_INFO * const,unsigned __int64)
0x180023bab  mov     ebx, eax
0x180023bad  test    eax, eax
0x180023baf  jns     short loc_180023BDC
0x180023bb1  jmp     loc_180023DAD
0x180023bb6  mov     rax, [rsi]
0x180023bb9  mov     rcx, rsi
0x180023bbc  mov     [rbp+47h+var_78], rsi
0x180023bc0  mov     rax, [rax+8]
0x180023bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bc9  mov     rax, [r15]
0x180023bcc  mov     rcx, r15
0x180023bcf  mov     [rbp+47h+var_50], r15
0x180023bd3  mov     rax, [rax+8]
0x180023bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bdc  lea     rdx, [rbp+47h+var_B8]
0x180023be0  mov     [rbp+47h+var_C0], r13
0x180023be4  lea     rcx, [rbp+47h+var_C0]
0x180023be8  call    ??$MakeAndInitialize@VCUserManager@@V1@AEAPEAUHWND__@@@Details@WRL@Microsoft@@YAJPEAPEAVCUserManager@@AEAPEAUHWND__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CUserManager,CUserManager,HWND__ * &>(CUserManager * *,HWND__ * &)
0x180023bed  mov     ebx, eax
0x180023bef  test    eax, eax
0x180023bf1  js      loc_180023D9F
0x180023bf7  mov     rcx, [rbp+47h+var_78]
0x180023bfb  mov     [rbp+47h+var_B8], r13
0x180023bff  test    rcx, rcx
0x180023c02  jz      short loc_180023C1A
0x180023c04  mov     rax, [rcx]
0x180023c07  lea     r8, [rbp+47h+var_B8]
0x180023c0b  lea     rdx, _GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461
0x180023c12  mov     rax, [rax]
0x180023c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c1a  mov     rcx, [rbp+47h+var_50]
0x180023c1e  mov     r8, r13
0x180023c21  mov     [rbp+47h+var_A0], r13
0x180023c25  test    rcx, rcx
0x180023c28  jz      short loc_180023C44
0x180023c2a  mov     rax, [rcx]
0x180023c2d  lea     r8, [rbp+47h+var_A0]
0x180023c31  lea     rdx, _GUID_3ee328ab_8f69_420a_9b86_7080f22af38b
0x180023c38  mov     rax, [rax]
0x180023c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c40  mov     r8, [rbp+47h+var_A0]
0x180023c44  mov     rsi, [rbp+47h+var_C0]
0x180023c48  xor     r9d, r9d
0x180023c4b  mov     rdx, [rbp+47h+var_B8]
0x180023c4f  mov     rcx, rsi
0x180023c52  mov     dword ptr [rsp+0F0h+ppv], r13d
0x180023c57  mov     rax, [rsi]
0x180023c5a  mov     rax, [rax+18h]
0x180023c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c63  mov     ebx, eax
0x180023c65  test    eax, eax
0x180023c67  js      loc_180023D59
0x180023c6d  test    edi, edi
0x180023c6f  jz      loc_180023D38
0x180023c75  mov     edx, 6
0x180023c7a  sub     edi, edx
0x180023c7c  jz      loc_180023D4C
0x180023c82  cmp     edi, 1
0x180023c85  jz      short loc_180023C91
0x180023c87  mov     ebx, 80070057h
0x180023c8c  jmp     loc_180023D59
0x180023c91  lea     rax, [rbp+47h+var_C0]
0x180023c95  mov     [rbp+47h+var_C0], r13
0x180023c99  lea     r9, _GUID_9767060c_9476_42e2_8f7b_2f10fd13765c; riid
0x180023ca0  mov     [rsp+0F0h+ppv], rax; ppv
0x180023ca5  xor     edx, edx; pUnkOuter
0x180023ca7  lea     rcx, _GUID_228826af_02e1_4226_a9e0_99a855e455a6; rclsid
0x180023cae  mov     r8d, 404h; dwClsContext
0x180023cb4  call    cs:__imp_CoCreateInstance
0x180023cba  test    eax, eax
0x180023cbc  js      short loc_180023D0B
0x180023cbe  mov     rcx, [rbp+47h+var_C0]
0x180023cc2  lea     rdx, [rbp+47h+var_B0]
0x180023cc6  mov     [rbp+47h+var_B0], r13
0x180023cca  mov     rax, [rcx]
0x180023ccd  mov     rax, [rax+28h]
0x180023cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cd6  test    eax, eax
0x180023cd8  js      short loc_180023CF2
0x180023cda  mov     rcx, [rbp+47h+var_B0]
0x180023cde  lea     rdx, [rbp+47h+var_A8]
0x180023ce2  mov     [rbp+47h+var_A8], r13d
0x180023ce6  mov     rax, [rcx]
0x180023ce9  mov     rax, [rax+30h]
0x180023ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cf2  mov     rcx, [rbp+47h+var_B0]
0x180023cf6  test    rcx, rcx
0x180023cf9  jz      short loc_180023D0B
0x180023cfb  mov     [rbp+47h+var_B0], r13
0x180023cff  mov     rax, [rcx]
0x180023d02  mov     rax, [rax+10h]
0x180023d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d0b  mov     r9, rsi
0x180023d0e  mov     r8, r14
0x180023d11  mov     edx, 7
0x180023d16  call    ?_TaskFlowHelper@CUserManagementWizards@@AEAAJW4TASK_FLOW_ID@@PEAUHWND__@@PEAVCUserManager@@@Z; CUserManagementWizards::_TaskFlowHelper(TASK_FLOW_ID,HWND__ *,CUserManager *)
0x180023d1b  mov     rcx, [rbp+47h+var_C0]
0x180023d1f  mov     ebx, eax
0x180023d21  test    rcx, rcx
0x180023d24  jz      short loc_180023D59
0x180023d26  mov     [rbp+47h+var_C0], r13
0x180023d2a  mov     rax, [rcx]
0x180023d2d  mov     rax, [rax+10h]
0x180023d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d36  jmp     short loc_180023D59
0x180023d38  test    r12d, r12d
0x180023d3b  jz      short loc_180023D4A
0x180023d3d  mov     rdx, rsi
0x180023d40  mov     rcx, r14
0x180023d43  call    ?AddNewAccount@@YAJPEAUHWND__@@PEAVCUserManager@@W4USER_CPL_ACTION_TYPE@@@Z; AddNewAccount(HWND__ *,CUserManager *,USER_CPL_ACTION_TYPE)
0x180023d48  jmp     short loc_180023D59
0x180023d4a  xor     edx, edx
0x180023d4c  mov     r9, rsi
0x180023d4f  mov     r8, r14
0x180023d52  call    ?_TaskFlowHelper@CUserManagementWizards@@AEAAJW4TASK_FLOW_ID@@PEAUHWND__@@PEAVCUserManager@@@Z; CUserManagementWizards::_TaskFlowHelper(TASK_FLOW_ID,HWND__ *,CUserManager *)
0x180023d57  mov     ebx, eax
0x180023d59  test    rsi, rsi
0x180023d5c  jz      short loc_180023D75
0x180023d5e  mov     rax, [rsi]
0x180023d61  mov     edx, 1
0x180023d66  mov     rcx, rsi
0x180023d69  mov     rax, [rax+90h]
0x180023d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d75  mov     rcx, [rbp+47h+var_A0]
0x180023d79  test    rcx, rcx
0x180023d7c  jz      short loc_180023D8A
0x180023d7e  mov     rax, [rcx]
0x180023d81  mov     rax, [rax+10h]
0x180023d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d8a  mov     rcx, [rbp+47h+var_B8]
0x180023d8e  test    rcx, rcx
0x180023d91  jz      short loc_180023D9F
0x180023d93  mov     rax, [rcx]
0x180023d96  mov     rax, [rax+10h]
0x180023d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d9f  mov     edx, 2; unsigned __int64
0x180023da4  lea     rcx, [rbp+47h+var_90]; struct INNER_OBJ_INFO *
0x180023da8  call    ?s_CleanInnerObjectArray@CUserCplInitializer@@SAXQEAUINNER_OBJ_INFO@@_K@Z; CUserCplInitializer::s_CleanInnerObjectArray(INNER_OBJ_INFO * const,unsigned __int64)
0x180023dad  call    cs:__imp_UnInitThread
0x180023db3  lea     rcx, __ImageBase
0x180023dba  call    cs:__imp_UnInitProcessPriv
0x180023dc0  mov     eax, ebx
0x180023dc2  mov     rcx, [rbp+47h+var_40]
0x180023dc6  xor     rcx, rsp; StackCookie
0x180023dc9  call    __security_check_cookie
0x180023dce  mov     rbx, [rsp+0F0h+arg_0]
0x180023dd6  add     rsp, 0C0h
0x180023ddd  pop     r15
0x180023ddf  pop     r14
0x180023de1  pop     r13
0x180023de3  pop     r12
0x180023de5  pop     rdi
0x180023de6  pop     rsi
0x180023de7  pop     rbp
0x180023de8  retn
```
