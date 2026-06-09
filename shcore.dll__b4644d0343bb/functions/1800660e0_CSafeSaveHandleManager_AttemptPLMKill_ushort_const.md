# CSafeSaveHandleManager::_AttemptPLMKill(ushort const *)

- ea: `0x1800660e0`
- end: `0x180066239`
- name: `?_AttemptPLMKill@CSafeSaveHandleManager@@AEAAJPEBG@Z`
- size: `345`
- prototype: `int(CSafeSaveHandleManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b1dc`

## callees

- `0x18000ddd4`
- `0x1800660e0`
- `0x180066910`
- `0x18008c240`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066141`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066141`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800661c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800661c4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180066177`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180066177`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSafeSaveHandleManager::_AttemptPLMKill(CSafeSaveHandleManager *this, const unsigned __int16 *a2)
{
  int ValueW; // ebx
  bool v4; // sf
  unsigned int v5; // r8d
  const struct _GUID *v6; // r9
  DWORD pcbData[2]; // [rsp+40h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-21h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-19h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-9h] BYREF

  pcbData[0] = 78;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FileInUseResolver",
             0,
             2u,
             0,
             sz,
             pcbData);
  if ( !ValueW )
    goto LABEL_4;
  sz[0] = 0;
  v4 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
LABEL_4:
    v4 = ValueW < 0;
  }
  if ( !v4 )
  {
    pclsid = 0;
    ValueW = CLSIDFromString(sz, &pclsid);
    if ( ValueW >= 0 )
    {
      *(_QWORD *)pcbData = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(pcbData);
      *(_QWORD *)pcbData = 0;
      ppv = 0;
      ValueW = CoCreateInstance(&pclsid, 0, 0x4001u, &GUID_64a1cbf0_3a1a_4461_9158_376969693950, &ppv);
      if ( ValueW >= 0 )
      {
        ValueW = _AndLoadFromFile((struct IUnknown *)ppv, a2, v5, v6, (void **)pcbData);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( ValueW >= 0 )
          ValueW = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 56LL))(*(_QWORD *)pcbData);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(pcbData);
    }
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1800660e0  mov     [rsp-8+arg_0], rbx
0x1800660e5  mov     [rsp-8+arg_10], rdi
0x1800660ea  push    rbp
0x1800660eb  lea     rbp, [rsp-57h]
0x1800660f0  sub     rsp, 0C0h
0x1800660f7  mov     rax, cs:__security_cookie
0x1800660fe  xor     rax, rsp
0x180066101  mov     [rbp+57h+var_10], rax
0x180066105  mov     rdi, rdx
0x180066108  mov     [rbp+57h+var_80], 4Eh ; 'N'
0x18006610f  lea     rax, [rbp+57h+var_80]
0x180066113  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180066118  lea     rax, [rbp+57h+sz]
0x18006611c  mov     [rsp+0C0h+pvData], rax; pvData
0x180066121  mov     [rsp+0C0h+pdwType], 0; pdwType
0x18006612a  mov     r9d, 2; dwFlags
0x180066130  xor     r8d, r8d; lpValue
0x180066133  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006613a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180066141  call    cs:__imp_RegGetValueW
0x180066147  mov     ebx, eax
0x180066149  test    eax, eax
0x18006614b  jz      short loc_180066160
0x18006614d  xor     eax, eax
0x18006614f  mov     [rbp+57h+sz], ax
0x180066153  test    ebx, ebx
0x180066155  jle     short loc_180066162
0x180066157  movzx   ebx, bx
0x18006615a  or      ebx, 80070000h
0x180066160  test    ebx, ebx
0x180066162  js      loc_180066216
0x180066168  xorps   xmm0, xmm0
0x18006616b  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18006616f  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180066173  lea     rcx, [rbp+57h+sz]; lpsz
0x180066177  call    cs:__imp_CLSIDFromString
0x18006617d  mov     ebx, eax
0x18006617f  test    eax, eax
0x180066181  js      loc_180066216
0x180066187  mov     qword ptr [rbp+57h+var_80], 0
0x18006618f  lea     rcx, [rbp+57h+var_80]
0x180066193  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180066198  mov     qword ptr [rbp+57h+var_80], 0
0x1800661a0  mov     [rbp+57h+ppv], 0
0x1800661a8  lea     rax, [rbp+57h+ppv]
0x1800661ac  mov     [rsp+0C0h+pdwType], rax; ppv
0x1800661b1  lea     r9, _GUID_64a1cbf0_3a1a_4461_9158_376969693950; riid
0x1800661b8  xor     edx, edx; pUnkOuter
0x1800661ba  mov     r8d, 4001h; dwClsContext
0x1800661c0  lea     rcx, [rbp+57h+pclsid]; rclsid
0x1800661c4  call    cs:__imp_CoCreateInstance
0x1800661ca  mov     ebx, eax
0x1800661cc  test    eax, eax
0x1800661ce  js      short loc_18006620D
0x1800661d0  lea     rax, [rbp+57h+var_80]
0x1800661d4  mov     [rsp+0C0h+pdwType], rax; void **
0x1800661d9  mov     rdx, rdi; unsigned __int16 *
0x1800661dc  mov     rcx, [rbp+57h+ppv]; struct IUnknown *
0x1800661e0  call    ?_AndLoadFromFile@@YAJPEAUIUnknown@@PEBGKAEBU_GUID@@PEAPEAX@Z; _AndLoadFromFile(IUnknown *,ushort const *,ulong,_GUID const &,void * *)
0x1800661e5  mov     ebx, eax
0x1800661e7  mov     rcx, [rbp+57h+ppv]
0x1800661eb  mov     rax, [rcx]
0x1800661ee  mov     rax, [rax+10h]
0x1800661f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661f7  test    ebx, ebx
0x1800661f9  js      short loc_18006620D
0x1800661fb  mov     rcx, qword ptr [rbp+57h+var_80]
0x1800661ff  mov     rax, [rcx]
0x180066202  mov     rax, [rax+38h]
0x180066206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006620b  mov     ebx, eax
0x18006620d  lea     rcx, [rbp+57h+var_80]
0x180066211  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180066216  mov     eax, ebx
0x180066218  mov     rcx, [rbp+57h+var_10]
0x18006621c  xor     rcx, rsp; StackCookie
0x18006621f  call    __security_check_cookie
0x180066224  lea     r11, [rsp+0C0h+var_s0]
0x18006622c  mov     rbx, [r11+10h]
0x180066230  mov     rdi, [r11+20h]
0x180066234  mov     rsp, r11
0x180066237  pop     rbp
0x180066238  retn
```
