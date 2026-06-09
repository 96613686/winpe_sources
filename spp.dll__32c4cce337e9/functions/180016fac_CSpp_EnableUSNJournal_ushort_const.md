# CSpp::_EnableUSNJournal(ushort const *)

- ea: `0x180016fac`
- end: `0x1800172fd`
- name: `?_EnableUSNJournal@CSpp@@AEAAJPEBG@Z`
- size: `849`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180011198`

## callees

- `0x180016fac`
- `0x180020710`
- `0x180020908`
- `0x1800268b4`
- `0x1800269ac`
- `0x1800295bc`
- `0x18002a778`
- `0x18002d6e8`
- `0x18003532c`
- `0x180035464`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180017112`
- `msvcrt!_wcsicmp` at `0x180017112`
- `KERNEL32!GetLastError` at `0x180017214`
- `KERNEL32!GetLastError` at `0x180017214`
- `KERNEL32!CreateFileW` at `0x18001717d`
- `KERNEL32!CreateFileW` at `0x18001717d`
- `KERNEL32!DeviceIoControl` at `0x1800171fa`
- `KERNEL32!DeviceIoControl` at `0x18001727f`
- `KERNEL32!DeviceIoControl` at `0x1800171fa`
- `KERNEL32!DeviceIoControl` at `0x18001727f`
- `KERNEL32!CloseHandle` at `0x1800172ba`
- `KERNEL32!CloseHandle` at `0x1800172ba`

## pseudocode

