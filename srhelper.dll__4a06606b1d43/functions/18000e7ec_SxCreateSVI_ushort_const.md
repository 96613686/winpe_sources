# SxCreateSVI(ushort const *)

- ea: `0x18000e7ec`
- end: `0x18000ea59`
- name: `?SxCreateSVI@@YAJPEBG@Z`
- size: `621`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, __int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000e554`

## callees

- `0x18000d348`
- `0x18000d43c`
- `0x18000d7d0`
- `0x18000e7ec`
- `0x18000f1e4`
- `0x18000f2cc`
- `0x180014f38`
- `0x1800153c4`
- `0x180015760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000e964`
- `KERNEL32!CloseHandle` at `0x18000e964`
- `KERNEL32!CreateFileW` at `0x18000e90d`
- `KERNEL32!CreateFileW` at `0x18000e9f7`
- `KERNEL32!CreateFileW` at `0x18000e90d`
- `KERNEL32!CreateFileW` at `0x18000e9f7`
- `ntdll!RtlFreeHeap` at `0x18000e946`
- `ntdll!RtlFreeHeap` at `0x18000e946`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18000e9c1`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18000e9c1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000e997`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000e997`
- `ntdll!RtlInitUnicodeString` at `0x18000e867`
- `ntdll!RtlInitUnicodeString` at `0x18000e867`

## string_xrefs

- `0x18000e833`: `SxCreateSVI`

## pseudocode

```c
__int64 __fastcall SxCreateSVI(const unsigned __int16 *a1, __int64 a2, __int64 a3, unsigned __int16 a4)
{
  __int64 FileW; // rbx
  __int16 v6; // ax
  unsigned __int16 v7; // dx
  __int16 v8; // ax
  unsigned int v9; // edi
  bool v11; // zf
  NTSTATUS v12; // esi
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-29h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  int v15; // [rsp+60h] [rbp-9h] BYREF
  __int16 v16; // [rsp+64h] [rbp-5h]
  __int16 v17; // [rsp+66h] [rbp-3h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, a3, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "SxCreateSVI", 0x1F5u, a4);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  DestinationString = 0;
  FileW = -1;
  RtlInitUnicodeString(&DestinationString, 0);
  v6 = 510;
  if ( !a1 )
  {
    v15 = -2147024809;
LABEL_6:
    v17 = v6;
    goto LABEL_13;
  }
  v15 = 0;
  v16 = 510;
  v15 = CBsString::Append((CBsString *)lpFileName, a1);
  v6 = 512;
  if ( v15 < 0 )
    goto LABEL_6;
  v16 = 512;
  v15 = CBsString::Trailing((CBsString *)lpFileName, v7);
  v6 = 513;
  if ( v15 < 0 )
    goto LABEL_6;
  v16 = 513;
  v15 = CBsString::Append((CBsString *)lpFileName, L"System Volume Information");
  v6 = 514;
  if ( v15 < 0 )
    goto LABEL_6;
  v16 = 514;
  FileW = (__int64)CreateFileW(lpFileName[0], 0, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW != -1 )
  {
    v15 = 0;
    v8 = 519;
LABEL_12:
    v16 = v8;
    goto LABEL_13;
  }
  v11 = RtlDosPathNameToNtPathName_U(a1, &DestinationString, 0, 0) == 0;
  v6 = 530;
  if ( v11 )
  {
    v15 = -2147024893;
    goto LABEL_6;
  }
  v15 = 0;
  v16 = 530;
  v12 = RtlCreateSystemVolumeInformationFolder(&DestinationString);
  if ( v12 < 0 )
  {
    FileW = (__int64)CreateFileW(lpFileName[0], 0, 7u, 0, 3u, 0x2000000u, 0);
    if ( FileW != -1 )
    {
      v15 = 0;
      v8 = 538;
      goto LABEL_12;
    }
    v15 = HRESULTFromNTSTATUS((unsigned int)v12);
    v8 = 542;
    if ( v15 >= 0 )
      goto LABEL_12;
    v17 = 542;
    CSxFunctionTracer::LogFailure((CSxFunctionTracer *)&v15, L"SPP", 0x3003u, L"%S", a1);
  }
LABEL_13:
  if ( DestinationString.Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
    DestinationString.Buffer = 0;
  }
  v9 = v15;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15);
  return v9;
}

```

