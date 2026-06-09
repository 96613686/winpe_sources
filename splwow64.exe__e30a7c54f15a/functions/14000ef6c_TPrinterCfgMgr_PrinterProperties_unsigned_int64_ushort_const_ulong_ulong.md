# TPrinterCfgMgr::PrinterProperties(unsigned __int64,ushort const *,ulong,ulong *)

- ea: `0x14000ef6c`
- end: `0x14000f107`
- name: `?PrinterProperties@TPrinterCfgMgr@@QEAAH_KPEBGKPEAK@Z`
- size: `411`
- prototype: `int(TPrinterCfgMgr *__hidden this, unsigned __int64, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000e530`

## callees

- `0x140006894`
- `0x140007298`
- `0x1400085d8`
- `0x14000ef6c`
- `0x140012f28`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000f085`
- `KERNEL32!GetLastError` at `0x14000f0a5`
- `KERNEL32!GetLastError` at `0x14000f0bf`
- `KERNEL32!GetLastError` at `0x14000f0d8`
- `KERNEL32!GetLastError` at `0x14000f085`
- `KERNEL32!GetLastError` at `0x14000f0a5`
- `KERNEL32!GetLastError` at `0x14000f0bf`
- `KERNEL32!GetLastError` at `0x14000f0d8`
- `KERNEL32!GetProcAddress` at `0x14000f008`
- `KERNEL32!GetProcAddress` at `0x14000f054`
- `KERNEL32!GetProcAddress` at `0x14000f008`
- `KERNEL32!GetProcAddress` at `0x14000f054`
- `KERNEL32!FreeLibrary` at `0x14000f0d0`
- `KERNEL32!FreeLibrary` at `0x14000f0d0`
- `KERNEL32!LoadLibraryExW` at `0x14000efec`
- `KERNEL32!LoadLibraryExW` at `0x14000efec`
- `WINSPOOL!OpenPrinterW` at `0x14000f024`
- `WINSPOOL!OpenPrinterW` at `0x14000f024`
- `WINSPOOL!ClosePrinter` at `0x14000f0b7`
- `WINSPOOL!ClosePrinter` at `0x14000f0b7`
- `RPCRT4!RpcRevertToSelf` at `0x14000f0e6`
- `RPCRT4!RpcRevertToSelf` at `0x14000f0e6`
- `RPCRT4!RpcImpersonateClient` at `0x14000efa4`
- `RPCRT4!RpcImpersonateClient` at `0x14000efa4`

## pseudocode

```c
__int64 __fastcall TPrinterCfgMgr::PrinterProperties(
        TLoad64BitDllsMgr **this,
        __int64 a2,
        WCHAR *a3,
        __int16 a4,
        unsigned int *a5)
{
  unsigned int v9; // edi
  RPC_STATUS v10; // eax
  NSecurityLibrary *v11; // rcx
  HMODULE Library; // rax
  HMODULE v13; // rbx
  FARPROC ProcAddress; // rsi
  FARPROC v15; // r15
  int v17; // [rsp+30h] [rbp-38h] BYREF
  HANDLE phPrinter; // [rsp+38h] [rbp-30h] BYREF
  __int128 v19; // [rsp+40h] [rbp-28h] BYREF
  WCHAR *v20; // [rsp+50h] [rbp-18h]

  v20 = 0;
  v17 = 0;
  v19 = 0;
  phPrinter = 0;
  v9 = 0;
  v10 = RpcImpersonateClient(0);
  if ( v10 )
  {
    *a5 = v10;
  }
  else
  {
    if ( NSecurityLibrary::IsClientAppContainer(v11) )
    {
      SplWow64Telemetry::WriteDbgTraceError("TPrinterCfgMgr::PrinterProperties", L"called from AppContainer");
      *a5 = 5;
    }
    else
    {
      Library = LoadLibraryExW(L"winspool.drv", 0, 0x800u);
      v13 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "DevicePropertySheets");
        if ( ProcAddress && OpenPrinterW(a3, &phPrinter, 0) )
        {
          WORD1(v19) = a4;
          LOWORD(v19) = 24;
          *((_QWORD *)&v19 + 1) = phPrinter;
          v20 = a3;
          v15 = GetProcAddress(v13, (LPCSTR)0xDA);
          if ( v15 )
          {
            TLoad64BitDllsMgr::IncUIRefCnt(this[6]);
            if ( ((int (__fastcall *)(__int64, FARPROC, __int128 *, int *))v15)(a2, ProcAddress, &v19, &v17) >= 0 )
              v9 = 1;
            else
              *a5 = GetLastError();
            TLoad64BitDllsMgr::DecUIRefCnt(this[6]);
          }
          else
          {
            *a5 = GetLastError();
          }
          ClosePrinter(phPrinter);
        }
        else
        {
          *a5 = GetLastError();
        }
        FreeLibrary(v13);
      }
      else
      {
        *a5 = GetLastError();
      }
    }
    RpcRevertToSelf();
  }
  return v9;
}

