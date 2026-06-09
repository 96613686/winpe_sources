# CSdSafeguard::_PrivateCopyFile(ushort const *,ushort const *,ISdAsyncPriv *)

- ea: `0x1800392c0`
- end: `0x180039578`
- name: `?_PrivateCopyFile@CSdSafeguard@@AEAAJPEBG0PEAUISdAsyncPriv@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(CSdSafeguard *__hidden this, LPCWSTR lpExistingFileName, const unsigned __int16 *, struct ISdAsyncPriv *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800378e0`
- `0x180037bc0`

## callees

- `0x180003c80`
- `0x180014c30`
- `0x180038f2c`
- `0x1800392c0`
- `0x180072e08`
- `0x180072f14`
- `0x18008a874`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!FlushFileBuffers` at `0x18003944a`
- `KERNEL32!FlushFileBuffers` at `0x18003944a`
- `KERNEL32!CopyFileExW` at `0x180039393`
- `KERNEL32!CopyFileExW` at `0x180039393`
- `KERNEL32!CreateFileW` at `0x180039432`
- `KERNEL32!CreateFileW` at `0x180039432`
- `KERNEL32!GetLastError` at `0x1800393a3`
- `KERNEL32!GetLastError` at `0x180039481`
- `KERNEL32!GetLastError` at `0x1800393a3`
- `KERNEL32!GetLastError` at `0x180039481`
- `KERNEL32!CloseHandle` at `0x18003954c`
- `KERNEL32!CloseHandle` at `0x18003954c`

## string_xrefs

- `0x1800392f1`: `CSdSafeguard::_PrivateCopyFile`

## pseudocode

```c
__int64 __fastcall CSdSafeguard::_PrivateCopyFile(
        CSdSafeguard *this,
        LPCWSTR lpExistingFileName,
        const unsigned __int16 *a3,
        struct ISdAsyncPriv *a4)
{
  __int64 v8; // rbx
  __int16 v9; // ax
  signed int v10; // edi
  unsigned int v11; // r12d
  unsigned int i; // r14d
  DWORD LastError; // eax
  CSdSafeguard *v14; // rcx
  bool v15; // sf
  HANDLE FileW; // rax
  __int64 v17; // rcx
  signed int v18; // eax
  signed int v19; // edi
  unsigned int v20; // edi
  int IsCopyFileErrorRetryable; // [rsp+40h] [rbp-29h] BYREF
  __int16 v23; // [rsp+44h] [rbp-25h]
  __int16 v24; // [rsp+46h] [rbp-23h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&IsCopyFileErrorRetryable,
    "CSdSafeguard::_PrivateCopyFile",
    0x38Du,
    1u);
  v8 = -1;
  v9 = 917;
  if ( !lpExistingFileName || (v23 = 917, v9 = 918, !a3) || (v23 = 918, v9 = 919, !a4) )
  {
    IsCopyFileErrorRetryable = -2147024809;
    goto LABEL_34;
  }
  v10 = 0;
  IsCopyFileErrorRetryable = 0;
  v23 = 919;
  ATL::CComPtr<ISdBackupSetRecord>::operator=((char *)this + 104, a4);
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 28) = 0;
  v11 = 2 - ((unsigned int)SdIsPathUNC(a3) != 0);
  for ( i = 0; i < v11; ++i )
  {
    if ( CopyFileExW(lpExistingFileName, a3, CSdSafeguard::_StaticCopyProgressRoutine, this, 0, 8u) )
      goto LABEL_16;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError == 1235 )
    {
      IsCopyFileErrorRetryable = *((_DWORD *)this + 28);
      v9 = 969;
      v15 = IsCopyFileErrorRetryable < 0;
    }
    else
    {
      IsCopyFileErrorRetryable = CSdSafeguard::_IsCopyFileErrorRetryable(v14, LastError);
      v15 = IsCopyFileErrorRetryable < 0;
      v9 = 973;
    }
    if ( v15 )
      goto LABEL_34;
    v23 = v9;
  }
  if ( v10 )
  {
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    IsCopyFileErrorRetryable = v10;
    v9 = 983;
    goto LABEL_34;
  }
LABEL_16:
  FileW = CreateFileW(a3, 0x40000000u, 3u, 0, 3u, 0x80u, 0);
  v8 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( !FlushFileBuffers(FileW) )
    {
      IsCopyFileErrorRetryable = GetLastFailureAsHRESULT(v17);
      v9 = 1000;
      goto LABEL_34;
    }
    IsCopyFileErrorRetryable = 0;
    v9 = 1000;
    goto LABEL_20;
  }
  v18 = GetLastError();
  v19 = v18;
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
  if ( v19 != -2147024864 && v19 != -2147024891 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids,
        (_DWORD)a3,
        v19);
    IsCopyFileErrorRetryable = v19;
    v9 = 1013;
    if ( v19 >= 0 )
    {
LABEL_20:
      v23 = v9;
      goto LABEL_35;
    }
