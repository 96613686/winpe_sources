# GetTargetForJunctionPointDirectory(ushort const *,ushort * *)

- ea: `0x1400e2788`
- end: `0x1400e2b33`
- name: `?GetTargetForJunctionPointDirectory@@YAJPEBGPEAPEAG@Z`
- size: `939`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting, service_task`

## callers

- `0x14011f9a8`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x1400e1be0`
- `0x1400e2788`
- `0x1400e4138`
- `0x140134cd2`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1400e28d0`
- `KERNEL32!CreateFileW` at `0x1400e28d0`
- `KERNEL32!CloseHandle` at `0x1400e2ad9`
- `KERNEL32!CloseHandle` at `0x1400e2ad9`
- `KERNEL32!GetLastError` at `0x1400e28df`
- `KERNEL32!GetLastError` at `0x1400e2971`
- `KERNEL32!GetLastError` at `0x1400e28df`
- `KERNEL32!GetLastError` at `0x1400e2971`
- `KERNEL32!DeviceIoControl` at `0x1400e2967`
- `KERNEL32!DeviceIoControl` at `0x1400e2967`
- `ole32!CoTaskMemAlloc` at `0x1400e2810`
- `ole32!CoTaskMemAlloc` at `0x1400e2a42`
- `ole32!CoTaskMemAlloc` at `0x1400e2810`
- `ole32!CoTaskMemAlloc` at `0x1400e2a42`
- `ole32!CoTaskMemFree` at `0x1400e2ae2`
- `ole32!CoTaskMemFree` at `0x1400e2aea`
- `ole32!CoTaskMemFree` at `0x1400e2ae2`
- `ole32!CoTaskMemFree` at `0x1400e2aea`

## string_xrefs

- `0x1400e27da`: `wszSourcePath`
- `0x1400e27e6`: `base\stor\blb\dsm\dsmutils\dll\fsutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetTargetForJunctionPointDirectory(LPCWSTR lpFileName, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HANDLE FileW; // rbp
  signed int LastError; // eax
  __int64 v11; // r8
  signed int v12; // eax
  void *v13; // rax
  void *v14; // r14
  unsigned int v16; // [rsp+70h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids);
  }
  if ( !lpFileName )
    BlbAssert("base\\stor\\blb\\dsm\\dsmutils\\dll\\fsutils.cpp", 0xFEAu, "wszSourcePath");
  *a2 = 0;
  v16 = -1;
  BytesReturned = 0;
  v4 = (unsigned __int16 *)CoTaskMemAlloc(0x4000u);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
    goto LABEL_53;
  }
  memset_0(v4, 0, 0x4000u);
  FSWrapperGetFileAttributes(lpFileName, &v16, 0);
  if ( (v16 & 0x400) == 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_15;
    }
    v8 = 46;
LABEL_14:
    WPP_SF_S(v7[2], v8, &WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids, lpFileName);
LABEL_15:
    v6 = -2147024809;
    goto LABEL_53;
  }
  if ( (v16 & 0x10) == 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_15;
    }
    v8 = 47;
    goto LABEL_14;
  }
  FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x2200000u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)&WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids,
        (_DWORD)lpFileName,
        v6);
    }
  }
  else
  {
    if ( DeviceIoControl(FileW, 0x900A8u, 0, 0, v5, 0x4000u, &BytesReturned, 0) )
    {
      if ( *(_DWORD *)v5 == -1610612733 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v5[6], v11, v5 + 8, v5[6], v5[7]);
        }
        v13 = CoTaskMemAlloc(v5[7] + 2LL);
        v14 = v13;
        if ( v13 )
        {
          v6 = 0;
          memset_0(v13, 0, v5[7] + 2LL);
          memcpy_0(v14, (char *)v5 + v5[6] + 16, v5[7]);
          *((_WORD *)v14 + ((unsigned __int64)v5[7] >> 1)) = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              (unsigned int)&WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids,
              (_DWORD)lpFileName,
              (__int64)v14);
          }
          *a2 = (unsigned __int16 *)v14;
        }
        else
        {
          v6 = -2147024882;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids);
        }
        v6 = -2147024809;
      }
    }
    else
    {
      v12 = GetLastError();
      v6 = v12;
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids);
      }
    }
    CloseHandle(FileW);
  }
