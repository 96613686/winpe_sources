# CompressFileBackedByWim

- ea: `0x18001b8c4`
- end: `0x18001bae2`
- name: `CompressFileBackedByWim`
- size: `542`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023f00`

## callees

- `0x180010938`
- `0x180017344`
- `0x180018e94`
- `0x180019188`
- `0x18001b8c4`
- `0x1800607b0`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001ba94`
- `KERNEL32!HeapFree` at `0x18001ba94`
- `KERNEL32!GetLastError` at `0x18001ba5e`
- `KERNEL32!GetLastError` at `0x18001ba5e`
- `KERNEL32!CreateFileW` at `0x18001b974`
- `KERNEL32!CreateFileW` at `0x18001b974`
- `KERNEL32!SetLastError` at `0x18001baa8`
- `KERNEL32!SetLastError` at `0x18001baa8`
- `KERNEL32!GetProcessHeap` at `0x18001ba80`
- `KERNEL32!GetProcessHeap` at `0x18001ba80`

## string_xrefs

- `0x18001ba2b`: `CompressFileBackedByWim`

## pseudocode

```c
__int64 __fastcall CompressFileBackedByWim(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        int a5,
        __int64 *a6,
        WCHAR **a7,
        _QWORD *a8)
{
  unsigned int v10; // r15d
  __int64 FileW; // rbp
  DWORD LastError; // r14d
  WCHAR *TempFile; // rdi
  __int64 v14; // rax
  __int128 v15; // xmm0
  HANDLE ProcessHeap; // rax
  _BYTE v19[24]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v20; // [rsp+68h] [rbp-70h]
  int v21; // [rsp+70h] [rbp-68h]
  int v22; // [rsp+74h] [rbp-64h]
  __int64 v23; // [rsp+78h] [rbp-60h]
  __int128 v24; // [rsp+80h] [rbp-58h]
  int v25; // [rsp+90h] [rbp-48h]

  v10 = 0;
  FileW = -1;
  LastError = 0;
  memset_0(v19, 0, 0x20u);
  TempFile = (WCHAR *)GetTempFile(a1);
  if ( !TempFile )
    goto LABEL_13;
  if ( !*TempFile )
    goto LABEL_13;
  FileW = (__int64)CreateFileW(TempFile, 0xC0010000, 7u, 0, 2u, 0x48000100u, 0);
  if ( FileW == -1 )
    goto LABEL_13;
  if ( !a1 || !*(_QWORD *)(a1 + 392) )
  {
    WIMLogMsg(
      1,
      a1,
      (int)TempFile,
      (int)L"Failed to get img event",
      -2147024890,
      (__int64)L"CompressFileBackedByWim",
      239);
LABEL_13:
    LastError = GetLastError();
    ReclaimTempFile(a1, FileW, TempFile);
    goto LABEL_14;
  }
  v20 = *(_QWORD *)(a1 + 392);
  v14 = *(_QWORD *)(a1 + 64);
  v23 = a3;
  v21 = 36;
  if ( !v14 )
    v14 = a1;
  v22 = *(_DWORD *)(v14 + 32);
  v15 = *a4;
  v25 = *((_DWORD *)a4 + 4);
  v24 = v15;
  if ( !(unsigned int)ReadWriteData((HANDLE)FileW, 1u) )
    goto LABEL_13;
  *a6 = FileW;
  *a8 = 36;
  if ( a7 )
  {
    *a7 = TempFile;
    TempFile = 0;
  }
  v10 = 1;
LABEL_14:
  if ( TempFile )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, TempFile);
  }
  if ( LastError )
    SetLastError(LastError);
  return v10;
}

```

## disassembly

