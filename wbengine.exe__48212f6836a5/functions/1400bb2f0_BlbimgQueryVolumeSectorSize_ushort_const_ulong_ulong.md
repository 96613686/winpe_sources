# BlbimgQueryVolumeSectorSize(ushort const *,ulong *,ulong *)

- ea: `0x1400bb2f0`
- end: `0x1400bb793`
- name: `?BlbimgQueryVolumeSectorSize@@YA?AW4_BLBIMG_RESULT_CODE@@PEBGPEAK1@Z`
- size: `1187`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x1400bf9a4`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14001358c`
- `0x140014200`
- `0x140014260`
- `0x14003c54c`
- `0x1400bb2f0`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1400bb3a9`
- `KERNEL32!CreateFileW` at `0x1400bb606`
- `KERNEL32!CreateFileW` at `0x1400bb3a9`
- `KERNEL32!CreateFileW` at `0x1400bb606`
- `KERNEL32!CloseHandle` at `0x1400bb5b0`
- `KERNEL32!CloseHandle` at `0x1400bb72e`
- `KERNEL32!CloseHandle` at `0x1400bb5b0`
- `KERNEL32!CloseHandle` at `0x1400bb72e`
- `KERNEL32!GetLastError` at `0x1400bb3b8`
- `KERNEL32!GetLastError` at `0x1400bb479`
- `KERNEL32!GetLastError` at `0x1400bb615`
- `KERNEL32!GetLastError` at `0x1400bb69b`
- `KERNEL32!GetLastError` at `0x1400bb3b8`
- `KERNEL32!GetLastError` at `0x1400bb479`
- `KERNEL32!GetLastError` at `0x1400bb615`
- `KERNEL32!GetLastError` at `0x1400bb69b`
- `KERNEL32!DeviceIoControl` at `0x1400bb46b`
- `KERNEL32!DeviceIoControl` at `0x1400bb691`
- `KERNEL32!DeviceIoControl` at `0x1400bb46b`
- `KERNEL32!DeviceIoControl` at `0x1400bb691`
- `ole32!CoTaskMemAlloc` at `0x1400bb41f`
- `ole32!CoTaskMemAlloc` at `0x1400bb41f`
- `ole32!CoTaskMemFree` at `0x1400bb49f`
- `ole32!CoTaskMemFree` at `0x1400bb737`
- `ole32!CoTaskMemFree` at `0x1400bb49f`
- `ole32!CoTaskMemFree` at `0x1400bb737`

## pseudocode

```c
__int64 __fastcall BlbimgQueryVolumeSectorSize(const WCHAR *a1, _DWORD *a2, DWORD *a3)
{
  unsigned int *v6; // r14
  HANDLE FileW; // r12
  DWORD LastError; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // r15d
  unsigned int *v12; // rax
  DWORD v13; // eax
  void *v14; // rcx
  int v15; // eax
  HANDLE v16; // rsi
  DWORD v17; // eax
  DWORD v18; // eax
  size_t Size; // [rsp+40h] [rbp-49h] BYREF
  __int128 OutBuffer; // [rsp+48h] [rbp-41h] BYREF
  __int64 v22; // [rsp+58h] [rbp-31h]
  WCHAR FileName[8]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v24; // [rsp+70h] [rbp-19h]
  _OWORD v25[2]; // [rsp+80h] [rbp-9h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
  }
  v6 = 0;
  v22 = 0;
  *a2 = 0;
  v25[0] = 0;
  Size = 0;
  *a3 = 0;
  OutBuffer = 0;
  *(_OWORD *)FileName = 0;
  v24 = 0;
  *(_OWORD *)((char *)v25 + 12) = 0;
  FileW = CreateFileW(a1, 0, 3u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    *a3 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids,
        (_DWORD)a1,
        LastError);
    }
    v9 = 11;
    goto LABEL_57;
  }
  v10 = 32;
  v11 = 0;
  LODWORD(Size) = 32;
  v9 = 2;
  while ( 1 )
  {
    if ( v11 >= 2 )
      goto LABEL_29;
    v12 = (unsigned int *)CoTaskMemAlloc(v10);
    v6 = v12;
    if ( !v12 )
    {
      v9 = 3;
      goto LABEL_34;
    }
    memset_0(v12, 0, (unsigned int)Size);
    if ( DeviceIoControl(FileW, 0x560000u, 0, 0, v6, Size, (LPDWORD)&Size, 0) )
      break;
    v13 = GetLastError();
    if ( v13 != 234 )
    {
      *a3 = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids,
          (_DWORD)a1,
          v13);
      }
      v9 = 11;
      goto LABEL_34;
    }
    if ( v11 == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids,
          Size,
          (__int64)a1);
      }
      goto LABEL_34;
    }
    LODWORD(Size) = 24 * *v6 + 8;
    CoTaskMemFree(v6);
    v10 = Size;
    ++v11;
    v6 = 0;
  }
  v10 = Size;
