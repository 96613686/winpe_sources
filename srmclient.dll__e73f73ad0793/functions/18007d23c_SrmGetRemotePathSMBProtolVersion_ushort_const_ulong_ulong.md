# SrmGetRemotePathSMBProtolVersion(ushort const *,ulong &,ulong &)

- ea: `0x18007d23c`
- end: `0x18007d4bb`
- name: `?SrmGetRemotePathSMBProtolVersion@@YA_NPEBGAEAK1@Z`
- size: `639`
- prototype: `bool __fastcall(PCWSTR DosPathName, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180053574`

## callees

- `0x18006febc`
- `0x1800700b8`
- `0x18007d23c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18007d3ad`
- `ntdll!NtOpenFile` at `0x18007d3ad`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18007d301`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18007d301`
- `ntdll!RtlFreeUnicodeString` at `0x18007d46d`
- `ntdll!RtlFreeUnicodeString` at `0x18007d46d`
- `KERNEL32!CloseHandle` at `0x18007d382`
- `KERNEL32!CloseHandle` at `0x18007d453`
- `KERNEL32!CloseHandle` at `0x18007d382`
- `KERNEL32!CloseHandle` at `0x18007d453`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007d3cc`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007d3cc`

## string_xrefs

- `0x18007d27d`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007d293`: `SRMPATHC`
- `0x18007d288`: `SrmGetRemotePathSMBProtolVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall SrmGetRemotePathSMBProtolVersion(PCWSTR DosPathName, unsigned int *a2, unsigned int *a3)
{
  char v6; // di
  NTSTATUS v7; // ebx
  __int64 v8; // r8
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR NtFileNamePart; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v14; // [rsp+88h] [rbp-78h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v16[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v17; // [rsp+C0h] [rbp-40h]
  _BYTE v18[96]; // [rsp+C8h] [rbp-38h] BYREF
  int v19; // [rsp+128h] [rbp+28h]
  _BYTE FileInformation[4]; // [rsp+130h] [rbp+30h] BYREF
  int v21; // [rsp+134h] [rbp+34h]
  unsigned __int16 v22; // [rsp+138h] [rbp+38h]
  unsigned __int16 v23; // [rsp+13Ah] [rbp+3Ah]
  _QWORD v24[22]; // [rsp+1B0h] [rbp+B0h] BYREF

  v14 = v16;
  v16[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v16[1] = L"SrmGetRemotePathSMBProtolVersion";
  v16[2] = L"SRMPATHC";
  v16[3] = 1451;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v24, (const struct CSrmDebugInfo *)v16, 0);
  *a2 = 0;
  *a3 = 0;
  v6 = 0;
  NtPathName = 0;
  NtFileNamePart = 0;
  if ( RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, &NtFileNamePart, 0) )
  {
    hObject = (HANDLE)-1LL;
    *(&ObjectAttributes.Length + 1) = 0;
    *(&ObjectAttributes.Attributes + 1) = 0;
    memset_0(FileInformation, 0, 0x74u);
    IoStatusBlock = 0;
    while ( 1 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &NtPathName;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( hObject != (HANDLE)-1LL )
        CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
      v7 = NtOpenFile(&hObject, 0x80u, &ObjectAttributes, &IoStatusBlock, 3u, 0);
      if ( v7 >= 0 )
      {
        if ( !GetFileInformationByHandleEx(hObject, FileRemoteProtocolInfo, FileInformation, 0x74u) )
          goto LABEL_14;
        if ( v21 == 0x20000 )
          break;
      }
      if ( v7 != -1073741772 || !NtFileNamePart )
        goto LABEL_14;
      v8 = -1;
      do
        ++v8;
      while ( NtFileNamePart[v8] );
      NtPathName.Buffer[((unsigned __int64)NtPathName.Length >> 1) - (unsigned __int16)v8] = 0;
      NtPathName.Length += -2 * v8;
    }
    *a2 = v22;
    *a3 = v23;
    v6 = 1;
LABEL_14:
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  RtlFreeUnicodeString(&NtPathName);
  v24[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v24);
  return v6;
}

