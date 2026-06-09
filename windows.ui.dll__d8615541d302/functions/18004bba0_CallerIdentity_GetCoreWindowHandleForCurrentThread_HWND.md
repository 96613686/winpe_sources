# CallerIdentity::GetCoreWindowHandleForCurrentThread(HWND__ * *)

- ea: `0x18004bba0`
- end: `0x18004bc94`
- name: `?GetCoreWindowHandleForCurrentThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004bb20`
- `0x18009ffc4`
- `0x1800a3374`
- `0x1800bdbd0`

## callees

- `0x1800038e0`
- `0x180004dd4`
- `0x18004bba0`
- `0x1800c6138`
- `0x1800ca010`

## import_xrefs

- `combase!__imp_RoGetDesignMode` at `0x18004bbc7`
- `combase!__imp_RoGetDesignMode` at `0x18004bbc7`
- `combase!__imp_RoGetDesignModeV2` at `0x18004bbde`
- `combase!__imp_RoGetDesignModeV2` at `0x18004bbde`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004bc18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004bc18`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCoreWindowHandleForCurrentThread(CallerIdentity *this, HWND *a2)
{
  HRESULT CoreWindowForCurrentThread; // ebx
  CallerIdentity *v4; // rcx
  void **v5; // r8
  struct _GUID ppv; // [rsp+40h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  ppv.Data1 = 0;
  RoGetDesignMode(&ppv, a2);
  if ( !ppv.Data1 || (*(_DWORD *)ppv.Data4 = 0, RoGetDesignModeV2(ppv.Data4), *(_DWORD *)ppv.Data4) )
  {
    *(_QWORD *)&ppv.Data1 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&ppv);
    CoreWindowForCurrentThread = CallerIdentity::GetCoreWindowForCurrentThread(v4, &ppv, v5);
    if ( CoreWindowForCurrentThread >= 0 )
      CoreWindowForCurrentThread = (*(__int64 (__fastcall **)(_QWORD, CallerIdentity *))(**(_QWORD **)&ppv.Data1 + 24LL))(
                                     *(_QWORD *)&ppv.Data1,
                                     this);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&ppv);
  }
  else
  {
    *(_QWORD *)&ppv.Data1 = 0;
    Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&ppv);
    CoreWindowForCurrentThread = CoCreateInstance(
                                   &GUID_958a6fb5_dcb2_4faf_aafd_7fb054ad1a3b,
                                   0,
                                   3u,
                                   &GUID_a656e803_4059_4a4c_a5b8_0d0de2c809fb,
                                   (LPVOID *)&ppv);
    if ( CoreWindowForCurrentThread >= 0 )
      CoreWindowForCurrentThread = (*(__int64 (__fastcall **)(_QWORD, CallerIdentity *))(**(_QWORD **)&ppv.Data1 + 24LL))(
                                     *(_QWORD *)&ppv.Data1,
                                     this);
    Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&ppv);
  }
  return (unsigned int)CoreWindowForCurrentThread;
}

```

## disassembly

```asm
0x18004bba0  mov     [rsp-8+arg_10], rbx
0x18004bba5  mov     [rsp-8+arg_18], rdi
0x18004bbaa  push    rbp
0x18004bbab  mov     rbp, rsp
0x18004bbae  sub     rsp, 30h
0x18004bbb2  mov     rdi, rcx
0x18004bbb5  mov     qword ptr [rcx], 0
0x18004bbbc  lea     rcx, [rbp+arg_0]
0x18004bbc0  mov     [rbp+arg_0.Data1], 0
0x18004bbc7  call    cs:__imp_RoGetDesignMode
0x18004bbcd  cmp     [rbp+arg_0.Data1], 0
0x18004bbd1  jz      short loc_18004BC44
0x18004bbd3  lea     rcx, [rbp+arg_0.Data4]
0x18004bbd7  mov     dword ptr [rbp+arg_0.Data4], 0
0x18004bbde  call    cs:__imp_RoGetDesignModeV2
0x18004bbe4  cmp     dword ptr [rbp+arg_0.Data4], 0
0x18004bbe8  jnz     short loc_18004BC44
0x18004bbea  lea     rcx, [rbp+arg_0]
0x18004bbee  mov     qword ptr [rbp+arg_0.Data1], 0
0x18004bbf6  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x18004bbfb  xor     edx, edx; pUnkOuter
0x18004bbfd  lea     rax, [rbp+arg_0]
0x18004bc01  lea     r9, _GUID_a656e803_4059_4a4c_a5b8_0d0de2c809fb; riid
0x18004bc08  mov     [rsp+30h+ppv], rax; ppv
0x18004bc0d  lea     rcx, _GUID_958a6fb5_dcb2_4faf_aafd_7fb054ad1a3b; rclsid
0x18004bc14  lea     r8d, [rdx+3]; dwClsContext
0x18004bc18  call    cs:__imp_CoCreateInstance
0x18004bc1e  mov     ebx, eax
0x18004bc20  test    eax, eax
0x18004bc22  js      short loc_18004BC39
0x18004bc24  mov     rcx, qword ptr [rbp+arg_0.Data1]
0x18004bc28  mov     rdx, rdi
0x18004bc2b  mov     rax, [rcx]
0x18004bc2e  mov     rax, [rax+18h]
0x18004bc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc37  mov     ebx, eax
0x18004bc39  lea     rcx, [rbp+arg_0]
0x18004bc3d  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x18004bc42  jmp     short loc_18004BC82
0x18004bc44  lea     rcx, [rbp+arg_0]
0x18004bc48  mov     qword ptr [rbp+arg_0.Data1], 0
0x18004bc50  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004bc55  lea     rdx, [rbp+arg_0]; struct _GUID *
0x18004bc59  call    ?GetCoreWindowForCurrentThread@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z; CallerIdentity::GetCoreWindowForCurrentThread(_GUID const &,void * *)
0x18004bc5e  mov     ebx, eax
0x18004bc60  test    eax, eax
0x18004bc62  js      short loc_18004BC79
0x18004bc64  mov     rcx, qword ptr [rbp+arg_0.Data1]
0x18004bc68  mov     rdx, rdi
0x18004bc6b  mov     rax, [rcx]
0x18004bc6e  mov     rax, [rax+18h]
0x18004bc72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc77  mov     ebx, eax
0x18004bc79  lea     rcx, [rbp+arg_0]
0x18004bc7d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004bc82  mov     rdi, [rsp+30h+arg_18]
0x18004bc87  mov     eax, ebx
0x18004bc89  mov     rbx, [rsp+30h+arg_10]
0x18004bc8e  add     rsp, 30h
0x18004bc92  pop     rbp
0x18004bc93  retn
```
