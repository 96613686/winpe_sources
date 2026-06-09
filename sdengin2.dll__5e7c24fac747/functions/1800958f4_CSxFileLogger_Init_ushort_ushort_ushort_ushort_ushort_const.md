# CSxFileLogger::Init(ushort *,ushort *,ushort *,ushort *,ushort const *)

- ea: `0x1800958f4`
- end: `0x180095be6`
- name: `?Init@CSxFileLogger@@QEAAJPEAG000PEBG@Z`
- size: `754`
- prototype: `__int64 __usercall@<rax>(CSxFileLogger *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18001b0fc`
- `0x180029e88`

## callees

- `0x1800081d8`
- `0x180008200`
- `0x180008240`
- `0x18000b5cc`
- `0x180012958`
- `0x180014394`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180095314`
- `0x1800958f4`
- `0x180099d58`
- `0x18009a24c`
- `0x18009a378`
- `0x18009ae34`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180095a6e`
- `KERNEL32!CreateFileW` at `0x180095a6e`
- `KERNEL32!GetLastError` at `0x180095aa2`
- `KERNEL32!GetLastError` at `0x180095b1e`
- `KERNEL32!GetLastError` at `0x180095aa2`
- `KERNEL32!GetLastError` at `0x180095b1e`
- `KERNEL32!CloseHandle` at `0x180095a85`
- `KERNEL32!CloseHandle` at `0x180095a85`
- `KERNEL32!WriteFile` at `0x180095b14`
- `KERNEL32!WriteFile` at `0x180095b14`

## pseudocode

```c
__int64 __fastcall CSxFileLogger::Init(
        CSxFileLogger *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *NumberOfBytesWritten,
        unsigned __int16 *a6)
{
  __int16 v10; // ax
  CSxStringList *v11; // rcx
  const unsigned __int16 *v12; // r9
  HANDLE FileW; // rax
  char *v14; // rcx
  HANDLE v15; // rbx
  signed int LastError; // eax
  signed int v17; // ebx
  signed int v18; // eax
  PVOID *v19; // rcx
  unsigned int v20; // ebx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-99h]
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-89h]
  const unsigned __int16 *v24; // [rsp+38h] [rbp-81h]
  const unsigned __int16 *v25; // [rsp+40h] [rbp-79h]
  const unsigned __int16 *v26; // [rsp+48h] [rbp-71h]
  const unsigned __int16 *v27; // [rsp+50h] [rbp-69h]
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int16 *v29[2]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v30[2]; // [rsp+80h] [rbp-39h] BYREF
  int Instance; // [rsp+90h] [rbp-29h] BYREF
  __int16 v32; // [rsp+94h] [rbp-25h]
  __int16 v33; // [rsp+96h] [rbp-23h]
  __int16 Buffer; // [rsp+110h] [rbp+57h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&Instance, "CSxFileLogger::Init", 86, 1);
  LODWORD(NumberOfBytesWritten) = 0;
  v29[0] = (unsigned __int16 *)qword_1800E8530;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  v30[0] = qword_1800E8530;
  Buffer = -257;
  v29[1] = 0;
  lpFileName[1] = 0;
  v30[1] = 0;
  Instance = CBsString::Set((CSxFileLogger *)((char *)this + 16), a4);
  v10 = 103;
  if ( Instance < 0 )
    goto LABEL_2;
  v32 = 103;
  v11 = (CSxStringList *)*((_QWORD *)this + 4);
  if ( v11 )
  {
    *((_QWORD *)this + 4) = 0;
    CSxStringList::Release(v11);
  }
  Instance = CSxStringList::CreateInstance((struct CSxStringList **)this + 4);
  v10 = 104;
  if ( Instance < 0 )
    goto LABEL_2;
  v32 = 104;
  Instance = CSxFileLogger::DeleteExtraLogs(this, a2, a6, v12, dwCreationDisposition);
  v10 = 106;
  if ( Instance < 0 )
    goto LABEL_2;
  v32 = 106;
  Instance = CBsString::Format((CBsString *)v29, L"%s.%s", a3, L"log");
  v10 = 108;
  if ( Instance < 0 )
    goto LABEL_2;
  v32 = 108;
  Instance = CBsString::SetPath((CBsString *)lpFileName, a2, v29[0], 0, 0, 0, hTemplateFile, v24, v25, v26, v27);
  v10 = 110;
  if ( Instance < 0 )
    goto LABEL_2;
  v32 = 110;
  FileW = CreateFileW(lpFileName[0], 0x40000000u, 3u, 0, 2u, 0x80u, 0);
  v14 = (char *)*((_QWORD *)this + 1);
  v15 = FileW;
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
  *((_QWORD *)this + 1) = v15;
  if ( v15 == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids,
        (_DWORD)a2,
        v17);
    Instance = v17;
    v10 = 125;
    if ( v17 >= 0 )
    {
      v32 = 125;
      goto LABEL_19;
    }
LABEL_2:
    v33 = v10;
    goto LABEL_32;
  }
LABEL_19:
  if ( WriteFile(*((HANDLE *)this + 1), &Buffer, 2u, (LPDWORD)&NumberOfBytesWritten, 0) )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
      goto LABEL_29;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids);
    goto LABEL_28;
  }
  v18 = GetLastError();
  if ( v18 > 0 )
    v18 = (unsigned __int16)v18 | 0x80070000;
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
    {
LABEL_29:
      if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x10000000) != 0 )
        WPP_SF_S(v19[2], 13, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids, a2);
      goto LABEL_32;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids,
      (unsigned int)v18);
LABEL_28:
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_29;
  }
LABEL_32:
  v20 = Instance;
  CBsString::_Release((CBsString *)v30);
  CBsString::_Release((CBsString *)lpFileName);
  CBsString::_Release((CBsString *)v29);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&Instance);
  return v20;
}

```

