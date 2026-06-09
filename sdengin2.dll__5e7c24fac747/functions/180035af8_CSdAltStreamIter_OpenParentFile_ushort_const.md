# CSdAltStreamIter::_OpenParentFile(ushort const *)

- ea: `0x180035af8`
- end: `0x180035d89`
- name: `?_OpenParentFile@CSdAltStreamIter@@AEAAJPEBG@Z`
- size: `657`
- prototype: `int(CSdAltStreamIter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180032510`

## callees

- `0x180008200`
- `0x180014394`
- `0x180035af8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18008f660`
- `0x18009a24c`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180035bf0`
- `ntdll!NtQueryInformationFile` at `0x180035c69`
- `ntdll!NtQueryInformationFile` at `0x180035bf0`
- `ntdll!NtQueryInformationFile` at `0x180035c69`
- `KERNEL32!CreateFileW` at `0x180035b9b`
- `KERNEL32!CreateFileW` at `0x180035b9b`
- `KERNEL32!CloseHandle` at `0x180035bb2`
- `KERNEL32!CloseHandle` at `0x180035bb2`
- `ole32!CoTaskMemFree` at `0x180035c1d`
- `ole32!CoTaskMemFree` at `0x180035c1d`
- `ole32!CoTaskMemAlloc` at `0x180035c34`
- `ole32!CoTaskMemAlloc` at `0x180035c34`

## string_xrefs

- `0x180035b21`: `CSdAltStreamIter::_OpenParentFile`

## pseudocode

```c
__int64 __fastcall CSdAltStreamIter::_OpenParentFile(CSdAltStreamIter *this, const unsigned __int16 *a2)
{
  __int16 v4; // ax
  LPCWSTR *v5; // r14
  int LastFailureAsHRESULT; // ebx
  HANDLE FileW; // rbx
  char *v8; // rcx
  NTSTATUS i; // eax
  unsigned int v10; // esi
  ULONG v11; // ebx
  void *v12; // rax
  __int16 v13; // ax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-29h] BYREF
  int v16; // [rsp+50h] [rbp-19h] BYREF
  __int16 v17; // [rsp+54h] [rbp-15h]
  __int16 v18; // [rsp+56h] [rbp-13h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CSdAltStreamIter::_OpenParentFile", 1348, 1);
  IoStatusBlock = 0;
  v4 = 1353;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v16 = -2147024809;
    goto LABEL_31;
  }
  v16 = 0;
  v17 = 1353;
  v5 = (LPCWSTR *)((char *)this + 48);
  LastFailureAsHRESULT = CBsString::Set((CSdAltStreamIter *)((char *)this + 48), a2);
  v16 = LastFailureAsHRESULT;
  v4 = 1355;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_31:
    v18 = v4;
    goto LABEL_32;
  }
  v17 = 1355;
  FileW = CreateFileW(*v5, 0, 7u, 0, 3u, 0x2000000u, 0);
  v8 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  *((_QWORD *)this + 5) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v16 = LastFailureAsHRESULT;
    v4 = 1359;
    goto LABEL_31;
  }
  v16 = 0;
  v17 = 1359;
  for ( i = NtQueryInformationFile(
              FileW,
              &IoStatusBlock,
              *((PVOID *)this + 9),
              *((_DWORD *)this + 20),
              FileStreamInformation);
        ;
        i = NtQueryInformationFile(*((HANDLE *)this + 5), &IoStatusBlock, v12, v11, FileStreamInformation) )
  {
    v10 = i;
    if ( i != -2147483643 && i != -1073741789 && i != -1073741820 )
      break;
    v11 = 2 * *((_DWORD *)this + 20);
    CoTaskMemFree(*((LPVOID *)this + 9));
    *((_QWORD *)this + 9) = 0;
    *((_DWORD *)this + 20) = 0;
    v12 = CoTaskMemAlloc(v11);
    *((_QWORD *)this + 9) = v12;
    if ( !v12 )
    {
      LastFailureAsHRESULT = -2147024882;
      v16 = -2147024882;
      v18 = 1372;
      goto LABEL_32;
    }
    v16 = 0;
    v17 = 1372;
    *((_DWORD *)this + 20) = v11;
  }
  if ( i < 0 )
  {
    if ( (unsigned int)HRESULTFromNTSTATUS((unsigned int)i) == -2147024809 )
    {
      v13 = 1384;
LABEL_15:
      LastFailureAsHRESULT = 0;
      v16 = 0;
      *((_DWORD *)this + 21) = 0;
      v17 = v13;
      goto LABEL_32;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids,
        (unsigned int)*v5,
        v10);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v10);
    v16 = LastFailureAsHRESULT;
    v4 = 1389;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v17 = 1389;
      goto LABEL_22;
    }
    goto LABEL_31;
  }
  LastFailureAsHRESULT = v16;
