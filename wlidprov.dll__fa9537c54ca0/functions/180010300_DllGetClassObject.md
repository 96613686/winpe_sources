# DllGetClassObject

- ea: `0x180010300`
- end: `0x18001042b`
- name: `DllGetClassObject`
- size: `299`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180010300`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800103bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800103bf`
- `RPCRT4!NdrDllGetClassObject` at `0x18001041e`
- `RPCRT4!NdrDllGetClassObject` at `0x18001041e`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // r8
  struct ATL::_ATL_OBJMAP_ENTRY30 *v8; // r14
  _DWORD *v9; // rcx
  _QWORD *v10; // rdi

  if ( !ATL::_AtlComModule || !ppv )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  *ppv = 0;
  v6 = 0;
  for ( i = off_180084330; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_180084338; ++i )
  {
    v8 = *i;
    if ( *i )
    {
      if ( *((_QWORD *)v8 + 2) )
      {
        v9 = *(_DWORD **)v8;
        if ( rclsid->Data1 == **(_DWORD **)v8
          && *(_DWORD *)&rclsid->Data2 == v9[1]
          && *(_DWORD *)rclsid->Data4 == v9[2]
          && *(_DWORD *)&rclsid->Data4[4] == v9[3] )
        {
          v10 = (_QWORD *)((char *)v8 + 32);
          if ( !*((_QWORD *)v8 + 4) )
          {
            EnterCriticalSection(&stru_180084340);
            if ( !*v10 )
              v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v8 + 2))(
                     *((_QWORD *)v8 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v8 + 32);
            LeaveCriticalSection(&stru_180084340);
          }
          if ( *v10 )
            v6 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *))*v10)(*v10, riid, ppv);
          break;
        }
      }
    }
  }
  if ( !*ppv && !v6 || v6 < 0 )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  return v6;
}

```

## disassembly

```asm
0x180010300  push    rbx
0x180010302  push    rbp
0x180010303  push    rsi
0x180010304  push    rdi
0x180010305  push    r14
0x180010307  push    r15
0x180010309  sub     rsp, 38h
0x18001030d  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180010314  mov     rsi, r8
0x180010317  mov     r15, rdx
0x18001031a  mov     rbp, rcx
0x18001031d  jz      loc_1800103F6
0x180010323  test    r8, r8
0x180010326  jz      loc_1800103F6
0x18001032c  mov     qword ptr [r8], 0
0x180010333  xor     ebx, ebx
0x180010335  mov     r8, cs:off_180084330
0x18001033c  cmp     r8, cs:off_180084338
0x180010343  jnb     short loc_180010399
0x180010345  mov     r14, [r8]
0x180010348  test    r14, r14
0x18001034b  jz      short loc_1800103B2
0x18001034d  cmp     [r14+10h], rbx
0x180010351  jz      short loc_1800103B2
0x180010353  mov     rcx, [r14]
0x180010356  mov     eax, [rcx]
0x180010358  cmp     [rbp+0], eax
0x18001035b  jnz     short loc_1800103B2
0x18001035d  mov     eax, [rcx+4]
0x180010360  cmp     [rbp+4], eax
0x180010363  jnz     short loc_1800103B2
0x180010365  mov     eax, [rcx+8]
0x180010368  cmp     [rbp+8], eax
0x18001036b  jnz     short loc_1800103B2
0x18001036d  mov     eax, [rcx+0Ch]
0x180010370  cmp     [rbp+0Ch], eax
0x180010373  jnz     short loc_1800103B2
0x180010375  lea     rdi, [r14+20h]
0x180010379  cmp     [rdi], rbx
0x18001037c  jz      short loc_1800103B8
0x18001037e  mov     rcx, [rdi]
0x180010381  test    rcx, rcx
0x180010384  jz      short loc_180010399
0x180010386  mov     rax, [rcx]
0x180010389  mov     r8, rsi
0x18001038c  mov     rdx, r15
0x18001038f  mov     rax, [rax]
0x180010392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010397  mov     ebx, eax
0x180010399  cmp     qword ptr [rsi], 0
0x18001039d  jz      short loc_1800103F2
0x18001039f  test    ebx, ebx
0x1800103a1  js      short loc_1800103F6
0x1800103a3  mov     eax, ebx
0x1800103a5  add     rsp, 38h
0x1800103a9  pop     r15
0x1800103ab  pop     r14
0x1800103ad  pop     rdi
0x1800103ae  pop     rsi
0x1800103af  pop     rbp
0x1800103b0  pop     rbx
0x1800103b1  retn
0x1800103b2  add     r8, 8
0x1800103b6  jmp     short loc_18001033C
0x1800103b8  lea     rcx, stru_180084340; lpCriticalSection
0x1800103bf  call    cs:__imp_EnterCriticalSection
0x1800103c5  cmp     [rdi], rbx
0x1800103c8  jnz     short loc_1800103E3
0x1800103ca  mov     rcx, [r14+18h]
0x1800103ce  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800103d5  mov     rax, [r14+10h]
0x1800103d9  mov     r8, rdi
0x1800103dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103e1  mov     ebx, eax
0x1800103e3  lea     rcx, stru_180084340; lpCriticalSection
0x1800103ea  call    cs:__imp_LeaveCriticalSection
0x1800103f0  jmp     short loc_18001037E
0x1800103f2  test    ebx, ebx
0x1800103f4  jnz     short loc_18001039F
0x1800103f6  lea     rax, gPFactory
0x1800103fd  mov     r8, rsi; ppv
0x180010400  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180010405  lea     r9, aProxyFileList; pProxyFileList
0x18001040c  lea     rax, CLSID_PSFactoryBuffer
0x180010413  mov     rdx, r15; riid
0x180010416  mov     rcx, rbp; rclsid
0x180010419  mov     [rsp+68h+pclsid], rax; pclsid
0x18001041e  call    cs:__imp_NdrDllGetClassObject
0x180010424  mov     ebx, eax
0x180010426  jmp     loc_1800103A3
```
