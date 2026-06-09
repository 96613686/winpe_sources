# CVdsService::QueryDriveLetters(ushort,ulong,_VDS_DRIVE_LETTER_PROP *)

- ea: `0x140028340`
- end: `0x14002863a`
- name: `?QueryDriveLetters@CVdsService@@UEAAJGKPEAU_VDS_DRIVE_LETTER_PROP@@@Z`
- size: `762`
- prototype: `int(CVdsService *__hidden this, unsigned __int16, unsigned int, struct _VDS_DRIVE_LETTER_PROP *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x140003710`
- `0x140004360`
- `0x140006a80`
- `0x140006e60`
- `0x140013298`
- `0x140015694`
- `0x140028340`
- `0x14002e123`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002848d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002848d`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x140028483`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x140028483`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1400284e2`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1400284e2`
- `vdsutil!VdsTraceEx` at `0x14002854a`
- `vdsutil!VdsTraceEx` at `0x1400285d4`
- `vdsutil!VdsTraceEx` at `0x1400285f9`
- `vdsutil!VdsTraceEx` at `0x14002854a`
- `vdsutil!VdsTraceEx` at `0x1400285d4`
- `vdsutil!VdsTraceEx` at `0x1400285f9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400283bd`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400283bd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400285bf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400285e4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028605`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400285bf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400285e4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140028605`

## string_xrefs

- `0x14002853e`: `CVdsService::QueryDriveLetters, 3`
- `0x1400283aa`: `CVdsService::QueryDriveLetters()`
- `0x1400285ee`: `CVdsService::QueryDriveLetters, 1`
- `0x1400285c9`: `CVdsService::QueryDriveLetters, 2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::QueryDriveLetters(
        CVdsService *this,
        unsigned __int16 a2,
        unsigned int a3,
        struct _VDS_DRIVE_LETTER_PROP *a4)
{
  __int64 v5; // r15
  int v6; // r12d
  signed int LastError; // ebx
  unsigned int i; // esi
  __int64 v10; // rcx
  __int64 v11; // rbx
  UINT DriveTypeW; // eax
  VDS_OBJECT_ID *p_volumeId; // rdx
  signed int IsLetterInMountMgrDB; // r14d
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+38h] [rbp-C8h]
  _BYTE v18[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR DeviceName[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR RootPathName[4]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v21[14]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR TargetPath[266]; // [rsp+7Ch] [rbp-84h] BYREF

  v5 = a3;
  v6 = a2;
  wcscpy(DeviceName, L"?:");
  wcscpy(RootPathName, L"?:\\");
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v18, 0x5Eu, "CVdsService::QueryDriveLetters()");
  memset_0(a4, 0, 28 * v5);
  if ( (unsigned __int16)(v6 - 65) > 0x19u )
  {
    VdsTraceEx(94, 0, "CVdsService::QueryDriveLetters, 1");
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
    return 2147755358LL;
  }
  if ( !(_DWORD)v5 || (unsigned int)(v5 + v6 - 1) > 0x5A )
  {
    VdsTraceEx(94, 0, "CVdsService::QueryDriveLetters, 2");
    LastError = -2147211937;
    goto LABEL_24;
  }
  LastError = (*(__int64 (__fastcall **)(CVdsService *))(*(_QWORD *)this + 32LL))(this);
  if ( LastError < 0 )
    goto LABEL_24;
  v16 = 0;
  v17 = 0;
  LastError = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v16);
  if ( LastError < 0 )
    goto LABEL_6;
  StringCchCopyW(v21, 0x112u, L"\\\\?\\GLOBALROOT");
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned int)v5 )
    {
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v16);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
      return 0;
    }
    DeviceName[0] = v6 + i;
    RootPathName[0] = v6 + i;
    if ( !QueryDosDeviceW(DeviceName, TargetPath, 0x104u) )
      break;
    v11 = i;
    a4[v11].wcLetter = DeviceName[0];
    a4[v11].bUsed = 1;
    DriveTypeW = GetDriveTypeW(RootPathName);
    p_volumeId = &a4[v11].volumeId;
    if ( DriveTypeW == 4 )
    {
      *p_volumeId = GUID_NULL;
LABEL_15:
      a4[v11].ulFlags = 0;
      continue;
    }
    CVdsService::GetVolumeId(v21, p_volumeId, 0);
    IsLetterInMountMgrDB = CVdsService::IsLetterInMountMgrDB(DeviceName[0]);
    if ( !IsLetterInMountMgrDB )
      goto LABEL_15;
    if ( IsLetterInMountMgrDB != 1 )
    {
      memset_0(a4, 0, 28 * v5);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v16);
      LastError = IsLetterInMountMgrDB;
      goto LABEL_24;
    }
    a4[v11].ulFlags = 1;
