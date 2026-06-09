# CWshNetwork::RemovePrinterConnection(ushort *,tagVARIANT *,tagVARIANT *)

- ea: `0x1800087c0`
- end: `0x18000892a`
- name: `?RemovePrinterConnection@CWshNetwork@@UEAAJPEAGPEAUtagVARIANT@@1@Z`
- size: `362`
- prototype: `int(CWshNetwork *__hidden this, unsigned __int16 *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800087c0`
- `0x180010250`
- `0x1800102e0`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008850`
- `KERNEL32!GetLastError` at `0x180008850`
- `KERNEL32!WideCharToMultiByte` at `0x180008843`
- `KERNEL32!WideCharToMultiByte` at `0x1800088b8`
- `KERNEL32!WideCharToMultiByte` at `0x180008843`
- `KERNEL32!WideCharToMultiByte` at `0x1800088b8`
- `WINSPOOL!DeletePrinterConnectionW` at `0x1800087f8`
- `WINSPOOL!DeletePrinterConnectionW` at `0x1800087f8`
- `WINSPOOL!ClosePrinter` at `0x1800088e8`
- `WINSPOOL!ClosePrinter` at `0x1800088f3`
- `WINSPOOL!ClosePrinter` at `0x1800088e8`
- `WINSPOOL!ClosePrinter` at `0x1800088f3`
- `WINSPOOL!DeletePrinter` at `0x1800088da`
- `WINSPOOL!DeletePrinter` at `0x1800088da`
- `WINSPOOL!OpenPrinterA` at `0x1800088cc`
- `WINSPOOL!OpenPrinterA` at `0x1800088cc`

## pseudocode

```c
int __fastcall CWshNetwork::RemovePrinterConnection(
        CWshNetwork *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4)
{
  int result; // eax
  int cbMultiByte; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    if ( DeletePrinterConnectionW(a2) )
      return 0;
    return (*(__int64 (__fastcall **)(CWshNetwork *, unsigned __int16 *, struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)this + 112LL))(
             this,
             a2,
             a3,
             a4);
  }
  *(_QWORD *)MultiByteStr = 0;
  cbMultiByte = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
  if ( cbMultiByte )
  {
    v10 = cbMultiByte + 15LL;
    if ( v10 < cbMultiByte )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    if ( WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, cbMultiByte, 0, 0) )
    {
      if ( OpenPrinterA(MultiByteStr, (LPHANDLE)MultiByteStr, 0) )
      {
        if ( DeletePrinter(*(HANDLE *)MultiByteStr) )
        {
          ClosePrinter(*(HANDLE *)MultiByteStr);
          return 0;
        }
        ClosePrinter(*(HANDLE *)MultiByteStr);
      }
      return (*(__int64 (__fastcall **)(CWshNetwork *, unsigned __int16 *, struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)this + 112LL))(
               this,
               a2,
               a3,
               a4);
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800087c0  push    rbp
0x1800087c2  push    rbx
0x1800087c3  push    rsi
0x1800087c4  push    rdi
0x1800087c5  push    r14
0x1800087c7  push    r15
0x1800087c9  sub     rsp, 58h
0x1800087cd  lea     rbp, [rsp+40h]
0x1800087d2  mov     rax, cs:__security_cookie
0x1800087d9  xor     rax, rbp
0x1800087dc  mov     [rbp+40h+var_38], rax
0x1800087e0  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x1800087e7  mov     r14, r9
0x1800087ea  mov     r15, r8
0x1800087ed  mov     rbx, rdx
0x1800087f0  mov     rsi, rcx
0x1800087f3  jz      short loc_18000880D
0x1800087f5  mov     rcx, rdx; pName
0x1800087f8  call    cs:__imp_DeletePrinterConnectionW
0x1800087fe  test    eax, eax
0x180008800  jz      loc_1800088F9
0x180008806  xor     eax, eax
0x180008808  jmp     loc_180008911
0x18000880d  mov     [rsp+80h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180008816  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000881a  mov     [rsp+80h+lpDefaultChar], 0; lpDefaultChar
0x180008823  mov     r8, rbx; lpWideCharStr
0x180008826  mov     [rsp+80h+cbMultiByte], 0; cbMultiByte
0x18000882e  xor     edx, edx; dwFlags
0x180008830  xor     ecx, ecx; CodePage
0x180008832  mov     [rsp+80h+lpMultiByteStr], 0; lpMultiByteStr
0x18000883b  mov     qword ptr [rbp+40h+MultiByteStr], 0
0x180008843  call    cs:__imp_WideCharToMultiByte
0x180008849  movsxd  rdx, eax
0x18000884c  test    eax, eax
0x18000884e  jnz     short loc_18000886B
0x180008850  call    cs:__imp_GetLastError
0x180008856  test    eax, eax
0x180008858  jle     loc_180008911
0x18000885e  movzx   eax, ax
0x180008861  or      eax, 80070000h
0x180008866  jmp     loc_180008911
0x18000886b  lea     rcx, [rdx+0Fh]
0x18000886f  cmp     rcx, rdx
0x180008872  ja      short loc_18000887E
0x180008874  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000887e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008882  mov     rax, rcx
0x180008885  call    _alloca_probe
0x18000888a  sub     rsp, rcx
0x18000888d  or      r9d, 0FFFFFFFFh; cchWideChar
0x180008891  mov     r8, rbx; lpWideCharStr
0x180008894  xor     ecx, ecx; CodePage
0x180008896  mov     [rsp+80h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000889f  lea     rdi, [rsp+80h+MultiByteStr]
0x1800088a4  mov     [rsp+80h+lpDefaultChar], 0; lpDefaultChar
0x1800088ad  mov     [rsp+80h+cbMultiByte], edx; cbMultiByte
0x1800088b1  xor     edx, edx; dwFlags
0x1800088b3  mov     [rsp+80h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800088b8  call    cs:__imp_WideCharToMultiByte
0x1800088be  test    eax, eax
0x1800088c0  jz      short loc_180008850
0x1800088c2  xor     r8d, r8d; pDefault
0x1800088c5  lea     rdx, [rbp+40h+MultiByteStr]; phPrinter
0x1800088c9  mov     rcx, rdi; pPrinterName
0x1800088cc  call    cs:__imp_OpenPrinterA
0x1800088d2  test    eax, eax
0x1800088d4  jz      short loc_1800088F9
0x1800088d6  mov     rcx, qword ptr [rbp+40h+MultiByteStr]; hPrinter
0x1800088da  call    cs:__imp_DeletePrinter
0x1800088e0  mov     rcx, qword ptr [rbp+40h+MultiByteStr]; hPrinter
0x1800088e4  test    eax, eax
0x1800088e6  jz      short loc_1800088F3
0x1800088e8  call    cs:__imp_ClosePrinter
0x1800088ee  jmp     loc_180008806
0x1800088f3  call    cs:__imp_ClosePrinter
0x1800088f9  mov     rax, [rsi]
0x1800088fc  mov     r9, r14
0x1800088ff  mov     r8, r15
0x180008902  mov     rdx, rbx
0x180008905  mov     rcx, rsi
0x180008908  mov     rax, [rax+70h]
0x18000890c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008911  mov     rcx, [rbp+40h+var_38]
0x180008915  xor     rcx, rbp; StackCookie
0x180008918  call    __security_check_cookie
0x18000891d  lea     rsp, [rbp+18h]
0x180008921  pop     r15
0x180008923  pop     r14
0x180008925  pop     rdi
0x180008926  pop     rsi
0x180008927  pop     rbx
0x180008928  pop     rbp
0x180008929  retn
```
