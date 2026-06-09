# CUserManagementWizards::RunTaskFlow(TASK_FLOW_ID,HWND__ *,IUserManager *)

- ea: `0x180023990`
- end: `0x180023a9e`
- name: `?RunTaskFlow@CUserManagementWizards@@UEAAJW4TASK_FLOW_ID@@PEAUHWND__@@PEAUIUserManager@@@Z`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023990`
- `0x1800606f0`
- `0x180067360`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023a22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023a22`
- `DUI70!UnInitProcessPriv` at `0x180023a8d`
- `DUI70!UnInitProcessPriv` at `0x180023a8d`
- `DUI70!UnInitThread` at `0x180023a80`
- `DUI70!UnInitThread` at `0x180023a80`
- `DUI70!InitThread` at `0x1800239cd`
- `DUI70!InitThread` at `0x1800239cd`
- `DUI70!InitProcessPriv` at `0x1800239b8`
- `DUI70!InitProcessPriv` at `0x1800239b8`

## pseudocode

```c
__int64 __fastcall CUserManagementWizards::RunTaskFlow(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdi
  HRESULT inited; // ebx
  LPVOID v8; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF

  v5 = a3;
  LOBYTE(a3) = 1;
  inited = InitProcessPriv(14, &_ImageBase, a3);
  if ( inited >= 0 )
  {
    inited = InitThread(65538);
    if ( inited >= 0 )
    {
      inited = CNavigateButton::Register();
      if ( inited >= 0 )
      {
        inited = UserTile::Register();
        if ( inited >= 0 )
        {
          ppv = 0;
          inited = CoCreateInstance(&stru_1800861F8, 0, 1u, &GUID_eb1dfc14_d0bc_49d7_b2f5_95ce28690d05, &ppv);
          if ( inited >= 0 )
          {
            inited = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, a4, a2);
            if ( inited >= 0 )
              inited = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 32LL))(ppv, v5);
          }
          v8 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
          }
        }
      }
      UnInitThread(v8);
    }
    UnInitProcessPriv(&_ImageBase);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180023990  push    rbx
0x180023992  push    rbp
0x180023993  push    rsi
0x180023994  push    rdi
0x180023995  sub     rsp, 48h
0x180023999  mov     rsi, r9
0x18002399c  mov     byte ptr [rsp+68h+ppv], 1
0x1800239a1  mov     r9b, 1
0x1800239a4  mov     rdi, r8
0x1800239a7  mov     ebp, edx
0x1800239a9  mov     r8b, r9b
0x1800239ac  lea     rdx, __ImageBase
0x1800239b3  mov     ecx, 0Eh
0x1800239b8  call    cs:__imp_InitProcessPriv
0x1800239be  mov     ebx, eax
0x1800239c0  test    eax, eax
0x1800239c2  js      loc_180023A93
0x1800239c8  mov     ecx, 10002h
0x1800239cd  call    cs:__imp_InitThread
0x1800239d3  mov     ebx, eax
0x1800239d5  test    eax, eax
0x1800239d7  js      loc_180023A86
0x1800239dd  call    ?Register@CNavigateButton@@SAJXZ; CNavigateButton::Register(void)
0x1800239e2  mov     ebx, eax
0x1800239e4  test    eax, eax
0x1800239e6  js      loc_180023A80
0x1800239ec  call    ?Register@UserTile@@SAJXZ; UserTile::Register(void)
0x1800239f1  mov     ebx, eax
0x1800239f3  test    eax, eax
0x1800239f5  js      loc_180023A80
0x1800239fb  xor     edx, edx; pUnkOuter
0x1800239fd  mov     [rsp+68h+var_38], 0
0x180023a06  lea     rax, [rsp+68h+var_38]
0x180023a0b  lea     r9, _GUID_eb1dfc14_d0bc_49d7_b2f5_95ce28690d05; riid
0x180023a12  mov     [rsp+68h+ppv], rax; ppv
0x180023a17  lea     rcx, stru_1800861F8; rclsid
0x180023a1e  lea     r8d, [rdx+1]; dwClsContext
0x180023a22  call    cs:__imp_CoCreateInstance
0x180023a28  mov     ebx, eax
0x180023a2a  test    eax, eax
0x180023a2c  js      short loc_180023A61
0x180023a2e  mov     rcx, [rsp+68h+var_38]
0x180023a33  mov     r8d, ebp
0x180023a36  mov     rdx, rsi
0x180023a39  mov     rax, [rcx]
0x180023a3c  mov     rax, [rax+18h]
0x180023a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a45  mov     ebx, eax
0x180023a47  test    eax, eax
0x180023a49  js      short loc_180023A61
0x180023a4b  mov     rcx, [rsp+68h+var_38]
0x180023a50  mov     rdx, rdi
0x180023a53  mov     rax, [rcx]
0x180023a56  mov     rax, [rax+20h]
0x180023a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a5f  mov     ebx, eax
0x180023a61  mov     rcx, [rsp+68h+var_38]
0x180023a66  test    rcx, rcx
0x180023a69  jz      short loc_180023A80
0x180023a6b  mov     [rsp+68h+var_38], 0
0x180023a74  mov     rax, [rcx]
0x180023a77  mov     rax, [rax+10h]
0x180023a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a80  call    cs:__imp_UnInitThread
0x180023a86  lea     rcx, __ImageBase
0x180023a8d  call    cs:__imp_UnInitProcessPriv
0x180023a93  mov     eax, ebx
0x180023a95  add     rsp, 48h
0x180023a99  pop     rdi
0x180023a9a  pop     rsi
0x180023a9b  pop     rbp
0x180023a9c  pop     rbx
0x180023a9d  retn
```
