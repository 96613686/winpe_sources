# GetUserFolder(ushort *,ulong)

- ea: `0x180025274`
- end: `0x180025355`
- name: `?GetUserFolder@@YAJPEAGK@Z`
- size: `225`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002a3f8`

## callees

- `0x180012c9c`
- `0x180025274`
- `0x18008a010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800252f6`
- `RPCRT4!RpcRevertToSelf` at `0x1800252f6`
- `RPCRT4!RpcImpersonateClient` at `0x18002529d`
- `RPCRT4!RpcImpersonateClient` at `0x18002529d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800252cb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800252cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025342`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025342`

## pseudocode

```c
__int64 __fastcall GetUserFolder(wchar_t *a1)
{
  RPC_STATUS v2; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF
  __int64 v5; // [rsp+60h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  ppv = 0;
  v5 = 0;
  pv = 0;
  v2 = RpcImpersonateClient(0);
  if ( v2 >= 0 )
  {
    v2 = CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, &ppv);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(LPVOID, const GUID *, __int64 *))(*(_QWORD *)ppv + 48LL))(
             ppv,
             &FOLDERID_Profile,
             &v5);
      RpcRevertToSelf();
      if ( v2 >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v5 + 48LL))(v5, 0, &pv);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        StringCchCopyW(a1, 0x104u, (const wchar_t *)pv);
        CoTaskMemFree(pv);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180025274  mov     rax, rsp
0x180025277  mov     [rax+8], rbx
0x18002527b  push    rdi
0x18002527c  sub     rsp, 40h
0x180025280  mov     rdi, rcx
0x180025283  mov     qword ptr [rax-18h], 0
0x18002528b  xor     ecx, ecx; BindingHandle
0x18002528d  mov     qword ptr [rax+18h], 0
0x180025295  mov     qword ptr [rax+20h], 0
0x18002529d  call    cs:__imp_RpcImpersonateClient
0x1800252a3  mov     ebx, eax
0x1800252a5  test    eax, eax
0x1800252a7  js      loc_180025348
0x1800252ad  xor     edx, edx; pUnkOuter
0x1800252af  lea     rax, [rsp+48h+var_18]
0x1800252b4  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x1800252bb  mov     [rsp+48h+ppv], rax; ppv
0x1800252c0  lea     rcx, CLSID_KnownFolderManager; rclsid
0x1800252c7  lea     r8d, [rdx+1]; dwClsContext
0x1800252cb  call    cs:__imp_CoCreateInstance
0x1800252d1  mov     ebx, eax
0x1800252d3  test    eax, eax
0x1800252d5  js      short loc_180025348
0x1800252d7  mov     rcx, [rsp+48h+var_18]
0x1800252dc  lea     r8, [rsp+48h+arg_10]
0x1800252e1  lea     rdx, FOLDERID_Profile
0x1800252e8  mov     rax, [rcx]
0x1800252eb  mov     rax, [rax+30h]
0x1800252ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252f4  mov     ebx, eax
0x1800252f6  call    cs:__imp_RpcRevertToSelf
0x1800252fc  test    ebx, ebx
0x1800252fe  js      short loc_180025348
0x180025300  mov     rcx, [rsp+48h+arg_10]
0x180025305  lea     r8, [rsp+48h+pv]
0x18002530a  xor     edx, edx
0x18002530c  mov     rax, [rcx]
0x18002530f  mov     rax, [rax+30h]
0x180025313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025318  mov     rcx, [rsp+48h+arg_10]
0x18002531d  mov     ebx, eax
0x18002531f  mov     rax, [rcx]
0x180025322  mov     rax, [rax+10h]
0x180025326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002532b  mov     r8, [rsp+48h+pv]; wchar_t *
0x180025330  mov     edx, 104h; unsigned __int64
0x180025335  mov     rcx, rdi; wchar_t *
0x180025338  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002533d  mov     rcx, [rsp+48h+pv]; pv
0x180025342  call    cs:__imp_CoTaskMemFree
0x180025348  mov     eax, ebx
0x18002534a  mov     rbx, [rsp+48h+arg_0]
0x18002534f  add     rsp, 40h
0x180025353  pop     rdi
0x180025354  retn
```
