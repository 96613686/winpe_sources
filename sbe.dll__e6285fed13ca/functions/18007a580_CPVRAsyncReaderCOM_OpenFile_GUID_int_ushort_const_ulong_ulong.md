# CPVRAsyncReaderCOM::OpenFile(_GUID *,int,ushort const *,ulong,ulong)

- ea: `0x18007a580`
- end: `0x18007a749`
- name: `?OpenFile@CPVRAsyncReaderCOM@@UEAAJPEAU_GUID@@HPEBGKK@Z`
- size: `457`
- prototype: `int(CPVRAsyncReaderCOM *__hidden this, struct _GUID *, int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180001c00`
- `0x18007776c`
- `0x1800785c8`
- `0x18007959c`
- `0x18007a580`
- `0x18007b720`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007a71f`
- `KERNEL32!CloseHandle` at `0x18007a71f`
- `KERNEL32!LeaveCriticalSection` at `0x18007a710`
- `KERNEL32!LeaveCriticalSection` at `0x18007a710`
- `KERNEL32!EnterCriticalSection` at `0x18007a5db`
- `KERNEL32!EnterCriticalSection` at `0x18007a5db`
- `KERNEL32!GetLastError` at `0x18007a6ec`
- `KERNEL32!GetLastError` at `0x18007a6ec`
- `KERNEL32!CreateFileW` at `0x18007a610`
- `KERNEL32!CreateFileW` at `0x18007a610`

## pseudocode

```c
__int64 __fastcall CPVRAsyncReaderCOM::OpenFile(
        CPVRAsyncReaderCOM *this,
        struct _GUID *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        DWORD dwShareMode,
        DWORD dwCreationDisposition)
{
  __int64 FileW; // rsi
  __int64 v12; // r8
  signed int v13; // ebx
  CPVRAsyncReader *v14; // rax
  CPVRAsyncReader *v15; // rax
  unsigned int v16; // edx
  signed int LastError; // eax
  unsigned int v18[4]; // [rsp+50h] [rbp-268h] BYREF
  _BYTE v19[528]; // [rsp+60h] [rbp-258h] BYREF

  v18[0] = 0;
  if ( !a4 )
    return 2147500035LL;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( *((_QWORD *)this + 4) )
  {
    FileW = -1;
    v13 = -2147418113;
    goto LABEL_20;
  }
  FileW = (__int64)CreateFileW(a4, 0x80000000, dwShareMode, 0, dwCreationDisposition, 0x60000000u, 0);
  if ( FileW == -1 )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_20;
  }
  if ( a2 )
  {
    v13 = FormWriteCacheName(a2, a3, v12, v19);
    if ( v13 < 0 )
      goto LABEL_20;
    a2 = (struct _GUID *)v19;
  }
  v14 = (CPVRAsyncReader *)operator new(0xB78u);
  if ( v14 )
  {
    v15 = CPVRAsyncReader::CPVRAsyncReader(
            v14,
            (void *)FileW,
            (const unsigned __int16 *)a2,
            *((_DWORD *)this + 2),
            *((struct CAsyncIo **)this + 2),
            *((_DWORD *)this + 3) * *((_DWORD *)this + 2),
            *((struct CPVRIOCounters **)this + 11),
            a3,
            v18);
    *((_QWORD *)this + 4) = v15;
    if ( v15 )
    {
      v13 = v18[0];
      if ( v18[0] )
      {
        if ( (int)v18[0] > 0 )
          v13 = LOWORD(v18[0]) | 0x80070000;
        CPVRAsyncReader::`scalar deleting destructor'(v15, v16);
        *((_QWORD *)this + 4) = 0;
      }
      else
      {
        *((_QWORD *)this + 10) = 0;
        CPVRAsyncReader::Seek(v15, (unsigned __int64 *)this + 10);
        v13 = 0;
      }
      goto LABEL_20;
    }
  }
  else
  {
    *((_QWORD *)this + 4) = 0;
  }
  v13 = -2147024882;
LABEL_20:
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18007a580  push    rbx
0x18007a582  push    rbp
0x18007a583  push    rsi
0x18007a584  push    rdi
0x18007a585  push    r12
0x18007a587  push    r14
0x18007a589  push    r15
0x18007a58b  sub     rsp, 280h
0x18007a592  mov     rax, cs:__security_cookie
0x18007a599  xor     rax, rsp
0x18007a59c  mov     [rsp+2B8h+var_48], rax
0x18007a5a4  mov     r15d, [rsp+2B8h+dwShareMode]
0x18007a5ac  mov     rsi, r9
0x18007a5af  mov     r12d, [rsp+2B8h+arg_28]
0x18007a5b7  mov     r14d, r8d
0x18007a5ba  mov     [rsp+2B8h+var_268], 0
0x18007a5c2  mov     rbx, rdx
0x18007a5c5  mov     rdi, rcx
0x18007a5c8  test    r9, r9
0x18007a5cb  jnz     short loc_18007A5D7
0x18007a5cd  mov     eax, 80004003h
0x18007a5d2  jmp     loc_18007A727
0x18007a5d7  add     rcx, 28h ; '('; lpCriticalSection
0x18007a5db  call    cs:__imp_EnterCriticalSection
0x18007a5e1  cmp     qword ptr [rdi+20h], 0
0x18007a5e6  jnz     loc_18007A703
0x18007a5ec  mov     [rsp+2B8h+hTemplateFile], 0; hTemplateFile
0x18007a5f5  xor     r9d, r9d; lpSecurityAttributes
0x18007a5f8  mov     [rsp+2B8h+dwFlagsAndAttributes], 60000000h; dwFlagsAndAttributes
0x18007a600  mov     r8d, r15d; dwShareMode
0x18007a603  mov     edx, 80000000h; dwDesiredAccess
0x18007a608  mov     [rsp+2B8h+dwCreationDisposition], r12d; dwCreationDisposition
0x18007a60d  mov     rcx, rsi; lpFileName
0x18007a610  call    cs:__imp_CreateFileW
0x18007a616  mov     rsi, rax
0x18007a619  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007a61d  jz      loc_18007A6EC
0x18007a623  test    rbx, rbx
0x18007a626  jz      short loc_18007A647
0x18007a628  lea     r9, [rsp+2B8h+var_258]
0x18007a62d  mov     edx, r14d
0x18007a630  mov     rcx, rbx
0x18007a633  call    FormWriteCacheName
0x18007a638  mov     ebx, eax
0x18007a63a  test    eax, eax
0x18007a63c  js      loc_18007A70C
0x18007a642  lea     rbx, [rsp+2B8h+var_258]
0x18007a647  mov     ecx, 0B78h; Size
0x18007a64c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007a651  test    rax, rax
0x18007a654  jz      loc_18007A6DD
0x18007a65a  mov     r9d, [rdi+8]; unsigned int
0x18007a65e  lea     rcx, [rsp+2B8h+var_268]
0x18007a663  mov     [rsp+2B8h+var_278], rcx; unsigned int *
0x18007a668  mov     edx, r9d
0x18007a66b  imul    edx, [rdi+0Ch]
0x18007a66f  mov     r8, rbx; unsigned __int16 *
0x18007a672  mov     rcx, [rdi+58h]
0x18007a676  mov     [rsp+2B8h+var_280], r14d; int
0x18007a67b  mov     [rsp+2B8h+hTemplateFile], rcx; struct CPVRIOCounters *
0x18007a680  mov     rcx, [rdi+10h]
0x18007a684  mov     [rsp+2B8h+dwFlagsAndAttributes], edx; unsigned int
0x18007a688  mov     rdx, rsi; void *
0x18007a68b  mov     qword ptr [rsp+2B8h+dwCreationDisposition], rcx; struct CAsyncIo *
0x18007a690  mov     rcx, rax; this
0x18007a693  call    ??0CPVRAsyncReader@@QEAA@PEAXPEBGKPEAVCAsyncIo@@KPEAVCPVRIOCounters@@HPEAK@Z; CPVRAsyncReader::CPVRAsyncReader(void *,ushort const *,ulong,CAsyncIo *,ulong,CPVRIOCounters *,int,ulong *)
0x18007a698  mov     [rdi+20h], rax
0x18007a69c  test    rax, rax
0x18007a69f  jz      short loc_18007A6E5
0x18007a6a1  mov     ebx, [rsp+2B8h+var_268]
0x18007a6a5  test    ebx, ebx
0x18007a6a7  jz      short loc_18007A6C6
0x18007a6a9  jle     short loc_18007A6B4
0x18007a6ab  movzx   ebx, bx
0x18007a6ae  or      ebx, 80070000h
0x18007a6b4  mov     rcx, rax; this
0x18007a6b7  call    ??_GCPVRAsyncReader@@QEAAPEAXI@Z; CPVRAsyncReader::`scalar deleting destructor'(uint)
0x18007a6bc  mov     qword ptr [rdi+20h], 0
0x18007a6c4  jmp     short loc_18007A70C
0x18007a6c6  lea     rdx, [rdi+50h]; unsigned __int64 *
0x18007a6ca  mov     rcx, rax; this
0x18007a6cd  mov     qword ptr [rdx], 0
0x18007a6d4  call    ?Seek@CPVRAsyncReader@@QEAAXPEA_K@Z; CPVRAsyncReader::Seek(unsigned __int64 *)
0x18007a6d9  xor     ebx, ebx
0x18007a6db  jmp     short loc_18007A70C
0x18007a6dd  mov     qword ptr [rdi+20h], 0
0x18007a6e5  mov     ebx, 8007000Eh
0x18007a6ea  jmp     short loc_18007A70C
0x18007a6ec  call    cs:__imp_GetLastError
0x18007a6f2  mov     ebx, eax
0x18007a6f4  test    eax, eax
0x18007a6f6  jle     short loc_18007A70C
0x18007a6f8  movzx   ebx, ax
0x18007a6fb  or      ebx, 80070000h
0x18007a701  jmp     short loc_18007A70C
0x18007a703  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007a707  mov     ebx, 8000FFFFh
0x18007a70c  lea     rcx, [rdi+28h]; lpCriticalSection
0x18007a710  call    cs:__imp_LeaveCriticalSection
0x18007a716  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007a71a  jz      short loc_18007A725
0x18007a71c  mov     rcx, rsi; hObject
0x18007a71f  call    cs:__imp_CloseHandle
0x18007a725  mov     eax, ebx
0x18007a727  mov     rcx, [rsp+2B8h+var_48]
0x18007a72f  xor     rcx, rsp; StackCookie
0x18007a732  call    __security_check_cookie
0x18007a737  add     rsp, 280h
0x18007a73e  pop     r15
0x18007a740  pop     r14
0x18007a742  pop     r12
0x18007a744  pop     rdi
0x18007a745  pop     rsi
0x18007a746  pop     rbp
0x18007a747  pop     rbx
0x18007a748  retn
```
