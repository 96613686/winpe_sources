# SxCreateSVI(ushort const *)

- ea: `0x18002c324`
- end: `0x18002c59e`
- name: `?SxCreateSVI@@YAJPEBG@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18002c08c`

## callees

- `0x1800216c8`
- `0x1800268b4`
- `0x1800269ac`
- `0x180026c70`
- `0x18002c324`
- `0x18002d778`
- `0x180034de0`
- `0x18003532c`
- `0x1800353c4`
- `0x180035b00`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002c452`
- `KERNEL32!CreateFileW` at `0x18002c53c`
- `KERNEL32!CreateFileW` at `0x18002c452`
- `KERNEL32!CreateFileW` at `0x18002c53c`
- `KERNEL32!CloseHandle` at `0x18002c4a9`
- `KERNEL32!CloseHandle` at `0x18002c4a9`
- `ntdll!RtlFreeHeap` at `0x18002c48b`
- `ntdll!RtlFreeHeap` at `0x18002c48b`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18002c506`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18002c506`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002c4dc`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002c4dc`
- `ntdll!RtlInitUnicodeString` at `0x18002c3ac`
- `ntdll!RtlInitUnicodeString` at `0x18002c3ac`

## string_xrefs

- `0x18002c372`: `SxCreateSVI`

## pseudocode

```c
__int64 __fastcall SxCreateSVI(const unsigned __int16 *a1)
{
  __int64 FileW; // rbx
  __int16 v3; // ax
  unsigned __int16 v4; // dx
  __int16 v5; // ax
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  bool v10; // zf
  NTSTATUS v11; // esi
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  int v14; // [rsp+60h] [rbp-9h] BYREF
  __int16 v15; // [rsp+64h] [rbp-5h]
  __int16 v16; // [rsp+66h] [rbp-3h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "SxCreateSVI", 501, 1);
  lpFileName[1] = 0;
  lpFileName[0] = &FileName;
  DestinationString = 0;
  FileW = -1;
  RtlInitUnicodeString(&DestinationString, 0);
  v3 = 510;
  if ( !a1 )
  {
    v14 = -2147024809;
LABEL_6:
    v16 = v3;
    goto LABEL_13;
  }
  v14 = 0;
  v15 = 510;
  v14 = CBsString::Set((CBsString *)lpFileName, a1);
  v3 = 512;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 512;
  v14 = CBsString::Trailing((CBsString *)lpFileName, v4);
  v3 = 513;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 513;
  v14 = CBsString::Append((CBsString *)lpFileName, L"System Volume Information");
  v3 = 514;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 514;
  FileW = (__int64)CreateFileW(lpFileName[0], 0, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW != -1 )
  {
    v14 = 0;
    v5 = 519;
LABEL_12:
    v15 = v5;
    goto LABEL_13;
  }
  v10 = RtlDosPathNameToNtPathName_U(a1, &DestinationString, 0, 0) == 0;
  v3 = 530;
  if ( v10 )
  {
    v14 = -2147024893;
    goto LABEL_6;
  }
  v14 = 0;
  v15 = 530;
  v11 = RtlCreateSystemVolumeInformationFolder(&DestinationString);
  if ( v11 < 0 )
  {
    FileW = (__int64)CreateFileW(lpFileName[0], 0, 7u, 0, 3u, 0x2000000u, 0);
    if ( FileW != -1 )
    {
      v14 = 0;
      v5 = 538;
      goto LABEL_12;
    }
    v14 = HRESULTFromNTSTATUS((unsigned int)v11);
    v5 = 542;
    if ( v14 >= 0 )
      goto LABEL_12;
    v16 = 542;
    CSxFunctionTracer::LogFailure((CSxFunctionTracer *)&v14, L"SPP", 0x3003u, L"%S", a1);
  }
LABEL_13:
  if ( DestinationString.Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
    DestinationString.Buffer = 0;
  }
  v6 = v14;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_Release((unsigned __int16 **)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14, v7, v8);
  return v6;
}

