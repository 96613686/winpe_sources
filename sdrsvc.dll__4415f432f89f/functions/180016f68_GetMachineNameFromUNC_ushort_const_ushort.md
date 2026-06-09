# GetMachineNameFromUNC(ushort const *,ushort * *)

- ea: `0x180016f68`
- end: `0x1800171ed`
- name: `?GetMachineNameFromUNC@@YAJPEBGPEAPEAG@Z`
- size: `645`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x180017c20`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180016f68`
- `0x1800171f4`
- `0x18001c58c`
- `0x18001c61c`
- `0x18001f624`
- `0x180020488`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `msvcrt!wcschr` at `0x180017124`
- `msvcrt!wcschr` at `0x180017124`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800171b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800171b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001706f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001706f`
- `ntdll!NtQueryInformationFile` at `0x1800170c3`
- `ntdll!NtQueryInformationFile` at `0x1800170c3`

## pseudocode

```c
__int64 __fastcall GetMachineNameFromUNC(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 FileW; // rbx
  __int16 v5; // ax
  int LastFailureAsHRESULT; // edi
  bool v7; // zf
  __int64 v8; // rcx
  unsigned int v9; // eax
  wchar_t *v10; // rcx
  unsigned __int16 *v11; // rax
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v14; // [rsp+44h] [rbp-BCh]
  __int16 v15; // [rsp+46h] [rbp-BAh]
  __int64 *v16; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-78h] BYREF
  unsigned int FileInformation; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v20; // [rsp+A4h] [rbp-5Ch] BYREF
  wchar_t Str[525]; // [rsp+A6h] [rbp-5Ah] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "GetMachineNameFromUNC", 807, 1);
  FileInformation = 0;
  FileW = -1;
  memset_0(&v20, 0, 0x414u);
  v17 = 0;
  v16 = qword_180028260;
  IoStatusBlock = 0;
  if ( a2 )
    *a2 = 0;
  v5 = 820;
  if ( !a1 || (v14 = 820, v5 = 821, !a2) || (v13 = 0, v14 = 821, v7 = (unsigned int)SdIsPathUNC(a1) == 0, v5 = 822, !v7) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_19:
    v13 = LastFailureAsHRESULT;
    goto LABEL_20;
  }
  v13 = 0;
  v14 = 822;
  FileW = (__int64)CreateFileW(a1, 0, 7u, 0, 3u, 0x2000000u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v13 = LastFailureAsHRESULT;
    v5 = 839;
LABEL_20:
    v15 = v5;
    goto LABEL_21;
  }
  v13 = 0;
  v14 = 839;
  v9 = NtQueryInformationFile(
         (HANDLE)FileW,
         &IoStatusBlock,
         &FileInformation,
         0x416u,
         FileNetworkPhysicalNameInformation);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v9);
  v13 = LastFailureAsHRESULT;
  v5 = 849;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_20;
  v14 = 849;
  if ( v20 != 92 || Str[0] == 92 )
  {
    v5 = 856;
    goto LABEL_18;
  }
  v14 = 856;
  v13 = 0;
  Str[((unsigned __int64)FileInformation >> 1) - 1] = 0;
  v10 = wcschr(Str, 0x5Cu);
  v5 = 870;
  if ( !v10 )
  {
LABEL_18:
    LastFailureAsHRESULT = -2130706378;
    goto LABEL_19;
  }
  v14 = 870;
  v13 = 0;
  *v10 = 0;
  LastFailureAsHRESULT = CBsString::Append((CBsString *)&v16, Str);
  v13 = LastFailureAsHRESULT;
  v5 = 876;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_20;
  v14 = 876;
  v11 = 0;
  v17 = 0;
  if ( v16 != qword_180028260 )
    v11 = (unsigned __int16 *)v16;
  *a2 = v11;
  v16 = qword_180028260;
LABEL_21:
  CBsString::_Release((LPVOID *)&v16);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180016f68  mov     [rsp-8+arg_10], rbx
