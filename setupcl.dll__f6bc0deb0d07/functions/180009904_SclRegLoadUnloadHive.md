# SclRegLoadUnloadHive

- ea: `0x180009904`
- end: `0x180009cbd`
- name: `SclRegLoadUnloadHive`
- size: `953`
- prototype: `__int64 __fastcall(char, const WCHAR *, const WCHAR *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180004844`
- `0x18000b738`
- `0x18000c73c`
- `0x18000dae0`
- `0x18000deec`

## callees

- `0x180001c74`
- `0x180008ff0`
- `0x180009904`
- `0x18000a524`
- `0x18000e66c`

## import_xrefs

- `ntdll!NtClose` at `0x180009c7c`
- `ntdll!NtClose` at `0x180009c7c`
- `ntdll!RtlFreeHeap` at `0x180009b02`
- `ntdll!RtlFreeHeap` at `0x180009c99`
- `ntdll!RtlFreeHeap` at `0x180009b02`
- `ntdll!RtlFreeHeap` at `0x180009c99`
- `ntdll!NtCreateFile` at `0x180009ba5`
- `ntdll!NtCreateFile` at `0x180009ba5`
- `ntdll!NtLoadKey` at `0x1800099cd`
- `ntdll!NtLoadKey` at `0x1800099cd`
- `ntdll!NtDelayExecution` at `0x180009bf5`
- `ntdll!NtDelayExecution` at `0x180009bf5`
- `ntdll!NtUnloadKey` at `0x180009a92`
- `ntdll!NtUnloadKey` at `0x180009a92`

## string_xrefs

- `0x1800099dc`: `Saw SHARING_VIOLATION while loading hive [%ws]; is it already loaded?`
- `0x180009b1a`: `(%lx): Failed to find loaded hive path for key: [%ws]`
- `0x180009bc1`: `Hive file [%ws] is in use; will attempt retries to ensure unload`

## pseudocode

