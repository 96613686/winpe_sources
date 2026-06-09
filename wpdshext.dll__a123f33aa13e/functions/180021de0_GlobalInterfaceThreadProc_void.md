# GlobalInterfaceThreadProc(void *)

- ea: `0x180021de0`
- end: `0x180022022`
- name: `?GlobalInterfaceThreadProc@@YAKPEAX@Z`
- size: `578`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180021de0`
- `0x180022028`
- `0x18002ff5c`
- `0x180078010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180021e48`
- `KERNEL32!SetEvent` at `0x180021fc5`
- `KERNEL32!SetEvent` at `0x180021e48`
- `KERNEL32!SetEvent` at `0x180021fc5`
- `KERNEL32!WaitForMultipleObjects` at `0x180021e6d`
- `KERNEL32!WaitForMultipleObjects` at `0x180021e6d`
- `ole32!CoUninitialize` at `0x180022012`
- `ole32!CoUninitialize` at `0x180022012`
- `ole32!CoCreateInstance` at `0x180021eb5`
- `ole32!CoCreateInstance` at `0x180021ee0`
- `ole32!CoCreateInstance` at `0x180021eb5`
- `ole32!CoCreateInstance` at `0x180021ee0`
- `ole32!CoInitializeEx` at `0x180021df5`
- `ole32!CoInitializeEx` at `0x180021df5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GlobalInterfaceThreadProc(LPVOID lpThreadParameter)
{
  HRESULT v2; // eax
  DWORD v3; // eax
  struct IPortableDeviceValues *v4; // rbx
  int ClientInfo; // eax
  int v6; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-10h] BYREF
  int v9; // [rsp+60h] [rbp+20h] BYREF
  LPVOID v10; // [rsp+68h] [rbp+28h] BYREF
  struct IPortableDeviceValues *v11; // [rsp+70h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+38h] BYREF

  v2 = CoInitializeEx(0, 4u);
  if ( v2 >= 0 )
  {
    *((_DWORD *)lpThreadParameter + 14) = 1;
    SetEvent(*((HANDLE *)lpThreadParameter + 4));
    Handles[0] = *((HANDLE *)lpThreadParameter + 3);
    Handles[1] = *((HANDLE *)lpThreadParameter + 5);
    while ( 1 )
    {
      v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !v3 )
        break;
      if ( v3 == 1 )
      {
        v10 = 0;
        v4 = 0;
        v11 = 0;
        ppv = 0;
        v9 = 0;
        *((_DWORD *)lpThreadParameter + 20) = 0;
        if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0
          && CoCreateInstance(&CLSID_PortableDeviceFTM, 0, 1u, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &v10) >= 0 )
        {
          ClientInfo = GetClientInfo(*((_DWORD *)g_pDeviceCache + 15), &v11);
          v4 = v11;
          if ( ClientInfo >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IPortableDeviceValues *))(*(_QWORD *)v10 + 24LL))(
                   v10,
                   **((_QWORD **)lpThreadParameter + 8),
                   v11);
            *((_DWORD *)lpThreadParameter + 20) = v6;
            if ( v6 == -2147024891
              && ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))v4->lpVtbl->SetUnsignedIntegerValue)(
                   v4,
                   &WPD_CLIENT_DESIRED_ACCESS,
                   0x80000000LL) >= 0
              && ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))v4->lpVtbl->SetUnsignedIntegerValue)(
                   v4,
                   &WPD_CLIENT_SHARE_MODE,
                   1) >= 0 )
            {
              *((_DWORD *)lpThreadParameter + 20) = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IPortableDeviceValues *))(*(_QWORD *)v10 + 24LL))(
                                                      v10,
                                                      **((_QWORD **)lpThreadParameter + 8),
                                                      v4);
            }
            if ( *((int *)lpThreadParameter + 20) >= 0
              && (*(int (__fastcall **)(LPVOID, LPVOID, GUID *, int *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   v10,
                   &IID_IPortableDevice,
                   &v9) >= 0 )
            {
              *(_DWORD *)(*((_QWORD *)lpThreadParameter + 9) + 20LL) = v9;
            }
          }
        }
        SetEvent(*((HANDLE *)lpThreadParameter + 6));
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( v4 )
          ((void (__fastcall *)(struct IPortableDeviceValues *))v4->lpVtbl->Release)(v4);
        if ( v10 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    CoUninitialize();
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, (unsigned int)v2);
  }
  return 0;
}

