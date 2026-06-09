# CloseBufferFile(long,tagSTGMEDIUM *,uchar *,void *,long)

- ea: `0x180066368`
- end: `0x180066494`
- name: `?CloseBufferFile@@YAXJPEAUtagSTGMEDIUM@@PEAEPEAXJ@Z`
- size: `300`
- prototype: `void __fastcall(int, struct tagSTGMEDIUM *, unsigned __int8 *, void *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180066774`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800202b8`
- `0x18002de18`
- `0x18002def8`
- `0x180066368`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800663bd`
- `KERNEL32!CloseHandle` at `0x1800663bd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800663e9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800663e9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800663f9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800663f9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800663ae`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800663ae`

## string_xrefs

- `0x180066439`: `CoImpersonateClient failed (0x%X)`
- `0x18006645b`: `CoImpersonateClient failed (0x%X)`

## pseudocode

```c
void __fastcall CloseBufferFile(int a1, struct tagSTGMEDIUM *a2, unsigned __int8 *a3, void *a4, int a5)
{
  struct tagWiaTraceData_Type *v9; // rax
  char *v10; // rdx
  unsigned int v11; // r8d
  HRESULT v12; // edi
  int v13; // edi
  char *v14; // rbx
  void *v15; // rdx
  void *v16; // rax
  int v17; // edx
  int v18; // ecx
  char *v19; // rbx
  void *v20; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-88h]
  _BYTE v22[120]; // [rsp+30h] [rbp-78h] BYREF

  v9 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::CloseBufferFile");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v22, v10, v11, "CloseBufferFile", lpMem, v9);
  if ( a3 )
    UnmapViewOfFile(a3);
  if ( a4 != (void *)-1LL )
    CloseHandle(a4);
  if ( (a1 != 256 || (unsigned int)(a5 + 2145320958) > 2) && a5 )
  {
    v12 = CoImpersonateClient();
    if ( v12 < 0 )
    {
      v19 = (char *)WiaTrace_TraceLog("CoImpersonateClient failed (0x%X)");
      WriteDbgTraceErrorWI("CloseBufferFile", v19);
      WiaTrcLib::Free((WiaTrcLib *)v19, v20);
      v16 = (void *)WiaTrace_Trace("CoImpersonateClient failed (0x%X)", (unsigned int)v12);
      goto LABEL_12;
    }
    DeleteFileW(a2->lpszFileName);
    v13 = SafeCoRevertToSelf();
    if ( v13 < 0 )
    {
      v14 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
      WriteDbgTraceErrorWI("CloseBufferFile", v14);
      WiaTrcLib::Free((WiaTrcLib *)v14, v15);
      v16 = (void *)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", (unsigned int)v13);
LABEL_12:
      WiaTrace_ProcessTrace_Ex(v18, v17, (int)"CloseBufferFile", 1, v16);
    }
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v22);
}

```

## disassembly

```asm
0x180066368  push    rbx
0x18006636a  push    rbp
0x18006636b  push    rsi
0x18006636c  push    rdi
0x18006636d  push    r14
0x18006636f  sub     rsp, 80h
0x180066376  mov     esi, ecx
0x180066378  mov     rbx, r9
0x18006637b  lea     rcx, aClosebufferfil; "::CloseBufferFile"
0x180066382  mov     rdi, r8
0x180066385  mov     rbp, rdx
0x180066388  call    WiaTrace_Trace
0x18006638d  lea     r14, aClosebufferfil_0; "CloseBufferFile"
0x180066394  mov     [rsp+0A8h+var_80], rax; struct tagWiaTraceData_Type *
0x180066399  mov     r9, r14; char *
0x18006639c  lea     rcx, [rsp+0A8h+var_78]; this
0x1800663a1  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800663a6  test    rdi, rdi
0x1800663a9  jz      short loc_1800663B4
0x1800663ab  mov     rcx, rdi; lpBaseAddress
0x1800663ae  call    cs:__imp_UnmapViewOfFile
0x1800663b4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800663b8  jz      short loc_1800663C3
0x1800663ba  mov     rcx, rbx; hObject
0x1800663bd  call    cs:__imp_CloseHandle
0x1800663c3  mov     ecx, [rsp+0A8h+arg_20]
0x1800663ca  cmp     esi, 100h
0x1800663d0  jnz     short loc_1800663E1
0x1800663d2  lea     eax, [rcx+7FDEFFFEh]
0x1800663d8  cmp     eax, 2
0x1800663db  jbe     loc_18006647C
0x1800663e1  test    ecx, ecx
0x1800663e3  jz      loc_18006647C
0x1800663e9  call    cs:__imp_CoImpersonateClient
0x1800663ef  mov     edi, eax
0x1800663f1  test    eax, eax
0x1800663f3  js      short loc_180066437
0x1800663f5  mov     rcx, [rbp+8]; lpFileName
0x1800663f9  call    cs:__imp_DeleteFileW
0x1800663ff  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x180066404  mov     edi, eax
0x180066406  test    eax, eax
0x180066408  jns     short loc_18006647C
0x18006640a  mov     edx, eax
0x18006640c  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x180066413  call    WiaTrace_TraceLog
0x180066418  mov     rdx, rax; char *
0x18006641b  mov     rcx, r14; char *
0x18006641e  mov     rbx, rax
0x180066421  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180066426  mov     rcx, rbx; this
0x180066429  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006642e  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x180066435  jmp     short loc_180066462
0x180066437  mov     edx, edi
0x180066439  lea     rcx, aCoimpersonatec; "CoImpersonateClient failed (0x%X)"
0x180066440  call    WiaTrace_TraceLog
0x180066445  mov     rdx, rax; char *
0x180066448  mov     rcx, r14; char *
0x18006644b  mov     rbx, rax
0x18006644e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180066453  mov     rcx, rbx; this
0x180066456  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006645b  lea     rcx, aCoimpersonatec; "CoImpersonateClient failed (0x%X)"
0x180066462  mov     edx, edi
0x180066464  call    WiaTrace_Trace
0x180066469  mov     r9d, 1; int
0x18006646f  mov     [rsp+0A8h+lpMem], rax; lpMem
0x180066474  mov     r8, r14; int
0x180066477  call    WiaTrace_ProcessTrace_Ex
0x18006647c  lea     rcx, [rsp+0A8h+var_78]; this
0x180066481  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180066486  add     rsp, 80h
0x18006648d  pop     r14
0x18006648f  pop     rdi
0x180066490  pop     rsi
0x180066491  pop     rbp
0x180066492  pop     rbx
0x180066493  retn
```