LABEL_29:
  if ( !((v10 - 8) / 0x18) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids, a1);
    }
LABEL_34:
    v14 = FileW;
LABEL_56:
    CloseHandle(v14);
    goto LABEL_57;
  }
  CloseHandle(FileW);
  v15 = StringCchPrintfW(FileName, 0x1Eu, L"\\\\.\\PhysicalDrive%d", v6[2]);
  if ( v15 < 0 )
  {
    *a3 = (unsigned __int16)v15;
    goto LABEL_57;
  }
  v16 = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
  if ( v16 != (HANDLE)-1LL )
  {
    if ( DeviceIoControl(v16, 0x70000u, 0, 0, &OutBuffer, 0x18u, (LPDWORD)&Size + 1, 0) )
    {
      v9 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids,
          (unsigned int)FileName,
          SBYTE4(v22));
      }
      *a2 = HIDWORD(v22);
    }
    else
    {
      v18 = GetLastError();
      *a3 = v18;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          (unsigned int)WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids,
          (unsigned int)FileName,
          v18);
      }
      v9 = 11;
    }
    v14 = v16;
    goto LABEL_56;
  }
  v17 = GetLastError();
  *a3 = v17;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids,
      (unsigned int)FileName,
      v17);
  }
  v9 = 11;
LABEL_57:
  CoTaskMemFree(v6);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
  }
  return v9;
}

