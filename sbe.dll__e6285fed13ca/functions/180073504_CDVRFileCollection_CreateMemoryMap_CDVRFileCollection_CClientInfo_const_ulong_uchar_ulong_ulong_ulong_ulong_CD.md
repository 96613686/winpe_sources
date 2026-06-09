# CDVRFileCollection::CreateMemoryMap(CDVRFileCollection::CClientInfo const *,ulong,uchar *,ulong,ulong &,ulong,ulong,CDVRFileCollection::CSharedData * &,void * *,void * *)

- ea: `0x180073504`
- end: `0x1800739ef`
- name: `?CreateMemoryMap@CDVRFileCollection@@IEAAJPEBUCClientInfo@1@KPEAEKAEAKKKAEAPEAUCSharedData@1@PEAPEAX4@Z`
- size: `1259`
- prototype: `int(CDVRFileCollection *__hidden this, const struct CDVRFileCollection::CClientInfo *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int, unsigned int, struct CDVRFileCollection::CSharedData **, void **, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180070c30`
- `0x180072028`

## callees

- `0x180001c00`
- `0x180073368`
- `0x180073504`
- `0x180073bd8`
- `0x180073ebc`
- `0x1800b33ed`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180073828`
- `KERNEL32!CloseHandle` at `0x18007394b`
- `KERNEL32!CloseHandle` at `0x180073959`
- `KERNEL32!CloseHandle` at `0x18007396c`
- `KERNEL32!CloseHandle` at `0x180073988`
- `KERNEL32!CloseHandle` at `0x1800b519a`
- `KERNEL32!CloseHandle` at `0x1800b51aa`
- `KERNEL32!CloseHandle` at `0x1800b51c7`
- `KERNEL32!CloseHandle` at `0x1800b51e9`
- `KERNEL32!CloseHandle` at `0x180073828`
- `KERNEL32!CloseHandle` at `0x18007394b`
- `KERNEL32!CloseHandle` at `0x180073959`
- `KERNEL32!CloseHandle` at `0x18007396c`
- `KERNEL32!CloseHandle` at `0x180073988`
- `KERNEL32!CloseHandle` at `0x1800b519a`
- `KERNEL32!CloseHandle` at `0x1800b51aa`
- `KERNEL32!CloseHandle` at `0x1800b51c7`
- `KERNEL32!CloseHandle` at `0x1800b51e9`
- `KERNEL32!GetLastError` at `0x180073626`
- `KERNEL32!GetLastError` at `0x18007368c`
- `KERNEL32!GetLastError` at `0x1800737e3`
- `KERNEL32!GetLastError` at `0x180073879`
- `KERNEL32!GetLastError` at `0x180073626`
- `KERNEL32!GetLastError` at `0x18007368c`
- `KERNEL32!GetLastError` at `0x1800737e3`
- `KERNEL32!GetLastError` at `0x180073879`
- `KERNEL32!GetFileInformationByHandle` at `0x180073682`
- `KERNEL32!GetFileInformationByHandle` at `0x180073682`
- `KERNEL32!MapViewOfFile` at `0x180073863`
- `KERNEL32!MapViewOfFile` at `0x180073863`
- `KERNEL32!CreateFileMappingW` at `0x1800737d8`
- `KERNEL32!CreateFileMappingW` at `0x1800737d8`
- `KERNEL32!UnmapViewOfFile` at `0x18007393d`
- `KERNEL32!UnmapViewOfFile` at `0x1800b518a`
- `KERNEL32!UnmapViewOfFile` at `0x18007393d`
- `KERNEL32!UnmapViewOfFile` at `0x1800b518a`
- `KERNEL32!DeleteFileW` at `0x1800739af`
- `KERNEL32!DeleteFileW` at `0x1800b520d`
- `KERNEL32!DeleteFileW` at `0x1800739af`
- `KERNEL32!DeleteFileW` at `0x1800b520d`
- `KERNEL32!CreateFileW` at `0x180073612`
- `KERNEL32!CreateFileW` at `0x180073612`

## pseudocode

```c
__int64 __fastcall CDVRFileCollection::CreateMemoryMap(
        LPCWSTR *this,
        const struct CDVRFileCollection::CClientInfo *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int *a6,
        DWORD a7,
        DWORD a8,
        struct CDVRFileCollection::CSharedData **a9,
        void **a10,
        void **a11)
{
  size_t v11; // r12
  void *v13; // r14
  struct CDVRFileCollection::CSharedData *v14; // rdi
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int SectionName; // ebx
  enum _ACCESS_MODE v18; // r8d
  signed int v19; // eax
  int v20; // r14d
  ULONG v21; // ecx
  int v22; // eax
  unsigned int *v23; // rax
  struct _SECURITY_ATTRIBUTES *v24; // rdx
  signed int v25; // eax
  HANDLE *v26; // r13
  volatile __int32 *v27; // rax
  signed int v28; // eax
  enum _ACCESS_MODE dwCreationDisposition; // [rsp+20h] [rbp-1B8h]
  unsigned int dwFlagsAndAttributes; // [rsp+28h] [rbp-1B0h]
  HANDLE FileMappingW; // [rsp+48h] [rbp-190h]
  int v33; // [rsp+58h] [rbp-180h]
  void *v34; // [rsp+60h] [rbp-178h] BYREF
  HANDLE v35; // [rsp+68h] [rbp-170h]
  int v36; // [rsp+70h] [rbp-168h]
  DWORD v37; // [rsp+74h] [rbp-164h]
  DWORD v38; // [rsp+78h] [rbp-160h]
  volatile __int32 *v39; // [rsp+80h] [rbp-158h]
  CDVRFileCollection *v40; // [rsp+88h] [rbp-150h]
  unsigned int *v41; // [rsp+90h] [rbp-148h]
  void *Buf1; // [rsp+98h] [rbp-140h]
  struct CDVRFileCollection::CSharedData **v43; // [rsp+A0h] [rbp-138h]
  void **v44; // [rsp+A8h] [rbp-130h]
  void **v45; // [rsp+B0h] [rbp-128h]
  LPCWSTR *v46; // [rsp+B8h] [rbp-120h]
  struct _ACL *v47; // [rsp+C0h] [rbp-118h] BYREF
  __int128 v48; // [rsp+C8h] [rbp-110h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-100h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+E0h] [rbp-F8h] BYREF
  WCHAR Name[64]; // [rsp+120h] [rbp-B8h] BYREF

  Buf1 = a4;
  v11 = a3;
  v40 = (CDVRFileCollection *)this;
  v46 = this;
  v41 = a6;
  v37 = a7;
  v38 = a7;
  v43 = a9;
  v44 = a10;
  v45 = a11;
  v35 = 0;
  v13 = 0;
  FileMappingW = 0;
  v14 = 0;
  v39 = 0;
  v33 = 0;
  *a9 = 0;
  if ( a11 )
    *a11 = (void *)-1LL;
  *a10 = 0;
  FileW = CreateFileW(this[14], 0xC0000000, 7u, 0, a7, a8, 0);
  v35 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    SectionName = LastError;
    if ( LastError > 0 )
      SectionName = (unsigned __int16)LastError | 0x80070000;
    FileW = 0;
    v35 = 0;
  }
  else
  {
    v33 = 1;
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
    {
      if ( FileInformation.nFileSizeHigh || FileInformation.nFileSizeLow != (_DWORD)v11 )
      {
        SectionName = -2147467259;
      }
      else
      {
        v20 = 0;
        v36 = 0;
        v47 = 0;
        v34 = 0;
        v48 = 0;
        v49 = 0;
        v21 = *((_DWORD *)a2 + 4);
        if ( !v21 )
          goto LABEL_19;
        v22 = CreateACL(v21, *((void ***)a2 + 3), v18, 0xF0017u, dwCreationDisposition, 7u, &v47, &v34);
        SectionName = v22;
        if ( v22 )
        {
          if ( v22 > 0 )
            SectionName = (unsigned __int16)v22 | 0x80070000;
        }
        else
        {
          LODWORD(v48) = 24;
          *((_QWORD *)&v48 + 1) = v34;
          LODWORD(v49) = 0;
LABEL_19:
          while ( 1 )
          {
            v23 = v41;
            ++*v41;
            SectionName = CDVRFileCollection::CreateSectionName(
                            v40,
                            FileInformation.dwVolumeSerialNumber,
                            FileInformation.nFileIndexHigh,
                            FileInformation.nFileIndexLow,
                            *v23,
                            dwFlagsAndAttributes,
                            Name);
            if ( SectionName < 0 )
              break;
            v24 = (struct _SECURITY_ATTRIBUTES *)&v48;
            if ( !*((_DWORD *)a2 + 4) )
              v24 = 0;
            FileMappingW = CreateFileMappingW(FileW, v24, 4u, 0, a5, Name);
            v25 = GetLastError();
            SectionName = v25;
            if ( FileMappingW && v25 != 183 )
            {
              if ( *((_DWORD *)a2 + 4) )
                FreeSecurityDescriptors(&v47, &v34);
              if ( a11 )
                *a11 = FileW;
              else
                CloseHandle(FileW);
              FileW = 0;
              v35 = 0;
              v26 = a10;
              *a10 = FileMappingW;
              v13 = 0;
              v27 = (volatile __int32 *)MapViewOfFile(*a10, 0xF001Fu, 0, 0, a5);
              v14 = (struct CDVRFileCollection::CSharedData *)v27;
              v39 = v27;
              if ( v27 )
              {
                if ( (_DWORD)v11 )
                {
                  if ( memcmp_0(Buf1, (const void *)v27, v11) )
                  {
                    SectionName = -2147467259;
                    goto LABEL_48;
                  }
                }
                else
                {
                  _InterlockedExchange(v27 + 20, 0);
                }
                *v43 = v14;
                v14 = 0;
                v39 = 0;
                SectionName = 0;
              }
              else
              {
                v28 = GetLastError();
                SectionName = v28;
                if ( v28 > 0 )
                  SectionName = (unsigned __int16)v28 | 0x80070000;
              }
              goto LABEL_48;
            }
            if ( v25 > 0 )
              SectionName = (unsigned __int16)v25 | 0x80070000;
            v36 = ++v20;
            if ( v20 == 20 )
            {
              if ( *((_DWORD *)a2 + 4) )
                FreeSecurityDescriptors(&v47, &v34);
              break;
            }
          }
        }
        v13 = FileMappingW;
      }
    }
    else
    {
      v19 = GetLastError();
      SectionName = v19;
      if ( v19 > 0 )
        SectionName = (unsigned __int16)v19 | 0x80070000;
    }
  }
  v26 = a10;
