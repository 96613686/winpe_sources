# DllGetClassObject

- ea: `0x1800138a0`
- end: `0x180013998`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180010adc`
- `0x1800138a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001394e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001394e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013923`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013923`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  v7 = qword_180021C98;
  if ( qword_180021C98 )
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
            EnterCriticalSection(&stru_180021280);
            if ( !*v8 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                     *(_QWORD *)(v7 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v7 + 32);
            LeaveCriticalSection(&stru_180021280);
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
0x1800138a0  push    rbx
0x1800138a2  push    rbp
0x1800138a3  push    rsi
0x1800138a4  push    rdi
0x1800138a5  push    r14
0x1800138a7  push    r15
0x1800138a9  sub     rsp, 28h
0x1800138ad  mov     rsi, r8
0x1800138b0  mov     r15, rdx
0x1800138b3  mov     rbp, rcx
0x1800138b6  test    r8, r8
0x1800138b9  jnz     short loc_1800138C5
0x1800138bb  mov     edi, 80004003h
0x1800138c0  jmp     loc_180013989
0x1800138c5  mov     qword ptr [r8], 0
0x1800138cc  xor     edi, edi
0x1800138ce  mov     rbx, cs:qword_180021C98
0x1800138d5  test    rbx, rbx
0x1800138d8  jz      loc_18001396F
0x1800138de  jmp     short loc_18001390C
0x1800138e0  cmp     [rbx+10h], rdi
0x1800138e4  jz      short loc_180013908
0x1800138e6  mov     rcx, [rbx]
0x1800138e9  mov     eax, [rcx]
0x1800138eb  cmp     [rbp+0], eax
0x1800138ee  jnz     short loc_180013908
0x1800138f0  mov     eax, [rcx+4]
0x1800138f3  cmp     [rbp+4], eax
0x1800138f6  jnz     short loc_180013908
0x1800138f8  mov     eax, [rcx+8]
0x1800138fb  cmp     [rbp+8], eax
0x1800138fe  jnz     short loc_180013908
0x180013900  mov     eax, [rcx+0Ch]
0x180013903  cmp     [rbp+0Ch], eax
0x180013906  jz      short loc_180013913
0x180013908  add     rbx, 48h ; 'H'
0x18001390c  cmp     [rbx], rdi
0x18001390f  jnz     short loc_1800138E0
0x180013911  jmp     short loc_18001396F
0x180013913  lea     r14, [rbx+20h]
0x180013917  cmp     [r14], rdi
0x18001391a  jnz     short loc_180013954
0x18001391c  lea     rcx, stru_180021280; lpCriticalSection
0x180013923  call    cs:__imp_EnterCriticalSection
0x180013929  cmp     [r14], rdi
0x18001392c  jnz     short loc_180013947
0x18001392e  mov     r8, r14
0x180013931  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180013938  mov     rcx, [rbx+18h]
0x18001393c  mov     rax, [rbx+10h]
0x180013940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013945  mov     edi, eax
0x180013947  lea     rcx, stru_180021280; lpCriticalSection
0x18001394e  call    cs:__imp_LeaveCriticalSection
0x180013954  mov     rcx, [r14]
0x180013957  test    rcx, rcx
0x18001395a  jz      short loc_18001396F
0x18001395c  mov     rax, [rcx]
0x18001395f  mov     r8, rsi
0x180013962  mov     rdx, r15
0x180013965  mov     rax, [rax]
0x180013968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001396d  mov     edi, eax
0x18001396f  cmp     qword ptr [rsi], 0
0x180013973  jnz     short loc_180013989
0x180013975  test    edi, edi
0x180013977  jnz     short loc_180013989
0x180013979  mov     r9, rsi; void **
0x18001397c  mov     r8, r15; struct _GUID *
0x18001397f  mov     rdx, rbp; struct _GUID *
0x180013982  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180013987  mov     edi, eax
0x180013989  mov     eax, edi
0x18001398b  add     rsp, 28h
0x18001398f  pop     r15
0x180013991  pop     r14
0x180013993  pop     rdi
0x180013994  pop     rsi
0x180013995  pop     rbp
0x180013996  pop     rbx
0x180013997  retn
```
