# TLoad64BitDllsMgr::DeviceCapabilitiesW(ushort *,ushort *,ushort,ulong,uchar *,int,ulong *,uchar * *,ulong *)

- ea: `0x1400069b8`
- end: `0x140006c0a`
- name: `?DeviceCapabilitiesW@TLoad64BitDllsMgr@@QEAAHPEAG0GKPEAEHPEAKPEAPEAE2@Z`
- size: `594`
- prototype: `int(TLoad64BitDllsMgr *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16, unsigned int, unsigned __int8 *, int, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000d920`

## callees

- `0x140001b9c`
- `0x1400028b8`
- `0x140006894`
- `0x1400069b8`
- `0x140007298`
- `0x1400073ac`
- `0x14000f1e4`
- `0x140016010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140006b83`
- `KERNEL32!SetLastError` at `0x140006b83`
- `KERNEL32!GetLastError` at `0x140006b34`
- `KERNEL32!GetLastError` at `0x140006b5f`
- `KERNEL32!GetLastError` at `0x140006ba0`
- `KERNEL32!GetLastError` at `0x140006bc0`
- `KERNEL32!GetLastError` at `0x140006b34`
- `KERNEL32!GetLastError` at `0x140006b5f`
- `KERNEL32!GetLastError` at `0x140006ba0`
- `KERNEL32!GetLastError` at `0x140006bc0`
- `KERNEL32!GetProcAddress` at `0x140006a4b`
- `KERNEL32!GetProcAddress` at `0x140006a4b`
- `KERNEL32!FreeLibrary` at `0x140006b98`
- `KERNEL32!FreeLibrary` at `0x140006b98`
- `WINSPOOL!OpenPrinterW` at `0x140006a15`
- `WINSPOOL!OpenPrinterW` at `0x140006a15`
- `WINSPOOL!ClosePrinter` at `0x140006bb8`
- `WINSPOOL!ClosePrinter` at `0x140006bb8`
- `RPCRT4!RpcRevertToSelf` at `0x140006bd0`
- `RPCRT4!RpcRevertToSelf` at `0x140006bd0`
- `RPCRT4!RpcImpersonateClient` at `0x1400069f7`
- `RPCRT4!RpcImpersonateClient` at `0x1400069f7`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::DeviceCapabilitiesW(
        TLoad64BitDllsMgr *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 a4,
        unsigned int a5,
        unsigned __int8 *a6,
        int a7,
        unsigned int *a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  unsigned int v12; // ebx
  RPC_STATUS v13; // ecx
  TPrinterDriver *v14; // rcx
  HMODULE PrinterDriver; // rax
  HMODULE v16; // rdi
  TLoad64BitDllsMgr *v17; // rcx
  FARPROC ProcAddress; // r14
  unsigned __int8 **v19; // rsi
  unsigned __int8 *v20; // r13
  unsigned __int64 v21; // rcx
  unsigned int *v22; // rbx
  unsigned __int8 *v23; // rax
  HANDLE phPrinter; // [rsp+80h] [rbp+18h] BYREF

  phPrinter = 0;
  v12 = -1;
  TLoad64BitDllsMgr::IncUIRefCnt(pGLdrObj);
  v13 = RpcImpersonateClient(0);
  if ( v13 )
  {
    *a10 = v13;
  }
  else
  {
    if ( OpenPrinterW(a2, &phPrinter, 0) )
    {
      PrinterDriver = (HMODULE)TPrinterDriver::LoadPrinterDriver(v14, phPrinter);
      v16 = PrinterDriver;
      if ( PrinterDriver )
      {
        ProcAddress = GetProcAddress(PrinterDriver, "DrvDeviceCapabilities");
        if ( ProcAddress )
        {
          a5 = 0;
          v19 = a9;
          *a9 = 0;
          if ( TLoad64BitDllsMgr::IsValidCapability(v17, phPrinter, a4, &a5) )
          {
            v20 = a6;
            v12 = ((__int64 (__fastcall *)(HANDLE, unsigned __int16 *, _QWORD, unsigned __int8 *, unsigned __int8 *))ProcAddress)(
                    phPrinter,
                    a2,
                    a4,
                    *v19,
                    a6);
            if ( v12 + 1 > 1 && a7 && a5 )
            {
              v21 = v12 * a5;
              v22 = a8;
              *a8 = v21;
              v23 = (unsigned __int8 *)operator new[](v21);
              *v19 = v23;
              if ( v23 )
              {
                memset_0(v23, 0, *v22);
                v12 = ((__int64 (__fastcall *)(HANDLE, unsigned __int16 *, _QWORD, unsigned __int8 *, unsigned __int8 *))ProcAddress)(
                        phPrinter,
                        a2,
                        a4,
                        *v19,
                        v20);
                if ( v12 == -1 )
                  *a10 = GetLastError();
              }
              else
              {
                v12 = -1;
                *a10 = 14;
              }
            }
            if ( !v12 )
              *a10 = GetLastError();
          }
          else
          {
            *a10 = 87;
          }
        }
        FreeLibrary(v16);
      }
      else
      {
        *a10 = GetLastError();
      }
      ClosePrinter(phPrinter);
    }
    else
    {
      *a10 = GetLastError();
    }
    RpcRevertToSelf();
  }
  TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
  return v12;
}

