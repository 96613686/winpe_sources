# wiasWritePageBufToFile

- ea: `0x18002cf80`
- end: `0x18002d125`
- name: `wiasWritePageBufToFile`
- size: `421`
- prototype: `__int64 __fastcall(struct _MINIDRV_TRANSFER_CONTEXT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002cf80`
- `0x18002d564`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18002d06b`
- `KERNEL32!WriteFile` at `0x18002d06b`
- `KERNEL32!GetLastError` at `0x18002d079`
- `KERNEL32!GetLastError` at `0x18002d079`

## string_xrefs

- `0x18002d090`: `wiasWritePageBufToFile, WriteFile failed (0x%X)`
- `0x18002d0b2`: `wiasWritePageBufToFile, WriteFile failed (0x%X)`
- `0x18002cf95`: `::wiasWritePageBufToFile`
- `0x18002cfa1`: `wiasWritePageBufToFile`
- `0x18002cfc4`: `wiasWritePageBufToFile, received NULL pmdtc pointer, 0x%08x`
- `0x18002cfe8`: `wiasWritePageBufToFile, received NULL pmdtc pointer, 0x%08x`
- `0x18002d0be`: `wiasWritePageBufToFile, lItemSize is negative or larger than buffer`
- `0x18002d0e0`: `wiasWritePageBufToFile, lItemSize is negative or larger than buffer`

## pseudocode

```c
__int64 __fastcall wiasWritePageBufToFile(struct _MINIDRV_TRANSFER_CONTEXT *a1)
{
  struct tagWiaTraceData_Type *v2; // rax
  char *v3; // rdx
  unsigned int v4; // r8d
  unsigned int v5; // edi
  char *v6; // rbx
  void *v7; // rdx
  void *v8; // rax
  int v9; // edx
  int v10; // ecx
  __int64 v11; // rax
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
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+8h] BYREF

  v2 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasWritePageBufToFile");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v23, v3, v4, "wiasWritePageBufToFile", lpOverlapped, v2);
  if ( !a1 )
  {
    v5 = -2147467261;
    v6 = (char *)WiaTrace_TraceLog("wiasWritePageBufToFile, received NULL pmdtc pointer, 0x%08x");
    WriteDbgTraceErrorWI("wiasWritePageBufToFile", v6);
    WiaTrcLib::Free((WiaTrcLib *)v6, v7);
    v8 = (void *)WiaTrace_Trace("wiasWritePageBufToFile, received NULL pmdtc pointer, 0x%08x", 2147500035LL);
LABEL_3:
    WiaTrace_ProcessTrace_Ex(v10, v9, (int)"wiasWritePageBufToFile", 1, v8);
    goto LABEL_15;
  }
  v11 = *(_QWORD *)((char *)a1 + 28) - *(_QWORD *)&WiaImgFmt_TIFF.Data1;
  if ( !v11 )
    v11 = *(_QWORD *)((char *)a1 + 36) - *(_QWORD *)WiaImgFmt_TIFF.Data4;
  if ( !v11 )
  {
    v5 = WritePageToMultiPageTiff(a1);
    goto LABEL_15;
  }
  v12 = *((_DWORD *)a1 + 30);
  NumberOfBytesWritten = 0;
  if ( v12 > *((_DWORD *)a1 + 15) || v12 < 0 )
  {
    v16 = (char *)WiaTrace_TraceLog("wiasWritePageBufToFile, lItemSize is negative or larger than buffer");
    WriteDbgTraceErrorWI("wiasWritePageBufToFile", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void *)WiaTrace_Trace("wiasWritePageBufToFile, lItemSize is negative or larger than buffer");
    WiaTrace_ProcessTrace_Ex(v20, v19, (int)"wiasWritePageBufToFile", 1, v18);
    v5 = -2147467259;
    goto LABEL_15;
  }
  v5 = 0;
  if ( !WriteFile(*((HANDLE *)a1 + 6), *((LPCVOID *)a1 + 10), v12, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v14 = (char *)WiaTrace_TraceLog("wiasWritePageBufToFile, WriteFile failed (0x%X)");
    WriteDbgTraceErrorWI("wiasWritePageBufToFile", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    v8 = (void *)WiaTrace_Trace("wiasWritePageBufToFile, WriteFile failed (0x%X)", v5);
    goto LABEL_3;
  }
LABEL_15:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v23);
  return v5;
}

