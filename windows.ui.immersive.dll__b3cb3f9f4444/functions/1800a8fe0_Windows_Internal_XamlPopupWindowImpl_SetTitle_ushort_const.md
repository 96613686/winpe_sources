# Windows::Internal::XamlPopupWindowImpl::SetTitle(ushort const *)

- ea: `0x1800a8fe0`
- end: `0x1800a912c`
- name: `?SetTitle@XamlPopupWindowImpl@Internal@Windows@@UEAAJPEBG@Z`
- size: `332`
- prototype: `__int64 __fastcall(Windows::Internal::XamlPopupWindowImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b5b8`
- `0x180034e0c`
- `0x18003729c`
- `0x1800a5390`
- `0x1800a8fe0`
- `0x1800ed010`

## import_xrefs

- `USER32!SetWindowTextW` at `0x1800a8ff6`
- `USER32!SetWindowTextW` at `0x1800a904b`
- `USER32!SetWindowTextW` at `0x1800a8ff6`
- `USER32!SetWindowTextW` at `0x1800a904b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a907e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a907e`

## pseudocode

```c
__int64 __fastcall Windows::Internal::XamlPopupWindowImpl::SetTitle(
        Windows::Internal::XamlPopupWindowImpl *this,
        const unsigned __int16 *a2)
{
  HWND v3; // rax
  bool v4; // zf
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // edi
  __int64 v8; // rdx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  int v13[2]; // [rsp+20h] [rbp-18h] BYREF
  LPCWSTR *p_lpString; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpString; // [rsp+48h] [rbp+10h] BYREF

  lpString = a2;
  SetWindowTextW(*((HWND *)this + 7), a2);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 88LL))(*((_QWORD *)this + 4)) == 1 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4)) )
    {
      v3 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 128LL))(*((_QWORD *)this + 4));
      if ( v3 )
        SetWindowTextW(v3, lpString);
    }
  }
  CoTaskMemFree(*((LPVOID *)this + 24));
  v4 = lpString == 0;
  *((_QWORD *)this + 24) = 0;
  if ( !v4 )
  {
    CoTaskMemFree(0);
    v7 = _AllocString<CTCoAllocPolicy>(v6, v5, lpString, (_QWORD *)this + 24);
    if ( v7 < 0 )
    {
      v8 = 1176;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\xamlpopupwindowimpl.cpp",
        (const char *)(unsigned int)v7,
        v13[0]);
      return (unsigned int)v7;
    }
  }
  v10 = *((_QWORD *)this + 36);
  p_lpString = &lpString;
  *(_QWORD *)v13 = this;
  v7 = CreationThreadDispatcher::RunSync__lambda_a70ba324e342efb7ddaf68098acf6d61___(v10, v13);
  if ( v7 < 0 )
  {
    v8 = 1185;
    goto LABEL_8;
  }
  if ( !*((_QWORD *)this + 48) )
    return 0;
  v11 = Windows::Internal::XamlPopupWindowImpl::_EnsureProxy(this, 1);
  v12 = v11;
  if ( v11 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A6,
    (unsigned int)"shell\\windowsuiimmersive\\popup\\xamlpopupwindowimpl.cpp",
    (const char *)(unsigned int)v11,
    v13[0]);
  return v12;
}

```

## disassembly

