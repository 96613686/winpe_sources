# CInternetTime::_OnCommandInternetCfgPage(HWND__ *,unsigned __int64,__int64)

- ea: `0x180015ca8`
- end: `0x180015ece`
- name: `?_OnCommandInternetCfgPage@CInternetTime@@AEAA_JPEAUHWND__@@_K_J@Z`
- size: `550`
- prototype: `__int64 __fastcall(CInternetTime *__hidden this, HWND hDlg, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016480`

## callees

- `0x180004da4`
- `0x1800085b8`
- `0x1800092c4`
- `0x18000c220`
- `0x180013bc0`
- `0x180013bec`
- `0x180015014`
- `0x1800150d4`
- `0x180015ca8`
- `0x180016010`
- `0x1800160a8`
- `0x180016384`
- `0x18001be54`
- `0x18001bf20`
- `0x18001cd38`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `USER32!GetWindowTextW` at `0x180015d9c`
- `USER32!GetWindowTextW` at `0x180015d9c`
- `USER32!EndDialog` at `0x180015e0f`
- `USER32!EndDialog` at `0x180015e8b`
- `USER32!EndDialog` at `0x180015e0f`
- `USER32!EndDialog` at `0x180015e8b`
- `USER32!SendMessageW` at `0x180015db0`
- `USER32!SendMessageW` at `0x180015db0`

## string_xrefs

- `0x180015d19`: `SynchronizeWithAnInternetTimeServer_UpdateNow`

## pseudocode

```c
__int64 __fastcall CInternetTime::_OnCommandInternetCfgPage(CDateTimeOm **this, HWND hDlg, int a3, HWND a4)
{
  unsigned int updated; // eax
  int v8; // eax
  CDateTimeOm *v9; // rcx
  int v10; // eax
  unsigned int v11; // esi
  int String[128]; // [rsp+20h] [rbp-E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  switch ( (unsigned __int16)a3 )
  {
    case 1u:
      wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        String,
        "SynchronizeWithAnInternetTimeServer_OKButton");
      *(_QWORD *)String = &TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::`vftable';
      TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::StartActivity((TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton *)String);
      v10 = CDateTimeOm::SaveInternetTime(this[1]);
      v11 = v10;
      if ( v10 >= 0 )
      {
        CDateTimeOm::StopInternetTimeSync(this[1]);
        EndDialog(hDlg, 1);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x22A,
          (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
          (const char *)(unsigned int)v10,
          String[0]);
        ShowErrorMessage(hDlg, 54);
      }
      wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        String,
        v11);
      TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::~SynchronizeWithAnInternetTimeServer_OKButton((TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton *)String);
      break;
    case 2u:
      CDateTimeOm::StopInternetTimeSync(this[1]);
      EndDialog(hDlg, *((int *)this + 8));
      break;
    case 0x334u:
      if ( !HIWORD(a3) )
        CInternetTime::_OnToggleFeature((CInternetTime *)this, hDlg);
      break;
    case 0x335u:
      if ( HIWORD(a3) == 1 )
      {
        CInternetTime::_ResetServer((CInternetTime *)this, a4);
      }
      else if ( HIWORD(a3) == 5 || HIWORD(a3) == 768 )
      {
        memset_0(String, 0, sizeof(String));
        GetWindowTextW(a4, (LPWSTR)String, 256);
        v8 = SendMessageW(a4, 0x147u, 0, 0);
        v9 = this[1];
        *(_DWORD *)(*((_QWORD *)v9 + 61) + 1068LL) = v8;
        CDateTimeOm::set_W32TimeServer(v9, (const unsigned __int16 *)String);
      }
      break;
    default:
      if ( (unsigned __int16)a3 == 826 && !HIWORD(a3) )
      {
        wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
          String,
          "SynchronizeWithAnInternetTimeServer_UpdateNow");
        *(_QWORD *)String = &TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::`vftable';
        TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::StartActivity((TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow *)String);
        updated = CInternetTime::_OnUpdateButton((CInternetTime *)this);
        wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
          String,
          updated);
        TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::~SynchronizeWithAnInternetTimeServer_UpdateNow((TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow *)String);
      }
      break;
  }
  return 1;
}

```

## disassembly

