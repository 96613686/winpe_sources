# SxCreateSVI(ushort const *)

- ea: `0x18008ed84`
- end: `0x18008f003`
- name: `?SxCreateSVI@@YAJPEBG@Z`
- size: `639`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800b4064`
- `0x1800b512c`

## callees

- `0x1800083cc`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18007035c`
- `0x18008ed84`
- `0x18008f660`
- `0x180099764`
- `0x18009a24c`
- `0x18009a3ac`
- `0x18009ae34`

## import_xrefs

- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18008ef6b`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18008ef6b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18008ef41`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18008ef41`
- `ntdll!RtlInitUnicodeString` at `0x18008ee0c`
- `ntdll!RtlInitUnicodeString` at `0x18008ee0c`
- `ntdll!RtlFreeHeap` at `0x18008eef0`
- `ntdll!RtlFreeHeap` at `0x18008eef0`
- `KERNEL32!CreateFileW` at `0x18008eeb7`
- `KERNEL32!CreateFileW` at `0x18008efa1`
- `KERNEL32!CreateFileW` at `0x18008eeb7`
- `KERNEL32!CreateFileW` at `0x18008efa1`
- `KERNEL32!CloseHandle` at `0x18008ef0e`
- `KERNEL32!CloseHandle` at `0x18008ef0e`

## string_xrefs

- `0x18008edd2`: `SxCreateSVI`

## pseudocode

```c
__int64 __fastcall SxCreateSVI(const unsigned __int16 *a1)
{
  __int64 FileW; // rbx
  __int16 v3; // ax
  __int16 v4; // ax
  unsigned int v5; // edi
  bool v7; // zf
  NTSTATUS v8; // esi
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  int v11; // [rsp+60h] [rbp-9h] BYREF
  __int16 v12; // [rsp+64h] [rbp-5h]
  __int16 v13; // [rsp+66h] [rbp-3h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "SxCreateSVI", 501, 1);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  DestinationString = 0;
  FileW = -1;
  RtlInitUnicodeString(&DestinationString, 0);
  v3 = 510;
  if ( !a1 )
  {
    v11 = -2147024809;
LABEL_6:
    v13 = v3;
    goto LABEL_13;
  }
  v11 = 0;
  v12 = 510;
  v11 = CBsString::Set((CBsString *)lpFileName, a1);
  v3 = 512;
  if ( v11 < 0 )
    goto LABEL_6;
  v12 = 512;
  v11 = CBsString::Trailing((CBsString *)lpFileName, 0x5Cu);
  v3 = 513;
  if ( v11 < 0 )
    goto LABEL_6;
  v12 = 513;
  v11 = CBsString::Append((CBsString *)lpFileName, L"System Volume Information");
  v3 = 514;
  if ( v11 < 0 )
    goto LABEL_6;
  v12 = 514;
  FileW = (__int64)CreateFileW(lpFileName[0], 0, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW != -1 )
  {
    v11 = 0;
    v4 = 519;
LABEL_12:
    v12 = v4;
    goto LABEL_13;
  }
  v7 = RtlDosPathNameToNtPathName_U(a1, &DestinationString, 0, 0) == 0;
  v3 = 530;
  if ( v7 )
  {
    v11 = -2147024893;
    goto LABEL_6;
  }
  v11 = 0;
  v12 = 530;
  v8 = RtlCreateSystemVolumeInformationFolder(&DestinationString);
  if ( v8 < 0 )
  {
    FileW = (__int64)CreateFileW(lpFileName[0], 0, 7u, 0, 3u, 0x2000000u, 0);
    if ( FileW != -1 )
    {
      v11 = 0;
      v4 = 538;
      goto LABEL_12;
    }
    v11 = HRESULTFromNTSTATUS((unsigned int)v8);
    v4 = 542;
    if ( v11 >= 0 )
      goto LABEL_12;
    v13 = 542;
    CSxFunctionTracer::LogFailure((CSxFunctionTracer *)&v11, L"SPP", 0x3003u, L"%S", a1);
  }
LABEL_13:
  if ( DestinationString.Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
    DestinationString.Buffer = 0;
  }
  v5 = v11;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return v5;
}

