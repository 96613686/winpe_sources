# SrmCreateSystemVolumeInformationFolder(ushort const *)

- ea: `0x18007c16c`
- end: `0x18007c342`
- name: `?SrmCreateSystemVolumeInformationFolder@@YAXPEBG@Z`
- size: `470`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180077c54`

## callees

- `0x180001350`
- `0x1800026b0`
- `0x18000ab74`
- `0x18000ac44`
- `0x18000ee10`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180075034`
- `0x18007c16c`
- `0x18007ca74`
- `0x18007f150`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18007c248`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x18007c248`
- `ntdll!RtlInitUnicodeString` at `0x18007c23d`
- `ntdll!RtlInitUnicodeString` at `0x18007c23d`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18007c250`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18007c250`
- `KERNEL32!GetLastError` at `0x18007c256`
- `KERNEL32!GetLastError` at `0x18007c256`

## string_xrefs

- `0x18007c1a3`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007c1bb`: `SRMPATHC`
- `0x18007c1af`: `SrmCreateSystemVolumeInformationFolder`
- `0x18007c32e`: `RtlCreateSystemVolumeInformationFolder on volume %s returned %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall SrmCreateSystemVolumeInformationFolder(const unsigned __int16 *a1)
{
  const WCHAR *v2; // rdx
  NTSTATUS v3; // eax
  DWORD LastError; // eax
  DWORD v5; // edi
  __int64 v6; // rdx
  __int64 v7; // r8
  const unsigned __int16 *v8; // rax
  unsigned __int16 **v9; // rdx
  unsigned __int16 *Buffer; // rbx
  __int64 v11; // rax
  __int64 v12; // [rsp+20h] [rbp-E0h]
  _QWORD *v13; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v15; // [rsp+58h] [rbp-A8h]
  _QWORD v16[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+80h] [rbp-80h]
  _BYTE v18[96]; // [rsp+88h] [rbp-78h] BYREF
  int v19; // [rsp+E8h] [rbp-18h]
  PCWSTR SourceString[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v21; // [rsp+100h] [rbp+0h]
  unsigned __int64 v22; // [rsp+108h] [rbp+8h]
  _QWORD v23[22]; // [rsp+120h] [rbp+20h] BYREF

  v13 = v16;
  v16[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v16[1] = L"SrmCreateSystemVolumeInformationFolder";
  v16[2] = L"SRMPATHC";
  v16[3] = 1014;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v23, (const struct CSrmDebugInfo *)v16, 0);
  v22 = 7;
  v21 = 0;
  LOWORD(SourceString[0]) = 0;
  SrmDosPathNameToRelativeNtPathName(a1, SourceString);
  DestinationString = 0;
  v2 = (const WCHAR *)SourceString;
  if ( v22 >= 8 )
    v2 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v2);
  v3 = RtlCreateSystemVolumeInformationFolder(&DestinationString);
  RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v3);
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError && LastError != 183 )
  {
    CSrmAutoPWSZ::CSrmAutoPWSZ((CSrmAutoPWSZ *)&v13);
    CSrmAutoPWSZ::operator&(&v13, v6, v7);
    v8 = (const unsigned __int16 *)std::wstring::c_str(SourceString);
    SrmGetDisplayPathForFilePath(v8, v9);
    Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&v13);
    v15 = v16;
    v11 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v16,
            (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
            (__int64)L"SRMPATHC",
            (__int64)L"SrmCreateSystemVolumeInformationFolder",
            1045,
            17);
    LODWORD(v12) = v5;
    CSrmFunctionTracer::TranslateWin32Error(
      v23,
      v11,
      L"RtlCreateSystemVolumeInformationFolder on volume %s returned %#x",
      Buffer,
      v12);
  }
  if ( v22 >= 8 )
    operator delete((void *)SourceString[0]);
  v22 = 7;
  v21 = 0;
  LOWORD(SourceString[0]) = 0;
  v23[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v23);
}

