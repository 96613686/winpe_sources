# CDbConnectionPool::CreateConnection(ushort const *,CDatabase *)

- ea: `0x180017b00`
- end: `0x180017bf4`
- name: `?CreateConnection@CDbConnectionPool@@QEAAJPEBGPEAVCDatabase@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(LPVOID *ppv, const unsigned __int16 *, struct CDatabase *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017b00`
- `0x180018250`
- `0x180030010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180017b28`
- `KERNEL32!EnterCriticalSection` at `0x180017b28`
- `KERNEL32!LeaveCriticalSection` at `0x180017b68`
- `KERNEL32!LeaveCriticalSection` at `0x180017b79`
- `KERNEL32!LeaveCriticalSection` at `0x180017b68`
- `KERNEL32!LeaveCriticalSection` at `0x180017b79`
- `OLE32!CoCreateInstance` at `0x180017b53`
- `OLE32!CoCreateInstance` at `0x180017b53`

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
0x180017b00  mov     [rsp+arg_8], rbx
0x180017b05  mov     [rsp+arg_10], rbp
0x180017b0a  push    rsi
0x180017b0b  push    rdi
0x180017b0c  push    r14
0x180017b0e  sub     rsp, 40h
0x180017b12  and     [rsp+58h+arg_0], 0
0x180017b18  lea     rsi, [rcx+8]
0x180017b1c  mov     rdi, rcx
0x180017b1f  mov     rbp, r8
0x180017b22  mov     rcx, rsi; lpCriticalSection
0x180017b25  mov     r14, rdx
0x180017b28  call    cs:__imp_EnterCriticalSection
0x180017b2f  nop     dword ptr [rax+rax+00h]
0x180017b34  cmp     qword ptr [rdi], 0
0x180017b38  jnz     short loc_180017B76
0x180017b3a  xor     edx, edx; pUnkOuter
0x180017b3c  mov     [rsp+58h+ppv], rdi; ppv
0x180017b41  lea     r9, IID_IDataInitialize; riid
0x180017b48  lea     rcx, CLSID_MSDAINITIALIZE; rclsid
0x180017b4f  lea     r8d, [rdx+1]; dwClsContext
0x180017b53  call    cs:__imp_CoCreateInstance
0x180017b5a  nop     dword ptr [rax+rax+00h]
0x180017b5f  mov     ebx, eax
0x180017b61  test    eax, eax
0x180017b63  jns     short loc_180017B76
0x180017b65  mov     rcx, rsi; lpCriticalSection
0x180017b68  call    cs:__imp_LeaveCriticalSection
0x180017b6f  nop     dword ptr [rax+rax+00h]
0x180017b74  jmp     short loc_180017BC8
0x180017b76  mov     rcx, rsi; lpCriticalSection
0x180017b79  call    cs:__imp_LeaveCriticalSection
0x180017b80  nop     dword ptr [rax+rax+00h]
0x180017b85  mov     rcx, [rdi]
0x180017b88  lea     rdx, [rsp+58h+arg_0]
0x180017b8d  mov     [rsp+58h+var_30], rdx
0x180017b92  mov     r9, r14
0x180017b95  lea     rdx, IID_IDBInitialize
0x180017b9c  mov     [rsp+58h+ppv], rdx
0x180017ba1  xor     edx, edx
0x180017ba3  mov     rax, [rcx]
0x180017ba6  lea     r8d, [rdx+1]
0x180017baa  mov     rax, [rax+18h]
0x180017bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bb3  mov     ebx, eax
0x180017bb5  test    eax, eax
0x180017bb7  js      short loc_180017BC8
0x180017bb9  mov     rdx, [rsp+58h+arg_0]; struct IUnknown *
0x180017bbe  mov     rcx, rbp; this
0x180017bc1  call    ?Initialize@CDatabase@@QEAAJPEAUIUnknown@@@Z; CDatabase::Initialize(IUnknown *)
0x180017bc6  mov     ebx, eax
0x180017bc8  mov     rcx, [rsp+58h+arg_0]
0x180017bcd  test    rcx, rcx
0x180017bd0  jz      short loc_180017BDE
0x180017bd2  mov     rax, [rcx]
0x180017bd5  mov     rax, [rax+10h]
0x180017bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bde  mov     rbp, [rsp+58h+arg_10]
0x180017be3  mov     eax, ebx
0x180017be5  mov     rbx, [rsp+58h+arg_8]
0x180017bea  add     rsp, 40h
0x180017bee  pop     r14
0x180017bf0  pop     rdi
0x180017bf1  pop     rsi
0x180017bf2  retn
```
