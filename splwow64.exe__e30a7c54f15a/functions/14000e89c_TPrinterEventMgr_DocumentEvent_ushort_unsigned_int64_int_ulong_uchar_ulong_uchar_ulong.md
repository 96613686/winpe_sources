# TPrinterEventMgr::DocumentEvent(ushort *,unsigned __int64,int,ulong,uchar *,ulong *,uchar * *,ulong *)

- ea: `0x14000e89c`
- end: `0x14000ec20`
- name: `?DocumentEvent@TPrinterEventMgr@@QEAAHPEAG_KHKPEAEPEAKPEAPEAE3@Z`
- size: `900`
- prototype: `int(TPrinterEventMgr *__hidden this, unsigned __int16 *, unsigned __int64, int, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14000d9e0`

## callees

- `0x140001b9c`
- `0x140006894`
- `0x140007298`
- `0x14000e89c`
- `0x14000ec28`
- `0x14000f1e4`
- `0x140015540`
- `0x140016010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000ebab`
- `KERNEL32!SetLastError` at `0x14000ebab`
- `KERNEL32!GetLastError` at `0x14000ebcb`
- `KERNEL32!GetLastError` at `0x14000ebeb`
- `KERNEL32!GetLastError` at `0x14000ebcb`
- `KERNEL32!GetLastError` at `0x14000ebeb`
- `KERNEL32!GetProcAddress` at `0x14000e921`
- `KERNEL32!GetProcAddress` at `0x14000e921`
- `KERNEL32!FreeLibrary` at `0x14000ebc3`
- `KERNEL32!FreeLibrary` at `0x14000ebc3`
- `WINSPOOL!OpenPrinterW` at `0x14000e8eb`
- `WINSPOOL!OpenPrinterW` at `0x14000e8eb`
- `WINSPOOL!ClosePrinter` at `0x14000ebe3`
- `WINSPOOL!ClosePrinter` at `0x14000ebe3`

## pseudocode

