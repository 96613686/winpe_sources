# WindowsFireall_EnableFWGroup

- ea: `0x18004101c`
- end: `0x180041125`
- name: `WindowsFireall_EnableFWGroup`
- size: `265`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004112c`
- `0x18004117c`
- `0x1800411cc`

## callees

- `0x180012914`
- `0x18004101c`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004104e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004104e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004107b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004107b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800410fe`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800410fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180041110`
- `OLEAUT32!__imp_SysFreeString` at `0x180041110`

## pseudocode

```c
__int64 __fastcall WindowsFireall_EnableFWGroup(int a1, _DWORD *a2, BSTR *a3)
{
  HRESULT v5; // ebx
  __int16 v7; // [rsp+50h] [rbp+20h] BYREF
  __int16 v8; // [rsp+52h] [rbp+22h]
  unsigned int v9; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  v8 = HIWORD(a1);
  ppv = 0;
  v9 = 0;
  v7 = 0;
  v5 = CoInitializeEx(0, 0);
  if ( v5 >= 0 )
  {
    v5 = CoCreateInstance(
           &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
           0,
           1u,
           &GUID_98325047_c671_4174_8d81_defcd3f03186,
           &ppv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 56LL))(ppv, &v9);
      if ( v5 >= 0 )
      {
        if ( a2 )
          *a2 = (*(unsigned int (__fastcall **)(LPVOID, _QWORD, BSTR, __int16 *))(*(_QWORD *)ppv + 168LL))(
                  ppv,
                  v9,
                  *a3,
                  &v7)
             || v7;
        v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, BSTR, __int64))(*(_QWORD *)ppv + 160LL))(
               ppv,
               v9,
               *a3,
               0xFFFFFFFFLL);
        if ( v5 == 1 )
          v5 = 0;
      }
    }
    CoUninitialize();
  }
  ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(&ppv);
  SysFreeString(*a3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004101c  mov     [rsp-18h+arg_8], rbx
0x180041021  mov     [rsp-18h+arg_0], ecx
0x180041025  push    rbp
0x180041026  push    rsi
0x180041027  push    rdi
0x180041028  mov     rbp, rsp
0x18004102b  sub     rsp, 30h
0x18004102f  mov     rdi, rdx
0x180041032  mov     [rbp+arg_18], 0
0x18004103a  xor     eax, eax
0x18004103c  mov     [rbp+arg_10], 0
0x180041043  xor     edx, edx; dwCoInit
0x180041045  mov     word ptr [rbp+arg_0], ax
0x180041049  xor     ecx, ecx; pvReserved
0x18004104b  mov     rsi, r8
0x18004104e  call    cs:__imp_CoInitializeEx
0x180041054  mov     ebx, eax
0x180041056  test    eax, eax
0x180041058  js      loc_180041104
0x18004105e  xor     edx, edx; pUnkOuter
0x180041060  lea     rax, [rbp+arg_18]
0x180041064  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x18004106b  mov     [rsp+30h+ppv], rax; ppv
0x180041070  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x180041077  lea     r8d, [rdx+1]; dwClsContext
0x18004107b  call    cs:__imp_CoCreateInstance
0x180041081  mov     ebx, eax
0x180041083  test    eax, eax
0x180041085  js      short loc_1800410FE
0x180041087  mov     rcx, [rbp+arg_18]
0x18004108b  lea     rdx, [rbp+arg_10]
0x18004108f  mov     rax, [rcx]
0x180041092  mov     rax, [rax+38h]
0x180041096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004109b  mov     ebx, eax
0x18004109d  test    eax, eax
0x18004109f  js      short loc_1800410FE
0x1800410a1  test    rdi, rdi
0x1800410a4  jz      short loc_1800410D7
0x1800410a6  mov     rcx, [rbp+arg_18]
0x1800410aa  lea     r9, [rbp+arg_0]
0x1800410ae  mov     r8, [rsi]
0x1800410b1  mov     edx, [rbp+arg_10]
0x1800410b4  mov     rax, [rcx]
0x1800410b7  mov     rax, [rax+0A8h]
0x1800410be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410c3  test    eax, eax
0x1800410c5  jnz     short loc_1800410D1
0x1800410c7  cmp     ax, word ptr [rbp+arg_0]
0x1800410cb  jnz     short loc_1800410D1
0x1800410cd  mov     [rdi], eax
0x1800410cf  jmp     short loc_1800410D7
0x1800410d1  mov     dword ptr [rdi], 1
0x1800410d7  mov     rcx, [rbp+arg_18]
0x1800410db  or      r9d, 0FFFFFFFFh
0x1800410df  mov     r8, [rsi]
0x1800410e2  mov     edx, [rbp+arg_10]
0x1800410e5  mov     rax, [rcx]
0x1800410e8  mov     rax, [rax+0A0h]
0x1800410ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410f4  mov     ebx, eax
0x1800410f6  xor     eax, eax
0x1800410f8  cmp     ebx, 1
0x1800410fb  cmovz   ebx, eax
0x1800410fe  call    cs:__imp_CoUninitialize
0x180041104  lea     rcx, [rbp+arg_18]
0x180041108  call    ??1?$CComPtrBase@UINetFwPolicy2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INetFwPolicy2>::~CComPtrBase<INetFwPolicy2>(void)
0x18004110d  mov     rcx, [rsi]; bstrString
0x180041110  call    cs:__imp_SysFreeString
0x180041116  mov     eax, ebx
0x180041118  mov     rbx, [rsp+30h+arg_8]
0x18004111d  add     rsp, 30h
0x180041121  pop     rdi
0x180041122  pop     rsi
0x180041123  pop     rbp
0x180041124  retn
```