```

## disassembly

```asm
0x1400069b8  mov     rax, rsp
0x1400069bb  mov     [rax+10h], rbx
0x1400069bf  mov     [rax+20h], rsi
0x1400069c3  mov     [rax+18h], r8
0x1400069c7  mov     [rax+8], rcx
0x1400069cb  push    rdi
0x1400069cc  push    r12
0x1400069ce  push    r13
0x1400069d0  push    r14
0x1400069d2  push    r15
0x1400069d4  sub     rsp, 40h
0x1400069d8  movzx   r12d, r9w
0x1400069dc  mov     r15, rdx
0x1400069df  xor     r13d, r13d
0x1400069e2  mov     [rax+18h], r13
0x1400069e6  or      ebx, 0FFFFFFFFh
0x1400069e9  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x1400069f0  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x1400069f5  xor     ecx, ecx; BindingHandle
0x1400069f7  call    cs:__imp_RpcImpersonateClient
0x1400069fd  mov     ecx, eax
0x1400069ff  test    eax, eax
0x140006a01  jnz     loc_140006BD8
0x140006a07  xor     r8d, r8d; pDefault
0x140006a0a  lea     rdx, [rsp+68h+phPrinter]; phPrinter
0x140006a12  mov     rcx, r15; pPrinterName
0x140006a15  call    cs:__imp_OpenPrinterW
0x140006a1b  test    eax, eax
0x140006a1d  jz      loc_140006BC0
0x140006a23  mov     rdx, [rsp+68h+phPrinter]; void *
0x140006a2b  call    ?LoadPrinterDriver@TPrinterDriver@@IEAAPEAXPEAX@Z; TPrinterDriver::LoadPrinterDriver(void *)
0x140006a30  mov     rdi, rax
0x140006a33  mov     [rsp+68h+arg_0], rax
0x140006a38  test    rax, rax
0x140006a3b  jz      loc_140006BA0
0x140006a41  lea     rdx, aDrvdevicecapab; "DrvDeviceCapabilities"
0x140006a48  mov     rcx, rax; hModule
0x140006a4b  call    cs:__imp_GetProcAddress
0x140006a51  mov     r14, rax
0x140006a54  test    rax, rax
0x140006a57  jz      loc_140006B95
0x140006a5d  mov     [rsp+68h+arg_20], r13d
0x140006a65  mov     rsi, [rsp+68h+arg_40]
0x140006a6d  mov     [rsi], r13
0x140006a70  lea     r9, [rsp+68h+arg_20]; unsigned int *
0x140006a78  movzx   r8d, r12w; unsigned __int16
0x140006a7c  mov     rdx, [rsp+68h+phPrinter]; void *
0x140006a84  call    ?IsValidCapability@TLoad64BitDllsMgr@@IEBAHPEAXGPEAK@Z; TLoad64BitDllsMgr::IsValidCapability(void *,ushort,ulong *)
0x140006a89  test    eax, eax
0x140006a8b  jz      loc_140006B71
0x140006a91  mov     r13, [rsp+68h+arg_28]
0x140006a99  mov     [rsp+68h+var_48], r13
0x140006a9e  mov     r9, [rsi]
0x140006aa1  movzx   r8d, r12w
0x140006aa5  mov     rdx, r15
0x140006aa8  mov     rcx, [rsp+68h+phPrinter]
0x140006ab0  mov     rax, r14
0x140006ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ab8  mov     ebx, eax
0x140006aba  mov     [rsp+68h+var_38], eax
0x140006abe  lea     ecx, [rax+1]
0x140006ac1  cmp     ecx, 1
0x140006ac4  jbe     loc_140006B5B
0x140006aca  cmp     [rsp+68h+arg_30], 0
0x140006ad2  jz      loc_140006B5B
0x140006ad8  mov     ecx, [rsp+68h+arg_20]
0x140006adf  test    ecx, ecx
0x140006ae1  jz      short loc_140006B5B
0x140006ae3  imul    ecx, ebx; unsigned __int64
0x140006ae6  mov     rbx, [rsp+68h+arg_38]
0x140006aee  mov     [rbx], ecx
0x140006af0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140006af5  mov     [rsi], rax
0x140006af8  test    rax, rax
0x140006afb  jz      short loc_140006B46
0x140006afd  mov     r8d, [rbx]; Size
0x140006b00  xor     edx, edx; Val
0x140006b02  mov     rcx, rax; void *
0x140006b05  call    memset_0
0x140006b0a  mov     [rsp+68h+var_48], r13
0x140006b0f  mov     r9, [rsi]
0x140006b12  movzx   r8d, r12w
0x140006b16  mov     rdx, r15
0x140006b19  mov     rcx, [rsp+68h+phPrinter]
0x140006b21  mov     rax, r14
0x140006b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b29  mov     ebx, eax
0x140006b2b  mov     [rsp+68h+var_38], eax
0x140006b2f  cmp     eax, 0FFFFFFFFh
0x140006b32  jnz     short loc_140006B5B
0x140006b34  call    cs:__imp_GetLastError
0x140006b3a  mov     rcx, [rsp+68h+arg_48]
0x140006b42  mov     [rcx], eax
0x140006b44  jmp     short loc_140006B5B
0x140006b46  or      ebx, 0FFFFFFFFh
0x140006b49  mov     [rsp+68h+var_38], ebx
0x140006b4d  mov     rax, [rsp+68h+arg_48]
0x140006b55  mov     dword ptr [rax], 0Eh
0x140006b5b  test    ebx, ebx
0x140006b5d  jnz     short loc_140006B7F
0x140006b5f  call    cs:__imp_GetLastError
0x140006b65  mov     rcx, [rsp+68h+arg_48]
0x140006b6d  mov     [rcx], eax
0x140006b6f  jmp     short loc_140006B7F
0x140006b71  mov     rax, [rsp+68h+arg_48]
0x140006b79  mov     dword ptr [rax], 57h ; 'W'
0x140006b7f  jmp     short loc_140006B95
0x140006b81  mov     ecx, eax; dwErrCode
0x140006b83  call    cs:__imp_SetLastError
0x140006b89  or      ebx, 0FFFFFFFFh
0x140006b8c  mov     [rsp+68h+var_38], ebx
0x140006b90  mov     rdi, [rsp+68h+arg_0]
0x140006b95  mov     rcx, rdi; hLibModule
0x140006b98  call    cs:__imp_FreeLibrary
0x140006b9e  jmp     short loc_140006BB0
0x140006ba0  call    cs:__imp_GetLastError
0x140006ba6  mov     rcx, [rsp+68h+arg_48]
0x140006bae  mov     [rcx], eax
0x140006bb0  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x140006bb8  call    cs:__imp_ClosePrinter
0x140006bbe  jmp     short loc_140006BD0
0x140006bc0  call    cs:__imp_GetLastError
0x140006bc6  mov     rcx, [rsp+68h+arg_48]
0x140006bce  mov     [rcx], eax
0x140006bd0  call    cs:__imp_RpcRevertToSelf
0x140006bd6  jmp     short loc_140006BE2
0x140006bd8  mov     rax, [rsp+68h+arg_48]
0x140006be0  mov     [rax], ecx
0x140006be2  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140006be9  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x140006bee  mov     eax, ebx
0x140006bf0  lea     r11, [rsp+68h+var_28]
0x140006bf5  mov     rbx, [r11+38h]
0x140006bf9  mov     rsi, [r11+48h]
0x140006bfd  mov     rsp, r11
0x140006c00  pop     r15
0x140006c02  pop     r14
0x140006c04  pop     r13
0x140006c06  pop     r12
0x140006c08  pop     rdi
0x140006c09  retn
```