```asm
0x180015ca8  mov     [rsp-8+arg_10], rbx
0x180015cad  push    rbp
0x180015cae  push    rsi
0x180015caf  push    rdi
0x180015cb0  lea     rbp, [rsp-130h]
0x180015cb8  sub     rsp, 230h
0x180015cbf  mov     rax, cs:__security_cookie
0x180015cc6  xor     rax, rsp
0x180015cc9  mov     [rbp+140h+var_20], rax
0x180015cd0  mov     rdi, rdx
0x180015cd3  mov     rbx, rcx
0x180015cd6  mov     rdx, r8
0x180015cd9  movzx   ecx, r8w
0x180015cdd  shr     rdx, 10h
0x180015ce1  mov     rsi, r9
0x180015ce4  sub     ecx, 1
0x180015ce7  jz      loc_180015E1A
0x180015ced  sub     ecx, 1
0x180015cf0  jz      loc_180015DFF
0x180015cf6  sub     ecx, 332h
0x180015cfc  jz      loc_180015DE6
0x180015d02  sub     ecx, 1
0x180015d05  jz      short loc_180015D63
0x180015d07  cmp     ecx, 5
0x180015d0a  jnz     loc_180015EA7
0x180015d10  test    dx, dx
0x180015d13  jnz     loc_180015EA7
0x180015d19  lea     rdx, aSynchronizewit_1; "SynchronizeWithAnInternetTimeServer_Upd"...
0x180015d20  lea     rcx, [rsp+240h+String]
0x180015d25  call    ??0?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015d2a  lea     rax, ??_7SynchronizeWithAnInternetTimeServer_UpdateNow@TimeDateTraceLoggingTelemetry@@6B@; const TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::`vftable'
0x180015d31  lea     rcx, [rsp+240h+String]; this
0x180015d36  mov     qword ptr [rsp+240h+String], rax
0x180015d3b  call    ?StartActivity@SynchronizeWithAnInternetTimeServer_UpdateNow@TimeDateTraceLoggingTelemetry@@QEAAXXZ; TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::StartActivity(void)
0x180015d40  mov     rcx, rbx; this
0x180015d43  call    ?_OnUpdateButton@CInternetTime@@AEAAJXZ; CInternetTime::_OnUpdateButton(void)
0x180015d48  mov     edx, eax
0x180015d4a  lea     rcx, [rsp+240h+String]
0x180015d4f  call    ?Stop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180015d54  lea     rcx, [rsp+240h+String]; this
0x180015d59  call    ??1SynchronizeWithAnInternetTimeServer_UpdateNow@TimeDateTraceLoggingTelemetry@@QEAA@XZ; TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_UpdateNow::~SynchronizeWithAnInternetTimeServer_UpdateNow(void)
0x180015d5e  jmp     loc_180015EA7
0x180015d63  movzx   ecx, dx
0x180015d66  sub     ecx, 1
0x180015d69  jz      short loc_180015DD6
0x180015d6b  sub     ecx, 4
0x180015d6e  jz      short loc_180015D7C
0x180015d70  cmp     ecx, 2FBh
0x180015d76  jnz     loc_180015EA7
0x180015d7c  xor     edx, edx; Val
0x180015d7e  lea     rcx, [rsp+240h+String]; void *
0x180015d83  mov     r8d, 200h; Size
0x180015d89  call    memset_0
0x180015d8e  mov     r8d, 100h; nMaxCount
0x180015d94  lea     rdx, [rsp+240h+String]; lpString
0x180015d99  mov     rcx, rsi; hWnd
0x180015d9c  call    cs:__imp_GetWindowTextW
0x180015da2  xor     r9d, r9d; lParam
0x180015da5  xor     r8d, r8d; wParam
0x180015da8  mov     edx, 147h; Msg
0x180015dad  mov     rcx, rsi; hWnd
0x180015db0  call    cs:__imp_SendMessageW
0x180015db6  mov     rcx, [rbx+8]; this
0x180015dba  mov     rdx, [rcx+1E8h]
0x180015dc1  mov     [rdx+42Ch], eax
0x180015dc7  lea     rdx, [rsp+240h+String]; unsigned __int16 *
0x180015dcc  call    ?set_W32TimeServer@CDateTimeOm@@QEAAJPEBG@Z; CDateTimeOm::set_W32TimeServer(ushort const *)
0x180015dd1  jmp     loc_180015EA7
0x180015dd6  mov     rdx, rsi; HWND
0x180015dd9  mov     rcx, rbx; this
0x180015ddc  call    ?_ResetServer@CInternetTime@@AEAAJPEAUHWND__@@@Z; CInternetTime::_ResetServer(HWND__ *)
0x180015de1  jmp     loc_180015EA7
0x180015de6  test    dx, dx
0x180015de9  jnz     loc_180015EA7
0x180015def  mov     rdx, rdi; hDlg
0x180015df2  mov     rcx, rbx; this
0x180015df5  call    ?_OnToggleFeature@CInternetTime@@AEAAJPEAUHWND__@@@Z; CInternetTime::_OnToggleFeature(HWND__ *)
0x180015dfa  jmp     loc_180015EA7
0x180015dff  mov     rcx, [rbx+8]; this
0x180015e03  call    ?StopInternetTimeSync@CDateTimeOm@@QEAAXXZ; CDateTimeOm::StopInternetTimeSync(void)
0x180015e08  movsxd  rdx, dword ptr [rbx+20h]; nResult
0x180015e0c  mov     rcx, rdi; hDlg
0x180015e0f  call    cs:__imp_EndDialog
0x180015e15  jmp     loc_180015EA7
0x180015e1a  lea     rdx, aSynchronizewit_0; "SynchronizeWithAnInternetTimeServer_OKB"...
0x180015e21  lea     rcx, [rsp+240h+String]
0x180015e26  call    ??0?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015e2b  lea     rax, ??_7SynchronizeWithAnInternetTimeServer_OKButton@TimeDateTraceLoggingTelemetry@@6B@; const TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::`vftable'
0x180015e32  lea     rcx, [rsp+240h+String]; this
0x180015e37  mov     qword ptr [rsp+240h+String], rax; int
0x180015e3c  call    ?StartActivity@SynchronizeWithAnInternetTimeServer_OKButton@TimeDateTraceLoggingTelemetry@@QEAAXXZ; TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::StartActivity(void)
0x180015e41  mov     rcx, [rbx+8]; this
0x180015e45  call    ?SaveInternetTime@CDateTimeOm@@QEAAJXZ; CDateTimeOm::SaveInternetTime(void)
0x180015e4a  mov     esi, eax
0x180015e4c  test    eax, eax
0x180015e4e  jns     short loc_180015E7A
0x180015e50  mov     rcx, [rbp+148h]; this
0x180015e57  lea     r8, aShellCplsUtcIn_0; "shell\\cpls\\utc\\inettime.cpp"
0x180015e5e  mov     r9d, eax; char *
0x180015e61  mov     edx, 22Ah; void *
0x180015e66  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015e6b  mov     edx, 36h ; '6'; int
0x180015e70  mov     rcx, rdi; HWND
0x180015e73  call    ?ShowErrorMessage@@YAXPEAUHWND__@@H@Z; ShowErrorMessage(HWND__ *,int)
0x180015e78  jmp     short loc_180015E91
0x180015e7a  mov     rcx, [rbx+8]; this
0x180015e7e  call    ?StopInternetTimeSync@CDateTimeOm@@QEAAXXZ; CDateTimeOm::StopInternetTimeSync(void)
0x180015e83  mov     edx, 1; nResult
0x180015e88  mov     rcx, rdi; hDlg
0x180015e8b  call    cs:__imp_EndDialog
0x180015e91  mov     edx, esi
0x180015e93  lea     rcx, [rsp+240h+String]
0x180015e98  call    ?Stop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180015e9d  lea     rcx, [rsp+240h+String]; this
0x180015ea2  call    ??1SynchronizeWithAnInternetTimeServer_OKButton@TimeDateTraceLoggingTelemetry@@QEAA@XZ; TimeDateTraceLoggingTelemetry::SynchronizeWithAnInternetTimeServer_OKButton::~SynchronizeWithAnInternetTimeServer_OKButton(void)
0x180015ea7  mov     eax, 1
0x180015eac  mov     rcx, [rbp+140h+var_20]
0x180015eb3  xor     rcx, rsp; StackCookie
0x180015eb6  call    __security_check_cookie
0x180015ebb  mov     rbx, [rsp+240h+arg_10]
0x180015ec3  add     rsp, 230h
0x180015eca  pop     rdi
0x180015ecb  pop     rsi
0x180015ecc  pop     rbp
0x180015ecd  retn
```