```c
__int64 __fastcall TPrinterEventMgr::DocumentEvent(
        TLoad64BitDllsMgr **this,
        unsigned __int16 *a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int *a7,
        unsigned __int8 **a8,
        unsigned int *a9)
{
  unsigned int Filter; // r15d
  TLoad64BitDllsMgr **v13; // rdi
  TPrinterDriver *v14; // rcx
  HMODULE PrinterDriver; // rax
  HMODULE v16; // r12
  int (*ProcAddress)(void *, void *, int, unsigned int, void *, unsigned int, void *); // rax
  int (*v18)(void *, void *, int, unsigned int, void *, unsigned int, void *); // rsi
  unsigned int v19; // eax
  _QWORD *v20; // rdi
  unsigned int v21; // ebx
  unsigned int *v22; // rcx
  unsigned __int8 **v23; // r13
  unsigned int v24; // ebx
  __int64 v25; // rax
  size_t v26; // rax
  unsigned int v27; // esi
  unsigned __int8 *v28; // rax
  unsigned int v29; // edx
  unsigned int v30; // edi
  unsigned __int8 *v31; // rax
  TLoad64BitDllsMgr **v33; // [rsp+48h] [rbp-50h]
  size_t Size; // [rsp+50h] [rbp-48h]
  int (*v35)(void *, void *, int, unsigned int, void *, unsigned int, void *); // [rsp+58h] [rbp-40h]
  HANDLE phPrinter; // [rsp+A0h] [rbp+8h] BYREF
  void *Src; // [rsp+B0h] [rbp+18h] BYREF

  phPrinter = 0;
  Filter = 0;
  v13 = this + 7;
  v33 = this + 7;
  TLoad64BitDllsMgr::IncUIRefCnt(this[7]);
  if ( !OpenPrinterW(a2, &phPrinter, 0) )
  {
    *a9 = GetLastError();
    goto LABEL_38;
  }
  PrinterDriver = (HMODULE)TPrinterDriver::LoadPrinterDriver(v14, phPrinter);
  v16 = PrinterDriver;
  if ( !PrinterDriver )
  {
    *a9 = GetLastError();
    goto LABEL_36;
  }
  ProcAddress = (int (*)(void *, void *, int, unsigned int, void *, unsigned int, void *))GetProcAddress(
                                                                                            PrinterDriver,
                                                                                            "DrvDocumentEvent");
  v18 = ProcAddress;
  v35 = ProcAddress;
  if ( ProcAddress )
  {
    if ( a4 == 14 )
    {
      Filter = DocumentEventQueryFilter(a5, a6, a7, a8, ProcAddress, phPrinter, a3);
LABEL_33:
      v13 = v33;
      goto LABEL_34;
    }
    Src = 0;
    v19 = ((__int64 (__fastcall *)(HANDLE, void *, _QWORD, _QWORD, unsigned __int8 *, int, void **))ProcAddress)(
            phPrinter,
            a3,
            a4,
            a5,
            a6,
            4,
            &Src);
    Filter = v19;
    if ( a3 == (void *)-1LL && v19 == 1 )
    {
      v20 = Src;
      v21 = 2;
      if ( Src && a4 - 7 <= 2 )
      {
        v22 = a7;
        *a7 = 0;
        v23 = a8;
        *a8 = 0;
        v24 = v19 + 9;
        if ( *(_DWORD *)v20 == v19 && (v25 = v20[1], *(_DWORD *)(v25 + 8) == v24) )
        {
          v26 = *(unsigned int *)(v25 + 16);
          *v22 = v26;
          v27 = 0;
          if ( (_DWORD)v26 )
          {
            Size = v26;
            v28 = (unsigned __int8 *)operator new[]((unsigned int)v26);
            *v23 = v28;
            if ( v28 )
              memcpy_0(v28, *(const void **)(v20[1] + 24LL), Size);
            else
              v27 = 8;
          }
        }
        else
        {
          v27 = 87;
        }
        *a9 = v27;
        if ( a4 != 9 )
        {
          if ( a4 == 7 )
          {
            v24 = 12;
          }
          else
          {
            v24 = 0;
            if ( a4 == 8 )
              v24 = 11;
          }
        }
        ((void (__fastcall *)(HANDLE, __int64, _QWORD, _QWORD, void **, _DWORD, _QWORD))v35)(
          phPrinter,
          -1,
          v24,
          0,
          &Src,
          0,
          0);
        goto LABEL_33;
      }
    }
    else
    {
      v21 = 2;
    }
    if ( v19 == 1 && Src && ((a4 - 1) & 0xFFFFFFFD) == 0 )
    {
      v29 = *((unsigned __int16 *)Src + 34) + *((unsigned __int16 *)Src + 35);
      *a7 = v29;
      v30 = v29;
      v31 = (unsigned __int8 *)operator new[](v29);
      *a8 = v31;
      if ( v31 )
        memcpy_0(v31, Src, v30);
      else
        *a9 = 14;
      if ( a4 != 1 )
        v21 = 4;
      ((void (__fastcall *)(HANDLE, void *, _QWORD, __int64, void **, _DWORD, _QWORD))v18)(
        phPrinter,
        a3,
        v21,
        8,
        &Src,
        0,
        0);
    }
    goto LABEL_33;
  }
LABEL_34:
  FreeLibrary(v16);
LABEL_36:
  ClosePrinter(phPrinter);
LABEL_38:
  TLoad64BitDllsMgr::DecUIRefCnt(*v13);
  return Filter;
}

```

## disassembly

