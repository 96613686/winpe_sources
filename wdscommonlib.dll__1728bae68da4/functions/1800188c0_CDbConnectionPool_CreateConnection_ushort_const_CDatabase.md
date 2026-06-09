# CDbConnectionPool::CreateConnection(ushort const *,CDatabase *)

- ea: `0x1800188c0`
- end: `0x1800189b4`
- name: `?CreateConnection@CDbConnectionPool@@QEAAJPEBGPEAVCDatabase@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(LPVOID *ppv, const unsigned __int16 *, struct CDatabase *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800188c0`
- `0x180019020`
- `0x180031010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800188e8`
- `KERNEL32!EnterCriticalSection` at `0x1800188e8`
- `KERNEL32!LeaveCriticalSection` at `0x180018928`
- `KERNEL32!LeaveCriticalSection` at `0x180018939`
- `KERNEL32!LeaveCriticalSection` at `0x180018928`
- `KERNEL32!LeaveCriticalSection` at `0x180018939`
- `OLE32!CoCreateInstance` at `0x180018913`
- `OLE32!CoCreateInstance` at `0x180018913`

## pseudocode

```c
__int64 __fastcall CDbConnectionPool::CreateConnection(LPVOID *ppv, const unsigned __int16 *a2, struct CDatabase *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  HRESULT Instance; // ebx
  struct IUnknown *v9; // [rsp+60h] [rbp+8h] BYREF

  v9 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)(ppv + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(ppv + 1));
  if ( *ppv || (Instance = CoCreateInstance(&CLSID_MSDAINITIALIZE, 0, 1u, &IID_IDataInitialize, ppv), Instance >= 0) )
  {
    LeaveCriticalSection(v3);
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *, GUID *, struct IUnknown **))(*(_QWORD *)*ppv + 24LL))(
                 *ppv,
                 0,
                 1,
                 a2,
                 &IID_IDBInitialize,
                 &v9);
    if ( Instance >= 0 )
      Instance = CDatabase::Initialize(a3, v9);
  }
  else
  {
    LeaveCriticalSection(v3);
  }
  if ( v9 )
    ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800188c0  mov     [rsp+arg_8], rbx
0x1800188c5  mov     [rsp+arg_10], rbp
0x1800188ca  push    rsi
0x1800188cb  push    rdi
0x1800188cc  push    r14
0x1800188ce  sub     rsp, 40h
0x1800188d2  and     [rsp+58h+arg_0], 0
0x1800188d8  lea     rsi, [rcx+8]
0x1800188dc  mov     rdi, rcx
0x1800188df  mov     rbp, r8
0x1800188e2  mov     rcx, rsi; lpCriticalSection
0x1800188e5  mov     r14, rdx
0x1800188e8  call    cs:__imp_EnterCriticalSection
0x1800188ef  nop     dword ptr [rax+rax+00h]
0x1800188f4  cmp     qword ptr [rdi], 0
0x1800188f8  jnz     short loc_180018936
0x1800188fa  xor     edx, edx; pUnkOuter
0x1800188fc  mov     [rsp+58h+ppv], rdi; ppv
0x180018901  lea     r9, IID_IDataInitialize; riid
0x180018908  lea     rcx, CLSID_MSDAINITIALIZE; rclsid
0x18001890f  lea     r8d, [rdx+1]; dwClsContext
0x180018913  call    cs:__imp_CoCreateInstance
0x18001891a  nop     dword ptr [rax+rax+00h]
0x18001891f  mov     ebx, eax
0x180018921  test    eax, eax
0x180018923  jns     short loc_180018936
0x180018925  mov     rcx, rsi; lpCriticalSection
0x180018928  call    cs:__imp_LeaveCriticalSection
0x18001892f  nop     dword ptr [rax+rax+00h]
0x180018934  jmp     short loc_180018988
0x180018936  mov     rcx, rsi; lpCriticalSection
0x180018939  call    cs:__imp_LeaveCriticalSection
0x180018940  nop     dword ptr [rax+rax+00h]
0x180018945  mov     rcx, [rdi]
0x180018948  lea     rdx, [rsp+58h+arg_0]
0x18001894d  mov     [rsp+58h+var_30], rdx
0x180018952  mov     r9, r14
0x180018955  lea     rdx, IID_IDBInitialize
0x18001895c  mov     [rsp+58h+ppv], rdx
0x180018961  xor     edx, edx
0x180018963  mov     rax, [rcx]
0x180018966  lea     r8d, [rdx+1]
0x18001896a  mov     rax, [rax+18h]
0x18001896e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018973  mov     ebx, eax
0x180018975  test    eax, eax
0x180018977  js      short loc_180018988
0x180018979  mov     rdx, [rsp+58h+arg_0]; struct IUnknown *
0x18001897e  mov     rcx, rbp; this
0x180018981  call    ?Initialize@CDatabase@@QEAAJPEAUIUnknown@@@Z; CDatabase::Initialize(IUnknown *)
0x180018986  mov     ebx, eax
0x180018988  mov     rcx, [rsp+58h+arg_0]
0x18001898d  test    rcx, rcx
0x180018990  jz      short loc_18001899E
0x180018992  mov     rax, [rcx]
0x180018995  mov     rax, [rax+10h]
0x180018999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001899e  mov     rbp, [rsp+58h+arg_10]
0x1800189a3  mov     eax, ebx
0x1800189a5  mov     rbx, [rsp+58h+arg_8]
0x1800189aa  add     rsp, 40h
0x1800189ae  pop     r14
0x1800189b0  pop     rdi
0x1800189b1  pop     rsi
0x1800189b2  retn
```
