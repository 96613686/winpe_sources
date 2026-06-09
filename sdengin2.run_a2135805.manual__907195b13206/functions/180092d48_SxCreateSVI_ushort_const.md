# SxCreateSVI(ushort const *)

- ea: `0x180092d48`
- end: `0x180092ff2`
- name: `?SxCreateSVI@@YAJPEBG@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800b9a24`
- `0x1800bab44`

## callees

- `0x180008588`
- `0x180072e08`
- `0x180072f14`
- `0x180073314`
- `0x180092d48`
- `0x180093698`
- `0x18009dd7c`
- `0x18009e904`
- `0x18009ea6c`
- `0x18009f560`

## import_xrefs

- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180092f4e`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180092f4e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180092f1e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180092f1e`
- `ntdll!RtlInitUnicodeString` at `0x180092dd0`
- `ntdll!RtlInitUnicodeString` at `0x180092dd0`
- `ntdll!RtlFreeHeap` at `0x180092ec0`
- `ntdll!RtlFreeHeap` at `0x180092ec0`
- `KERNEL32!CreateFileW` at `0x180092e81`
- `KERNEL32!CreateFileW` at `0x180092f8a`
- `KERNEL32!CreateFileW` at `0x180092e81`
- `KERNEL32!CreateFileW` at `0x180092f8a`
- `KERNEL32!CloseHandle` at `0x180092ee4`
- `KERNEL32!CloseHandle` at `0x180092ee4`

## string_xrefs

