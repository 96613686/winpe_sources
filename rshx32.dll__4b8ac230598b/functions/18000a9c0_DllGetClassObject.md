# DllGetClassObject

- ea: `0x18000a9c0`
- end: `0x18000aabe`
- name: `DllGetClassObject`
- size: `254`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a9c0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa26`
- `RPCRT4!NdrDllGetClassObject` at `0x18000aaad`
- `RPCRT4!NdrDllGetClassObject` at `0x18000aaad`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v6; // esi
  HRESULT v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx

  *ppv = 0;
  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_NTFSSecurityExt )
  {
    v6 = 1;
LABEL_6:
    v7 = -2147024882;
    v8 = LocalAlloc(0x40u, 0x10u);
    v9 = v8;
    if ( v8 )
    {
      v8[2] = 1;
      *(_QWORD *)v8 = &CSecurityExtensionCF::`vftable';
      v8[3] = v6;
      _InterlockedIncrement(&g_cRefThisDll);
      v7 = (**(__int64 (__fastcall ***)(HLOCAL, const IID *const, LPVOID *))v8)(v8, riid, ppv);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v7;
  }
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_PrintSecurityExt.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_PrintSecurityExt.Data4 )
  {
    v6 = 3;
    goto LABEL_6;
  }
  pStubVtblList = aProxyFileList->pStubVtblList;
  if ( *pStubVtblList )
    pclsid = **(const CLSID ***)pStubVtblList;
  else
    pclsid = 0;
  return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
}

```

## disassembly

```asm
0x18000a9c0  push    rbx
0x18000a9c2  push    rbp
0x18000a9c3  push    rsi
0x18000a9c4  push    rdi
0x18000a9c5  push    r14
0x18000a9c7  sub     rsp, 30h
0x18000a9cb  mov     qword ptr [r8], 0
0x18000a9d2  mov     r14, r8
0x18000a9d5  mov     rax, [rcx]
0x18000a9d8  mov     rbp, rdx
0x18000a9db  cmp     rax, qword ptr cs:CLSID_NTFSSecurityExt.Data1
0x18000a9e2  mov     r10, rcx
0x18000a9e5  jnz     short loc_18000A9FB
0x18000a9e7  mov     rax, [rcx+8]
0x18000a9eb  cmp     rax, qword ptr cs:CLSID_NTFSSecurityExt.Data4
0x18000a9f2  jnz     short loc_18000A9FB
0x18000a9f4  mov     esi, 1
0x18000a9f9  jmp     short loc_18000AA19
0x18000a9fb  mov     rax, [rcx]
0x18000a9fe  cmp     rax, qword ptr cs:CLSID_PrintSecurityExt.Data1
0x18000aa05  jnz     short loc_18000AA78
0x18000aa07  mov     rax, [rcx+8]
0x18000aa0b  cmp     rax, qword ptr cs:CLSID_PrintSecurityExt.Data4
0x18000aa12  jnz     short loc_18000AA78
0x18000aa14  mov     esi, 3
0x18000aa19  mov     edx, 10h; uBytes
0x18000aa1e  mov     edi, 8007000Eh
0x18000aa23  lea     ecx, [rdx+30h]; uFlags
0x18000aa26  call    cs:__imp_LocalAlloc
0x18000aa2c  mov     rbx, rax
0x18000aa2f  test    rax, rax
0x18000aa32  jz      short loc_18000AA74
0x18000aa34  lea     rax, ??_7CSecurityExtensionCF@@6B@; const CSecurityExtensionCF::`vftable'
0x18000aa3b  mov     dword ptr [rbx+8], 1
0x18000aa42  mov     [rbx], rax
0x18000aa45  mov     [rbx+0Ch], esi
0x18000aa48  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000aa4f  mov     rax, [rbx]
0x18000aa52  mov     r8, r14
0x18000aa55  mov     rdx, rbp
0x18000aa58  mov     rcx, rbx
0x18000aa5b  mov     rax, [rax]
0x18000aa5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa63  mov     rcx, [rbx]
0x18000aa66  mov     edi, eax
0x18000aa68  mov     rax, [rcx+10h]
0x18000aa6c  mov     rcx, rbx
0x18000aa6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa74  mov     eax, edi
0x18000aa76  jmp     short loc_18000AAB3
0x18000aa78  mov     rax, cs:aProxyFileList
0x18000aa7f  mov     rcx, [rax+8]
0x18000aa83  mov     rax, [rcx]
0x18000aa86  test    rax, rax
0x18000aa89  jz      short loc_18000AA90
0x18000aa8b  mov     rcx, [rax]
0x18000aa8e  jmp     short loc_18000AA92
0x18000aa90  xor     ecx, ecx
0x18000aa92  lea     rax, gPFactory
0x18000aa99  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000aa9e  lea     r9, aProxyFileList; pProxyFileList
0x18000aaa5  mov     [rsp+58h+pclsid], rcx; pclsid
0x18000aaaa  mov     rcx, r10; rclsid
0x18000aaad  call    cs:__imp_NdrDllGetClassObject
0x18000aab3  add     rsp, 30h
0x18000aab7  pop     r14
0x18000aab9  pop     rdi
0x18000aaba  pop     rsi
0x18000aabb  pop     rbp
0x18000aabc  pop     rbx
0x18000aabd  retn
```