```asm
0x1800a8fe0  mov     [rsp+arg_0], rbx
0x1800a8fe5  mov     [rsp+lpString], rdx
0x1800a8fea  push    rdi
0x1800a8feb  sub     rsp, 30h
0x1800a8fef  mov     rbx, rcx
0x1800a8ff2  mov     rcx, [rcx+38h]; hWnd
0x1800a8ff6  call    cs:__imp_SetWindowTextW
0x1800a8ffd  nop     dword ptr [rax+rax+00h]
0x1800a9002  mov     rcx, [rbx+20h]
0x1800a9006  mov     rax, [rcx]
0x1800a9009  mov     rax, [rax+58h]
0x1800a900d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9012  cmp     eax, 1
0x1800a9015  jnz     short loc_1800A9057
0x1800a9017  mov     rcx, [rbx+20h]
0x1800a901b  mov     rax, [rcx]
0x1800a901e  mov     rax, [rax+78h]
0x1800a9022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9027  test    al, al
0x1800a9029  jz      short loc_1800A9057
0x1800a902b  mov     rcx, [rbx+20h]
0x1800a902f  mov     rax, [rcx]
0x1800a9032  mov     rax, [rax+80h]
0x1800a9039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a903e  test    rax, rax
0x1800a9041  jz      short loc_1800A9057
0x1800a9043  mov     rdx, [rsp+38h+lpString]; lpString
0x1800a9048  mov     rcx, rax; hWnd
0x1800a904b  call    cs:__imp_SetWindowTextW
0x1800a9052  nop     dword ptr [rax+rax+00h]
0x1800a9057  lea     rdi, [rbx+0C0h]
0x1800a905e  mov     rcx, [rdi]; pv
0x1800a9061  call    cs:__imp_CoTaskMemFree
0x1800a9068  nop     dword ptr [rax+rax+00h]
0x1800a906d  cmp     [rsp+38h+lpString], 0
0x1800a9073  mov     qword ptr [rdi], 0
0x1800a907a  jz      short loc_1800A90BA
0x1800a907c  xor     ecx, ecx; pv
0x1800a907e  call    cs:__imp_CoTaskMemFree
0x1800a9085  nop     dword ptr [rax+rax+00h]
0x1800a908a  mov     r8, [rsp+38h+lpString]
0x1800a908f  mov     r9, rdi
0x1800a9092  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800a9097  mov     edi, eax
0x1800a9099  test    eax, eax
0x1800a909b  jns     short loc_1800A90BA
0x1800a909d  mov     edx, 498h; void *
0x1800a90a2  mov     rcx, [rsp+38h]; this
0x1800a90a7  lea     r8, aShellWindowsui_15; "shell\\windowsuiimmersive\\popup\\xamlp"...
0x1800a90ae  mov     r9d, edi; char *
0x1800a90b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a90b6  mov     eax, edi
0x1800a90b8  jmp     short loc_1800A9120
0x1800a90ba  mov     rcx, [rbx+120h]
0x1800a90c1  lea     rax, [rsp+38h+lpString]
0x1800a90c6  lea     rdx, [rsp+38h+var_18]
0x1800a90cb  mov     [rsp+38h+var_10], rax
0x1800a90d0  mov     qword ptr [rsp+38h+var_18], rbx; int
0x1800a90d5  call    CreationThreadDispatcher__RunSync__lambda_a70ba324e342efb7ddaf68098acf6d61___
0x1800a90da  mov     edi, eax
0x1800a90dc  test    eax, eax
0x1800a90de  jns     short loc_1800A90E7
0x1800a90e0  mov     edx, 4A1h
0x1800a90e5  jmp     short loc_1800A90A2
0x1800a90e7  cmp     qword ptr [rbx+180h], 0
0x1800a90ef  jz      short loc_1800A911E
0x1800a90f1  mov     dl, 1; bool
0x1800a90f3  mov     rcx, rbx; this
0x1800a90f6  call    ?_EnsureProxy@XamlPopupWindowImpl@Internal@Windows@@AEAAJ_N@Z; Windows::Internal::XamlPopupWindowImpl::_EnsureProxy(bool)
0x1800a90fb  mov     ebx, eax
0x1800a90fd  test    eax, eax
0x1800a90ff  jns     short loc_1800A911E
0x1800a9101  mov     rcx, [rsp+38h]; this
0x1800a9106  lea     r8, aShellWindowsui_15; "shell\\windowsuiimmersive\\popup\\xamlp"...
0x1800a910d  mov     r9d, eax; char *
0x1800a9110  mov     edx, 4A6h; void *
0x1800a9115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a911a  mov     eax, ebx
0x1800a911c  jmp     short loc_1800A9120
0x1800a911e  xor     eax, eax
0x1800a9120  mov     rbx, [rsp+38h+arg_0]
0x1800a9125  add     rsp, 30h
0x1800a9129  pop     rdi
0x1800a912a  retn
```