```

## disassembly

```asm
0x180021de0  push    rbp
0x180021de2  push    rbx
0x180021de3  push    rdi
0x180021de4  mov     rbp, rsp
0x180021de7  sub     rsp, 40h
0x180021deb  mov     rdi, rcx
0x180021dee  mov     edx, 4; dwCoInit
0x180021df3  xor     ecx, ecx; pvReserved
0x180021df5  call    cs:__imp_CoInitializeEx
0x180021dfb  test    eax, eax
0x180021dfd  jns     short loc_180021E3D
0x180021dff  lea     rdx, WPP_GLOBAL_Control
0x180021e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e0d  cmp     rcx, rdx
0x180021e10  jz      loc_180022018
0x180021e16  test    byte ptr [rcx+1Ch], 2
0x180021e1a  jz      loc_180022018
0x180021e20  mov     edx, 35h ; '5'
0x180021e25  mov     r9d, eax
0x180021e28  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x180021e2f  mov     rcx, [rcx+10h]
0x180021e33  call    WPP_SF_d
0x180021e38  jmp     loc_180022018
0x180021e3d  mov     dword ptr [rdi+38h], 1
0x180021e44  mov     rcx, [rdi+20h]; hEvent
0x180021e48  call    cs:__imp_SetEvent
0x180021e4e  mov     rax, [rdi+18h]
0x180021e52  mov     [rbp+Handles], rax
0x180021e56  mov     rax, [rdi+28h]
0x180021e5a  mov     [rbp+var_8], rax
0x180021e5e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180021e62  xor     r8d, r8d; bWaitAll
0x180021e65  lea     rdx, [rbp+Handles]; lpHandles
0x180021e69  lea     ecx, [r8+2]; nCount
0x180021e6d  call    cs:__imp_WaitForMultipleObjects
0x180021e73  test    eax, eax
0x180021e75  jz      loc_180022012
0x180021e7b  cmp     eax, 1
0x180021e7e  jnz     short loc_180021E5E
0x180021e80  mov     [rbp+arg_8], 0
0x180021e88  xor     ebx, ebx
0x180021e8a  mov     [rbp+arg_10], rbx
0x180021e8e  mov     [rbp+arg_18], rbx
0x180021e92  mov     [rbp+arg_0], ebx
0x180021e95  mov     [rdi+50h], ebx
0x180021e98  lea     rax, [rbp+arg_18]
0x180021e9c  mov     [rsp+40h+ppv], rax; ppv
0x180021ea1  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180021ea8  xor     edx, edx; pUnkOuter
0x180021eaa  lea     r8d, [rbx+1]; dwClsContext
0x180021eae  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180021eb5  call    cs:__imp_CoCreateInstance
0x180021ebb  test    eax, eax
0x180021ebd  js      loc_180021FC1
0x180021ec3  lea     rax, [rbp+arg_8]
0x180021ec7  mov     [rsp+40h+ppv], rax; ppv
0x180021ecc  lea     r9, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c; riid
0x180021ed3  xor     edx, edx; pUnkOuter
0x180021ed5  lea     r8d, [rbx+1]; dwClsContext
0x180021ed9  lea     rcx, CLSID_PortableDeviceFTM; rclsid
0x180021ee0  call    cs:__imp_CoCreateInstance
0x180021ee6  test    eax, eax
0x180021ee8  js      loc_180021FC1
0x180021eee  lea     rdx, [rbp+arg_10]; struct IPortableDeviceValues **
0x180021ef2  mov     rcx, cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA; CDeviceCache * g_pDeviceCache
0x180021ef9  mov     ecx, [rcx+3Ch]; int
0x180021efc  call    ?GetClientInfo@@YAJHPEAPEAUIPortableDeviceValues@@@Z; GetClientInfo(int,IPortableDeviceValues * *)
0x180021f01  mov     rbx, [rbp+arg_10]
0x180021f05  test    eax, eax
0x180021f07  js      loc_180021FC1
0x180021f0d  mov     rcx, [rbp+arg_8]
0x180021f11  mov     rax, [rcx]
0x180021f14  mov     rdx, [rdi+40h]
0x180021f18  mov     r8, rbx
0x180021f1b  mov     rdx, [rdx]
0x180021f1e  mov     rax, [rax+18h]
0x180021f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f27  mov     [rdi+50h], eax
0x180021f2a  cmp     eax, 80070005h
0x180021f2f  jnz     short loc_180021F8E
0x180021f31  mov     rax, [rbx]
0x180021f34  mov     r8d, 80000000h
0x180021f3a  lea     rdx, WPD_CLIENT_DESIRED_ACCESS
0x180021f41  mov     rcx, rbx
0x180021f44  mov     rax, [rax+48h]
0x180021f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f4d  test    eax, eax
0x180021f4f  js      short loc_180021F8E
0x180021f51  mov     rax, [rbx]
0x180021f54  mov     r8d, 1
0x180021f5a  lea     rdx, WPD_CLIENT_SHARE_MODE
0x180021f61  mov     rcx, rbx
0x180021f64  mov     rax, [rax+48h]
0x180021f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f6d  test    eax, eax
0x180021f6f  js      short loc_180021F8E
0x180021f71  mov     rcx, [rbp+arg_8]
0x180021f75  mov     rax, [rcx]
0x180021f78  mov     rdx, [rdi+40h]
0x180021f7c  mov     r8, rbx
0x180021f7f  mov     rdx, [rdx]
0x180021f82  mov     rax, [rax+18h]
0x180021f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f8b  mov     [rdi+50h], eax
0x180021f8e  cmp     dword ptr [rdi+50h], 0
0x180021f92  jl      short loc_180021FC1
0x180021f94  mov     rcx, [rbp+arg_18]
0x180021f98  mov     rax, [rcx]
0x180021f9b  lea     r9, [rbp+arg_0]
0x180021f9f  lea     r8, IID_IPortableDevice
0x180021fa6  mov     rdx, [rbp+arg_8]
0x180021faa  mov     rax, [rax+18h]
0x180021fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb3  test    eax, eax
0x180021fb5  js      short loc_180021FC1
0x180021fb7  mov     rcx, [rdi+48h]
0x180021fbb  mov     eax, [rbp+arg_0]
0x180021fbe  mov     [rcx+14h], eax
0x180021fc1  mov     rcx, [rdi+30h]; hEvent
0x180021fc5  call    cs:__imp_SetEvent
0x180021fcb  nop
0x180021fcc  mov     rcx, [rbp+arg_18]
0x180021fd0  test    rcx, rcx
0x180021fd3  jz      short loc_180021FE2
0x180021fd5  mov     rax, [rcx]
0x180021fd8  mov     rax, [rax+10h]
0x180021fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fe1  nop
0x180021fe2  test    rbx, rbx
0x180021fe5  jz      short loc_180021FF7
0x180021fe7  mov     rax, [rbx]
0x180021fea  mov     rcx, rbx
0x180021fed  mov     rax, [rax+10h]
0x180021ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ff6  nop
0x180021ff7  mov     rcx, [rbp+arg_8]
0x180021ffb  test    rcx, rcx
0x180021ffe  jz      short loc_18002200D
0x180022000  mov     rax, [rcx]
0x180022003  mov     rax, [rax+10h]
0x180022007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002200c  nop
0x18002200d  jmp     loc_180021E5E
0x180022012  call    cs:__imp_CoUninitialize
0x180022018  xor     eax, eax
0x18002201a  add     rsp, 40h
0x18002201e  pop     rdi
0x18002201f  pop     rbx
0x180022020  pop     rbp
0x180022021  retn
```
