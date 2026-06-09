# XWUnregisterTask

- ea: `0x18000b9c0`
- end: `0x18000bab9`
- name: `XWUnregisterTask`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000b9c0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ba18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ba18`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b9d5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b9d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba77`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba77`

## pseudocode

```c
__int64 __fastcall XWUnregisterTask(__int64 a1, unsigned int a2)
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
        v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, a1, a2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v6 != -2147417850 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b9c0  push    rbx
0x18000b9c2  push    rbp
0x18000b9c3  push    rsi
0x18000b9c4  push    rdi
0x18000b9c5  sub     rsp, 38h
0x18000b9c9  mov     esi, edx
0x18000b9cb  mov     rbp, rcx
0x18000b9ce  mov     edx, 6; dwCoInit
0x18000b9d3  xor     ecx, ecx; pvReserved
0x18000b9d5  call    cs:__imp_CoInitializeEx
0x18000b9db  xor     ebx, ebx
0x18000b9dd  mov     edi, eax
0x18000b9df  cmp     eax, 80010106h
0x18000b9e4  cmovnz  ebx, eax
0x18000b9e7  test    ebx, ebx
0x18000b9e9  js      loc_18000BA7D
0x18000b9ef  lea     rax, [rsp+58h+arg_10]
0x18000b9f4  mov     [rsp+58h+arg_10], 0
0x18000b9fd  lea     r9, IID_IXWizard; riid
0x18000ba04  mov     [rsp+58h+ppv], rax; ppv
0x18000ba09  xor     edx, edx; pUnkOuter
0x18000ba0b  lea     rcx, CLSID_CXWizard; rclsid
0x18000ba12  mov     r8d, 401h; dwClsContext
0x18000ba18  call    cs:__imp_CoCreateInstance
0x18000ba1e  mov     ebx, eax
0x18000ba20  test    eax, eax
0x18000ba22  js      short loc_18000BA6F
0x18000ba24  mov     rcx, [rsp+58h+arg_10]
0x18000ba29  xor     r8d, r8d
0x18000ba2c  mov     rax, [rcx]
0x18000ba2f  lea     edx, [r8+1]
0x18000ba33  mov     rax, [rax+0D8h]
0x18000ba3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba3f  mov     ebx, eax
0x18000ba41  test    eax, eax
0x18000ba43  js      short loc_18000BA5E
0x18000ba45  mov     rcx, [rsp+58h+arg_10]
0x18000ba4a  mov     r8d, esi
0x18000ba4d  mov     rdx, rbp
0x18000ba50  mov     rax, [rcx]
0x18000ba53  mov     rax, [rax+40h]
0x18000ba57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba5c  mov     ebx, eax
0x18000ba5e  mov     rcx, [rsp+58h+arg_10]
0x18000ba63  mov     rax, [rcx]
0x18000ba66  mov     rax, [rax+10h]
0x18000ba6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba6f  cmp     edi, 80010106h
0x18000ba75  jz      short loc_18000BA7D
0x18000ba77  call    cs:__imp_CoUninitialize
0x18000ba7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba84  lea     rax, WPP_GLOBAL_Control
0x18000ba8b  cmp     rcx, rax
0x18000ba8e  jz      short loc_18000BAAE
0x18000ba90  test    byte ptr [rcx+1Ch], 10h
0x18000ba94  jz      short loc_18000BAAE
0x18000ba96  mov     rcx, [rcx+10h]
0x18000ba9a  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000baa1  mov     edx, 17h
0x18000baa6  mov     r9d, ebx
0x18000baa9  call    WPP_SF_d
0x18000baae  mov     eax, ebx
0x18000bab0  add     rsp, 38h
0x18000bab4  pop     rdi
0x18000bab5  pop     rsi
0x18000bab6  pop     rbp
0x18000bab7  pop     rbx
0x18000bab8  retn
```