## disassembly

```asm
0x18000e7ec  push    rbp
0x18000e7ee  push    rbx
0x18000e7ef  push    rsi
0x18000e7f0  push    rdi
0x18000e7f1  lea     rbp, [rsp-3Fh]
0x18000e7f6  sub     rsp, 0A8h
0x18000e7fd  mov     rdi, rcx
0x18000e800  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e807  lea     rax, WPP_GLOBAL_Control
0x18000e80e  cmp     rcx, rax
0x18000e811  jz      short loc_18000E82D
0x18000e813  test    dword ptr [rcx+1Ch], 20000000h
0x18000e81a  jz      short loc_18000E82D
0x18000e81c  mov     rcx, [rcx+10h]
0x18000e820  mov     edx, 13h
0x18000e825  mov     r9, rdi
0x18000e828  call    WPP_SF_q
0x18000e82d  mov     r8d, 1F5h; unsigned __int16
0x18000e833  lea     rdx, aSxcreatesvi; "SxCreateSVI"
0x18000e83a  lea     rcx, [rbp+57h+var_60]; this
0x18000e83e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e843  xorps   xmm0, xmm0
0x18000e846  mov     [rbp+57h+var_78], 0
0x18000e84e  lea     rax, qword_18001A620
0x18000e855  xor     edx, edx; SourceString
0x18000e857  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000e85b  mov     [rbp+57h+lpFileName], rax
0x18000e85f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000e863  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e867  call    cs:__imp_RtlInitUnicodeString
0x18000e86d  mov     eax, 1FEh
0x18000e872  test    rdi, rdi
0x18000e875  jnz     short loc_18000E887
0x18000e877  mov     [rbp+57h+var_60], 80070057h
0x18000e87e  mov     [rbp+57h+var_5A], ax
0x18000e882  jmp     loc_18000E92C
0x18000e887  mov     [rbp+57h+var_60], 0
0x18000e88e  mov     [rbp+57h+var_5C], ax
0x18000e892  mov     rdx, rdi; unsigned __int16 *
0x18000e895  lea     rcx, [rbp+57h+lpFileName]; this
0x18000e899  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000e89e  mov     [rbp+57h+var_60], eax
0x18000e8a1  test    eax, eax
0x18000e8a3  mov     eax, 200h
0x18000e8a8  js      short loc_18000E87E
0x18000e8aa  lea     rcx, [rbp+57h+lpFileName]; this
0x18000e8ae  mov     [rbp+57h+var_5C], ax
0x18000e8b2  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18000e8b7  mov     [rbp+57h+var_60], eax
0x18000e8ba  test    eax, eax
0x18000e8bc  mov     eax, 201h
0x18000e8c1  js      short loc_18000E87E
0x18000e8c3  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x18000e8ca  mov     [rbp+57h+var_5C], ax
0x18000e8ce  lea     rcx, [rbp+57h+lpFileName]; this
0x18000e8d2  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000e8d7  mov     [rbp+57h+var_60], eax
0x18000e8da  test    eax, eax
0x18000e8dc  mov     eax, 202h
0x18000e8e1  js      short loc_18000E87E
0x18000e8e3  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18000e8e7  xor     r9d, r9d; lpSecurityAttributes
0x18000e8ea  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18000e8f3  xor     edx, edx; dwDesiredAccess
0x18000e8f5  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000e8fd  mov     [rbp+57h+var_5C], ax
0x18000e901  lea     r8d, [r9+7]; dwShareMode
0x18000e905  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e90d  call    cs:__imp_CreateFileW
0x18000e913  mov     rbx, rax
0x18000e916  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e91a  jz      short loc_18000E98A
0x18000e91c  mov     [rbp+57h+var_60], 0
0x18000e923  mov     eax, 207h
0x18000e928  mov     [rbp+57h+var_5C], ax
0x18000e92c  cmp     [rbp+57h+DestinationString.Buffer], 0
0x18000e931  jz      short loc_18000E954
0x18000e933  mov     rcx, gs:60h
0x18000e93c  xor     edx, edx; Flags
0x18000e93e  mov     r8, [rbp+57h+DestinationString.Buffer]; P
0x18000e942  mov     rcx, [rcx+30h]; HeapHandle
0x18000e946  call    cs:__imp_RtlFreeHeap
0x18000e94c  mov     [rbp+57h+DestinationString.Buffer], 0
0x18000e954  mov     edi, [rbp+57h+var_60]
0x18000e957  lea     rcx, [rbx-1]
0x18000e95b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000e95f  ja      short loc_18000E96A
0x18000e961  mov     rcx, rbx; hObject
0x18000e964  call    cs:__imp_CloseHandle
0x18000e96a  lea     rcx, [rbp+57h+lpFileName]; this
0x18000e96e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000e973  lea     rcx, [rbp+57h+var_60]; this
0x18000e977  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e97c  mov     eax, edi
0x18000e97e  add     rsp, 0A8h
0x18000e985  pop     rdi
0x18000e986  pop     rsi
0x18000e987  pop     rbx
0x18000e988  pop     rbp
0x18000e989  retn
0x18000e98a  xor     r9d, r9d; DirectoryInfo
0x18000e98d  lea     rdx, [rbp+57h+DestinationString]; NtPathName
0x18000e991  xor     r8d, r8d; NtFileNamePart
0x18000e994  mov     rcx, rdi; DosPathName
0x18000e997  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000e99d  test    al, al
0x18000e99f  mov     eax, 212h
0x18000e9a4  jnz     short loc_18000E9B2
0x18000e9a6  mov     [rbp+57h+var_60], 80070003h
0x18000e9ad  jmp     loc_18000E87E
0x18000e9b2  lea     rcx, [rbp+57h+DestinationString]; VolumeRootPath
0x18000e9b6  mov     [rbp+57h+var_60], 0
0x18000e9bd  mov     [rbp+57h+var_5C], ax
0x18000e9c1  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x18000e9c7  mov     esi, eax
0x18000e9c9  test    eax, eax
0x18000e9cb  jns     loc_18000E92C
0x18000e9d1  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18000e9d5  xor     r9d, r9d; lpSecurityAttributes
0x18000e9d8  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18000e9e1  xor     edx, edx; dwDesiredAccess
0x18000e9e3  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000e9eb  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e9f3  lea     r8d, [r9+7]; dwShareMode
0x18000e9f7  call    cs:__imp_CreateFileW
0x18000e9fd  mov     rbx, rax
0x18000ea00  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ea04  jz      short loc_18000EA17
0x18000ea06  mov     [rbp+57h+var_60], 0
0x18000ea0d  mov     eax, 21Ah
0x18000ea12  jmp     loc_18000E928
0x18000ea17  mov     ecx, esi
0x18000ea19  call    HRESULTFromNTSTATUS
0x18000ea1e  mov     [rbp+57h+var_60], eax
0x18000ea21  test    eax, eax
0x18000ea23  mov     eax, 21Eh
0x18000ea28  jns     loc_18000E928
0x18000ea2e  lea     r9, aS_0; "%S"
0x18000ea35  mov     [rbp+57h+var_5A], ax
0x18000ea39  mov     r8d, 3003h; unsigned int
0x18000ea3f  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdi
0x18000ea44  lea     rdx, c_wszEventSourceSPP; "SPP"
0x18000ea4b  lea     rcx, [rbp+57h+var_60]; this
0x18000ea4f  call    ?LogFailure@CSxFunctionTracer@@QEBAXPEBGK0ZZ; CSxFunctionTracer::LogFailure(ushort const *,ulong,ushort const *,...)
0x18000ea54  jmp     loc_18000E92C
```
