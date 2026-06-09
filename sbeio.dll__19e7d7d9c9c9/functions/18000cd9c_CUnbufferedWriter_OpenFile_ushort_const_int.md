# CUnbufferedWriter::OpenFile(ushort const *,int)

- ea: `0x18000cd9c`
- end: `0x18000cf9f`
- name: `?OpenFile@CUnbufferedWriter@@QEAAJPEBGH@Z`
- size: `515`
- prototype: `__int64 __fastcall(CUnbufferedWriter *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180009820`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x180001f1c`
- `0x180005060`
- `0x18000774c`
- `0x18000c9f8`
- `0x18000cd9c`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000cdd5`
- `KERNEL32!GetProcAddress` at `0x18000cde8`
- `KERNEL32!GetProcAddress` at `0x18000cdd5`
- `KERNEL32!GetProcAddress` at `0x18000cde8`
- `KERNEL32!GetFileType` at `0x18000cf17`
- `KERNEL32!GetFileType` at `0x18000cf17`
- `KERNEL32!GetModuleHandleW` at `0x18000cdb9`
- `KERNEL32!GetModuleHandleW` at `0x18000cdb9`
- `KERNEL32!CloseHandle` at `0x18000cf6f`
- `KERNEL32!CloseHandle` at `0x18000cf82`
- `KERNEL32!CloseHandle` at `0x18000cf6f`
- `KERNEL32!CloseHandle` at `0x18000cf82`
- `KERNEL32!GetLastError` at `0x18000cf46`
- `KERNEL32!GetLastError` at `0x18000cf46`
- `KERNEL32!CreateFileW` at `0x18000cf05`
- `KERNEL32!CreateFileW` at `0x18000cf05`
- `KERNEL32!CreateMutexW` at `0x18000cec4`
- `KERNEL32!CreateMutexW` at `0x18000cec4`

## string_xrefs

- `0x18000cdaf`: `kernel32.dll`
- `0x18000cdcb`: `GetQueuedCompletionStatus`
- `0x18000cddb`: `CreateIoCompletionPort`

## pseudocode

