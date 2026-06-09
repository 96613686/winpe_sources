# CSpp::_GetMinDiffAreaSize(ushort const *,unsigned __int64 *)

- ea: `0x180019780`
- end: `0x1800199fc`
- name: `?_GetMinDiffAreaSize@CSpp@@CAJPEBGPEA_K@Z`
- size: `636`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000c910`
- `0x18000f270`

## callees

- `0x180019780`
- `0x180020710`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18003532c`
- `0x180035464`
- `0x180035b00`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001989a`
- `KERNEL32!CreateFileW` at `0x18001989a`
- `KERNEL32!DeviceIoControl` at `0x180019957`
- `KERNEL32!DeviceIoControl` at `0x180019957`
- `KERNEL32!CloseHandle` at `0x1800199cb`
- `KERNEL32!CloseHandle` at `0x1800199cb`

## pseudocode

```c
__int64 __fastcall CSpp::_GetMinDiffAreaSize(const unsigned __int16 *a1, unsigned __int64 *a2)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  unsigned __int16 v6; // dx
  LPCWSTR v7; // r14
  __int64 v8; // rcx
  HANDLE FileW; // rdi
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-19h] BYREF
  int v15; // [rsp+50h] [rbp-9h] BYREF
  __int16 v16; // [rsp+54h] [rbp-5h]
  __int16 v17; // [rsp+56h] [rbp-3h]
  DWORD BytesReturned; // [rsp+C0h] [rbp+67h] BYREF
  unsigned __int64 OutBuffer; // [rsp+D0h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "CSpp::_GetMinDiffAreaSize", 12675, 1);
  lpFileName[1] = 0;
  lpFileName[0] = &FileName;
  v4 = 12680;
  OutBuffer = 0;
  BytesReturned = 0;
  if ( !a1 || (v16 = 12680, v4 = 12681, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
    v15 = -2147024809;
LABEL_6:
    v17 = v4;
    goto LABEL_22;
  }
  v15 = 0;
  v16 = 12681;
  *a2 = 0;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)lpFileName, a1);
  v15 = LastFailureAsHRESULT;
  v4 = 12685;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v16 = 12685;
  CBsString::UnTrailing((CBsString *)lpFileName, v6);
  v7 = lpFileName[0];
  FileW = CreateFileW(lpFileName[0], 0x80000000, 3u, 0, 3u, 0x2000080u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v16 = 12697;
    v15 = 0;
    if ( DeviceIoControl(FileW, 0x534058u, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
    {
      LastFailureAsHRESULT = 0;
      v15 = 0;
      v16 = 12705;
      *a2 = OutBuffer;
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
      v15 = LastFailureAsHRESULT;
      v17 = 12705;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          221,
          (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
          (unsigned int)"DeviceIoControl( shVolume, IOCTL_VOLSNAP_QUERY_DIFF_AREA_MINIMUM_SIZE, NULL, 0, &minDiffAreaSize"
                        ", sizeof( minDiffAreaSize ), &cBytes, NULL )",
          (__int64)v7,
          LastFailureAsHRESULT);
        LastFailureAsHRESULT = v15;
      }
    }
    goto LABEL_21;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
  v15 = LastFailureAsHRESULT;
  v17 = 12697;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      220,
      (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
      (unsigned int)"shVolume.IsValid()",
      (__int64)v7,
      LastFailureAsHRESULT);
    LastFailureAsHRESULT = v15;
  }
  if ( FileW != (HANDLE)-1LL && FileW )
LABEL_21:
    CloseHandle(FileW);
LABEL_22:
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15, v11, v12);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180019780  mov     [rsp-8+arg_8], rbx
0x180019785  push    rbp
0x180019786  push    rsi
0x180019787  push    rdi
0x180019788  push    r12
0x18001978a  push    r14
0x18001978c  lea     rbp, [rsp-37h]
0x180019791  sub     rsp, 90h
0x180019798  mov     rsi, rdx
0x18001979b  mov     rbx, rcx
0x18001979e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197a5  lea     r12, WPP_GLOBAL_Control
0x1800197ac  cmp     rcx, r12
0x1800197af  jz      short loc_1800197CF
0x1800197b1  test    dword ptr [rcx+1Ch], 20000000h
0x1800197b8  jz      short loc_1800197CF
0x1800197ba  mov     rcx, [rcx+10h]
0x1800197be  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800197c5  mov     edx, 0DBh
0x1800197ca  call    WPP_SF_
0x1800197cf  mov     r9d, 1; unsigned __int16
0x1800197d5  lea     rdx, aCsppGetmindiff; "CSpp::_GetMinDiffAreaSize"
0x1800197dc  mov     r8d, 3183h; unsigned __int16
0x1800197e2  lea     rcx, [rbp+57h+var_60]; this
0x1800197e6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800197eb  mov     [rbp+57h+var_68], 0
0x1800197f3  lea     rax, FileName
0x1800197fa  mov     [rbp+57h+lpFileName], rax
0x1800197fe  mov     eax, 3188h
0x180019803  mov     [rbp+57h+OutBuffer], 0
0x18001980b  mov     [rbp+57h+BytesReturned], 0
0x180019812  test    rbx, rbx
0x180019815  jnz     short loc_180019828
0x180019817  mov     ebx, 80070057h
0x18001981c  mov     [rbp+57h+var_60], ebx
0x18001981f  mov     [rbp+57h+var_5A], ax
0x180019823  jmp     loc_1800199D1
0x180019828  mov     [rbp+57h+var_5C], ax
0x18001982c  mov     eax, 3189h
0x180019831  test    rsi, rsi
0x180019834  jz      short loc_180019817
0x180019836  mov     rdx, rbx; unsigned __int16 *
0x180019839  mov     [rbp+57h+var_60], 0
0x180019840  lea     rcx, [rbp+57h+lpFileName]; this
0x180019844  mov     [rbp+57h+var_5C], ax
0x180019848  mov     qword ptr [rsi], 0
0x18001984f  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180019854  mov     ebx, eax
0x180019856  mov     [rbp+57h+var_60], eax
0x180019859  test    eax, eax
0x18001985b  mov     eax, 318Dh
0x180019860  js      short loc_18001981F
0x180019862  lea     rcx, [rbp+57h+lpFileName]; this
0x180019866  mov     [rbp+57h+var_5C], ax
0x18001986a  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x18001986f  mov     r14, [rbp+57h+lpFileName]
0x180019873  mov     r8d, 3; dwShareMode
0x180019879  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x180019882  mov     rcx, r14; lpFileName
0x180019885  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18001988d  xor     r9d, r9d; lpSecurityAttributes
0x180019890  mov     edx, 80000000h; dwDesiredAccess
0x180019895  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001989a  call    cs:__imp_CreateFileW
0x1800198a0  mov     rdi, rax
0x1800198a3  inc     rax
0x1800198a6  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800198ac  jnz     short loc_180019916
0x1800198ae  call    GetLastFailureAsHRESULT
0x1800198b3  mov     ebx, eax
0x1800198b5  mov     [rbp+57h+var_60], eax
0x1800198b8  mov     eax, 3199h
0x1800198bd  mov     [rbp+57h+var_5A], ax
0x1800198c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198c8  cmp     rcx, r12
0x1800198cb  jz      short loc_1800198FE
0x1800198cd  test    dword ptr [rcx+1Ch], 2000000h
0x1800198d4  jz      short loc_1800198FE
0x1800198d6  mov     rcx, [rcx+10h]
0x1800198da  lea     r9, aShvolumeIsvali; "shVolume.IsValid()"
0x1800198e1  mov     edx, 0DCh
0x1800198e6  mov     [rsp+0B0h+dwFlagsAndAttributes], ebx
0x1800198ea  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800198f1  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x1800198f6  call    WPP_SF_sSd
0x1800198fb  mov     ebx, [rbp+57h+var_60]
0x1800198fe  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180019902  jz      loc_1800199D1
0x180019908  test    rdi, rdi
0x18001990b  jz      loc_1800199D1
0x180019911  jmp     loc_1800199C8
0x180019916  mov     [rsp+0B0h+lpOverlapped], 0; lpOverlapped
0x18001991f  mov     eax, 3199h
0x180019924  mov     [rbp+57h+var_5C], ax
0x180019928  xor     r9d, r9d; nInBufferSize
0x18001992b  lea     rax, [rbp+57h+BytesReturned]
0x18001992f  mov     [rbp+57h+var_60], 0
0x180019936  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x18001993b  xor     r8d, r8d; lpInBuffer
0x18001993e  lea     rax, [rbp+57h+OutBuffer]
0x180019942  mov     [rsp+0B0h+dwFlagsAndAttributes], 8; nOutBufferSize
0x18001994a  mov     edx, 534058h; dwIoControlCode
0x18001994f  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; lpOutBuffer
0x180019954  mov     rcx, rdi; hDevice
0x180019957  call    cs:__imp_DeviceIoControl
0x18001995d  test    eax, eax
0x18001995f  jnz     short loc_1800199B3
0x180019961  call    GetLastFailureAsHRESULT
0x180019966  mov     ebx, eax
0x180019968  mov     [rbp+57h+var_60], eax
0x18001996b  mov     eax, 31A1h
0x180019970  mov     [rbp+57h+var_5A], ax
0x180019974  mov     rcx, cs:WPP_GLOBAL_Control
0x18001997b  cmp     rcx, r12
0x18001997e  jz      short loc_1800199C8
0x180019980  test    dword ptr [rcx+1Ch], 2000000h
0x180019987  jz      short loc_1800199C8
0x180019989  mov     rcx, [rcx+10h]
0x18001998d  lea     r9, aDeviceiocontro; "DeviceIoControl( shVolume, IOCTL_VOLSNA"...
0x180019994  mov     edx, 0DDh
0x180019999  mov     [rsp+0B0h+dwFlagsAndAttributes], ebx
0x18001999d  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800199a4  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x1800199a9  call    WPP_SF_sSd
0x1800199ae  mov     ebx, [rbp+57h+var_60]
0x1800199b1  jmp     short loc_1800199C8
0x1800199b3  mov     rcx, [rbp+57h+OutBuffer]
0x1800199b7  xor     ebx, ebx
0x1800199b9  mov     eax, 31A1h
0x1800199be  mov     [rbp+57h+var_60], ebx
0x1800199c1  mov     [rbp+57h+var_5C], ax
0x1800199c5  mov     [rsi], rcx
0x1800199c8  mov     rcx, rdi; hObject
0x1800199cb  call    cs:__imp_CloseHandle
0x1800199d1  lea     rcx, [rbp+57h+lpFileName]; this
0x1800199d5  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800199da  lea     rcx, [rbp+57h+var_60]; this
0x1800199de  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800199e3  mov     eax, ebx
0x1800199e5  mov     rbx, [rsp+0B0h+arg_8]
0x1800199ed  add     rsp, 90h
0x1800199f4  pop     r14
0x1800199f6  pop     r12
0x1800199f8  pop     rdi
0x1800199f9  pop     rsi
0x1800199fa  pop     rbp
0x1800199fb  retn
```
