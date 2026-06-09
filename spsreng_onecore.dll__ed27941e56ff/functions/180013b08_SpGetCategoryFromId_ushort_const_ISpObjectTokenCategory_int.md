# SpGetCategoryFromId(ushort const *,ISpObjectTokenCategory * *,int)

- ea: `0x180013b08`
- end: `0x180013b98`
- name: `?SpGetCategoryFromId@@YAJPEBGPEAPEAUISpObjectTokenCategory@@H@Z`
- size: `144`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct ISpObjectTokenCategory **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013948`

## callees

- `0x180002db8`
- `0x180013b08`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b42`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpGetCategoryFromId(const unsigned __int16 *a1, struct ISpObjectTokenCategory **a2)
{
  __int64 v4; // rdx
  HRESULT Instance; // ebx
  struct ISpObjectTokenCategory *v6; // rax
  struct ISpObjectTokenCategory *v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  Instance = CoCreateInstance(
               &CLSID_SpObjectTokenCategory,
               0,
               0x17u,
               &GUID_2d3d3845_39af_4850_bbf9_40b49780011d,
               (LPVOID *)&v8);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct ISpObjectTokenCategory *, const unsigned __int16 *, _QWORD))v8->lpVtbl->SetId)(
                 v8,
                 a1,
                 0);
    if ( Instance >= 0 )
    {
      v6 = v8;
      v8 = 0;
      *a2 = v6;
    }
  }
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v8, v4);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180013b08  mov     r11, rsp
0x180013b0b  mov     [r11+8], rbx
0x180013b0f  mov     [r11+10h], rsi
0x180013b13  push    rdi
0x180013b14  sub     rsp, 30h
0x180013b18  mov     rdi, rdx
0x180013b1b  mov     rsi, rcx
0x180013b1e  mov     qword ptr [r11+20h], 0
0x180013b26  lea     rax, [r11+20h]
0x180013b2a  mov     [r11-18h], rax
0x180013b2e  lea     r9, _GUID_2d3d3845_39af_4850_bbf9_40b49780011d; riid
0x180013b35  xor     edx, edx; pUnkOuter
0x180013b37  lea     r8d, [rdx+17h]; dwClsContext
0x180013b3b  lea     rcx, CLSID_SpObjectTokenCategory; rclsid
0x180013b42  call    cs:__imp_CoCreateInstance
0x180013b48  mov     ebx, eax
0x180013b4a  test    eax, eax
0x180013b4c  js      short loc_180013B7C
0x180013b4e  mov     rcx, [rsp+38h+arg_18]
0x180013b53  mov     rax, [rcx]
0x180013b56  xor     r8d, r8d
0x180013b59  mov     rdx, rsi
0x180013b5c  mov     rax, [rax+78h]
0x180013b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b65  mov     ebx, eax
0x180013b67  test    eax, eax
0x180013b69  js      short loc_180013B7C
0x180013b6b  mov     rax, [rsp+38h+arg_18]
0x180013b70  mov     [rsp+38h+arg_18], 0
0x180013b79  mov     [rdi], rax
0x180013b7c  lea     rcx, [rsp+38h+arg_18]
0x180013b81  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180013b86  mov     eax, ebx
0x180013b88  mov     rbx, [rsp+38h+arg_0]
0x180013b8d  mov     rsi, [rsp+38h+arg_8]
0x180013b92  add     rsp, 30h
0x180013b96  pop     rdi
0x180013b97  retn
```