```c
__int64 __fastcall CUnbufferedWriter::OpenFile(unsigned __int16 **this, const unsigned __int16 *a2, int a3)
{
  HMODULE ModuleHandleW; // rax
  FARPROC *v7; // rsi
  HMODULE v8; // rbx
  signed int v9; // ebx
  unsigned __int64 v10; // rdx
  unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r14
  unsigned __int16 *v14; // rax
  unsigned __int16 *MutexW; // rax
  unsigned __int16 *FileW; // rax
  __int64 v17; // rax
  signed int LastError; // eax
  unsigned __int16 *v19; // rcx
  unsigned __int16 *v20; // rcx
  unsigned __int64 v22; // [rsp+80h] [rbp+8h] BYREF

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  v7 = (FARPROC *)(this + 1);
  v8 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    *this = (unsigned __int16 *)GetProcAddress(ModuleHandleW, "GetQueuedCompletionStatus");
    *v7 = GetProcAddress(v8, "CreateIoCompletionPort");
  }
  if ( !*this || !*v7 )
  {
    v9 = -2147467263;
    goto LABEL_23;
  }
  v9 = CUnbufferedWriter::CalcWriteSize((CUnbufferedWriter *)this, a3);
  if ( v9 < 0 )
    goto LABEL_23;
  v22 = 0;
  v9 = StringCchLengthW(a2, 0x104u, &v22);
  if ( v9 < 0 )
    goto LABEL_23;
  v11 = this[2];
  if ( v11 )
  {
    operator delete(v11, v10);
    this[2] = 0;
  }
  v12 = v22;
  v13 = v22 + 1;
  v14 = (unsigned __int16 *)operator new[](saturated_mul(v22 + 1, 2u));
  this[2] = v14;
  if ( !v14 )
  {
    v9 = -2147024882;
LABEL_23:
    v19 = this[3];
    if ( v19 != (unsigned __int16 *)-1LL )
    {
      CloseHandle(v19);
      this[3] = (unsigned __int16 *)-1LL;
    }
    v20 = this[4];
    if ( v20 )
    {
      CloseHandle(v20);
      this[4] = 0;
    }
    return (unsigned int)v9;
  }
  memset_0(v14, 0, 2 * v12 + 2);
  v9 = StringCchCopyW(this[2], v13, a2);
  if ( v9 < 0 )
    goto LABEL_23;
  MutexW = (unsigned __int16 *)CreateMutexW(0, 0, 0);
  this[9] = MutexW;
  if ( MutexW == (unsigned __int16 *)-1LL )
  {
    v9 = -2147023446;
    goto LABEL_23;
  }
  FileW = (unsigned __int16 *)CreateFileW(a2, 0xC0000000, 3u, 0, 2u, 0x60000000u, 0);
  this[3] = FileW;
  if ( FileW != (unsigned __int16 *)-1LL )
  {
    if ( GetFileType(FileW) != 1 )
    {
      v9 = -1072889828;
      goto LABEL_23;
    }
    v17 = ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, unsigned __int16 **, _QWORD))*v7)(this[3], 0, this, 0);
    this[4] = (unsigned __int16 *)v17;
    if ( v17 != -1 )
      return (unsigned int)v9;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_23;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000cd9c  push    rbx
0x18000cd9e  push    rbp
0x18000cd9f  push    rsi
0x18000cda0  push    rdi
0x18000cda1  push    r12
0x18000cda3  push    r14
0x18000cda5  sub     rsp, 48h
0x18000cda9  mov     rdi, rcx
0x18000cdac  mov     r14d, r8d
0x18000cdaf  lea     rcx, ModuleName; "kernel32.dll"
0x18000cdb6  mov     rbp, rdx
0x18000cdb9  call    cs:__imp_GetModuleHandleW
0x18000cdbf  lea     rsi, [rdi+8]
0x18000cdc3  mov     rbx, rax
0x18000cdc6  test    rax, rax
0x18000cdc9  jz      short loc_18000CDF1
0x18000cdcb  lea     rdx, ProcName; "GetQueuedCompletionStatus"
0x18000cdd2  mov     rcx, rax; hModule
0x18000cdd5  call    cs:__imp_GetProcAddress
0x18000cddb  lea     rdx, aCreateiocomple; "CreateIoCompletionPort"
0x18000cde2  mov     rcx, rbx; hModule
0x18000cde5  mov     [rdi], rax
0x18000cde8  call    cs:__imp_GetProcAddress
0x18000cdee  mov     [rsi], rax
0x18000cdf1  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000cdf5  cmp     qword ptr [rdi], 0
0x18000cdf9  jz      loc_18000CF61
0x18000cdff  cmp     qword ptr [rsi], 0
0x18000ce03  jz      loc_18000CF61
0x18000ce09  mov     edx, r14d; int
0x18000ce0c  mov     rcx, rdi; this
0x18000ce0f  call    ?CalcWriteSize@CUnbufferedWriter@@AEAAJH@Z; CUnbufferedWriter::CalcWriteSize(int)
0x18000ce14  mov     ebx, eax
0x18000ce16  test    eax, eax
0x18000ce18  js      loc_18000CF66
0x18000ce1e  lea     r8, [rsp+78h+arg_0]; unsigned __int64 *
0x18000ce26  mov     [rsp+78h+arg_0], 0
0x18000ce32  mov     edx, 104h; unsigned __int64
0x18000ce37  mov     rcx, rbp; unsigned __int16 *
0x18000ce3a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000ce3f  mov     ebx, eax
0x18000ce41  test    eax, eax
0x18000ce43  js      loc_18000CF66
0x18000ce49  mov     rcx, [rdi+10h]; void *
0x18000ce4d  test    rcx, rcx
0x18000ce50  jz      short loc_18000CE5F
0x18000ce52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ce57  mov     qword ptr [rdi+10h], 0
0x18000ce5f  mov     rbx, [rsp+78h+arg_0]
0x18000ce67  mov     eax, 2
0x18000ce6c  lea     r14, [rbx+1]
0x18000ce70  mul     r14
0x18000ce73  cmovb   rax, r12
0x18000ce77  mov     rcx, rax; unsigned __int64
0x18000ce7a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ce7f  mov     [rdi+10h], rax
0x18000ce83  test    rax, rax
0x18000ce86  jnz     short loc_18000CE92
0x18000ce88  mov     ebx, 8007000Eh
0x18000ce8d  jmp     loc_18000CF66
0x18000ce92  lea     r8, ds:2[rbx*2]; Size
0x18000ce9a  xor     edx, edx; Val
0x18000ce9c  mov     rcx, rax; void *
0x18000ce9f  call    memset_0
0x18000cea4  mov     rcx, [rdi+10h]; unsigned __int16 *
0x18000cea8  mov     r8, rbp; unsigned __int16 *
0x18000ceab  mov     rdx, r14; unsigned __int64
0x18000ceae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ceb3  mov     ebx, eax
0x18000ceb5  test    eax, eax
0x18000ceb7  js      loc_18000CF66
0x18000cebd  xor     r8d, r8d; lpName
0x18000cec0  xor     edx, edx; bInitialOwner
0x18000cec2  xor     ecx, ecx; lpMutexAttributes
0x18000cec4  call    cs:__imp_CreateMutexW
0x18000ceca  mov     [rdi+48h], rax
0x18000cece  cmp     rax, r12
0x18000ced1  jnz     short loc_18000CEDD
0x18000ced3  mov     ebx, 800705AAh
0x18000ced8  jmp     loc_18000CF66
0x18000cedd  xor     r9d, r9d; lpSecurityAttributes
0x18000cee0  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18000cee9  mov     [rsp+78h+dwFlagsAndAttributes], 60000000h; dwFlagsAndAttributes
0x18000cef1  mov     edx, 0C0000000h; dwDesiredAccess
0x18000cef6  mov     rcx, rbp; lpFileName
0x18000cef9  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x18000cf01  lea     r8d, [r9+3]; dwShareMode
0x18000cf05  call    cs:__imp_CreateFileW
0x18000cf0b  mov     [rdi+18h], rax
0x18000cf0f  cmp     rax, r12
0x18000cf12  jz      short loc_18000CF46
0x18000cf14  mov     rcx, rax; hFile
0x18000cf17  call    cs:__imp_GetFileType
0x18000cf1d  cmp     eax, 1
0x18000cf20  jz      short loc_18000CF29
0x18000cf22  mov     ebx, 0C00D001Ch
0x18000cf27  jmp     short loc_18000CF66
0x18000cf29  mov     rcx, [rdi+18h]
0x18000cf2d  xor     r9d, r9d
0x18000cf30  mov     rax, [rsi]
0x18000cf33  mov     r8, rdi
0x18000cf36  xor     edx, edx
0x18000cf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf3d  mov     [rdi+20h], rax
0x18000cf41  cmp     rax, r12
0x18000cf44  jnz     short loc_18000CF90
0x18000cf46  call    cs:__imp_GetLastError
0x18000cf4c  mov     ebx, eax
0x18000cf4e  test    eax, eax
0x18000cf50  jle     short loc_18000CF5B
0x18000cf52  movzx   ebx, ax
0x18000cf55  or      ebx, 80070000h
0x18000cf5b  test    ebx, ebx
0x18000cf5d  jns     short loc_18000CF90
0x18000cf5f  jmp     short loc_18000CF66
0x18000cf61  mov     ebx, 80004001h
0x18000cf66  mov     rcx, [rdi+18h]; hObject
0x18000cf6a  cmp     rcx, r12
0x18000cf6d  jz      short loc_18000CF79
0x18000cf6f  call    cs:__imp_CloseHandle
0x18000cf75  mov     [rdi+18h], r12
0x18000cf79  mov     rcx, [rdi+20h]; hObject
0x18000cf7d  test    rcx, rcx
0x18000cf80  jz      short loc_18000CF90
0x18000cf82  call    cs:__imp_CloseHandle
0x18000cf88  mov     qword ptr [rdi+20h], 0
0x18000cf90  mov     eax, ebx
0x18000cf92  add     rsp, 48h
0x18000cf96  pop     r14
0x18000cf98  pop     r12
0x18000cf9a  pop     rdi
0x18000cf9b  pop     rsi
0x18000cf9c  pop     rbp
0x18000cf9d  pop     rbx
0x18000cf9e  retn
```
