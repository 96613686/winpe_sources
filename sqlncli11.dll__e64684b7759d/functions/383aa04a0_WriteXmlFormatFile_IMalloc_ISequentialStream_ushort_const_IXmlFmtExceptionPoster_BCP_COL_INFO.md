# WriteXmlFormatFile(IMalloc *,ISequentialStream *,ushort const *,IXmlFmtExceptionPoster *,BCP_COL_INFO *)

- ea: `0x383aa04a0`
- end: `0x383aa09a4`
- name: `?WriteXmlFormatFile@@YAJPEAUIMalloc@@PEAUISequentialStream@@PEBGPEAVIXmlFmtExceptionPoster@@PEAUBCP_COL_INFO@@@Z`
- size: `1284`
- prototype: `__int64 __fastcall(struct IMalloc *, struct ISequentialStream *, const unsigned __int16 *, struct IXmlFmtExceptionPoster *, struct BCP_COL_INFO *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x383970430`
- `0x383a30900`

## callees

- `0x3838434c0`
- `0x383844d50`
- `0x38391aed0`
- `0x383aa0200`
- `0x383aa04a0`
- `0x383aa7f20`
- `0x383aac690`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x383aa0662`
- `KERNEL32!FreeLibrary` at `0x383aa08c2`
- `KERNEL32!FreeLibrary` at `0x383aa0662`
- `KERNEL32!FreeLibrary` at `0x383aa08c2`
- `KERNEL32!GetLastError` at `0x383aa07af`
- `KERNEL32!GetLastError` at `0x383aa07af`
- `KERNEL32!CloseHandle` at `0x383aa0974`
- `KERNEL32!CloseHandle` at `0x383aa0974`
- `KERNEL32!WriteFile` at `0x383aa07a5`
- `KERNEL32!WriteFile` at `0x383aa07a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall WriteXmlFormatFile(
        struct IMalloc *a1,
        struct ISequentialStream *a2,
        const unsigned __int16 *a3,
        struct IXmlFmtExceptionPoster *a4,
        struct BCP_COL_INFO *a5)
{
  unsigned int v8; // edi
  int v9; // esi
  char *v10; // rcx
  _QWORD *v11; // rdx
  __int64 v12; // rax
  char *v13; // rcx
  _QWORD *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rbx
  signed int LastError; // eax
  char *v18; // rcx
  _QWORD *v19; // rdx
  __int64 v20; // rax
  char *v21; // rcx
  _QWORD *v22; // rdx
  __int64 v23; // rax
  _QWORD v25[2]; // [rsp+30h] [rbp-1158h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+40h] [rbp-1148h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-1144h] BYREF
  void **v28; // [rsp+48h] [rbp-1140h] BYREF
  int v29; // [rsp+50h] [rbp-1138h]
  HANDLE hFile; // [rsp+58h] [rbp-1130h]
  __int64 v31; // [rsp+60h] [rbp-1128h]
  __int64 v32; // [rsp+70h] [rbp-1118h]
  __int64 v33; // [rsp+78h] [rbp-1110h] BYREF
  void **v34; // [rsp+80h] [rbp-1108h] BYREF
  __int64 v35; // [rsp+88h] [rbp-1100h]
  __int64 v36; // [rsp+90h] [rbp-10F8h]
  __int64 v37; // [rsp+A8h] [rbp-10E0h]
  __int64 v38; // [rsp+C0h] [rbp-10C8h]
  char v39; // [rsp+C8h] [rbp-10C0h] BYREF
  char *v40; // [rsp+D0h] [rbp-10B8h]
  char v41; // [rsp+E8h] [rbp-10A0h] BYREF
  char *v42; // [rsp+F0h] [rbp-1098h]
  HMODULE hLibModule; // [rsp+F8h] [rbp-1090h]
  __int64 v44; // [rsp+100h] [rbp-1088h]
  __int64 v45; // [rsp+110h] [rbp-1078h]
  __int64 v46; // [rsp+138h] [rbp-1050h]
  _BYTE Buffer[4096]; // [rsp+150h] [rbp-1038h] BYREF