LABEL_53:
  CoTaskMemFree(v5);
  CoTaskMemFree(0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1400e2788  mov     [rsp+arg_10], rbx
0x1400e278d  push    rbp
0x1400e278e  push    rsi
0x1400e278f  push    rdi
0x1400e2790  push    r14
0x1400e2792  push    r15
0x1400e2794  sub     rsp, 40h
0x1400e2798  mov     r15, rdx
0x1400e279b  mov     rsi, rcx
0x1400e279e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e27a5  lea     r14, WPP_GLOBAL_Control
0x1400e27ac  lea     rbx, WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids
0x1400e27b3  cmp     rcx, r14
0x1400e27b6  jz      short loc_1400E27D5
0x1400e27b8  test    byte ptr [rcx+1Ch], 1
0x1400e27bc  jz      short loc_1400E27D5
0x1400e27be  cmp     byte ptr [rcx+19h], 4
0x1400e27c2  jb      short loc_1400E27D5
0x1400e27c4  mov     rcx, [rcx+10h]
0x1400e27c8  mov     edx, 2Dh ; '-'
0x1400e27cd  mov     r8, rbx
0x1400e27d0  call    WPP_SF_
0x1400e27d5  test    rsi, rsi
0x1400e27d8  jnz     short loc_1400E27F2
0x1400e27da  lea     r8, aWszsourcepath; "wszSourcePath"
0x1400e27e1  mov     edx, 0FEAh; unsigned int
0x1400e27e6  lea     rcx, aBaseStorBlbDsm_14; "base\\stor\\blb\\dsm\\dsmutils\\dll\\fs"...
0x1400e27ed  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400e27f2  mov     ebp, 4000h
0x1400e27f7  mov     qword ptr [r15], 0
0x1400e27fe  mov     ecx, ebp; cb
0x1400e2800  mov     [rsp+68h+arg_0], 0FFFFFFFFh
0x1400e2808  mov     [rsp+68h+BytesReturned], 0
0x1400e2810  call    cs:__imp_CoTaskMemAlloc
0x1400e2816  mov     rdi, rax
0x1400e2819  test    rax, rax
0x1400e281c  jnz     short loc_1400E2828
0x1400e281e  mov     ebx, 8007000Eh
0x1400e2823  jmp     loc_1400E2ADF
0x1400e2828  mov     r8, rbp; Size
0x1400e282b  xor     edx, edx; Val
0x1400e282d  mov     rcx, rdi; void *
0x1400e2830  call    memset_0
0x1400e2835  xor     r8d, r8d; bool
0x1400e2838  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x1400e283d  mov     rcx, rsi; lpFileName
0x1400e2840  call    ?FSWrapperGetFileAttributes@@YAJPEBGPEAK_N@Z; FSWrapperGetFileAttributes(ushort const *,ulong *,bool)
0x1400e2845  test    [rsp+68h+arg_0], 400h
0x1400e284d  jnz     short loc_1400E2885
0x1400e284f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e2856  cmp     rcx, r14
0x1400e2859  jz      short loc_1400E287B
0x1400e285b  test    byte ptr [rcx+1Ch], 1
0x1400e285f  jz      short loc_1400E287B
0x1400e2861  cmp     byte ptr [rcx+19h], 2
0x1400e2865  jb      short loc_1400E287B
0x1400e2867  mov     edx, 2Eh ; '.'
0x1400e286c  mov     rcx, [rcx+10h]
0x1400e2870  mov     r9, rsi
0x1400e2873  mov     r8, rbx
0x1400e2876  call    WPP_SF_S
0x1400e287b  mov     ebx, 80070057h
0x1400e2880  jmp     loc_1400E2ADF
0x1400e2885  test    byte ptr [rsp+68h+arg_0], 10h
0x1400e288a  jnz     short loc_1400E28AB
0x1400e288c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e2893  cmp     rcx, r14
0x1400e2896  jz      short loc_1400E287B
0x1400e2898  test    byte ptr [rcx+1Ch], 1
0x1400e289c  jz      short loc_1400E287B
0x1400e289e  cmp     byte ptr [rcx+19h], 2
0x1400e28a2  jb      short loc_1400E287B
0x1400e28a4  mov     edx, 2Fh ; '/'
0x1400e28a9  jmp     short loc_1400E286C
0x1400e28ab  xor     r9d, r9d; lpSecurityAttributes
0x1400e28ae  mov     [rsp+68h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x1400e28b7  mov     [rsp+68h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1400e28bf  xor     edx, edx; dwDesiredAccess
0x1400e28c1  mov     rcx, rsi; lpFileName
0x1400e28c4  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1400e28cc  lea     r8d, [r9+7]; dwShareMode
0x1400e28d0  call    cs:__imp_CreateFileW
0x1400e28d6  mov     rbp, rax
0x1400e28d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400e28dd  jnz     short loc_1400E2939
0x1400e28df  call    cs:__imp_GetLastError
0x1400e28e5  mov     ebx, eax
0x1400e28e7  test    eax, eax
0x1400e28e9  jle     short loc_1400E28F4
0x1400e28eb  movzx   ebx, ax
0x1400e28ee  or      ebx, 80070000h
0x1400e28f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e28fb  cmp     rcx, r14
0x1400e28fe  jz      loc_1400E2ADF
0x1400e2904  test    byte ptr [rcx+1Ch], 1
0x1400e2908  jz      loc_1400E2ADF
0x1400e290e  cmp     byte ptr [rcx+19h], 2
0x1400e2912  jb      loc_1400E2ADF
0x1400e2918  mov     rcx, [rcx+10h]
0x1400e291c  lea     r8, WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids
0x1400e2923  mov     edx, 30h ; '0'
0x1400e2928  mov     [rsp+68h+dwCreationDisposition], ebx
0x1400e292c  mov     r9, rsi
0x1400e292f  call    WPP_SF_Sd
0x1400e2934  jmp     loc_1400E2ADF
0x1400e2939  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1400e2942  lea     rax, [rsp+68h+BytesReturned]
0x1400e2947  mov     [rsp+68h+hTemplateFile], rax; lpBytesReturned
0x1400e294c  xor     r9d, r9d; nInBufferSize
0x1400e294f  mov     [rsp+68h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x1400e2957  xor     r8d, r8d; lpInBuffer
0x1400e295a  mov     edx, 900A8h; dwIoControlCode
0x1400e295f  mov     qword ptr [rsp+68h+dwCreationDisposition], rdi; lpOutBuffer
0x1400e2964  mov     rcx, rbp; hDevice
0x1400e2967  call    cs:__imp_DeviceIoControl
0x1400e296d  test    eax, eax
0x1400e296f  jnz     short loc_1400E29C7
0x1400e2971  call    cs:__imp_GetLastError
0x1400e2977  mov     ebx, eax
0x1400e2979  test    eax, eax
0x1400e297b  jle     short loc_1400E2986
0x1400e297d  movzx   ebx, ax
0x1400e2980  or      ebx, 80070000h
0x1400e2986  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e298d  cmp     rcx, r14
0x1400e2990  jz      loc_1400E2AD6
0x1400e2996  test    byte ptr [rcx+1Ch], 1
0x1400e299a  jz      loc_1400E2AD6
0x1400e29a0  cmp     byte ptr [rcx+19h], 2
0x1400e29a4  jb      loc_1400E2AD6
0x1400e29aa  mov     rcx, [rcx+10h]
0x1400e29ae  lea     r8, WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids
0x1400e29b5  mov     edx, 31h ; '1'
0x1400e29ba  mov     r9d, ebx
0x1400e29bd  call    WPP_SF_d
0x1400e29c2  jmp     loc_1400E2AD6
0x1400e29c7  cmp     dword ptr [rdi], 0A0000003h
0x1400e29cd  jz      short loc_1400E2A05
0x1400e29cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e29d6  cmp     rcx, r14
0x1400e29d9  jz      short loc_1400E29FB
0x1400e29db  test    byte ptr [rcx+1Ch], 1
0x1400e29df  jz      short loc_1400E29FB
0x1400e29e1  cmp     byte ptr [rcx+19h], 2
0x1400e29e5  jb      short loc_1400E29FB
0x1400e29e7  mov     r9d, [rdi]
0x1400e29ea  mov     edx, 32h ; '2'
0x1400e29ef  mov     rcx, [rcx+10h]
0x1400e29f3  mov     r8, rbx
0x1400e29f6  call    WPP_SF_d
0x1400e29fb  mov     ebx, 80070057h
0x1400e2a00  jmp     loc_1400E2AD6
0x1400e2a05  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e2a0c  cmp     rcx, r14
0x1400e2a0f  jz      short loc_1400E2A3A
0x1400e2a11  test    byte ptr [rcx+1Ch], 1
0x1400e2a15  jz      short loc_1400E2A3A
0x1400e2a17  cmp     byte ptr [rcx+19h], 4
0x1400e2a1b  jb      short loc_1400E2A3A
0x1400e2a1d  movzx   eax, word ptr [rdi+0Eh]
0x1400e2a21  lea     r9, [rdi+10h]
0x1400e2a25  movzx   edx, word ptr [rdi+0Ch]
0x1400e2a29  mov     rcx, [rcx+10h]
0x1400e2a2d  mov     [rsp+68h+dwFlagsAndAttributes], eax
0x1400e2a31  mov     [rsp+68h+dwCreationDisposition], edx
0x1400e2a35  call    WPP_SF_qdd
0x1400e2a3a  movzx   ecx, word ptr [rdi+0Eh]
0x1400e2a3e  add     rcx, 2; cb
0x1400e2a42  call    cs:__imp_CoTaskMemAlloc
0x1400e2a48  mov     r14, rax
0x1400e2a4b  test    rax, rax
0x1400e2a4e  jnz     short loc_1400E2A57
0x1400e2a50  mov     ebx, 8007000Eh
0x1400e2a55  jmp     short loc_1400E2ACF
0x1400e2a57  movzx   r8d, word ptr [rdi+0Eh]
0x1400e2a5c  xor     edx, edx; Val
0x1400e2a5e  add     r8, 2; Size
0x1400e2a62  mov     rcx, r14; void *
0x1400e2a65  xor     ebx, ebx
0x1400e2a67  call    memset_0
0x1400e2a6c  movzx   edx, word ptr [rdi+0Ch]
0x1400e2a70  mov     rcx, r14; void *
0x1400e2a73  movzx   r8d, word ptr [rdi+0Eh]; Size
0x1400e2a78  add     rdx, 10h
0x1400e2a7c  add     rdx, rdi; Src
0x1400e2a7f  call    memcpy_0
0x1400e2a84  movzx   ecx, word ptr [rdi+0Eh]
0x1400e2a88  shr     rcx, 1
0x1400e2a8b  xor     eax, eax
0x1400e2a8d  mov     [r14+rcx*2], ax
0x1400e2a92  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e2a99  lea     rax, WPP_GLOBAL_Control
0x1400e2aa0  cmp     rcx, rax
0x1400e2aa3  jz      short loc_1400E2ACC
0x1400e2aa5  test    byte ptr [rcx+1Ch], 1
0x1400e2aa9  jz      short loc_1400E2ACC
0x1400e2aab  cmp     byte ptr [rcx+19h], 4
0x1400e2aaf  jb      short loc_1400E2ACC
0x1400e2ab1  mov     rcx, [rcx+10h]
0x1400e2ab5  lea     edx, [rbx+34h]
0x1400e2ab8  mov     r9, rsi
0x1400e2abb  mov     qword ptr [rsp+68h+dwCreationDisposition], r14
0x1400e2ac0  lea     r8, WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids
0x1400e2ac7  call    WPP_SF_SS
0x1400e2acc  mov     [r15], r14
0x1400e2acf  lea     r14, WPP_GLOBAL_Control
0x1400e2ad6  mov     rcx, rbp; hObject
0x1400e2ad9  call    cs:__imp_CloseHandle
0x1400e2adf  mov     rcx, rdi; pv
0x1400e2ae2  call    cs:__imp_CoTaskMemFree
0x1400e2ae8  xor     ecx, ecx; pv
0x1400e2aea  call    cs:__imp_CoTaskMemFree
0x1400e2af0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e2af7  cmp     rcx, r14
0x1400e2afa  jz      short loc_1400E2B1D
0x1400e2afc  test    byte ptr [rcx+1Ch], 1
0x1400e2b00  jz      short loc_1400E2B1D
0x1400e2b02  cmp     byte ptr [rcx+19h], 4
0x1400e2b06  jb      short loc_1400E2B1D
0x1400e2b08  mov     rcx, [rcx+10h]
0x1400e2b0c  lea     r8, WPP_17bef13e71a1322d92109b3fa5e1dd6a_Traceguids
0x1400e2b13  mov     edx, 35h ; '5'
0x1400e2b18  call    WPP_SF_
0x1400e2b1d  mov     eax, ebx
0x1400e2b1f  mov     rbx, [rsp+68h+arg_10]
0x1400e2b27  add     rsp, 40h
0x1400e2b2b  pop     r15
0x1400e2b2d  pop     r14
0x1400e2b2f  pop     rdi
0x1400e2b30  pop     rsi
0x1400e2b31  pop     rbp
0x1400e2b32  retn
```
