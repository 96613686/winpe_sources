# CSchedule::NewWorkItem(ushort const *,_GUID const &,_GUID const &,IUnknown * *)

- ea: `0x180006e10`
- end: `0x180006fb1`
- name: `?NewWorkItem@CSchedule@@UEAAJPEBGAEBU_GUID@@1PEAPEAUIUnknown@@@Z`
- size: `417`
- prototype: `__int64 __usercall@<rax>(CSchedule *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const struct _GUID *@<r8>, const struct _GUID *@<r9>, struct IUnknown **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180006e10`
- `0x180006fb8`
- `0x180007988`
- `0x1800115d0`
- `0x1800284c4`
- `0x18002cc94`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f6c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006f2a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006f2a`

## pseudocode

```c
signed int __fastcall CSchedule::NewWorkItem(
        LPCWSTR *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  signed int result; // eax
  struct IUnknown **v10; // rsi
  __int64 v11; // rax
  struct CJob *v12; // rax
  CJob *v13; // rdi
  int v14; // eax
  WCHAR *v15; // rbp
  unsigned int v16; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v19; // edx
  void *Block; // [rsp+60h] [rbp+8h] BYREF

  if ( this[7] || (result = FolderAccessCheckOnThreadToken(this[8], 2u), result >= 0) )
  {
    if ( a2 && (v10 = a5) != 0 )
    {
      *a5 = 0;
      v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&CLSID_CTask.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&CLSID_CTask.Data1 )
        v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)CLSID_CTask.Data4;
      if ( v11 )
        return -2147221231;
      Block = 0;
      result = CSchedule::CheckJobName((CSchedule *)this, a2, (unsigned __int16 **)&Block);
      if ( result >= 0 )
      {
        v12 = CJob::Create();
        v13 = v12;
        if ( !v12 )
        {
          operator delete(Block);
          return -2147024882;
        }
        v14 = (**(__int64 (__fastcall ***)(struct CJob *, const struct _GUID *, struct IUnknown **))v12)(v12, a4, v10);
        v15 = (WCHAR *)Block;
        v16 = v14;
        if ( v14 >= 0 )
        {
          (*(void (__fastcall **)(CJob *))(*(_QWORD *)v13 + 16LL))(v13);
          FileW = CreateFileW(v15, 0, 3u, 0, 3u, 0, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            v16 = LastError;
            if ( LastError == 2 )
            {
              *((_QWORD *)v13 + 19) = v15;
              return 0;
            }
            if ( LastError > 0 )
              v16 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            CloseHandle(FileW);
            v16 = -2147024816;
          }
        }
        operator delete(v15);
        CJob::`scalar deleting destructor'(v13, v19);
        result = v16;
        *v10 = 0;
      }
    }
    else
    {
      return -2147024809;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006e10  mov     [rsp+arg_8], rbx
0x180006e15  mov     [rsp+arg_10], rbp
0x180006e1a  push    rsi
0x180006e1b  push    rdi
0x180006e1c  push    r14
0x180006e1e  sub     rsp, 40h
0x180006e22  cmp     qword ptr [rcx+38h], 0
0x180006e27  mov     rbp, r9
0x180006e2a  mov     r14, r8
0x180006e2d  mov     rdi, rdx
0x180006e30  mov     rbx, rcx
0x180006e33  jnz     short loc_180006E4B
0x180006e35  mov     rcx, [rcx+40h]; lpFileName
0x180006e39  mov     edx, 2; DesiredAccess
0x180006e3e  call    ?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z; FolderAccessCheckOnThreadToken(ushort const *,ulong)
0x180006e43  test    eax, eax
0x180006e45  js      loc_180006F9D
0x180006e4b  test    rdi, rdi
0x180006e4e  jz      loc_180006F98
0x180006e54  mov     rsi, [rsp+58h+arg_20]
0x180006e5c  test    rsi, rsi
0x180006e5f  jz      loc_180006F98
0x180006e65  mov     qword ptr [rsi], 0
0x180006e6c  mov     rax, [r14]
0x180006e6f  sub     rax, qword ptr cs:CLSID_CTask.Data1
0x180006e76  jnz     short loc_180006E83
0x180006e78  mov     rax, [r14+8]
0x180006e7c  sub     rax, qword ptr cs:CLSID_CTask.Data4
0x180006e83  test    rax, rax
0x180006e86  jz      short loc_180006E92
0x180006e88  mov     eax, 80040111h
0x180006e8d  jmp     loc_180006F9D
0x180006e92  lea     r8, [rsp+58h+Block]; unsigned __int16 **
0x180006e97  mov     [rsp+58h+Block], 0
0x180006ea0  mov     rdx, rdi; unsigned __int16 *
0x180006ea3  mov     rcx, rbx; this
0x180006ea6  call    ?CheckJobName@CSchedule@@AEAAJPEBGPEAPEAG@Z; CSchedule::CheckJobName(ushort const *,ushort * *)
0x180006eab  test    eax, eax
0x180006ead  js      loc_180006F9D
0x180006eb3  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x180006eb8  mov     rdi, rax
0x180006ebb  test    rax, rax
0x180006ebe  jnz     short loc_180006ED4
0x180006ec0  mov     rcx, [rsp+58h+Block]; Block
0x180006ec5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006eca  mov     eax, 8007000Eh
0x180006ecf  jmp     loc_180006F9D
0x180006ed4  mov     rax, [rax]
0x180006ed7  mov     r8, rsi
0x180006eda  mov     rdx, rbp
0x180006edd  mov     rcx, rdi
0x180006ee0  mov     rax, [rax]
0x180006ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ee8  mov     rbp, [rsp+58h+Block]
0x180006eed  mov     ebx, eax
0x180006eef  test    eax, eax
0x180006ef1  js      loc_180006F7D
0x180006ef7  mov     rax, [rdi]
0x180006efa  mov     rcx, rdi
0x180006efd  mov     rax, [rax+10h]
0x180006f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f06  mov     r8d, 3; dwShareMode
0x180006f0c  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180006f15  mov     [rsp+58h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180006f1d  xor     r9d, r9d; lpSecurityAttributes
0x180006f20  xor     edx, edx; dwDesiredAccess
0x180006f22  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x180006f27  mov     rcx, rbp; lpFileName
0x180006f2a  call    cs:__imp_CreateFileW
0x180006f31  nop     dword ptr [rax+rax+00h]
0x180006f36  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006f3a  jnz     short loc_180006F69
0x180006f3c  call    cs:__imp_GetLastError
0x180006f43  nop     dword ptr [rax+rax+00h]
0x180006f48  mov     ebx, eax
0x180006f4a  cmp     eax, 2
0x180006f4d  jnz     short loc_180006F5A
0x180006f4f  mov     [rdi+98h], rbp
0x180006f56  xor     eax, eax
0x180006f58  jmp     short loc_180006F9D
0x180006f5a  test    eax, eax
0x180006f5c  jle     short loc_180006F7D
0x180006f5e  movzx   ebx, ax
0x180006f61  or      ebx, 80070000h
0x180006f67  jmp     short loc_180006F7D
0x180006f69  mov     rcx, rax; hObject
0x180006f6c  call    cs:__imp_CloseHandle
0x180006f73  nop     dword ptr [rax+rax+00h]
0x180006f78  mov     ebx, 80070050h
0x180006f7d  mov     rcx, rbp; Block
0x180006f80  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006f85  mov     rcx, rdi; this
0x180006f88  call    ??_GCJob@@QEAAPEAXI@Z; CJob::`scalar deleting destructor'(uint)
0x180006f8d  mov     eax, ebx
0x180006f8f  mov     qword ptr [rsi], 0
0x180006f96  jmp     short loc_180006F9D
0x180006f98  mov     eax, 80070057h
0x180006f9d  mov     rbx, [rsp+58h+arg_8]
0x180006fa2  mov     rbp, [rsp+58h+arg_10]
0x180006fa7  add     rsp, 40h
0x180006fab  pop     r14
0x180006fad  pop     rdi
0x180006fae  pop     rsi
0x180006faf  retn
```
