# CWbemObjectSink::CreateObjectSink(CWbemObjectSink * *,CSWbemServices *,IDispatch *,IDispatch *,bool,ushort *)

- ea: `0x180028d54`
- end: `0x180028e42`
- name: `?CreateObjectSink@CWbemObjectSink@@SAPEAUIWbemObjectSink@@PEAPEAV1@PEAVCSWbemServices@@PEAUIDispatch@@2_NPEAG@Z`
- size: `238`
- prototype: `static struct IWbemObjectSink *(struct CWbemObjectSink **, struct CSWbemServices *, struct IDispatch *, struct IDispatch *, bool, unsigned __int16 *)`
- caller_count: `11`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800296a0`
- `0x1800298b0`
- `0x180029a70`
- `0x180029c10`
- `0x180029d90`
- `0x180029f10`
- `0x18002a090`
- `0x18002a200`
- `0x18002a4e0`
- `0x18002a6d0`
- `0x18002abf0`

## callees

- `0x18000311c`
- `0x18000c0b0`
- `0x180018130`
- `0x1800287bc`
- `0x180028ca8`
- `0x180028d54`
- `0x180028ecc`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180028d80`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180028d80`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IWbemObjectSink *__fastcall CWbemObjectSink::CreateObjectSink(
        struct CWbemObjectSink **a1,
        struct CSWbemServices *a2,
        struct IDispatch *a3,
        struct IDispatch *a4,
        bool a5,
        unsigned __int16 *a6)
{
  struct IWbemObjectSink *ObjectStub; // rdi
  CWbemObjectSink *v11; // rcx
  CWbemObjectSink *v12; // rbx
  unsigned int v13; // edx
  CSWbemServices *v14; // rcx
  struct IWbemServices *IWbemServices; // rax
  CWbemObjectSink *v17; // [rsp+50h] [rbp+8h] BYREF

  ObjectStub = 0;
  if ( !a3 )
    goto LABEL_11;
  v11 = (CWbemObjectSink *)CWin32DefaultArena::WbemMemAlloc(0x68u);
  v17 = v11;
  if ( v11 )
    v12 = CWbemObjectSink::CWbemObjectSink(v11, a2, a3, a4, a5, a6);
  else
    v12 = 0;
  if ( v12 )
  {
    ObjectStub = CWbemObjectSink::GetObjectStub(v12);
    if ( ObjectStub )
    {
      if ( *((_QWORD *)v12 + 3) )
      {
        v14 = (CSWbemServices *)*((_QWORD *)v12 + 1);
        if ( v14 )
        {
          v17 = 0;
          IWbemServices = CSWbemServices::GetIWbemServices(v14);
          ATL::CComPtr<IWbemServices>::Attach(&v17, IWbemServices);
          (*(void (__fastcall **)(_QWORD, struct IWbemObjectSink *, CWbemObjectSink *))(**((_QWORD **)v12 + 3) + 48LL))(
            *((_QWORD *)v12 + 3),
            ObjectStub,
            v17);
          ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>((__int64 *)&v17);
        }
      }
      goto LABEL_12;
    }
    CWbemObjectSink::`scalar deleting destructor'(v12, v13);
LABEL_11:
    v12 = 0;
  }
LABEL_12:
  *a1 = v12;
  return ObjectStub;
}

```

## disassembly

```asm
0x180028d54  mov     [rsp+arg_8], rbx
0x180028d59  mov     [rsp+arg_10], rbp
0x180028d5e  push    rsi
0x180028d5f  push    rdi
0x180028d60  push    r14
0x180028d62  sub     rsp, 30h
0x180028d66  mov     rbp, r9
0x180028d69  mov     rbx, r8
0x180028d6c  mov     r14, rdx
0x180028d6f  mov     rsi, rcx
0x180028d72  xor     edi, edi
0x180028d74  test    r8, r8
0x180028d77  jz      loc_180028E27
0x180028d7d  lea     ecx, [rdi+68h]
0x180028d80  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180028d86  mov     rcx, rax; this
0x180028d89  mov     [rsp+48h+arg_0], rax
0x180028d8e  test    rax, rax
0x180028d91  jz      short loc_180028DB8
0x180028d93  mov     rax, [rsp+48h+arg_28]
0x180028d98  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x180028d9d  mov     al, [rsp+48h+arg_20]
0x180028da1  mov     [rsp+48h+var_28], al; bool
0x180028da5  mov     r9, rbp; struct IDispatch *
0x180028da8  mov     r8, rbx; struct IDispatch *
0x180028dab  mov     rdx, r14; struct CSWbemServices *
0x180028dae  call    ??0CWbemObjectSink@@QEAA@PEAVCSWbemServices@@PEAUIDispatch@@1_NPEAG@Z; CWbemObjectSink::CWbemObjectSink(CSWbemServices *,IDispatch *,IDispatch *,bool,ushort *)
0x180028db3  mov     rbx, rax
0x180028db6  jmp     short loc_180028DBA
0x180028db8  xor     ebx, ebx
0x180028dba  test    rbx, rbx
0x180028dbd  jz      short loc_180028E29
0x180028dbf  mov     rcx, rbx; this
0x180028dc2  call    ?GetObjectStub@CWbemObjectSink@@QEAAPEAUIWbemObjectSink@@XZ; CWbemObjectSink::GetObjectStub(void)
0x180028dc7  mov     rdi, rax
0x180028dca  test    rax, rax
0x180028dcd  jz      short loc_180028E1F
0x180028dcf  cmp     qword ptr [rbx+18h], 0
0x180028dd4  jz      short loc_180028E29
0x180028dd6  mov     rcx, [rbx+8]; this
0x180028dda  test    rcx, rcx
0x180028ddd  jz      short loc_180028E29
0x180028ddf  mov     [rsp+48h+arg_0], 0
0x180028de8  call    ?GetIWbemServices@CSWbemServices@@QEAAPEAUIWbemServices@@XZ; CSWbemServices::GetIWbemServices(void)
0x180028ded  mov     rdx, rax
0x180028df0  lea     rcx, [rsp+48h+arg_0]
0x180028df5  call    ?Attach@?$CComPtr@UIWbemServices@@@ATL@@QEAAXPEAUIWbemServices@@@Z; ATL::CComPtr<IWbemServices>::Attach(IWbemServices *)
0x180028dfa  mov     rcx, [rbx+18h]
0x180028dfe  mov     rax, [rcx]
0x180028e01  mov     r8, [rsp+48h+arg_0]
0x180028e06  mov     rdx, rdi
0x180028e09  mov     rax, [rax+30h]
0x180028e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e12  nop
0x180028e13  lea     rcx, [rsp+48h+arg_0]
0x180028e18  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180028e1d  jmp     short loc_180028E29
0x180028e1f  mov     rcx, rbx; this
0x180028e22  call    ??_GCWbemObjectSink@@QEAAPEAXI@Z; CWbemObjectSink::`scalar deleting destructor'(uint)
0x180028e27  xor     ebx, ebx
0x180028e29  mov     [rsi], rbx
0x180028e2c  mov     rax, rdi
0x180028e2f  mov     rbx, [rsp+48h+arg_8]
0x180028e34  mov     rbp, [rsp+48h+arg_10]
0x180028e39  add     rsp, 30h
0x180028e3d  pop     r14
0x180028e3f  pop     rdi
0x180028e40  pop     rsi
0x180028e41  retn
```
