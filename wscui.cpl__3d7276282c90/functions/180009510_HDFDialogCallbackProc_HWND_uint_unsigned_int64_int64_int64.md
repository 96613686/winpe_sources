# HDFDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x180009510`
- end: `0x180009589`
- name: `?HDFDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `121`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009510`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009546`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009546`

## pseudocode

```c
__int64 __fastcall HDFDialogCallbackProc(HWND a1, int a2, int a3)
{
  HRESULT v3; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF

  v3 = 0;
  if ( a2 == 2 && a3 == 10 )
  {
    ppv = 0;
    v3 = CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &ppv);
    if ( v3 >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
        ppv,
        L"Microsoft.ProgramsAndFeatures",
        0,
        0);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009510  push    rbx
0x180009512  sub     rsp, 40h
0x180009516  xor     ebx, ebx
0x180009518  cmp     edx, 2
0x18000951b  jnz     short loc_180009581
0x18000951d  cmp     r8d, 0Ah
0x180009521  jnz     short loc_180009581
0x180009523  lea     rax, [rsp+48h+var_18]
0x180009528  mov     [rsp+48h+var_18], rbx
0x18000952d  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x180009534  mov     [rsp+48h+ppv], rax; ppv
0x180009539  xor     edx, edx; pUnkOuter
0x18000953b  lea     r8d, [rbx+1]; dwClsContext
0x18000953f  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180009546  call    cs:__imp_CoCreateInstance
0x18000954c  mov     ebx, eax
0x18000954e  test    eax, eax
0x180009550  js      short loc_180009581
0x180009552  mov     rcx, [rsp+48h+var_18]
0x180009557  lea     rdx, aMicrosoftProgr; "Microsoft.ProgramsAndFeatures"
0x18000955e  xor     r9d, r9d
0x180009561  xor     r8d, r8d
0x180009564  mov     rax, [rcx]
0x180009567  mov     rax, [rax+18h]
0x18000956b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009570  mov     rcx, [rsp+48h+var_18]
0x180009575  mov     rdx, [rcx]
0x180009578  mov     rax, [rdx+10h]
0x18000957c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009581  mov     eax, ebx
0x180009583  add     rsp, 40h
0x180009587  pop     rbx
0x180009588  retn
```
