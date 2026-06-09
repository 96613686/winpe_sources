# CEcsPath::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)

- ea: `0x180062448`
- end: `0x180062693`
- name: `?CreateFileW@CEcsPath@@SAJPEBGKKKKKKPEAPEAX@Z`
- size: `587`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800593c8`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180062448`
- `0x180063cec`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18006258f`
- `ntdll!RtlInitUnicodeString` at `0x18006258f`
- `ntdll!NtFsControlFile` at `0x180062649`
- `ntdll!NtFsControlFile` at `0x180062649`
- `ntdll!NtCreateFile` at `0x1800625f2`
- `ntdll!NtCreateFile` at `0x1800625f2`
- `ntdll!NtClose` at `0x180062661`
- `ntdll!NtClose` at `0x180062661`

## string_xrefs

- `0x1800624c4`: `CEcsPath::CreateFileW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEcsPath::CreateFileW(
        PCWSTR SourceString,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        void **a8)
{
  _BYTE *v9; // rax
  char v10; // cl
  void **v11; // rdi
  NTSTATUS v12; // ebx
  void *v13; // rcx
  unsigned int v14; // ebx
  void *FileHandle; // [rsp+68h] [rbp-69h] BYREF
  int v17; // [rsp+70h] [rbp-61h] BYREF
  int v18; // [rsp+74h] [rbp-5Dh]
  char v19; // [rsp+78h] [rbp-59h]
  const char *v20; // [rsp+80h] [rbp-51h]
  __int64 v21; // [rsp+88h] [rbp-49h]
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-21h] BYREF
  __int128 InputBuffer; // [rsp+E0h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+F0h] [rbp+1Fh]
  int pExceptionObject; // [rsp+130h] [rbp+5Fh] BYREF

  pExceptionObject = a4;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_5d95a7213829360425c4708bf03e9463_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( (v9[68] & 2) == 0 || (v10 = 1, v9[65] < 6u) )
    v10 = 0;
  v17 = 0;
  v18 = 1148;
  v19 = v10;
  v20 = "CEcsPath::CreateFileW";
  v21 = 0;
  FileHandle = 0;
  v11 = a8;
  if ( a8 )
    *a8 = 0;
  if ( !SourceString )
  {
    v17 = -2147024809;
    HIWORD(v18) = 1154;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  v17 = 0;
  LOWORD(v18) = 1154;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_SDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      30,
      (unsigned int)WPP_5d95a7213829360425c4708bf03e9463_Traceguids,
      (_DWORD)SourceString,
      128);
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 2;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = NtCreateFile(&FileHandle, 0x110180u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, 0x22u, 0, 0);
  if ( v12 >= 0 )
  {
    InputBuffer = 0;
    v26 = 0;
    LODWORD(InputBuffer) = 8;
    v12 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
  }
  v13 = FileHandle;
  *v11 = FileHandle;
  if ( v12 < 0 && v13 )
    NtClose(v13);
  v14 = HRESULTFromNTSTATUS((unsigned int)v12);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v17);
  return v14;
}

