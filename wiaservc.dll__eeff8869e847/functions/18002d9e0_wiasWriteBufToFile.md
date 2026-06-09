# wiasWriteBufToFile

- ea: `0x18002d9e0`
- end: `0x18002db59`
- name: `wiasWriteBufToFile`
- size: `377`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002d9e0`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18002da9f`
- `KERNEL32!WriteFile` at `0x18002da9f`
- `KERNEL32!GetLastError` at `0x18002daad`
- `KERNEL32!GetLastError` at `0x18002daad`

## string_xrefs

- `0x18002dac4`: `wiasWritePageBufToFile, WriteFile failed (0x%X)`
- `0x18002dae6`: `wiasWritePageBufToFile, WriteFile failed (0x%X)`
- `0x18002daf2`: `wiasWritePageBufToFile, lItemSize is negative or larger than buffer`
- `0x18002db14`: `wiasWritePageBufToFile, lItemSize is negative or larger than buffer`
- `0x18002d9f2`: `::wiasWriteBufToFile`
- `0x18002da01`: `wiasWriteBufToFile`
- `0x18002da2f`: `wiasWriteBufToFile, received NULL pmdtc pointer, 0x%08x`
- `0x18002da53`: `wiasWriteBufToFile, received NULL pmdtc pointer, 0x%08x`

## pseudocode

```c
__int64 __fastcall wiasWriteBufToFile(__int64 a1, __int64 a2)
{
  struct tagWiaTraceData_Type *v3; // rax
  char *v4; // rdx
  unsigned int v5; // r8d
  unsigned int v6; // edi
  char *v7; // rbx
  void *v8; // rdx
  void *v9; // rax
  int v10; // edx
  int v11; // ecx
  signed int v12; // r8d
  signed int LastError; // eax
  char *v14; // rbx
  void *v15; // rdx
  char *v16; // rbx
  void *v17; // rdx
  void *v18; // rax
  int v19; // edx
  int v20; // ecx
  unsigned int lpOverlapped; // [rsp+20h] [rbp-68h]
  _BYTE v23[80]; // [rsp+30h] [rbp-58h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp+10h] BYREF

  v3 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasWriteBufToFile");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v23, v4, v5, "wiasWriteBufToFile", lpOverlapped, v3);
  NumberOfBytesWritten = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    v7 = (char *)WiaTrace_TraceLog("wiasWriteBufToFile, received NULL pmdtc pointer, 0x%08x");
    WriteDbgTraceErrorWI("wiasWriteBufToFile", v7);
    WiaTrcLib::Free((WiaTrcLib *)v7, v8);
    v9 = (void *)WiaTrace_Trace("wiasWriteBufToFile, received NULL pmdtc pointer, 0x%08x", 2147500035LL);
LABEL_3:
    WiaTrace_ProcessTrace_Ex(v11, v10, (int)"wiasWriteBufToFile", 1, v9);
    goto LABEL_11;
  }
  v12 = *(_DWORD *)(a2 + 120);
  if ( v12 > *(_DWORD *)(a2 + 60) || v12 < 0 )
  {
    v16 = (char *)WiaTrace_TraceLog("wiasWritePageBufToFile, lItemSize is negative or larger than buffer");
    WriteDbgTraceErrorWI("wiasWriteBufToFile", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void *)WiaTrace_Trace("wiasWritePageBufToFile, lItemSize is negative or larger than buffer");
    WiaTrace_ProcessTrace_Ex(v20, v19, (int)"wiasWriteBufToFile", 1, v18);
    v6 = -2147467259;
    goto LABEL_11;
  }
  v6 = 0;
  if ( !WriteFile(*(HANDLE *)(a2 + 48), *(LPCVOID *)(a2 + 80), v12, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v14 = (char *)WiaTrace_TraceLog("wiasWritePageBufToFile, WriteFile failed (0x%X)");
    WriteDbgTraceErrorWI("wiasWriteBufToFile", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    v9 = (void *)WiaTrace_Trace("wiasWritePageBufToFile, WriteFile failed (0x%X)", v6);
    goto LABEL_3;
  }
LABEL_11:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v23);
  return v6;
}

```

## disassembly

