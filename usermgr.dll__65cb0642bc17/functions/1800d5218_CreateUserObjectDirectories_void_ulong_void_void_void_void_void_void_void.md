# CreateUserObjectDirectories(void *,ulong,void * *,void * *,void * *,void * *,void * *,void * *,void * *)

- ea: `0x1800d5218`
- end: `0x1800d5a87`
- name: `?CreateUserObjectDirectories@@YAJPEAXKPEAPEAX111111@Z`
- size: `2159`
- prototype: `__int64 __fastcall(void *, unsigned int, void **, void **, PHANDLE, void **, void **, void **, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d4e98`

## callees

- `0x18006f1c9`
- `0x1800d4b2c`
- `0x1800d5020`
- `0x1800d5218`
- `0x1800d5a90`
- `0x1800d5ba4`
- `0x1800d5c70`
- `0x1800de450`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x1800d53e4`
- `ntdll!NtQuerySecurityObject` at `0x1800d55b1`
- `ntdll!NtQuerySecurityObject` at `0x1800d566b`
- `ntdll!NtQuerySecurityObject` at `0x1800d5710`
- `ntdll!NtQuerySecurityObject` at `0x1800d53e4`
- `ntdll!NtQuerySecurityObject` at `0x1800d55b1`
- `ntdll!NtQuerySecurityObject` at `0x1800d566b`
- `ntdll!NtQuerySecurityObject` at `0x1800d5710`
- `ntdll!NtCreateFile` at `0x1800d5a5c`
- `ntdll!NtCreateFile` at `0x1800d5a5c`
- `ntdll!NtOpenDirectoryObject` at `0x1800d57e3`
- `ntdll!NtOpenDirectoryObject` at `0x1800d57e3`
- `ntdll!NtClose` at `0x1800d54a8`
- `ntdll!NtClose` at `0x1800d54b8`
- `ntdll!NtClose` at `0x1800d54c8`
- `ntdll!NtClose` at `0x1800d54d7`
- `ntdll!NtClose` at `0x1800d54ee`
- `ntdll!NtClose` at `0x1800d54fd`
- `ntdll!NtClose` at `0x1800d550c`
- `ntdll!NtClose` at `0x1800d5522`
- `ntdll!NtClose` at `0x1800d5537`
- `ntdll!NtClose` at `0x1800d554c`
- `ntdll!NtClose` at `0x1800d5562`
- `ntdll!NtClose` at `0x1800d54a8`
- `ntdll!NtClose` at `0x1800d54b8`
- `ntdll!NtClose` at `0x1800d54c8`
- `ntdll!NtClose` at `0x1800d54d7`
- `ntdll!NtClose` at `0x1800d54ee`
- `ntdll!NtClose` at `0x1800d54fd`
- `ntdll!NtClose` at `0x1800d550c`
- `ntdll!NtClose` at `0x1800d5522`
- `ntdll!NtClose` at `0x1800d5537`
- `ntdll!NtClose` at `0x1800d554c`
- `ntdll!NtClose` at `0x1800d5562`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800d5386`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800d5386`
- `ntdll!NtCreateDirectoryObjectEx` at `0x1800d5626`
- `ntdll!NtCreateDirectoryObjectEx` at `0x1800d578b`
- `ntdll!NtCreateDirectoryObjectEx` at `0x1800d5876`
- `ntdll!NtCreateDirectoryObjectEx` at `0x1800d5626`
- `ntdll!NtCreateDirectoryObjectEx` at `0x1800d578b`
- `ntdll!NtCreateDirectoryObjectEx` at `0x1800d5876`
- `ntdll!RtlAllocateHeap` at `0x1800d5413`
- `ntdll!RtlAllocateHeap` at `0x1800d569a`
- `ntdll!RtlAllocateHeap` at `0x1800d5413`
- `ntdll!RtlAllocateHeap` at `0x1800d569a`
- `ntdll!RtlFreeHeap` at `0x1800d544d`
- `ntdll!RtlFreeHeap` at `0x1800d5473`
- `ntdll!RtlFreeHeap` at `0x1800d5499`
- `ntdll!RtlFreeHeap` at `0x1800d56c4`
- `ntdll!RtlFreeHeap` at `0x1800d56e1`
- `ntdll!RtlFreeHeap` at `0x1800d544d`
- `ntdll!RtlFreeHeap` at `0x1800d5473`
- `ntdll!RtlFreeHeap` at `0x1800d5499`
- `ntdll!RtlFreeHeap` at `0x1800d56c4`
- `ntdll!RtlFreeHeap` at `0x1800d56e1`
- `ntdll!RtlInitUnicodeString` at `0x1800d5827`
- `ntdll!RtlInitUnicodeString` at `0x1800d58c7`
- `ntdll!RtlInitUnicodeString` at `0x1800d5908`
- `ntdll!RtlInitUnicodeString` at `0x1800d5982`
- `ntdll!RtlInitUnicodeString` at `0x1800d5827`
- `ntdll!RtlInitUnicodeString` at `0x1800d58c7`
- `ntdll!RtlInitUnicodeString` at `0x1800d5908`
- `ntdll!RtlInitUnicodeString` at `0x1800d5982`
- `ntdll!RtlGetAce` at `0x1800d5a08`
- `ntdll!RtlGetAce` at `0x1800d5a08`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CreateUserObjectDirectories(
        void *a1,
        unsigned int a2,
        void **a3,
        void **a4,
        PHANDLE a5,
        void **a6,
        void **a7,
        void **a8,
        void **a9)
{
  HANDLE *v9; // r14
  HANDLE *v11; // rsi
  NTSTATUS v14; // ebx
  unsigned int v15; // r9d
  PVOID Heap; // r14
  HANDLE *v17; // r15
  PVOID v19; // rsi
  unsigned int v20; // r9d
  struct _ACL *v21; // rdi
  int v22; // ebx
  ULONG v23; // edx
  int *v24; // rdx
  int v25; // r8d
  int v26; // ecx
  PVOID Ace; // [rsp+60h] [rbp-A0h] BYREF
  ULONG Length; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v30; // [rsp+78h] [rbp-88h] BYREF
  HANDLE v31; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES v32; // [rsp+88h] [rbp-78h] BYREF
  PHANDLE SymbolicLinkHandle; // [rsp+B8h] [rbp-48h]
  HANDLE FileHandle; // [rsp+C0h] [rbp-40h] BYREF
  PHANDLE v35; // [rsp+C8h] [rbp-38h]
  HANDLE v36; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE v37; // [rsp+D8h] [rbp-28h] BYREF
  void **v38; // [rsp+E0h] [rbp-20h]
  struct _UNICODE_STRING UnicodeString; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD v40[3]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v41; // [rsp+104h] [rbp+4h]
  __int64 v42; // [rsp+110h] [rbp+10h] BYREF
  void **v43; // [rsp+118h] [rbp+18h]
  _OWORD v44[2]; // [rsp+120h] [rbp+20h] BYREF
  PVOID P; // [rsp+140h] [rbp+40h]
  struct _UNICODE_STRING DestinationString; // [rsp+148h] [rbp+48h] BYREF
  struct _UNICODE_STRING v47; // [rsp+158h] [rbp+58h] BYREF
  struct _UNICODE_STRING v48; // [rsp+168h] [rbp+68h] BYREF
  struct _UNICODE_STRING v49; // [rsp+178h] [rbp+78h] BYREF
  _OWORD v50[2]; // [rsp+188h] [rbp+88h] BYREF
  PVOID v51; // [rsp+1A8h] [rbp+A8h]
  _OWORD v52[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  PVOID v53; // [rsp+1D0h] [rbp+D0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1D8h] [rbp+D8h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+208h] [rbp+108h] BYREF
  unsigned __int16 v56[256]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v57[256]; // [rsp+420h] [rbp+320h] BYREF
  WCHAR SourceString[256]; // [rsp+620h] [rbp+520h] BYREF
  WCHAR v59[256]; // [rsp+820h] [rbp+720h] BYREF
  WCHAR v60[256]; // [rsp+A20h] [rbp+920h] BYREF

  v9 = a6;
  v11 = a7;
  Ace = a8;
  v38 = a4;
  Length = 0;
  v36 = 0;
  Handle = 0;
  v43 = a3;
  SymbolicLinkHandle = a6;
  v35 = a7;
  memset(&v32, 0, sizeof(v32));
  memset_0(v56, 0, sizeof(v56));
  v31 = 0;
  P = 0;
  v30 = 0;
  v48 = 0;
  memset(v44, 0, sizeof(v44));
  memset_0(v57, 0, sizeof(v57));
  v40[0] = 4;
  *a3 = 0;
  v42 = 0;
  FileHandle = 0;
  v51 = 0;
  v53 = 0;
  v37 = 0;
  v47 = 0;
  v40[1] = 1048578;
  *v38 = 0;
  *a6 = 0;
  *a5 = 0;
  *a7 = 0;
  *a9 = 0;
  memset(v50, 0, sizeof(v50));
  v40[2] = 8;
  v41 = 1048580;
  DestinationString = 0;
  memset(v52, 0, sizeof(v52));
  v49 = 0;
  IoStatusBlock = 0;
  UnicodeString = 0;
  v14 = RtlConvertSidToUnicodeString(&UnicodeString, a1, 1u);
  if ( v14 < 0 )
    goto LABEL_8;
  v14 = OpenSessionBaseObjectDirectory(a2, &v36);
  if ( v14 < 0 )
    goto LABEL_8;
  v14 = OpenUserParentDirectory(0, a2, v56, v15, &Handle);
  if ( v14 < 0 )
    goto LABEL_8;
  v14 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length);
  if ( (int)(v14 + 0x80000000) >= 0 && v14 != -1073741789 )
    goto LABEL_8;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Length);
  if ( !Heap )
  {
    v9 = SymbolicLinkHandle;
    v14 = -1073741801;
LABEL_8:
    v17 = (HANDLE *)Ace;
    goto LABEL_9;
  }
  v19 = 0;
  v14 = NtQuerySecurityObject(Handle, 4u, Heap, Length, &Length);
  if ( v14 >= 0 )
  {
    v14 = BuildPrivateDirectorySecurityDescriptor(a2, Heap, a1, 0, v44);
    if ( v14 >= 0 )
    {
      v32.RootDirectory = Handle;
      v32.Length = 48;
      v32.ObjectName = &UnicodeString;
      v32.SecurityDescriptor = v44;
      v32.Attributes = 128;
      v32.SecurityQualityOfService = 0;
      v14 = NtCreateDirectoryObjectEx(&v31, 15, &v32, v36, 1);
      if ( v14 >= 0 )
      {
        v14 = OpenUserParentDirectory(1, a2, v57, v20, &v30);
        if ( v14 >= 0 )
        {
          v14 = NtQuerySecurityObject(v30, 4u, 0, 0, &Length);
          if ( (int)(v14 + 0x80000000) < 0 || v14 == -1073741789 )
          {
            v19 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Length);
            if ( v19 )
            {
              v14 = NtQuerySecurityObject(v30, 4u, v19, Length, &Length);
              if ( v14 >= 0 )
              {
                v14 = BuildPrivateDirectorySecurityDescriptor(a2, v19, a1, 0, v50);
                if ( v14 >= 0 )
                {
                  v32.RootDirectory = v30;
                  v32.Length = 48;
                  v32.Attributes = 128;
                  v32.ObjectName = &UnicodeString;
                  v32.SecurityDescriptor = v50;
                  v32.SecurityQualityOfService = 0;
                  v14 = NtCreateDirectoryObjectEx(&v42, 15, &v32, 0, 1);
                  if ( v14 >= 0 )
                  {
                    memset(&ObjectAttributes.Attributes, 0, 24);
                    FileHandle = 0;
                    ObjectAttributes.RootDirectory = 0;
                    *(_QWORD *)&ObjectAttributes.Length = 48;
                    ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1800FA9B0;
                    v14 = NtOpenDirectoryObject(&FileHandle, 3u, &ObjectAttributes);
                    if ( v14 >= 0 )
                    {
                      v14 = BuildPrivateDirectorySecurityDescriptor(a2, Heap, a1, 7u, v52);
                      if ( v14 >= 0 )
                      {
                        RtlInitUnicodeString(&DestinationString, L"RPC Control");
                        v32.RootDirectory = v31;
                        v32.Length = 48;
                        v32.ObjectName = &DestinationString;
                        v32.SecurityDescriptor = v52;
                        v32.Attributes = 128;
                        v32.SecurityQualityOfService = 0;
                        v14 = NtCreateDirectoryObjectEx(&v37, 15, &v32, FileHandle, 1);
                        if ( v14 >= 0 )
                        {
                          v14 = RtlStringCchPrintfW(SourceString, 0x100u, L"%ws\\%ws", v56, UnicodeString.Buffer);
                          if ( v14 >= 0 )
                          {
                            RtlInitUnicodeString(&v48, SourceString);
                            v14 = RtlStringCchPrintfW(v59, 0x100u, L"%ws\\%ws", v57, UnicodeString.Buffer);
                            if ( v14 >= 0 )
                            {
                              RtlInitUnicodeString(&v47, v59);
                              v17 = (HANDLE *)Ace;
                              v14 = CreateUserDirectorySymbolicLinks(
                                      v31,
                                      &v48,
                                      &v47,
                                      v44,
                                      a5,
                                      SymbolicLinkHandle,
                                      v35,
                                      (PHANDLE)Ace);
                              if ( v14 >= 0 )
                              {
                                v14 = RtlStringCchPrintfW(v60, 0x100u, L"\\Device\\NamedPipe%ws", SourceString);
                                if ( v14 >= 0 )
                                {
                                  RtlInitUnicodeString(&v49, v60);
                                  v32.Length = 48;
                                  v21 = (struct _ACL *)P;
                                  v22 = 0;
                                  v32.ObjectName = &v49;
                                  v23 = 0;
                                  v32.RootDirectory = 0;
                                  v32.SecurityDescriptor = v44;
                                  v32.Attributes = 66;
                                  v32.SecurityQualityOfService = 0;
                                  Ace = 0;
                                  while ( RtlGetAce(v21, v23, &Ace) >= 0 )
                                  {
                                    v24 = v40;
                                    v25 = *((_DWORD *)Ace + 1);
                                    *((_WORD *)Ace + 2) = 0;
                                    v26 = 4;
                                    do
                                    {
                                      if ( v26 == (unsigned __int16)(v26 & v25) )
                                        *((_DWORD *)Ace + 1) |= v24[1];
                                      v24 += 2;
                                      v26 = *v24;
                                    }
                                    while ( *v24 );
                                    v23 = ++v22;
                                  }
                                  v14 = NtCreateFile(a9, 0x1F0006u, &v32, &IoStatusBlock, 0, 0x80u, 3u, 3u, 1u, 0, 0);
                                  if ( v14 >= 0 )
                                  {
                                    *v43 = v31;
                                    *v38 = v37;
                                  }
                                }
                              }
                              goto LABEL_48;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            else
            {
              v14 = -1073741801;
            }
          }
        }
      }
    }
  }
  v17 = (HANDLE *)Ace;
LABEL_48:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v19 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
  v11 = v35;
  v9 = SymbolicLinkHandle;
LABEL_9:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v51 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v51);
  if ( v53 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v53);
  if ( v36 )
    NtClose(v36);
  if ( Handle )
    NtClose(Handle);
  if ( v30 )
    NtClose(v30);
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v14 < 0 )
  {
    if ( v31 )
      NtClose(v31);
    if ( v37 )
      NtClose(v37);
    if ( *a5 )
    {
      NtClose(*a5);
      *a5 = 0;
    }
    if ( *v9 )
    {
      NtClose(*v9);
      *v9 = 0;
    }
    if ( *v11 )
    {
      NtClose(*v11);
      *v11 = 0;
    }
    if ( *v17 )
    {
      NtClose(*v17);
      *v17 = 0;
    }
    if ( *a9 )
    {
      NtClose(*a9);
      *a9 = 0;
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800d5218  push    rbp
0x1800d521a  push    rbx
0x1800d521b  push    rsi
0x1800d521c  push    rdi
0x1800d521d  push    r12
0x1800d521f  push    r13
0x1800d5221  push    r14
0x1800d5223  push    r15
0x1800d5225  lea     rbp, [rsp-0B38h]
0x1800d522d  sub     rsp, 0C38h
0x1800d5234  mov     rax, cs:__security_cookie
0x1800d523b  xor     rax, rsp
0x1800d523e  mov     [rbp+0B70h+var_50], rax
0x1800d5245  mov     rax, [rbp+0B70h+arg_38]
0x1800d524c  xorps   xmm0, xmm0
0x1800d524f  mov     r14, [rbp+0B70h+arg_28]
0x1800d5256  mov     rbx, r8
0x1800d5259  mov     rsi, [rbp+0B70h+arg_30]
0x1800d5260  mov     edi, edx
0x1800d5262  mov     r13, [rbp+0B70h+arg_20]
0x1800d5269  mov     r15, rcx
0x1800d526c  mov     r12, [rbp+0B70h+arg_40]
0x1800d5273  lea     rcx, [rbp+0B70h+var_A50]; void *
0x1800d527a  mov     [rsp+0C70h+Ace], rax
0x1800d527f  xor     edx, edx; Val
0x1800d5281  xor     eax, eax
0x1800d5283  mov     [rbp+0B70h+var_B90], r9
0x1800d5287  mov     r8d, 200h; Size
0x1800d528d  mov     [rsp+0C70h+Length], eax
0x1800d5291  mov     [rbp+0B70h+var_BA0], rax
0x1800d5295  mov     [rsp+0C70h+Handle], rax
0x1800d529a  mov     [rbp+0B70h+var_B58], rbx
0x1800d529e  mov     [rbp+0B70h+SymbolicLinkHandle], r14
0x1800d52a2  mov     [rbp+0B70h+var_BA8], rsi
0x1800d52a6  movups  xmmword ptr [rbp+0B70h+var_BE8.Length], xmm0
0x1800d52aa  movups  xmmword ptr [rbp+0B70h+var_BE8.ObjectName], xmm0
0x1800d52ae  movups  xmmword ptr [rbp+0B70h+var_BE8.SecurityDescriptor], xmm0
0x1800d52b2  call    memset_0
0x1800d52b7  xorps   xmm1, xmm1
0x1800d52ba  mov     [rbp+0B70h+var_BF0], 0
0x1800d52c2  xor     eax, eax
0x1800d52c4  lea     rcx, [rbp+0B70h+var_850]; void *
0x1800d52cb  xorps   xmm0, xmm0
0x1800d52ce  mov     [rbp+0B70h+P], rax
0x1800d52d2  xor     edx, edx; Val
0x1800d52d4  mov     [rsp+0C70h+var_BF8], rax
0x1800d52d9  mov     r8d, 200h; Size
0x1800d52df  movups  xmmword ptr [rbp+0B70h+var_B08.Length], xmm0
0x1800d52e3  movups  [rbp+0B70h+var_B50], xmm1
0x1800d52e7  movups  [rbp+0B70h+var_B40], xmm1
0x1800d52eb  call    memset_0
0x1800d52f0  xor     ecx, ecx
0x1800d52f2  mov     [rbp+0B70h+var_B78], 4
0x1800d52f9  mov     [rbx], rcx
0x1800d52fc  xorps   xmm1, xmm1
0x1800d52ff  xorps   xmm0, xmm0
0x1800d5302  mov     [rbp+0B70h+var_B60], rcx
0x1800d5306  xor     eax, eax
0x1800d5308  mov     [rbp+0B70h+FileHandle], rcx
0x1800d530c  mov     [rbp+0B70h+var_AC8], rax
0x1800d5313  mov     r8b, 1; AllocateDestinationString
0x1800d5316  mov     [rbp+0B70h+var_AA0], rax
0x1800d531d  mov     rdx, r15; Sid
0x1800d5320  mov     rax, [rbp+0B70h+var_B90]
0x1800d5324  mov     [rbp+0B70h+var_B98], rcx
0x1800d5328  movups  xmmword ptr [rbp+0B70h+var_B18.Length], xmm0
0x1800d532c  mov     [rbp+0B70h+var_B74], 100002h
0x1800d5333  mov     [rax], rcx
0x1800d5336  mov     [r14], rcx
0x1800d5339  mov     [r13+0], rcx
0x1800d533d  mov     [rsi], rcx
0x1800d5340  mov     [r12], rcx
0x1800d5344  lea     rcx, [rbp+0B70h+UnicodeString]; UnicodeString
0x1800d5348  movups  [rbp+0B70h+var_AE8], xmm1
0x1800d534f  mov     [rbp+0B70h+var_B70], 8
0x1800d5356  movups  [rbp+0B70h+var_AD8], xmm1
0x1800d535d  mov     [rbp+0B70h+var_B6C], 100004h
0x1800d5365  movups  xmmword ptr [rbp+0B70h+DestinationString.Length], xmm0
0x1800d5369  movups  [rbp+0B70h+var_AC0], xmm1
0x1800d5370  movups  [rbp+0B70h+var_AB0], xmm1
0x1800d5377  movups  xmmword ptr [rbp+0B70h+var_AF8.Length], xmm0
0x1800d537b  movups  xmmword ptr [rbp+0B70h+IoStatusBlock], xmm0
0x1800d5382  movups  xmmword ptr [rbp+0B70h+UnicodeString.Length], xmm1
0x1800d5386  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800d538c  mov     ebx, eax
0x1800d538e  test    eax, eax
0x1800d5390  js      loc_1800D542E
0x1800d5396  lea     rdx, [rbp+0B70h+var_BA0]; void **
0x1800d539a  mov     ecx, edi; unsigned int
0x1800d539c  call    ?OpenSessionBaseObjectDirectory@@YAJKPEAPEAX@Z; OpenSessionBaseObjectDirectory(ulong,void * *)
0x1800d53a1  mov     ebx, eax
0x1800d53a3  test    eax, eax
0x1800d53a5  js      loc_1800D542E
0x1800d53ab  lea     rax, [rsp+0C70h+Handle]
0x1800d53b0  mov     edx, edi; unsigned int
0x1800d53b2  lea     r8, [rbp+0B70h+var_A50]; unsigned __int16 *
0x1800d53b9  mov     [rsp+0C70h+LengthNeeded], rax; void **
0x1800d53be  xor     ecx, ecx; int
0x1800d53c0  call    ?OpenUserParentDirectory@@YAJHKPEAGKPEAPEAX@Z; OpenUserParentDirectory(int,ulong,ushort *,ulong,void * *)
0x1800d53c5  mov     ebx, eax
0x1800d53c7  test    eax, eax
0x1800d53c9  js      short loc_1800D542E
0x1800d53cb  mov     rcx, [rsp+0C70h+Handle]; Handle
0x1800d53d0  lea     rax, [rsp+0C70h+Length]
0x1800d53d5  xor     r9d, r9d; Length
0x1800d53d8  mov     [rsp+0C70h+LengthNeeded], rax; LengthNeeded
0x1800d53dd  xor     r8d, r8d; SecurityDescriptor
0x1800d53e0  lea     edx, [r9+4]; SecurityInformation
0x1800d53e4  call    cs:__imp_NtQuerySecurityObject
0x1800d53ea  mov     ecx, 80000000h
0x1800d53ef  mov     ebx, eax
0x1800d53f1  add     eax, ecx
0x1800d53f3  test    ecx, eax
0x1800d53f5  jnz     short loc_1800D53FF
0x1800d53f7  cmp     ebx, 0C0000023h
0x1800d53fd  jnz     short loc_1800D542E
0x1800d53ff  mov     rcx, gs:60h
0x1800d5408  xor     edx, edx; Flags
0x1800d540a  mov     r8d, [rsp+0C70h+Length]; Size
0x1800d540f  mov     rcx, [rcx+30h]; HeapHandle
0x1800d5413  call    cs:__imp_RtlAllocateHeap
0x1800d5419  mov     r14, rax
0x1800d541c  test    rax, rax
0x1800d541f  jnz     loc_1800D5595
0x1800d5425  mov     r14, [rbp+0B70h+SymbolicLinkHandle]
0x1800d5429  mov     ebx, 0C0000017h
0x1800d542e  mov     r15, [rsp+0C70h+Ace]
0x1800d5433  cmp     [rbp+0B70h+P], 0
0x1800d5438  jz      short loc_1800D5453
0x1800d543a  mov     rcx, gs:60h
0x1800d5443  xor     edx, edx; Flags
0x1800d5445  mov     r8, [rbp+0B70h+P]; P
0x1800d5449  mov     rcx, [rcx+30h]; HeapHandle
0x1800d544d  call    cs:__imp_RtlFreeHeap
0x1800d5453  cmp     [rbp+0B70h+var_AC8], 0
0x1800d545b  jz      short loc_1800D5479
0x1800d545d  mov     rcx, gs:60h
0x1800d5466  xor     edx, edx; Flags
0x1800d5468  mov     r8, [rbp+0B70h+var_AC8]; P
0x1800d546f  mov     rcx, [rcx+30h]; HeapHandle
0x1800d5473  call    cs:__imp_RtlFreeHeap
0x1800d5479  cmp     [rbp+0B70h+var_AA0], 0
0x1800d5481  jz      short loc_1800D549F
0x1800d5483  mov     rcx, gs:60h
0x1800d548c  xor     edx, edx; Flags
0x1800d548e  mov     r8, [rbp+0B70h+var_AA0]; P
0x1800d5495  mov     rcx, [rcx+30h]; HeapHandle
0x1800d5499  call    cs:__imp_RtlFreeHeap
0x1800d549f  mov     rcx, [rbp+0B70h+var_BA0]; Handle
0x1800d54a3  test    rcx, rcx
0x1800d54a6  jz      short loc_1800D54AE
0x1800d54a8  call    cs:__imp_NtClose
0x1800d54ae  mov     rcx, [rsp+0C70h+Handle]; Handle
0x1800d54b3  test    rcx, rcx
0x1800d54b6  jz      short loc_1800D54BE
0x1800d54b8  call    cs:__imp_NtClose
0x1800d54be  mov     rcx, [rsp+0C70h+var_BF8]; Handle
0x1800d54c3  test    rcx, rcx
0x1800d54c6  jz      short loc_1800D54CE
0x1800d54c8  call    cs:__imp_NtClose
0x1800d54ce  mov     rcx, [rbp+0B70h+FileHandle]; Handle
0x1800d54d2  test    rcx, rcx
0x1800d54d5  jz      short loc_1800D54DD
0x1800d54d7  call    cs:__imp_NtClose
0x1800d54dd  test    ebx, ebx
0x1800d54df  jns     loc_1800D5570
0x1800d54e5  mov     rcx, [rbp+0B70h+var_BF0]; Handle
0x1800d54e9  test    rcx, rcx
0x1800d54ec  jz      short loc_1800D54F4
0x1800d54ee  call    cs:__imp_NtClose
0x1800d54f4  mov     rcx, [rbp+0B70h+var_B98]; Handle
0x1800d54f8  test    rcx, rcx
0x1800d54fb  jz      short loc_1800D5503
0x1800d54fd  call    cs:__imp_NtClose
0x1800d5503  mov     rcx, [r13+0]; Handle
0x1800d5507  test    rcx, rcx
0x1800d550a  jz      short loc_1800D551A
0x1800d550c  call    cs:__imp_NtClose
0x1800d5512  mov     qword ptr [r13+0], 0
0x1800d551a  mov     rcx, [r14]; Handle
0x1800d551d  test    rcx, rcx
0x1800d5520  jz      short loc_1800D552F
0x1800d5522  call    cs:__imp_NtClose
0x1800d5528  mov     qword ptr [r14], 0
0x1800d552f  mov     rcx, [rsi]; Handle
0x1800d5532  test    rcx, rcx
0x1800d5535  jz      short loc_1800D5544
0x1800d5537  call    cs:__imp_NtClose
0x1800d553d  mov     qword ptr [rsi], 0
0x1800d5544  mov     rcx, [r15]; Handle
0x1800d5547  test    rcx, rcx
0x1800d554a  jz      short loc_1800D5559
0x1800d554c  call    cs:__imp_NtClose
0x1800d5552  mov     qword ptr [r15], 0
0x1800d5559  mov     rcx, [r12]; Handle
0x1800d555d  test    rcx, rcx
0x1800d5560  jz      short loc_1800D5570
0x1800d5562  call    cs:__imp_NtClose
0x1800d5568  mov     qword ptr [r12], 0
0x1800d5570  mov     eax, ebx
0x1800d5572  mov     rcx, [rbp+0B70h+var_50]
0x1800d5579  xor     rcx, rsp; StackCookie
0x1800d557c  call    __security_check_cookie
0x1800d5581  add     rsp, 0C38h
0x1800d5588  pop     r15
0x1800d558a  pop     r14
0x1800d558c  pop     r13
0x1800d558e  pop     r12
0x1800d5590  pop     rdi
0x1800d5591  pop     rsi
0x1800d5592  pop     rbx
0x1800d5593  pop     rbp
0x1800d5594  retn
0x1800d5595  mov     r9d, [rsp+0C70h+Length]; Length
0x1800d559a  lea     rax, [rsp+0C70h+Length]
0x1800d559f  mov     rcx, [rsp+0C70h+Handle]; Handle
0x1800d55a4  xor     esi, esi
0x1800d55a6  mov     r8, r14; SecurityDescriptor
0x1800d55a9  mov     [rsp+0C70h+LengthNeeded], rax; LengthNeeded
0x1800d55ae  lea     edx, [rsi+4]; SecurityInformation
0x1800d55b1  call    cs:__imp_NtQuerySecurityObject
0x1800d55b7  mov     ebx, eax
0x1800d55b9  test    eax, eax
0x1800d55bb  js      loc_1800D56AD
0x1800d55c1  lea     rax, [rbp+0B70h+var_B50]
0x1800d55c5  xor     r9d, r9d; unsigned int
0x1800d55c8  mov     r8, r15; void *
0x1800d55cb  mov     [rsp+0C70h+LengthNeeded], rax; void *
0x1800d55d0  mov     rdx, r14; void *
0x1800d55d3  mov     ecx, edi; unsigned int
0x1800d55d5  call    ?BuildPrivateDirectorySecurityDescriptor@@YAJKPEAX0K0@Z; BuildPrivateDirectorySecurityDescriptor(ulong,void *,void *,ulong,void *)
0x1800d55da  mov     ebx, eax
0x1800d55dc  test    eax, eax
0x1800d55de  js      loc_1800D56AD
0x1800d55e4  mov     rax, [rsp+0C70h+Handle]
0x1800d55e9  lea     r8, [rbp+0B70h+var_BE8]
0x1800d55ed  mov     r9, [rbp+0B70h+var_BA0]
0x1800d55f1  lea     edx, [rsi+0Fh]
0x1800d55f4  mov     [rbp+0B70h+var_BE8.RootDirectory], rax
0x1800d55f8  lea     rcx, [rbp+0B70h+var_BF0]
0x1800d55fc  lea     rax, [rbp+0B70h+UnicodeString]
0x1800d5600  mov     [rbp+0B70h+var_BE8.Length], 30h ; '0'
0x1800d5607  mov     [rbp+0B70h+var_BE8.ObjectName], rax
0x1800d560b  lea     rax, [rbp+0B70h+var_B50]
0x1800d560f  mov     [rbp+0B70h+var_BE8.SecurityDescriptor], rax
0x1800d5613  mov     [rbp+0B70h+var_BE8.Attributes], 80h
0x1800d561a  mov     [rbp+0B70h+var_BE8.SecurityQualityOfService], rsi
0x1800d561e  mov     dword ptr [rsp+0C70h+LengthNeeded], 1
0x1800d5626  call    cs:__imp_NtCreateDirectoryObjectEx
0x1800d562c  mov     ebx, eax
0x1800d562e  test    eax, eax
0x1800d5630  js      short loc_1800D56AD
0x1800d5632  lea     rax, [rsp+0C70h+var_BF8]
0x1800d5637  mov     edx, edi; unsigned int
0x1800d5639  lea     r8, [rbp+0B70h+var_850]; unsigned __int16 *
0x1800d5640  mov     [rsp+0C70h+LengthNeeded], rax; void **
0x1800d5645  lea     ecx, [rsi+1]; int
0x1800d5648  call    ?OpenUserParentDirectory@@YAJHKPEAGKPEAPEAX@Z; OpenUserParentDirectory(int,ulong,ushort *,ulong,void * *)
0x1800d564d  mov     ebx, eax
0x1800d564f  test    eax, eax
0x1800d5651  js      short loc_1800D56AD
0x1800d5653  mov     rcx, [rsp+0C70h+var_BF8]; Handle
0x1800d5658  lea     rax, [rsp+0C70h+Length]
0x1800d565d  xor     r9d, r9d; Length
0x1800d5660  mov     [rsp+0C70h+LengthNeeded], rax; LengthNeeded
0x1800d5665  xor     r8d, r8d; SecurityDescriptor
0x1800d5668  lea     edx, [rsi+4]; SecurityInformation
0x1800d566b  call    cs:__imp_NtQuerySecurityObject
0x1800d5671  mov     ecx, 80000000h
0x1800d5676  mov     ebx, eax
0x1800d5678  add     eax, ecx
0x1800d567a  test    ecx, eax
0x1800d567c  jnz     short loc_1800D5686
0x1800d567e  cmp     ebx, 0C0000023h
0x1800d5684  jnz     short loc_1800D56AD
0x1800d5686  mov     rcx, gs:60h
0x1800d568f  xor     edx, edx; Flags
0x1800d5691  mov     r8d, [rsp+0C70h+Length]; Size
0x1800d5696  mov     rcx, [rcx+30h]; HeapHandle
0x1800d569a  call    cs:__imp_RtlAllocateHeap
0x1800d56a0  mov     rsi, rax
0x1800d56a3  test    rax, rax
0x1800d56a6  jnz     short loc_1800D56F4
0x1800d56a8  mov     ebx, 0C0000017h
0x1800d56ad  mov     r15, [rsp+0C70h+Ace]
0x1800d56b2  mov     rcx, gs:60h
0x1800d56bb  mov     r8, r14; P
0x1800d56be  xor     edx, edx; Flags
0x1800d56c0  mov     rcx, [rcx+30h]; HeapHandle
0x1800d56c4  call    cs:__imp_RtlFreeHeap
0x1800d56ca  test    rsi, rsi
0x1800d56cd  jz      short loc_1800D56E7
0x1800d56cf  mov     rcx, gs:60h
0x1800d56d8  mov     r8, rsi; P
0x1800d56db  xor     edx, edx; Flags
0x1800d56dd  mov     rcx, [rcx+30h]; HeapHandle
0x1800d56e1  call    cs:__imp_RtlFreeHeap
0x1800d56e7  mov     rsi, [rbp+0B70h+var_BA8]
0x1800d56eb  mov     r14, [rbp+0B70h+SymbolicLinkHandle]
0x1800d56ef  jmp     loc_1800D5433
  ... truncated ...
```