```

## disassembly

```asm
0x18007c16c  push    rbp
0x18007c16e  push    rbx
0x18007c16f  push    rdi
0x18007c170  push    r12
0x18007c172  push    r13
0x18007c174  push    r15
0x18007c176  lea     rbp, [rsp-0E8h]
0x18007c17e  sub     rsp, 1E8h
0x18007c185  mov     rax, cs:__security_cookie
0x18007c18c  xor     rax, rsp
0x18007c18f  mov     [rbp+110h+var_40], rax
0x18007c196  mov     rbx, rcx
0x18007c199  lea     rax, [rsp+210h+var_1B0]
0x18007c19e  mov     [rsp+210h+var_1D0], rax
0x18007c1a3  lea     r15, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007c1aa  mov     [rsp+210h+var_1B0], r15
0x18007c1af  lea     r12, aSrmcreatesyste; "SrmCreateSystemVolumeInformationFolder"
0x18007c1b6  mov     [rsp+210h+var_1A8], r12
0x18007c1bb  lea     r13, aSrmpathc; "SRMPATHC"
0x18007c1c2  mov     [rsp+210h+var_1A0], r13
0x18007c1c7  mov     [rsp+210h+var_198], 3F6h
0x18007c1d0  mov     [rbp+110h+var_190], 0FFh
0x18007c1d7  mov     [rbp+110h+var_128], 1000000h
0x18007c1de  xor     edx, edx; Val
0x18007c1e0  lea     r8d, [rdx+60h]; Size
0x18007c1e4  lea     rcx, [rbp+110h+var_188]; void *
0x18007c1e8  call    memset_0
0x18007c1ed  nop
0x18007c1ee  xor     r8d, r8d
0x18007c1f1  lea     rdx, [rsp+210h+var_1B0]
0x18007c1f6  lea     rcx, [rbp+110h+var_F0]
0x18007c1fa  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007c1ff  nop
0x18007c200  mov     [rbp+110h+var_108], 7
0x18007c208  mov     [rbp+110h+var_110], 0
0x18007c210  xor     eax, eax
0x18007c212  mov     word ptr [rbp+110h+SourceString], ax
0x18007c216  lea     rdx, [rbp+110h+SourceString]; void *
0x18007c21a  mov     rcx, rbx; DosName
0x18007c21d  call    ?SrmDosPathNameToRelativeNtPathName@@YAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SrmDosPathNameToRelativeNtPathName(ushort const *,std::wstring &)
0x18007c222  xorps   xmm0, xmm0
0x18007c225  movups  xmmword ptr [rsp+210h+DestinationString.Length], xmm0
0x18007c22a  lea     rdx, [rbp+110h+SourceString]
0x18007c22e  cmp     [rbp+110h+var_108], 8
0x18007c233  cmovnb  rdx, [rbp+110h+SourceString]; SourceString
0x18007c238  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x18007c23d  call    cs:__imp_RtlInitUnicodeString
0x18007c243  lea     rcx, [rsp+210h+DestinationString]; VolumeRootPath
0x18007c248  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x18007c24e  mov     ecx, eax; Status
0x18007c250  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x18007c256  call    cs:__imp_GetLastError
0x18007c25c  mov     edi, eax
0x18007c25e  test    eax, eax
0x18007c260  jz      short loc_18007C269
0x18007c262  cmp     eax, 0B7h
0x18007c267  jnz     short loc_18007C2C3
0x18007c269  cmp     [rbp+110h+var_108], 8
0x18007c26e  jb      short loc_18007C279
0x18007c270  mov     rcx, [rbp+110h+SourceString]; Block
0x18007c274  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c279  mov     [rbp+110h+var_108], 7
0x18007c281  mov     [rbp+110h+var_110], 0
0x18007c289  xor     eax, eax
0x18007c28b  mov     word ptr [rbp+110h+SourceString], ax
0x18007c28f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007c296  mov     [rbp+110h+var_F0], rax
0x18007c29a  lea     rcx, [rbp+110h+var_F0]; this
0x18007c29e  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007c2a3  mov     rcx, [rbp+110h+var_40]
0x18007c2aa  xor     rcx, rsp; StackCookie
0x18007c2ad  call    __security_check_cookie
0x18007c2b2  add     rsp, 1E8h
0x18007c2b9  pop     r15
0x18007c2bb  pop     r13
0x18007c2bd  pop     r12
0x18007c2bf  pop     rdi
0x18007c2c0  pop     rbx
0x18007c2c1  pop     rbp
0x18007c2c2  retn
0x18007c2c3  lea     rcx, [rsp+210h+var_1D0]; this
0x18007c2c8  call    ??0CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::CSrmAutoPWSZ(void)
0x18007c2cd  nop
0x18007c2ce  lea     rcx, [rsp+210h+var_1D0]
0x18007c2d3  call    ??ICSrmAutoPWSZ@@QEAAPEAPEAGXZ; CSrmAutoPWSZ::operator&(void)
0x18007c2d8  mov     rdx, rax
0x18007c2db  lea     rcx, [rbp+110h+SourceString]
0x18007c2df  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007c2e4  mov     rcx, rax; unsigned __int16 *
0x18007c2e7  call    ?SrmGetDisplayPathForFilePath@@YAXPEBGPEAPEAG@Z; SrmGetDisplayPathForFilePath(ushort const *,ushort * *)
0x18007c2ec  lea     rcx, [rsp+210h+var_1D0]; this
0x18007c2f1  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x18007c2f6  mov     rbx, rax
0x18007c2f9  lea     rax, [rsp+210h+var_1B0]
0x18007c2fe  mov     [rsp+210h+var_1B8], rax
0x18007c303  mov     [rsp+210h+var_1E8], 11h
0x18007c30b  mov     dword ptr [rsp+210h+var_1F0], 415h
0x18007c313  mov     r9, r12
0x18007c316  mov     r8, r13
0x18007c319  mov     rdx, r15
0x18007c31c  lea     rcx, [rsp+210h+var_1B0]
0x18007c321  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007c326  nop
0x18007c327  mov     dword ptr [rsp+210h+var_1F0], edi
0x18007c32b  mov     r9, rbx
0x18007c32e  lea     r8, aRtlcreatesyste; "RtlCreateSystemVolumeInformationFolder "...
0x18007c335  mov     rdx, rax
0x18007c338  lea     rcx, [rbp+110h+var_F0]
0x18007c33c  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
```