```

## disassembly

```asm
0x14000ef6c  push    rbp
0x14000ef6e  push    rbx
0x14000ef6f  push    rsi
0x14000ef70  push    rdi
0x14000ef71  push    r12
0x14000ef73  push    r13
0x14000ef75  push    r14
0x14000ef77  push    r15
0x14000ef79  mov     rbp, rsp
0x14000ef7c  sub     rsp, 68h
0x14000ef80  xor     eax, eax
0x14000ef82  mov     r14, rcx
0x14000ef85  xorps   xmm0, xmm0
0x14000ef88  mov     [rbp+var_18], rax
0x14000ef8c  xor     ecx, ecx; BindingHandle
0x14000ef8e  mov     [rbp+var_38], eax
0x14000ef91  movups  [rbp+var_28], xmm0
0x14000ef95  mov     [rbp+phPrinter], rax
0x14000ef99  mov     r12d, r9d
0x14000ef9c  mov     r15, r8
0x14000ef9f  mov     r13, rdx
0x14000efa2  xor     edi, edi
0x14000efa4  call    cs:__imp_RpcImpersonateClient
0x14000efaa  test    eax, eax
0x14000efac  jnz     loc_14000F0EE
0x14000efb2  call    ?IsClientAppContainer@NSecurityLibrary@@YA_NXZ; NSecurityLibrary::IsClientAppContainer(void)
0x14000efb7  test    al, al
0x14000efb9  jz      short loc_14000EFDD
0x14000efbb  lea     rdx, aCalledFromAppc; "called from AppContainer"
0x14000efc2  lea     rcx, aTprintercfgmgr; "TPrinterCfgMgr::PrinterProperties"
0x14000efc9  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000efce  mov     rax, [rbp+arg_20]
0x14000efd2  mov     dword ptr [rax], 5
0x14000efd8  jmp     loc_14000F0E6
0x14000efdd  xor     edx, edx; hFile
0x14000efdf  lea     rcx, LibFileName; "winspool.drv"
0x14000efe6  mov     r8d, 800h; dwFlags
0x14000efec  call    cs:__imp_LoadLibraryExW
0x14000eff2  mov     rbx, rax
0x14000eff5  test    rax, rax
0x14000eff8  jz      loc_14000F0D8
0x14000effe  lea     rdx, aDeviceproperty; "DevicePropertySheets"
0x14000f005  mov     rcx, rax; hModule
0x14000f008  call    cs:__imp_GetProcAddress
0x14000f00e  mov     rsi, rax
0x14000f011  test    rax, rax
0x14000f014  jz      loc_14000F0BF
0x14000f01a  xor     r8d, r8d; pDefault
0x14000f01d  lea     rdx, [rbp+phPrinter]; phPrinter
0x14000f021  mov     rcx, r15; pPrinterName
0x14000f024  call    cs:__imp_OpenPrinterW
0x14000f02a  test    eax, eax
0x14000f02c  jz      loc_14000F0BF
0x14000f032  mov     eax, 18h
0x14000f037  mov     word ptr [rbp+var_28+2], r12w
0x14000f03c  mov     word ptr [rbp+var_28], ax
0x14000f040  mov     edx, 0DAh; lpProcName
0x14000f045  mov     rax, [rbp+phPrinter]
0x14000f049  mov     rcx, rbx; hModule
0x14000f04c  mov     qword ptr [rbp+var_28+8], rax
0x14000f050  mov     [rbp+var_18], r15
0x14000f054  call    cs:__imp_GetProcAddress
0x14000f05a  mov     r15, rax
0x14000f05d  test    rax, rax
0x14000f060  jz      short loc_14000F0A5
0x14000f062  mov     rcx, [r14+30h]; this
0x14000f066  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x14000f06b  lea     r9, [rbp+var_38]
0x14000f06f  mov     rdx, rsi
0x14000f072  lea     r8, [rbp+var_28]
0x14000f076  mov     rcx, r13
0x14000f079  mov     rax, r15
0x14000f07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f081  test    eax, eax
0x14000f083  jns     short loc_14000F095
0x14000f085  call    cs:__imp_GetLastError
0x14000f08b  mov     ecx, eax
0x14000f08d  mov     rax, [rbp+arg_20]
0x14000f091  mov     [rax], ecx
0x14000f093  jmp     short loc_14000F09A
0x14000f095  mov     edi, 1
0x14000f09a  mov     rcx, [r14+30h]; this
0x14000f09e  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x14000f0a3  jmp     short loc_14000F0B3
0x14000f0a5  call    cs:__imp_GetLastError
0x14000f0ab  mov     ecx, eax
0x14000f0ad  mov     rax, [rbp+arg_20]
0x14000f0b1  mov     [rax], ecx
0x14000f0b3  mov     rcx, [rbp+phPrinter]; hPrinter
0x14000f0b7  call    cs:__imp_ClosePrinter
0x14000f0bd  jmp     short loc_14000F0CD
0x14000f0bf  call    cs:__imp_GetLastError
0x14000f0c5  mov     ecx, eax
0x14000f0c7  mov     rax, [rbp+arg_20]
0x14000f0cb  mov     [rax], ecx
0x14000f0cd  mov     rcx, rbx; hLibModule
0x14000f0d0  call    cs:__imp_FreeLibrary
0x14000f0d6  jmp     short loc_14000F0E6
0x14000f0d8  call    cs:__imp_GetLastError
0x14000f0de  mov     ecx, eax
0x14000f0e0  mov     rax, [rbp+arg_20]
0x14000f0e4  mov     [rax], ecx
0x14000f0e6  call    cs:__imp_RpcRevertToSelf
0x14000f0ec  jmp     short loc_14000F0F4
0x14000f0ee  mov     rcx, [rbp+arg_20]
0x14000f0f2  mov     [rcx], eax
0x14000f0f4  mov     eax, edi
0x14000f0f6  add     rsp, 68h
0x14000f0fa  pop     r15
0x14000f0fc  pop     r14
0x14000f0fe  pop     r13
0x14000f100  pop     r12
0x14000f102  pop     rdi
0x14000f103  pop     rsi
0x14000f104  pop     rbx
0x14000f105  pop     rbp
0x14000f106  retn
```
