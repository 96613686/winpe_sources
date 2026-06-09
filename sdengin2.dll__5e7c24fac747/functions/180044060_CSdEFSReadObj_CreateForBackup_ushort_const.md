# CSdEFSReadObj::CreateForBackup(ushort const *)

- ea: `0x180044060`
- end: `0x1800442ec`
- name: `?CreateForBackup@CSdEFSReadObj@@UEAAJPEBG@Z`
- size: `652`
- prototype: `__int64 __fastcall(CSdEFSReadObj *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180008240`
- `0x180044060`
- `0x18004688c`
- `0x180046c60`
- `0x180047118`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x180044280`
- `KERNEL32!SetFilePointerEx` at `0x180044280`
- `KERNEL32!GetFileSizeEx` at `0x18004418c`
- `KERNEL32!GetFileSizeEx` at `0x18004418c`
- `KERNEL32!CreateFileW` at `0x180044106`
- `KERNEL32!CreateFileW` at `0x180044106`
- `KERNEL32!CloseHandle` at `0x18004413a`
- `KERNEL32!CloseHandle` at `0x18004414d`
- `KERNEL32!CloseHandle` at `0x1800441e8`
- `KERNEL32!CloseHandle` at `0x1800442bf`
- `KERNEL32!CloseHandle` at `0x18004413a`
- `KERNEL32!CloseHandle` at `0x18004414d`
- `KERNEL32!CloseHandle` at `0x1800441e8`
- `KERNEL32!CloseHandle` at `0x1800442bf`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!CloseEncryptedFileRaw` at `0x1800442de`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!CloseEncryptedFileRaw` at `0x1800442de`

## string_xrefs

- `0x180044088`: `CSdEFSReadObj::CreateForBackup`

## pseudocode

```c
__int64 __fastcall CSdEFSReadObj::CreateForBackup(CSdEFSReadObj *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  int LastFailureAsHRESULT; // esi
  __int64 v6; // rcx
  __int64 FileW; // rbx
  __int64 v9; // rcx
  CSdEFSReadObj *v10; // rcx
  __int16 v11; // ax
  __int64 v12; // rcx
  char *v13; // rcx
  int v14; // [rsp+40h] [rbp-40h] BYREF
  __int16 v15; // [rsp+44h] [rbp-3Ch]
  __int16 v16; // [rsp+46h] [rbp-3Ah]
  PVOID pvContext; // [rsp+B8h] [rbp+38h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+C0h] [rbp+40h] BYREF
  HANDLE hFile; // [rsp+C8h] [rbp+48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CSdEFSReadObj::CreateForBackup", 0x424u, 1u);
  pvContext = 0;
  v4 = -1;
  hFile = (HANDLE)-1LL;
  FileSize.QuadPart = 0;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v14 = -2147024809;
    v16 = 1069;
    goto LABEL_10;
  }
  v14 = 0;
  v15 = 1069;
  CSdEFSReadObj::_Dispose(this);
  FileW = (__int64)CreateFileW(a2, 0, 7u, 0, 3u, 0x2000000u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
    v14 = LastFailureAsHRESULT;
    v16 = 1093;
    goto LABEL_5;
  }
  v14 = 0;
  v15 = 1093;
  if ( !GetFileSizeEx((HANDLE)FileW, &FileSize) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v14 = LastFailureAsHRESULT;
    v16 = 1095;
LABEL_7:
    CloseHandle((HANDLE)FileW);
    goto LABEL_8;
  }
  v15 = 1095;
  if ( FileSize.QuadPart < 0 )
  {
    LastFailureAsHRESULT = -2130706378;
    v14 = -2130706378;
    v16 = 1098;
    goto LABEL_7;
  }
  v14 = 0;
  v15 = 1098;
  *((union _LARGE_INTEGER *)this + 16) = FileSize;
  CloseHandle((HANDLE)FileW);
  FileW = -1;
  v10 = (CSdEFSReadObj *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_073a8bff2569312743b066711ccc96ff_Traceguids, a2);
  LastFailureAsHRESULT = CSdEFSReadObj::_OpenEncryptedFileRawWithRetry(v10, a2, 0, &pvContext);
  v14 = LastFailureAsHRESULT;
  v11 = 1107;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_19;
  v15 = 1107;
  LastFailureAsHRESULT = CSdEFSReadObj::_CopyToTemporary(this, pvContext, &hFile);
  v14 = LastFailureAsHRESULT;
  v4 = (__int64)hFile;
  v11 = 1112;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_19;
  v15 = 1112;
  if ( !SetFilePointerEx(hFile, 0, 0, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
    v14 = LastFailureAsHRESULT;
    v11 = 1118;
LABEL_19:
    v16 = v11;
    goto LABEL_26;
  }
  LastFailureAsHRESULT = 0;
  v14 = 0;
  v15 = 1118;
  *((_DWORD *)this + 21) = 1;
  v13 = (char *)*((_QWORD *)this + 11);
  if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v13);
    LastFailureAsHRESULT = v14;
  }
  *((_QWORD *)this + 11) = v4;
  v4 = -1;
