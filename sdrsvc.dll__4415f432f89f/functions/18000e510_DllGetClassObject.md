# DllGetClassObject

- ea: `0x18000e510`
- end: `0x18000e608`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800097e8`
- `0x18000e510`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e5be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e5be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e593`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e593`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const IID *v5; // rbp
  HRESULT v6; // edi
  __int64 v7; // rbx
  const IID *const *v8; // r14

  v5 = rclsid;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = qword_18002E1D8;
  if ( qword_18002E1D8 )
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
            EnterCriticalSection(&stru_18002D3C0);
            if ( !*v8 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                     *(_QWORD *)(v7 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v7 + 32);
            LeaveCriticalSection(&stru_18002D3C0);
          }
          rclsid = *v8;
          if ( *v8 )
            v6 = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                   rclsid,
                   riid,
                   ppv);
          break;
        }
      }
      v7 += 72;
    }
  }
  if ( !*ppv && !v6 )
    return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  return v6;
}

```

## disassembly

```asm
0x18000e510  push    rbx
0x18000e512  push    rbp
0x18000e513  push    rsi
0x18000e514  push    rdi
0x18000e515  push    r14
0x18000e517  push    r15
0x18000e519  sub     rsp, 28h
0x18000e51d  mov     rsi, r8
0x18000e520  mov     r15, rdx
0x18000e523  mov     rbp, rcx
0x18000e526  test    r8, r8
0x18000e529  jnz     short loc_18000E535
0x18000e52b  mov     edi, 80004003h
0x18000e530  jmp     loc_18000E5F9
0x18000e535  mov     qword ptr [r8], 0
0x18000e53c  xor     edi, edi
0x18000e53e  mov     rbx, cs:qword_18002E1D8
0x18000e545  test    rbx, rbx
0x18000e548  jz      loc_18000E5DF
0x18000e54e  jmp     short loc_18000E57C
0x18000e550  cmp     [rbx+10h], rdi
0x18000e554  jz      short loc_18000E578
0x18000e556  mov     rcx, [rbx]
0x18000e559  mov     eax, [rcx]
0x18000e55b  cmp     [rbp+0], eax
0x18000e55e  jnz     short loc_18000E578
0x18000e560  mov     eax, [rcx+4]
0x18000e563  cmp     [rbp+4], eax
0x18000e566  jnz     short loc_18000E578
0x18000e568  mov     eax, [rcx+8]
0x18000e56b  cmp     [rbp+8], eax
0x18000e56e  jnz     short loc_18000E578
0x18000e570  mov     eax, [rcx+0Ch]
0x18000e573  cmp     [rbp+0Ch], eax
0x18000e576  jz      short loc_18000E583
0x18000e578  add     rbx, 48h ; 'H'
0x18000e57c  cmp     [rbx], rdi
0x18000e57f  jnz     short loc_18000E550
0x18000e581  jmp     short loc_18000E5DF
0x18000e583  lea     r14, [rbx+20h]
0x18000e587  cmp     [r14], rdi
0x18000e58a  jnz     short loc_18000E5C4
0x18000e58c  lea     rcx, stru_18002D3C0; lpCriticalSection
0x18000e593  call    cs:__imp_EnterCriticalSection
0x18000e599  cmp     [r14], rdi
0x18000e59c  jnz     short loc_18000E5B7
0x18000e59e  mov     rcx, [rbx+18h]
0x18000e5a2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000e5a9  mov     rax, [rbx+10h]
0x18000e5ad  mov     r8, r14
0x18000e5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5b5  mov     edi, eax
0x18000e5b7  lea     rcx, stru_18002D3C0; lpCriticalSection
0x18000e5be  call    cs:__imp_LeaveCriticalSection
0x18000e5c4  mov     rcx, [r14]
0x18000e5c7  test    rcx, rcx
0x18000e5ca  jz      short loc_18000E5DF
0x18000e5cc  mov     rax, [rcx]
0x18000e5cf  mov     r8, rsi
0x18000e5d2  mov     rdx, r15
0x18000e5d5  mov     rax, [rax]
0x18000e5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5dd  mov     edi, eax
0x18000e5df  cmp     qword ptr [rsi], 0
0x18000e5e3  jnz     short loc_18000E5F9
0x18000e5e5  test    edi, edi
0x18000e5e7  jnz     short loc_18000E5F9
0x18000e5e9  mov     r9, rsi; void **
0x18000e5ec  mov     r8, r15; struct _GUID *
0x18000e5ef  mov     rdx, rbp; struct _GUID *
0x18000e5f2  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000e5f7  mov     edi, eax
0x18000e5f9  mov     eax, edi
0x18000e5fb  add     rsp, 28h
0x18000e5ff  pop     r15
0x18000e601  pop     r14
0x18000e603  pop     rdi
0x18000e604  pop     rsi
0x18000e605  pop     rbp
0x18000e606  pop     rbx
0x18000e607  retn
```
