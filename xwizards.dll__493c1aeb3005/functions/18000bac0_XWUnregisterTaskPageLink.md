# XWUnregisterTaskPageLink

- ea: `0x18000bac0`
- end: `0x18000bbba`
- name: `XWUnregisterTaskPageLink`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000bac0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bb19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bb19`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000bad6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000bad6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bb78`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bb78`

## pseudocode

```c
__int64 __fastcall XWUnregisterTaskPageLink(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  HRESULT v5; // ebx
  HRESULT v6; // edi
  LPVOID ppv; // [rsp+70h] [rbp+18h] BYREF

  v4 = CoInitializeEx(0, 6u);
  v5 = 0;
  v6 = v4;
  if ( v4 != -2147417850 )
    v5 = v4;
  if ( v5 >= 0 )
  {
    ppv = 0;
    v5 = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, &ppv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 216LL))(ppv, 1);
      if ( v5 >= 0 )
        v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 88LL))(ppv, a1, a2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v6 != -2147417850 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000bac0  push    rbx
0x18000bac2  push    rbp
0x18000bac3  push    rsi
0x18000bac4  push    rdi
0x18000bac5  sub     rsp, 38h
0x18000bac9  mov     rsi, rdx
0x18000bacc  mov     rbp, rcx
0x18000bacf  mov     edx, 6; dwCoInit
0x18000bad4  xor     ecx, ecx; pvReserved
0x18000bad6  call    cs:__imp_CoInitializeEx
0x18000badc  xor     ebx, ebx
0x18000bade  mov     edi, eax
0x18000bae0  cmp     eax, 80010106h
0x18000bae5  cmovnz  ebx, eax
0x18000bae8  test    ebx, ebx
0x18000baea  js      loc_18000BB7E
0x18000baf0  lea     rax, [rsp+58h+arg_10]
0x18000baf5  mov     [rsp+58h+arg_10], 0
0x18000bafe  lea     r9, IID_IXWizard; riid
0x18000bb05  mov     [rsp+58h+ppv], rax; ppv
0x18000bb0a  xor     edx, edx; pUnkOuter
0x18000bb0c  lea     rcx, CLSID_CXWizard; rclsid
0x18000bb13  mov     r8d, 401h; dwClsContext
0x18000bb19  call    cs:__imp_CoCreateInstance
0x18000bb1f  mov     ebx, eax
0x18000bb21  test    eax, eax
0x18000bb23  js      short loc_18000BB70
0x18000bb25  mov     rcx, [rsp+58h+arg_10]
0x18000bb2a  xor     r8d, r8d
0x18000bb2d  mov     rax, [rcx]
0x18000bb30  lea     edx, [r8+1]
0x18000bb34  mov     rax, [rax+0D8h]
0x18000bb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb40  mov     ebx, eax
0x18000bb42  test    eax, eax
0x18000bb44  js      short loc_18000BB5F
0x18000bb46  mov     rcx, [rsp+58h+arg_10]
0x18000bb4b  mov     r8, rsi
0x18000bb4e  mov     rdx, rbp
0x18000bb51  mov     rax, [rcx]
0x18000bb54  mov     rax, [rax+58h]
0x18000bb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb5d  mov     ebx, eax
0x18000bb5f  mov     rcx, [rsp+58h+arg_10]
0x18000bb64  mov     rax, [rcx]
0x18000bb67  mov     rax, [rax+10h]
0x18000bb6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb70  cmp     edi, 80010106h
0x18000bb76  jz      short loc_18000BB7E
0x18000bb78  call    cs:__imp_CoUninitialize
0x18000bb7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb85  lea     rax, WPP_GLOBAL_Control
0x18000bb8c  cmp     rcx, rax
0x18000bb8f  jz      short loc_18000BBAF
0x18000bb91  test    byte ptr [rcx+1Ch], 10h
0x18000bb95  jz      short loc_18000BBAF
0x18000bb97  mov     rcx, [rcx+10h]
0x18000bb9b  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000bba2  mov     edx, 1Ah
0x18000bba7  mov     r9d, ebx
0x18000bbaa  call    WPP_SF_d
0x18000bbaf  mov     eax, ebx
0x18000bbb1  add     rsp, 38h
0x18000bbb5  pop     rdi
0x18000bbb6  pop     rsi
0x18000bbb7  pop     rbp
0x18000bbb8  pop     rbx
0x18000bbb9  retn
```
