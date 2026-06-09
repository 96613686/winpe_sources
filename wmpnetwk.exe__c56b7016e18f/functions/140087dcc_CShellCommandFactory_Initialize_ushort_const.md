# CShellCommandFactory::Initialize(ushort const *)

- ea: `0x140087dcc`
- end: `0x140087eee`
- name: `?Initialize@CShellCommandFactory@@QEAAJPEBG@Z`
- size: `290`
- prototype: `__int64 __fastcall(CShellCommandFactory *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400798c8`

## callees

- `0x14000c780`
- `0x140024688`
- `0x140045f20`
- `0x140087dcc`
- `0x140088124`
- `0x14009e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140087e53`
- `ole32!CoCreateInstance` at `0x140087e53`
- `ole32!CLSIDFromProgID` at `0x140087e21`
- `ole32!CLSIDFromProgID` at `0x140087e21`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CShellCommandFactory::Initialize(CShellCommandFactory *this, const unsigned __int16 *a2)
{
  int Libraries; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-30h] BYREF
  __int64 v6; // [rsp+38h] [rbp-28h] BYREF
  GUID clsid; // [rsp+40h] [rbp-20h] BYREF

  ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 8, a2);
  Libraries = CShellLibraryCache::LoadLibraries((CShellCommandFactory *)((char *)this + 16), (_QWORD *)this + 1);
  if ( Libraries >= 0 )
  {
    clsid = 0;
    Libraries = CLSIDFromProgID(L"Search.CollatorDSO.1", &clsid);
    if ( Libraries >= 0 )
    {
      ppv = 0;
      Libraries = CoCreateInstance(&clsid, 0, 1u, &GUID_0c733a8b_2a1c_11ce_ade5_00aa0044773d, &ppv);
      if ( Libraries >= 0 )
      {
        Libraries = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv);
        if ( Libraries >= 0 )
        {
          v6 = 0;
          Libraries = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                        ppv,
                        &GUID_0c733a5d_2a1c_11ce_ade5_00aa0044773d,
                        &v6);
          if ( Libraries >= 0 )
            Libraries = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, CShellCommandFactory *))(*(_QWORD *)v6 + 24LL))(
                          v6,
                          0,
                          &GUID_0c733a1d_2a1c_11ce_ade5_00aa0044773d,
                          this);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    }
  }
  return (unsigned int)Libraries;
}

```

## disassembly

```asm
0x140087dcc  mov     [rsp-8+arg_10], rbx
0x140087dd1  mov     [rsp-8+arg_18], rdi
0x140087dd6  push    rbp
0x140087dd7  mov     rbp, rsp
0x140087dda  sub     rsp, 60h
0x140087dde  mov     rax, cs:__security_cookie
0x140087de5  xor     rax, rsp
0x140087de8  mov     [rbp+var_10], rax
0x140087dec  mov     rdi, rcx
0x140087def  add     rcx, 8
0x140087df3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140087df8  lea     rcx, [rdi+10h]; this
0x140087dfc  lea     rdx, [rdi+8]
0x140087e00  call    ?LoadLibraries@CShellLibraryCache@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CShellLibraryCache::LoadLibraries(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x140087e05  mov     ebx, eax
0x140087e07  test    eax, eax
0x140087e09  js      loc_140087ECE
0x140087e0f  xorps   xmm0, xmm0
0x140087e12  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x140087e16  lea     rdx, [rbp+clsid]; lpclsid
0x140087e1a  lea     rcx, szProgID; "Search.CollatorDSO.1"
0x140087e21  call    cs:__imp_CLSIDFromProgID
0x140087e27  mov     ebx, eax
0x140087e29  test    eax, eax
0x140087e2b  js      loc_140087ECE
0x140087e31  mov     [rbp+var_30], 0
0x140087e39  lea     rax, [rbp+var_30]
0x140087e3d  mov     [rsp+60h+ppv], rax; ppv
0x140087e42  lea     r9, _GUID_0c733a8b_2a1c_11ce_ade5_00aa0044773d; riid
0x140087e49  xor     edx, edx; pUnkOuter
0x140087e4b  lea     r8d, [rdx+1]; dwClsContext
0x140087e4f  lea     rcx, [rbp+clsid]; rclsid
0x140087e53  call    cs:__imp_CoCreateInstance
0x140087e59  mov     ebx, eax
0x140087e5b  test    eax, eax
0x140087e5d  js      short loc_140087EC5
0x140087e5f  mov     rcx, [rbp+var_30]
0x140087e63  mov     rax, [rcx]
0x140087e66  mov     rax, [rax+18h]
0x140087e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087e6f  mov     ebx, eax
0x140087e71  test    eax, eax
0x140087e73  js      short loc_140087EC5
0x140087e75  mov     [rbp+var_28], 0
0x140087e7d  mov     rcx, [rbp+var_30]
0x140087e81  mov     rax, [rcx]
0x140087e84  lea     r8, [rbp+var_28]
0x140087e88  lea     rdx, _GUID_0c733a5d_2a1c_11ce_ade5_00aa0044773d
0x140087e8f  mov     rax, [rax]
0x140087e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087e97  mov     ebx, eax
0x140087e99  test    eax, eax
0x140087e9b  js      short loc_140087EBB
0x140087e9d  mov     rcx, [rbp+var_28]
0x140087ea1  mov     rax, [rcx]
0x140087ea4  mov     r9, rdi
0x140087ea7  lea     r8, _GUID_0c733a1d_2a1c_11ce_ade5_00aa0044773d
0x140087eae  xor     edx, edx
0x140087eb0  mov     rax, [rax+18h]
0x140087eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087eb9  mov     ebx, eax
0x140087ebb  lea     rcx, [rbp+var_28]
0x140087ebf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140087ec4  nop
0x140087ec5  lea     rcx, [rbp+var_30]
0x140087ec9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140087ece  mov     eax, ebx
0x140087ed0  mov     rcx, [rbp+var_10]
0x140087ed4  xor     rcx, rsp; StackCookie
0x140087ed7  call    __security_check_cookie
0x140087edc  lea     r11, [rsp+60h+var_s0]
0x140087ee1  mov     rbx, [r11+20h]
0x140087ee5  mov     rdi, [r11+28h]
0x140087ee9  mov     rsp, r11
0x140087eec  pop     rbp
0x140087eed  retn
```
