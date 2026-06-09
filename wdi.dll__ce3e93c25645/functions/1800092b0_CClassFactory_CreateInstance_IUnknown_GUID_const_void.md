# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800092b0`
- end: `0x1800093a6`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `246`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180002ba0`
- `0x180007f50`
- `0x1800092b0`
- `0x18000d3c8`
- `0x180010010`

## string_xrefs

- `0x18000933d`: `CClassFactory::CreateInstance`
- `0x180009381`: `CClassFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  CWdiHandler *v7; // rax
  CWdiHandler *v8; // rax
  CWdiHandler *v9; // rdi
  int Args; // eax

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = (CWdiHandler *)operator new(0x30u);
      if ( v7 && (v8 = CWdiHandler::CWdiHandler(v7), (v9 = v8) != 0) )
      {
        Args = (**(__int64 (__fastcall ***)(CWdiHandler *, const struct _GUID *, void **))v8)(v8, a3, a4);
        v6 = Args;
        if ( Args < 0 )
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\factory.cpp",
            (int)L"CClassFactory::CreateInstance",
            99,
            (int)L"Error = %d",
            Args);
        (*(void (__fastcall **)(CWdiHandler *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      else
      {
        v6 = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\factory.cpp",
          (int)L"CClassFactory::CreateInstance",
          96,
          (int)L"Error = %d",
          14);
      }
    }
  }
  else
  {
    v6 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\factory.cpp",
      (int)L"CClassFactory::CreateInstance",
      84,
      (int)L"Error = %d",
      87);
  }
  return v6;
}

```

## disassembly

```asm
0x1800092b0  mov     [rsp+arg_0], rbx
0x1800092b5  mov     [rsp+arg_8], rsi
0x1800092ba  push    rdi
0x1800092bb  sub     rsp, 30h
0x1800092bf  mov     rbx, r9
0x1800092c2  mov     rsi, r8
0x1800092c5  test    r9, r9
0x1800092c8  jnz     short loc_1800092E0
0x1800092ca  mov     ebx, 80070057h
0x1800092cf  mov     dword ptr [rsp+38h+Args], 57h ; 'W'
0x1800092d7  lea     r8d, [r9+54h]
0x1800092db  jmp     loc_18000937A
0x1800092e0  mov     qword ptr [r9], 0
0x1800092e7  test    rdx, rdx
0x1800092ea  jz      short loc_1800092F6
0x1800092ec  mov     ebx, 80040110h
0x1800092f1  jmp     loc_180009394
0x1800092f6  mov     ecx, 30h ; '0'; Size
0x1800092fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009300  test    rax, rax
0x180009303  jz      short loc_180009367
0x180009305  mov     rcx, rax; this
0x180009308  call    ??0CWdiHandler@@QEAA@XZ; CWdiHandler::CWdiHandler(void)
0x18000930d  mov     rdi, rax
0x180009310  test    rax, rax
0x180009313  jz      short loc_180009367
0x180009315  mov     rax, [rax]
0x180009318  mov     r8, rbx
0x18000931b  mov     rdx, rsi
0x18000931e  mov     rcx, rdi
0x180009321  mov     rax, [rax]
0x180009324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009329  mov     ebx, eax
0x18000932b  test    eax, eax
0x18000932d  jns     short loc_180009356
0x18000932f  movzx   ecx, ax
0x180009332  lea     r9, aErrorD_0; "Error = %d"
0x180009339  mov     dword ptr [rsp+38h+Args], ecx; Args
0x18000933d  lea     rdx, aCclassfactoryC; "CClassFactory::CreateInstance"
0x180009344  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000934b  mov     r8d, 63h ; 'c'; int
0x180009351  call    WdipTraceError
0x180009356  mov     rax, [rdi]
0x180009359  mov     rcx, rdi
0x18000935c  mov     rax, [rax+10h]
0x180009360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009365  jmp     short loc_180009394
0x180009367  mov     ebx, 8007000Eh
0x18000936c  mov     dword ptr [rsp+38h+Args], 0Eh; Args
0x180009374  mov     r8d, 60h ; '`'; int
0x18000937a  lea     r9, aErrorD_0; "Error = %d"
0x180009381  lea     rdx, aCclassfactoryC; "CClassFactory::CreateInstance"
0x180009388  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000938f  call    WdipTraceError
0x180009394  mov     rsi, [rsp+38h+arg_8]
0x180009399  mov     eax, ebx
0x18000939b  mov     rbx, [rsp+38h+arg_0]
0x1800093a0  add     rsp, 30h
0x1800093a4  pop     rdi
0x1800093a5  retn
```