```c
__int64 __fastcall CSpp::_EnableUSNJournal(CSpp *this, const unsigned __int16 *a2)
{
  __int16 v3; // ax
  signed int LastFailureAsHRESULT; // ebx
  unsigned __int16 v5; // dx
  unsigned int v6; // edx
  int SystemVolume; // eax
  const WCHAR *v8; // rdi
  unsigned __int16 v9; // dx
  __int64 v10; // rcx
  HANDLE FileW; // rdi
  __int16 v12; // ax
  __int16 v13; // ax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v20; // [rsp+4Ch] [rbp-B4h]
  __int16 v21; // [rsp+4Eh] [rbp-B2h]
  wchar_t *String2[2]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 InBuffer; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE OutBuffer[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v26; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v27[526]; // [rsp+F2h] [rbp-Eh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v19, "CSpp::_EnableUSNJournal", 2205, 1);
  String1[0] = (wchar_t *)&FileName;
  String2[0] = (wchar_t *)&FileName;
  String1[1] = 0;
  String2[1] = 0;
  memset_0(OutBuffer, 0, sizeof(OutBuffer));
  BytesReturned = 0;
  v26 = 0;
  InBuffer = 0;
  memset_0(v27, 0, 0x206u);
  v3 = 2217;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v19 = -2147024809;
LABEL_6:
    v21 = v3;
    goto LABEL_36;
  }
  v19 = 0;
  v20 = 2217;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)String1, a2);
  v19 = LastFailureAsHRESULT;
  v3 = 2219;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v20 = 2219;
  CBsString::UnTrailing((CBsString *)String1, v5);
  SystemVolume = SxGetSystemVolume(&v26, v6);
  v8 = String1[0];
  if ( SystemVolume < 0 )
    goto LABEL_16;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)String2, &v26);
  v19 = LastFailureAsHRESULT;
  v3 = 2229;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v20 = 2229;
  CBsString::UnTrailing((CBsString *)String2, v9);
  if ( !(unsigned int)SxIsBootVolume(v8) || _wcsicmp(v8, String2[0]) )
  {
LABEL_16:
    FileW = CreateFileW(v8, 0x40000000u, 3u, 0, 3u, 0, 0);
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
      v19 = LastFailureAsHRESULT;
      v21 = 2247;
      if ( FileW == (HANDLE)-1LL || !FileW )
        goto LABEL_36;
LABEL_35:
      CloseHandle(FileW);
      goto LABEL_36;
    }
    v20 = 2247;
    v19 = 0;
    if ( DeviceIoControl(FileW, 0x900F4u, 0, 0, OutBuffer, 0x40u, &BytesReturned, 0) )
    {
      v12 = 2270;
LABEL_22:
      v19 = 0;
      LastFailureAsHRESULT = 0;
LABEL_34:
      v20 = v12;
      goto LABEL_35;
    }
    LastFailureAsHRESULT = GetLastError();
    if ( LastFailureAsHRESULT == 1 )
    {
      v19 = 1;
      v12 = 2293;
      LastFailureAsHRESULT = 1;
      goto LABEL_34;
    }
    if ( LastFailureAsHRESULT == 1179 )
    {
      InBuffer = 0u;
      if ( !DeviceIoControl(FileW, 0x900E7u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
        v19 = LastFailureAsHRESULT;
        v13 = 2289;
        goto LABEL_29;
      }
    }
    else
    {
      if ( LastFailureAsHRESULT > 0 )
        LastFailureAsHRESULT = (unsigned __int16)LastFailureAsHRESULT | 0x80070000;
      v19 = LastFailureAsHRESULT;
      if ( LastFailureAsHRESULT < 0 )
      {
        v13 = 2297;
LABEL_29:
        v21 = v13;
        goto LABEL_35;
      }
    }
    v12 = 2301;
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, v8);
  v19 = 1;
  v20 = 2239;
  LastFailureAsHRESULT = 1;
LABEL_36:
  CBsString::_Release((CBsString *)String2);
  CBsString::_Release((CBsString *)String1);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v19, v15, v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180016fac  push    rbp
0x180016fae  push    rbx
0x180016faf  push    rsi
0x180016fb0  push    rdi
0x180016fb1  push    r14
0x180016fb3  push    r15
0x180016fb5  lea     rbp, [rsp-218h]
0x180016fbd  sub     rsp, 318h
0x180016fc4  mov     rax, cs:__security_cookie
0x180016fcb  xor     rax, rsp
0x180016fce  mov     [rbp+240h+var_40], rax
0x180016fd5  mov     rbx, rdx
0x180016fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180016fdf  lea     r15, WPP_GLOBAL_Control
0x180016fe6  cmp     rcx, r15
0x180016fe9  jz      short loc_180017009
0x180016feb  test    dword ptr [rcx+1Ch], 20000000h
0x180016ff2  jz      short loc_180017009
0x180016ff4  mov     rcx, [rcx+10h]
0x180016ff8  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180016fff  mov     edx, 13h
0x180017004  call    WPP_SF_
0x180017009  mov     r14d, 1
0x18001700f  lea     rdx, aCsppEnableusnj; "CSpp::_EnableUSNJournal"
0x180017016  mov     r9d, r14d; unsigned __int16
0x180017019  lea     rcx, [rsp+340h+var_2F8]; this
0x18001701e  mov     r8d, 89Dh; unsigned __int16
0x180017024  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017029  lea     rax, FileName
0x180017030  xor     esi, esi
0x180017032  xor     edx, edx; Val
0x180017034  mov     [rbp+240h+String1], rax
0x180017038  lea     r8d, [r14+3Fh]; Size
0x18001703c  mov     [rbp+240h+String2], rax
0x180017040  lea     rcx, [rbp+240h+OutBuffer]; void *
0x180017044  mov     [rbp+240h+var_2A8], rsi
0x180017048  mov     [rbp+240h+var_2B8], rsi
0x18001704c  call    memset_0
0x180017051  xorps   xmm0, xmm0
0x180017054  mov     [rsp+340h+BytesReturned], esi
0x180017058  xor     edx, edx; Val
0x18001705a  mov     [rbp+240h+var_250], si
0x18001705e  mov     r8d, 206h; Size
0x180017064  lea     rcx, [rbp+240h+var_24E]; void *
0x180017068  movups  [rbp+240h+InBuffer], xmm0
0x18001706c  call    memset_0
0x180017071  mov     eax, 8A9h
0x180017076  test    rbx, rbx
0x180017079  jnz     short loc_18001708E
0x18001707b  mov     ebx, 80070057h
0x180017080  mov     [rsp+340h+var_2F8], ebx
0x180017084  mov     [rsp+340h+var_2F2], ax
0x180017089  jmp     loc_1800172C0
0x18001708e  mov     rdx, rbx; unsigned __int16 *
0x180017091  mov     [rsp+340h+var_2F8], esi
0x180017095  lea     rcx, [rbp+240h+String1]; this
0x180017099  mov     [rsp+340h+var_2F4], ax
0x18001709e  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800170a3  mov     ebx, eax
0x1800170a5  mov     [rsp+340h+var_2F8], eax
0x1800170a9  test    eax, eax
0x1800170ab  mov     eax, 8ABh
0x1800170b0  js      short loc_180017084
0x1800170b2  lea     rcx, [rbp+240h+String1]; this
0x1800170b6  mov     [rsp+340h+var_2F4], ax
0x1800170bb  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1800170c0  lea     rcx, [rbp+240h+var_250]; unsigned __int16 *
0x1800170c4  call    ?SxGetSystemVolume@@YAJPEAGK@Z; SxGetSystemVolume(ushort *,ulong)
0x1800170c9  mov     rdi, [rbp+240h+String1]
0x1800170cd  test    eax, eax
0x1800170cf  js      loc_18001715E
0x1800170d5  lea     rdx, [rbp+240h+var_250]; unsigned __int16 *
0x1800170d9  lea     rcx, [rbp+240h+String2]; this
0x1800170dd  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800170e2  mov     ebx, eax
0x1800170e4  mov     [rsp+340h+var_2F8], eax
0x1800170e8  test    eax, eax
0x1800170ea  mov     eax, 8B5h
0x1800170ef  js      short loc_180017084
0x1800170f1  lea     rcx, [rbp+240h+String2]; this
0x1800170f5  mov     [rsp+340h+var_2F4], ax
0x1800170fa  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1800170ff  mov     rcx, rdi; unsigned __int16 *
0x180017102  call    ?SxIsBootVolume@@YAJPEBG@Z; SxIsBootVolume(ushort const *)
0x180017107  test    eax, eax
0x180017109  jz      short loc_18001715E
0x18001710b  mov     rdx, [rbp+240h+String2]; String2
0x18001710f  mov     rcx, rdi; String1
0x180017112  call    cs:__imp__wcsicmp
0x180017118  test    eax, eax
0x18001711a  jnz     short loc_18001715E
0x18001711c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017123  cmp     rcx, r15
0x180017126  jz      short loc_180017147
0x180017128  test    dword ptr [rcx+1Ch], 8000000h
0x18001712f  jz      short loc_180017147
0x180017131  mov     rcx, [rcx+10h]
0x180017135  lea     edx, [rax+14h]
0x180017138  mov     r9, rdi
0x18001713b  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180017142  call    WPP_SF_S
0x180017147  mov     eax, 8BFh
0x18001714c  mov     [rsp+340h+var_2F8], r14d
0x180017151  mov     [rsp+340h+var_2F4], ax
0x180017156  mov     ebx, r14d
0x180017159  jmp     loc_1800172C0
0x18001715e  mov     [rsp+340h+hTemplateFile], rsi; hTemplateFile
0x180017163  mov     r8d, 3; dwShareMode
0x180017169  mov     [rsp+340h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18001716d  xor     r9d, r9d; lpSecurityAttributes
0x180017170  mov     edx, 40000000h; dwDesiredAccess
0x180017175  mov     [rsp+340h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001717a  mov     rcx, rdi; lpFileName
0x18001717d  call    cs:__imp_CreateFileW
0x180017183  mov     rdi, rax
0x180017186  inc     rax
0x180017189  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001718f  jnz     short loc_1800171BE
0x180017191  call    GetLastFailureAsHRESULT
0x180017196  mov     ebx, eax
0x180017198  mov     [rsp+340h+var_2F8], eax
0x18001719c  mov     eax, 8C7h
0x1800171a1  mov     [rsp+340h+var_2F2], ax
0x1800171a6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800171aa  jz      loc_1800172C0
0x1800171b0  test    rdi, rdi
0x1800171b3  jz      loc_1800172C0
0x1800171b9  jmp     loc_1800172B7
0x1800171be  mov     [rsp+340h+lpOverlapped], rsi; lpOverlapped
0x1800171c3  mov     eax, 8C7h
0x1800171c8  mov     [rsp+340h+var_2F4], ax
0x1800171cd  xor     r9d, r9d; nInBufferSize
0x1800171d0  lea     rax, [rsp+340h+BytesReturned]
0x1800171d5  mov     [rsp+340h+var_2F8], esi
0x1800171d9  mov     [rsp+340h+hTemplateFile], rax; lpBytesReturned
0x1800171de  xor     r8d, r8d; lpInBuffer
0x1800171e1  lea     rax, [rbp+240h+OutBuffer]
0x1800171e5  mov     [rsp+340h+dwFlagsAndAttributes], 40h ; '@'; nOutBufferSize
0x1800171ed  mov     edx, 900F4h; dwIoControlCode
0x1800171f2  mov     qword ptr [rsp+340h+dwCreationDisposition], rax; lpOutBuffer
0x1800171f7  mov     rcx, rdi; hDevice
0x1800171fa  call    cs:__imp_DeviceIoControl
0x180017200  test    eax, eax
0x180017202  jz      short loc_180017214
0x180017204  mov     eax, 8DEh
0x180017209  mov     [rsp+340h+var_2F8], esi
0x18001720d  mov     ebx, esi
0x18001720f  jmp     loc_1800172B2
0x180017214  call    cs:__imp_GetLastError
0x18001721a  mov     ebx, eax
0x18001721c  sub     eax, r14d
0x18001721f  jz      loc_1800172A5
0x180017225  cmp     eax, 49Ah
0x18001722a  jz      short loc_18001724D
0x18001722c  test    ebx, ebx
0x18001722e  jle     short loc_180017239
0x180017230  movzx   ebx, bx
0x180017233  or      ebx, 80070000h
0x180017239  mov     [rsp+340h+var_2F8], ebx
0x18001723d  test    ebx, ebx
0x18001723f  jns     short loc_18001729B
0x180017241  mov     eax, 8F9h
0x180017246  mov     [rsp+340h+var_2F2], ax
0x18001724b  jmp     short loc_1800172B7
0x18001724d  mov     [rsp+340h+lpOverlapped], rsi; lpOverlapped
0x180017252  lea     rax, [rsp+340h+BytesReturned]
0x180017257  mov     [rsp+340h+hTemplateFile], rax; lpBytesReturned
0x18001725c  lea     r8, [rbp+240h+InBuffer]; lpInBuffer
0x180017260  mov     [rsp+340h+dwFlagsAndAttributes], esi; nOutBufferSize
0x180017264  mov     r9d, 10h; nInBufferSize
0x18001726a  mov     edx, 900E7h; dwIoControlCode
0x18001726f  mov     qword ptr [rsp+340h+dwCreationDisposition], rsi; lpOutBuffer
0x180017274  mov     rcx, rdi; hDevice
0x180017277  mov     qword ptr [rbp+240h+InBuffer], rsi
0x18001727b  mov     qword ptr [rbp+240h+InBuffer+8], rsi
0x18001727f  call    cs:__imp_DeviceIoControl
0x180017285  test    eax, eax
0x180017287  jnz     short loc_18001729B
0x180017289  call    GetLastFailureAsHRESULT
0x18001728e  mov     ebx, eax
0x180017290  mov     [rsp+340h+var_2F8], eax
0x180017294  mov     eax, 8F1h
0x180017299  jmp     short loc_180017246
0x18001729b  mov     eax, 8FDh
0x1800172a0  jmp     loc_180017209
0x1800172a5  mov     [rsp+340h+var_2F8], r14d
0x1800172aa  mov     eax, 8F5h
0x1800172af  mov     ebx, r14d
0x1800172b2  mov     [rsp+340h+var_2F4], ax
0x1800172b7  mov     rcx, rdi; hObject
0x1800172ba  call    cs:__imp_CloseHandle
0x1800172c0  lea     rcx, [rbp+240h+String2]; this
0x1800172c4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800172c9  lea     rcx, [rbp+240h+String1]; this
0x1800172cd  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800172d2  lea     rcx, [rsp+340h+var_2F8]; this
0x1800172d7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800172dc  mov     eax, ebx
0x1800172de  mov     rcx, [rbp+240h+var_40]
0x1800172e5  xor     rcx, rsp; StackCookie
0x1800172e8  call    __security_check_cookie
0x1800172ed  add     rsp, 318h
0x1800172f4  pop     r15
0x1800172f6  pop     r14
0x1800172f8  pop     rdi
0x1800172f9  pop     rsi
0x1800172fa  pop     rbx
0x1800172fb  pop     rbp
0x1800172fc  retn
```