LABEL_18:
    ;
  }
  LastError = GetLastError();
  if ( LastError == 2 )
  {
    v10 = i;
    a4[v10].wcLetter = DeviceName[0];
    a4[v10].bUsed = 0;
    a4[v10].volumeId = GUID_NULL;
    a4[v10].ulFlags = 0;
    goto LABEL_18;
  }
  VdsTraceEx(94, 0, "CVdsService::QueryDriveLetters, 3");
  VdsLogError(0xC2000001, 0, 0, LastError, 0x200001Eu, 0);
  memset_0(a4, 0, 28 * v5);
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_6:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v16);
LABEL_24:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140028340  mov     [rsp-8+arg_8], rbx
0x140028345  push    rbp
0x140028346  push    rsi
0x140028347  push    rdi
0x140028348  push    r12
0x14002834a  push    r13
0x14002834c  push    r14
0x14002834e  push    r15
0x140028350  lea     rbp, [rsp-1A0h]
0x140028358  sub     rsp, 2A0h
0x14002835f  mov     rax, cs:__security_cookie
0x140028366  xor     rax, rsp
0x140028369  mov     [rbp+1D0h+var_40], rax
0x140028370  mov     rdi, r9
0x140028373  mov     r15d, r8d
0x140028376  movzx   r12d, dx
0x14002837a  mov     rbx, rcx
0x14002837d  mov     eax, 3Fh ; '?'
0x140028382  mov     [rsp+2D0h+DeviceName], ax
0x140028387  mov     [rsp+2D0h+var_27E], 3Ah ; ':'
0x14002838f  mov     [rsp+2D0h+RootPathName], ax
0x140028394  mov     eax, dword ptr cs:asc_140069000+2; ":\\"
0x14002839a  mov     [rsp+2D0h+var_276], eax
0x14002839e  movzx   eax, word ptr cs:asc_140069000+6; ""
0x1400283a5  mov     [rsp+2D0h+var_272], ax
0x1400283aa  lea     r8, aCvdsserviceQue_16; "CVdsService::QueryDriveLetters()"
0x1400283b1  mov     esi, 5Eh ; '^'
0x1400283b6  mov     edx, esi
0x1400283b8  lea     rcx, [rsp+2D0h+var_290]
0x1400283bd  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400283c3  nop
0x1400283c4  imul    r13, r15, 1Ch
0x1400283c8  mov     r8, r13; Size
0x1400283cb  xor     edx, edx; Val
0x1400283cd  mov     rcx, rdi; void *
0x1400283d0  call    memset_0
0x1400283d5  lea     eax, [r12-41h]
0x1400283da  cmp     ax, 19h
0x1400283de  ja      loc_1400285EE
0x1400283e4  xor     r14d, r14d
0x1400283e7  test    r15d, r15d
0x1400283ea  jz      loc_1400285C9
0x1400283f0  lea     edx, [r12-1]
0x1400283f5  add     edx, r15d
0x1400283f8  cmp     edx, 5Ah ; 'Z'
0x1400283fb  ja      loc_1400285C9
0x140028401  mov     rax, [rbx]
0x140028404  mov     rcx, rbx
0x140028407  mov     rax, [rax+20h]
0x14002840b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028410  mov     ebx, eax
0x140028412  test    eax, eax
0x140028414  js      loc_1400285DF
0x14002841a  mov     [rsp+2D0h+var_2A0], r14
0x14002841f  mov     [rsp+2D0h+var_298], r14d
0x140028424  lea     rcx, [rsp+2D0h+var_2A0]; this
0x140028429  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x14002842e  mov     ebx, eax
0x140028430  test    eax, eax
0x140028432  jns     short loc_140028443
0x140028434  lea     rcx, [rsp+2D0h+var_2A0]; this
0x140028439  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14002843e  jmp     loc_1400285DF
0x140028443  lea     r8, aGlobalroot; "\\\\?\\GLOBALROOT"
0x14002844a  mov     edx, 112h; unsigned __int64
0x14002844f  lea     rcx, [rsp+2D0h+var_270]; unsigned __int16 *
0x140028454  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140028459  mov     esi, r14d
0x14002845c  cmp     esi, r15d
0x14002845f  jnb     loc_1400285AF
0x140028465  lea     eax, [r12+rsi]
0x140028469  mov     [rsp+2D0h+DeviceName], ax
0x14002846e  mov     [rsp+2D0h+RootPathName], ax
0x140028473  mov     r8d, 104h; ucchMax
0x140028479  lea     rdx, [rsp+2D0h+TargetPath]; lpTargetPath
0x14002847e  lea     rcx, [rsp+2D0h+DeviceName]; lpDeviceName
0x140028483  call    cs:__imp_QueryDosDeviceW
0x140028489  test    eax, eax
0x14002848b  jnz     short loc_1400284C6
0x14002848d  call    cs:__imp_GetLastError
0x140028493  mov     ebx, eax
0x140028495  cmp     eax, 2
0x140028498  jnz     loc_14002853E
0x14002849e  mov     eax, esi
0x1400284a0  imul    rcx, rax, 1Ch
0x1400284a4  movzx   eax, [rsp+2D0h+DeviceName]
0x1400284a9  mov     [rcx+rdi], ax
0x1400284ad  mov     [rcx+rdi+18h], r14d
0x1400284b2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400284b9  movdqu  xmmword ptr [rcx+rdi+4], xmm0
0x1400284bf  mov     [rcx+rdi+14h], r14d
0x1400284c4  jmp     short loc_140028537
0x1400284c6  mov     eax, esi
0x1400284c8  imul    rbx, rax, 1Ch
0x1400284cc  movzx   eax, [rsp+2D0h+DeviceName]
0x1400284d1  mov     [rbx+rdi], ax
0x1400284d5  mov     dword ptr [rbx+rdi+18h], 1
0x1400284dd  lea     rcx, [rsp+2D0h+RootPathName]; lpRootPathName
0x1400284e2  call    cs:__imp_GetDriveTypeW
0x1400284e8  lea     rdx, [rdi+4]
0x1400284ec  add     rdx, rbx; struct _GUID *
0x1400284ef  cmp     eax, 4
0x1400284f2  jnz     short loc_140028501
0x1400284f4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400284fb  movdqu  xmmword ptr [rdx], xmm0
0x1400284ff  jmp     short loc_140028522
0x140028501  xor     r8d, r8d; int *
0x140028504  lea     rcx, [rsp+2D0h+var_270]; unsigned __int16 *
0x140028509  call    ?GetVolumeId@CVdsService@@SAJPEAGPEAU_GUID@@PEAH@Z; CVdsService::GetVolumeId(ushort *,_GUID *,int *)
0x14002850e  movzx   ecx, [rsp+2D0h+DeviceName]; unsigned __int16
0x140028513  call    ?IsLetterInMountMgrDB@CVdsService@@SAJG@Z; CVdsService::IsLetterInMountMgrDB(ushort)
0x140028518  mov     r14d, eax
0x14002851b  test    eax, eax
0x14002851d  jnz     short loc_140028529
0x14002851f  xor     r14d, r14d
0x140028522  mov     [rbx+rdi+14h], r14d
0x140028527  jmp     short loc_140028537
0x140028529  cmp     r14d, 1
0x14002852d  jnz     short loc_140028592
0x14002852f  mov     [rbx+rdi+14h], r14d
0x140028534  xor     r14d, r14d
0x140028537  inc     esi
0x140028539  jmp     loc_14002845C
0x14002853e  lea     r8, aCvdsserviceQue_6; "CVdsService::QueryDriveLetters, 3"
0x140028545  xor     edx, edx
0x140028547  lea     ecx, [rdx+5Eh]
0x14002854a  call    cs:__imp_VdsTraceEx
0x140028550  mov     [rsp+2D0h+var_2A8], r14; unsigned __int16 *
0x140028555  mov     [rsp+2D0h+var_2B0], 200001Eh; unsigned int
0x14002855d  mov     r9d, ebx; unsigned int
0x140028560  xor     r8d, r8d; void *
0x140028563  xor     edx, edx; unsigned int
0x140028565  mov     ecx, 0C2000001h; unsigned int
0x14002856a  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14002856f  mov     r8, r13; Size
0x140028572  xor     edx, edx; Val
0x140028574  mov     rcx, rdi; void *
0x140028577  call    memset_0
0x14002857c  test    ebx, ebx
0x14002857e  jle     loc_140028434
0x140028584  movzx   ebx, bx
0x140028587  or      ebx, 80070000h
0x14002858d  jmp     loc_140028434
0x140028592  mov     r8, r13; Size
0x140028595  xor     edx, edx; Val
0x140028597  mov     rcx, rdi; void *
0x14002859a  call    memset_0
0x14002859f  nop
0x1400285a0  lea     rcx, [rsp+2D0h+var_2A0]; this
0x1400285a5  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400285aa  mov     ebx, r14d
0x1400285ad  jmp     short loc_1400285DF
0x1400285af  lea     rcx, [rsp+2D0h+var_2A0]; this
0x1400285b4  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400285b9  nop
0x1400285ba  lea     rcx, [rsp+2D0h+var_290]
0x1400285bf  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400285c5  xor     eax, eax
0x1400285c7  jmp     short loc_140028610
0x1400285c9  lea     r8, aCvdsserviceQue_4; "CVdsService::QueryDriveLetters, 2"
0x1400285d0  xor     edx, edx
0x1400285d2  mov     ecx, esi
0x1400285d4  call    cs:__imp_VdsTraceEx
0x1400285da  mov     ebx, 8004255Fh
0x1400285df  lea     rcx, [rsp+2D0h+var_290]
0x1400285e4  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400285ea  mov     eax, ebx
0x1400285ec  jmp     short loc_140028610
0x1400285ee  lea     r8, aCvdsserviceQue_17; "CVdsService::QueryDriveLetters, 1"
0x1400285f5  xor     edx, edx
0x1400285f7  mov     ecx, esi
0x1400285f9  call    cs:__imp_VdsTraceEx
0x1400285ff  nop
0x140028600  lea     rcx, [rsp+2D0h+var_290]
0x140028605  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002860b  mov     eax, 8004255Eh
0x140028610  mov     rcx, [rbp+1D0h+var_40]
0x140028617  xor     rcx, rsp; StackCookie
0x14002861a  call    __security_check_cookie
0x14002861f  mov     rbx, [rsp+2D0h+arg_8]
0x140028627  add     rsp, 2A0h
0x14002862e  pop     r15
0x140028630  pop     r14
0x140028632  pop     r13
0x140028634  pop     r12
0x140028636  pop     rdi
0x140028637  pop     rsi
0x140028638  pop     rbp
0x140028639  retn
```
