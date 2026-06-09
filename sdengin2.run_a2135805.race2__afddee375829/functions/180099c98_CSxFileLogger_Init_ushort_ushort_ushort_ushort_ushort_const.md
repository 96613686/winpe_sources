# CSxFileLogger::Init(ushort *,ushort *,ushort *,ushort *,ushort const *)

- ea: `0x180099c98`
- end: `0x180099fa9`
- name: `?Init@CSxFileLogger@@QEAAJPEAG000PEBG@Z`
- size: `785`
- prototype: `__int64 __usercall@<rax>(CSxFileLogger *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18001bba8`
- `0x18002af08`

## callees

- `0x180008370`
- `0x1800083a0`
- `0x1800083e4`
- `0x18000b8f4`
- `0x1800131b0`
- `0x180014c30`
- `0x180072e08`
- `0x180072f14`
- `0x180099690`
- `0x180099c98`
- `0x18009e3c4`
- `0x18009e904`
- `0x18009ea34`
- `0x18009f560`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180099e12`
- `KERNEL32!CreateFileW` at `0x180099e12`
- `KERNEL32!GetLastError` at `0x180099e52`
- `KERNEL32!GetLastError` at `0x180099eda`
- `KERNEL32!GetLastError` at `0x180099e52`
- `KERNEL32!GetLastError` at `0x180099eda`
- `KERNEL32!CloseHandle` at `0x180099e2f`
- `KERNEL32!CloseHandle` at `0x180099e2f`
- `KERNEL32!WriteFile` at `0x180099eca`
- `KERNEL32!WriteFile` at `0x180099eca`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&Instance, "CSxFileLogger::Init", 0x56u, 1u);
  LODWORD(NumberOfBytesWritten) = 0;
  v29[0] = (unsigned __int16 *)qword_1800EE510;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  v30[0] = qword_1800EE510;
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
0x180099c98  push    rbp
0x180099c9a  push    rbx
0x180099c9b  push    rsi
0x180099c9c  push    rdi
0x180099c9d  push    r12
0x180099c9f  push    r14
0x180099ca1  lea     rbp, [rsp-1Fh]
0x180099ca6  sub     rsp, 0D8h
0x180099cad  mov     rbx, r9
0x180099cb0  mov     r14, r8
0x180099cb3  mov     r9d, 1; unsigned __int16
0x180099cb9  mov     rsi, rdx
0x180099cbc  mov     rdi, rcx
0x180099cbf  lea     rdx, aCsxfileloggerI; "CSxFileLogger::Init"
0x180099cc6  lea     rcx, [rbp+47h+var_70]; this
0x180099cca  lea     r8d, [r9+55h]; unsigned __int16
0x180099cce  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180099cd3  lea     rax, qword_1800EE510
0x180099cda  mov     dword ptr [rbp+47h+NumberOfBytesWritten], 0
0x180099ce1  mov     [rbp+47h+var_90], rax
0x180099ce5  lea     rcx, [rdi+10h]; this
0x180099ce9  mov     [rbp+47h+lpFileName], rax
0x180099ced  mov     rdx, rbx; unsigned __int16 *
0x180099cf0  mov     [rbp+47h+var_80], rax
0x180099cf4  mov     eax, 0FEFFh
0x180099cf9  mov     [rbp+47h+Buffer], ax
0x180099cfd  mov     [rbp+47h+var_88], 0
0x180099d05  mov     [rbp+47h+var_98], 0
0x180099d0d  mov     [rbp+47h+var_78], 0
0x180099d15  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180099d1a  mov     [rbp+47h+var_70], eax
0x180099d1d  test    eax, eax
0x180099d1f  mov     eax, 67h ; 'g'
0x180099d24  jns     short loc_180099D2F
0x180099d26  mov     [rbp+47h+var_6A], ax
0x180099d2a  jmp     loc_180099F6F
0x180099d2f  lea     rbx, [rdi+20h]
0x180099d33  mov     [rbp+47h+var_6C], ax
0x180099d37  mov     rcx, [rbx]; this
0x180099d3a  test    rcx, rcx
0x180099d3d  jz      short loc_180099D4B
0x180099d3f  mov     qword ptr [rbx], 0
0x180099d46  call    ?Release@CSxStringList@@QEAAKXZ; CSxStringList::Release(void)
0x180099d4b  mov     rcx, rbx; struct CSxStringList **
0x180099d4e  call    ?CreateInstance@CSxStringList@@SAJPEAPEAV1@@Z; CSxStringList::CreateInstance(CSxStringList * *)
0x180099d53  mov     [rbp+47h+var_70], eax
0x180099d56  test    eax, eax
0x180099d58  mov     eax, 68h ; 'h'
0x180099d5d  js      short loc_180099D26
0x180099d5f  mov     r8, [rbp+47h+arg_28]; unsigned __int16 *
0x180099d63  mov     rdx, rsi; unsigned __int16 *
0x180099d66  mov     rcx, rdi; this
0x180099d69  mov     [rbp+47h+var_6C], ax
0x180099d6d  call    ?DeleteExtraLogs@CSxFileLogger@@QEAAJPEBG00K@Z; CSxFileLogger::DeleteExtraLogs(ushort const *,ushort const *,ushort const *,ulong)
0x180099d72  mov     [rbp+47h+var_70], eax
0x180099d75  test    eax, eax
0x180099d77  mov     eax, 6Ah ; 'j'
0x180099d7c  js      short loc_180099D26
0x180099d7e  lea     r9, aLog; "log"
0x180099d85  mov     [rbp+47h+var_6C], ax
0x180099d89  mov     r8, r14
0x180099d8c  lea     rdx, aSS_0; "%s.%s"
0x180099d93  lea     rcx, [rbp+47h+var_90]; this
0x180099d97  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180099d9c  mov     [rbp+47h+var_70], eax
0x180099d9f  test    eax, eax
0x180099da1  mov     eax, 6Ch ; 'l'
0x180099da6  js      loc_180099D26
0x180099dac  mov     r8, [rbp+47h+var_90]; unsigned __int16 *
0x180099db0  lea     rcx, [rbp+47h+lpFileName]; this
0x180099db4  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], 0; unsigned __int16 *
0x180099dbd  xor     r9d, r9d; unsigned __int16 *
0x180099dc0  mov     rdx, rsi; unsigned __int16 *
0x180099dc3  mov     qword ptr [rsp+100h+dwCreationDisposition], 0; unsigned __int16 *
0x180099dcc  mov     [rbp+47h+var_6C], ax
0x180099dd0  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180099dd5  mov     [rbp+47h+var_70], eax
0x180099dd8  test    eax, eax
0x180099dda  mov     eax, 6Eh ; 'n'
0x180099ddf  js      loc_180099D26
0x180099de5  mov     rcx, [rbp+47h+lpFileName]; lpFileName
0x180099de9  lea     r8d, [rax-6Bh]; dwShareMode
0x180099ded  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x180099df6  xor     r9d, r9d; lpSecurityAttributes
0x180099df9  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180099e01  mov     edx, 40000000h; dwDesiredAccess
0x180099e06  mov     [rsp+100h+dwCreationDisposition], 2; dwCreationDisposition
0x180099e0e  mov     [rbp+47h+var_6C], ax
0x180099e12  call    cs:__imp_CreateFileW
0x180099e19  nop     dword ptr [rax+rax+00h]
0x180099e1e  mov     rcx, [rdi+8]; hObject
0x180099e22  mov     rbx, rax
0x180099e25  lea     rdx, [rcx-1]
0x180099e29  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180099e2d  ja      short loc_180099E3B
0x180099e2f  call    cs:__imp_CloseHandle
0x180099e36  nop     dword ptr [rax+rax+00h]
0x180099e3b  mov     [rdi+8], rbx
0x180099e3f  lea     r12, WPP_GLOBAL_Control
0x180099e46  mov     r14d, 10000000h
0x180099e4c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180099e50  jnz     short loc_180099EAF
0x180099e52  call    cs:__imp_GetLastError
0x180099e59  nop     dword ptr [rax+rax+00h]
0x180099e5e  mov     ebx, eax
0x180099e60  test    eax, eax
0x180099e62  jle     short loc_180099E6D
0x180099e64  movzx   ebx, ax
0x180099e67  or      ebx, 80070000h
0x180099e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180099e74  cmp     rcx, r12
0x180099e77  jz      short loc_180099E9B
0x180099e79  test    [rcx+1Ch], r14d
0x180099e7d  jz      short loc_180099E9B
0x180099e7f  mov     rcx, [rcx+10h]
0x180099e83  lea     r8, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids
0x180099e8a  mov     edx, 0Ah
0x180099e8f  mov     [rsp+100h+dwCreationDisposition], ebx
0x180099e93  mov     r9, rsi
0x180099e96  call    WPP_SF_Sd
0x180099e9b  mov     [rbp+47h+var_70], ebx
0x180099e9e  mov     eax, 7Dh ; '}'
0x180099ea3  test    ebx, ebx
0x180099ea5  js      loc_180099D26
0x180099eab  mov     [rbp+47h+var_6C], ax
0x180099eaf  mov     rcx, [rdi+8]; hFile
0x180099eb3  lea     r9, [rbp+47h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180099eb7  mov     r8d, 2; nNumberOfBytesToWrite
0x180099ebd  mov     qword ptr [rsp+100h+dwCreationDisposition], 0; lpOverlapped
0x180099ec6  lea     rdx, [rbp+47h+Buffer]; lpBuffer
0x180099eca  call    cs:__imp_WriteFile
0x180099ed1  nop     dword ptr [rax+rax+00h]
0x180099ed6  test    eax, eax
0x180099ed8  jnz     short loc_180099F1E
0x180099eda  call    cs:__imp_GetLastError
0x180099ee1  nop     dword ptr [rax+rax+00h]
0x180099ee6  test    eax, eax
0x180099ee8  jle     short loc_180099EF2
0x180099eea  movzx   eax, ax
0x180099eed  or      eax, 80070000h
0x180099ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180099ef9  cmp     rcx, r12
0x180099efc  jz      short loc_180099F6F
0x180099efe  test    [rcx+1Ch], r14d
0x180099f02  jz      short loc_180099F4C
0x180099f04  mov     rcx, [rcx+10h]
0x180099f08  lea     r8, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids
0x180099f0f  mov     edx, 0Bh
0x180099f14  mov     r9d, eax
0x180099f17  call    WPP_SF_d
0x180099f1c  jmp     short loc_180099F45
0x180099f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180099f25  cmp     rcx, r12
0x180099f28  jz      short loc_180099F6F
0x180099f2a  test    [rcx+1Ch], r14d
0x180099f2e  jz      short loc_180099F4C
0x180099f30  mov     rcx, [rcx+10h]
0x180099f34  lea     r8, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids
0x180099f3b  mov     edx, 0Ch
0x180099f40  call    WPP_SF_
0x180099f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180099f4c  cmp     rcx, r12
0x180099f4f  jz      short loc_180099F6F
0x180099f51  test    [rcx+1Ch], r14d
0x180099f55  jz      short loc_180099F6F
0x180099f57  mov     rcx, [rcx+10h]
0x180099f5b  lea     r8, WPP_0dc92619387c32b058f0b60f1e94783b_Traceguids
0x180099f62  mov     edx, 0Dh
0x180099f67  mov     r9, rsi
0x180099f6a  call    WPP_SF_S
0x180099f6f  mov     ebx, [rbp+47h+var_70]
0x180099f72  lea     rcx, [rbp+47h+var_80]; this
0x180099f76  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180099f7b  lea     rcx, [rbp+47h+lpFileName]; this
0x180099f7f  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180099f84  lea     rcx, [rbp+47h+var_90]; this
0x180099f88  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180099f8d  lea     rcx, [rbp+47h+var_70]; this
0x180099f91  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180099f96  mov     eax, ebx
0x180099f98  add     rsp, 0D8h
0x180099f9f  pop     r14
0x180099fa1  pop     r12
0x180099fa3  pop     rdi
0x180099fa4  pop     rsi
0x180099fa5  pop     rbx
0x180099fa6  pop     rbp
0x180099fa7  retn
```
