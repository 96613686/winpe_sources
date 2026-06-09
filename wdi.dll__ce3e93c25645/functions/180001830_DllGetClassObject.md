# DllGetClassObject

- ea: `0x180001830`
- end: `0x18000196b`
- name: `DllGetClassObject`
- size: `315`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001830`
- `0x180002ba0`
- `0x180007f50`
- `0x180009284`
- `0x180010010`

## string_xrefs

- `0x180001899`: `DllGetClassObject`
- `0x180001913`: `DllGetClassObject`
- `0x18000194d`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  CClassFactory *v6; // rax
  HRESULT v7; // ebx
  CClassFactory *v8; // rax
  CClassFactory *v9; // rdi
  int Args; // eax

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  v5 = *(_QWORD *)&CLSID_CWdiHandler.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_CWdiHandler.Data1 == *(_QWORD *)&rclsid->Data1 )
    v5 = *(_QWORD *)CLSID_CWdiHandler.Data4 - *(_QWORD *)rclsid->Data4;
  if ( v5 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
      (int)L"DllGetClassObject",
      112,
      (int)L"Error = %d",
      5);
    return -2147467259;
  }
  else
  {
    v6 = (CClassFactory *)operator new(0x10u);
    if ( v6 && (v8 = CClassFactory::CClassFactory(v6), (v9 = v8) != 0) )
    {
      Args = (**(__int64 (__fastcall ***)(CClassFactory *, const IID *const, LPVOID *))v8)(v8, riid, ppv);
      v7 = Args;
      if ( Args < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
          (int)L"DllGetClassObject",
          119,
          (int)L"Error = %d",
          Args);
      (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    else
    {
      v7 = -2147024882;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
        (int)L"DllGetClassObject",
        116,
        (int)L"Error = %d",
        14);
    }
    return v7;
  }
}

```

## disassembly

```asm
0x180001830  mov     [rsp+arg_8], rbx
0x180001835  push    rsi
0x180001836  sub     rsp, 30h
0x18000183a  mov     rbx, r8
0x18000183d  mov     rsi, rdx
0x180001840  test    r8, r8
0x180001843  jz      loc_180001938
0x180001849  mov     qword ptr [r8], 0
0x180001850  mov     rax, qword ptr cs:CLSID_CWdiHandler.Data1
0x180001857  sub     rax, [rcx]
0x18000185a  jnz     short loc_180001867
0x18000185c  mov     rax, qword ptr cs:CLSID_CWdiHandler.Data4
0x180001863  sub     rax, [rcx+8]
0x180001867  test    rax, rax
0x18000186a  jnz     loc_1800018FE
0x180001870  mov     ecx, 10h; Size
0x180001875  mov     [rsp+38h+arg_0], rdi
0x18000187a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000187f  test    rax, rax
0x180001882  jnz     short loc_1800018B3
0x180001884  lea     r9, aErrorD_0; "Error = %d"
0x18000188b  mov     dword ptr [rsp+38h+Args], 0Eh; Args
0x180001893  mov     r8d, 74h ; 't'; int
0x180001899  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x1800018a0  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800018a7  mov     ebx, 8007000Eh
0x1800018ac  call    WdipTraceError
0x1800018b1  jmp     short loc_1800018EC
0x1800018b3  mov     rcx, rax; this
0x1800018b6  call    ??0CClassFactory@@QEAA@XZ; CClassFactory::CClassFactory(void)
0x1800018bb  mov     rdi, rax
0x1800018be  test    rax, rax
0x1800018c1  jz      short loc_180001884
0x1800018c3  mov     rax, [rax]
0x1800018c6  mov     r8, rbx
0x1800018c9  mov     rdx, rsi
0x1800018cc  mov     rcx, rdi
0x1800018cf  mov     rax, [rax]
0x1800018d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018d7  mov     ebx, eax
0x1800018d9  test    eax, eax
0x1800018db  js      short loc_18000193F
0x1800018dd  mov     rax, [rdi]
0x1800018e0  mov     rcx, rdi
0x1800018e3  mov     rax, [rax+10h]
0x1800018e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018ec  mov     rdi, [rsp+38h+arg_0]
0x1800018f1  mov     eax, ebx
0x1800018f3  mov     rbx, [rsp+38h+arg_8]
0x1800018f8  add     rsp, 30h
0x1800018fc  pop     rsi
0x1800018fd  retn
0x1800018fe  lea     r9, aErrorD_0; "Error = %d"
0x180001905  mov     dword ptr [rsp+38h+Args], 4005h; Args
0x18000190d  mov     r8d, 70h ; 'p'; int
0x180001913  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18000191a  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001921  mov     ebx, 80004005h
0x180001926  call    WdipTraceError
0x18000192b  mov     eax, ebx
0x18000192d  mov     rbx, [rsp+38h+arg_8]
0x180001932  add     rsp, 30h
0x180001936  pop     rsi
0x180001937  retn
0x180001938  mov     eax, 80070057h
0x18000193d  jmp     short loc_1800018F3
0x18000193f  movzx   ecx, ax
0x180001942  lea     r9, aErrorD_0; "Error = %d"
0x180001949  mov     dword ptr [rsp+38h+Args], ecx; Args
0x18000194d  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180001954  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000195b  mov     r8d, 77h ; 'w'; int
0x180001961  call    WdipTraceError
0x180001966  jmp     loc_1800018DD
```
