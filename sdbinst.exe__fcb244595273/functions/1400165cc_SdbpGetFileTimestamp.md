# SdbpGetFileTimestamp

- ea: `0x1400165cc`
- end: `0x140016875`
- name: `SdbpGetFileTimestamp`
- size: `681`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140016c98`
- `0x14001c290`

## callees

- `0x14001008c`
- `0x1400165cc`
- `0x14002e3e2`
- `0x14002e420`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400166e0`
- `KERNEL32!GetProcAddress` at `0x1400166e0`
- `KERNEL32!GetModuleHandleW` at `0x1400166c1`
- `KERNEL32!GetModuleHandleW` at `0x1400166c1`
- `msvcrt!_wcsnicmp` at `0x140016665`
- `msvcrt!_wcsnicmp` at `0x140016665`
- `ntdll!RtlInitUnicodeString` at `0x14001664f`
- `ntdll!RtlInitUnicodeString` at `0x14001664f`
- `ntdll!RtlFreeHeap` at `0x140016849`
- `ntdll!RtlFreeHeap` at `0x140016849`
- `ntdll!ZwClose` at `0x140016827`
- `ntdll!ZwClose` at `0x140016827`
- `ntdll!ZwCreateFile` at `0x140016776`
- `ntdll!ZwCreateFile` at `0x140016776`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14001667d`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14001667d`
- `ntdll!NtQueryInformationFile` at `0x1400167cd`
- `ntdll!NtQueryInformationFile` at `0x1400167cd`

## string_xrefs