```

## disassembly

```asm
0x18008ed84  push    rbp
0x18008ed86  push    rbx
0x18008ed87  push    rsi
0x18008ed88  push    rdi
0x18008ed89  lea     rbp, [rsp-3Fh]
0x18008ed8e  sub     rsp, 0A8h
0x18008ed95  mov     rdi, rcx
0x18008ed98  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ed9f  lea     rax, WPP_GLOBAL_Control
0x18008eda6  cmp     rcx, rax
0x18008eda9  jz      short loc_18008EDCC
0x18008edab  test    dword ptr [rcx+1Ch], 20000000h
0x18008edb2  jz      short loc_18008EDCC
0x18008edb4  mov     rcx, [rcx+10h]
0x18008edb8  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18008edbf  mov     edx, 13h
0x18008edc4  mov     r9, rdi
0x18008edc7  call    WPP_SF_q
0x18008edcc  mov     r9d, 1; unsigned __int16
0x18008edd2  lea     rdx, aSxcreatesvi; "SxCreateSVI"
0x18008edd9  mov     r8d, 1F5h; unsigned __int16
0x18008eddf  lea     rcx, [rbp+57h+var_60]; this
0x18008ede3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008ede8  xorps   xmm0, xmm0
0x18008edeb  mov     [rbp+57h+var_78], 0
0x18008edf3  lea     rax, qword_1800E8530
0x18008edfa  xor     edx, edx; SourceString
0x18008edfc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008ee00  mov     [rbp+57h+lpFileName], rax
0x18008ee04  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18008ee08  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008ee0c  call    cs:__imp_RtlInitUnicodeString
0x18008ee12  mov     eax, 1FEh
0x18008ee17  test    rdi, rdi
0x18008ee1a  jnz     short loc_18008EE2C
0x18008ee1c  mov     [rbp+57h+var_60], 80070057h
0x18008ee23  mov     [rbp+57h+var_5A], ax
0x18008ee27  jmp     loc_18008EED6
0x18008ee2c  mov     rdx, rdi; unsigned __int16 *
0x18008ee2f  mov     [rbp+57h+var_60], 0
0x18008ee36  lea     rcx, [rbp+57h+lpFileName]; this
0x18008ee3a  mov     [rbp+57h+var_5C], ax
0x18008ee3e  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18008ee43  mov     [rbp+57h+var_60], eax
0x18008ee46  test    eax, eax
0x18008ee48  mov     eax, 200h
0x18008ee4d  js      short loc_18008EE23
0x18008ee4f  mov     edx, 5Ch ; '\'; unsigned __int16
0x18008ee54  mov     [rbp+57h+var_5C], ax
0x18008ee58  lea     rcx, [rbp+57h+lpFileName]; this
0x18008ee5c  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18008ee61  mov     [rbp+57h+var_60], eax
0x18008ee64  test    eax, eax
0x18008ee66  mov     eax, 201h
0x18008ee6b  js      short loc_18008EE23
0x18008ee6d  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x18008ee74  mov     [rbp+57h+var_5C], ax
0x18008ee78  lea     rcx, [rbp+57h+lpFileName]; this
0x18008ee7c  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18008ee81  mov     [rbp+57h+var_60], eax
0x18008ee84  test    eax, eax
0x18008ee86  mov     eax, 202h
0x18008ee8b  js      short loc_18008EE23
0x18008ee8d  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18008ee91  xor     r9d, r9d; lpSecurityAttributes
0x18008ee94  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18008ee9d  xor     edx, edx; dwDesiredAccess
0x18008ee9f  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18008eea7  mov     [rbp+57h+var_5C], ax
0x18008eeab  lea     r8d, [r9+7]; dwShareMode
0x18008eeaf  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18008eeb7  call    cs:__imp_CreateFileW
0x18008eebd  mov     rbx, rax
0x18008eec0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008eec4  jz      short loc_18008EF34
0x18008eec6  mov     [rbp+57h+var_60], 0
0x18008eecd  mov     eax, 207h
0x18008eed2  mov     [rbp+57h+var_5C], ax
0x18008eed6  cmp     [rbp+57h+DestinationString.Buffer], 0
0x18008eedb  jz      short loc_18008EEFE
0x18008eedd  mov     rcx, gs:60h
0x18008eee6  xor     edx, edx; Flags
0x18008eee8  mov     r8, [rbp+57h+DestinationString.Buffer]; P
0x18008eeec  mov     rcx, [rcx+30h]; HeapHandle
0x18008eef0  call    cs:__imp_RtlFreeHeap
0x18008eef6  mov     [rbp+57h+DestinationString.Buffer], 0
0x18008eefe  mov     edi, [rbp+57h+var_60]
0x18008ef01  lea     rcx, [rbx-1]
0x18008ef05  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18008ef09  ja      short loc_18008EF14
0x18008ef0b  mov     rcx, rbx; hObject
0x18008ef0e  call    cs:__imp_CloseHandle
0x18008ef14  lea     rcx, [rbp+57h+lpFileName]; this
0x18008ef18  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18008ef1d  lea     rcx, [rbp+57h+var_60]; this
0x18008ef21  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008ef26  mov     eax, edi
0x18008ef28  add     rsp, 0A8h
0x18008ef2f  pop     rdi
0x18008ef30  pop     rsi
0x18008ef31  pop     rbx
0x18008ef32  pop     rbp
0x18008ef33  retn
0x18008ef34  xor     r9d, r9d; DirectoryInfo
0x18008ef37  lea     rdx, [rbp+57h+DestinationString]; NtPathName
0x18008ef3b  xor     r8d, r8d; NtFileNamePart
0x18008ef3e  mov     rcx, rdi; DosPathName
0x18008ef41  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18008ef47  test    al, al
0x18008ef49  mov     eax, 212h
0x18008ef4e  jnz     short loc_18008EF5C
0x18008ef50  mov     [rbp+57h+var_60], 80070003h
0x18008ef57  jmp     loc_18008EE23
0x18008ef5c  lea     rcx, [rbp+57h+DestinationString]; VolumeRootPath
0x18008ef60  mov     [rbp+57h+var_60], 0
0x18008ef67  mov     [rbp+57h+var_5C], ax
0x18008ef6b  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x18008ef71  mov     esi, eax
0x18008ef73  test    eax, eax
0x18008ef75  jns     loc_18008EED6
0x18008ef7b  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18008ef7f  xor     r9d, r9d; lpSecurityAttributes
0x18008ef82  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18008ef8b  xor     edx, edx; dwDesiredAccess
0x18008ef8d  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18008ef95  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18008ef9d  lea     r8d, [r9+7]; dwShareMode
0x18008efa1  call    cs:__imp_CreateFileW
0x18008efa7  mov     rbx, rax
0x18008efaa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008efae  jz      short loc_18008EFC1
0x18008efb0  mov     [rbp+57h+var_60], 0
0x18008efb7  mov     eax, 21Ah
0x18008efbc  jmp     loc_18008EED2
0x18008efc1  mov     ecx, esi
0x18008efc3  call    HRESULTFromNTSTATUS
0x18008efc8  mov     [rbp+57h+var_60], eax
0x18008efcb  test    eax, eax
0x18008efcd  mov     eax, 21Eh
0x18008efd2  jns     loc_18008EED2
0x18008efd8  lea     r9, aS_2; "%S"
0x18008efdf  mov     [rbp+57h+var_5A], ax
0x18008efe3  mov     r8d, 3003h; unsigned int
0x18008efe9  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdi
0x18008efee  lea     rdx, c_wszEventSourceSPP; "SPP"
0x18008eff5  lea     rcx, [rbp+57h+var_60]; this
0x18008eff9  call    ?LogFailure@CSxFunctionTracer@@QEBAXPEBGK0ZZ; CSxFunctionTracer::LogFailure(ushort const *,ulong,ushort const *,...)
0x18008effe  jmp     loc_18008EED6
```
