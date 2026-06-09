# DllGetClassObject

- ea: `0x18000c4e0`
- end: `0x18000c5db`
- name: `DllGetClassObject`
- size: `251`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c4e0`
- `0x18000daec`
- `0x180015540`
- `0x180016908`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c561`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c561`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID *v5; // rdi
  HRESULT v7; // ebp
  __int64 v8; // r14
  _RTL_CRITICAL_SECTION *v9; // [rsp+28h] [rbp-50h] BYREF
  char v10; // [rsp+30h] [rbp-48h]

  v5 = rclsid;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v7 = 0;
  v8 = qword_180049CB8;
  if ( qword_180049CB8 )
  {
    while ( *(_QWORD *)v8 )
    {
      if ( *(_QWORD *)(v8 + 16) && (unsigned int)InlineIsEqualGUID(v5, *(_QWORD *)v8) )
      {
        if ( !*(_QWORD *)(v8 + 32) )
        {
          v9 = &stru_180048410;
          EnterCriticalSection(&stru_180048410);
          v10 = 1;
          if ( !*(_QWORD *)(v8 + 32) )
            v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v8 + 16))(
                   *(_QWORD *)(v8 + 24),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v8 + 32);
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v9);
        }
        rclsid = *(const IID *const *)(v8 + 32);
        if ( rclsid )
          v7 = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                 rclsid,
                 riid,
                 ppv);
        break;
      }
      v8 += 72;
    }
  }
  if ( !*ppv && !v7 )
    return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  return v7;
}

```

## disassembly

```asm
0x18000c4e0  push    rbx
0x18000c4e2  push    rbp
0x18000c4e3  push    rsi
0x18000c4e4  push    rdi
0x18000c4e5  push    r14
0x18000c4e7  push    r15
0x18000c4e9  sub     rsp, 48h
0x18000c4ed  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x18000c4f6  mov     rbx, r8
0x18000c4f9  mov     rsi, rdx
0x18000c4fc  mov     rdi, rcx
0x18000c4ff  test    r8, r8
0x18000c502  jnz     short loc_18000C516
0x18000c504  mov     eax, 80004003h
0x18000c509  add     rsp, 48h
0x18000c50d  pop     r15
0x18000c50f  pop     r14
0x18000c511  pop     rdi
0x18000c512  pop     rsi
0x18000c513  pop     rbp
0x18000c514  pop     rbx
0x18000c515  retn
0x18000c516  mov     qword ptr [r8], 0
0x18000c51d  xor     ebp, ebp
0x18000c51f  mov     r14, cs:qword_180049CB8
0x18000c526  test    r14, r14
0x18000c529  jz      loc_18000C5B2
0x18000c52f  mov     rdx, [r14]
0x18000c532  test    rdx, rdx
0x18000c535  jz      short loc_18000C5B2
0x18000c537  cmp     [r14+10h], rbp
0x18000c53b  jz      short loc_18000C549
0x18000c53d  mov     rcx, rdi
0x18000c540  call    InlineIsEqualGUID
0x18000c545  test    eax, eax
0x18000c547  jnz     short loc_18000C54F
0x18000c549  add     r14, 48h ; 'H'
0x18000c54d  jmp     short loc_18000C52F
0x18000c54f  cmp     [r14+20h], rbp
0x18000c553  jnz     short loc_18000C596
0x18000c555  lea     rcx, stru_180048410; lpCriticalSection
0x18000c55c  mov     [rsp+78h+var_50], rcx
0x18000c561  call    cs:__imp_EnterCriticalSection
0x18000c567  mov     [rsp+78h+var_48], 1
0x18000c56c  cmp     [r14+20h], rbp
0x18000c570  jnz     short loc_18000C58C
0x18000c572  lea     r8, [r14+20h]
0x18000c576  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c57d  mov     rcx, [r14+18h]
0x18000c581  mov     rax, [r14+10h]
0x18000c585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c58a  mov     ebp, eax
0x18000c58c  lea     rcx, [rsp+78h+var_50]
0x18000c591  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000c596  mov     rcx, [r14+20h]
0x18000c59a  test    rcx, rcx
0x18000c59d  jz      short loc_18000C5B2
0x18000c59f  mov     rax, [rcx]
0x18000c5a2  mov     r8, rbx
0x18000c5a5  mov     rdx, rsi
0x18000c5a8  mov     rax, [rax]
0x18000c5ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5b0  mov     ebp, eax
0x18000c5b2  cmp     qword ptr [rbx], 0
0x18000c5b6  jnz     short loc_18000C5CC
0x18000c5b8  test    ebp, ebp
0x18000c5ba  jnz     short loc_18000C5CC
0x18000c5bc  mov     r9, rbx; void **
0x18000c5bf  mov     r8, rsi; struct _GUID *
0x18000c5c2  mov     rdx, rdi; struct _GUID *
0x18000c5c5  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000c5ca  mov     ebp, eax
0x18000c5cc  mov     eax, ebp
0x18000c5ce  add     rsp, 48h
0x18000c5d2  pop     r15
0x18000c5d4  pop     r14
0x18000c5d6  pop     rdi
0x18000c5d7  pop     rsi
0x18000c5d8  pop     rbp
0x18000c5d9  pop     rbx
0x18000c5da  retn
```