LABEL_48:
  if ( v14 )
    UnmapViewOfFile(v14);
  if ( v13 )
    CloseHandle(v13);
  if ( FileW )
    CloseHandle(FileW);
  if ( SectionName < 0 )
  {
    if ( *v26 )
    {
      CloseHandle(*v26);
      *v26 = 0;
    }
    if ( a11 && *a11 != (void *)-1LL )
    {
      CloseHandle(*a11);
      *a11 = (void *)-1LL;
    }
    if ( v37 == 1 && v33 )
      DeleteFileW(*((LPCWSTR *)v40 + 14));
  }
  return (unsigned int)SectionName;
}

```

## disassembly

```asm
0x180073504  mov     [rsp+arg_10], rbx
0x180073509  mov     [rsp+arg_18], rsi
0x18007350e  push    rdi
0x18007350f  push    r12
0x180073511  push    r13
0x180073513  push    r14
0x180073515  push    r15
0x180073517  sub     rsp, 1B0h
0x18007351e  mov     rax, cs:__security_cookie
0x180073525  xor     rax, rsp
0x180073528  mov     [rsp+1D8h+var_38], rax
0x180073530  mov     [rsp+1D8h+Buf1], r9
0x180073538  mov     r12d, r8d
0x18007353b  mov     r13, rdx
0x18007353e  mov     r10, rcx
0x180073541  mov     [rsp+1D8h+var_150], rcx
0x180073549  mov     [rsp+1D8h+var_120], rcx
0x180073551  mov     eax, [rsp+1D8h+arg_20]
0x180073558  mov     [rsp+1D8h+dwMaximumSizeLow], eax
0x18007355c  mov     rax, [rsp+1D8h+arg_28]
0x180073564  mov     [rsp+1D8h+var_148], rax
0x18007356c  mov     r8d, [rsp+1D8h+arg_30]
0x180073574  mov     [rsp+1D8h+var_164], r8d
0x180073579  mov     [rsp+1D8h+var_160], r8d
0x18007357e  mov     eax, [rsp+1D8h+arg_38]
0x180073585  mov     rdx, [rsp+1D8h+arg_40]
0x18007358d  mov     [rsp+1D8h+var_138], rdx
0x180073595  mov     rcx, [rsp+1D8h+arg_48]
0x18007359d  mov     [rsp+1D8h+var_188], rcx
0x1800735a2  mov     [rsp+1D8h+var_130], rcx
0x1800735aa  mov     r15, [rsp+1D8h+arg_50]
0x1800735b2  mov     [rsp+1D8h+var_128], r15
0x1800735ba  xor     r9d, r9d
0x1800735bd  mov     [rsp+1D8h+var_198], r9d
0x1800735c2  mov     [rsp+1D8h+var_170], r9
0x1800735c7  mov     r14d, r9d
0x1800735ca  mov     [rsp+1D8h+var_190], r9
0x1800735cf  mov     edi, r9d
0x1800735d2  mov     [rsp+1D8h+var_158], r9
0x1800735da  mov     [rsp+1D8h+var_180], r9d
0x1800735df  mov     [rdx], r9
0x1800735e2  test    r15, r15
0x1800735e5  jz      short loc_1800735EE
0x1800735e7  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1800735ee  mov     [rcx], r9
0x1800735f1  mov     [rsp+1D8h+hTemplateFile], r9; hTemplateFile
0x1800735f6  mov     [rsp+1D8h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800735fa  mov     [rsp+1D8h+dwCreationDisposition], r8d; enum _ACCESS_MODE
0x1800735ff  xor     r9d, r9d; lpSecurityAttributes
0x180073602  lea     ebx, [r9+7]
0x180073606  mov     r8d, ebx; dwShareMode
0x180073609  mov     edx, 0C0000000h; dwDesiredAccess
0x18007360e  mov     rcx, [r10+70h]; lpFileName
0x180073612  call    cs:__imp_CreateFileW
0x180073618  mov     rsi, rax
0x18007361b  mov     [rsp+1D8h+var_170], rax
0x180073620  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180073624  jnz     short loc_18007364B
0x180073626  call    cs:__imp_GetLastError
0x18007362c  mov     ebx, eax
0x18007362e  test    eax, eax
0x180073630  jle     short loc_18007363B
0x180073632  movzx   ebx, ax
0x180073635  or      ebx, 80070000h
0x18007363b  mov     [rsp+1D8h+var_198], ebx
0x18007363f  xor     esi, esi
0x180073641  mov     [rsp+1D8h+var_170], rsi
0x180073646  jmp     loc_180073930
0x18007364b  mov     [rsp+1D8h+var_180], 1
0x180073653  xorps   xmm0, xmm0
0x180073656  xor     eax, eax
0x180073658  movups  xmmword ptr [rsp+1D8h+FileInformation.dwFileAttributes], xmm0
0x180073660  movups  xmmword ptr [rsp+1D8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180073668  movups  xmmword ptr [rsp+1D8h+FileInformation.nFileSizeHigh], xmm0
0x180073670  mov     [rsp+1D8h+FileInformation.nFileIndexLow], eax
0x180073677  lea     rdx, [rsp+1D8h+FileInformation]; lpFileInformation
0x18007367f  mov     rcx, rsi; hFile
0x180073682  call    cs:__imp_GetFileInformationByHandle
0x180073688  test    eax, eax
0x18007368a  jnz     short loc_1800736AA
0x18007368c  call    cs:__imp_GetLastError
0x180073692  mov     ebx, eax
0x180073694  test    eax, eax
0x180073696  jle     short loc_1800736A1
0x180073698  movzx   ebx, ax
0x18007369b  or      ebx, 80070000h
0x1800736a1  mov     [rsp+1D8h+var_198], ebx
0x1800736a5  jmp     loc_180073930
0x1800736aa  cmp     [rsp+1D8h+FileInformation.nFileSizeHigh], 0
0x1800736b2  ja      loc_180073921
0x1800736b8  cmp     [rsp+1D8h+FileInformation.nFileSizeLow], r12d
0x1800736c0  jnz     loc_180073921
0x1800736c6  xor     r14d, r14d
0x1800736c9  mov     [rsp+1D8h+var_168], r14d
0x1800736ce  mov     [rsp+1D8h+var_118], r14
0x1800736d6  mov     [rsp+1D8h+var_178], r14
0x1800736db  xorps   xmm0, xmm0
0x1800736de  xor     eax, eax
0x1800736e0  movups  [rsp+1D8h+var_110], xmm0
0x1800736e8  mov     [rsp+1D8h+var_100], rax
0x1800736f0  mov     ecx, [r13+10h]; cCountOfExplicitEntries
0x1800736f4  test    ecx, ecx
0x1800736f6  jz      short loc_18007375C
0x1800736f8  lea     rax, [rsp+1D8h+var_178]
0x1800736fd  mov     [rsp+1D8h+var_1A0], rax; void **
0x180073702  lea     rax, [rsp+1D8h+var_118]
0x18007370a  mov     [rsp+1D8h+hTemplateFile], rax; struct _ACL **
0x18007370f  mov     [rsp+1D8h+dwFlagsAndAttributes], ebx; unsigned int
0x180073713  mov     r9d, 0F0017h; unsigned int
0x180073719  mov     rdx, [r13+18h]; void **
0x18007371d  call    ?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z; CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)
0x180073722  mov     ebx, eax
0x180073724  test    eax, eax
0x180073726  jz      short loc_18007373C
0x180073728  jle     short loc_180073733
0x18007372a  movzx   ebx, ax
0x18007372d  or      ebx, 80070000h
0x180073733  mov     [rsp+1D8h+var_198], ebx
0x180073737  jmp     loc_18007392B
0x18007373c  mov     dword ptr [rsp+1D8h+var_110], 18h
0x180073747  mov     rax, [rsp+1D8h+var_178]
0x18007374c  mov     qword ptr [rsp+1D8h+var_110+8], rax
0x180073754  mov     dword ptr [rsp+1D8h+var_100], r14d
0x18007375c  mov     rax, [rsp+1D8h+var_148]
0x180073764  inc     dword ptr [rax]
0x180073766  mov     eax, [rax]
0x180073768  lea     rcx, [rsp+1D8h+Name]
0x180073770  mov     [rsp+1D8h+hTemplateFile], rcx; Buffer
0x180073775  mov     [rsp+1D8h+dwCreationDisposition], eax; unsigned int
0x180073779  mov     r9d, [rsp+1D8h+FileInformation.nFileIndexLow]; unsigned int
0x180073781  mov     r8d, [rsp+1D8h+FileInformation.nFileIndexHigh]; unsigned int
0x180073789  mov     edx, [rsp+1D8h+FileInformation.dwVolumeSerialNumber]; unsigned int
0x180073790  mov     rcx, [rsp+1D8h+var_150]; this
0x180073798  call    ?CreateSectionName@CDVRFileCollection@@AEAAJKKKKKPEAG@Z; CDVRFileCollection::CreateSectionName(ulong,ulong,ulong,ulong,ulong,ushort *)
0x18007379d  mov     ebx, eax
0x18007379f  test    eax, eax
0x1800737a1  js      loc_18007391B
0x1800737a7  lea     rdx, [rsp+1D8h+var_110]
0x1800737af  xor     eax, eax
0x1800737b1  cmp     [r13+10h], eax
0x1800737b5  cmovbe  rdx, rax; lpFileMappingAttributes
0x1800737b9  lea     rax, [rsp+1D8h+Name]
0x1800737c1  mov     qword ptr [rsp+1D8h+dwFlagsAndAttributes], rax; lpName
0x1800737c6  mov     eax, [rsp+1D8h+dwMaximumSizeLow]
0x1800737ca  mov     [rsp+1D8h+dwCreationDisposition], eax; dwMaximumSizeLow
0x1800737ce  xor     r9d, r9d; dwMaximumSizeHigh
0x1800737d1  lea     r8d, [r9+4]; flProtect
0x1800737d5  mov     rcx, rsi; hFile
0x1800737d8  call    cs:__imp_CreateFileMappingW
0x1800737de  mov     [rsp+1D8h+var_190], rax
0x1800737e3  call    cs:__imp_GetLastError
0x1800737e9  mov     ebx, eax
0x1800737eb  cmp     [rsp+1D8h+var_190], 0
0x1800737f1  jz      loc_1800738DD
0x1800737f7  cmp     eax, 0B7h
0x1800737fc  jz      loc_1800738DD
0x180073802  cmp     dword ptr [r13+10h], 0
0x180073807  jbe     short loc_18007381B
0x180073809  lea     rdx, [rsp+1D8h+var_178]; void **
0x18007380e  lea     rcx, [rsp+1D8h+var_118]; struct _ACL **
0x180073816  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x18007381b  test    r15, r15
0x18007381e  jz      short loc_180073825
0x180073820  mov     [r15], rsi
0x180073823  jmp     short loc_18007382E
0x180073825  mov     rcx, rsi; hObject
0x180073828  call    cs:__imp_CloseHandle
0x18007382e  xor     esi, esi
0x180073830  mov     [rsp+1D8h+var_170], rsi
0x180073835  mov     rax, [rsp+1D8h+var_190]
0x18007383a  mov     r13, [rsp+1D8h+var_188]
0x18007383f  mov     [r13+0], rax
0x180073843  xor     r14d, r14d
0x180073846  mov     [rsp+1D8h+var_190], r14
0x18007384b  mov     eax, [rsp+1D8h+dwMaximumSizeLow]
0x18007384f  mov     qword ptr [rsp+1D8h+dwCreationDisposition], rax; dwNumberOfBytesToMap
0x180073854  xor     r9d, r9d; dwFileOffsetLow
0x180073857  xor     r8d, r8d; dwFileOffsetHigh
0x18007385a  mov     edx, 0F001Fh; dwDesiredAccess
0x18007385f  mov     rcx, [r13+0]; hFileMappingObject
0x180073863  call    cs:__imp_MapViewOfFile
0x180073869  mov     rdi, rax
0x18007386c  mov     [rsp+1D8h+var_158], rax
0x180073874  test    rax, rax
0x180073877  jnz     short loc_180073897
0x180073879  call    cs:__imp_GetLastError
0x18007387f  mov     ebx, eax
0x180073881  test    eax, eax
0x180073883  jle     short loc_18007388E
0x180073885  movzx   ebx, ax
0x180073888  or      ebx, 80070000h
0x18007388e  mov     [rsp+1D8h+var_198], ebx
0x180073892  jmp     loc_180073935
0x180073897  test    r12d, r12d
0x18007389a  jz      short loc_1800738BF
0x18007389c  mov     r8, r12; Size
0x18007389f  mov     rdx, rdi; Buf2
0x1800738a2  mov     rcx, [rsp+1D8h+Buf1]; Buf1
0x1800738aa  call    memcmp_0
0x1800738af  test    eax, eax
0x1800738b1  jz      short loc_1800738BA
0x1800738b3  mov     ebx, 80004005h
0x1800738b8  jmp     short loc_18007388E
0x1800738ba  test    r12d, r12d
0x1800738bd  jnz     short loc_1800738C4
0x1800738bf  xor     eax, eax
0x1800738c1  xchg    eax, [rdi+50h]
0x1800738c4  mov     rax, [rsp+1D8h+var_138]
0x1800738cc  mov     [rax], rdi
0x1800738cf  xor     edi, edi
0x1800738d1  mov     [rsp+1D8h+var_158], rdi
0x1800738d9  xor     ebx, ebx
0x1800738db  jmp     short loc_18007388E
0x1800738dd  test    eax, eax
0x1800738df  jle     short loc_1800738EA
0x1800738e1  movzx   ebx, ax
0x1800738e4  or      ebx, 80070000h
0x1800738ea  mov     [rsp+1D8h+var_198], ebx
0x1800738ee  inc     r14d
0x1800738f1  mov     [rsp+1D8h+var_168], r14d
0x1800738f6  cmp     r14d, 14h
0x1800738fa  jnz     loc_18007375C
0x180073900  cmp     dword ptr [r13+10h], 0
0x180073905  jbe     short loc_18007392B
0x180073907  lea     rdx, [rsp+1D8h+var_178]; void **
0x18007390c  lea     rcx, [rsp+1D8h+var_118]; struct _ACL **
0x180073914  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x180073919  jmp     short loc_18007392B
0x18007391b  mov     [rsp+1D8h+var_198], eax
0x18007391f  jmp     short loc_18007392B
0x180073921  mov     ebx, 80004005h
0x180073926  jmp     loc_1800736A1
0x18007392b  mov     r14, [rsp+1D8h+var_190]
0x180073930  mov     r13, [rsp+1D8h+var_188]
0x180073935  test    rdi, rdi
0x180073938  jz      short loc_180073943
0x18007393a  mov     rcx, rdi; lpBaseAddress
0x18007393d  call    cs:__imp_UnmapViewOfFile
0x180073943  test    r14, r14
0x180073946  jz      short loc_180073951
0x180073948  mov     rcx, r14; hObject
0x18007394b  call    cs:__imp_CloseHandle
0x180073951  test    rsi, rsi
0x180073954  jz      short loc_18007395F
0x180073956  mov     rcx, rsi; hObject
0x180073959  call    cs:__imp_CloseHandle
0x18007395f  test    ebx, ebx
0x180073961  jns     short loc_1800739B5
0x180073963  mov     rcx, [r13+0]; hObject
0x180073967  test    rcx, rcx
0x18007396a  jz      short loc_18007397A
0x18007396c  call    cs:__imp_CloseHandle
0x180073972  mov     qword ptr [r13+0], 0
0x18007397a  test    r15, r15
0x18007397d  jz      short loc_180073995
0x18007397f  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180073983  jz      short loc_180073995
0x180073985  mov     rcx, [r15]; hObject
0x180073988  call    cs:__imp_CloseHandle
0x18007398e  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180073995  cmp     [rsp+1D8h+var_164], 1
0x18007399a  jnz     short loc_1800739B5
0x18007399c  cmp     [rsp+1D8h+var_180], 0
0x1800739a1  jz      short loc_1800739B5
0x1800739a3  mov     rax, [rsp+1D8h+var_150]
0x1800739ab  mov     rcx, [rax+70h]; lpFileName
0x1800739af  call    cs:__imp_DeleteFileW
0x1800739b5  jmp     short loc_1800739C0
0x1800739b7  mov     ebx, 0C0000005h
0x1800739bc  mov     [rsp+1D8h+var_198], ebx
0x1800739c0  mov     eax, ebx
0x1800739c2  mov     rcx, [rsp+1D8h+var_38]
0x1800739ca  xor     rcx, rsp; StackCookie
0x1800739cd  call    __security_check_cookie
0x1800739d2  lea     r11, [rsp+1D8h+var_28]
0x1800739da  mov     rbx, [r11+40h]
0x1800739de  mov     rsi, [r11+48h]
0x1800739e2  mov     rsp, r11
0x1800739e5  pop     r15
0x1800739e7  pop     r14
0x1800739e9  pop     r13
0x1800739eb  pop     r12
0x1800739ed  pop     rdi
0x1800739ee  retn
0x1800b5174  push    rbx
0x1800b5176  push    rbp
0x1800b5177  sub     rsp, 48h
0x1800b517b  mov     rbp, rdx
0x1800b517e  mov     rcx, [rbp+80h]; lpBaseAddress
0x1800b5185  test    rcx, rcx
0x1800b5188  jz      short loc_1800B5191
0x1800b518a  call    cs:__imp_UnmapViewOfFile
0x1800b5190  nop
0x1800b5191  mov     rcx, [rbp+48h]; hObject
0x1800b5195  test    rcx, rcx
0x1800b5198  jz      short loc_1800B51A1
0x1800b519a  call    cs:__imp_CloseHandle
0x1800b51a0  nop
0x1800b51a1  mov     rcx, [rbp+68h]; hObject
0x1800b51a5  test    rcx, rcx
  ... truncated ...
```
