# DllGetClassObject

- ea: `0x180004b50`
- end: `0x180004c7c`
- name: `DllGetClassObject`
- size: `300`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002de8`
- `0x180004b50`
- `0x180006010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180004c65`
- `RPCRT4!NdrDllGetClassObject` at `0x180004c65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004bd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004bd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004bfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004bfe`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const IID *v5; // rbp
  HRESULT ClassObject; // edi
  __int64 v7; // rbx
  const IID *const *v8; // r14

  v5 = rclsid;
  if ( ppv )
  {
    *ppv = 0;
    ClassObject = 0;
    v7 = qword_18000C348;
    if ( qword_18000C348 )
    {
      while ( *(_QWORD *)v7 )
      {
        if ( *(_QWORD *)(v7 + 16) )
        {
          rclsid = *(const IID *const *)v7;
          if ( v5->Data1 == **(_DWORD **)v7
            && *(_DWORD *)&v5->Data2 == *(_DWORD *)&rclsid->Data2
            && *(_DWORD *)v5->Data4 == *(_DWORD *)rclsid->Data4
            && *(_DWORD *)&v5->Data4[4] == *(_DWORD *)&rclsid->Data4[4] )
          {
            v8 = (const IID *const *)(v7 + 32);
            if ( !*(_QWORD *)(v7 + 32) )
            {
              EnterCriticalSection(&CriticalSection);
              if ( !*v8 )
                ClassObject = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                                *(_QWORD *)(v7 + 24),
                                &GUID_00000000_0000_0000_c000_000000000046,
                                v7 + 32);
              LeaveCriticalSection(&CriticalSection);
            }
            rclsid = *v8;
            if ( *v8 )
              ClassObject = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                              rclsid,
                              riid,
                              ppv);
            break;
          }
        }
        v7 += 72;
      }
    }
    if ( !*ppv && !ClassObject )
      ClassObject = ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  }
  else
  {
    ClassObject = -2147467261;
  }
  if ( ClassObject < 0 )
    return NdrDllGetClassObject(v5, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, &pclsid, &gPFactory);
  return ClassObject;
}

```

## disassembly

```asm
0x180004b50  push    rbx
0x180004b52  push    rbp
0x180004b53  push    rsi
0x180004b54  push    rdi
0x180004b55  push    r14
0x180004b57  push    r15
0x180004b59  sub     rsp, 38h
0x180004b5d  mov     rsi, r8
0x180004b60  mov     r15, rdx
0x180004b63  mov     rbp, rcx
0x180004b66  test    r8, r8
0x180004b69  jnz     short loc_180004B75
0x180004b6b  mov     edi, 80004003h
0x180004b70  jmp     loc_180004C39
0x180004b75  mov     qword ptr [r8], 0
0x180004b7c  xor     edi, edi
0x180004b7e  mov     rbx, cs:qword_18000C348
0x180004b85  test    rbx, rbx
0x180004b88  jz      loc_180004C1F
0x180004b8e  jmp     short loc_180004BBC
0x180004b90  cmp     [rbx+10h], rdi
0x180004b94  jz      short loc_180004BB8
0x180004b96  mov     rcx, [rbx]
0x180004b99  mov     eax, [rcx]
0x180004b9b  cmp     [rbp+0], eax
0x180004b9e  jnz     short loc_180004BB8
0x180004ba0  mov     eax, [rcx+4]
0x180004ba3  cmp     [rbp+4], eax
0x180004ba6  jnz     short loc_180004BB8
0x180004ba8  mov     eax, [rcx+8]
0x180004bab  cmp     [rbp+8], eax
0x180004bae  jnz     short loc_180004BB8
0x180004bb0  mov     eax, [rcx+0Ch]
0x180004bb3  cmp     [rbp+0Ch], eax
0x180004bb6  jz      short loc_180004BC3
0x180004bb8  add     rbx, 48h ; 'H'
0x180004bbc  cmp     [rbx], rdi
0x180004bbf  jnz     short loc_180004B90
0x180004bc1  jmp     short loc_180004C1F
0x180004bc3  lea     r14, [rbx+20h]
0x180004bc7  cmp     [r14], rdi
0x180004bca  jnz     short loc_180004C04
0x180004bcc  lea     rcx, CriticalSection; lpCriticalSection
0x180004bd3  call    cs:__imp_EnterCriticalSection
0x180004bd9  cmp     [r14], rdi
0x180004bdc  jnz     short loc_180004BF7
0x180004bde  mov     r8, r14
0x180004be1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004be8  mov     rcx, [rbx+18h]
0x180004bec  mov     rax, [rbx+10h]
0x180004bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf5  mov     edi, eax
0x180004bf7  lea     rcx, CriticalSection; lpCriticalSection
0x180004bfe  call    cs:__imp_LeaveCriticalSection
0x180004c04  mov     rcx, [r14]
0x180004c07  test    rcx, rcx
0x180004c0a  jz      short loc_180004C1F
0x180004c0c  mov     rax, [rcx]
0x180004c0f  mov     r8, rsi
0x180004c12  mov     rdx, r15
0x180004c15  mov     rax, [rax]
0x180004c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1d  mov     edi, eax
0x180004c1f  cmp     qword ptr [rsi], 0
0x180004c23  jnz     short loc_180004C39
0x180004c25  test    edi, edi
0x180004c27  jnz     short loc_180004C39
0x180004c29  mov     r9, rsi; void **
0x180004c2c  mov     r8, r15; struct _GUID *
0x180004c2f  mov     rdx, rbp; struct _GUID *
0x180004c32  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180004c37  mov     edi, eax
0x180004c39  test    edi, edi
0x180004c3b  jns     short loc_180004C6D
0x180004c3d  lea     rax, gPFactory
0x180004c44  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180004c49  lea     rax, pclsid
0x180004c50  mov     [rsp+68h+pclsid], rax; pclsid
0x180004c55  lea     r9, aProxyFileList; pProxyFileList
0x180004c5c  mov     r8, rsi; ppv
0x180004c5f  mov     rdx, r15; riid
0x180004c62  mov     rcx, rbp; rclsid
0x180004c65  call    cs:__imp_NdrDllGetClassObject
0x180004c6b  mov     edi, eax
0x180004c6d  mov     eax, edi
0x180004c6f  add     rsp, 38h
0x180004c73  pop     r15
0x180004c75  pop     r14
0x180004c77  pop     rdi
0x180004c78  pop     rsi
0x180004c79  pop     rbp
0x180004c7a  pop     rbx
0x180004c7b  retn
```
