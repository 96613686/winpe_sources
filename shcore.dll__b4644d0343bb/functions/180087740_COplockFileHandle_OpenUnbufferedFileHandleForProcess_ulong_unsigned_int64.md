# COplockFileHandle::OpenUnbufferedFileHandleForProcess(ulong,unsigned __int64 *)

- ea: `0x180087740`
- end: `0x180087911`
- name: `?OpenUnbufferedFileHandleForProcess@COplockFileHandle@@UEAAJKPEA_K@Z`
- size: `465`
- prototype: `int(COplockFileHandle *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180087740`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180087864`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180087864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800878db`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008788f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008788f`
- `ntdll!RtlInitUnicodeString` at `0x1800877bd`
- `ntdll!RtlInitUnicodeString` at `0x1800877bd`
- `ntdll!NtCreateFile` at `0x180087834`
- `ntdll!NtCreateFile` at `0x180087834`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008784a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008784a`

## pseudocode

```c
__int64 __fastcall COplockFileHandle::OpenUnbufferedFileHandleForProcess(COplockFileHandle *this, DWORD a2, HANDLE *a3)
{
  char *v3; // r14
  __int64 v4; // rax
  int v7; // edi
  NTSTATUS v8; // eax
  HANDLE v9; // rsi
  void *v10; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v13; // eax
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+E0h] [rbp+67h] BYREF
  void *v19; // [rsp+F0h] [rbp+77h] BYREF
  HANDLE TargetHandle; // [rsp+F8h] [rbp+7Fh] BYREF

  v3 = (char *)this - 136;
  *a3 = 0;
  v4 = *((_QWORD *)this - 17);
  v19 = 0;
  v7 = (*(__int64 (__fastcall **)(char *, void **))(v4 + 24))((char *)this - 136, &v19);
  if ( v7 >= 0 )
  {
    FileHandle = (void *)-1LL;
    IoStatusBlock = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, &SourceString);
    ObjectAttributes.RootDirectory = v19;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v8 = NtCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x48u, 0, 0);
    if ( v8 < 0 )
    {
      v7 = v8 | 0x10000000;
    }
    else
    {
      v9 = OpenProcess(0x40u, 0, a2);
      if ( v9 )
      {
        v10 = FileHandle;
        TargetHandle = 0;
        CurrentProcess = GetCurrentProcess();
        if ( DuplicateHandle(CurrentProcess, v10, v9, &TargetHandle, 0x120089u, 1, 0) )
        {
          *a3 = TargetHandle;
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
        }
        CloseHandle(v9);
      }
      else
      {
        v13 = GetLastError();
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
      }
      CloseHandle(FileHandle);
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 32LL))(v3);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180087740  mov     [rsp-8+arg_8], rbx
0x180087745  push    rbp
0x180087746  push    rsi
0x180087747  push    rdi
0x180087748  push    r14
0x18008774a  push    r15
0x18008774c  lea     rbp, [rsp-37h]
0x180087751  sub     rsp, 0B0h
0x180087758  lea     r14, [rcx-88h]
0x18008775f  mov     qword ptr [r8], 0
0x180087766  mov     rax, [r14]
0x180087769  mov     ebx, edx
0x18008776b  lea     rdx, [rbp+57h+arg_10]
0x18008776f  mov     [rbp+57h+arg_10], 0
0x180087777  mov     rcx, r14
0x18008777a  mov     r15, r8
0x18008777d  mov     rax, [rax+18h]
0x180087781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087786  mov     edi, eax
0x180087788  test    eax, eax
0x18008778a  js      loc_1800878F8
0x180087790  xorps   xmm1, xmm1
0x180087793  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18008779b  xorps   xmm0, xmm0
0x18008779e  lea     rdx, SourceString; SourceString
0x1800877a5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800877a9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800877ad  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800877b1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800877b5  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800877b9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800877bd  call    cs:__imp_RtlInitUnicodeString
0x1800877c3  mov     rax, [rbp+57h+arg_10]
0x1800877c7  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800877cb  mov     [rsp+0D0h+EaLength], 0; EaLength
0x1800877d3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800877d7  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x1800877e0  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800877e4  mov     [rsp+0D0h+CreateOptions], 48h ; 'H'; CreateOptions
0x1800877ec  xorps   xmm0, xmm0
0x1800877ef  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x1800877f7  mov     edx, 120089h; DesiredAccess
0x1800877fc  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180087800  lea     rax, [rbp+57h+DestinationString]
0x180087804  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x18008780c  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x180087814  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180087818  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x180087821  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180087828  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18008782f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180087834  call    cs:__imp_NtCreateFile
0x18008783a  test    eax, eax
0x18008783c  js      loc_1800878E3
0x180087842  xor     edx, edx; bInheritHandle
0x180087844  mov     r8d, ebx; dwProcessId
0x180087847  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18008784a  call    cs:__imp_OpenProcess
0x180087850  mov     rsi, rax
0x180087853  test    rax, rax
0x180087856  jz      short loc_1800878C2
0x180087858  mov     rbx, [rbp+57h+FileHandle]
0x18008785c  mov     [rbp+57h+TargetHandle], 0
0x180087864  call    cs:__imp_GetCurrentProcess
0x18008786a  mov     [rsp+0D0h+ShareAccess], 0; dwOptions
0x180087872  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x180087876  mov     rcx, rax; hSourceProcessHandle
0x180087879  mov     [rsp+0D0h+FileAttributes], 1; bInheritHandle
0x180087881  mov     r8, rsi; hTargetProcessHandle
0x180087884  mov     dword ptr [rsp+0D0h+AllocationSize], 120089h; dwDesiredAccess
0x18008788c  mov     rdx, rbx; hSourceHandle
0x18008788f  call    cs:__imp_DuplicateHandle
0x180087895  test    eax, eax
0x180087897  jz      short loc_1800878A2
0x180087899  mov     rax, [rbp+57h+TargetHandle]
0x18008789d  mov     [r15], rax
0x1800878a0  jmp     short loc_1800878B7
0x1800878a2  call    cs:__imp_GetLastError
0x1800878a8  mov     edi, eax
0x1800878aa  test    eax, eax
0x1800878ac  jle     short loc_1800878B7
0x1800878ae  movzx   edi, ax
0x1800878b1  or      edi, 80070000h
0x1800878b7  mov     rcx, rsi; hObject
0x1800878ba  call    cs:__imp_CloseHandle
0x1800878c0  jmp     short loc_1800878D7
0x1800878c2  call    cs:__imp_GetLastError
0x1800878c8  mov     edi, eax
0x1800878ca  test    eax, eax
0x1800878cc  jle     short loc_1800878D7
0x1800878ce  movzx   edi, ax
0x1800878d1  or      edi, 80070000h
0x1800878d7  mov     rcx, [rbp+57h+FileHandle]; hObject
0x1800878db  call    cs:__imp_CloseHandle
0x1800878e1  jmp     short loc_1800878E9
0x1800878e3  mov     edi, eax
0x1800878e5  bts     edi, 1Ch
0x1800878e9  mov     rax, [r14]
0x1800878ec  mov     rcx, r14
0x1800878ef  mov     rax, [rax+20h]
0x1800878f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800878f8  mov     rbx, [rsp+0D0h+arg_8]
0x180087900  mov     eax, edi
0x180087902  add     rsp, 0B0h
0x180087909  pop     r15
0x18008790b  pop     r14
0x18008790d  pop     rdi
0x18008790e  pop     rsi
0x18008790f  pop     rbp
0x180087910  retn
```