LABEL_22:
  if ( IoStatusBlock.Information < 0x20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids, v10);
    v13 = 1401;
    goto LABEL_15;
  }
  *((_DWORD *)this + 21) = 1;
  *((_QWORD *)this + 8) = *((_QWORD *)this + 9);
LABEL_32:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180035af8  push    rbp
0x180035afa  push    rbx
0x180035afb  push    rsi
0x180035afc  push    rdi
0x180035afd  push    r12
0x180035aff  push    r13
0x180035b01  push    r14
0x180035b03  lea     rbp, [rsp-27h]
0x180035b08  sub     rsp, 90h
0x180035b0f  mov     rbx, rdx
0x180035b12  mov     rdi, rcx
0x180035b15  mov     r9d, 1; unsigned __int16
0x180035b1b  mov     r8d, 544h; unsigned __int16
0x180035b21  lea     rdx, aCsdaltstreamit_2; "CSdAltStreamIter::_OpenParentFile"
0x180035b28  lea     rcx, [rbp+57h+var_70]; this
0x180035b2c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180035b31  xorps   xmm0, xmm0
0x180035b34  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180035b38  mov     eax, 549h
0x180035b3d  test    rbx, rbx
0x180035b40  jz      loc_180035D60
0x180035b46  mov     [rbp+57h+var_70], 0
0x180035b4d  mov     [rbp+57h+var_6C], ax
0x180035b51  lea     r14, [rdi+30h]
0x180035b55  mov     rdx, rbx; unsigned __int16 *
0x180035b58  mov     rcx, r14; this
0x180035b5b  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180035b60  mov     ebx, eax
0x180035b62  mov     [rbp+57h+var_70], eax
0x180035b65  test    eax, eax
0x180035b67  mov     eax, 54Bh
0x180035b6c  js      loc_180035D68
0x180035b72  mov     [rbp+57h+var_6C], ax
0x180035b76  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x180035b7f  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180035b87  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180035b8f  xor     r9d, r9d; lpSecurityAttributes
0x180035b92  xor     edx, edx; dwDesiredAccess
0x180035b94  lea     r8d, [r9+7]; dwShareMode
0x180035b98  mov     rcx, [r14]; lpFileName
0x180035b9b  call    cs:__imp_CreateFileW
0x180035ba1  mov     rbx, rax
0x180035ba4  mov     rcx, [rdi+28h]; hObject
0x180035ba8  lea     rdx, [rcx-1]
0x180035bac  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180035bb0  ja      short loc_180035BB8
0x180035bb2  call    cs:__imp_CloseHandle
0x180035bb8  mov     [rdi+28h], rbx
0x180035bbc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180035bc0  jz      loc_180035D4F
0x180035bc6  mov     [rbp+57h+var_70], 0
0x180035bcd  mov     eax, 54Fh
0x180035bd2  mov     [rbp+57h+var_6C], ax
0x180035bd6  mov     r13d, 16h
0x180035bdc  mov     [rsp+0C0h+dwCreationDisposition], r13d; FileInformationClass
0x180035be1  mov     r9d, [rdi+50h]; Length
0x180035be5  mov     r8, [rdi+48h]; FileInformation
0x180035be9  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180035bed  mov     rcx, rbx; FileHandle
0x180035bf0  call    cs:__imp_NtQueryInformationFile
0x180035bf6  mov     r12d, 55Ch
0x180035bfc  mov     esi, eax
0x180035bfe  cmp     eax, 80000005h
0x180035c03  jz      short loc_180035C13
0x180035c05  cmp     eax, 0C0000023h
0x180035c0a  jz      short loc_180035C13
0x180035c0c  cmp     eax, 0C0000004h
0x180035c11  jnz     short loc_180035C71
0x180035c13  mov     eax, [rdi+50h]
0x180035c16  lea     ebx, [rax+rax]
0x180035c19  mov     rcx, [rdi+48h]; pv
0x180035c1d  call    cs:__imp_CoTaskMemFree
0x180035c23  mov     qword ptr [rdi+48h], 0
0x180035c2b  mov     dword ptr [rdi+50h], 0
0x180035c32  mov     ecx, ebx; cb
0x180035c34  call    cs:__imp_CoTaskMemAlloc
0x180035c3a  mov     [rdi+48h], rax
0x180035c3e  test    rax, rax
0x180035c41  jz      loc_180035D40
0x180035c47  mov     [rbp+57h+var_70], 0
0x180035c4e  mov     [rbp+57h+var_6C], r12w
0x180035c53  mov     [rdi+50h], ebx
0x180035c56  mov     [rsp+0C0h+dwCreationDisposition], r13d; FileInformationClass
0x180035c5b  mov     r9d, ebx; Length
0x180035c5e  mov     r8, rax; FileInformation
0x180035c61  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180035c65  mov     rcx, [rdi+28h]; FileHandle
0x180035c69  call    cs:__imp_NtQueryInformationFile
0x180035c6f  jmp     short loc_180035BFC
0x180035c71  lea     r13, WPP_GLOBAL_Control
0x180035c78  mov     r12d, 1000h
0x180035c7e  test    esi, esi
0x180035c80  jns     short loc_180035CF1
0x180035c82  mov     ecx, esi
0x180035c84  call    HRESULTFromNTSTATUS
0x180035c89  mov     ebx, 80070057h
0x180035c8e  cmp     eax, ebx
0x180035c90  jnz     short loc_180035CA8
0x180035c92  mov     eax, 568h
0x180035c97  xor     ebx, ebx
0x180035c99  mov     [rbp+57h+var_70], ebx
0x180035c9c  mov     [rdi+54h], ebx
0x180035c9f  mov     [rbp+57h+var_6C], ax
0x180035ca3  jmp     loc_180035D6C
0x180035ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180035caf  cmp     rcx, r13
0x180035cb2  jz      short loc_180035CD6
0x180035cb4  test    [rcx+1Ch], r12d
0x180035cb8  jz      short loc_180035CD6
0x180035cba  mov     edx, 1Eh
0x180035cbf  mov     [rsp+0C0h+dwCreationDisposition], esi
0x180035cc3  mov     r9, [r14]
0x180035cc6  lea     r8, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids
0x180035ccd  mov     rcx, [rcx+10h]
0x180035cd1  call    WPP_SF_Sd
0x180035cd6  mov     ecx, esi
0x180035cd8  call    HRESULTFromNTSTATUS
0x180035cdd  mov     ebx, eax
0x180035cdf  mov     [rbp+57h+var_70], eax
0x180035ce2  test    eax, eax
0x180035ce4  mov     eax, 56Dh
0x180035ce9  js      short loc_180035D68
0x180035ceb  mov     [rbp+57h+var_6C], ax
0x180035cef  jmp     short loc_180035CF4
0x180035cf1  mov     ebx, [rbp+57h+var_70]
0x180035cf4  cmp     [rbp+57h+IoStatusBlock.Information], 20h ; ' '
0x180035cf9  jnb     short loc_180035D2F
0x180035cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d02  cmp     rcx, r13
0x180035d05  jz      short loc_180035D25
0x180035d07  test    [rcx+1Ch], r12d
0x180035d0b  jz      short loc_180035D25
0x180035d0d  mov     edx, 1Fh
0x180035d12  mov     r9d, esi
0x180035d15  lea     r8, WPP_2494e4283e1c3b4c1616acb96245299d_Traceguids
0x180035d1c  mov     rcx, [rcx+10h]
0x180035d20  call    WPP_SF_d
0x180035d25  mov     eax, 579h
0x180035d2a  jmp     loc_180035C97
0x180035d2f  mov     dword ptr [rdi+54h], 1
0x180035d36  mov     rax, [rdi+48h]
0x180035d3a  mov     [rdi+40h], rax
0x180035d3e  jmp     short loc_180035D6C
0x180035d40  mov     ebx, 8007000Eh
0x180035d45  mov     [rbp+57h+var_70], ebx
0x180035d48  mov     [rbp+57h+var_6A], r12w
0x180035d4d  jmp     short loc_180035D6C
0x180035d4f  call    GetLastFailureAsHRESULT
0x180035d54  mov     ebx, eax
0x180035d56  mov     [rbp+57h+var_70], eax
0x180035d59  mov     eax, 54Fh
0x180035d5e  jmp     short loc_180035D68
0x180035d60  mov     ebx, 80070057h
0x180035d65  mov     [rbp+57h+var_70], ebx
0x180035d68  mov     [rbp+57h+var_6A], ax
0x180035d6c  lea     rcx, [rbp+57h+var_70]; this
0x180035d70  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180035d75  mov     eax, ebx
0x180035d77  add     rsp, 90h
0x180035d7e  pop     r14
0x180035d80  pop     r13
0x180035d82  pop     r12
0x180035d84  pop     rdi
0x180035d85  pop     rsi
0x180035d86  pop     rbx
0x180035d87  pop     rbp
0x180035d88  retn
```
