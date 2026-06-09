# SxIsShadowCopyScoped(ushort const *,uchar *)

- ea: `0x1400068d4`
- end: `0x140006aaa`
- name: `?SxIsShadowCopyScoped@@YAJPEBGPEAE@Z`
- size: `470`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1400029b4`
- `0x1400050f0`

## callees

- `0x140002e1c`
- `0x1400068d4`
- `0x140006cc8`
- `0x14000e324`
- `0x14000e41c`
- `0x14000fe8c`
- `0x1400103c4`
- `0x140010744`
- `0x140010980`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140006a7a`
- `KERNEL32!CloseHandle` at `0x140006a7a`
- `KERNEL32!CreateFileW` at `0x1400069c7`
- `KERNEL32!CreateFileW` at `0x1400069c7`
- `KERNEL32!DeviceIoControl` at `0x140006a2d`
- `KERNEL32!DeviceIoControl` at `0x140006a2d`

## string_xrefs

- `0x140006933`: `SxIsShadowCopyScoped`

## pseudocode

```c
__int64 __fastcall SxIsShadowCopyScoped(const unsigned __int16 *a1, unsigned __int8 *a2)
{
  unsigned __int16 v4; // dx
  int LastFailureAsHRESULT; // edi
  __int16 v6; // ax
  char *FileW; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-21h] BYREF
  int v11; // [rsp+58h] [rbp-11h] BYREF
  __int16 v12; // [rsp+5Ch] [rbp-Dh]
  __int16 v13; // [rsp+5Eh] [rbp-Bh]
  __int128 OutBuffer; // [rsp+90h] [rbp+27h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "SxIsShadowCopyScoped", 0x103u, 1u);
  *a2 = 0;
  lpFileName[1] = 0;
  OutBuffer = 0;
  lpFileName[0] = (LPCWSTR)qword_140013960;
  BytesReturned = 0;
  LastFailureAsHRESULT = CBsString::Append((CBsString *)lpFileName, a1);
  v11 = LastFailureAsHRESULT;
  v6 = 268;
  if ( LastFailureAsHRESULT < 0 )
  {
    FileW = 0;
LABEL_6:
    v13 = v6;
    goto LABEL_12;
  }
  v12 = 268;
  CBsString::UnTrailing((CBsString *)lpFileName, v4);
  FileW = (char *)CreateFileW(lpFileName[0], 0x80000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v11 = LastFailureAsHRESULT;
    v6 = 275;
    goto LABEL_6;
  }
  v12 = 275;
  v11 = 0;
  if ( !DeviceIoControl(FileW, 0x5301E0u, 0, 0, &OutBuffer, 0x10u, &BytesReturned, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v11 = LastFailureAsHRESULT;
    v6 = 284;
    goto LABEL_6;
  }
  v11 = 0;
  v12 = 284;
  *a2 = OutBuffer & 1;
  LastFailureAsHRESULT = 0;
LABEL_12:
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1400068d4  mov     [rsp-8+arg_10], rbx
0x1400068d9  push    rbp
0x1400068da  push    rsi
0x1400068db  push    rdi
0x1400068dc  lea     rbp, [rsp-47h]
0x1400068e1  sub     rsp, 0B0h
0x1400068e8  mov     rax, cs:__security_cookie
0x1400068ef  xor     rax, rsp
0x1400068f2  mov     [rbp+57h+var_20], rax
0x1400068f6  mov     rsi, rdx
0x1400068f9  mov     rbx, rcx
0x1400068fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140006903  lea     rax, WPP_GLOBAL_Control
0x14000690a  cmp     rcx, rax
0x14000690d  jz      short loc_14000692D
0x14000690f  test    dword ptr [rcx+1Ch], 20000000h
0x140006916  jz      short loc_14000692D
0x140006918  mov     rcx, [rcx+10h]
0x14000691c  lea     r8, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids
0x140006923  mov     edx, 12h
0x140006928  call    WPP_SF_
0x14000692d  mov     r9d, 1; unsigned __int16
0x140006933  lea     rdx, aSxisshadowcopy; "SxIsShadowCopyScoped"
0x14000693a  mov     r8d, 103h; unsigned __int16
0x140006940  lea     rcx, [rbp+57h+var_68]; this
0x140006944  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140006949  xorps   xmm0, xmm0
0x14000694c  mov     byte ptr [rsi], 0
0x14000694f  lea     rax, qword_140013960
0x140006956  mov     [rbp+57h+var_70], 0
0x14000695e  movups  [rbp+57h+OutBuffer], xmm0
0x140006962  mov     [rbp+57h+lpFileName], rax
0x140006966  mov     [rbp+57h+BytesReturned], 0
0x14000696d  mov     rdx, rbx; unsigned __int16 *
0x140006970  lea     rcx, [rbp+57h+lpFileName]; this
0x140006974  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x140006979  mov     edi, eax
0x14000697b  mov     [rbp+57h+var_68], eax
0x14000697e  test    eax, eax
0x140006980  mov     eax, 10Ch
0x140006985  jns     short loc_140006992
0x140006987  xor     ebx, ebx
0x140006989  mov     [rbp+57h+var_62], ax
0x14000698d  jmp     loc_140006A64
0x140006992  lea     rcx, [rbp+57h+lpFileName]; this
0x140006996  mov     [rbp+57h+var_64], ax
0x14000699a  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x14000699f  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1400069a3  mov     r8d, 3; dwShareMode
0x1400069a9  mov     [rsp+0C0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x1400069b2  xor     r9d, r9d; lpSecurityAttributes
0x1400069b5  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400069bd  mov     edx, 80000000h; dwDesiredAccess
0x1400069c2  mov     [rsp+0C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400069c7  call    cs:__imp_CreateFileW
0x1400069cd  mov     rbx, rax
0x1400069d0  inc     rax
0x1400069d3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400069d9  jnz     short loc_1400069EC
0x1400069db  call    GetLastFailureAsHRESULT
0x1400069e0  mov     edi, eax
0x1400069e2  mov     [rbp+57h+var_68], eax
0x1400069e5  mov     eax, 113h
0x1400069ea  jmp     short loc_140006989
0x1400069ec  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x1400069f5  mov     eax, 113h
0x1400069fa  mov     [rbp+57h+var_64], ax
0x1400069fe  xor     r9d, r9d; nInBufferSize
0x140006a01  lea     rax, [rbp+57h+BytesReturned]
0x140006a05  mov     [rbp+57h+var_68], 0
0x140006a0c  mov     [rsp+0C0h+hTemplateFile], rax; lpBytesReturned
0x140006a11  xor     r8d, r8d; lpInBuffer
0x140006a14  lea     rax, [rbp+57h+OutBuffer]
0x140006a18  mov     [rsp+0C0h+dwFlagsAndAttributes], 10h; nOutBufferSize
0x140006a20  mov     edx, 5301E0h; dwIoControlCode
0x140006a25  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; lpOutBuffer
0x140006a2a  mov     rcx, rbx; hDevice
0x140006a2d  call    cs:__imp_DeviceIoControl
0x140006a33  test    eax, eax
0x140006a35  jnz     short loc_140006A4B
0x140006a37  call    GetLastFailureAsHRESULT
0x140006a3c  mov     edi, eax
0x140006a3e  mov     [rbp+57h+var_68], eax
0x140006a41  mov     eax, 11Ch
0x140006a46  jmp     loc_140006989
0x140006a4b  mov     eax, 11Ch
0x140006a50  mov     [rbp+57h+var_68], 0
0x140006a57  mov     [rbp+57h+var_64], ax
0x140006a5b  mov     al, byte ptr [rbp+57h+OutBuffer]
0x140006a5e  and     al, 1
0x140006a60  mov     [rsi], al
0x140006a62  xor     edi, edi
0x140006a64  lea     rcx, [rbp+57h+lpFileName]; this
0x140006a68  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x140006a6d  lea     rcx, [rbx-1]
0x140006a71  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140006a75  ja      short loc_140006A80
0x140006a77  mov     rcx, rbx; hObject
0x140006a7a  call    cs:__imp_CloseHandle
0x140006a80  lea     rcx, [rbp+57h+var_68]; this
0x140006a84  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140006a89  mov     eax, edi
0x140006a8b  mov     rcx, [rbp+57h+var_20]
0x140006a8f  xor     rcx, rsp; StackCookie
0x140006a92  call    __security_check_cookie
0x140006a97  mov     rbx, [rsp+0C0h+arg_10]
0x140006a9f  add     rsp, 0B0h
0x140006aa6  pop     rdi
0x140006aa7  pop     rsi
0x140006aa8  pop     rbp
0x140006aa9  retn
```
