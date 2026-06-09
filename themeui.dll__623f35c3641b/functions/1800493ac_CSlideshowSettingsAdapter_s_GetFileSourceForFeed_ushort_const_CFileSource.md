# CSlideshowSettingsAdapter::s_GetFileSourceForFeed(ushort const *,CFileSource * *)

- ea: `0x1800493ac`
- end: `0x180049495`
- name: `?s_GetFileSourceForFeed@CSlideshowSettingsAdapter@@CAJPEBGPEAPEAVCFileSource@@@Z`
- size: `233`
- prototype: `static int(const unsigned __int16 *, struct CFileSource **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180049098`

## callees

- `0x1800493ac`
- `0x18004949c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049460`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049460`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800493ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800493ed`

## pseudocode

```c
__int64 __fastcall CSlideshowSettingsAdapter::s_GetFileSourceForFeed(
        const unsigned __int16 *a1,
        struct CFileSource **a2)
{
  HRESULT FileSourceForLocalPath; // ebx
  LPVOID pv; // [rsp+58h] [rbp+28h] BYREF
  __int64 v7; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  ppv = 0;
  FileSourceForLocalPath = CoCreateInstance(
                             &CLSID_XFeedsManager,
                             0,
                             1u,
                             &GUID_5357e238_fb12_4aca_a930_cab7832b84bf,
                             &ppv);
  if ( FileSourceForLocalPath >= 0 )
  {
    v7 = 0;
    FileSourceForLocalPath = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, GUID *, __int64 *))(*(_QWORD *)ppv + 56LL))(
                               ppv,
                               a1,
                               &GUID_a44179a4_e0f6_403b_af8d_d080f425a451,
                               &v7);
    if ( FileSourceForLocalPath >= 0 )
    {
      pv = 0;
      FileSourceForLocalPath = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v7 + 176LL))(v7, &pv);
      if ( FileSourceForLocalPath >= 0 )
      {
        FileSourceForLocalPath = CSlideshowSettingsAdapter::s_GetFileSourceForLocalPath(
                                   (const unsigned __int16 *)pv,
                                   a2);
        CoTaskMemFree(pv);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)FileSourceForLocalPath;
}

```

## disassembly

```asm
0x1800493ac  mov     [rsp-18h+arg_0], rbx
0x1800493b1  push    rbp
0x1800493b2  push    rsi
0x1800493b3  push    rdi
0x1800493b4  mov     rbp, rsp
0x1800493b7  sub     rsp, 30h
0x1800493bb  mov     rdi, rdx
0x1800493be  mov     qword ptr [rdx], 0
0x1800493c5  xor     edx, edx; pUnkOuter
0x1800493c7  mov     [rbp+arg_18], 0
0x1800493cf  mov     rsi, rcx
0x1800493d2  lea     rax, [rbp+arg_18]
0x1800493d6  lea     r9, _GUID_5357e238_fb12_4aca_a930_cab7832b84bf; riid
0x1800493dd  mov     [rsp+30h+ppv], rax; ppv
0x1800493e2  lea     rcx, CLSID_XFeedsManager; rclsid
0x1800493e9  lea     r8d, [rdx+1]; dwClsContext
0x1800493ed  call    cs:__imp_CoCreateInstance
0x1800493f3  mov     ebx, eax
0x1800493f5  test    eax, eax
0x1800493f7  js      loc_180049486
0x1800493fd  mov     rcx, [rbp+arg_18]
0x180049401  lea     r9, [rbp+arg_10]
0x180049405  mov     [rbp+arg_10], 0
0x18004940d  lea     r8, _GUID_a44179a4_e0f6_403b_af8d_d080f425a451
0x180049414  mov     rdx, rsi
0x180049417  mov     rax, [rcx]
0x18004941a  mov     rax, [rax+38h]
0x18004941e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049423  mov     ebx, eax
0x180049425  test    eax, eax
0x180049427  js      short loc_180049476
0x180049429  mov     rcx, [rbp+arg_10]
0x18004942d  lea     rdx, [rbp+pv]
0x180049431  mov     [rbp+pv], 0
0x180049439  mov     rax, [rcx]
0x18004943c  mov     rax, [rax+0B0h]
0x180049443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049448  mov     ebx, eax
0x18004944a  test    eax, eax
0x18004944c  js      short loc_180049466
0x18004944e  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180049452  mov     rdx, rdi; struct CFileSource **
0x180049455  call    ?s_GetFileSourceForLocalPath@CSlideshowSettingsAdapter@@CAJPEBGPEAPEAVCFileSource@@@Z; CSlideshowSettingsAdapter::s_GetFileSourceForLocalPath(ushort const *,CFileSource * *)
0x18004945a  mov     rcx, [rbp+pv]; pv
0x18004945e  mov     ebx, eax
0x180049460  call    cs:__imp_CoTaskMemFree
0x180049466  mov     rcx, [rbp+arg_10]
0x18004946a  mov     rax, [rcx]
0x18004946d  mov     rax, [rax+10h]
0x180049471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049476  mov     rcx, [rbp+arg_18]
0x18004947a  mov     rax, [rcx]
0x18004947d  mov     rax, [rax+10h]
0x180049481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049486  mov     eax, ebx
0x180049488  mov     rbx, [rsp+30h+arg_0]
0x18004948d  add     rsp, 30h
0x180049491  pop     rdi
0x180049492  pop     rsi
0x180049493  pop     rbp
0x180049494  retn
```