- `0x180092d96`: `SxCreateSVI`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "SxCreateSVI", 0x1F5u, 1u);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
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
0x180092d48  push    rbp
0x180092d4a  push    rbx
0x180092d4b  push    rsi
0x180092d4c  push    rdi
0x180092d4d  lea     rbp, [rsp-3Fh]
0x180092d52  sub     rsp, 0A8h
0x180092d59  mov     rdi, rcx
0x180092d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180092d63  lea     rax, WPP_GLOBAL_Control
0x180092d6a  cmp     rcx, rax
0x180092d6d  jz      short loc_180092D90
0x180092d6f  test    dword ptr [rcx+1Ch], 20000000h
0x180092d76  jz      short loc_180092D90
0x180092d78  mov     rcx, [rcx+10h]
0x180092d7c  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x180092d83  mov     edx, 13h
0x180092d88  mov     r9, rdi
0x180092d8b  call    WPP_SF_q
0x180092d90  mov     r9d, 1; unsigned __int16
0x180092d96  lea     rdx, aSxcreatesvi; "SxCreateSVI"
0x180092d9d  mov     r8d, 1F5h; unsigned __int16
0x180092da3  lea     rcx, [rbp+57h+var_60]; this
0x180092da7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180092dac  xorps   xmm0, xmm0
0x180092daf  mov     [rbp+57h+var_78], 0
0x180092db7  lea     rax, qword_1800EE510
0x180092dbe  xor     edx, edx; SourceString
0x180092dc0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180092dc4  mov     [rbp+57h+lpFileName], rax
0x180092dc8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180092dcc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180092dd0  call    cs:__imp_RtlInitUnicodeString
0x180092dd7  nop     dword ptr [rax+rax+00h]
0x180092ddc  mov     eax, 1FEh
0x180092de1  test    rdi, rdi
0x180092de4  jnz     short loc_180092DF6
0x180092de6  mov     [rbp+57h+var_60], 80070057h
0x180092ded  mov     [rbp+57h+var_5A], ax
0x180092df1  jmp     loc_180092EA6
0x180092df6  mov     rdx, rdi; unsigned __int16 *
0x180092df9  mov     [rbp+57h+var_60], 0
0x180092e00  lea     rcx, [rbp+57h+lpFileName]; this
0x180092e04  mov     [rbp+57h+var_5C], ax
0x180092e08  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180092e0d  mov     [rbp+57h+var_60], eax
0x180092e10  test    eax, eax
0x180092e12  mov     eax, 200h
0x180092e17  js      short loc_180092DED
0x180092e19  mov     edx, 5Ch ; '\'; unsigned __int16
0x180092e1e  mov     [rbp+57h+var_5C], ax
0x180092e22  lea     rcx, [rbp+57h+lpFileName]; this
0x180092e26  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180092e2b  mov     [rbp+57h+var_60], eax
0x180092e2e  test    eax, eax
0x180092e30  mov     eax, 201h
0x180092e35  js      short loc_180092DED
0x180092e37  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x180092e3e  mov     [rbp+57h+var_5C], ax
0x180092e42  lea     rcx, [rbp+57h+lpFileName]; this
0x180092e46  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180092e4b  mov     [rbp+57h+var_60], eax
0x180092e4e  test    eax, eax
0x180092e50  mov     eax, 202h
0x180092e55  js      short loc_180092DED
0x180092e57  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180092e5b  xor     r9d, r9d; lpSecurityAttributes
0x180092e5e  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x180092e67  xor     edx, edx; dwDesiredAccess
0x180092e69  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180092e71  mov     [rbp+57h+var_5C], ax
0x180092e75  lea     r8d, [r9+7]; dwShareMode
0x180092e79  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180092e81  call    cs:__imp_CreateFileW
0x180092e88  nop     dword ptr [rax+rax+00h]
0x180092e8d  mov     rbx, rax
0x180092e90  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180092e94  jz      short loc_180092F11
0x180092e96  mov     [rbp+57h+var_60], 0
0x180092e9d  mov     eax, 207h
0x180092ea2  mov     [rbp+57h+var_5C], ax
0x180092ea6  cmp     [rbp+57h+DestinationString.Buffer], 0
0x180092eab  jz      short loc_180092ED4
0x180092ead  mov     rcx, gs:60h
0x180092eb6  xor     edx, edx; Flags
0x180092eb8  mov     r8, [rbp+57h+DestinationString.Buffer]; P
0x180092ebc  mov     rcx, [rcx+30h]; HeapHandle
0x180092ec0  call    cs:__imp_RtlFreeHeap
0x180092ec7  nop     dword ptr [rax+rax+00h]
0x180092ecc  mov     [rbp+57h+DestinationString.Buffer], 0
0x180092ed4  mov     edi, [rbp+57h+var_60]
0x180092ed7  lea     rcx, [rbx-1]
0x180092edb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180092edf  ja      short loc_180092EF0
0x180092ee1  mov     rcx, rbx; hObject
0x180092ee4  call    cs:__imp_CloseHandle
0x180092eeb  nop     dword ptr [rax+rax+00h]
0x180092ef0  lea     rcx, [rbp+57h+lpFileName]; this
0x180092ef4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180092ef9  lea     rcx, [rbp+57h+var_60]; this
0x180092efd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180092f02  mov     eax, edi
0x180092f04  add     rsp, 0A8h
0x180092f0b  pop     rdi
0x180092f0c  pop     rsi
0x180092f0d  pop     rbx
0x180092f0e  pop     rbp
0x180092f0f  retn
0x180092f11  xor     r9d, r9d; DirectoryInfo
0x180092f14  lea     rdx, [rbp+57h+DestinationString]; NtPathName
0x180092f18  xor     r8d, r8d; NtFileNamePart
0x180092f1b  mov     rcx, rdi; DosPathName
0x180092f1e  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180092f25  nop     dword ptr [rax+rax+00h]
0x180092f2a  test    al, al
0x180092f2c  mov     eax, 212h
0x180092f31  jnz     short loc_180092F3F
0x180092f33  mov     [rbp+57h+var_60], 80070003h
0x180092f3a  jmp     loc_180092DED
0x180092f3f  lea     rcx, [rbp+57h+DestinationString]; VolumeRootPath
0x180092f43  mov     [rbp+57h+var_60], 0
0x180092f4a  mov     [rbp+57h+var_5C], ax
0x180092f4e  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x180092f55  nop     dword ptr [rax+rax+00h]
0x180092f5a  mov     esi, eax
0x180092f5c  test    eax, eax
0x180092f5e  jns     loc_180092EA6
0x180092f64  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180092f68  xor     r9d, r9d; lpSecurityAttributes
0x180092f6b  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x180092f74  xor     edx, edx; dwDesiredAccess
0x180092f76  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180092f7e  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180092f86  lea     r8d, [r9+7]; dwShareMode
0x180092f8a  call    cs:__imp_CreateFileW
0x180092f91  nop     dword ptr [rax+rax+00h]
0x180092f96  mov     rbx, rax
0x180092f99  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180092f9d  jz      short loc_180092FB0
0x180092f9f  mov     [rbp+57h+var_60], 0
0x180092fa6  mov     eax, 21Ah
0x180092fab  jmp     loc_180092EA2
0x180092fb0  mov     ecx, esi
0x180092fb2  call    HRESULTFromNTSTATUS
0x180092fb7  mov     [rbp+57h+var_60], eax
0x180092fba  test    eax, eax
0x180092fbc  mov     eax, 21Eh
0x180092fc1  jns     loc_180092EA2
0x180092fc7  lea     r9, aS_2; "%S"
0x180092fce  mov     [rbp+57h+var_5A], ax
0x180092fd2  mov     r8d, 3003h; unsigned int
0x180092fd8  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdi
0x180092fdd  lea     rdx, c_wszEventSourceSPP; "SPP"
0x180092fe4  lea     rcx, [rbp+57h+var_60]; this
0x180092fe8  call    ?LogFailure@CSxFunctionTracer@@QEBAXPEBGK0ZZ; CSxFunctionTracer::LogFailure(ushort const *,ulong,ushort const *,...)
0x180092fed  jmp     loc_180092EA6
```
