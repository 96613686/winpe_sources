# SpGetTokenFromId(ushort const *,ISpObjectToken * *,int)

- ea: `0x1800b13a0`
- end: `0x1800b1432`
- name: `?SpGetTokenFromId@@YAJPEBGPEAPEAUISpObjectToken@@H@Z`
- size: `146`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct ISpObjectToken **, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b14d8`
- `0x1800ca130`

## callees

- `0x180002db8`
- `0x1800b13a0`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b13da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b13da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpGetTokenFromId(const unsigned __int16 *a1, struct ISpObjectToken **a2)
{
  HRESULT Instance; // ebx
  struct ISpObjectToken *v5; // rax
  struct ISpObjectToken *v7; // [rsp+58h] [rbp+20h] BYREF

  v7 = 0;
  Instance = CoCreateInstance(&CLSID_SpObjectToken, 0, 0x17u, &GUID_14056589_e16c_11d2_bb90_00c04f8ee6c0, (LPVOID *)&v7);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct ISpObjectToken *, _QWORD, const unsigned __int16 *, _QWORD))v7->lpVtbl->SetId)(
                 v7,
                 0,
                 a1,
                 0);
    if ( Instance >= 0 )
    {
      v5 = v7;
      v7 = 0;
      *a2 = v5;
    }
  }
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v7);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800b13a0  mov     r11, rsp
0x1800b13a3  mov     [r11+8], rbx
0x1800b13a7  mov     [r11+10h], rsi
0x1800b13ab  push    rdi
0x1800b13ac  sub     rsp, 30h
0x1800b13b0  mov     rdi, rdx
0x1800b13b3  mov     rsi, rcx
0x1800b13b6  mov     qword ptr [r11+20h], 0
0x1800b13be  lea     rax, [r11+20h]
0x1800b13c2  mov     [r11-18h], rax
0x1800b13c6  lea     r9, _GUID_14056589_e16c_11d2_bb90_00c04f8ee6c0; riid
0x1800b13cd  xor     edx, edx; pUnkOuter
0x1800b13cf  lea     r8d, [rdx+17h]; dwClsContext
0x1800b13d3  lea     rcx, CLSID_SpObjectToken; rclsid
0x1800b13da  call    cs:__imp_CoCreateInstance
0x1800b13e0  mov     ebx, eax
0x1800b13e2  test    eax, eax
0x1800b13e4  js      short loc_1800B1416
0x1800b13e6  mov     rcx, [rsp+38h+arg_18]
0x1800b13eb  mov     rax, [rcx]
0x1800b13ee  xor     r9d, r9d
0x1800b13f1  mov     r8, rsi
0x1800b13f4  xor     edx, edx
0x1800b13f6  mov     rax, [rax+78h]
0x1800b13fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b13ff  mov     ebx, eax
0x1800b1401  test    eax, eax
0x1800b1403  js      short loc_1800B1416
0x1800b1405  mov     rax, [rsp+38h+arg_18]
0x1800b140a  mov     [rsp+38h+arg_18], 0
0x1800b1413  mov     [rdi], rax
0x1800b1416  lea     rcx, [rsp+38h+arg_18]
0x1800b141b  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800b1420  mov     eax, ebx
0x1800b1422  mov     rbx, [rsp+38h+arg_0]
0x1800b1427  mov     rsi, [rsp+38h+arg_8]
0x1800b142c  add     rsp, 30h
0x1800b1430  pop     rdi
0x1800b1431  retn
```
