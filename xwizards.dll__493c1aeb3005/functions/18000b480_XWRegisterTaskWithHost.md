# XWRegisterTaskWithHost

- ea: `0x18000b480`
- end: `0x18000b5b3`
- name: `XWRegisterTaskWithHost`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000b480`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b4e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b4e3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b4a0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b4a0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b56d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b56d`

## pseudocode

```c
__int64 __fastcall XWRegisterTaskWithHost(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, __int64 a7)
{
  HRESULT v11; // eax
  HRESULT v12; // ebx
  HRESULT v13; // edi
  LPVOID ppv; // [rsp+50h] [rbp-48h] BYREF

  v11 = CoInitializeEx(0, 6u);
  v12 = 0;
  v13 = v11;
  if ( v11 != -2147417850 )
    v12 = v11;
  if ( v12 >= 0 )
  {
    ppv = 0;
    v12 = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, &ppv);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 216LL))(ppv, 1);
      if ( v12 >= 0 )
        v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64, __int64, int, int, __int64))(*(_QWORD *)ppv + 32LL))(
                ppv,
                a1,
                a2,
                a3,
                a4,
                a5,
                a6,
                a7);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v13 != -2147417850 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
      (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b480  push    rbx
0x18000b482  push    rbp
0x18000b483  push    rsi
0x18000b484  push    rdi
0x18000b485  push    r14
0x18000b487  push    r15
0x18000b489  sub     rsp, 68h
0x18000b48d  mov     r14, rdx
0x18000b490  mov     r15, rcx
0x18000b493  mov     edx, 6; dwCoInit
0x18000b498  xor     ecx, ecx; pvReserved
0x18000b49a  mov     rsi, r9
0x18000b49d  mov     rbp, r8
0x18000b4a0  call    cs:__imp_CoInitializeEx
0x18000b4a6  xor     ebx, ebx
0x18000b4a8  mov     edi, eax
0x18000b4aa  cmp     eax, 80010106h
0x18000b4af  cmovnz  ebx, eax
0x18000b4b2  test    ebx, ebx
0x18000b4b4  js      loc_18000B573
0x18000b4ba  lea     rax, [rsp+98h+var_48]
0x18000b4bf  mov     [rsp+98h+var_48], 0
0x18000b4c8  lea     r9, IID_IXWizard; riid
0x18000b4cf  mov     [rsp+98h+ppv], rax; ppv
0x18000b4d4  xor     edx, edx; pUnkOuter
0x18000b4d6  lea     rcx, CLSID_CXWizard; rclsid
0x18000b4dd  mov     r8d, 401h; dwClsContext
0x18000b4e3  call    cs:__imp_CoCreateInstance
0x18000b4e9  mov     ebx, eax
0x18000b4eb  test    eax, eax
0x18000b4ed  js      short loc_18000B565
0x18000b4ef  mov     rcx, [rsp+98h+var_48]
0x18000b4f4  xor     r8d, r8d
0x18000b4f7  mov     rax, [rcx]
0x18000b4fa  lea     edx, [r8+1]
0x18000b4fe  mov     rax, [rax+0D8h]
0x18000b505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b50a  mov     ebx, eax
0x18000b50c  test    eax, eax
0x18000b50e  js      short loc_18000B554
0x18000b510  mov     rdx, [rsp+98h+arg_30]
0x18000b518  mov     r9, rbp
0x18000b51b  mov     rcx, [rsp+98h+var_48]
0x18000b520  mov     r8, r14
0x18000b523  mov     [rsp+98h+var_60], rdx
0x18000b528  mov     edx, [rsp+98h+arg_28]
0x18000b52f  mov     [rsp+98h+var_68], edx
0x18000b533  mov     rax, [rcx]
0x18000b536  mov     edx, [rsp+98h+arg_20]
0x18000b53d  mov     [rsp+98h+var_70], edx
0x18000b541  mov     rdx, r15
0x18000b544  mov     [rsp+98h+ppv], rsi
0x18000b549  mov     rax, [rax+20h]
0x18000b54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b552  mov     ebx, eax
0x18000b554  mov     rcx, [rsp+98h+var_48]
0x18000b559  mov     rax, [rcx]
0x18000b55c  mov     rax, [rax+10h]
0x18000b560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b565  cmp     edi, 80010106h
0x18000b56b  jz      short loc_18000B573
0x18000b56d  call    cs:__imp_CoUninitialize
0x18000b573  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b57a  lea     rax, WPP_GLOBAL_Control
0x18000b581  cmp     rcx, rax
0x18000b584  jz      short loc_18000B5A4
0x18000b586  test    byte ptr [rcx+1Ch], 10h
0x18000b58a  jz      short loc_18000B5A4
0x18000b58c  mov     rcx, [rcx+10h]
0x18000b590  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000b597  mov     edx, 13h
0x18000b59c  mov     r9d, ebx
0x18000b59f  call    WPP_SF_d
0x18000b5a4  mov     eax, ebx
0x18000b5a6  add     rsp, 68h
0x18000b5aa  pop     r15
0x18000b5ac  pop     r14
0x18000b5ae  pop     rdi
0x18000b5af  pop     rsi
0x18000b5b0  pop     rbp
0x18000b5b1  pop     rbx
0x18000b5b2  retn
```
