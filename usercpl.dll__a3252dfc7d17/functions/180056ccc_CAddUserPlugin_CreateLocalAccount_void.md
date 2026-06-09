# CAddUserPlugin::_CreateLocalAccount(void)

- ea: `0x180056ccc`
- end: `0x180056ec8`
- name: `?_CreateLocalAccount@CAddUserPlugin@@AEAAJXZ`
- size: `508`
- prototype: `__int64 __fastcall(CAddUserPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180054d10`

## callees

- `0x180026218`
- `0x1800544c8`
- `0x180054710`
- `0x180054d20`
- `0x180056030`
- `0x180056158`
- `0x180056964`
- `0x180056ccc`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ddb`
- `OLEAUT32!__imp_SysFreeString` at `0x180056e21`
- `OLEAUT32!__imp_SysFreeString` at `0x180056e21`
- `ntdll!WinSqmIncrementDWORD` at `0x180056e36`
- `ntdll!WinSqmIncrementDWORD` at `0x180056e36`

## pseudocode

```c
__int64 __fastcall CAddUserPlugin::_CreateLocalAccount(CAddUserPlugin *this)
{
  int v2; // ebx
  __int64 v3; // r8
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v7; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v9[42]; // [rsp+40h] [rbp-C0h] BYREF

  v7 = 0;
  wil::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v9,
    (__int64)"AddLocalUserFlow");
  v9[0] = &TaskFlowTelemetry::AddLocalUserFlow::`vftable';
  TaskFlowTelemetry::AddLocalUserFlow::StartActivity((TaskFlowTelemetry::AddLocalUserFlow *)v9);
  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 10) + 88LL))(
         *((_QWORD *)this + 10),
         *((_QWORD *)this + 24),
         1,
         &v7);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 64LL))(v7, *((_QWORD *)this + 24));
    if ( v2 < 0 )
      goto LABEL_8;
    v3 = *((_QWORD *)this + 25);
    if ( v3 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64, _QWORD))(*(_QWORD *)v7 + 72LL))(
             v7,
             &Class,
             v3,
             *((_QWORD *)this + 26));
      if ( v2 < 0 )
        goto LABEL_8;
    }
    CoTaskMemFree(*((LPVOID *)this + 27));
    v4 = v7;
    *((_QWORD *)this + 27) = 0;
    bstrString = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v4 + 96LL))(v4, &bstrString);
    if ( v2 < 0 || (v2 = CoAllocString(bstrString, (unsigned __int16 **)this + 27), SysFreeString(bstrString), v2 < 0) )
    {
LABEL_8:
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 10) + 96LL))(*((_QWORD *)this + 10), v7, 0);
    }
    else
    {
      WinSqmIncrementDWORD(0, 8909, 1);
      TaskFlowTelemetry::UserAccountAddUserDialogLocalUserAdded();
    }
  }
  wil::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v9,
    (unsigned int)v2);
  v9[0] = &TaskFlowTelemetry::AddLocalUserFlow::`vftable';
  wil::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v9);
  wil::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v9);
  v5 = v7;
  if ( v7 )
  {
    v7 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180056ccc  mov     [rsp-8+arg_8], rbx
0x180056cd1  mov     [rsp-8+arg_10], rsi
0x180056cd6  push    rbp
0x180056cd7  push    rdi
0x180056cd8  push    r15
0x180056cda  lea     rbp, [rsp-0A0h]
0x180056ce2  sub     rsp, 1A0h
0x180056ce9  mov     rax, cs:__security_cookie
0x180056cf0  xor     rax, rsp
0x180056cf3  mov     [rbp+0B0h+var_20], rax
0x180056cfa  mov     rdi, rcx
0x180056cfd  mov     [rsp+1B0h+var_180], 0
0x180056d06  lea     rcx, [rsp+1B0h+var_170]
0x180056d0b  lea     rdx, aAddlocaluserfl; "AddLocalUserFlow"
0x180056d12  call    ??0?$ActivityBase@VTaskFlowLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180056d17  lea     r15, ??_7AddLocalUserFlow@TaskFlowTelemetry@@6B@; const TaskFlowTelemetry::AddLocalUserFlow::`vftable'
0x180056d1e  lea     rcx, [rsp+1B0h+var_170]; this
0x180056d23  mov     [rsp+1B0h+var_170], r15
0x180056d28  call    ?StartActivity@AddLocalUserFlow@TaskFlowTelemetry@@QEAAXXZ; TaskFlowTelemetry::AddLocalUserFlow::StartActivity(void)
0x180056d2d  mov     rbx, [rdi+50h]
0x180056d31  mov     rcx, [rsp+1B0h+var_180]
0x180056d36  mov     rax, [rbx]
0x180056d39  mov     rsi, [rax+58h]
0x180056d3d  test    rcx, rcx
0x180056d40  jz      short loc_180056D57
0x180056d42  mov     [rsp+1B0h+var_180], 0
0x180056d4b  mov     rax, [rcx]
0x180056d4e  mov     rax, [rax+10h]
0x180056d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d57  mov     rdx, [rdi+0C0h]
0x180056d5e  lea     r9, [rsp+1B0h+var_180]
0x180056d63  mov     r8d, 1
0x180056d69  mov     rcx, rbx
0x180056d6c  mov     rax, rsi
0x180056d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d74  mov     ebx, eax
0x180056d76  test    eax, eax
0x180056d78  js      loc_180056E5B
0x180056d7e  mov     rcx, [rsp+1B0h+var_180]
0x180056d83  mov     rdx, [rdi+0C0h]
0x180056d8a  mov     rax, [rcx]
0x180056d8d  mov     rax, [rax+40h]
0x180056d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d96  mov     ebx, eax
0x180056d98  test    eax, eax
0x180056d9a  js      loc_180056E43
0x180056da0  mov     r8, [rdi+0C8h]
0x180056da7  test    r8, r8
0x180056daa  jz      short loc_180056DD1
0x180056dac  mov     rcx, [rsp+1B0h+var_180]
0x180056db1  lea     rdx, Class
0x180056db8  mov     r9, [rdi+0D0h]
0x180056dbf  mov     rax, [rcx]
0x180056dc2  mov     rax, [rax+48h]
0x180056dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056dcb  mov     ebx, eax
0x180056dcd  test    eax, eax
0x180056dcf  js      short loc_180056E43
0x180056dd1  lea     rsi, [rdi+0D8h]
0x180056dd8  mov     rcx, [rsi]; pv
0x180056ddb  call    cs:__imp_CoTaskMemFree
0x180056de1  mov     rcx, [rsp+1B0h+var_180]
0x180056de6  lea     rdx, [rsp+1B0h+bstrString]
0x180056deb  mov     qword ptr [rsi], 0
0x180056df2  mov     [rsp+1B0h+bstrString], 0
0x180056dfb  mov     rax, [rcx]
0x180056dfe  mov     rax, [rax+60h]
0x180056e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e07  mov     ebx, eax
0x180056e09  test    eax, eax
0x180056e0b  js      short loc_180056E43
0x180056e0d  mov     rcx, [rsp+1B0h+bstrString]; unsigned __int16 *
0x180056e12  mov     rdx, rsi; unsigned __int16 **
0x180056e15  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x180056e1a  mov     rcx, [rsp+1B0h+bstrString]; bstrString
0x180056e1f  mov     ebx, eax
0x180056e21  call    cs:__imp_SysFreeString
0x180056e27  test    ebx, ebx
0x180056e29  js      short loc_180056E43
0x180056e2b  xor     ecx, ecx
0x180056e2d  mov     edx, 22CDh
0x180056e32  lea     r8d, [rcx+1]
0x180056e36  call    cs:__imp_WinSqmIncrementDWORD
0x180056e3c  call    ?UserAccountAddUserDialogLocalUserAdded@TaskFlowTelemetry@@SAXXZ; TaskFlowTelemetry::UserAccountAddUserDialogLocalUserAdded(void)
0x180056e41  jmp     short loc_180056E5B
0x180056e43  mov     rcx, [rdi+50h]
0x180056e47  xor     r8d, r8d
0x180056e4a  mov     rdx, [rsp+1B0h+var_180]
0x180056e4f  mov     rax, [rcx]
0x180056e52  mov     rax, [rax+60h]
0x180056e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e5b  mov     edx, ebx
0x180056e5d  lea     rcx, [rsp+1B0h+var_170]
0x180056e62  call    ?Stop@?$ActivityBase@VTaskFlowLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180056e67  lea     rcx, [rsp+1B0h+var_170]
0x180056e6c  mov     [rsp+1B0h+var_170], r15
0x180056e71  call    ?Destroy@?$ActivityBase@VTaskFlowLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180056e76  lea     rcx, [rsp+1B0h+var_170]
0x180056e7b  call    ??1?$ActivityBase@VTaskFlowLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TaskFlowLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180056e80  mov     rcx, [rsp+1B0h+var_180]
0x180056e85  test    rcx, rcx
0x180056e88  jz      short loc_180056E9F
0x180056e8a  mov     [rsp+1B0h+var_180], 0
0x180056e93  mov     rax, [rcx]
0x180056e96  mov     rax, [rax+10h]
0x180056e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e9f  mov     eax, ebx
0x180056ea1  mov     rcx, [rbp+0B0h+var_20]
0x180056ea8  xor     rcx, rsp; StackCookie
0x180056eab  call    __security_check_cookie
0x180056eb0  lea     r11, [rsp+1B0h+var_10]
0x180056eb8  mov     rbx, [r11+28h]
0x180056ebc  mov     rsi, [r11+30h]
0x180056ec0  mov     rsp, r11
0x180056ec3  pop     r15
0x180056ec5  pop     rdi
0x180056ec6  pop     rbp
0x180056ec7  retn
```
