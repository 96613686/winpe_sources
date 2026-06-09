# CSchedule::NewWorkItem(ushort const *,_GUID const &,_GUID const &,IUnknown * *)

- ea: `0x1800069e0`
- end: `0x180006b6a`
- name: `?NewWorkItem@CSchedule@@UEAAJPEBGAEBU_GUID@@1PEAPEAUIUnknown@@@Z`
- size: `394`
- prototype: `int __fastcall(LPCWSTR *this, const unsigned __int16 *, const struct _GUID *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800069e0`
- `0x180006b70`
- `0x1800074c8`
- `0x180010b94`
- `0x180026ce4`
- `0x18002b0d0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b2c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006af6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006af6`

## pseudocode

```c
int __fastcall CSchedule::NewWorkItem(
        LPCWSTR *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  int result; // eax
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
0x1800069e0  mov     [rsp+arg_8], rbx
0x1800069e5  mov     [rsp+arg_10], rbp
0x1800069ea  push    rsi
0x1800069eb  push    rdi
0x1800069ec  push    r14
0x1800069ee  sub     rsp, 40h
0x1800069f2  cmp     qword ptr [rcx+38h], 0
0x1800069f7  mov     rbp, r9
0x1800069fa  mov     r14, r8
0x1800069fd  mov     rdi, rdx
0x180006a00  mov     rbx, rcx
0x180006a03  jnz     short loc_180006A1B
0x180006a05  mov     rcx, [rcx+40h]; lpFileName
0x180006a09  mov     edx, 2; DesiredAccess
0x180006a0e  call    ?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z; FolderAccessCheckOnThreadToken(ushort const *,ulong)
0x180006a13  test    eax, eax
0x180006a15  js      loc_180006B57
0x180006a1b  test    rdi, rdi
0x180006a1e  jz      loc_180006B52
0x180006a24  mov     rsi, [rsp+58h+arg_20]
0x180006a2c  test    rsi, rsi
0x180006a2f  jz      loc_180006B52
0x180006a35  mov     qword ptr [rsi], 0
0x180006a3c  mov     rax, [r14]
0x180006a3f  sub     rax, qword ptr cs:CLSID_CTask.Data1
0x180006a46  jnz     short loc_180006A53
0x180006a48  mov     rax, [r14+8]
0x180006a4c  sub     rax, qword ptr cs:CLSID_CTask.Data4
0x180006a53  test    rax, rax
0x180006a56  jz      short loc_180006A62
0x180006a58  mov     eax, 80040111h
0x180006a5d  jmp     loc_180006B57
0x180006a62  lea     r8, [rsp+58h+Block]; unsigned __int16 **
0x180006a67  mov     [rsp+58h+Block], 0
0x180006a70  mov     rdx, rdi; unsigned __int16 *
0x180006a73  mov     rcx, rbx; this
0x180006a76  call    ?CheckJobName@CSchedule@@AEAAJPEBGPEAPEAG@Z; CSchedule::CheckJobName(ushort const *,ushort * *)
0x180006a7b  test    eax, eax
0x180006a7d  js      loc_180006B57
0x180006a83  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x180006a88  mov     rdi, rax
0x180006a8b  test    rax, rax
0x180006a8e  jnz     short loc_180006AA4
0x180006a90  mov     rcx, [rsp+58h+Block]; Block
0x180006a95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006a9a  mov     eax, 8007000Eh
0x180006a9f  jmp     loc_180006B57
0x180006aa4  mov     rax, [rax]
0x180006aa7  mov     r8, rsi
0x180006aaa  mov     rdx, rbp
0x180006aad  mov     rcx, rdi
0x180006ab0  mov     rax, [rax]
0x180006ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab8  mov     rbp, [rsp+58h+Block]
0x180006abd  mov     ebx, eax
0x180006abf  test    eax, eax
0x180006ac1  js      short loc_180006B37
0x180006ac3  mov     rax, [rdi]
0x180006ac6  mov     rcx, rdi
0x180006ac9  mov     rax, [rax+10h]
0x180006acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad2  mov     r8d, 3; dwShareMode
0x180006ad8  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180006ae1  mov     [rsp+58h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180006ae9  xor     r9d, r9d; lpSecurityAttributes
0x180006aec  xor     edx, edx; dwDesiredAccess
0x180006aee  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x180006af3  mov     rcx, rbp; lpFileName
0x180006af6  call    cs:__imp_CreateFileW
0x180006afc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006b00  jnz     short loc_180006B29
0x180006b02  call    cs:__imp_GetLastError
0x180006b08  mov     ebx, eax
0x180006b0a  cmp     eax, 2
0x180006b0d  jnz     short loc_180006B1A
0x180006b0f  mov     [rdi+98h], rbp
0x180006b16  xor     eax, eax
0x180006b18  jmp     short loc_180006B57
0x180006b1a  test    eax, eax
0x180006b1c  jle     short loc_180006B37
0x180006b1e  movzx   ebx, ax
0x180006b21  or      ebx, 80070000h
0x180006b27  jmp     short loc_180006B37
0x180006b29  mov     rcx, rax; hObject
0x180006b2c  call    cs:__imp_CloseHandle
0x180006b32  mov     ebx, 80070050h
0x180006b37  mov     rcx, rbp; Block
0x180006b3a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006b3f  mov     rcx, rdi; this
0x180006b42  call    ??_GCJob@@QEAAPEAXI@Z; CJob::`scalar deleting destructor'(uint)
0x180006b47  mov     eax, ebx
0x180006b49  mov     qword ptr [rsi], 0
0x180006b50  jmp     short loc_180006B57
0x180006b52  mov     eax, 80070057h
0x180006b57  mov     rbx, [rsp+58h+arg_8]
0x180006b5c  mov     rbp, [rsp+58h+arg_10]
0x180006b61  add     rsp, 40h
0x180006b65  pop     r14
0x180006b67  pop     rdi
0x180006b68  pop     rsi
0x180006b69  retn
```
