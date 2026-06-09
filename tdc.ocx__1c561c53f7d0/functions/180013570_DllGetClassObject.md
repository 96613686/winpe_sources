# DllGetClassObject

- ea: `0x180013570`
- end: `0x180013668`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ff44`
- `0x180013570`
- `0x180015010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001361e`
- `KERNEL32!LeaveCriticalSection` at `0x18001361e`
- `KERNEL32!EnterCriticalSection` at `0x1800135f3`
- `KERNEL32!EnterCriticalSection` at `0x1800135f3`

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
  v7 = qword_18001BDB8;
  if ( qword_18001BDB8 )
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
            EnterCriticalSection(&stru_18001B640);
            if ( !*v8 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                     *(_QWORD *)(v7 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v7 + 32);
            LeaveCriticalSection(&stru_18001B640);
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
0x180013570  push    rbx
0x180013572  push    rbp
0x180013573  push    rsi
0x180013574  push    rdi
0x180013575  push    r14
0x180013577  push    r15
0x180013579  sub     rsp, 28h
0x18001357d  mov     rsi, r8
0x180013580  mov     r15, rdx
0x180013583  mov     rbp, rcx
0x180013586  test    r8, r8
0x180013589  jnz     short loc_180013595
0x18001358b  mov     edi, 80004003h
0x180013590  jmp     loc_180013659
0x180013595  mov     qword ptr [r8], 0
0x18001359c  xor     edi, edi
0x18001359e  mov     rbx, cs:qword_18001BDB8
0x1800135a5  test    rbx, rbx
0x1800135a8  jz      loc_18001363F
0x1800135ae  jmp     short loc_1800135DC
0x1800135b0  cmp     [rbx+10h], rdi
0x1800135b4  jz      short loc_1800135D8
0x1800135b6  mov     rcx, [rbx]
0x1800135b9  mov     eax, [rcx]
0x1800135bb  cmp     [rbp+0], eax
0x1800135be  jnz     short loc_1800135D8
0x1800135c0  mov     eax, [rcx+4]
0x1800135c3  cmp     [rbp+4], eax
0x1800135c6  jnz     short loc_1800135D8
0x1800135c8  mov     eax, [rcx+8]
0x1800135cb  cmp     [rbp+8], eax
0x1800135ce  jnz     short loc_1800135D8
0x1800135d0  mov     eax, [rcx+0Ch]
0x1800135d3  cmp     [rbp+0Ch], eax
0x1800135d6  jz      short loc_1800135E3
0x1800135d8  add     rbx, 48h ; 'H'
0x1800135dc  cmp     [rbx], rdi
0x1800135df  jnz     short loc_1800135B0
0x1800135e1  jmp     short loc_18001363F
0x1800135e3  lea     r14, [rbx+20h]
0x1800135e7  cmp     [r14], rdi
0x1800135ea  jnz     short loc_180013624
0x1800135ec  lea     rcx, stru_18001B640; lpCriticalSection
0x1800135f3  call    cs:__imp_EnterCriticalSection
0x1800135f9  cmp     [r14], rdi
0x1800135fc  jnz     short loc_180013617
0x1800135fe  mov     rcx, [rbx+18h]
0x180013602  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180013609  mov     rax, [rbx+10h]
0x18001360d  mov     r8, r14
0x180013610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013615  mov     edi, eax
0x180013617  lea     rcx, stru_18001B640; lpCriticalSection
0x18001361e  call    cs:__imp_LeaveCriticalSection
0x180013624  mov     rcx, [r14]
0x180013627  test    rcx, rcx
0x18001362a  jz      short loc_18001363F
0x18001362c  mov     rax, [rcx]
0x18001362f  mov     r8, rsi
0x180013632  mov     rdx, r15
0x180013635  mov     rax, [rax]
0x180013638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001363d  mov     edi, eax
0x18001363f  cmp     qword ptr [rsi], 0
0x180013643  jnz     short loc_180013659
0x180013645  test    edi, edi
0x180013647  jnz     short loc_180013659
0x180013649  mov     r9, rsi; void **
0x18001364c  mov     r8, r15; struct _GUID *
0x18001364f  mov     rdx, rbp; struct _GUID *
0x180013652  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180013657  mov     edi, eax
0x180013659  mov     eax, edi
0x18001365b  add     rsp, 28h
0x18001365f  pop     r15
0x180013661  pop     r14
0x180013663  pop     rdi
0x180013664  pop     rsi
0x180013665  pop     rbp
0x180013666  pop     rbx
0x180013667  retn
```
