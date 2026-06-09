# CSdEFSReadObj::CreateForBackup(ushort const *)

- ea: `0x1800459d0`
- end: `0x180045c90`
- name: `?CreateForBackup@CSdEFSReadObj@@UEAAJPEBG@Z`
- size: `704`
- prototype: `__int64 __fastcall(CSdEFSReadObj *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800083e4`
- `0x1800459d0`
- `0x1800483b4`
- `0x1800487bc`
- `0x180048c88`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x180045c12`
- `KERNEL32!SetFilePointerEx` at `0x180045c12`
- `KERNEL32!GetFileSizeEx` at `0x180045b0f`
- `KERNEL32!GetFileSizeEx` at `0x180045b0f`
- `KERNEL32!CreateFileW` at `0x180045a76`
- `KERNEL32!CreateFileW` at `0x180045a76`
- `KERNEL32!CloseHandle` at `0x180045ab0`
- `KERNEL32!CloseHandle` at `0x180045ac9`
- `KERNEL32!CloseHandle` at `0x180045b74`
- `KERNEL32!CloseHandle` at `0x180045c57`
- `KERNEL32!CloseHandle` at `0x180045ab0`
- `KERNEL32!CloseHandle` at `0x180045ac9`
- `KERNEL32!CloseHandle` at `0x180045b74`
- `KERNEL32!CloseHandle` at `0x180045c57`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!CloseEncryptedFileRaw` at `0x180045c7c`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!CloseEncryptedFileRaw` at `0x180045c7c`

## string_xrefs

- `0x1800459f8`: `CSdEFSReadObj::CreateForBackup`

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
0x1800459d0  mov     [rsp-28h+arg_0], rbx
0x1800459d5  push    rbp
0x1800459d6  push    rsi
0x1800459d7  push    rdi
0x1800459d8  push    r13
0x1800459da  push    r14
0x1800459dc  mov     rbp, rsp
0x1800459df  sub     rsp, 80h
0x1800459e6  mov     rsi, rdx
0x1800459e9  mov     r14, rcx
0x1800459ec  mov     r9d, 1; unsigned __int16
0x1800459f2  mov     r8d, 424h; unsigned __int16
0x1800459f8  lea     rdx, aCsdefsreadobjC_3; "CSdEFSReadObj::CreateForBackup"
0x1800459ff  lea     rcx, [rbp+var_40]; this
0x180045a03  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180045a08  mov     [rbp+pvContext], 0
0x180045a10  or      r13, 0FFFFFFFFFFFFFFFFh
0x180045a14  mov     rdi, r13
0x180045a17  mov     [rbp+hFile], r13
0x180045a1b  mov     qword ptr [rbp+FileSize], 0
0x180045a23  mov     eax, 42Dh
0x180045a28  test    rsi, rsi
0x180045a2b  jnz     short loc_180045A3E
0x180045a2d  mov     esi, 80070057h
0x180045a32  mov     [rbp+var_40], esi
0x180045a35  mov     [rbp+var_3A], ax
0x180045a39  jmp     loc_180045AD5
0x180045a3e  mov     [rbp+var_40], 0
0x180045a45  mov     [rbp+var_3C], ax
0x180045a49  mov     rcx, r14; this
0x180045a4c  call    ?_Dispose@CSdEFSReadObj@@AEAAJXZ; CSdEFSReadObj::_Dispose(void)
0x180045a51  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180045a5a  mov     [rsp+80h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180045a62  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180045a6a  xor     r9d, r9d; lpSecurityAttributes
0x180045a6d  xor     edx, edx; dwDesiredAccess
0x180045a6f  lea     r8d, [r9+7]; dwShareMode
0x180045a73  mov     rcx, rsi; lpFileName
0x180045a76  call    cs:__imp_CreateFileW
0x180045a7d  nop     dword ptr [rax+rax+00h]
0x180045a82  mov     rbx, rax
0x180045a85  inc     rax
0x180045a88  test    rax, 0FFFFFFFFFFFFFFFEh
0x180045a8e  jnz     short loc_180045AF8
0x180045a90  call    GetLastFailureAsHRESULT
0x180045a95  mov     esi, eax
0x180045a97  mov     [rbp+var_40], eax
0x180045a9a  mov     eax, 445h
0x180045a9f  mov     [rbp+var_3A], ax
0x180045aa3  cmp     rbx, r13
0x180045aa6  jz      short loc_180045ABC
0x180045aa8  test    rbx, rbx
0x180045aab  jz      short loc_180045ABC
0x180045aad  mov     rcx, rbx; hObject
0x180045ab0  call    cs:__imp_CloseHandle
0x180045ab7  nop     dword ptr [rax+rax+00h]
0x180045abc  lea     rcx, [rdi-1]
0x180045ac0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180045ac4  ja      short loc_180045AD5
0x180045ac6  mov     rcx, rdi; hObject
0x180045ac9  call    cs:__imp_CloseHandle
0x180045ad0  nop     dword ptr [rax+rax+00h]
0x180045ad5  lea     rcx, [rbp+var_40]; this
0x180045ad9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180045ade  mov     eax, esi
0x180045ae0  mov     rbx, [rsp+80h+arg_0]
0x180045ae8  add     rsp, 80h
0x180045aef  pop     r14
0x180045af1  pop     r13
0x180045af3  pop     rdi
0x180045af4  pop     rsi
0x180045af5  pop     rbp
0x180045af6  retn
0x180045af8  mov     [rbp+var_40], 0
0x180045aff  mov     eax, 445h
0x180045b04  mov     [rbp+var_3C], ax
0x180045b08  lea     rdx, [rbp+FileSize]; lpFileSize
0x180045b0c  mov     rcx, rbx; hFile
0x180045b0f  call    cs:__imp_GetFileSizeEx
0x180045b16  nop     dword ptr [rax+rax+00h]
0x180045b1b  test    eax, eax
0x180045b1d  jnz     short loc_180045B37
0x180045b1f  call    GetLastFailureAsHRESULT
0x180045b24  mov     esi, eax
0x180045b26  mov     [rbp+var_40], eax
0x180045b29  mov     eax, 447h
0x180045b2e  mov     [rbp+var_3A], ax
0x180045b32  jmp     loc_180045AAD
0x180045b37  mov     eax, 447h
0x180045b3c  mov     [rbp+var_3C], ax
0x180045b40  mov     rax, qword ptr [rbp+FileSize]
0x180045b44  mov     ecx, 44Ah
0x180045b49  test    rax, rax
0x180045b4c  jns     short loc_180045B5F
0x180045b4e  mov     esi, 81000036h
0x180045b53  mov     [rbp+var_40], esi
0x180045b56  mov     [rbp+var_3A], cx
0x180045b5a  jmp     loc_180045AAD
0x180045b5f  mov     [rbp+var_40], 0
0x180045b66  mov     [rbp+var_3C], cx
0x180045b6a  mov     [r14+80h], rax
0x180045b71  mov     rcx, rbx; hObject
0x180045b74  call    cs:__imp_CloseHandle
0x180045b7b  nop     dword ptr [rax+rax+00h]
0x180045b80  mov     rbx, r13
0x180045b83  lea     rax, WPP_GLOBAL_Control
0x180045b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b91  cmp     rcx, rax
0x180045b94  jz      short loc_180045BB7
0x180045b96  test    dword ptr [rcx+1Ch], 2000h
0x180045b9d  jz      short loc_180045BB7
0x180045b9f  mov     edx, 0Eh
0x180045ba4  mov     r9, rsi
0x180045ba7  lea     r8, WPP_073a8bff2569312743b066711ccc96ff_Traceguids
0x180045bae  mov     rcx, [rcx+10h]
0x180045bb2  call    WPP_SF_S
0x180045bb7  lea     r9, [rbp+pvContext]; void **
0x180045bbb  xor     r8d, r8d; unsigned int
0x180045bbe  mov     rdx, rsi; unsigned __int16 *
0x180045bc1  call    ?_OpenEncryptedFileRawWithRetry@CSdEFSReadObj@@AEAAJPEBGKPEAPEAX@Z; CSdEFSReadObj::_OpenEncryptedFileRawWithRetry(ushort const *,ulong,void * *)
0x180045bc6  mov     esi, eax
0x180045bc8  mov     [rbp+var_40], eax
0x180045bcb  test    eax, eax
0x180045bcd  mov     eax, 453h
0x180045bd2  jns     short loc_180045BDD
0x180045bd4  mov     [rbp+var_3A], ax
0x180045bd8  jmp     loc_180045C6D
0x180045bdd  mov     [rbp+var_3C], ax
0x180045be1  lea     r8, [rbp+hFile]; void **
0x180045be5  mov     rdx, [rbp+pvContext]; void *
0x180045be9  mov     rcx, r14; this
0x180045bec  call    ?_CopyToTemporary@CSdEFSReadObj@@AEAAJPEAXPEAPEAX@Z; CSdEFSReadObj::_CopyToTemporary(void *,void * *)
0x180045bf1  mov     esi, eax
0x180045bf3  mov     [rbp+var_40], eax
0x180045bf6  mov     rdi, [rbp+hFile]
0x180045bfa  test    eax, eax
0x180045bfc  mov     eax, 458h
0x180045c01  js      short loc_180045BD4
0x180045c03  mov     [rbp+var_3C], ax
0x180045c07  xor     edx, edx; liDistanceToMove
0x180045c09  xor     r9d, r9d; dwMoveMethod
0x180045c0c  xor     r8d, r8d; lpNewFilePointer
0x180045c0f  mov     rcx, rdi; hFile
0x180045c12  call    cs:__imp_SetFilePointerEx
0x180045c19  nop     dword ptr [rax+rax+00h]
0x180045c1e  test    eax, eax
0x180045c20  jnz     short loc_180045C33
0x180045c22  call    GetLastFailureAsHRESULT
0x180045c27  mov     esi, eax
0x180045c29  mov     [rbp+var_40], eax
0x180045c2c  mov     eax, 45Eh
0x180045c31  jmp     short loc_180045BD4
0x180045c33  xor     esi, esi
0x180045c35  mov     [rbp+var_40], esi
0x180045c38  mov     eax, 45Eh
0x180045c3d  mov     [rbp+var_3C], ax
0x180045c41  mov     dword ptr [r14+54h], 1
0x180045c49  mov     rcx, [r14+58h]; hObject
0x180045c4d  lea     rax, [rcx-1]
0x180045c51  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180045c55  ja      short loc_180045C66
0x180045c57  call    cs:__imp_CloseHandle
0x180045c5e  nop     dword ptr [rax+rax+00h]
0x180045c63  mov     esi, [rbp+var_40]
0x180045c66  mov     [r14+58h], rdi
0x180045c6a  mov     rdi, r13
0x180045c6d  cmp     [rbp+pvContext], 0
0x180045c72  jz      loc_180045AA3
0x180045c78  mov     rcx, [rbp+pvContext]; pvContext
0x180045c7c  call    cs:__imp_CloseEncryptedFileRaw
0x180045c83  nop     dword ptr [rax+rax+00h]
0x180045c88  mov     esi, [rbp+var_40]
0x180045c8b  jmp     loc_180045ABC
```