## disassembly

```asm
0x1800958f4  push    rbp
0x1800958f6  push    rbx
0x1800958f7  push    rsi
0x1800958f8  push    rdi
0x1800958f9  push    r12
0x1800958fb  push    r14
0x1800958fd  lea     rbp, [rsp-1Fh]
0x180095902  sub     rsp, 0D8h
0x180095909  mov     rbx, r9
0x18009590c  mov     r14, r8
0x18009590f  mov     r9d, 1; unsigned __int16
0x180095915  mov     rsi, rdx
0x180095918  mov     rdi, rcx
0x18009591b  lea     rdx, aCsxfileloggerI; "CSxFileLogger::Init"
0x180095922  lea     rcx, [rbp+47h+var_70]; this
0x180095926  lea     r8d, [r9+55h]; unsigned __int16
0x18009592a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18009592f  lea     rax, qword_1800E8530
0x180095936  mov     dword ptr [rbp+47h+NumberOfBytesWritten], 0
0x18009593d  mov     [rbp+47h+var_90], rax
0x180095941  lea     rcx, [rdi+10h]; this
0x180095945  mov     [rbp+47h+lpFileName], rax
0x180095949  mov     rdx, rbx; unsigned __int16 *
0x18009594c  mov     [rbp+47h+var_80], rax
0x180095950  mov     eax, 0FEFFh
0x180095955  mov     [rbp+47h+Buffer], ax
0x180095959  mov     [rbp+47h+var_88], 0
0x180095961  mov     [rbp+47h+var_98], 0
0x180095969  mov     [rbp+47h+var_78], 0
0x180095971  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180095976  mov     [rbp+47h+var_70], eax
0x180095979  test    eax, eax
0x18009597b  mov     eax, 67h ; 'g'
0x180095980  jns     short loc_18009598B
0x180095982  mov     [rbp+47h+var_6A], ax
0x180095986  jmp     loc_180095BAD
0x18009598b  lea     rbx, [rdi+20h]
0x18009598f  mov     [rbp+47h+var_6C], ax
0x180095993  mov     rcx, [rbx]; this
0x180095996  test    rcx, rcx
0x180095999  jz      short loc_1800959A7
0x18009599b  mov     qword ptr [rbx], 0
0x1800959a2  call    ?Release@CSxStringList@@QEAAKXZ; CSxStringList::Release(void)
0x1800959a7  mov     rcx, rbx; struct CSxStringList **
0x1800959aa  call    ?CreateInstance@CSxStringList@@SAJPEAPEAV1@@Z; CSxStringList::CreateInstance(CSxStringList * *)
0x1800959af  mov     [rbp+47h+var_70], eax
0x1800959b2  test    eax, eax
0x1800959b4  mov     eax, 68h ; 'h'
0x1800959b9  js      short loc_180095982
0x1800959bb  mov     r8, [rbp+47h+arg_28]; unsigned __int16 *
0x1800959bf  mov     rdx, rsi; unsigned __int16 *
0x1800959c2  mov     rcx, rdi; this
0x1800959c5  mov     [rbp+47h+var_6C], ax
0x1800959c9  call    ?DeleteExtraLogs@CSxFileLogger@@QEAAJPEBG00K@Z; CSxFileLogger::DeleteExtraLogs(ushort const *,ushort const *,ushort const *,ulong)
0x1800959ce  mov     [rbp+47h+var_70], eax
0x1800959d1  test    eax, eax
0x1800959d3  mov     eax, 6Ah ; 'j'
0x1800959d8  js      short loc_180095982
0x1800959da  lea     r9, aLog; "log"
0x1800959e1  mov     [rbp+47h+var_6C], ax
0x1800959e5  mov     r8, r14
0x1800959e8  lea     rdx, aSS_0; "%s.%s"
0x1800959ef  lea     rcx, [rbp+47h+var_90]; this
0x1800959f3  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800959f8  mov     [rbp+47h+var_70], eax
0x1800959fb  test    eax, eax
0x1800959fd  mov     eax, 6Ch ; 'l'
0x180095a02  js      loc_180095982
0x180095a08  mov     r8, [rbp+47h+var_90]; unsigned __int16 *
0x180095a0c  lea     rcx, [rbp+47h+lpFileName]; this
0x180095a10  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], 0; unsigned __int16 *
0x180095a19  xor     r9d, r9d; unsigned __int16 *
0x180095a1c  mov     rdx, rsi; unsigned __int16 *
0x180095a1f  mov     qword ptr [rsp+100h+dwCreationDisposition], 0; unsigned __int16 *
0x180095a28  mov     [rbp+47h+var_6C], ax
0x180095a2c  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180095a31  mov     [rbp+47h+var_70], eax
0x180095a34  test    eax, eax
0x180095a36  mov     eax, 6Eh ; 'n'
0x180095a3b  js      loc_180095982
0x180095a41  mov     rcx, [rbp+47h+lpFileName]; lpFileName
0x180095a45  lea     r8d, [rax-6Bh]; dwShareMode
0x180095a49  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x180095a52  xor     r9d, r9d; lpSecurityAttributes
0x180095a55  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180095a5d  mov     edx, 40000000h; dwDesiredAccess
0x180095a62  mov     [rsp+100h+dwCreationDisposition], 2; dwCreationDisposition
0x180095a6a  mov     [rbp+47h+var_6C], ax
0x180095a6e  call    cs:__imp_CreateFileW
0x180095a74  mov     rcx, [rdi+8]; hObject
0x180095a78  mov     rbx, rax
0x180095a7b  lea     rdx, [rcx-1]
0x180095a7f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180095a83  ja      short loc_180095A8B
0x180095a85  call    cs:__imp_CloseHandle
0x180095a8b  mov     [rdi+8], rbx
0x180095a8f  lea     r12, WPP_GLOBAL_Control
0x180095a96  mov     r14d, 10000000h
0x180095a9c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180095aa0  jnz     short loc_180095AF9
0x180095aa2  call    cs:__imp_GetLastError
0x180095aa8  mov     ebx, eax
0x180095aaa  test    eax, eax
0x180095aac  jle     short loc_180095AB7
0x180095aae  movzx   ebx, ax
0x180095ab1  or      ebx, 80070000h
0x180095ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x180095abe  cmp     rcx, r12
0x180095ac1  jz      short loc_180095AE5
0x180095ac3  test    [rcx+1Ch], r14d
0x180095ac7  jz      short loc_180095AE5
0x180095ac9  mov     rcx, [rcx+10h]
0x180095acd  lea     r8, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids
0x180095ad4  mov     edx, 0Ah
0x180095ad9  mov     [rsp+100h+dwCreationDisposition], ebx
0x180095add  mov     r9, rsi
0x180095ae0  call    WPP_SF_Sd
0x180095ae5  mov     [rbp+47h+var_70], ebx
0x180095ae8  mov     eax, 7Dh ; '}'
0x180095aed  test    ebx, ebx
0x180095aef  js      loc_180095982
0x180095af5  mov     [rbp+47h+var_6C], ax
0x180095af9  mov     rcx, [rdi+8]; hFile
0x180095afd  lea     r9, [rbp+47h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180095b01  mov     r8d, 2; nNumberOfBytesToWrite
0x180095b07  mov     qword ptr [rsp+100h+dwCreationDisposition], 0; lpOverlapped
0x180095b10  lea     rdx, [rbp+47h+Buffer]; lpBuffer
0x180095b14  call    cs:__imp_WriteFile
0x180095b1a  test    eax, eax
0x180095b1c  jnz     short loc_180095B5C
0x180095b1e  call    cs:__imp_GetLastError
0x180095b24  test    eax, eax
0x180095b26  jle     short loc_180095B30
0x180095b28  movzx   eax, ax
0x180095b2b  or      eax, 80070000h
0x180095b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b37  cmp     rcx, r12
0x180095b3a  jz      short loc_180095BAD
0x180095b3c  test    [rcx+1Ch], r14d
0x180095b40  jz      short loc_180095B8A
0x180095b42  mov     rcx, [rcx+10h]
0x180095b46  lea     r8, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids
0x180095b4d  mov     edx, 0Bh
0x180095b52  mov     r9d, eax
0x180095b55  call    WPP_SF_d
0x180095b5a  jmp     short loc_180095B83
0x180095b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b63  cmp     rcx, r12
0x180095b66  jz      short loc_180095BAD
0x180095b68  test    [rcx+1Ch], r14d
0x180095b6c  jz      short loc_180095B8A
0x180095b6e  mov     rcx, [rcx+10h]
0x180095b72  lea     r8, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids
0x180095b79  mov     edx, 0Ch
0x180095b7e  call    WPP_SF_
0x180095b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b8a  cmp     rcx, r12
0x180095b8d  jz      short loc_180095BAD
0x180095b8f  test    [rcx+1Ch], r14d
0x180095b93  jz      short loc_180095BAD
0x180095b95  mov     rcx, [rcx+10h]
0x180095b99  lea     r8, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids
0x180095ba0  mov     edx, 0Dh
0x180095ba5  mov     r9, rsi
0x180095ba8  call    WPP_SF_S
0x180095bad  mov     ebx, [rbp+47h+var_70]
0x180095bb0  lea     rcx, [rbp+47h+var_80]; this
0x180095bb4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180095bb9  lea     rcx, [rbp+47h+lpFileName]; this
0x180095bbd  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180095bc2  lea     rcx, [rbp+47h+var_90]; this
0x180095bc6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180095bcb  lea     rcx, [rbp+47h+var_70]; this
0x180095bcf  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180095bd4  mov     eax, ebx
0x180095bd6  add     rsp, 0D8h
0x180095bdd  pop     r14
0x180095bdf  pop     r12
0x180095be1  pop     rdi
0x180095be2  pop     rsi
0x180095be3  pop     rbx
0x180095be4  pop     rbp
0x180095be5  retn
```
