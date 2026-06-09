# CreateDevice(ushort const *,ushort const *,ulong,int,CreateStorageDeviceFlags,_GUID const *,char const *,ulong,_GUID const *)

- ea: `0x140097018`
- end: `0x1400974ac`
- name: `?CreateDevice@@YAPEAXPEBG0KHW4CreateStorageDeviceFlags@@PEBU_GUID@@PEBDK2@Z`
- size: `1172`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140096bc8`
- `0x1400974e0`

## callees

- `0x140096da8`
- `0x140097018`
- `0x1400974b4`
- `0x14011ea40`
- `0x14011f6fc`
- `0x140121a35`
- `0x1401a5b20`
- `0x1401a5cdc`
- `0x1401a6490`
- `0x1401a68b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14009743f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14009743f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140097218`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140097218`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14009744d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14009744d`
- `ntdll!RtlNtStatusToDosError` at `0x140097168`
- `ntdll!RtlNtStatusToDosError` at `0x14009729e`
- `ntdll!RtlNtStatusToDosError` at `0x1400973f9`
- `ntdll!RtlNtStatusToDosError` at `0x140097168`
- `ntdll!RtlNtStatusToDosError` at `0x14009729e`
- `ntdll!RtlNtStatusToDosError` at `0x1400973f9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140097156`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140097156`
- `ntdll!RtlFreeUnicodeString` at `0x140097427`
- `ntdll!RtlFreeUnicodeString` at `0x140097427`
- `ntdll!RtlInitUnicodeStringEx` at `0x14009728c`
- `ntdll!RtlInitUnicodeStringEx` at `0x14009728c`
- `ntdll!NtCreateFile` at `0x1400973ac`
- `ntdll!NtCreateFile` at `0x1400973ac`

## string_xrefs

