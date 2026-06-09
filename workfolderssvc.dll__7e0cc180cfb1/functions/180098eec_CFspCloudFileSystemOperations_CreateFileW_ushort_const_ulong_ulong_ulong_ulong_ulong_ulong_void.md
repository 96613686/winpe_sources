# CFspCloudFileSystemOperations::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)

- ea: `0x180098eec`
- end: `0x180099180`
- name: `?CreateFileW@CFspCloudFileSystemOperations@@SAJPEBGKKKKKKPEAPEAX@Z`
- size: `660`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, ACCESS_MASK DesiredAccess@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, ULONG, ULONG, unsigned int, void **)`
- caller_count: `16`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008f34c`
- `0x18008faa4`
- `0x180090710`
- `0x1800908d8`
- `0x180090c88`
- `0x180092d2c`
- `0x180093f50`
- `0x180094118`
- `0x1800942b0`
- `0x1800946c0`
- `0x180094880`
- `0x1800950b4`
- `0x180095750`
- `0x180096930`
- `0x18009a0e0`
- `0x18009a224`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180063cec`
- `0x180098eec`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180099040`
- `ntdll!RtlInitUnicodeString` at `0x180099040`
- `ntdll!NtFsControlFile` at `0x180099120`
- `ntdll!NtFsControlFile` at `0x180099120`
- `ntdll!NtCreateFile` at `0x1800990a2`
- `ntdll!NtCreateFile` at `0x1800990a2`
- `ntdll!NtClose` at `0x180099156`
- `ntdll!NtClose` at `0x180099156`

## string_xrefs

