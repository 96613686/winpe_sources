# CoCreateInstanceAsSystem

- ea: `0x1800185b4`
- end: `0x1800186c0`
- name: `CoCreateInstanceAsSystem`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012d7c`
- `0x180013cc0`

## callees

- `0x180002610`
- `0x18000934c`
- `0x18001741c`
- `0x1800175b8`
- `0x180017658`
- `0x180017d1c`
- `0x180017e3c`
- `0x1800183f4`
- `0x1800185b4`
- `0x18001f010`

## string_xrefs

- `0x18001866f`: `shell\lib\comtaskserverutil.cpp`

## pseudocode

```c
__int64 __fastcall CoCreateInstanceAsSystem(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  wil::details *v6; // r8
  __int64 v7; // r9
  int COMTaskServerObject; // eax
  int v9; // ebx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-188h]
  LPVOID v14[2]; // [rsp+30h] [rbp-178h] BYREF
  _QWORD v15[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  *a3 = 0;
  wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v15);
  v15[0] = &CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::`vftable';
  CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::StartActivity((CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem *)v15);
  v14[0] = 0;
  COMTaskServerObject = CoCreateCOMTaskServerObject(v5, v4, v6, v7, v13, v14);
  v9 = COMTaskServerObject;
  if ( COMTaskServerObject < 0 )
  {
    v10 = (unsigned int)COMTaskServerObject;
    v11 = 127;
LABEL_7:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (int)"shell\\lib\\comtaskserverutil.cpp", (const char *)v10);
    goto LABEL_9;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD, GUID *, _QWORD *))(*(_QWORD *)v14[0] + 24LL))(
         v14[0],
         &CLSID_PicturePasswordEnrollmentHandler,
         0,
         &GUID_46aca899_50f6_4a46_a9e3_273705ca4914,
         a3);
  if ( v9 != -2147024891 )
  {
    if ( v9 >= 0 )
    {
      wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15);
      v9 = 0;
      goto LABEL_9;
    }
    v10 = (unsigned int)v9;
    v11 = 131;
    goto LABEL_7;
  }
  v9 = -2147024891;
LABEL_9:
  wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>((__int64 *)v14);
  CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::~CoCreateInstanceAsSystem((CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem *)v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800185b4  mov     [rsp+arg_0], rbx
0x1800185b9  push    rdi
0x1800185ba  sub     rsp, 1A0h
0x1800185c1  mov     rax, cs:__security_cookie
0x1800185c8  xor     rax, rsp
0x1800185cb  mov     [rsp+1A8h+var_18], rax
0x1800185d3  lea     rcx, [rsp+1A8h+var_168]; struct wil::details::IFailureCallback *
0x1800185d8  mov     qword ptr [r8], 0
0x1800185df  mov     rdi, r8
0x1800185e2  call    ??0?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800185e7  lea     rax, ??_7CoCreateInstanceAsSystem@CoCreateInstanceAsSystemTelemetry@@6B@; const CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::`vftable'
0x1800185ee  lea     rcx, [rsp+1A8h+var_168]; this
0x1800185f3  mov     [rsp+1A8h+var_168], rax
0x1800185f8  call    ?StartActivity@CoCreateInstanceAsSystem@CoCreateInstanceAsSystemTelemetry@@QEAAXXZ; CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::StartActivity(void)
0x1800185fd  lea     rax, [rsp+1A8h+var_178]
0x180018602  mov     [rsp+1A8h+var_178], 0
0x18001860b  mov     [rsp+1A8h+var_180], rax; LPVOID *
0x180018610  call    CoCreateCOMTaskServerObject
0x180018615  mov     ebx, eax
0x180018617  test    eax, eax
0x180018619  jns     short loc_180018625
0x18001861b  mov     r9d, eax
0x18001861e  mov     edx, 7Fh
0x180018623  jmp     short loc_180018667
0x180018625  mov     rcx, [rsp+1A8h+var_178]
0x18001862a  lea     r9, _GUID_46aca899_50f6_4a46_a9e3_273705ca4914
0x180018631  xor     r8d, r8d
0x180018634  mov     qword ptr [rsp+1A8h+var_188], rdi; int
0x180018639  lea     rdx, CLSID_PicturePasswordEnrollmentHandler
0x180018640  mov     rax, [rcx]
0x180018643  mov     rax, [rax+18h]
0x180018647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001864c  mov     ebx, eax
0x18001864e  mov     eax, 80070005h
0x180018653  cmp     ebx, eax
0x180018655  jnz     short loc_18001865B
0x180018657  mov     ebx, eax
0x180018659  jmp     short loc_180018689
0x18001865b  test    ebx, ebx
0x18001865d  jns     short loc_18001867D
0x18001865f  mov     r9d, ebx; char *
0x180018662  mov     edx, 83h; void *
0x180018667  mov     rcx, [rsp+1A8h]; this
0x18001866f  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180018676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001867b  jmp     short loc_180018689
0x18001867d  lea     rcx, [rsp+1A8h+var_168]
0x180018682  call    ?Stop@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180018687  xor     ebx, ebx
0x180018689  lea     rcx, [rsp+1A8h+var_178]
0x18001868e  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x180018693  lea     rcx, [rsp+1A8h+var_168]; this
0x180018698  call    ??1CoCreateInstanceAsSystem@CoCreateInstanceAsSystemTelemetry@@QEAA@XZ; CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::~CoCreateInstanceAsSystem(void)
0x18001869d  mov     eax, ebx
0x18001869f  mov     rcx, [rsp+1A8h+var_18]
0x1800186a7  xor     rcx, rsp; StackCookie
0x1800186aa  call    __security_check_cookie
0x1800186af  mov     rbx, [rsp+1A8h+arg_0]
0x1800186b7  add     rsp, 1A0h
0x1800186be  pop     rdi
0x1800186bf  retn
```