0x180016f6d  mov     [rsp-8+arg_18], rsi
0x180016f72  push    rbp
0x180016f73  push    rdi
0x180016f74  push    r15
0x180016f76  lea     rbp, [rsp-3D0h]
0x180016f7e  sub     rsp, 4D0h
0x180016f85  mov     rax, cs:__security_cookie
0x180016f8c  xor     rax, rsp
0x180016f8f  mov     [rbp+3E0h+var_20], rax
0x180016f96  mov     rsi, rdx
0x180016f99  mov     rdi, rcx
0x180016f9c  lea     rdx, aGetmachinename; "GetMachineNameFromUNC"
0x180016fa3  mov     r9d, 1; unsigned __int16
0x180016fa9  lea     rcx, [rsp+4E0h+var_4A0]; this
0x180016fae  mov     r8d, 327h; unsigned __int16
0x180016fb4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180016fb9  xor     edx, edx; Val
0x180016fbb  mov     [rbp+3E0h+FileInformation], 0
0x180016fc2  mov     r8d, 414h; Size
0x180016fc8  lea     rcx, [rbp+3E0h+var_43C]; void *
0x180016fcc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016fd0  call    memset_0
0x180016fd5  mov     [rbp+3E0h+var_460], 0
0x180016fdd  xorps   xmm0, xmm0
0x180016fe0  lea     r15, qword_180028260
0x180016fe7  mov     [rsp+4E0h+var_468], r15
0x180016fec  movups  xmmword ptr [rbp+3E0h+IoStatusBlock], xmm0
0x180016ff0  test    rsi, rsi
0x180016ff3  jz      short loc_180016FFC
0x180016ff5  mov     qword ptr [rsi], 0
0x180016ffc  mov     eax, 334h
0x180017001  test    rdi, rdi
0x180017004  jnz     short loc_180017010
0x180017006  mov     edi, 80070057h
0x18001700b  jmp     loc_180017194
0x180017010  mov     [rsp+4E0h+var_49C], ax
0x180017015  mov     eax, 335h
0x18001701a  test    rsi, rsi
0x18001701d  jz      short loc_180017006
0x18001701f  mov     rcx, rdi; unsigned __int16 *
0x180017022  mov     [rsp+4E0h+var_4A0], 0
0x18001702a  mov     [rsp+4E0h+var_49C], ax
0x18001702f  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x180017034  test    eax, eax
0x180017036  mov     eax, 336h
0x18001703b  jnz     short loc_180017006
0x18001703d  xor     r9d, r9d; lpSecurityAttributes
0x180017040  mov     [rsp+4E0h+hTemplateFile], 0; hTemplateFile
0x180017049  mov     [rsp+4E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180017051  xor     edx, edx; dwDesiredAccess
0x180017053  mov     rcx, rdi; lpFileName
0x180017056  mov     [rsp+4E0h+var_4A0], 0
0x18001705e  mov     [rsp+4E0h+var_49C], ax
0x180017063  lea     r8d, [r9+7]; dwShareMode
0x180017067  mov     [rsp+4E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001706f  call    cs:__imp_CreateFileW
0x180017075  mov     rbx, rax
0x180017078  inc     rax
0x18001707b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180017081  jnz     short loc_180017098
0x180017083  call    GetLastFailureAsHRESULT
0x180017088  mov     edi, eax
0x18001708a  mov     [rsp+4E0h+var_4A0], eax
0x18001708e  mov     eax, 347h
0x180017093  jmp     loc_180017198
0x180017098  mov     eax, 347h
0x18001709d  mov     [rsp+4E0h+var_4A0], 0
0x1800170a5  mov     r9d, 416h; Length
0x1800170ab  mov     [rsp+4E0h+var_49C], ax
0x1800170b0  lea     r8, [rbp+3E0h+FileInformation]; FileInformation
0x1800170b4  mov     [rsp+4E0h+dwCreationDisposition], 31h ; '1'; FileInformationClass
0x1800170bc  lea     rdx, [rbp+3E0h+IoStatusBlock]; IoStatusBlock
0x1800170c0  mov     rcx, rbx; FileHandle
0x1800170c3  call    cs:__imp_NtQueryInformationFile
0x1800170c9  mov     ecx, eax
0x1800170cb  call    HRESULTFromNTSTATUS
0x1800170d0  mov     edi, eax
0x1800170d2  mov     [rsp+4E0h+var_4A0], eax
0x1800170d6  test    eax, eax
0x1800170d8  mov     eax, 351h
0x1800170dd  js      loc_180017198
0x1800170e3  mov     edx, 5Ch ; '\'; Ch
0x1800170e8  mov     [rsp+4E0h+var_49C], ax
0x1800170ed  cmp     [rbp+3E0h+var_43C], dx
0x1800170f1  jnz     loc_18001718A
0x1800170f7  cmp     [rbp+3E0h+Str], dx
0x1800170fb  jz      loc_18001718A
0x180017101  mov     ecx, [rbp+3E0h+FileInformation]
0x180017104  mov     eax, 358h
0x180017109  shr     rcx, 1
0x18001710c  mov     [rsp+4E0h+var_49C], ax
0x180017111  xor     eax, eax
0x180017113  mov     [rsp+4E0h+var_4A0], 0
0x18001711b  mov     [rbp+rcx*2+3E0h+var_43C], ax
0x180017120  lea     rcx, [rbp+3E0h+Str]; Str
0x180017124  call    cs:__imp_wcschr
0x18001712a  mov     rcx, rax
0x18001712d  test    rax, rax
0x180017130  mov     eax, 366h
0x180017135  jz      short loc_18001718F
0x180017137  mov     [rsp+4E0h+var_49C], ax
0x18001713c  xor     eax, eax
0x18001713e  mov     [rsp+4E0h+var_4A0], 0
0x180017146  mov     [rcx], ax
0x180017149  lea     rdx, [rbp+3E0h+Str]; unsigned __int16 *
0x18001714d  lea     rcx, [rsp+4E0h+var_468]; this
0x180017152  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180017157  mov     edi, eax
0x180017159  mov     [rsp+4E0h+var_4A0], eax
0x18001715d  test    eax, eax
0x18001715f  mov     eax, 36Ch
0x180017164  js      short loc_180017198
0x180017166  mov     [rsp+4E0h+var_49C], ax
0x18001716b  xor     eax, eax
0x18001716d  cmp     [rsp+4E0h+var_468], r15
0x180017172  mov     [rbp+3E0h+var_460], 0
0x18001717a  cmovnz  rax, [rsp+4E0h+var_468]
0x180017180  mov     [rsi], rax
0x180017183  mov     [rsp+4E0h+var_468], r15
0x180017188  jmp     short loc_18001719D
0x18001718a  mov     eax, 358h
0x18001718f  mov     edi, 81000036h
0x180017194  mov     [rsp+4E0h+var_4A0], edi
0x180017198  mov     [rsp+4E0h+var_49A], ax
0x18001719d  lea     rcx, [rsp+4E0h+var_468]; this
0x1800171a2  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800171a7  lea     rcx, [rbx-1]
0x1800171ab  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800171af  ja      short loc_1800171BA
0x1800171b1  mov     rcx, rbx; hObject
0x1800171b4  call    cs:__imp_CloseHandle
0x1800171ba  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800171bf  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800171c4  mov     eax, edi
0x1800171c6  mov     rcx, [rbp+3E0h+var_20]
0x1800171cd  xor     rcx, rsp; StackCookie
0x1800171d0  call    __security_check_cookie
0x1800171d5  lea     r11, [rsp+4E0h+var_10]
0x1800171dd  mov     rbx, [r11+30h]
0x1800171e1  mov     rsi, [r11+38h]
0x1800171e5  mov     rsp, r11
0x1800171e8  pop     r15
0x1800171ea  pop     rdi
0x1800171eb  pop     rbp
0x1800171ec  retn
```