```

## disassembly

```asm
0x1400bb2f0  mov     [rsp-8+arg_18], rbx
0x1400bb2f5  push    rbp
0x1400bb2f6  push    rsi
0x1400bb2f7  push    rdi
0x1400bb2f8  push    r12
0x1400bb2fa  push    r13
0x1400bb2fc  push    r14
0x1400bb2fe  push    r15
0x1400bb300  lea     rbp, [rsp-27h]
0x1400bb305  sub     rsp, 0B0h
0x1400bb30c  mov     rax, cs:__security_cookie
0x1400bb313  xor     rax, rsp
0x1400bb316  mov     [rbp+57h+var_40], rax
0x1400bb31a  mov     rdi, r8
0x1400bb31d  mov     r13, rdx
0x1400bb320  mov     rsi, rcx
0x1400bb323  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb32a  lea     rbx, WPP_GLOBAL_Control
0x1400bb331  cmp     rcx, rbx
0x1400bb334  jz      short loc_1400BB357
0x1400bb336  test    byte ptr [rcx+1Ch], 4
0x1400bb33a  jz      short loc_1400BB357
0x1400bb33c  cmp     byte ptr [rcx+19h], 4
0x1400bb340  jb      short loc_1400BB357
0x1400bb342  mov     rcx, [rcx+10h]
0x1400bb346  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400bb34d  mov     edx, 24h ; '$'
0x1400bb352  call    WPP_SF_
0x1400bb357  xor     r14d, r14d
0x1400bb35a  xorps   xmm1, xmm1
0x1400bb35d  xor     eax, eax
0x1400bb35f  mov     [rsp+0E0h+hTemplateFile], r14; hTemplateFile
0x1400bb364  mov     [rbp+57h+var_88], rax
0x1400bb368  xorps   xmm0, xmm0
0x1400bb36b  mov     [r13+0], r14d
0x1400bb36f  xor     r9d, r9d; lpSecurityAttributes
0x1400bb372  lea     eax, [r14+3]
0x1400bb376  mov     [rsp+0E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1400bb37e  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x1400bb382  mov     r8d, eax; dwShareMode
0x1400bb385  mov     dword ptr [rbp+57h+Size], r14d
0x1400bb389  xor     edx, edx; dwDesiredAccess
0x1400bb38b  mov     dword ptr [rbp+57h+Size+4], r14d
0x1400bb38f  mov     rcx, rsi; lpFileName
0x1400bb392  mov     [rdi], r14d
0x1400bb395  movups  [rbp+57h+OutBuffer], xmm0
0x1400bb399  mov     [rsp+0E0h+dwCreationDisposition], eax; dwCreationDisposition
0x1400bb39d  movups  xmmword ptr [rbp+57h+FileName], xmm1
0x1400bb3a1  movups  [rbp+57h+var_70], xmm1
0x1400bb3a5  movups  xmmword ptr [rbp+57h+var_60+0Ch], xmm1
0x1400bb3a9  call    cs:__imp_CreateFileW
0x1400bb3af  mov     r12, rax
0x1400bb3b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400bb3b6  jnz     short loc_1400BB406
0x1400bb3b8  call    cs:__imp_GetLastError
0x1400bb3be  mov     [rdi], eax
0x1400bb3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb3c7  cmp     rcx, rbx
0x1400bb3ca  jz      short loc_1400BB3F5
0x1400bb3cc  test    byte ptr [rcx+1Ch], 4
0x1400bb3d0  jz      short loc_1400BB3F5
0x1400bb3d2  lea     ebx, [r14+2]
0x1400bb3d6  cmp     [rcx+19h], bl
0x1400bb3d9  jb      short loc_1400BB3F5
0x1400bb3db  mov     rcx, [rcx+10h]
0x1400bb3df  lea     edx, [rbx+23h]
0x1400bb3e2  mov     r9, rsi
0x1400bb3e5  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1400bb3e9  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400bb3f0  call    WPP_SF_Sd
0x1400bb3f5  mov     ebx, 0Bh
0x1400bb3fa  lea     rdi, WPP_GLOBAL_Control
0x1400bb401  jmp     loc_1400BB734
0x1400bb406  mov     eax, 20h ; ' '
0x1400bb40b  mov     r15d, r14d
0x1400bb40e  mov     dword ptr [rbp+57h+Size], eax
0x1400bb411  lea     ebx, [rax-1Eh]
0x1400bb414  cmp     r15d, ebx
0x1400bb417  jnb     loc_1400BB546
0x1400bb41d  mov     ecx, eax; cb
0x1400bb41f  call    cs:__imp_CoTaskMemAlloc
0x1400bb425  mov     r14, rax
0x1400bb428  test    rax, rax
0x1400bb42b  jz      loc_1400BB59F
0x1400bb431  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x1400bb435  xor     edx, edx; Val
0x1400bb437  mov     rcx, rax; void *
0x1400bb43a  call    memset_0
0x1400bb43f  lea     rax, [rbp+57h+Size]
0x1400bb443  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x1400bb44c  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1400bb451  xor     r9d, r9d; nInBufferSize
0x1400bb454  mov     eax, dword ptr [rbp+57h+Size]
0x1400bb457  xor     r8d, r8d; lpInBuffer
0x1400bb45a  mov     [rsp+0E0h+dwFlagsAndAttributes], eax; nOutBufferSize
0x1400bb45e  mov     edx, 560000h; dwIoControlCode
0x1400bb463  mov     rcx, r12; hDevice
0x1400bb466  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14; lpOutBuffer
0x1400bb46b  call    cs:__imp_DeviceIoControl
0x1400bb471  test    eax, eax
0x1400bb473  jnz     loc_1400BB543
0x1400bb479  call    cs:__imp_GetLastError
0x1400bb47f  cmp     eax, 0EAh
0x1400bb484  jnz     short loc_1400BB500
0x1400bb486  cmp     r15d, 1
0x1400bb48a  jz      short loc_1400BB4B3
0x1400bb48c  mov     eax, [r14]
0x1400bb48f  lea     ecx, [rax+rax*2]
0x1400bb492  lea     ecx, ds:8[rcx*8]
0x1400bb499  mov     dword ptr [rbp+57h+Size], ecx
0x1400bb49c  mov     rcx, r14; pv
0x1400bb49f  call    cs:__imp_CoTaskMemFree
0x1400bb4a5  mov     eax, dword ptr [rbp+57h+Size]
0x1400bb4a8  inc     r15d
0x1400bb4ab  xor     r14d, r14d
0x1400bb4ae  jmp     loc_1400BB414
0x1400bb4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb4ba  lea     rdi, WPP_GLOBAL_Control
0x1400bb4c1  cmp     rcx, rdi
0x1400bb4c4  jz      loc_1400BB597
0x1400bb4ca  test    byte ptr [rcx+1Ch], 4
0x1400bb4ce  jz      loc_1400BB597
0x1400bb4d4  cmp     [rcx+19h], bl
0x1400bb4d7  jb      loc_1400BB597
0x1400bb4dd  mov     r9d, dword ptr [rbp+57h+Size]
0x1400bb4e1  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400bb4e8  mov     rcx, [rcx+10h]
0x1400bb4ec  mov     edx, 27h ; '''
0x1400bb4f1  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi
0x1400bb4f6  call    WPP_SF_dS
0x1400bb4fb  jmp     loc_1400BB597
0x1400bb500  mov     [rdi], eax
0x1400bb502  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb509  lea     rdi, WPP_GLOBAL_Control
0x1400bb510  cmp     rcx, rdi
0x1400bb513  jz      short loc_1400BB53C
0x1400bb515  test    byte ptr [rcx+1Ch], 4
0x1400bb519  jz      short loc_1400BB53C
0x1400bb51b  cmp     [rcx+19h], bl
0x1400bb51e  jb      short loc_1400BB53C
0x1400bb520  mov     rcx, [rcx+10h]
0x1400bb524  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400bb52b  mov     edx, 26h ; '&'
0x1400bb530  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1400bb534  mov     r9, rsi
0x1400bb537  call    WPP_SF_Sd
0x1400bb53c  mov     ebx, 0Bh
0x1400bb541  jmp     short loc_1400BB597
0x1400bb543  mov     eax, dword ptr [rbp+57h+Size]
0x1400bb546  add     eax, 0FFFFFFF8h
0x1400bb549  mov     ecx, eax
0x1400bb54b  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400bb555  mul     rcx
0x1400bb558  shr     rdx, 4
0x1400bb55c  cmp     edx, 1
0x1400bb55f  jnb     short loc_1400BB5AD
0x1400bb561  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb568  lea     rdi, WPP_GLOBAL_Control
0x1400bb56f  cmp     rcx, rdi
0x1400bb572  jz      short loc_1400BB597
0x1400bb574  test    byte ptr [rcx+1Ch], 4
0x1400bb578  jz      short loc_1400BB597
0x1400bb57a  cmp     [rcx+19h], bl
0x1400bb57d  jb      short loc_1400BB597
0x1400bb57f  mov     rcx, [rcx+10h]
0x1400bb583  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400bb58a  mov     edx, 28h ; '('
0x1400bb58f  mov     r9, rsi
0x1400bb592  call    WPP_SF_S
0x1400bb597  mov     rcx, r12
0x1400bb59a  jmp     loc_1400BB72E
0x1400bb59f  mov     ebx, 3
0x1400bb5a4  lea     rdi, WPP_GLOBAL_Control
0x1400bb5ab  jmp     short loc_1400BB597
0x1400bb5ad  mov     rcx, r12; hObject
0x1400bb5b0  call    cs:__imp_CloseHandle
0x1400bb5b6  mov     r9d, [r14+8]
0x1400bb5ba  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x1400bb5c1  mov     edx, 1Eh; unsigned __int64
0x1400bb5c6  lea     rcx, [rbp+57h+FileName]; unsigned __int16 *
0x1400bb5ca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400bb5cf  test    eax, eax
0x1400bb5d1  jns     short loc_1400BB5DD
0x1400bb5d3  movzx   eax, ax
0x1400bb5d6  mov     [rdi], eax
0x1400bb5d8  jmp     loc_1400BB3FA
0x1400bb5dd  xor     r9d, r9d; lpSecurityAttributes
0x1400bb5e0  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x1400bb5e9  mov     [rsp+0E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1400bb5f1  lea     rcx, [rbp+57h+FileName]; lpFileName
0x1400bb5f5  mov     edx, 80000000h; dwDesiredAccess
0x1400bb5fa  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1400bb602  lea     r8d, [r9+3]; dwShareMode
0x1400bb606  call    cs:__imp_CreateFileW
0x1400bb60c  mov     rsi, rax
0x1400bb60f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400bb613  jnz     short loc_1400BB660
0x1400bb615  call    cs:__imp_GetLastError
0x1400bb61b  mov     [rdi], eax
0x1400bb61d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb624  lea     rdi, WPP_GLOBAL_Control
0x1400bb62b  cmp     rcx, rdi
0x1400bb62e  jz      short loc_1400BB656
0x1400bb630  test    byte ptr [rcx+1Ch], 4
0x1400bb634  jz      short loc_1400BB656
0x1400bb636  cmp     [rcx+19h], bl
0x1400bb639  jb      short loc_1400BB656
0x1400bb63b  mov     rcx, [rcx+10h]
0x1400bb63f  lea     edx, [rsi+2Ah]
0x1400bb642  lea     r9, [rbp+57h+FileName]
0x1400bb646  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1400bb64a  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400bb651  call    WPP_SF_Sd
0x1400bb656  mov     ebx, 0Bh
0x1400bb65b  jmp     loc_1400BB734
0x1400bb660  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x1400bb669  lea     rax, [rbp+57h+Size+4]
0x1400bb66d  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1400bb672  xor     r9d, r9d; nInBufferSize
0x1400bb675  lea     rax, [rbp+57h+OutBuffer]
0x1400bb679  mov     [rsp+0E0h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x1400bb681  xor     r8d, r8d; lpInBuffer
0x1400bb684  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; lpOutBuffer
0x1400bb689  mov     edx, 70000h; dwIoControlCode
0x1400bb68e  mov     rcx, rsi; hDevice
0x1400bb691  call    cs:__imp_DeviceIoControl
0x1400bb697  test    eax, eax
0x1400bb699  jnz     short loc_1400BB6E5
0x1400bb69b  call    cs:__imp_GetLastError
0x1400bb6a1  mov     [rdi], eax
0x1400bb6a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb6aa  lea     rdi, WPP_GLOBAL_Control
0x1400bb6b1  cmp     rcx, rdi
0x1400bb6b4  jz      short loc_1400BB6DE
0x1400bb6b6  test    byte ptr [rcx+1Ch], 4
0x1400bb6ba  jz      short loc_1400BB6DE
0x1400bb6bc  cmp     [rcx+19h], bl
0x1400bb6bf  jb      short loc_1400BB6DE
0x1400bb6c1  mov     rcx, [rcx+10h]
0x1400bb6c5  lea     r9, [rbp+57h+FileName]
0x1400bb6c9  mov     edx, 2Ah ; '*'
0x1400bb6ce  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1400bb6d2  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400bb6d9  call    WPP_SF_Sd
0x1400bb6de  mov     ebx, 0Bh
0x1400bb6e3  jmp     short loc_1400BB72B
0x1400bb6e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb6ec  lea     rdi, WPP_GLOBAL_Control
0x1400bb6f3  xor     ebx, ebx
0x1400bb6f5  cmp     rcx, rdi
0x1400bb6f8  jz      short loc_1400BB724
0x1400bb6fa  test    byte ptr [rcx+1Ch], 4
0x1400bb6fe  jz      short loc_1400BB724
0x1400bb700  cmp     byte ptr [rcx+19h], 4
0x1400bb704  jb      short loc_1400BB724
0x1400bb706  mov     eax, dword ptr [rbp+57h+var_88+4]
0x1400bb709  lea     edx, [rbx+2Bh]
0x1400bb70c  mov     rcx, [rcx+10h]
0x1400bb710  lea     r9, [rbp+57h+FileName]
0x1400bb714  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400bb71b  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1400bb71f  call    WPP_SF_Sd
0x1400bb724  mov     eax, dword ptr [rbp+57h+var_88+4]
0x1400bb727  mov     [r13+0], eax
0x1400bb72b  mov     rcx, rsi; hObject
0x1400bb72e  call    cs:__imp_CloseHandle
0x1400bb734  mov     rcx, r14; pv
0x1400bb737  call    cs:__imp_CoTaskMemFree
0x1400bb73d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb744  cmp     rcx, rdi
0x1400bb747  jz      short loc_1400BB76A
0x1400bb749  test    byte ptr [rcx+1Ch], 4
0x1400bb74d  jz      short loc_1400BB76A
0x1400bb74f  cmp     byte ptr [rcx+19h], 4
0x1400bb753  jb      short loc_1400BB76A
0x1400bb755  mov     rcx, [rcx+10h]
0x1400bb759  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400bb760  mov     edx, 2Ch ; ','
0x1400bb765  call    WPP_SF_
0x1400bb76a  mov     eax, ebx
0x1400bb76c  mov     rcx, [rbp+57h+var_40]
0x1400bb770  xor     rcx, rsp; StackCookie
0x1400bb773  call    __security_check_cookie
0x1400bb778  mov     rbx, [rsp+0E0h+arg_18]
0x1400bb780  add     rsp, 0B0h
0x1400bb787  pop     r15
0x1400bb789  pop     r14
0x1400bb78b  pop     r13
0x1400bb78d  pop     r12
0x1400bb78f  pop     rdi
0x1400bb790  pop     rsi
0x1400bb791  pop     rbp
0x1400bb792  retn
```
