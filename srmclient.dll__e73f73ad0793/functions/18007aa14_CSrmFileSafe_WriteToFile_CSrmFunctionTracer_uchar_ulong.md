# CSrmFileSafe::WriteToFile(CSrmFunctionTracer &,uchar *,ulong)

- ea: `0x18007aa14`
- end: `0x18007acef`
- name: `?WriteToFile@CSrmFileSafe@@AEAAXAEAVCSrmFunctionTracer@@PEAEK@Z`
- size: `731`
- prototype: `void(CSrmFileSafe *__hidden this, struct CSrmFunctionTracer *, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180079b9c`
- `0x18007a3b8`
- `0x18007a848`

## callees

- `0x1800026b0`
- `0x18000ab74`
- `0x18000ac10`
- `0x18000ac44`
- `0x18000ee10`
- `0x18006fe68`
- `0x18007006c`
- `0x180070380`
- `0x180071efc`
- `0x180073d04`
- `0x180074048`
- `0x180074a04`
- `0x18007aa14`
- `0x18007f650`
- `0x1800b078a`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18007aa65`
- `KERNEL32!WriteFile` at `0x18007aa65`
- `KERNEL32!GetLastError` at `0x18007aa73`
- `KERNEL32!GetLastError` at `0x18007aa73`

## string_xrefs

- `0x18007acd6`: `Volume not ready for SRM store file %s`
- `0x18007aae8`: `WriteFile for SRM store file %s failed with %lu`
- `0x18007aa9a`: `CSrmFileSafe::WriteToFile`
- `0x18007ac29`: `WriteFile('%s')`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSrmFileSafe::WriteToFile(HANDLE *this, struct CSrmFunctionTracer *a2, unsigned __int8 *a3, DWORD a4)
{
  unsigned __int64 LastError; // rbx
  _QWORD *v7; // rdi
  _QWORD *v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  unsigned __int16 **v12; // rax
  const unsigned __int16 *v13; // r8
  unsigned __int16 *Buffer; // rax
  struct CSrmDebugInfo *v15; // r10
  CSrmDebugInfo *v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rax
  unsigned __int16 *v19; // rax
  struct CSrmDebugInfo *v20; // r9
  CSrmDebugInfo *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-E0h]
  LPVOID v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v26[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+6Ch] [rbp-94h]
  int v29; // [rsp+70h] [rbp-90h]
  _BYTE v30[96]; // [rsp+78h] [rbp-88h] BYREF
  int v31; // [rsp+D8h] [rbp-28h]
  _BYTE v32[144]; // [rsp+E0h] [rbp-20h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+1A0h] [rbp+A0h] BYREF

  NumberOfBytesWritten = 0;
  if ( !WriteFile(this[27], a3, a4, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    v7 = this + 15;
    if ( v7[3] < 8u )
      v8 = v7;
    else
      v8 = (_QWORD *)*v7;
    v26[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v26[1] = L"CSrmFileSafe::WriteToFile";
    v26[2] = L"FILESF_C";
    v27 = 714;
    v28 = 17;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(v30, 0, sizeof(v30));
    LODWORD(lpOverlapped) = LastError;
    CSrmFunctionTracer::Trace(a2, v26, L"WriteFile for SRM store file %s failed with %lu", v8, lpOverlapped);
    if ( (unsigned int)LastError > 0x37 || (v9 = 0x80000000280020LL, !_bittest64(&v9, LastError)) )
    {
      if ( (_DWORD)LastError == 112 )
      {
        CSrmAutoPWSZ::CSrmAutoPWSZ((CSrmAutoPWSZ *)v25);
        v10 = std::wstring::c_str(v7);
        v12 = (unsigned __int16 **)CSrmAutoPWSZ::operator&(v25, v11, v10);
        SrmGetVolumeDisplayNameForPath(v13, v12);
        CSrmDebugInfo::CSrmDebugInfo(
          (__int64)v26,
          (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
          (__int64)L"FILESF_C",
          (__int64)L"CSrmFileSafe::WriteToFile",
          723,
          17);
        Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)v25);
        v16 = CSrmDebugInfo::operator<<(v15, (CSrmDebugInfo *)v32, Buffer);
        CSrmFunctionTracer::LogError((__int64)a2, 0x8004301E, (__int64)v16, 1u);
        CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v26);
        CSrmAutoPWSZ::~CSrmAutoPWSZ(v25);
        goto LABEL_12;
      }
      if ( (_DWORD)LastError != 1167 )
      {
LABEL_12:
        v17 = std::wstring::c_str(v7);
        if ( (int)LastError > 0 )
          LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
        v18 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v32,
                (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
                (__int64)L"FILESF_C",
                (__int64)L"CSrmFileSafe::WriteToFile",
                746,
                17);
        CSrmFunctionTracer::TranslateGenericError(a2, v18, (unsigned int)LastError, L"WriteFile('%s')", v17);
      }
    }
    CSrmDebugInfo::CSrmDebugInfo(
      (__int64)v32,
      (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
      (__int64)L"FILESF_C",
      (__int64)L"CSrmFileSafe::WriteToFile",
      736,
      17);
    v19 = (unsigned __int16 *)std::wstring::c_str(v7);
    v21 = CSrmDebugInfo::operator<<(v20, (CSrmDebugInfo *)v26, v19);
    CSrmFunctionTracer::LogError((__int64)a2, 0x80042039, (__int64)v21, 2u);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v32);
    v22 = std::wstring::c_str(v7);
    v23 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v32,
            (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            (__int64)L"FILESF_C",
            (__int64)L"CSrmFileSafe::WriteToFile",
            739,
            17);
    CSrmFunctionTracer::Throw(a2, v23, 2147767142LL, L"Volume not ready for SRM store file %s", v22);
  }
}

```