- `0x1400166a2`: `ntdll.dll`
- `0x14001678d`: `Failed to open file [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetFileTimestamp(_QWORD *a1, const WCHAR *a2, int a3)
{
  int v6; // ebx
  struct _UNICODE_STRING *p_DestinationString; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v23; // [rsp+D8h] [rbp-28h]
  __int64 v24; // [rsp+E8h] [rbp-18h]
  _BYTE v25[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v26; // [rsp+108h] [rbp+8h]

  v24 = 0;
  v17 = 0;
  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  v23 = 0;
  memset_0(v25, 0, 0x48u);
  P = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( _wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
  {
    v6 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &v17, 0, 0);
    if ( v6 < 0 )
      goto LABEL_20;
    p_DestinationString = (struct _UNICODE_STRING *)&v17;
  }
  else
  {
    p_DestinationString = &DestinationString;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = p_DestinationString;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( !ModuleHandleW )
  {
    v6 = -1073741823;
    goto LABEL_20;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "NtQueryInformationByName");
  if ( ProcAddress )
  {
    v10 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, _BYTE *, __int64, int))ProcAddress)(
            &ObjectAttributes,
            &IoStatusBlock,
            v25,
            72,
            68);
    v6 = v10;
    if ( v10 == -1073741772 )
      goto LABEL_20;
    if ( v10 >= 0 )
    {
      v11 = *((_QWORD *)&v26 + 1);
      v12 = v26;
LABEL_17:
      if ( a3 )
        v11 = v12;
      v6 = 0;
      *a1 = v11;
      goto LABEL_20;
    }
  }
  v13 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x60u, 0, 0);
  v6 = v13;
  if ( v13 >= 0 )
  {
    v14 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    v6 = v14;
    if ( v14 < 0 )
    {
      AslLogCallPrintf(1, "SdbpGetFileTimestamp", 1583, "Failed to get timestamp from %S. [%x]", a2, v14);
      goto LABEL_20;
    }
    v11 = *((_QWORD *)&v23 + 1);
    v12 = v23;
    v26 = v23;
    goto LABEL_17;
  }
  if ( v13 != -1073741772 )
    AslLogCallPrintf(1, "SdbpGetFileTimestamp", 1572, "Failed to open file [%x]", v13);
LABEL_20:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400165cc  mov     [rsp-8+arg_10], rbx
0x1400165d1  mov     [rsp-8+arg_18], rsi
0x1400165d6  push    rbp
0x1400165d7  push    rdi
0x1400165d8  push    r14
0x1400165da  lea     rbp, [rsp-50h]
0x1400165df  sub     rsp, 150h
0x1400165e6  mov     rax, cs:__security_cookie
0x1400165ed  xor     rax, rsp
0x1400165f0  mov     [rbp+60h+var_20], rax
0x1400165f4  xorps   xmm0, xmm0
0x1400165f7  xor     eax, eax
0x1400165f9  xorps   xmm1, xmm1
0x1400165fc  mov     [rbp+60h+var_78], rax
0x140016600  mov     esi, r8d
0x140016603  mov     [rsp+160h+var_F8], rax
0x140016608  mov     rdi, rdx
0x14001660b  mov     [rsp+160h+FileHandle], rax
0x140016610  mov     r14, rcx
0x140016613  lea     r8d, [rax+48h]; Size
0x140016617  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x14001661b  xor     edx, edx; Val
0x14001661d  lea     rcx, [rbp+60h+var_70]; void *
0x140016621  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x140016625  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x140016629  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x14001662d  movups  xmmword ptr [rsp+160h+IoStatusBlock], xmm0
0x140016632  movups  [rbp+60h+FileInformation], xmm1
0x140016636  movups  [rbp+60h+var_88], xmm1
0x14001663a  call    memset_0
0x14001663f  mov     rdx, rdi; SourceString
0x140016642  mov     [rsp+160h+P], 0
0x14001664b  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x14001664f  call    cs:__imp_RtlInitUnicodeString
0x140016655  mov     r8d, 0Ch; MaxCount
0x14001665b  lea     rdx, aSystemroot_4; "\\SystemRoot\\"
0x140016662  mov     rcx, rdi; String1
0x140016665  call    cs:__imp__wcsnicmp
0x14001666b  test    eax, eax
0x14001666d  jz      short loc_140016694
0x14001666f  xor     r9d, r9d
0x140016672  lea     rdx, [rsp+160h+var_F8]
0x140016677  xor     r8d, r8d
0x14001667a  mov     rcx, rdi
0x14001667d  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140016683  mov     ebx, eax
0x140016685  test    eax, eax
0x140016687  js      loc_14001681D
0x14001668d  lea     rax, [rsp+160h+var_F8]
0x140016692  jmp     short loc_140016698
0x140016694  lea     rax, [rbp+60h+DestinationString]
0x140016698  xorps   xmm0, xmm0
0x14001669b  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1400166a2  lea     rcx, LibFileName; "ntdll.dll"
0x1400166a9  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x1400166b1  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400166b6  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x1400166bd  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1400166c1  call    cs:__imp_GetModuleHandleW
0x1400166c7  test    rax, rax
0x1400166ca  jnz     short loc_1400166D6
0x1400166cc  mov     ebx, 0C0000001h
0x1400166d1  jmp     loc_14001681D
0x1400166d6  lea     rdx, aNtqueryinforma; "NtQueryInformationByName"
0x1400166dd  mov     rcx, rax; hModule
0x1400166e0  call    cs:__imp_GetProcAddress
0x1400166e6  test    rax, rax
0x1400166e9  jz      short loc_140016729
0x1400166eb  mov     r9d, 48h ; 'H'
0x1400166f1  mov     dword ptr [rsp+160h+AllocationSize], 44h ; 'D'
0x1400166f9  lea     r8, [rbp+60h+var_70]
0x1400166fd  lea     rdx, [rsp+160h+IoStatusBlock]
0x140016702  lea     rcx, [rbp+60h+ObjectAttributes]
0x140016706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001670b  mov     ebx, eax
0x14001670d  cmp     eax, 0C0000034h
0x140016712  jz      loc_14001681D
0x140016718  test    eax, eax
0x14001671a  js      short loc_140016729
0x14001671c  mov     rax, qword ptr [rbp+60h+var_58+8]
0x140016720  mov     rcx, qword ptr [rbp+60h+var_58]
0x140016724  jmp     loc_140016812
0x140016729  mov     [rsp+160h+EaLength], 0; EaLength
0x140016731  lea     r9, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x140016736  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x14001673f  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x140016743  mov     [rsp+160h+CreateOptions], 60h ; '`'; CreateOptions
0x14001674b  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x140016750  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x140016758  mov     edx, 80100080h; DesiredAccess
0x14001675d  mov     [rsp+160h+ShareAccess], 1; ShareAccess
0x140016765  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x14001676d  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x140016776  call    cs:__imp_ZwCreateFile
0x14001677c  mov     ebx, eax
0x14001677e  test    eax, eax
0x140016780  jns     short loc_1400167B1
0x140016782  cmp     eax, 0C0000034h
0x140016787  jz      loc_14001681D
0x14001678d  lea     r9, aFailedToOpenFi; "Failed to open file [%x]"
0x140016794  mov     dword ptr [rsp+160h+AllocationSize], eax
0x140016798  mov     r8d, 624h
0x14001679e  lea     rdx, aSdbpgetfiletim_0; "SdbpGetFileTimestamp"
0x1400167a5  mov     ecx, 1
0x1400167aa  call    AslLogCallPrintf
0x1400167af  jmp     short loc_14001681D
0x1400167b1  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x1400167b6  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x1400167ba  mov     r9d, 28h ; '('; Length
0x1400167c0  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x1400167c8  lea     rdx, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x1400167cd  call    cs:__imp_NtQueryInformationFile
0x1400167d3  mov     ebx, eax
0x1400167d5  test    eax, eax
0x1400167d7  jns     short loc_140016802
0x1400167d9  mov     [rsp+160h+FileAttributes], eax
0x1400167dd  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x1400167e4  mov     r8d, 62Fh
0x1400167ea  mov     [rsp+160h+AllocationSize], rdi
0x1400167ef  lea     rdx, aSdbpgetfiletim_0; "SdbpGetFileTimestamp"
0x1400167f6  mov     ecx, 1
0x1400167fb  call    AslLogCallPrintf
0x140016800  jmp     short loc_14001681D
0x140016802  mov     rcx, qword ptr [rbp+60h+var_88]
0x140016806  mov     rax, qword ptr [rbp+60h+var_88+8]
0x14001680a  mov     qword ptr [rbp+60h+var_58], rcx
0x14001680e  mov     qword ptr [rbp+60h+var_58+8], rax
0x140016812  test    esi, esi
0x140016814  cmovnz  rax, rcx
0x140016818  xor     ebx, ebx
0x14001681a  mov     [r14], rax
0x14001681d  mov     rcx, [rsp+160h+FileHandle]; Handle
0x140016822  test    rcx, rcx
0x140016825  jz      short loc_14001682D
0x140016827  call    cs:__imp_ZwClose
0x14001682d  cmp     [rsp+160h+P], 0
0x140016833  jz      short loc_14001684F
0x140016835  mov     rcx, gs:60h
0x14001683e  xor     edx, edx; Flags
0x140016840  mov     r8, [rsp+160h+P]; P
0x140016845  mov     rcx, [rcx+30h]; HeapHandle
0x140016849  call    cs:__imp_RtlFreeHeap
0x14001684f  mov     eax, ebx
0x140016851  mov     rcx, [rbp+60h+var_20]
0x140016855  xor     rcx, rsp; StackCookie
0x140016858  call    __security_check_cookie
0x14001685d  lea     r11, [rsp+160h+var_10]
0x140016865  mov     rbx, [r11+30h]
0x140016869  mov     rsi, [r11+38h]
0x14001686d  mov     rsp, r11
0x140016870  pop     r14
0x140016872  pop     rdi
0x140016873  pop     rbp
0x140016874  retn
```