LABEL_26:
  if ( pvContext )
  {
    CloseEncryptedFileRaw(pvContext);
    LastFailureAsHRESULT = v14;
    goto LABEL_8;
  }
LABEL_5:
  if ( FileW != -1 && FileW )
    goto LABEL_7;
LABEL_8:
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v4);
LABEL_10:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180044060  mov     [rsp-28h+arg_0], rbx
0x180044065  push    rbp
0x180044066  push    rsi
0x180044067  push    rdi
0x180044068  push    r13
0x18004406a  push    r14
0x18004406c  mov     rbp, rsp
0x18004406f  sub     rsp, 80h
0x180044076  mov     rsi, rdx
0x180044079  mov     r14, rcx
0x18004407c  mov     r9d, 1; unsigned __int16
0x180044082  mov     r8d, 424h; unsigned __int16
0x180044088  lea     rdx, aCsdefsreadobjC_3; "CSdEFSReadObj::CreateForBackup"
0x18004408f  lea     rcx, [rbp+var_40]; this
0x180044093  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180044098  mov     [rbp+pvContext], 0
0x1800440a0  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800440a4  mov     rdi, r13
0x1800440a7  mov     [rbp+hFile], r13
0x1800440ab  mov     qword ptr [rbp+FileSize], 0
0x1800440b3  mov     eax, 42Dh
0x1800440b8  test    rsi, rsi
0x1800440bb  jnz     short loc_1800440CE
0x1800440bd  mov     esi, 80070057h
0x1800440c2  mov     [rbp+var_40], esi
0x1800440c5  mov     [rbp+var_3A], ax
0x1800440c9  jmp     loc_180044153
0x1800440ce  mov     [rbp+var_40], 0
0x1800440d5  mov     [rbp+var_3C], ax
0x1800440d9  mov     rcx, r14; this
0x1800440dc  call    ?_Dispose@CSdEFSReadObj@@AEAAJXZ; CSdEFSReadObj::_Dispose(void)
0x1800440e1  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1800440ea  mov     [rsp+80h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800440f2  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x1800440fa  xor     r9d, r9d; lpSecurityAttributes
0x1800440fd  xor     edx, edx; dwDesiredAccess
0x1800440ff  lea     r8d, [r9+7]; dwShareMode
0x180044103  mov     rcx, rsi; lpFileName
0x180044106  call    cs:__imp_CreateFileW
0x18004410c  mov     rbx, rax
0x18004410f  inc     rax
0x180044112  test    rax, 0FFFFFFFFFFFFFFFEh
0x180044118  jnz     short loc_180044175
0x18004411a  call    GetLastFailureAsHRESULT
0x18004411f  mov     esi, eax
0x180044121  mov     [rbp+var_40], eax
0x180044124  mov     eax, 445h
0x180044129  mov     [rbp+var_3A], ax
0x18004412d  cmp     rbx, r13
0x180044130  jz      short loc_180044140
0x180044132  test    rbx, rbx
0x180044135  jz      short loc_180044140
0x180044137  mov     rcx, rbx; hObject
0x18004413a  call    cs:__imp_CloseHandle
0x180044140  lea     rcx, [rdi-1]
0x180044144  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180044148  ja      short loc_180044153
0x18004414a  mov     rcx, rdi; hObject
0x18004414d  call    cs:__imp_CloseHandle
0x180044153  lea     rcx, [rbp+var_40]; this
0x180044157  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004415c  mov     eax, esi
0x18004415e  mov     rbx, [rsp+80h+arg_0]
0x180044166  add     rsp, 80h
0x18004416d  pop     r14
0x18004416f  pop     r13
0x180044171  pop     rdi
0x180044172  pop     rsi
0x180044173  pop     rbp
0x180044174  retn
0x180044175  mov     [rbp+var_40], 0
0x18004417c  mov     eax, 445h
0x180044181  mov     [rbp+var_3C], ax
0x180044185  lea     rdx, [rbp+FileSize]; lpFileSize
0x180044189  mov     rcx, rbx; hFile
0x18004418c  call    cs:__imp_GetFileSizeEx
0x180044192  test    eax, eax
0x180044194  jnz     short loc_1800441AB
0x180044196  call    GetLastFailureAsHRESULT
0x18004419b  mov     esi, eax
0x18004419d  mov     [rbp+var_40], eax
0x1800441a0  mov     eax, 447h
0x1800441a5  mov     [rbp+var_3A], ax
0x1800441a9  jmp     short loc_180044137
0x1800441ab  mov     eax, 447h
0x1800441b0  mov     [rbp+var_3C], ax
0x1800441b4  mov     rax, qword ptr [rbp+FileSize]
0x1800441b8  mov     ecx, 44Ah
0x1800441bd  test    rax, rax
0x1800441c0  jns     short loc_1800441D3
0x1800441c2  mov     esi, 81000036h
0x1800441c7  mov     [rbp+var_40], esi
0x1800441ca  mov     [rbp+var_3A], cx
0x1800441ce  jmp     loc_180044137
0x1800441d3  mov     [rbp+var_40], 0
0x1800441da  mov     [rbp+var_3C], cx
0x1800441de  mov     [r14+80h], rax
0x1800441e5  mov     rcx, rbx; hObject
0x1800441e8  call    cs:__imp_CloseHandle
0x1800441ee  mov     rbx, r13
0x1800441f1  lea     rax, WPP_GLOBAL_Control
0x1800441f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800441ff  cmp     rcx, rax
0x180044202  jz      short loc_180044225
0x180044204  test    dword ptr [rcx+1Ch], 2000h
0x18004420b  jz      short loc_180044225
0x18004420d  mov     edx, 0Eh
0x180044212  mov     r9, rsi
0x180044215  lea     r8, WPP_073a8bff2569312743b066711ccc96ff_Traceguids
0x18004421c  mov     rcx, [rcx+10h]
0x180044220  call    WPP_SF_S
0x180044225  lea     r9, [rbp+pvContext]; void **
0x180044229  xor     r8d, r8d; unsigned int
0x18004422c  mov     rdx, rsi; unsigned __int16 *
0x18004422f  call    ?_OpenEncryptedFileRawWithRetry@CSdEFSReadObj@@AEAAJPEBGKPEAPEAX@Z; CSdEFSReadObj::_OpenEncryptedFileRawWithRetry(ushort const *,ulong,void * *)
0x180044234  mov     esi, eax
0x180044236  mov     [rbp+var_40], eax
0x180044239  test    eax, eax
0x18004423b  mov     eax, 453h
0x180044240  jns     short loc_18004424B
0x180044242  mov     [rbp+var_3A], ax
0x180044246  jmp     loc_1800442CF
0x18004424b  mov     [rbp+var_3C], ax
0x18004424f  lea     r8, [rbp+hFile]; void **
0x180044253  mov     rdx, [rbp+pvContext]; void *
0x180044257  mov     rcx, r14; this
0x18004425a  call    ?_CopyToTemporary@CSdEFSReadObj@@AEAAJPEAXPEAPEAX@Z; CSdEFSReadObj::_CopyToTemporary(void *,void * *)
0x18004425f  mov     esi, eax
0x180044261  mov     [rbp+var_40], eax
0x180044264  mov     rdi, [rbp+hFile]
0x180044268  test    eax, eax
0x18004426a  mov     eax, 458h
0x18004426f  js      short loc_180044242
0x180044271  mov     [rbp+var_3C], ax
0x180044275  xor     edx, edx; liDistanceToMove
0x180044277  xor     r9d, r9d; dwMoveMethod
0x18004427a  xor     r8d, r8d; lpNewFilePointer
0x18004427d  mov     rcx, rdi; hFile
0x180044280  call    cs:__imp_SetFilePointerEx
0x180044286  test    eax, eax
0x180044288  jnz     short loc_18004429B
0x18004428a  call    GetLastFailureAsHRESULT
0x18004428f  mov     esi, eax
0x180044291  mov     [rbp+var_40], eax
0x180044294  mov     eax, 45Eh
0x180044299  jmp     short loc_180044242
0x18004429b  xor     esi, esi
0x18004429d  mov     [rbp+var_40], esi
0x1800442a0  mov     eax, 45Eh
0x1800442a5  mov     [rbp+var_3C], ax
0x1800442a9  mov     dword ptr [r14+54h], 1
0x1800442b1  mov     rcx, [r14+58h]; hObject
0x1800442b5  lea     rax, [rcx-1]
0x1800442b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800442bd  ja      short loc_1800442C8
0x1800442bf  call    cs:__imp_CloseHandle
0x1800442c5  mov     esi, [rbp+var_40]
0x1800442c8  mov     [r14+58h], rdi
0x1800442cc  mov     rdi, r13
0x1800442cf  cmp     [rbp+pvContext], 0
0x1800442d4  jz      loc_18004412D
0x1800442da  mov     rcx, [rbp+pvContext]; pvContext
0x1800442de  call    cs:__imp_CloseEncryptedFileRaw
0x1800442e4  mov     esi, [rbp+var_40]
0x1800442e7  jmp     loc_180044140
```