- `0x140097331`: `VstorCreateDevice_CreateFile`
- `0x1400970be`: `VstorCreateDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall CreateDevice(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        struct _GUID *a6,
        char *a7,
        unsigned int a8,
        struct _GUID *a9)
{
  char *v13; // r15
  __int64 v14; // rdi
  signed int v15; // ebx
  unsigned int v16; // r12d
  const wchar_t *v17; // r13
  int inited; // eax
  PWSTR Buffer; // r14
  __int16 v20; // cx
  int v21; // eax
  __int64 v22; // rbx
  size_t v23; // rbx
  char *v24; // rsi
  __int64 v25; // rbx
  int v26; // edi
  void *v27; // rbx
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-88h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  int EaBuffer; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v35; // [rsp+C4h] [rbp-3Ch]
  struct _GUID v36; // [rsp+D4h] [rbp-2Ch]
  __int64 v37; // [rsp+E4h] [rbp-1Ch]
  _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v40[42]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v41[42]; // [rsp+260h] [rbp+160h] BYREF

  FileHandle = (void *)-1LL;
  UnicodeString = 0;
  v13 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  EaBuffer = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  memset_0(v40, 0, sizeof(v40));
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v40);
  v40[0] = &VstorlibTraceProvider::VstorCreateDevice::`vftable';
  VstorlibTraceProvider::VstorCreateDevice::StartActivity(
    (VstorlibTraceProvider::VstorCreateDevice *)v40,
    a1,
    (const unsigned __int16 *)a2,
    a3,
    a4,
    a5,
    a6,
    a7,
    a8,
    a9);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a2 + 2 * v14) );
  if ( !v14 )
  {
    v15 = 87;
    goto LABEL_37;
  }
  v16 = 0;
  v17 = 0;
  if ( a4 )
  {
    inited = RtlDosPathNameToNtPathName_U_WithStatus(a2, &UnicodeString, 0, 0);
    if ( inited < 0 )
    {
LABEL_27:
      v15 = RtlNtStatusToDosError(inited);
      goto LABEL_37;
    }
    LODWORD(v14) = UnicodeString.Length >> 1;
    Buffer = UnicodeString.Buffer;
  }
  else if ( (unsigned int)v14 > 2 && *(_WORD *)a2 == 92 && (Buffer = (PWSTR)(a2 + 2), *(_WORD *)(a2 + 2) == 92) )
  {
    v20 = *(_WORD *)(a2 + 4);
    v21 = v14 - 1;
    if ( v20 == 63 )
      v21 = v14;
    LODWORD(v14) = v21;
    if ( v20 == 63 )
      Buffer = (PWSTR)a2;
    v16 = v20 != 63 ? 7 : 0;
    v17 = L"\\\\?\\UNC";
    if ( v20 == 63 )
      v17 = 0;
  }
  else
  {
    Buffer = (PWSTR)a2;
    if ( (unsigned int)v14 > 0x104 )
    {
      v16 = 4;
      v17 = L"\\\\?\\";
    }
  }
  v22 = -1;
  do
    ++v22;
  while ( a1[v22] );
  v13 = (char *)malloc(saturated_mul((unsigned int)v22 + v16 + (_DWORD)v14 + 1, 2u));
  if ( !v13 )
  {
    v15 = 14;
    goto LABEL_37;
  }
  v23 = 2LL * (unsigned int)v22;
  memcpy_0(v13, a1, v23);
  v24 = &v13[v23];
  if ( v16 )
  {
    memcpy_0(v24, v17, 2LL * v16);
    v24 += 2 * v16;
  }
  memcpy_0(v24, Buffer, 2LL * (unsigned int)v14);
  *(_WORD *)&v24[2 * (unsigned int)v14] = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)v13);
  if ( inited < 0 )
    goto LABEL_27;
  BYTE1(v35) = 10;
  WORD1(v35) = 25;
  *(_QWORD *)((char *)&v35 + 4) = *(_QWORD *)"StorVsp-v2";
  *(_DWORD *)((char *)&v35 + 11) = *(_DWORD *)"-v2";
  HIDWORD(v37) = a5;
  if ( a6 )
  {
    v36 = *a6;
    LOBYTE(v37) = 1;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  memset_0(v41, 0, sizeof(v41));
  v25 = v40[34];
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v41);
  v41[0] = &VstorlibTraceProvider::VstorCreateDevice_CreateFile::`vftable';
  VstorlibTraceProvider::VstorCreateDevice_CreateFile::StartActivity(
    (VstorlibTraceProvider::VstorCreateDevice_CreateFile *)v41,
    &DestinationString,
    a6,
    (const struct _GUID *)(v25 + 8));
  v26 = NtCreateFile(&FileHandle, a3, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 2u, 0x40u, &EaBuffer, 0x2Cu);
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v41,
    (v26 | 0x10000000) & (unsigned int)-(v26 != 0));
  VstorlibTraceProvider::VstorCreateDevice_CreateFile::~VstorCreateDevice_CreateFile((VstorlibTraceProvider::VstorCreateDevice_CreateFile *)v41);
  if ( v26 >= 0 )
  {
    v15 = 0;
  }
  else if ( v26 == -1073741808 || v26 == -1073741766 )
  {
    v15 = -1069940716;
  }
  else
  {
    v15 = RtlNtStatusToDosError(v26);
    if ( v15 == 317 )
      v15 = v26;
  }
LABEL_37:
  if ( UnicodeString.Buffer )
  {
    RtlFreeUnicodeString(&UnicodeString);
    UnicodeString.Buffer = 0;
  }
  if ( v13 )
    free(v13);
  SetLastError(v15);
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v40, (unsigned int)v15);
  v27 = FileHandle;
  VstorlibTraceProvider::VstorCreateDevice::~VstorCreateDevice((VstorlibTraceProvider::VstorCreateDevice *)v40);
  return v27;
}

```

## disassembly