```c
__int64 __fastcall SclRegLoadUnloadHive(char a1, const WCHAR *a2, const WCHAR *a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  char *v8; // rax
  int v9; // r9d
  __int64 *v10; // r8
  int v11; // edx
  NTSTATUS v12; // eax
  WCHAR *v13; // r15
  NTSTATUS v14; // eax
  int v15; // r14d
  NTSTATUS v16; // eax
  int v17; // r9d
  char *v18; // rdx
  ULONG ShareAccess[2]; // [rsp+30h] [rbp-D0h]
  ULONG ShareAccessa[2]; // [rsp+30h] [rbp-D0h]
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v23; // [rsp+68h] [rbp-98h] BYREF
  PVOID P[2]; // [rsp+70h] [rbp-90h]
  struct _OBJECT_ATTRIBUTES FileObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v26; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v28; // [rsp+F0h] [rbp-10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  LARGE_INTEGER Interval; // [rsp+158h] [rbp+58h] BYREF

  v28 = 0;
  v26 = 0;
  memset(&KeyObjectAttributes, 0, 44);
  memset(&FileObjectAttributes, 0, 44);
  INIT_OBJA_EX((__int64)&KeyObjectAttributes, &v28, a2, 64, 0);
  KeyObjectAttributes.RootDirectory = 0;
  if ( !a1 )
  {
    v23 = a2;
    *(_OWORD *)P = 0;
    v7 = SclRegEnumerateHiveList(v6, (__int64)&v23);
    if ( v7 >= 0 )
    {
      if ( P[1] )
      {
        v13 = (WCHAR *)P[1];
        P[1] = 0;
        v14 = NtUnloadKey(&KeyObjectAttributes);
        v7 = v14;
        if ( v14 >= 0 )
        {
          Interval.QuadPart = -5000000;
          v15 = 0;
          INIT_OBJA_EX((__int64)&FileObjectAttributes, &v26, v13, 64, 0);
          FileObjectAttributes.RootDirectory = 0;
          while ( 1 )
          {
            IoStatusBlock = 0;
            FileHandle = 0;
            v16 = NtCreateFile(&FileHandle, 0x120089u, &FileObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, 0, 0, 0);
            v7 = v16;
            if ( v16 >= 0 )
              break;
            if ( v16 != -1073741757 )
            {
              v17 = 578;
              v18 = "(%lx): Failed to get exclusive lock on hive file: [%ws]";
              goto LABEL_27;
            }
            if ( !v15 )
              SclLogGenericMessage(
                0,
                2,
                (int)SclEvent_Generic_Warning,
                588,
                (__int64)"SclRegLoadUnloadHive",
                "Hive file [%ws] is in use; will attempt retries to ensure unload",
                a3);
            v7 = NtDelayExecution(0, &Interval);
            if ( v7 < 0 )
            {
              v17 = 597;
              v18 = "(%lx): Failed to delay execution";
LABEL_27:
              ShareAccess[0] = v7;
              SclLogGenericMessage(
                0,
                3,
                (int)SclEvent_Generic_Error,
                v17,
                (__int64)"SclRegLoadUnloadHive",
                v18,
                *(_QWORD *)ShareAccess,
                a3);
              ShareAccessa[0] = v7;
              SclLogGenericMessage(
                0,
                3,
                (int)SclEvent_Generic_Error,
                607,
                (__int64)"SclRegLoadUnloadHive",
                "(%lx): Failed to ensure hive file [%ws] is unloaded",
                *(_QWORD *)ShareAccessa,
                a3);
              goto LABEL_29;
            }
            if ( (unsigned int)++v15 >= 0x3C )
              goto LABEL_29;
          }
          NtClose(FileHandle);
        }
        else
        {
          SclLogGenericMessage(
            0,
            3,
            (int)SclEvent_Generic_Error,
            508,
            (__int64)"SclRegLoadUnloadHive",
            "(%lx): Failed to unload key: [%ws]",
            v14,
            a2);
        }
        goto LABEL_29;
      }
      v7 = -1073741772;
    }
    v13 = 0;
    if ( P[1] )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
      P[1] = 0;
    }
    SclLogGenericMessage(
      0,
      3,
      (int)SclEvent_Generic_Error,
      500,
      (__int64)"SclRegLoadUnloadHive",
      "(%lx): Failed to find loaded hive path for key: [%ws]",
      v7,
      a2);
LABEL_29:
    if ( v13 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    return (unsigned int)v7;
  }
  if ( !SclFileObjectExists(a3) )
  {
    v7 = -1073741772;
    v8 = "Hive does not exist: [%ws]";
    v9 = 459;
    v10 = SclEvent_Generic_Error;
    v11 = 3;
LABEL_6:
    SclLogGenericMessage(0, v11, (int)v10, v9, (__int64)"SclRegLoadUnloadHive", v8, a3);
    return (unsigned int)v7;
  }
  INIT_OBJA_EX((__int64)&FileObjectAttributes, &v26, a3, 64, 0);
  FileObjectAttributes.RootDirectory = 0;
  v12 = NtLoadKey(&KeyObjectAttributes, &FileObjectAttributes);
  v7 = v12;
  if ( v12 == -1073741757 )
  {
    v8 = "Saw SHARING_VIOLATION while loading hive [%ws]; is it already loaded?";
    v9 = 476;
    v10 = SclEvent_Generic_Info;
    v11 = 1;
    goto LABEL_6;
  }
  if ( v12 < 0 )
    SclLogGenericMessage(
      0,
      3,
      (int)SclEvent_Generic_Error,
      483,
      (__int64)"SclRegLoadUnloadHive",
      "(%lx): Failed to load hive: [%ws]",
      v12,
      a3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009904  mov     [rsp-8+arg_0], rbx
0x180009909  mov     [rsp-8+arg_8], rsi
0x18000990e  push    rbp
0x18000990f  push    rdi
0x180009910  push    r12
0x180009912  push    r14
0x180009914  push    r15
0x180009916  lea     rbp, [rsp-10h]
0x18000991b  sub     rsp, 110h
0x180009922  xorps   xmm0, xmm0
0x180009925  xor     eax, eax
0x180009927  mov     rsi, r8
0x18000992a  mov     rdi, rdx
0x18000992d  mov     bl, cl
0x18000992f  xorps   xmm1, xmm1
0x180009932  mov     r8, rdx
0x180009935  lea     rcx, [rbp+30h+KeyObjectAttributes]
0x180009939  movups  xmmword ptr [rbp+30h+KeyObjectAttributes.ObjectName], xmm0
0x18000993d  xor     r12d, r12d
0x180009940  lea     r9d, [rax+40h]
0x180009944  movups  xmmword ptr [rbp+30h+FileObjectAttributes.ObjectName], xmm0
0x180009948  lea     rdx, [rbp+30h+var_40]
0x18000994c  mov     [rsp+130h+AllocationSize], r12
0x180009951  movups  [rbp+30h+var_40], xmm0
0x180009955  movups  [rbp+30h+var_80], xmm1
0x180009959  movups  xmmword ptr [rbp+30h+KeyObjectAttributes.Length], xmm0
0x18000995d  movups  xmmword ptr [rbp+30h+KeyObjectAttributes+1Ch], xmm0
0x180009961  movups  xmmword ptr [rbp+30h+FileObjectAttributes.Length], xmm0
0x180009965  movups  xmmword ptr [rbp+30h+FileObjectAttributes+1Ch], xmm0
0x180009969  call    INIT_OBJA_EX
0x18000996e  mov     [rbp+30h+KeyObjectAttributes.RootDirectory], r12
0x180009972  test    bl, bl
0x180009974  jz      loc_180009A5E
0x18000997a  mov     rcx, rsi
0x18000997d  call    SclFileObjectExists
0x180009982  test    al, al
0x180009984  jnz     short loc_1800099A6
0x180009986  mov     ebx, 0C0000034h
0x18000998b  lea     rax, aHiveDoesNotExi; "Hive does not exist: [%ws]"
0x180009992  mov     r9d, 1CBh
0x180009998  lea     r8, SclEvent_Generic_Error
0x18000999f  lea     edx, [r12+3]
0x1800099a4  jmp     short loc_1800099F5
0x1800099a6  mov     r9d, 40h ; '@'
0x1800099ac  mov     [rsp+130h+AllocationSize], r12
0x1800099b1  mov     r8, rsi
0x1800099b4  lea     rdx, [rbp+30h+var_80]
0x1800099b8  lea     rcx, [rbp+30h+FileObjectAttributes]
0x1800099bc  call    INIT_OBJA_EX
0x1800099c1  lea     rdx, [rbp+30h+FileObjectAttributes]; FileObjectAttributes
0x1800099c5  mov     [rbp+30h+FileObjectAttributes.RootDirectory], r12
0x1800099c9  lea     rcx, [rbp+30h+KeyObjectAttributes]; KeyObjectAttributes
0x1800099cd  call    cs:__imp_NtLoadKey
0x1800099d3  mov     ebx, eax
0x1800099d5  cmp     eax, 0C0000043h
0x1800099da  jnz     short loc_180009A17
0x1800099dc  lea     rax, aSawSharingViol; "Saw SHARING_VIOLATION while loading hiv"...
0x1800099e3  mov     r9d, 1DCh
0x1800099e9  lea     r8, SclEvent_Generic_Info
0x1800099f0  mov     edx, 1
0x1800099f5  mov     qword ptr [rsp+130h+ShareAccess], rsi
0x1800099fa  lea     rdi, aSclregloadunlo; "SclRegLoadUnloadHive"
0x180009a01  mov     qword ptr [rsp+130h+FileAttributes], rax
0x180009a06  xor     ecx, ecx
0x180009a08  mov     [rsp+130h+AllocationSize], rdi
0x180009a0d  call    SclLogGenericMessage
0x180009a12  jmp     loc_180009C9F
0x180009a17  test    eax, eax
0x180009a19  jns     loc_180009C9F
0x180009a1f  mov     qword ptr [rsp+130h+CreateDisposition], rsi
0x180009a24  lea     rdi, aSclregloadunlo; "SclRegLoadUnloadHive"
0x180009a2b  mov     [rsp+130h+ShareAccess], eax
0x180009a2f  lea     r8, SclEvent_Generic_Error
0x180009a36  lea     rax, aLxFailedToLoad; "(%lx): Failed to load hive: [%ws]"
0x180009a3d  mov     r9d, 1E3h
0x180009a43  mov     qword ptr [rsp+130h+FileAttributes], rax
0x180009a48  mov     edx, 3
0x180009a4d  xor     ecx, ecx
0x180009a4f  mov     [rsp+130h+AllocationSize], rdi
0x180009a54  call    SclLogGenericMessage
0x180009a59  jmp     loc_180009C9F
0x180009a5e  xorps   xmm0, xmm0
0x180009a61  mov     [rsp+130h+var_C8], rdi
0x180009a66  lea     rdx, [rsp+130h+var_C8]
0x180009a6b  movdqu  xmmword ptr [rsp+130h+P], xmm0
0x180009a71  call    SclRegEnumerateHiveList
0x180009a76  mov     ebx, eax
0x180009a78  mov     rax, [rsp+130h+P+8]
0x180009a7d  test    ebx, ebx
0x180009a7f  js      short loc_180009AE6
0x180009a81  test    rax, rax
0x180009a84  jz      short loc_180009AE1
0x180009a86  mov     r15, rax
0x180009a89  mov     [rsp+130h+P+8], r12
0x180009a8e  lea     rcx, [rbp+30h+KeyObjectAttributes]; KeyObjectAttributes
0x180009a92  call    cs:__imp_NtUnloadKey
0x180009a98  mov     ebx, eax
0x180009a9a  test    eax, eax
0x180009a9c  jns     loc_180009B2D
0x180009aa2  mov     qword ptr [rsp+130h+CreateDisposition], rdi
0x180009aa7  mov     r9d, 1FCh
0x180009aad  mov     [rsp+130h+ShareAccess], eax
0x180009ab1  lea     rax, aLxFailedToUnlo; "(%lx): Failed to unload key: [%ws]"
0x180009ab8  lea     rdi, aSclregloadunlo; "SclRegLoadUnloadHive"
0x180009abf  mov     qword ptr [rsp+130h+FileAttributes], rax
0x180009ac4  lea     r8, SclEvent_Generic_Error
0x180009acb  mov     edx, 3
0x180009ad0  mov     [rsp+130h+AllocationSize], rdi
0x180009ad5  xor     ecx, ecx
0x180009ad7  call    SclLogGenericMessage
0x180009adc  jmp     loc_180009C82
0x180009ae1  mov     ebx, 0C0000034h
0x180009ae6  mov     r15, r12
0x180009ae9  test    rax, rax
0x180009aec  jz      short loc_180009B0D
0x180009aee  mov     rcx, gs:60h
0x180009af7  xor     edx, edx; Flags
0x180009af9  mov     r8, [rsp+130h+P+8]; P
0x180009afe  mov     rcx, [rcx+30h]; HeapHandle
0x180009b02  call    cs:__imp_RtlFreeHeap
0x180009b08  mov     [rsp+130h+P+8], r12
0x180009b0d  test    ebx, ebx
0x180009b0f  jns     loc_180009A8E
0x180009b15  mov     qword ptr [rsp+130h+CreateDisposition], rdi
0x180009b1a  lea     rax, aLxFailedToFind; "(%lx): Failed to find loaded hive path "...
0x180009b21  mov     [rsp+130h+ShareAccess], ebx
0x180009b25  mov     r9d, 1F4h
0x180009b2b  jmp     short loc_180009AB8
0x180009b2d  mov     r9d, 40h ; '@'
0x180009b33  mov     qword ptr [rbp+30h+Interval], 0FFFFFFFFFFB3B4C0h
0x180009b3b  mov     r8, r15
0x180009b3e  mov     [rsp+130h+AllocationSize], r12
0x180009b43  lea     rdx, [rbp+30h+var_80]
0x180009b47  mov     r14d, r12d
0x180009b4a  lea     rcx, [rbp+30h+FileObjectAttributes]
0x180009b4e  call    INIT_OBJA_EX
0x180009b53  mov     [rbp+30h+FileObjectAttributes.RootDirectory], r12
0x180009b57  lea     rdi, aSclregloadunlo; "SclRegLoadUnloadHive"
0x180009b5e  mov     [rsp+130h+EaLength], r12d; EaLength
0x180009b63  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x180009b67  mov     [rsp+130h+EaBuffer], r12; EaBuffer
0x180009b6c  lea     r8, [rbp+30h+FileObjectAttributes]; ObjectAttributes
0x180009b70  mov     [rsp+130h+CreateOptions], r12d; CreateOptions
0x180009b75  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x180009b7a  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x180009b82  xorps   xmm0, xmm0
0x180009b85  mov     [rsp+130h+ShareAccess], r12d; ShareAccess
0x180009b8a  mov     edx, 120089h; DesiredAccess
0x180009b8f  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x180009b97  mov     [rsp+130h+AllocationSize], r12; AllocationSize
0x180009b9c  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x180009ba0  mov     [rsp+130h+FileHandle], r12
0x180009ba5  call    cs:__imp_NtCreateFile
0x180009bab  mov     ebx, eax
0x180009bad  test    eax, eax
0x180009baf  jns     loc_180009C77
0x180009bb5  cmp     eax, 0C0000043h
0x180009bba  jnz     short loc_180009C1F
0x180009bbc  test    r14d, r14d
0x180009bbf  jnz     short loc_180009BEF
0x180009bc1  lea     rax, aHiveFileWsIsIn; "Hive file [%ws] is in use; will attempt"...
0x180009bc8  mov     qword ptr [rsp+130h+ShareAccess], rsi
0x180009bcd  mov     qword ptr [rsp+130h+FileAttributes], rax
0x180009bd2  lea     r8, SclEvent_Generic_Warning
0x180009bd9  mov     r9d, 24Ch
0x180009bdf  mov     [rsp+130h+AllocationSize], rdi
0x180009be4  lea     edx, [r14+2]
0x180009be8  xor     ecx, ecx
0x180009bea  call    SclLogGenericMessage
0x180009bef  lea     rdx, [rbp+30h+Interval]; Interval
0x180009bf3  xor     ecx, ecx; Alertable
0x180009bf5  call    cs:__imp_NtDelayExecution
0x180009bfb  mov     ebx, eax
0x180009bfd  test    eax, eax
0x180009bff  js      short loc_180009C10
0x180009c01  inc     r14d
0x180009c04  cmp     r14d, 3Ch ; '<'
0x180009c08  jb      loc_180009B5E
0x180009c0e  jmp     short loc_180009C82
0x180009c10  mov     r9d, 255h
0x180009c16  lea     rdx, aLxFailedToDela; "(%lx): Failed to delay execution"
0x180009c1d  jmp     short loc_180009C2C
0x180009c1f  mov     r9d, 242h
0x180009c25  lea     rdx, aLxFailedToGetE; "(%lx): Failed to get exclusive lock on "...
0x180009c2c  mov     qword ptr [rsp+130h+CreateDisposition], rsi
0x180009c31  mov     rax, rdi
0x180009c34  mov     [rsp+130h+ShareAccess], ebx
0x180009c38  mov     r8d, ebx
0x180009c3b  mov     qword ptr [rsp+130h+FileAttributes], rdx
0x180009c40  lea     r8, SclEvent_Generic_Error
0x180009c47  mov     edx, 3
0x180009c4c  mov     [rsp+130h+AllocationSize], rax
0x180009c51  mov     r10, rsi
0x180009c54  mov     rcx, r12
0x180009c57  call    SclLogGenericMessage
0x180009c5c  mov     qword ptr [rsp+130h+CreateDisposition], rsi
0x180009c61  lea     rax, aLxFailedToEnsu; "(%lx): Failed to ensure hive file [%ws]"...
0x180009c68  mov     [rsp+130h+ShareAccess], ebx
0x180009c6c  mov     r9d, 25Fh
0x180009c72  jmp     loc_180009ABF
0x180009c77  mov     rcx, [rsp+130h+FileHandle]; Handle
0x180009c7c  call    cs:__imp_NtClose
0x180009c82  test    r15, r15
0x180009c85  jz      short loc_180009C9F
0x180009c87  mov     rcx, gs:60h
0x180009c90  mov     r8, r15; P
0x180009c93  xor     edx, edx; Flags
0x180009c95  mov     rcx, [rcx+30h]; HeapHandle
0x180009c99  call    cs:__imp_RtlFreeHeap
0x180009c9f  lea     r11, [rsp+130h+var_20]
0x180009ca7  mov     eax, ebx
0x180009ca9  mov     rbx, [r11+30h]
0x180009cad  mov     rsi, [r11+38h]
0x180009cb1  mov     rsp, r11
0x180009cb4  pop     r15
0x180009cb6  pop     r14
0x180009cb8  pop     r12
0x180009cba  pop     rdi
0x180009cbb  pop     rbp
0x180009cbc  retn
```
