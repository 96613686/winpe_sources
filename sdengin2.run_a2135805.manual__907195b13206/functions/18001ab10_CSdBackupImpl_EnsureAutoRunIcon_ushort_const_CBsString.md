# CSdBackupImpl::_EnsureAutoRunIcon(ushort const *,CBsString *)

- ea: `0x18001ab10`
- end: `0x18001adf6`
- name: `?_EnsureAutoRunIcon@CSdBackupImpl@@AEAAJPEBGPEAVCBsString@@@Z`
- size: `742`
- prototype: `int(CSdBackupImpl *__hidden this, const unsigned __int16 *, struct CBsString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180021ffc`

## callees

- `0x18001ab10`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e904`
- `0x18009ea34`
- `0x18009f560`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001aced`
- `KERNEL32!CreateFileW` at `0x18001aced`
- `KERNEL32!GetLastError` at `0x18001ad07`
- `KERNEL32!GetLastError` at `0x18001ad07`
- `KERNEL32!CloseHandle` at `0x18001adca`
- `KERNEL32!CloseHandle` at `0x18001adca`
- `KERNEL32!FindResourceW` at `0x18001abaf`
- `KERNEL32!FindResourceW` at `0x18001abaf`
- `KERNEL32!LoadResource` at `0x18001abeb`
- `KERNEL32!LoadResource` at `0x18001abeb`
- `KERNEL32!LockResource` at `0x18001ac20`
- `KERNEL32!LockResource` at `0x18001ac20`
- `KERNEL32!SizeofResource` at `0x18001ac5f`
- `KERNEL32!SizeofResource` at `0x18001ac5f`
- `KERNEL32!WriteFile` at `0x18001ad5e`
- `KERNEL32!WriteFile` at `0x18001ad5e`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_EnsureAutoRunIcon(
        CSdBackupImpl *this,
        const unsigned __int16 *a2,
        struct CBsString *a3)
{
  __int64 FileW; // rbx
  __int16 v6; // ax
  signed int LastFailureAsHRESULT; // edi
  __int64 v8; // rcx
  HRSRC ResourceW; // rdi
  HGLOBAL Resource; // rcx
  __int64 v11; // rcx
  const void *v12; // r15
  __int64 v13; // rcx
  DWORD v14; // r12d
  signed int LastError; // eax
  __int64 v16; // rcx
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-69h]
  const unsigned __int16 *v19; // [rsp+38h] [rbp-61h]
  const unsigned __int16 *v20; // [rsp+40h] [rbp-59h]
  const unsigned __int16 *v21; // [rsp+48h] [rbp-51h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp-49h]
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-39h] BYREF
  int v24; // [rsp+70h] [rbp-29h] BYREF
  __int16 v25; // [rsp+74h] [rbp-25h]
  __int16 v26; // [rsp+76h] [rbp-23h]
  CSdBackupImpl *NumberOfBytesWritten; // [rsp+100h] [rbp+67h] BYREF

  NumberOfBytesWritten = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v24, "CSdBackupImpl::_EnsureAutoRunIcon", 0x10CAu, 1u);
  FileW = -1;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  LODWORD(NumberOfBytesWritten) = 0;
  v6 = 4308;
  if ( !a2 || (v25 = 4308, v6 = 4309, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
    v24 = -2147024809;
LABEL_3:
    v26 = v6;
    goto LABEL_25;
  }
  v24 = 0;
  v25 = 4309;
  ResourceW = FindResourceW(hInstance, L"IDI_RESTOREICON", L"ICONBINARY");
  if ( !ResourceW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v24 = LastFailureAsHRESULT;
    v6 = 4316;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4316;
  Resource = LoadResource(hInstance, ResourceW);
  if ( !Resource )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(0);
    v24 = LastFailureAsHRESULT;
    v6 = 4319;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4319;
  v12 = LockResource(Resource);
  if ( !v12 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
    v24 = LastFailureAsHRESULT;
    v6 = 4322;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4322;
  v14 = SizeofResource(hInstance, ResourceW);
  if ( !v14 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
    v24 = LastFailureAsHRESULT;
    v6 = 4325;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4325;
  LastFailureAsHRESULT = CBsString::SetPath(
                           (CBsString *)lpFileName,
                           a2,
                           L"restore.ico",
                           0,
                           0,
                           0,
                           hTemplateFile,
                           v19,
                           v20,
                           v21,
                           v22);
  v24 = LastFailureAsHRESULT;
  v6 = 4327;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v25 = 4327;
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 0, 0, 1u, 0x80u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    LastFailureAsHRESULT = LastError;
    if ( LastError == 80 )
    {
      v24 = 0;
      v6 = 4343;
      LastFailureAsHRESULT = 0;
      goto LABEL_24;
    }
    if ( LastError > 0 )
      LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
    v24 = LastFailureAsHRESULT;
    v6 = 4345;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v25 = 4345;
  }
  if ( !WriteFile((HANDLE)FileW, v12, v14, (LPDWORD)&NumberOfBytesWritten, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v16);
    v24 = LastFailureAsHRESULT;
    v6 = 4352;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 4352;
  LastFailureAsHRESULT = CBsString::Set(a3, L"restore.ico");
  v24 = LastFailureAsHRESULT;
  v6 = 4358;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
LABEL_24:
  v25 = v6;
LABEL_25:
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v24);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001ab10  mov     [rsp-8+NumberOfBytesWritten], rcx
0x18001ab15  push    rbp
0x18001ab16  push    rbx
0x18001ab17  push    rsi
0x18001ab18  push    rdi
0x18001ab19  push    r12
0x18001ab1b  push    r13
0x18001ab1d  push    r14
0x18001ab1f  push    r15
0x18001ab21  lea     rbp, [rsp-1Fh]
0x18001ab26  sub     rsp, 0B8h
0x18001ab2d  mov     rsi, r8
0x18001ab30  mov     r14, rdx
0x18001ab33  mov     r9d, 1; unsigned __int16
0x18001ab39  mov     r8d, 10CAh; unsigned __int16
0x18001ab3f  lea     rdx, aCsdbackupimplE_0; "CSdBackupImpl::_EnsureAutoRunIcon"
0x18001ab46  lea     rcx, [rbp+57h+var_80]; this
0x18001ab4a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ab4f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ab53  lea     rax, qword_1800EE510
0x18001ab5a  mov     [rbp+57h+lpFileName], rax
0x18001ab5e  xor     r13d, r13d
0x18001ab61  mov     [rbp+57h+var_88], r13
0x18001ab65  mov     dword ptr [rbp+57h+NumberOfBytesWritten], r13d
0x18001ab69  mov     eax, 10D4h
0x18001ab6e  test    r14, r14
0x18001ab71  jnz     short loc_18001AB84
0x18001ab73  mov     edi, 80070057h
0x18001ab78  mov     [rbp+57h+var_80], edi
0x18001ab7b  mov     [rbp+57h+var_7A], ax
0x18001ab7f  jmp     loc_18001ADB4
0x18001ab84  mov     [rbp+57h+var_7C], ax
0x18001ab88  mov     eax, 10D5h
0x18001ab8d  test    rsi, rsi
0x18001ab90  jz      short loc_18001AB73
0x18001ab92  mov     [rbp+57h+var_80], r13d
0x18001ab96  mov     [rbp+57h+var_7C], ax
0x18001ab9a  lea     r8, Type; "ICONBINARY"
0x18001aba1  lea     rdx, Name; "IDI_RESTOREICON"
0x18001aba8  mov     rcx, cs:hInstance; hModule
0x18001abaf  call    cs:__imp_FindResourceW
0x18001abb6  nop     dword ptr [rax+rax+00h]
0x18001abbb  mov     rdi, rax
0x18001abbe  test    rax, rax
0x18001abc1  jnz     short loc_18001ABD4
0x18001abc3  call    GetLastFailureAsHRESULT
0x18001abc8  mov     edi, eax
0x18001abca  mov     [rbp+57h+var_80], eax
0x18001abcd  mov     eax, 10DCh
0x18001abd2  jmp     short loc_18001AB7B
0x18001abd4  mov     [rbp+57h+var_80], r13d
0x18001abd8  mov     eax, 10DCh
0x18001abdd  mov     [rbp+57h+var_7C], ax
0x18001abe1  mov     rdx, rdi; hResInfo
0x18001abe4  mov     rcx, cs:hInstance; hModule
0x18001abeb  call    cs:__imp_LoadResource
0x18001abf2  nop     dword ptr [rax+rax+00h]
0x18001abf7  mov     rcx, rax; hResData
0x18001abfa  test    rax, rax
0x18001abfd  jnz     short loc_18001AC13
0x18001abff  call    GetLastFailureAsHRESULT
0x18001ac04  mov     edi, eax
0x18001ac06  mov     [rbp+57h+var_80], eax
0x18001ac09  mov     eax, 10DFh
0x18001ac0e  jmp     loc_18001AB7B
0x18001ac13  mov     [rbp+57h+var_80], r13d
0x18001ac17  mov     eax, 10DFh
0x18001ac1c  mov     [rbp+57h+var_7C], ax
0x18001ac20  call    cs:__imp_LockResource
0x18001ac27  nop     dword ptr [rax+rax+00h]
0x18001ac2c  mov     r15, rax
0x18001ac2f  test    rax, rax
0x18001ac32  jnz     short loc_18001AC48
0x18001ac34  call    GetLastFailureAsHRESULT
0x18001ac39  mov     edi, eax
0x18001ac3b  mov     [rbp+57h+var_80], eax
0x18001ac3e  mov     eax, 10E2h
0x18001ac43  jmp     loc_18001AB7B
0x18001ac48  mov     [rbp+57h+var_80], r13d
0x18001ac4c  mov     eax, 10E2h
0x18001ac51  mov     [rbp+57h+var_7C], ax
0x18001ac55  mov     rdx, rdi; hResInfo
0x18001ac58  mov     rcx, cs:hInstance; hModule
0x18001ac5f  call    cs:__imp_SizeofResource
0x18001ac66  nop     dword ptr [rax+rax+00h]
0x18001ac6b  mov     r12d, eax
0x18001ac6e  test    eax, eax
0x18001ac70  jnz     short loc_18001AC86
0x18001ac72  call    GetLastFailureAsHRESULT
0x18001ac77  mov     edi, eax
0x18001ac79  mov     [rbp+57h+var_80], eax
0x18001ac7c  mov     eax, 10E5h
0x18001ac81  jmp     loc_18001AB7B
0x18001ac86  mov     [rbp+57h+var_80], r13d
0x18001ac8a  mov     eax, 10E5h
0x18001ac8f  mov     [rbp+57h+var_7C], ax
0x18001ac93  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x18001ac98  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r13; unsigned __int16 *
0x18001ac9d  xor     r9d, r9d; unsigned __int16 *
0x18001aca0  lea     r8, aRestoreIco; "restore.ico"
0x18001aca7  mov     rdx, r14; unsigned __int16 *
0x18001acaa  lea     rcx, [rbp+57h+lpFileName]; this
0x18001acae  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001acb3  mov     edi, eax
0x18001acb5  mov     [rbp+57h+var_80], eax
0x18001acb8  test    eax, eax
0x18001acba  mov     eax, 10E7h
0x18001acbf  js      loc_18001AB7B
0x18001acc5  mov     [rbp+57h+var_7C], ax
0x18001acc9  mov     [rsp+0F0h+hTemplateFile], r13; hTemplateFile
0x18001acce  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001acd6  mov     [rsp+0F0h+dwCreationDisposition], 1; dwCreationDisposition
0x18001acde  xor     r9d, r9d; lpSecurityAttributes
0x18001ace1  xor     r8d, r8d; dwShareMode
0x18001ace4  mov     edx, 0C0000000h; dwDesiredAccess
0x18001ace9  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18001aced  call    cs:__imp_CreateFileW
0x18001acf4  nop     dword ptr [rax+rax+00h]
0x18001acf9  mov     rbx, rax
0x18001acfc  inc     rax
0x18001acff  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001ad05  jnz     short loc_18001AD4C
0x18001ad07  call    cs:__imp_GetLastError
0x18001ad0e  nop     dword ptr [rax+rax+00h]
0x18001ad13  mov     edi, eax
0x18001ad15  cmp     eax, 50h ; 'P'
0x18001ad18  jnz     short loc_18001AD2B
0x18001ad1a  mov     [rbp+57h+var_80], r13d
0x18001ad1e  mov     eax, 10F7h
0x18001ad23  mov     edi, r13d
0x18001ad26  jmp     loc_18001ADB0
0x18001ad2b  test    eax, eax
0x18001ad2d  jle     short loc_18001AD38
0x18001ad2f  movzx   edi, ax
0x18001ad32  or      edi, 80070000h
0x18001ad38  mov     [rbp+57h+var_80], edi
0x18001ad3b  mov     eax, 10F9h
0x18001ad40  test    edi, edi
0x18001ad42  js      loc_18001AB7B
0x18001ad48  mov     [rbp+57h+var_7C], ax
0x18001ad4c  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r13; lpOverlapped
0x18001ad51  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ad55  mov     r8d, r12d; nNumberOfBytesToWrite
0x18001ad58  mov     rdx, r15; lpBuffer
0x18001ad5b  mov     rcx, rbx; hFile
0x18001ad5e  call    cs:__imp_WriteFile
0x18001ad65  nop     dword ptr [rax+rax+00h]
0x18001ad6a  test    eax, eax
0x18001ad6c  jnz     short loc_18001AD82
0x18001ad6e  call    GetLastFailureAsHRESULT
0x18001ad73  mov     edi, eax
0x18001ad75  mov     [rbp+57h+var_80], eax
0x18001ad78  mov     eax, 1100h
0x18001ad7d  jmp     loc_18001AB7B
0x18001ad82  mov     [rbp+57h+var_80], r13d
0x18001ad86  mov     eax, 1100h
0x18001ad8b  mov     [rbp+57h+var_7C], ax
0x18001ad8f  lea     rdx, aRestoreIco; "restore.ico"
0x18001ad96  mov     rcx, rsi; this
0x18001ad99  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001ad9e  mov     edi, eax
0x18001ada0  mov     [rbp+57h+var_80], eax
0x18001ada3  test    eax, eax
0x18001ada5  mov     eax, 1106h
0x18001adaa  js      loc_18001AB7B
0x18001adb0  mov     [rbp+57h+var_7C], ax
0x18001adb4  lea     rcx, [rbp+57h+lpFileName]; this
0x18001adb8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001adbd  lea     rdx, [rbx-1]
0x18001adc1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001adc5  ja      short loc_18001ADD6
0x18001adc7  mov     rcx, rbx; hObject
0x18001adca  call    cs:__imp_CloseHandle
0x18001add1  nop     dword ptr [rax+rax+00h]
0x18001add6  lea     rcx, [rbp+57h+var_80]; this
0x18001adda  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001addf  mov     eax, edi
0x18001ade1  add     rsp, 0B8h
0x18001ade8  pop     r15
0x18001adea  pop     r14
0x18001adec  pop     r13
0x18001adee  pop     r12
0x18001adf0  pop     rdi
0x18001adf1  pop     rsi
0x18001adf2  pop     rbx
0x18001adf3  pop     rbp
0x18001adf4  retn
```