```asm
0x18002d9e0  mov     [rsp+arg_0], rbx
0x18002d9e5  mov     [rsp+arg_10], rsi
0x18002d9ea  push    rdi
0x18002d9eb  sub     rsp, 80h
0x18002d9f2  lea     rcx, aWiaswritebufto_2; "::wiasWriteBufToFile"
0x18002d9f9  mov     rbx, rdx
0x18002d9fc  call    WiaTrace_Trace
0x18002da01  lea     rsi, aWiaswritebufto_1; "wiasWriteBufToFile"
0x18002da08  mov     [rsp+88h+var_60], rax; struct tagWiaTraceData_Type *
0x18002da0d  mov     r9, rsi; char *
0x18002da10  lea     rcx, [rsp+88h+var_58]; this
0x18002da15  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18002da1a  mov     [rsp+88h+NumberOfBytesWritten], 0
0x18002da25  test    rbx, rbx
0x18002da28  jnz     short loc_18002DA79
0x18002da2a  mov     edi, 80004003h
0x18002da2f  lea     rcx, aWiaswritebufto_0; "wiasWriteBufToFile, received NULL pmdtc"...
0x18002da36  mov     edx, edi
0x18002da38  call    WiaTrace_TraceLog
0x18002da3d  mov     rdx, rax; char *
0x18002da40  mov     rcx, rsi; char *
0x18002da43  mov     rbx, rax
0x18002da46  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002da4b  mov     rcx, rbx; this
0x18002da4e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002da53  lea     rcx, aWiaswritebufto_0; "wiasWriteBufToFile, received NULL pmdtc"...
0x18002da5a  mov     edx, edi
0x18002da5c  call    WiaTrace_Trace
0x18002da61  mov     r9d, 1; int
0x18002da67  mov     [rsp+88h+lpOverlapped], rax; lpMem
0x18002da6c  mov     r8, rsi; int
0x18002da6f  call    WiaTrace_ProcessTrace_Ex
0x18002da74  jmp     loc_18002DB38
0x18002da79  mov     r8d, [rbx+78h]; nNumberOfBytesToWrite
0x18002da7d  cmp     r8d, [rbx+3Ch]
0x18002da81  jg      short loc_18002DAF2
0x18002da83  test    r8d, r8d
0x18002da86  js      short loc_18002DAF2
0x18002da88  mov     rdx, [rbx+50h]; lpBuffer
0x18002da8c  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002da94  mov     rcx, [rbx+30h]; hFile
0x18002da98  xor     edi, edi
0x18002da9a  mov     [rsp+88h+lpOverlapped], rdi; lpOverlapped
0x18002da9f  call    cs:__imp_WriteFile
0x18002daa5  test    eax, eax
0x18002daa7  jnz     loc_18002DB38
0x18002daad  call    cs:__imp_GetLastError
0x18002dab3  mov     edi, eax
0x18002dab5  test    eax, eax
0x18002dab7  jle     short loc_18002DAC2
0x18002dab9  movzx   edi, ax
0x18002dabc  or      edi, 80070000h
0x18002dac2  mov     edx, edi
0x18002dac4  lea     rcx, aWiaswritepageb_4; "wiasWritePageBufToFile, WriteFile faile"...
0x18002dacb  call    WiaTrace_TraceLog
0x18002dad0  mov     rdx, rax; char *
0x18002dad3  mov     rcx, rsi; char *
0x18002dad6  mov     rbx, rax
0x18002dad9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002dade  mov     rcx, rbx; this
0x18002dae1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002dae6  lea     rcx, aWiaswritepageb_4; "wiasWritePageBufToFile, WriteFile faile"...
0x18002daed  jmp     loc_18002DA5A
0x18002daf2  lea     rcx, aWiaswritepageb_6; "wiasWritePageBufToFile, lItemSize is ne"...
0x18002daf9  call    WiaTrace_TraceLog
0x18002dafe  mov     rdx, rax; char *
0x18002db01  mov     rcx, rsi; char *
0x18002db04  mov     rbx, rax
0x18002db07  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002db0c  mov     rcx, rbx; this
0x18002db0f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002db14  lea     rcx, aWiaswritepageb_6; "wiasWritePageBufToFile, lItemSize is ne"...
0x18002db1b  call    WiaTrace_Trace
0x18002db20  mov     r9d, 1; int
0x18002db26  mov     [rsp+88h+lpOverlapped], rax; lpMem
0x18002db2b  mov     r8, rsi; int
0x18002db2e  call    WiaTrace_ProcessTrace_Ex
0x18002db33  mov     edi, 80004005h
0x18002db38  lea     rcx, [rsp+88h+var_58]; this
0x18002db3d  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18002db42  lea     r11, [rsp+88h+var_8]
0x18002db4a  mov     eax, edi
0x18002db4c  mov     rbx, [r11+10h]
0x18002db50  mov     rsi, [r11+20h]
0x18002db54  mov     rsp, r11
0x18002db57  pop     rdi
0x18002db58  retn
```