```

## disassembly

```asm
0x18002c324  push    rbp
0x18002c326  push    rbx
0x18002c327  push    rsi
0x18002c328  push    rdi
0x18002c329  lea     rbp, [rsp-3Fh]
0x18002c32e  sub     rsp, 0A8h
0x18002c335  mov     rdi, rcx
0x18002c338  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c33f  lea     rax, WPP_GLOBAL_Control
0x18002c346  cmp     rcx, rax
0x18002c349  jz      short loc_18002C36C
0x18002c34b  test    dword ptr [rcx+1Ch], 20000000h
0x18002c352  jz      short loc_18002C36C
0x18002c354  mov     rcx, [rcx+10h]
0x18002c358  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002c35f  mov     edx, 13h
0x18002c364  mov     r9, rdi
0x18002c367  call    WPP_SF_q
0x18002c36c  mov     r9d, 1; unsigned __int16
0x18002c372  lea     rdx, aSxcreatesvi; "SxCreateSVI"
0x18002c379  mov     r8d, 1F5h; unsigned __int16
0x18002c37f  lea     rcx, [rbp+57h+var_60]; this
0x18002c383  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002c388  xorps   xmm0, xmm0
0x18002c38b  mov     [rbp+57h+var_78], 0
0x18002c393  lea     rax, FileName
0x18002c39a  xor     edx, edx; SourceString
0x18002c39c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002c3a0  mov     [rbp+57h+lpFileName], rax
0x18002c3a4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002c3a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c3ac  call    cs:__imp_RtlInitUnicodeString
0x18002c3b2  mov     eax, 1FEh
0x18002c3b7  test    rdi, rdi
0x18002c3ba  jnz     short loc_18002C3CC
0x18002c3bc  mov     [rbp+57h+var_60], 80070057h
0x18002c3c3  mov     [rbp+57h+var_5A], ax
0x18002c3c7  jmp     loc_18002C471
0x18002c3cc  mov     rdx, rdi; unsigned __int16 *
0x18002c3cf  mov     [rbp+57h+var_60], 0
0x18002c3d6  lea     rcx, [rbp+57h+lpFileName]; this
0x18002c3da  mov     [rbp+57h+var_5C], ax
0x18002c3de  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002c3e3  mov     [rbp+57h+var_60], eax
0x18002c3e6  test    eax, eax
0x18002c3e8  mov     eax, 200h
0x18002c3ed  js      short loc_18002C3C3
0x18002c3ef  lea     rcx, [rbp+57h+lpFileName]; this
0x18002c3f3  mov     [rbp+57h+var_5C], ax
0x18002c3f7  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18002c3fc  mov     [rbp+57h+var_60], eax
0x18002c3ff  test    eax, eax
0x18002c401  mov     eax, 201h
0x18002c406  js      short loc_18002C3C3
0x18002c408  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x18002c40f  mov     [rbp+57h+var_5C], ax
0x18002c413  lea     rcx, [rbp+57h+lpFileName]; this
0x18002c417  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18002c41c  mov     [rbp+57h+var_60], eax
0x18002c41f  test    eax, eax
0x18002c421  mov     eax, 202h
0x18002c426  js      short loc_18002C3C3
0x18002c428  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18002c42c  xor     r9d, r9d; lpSecurityAttributes
0x18002c42f  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18002c438  xor     edx, edx; dwDesiredAccess
0x18002c43a  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002c442  mov     [rbp+57h+var_5C], ax
0x18002c446  lea     r8d, [r9+7]; dwShareMode
0x18002c44a  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c452  call    cs:__imp_CreateFileW
0x18002c458  mov     rbx, rax
0x18002c45b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c45f  jz      short loc_18002C4CF
0x18002c461  mov     [rbp+57h+var_60], 0
0x18002c468  mov     eax, 207h
0x18002c46d  mov     [rbp+57h+var_5C], ax
0x18002c471  cmp     [rbp+57h+DestinationString.Buffer], 0
0x18002c476  jz      short loc_18002C499
0x18002c478  mov     rcx, gs:60h
0x18002c481  xor     edx, edx; Flags
0x18002c483  mov     r8, [rbp+57h+DestinationString.Buffer]; P
0x18002c487  mov     rcx, [rcx+30h]; HeapHandle
0x18002c48b  call    cs:__imp_RtlFreeHeap
0x18002c491  mov     [rbp+57h+DestinationString.Buffer], 0
0x18002c499  mov     edi, [rbp+57h+var_60]
0x18002c49c  lea     rcx, [rbx-1]
0x18002c4a0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002c4a4  ja      short loc_18002C4AF
0x18002c4a6  mov     rcx, rbx; hObject
0x18002c4a9  call    cs:__imp_CloseHandle
0x18002c4af  lea     rcx, [rbp+57h+lpFileName]; this
0x18002c4b3  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002c4b8  lea     rcx, [rbp+57h+var_60]; this
0x18002c4bc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002c4c1  mov     eax, edi
0x18002c4c3  add     rsp, 0A8h
0x18002c4ca  pop     rdi
0x18002c4cb  pop     rsi
0x18002c4cc  pop     rbx
0x18002c4cd  pop     rbp
0x18002c4ce  retn
0x18002c4cf  xor     r9d, r9d; DirectoryInfo
0x18002c4d2  lea     rdx, [rbp+57h+DestinationString]; NtPathName
0x18002c4d6  xor     r8d, r8d; NtFileNamePart
0x18002c4d9  mov     rcx, rdi; DosPathName
0x18002c4dc  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18002c4e2  test    al, al
0x18002c4e4  mov     eax, 212h
0x18002c4e9  jnz     short loc_18002C4F7
0x18002c4eb  mov     [rbp+57h+var_60], 80070003h
0x18002c4f2  jmp     loc_18002C3C3
0x18002c4f7  lea     rcx, [rbp+57h+DestinationString]; VolumeRootPath
0x18002c4fb  mov     [rbp+57h+var_60], 0
0x18002c502  mov     [rbp+57h+var_5C], ax
0x18002c506  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x18002c50c  mov     esi, eax
0x18002c50e  test    eax, eax
0x18002c510  jns     loc_18002C471
0x18002c516  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18002c51a  xor     r9d, r9d; lpSecurityAttributes
0x18002c51d  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18002c526  xor     edx, edx; dwDesiredAccess
0x18002c528  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002c530  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c538  lea     r8d, [r9+7]; dwShareMode
0x18002c53c  call    cs:__imp_CreateFileW
0x18002c542  mov     rbx, rax
0x18002c545  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c549  jz      short loc_18002C55C
0x18002c54b  mov     [rbp+57h+var_60], 0
0x18002c552  mov     eax, 21Ah
0x18002c557  jmp     loc_18002C46D
0x18002c55c  mov     ecx, esi
0x18002c55e  call    HRESULTFromNTSTATUS
0x18002c563  mov     [rbp+57h+var_60], eax
0x18002c566  test    eax, eax
0x18002c568  mov     eax, 21Eh
0x18002c56d  jns     loc_18002C46D
0x18002c573  lea     r9, aS_0; "%S"
0x18002c57a  mov     [rbp+57h+var_5A], ax
0x18002c57e  mov     r8d, 3003h; unsigned int
0x18002c584  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdi
0x18002c589  lea     rdx, c_wszEventSourceSPP; "SPP"
0x18002c590  lea     rcx, [rbp+57h+var_60]; this
0x18002c594  call    ?LogFailure@CSxFunctionTracer@@QEBAXPEBGK0ZZ; CSxFunctionTracer::LogFailure(ushort const *,ulong,ushort const *,...)
0x18002c599  jmp     loc_18002C471
```