```

## disassembly

```asm
0x18002cf80  mov     [rsp+arg_8], rbx
0x18002cf85  mov     [rsp+arg_10], rsi
0x18002cf8a  push    rdi
0x18002cf8b  sub     rsp, 80h
0x18002cf92  mov     rbx, rcx
0x18002cf95  lea     rcx, aWiaswritepageb_2; "::wiasWritePageBufToFile"
0x18002cf9c  call    WiaTrace_Trace
0x18002cfa1  lea     rsi, aWiaswritepageb_7; "wiasWritePageBufToFile"
0x18002cfa8  mov     [rsp+88h+var_60], rax; struct tagWiaTraceData_Type *
0x18002cfad  mov     r9, rsi; char *
0x18002cfb0  lea     rcx, [rsp+88h+var_58]; this
0x18002cfb5  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18002cfba  test    rbx, rbx
0x18002cfbd  jnz     short loc_18002D00E
0x18002cfbf  mov     edi, 80004003h
0x18002cfc4  lea     rcx, aWiaswritepageb_10; "wiasWritePageBufToFile, received NULL p"...
0x18002cfcb  mov     edx, edi
0x18002cfcd  call    WiaTrace_TraceLog
0x18002cfd2  mov     rdx, rax; char *
0x18002cfd5  mov     rcx, rsi; char *
0x18002cfd8  mov     rbx, rax
0x18002cfdb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002cfe0  mov     rcx, rbx; this
0x18002cfe3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002cfe8  lea     rcx, aWiaswritepageb_10; "wiasWritePageBufToFile, received NULL p"...
0x18002cfef  mov     edx, edi
0x18002cff1  call    WiaTrace_Trace
0x18002cff6  mov     r9d, 1; int
0x18002cffc  mov     [rsp+88h+lpOverlapped], rax; lpMem
0x18002d001  mov     r8, rsi; int
0x18002d004  call    WiaTrace_ProcessTrace_Ex
0x18002d009  jmp     loc_18002D104
0x18002d00e  mov     rax, [rbx+1Ch]
0x18002d012  sub     rax, qword ptr cs:WiaImgFmt_TIFF.Data1
0x18002d019  jnz     short loc_18002D026
0x18002d01b  mov     rax, [rbx+24h]
0x18002d01f  sub     rax, qword ptr cs:WiaImgFmt_TIFF.Data4
0x18002d026  test    rax, rax
0x18002d029  jnz     short loc_18002D03A
0x18002d02b  mov     rcx, rbx; struct _MINIDRV_TRANSFER_CONTEXT *
0x18002d02e  call    ?WritePageToMultiPageTiff@@YAJPEAU_MINIDRV_TRANSFER_CONTEXT@@@Z; WritePageToMultiPageTiff(_MINIDRV_TRANSFER_CONTEXT *)
0x18002d033  mov     edi, eax
0x18002d035  jmp     loc_18002D104
0x18002d03a  mov     r8d, [rbx+78h]; nNumberOfBytesToWrite
0x18002d03e  mov     [rsp+88h+NumberOfBytesWritten], 0
0x18002d049  cmp     r8d, [rbx+3Ch]
0x18002d04d  jg      short loc_18002D0BE
0x18002d04f  test    r8d, r8d
0x18002d052  js      short loc_18002D0BE
0x18002d054  mov     rdx, [rbx+50h]; lpBuffer
0x18002d058  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002d060  mov     rcx, [rbx+30h]; hFile
0x18002d064  xor     edi, edi
0x18002d066  mov     [rsp+88h+lpOverlapped], rdi; lpOverlapped
0x18002d06b  call    cs:__imp_WriteFile
0x18002d071  test    eax, eax
0x18002d073  jnz     loc_18002D104
0x18002d079  call    cs:__imp_GetLastError
0x18002d07f  mov     edi, eax
0x18002d081  test    eax, eax
0x18002d083  jle     short loc_18002D08E
0x18002d085  movzx   edi, ax
0x18002d088  or      edi, 80070000h
0x18002d08e  mov     edx, edi
0x18002d090  lea     rcx, aWiaswritepageb_4; "wiasWritePageBufToFile, WriteFile faile"...
0x18002d097  call    WiaTrace_TraceLog
0x18002d09c  mov     rdx, rax; char *
0x18002d09f  mov     rcx, rsi; char *
0x18002d0a2  mov     rbx, rax
0x18002d0a5  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d0aa  mov     rcx, rbx; this
0x18002d0ad  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d0b2  lea     rcx, aWiaswritepageb_4; "wiasWritePageBufToFile, WriteFile faile"...
0x18002d0b9  jmp     loc_18002CFEF
0x18002d0be  lea     rcx, aWiaswritepageb_6; "wiasWritePageBufToFile, lItemSize is ne"...
0x18002d0c5  call    WiaTrace_TraceLog
0x18002d0ca  mov     rdx, rax; char *
0x18002d0cd  mov     rcx, rsi; char *
0x18002d0d0  mov     rbx, rax
0x18002d0d3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002d0d8  mov     rcx, rbx; this
0x18002d0db  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002d0e0  lea     rcx, aWiaswritepageb_6; "wiasWritePageBufToFile, lItemSize is ne"...
0x18002d0e7  call    WiaTrace_Trace
0x18002d0ec  mov     r9d, 1; int
0x18002d0f2  mov     [rsp+88h+lpOverlapped], rax; lpMem
0x18002d0f7  mov     r8, rsi; int
0x18002d0fa  call    WiaTrace_ProcessTrace_Ex
0x18002d0ff  mov     edi, 80004005h
0x18002d104  lea     rcx, [rsp+88h+var_58]; this
0x18002d109  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18002d10e  lea     r11, [rsp+88h+var_8]
0x18002d116  mov     eax, edi
0x18002d118  mov     rbx, [r11+18h]
0x18002d11c  mov     rsi, [r11+20h]
0x18002d120  mov     rsp, r11
0x18002d123  pop     rdi
0x18002d124  retn
```
