# CContextMenuDUI::ReportSQM(void)

- ea: `0x1800796dc`
- end: `0x1800798cb`
- name: `?ReportSQM@CContextMenuDUI@@QEAAXXZ`
- size: `495`
- prototype: `void __fastcall(CContextMenuDUI *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180075204`
- `0x1800754a0`

## callees

- `0x18000af00`
- `0x180013f14`
- `0x180054130`
- `0x1800796dc`
- `0x1800e07ec`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800797c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800797c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079748`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079748`
- `ntdll!WinSqmAddToStreamEx` at `0x180079891`
- `ntdll!WinSqmAddToStreamEx` at `0x180079891`
- `ntdll!WinSqmIsOptedIn` at `0x180079707`
- `ntdll!WinSqmIsOptedIn` at `0x180079707`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079796`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079796`

## pseudocode

```c
void __fastcall CContextMenuDUI::ReportSQM(CContextMenuDUI *this)
{
  HANDLE CurrentProcess; // rax
  unsigned __int16 **v3; // r8
  HRESULT v4; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, _QWORD, __int64 *, _QWORD, _QWORD, _QWORD); // rbx
  DWORD CurrentProcessId; // eax
  __int64 v8; // rcx
  int v9; // eax
  LPVOID ppv; // [rsp+40h] [rbp-29h] BYREF
  __int64 v11; // [rsp+48h] [rbp-21h] BYREF
  __int64 v12; // [rsp+50h] [rbp-19h]
  __int64 v13; // [rsp+58h] [rbp-11h]
  _DWORD v14[2]; // [rsp+60h] [rbp-9h] BYREF
  const wchar_t *v15; // [rsp+68h] [rbp-1h]
  int v16; // [rsp+70h] [rbp+7h]
  int v17; // [rsp+74h] [rbp+Bh]
  const wchar_t *v18; // [rsp+78h] [rbp+Fh]
  int v19; // [rsp+80h] [rbp+17h]
  int v20; // [rsp+84h] [rbp+1Bh]
  int v21; // [rsp+88h] [rbp+1Fh]
  int v22; // [rsp+8Ch] [rbp+23h]
  int v23; // [rsp+90h] [rbp+27h]
  int v24; // [rsp+94h] [rbp+2Bh]
  int v25; // [rsp+98h] [rbp+2Fh]
  int v26; // [rsp+9Ch] [rbp+33h]

  if ( (unsigned int)WinSqmIsOptedIn() )
  {
    v11 = 0;
    v12 = 0;
    v13 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
    v12 = -1;
    v13 = -1;
    CurrentProcess = GetCurrentProcess();
    if ( (int)CallerIdentity::GetProcessAppId(CurrentProcess, &v11, v3) >= 0 )
      goto LABEL_6;
    ppv = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
    v4 = CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 3u, &GUID_de25675a_72de_44b4_9373_05170450c140, &ppv);
    if ( v4 >= 0 )
    {
      v5 = ppv;
      v6 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 48LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
      v12 = -1;
      v13 = -1;
      CurrentProcessId = GetCurrentProcessId();
      v4 = v6(v5, CurrentProcessId, &v11, 0, 0, 0);
    }
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
    if ( v4 >= 0 )
    {
LABEL_6:
      v8 = *((_QWORD *)this + 18);
      LODWORD(ppv) = 0;
      if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 56LL))(v8, &ppv) >= 0 )
      {
        v22 = 0;
        v14[0] = 16;
        v15 = L"(null)";
        v18 = L"(null)";
        v16 = 16;
        v20 = 1;
        v14[1] = 2;
        v17 = 2;
        v24 = 1;
        v19 = 16;
        v21 = (int)ppv;
        v9 = *((_DWORD *)this + 40);
        v23 = 16;
        v26 = 0;
        v25 = v9;
        WinSqmAddToStreamEx(0, 8712, 4, v14, 0);
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
  }
}

```

## disassembly