```asm
0x18001b8c4  mov     [rsp+arg_8], rbx
0x18001b8c9  push    rbp
0x18001b8ca  push    rsi
0x18001b8cb  push    rdi
0x18001b8cc  push    r12
0x18001b8ce  push    r13
0x18001b8d0  push    r14
0x18001b8d2  push    r15
0x18001b8d4  sub     rsp, 0A0h
0x18001b8db  mov     rax, cs:__security_cookie
0x18001b8e2  xor     rax, rsp
0x18001b8e5  mov     [rsp+0D8h+var_40], rax
0x18001b8ed  mov     rax, [rsp+0D8h+arg_38]
0x18001b8f5  mov     rbx, r8
0x18001b8f8  mov     r13, [rsp+0D8h+arg_28]
0x18001b900  mov     rsi, rcx
0x18001b903  mov     r12, [rsp+0D8h+arg_30]
0x18001b90b  lea     rcx, [rsp+0D8h+var_88]; void *
0x18001b910  mov     [rsp+0D8h+var_90], rax
0x18001b915  xor     edx, edx; Val
0x18001b917  xor     eax, eax
0x18001b919  mov     [rsp+0D8h+var_98], r9
0x18001b91e  mov     r15d, eax
0x18001b921  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001b925  mov     r14d, eax
0x18001b928  lea     r8d, [rax+20h]; Size
0x18001b92c  call    memset_0
0x18001b931  mov     rcx, rsi
0x18001b934  call    GetTempFile
0x18001b939  mov     rdi, rax
0x18001b93c  xor     eax, eax
0x18001b93e  test    rdi, rdi
0x18001b941  jz      loc_18001BA5E
0x18001b947  cmp     [rdi], ax
0x18001b94a  jz      loc_18001BA5E
0x18001b950  mov     [rsp+0D8h+hTemplateFile], rax; hTemplateFile
0x18001b955  lea     r8d, [rbp+8]; dwShareMode
0x18001b959  mov     [rsp+0D8h+dwFlagsAndAttributes], 48000100h; dwFlagsAndAttributes
0x18001b961  xor     r9d, r9d; lpSecurityAttributes
0x18001b964  mov     edx, 0C0010000h; dwDesiredAccess
0x18001b969  mov     [rsp+0D8h+dwCreationDisposition], 2; dwCreationDisposition
0x18001b971  mov     rcx, rdi; lpFileName
0x18001b974  call    cs:__imp_CreateFileW
0x18001b97b  nop     dword ptr [rax+rax+00h]
0x18001b980  mov     rbp, rax
0x18001b983  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b987  jz      loc_18001BA5E
0x18001b98d  test    rsi, rsi
0x18001b990  jz      loc_18001BA2B
0x18001b996  mov     rax, [rsi+188h]
0x18001b99d  test    rax, rax
0x18001b9a0  jz      loc_18001BA2B
0x18001b9a6  mov     [rsp+0D8h+var_70], rax
0x18001b9ab  lea     r9, [rsp+0D8h+var_88]
0x18001b9b0  mov     rax, [rsi+40h]
0x18001b9b4  lea     rdx, [rsp+0D8h+var_68]
0x18001b9b9  mov     [rsp+0D8h+var_60], rbx
0x18001b9be  mov     rcx, rbp; hFile
0x18001b9c1  xor     ebx, ebx
0x18001b9c3  mov     [rsp+0D8h+var_68], 24h ; '$'
0x18001b9cb  test    rax, rax
0x18001b9ce  mov     [rsp+0D8h+dwCreationDisposition], 1; DWORD
0x18001b9d6  cmovz   rax, rsi
0x18001b9da  lea     r8d, [rbx+24h]
0x18001b9de  mov     eax, [rax+20h]
0x18001b9e1  mov     [rsp+0D8h+var_64], eax
0x18001b9e5  mov     rax, [rsp+0D8h+var_98]
0x18001b9ea  movups  xmm0, xmmword ptr [rax]
0x18001b9ed  mov     eax, [rax+10h]
0x18001b9f0  mov     [rsp+0D8h+var_48], eax
0x18001b9f7  movups  [rsp+0D8h+var_58], xmm0
0x18001b9ff  call    ReadWriteData
0x18001ba04  test    eax, eax
0x18001ba06  jz      short loc_18001BA5E
0x18001ba08  mov     rax, [rsp+0D8h+var_90]
0x18001ba0d  mov     [r13+0], rbp
0x18001ba11  mov     qword ptr [rax], 24h ; '$'
0x18001ba18  test    r12, r12
0x18001ba1b  jz      short loc_18001BA23
0x18001ba1d  mov     [r12], rdi
0x18001ba21  mov     edi, ebx
0x18001ba23  mov     r15d, 1
0x18001ba29  jmp     short loc_18001BA7B
0x18001ba2b  lea     rax, aCompressfileba; "CompressFileBackedByWim"
0x18001ba32  mov     dword ptr [rsp+0D8h+hTemplateFile], 0EFh; int
0x18001ba3a  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], rax; __int64
0x18001ba3f  lea     r9, aFailedToGetImg; "Failed to get img event"
0x18001ba46  mov     r8, rdi; int
0x18001ba49  mov     [rsp+0D8h+dwCreationDisposition], 80070006h; Status
0x18001ba51  mov     rdx, rsi; int
0x18001ba54  mov     ecx, 1; int
0x18001ba59  call    _WIMLogMsg
0x18001ba5e  call    cs:__imp_GetLastError
0x18001ba65  nop     dword ptr [rax+rax+00h]
0x18001ba6a  mov     r8, rdi
0x18001ba6d  mov     rdx, rbp
0x18001ba70  mov     rcx, rsi
0x18001ba73  mov     r14d, eax
0x18001ba76  call    ReclaimTempFile
0x18001ba7b  test    rdi, rdi
0x18001ba7e  jz      short loc_18001BAA0
0x18001ba80  call    cs:__imp_GetProcessHeap
0x18001ba87  nop     dword ptr [rax+rax+00h]
0x18001ba8c  mov     r8, rdi; lpMem
0x18001ba8f  xor     edx, edx; dwFlags
0x18001ba91  mov     rcx, rax; hHeap
0x18001ba94  call    cs:__imp_HeapFree
0x18001ba9b  nop     dword ptr [rax+rax+00h]
0x18001baa0  test    r14d, r14d
0x18001baa3  jz      short loc_18001BAB4
0x18001baa5  mov     ecx, r14d; dwErrCode
0x18001baa8  call    cs:__imp_SetLastError
0x18001baaf  nop     dword ptr [rax+rax+00h]
0x18001bab4  mov     eax, r15d
0x18001bab7  mov     rcx, [rsp+0D8h+var_40]
0x18001babf  xor     rcx, rsp; StackCookie
0x18001bac2  call    __security_check_cookie
0x18001bac7  mov     rbx, [rsp+0D8h+arg_8]
0x18001bacf  add     rsp, 0A0h
0x18001bad6  pop     r15
0x18001bad8  pop     r14
0x18001bada  pop     r13
0x18001badc  pop     r12
0x18001bade  pop     rdi
0x18001badf  pop     rsi
0x18001bae0  pop     rbp
0x18001bae1  retn
```
