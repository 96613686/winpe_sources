# CallerIdentity::GetCoreWindowHandleForCurrentThread(HWND__ * *)

- ea: `0x18007b860`
- end: `0x18007b932`
- name: `?GetCoreWindowHandleForCurrentThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002cfcc`

## callees

- `0x18007b71c`
- `0x18007b860`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b8cf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b8cf`
- `combase!__imp_RoGetDesignMode` at `0x18007b887`
- `combase!__imp_RoGetDesignMode` at `0x18007b887`
- `combase!__imp_RoGetDesignModeV2` at `0x18007b89e`
- `combase!__imp_RoGetDesignModeV2` at `0x18007b89e`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCoreWindowHandleForCurrentThread(CallerIdentity *this, HWND *a2)
{
  CallerIdentity *v3; // rcx
  void **v4; // r8
  HRESULT CoreWindowForCurrentThread; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  struct _GUID ppv; // [rsp+40h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  ppv.Data1 = 0;
  RoGetDesignMode(&ppv, a2);
  if ( !ppv.Data1 || (*(_DWORD *)ppv.Data4 = 0, RoGetDesignModeV2(ppv.Data4), *(_DWORD *)ppv.Data4) )
  {
    *(_QWORD *)&ppv.Data1 = 0;
    CoreWindowForCurrentThread = CallerIdentity::GetCoreWindowForCurrentThread(v3, &ppv, v4);
  }
  else
  {
    *(_QWORD *)&ppv.Data1 = 0;
    CoreWindowForCurrentThread = CoCreateInstance(
                                   &GUID_958a6fb5_dcb2_4faf_aafd_7fb054ad1a3b,
                                   0,
                                   3u,
                                   &GUID_a656e803_4059_4a4c_a5b8_0d0de2c809fb,
                                   (LPVOID *)&ppv);
  }
  v6 = CoreWindowForCurrentThread;
  if ( CoreWindowForCurrentThread >= 0 )
    v6 = (*(__int64 (__fastcall **)(_QWORD, CallerIdentity *))(**(_QWORD **)&ppv.Data1 + 24LL))(
           *(_QWORD *)&ppv.Data1,
           this);
  v7 = *(_QWORD *)&ppv.Data1;
  if ( *(_QWORD *)&ppv.Data1 )
  {
    *(_QWORD *)&ppv.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x18007b860  mov     [rsp-8+arg_10], rbx
0x18007b865  mov     [rsp-8+arg_18], rdi
0x18007b86a  push    rbp
0x18007b86b  mov     rbp, rsp
0x18007b86e  sub     rsp, 30h
0x18007b872  mov     rdi, rcx
0x18007b875  mov     qword ptr [rcx], 0
0x18007b87c  lea     rcx, [rbp+arg_0]
0x18007b880  mov     [rbp+arg_0.Data1], 0
0x18007b887  call    cs:__imp_RoGetDesignMode
0x18007b88d  cmp     [rbp+arg_0.Data1], 0
0x18007b891  jz      short loc_18007B8D7
0x18007b893  lea     rcx, [rbp+arg_0.Data4]
0x18007b897  mov     dword ptr [rbp+arg_0.Data4], 0
0x18007b89e  call    cs:__imp_RoGetDesignModeV2
0x18007b8a4  cmp     dword ptr [rbp+arg_0.Data4], 0
0x18007b8a8  jnz     short loc_18007B8D7
0x18007b8aa  xor     edx, edx; pUnkOuter
0x18007b8ac  mov     qword ptr [rbp+arg_0.Data1], 0
0x18007b8b4  lea     rax, [rbp+arg_0]
0x18007b8b8  lea     r9, _GUID_a656e803_4059_4a4c_a5b8_0d0de2c809fb; riid
0x18007b8bf  mov     [rsp+30h+ppv], rax; ppv
0x18007b8c4  lea     rcx, _GUID_958a6fb5_dcb2_4faf_aafd_7fb054ad1a3b; rclsid
0x18007b8cb  lea     r8d, [rdx+3]; dwClsContext
0x18007b8cf  call    cs:__imp_CoCreateInstance
0x18007b8d5  jmp     short loc_18007B8E8
0x18007b8d7  lea     rdx, [rbp+arg_0]; struct _GUID *
0x18007b8db  mov     qword ptr [rbp+arg_0.Data1], 0
0x18007b8e3  call    ?GetCoreWindowForCurrentThread@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z; CallerIdentity::GetCoreWindowForCurrentThread(_GUID const &,void * *)
0x18007b8e8  mov     ebx, eax
0x18007b8ea  test    eax, eax
0x18007b8ec  js      short loc_18007B903
0x18007b8ee  mov     rcx, qword ptr [rbp+arg_0.Data1]
0x18007b8f2  mov     rdx, rdi
0x18007b8f5  mov     rax, [rcx]
0x18007b8f8  mov     rax, [rax+18h]
0x18007b8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b901  mov     ebx, eax
0x18007b903  mov     rcx, qword ptr [rbp+arg_0.Data1]
0x18007b907  test    rcx, rcx
0x18007b90a  jz      short loc_18007B920
0x18007b90c  mov     qword ptr [rbp+arg_0.Data1], 0
0x18007b914  mov     rax, [rcx]
0x18007b917  mov     rax, [rax+10h]
0x18007b91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b920  mov     rdi, [rsp+30h+arg_18]
0x18007b925  mov     eax, ebx
0x18007b927  mov     rbx, [rsp+30h+arg_10]
0x18007b92c  add     rsp, 30h
0x18007b930  pop     rbp
0x18007b931  retn
```
