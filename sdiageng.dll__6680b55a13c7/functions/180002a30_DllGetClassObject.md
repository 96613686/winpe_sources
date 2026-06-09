# DllGetClassObject

- ea: `0x180002a30`
- end: `0x180002b2b`
- name: `DllGetClassObject`
- size: `251`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001264`
- `0x180002a30`
- `0x180026fa0`
- `0x18002a010`

## string_xrefs

- `0x180002ac5`: `DllGetClassObject`
- `0x180002b08`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v5; // ebx
  unsigned int v6; // r8d
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  int v9; // eax

  if ( !ppv )
  {
    v5 = -2147024809;
    v6 = 144;
LABEL_10:
    SdpDebugTrace(1u, L"DllGetClassObject", v6, v5);
    return v5;
  }
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_CScriptedDiag != *(_OWORD *)rclsid )
  {
    v5 = -2147467259;
    v6 = 153;
    goto LABEL_10;
  }
  v7 = operator new(0x10u);
  v8 = v7;
  if ( !v7 )
  {
    v5 = -2147024882;
    v6 = 157;
    goto LABEL_10;
  }
  v7[2] = 1;
  *(_QWORD *)v7 = &CScriptedDiagFactory::`vftable';
  _InterlockedIncrement(&g_Count);
  v9 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v7)(v7, riid, ppv);
  v5 = v9;
  if ( v9 < 0 )
    SdpDebugTrace(1u, L"DllGetClassObject", 0xA0u, v9);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v5;
}

```

## disassembly

```asm
0x180002a30  mov     [rsp+arg_0], rbx
0x180002a35  mov     [rsp+arg_8], rsi
0x180002a3a  push    rdi
0x180002a3b  sub     rsp, 20h
0x180002a3f  mov     rbx, r8
0x180002a42  mov     rsi, rdx
0x180002a45  test    r8, r8
0x180002a48  jnz     short loc_180002A5A
0x180002a4a  mov     ebx, 80070057h
0x180002a4f  mov     r8d, 90h
0x180002a55  jmp     loc_180002B05
0x180002a5a  mov     qword ptr [r8], 0
0x180002a61  mov     rax, qword ptr cs:CLSID_CScriptedDiag.Data1
0x180002a68  cmp     rax, [rcx]
0x180002a6b  jnz     loc_180002AFA
0x180002a71  mov     rax, qword ptr cs:CLSID_CScriptedDiag.Data4
0x180002a78  cmp     rax, [rcx+8]
0x180002a7c  jnz     short loc_180002AFA
0x180002a7e  mov     ecx, 10h; Size
0x180002a83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002a88  mov     rdi, rax
0x180002a8b  test    rax, rax
0x180002a8e  jz      short loc_180002AED
0x180002a90  lea     rax, ??_7CScriptedDiagFactory@@6B@; const CScriptedDiagFactory::`vftable'
0x180002a97  mov     dword ptr [rdi+8], 1
0x180002a9e  mov     [rdi], rax
0x180002aa1  lock inc cs:?g_Count@@3JA; long g_Count
0x180002aa8  mov     rax, [rdi]
0x180002aab  mov     r8, rbx
0x180002aae  mov     rdx, rsi
0x180002ab1  mov     rcx, rdi
0x180002ab4  mov     rax, [rax]
0x180002ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002abc  mov     ebx, eax
0x180002abe  test    eax, eax
0x180002ac0  jns     short loc_180002ADC
0x180002ac2  mov     r9d, eax; int
0x180002ac5  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180002acc  mov     r8d, 0A0h; int
0x180002ad2  mov     ecx, 1; Level
0x180002ad7  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002adc  mov     rax, [rdi]
0x180002adf  mov     rcx, rdi
0x180002ae2  mov     rax, [rax+10h]
0x180002ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aeb  jmp     short loc_180002B19
0x180002aed  mov     ebx, 8007000Eh
0x180002af2  mov     r8d, 9Dh
0x180002af8  jmp     short loc_180002B05
0x180002afa  mov     ebx, 80004005h
0x180002aff  mov     r8d, 99h; int
0x180002b05  mov     r9d, ebx; int
0x180002b08  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180002b0f  mov     ecx, 1; Level
0x180002b14  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002b19  mov     rsi, [rsp+28h+arg_8]
0x180002b1e  mov     eax, ebx
0x180002b20  mov     rbx, [rsp+28h+arg_0]
0x180002b25  add     rsp, 20h
0x180002b29  pop     rdi
0x180002b2a  retn
```