## disassembly

```asm
0x18007aa14  mov     [rsp-8+arg_8], rbx
0x18007aa19  mov     [rsp-8+arg_10], rsi
0x18007aa1e  push    rbp
0x18007aa1f  push    rdi
0x18007aa20  push    r12
0x18007aa22  push    r13
0x18007aa24  push    r14
0x18007aa26  lea     rbp, [rsp-70h]
0x18007aa2b  sub     rsp, 170h
0x18007aa32  mov     eax, r9d
0x18007aa35  mov     r10, r8
0x18007aa38  mov     r14, rdx
0x18007aa3b  mov     rdi, rcx
0x18007aa3e  mov     [rbp+90h+NumberOfBytesWritten], 0
0x18007aa48  mov     [rsp+190h+lpOverlapped], 0; lpOverlapped
0x18007aa51  lea     r9, [rbp+90h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007aa58  mov     r8d, eax; nNumberOfBytesToWrite
0x18007aa5b  mov     rdx, r10; lpBuffer
0x18007aa5e  mov     rcx, [rcx+0D8h]; hFile
0x18007aa65  call    cs:__imp_WriteFile
0x18007aa6b  test    eax, eax
0x18007aa6d  jnz     loc_18007AB2B
0x18007aa73  call    cs:__imp_GetLastError
0x18007aa79  mov     ebx, eax
0x18007aa7b  add     rdi, 78h ; 'x'
0x18007aa7f  cmp     qword ptr [rdi+18h], 8
0x18007aa84  jb      short loc_18007AA8B
0x18007aa86  mov     rsi, [rdi]
0x18007aa89  jmp     short loc_18007AA8E
0x18007aa8b  mov     rsi, rdi
0x18007aa8e  lea     r12, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x18007aa95  mov     [rsp+190h+var_140], r12
0x18007aa9a  lea     r13, aCsrmfilesafeWr; "CSrmFileSafe::WriteToFile"
0x18007aaa1  mov     [rsp+190h+var_138], r13
0x18007aaa6  lea     rax, aFilesfC; "FILESF_C"
0x18007aaad  mov     [rsp+190h+var_130], rax
0x18007aab2  mov     [rsp+190h+var_128], 2CAh
0x18007aaba  mov     [rsp+190h+var_124], 11h
0x18007aac2  mov     [rsp+190h+var_120], 0FFh
0x18007aaca  mov     [rbp+90h+var_B8], 1000000h
0x18007aad1  xor     edx, edx; Val
0x18007aad3  lea     r8d, [rdx+60h]; Size
0x18007aad7  lea     rcx, [rsp+190h+var_118]; void *
0x18007aadc  call    memset_0
0x18007aae1  mov     dword ptr [rsp+190h+lpOverlapped], ebx
0x18007aae5  mov     r9, rsi
0x18007aae8  lea     r8, aWritefileForSr; "WriteFile for SRM store file %s failed "...
0x18007aaef  lea     rdx, [rsp+190h+var_140]
0x18007aaf4  mov     rcx, r14
0x18007aaf7  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007aafc  cmp     ebx, 37h ; '7'
0x18007aaff  ja      short loc_18007AB15
0x18007ab01  mov     rcx, 80000000280020h
0x18007ab0b  bt      rcx, rbx
0x18007ab0f  jb      loc_18007AC3F
0x18007ab15  cmp     ebx, 70h ; 'p'
0x18007ab18  jz      short loc_18007AB4C
0x18007ab1a  cmp     ebx, 48Fh
0x18007ab20  jz      loc_18007AC3F
0x18007ab26  jmp     loc_18007ABE6
0x18007ab2b  lea     r11, [rsp+190h+var_20]
0x18007ab33  mov     rbx, [r11+38h]
0x18007ab37  mov     rsi, [r11+40h]
0x18007ab3b  mov     rsp, r11
0x18007ab3e  pop     r14
0x18007ab40  pop     r13
0x18007ab42  pop     r12
0x18007ab44  pop     rdi
0x18007ab45  pop     rbp
0x18007ab46  retn
0x18007ab47  jmp     loc_18007ABE6
0x18007ab4c  lea     rcx, [rsp+190h+var_150]; this
0x18007ab51  call    ??0CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::CSrmAutoPWSZ(void)
0x18007ab56  nop
0x18007ab57  mov     rcx, rdi
0x18007ab5a  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007ab5f  mov     r8, rax
0x18007ab62  lea     rcx, [rsp+190h+var_150]
0x18007ab67  call    ??ICSrmAutoPWSZ@@QEAAPEAPEAGXZ; CSrmAutoPWSZ::operator&(void)
0x18007ab6c  mov     rdx, rax; unsigned __int16 **
0x18007ab6f  mov     rcx, r8; unsigned __int16 *
0x18007ab72  call    ?SrmGetVolumeDisplayNameForPath@@YAXPEBGPEAPEAG@Z; SrmGetVolumeDisplayNameForPath(ushort const *,ushort * *)
0x18007ab77  mov     [rsp+190h+var_168], 11h
0x18007ab7f  mov     dword ptr [rsp+190h+lpOverlapped], 2D3h
0x18007ab87  mov     r9, r13
0x18007ab8a  lea     r8, aFilesfC; "FILESF_C"
0x18007ab91  mov     rdx, r12
0x18007ab94  lea     rcx, [rsp+190h+var_140]
0x18007ab99  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007ab9e  mov     r10, rax
0x18007aba1  lea     rcx, [rsp+190h+var_150]; this
0x18007aba6  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x18007abab  mov     r8, rax; unsigned __int16 *
0x18007abae  lea     rdx, [rbp+90h+var_B0]; this
0x18007abb2  mov     rcx, r10; struct CSrmDebugInfo *
0x18007abb5  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x18007abba  mov     r9d, 1
0x18007abc0  mov     r8, rax
0x18007abc3  mov     edx, 8004301Eh
0x18007abc8  mov     rcx, r14
0x18007abcb  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x18007abd0  nop
0x18007abd1  lea     rcx, [rsp+190h+var_140]; this
0x18007abd6  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18007abdb  nop
0x18007abdc  lea     rcx, [rsp+190h+var_150]; this
0x18007abe1  call    ??1CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::~CSrmAutoPWSZ(void)
0x18007abe6  mov     rcx, rdi
0x18007abe9  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007abee  mov     rdi, rax
0x18007abf1  test    ebx, ebx
0x18007abf3  jle     short loc_18007ABFE
0x18007abf5  movzx   ebx, bx
0x18007abf8  or      ebx, 80070000h
0x18007abfe  mov     [rsp+190h+var_168], 11h
0x18007ac06  mov     dword ptr [rsp+190h+lpOverlapped], 2EAh
0x18007ac0e  mov     r9, r13
0x18007ac11  lea     r8, aFilesfC; "FILESF_C"
0x18007ac18  mov     rdx, r12
0x18007ac1b  lea     rcx, [rbp+90h+var_B0]
0x18007ac1f  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007ac24  mov     [rsp+190h+lpOverlapped], rdi
0x18007ac29  lea     r9, aWritefileS; "WriteFile('%s')"
0x18007ac30  mov     r8d, ebx
0x18007ac33  mov     rdx, rax
0x18007ac36  mov     rcx, r14
0x18007ac39  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18007ac3f  mov     [rsp+190h+var_168], 11h
0x18007ac47  mov     dword ptr [rsp+190h+lpOverlapped], 2E0h
0x18007ac4f  mov     r9, r13
0x18007ac52  lea     r8, aFilesfC; "FILESF_C"
0x18007ac59  mov     rdx, r12
0x18007ac5c  lea     rcx, [rbp+90h+var_B0]
0x18007ac60  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007ac65  mov     r9, rax
0x18007ac68  mov     rcx, rdi
0x18007ac6b  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007ac70  mov     r8, rax; unsigned __int16 *
0x18007ac73  lea     rdx, [rsp+190h+var_140]; this
0x18007ac78  mov     rcx, r9; struct CSrmDebugInfo *
0x18007ac7b  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x18007ac80  mov     r9d, 2
0x18007ac86  mov     r8, rax
0x18007ac89  mov     edx, 80042039h
0x18007ac8e  mov     rcx, r14
0x18007ac91  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x18007ac96  nop
0x18007ac97  lea     rcx, [rbp+90h+var_B0]; this
0x18007ac9b  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18007aca0  mov     rcx, rdi
0x18007aca3  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007aca8  mov     rbx, rax
0x18007acab  mov     [rsp+190h+var_168], 11h
0x18007acb3  mov     dword ptr [rsp+190h+lpOverlapped], 2E3h
0x18007acbb  mov     r9, r13
0x18007acbe  lea     r8, aFilesfC; "FILESF_C"
0x18007acc5  mov     rdx, r12
0x18007acc8  lea     rcx, [rbp+90h+var_B0]
0x18007accc  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007acd1  mov     [rsp+190h+lpOverlapped], rbx
0x18007acd6  lea     r9, aVolumeNotReady; "Volume not ready for SRM store file %s"
0x18007acdd  mov     r8d, 80045366h
0x18007ace3  mov     rdx, rax
0x18007ace6  mov     rcx, r14
0x18007ace9  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