  v46 = -2;
  v25[1] = a3;
  v8 = 0;
  v28 = &CFileWriteStream::`vftable';
  v29 = 1;
  hFile = (HANDLE)-1LL;
  v31 = -1;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  CBulkFormat::CBulkFormat((CBulkFormat *)&v34, g_pMO);
  v32 = 0;
  v9 = CFileWriteStream::Open((CFileWriteStream *)&v28, (const unsigned __int16 *)a2);
  if ( v9 >= 0 )
  {
    v25[0] = a1;
    if ( a1 )
      ((void (__fastcall *)(struct IMalloc *))a1->lpVtbl->AddRef)(a1);
    v16 = *CBulkFormat::GetXMLFormatStreamFromBCP((__int64)&v34, (CFmtStream *)&v33, (CFmtStream *)v25, (__int64)a4);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    v32 = v16;
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    while ( 1 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, DWORD *))(*(_QWORD *)v16 + 24LL))(
             v16,
             Buffer,
             4096,
             &nNumberOfBytesToWrite);
      if ( v9 >= 0 )
      {
        v8 = 0;
        NumberOfBytesWritten = 0;
        if ( hFile == (HANDLE)-1LL )
        {
          v8 = -2147221301;
        }
        else if ( !WriteFile(hFile, Buffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      if ( v9 )
        break;
      if ( v8 )
        goto LABEL_48;
    }
    if ( v9 != 1 )
      goto LABEL_50;
    if ( !v8 )
      goto LABEL_49;
LABEL_48:
    v9 = v8;
    if ( v8 != 1 )
      goto LABEL_50;
LABEL_49:
    v9 = 0;
LABEL_50:
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    while ( v42 != &v41 )
    {
      if ( v42 )
        v18 = v42 - 56;
      else
        v18 = 0;
      v19 = (_QWORD *)*((_QWORD *)v18 + 8);
      v20 = *((_QWORD *)v18 + 7);
      *(_QWORD *)(v20 + 8) = v19;
      *v19 = v20;
      *((_QWORD *)v18 + 8) = 0;
      *((_QWORD *)v18 + 7) = 0;
      if ( v18 )
        (**(void (__fastcall ***)(char *, __int64))v18)(v18, 1);
    }
    while ( v40 != &v39 )
    {
      if ( v40 )
        v21 = v40 - 48;
      else
        v21 = 0;
      v22 = (_QWORD *)*((_QWORD *)v21 + 7);
      v23 = *((_QWORD *)v21 + 6);
      *(_QWORD *)(v23 + 8) = v22;
      *v22 = v23;
      *((_QWORD *)v21 + 7) = 0;
      *((_QWORD *)v21 + 6) = 0;
      if ( v21 )
        (**(void (__fastcall ***)(char *, __int64))v21)(v21, 1);
    }
    if ( v45 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( hLibModule )
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    v34 = &CBulkRecord::`vftable';
    if ( v38 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    v34 = &CBulkField::`vftable';
    if ( v37 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    if ( v36 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    if ( v35 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43550[0], 348169, off_383B49120[0], 340);
    while ( v42 != &v41 )
    {
      if ( v42 )
        v10 = v42 - 56;
      else
        v10 = 0;
      v11 = (_QWORD *)*((_QWORD *)v10 + 8);
      v12 = *((_QWORD *)v10 + 7);
      *(_QWORD *)(v12 + 8) = v11;
      *v11 = v12;
      *((_QWORD *)v10 + 8) = 0;
      *((_QWORD *)v10 + 7) = 0;
      if ( v10 )
        (**(void (__fastcall ***)(char *, __int64))v10)(v10, 1);
    }
    while ( v40 != &v39 )
    {
      if ( v40 )
        v13 = v40 - 48;
      else
        v13 = 0;
      v14 = (_QWORD *)*((_QWORD *)v13 + 7);
      v15 = *((_QWORD *)v13 + 6);
      *(_QWORD *)(v15 + 8) = v14;
      *v14 = v15;
      *((_QWORD *)v13 + 7) = 0;
      *((_QWORD *)v13 + 6) = 0;
      if ( v13 )
        (**(void (__fastcall ***)(char *, __int64))v13)(v13, 1);
    }
    if ( v45 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( hLibModule )
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    v34 = &CBulkRecord::`vftable';
    if ( v38 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    v34 = &CBulkField::`vftable';
    if ( v37 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    if ( v36 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    if ( v35 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  }
  v28 = &CFileWriteStream::`vftable';
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x383aa04a0  push    rsi
0x383aa04a2  push    rdi
0x383aa04a3  push    r12
0x383aa04a5  push    r14
0x383aa04a7  push    r15
0x383aa04a9  mov     eax, 1160h
0x383aa04ae  call    _alloca_probe
0x383aa04b3  sub     rsp, rax
0x383aa04b6  mov     [rsp+1188h+var_1050], 0FFFFFFFFFFFFFFFEh
0x383aa04c2  mov     [rsp+1188h+arg_0], rbx
0x383aa04ca  mov     rax, cs:__security_cookie
0x383aa04d1  xor     rax, rsp
0x383aa04d4  mov     [rsp+1188h+var_38], rax
0x383aa04dc  mov     r14, r9
0x383aa04df  mov     rsi, rdx
0x383aa04e2  mov     rbx, rcx
0x383aa04e5  mov     [rsp+1188h+var_1150], r8
0x383aa04ea  mov     rdx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; struct IMalloc *
0x383aa04f1  xor     r12d, r12d
0x383aa04f4  mov     edi, r12d
0x383aa04f7  lea     r15, ??_7CFileWriteStream@@6B@; const CFileWriteStream::`vftable'
0x383aa04fe  mov     [rsp+1188h+var_1140], r15
0x383aa0503  mov     [rsp+1188h+var_1138], 1
0x383aa050b  mov     [rsp+1188h+hFile], 0FFFFFFFFFFFFFFFFh
0x383aa0514  mov     [rsp+1188h+var_1128], 0FFFFFFFFFFFFFFFFh
0x383aa051d  mov     [rsp+1188h+nNumberOfBytesToWrite], r12d
0x383aa0522  mov     [rsp+1188h+NumberOfBytesWritten], r12d
0x383aa0527  lea     rcx, [rsp+1188h+var_1108]; this
0x383aa052f  call    ??0CBulkFormat@@QEAA@PEAUIMalloc@@@Z; CBulkFormat::CBulkFormat(IMalloc *)
0x383aa0534  nop
0x383aa0535  mov     [rsp+1188h+var_1118], r12
0x383aa053a  mov     rdx, rsi; unsigned __int16 *
0x383aa053d  lea     rcx, [rsp+1188h+var_1140]; this
0x383aa0542  call    ?Open@CFileWriteStream@@UEAAJPEBG@Z; CFileWriteStream::Open(ushort const *)
0x383aa0547  mov     esi, eax
0x383aa0549  test    eax, eax
0x383aa054b  jns     loc_383AA06FC
0x383aa0551  test    byte ptr cs:_bidGblFlags, 2
0x383aa0558  jz      short loc_383AA0585
0x383aa055a  mov     rcx, cs:off_383B43550; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383aa0561  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383aa0568  test    rax, rax
0x383aa056b  jz      short loc_383AA0585
0x383aa056d  mov     r9d, 154h
0x383aa0573  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383aa057a  mov     edx, 55009h
0x383aa057f  call    _bidTraceW
0x383aa0584  nop
0x383aa0585  nop     word ptr [rax+rax+00000000h]
0x383aa0590  lea     rax, [rsp+1188h+var_10A0]
0x383aa0598  mov     rcx, [rsp+1188h+var_1098]
0x383aa05a0  cmp     rcx, rax
0x383aa05a3  jz      short loc_383AA05DB
0x383aa05a5  test    rcx, rcx
0x383aa05a8  jnz     short loc_383AA05AF
0x383aa05aa  mov     rcx, r12
0x383aa05ad  jmp     short loc_383AA05B3
0x383aa05af  add     rcx, 0FFFFFFFFFFFFFFC8h
0x383aa05b3  mov     rdx, [rcx+40h]
0x383aa05b7  mov     rax, [rcx+38h]
0x383aa05bb  mov     [rax+8], rdx
0x383aa05bf  mov     [rdx], rax
0x383aa05c2  mov     [rcx+40h], r12
0x383aa05c6  mov     [rcx+38h], r12
0x383aa05ca  test    rcx, rcx
0x383aa05cd  jz      short loc_383AA0590
0x383aa05cf  mov     rax, [rcx]
0x383aa05d2  mov     edx, 1
0x383aa05d7  call    qword ptr [rax]
0x383aa05d9  jmp     short loc_383AA0590
0x383aa05db  lea     rax, [rsp+1188h+var_10C0]
0x383aa05e3  mov     rcx, [rsp+1188h+var_10B8]
0x383aa05eb  cmp     rcx, rax
0x383aa05ee  jz      short loc_383AA0626
0x383aa05f0  test    rcx, rcx
0x383aa05f3  jnz     short loc_383AA05FA
0x383aa05f5  mov     rcx, r12
0x383aa05f8  jmp     short loc_383AA05FE
0x383aa05fa  add     rcx, 0FFFFFFFFFFFFFFD0h
0x383aa05fe  mov     rdx, [rcx+38h]
0x383aa0602  mov     rax, [rcx+30h]
0x383aa0606  mov     [rax+8], rdx
0x383aa060a  mov     [rdx], rax
0x383aa060d  mov     [rcx+38h], r12
0x383aa0611  mov     [rcx+30h], r12
0x383aa0615  test    rcx, rcx
0x383aa0618  jz      short loc_383AA05DB
0x383aa061a  mov     rax, [rcx]
0x383aa061d  mov     edx, 1
0x383aa0622  call    qword ptr [rax]
0x383aa0624  jmp     short loc_383AA05DB
0x383aa0626  mov     rdx, [rsp+1188h+var_1078]
0x383aa062e  test    rdx, rdx
0x383aa0631  jz      short loc_383AA0641
0x383aa0633  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa063a  mov     rax, [rcx]
0x383aa063d  call    qword ptr [rax+68h]
0x383aa0640  nop
0x383aa0641  mov     rcx, [rsp+1188h+var_1088]
0x383aa0649  test    rcx, rcx
0x383aa064c  jz      short loc_383AA0655
0x383aa064e  mov     rax, [rcx]
0x383aa0651  call    qword ptr [rax+10h]
0x383aa0654  nop
0x383aa0655  mov     rcx, [rsp+1188h+hLibModule]; hLibModule
0x383aa065d  test    rcx, rcx
0x383aa0660  jz      short loc_383AA0670
0x383aa0662  call    cs:__imp_FreeLibrary
0x383aa0668  mov     [rsp+1188h+hLibModule], r12
0x383aa0670  lea     rax, ??_7CBulkRecord@@6B@; const CBulkRecord::`vftable'
0x383aa0677  mov     [rsp+1188h+var_1108], rax
0x383aa067f  mov     rdx, [rsp+1188h+var_10C8]
0x383aa0687  test    rdx, rdx
0x383aa068a  jz      short loc_383AA0699
0x383aa068c  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa0693  mov     rax, [rcx]
0x383aa0696  call    qword ptr [rax+68h]
0x383aa0699  lea     rax, ??_7CBulkField@@6B@; const CBulkField::`vftable'
0x383aa06a0  mov     [rsp+1188h+var_1108], rax
0x383aa06a8  mov     rdx, [rsp+1188h+var_10E0]
0x383aa06b0  test    rdx, rdx
0x383aa06b3  jz      short loc_383AA06C2
0x383aa06b5  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa06bc  mov     rax, [rcx]
0x383aa06bf  call    qword ptr [rax+68h]
0x383aa06c2  mov     rdx, [rsp+1188h+var_10F8]
0x383aa06ca  test    rdx, rdx
0x383aa06cd  jz      short loc_383AA06DC
0x383aa06cf  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa06d6  mov     rax, [rcx]
0x383aa06d9  call    qword ptr [rax+68h]
0x383aa06dc  mov     rdx, [rsp+1188h+var_1100]
0x383aa06e4  test    rdx, rdx
0x383aa06e7  jz      short loc_383AA06F7
0x383aa06e9  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa06f0  mov     rax, [rcx]
0x383aa06f3  call    qword ptr [rax+68h]
0x383aa06f6  nop
0x383aa06f7  jmp     loc_383AA0964
0x383aa06fc  mov     [rsp+1188h+var_1158], rbx
0x383aa0701  test    rbx, rbx
0x383aa0704  jz      short loc_383AA070F
0x383aa0706  mov     rax, [rbx]
0x383aa0709  mov     rcx, rbx
0x383aa070c  call    qword ptr [rax+8]
0x383aa070f  mov     r9, r14
0x383aa0712  lea     r8, [rsp+1188h+var_1158]
0x383aa0717  lea     rdx, [rsp+1188h+var_1110]
0x383aa071c  lea     rcx, [rsp+1188h+var_1108]
0x383aa0724  call    ?GetXMLFormatStreamFromBCP@CBulkFormat@@QEAA?AV?$CComPtr@UISequentialStream@@@@V2@PEAUBCP_COL_INFO@@@Z; CBulkFormat::GetXMLFormatStreamFromBCP(CComPtr<ISequentialStream>,BCP_COL_INFO *)
0x383aa0729  nop
0x383aa072a  mov     rbx, [rax]
0x383aa072d  test    rbx, rbx
0x383aa0730  jz      short loc_383AA073B
0x383aa0732  mov     rax, [rbx]
0x383aa0735  mov     rcx, rbx
0x383aa0738  call    qword ptr [rax+8]
0x383aa073b  mov     [rsp+1188h+var_1118], rbx
0x383aa0740  mov     rcx, [rsp+1188h+var_1110]
0x383aa0745  test    rcx, rcx
0x383aa0748  jz      short loc_383AA0750
0x383aa074a  mov     rax, [rcx]
0x383aa074d  call    qword ptr [rax+10h]
0x383aa0750  mov     rax, [rbx]
0x383aa0753  lea     r9, [rsp+1188h+nNumberOfBytesToWrite]
0x383aa0758  mov     r8d, 1000h
0x383aa075e  lea     rdx, [rsp+1188h+Buffer]
0x383aa0766  mov     rcx, rbx
0x383aa0769  call    qword ptr [rax+18h]
0x383aa076c  mov     esi, eax
0x383aa076e  test    eax, eax
0x383aa0770  js      short loc_383AA07C4
0x383aa0772  mov     edi, r12d
0x383aa0775  mov     [rsp+1188h+NumberOfBytesWritten], r12d
0x383aa077a  cmp     [rsp+1188h+hFile], 0FFFFFFFFFFFFFFFFh
0x383aa0780  jnz     short loc_383AA0789
0x383aa0782  mov     edi, 800400CBh
0x383aa0787  jmp     short loc_383AA07C4
0x383aa0789  mov     [rsp+1188h+lpOverlapped], r12; lpOverlapped
0x383aa078e  lea     r9, [rsp+1188h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x383aa0793  mov     r8d, [rsp+1188h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x383aa0798  lea     rdx, [rsp+1188h+Buffer]; lpBuffer
0x383aa07a0  mov     rcx, [rsp+1188h+hFile]; hFile
0x383aa07a5  call    cs:__imp_WriteFile
0x383aa07ab  test    eax, eax
0x383aa07ad  jnz     short loc_383AA07C4
0x383aa07af  call    cs:__imp_GetLastError
0x383aa07b5  mov     edi, eax
0x383aa07b7  test    eax, eax
0x383aa07b9  jle     short loc_383AA07C4
0x383aa07bb  movzx   edi, ax
0x383aa07be  or      edi, 80070000h
0x383aa07c4  test    esi, esi
0x383aa07c6  jnz     short loc_383AA07CE
0x383aa07c8  test    edi, edi
0x383aa07ca  jz      short loc_383AA0750
0x383aa07cc  jmp     short loc_383AA07D7
0x383aa07ce  cmp     esi, 1
0x383aa07d1  jnz     short loc_383AA07E1
0x383aa07d3  test    edi, edi
0x383aa07d5  jz      short loc_383AA07DE
0x383aa07d7  cmp     edi, 1
0x383aa07da  mov     esi, edi
0x383aa07dc  jnz     short loc_383AA07E1
0x383aa07de  mov     esi, r12d
0x383aa07e1  test    rbx, rbx
0x383aa07e4  jz      short loc_383AA07F0
0x383aa07e6  mov     rax, [rbx]
0x383aa07e9  mov     rcx, rbx
0x383aa07ec  call    qword ptr [rax+10h]
0x383aa07ef  nop
0x383aa07f0  lea     rax, [rsp+1188h+var_10A0]
0x383aa07f8  mov     rcx, [rsp+1188h+var_1098]
0x383aa0800  cmp     rcx, rax
0x383aa0803  jz      short loc_383AA083B
0x383aa0805  test    rcx, rcx
0x383aa0808  jnz     short loc_383AA080F
0x383aa080a  mov     rcx, r12
0x383aa080d  jmp     short loc_383AA0813
0x383aa080f  add     rcx, 0FFFFFFFFFFFFFFC8h
0x383aa0813  mov     rdx, [rcx+40h]
0x383aa0817  mov     rax, [rcx+38h]
0x383aa081b  mov     [rax+8], rdx
0x383aa081f  mov     [rdx], rax
0x383aa0822  mov     [rcx+40h], r12
0x383aa0826  mov     [rcx+38h], r12
0x383aa082a  test    rcx, rcx
0x383aa082d  jz      short loc_383AA07F0
0x383aa082f  mov     rax, [rcx]
0x383aa0832  mov     edx, 1
0x383aa0837  call    qword ptr [rax]
0x383aa0839  jmp     short loc_383AA07F0
0x383aa083b  lea     rax, [rsp+1188h+var_10C0]
0x383aa0843  mov     rcx, [rsp+1188h+var_10B8]
0x383aa084b  cmp     rcx, rax
0x383aa084e  jz      short loc_383AA0886
0x383aa0850  test    rcx, rcx
0x383aa0853  jnz     short loc_383AA085A
0x383aa0855  mov     rcx, r12
0x383aa0858  jmp     short loc_383AA085E
0x383aa085a  add     rcx, 0FFFFFFFFFFFFFFD0h
0x383aa085e  mov     rdx, [rcx+38h]
0x383aa0862  mov     rax, [rcx+30h]
0x383aa0866  mov     [rax+8], rdx
0x383aa086a  mov     [rdx], rax
0x383aa086d  mov     [rcx+38h], r12
0x383aa0871  mov     [rcx+30h], r12
0x383aa0875  test    rcx, rcx
0x383aa0878  jz      short loc_383AA083B
0x383aa087a  mov     rax, [rcx]
0x383aa087d  mov     edx, 1
0x383aa0882  call    qword ptr [rax]
0x383aa0884  jmp     short loc_383AA083B
0x383aa0886  mov     rdx, [rsp+1188h+var_1078]
0x383aa088e  test    rdx, rdx
0x383aa0891  jz      short loc_383AA08A1
0x383aa0893  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa089a  mov     rax, [rcx]
0x383aa089d  call    qword ptr [rax+68h]
0x383aa08a0  nop
0x383aa08a1  mov     rcx, [rsp+1188h+var_1088]
0x383aa08a9  test    rcx, rcx
0x383aa08ac  jz      short loc_383AA08B5
0x383aa08ae  mov     rax, [rcx]
0x383aa08b1  call    qword ptr [rax+10h]
0x383aa08b4  nop
0x383aa08b5  mov     rcx, [rsp+1188h+hLibModule]; hLibModule
0x383aa08bd  test    rcx, rcx
0x383aa08c0  jz      short loc_383AA08D0
0x383aa08c2  call    cs:__imp_FreeLibrary
0x383aa08c8  mov     [rsp+1188h+hLibModule], r12
0x383aa08d0  lea     rax, ??_7CBulkRecord@@6B@; const CBulkRecord::`vftable'
0x383aa08d7  mov     [rsp+1188h+var_1108], rax
0x383aa08df  mov     rdx, [rsp+1188h+var_10C8]
0x383aa08e7  test    rdx, rdx
0x383aa08ea  jz      short loc_383AA08F9
0x383aa08ec  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa08f3  mov     rax, [rcx]
0x383aa08f6  call    qword ptr [rax+68h]
0x383aa08f9  lea     rax, ??_7CBulkField@@6B@; const CBulkField::`vftable'
0x383aa0900  mov     [rsp+1188h+var_1108], rax
0x383aa0908  mov     rdx, [rsp+1188h+var_10E0]
0x383aa0910  test    rdx, rdx
0x383aa0913  jz      short loc_383AA0922
0x383aa0915  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa091c  mov     rax, [rcx]
0x383aa091f  call    qword ptr [rax+68h]
0x383aa0922  mov     rdx, [rsp+1188h+var_10F8]
0x383aa092a  test    rdx, rdx
0x383aa092d  jz      short loc_383AA093C
0x383aa092f  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa0936  mov     rax, [rcx]
0x383aa0939  call    qword ptr [rax+68h]
0x383aa093c  mov     rdx, [rsp+1188h+var_1100]
0x383aa0944  test    rdx, rdx
0x383aa0947  jz      short loc_383AA0957
0x383aa0949  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aa0950  mov     rax, [rcx]
0x383aa0953  call    qword ptr [rax+68h]
0x383aa0956  nop
  ... truncated ...
```