```asm
0x1800796dc  mov     [rsp-8+arg_8], rbx
0x1800796e1  mov     [rsp-8+arg_10], rsi
0x1800796e6  push    rbp
0x1800796e7  push    rdi
0x1800796e8  push    r15
0x1800796ea  lea     rbp, [rsp-47h]
0x1800796ef  sub     rsp, 0B0h
0x1800796f6  mov     rax, cs:__security_cookie
0x1800796fd  xor     rax, rsp
0x180079700  mov     [rbp+57h+var_20], rax
0x180079704  mov     rsi, rcx
0x180079707  call    cs:__imp_WinSqmIsOptedIn
0x18007970e  nop     dword ptr [rax+rax+00h]
0x180079713  test    eax, eax
0x180079715  jz      loc_1800798A6
0x18007971b  lea     rcx, [rbp+57h+var_78]
0x18007971f  mov     [rbp+57h+var_78], 0
0x180079727  mov     [rbp+57h+var_70], 0
0x18007972f  mov     [rbp+57h+var_68], 0
0x180079737  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007973c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180079740  mov     [rbp+57h+var_70], r15
0x180079744  mov     [rbp+57h+var_68], r15
0x180079748  call    cs:__imp_GetCurrentProcess
0x18007974f  nop     dword ptr [rax+rax+00h]
0x180079754  mov     rcx, rax; ProcessHandle
0x180079757  lea     rdx, [rbp+57h+var_78]; void *
0x18007975b  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x180079760  test    eax, eax
0x180079762  jns     loc_180079809
0x180079768  lea     rcx, [rbp+57h+var_80]
0x18007976c  mov     [rbp+57h+var_80], 0
0x180079774  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180079779  lea     rax, [rbp+57h+var_80]
0x18007977d  xor     edx, edx; pUnkOuter
0x18007977f  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180079786  mov     [rsp+0C0h+ppv], rax; ppv
0x18007978b  lea     r8d, [r15+4]; dwClsContext
0x18007978f  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x180079796  call    cs:__imp_CoCreateInstance
0x18007979d  nop     dword ptr [rax+rax+00h]
0x1800797a2  mov     ebx, eax
0x1800797a4  test    eax, eax
0x1800797a6  js      short loc_1800797F8
0x1800797a8  mov     rdi, [rbp+57h+var_80]
0x1800797ac  lea     rcx, [rbp+57h+var_78]
0x1800797b0  mov     rax, [rdi]
0x1800797b3  mov     rbx, [rax+30h]
0x1800797b7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800797bc  mov     [rbp+57h+var_70], r15
0x1800797c0  mov     [rbp+57h+var_68], r15
0x1800797c4  call    cs:__imp_GetCurrentProcessId
0x1800797cb  nop     dword ptr [rax+rax+00h]
0x1800797d0  mov     [rsp+0C0h+var_98], 0
0x1800797d9  lea     r8, [rbp+57h+var_78]
0x1800797dd  mov     edx, eax
0x1800797df  mov     [rsp+0C0h+ppv], 0
0x1800797e8  mov     rax, rbx
0x1800797eb  xor     r9d, r9d
0x1800797ee  mov     rcx, rdi
0x1800797f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800797f6  mov     ebx, eax
0x1800797f8  lea     rcx, [rbp+57h+var_80]
0x1800797fc  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180079801  test    ebx, ebx
0x180079803  js      loc_18007989D
0x180079809  mov     rcx, [rsi+90h]
0x180079810  lea     rdx, [rbp+57h+var_80]
0x180079814  mov     dword ptr [rbp+57h+var_80], 0
0x18007981b  mov     rax, [rcx]
0x18007981e  mov     rax, [rax+38h]
0x180079822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079827  test    eax, eax
0x180079829  js      short loc_18007989D
0x18007982b  mov     edx, 10h
0x180079830  mov     [rbp+57h+var_34], 0
0x180079837  lea     rcx, aNull; "(null)"
0x18007983e  mov     [rbp+57h+var_60], edx
0x180079841  mov     [rbp+57h+var_58], rcx
0x180079845  lea     r9, [rbp+57h+var_60]
0x180079849  mov     [rbp+57h+var_48], rcx
0x18007984d  lea     ecx, [rdx-0Fh]
0x180079850  mov     [rbp+57h+var_50], edx
0x180079853  lea     eax, [rdx-0Eh]
0x180079856  mov     [rbp+57h+var_3C], ecx
0x180079859  mov     [rbp+57h+var_5C], eax
0x18007985c  mov     [rbp+57h+var_4C], eax
0x18007985f  mov     eax, dword ptr [rbp+57h+var_80]
0x180079862  mov     [rbp+57h+var_2C], ecx
0x180079865  xor     ecx, ecx
0x180079867  mov     [rbp+57h+var_40], edx
0x18007986a  mov     [rbp+57h+var_38], eax
0x18007986d  mov     eax, [rsi+0A0h]
0x180079873  mov     [rbp+57h+var_30], edx
0x180079876  lea     r8d, [rcx+4]
0x18007987a  mov     edx, 2208h
0x18007987f  mov     [rbp+57h+var_24], 0
0x180079886  mov     [rbp+57h+var_28], eax
0x180079889  mov     dword ptr [rsp+0C0h+ppv], 0
0x180079891  call    cs:__imp_WinSqmAddToStreamEx
0x180079898  nop     dword ptr [rax+rax+00h]
0x18007989d  lea     rcx, [rbp+57h+var_78]
0x1800798a1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800798a6  mov     rcx, [rbp+57h+var_20]
0x1800798aa  xor     rcx, rsp; StackCookie
0x1800798ad  call    __security_check_cookie
0x1800798b2  lea     r11, [rsp+0C0h+var_10]
0x1800798ba  mov     rbx, [r11+28h]
0x1800798be  mov     rsi, [r11+30h]
0x1800798c2  mov     rsp, r11
0x1800798c5  pop     r15
0x1800798c7  pop     rdi
0x1800798c8  pop     rbp
0x1800798c9  retn
```