```

## disassembly

```asm
0x180062448  mov     rax, rsp
0x18006244b  mov     [rax+8], rbx
0x18006244f  mov     [rax+10h], rsi
0x180062453  mov     [rax+20h], r9d
0x180062457  push    rbp
0x180062458  push    rdi
0x180062459  push    r12
0x18006245b  lea     rbp, [rax-3Fh]
0x18006245f  sub     rsp, 0F0h
0x180062466  mov     rbx, rcx
0x180062469  lea     r12, WPP_GLOBAL_Control
0x180062470  mov     rax, cs:WPP_GLOBAL_Control
0x180062477  cmp     rax, r12
0x18006247a  jz      short loc_1800624A4
0x18006247c  test    byte ptr [rax+44h], 2
0x180062480  jz      short loc_1800624A4
0x180062482  cmp     byte ptr [rax+41h], 6
0x180062486  jb      short loc_1800624A4
0x180062488  mov     edx, 1Dh
0x18006248d  lea     r8, WPP_5d95a7213829360425c4708bf03e9463_Traceguids
0x180062494  mov     rcx, [rax+38h]
0x180062498  call    WPP_SF_
0x18006249d  mov     rax, cs:WPP_GLOBAL_Control
0x1800624a4  xor     esi, esi
0x1800624a6  test    byte ptr [rax+44h], 2
0x1800624aa  jz      short loc_1800624B4
0x1800624ac  cmp     byte ptr [rax+41h], 6
0x1800624b0  mov     cl, 1
0x1800624b2  jnb     short loc_1800624B7
0x1800624b4  mov     cl, sil
0x1800624b7  mov     [rbp+37h+var_98], esi
0x1800624ba  mov     [rbp+37h+var_94], 47Ch
0x1800624c1  mov     [rbp+37h+var_90], cl
0x1800624c4  lea     rax, aCecspathCreate_0; "CEcsPath::CreateFileW"
0x1800624cb  mov     [rbp+37h+var_88], rax
0x1800624cf  mov     [rbp+37h+var_80], rsi
0x1800624d3  mov     [rbp+37h+FileHandle], rsi
0x1800624d7  mov     rdi, [rbp+37h+arg_38]
0x1800624db  test    rdi, rdi
0x1800624de  jz      short loc_1800624E3
0x1800624e0  mov     [rdi], rsi
0x1800624e3  mov     eax, [rbp+37h+var_98]
0x1800624e6  mov     [rbp+37h+var_98], eax
0x1800624e9  mov     eax, 482h
0x1800624ee  test    rbx, rbx
0x1800624f1  jnz     short loc_180062513
0x1800624f3  mov     ecx, 80070057h
0x1800624f8  mov     [rbp+37h+var_98], ecx
0x1800624fb  mov     word ptr [rbp+37h+var_94+2], ax
0x1800624ff  mov     [rbp+37h+pExceptionObject], ecx
0x180062502  lea     rdx, _TI1J; pThrowInfo
0x180062509  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x18006250d  call    _CxxThrowException_0
0x180062513  mov     [rbp+37h+var_98], esi
0x180062516  mov     word ptr [rbp+37h+var_94], ax
0x18006251a  xorps   xmm0, xmm0
0x18006251d  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x180062521  xorps   xmm1, xmm1
0x180062524  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm1
0x180062528  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm1
0x18006252c  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm1
0x180062530  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x180062534  mov     rcx, cs:WPP_GLOBAL_Control
0x18006253b  cmp     rcx, r12
0x18006253e  jz      short loc_180062588
0x180062540  test    byte ptr [rcx+44h], 2
0x180062544  jz      short loc_180062588
0x180062546  cmp     byte ptr [rcx+41h], 4
0x18006254a  jb      short loc_180062588
0x18006254c  mov     edx, 1Eh
0x180062551  mov     dword ptr [rsp+100h+EaBuffer], 8
0x180062559  mov     [rsp+100h+CreateOptions], 1
0x180062561  mov     [rsp+100h+CreateDisposition], 22h ; '"'
0x180062569  mov     [rsp+100h+ShareAccess], esi
0x18006256d  mov     dword ptr [rsp+100h+AllocationSize], 110180h
0x180062575  mov     r9, rbx
0x180062578  lea     r8, WPP_5d95a7213829360425c4708bf03e9463_Traceguids
0x18006257f  mov     rcx, [rcx+38h]
0x180062583  call    WPP_SF_SDDDDDD
0x180062588  mov     rdx, rbx; SourceString
0x18006258b  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x18006258f  call    cs:__imp_RtlInitUnicodeString
0x180062595  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x18006259c  mov     [rbp+37h+ObjectAttributes.RootDirectory], rsi
0x1800625a0  mov     [rbp+37h+ObjectAttributes.Attributes], 2
0x1800625a7  lea     rax, [rbp+37h+DestinationString]
0x1800625ab  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x1800625af  xorps   xmm0, xmm0
0x1800625b2  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800625b7  mov     [rsp+100h+EaLength], esi; EaLength
0x1800625bb  mov     [rsp+100h+EaBuffer], rsi; EaBuffer
0x1800625c0  mov     [rsp+100h+CreateOptions], 22h ; '"'; CreateOptions
0x1800625c8  mov     [rsp+100h+CreateDisposition], 1; CreateDisposition
0x1800625d0  mov     [rsp+100h+ShareAccess], esi; ShareAccess
0x1800625d4  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x1800625dc  mov     [rsp+100h+AllocationSize], rsi; AllocationSize
0x1800625e1  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1800625e5  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1800625e9  mov     edx, 110180h; DesiredAccess
0x1800625ee  lea     rcx, [rbp+37h+FileHandle]; FileHandle
0x1800625f2  call    cs:__imp_NtCreateFile
0x1800625f8  mov     ebx, eax
0x1800625fa  test    eax, eax
0x1800625fc  js      short loc_180062651
0x1800625fe  xorps   xmm0, xmm0
0x180062601  xor     eax, eax
0x180062603  movups  [rbp+37h+InputBuffer], xmm0
0x180062607  mov     [rbp+37h+var_18], rax
0x18006260b  mov     dword ptr [rbp+37h+InputBuffer], 8
0x180062612  mov     dword ptr [rsp+100h+EaBuffer], esi; OutputBufferLength
0x180062616  mov     qword ptr [rsp+100h+CreateOptions], rsi; OutputBuffer
0x18006261b  mov     [rsp+100h+CreateDisposition], 18h; InputBufferLength
0x180062623  lea     rax, [rbp+37h+InputBuffer]
0x180062627  mov     qword ptr [rsp+100h+ShareAccess], rax; InputBuffer
0x18006262c  mov     [rsp+100h+FileAttributes], 900FCh; FsControlCode
0x180062634  lea     rax, [rbp+37h+IoStatusBlock]
0x180062638  mov     [rsp+100h+AllocationSize], rax; IoStatusBlock
0x18006263d  xor     r9d, r9d; ApcContext
0x180062640  xor     r8d, r8d; ApcRoutine
0x180062643  xor     edx, edx; Event
0x180062645  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x180062649  call    cs:__imp_NtFsControlFile
0x18006264f  mov     ebx, eax
0x180062651  mov     rcx, [rbp+37h+FileHandle]; Handle
0x180062655  mov     [rdi], rcx
0x180062658  test    ebx, ebx
0x18006265a  jns     short loc_180062667
0x18006265c  test    rcx, rcx
0x18006265f  jz      short loc_180062667
0x180062661  call    cs:__imp_NtClose
0x180062667  mov     ecx, ebx
0x180062669  call    HRESULTFromNTSTATUS
0x18006266e  mov     ebx, eax
0x180062670  lea     rcx, [rbp+37h+var_98]; this
0x180062674  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180062679  mov     eax, ebx
0x18006267b  lea     r11, [rsp+100h+var_10]
0x180062683  mov     rbx, [r11+20h]
0x180062687  mov     rsi, [r11+28h]
0x18006268b  mov     rsp, r11
0x18006268e  pop     r12
0x180062690  pop     rdi
0x180062691  pop     rbp
0x180062692  retn
```