```asm
0x14000e89c  mov     rax, rsp
0x14000e89f  mov     [rax+10h], rbx
0x14000e8a3  mov     [rax+20h], rsi
0x14000e8a7  push    rdi
0x14000e8a8  push    r12
0x14000e8aa  push    r13
0x14000e8ac  push    r14
0x14000e8ae  push    r15
0x14000e8b0  sub     rsp, 70h
0x14000e8b4  mov     r14d, r9d
0x14000e8b7  mov     r13, r8
0x14000e8ba  mov     rbx, rdx
0x14000e8bd  mov     qword ptr [rax+8], 0
0x14000e8c5  xor     r15d, r15d
0x14000e8c8  mov     [rax-58h], r15d
0x14000e8cc  lea     rdi, [rcx+38h]
0x14000e8d0  mov     [rsp+98h+var_50], rdi
0x14000e8d5  mov     rcx, [rdi]; this
0x14000e8d8  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x14000e8dd  xor     r8d, r8d; pDefault
0x14000e8e0  lea     rdx, [rsp+98h+phPrinter]; phPrinter
0x14000e8e8  mov     rcx, rbx; pPrinterName
0x14000e8eb  call    cs:__imp_OpenPrinterW
0x14000e8f1  test    eax, eax
0x14000e8f3  jz      loc_14000EBEB
0x14000e8f9  mov     rdx, [rsp+98h+phPrinter]; void *
0x14000e901  call    ?LoadPrinterDriver@TPrinterDriver@@IEAAPEAXPEAX@Z; TPrinterDriver::LoadPrinterDriver(void *)
0x14000e906  mov     r12, rax
0x14000e909  mov     [rsp+98h+var_38], rax
0x14000e90e  test    rax, rax
0x14000e911  jz      loc_14000EBCB
0x14000e917  lea     rdx, aDrvdocumenteve; "DrvDocumentEvent"
0x14000e91e  mov     rcx, rax; hModule
0x14000e921  call    cs:__imp_GetProcAddress
0x14000e927  mov     rsi, rax
0x14000e92a  mov     [rsp+98h+var_40], rax
0x14000e92f  test    rax, rax
0x14000e932  jz      loc_14000EBC0
0x14000e938  cmp     r14d, 0Eh
0x14000e93c  jnz     short loc_14000E985
0x14000e93e  mov     [rsp+98h+var_68], r13; void *
0x14000e943  mov     rcx, [rsp+98h+phPrinter]
0x14000e94b  mov     [rsp+98h+var_70], rcx; void *
0x14000e950  mov     [rsp+98h+var_78], rax; int (*)(void *, void *, int, unsigned int, void *, unsigned int, void *)
0x14000e955  mov     r9, [rsp+98h+arg_38]; unsigned __int8 **
0x14000e95d  mov     r8, [rsp+98h+arg_30]; unsigned int *
0x14000e965  mov     rdx, [rsp+98h+arg_28]; unsigned __int8 *
0x14000e96d  mov     ecx, [rsp+98h+arg_20]; unsigned int
0x14000e974  call    ?DocumentEventQueryFilter@@YAHKPEAEPEAKPEAPEAEP6AHPEAX3HK3K3@Z33@Z; DocumentEventQueryFilter(ulong,uchar *,ulong *,uchar * *,int (*)(void *,void *,int,ulong,void *,ulong,void *),void *,void *)
0x14000e979  mov     r15d, eax
0x14000e97c  mov     [rsp+98h+var_58], eax
0x14000e980  jmp     loc_14000EBA2
0x14000e985  mov     [rsp+98h+Src], 0
0x14000e991  lea     rax, [rsp+98h+Src]
0x14000e999  mov     [rsp+98h+var_68], rax
0x14000e99e  mov     dword ptr [rsp+98h+var_70], 4
0x14000e9a6  mov     rax, [rsp+98h+arg_28]
0x14000e9ae  mov     [rsp+98h+var_78], rax
0x14000e9b3  mov     r9d, [rsp+98h+arg_20]
0x14000e9bb  mov     r8d, r14d
0x14000e9be  mov     rdx, r13
0x14000e9c1  mov     rcx, [rsp+98h+phPrinter]
0x14000e9c9  mov     rax, rsi
0x14000e9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9d1  mov     r15d, eax
0x14000e9d4  mov     [rsp+98h+var_58], eax
0x14000e9d8  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x14000e9dc  jnz     loc_14000EADD
0x14000e9e2  cmp     eax, 1
0x14000e9e5  jnz     loc_14000EADD
0x14000e9eb  mov     rdi, [rsp+98h+Src]
0x14000e9f3  lea     ebx, [rax+1]
0x14000e9f6  test    rdi, rdi
0x14000e9f9  jz      loc_14000EAE2
0x14000e9ff  lea     eax, [r14-7]
0x14000ea03  cmp     eax, ebx
0x14000ea05  ja      loc_14000EAE2
0x14000ea0b  mov     rcx, [rsp+98h+arg_30]
0x14000ea13  mov     dword ptr [rcx], 0
0x14000ea19  mov     r13, [rsp+98h+arg_38]
0x14000ea21  mov     qword ptr [r13+0], 0
0x14000ea29  lea     ebx, [r15+9]
0x14000ea2d  cmp     [rdi], r15d
0x14000ea30  jnz     short loc_14000EA81
0x14000ea32  mov     rax, [rdi+8]
0x14000ea36  cmp     [rax+8], ebx
0x14000ea39  jnz     short loc_14000EA81
0x14000ea3b  mov     eax, [rax+10h]
0x14000ea3e  mov     [rcx], eax
0x14000ea40  xor     esi, esi
0x14000ea42  mov     [rsp+98h+var_54], esi
0x14000ea46  test    eax, eax
0x14000ea48  jz      short loc_14000EA86
0x14000ea4a  mov     [rsp+98h+Size], rax
0x14000ea4f  mov     ecx, eax; unsigned __int64
0x14000ea51  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000ea56  mov     [r13+0], rax
0x14000ea5a  test    rax, rax
0x14000ea5d  jz      short loc_14000EA76
0x14000ea5f  mov     rdx, [rdi+8]
0x14000ea63  mov     r8, [rsp+98h+Size]; Size
0x14000ea68  mov     rdx, [rdx+18h]; Src
0x14000ea6c  mov     rcx, rax; void *
0x14000ea6f  call    memcpy_0
0x14000ea74  jmp     short loc_14000EA86
0x14000ea76  mov     esi, 8
0x14000ea7b  mov     [rsp+98h+var_54], esi
0x14000ea7f  jmp     short loc_14000EA86
0x14000ea81  mov     esi, 57h ; 'W'
0x14000ea86  mov     rax, [rsp+98h+arg_40]
0x14000ea8e  mov     [rax], esi
0x14000ea90  cmp     r14d, 9
0x14000ea94  jz      short loc_14000EAAE
0x14000ea96  cmp     r14d, 7
0x14000ea9a  jnz     short loc_14000EAA2
0x14000ea9c  lea     ebx, [r14+5]
0x14000eaa0  jmp     short loc_14000EAAE
0x14000eaa2  xor     ebx, ebx
0x14000eaa4  lea     eax, [rbx+0Bh]
0x14000eaa7  cmp     r14d, 8
0x14000eaab  cmovz   ebx, eax
0x14000eaae  mov     [rsp+98h+var_68], 0
0x14000eab7  mov     dword ptr [rsp+98h+var_70], 0
0x14000eabf  lea     rax, [rsp+98h+Src]
0x14000eac7  mov     [rsp+98h+var_78], rax
0x14000eacc  xor     r9d, r9d
0x14000eacf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000ead3  mov     rax, [rsp+98h+var_40]
0x14000ead8  jmp     loc_14000EB92
0x14000eadd  mov     ebx, 2
0x14000eae2  cmp     r15d, 1
0x14000eae6  jnz     loc_14000EBA2
0x14000eaec  mov     rdi, [rsp+98h+Src]
0x14000eaf4  test    rdi, rdi
0x14000eaf7  jz      loc_14000EBA2
0x14000eafd  lea     eax, [r14-1]
0x14000eb01  test    eax, 0FFFFFFFDh
0x14000eb06  jnz     loc_14000EBA2
0x14000eb0c  movzx   edx, word ptr [rdi+46h]
0x14000eb10  movzx   eax, word ptr [rdi+44h]
0x14000eb14  add     edx, eax
0x14000eb16  mov     rax, [rsp+98h+arg_30]
0x14000eb1e  mov     [rax], edx
0x14000eb20  mov     edi, edx
0x14000eb22  mov     ecx, edx; unsigned __int64
0x14000eb24  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000eb29  mov     rcx, [rsp+98h+arg_38]
0x14000eb31  mov     [rcx], rax
0x14000eb34  test    rax, rax
0x14000eb37  jz      short loc_14000EB4E
0x14000eb39  mov     r8d, edi; Size
0x14000eb3c  mov     rdx, [rsp+98h+Src]; Src
0x14000eb44  mov     rcx, rax; void *
0x14000eb47  call    memcpy_0
0x14000eb4c  jmp     short loc_14000EB5C
0x14000eb4e  mov     rax, [rsp+98h+arg_40]
0x14000eb56  mov     dword ptr [rax], 0Eh
0x14000eb5c  cmp     r14d, 1
0x14000eb60  mov     eax, 4
0x14000eb65  cmovnz  ebx, eax
0x14000eb68  mov     [rsp+98h+var_68], 0
0x14000eb71  mov     dword ptr [rsp+98h+var_70], 0
0x14000eb79  lea     rax, [rsp+98h+Src]
0x14000eb81  mov     [rsp+98h+var_78], rax
0x14000eb86  mov     r9d, 8
0x14000eb8c  mov     rdx, r13
0x14000eb8f  mov     rax, rsi
0x14000eb92  mov     r8d, ebx
0x14000eb95  mov     rcx, [rsp+98h+phPrinter]
0x14000eb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eba2  mov     rdi, [rsp+98h+var_50]
0x14000eba7  jmp     short loc_14000EBC0
0x14000eba9  mov     ecx, eax; dwErrCode
0x14000ebab  call    cs:__imp_SetLastError
0x14000ebb1  mov     r12, [rsp+98h+var_38]
0x14000ebb6  mov     r15d, [rsp+98h+var_58]
0x14000ebbb  mov     rdi, [rsp+98h+var_50]
0x14000ebc0  mov     rcx, r12; hLibModule
0x14000ebc3  call    cs:__imp_FreeLibrary
0x14000ebc9  jmp     short loc_14000EBDB
0x14000ebcb  call    cs:__imp_GetLastError
0x14000ebd1  mov     rcx, [rsp+98h+arg_40]
0x14000ebd9  mov     [rcx], eax
0x14000ebdb  mov     rcx, [rsp+98h+phPrinter]; hPrinter
0x14000ebe3  call    cs:__imp_ClosePrinter
0x14000ebe9  jmp     short loc_14000EBFB
0x14000ebeb  call    cs:__imp_GetLastError
0x14000ebf1  mov     rdx, [rsp+98h+arg_40]
0x14000ebf9  mov     [rdx], eax
0x14000ebfb  mov     rcx, [rdi]; this
0x14000ebfe  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x14000ec03  mov     eax, r15d
0x14000ec06  lea     r11, [rsp+98h+var_28]
0x14000ec0b  mov     rbx, [r11+38h]
0x14000ec0f  mov     rsi, [r11+48h]
0x14000ec13  mov     rsp, r11
0x14000ec16  pop     r15
0x14000ec18  pop     r14
0x14000ec1a  pop     r13
0x14000ec1c  pop     r12
0x14000ec1e  pop     rdi
0x14000ec1f  retn
```