- `0x180098f7e`: `CFspCloudFileSystemOperations::CreateFileW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFspCloudFileSystemOperations::CreateFileW(
        PCWSTR SourceString,
        ACCESS_MASK DesiredAccess,
        __int64 a3,
        ULONG a4,
        ULONG CreateOptions,
        ULONG CreateDisposition,
        unsigned int a7,
        void **a8)
{
  _DWORD *v11; // rax
  char v12; // cl
  int v13; // ebx
  unsigned int v14; // eax
  __int16 v15; // ax
  void *v16; // rcx
  unsigned int v17; // eax
  void *FileHandle; // [rsp+60h] [rbp-91h] BYREF
  int v20; // [rsp+68h] [rbp-89h] BYREF
  int v21; // [rsp+6Ch] [rbp-85h]
  char v22; // [rsp+70h] [rbp-81h]
  const char *v23; // [rsp+78h] [rbp-79h]
  __int64 v24; // [rsp+80h] [rbp-71h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-69h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-49h] BYREF
  __int128 InputBuffer; // [rsp+D8h] [rbp-19h] BYREF
  __int64 v29; // [rsp+E8h] [rbp-9h]

  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( (v11[17] & 0x100) == 0 || (v12 = 1, *((_BYTE *)v11 + 65) < 6u) )
    v12 = 0;
  v20 = 0;
  v21 = 251;
  v22 = v12;
  v23 = "CFspCloudFileSystemOperations::CreateFileW";
  v24 = 0;
  FileHandle = 0;
  if ( a8 )
    *a8 = 0;
  if ( !SourceString )
  {
    v13 = -2147024809;
    v20 = -2147024809;
    HIWORD(v21) = 256;
    goto LABEL_25;
  }
  v20 = 0;
  LOWORD(v21) = 256;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_SDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      15,
      (unsigned int)WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids,
      (_DWORD)SourceString,
      DesiredAccess);
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 2;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v14 = NtCreateFile(
          &FileHandle,
          DesiredAccess,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          a4,
          CreateDisposition,
          CreateOptions,
          0,
          0);
  v13 = HRESULTFromNTSTATUS(v14);
  v20 = v13;
  v15 = 284;
  if ( v13 < 0 )
    goto LABEL_17;
  LOWORD(v21) = 284;
  if ( !a7 )
  {
LABEL_21:
    v16 = FileHandle;
    *a8 = FileHandle;
    goto LABEL_22;
  }
  InputBuffer = 0;
  v29 = 0;
  LODWORD(InputBuffer) = a7;
  v17 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
  v13 = HRESULTFromNTSTATUS(v17);
  v20 = v13;
  v15 = 301;
  if ( v13 >= 0 )
  {
    LOWORD(v21) = 301;
    goto LABEL_21;
  }
LABEL_17:
  HIWORD(v21) = v15;
  v16 = FileHandle;
LABEL_22:
  if ( v13 < 0 && v16 )
  {
    NtClose(v16);
    v13 = v20;
  }
LABEL_25:
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v20);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180098eec  push    rbp
0x180098eee  push    rbx
0x180098eef  push    rsi
0x180098ef0  push    rdi
0x180098ef1  push    r12
0x180098ef3  push    r13
0x180098ef5  push    r14
0x180098ef7  push    r15
0x180098ef9  lea     rbp, [rsp-7]
0x180098efe  sub     rsp, 0F8h
0x180098f05  mov     r12d, r9d
0x180098f08  mov     r13d, edx
0x180098f0b  mov     rbx, rcx
0x180098f0e  lea     r9, WPP_GLOBAL_Control
0x180098f15  mov     r8d, 100h
0x180098f1b  mov     rax, cs:WPP_GLOBAL_Control
0x180098f22  cmp     rax, r9
0x180098f25  jz      short loc_180098F5C
0x180098f27  test    [rax+44h], r8d
0x180098f2b  jz      short loc_180098F5C
0x180098f2d  cmp     byte ptr [rax+41h], 6
0x180098f31  jb      short loc_180098F5C
0x180098f33  mov     edx, 0Eh
0x180098f38  lea     r8, WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids
0x180098f3f  mov     rcx, [rax+38h]
0x180098f43  call    WPP_SF_
0x180098f48  mov     rax, cs:WPP_GLOBAL_Control
0x180098f4f  mov     r8d, 100h
0x180098f55  lea     r9, WPP_GLOBAL_Control
0x180098f5c  xor     edx, edx
0x180098f5e  test    [rax+44h], r8d
0x180098f62  jz      short loc_180098F6C
0x180098f64  cmp     byte ptr [rax+41h], 6
0x180098f68  mov     cl, 1
0x180098f6a  jnb     short loc_180098F6E
0x180098f6c  mov     cl, dl
0x180098f6e  mov     [rsp+130h+var_C8], edx
0x180098f72  mov     [rsp+130h+var_C4], 0FBh
0x180098f7a  mov     [rsp+130h+var_C0], cl
0x180098f7e  lea     rax, aCfspcloudfiles_0; "CFspCloudFileSystemOperations::CreateFi"...
0x180098f85  mov     [rbp+3Fh+var_B8], rax
0x180098f89  mov     [rbp+3Fh+var_B0], rdx
0x180098f8d  mov     [rsp+130h+FileHandle], rdx
0x180098f92  mov     rdi, [rbp+3Fh+arg_38]
0x180098f99  test    rdi, rdi
0x180098f9c  jz      short loc_180098FA1
0x180098f9e  mov     [rdi], rdx
0x180098fa1  mov     eax, [rsp+130h+var_C8]
0x180098fa5  mov     [rsp+130h+var_C8], eax
0x180098fa9  test    rbx, rbx
0x180098fac  jnz     short loc_180098FC2
0x180098fae  mov     ebx, 80070057h
0x180098fb3  mov     [rsp+130h+var_C8], ebx
0x180098fb7  mov     word ptr [rsp+130h+var_C4+2], r8w
0x180098fbd  jmp     loc_180099160
0x180098fc2  mov     [rsp+130h+var_C8], edx
0x180098fc6  mov     word ptr [rsp+130h+var_C4], r8w
0x180098fcc  xorps   xmm0, xmm0
0x180098fcf  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x180098fd3  xorps   xmm1, xmm1
0x180098fd6  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm1
0x180098fda  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm1
0x180098fde  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x180098fe2  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x180098fe6  mov     esi, [rbp+3Fh+arg_30]
0x180098fe9  mov     r14d, [rbp+3Fh+arg_28]
0x180098fed  mov     r15d, [rbp+3Fh+arg_20]
0x180098ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x180098ff8  cmp     rcx, r9
0x180098ffb  jz      short loc_180099039
0x180098ffd  test    [rcx+44h], r8d
0x180099001  jz      short loc_180099039
0x180099003  cmp     byte ptr [rcx+41h], 4
0x180099007  jb      short loc_180099039
0x180099009  mov     edx, 0Fh
0x18009900e  mov     dword ptr [rsp+130h+EaBuffer], esi
0x180099012  mov     [rsp+130h+CreateOptions], r14d
0x180099017  mov     [rsp+130h+CreateDisposition], r15d
0x18009901c  mov     [rsp+130h+ShareAccess], r12d
0x180099021  mov     dword ptr [rsp+130h+AllocationSize], r13d
0x180099026  mov     r9, rbx
0x180099029  lea     r8, WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids
0x180099030  mov     rcx, [rcx+38h]
0x180099034  call    WPP_SF_SDDDDDD
0x180099039  mov     rdx, rbx; SourceString
0x18009903c  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x180099040  call    cs:__imp_RtlInitUnicodeString
0x180099046  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18009904d  xor     ecx, ecx
0x18009904f  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rcx
0x180099053  mov     [rbp+3Fh+ObjectAttributes.Attributes], 2
0x18009905a  lea     rax, [rbp+3Fh+DestinationString]
0x18009905e  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x180099062  xorps   xmm0, xmm0
0x180099065  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18009906a  mov     [rsp+130h+EaLength], ecx; EaLength
0x18009906e  mov     [rsp+130h+EaBuffer], rcx; EaBuffer
0x180099073  mov     [rsp+130h+CreateOptions], r15d; CreateOptions
0x180099078  mov     [rsp+130h+CreateDisposition], r14d; CreateDisposition
0x18009907d  mov     [rsp+130h+ShareAccess], r12d; ShareAccess
0x180099082  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x18009908a  xor     r14d, r14d
0x18009908d  mov     [rsp+130h+AllocationSize], r14; AllocationSize
0x180099092  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x180099096  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x18009909a  mov     edx, r13d; DesiredAccess
0x18009909d  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x1800990a2  call    cs:__imp_NtCreateFile
0x1800990a8  mov     ecx, eax
0x1800990aa  call    HRESULTFromNTSTATUS
0x1800990af  mov     ebx, eax
0x1800990b1  mov     [rsp+130h+var_C8], eax
0x1800990b5  mov     [rsp+130h+var_C8], eax
0x1800990b9  test    eax, eax
0x1800990bb  mov     eax, 11Ch
0x1800990c0  jns     short loc_1800990CE
0x1800990c2  mov     word ptr [rsp+130h+var_C4+2], ax
0x1800990c7  mov     rcx, [rsp+130h+FileHandle]
0x1800990cc  jmp     short loc_18009914D
0x1800990ce  mov     word ptr [rsp+130h+var_C4], ax
0x1800990d3  test    esi, esi
0x1800990d5  jz      short loc_180099145
0x1800990d7  xorps   xmm0, xmm0
0x1800990da  xor     eax, eax
0x1800990dc  movups  [rbp+3Fh+InputBuffer], xmm0
0x1800990e0  mov     [rbp+3Fh+var_48], rax
0x1800990e4  mov     dword ptr [rbp+3Fh+InputBuffer], esi
0x1800990e7  mov     dword ptr [rsp+130h+EaBuffer], r14d; OutputBufferLength
0x1800990ec  mov     qword ptr [rsp+130h+CreateOptions], r14; OutputBuffer
0x1800990f1  mov     [rsp+130h+CreateDisposition], 18h; InputBufferLength
0x1800990f9  lea     rax, [rbp+3Fh+InputBuffer]
0x1800990fd  mov     qword ptr [rsp+130h+ShareAccess], rax; InputBuffer
0x180099102  mov     [rsp+130h+FileAttributes], 900FCh; FsControlCode
0x18009910a  lea     rax, [rbp+3Fh+IoStatusBlock]
0x18009910e  mov     [rsp+130h+AllocationSize], rax; IoStatusBlock
0x180099113  xor     r9d, r9d; ApcContext
0x180099116  xor     r8d, r8d; ApcRoutine
0x180099119  xor     edx, edx; Event
0x18009911b  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x180099120  call    cs:__imp_NtFsControlFile
0x180099126  mov     ecx, eax
0x180099128  call    HRESULTFromNTSTATUS
0x18009912d  mov     ebx, eax
0x18009912f  mov     [rsp+130h+var_C8], eax
0x180099133  mov     [rsp+130h+var_C8], eax
0x180099137  test    eax, eax
0x180099139  mov     eax, 12Dh
0x18009913e  js      short loc_1800990C2
0x180099140  mov     word ptr [rsp+130h+var_C4], ax
0x180099145  mov     rcx, [rsp+130h+FileHandle]; Handle
0x18009914a  mov     [rdi], rcx
0x18009914d  test    ebx, ebx
0x18009914f  jns     short loc_180099160
0x180099151  test    rcx, rcx
0x180099154  jz      short loc_180099160
0x180099156  call    cs:__imp_NtClose
0x18009915c  mov     ebx, [rsp+130h+var_C8]
0x180099160  lea     rcx, [rsp+130h+var_C8]; this
0x180099165  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18009916a  mov     eax, ebx
0x18009916c  add     rsp, 0F8h
0x180099173  pop     r15
0x180099175  pop     r14
0x180099177  pop     r13
0x180099179  pop     r12
0x18009917b  pop     rdi
0x18009917c  pop     rsi
0x18009917d  pop     rbx
0x18009917e  pop     rbp
0x18009917f  retn
```