LABEL_34:
    v24 = v9;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids,
      (_DWORD)a3,
      v19);
LABEL_35:
  ATL::CComPtr<ISdBackupSetRecord>::operator=((char *)this + 104, 0);
  v20 = IsCopyFileErrorRetryable;
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&IsCopyFileErrorRetryable);
  return v20;
}

```

## disassembly

```asm
0x1800392c0  push    rbp
0x1800392c2  push    rbx
0x1800392c3  push    rsi
0x1800392c4  push    rdi
0x1800392c5  push    r12
0x1800392c7  push    r13
0x1800392c9  push    r14
0x1800392cb  push    r15
0x1800392cd  lea     rbp, [rsp-1Fh]
0x1800392d2  sub     rsp, 88h
0x1800392d9  mov     r14, r9
0x1800392dc  mov     rsi, r8
0x1800392df  mov     r13, rdx
0x1800392e2  mov     r15, rcx
0x1800392e5  mov     r9d, 1; unsigned __int16
0x1800392eb  mov     r8d, 38Dh; unsigned __int16
0x1800392f1  lea     rdx, aCsdsafeguardPr; "CSdSafeguard::_PrivateCopyFile"
0x1800392f8  lea     rcx, [rbp+57h+var_80]; this
0x1800392fc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180039301  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180039305  xor     r12d, r12d
0x180039308  mov     eax, 395h
0x18003930d  test    r13, r13
0x180039310  jz      loc_180039526
0x180039316  mov     [rbp+57h+var_7C], ax
0x18003931a  mov     eax, 396h
0x18003931f  test    rsi, rsi
0x180039322  jz      loc_180039526
0x180039328  mov     [rbp+57h+var_7C], ax
0x18003932c  mov     eax, 397h
0x180039331  test    r14, r14
0x180039334  jz      loc_180039526
0x18003933a  mov     edi, r12d
0x18003933d  mov     [rbp+57h+var_80], r12d
0x180039341  mov     [rbp+57h+var_7C], ax
0x180039345  lea     rcx, [r15+68h]
0x180039349  mov     rdx, r14
0x18003934c  call    ??4?$CComPtr@UISdBackupSetRecord@@@ATL@@QEAAPEAUISdBackupSetRecord@@PEAU2@@Z; ATL::CComPtr<ISdBackupSetRecord>::operator=(ISdBackupSetRecord *)
0x180039351  mov     [r15+60h], r12
0x180039355  mov     [r15+70h], r12d
0x180039359  mov     rcx, rsi; unsigned __int16 *
0x18003935c  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x180039361  neg     eax
0x180039363  sbb     r12d, r12d
0x180039366  add     r12d, 2
0x18003936a  xor     r14d, r14d
0x18003936d  cmp     r14d, r12d
0x180039370  jnb     short loc_1800393E8
0x180039372  mov     [rsp+0C0h+dwCopyFlags], 8; dwCopyFlags
0x18003937a  mov     [rsp+0C0h+pbCancel], 0; pbCancel
0x180039383  mov     r9, r15; lpData
0x180039386  lea     r8, ?_StaticCopyProgressRoutine@CSdSafeguard@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z; lpProgressRoutine
0x18003938d  mov     rdx, rsi; lpNewFileName
0x180039390  mov     rcx, r13; lpExistingFileName
0x180039393  call    cs:__imp_CopyFileExW
0x18003939a  nop     dword ptr [rax+rax+00h]
0x18003939f  test    eax, eax
0x1800393a1  jnz     short loc_18003940B
0x1800393a3  call    cs:__imp_GetLastError
0x1800393aa  nop     dword ptr [rax+rax+00h]
0x1800393af  mov     edi, eax
0x1800393b1  cmp     eax, 4D3h
0x1800393b6  jnz     short loc_1800393C8
0x1800393b8  mov     ecx, [r15+70h]
0x1800393bc  mov     [rbp+57h+var_80], ecx
0x1800393bf  mov     eax, 3C9h
0x1800393c4  test    ecx, ecx
0x1800393c6  jmp     short loc_1800393D9
0x1800393c8  mov     edx, eax; unsigned int
0x1800393ca  call    ?_IsCopyFileErrorRetryable@CSdSafeguard@@AEAAJK@Z; CSdSafeguard::_IsCopyFileErrorRetryable(ulong)
0x1800393cf  mov     [rbp+57h+var_80], eax
0x1800393d2  test    eax, eax
0x1800393d4  mov     eax, 3CDh
0x1800393d9  js      loc_18003952D
0x1800393df  mov     [rbp+57h+var_7C], ax
0x1800393e3  inc     r14d
0x1800393e6  jmp     short loc_18003936D
0x1800393e8  test    edi, edi
0x1800393ea  jz      short loc_18003940B
0x1800393ec  jle     short loc_1800393F7
0x1800393ee  movzx   edi, di
0x1800393f1  or      edi, 80070000h
0x1800393f7  mov     [rbp+57h+var_80], edi
0x1800393fa  mov     eax, 3D7h
0x1800393ff  test    edi, edi
0x180039401  js      loc_18003952D
0x180039407  mov     [rbp+57h+var_7C], ax
0x18003940b  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x180039414  mov     [rsp+0C0h+dwCopyFlags], 80h; dwFlagsAndAttributes
0x18003941c  mov     r8d, 3; dwShareMode
0x180039422  mov     dword ptr [rsp+0C0h+pbCancel], r8d; dwCreationDisposition
0x180039427  xor     r9d, r9d; lpSecurityAttributes
0x18003942a  mov     edx, 40000000h; dwDesiredAccess
0x18003942f  mov     rcx, rsi; lpFileName
0x180039432  call    cs:__imp_CreateFileW
0x180039439  nop     dword ptr [rax+rax+00h]
0x18003943e  mov     rbx, rax
0x180039441  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039445  jz      short loc_180039481
0x180039447  mov     rcx, rax; hFile
0x18003944a  call    cs:__imp_FlushFileBuffers
0x180039451  nop     dword ptr [rax+rax+00h]
0x180039456  test    eax, eax
0x180039458  jnz     short loc_18003946C
0x18003945a  call    GetLastFailureAsHRESULT
0x18003945f  mov     [rbp+57h+var_80], eax
0x180039462  mov     eax, 3E8h
0x180039467  jmp     loc_18003952D
0x18003946c  mov     [rbp+57h+var_80], 0
0x180039473  mov     eax, 3E8h
0x180039478  mov     [rbp+57h+var_7C], ax
0x18003947c  jmp     loc_180039531
0x180039481  call    cs:__imp_GetLastError
0x180039488  nop     dword ptr [rax+rax+00h]
0x18003948d  mov     edi, eax
0x18003948f  test    eax, eax
0x180039491  jle     short loc_18003949C
0x180039493  movzx   edi, ax
0x180039496  or      edi, 80070000h
0x18003949c  cmp     edi, 80070020h
0x1800394a2  jz      short loc_1800394EF
0x1800394a4  cmp     edi, 80070005h
0x1800394aa  jz      short loc_1800394EF
0x1800394ac  lea     rax, WPP_GLOBAL_Control
0x1800394b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394ba  cmp     rcx, rax
0x1800394bd  jz      short loc_1800394E1
0x1800394bf  test    byte ptr [rcx+1Ch], 20h
0x1800394c3  jz      short loc_1800394E1
0x1800394c5  mov     edx, 19h
0x1800394ca  mov     dword ptr [rsp+0C0h+pbCancel], edi
0x1800394ce  mov     r9, rsi
0x1800394d1  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x1800394d8  mov     rcx, [rcx+10h]
0x1800394dc  call    WPP_SF_Sd
0x1800394e1  mov     [rbp+57h+var_80], edi
0x1800394e4  mov     eax, 3F5h
0x1800394e9  test    edi, edi
0x1800394eb  js      short loc_18003952D
0x1800394ed  jmp     short loc_180039478
0x1800394ef  lea     rax, WPP_GLOBAL_Control
0x1800394f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394fd  cmp     rcx, rax
0x180039500  jz      short loc_180039531
0x180039502  test    byte ptr [rcx+1Ch], 20h
0x180039506  jz      short loc_180039531
0x180039508  mov     edx, 18h
0x18003950d  mov     dword ptr [rsp+0C0h+pbCancel], edi
0x180039511  mov     r9, rsi
0x180039514  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x18003951b  mov     rcx, [rcx+10h]
0x18003951f  call    WPP_SF_Sd
0x180039524  jmp     short loc_180039531
0x180039526  mov     [rbp+57h+var_80], 80070057h
0x18003952d  mov     [rbp+57h+var_7A], ax
0x180039531  lea     rcx, [r15+68h]
0x180039535  xor     edx, edx
0x180039537  call    ??4?$CComPtr@UISdBackupSetRecord@@@ATL@@QEAAPEAUISdBackupSetRecord@@PEAU2@@Z; ATL::CComPtr<ISdBackupSetRecord>::operator=(ISdBackupSetRecord *)
0x18003953c  mov     edi, [rbp+57h+var_80]
0x18003953f  lea     rcx, [rbx-1]
0x180039543  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180039547  ja      short loc_180039558
0x180039549  mov     rcx, rbx; hObject
0x18003954c  call    cs:__imp_CloseHandle
0x180039553  nop     dword ptr [rax+rax+00h]
0x180039558  lea     rcx, [rbp+57h+var_80]; this
0x18003955c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180039561  mov     eax, edi
0x180039563  add     rsp, 88h
0x18003956a  pop     r15
0x18003956c  pop     r14
0x18003956e  pop     r13
0x180039570  pop     r12
0x180039572  pop     rdi
0x180039573  pop     rsi
0x180039574  pop     rbx
0x180039575  pop     rbp
0x180039576  retn
```
