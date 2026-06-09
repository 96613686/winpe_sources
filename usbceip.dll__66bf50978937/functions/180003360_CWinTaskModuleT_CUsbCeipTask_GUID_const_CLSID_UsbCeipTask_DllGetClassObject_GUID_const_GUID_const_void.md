# CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180003360`
- end: `0x18000340c`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VCUsbCeipTask@@$1?CLSID_UsbCeipTask@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003c10`

## callees

- `0x18000246c`
- `0x180003360`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllGetClassObject(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v7; // rax
  unsigned int v8; // edi
  _DWORD *v9; // [rsp+30h] [rbp+8h]

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v7 = *(_QWORD *)&CLSID_UsbCeipTask.Data1 - *a2;
  if ( *(_QWORD *)&CLSID_UsbCeipTask.Data1 == *a2 )
    v7 = *(_QWORD *)CLSID_UsbCeipTask.Data4 - a2[1];
  if ( v7 )
  {
    return (unsigned int)-2147221231;
  }
  else
  {
    v9 = operator new(0x10u);
    *(_QWORD *)v9 = &CWinTaskClassFactoryT<CUsbCeipTask,1>::`vftable';
    v9[2] = 1;
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
    v8 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, a3, a4);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x180003360  mov     [rsp+arg_8], rbx
0x180003365  mov     [rsp+arg_10], rsi
0x18000336a  push    rdi
0x18000336b  sub     rsp, 20h
0x18000336f  mov     rdi, r9
0x180003372  mov     rsi, r8
0x180003375  test    r9, r9
0x180003378  jnz     short loc_180003381
0x18000337a  mov     eax, 80070057h
0x18000337f  jmp     short loc_1800033FC
0x180003381  mov     qword ptr [r9], 0
0x180003388  mov     rax, qword ptr cs:CLSID_UsbCeipTask.Data1
0x18000338f  sub     rax, [rdx]
0x180003392  jnz     short loc_18000339F
0x180003394  mov     rax, qword ptr cs:CLSID_UsbCeipTask.Data4
0x18000339b  sub     rax, [rdx+8]
0x18000339f  test    rax, rax
0x1800033a2  jz      short loc_1800033AB
0x1800033a4  mov     edi, 80040111h
0x1800033a9  jmp     short loc_1800033FA
0x1800033ab  mov     ecx, 10h; Size
0x1800033b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800033b5  mov     rbx, rax
0x1800033b8  mov     [rsp+28h+arg_0], rax
0x1800033bd  lea     rax, ??_7?$CWinTaskClassFactoryT@VCUsbCeipTask@@$00@@6B@; const CWinTaskClassFactoryT<CUsbCeipTask,1>::`vftable'
0x1800033c4  mov     [rbx], rax
0x1800033c7  mov     dword ptr [rbx+8], 1
0x1800033ce  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800033d5  mov     rax, [rbx]
0x1800033d8  mov     r8, rdi
0x1800033db  mov     rdx, rsi
0x1800033de  mov     rcx, rbx
0x1800033e1  mov     rax, [rax]
0x1800033e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e9  mov     edi, eax
0x1800033eb  mov     rcx, [rbx]
0x1800033ee  mov     rax, [rcx+10h]
0x1800033f2  mov     rcx, rbx
0x1800033f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033fa  mov     eax, edi
0x1800033fc  mov     rbx, [rsp+28h+arg_8]
0x180003401  mov     rsi, [rsp+28h+arg_10]
0x180003406  add     rsp, 20h
0x18000340a  pop     rdi
0x18000340b  retn
```