```asm
0x140097018  mov     [rsp-8+arg_18], rbx
0x14009701d  push    rbp
0x14009701e  push    rsi
0x14009701f  push    rdi
0x140097020  push    r12
0x140097022  push    r13
0x140097024  push    r14
0x140097026  push    r15
0x140097028  lea     rbp, [rsp-2C0h]
0x140097030  sub     rsp, 3C0h
0x140097037  mov     rax, cs:__security_cookie
0x14009703e  xor     rax, rsp
0x140097041  mov     [rbp+2F0h+var_40], rax
0x140097048  mov     r14d, r9d
0x14009704b  mov     r13d, r8d
0x14009704e  mov     [rsp+3F0h+DesiredAccess], r8d
0x140097053  mov     rsi, rdx
0x140097056  mov     r12, rcx
0x140097059  mov     [rsp+3F0h+Src], rcx
0x14009705e  mov     rdi, [rbp+2F0h+arg_28]
0x140097065  mov     [rsp+3F0h+var_380], rdi
0x14009706a  mov     rbx, [rbp+2F0h+arg_30]
0x140097071  mov     [rbp+2F0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x140097079  xorps   xmm0, xmm0
0x14009707c  movups  xmmword ptr [rsp+3F0h+UnicodeString.Length], xmm0
0x140097081  xor     eax, eax
0x140097083  mov     r15d, eax
0x140097086  movups  xmmword ptr [rbp+2F0h+DestinationString.Length], xmm0
0x14009708a  xorps   xmm1, xmm1
0x14009708d  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.Length], xmm1
0x140097091  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.ObjectName], xmm1
0x140097095  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x140097099  movups  xmmword ptr [rbp+2F0h+IoStatusBlock], xmm0
0x14009709d  mov     [rbp+2F0h+var_330], eax
0x1400970a0  movups  [rbp+2F0h+var_32C], xmm1
0x1400970a4  movups  [rbp+2F0h+var_31C], xmm1
0x1400970a8  mov     [rbp+2F0h+var_30C], rax
0x1400970ac  xor     edx, edx; Val
0x1400970ae  mov     r8d, 150h; Size
0x1400970b4  lea     rcx, [rbp+2F0h+var_2E0]; void *
0x1400970b8  call    memset_0
0x1400970bd  nop
0x1400970be  lea     rdx, aVstorcreatedev_2; "VstorCreateDevice"
0x1400970c5  lea     rcx, [rbp+2F0h+var_2E0]; struct wil::details::IFailureCallback *
0x1400970c9  call    ??0?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400970ce  lea     rax, ??_7VstorCreateDevice@VstorlibTraceProvider@@6B@; const VstorlibTraceProvider::VstorCreateDevice::`vftable'
0x1400970d5  mov     [rbp+2F0h+var_2E0], rax
0x1400970d9  mov     rax, [rbp+2F0h+arg_40]
0x1400970e0  mov     [rsp+3F0h+EaBuffer], rax; struct _GUID *
0x1400970e5  mov     eax, [rbp+2F0h+arg_38]
0x1400970eb  mov     [rsp+3F0h+CreateOptions], eax; unsigned int
0x1400970ef  mov     qword ptr [rsp+3F0h+CreateDisposition], rbx; char *
0x1400970f4  mov     qword ptr [rsp+3F0h+ShareAccess], rdi; struct _GUID *
0x1400970f9  mov     eax, [rbp+2F0h+arg_20]
0x1400970ff  mov     [rsp+3F0h+FileAttributes], eax; unsigned int
0x140097103  mov     dword ptr [rsp+3F0h+AllocationSize], r14d; int
0x140097108  mov     r9d, r13d; unsigned int
0x14009710b  mov     r8, rsi; unsigned __int16 *
0x14009710e  mov     rdx, r12; unsigned __int16 *
0x140097111  lea     rcx, [rbp+2F0h+var_2E0]; this
0x140097115  call    ?StartActivity@VstorCreateDevice@VstorlibTraceProvider@@QEAAXPEBG0KHIPEBU_GUID@@PEBDK1@Z; VstorlibTraceProvider::VstorCreateDevice::StartActivity(ushort const *,ushort const *,ulong,int,uint,_GUID const *,char const *,ulong,_GUID const *)
0x14009711a  nop
0x14009711b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14009711f  mov     rdi, r8
0x140097122  xor     ebx, ebx
0x140097124  inc     rdi
0x140097127  cmp     [rsi+rdi*2], bx
0x14009712b  jnz     short loc_140097124
0x14009712d  test    rdi, rdi
0x140097130  jnz     short loc_14009713D
0x140097132  lea     ebx, [rdi+57h]
0x140097135  xor     r14d, r14d
0x140097138  jmp     loc_14009741C
0x14009713d  mov     r12d, ebx
0x140097140  mov     r13, rbx
0x140097143  test    r14d, r14d
0x140097146  jz      short loc_140097189
0x140097148  xor     r9d, r9d
0x14009714b  xor     r8d, r8d
0x14009714e  lea     rdx, [rsp+3F0h+UnicodeString]
0x140097153  mov     rcx, rsi
0x140097156  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14009715d  nop     dword ptr [rax+rax+00h]
0x140097162  test    eax, eax
0x140097164  jns     short loc_140097178
0x140097166  mov     ecx, eax; Status
0x140097168  call    cs:__imp_RtlNtStatusToDosError
0x14009716f  nop     dword ptr [rax+rax+00h]
0x140097174  mov     ebx, eax
0x140097176  jmp     short loc_140097135
0x140097178  movzx   edi, [rsp+3F0h+UnicodeString.Length]
0x14009717d  shr     edi, 1
0x14009717f  mov     r14, [rbp+2F0h+UnicodeString.Buffer]
0x140097183  or      r8, 0FFFFFFFFFFFFFFFFh
0x140097187  jmp     short loc_1400971EE
0x140097189  cmp     edi, 2
0x14009718c  jbe     short loc_1400971D6
0x14009718e  cmp     word ptr [rsi], 5Ch ; '\'
0x140097192  jnz     short loc_1400971D6
0x140097194  lea     r14, [rsi+2]
0x140097198  cmp     word ptr [r14], 5Ch ; '\'
0x14009719d  jnz     short loc_1400971D6
0x14009719f  movzx   ecx, word ptr [rsi+4]
0x1400971a3  lea     eax, [rdi-1]
0x1400971a6  mov     dx, 3Fh ; '?'
0x1400971aa  cmp     cx, dx
0x1400971ad  cmovz   eax, edi
0x1400971b0  mov     edi, eax
0x1400971b2  cmovz   r14, rsi
0x1400971b6  movzx   eax, cx
0x1400971b9  sub     ax, dx
0x1400971bc  neg     ax
0x1400971bf  sbb     r12d, r12d
0x1400971c2  and     r12d, 7
0x1400971c6  lea     r13, aUnc; "\\\\?\\UNC"
0x1400971cd  cmp     cx, dx
0x1400971d0  cmovz   r13, rbx
0x1400971d4  jmp     short loc_1400971EE
0x1400971d6  mov     r14, rsi
0x1400971d9  cmp     edi, 104h
0x1400971df  jbe     short loc_1400971EE
0x1400971e1  mov     r12d, 4
0x1400971e7  lea     r13, asc_140311EC8; "\\\\?\\"
0x1400971ee  mov     rbx, r8
0x1400971f1  mov     rsi, [rsp+3F0h+Src]
0x1400971f6  xor     eax, eax
0x1400971f8  inc     rbx
0x1400971fb  cmp     [rsi+rbx*2], ax
0x1400971ff  jnz     short loc_1400971F8
0x140097201  lea     edx, [rdi+1]
0x140097204  add     edx, r12d
0x140097207  add     edx, ebx
0x140097209  mov     eax, 2
0x14009720e  mul     rdx
0x140097211  cmovb   rax, r8
0x140097215  mov     rcx, rax; Size
0x140097218  call    cs:__imp_malloc
0x14009721f  nop     dword ptr [rax+rax+00h]
0x140097224  mov     r15, rax
0x140097227  test    rax, rax
0x14009722a  jnz     short loc_140097234
0x14009722c  lea     ebx, [rax+0Eh]
0x14009722f  jmp     loc_140097135
0x140097234  mov     eax, ebx
0x140097236  lea     rbx, [rax+rax]
0x14009723a  mov     r8, rbx; Size
0x14009723d  mov     rdx, rsi; Src
0x140097240  mov     rcx, r15; void *
0x140097243  call    memcpy_0
0x140097248  lea     rsi, [rbx+r15]
0x14009724c  test    r12d, r12d
0x14009724f  jz      short loc_140097269
0x140097251  mov     eax, r12d
0x140097254  lea     rbx, [rax+rax]
0x140097258  mov     r8, rbx; Size
0x14009725b  mov     rdx, r13; Src
0x14009725e  mov     rcx, rsi; void *
0x140097261  call    memcpy_0
0x140097266  add     rsi, rbx
0x140097269  mov     eax, edi
0x14009726b  lea     rbx, [rax+rax]
0x14009726f  mov     r8, rbx; Size
0x140097272  mov     rdx, r14; Src
0x140097275  mov     rcx, rsi; void *
0x140097278  call    memcpy_0
0x14009727d  xor     r14d, r14d
0x140097280  mov     [rbx+rsi], r14w
0x140097285  mov     rdx, r15; SourceString
0x140097288  lea     rcx, [rbp+2F0h+DestinationString]; DestinationString
0x14009728c  call    cs:__imp_RtlInitUnicodeStringEx
0x140097293  nop     dword ptr [rax+rax+00h]
0x140097298  test    eax, eax
0x14009729a  jns     short loc_1400972B1
0x14009729c  mov     ecx, eax; Status
0x14009729e  call    cs:__imp_RtlNtStatusToDosError
0x1400972a5  nop     dword ptr [rax+rax+00h]
0x1400972aa  mov     ebx, eax
0x1400972ac  jmp     loc_14009741C
0x1400972b1  mov     byte ptr [rbp+2F0h+var_32C+1], 0Ah
0x1400972b5  mov     eax, 19h
0x1400972ba  mov     word ptr [rbp+2F0h+var_32C+2], ax
0x1400972be  movsd   xmm0, qword ptr cs:aStorvspV2; "StorVsp-v2"
0x1400972c6  movsd   qword ptr [rbp+2F0h+var_32C+4], xmm0
0x1400972cb  mov     eax, dword ptr cs:aStorvspV2+7; "-v2"
0x1400972d1  mov     dword ptr [rbp+2F0h+var_32C+0Bh], eax
0x1400972d4  mov     eax, [rbp+2F0h+arg_20]
0x1400972da  mov     dword ptr [rbp+2F0h+var_30C+4], eax
0x1400972dd  mov     rdi, [rsp+3F0h+var_380]
0x1400972e2  test    rdi, rdi
0x1400972e5  jz      short loc_1400972F3
0x1400972e7  movups  xmm0, xmmword ptr [rdi]
0x1400972ea  movdqu  [rbp+2F0h+var_31C], xmm0
0x1400972ef  mov     byte ptr [rbp+2F0h+var_30C], 1
0x1400972f3  mov     [rbp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x1400972fa  mov     [rbp+2F0h+ObjectAttributes.RootDirectory], r14
0x1400972fe  mov     esi, 40h ; '@'
0x140097303  mov     [rbp+2F0h+ObjectAttributes.Attributes], esi
0x140097306  lea     rax, [rbp+2F0h+DestinationString]
0x14009730a  mov     [rbp+2F0h+ObjectAttributes.ObjectName], rax
0x14009730e  xorps   xmm0, xmm0
0x140097311  movdqu  xmmword ptr [rbp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140097316  xor     edx, edx; Val
0x140097318  mov     r8d, 150h; Size
0x14009731e  lea     rcx, [rbp+2F0h+var_190]; void *
0x140097325  call    memset_0
0x14009732a  mov     rbx, [rbp+2F0h+var_1D0]
0x140097331  lea     rdx, aVstorcreatedev_1; "VstorCreateDevice_CreateFile"
0x140097338  lea     rcx, [rbp+2F0h+var_190]; struct wil::details::IFailureCallback *
0x14009733f  call    ??0?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140097344  lea     rax, ??_7VstorCreateDevice_CreateFile@VstorlibTraceProvider@@6B@; const VstorlibTraceProvider::VstorCreateDevice_CreateFile::`vftable'
0x14009734b  mov     [rbp+2F0h+var_190], rax
0x140097352  lea     r9, [rbx+8]; struct _GUID *
0x140097356  mov     r8, rdi; struct _GUID *
0x140097359  lea     rdx, [rbp+2F0h+DestinationString]; struct _UNICODE_STRING *
0x14009735d  lea     rcx, [rbp+2F0h+var_190]; this
0x140097364  call    ?StartActivity@VstorCreateDevice_CreateFile@VstorlibTraceProvider@@QEAAXAEAU_UNICODE_STRING@@PEBU_GUID@@1@Z; VstorlibTraceProvider::VstorCreateDevice_CreateFile::StartActivity(_UNICODE_STRING &,_GUID const *,_GUID const *)
0x140097369  nop
0x14009736a  mov     [rsp+3F0h+EaLength], 2Ch ; ','; EaLength
0x140097372  lea     rax, [rbp+2F0h+var_330]
0x140097376  mov     [rsp+3F0h+EaBuffer], rax; EaBuffer
0x14009737b  mov     [rsp+3F0h+CreateOptions], esi; CreateOptions
0x14009737f  mov     [rsp+3F0h+CreateDisposition], 2; CreateDisposition
0x140097387  mov     [rsp+3F0h+ShareAccess], 7; ShareAccess
0x14009738f  mov     [rsp+3F0h+FileAttributes], 80h; FileAttributes
0x140097397  mov     [rsp+3F0h+AllocationSize], r14; AllocationSize
0x14009739c  lea     r9, [rbp+2F0h+IoStatusBlock]; IoStatusBlock
0x1400973a0  lea     r8, [rbp+2F0h+ObjectAttributes]; ObjectAttributes
0x1400973a4  mov     edx, [rsp+3F0h+DesiredAccess]; DesiredAccess
0x1400973a8  lea     rcx, [rbp+2F0h+FileHandle]; FileHandle
0x1400973ac  call    cs:__imp_NtCreateFile
0x1400973b3  nop     dword ptr [rax+rax+00h]
0x1400973b8  mov     edi, eax
0x1400973ba  mov     ecx, eax
0x1400973bc  mov     r8d, eax
0x1400973bf  bts     r8d, 1Ch
0x1400973c4  neg     ecx
0x1400973c6  sbb     edx, edx
0x1400973c8  and     edx, r8d
0x1400973cb  lea     rcx, [rbp+2F0h+var_190]
0x1400973d2  call    ?Stop@?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400973d7  lea     rcx, [rbp+2F0h+var_190]; this
0x1400973de  call    ??1VstorCreateDevice_CreateFile@VstorlibTraceProvider@@QEAA@XZ; VstorlibTraceProvider::VstorCreateDevice_CreateFile::~VstorCreateDevice_CreateFile(void)
0x1400973e3  test    edi, edi
0x1400973e5  jns     short loc_140097419
0x1400973e7  cmp     edi, 0C0000010h
0x1400973ed  jz      short loc_140097412
0x1400973ef  cmp     edi, 0C000003Ah
0x1400973f5  jz      short loc_140097412
0x1400973f7  mov     ecx, edi; Status
0x1400973f9  call    cs:__imp_RtlNtStatusToDosError
0x140097400  nop     dword ptr [rax+rax+00h]
0x140097405  mov     ebx, eax
0x140097407  cmp     eax, 13Dh
0x14009740c  jnz     short loc_14009741C
0x14009740e  mov     ebx, edi
0x140097410  jmp     short loc_14009741C
0x140097412  mov     ebx, 0C03A0014h
0x140097417  jmp     short loc_14009741C
0x140097419  mov     ebx, r14d
0x14009741c  cmp     [rbp+2F0h+UnicodeString.Buffer], r14
0x140097420  jz      short loc_140097437
0x140097422  lea     rcx, [rsp+3F0h+UnicodeString]; UnicodeString
0x140097427  call    cs:__imp_RtlFreeUnicodeString
0x14009742e  nop     dword ptr [rax+rax+00h]
0x140097433  mov     [rbp+2F0h+UnicodeString.Buffer], r14
0x140097437  test    r15, r15
0x14009743a  jz      short loc_14009744B
0x14009743c  mov     rcx, r15; Block
0x14009743f  call    cs:__imp_free
0x140097446  nop     dword ptr [rax+rax+00h]
0x14009744b  mov     ecx, ebx; dwErrCode
0x14009744d  call    cs:__imp_SetLastError
0x140097454  nop     dword ptr [rax+rax+00h]
0x140097459  test    ebx, ebx
0x14009745b  jle     short loc_140097466
0x14009745d  movzx   ebx, bx
0x140097460  or      ebx, 80070000h
0x140097466  mov     edx, ebx
0x140097468  lea     rcx, [rbp+2F0h+var_2E0]
0x14009746c  call    ?Stop@?$ActivityBase@VVstorlibTraceProvider@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VstorlibTraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140097471  mov     rbx, [rbp+2F0h+FileHandle]
0x140097475  lea     rcx, [rbp+2F0h+var_2E0]; this
0x140097479  call    ??1VstorCreateDevice@VstorlibTraceProvider@@QEAA@XZ; VstorlibTraceProvider::VstorCreateDevice::~VstorCreateDevice(void)
0x14009747e  mov     rax, rbx
0x140097481  mov     rcx, [rbp+2F0h+var_40]
0x140097488  xor     rcx, rsp; StackCookie
0x14009748b  call    __security_check_cookie
0x140097490  mov     rbx, [rsp+3F0h+arg_18]
0x140097498  add     rsp, 3C0h
0x14009749f  pop     r15
0x1400974a1  pop     r14
0x1400974a3  pop     r13
0x1400974a5  pop     r12
0x1400974a7  pop     rdi
0x1400974a8  pop     rsi
0x1400974a9  pop     rbp
0x1400974aa  retn
```