```

## disassembly

```asm
0x18007d23c  mov     [rsp-8+arg_18], rbx
0x18007d241  push    rbp
0x18007d242  push    rsi
0x18007d243  push    rdi
0x18007d244  push    r12
0x18007d246  push    r13
0x18007d248  push    r14
0x18007d24a  push    r15
0x18007d24c  lea     rbp, [rsp-170h]
0x18007d254  sub     rsp, 270h
0x18007d25b  mov     rax, cs:__security_cookie
0x18007d262  xor     rax, rsp
0x18007d265  mov     [rbp+1A0h+var_40], rax
0x18007d26c  mov     r14, r8
0x18007d26f  mov     rsi, rdx
0x18007d272  mov     rbx, rcx
0x18007d275  lea     rax, [rbp+1A0h+var_200]
0x18007d279  mov     [rbp+1A0h+var_218], rax
0x18007d27d  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007d284  mov     [rbp+1A0h+var_200], rax
0x18007d288  lea     rax, aSrmgetremotepa; "SrmGetRemotePathSMBProtolVersion"
0x18007d28f  mov     [rbp+1A0h+var_1F8], rax
0x18007d293  lea     rax, aSrmpathc; "SRMPATHC"
0x18007d29a  mov     [rbp+1A0h+var_1F0], rax
0x18007d29e  mov     [rbp+1A0h+var_1E8], 5ABh
0x18007d2a6  xor     r15d, r15d
0x18007d2a9  mov     [rbp+1A0h+var_1E0], 0FFh
0x18007d2b0  mov     [rbp+1A0h+var_178], 1000000h
0x18007d2b7  xor     edx, edx; Val
0x18007d2b9  lea     r8d, [r15+60h]; Size
0x18007d2bd  lea     rcx, [rbp+1A0h+var_1D8]; void *
0x18007d2c1  call    memset_0
0x18007d2c6  nop
0x18007d2c7  xor     r8d, r8d
0x18007d2ca  lea     rdx, [rbp+1A0h+var_200]
0x18007d2ce  lea     rcx, [rbp+1A0h+var_F0]
0x18007d2d5  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007d2da  nop
0x18007d2db  mov     [rsi], r15d
0x18007d2de  mov     [r14], r15d
0x18007d2e1  mov     dil, r15b
0x18007d2e4  xorps   xmm0, xmm0
0x18007d2e7  movups  xmmword ptr [rsp+2A0h+NtPathName.Length], xmm0
0x18007d2ec  mov     [rsp+2A0h+NtFileNamePart], r15
0x18007d2f1  xor     r9d, r9d; DirectoryInfo
0x18007d2f4  lea     r8, [rsp+2A0h+NtFileNamePart]; NtFileNamePart
0x18007d2f9  lea     rdx, [rsp+2A0h+NtPathName]; NtPathName
0x18007d2fe  mov     rcx, rbx; DosPathName
0x18007d301  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18007d307  test    al, al
0x18007d309  jz      loc_18007D468
0x18007d30f  lea     r13, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18007d316  mov     [rsp+2A0h+var_270], r13
0x18007d31b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18007d31f  mov     [rsp+2A0h+hObject], r12
0x18007d324  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18007d32b  mov     [rsp+2A0h+var_270], rax
0x18007d330  mov     dword ptr [rsp+2A0h+ObjectAttributes+4], r15d
0x18007d335  mov     dword ptr [rsp+2A0h+ObjectAttributes+1Ch], r15d
0x18007d33a  xor     edx, edx; Val
0x18007d33c  lea     r8d, [r15+74h]; Size
0x18007d340  lea     rcx, [rbp+1A0h+FileInformation]; void *
0x18007d344  call    memset_0
0x18007d349  xorps   xmm0, xmm0
0x18007d34c  movups  xmmword ptr [rbp+1A0h+IoStatusBlock], xmm0
0x18007d350  mov     [rsp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x18007d358  mov     [rsp+2A0h+ObjectAttributes.RootDirectory], r15
0x18007d35d  mov     [rsp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x18007d365  lea     rax, [rsp+2A0h+NtPathName]
0x18007d36a  mov     [rsp+2A0h+ObjectAttributes.ObjectName], rax
0x18007d36f  xorps   xmm0, xmm0
0x18007d372  movdqu  xmmword ptr [rsp+2A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007d378  mov     rcx, [rsp+2A0h+hObject]; hObject
0x18007d37d  cmp     rcx, r12
0x18007d380  jz      short loc_18007D388
0x18007d382  call    cs:__imp_CloseHandle
0x18007d388  mov     [rsp+2A0h+hObject], r12
0x18007d38d  mov     [rsp+2A0h+OpenOptions], r15d; OpenOptions
0x18007d392  mov     [rsp+2A0h+ShareAccess], 3; ShareAccess
0x18007d39a  lea     r9, [rbp+1A0h+IoStatusBlock]; IoStatusBlock
0x18007d39e  lea     r8, [rsp+2A0h+ObjectAttributes]; ObjectAttributes
0x18007d3a3  mov     edx, 80h; DesiredAccess
0x18007d3a8  lea     rcx, [rsp+2A0h+hObject]; FileHandle
0x18007d3ad  call    cs:__imp_NtOpenFile
0x18007d3b3  mov     ebx, eax
0x18007d3b5  test    eax, eax
0x18007d3b7  js      short loc_18007D3DF
0x18007d3b9  mov     r9d, 74h ; 't'; dwBufferSize
0x18007d3bf  lea     r8, [rbp+1A0h+FileInformation]; lpFileInformation
0x18007d3c3  lea     edx, [r9-67h]; FileInformationClass
0x18007d3c7  mov     rcx, [rsp+2A0h+hObject]; hFile
0x18007d3cc  call    cs:__imp_GetFileInformationByHandleEx
0x18007d3d2  test    eax, eax
0x18007d3d4  jz      short loc_18007D43D
0x18007d3d6  cmp     [rbp+1A0h+var_16C], 20000h
0x18007d3dd  jz      short loc_18007D42D
0x18007d3df  cmp     ebx, 0C0000034h
0x18007d3e5  jnz     short loc_18007D43D
0x18007d3e7  mov     rax, [rsp+2A0h+NtFileNamePart]
0x18007d3ec  test    rax, rax
0x18007d3ef  jz      short loc_18007D43D
0x18007d3f1  mov     r8, r12
0x18007d3f4  inc     r8
0x18007d3f7  cmp     [rax+r8*2], r15w
0x18007d3fc  jnz     short loc_18007D3F4
0x18007d3fe  movzx   edx, [rsp+2A0h+NtPathName.Length]
0x18007d403  shr     rdx, 1
0x18007d406  movzx   eax, r8w
0x18007d40a  sub     rdx, rax
0x18007d40d  mov     rax, [rsp+2A0h+NtPathName.Buffer]
0x18007d412  mov     [rax+rdx*2], r15w
0x18007d417  mov     eax, 0FFFEh
0x18007d41c  movzx   ecx, r8w
0x18007d420  imul    ecx, eax
0x18007d423  add     [rsp+2A0h+NtPathName.Length], cx
0x18007d428  jmp     loc_18007D350
0x18007d42d  movzx   eax, [rbp+1A0h+var_168]
0x18007d431  mov     [rsi], eax
0x18007d433  movzx   eax, [rbp+1A0h+var_166]
0x18007d437  mov     [r14], eax
0x18007d43a  mov     dil, 1
0x18007d43d  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18007d444  mov     [rsp+2A0h+var_270], rax
0x18007d449  mov     rcx, [rsp+2A0h+hObject]; hObject
0x18007d44e  cmp     rcx, r12
0x18007d451  jz      short loc_18007D459
0x18007d453  call    cs:__imp_CloseHandle
0x18007d459  mov     [rsp+2A0h+hObject], r12
0x18007d45e  mov     [rsp+2A0h+var_270], r13
0x18007d463  mov     [rsp+2A0h+hObject], r12
0x18007d468  lea     rcx, [rsp+2A0h+NtPathName]; UnicodeString
0x18007d46d  call    cs:__imp_RtlFreeUnicodeString
0x18007d473  nop
0x18007d474  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007d47b  mov     [rbp+1A0h+var_F0], rax
0x18007d482  lea     rcx, [rbp+1A0h+var_F0]; this
0x18007d489  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007d48e  mov     al, dil
0x18007d491  mov     rcx, [rbp+1A0h+var_40]
0x18007d498  xor     rcx, rsp; StackCookie
0x18007d49b  call    __security_check_cookie
0x18007d4a0  mov     rbx, [rsp+2A0h+arg_18]
0x18007d4a8  add     rsp, 270h
0x18007d4af  pop     r15
0x18007d4b1  pop     r14
0x18007d4b3  pop     r13
0x18007d4b5  pop     r12
0x18007d4b7  pop     rdi
0x18007d4b8  pop     rsi
0x18007d4b9  pop     rbp
0x18007d4ba  retn
```
