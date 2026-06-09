# BlbGetPartitionOffsetForVolume(ushort const *,__int64 *)

- ea: `0x140121620`
- end: `0x140121889`
- name: `?BlbGetPartitionOffsetForVolume@@YAJPEBGPEA_J@Z`
- size: `617`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x140030644`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x140121620`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1401216da`
- `KERNEL32!CreateFileW` at `0x1401216da`
- `KERNEL32!CloseHandle` at `0x140121841`
- `KERNEL32!CloseHandle` at `0x140121841`
- `KERNEL32!GetLastError` at `0x1401216e9`
- `KERNEL32!GetLastError` at `0x14012179e`
- `KERNEL32!GetLastError` at `0x1401216e9`
- `KERNEL32!GetLastError` at `0x14012179e`
- `KERNEL32!DeviceIoControl` at `0x140121794`
- `KERNEL32!DeviceIoControl` at `0x140121794`
- `ole32!CoTaskMemAlloc` at `0x140121758`
- `ole32!CoTaskMemAlloc` at `0x140121758`
- `ole32!CoTaskMemFree` at `0x140121750`
- `ole32!CoTaskMemFree` at `0x14012182c`
- `ole32!CoTaskMemFree` at `0x140121750`
- `ole32!CoTaskMemFree` at `0x14012182c`

## pseudocode

```c
__int64 __fastcall BlbGetPartitionOffsetForVolume(LPCWSTR lpFileName, __int64 *a2)
{
  HANDLE FileW; // rbp
  signed int v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  _QWORD *v8; // rdi
  DWORD i; // ebx
  signed int LastError; // eax
  DWORD BytesReturned; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids);
  }
  if ( !lpFileName )
    BlbAssert("base\\stor\\blb\\wsbutil\\wsbvolumeutils.cpp", 0x753u, "wszVolumeName");
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\wsbutil\\wsbvolumeutils.cpp", 0x754u, "pPartitionOffset");
  BytesReturned = 0;
  *a2 = 0;
  FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v8 = 0;
    for ( i = 32; ; i += 32 )
    {
      if ( v8 )
        CoTaskMemFree(v8);
      v8 = CoTaskMemAlloc(i);
      if ( !v8 )
        break;
      if ( DeviceIoControl(FileW, 0x560000u, 0, 0, v8, i, &BytesReturned, 0) )
      {
        v6 = 0;
        if ( v8 == (_QWORD *)-8LL )
          BlbAssert("base\\stor\\blb\\wsbutil\\wsbvolumeutils.cpp", 0x79Au, "pDiskExtent");
        *a2 = v8[2];
        goto LABEL_34;
      }
      LastError = GetLastError();
      if ( LastError != 234 && LastError != 122 )
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        else
          v6 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids);
        }
LABEL_34:
        CoTaskMemFree(v8);
        goto LABEL_36;
      }
    }
    v6 = -2147024882;
LABEL_36:
    if ( FileW )
      CloseHandle(FileW);
    goto LABEL_38;
  }
  v5 = GetLastError();
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_39:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
        WPP_SF_(v7[2], 99, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids);
      return v6;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      (unsigned int)WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids,
      (_DWORD)lpFileName,
      v6);
LABEL_38:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_39;
  }
  return v6;
}

```

## disassembly

```asm
0x140121620  mov     [rsp+arg_8], rbx
0x140121625  mov     [rsp+arg_10], rbp
0x14012162a  push    rsi
0x14012162b  push    rdi
0x14012162c  push    r14
0x14012162e  sub     rsp, 40h
0x140121632  mov     r14, rdx
0x140121635  mov     rdi, rcx
0x140121638  mov     rcx, cs:WPP_GLOBAL_Control
0x14012163f  lea     rsi, WPP_GLOBAL_Control
0x140121646  cmp     rcx, rsi
0x140121649  jz      short loc_14012166C
0x14012164b  test    byte ptr [rcx+1Ch], 1
0x14012164f  jz      short loc_14012166C
0x140121651  cmp     byte ptr [rcx+19h], 4
0x140121655  jb      short loc_14012166C
0x140121657  mov     rcx, [rcx+10h]
0x14012165b  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x140121662  mov     edx, 60h ; '`'
0x140121667  call    WPP_SF_
0x14012166c  test    rdi, rdi
0x14012166f  jnz     short loc_140121689
0x140121671  lea     r8, aWszvolumename; "wszVolumeName"
0x140121678  mov     edx, 753h; unsigned int
0x14012167d  lea     rcx, aBaseStorBlbWsb; "base\\stor\\blb\\wsbutil\\wsbvolumeutil"...
0x140121684  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140121689  test    r14, r14
0x14012168c  jnz     short loc_1401216A6
0x14012168e  lea     r8, aPpartitionoffs; "pPartitionOffset"
0x140121695  mov     edx, 754h; unsigned int
0x14012169a  lea     rcx, aBaseStorBlbWsb; "base\\stor\\blb\\wsbutil\\wsbvolumeutil"...
0x1401216a1  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1401216a6  xor     r9d, r9d; lpSecurityAttributes
0x1401216a9  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1401216b2  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1401216ba  xor     edx, edx; dwDesiredAccess
0x1401216bc  mov     rcx, rdi; lpFileName
0x1401216bf  mov     [rsp+58h+BytesReturned], 0
0x1401216c7  mov     qword ptr [r14], 0
0x1401216ce  lea     r8d, [r9+7]; dwShareMode
0x1401216d2  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1401216da  call    cs:__imp_CreateFileW
0x1401216e0  mov     rbp, rax
0x1401216e3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401216e7  jnz     short loc_140121743
0x1401216e9  call    cs:__imp_GetLastError
0x1401216ef  mov     ebx, eax
0x1401216f1  test    eax, eax
0x1401216f3  jle     short loc_1401216FE
0x1401216f5  movzx   ebx, ax
0x1401216f8  or      ebx, 80070000h
0x1401216fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140121705  cmp     rcx, rsi
0x140121708  jz      loc_140121874
0x14012170e  test    byte ptr [rcx+1Ch], 4
0x140121712  jz      loc_14012184E
0x140121718  cmp     byte ptr [rcx+19h], 2
0x14012171c  jb      loc_14012184E
0x140121722  mov     rcx, [rcx+10h]
0x140121726  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x14012172d  mov     edx, 61h ; 'a'
0x140121732  mov     [rsp+58h+dwCreationDisposition], ebx
0x140121736  mov     r9, rdi
0x140121739  call    WPP_SF_Sd
0x14012173e  jmp     loc_140121847
0x140121743  xor     edi, edi
0x140121745  lea     ebx, [rdi+20h]
0x140121748  test    rdi, rdi
0x14012174b  jz      short loc_140121756
0x14012174d  mov     rcx, rdi; pv
0x140121750  call    cs:__imp_CoTaskMemFree
0x140121756  mov     ecx, ebx; cb
0x140121758  call    cs:__imp_CoTaskMemAlloc
0x14012175e  mov     rdi, rax
0x140121761  test    rax, rax
0x140121764  jz      loc_140121834
0x14012176a  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x140121773  lea     rax, [rsp+58h+BytesReturned]
0x140121778  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x14012177d  xor     r9d, r9d; nInBufferSize
0x140121780  mov     [rsp+58h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x140121784  xor     r8d, r8d; lpInBuffer
0x140121787  mov     edx, 560000h; dwIoControlCode
0x14012178c  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; lpOutBuffer
0x140121791  mov     rcx, rbp; hDevice
0x140121794  call    cs:__imp_DeviceIoControl
0x14012179a  test    eax, eax
0x14012179c  jnz     short loc_1401217F8
0x14012179e  call    cs:__imp_GetLastError
0x1401217a4  cmp     eax, 0EAh
0x1401217a9  jz      short loc_1401217B0
0x1401217ab  cmp     eax, 7Ah ; 'z'
0x1401217ae  jnz     short loc_1401217B5
0x1401217b0  add     ebx, 20h ; ' '
0x1401217b3  jmp     short loc_140121748
0x1401217b5  test    eax, eax
0x1401217b7  jg      short loc_1401217BD
0x1401217b9  mov     ebx, eax
0x1401217bb  jmp     short loc_1401217C6
0x1401217bd  movzx   ebx, ax
0x1401217c0  or      ebx, 80070000h
0x1401217c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1401217cd  cmp     rcx, rsi
0x1401217d0  jz      short loc_140121829
0x1401217d2  test    byte ptr [rcx+1Ch], 4
0x1401217d6  jz      short loc_140121829
0x1401217d8  cmp     byte ptr [rcx+19h], 2
0x1401217dc  jb      short loc_140121829
0x1401217de  mov     rcx, [rcx+10h]
0x1401217e2  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x1401217e9  mov     edx, 62h ; 'b'
0x1401217ee  mov     r9d, eax
0x1401217f1  call    WPP_SF_d
0x1401217f6  jmp     short loc_140121829
0x1401217f8  xor     ebx, ebx
0x1401217fa  lea     rsi, [rdi+8]
0x1401217fe  test    rsi, rsi
0x140121801  jnz     short loc_14012181B
0x140121803  lea     r8, aPdiskextent; "pDiskExtent"
0x14012180a  mov     edx, 79Ah; unsigned int
0x14012180f  lea     rcx, aBaseStorBlbWsb; "base\\stor\\blb\\wsbutil\\wsbvolumeutil"...
0x140121816  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14012181b  mov     rax, [rsi+8]
0x14012181f  lea     rsi, WPP_GLOBAL_Control
0x140121826  mov     [r14], rax
0x140121829  mov     rcx, rdi; pv
0x14012182c  call    cs:__imp_CoTaskMemFree
0x140121832  jmp     short loc_140121839
0x140121834  mov     ebx, 8007000Eh
0x140121839  test    rbp, rbp
0x14012183c  jz      short loc_140121847
0x14012183e  mov     rcx, rbp; hObject
0x140121841  call    cs:__imp_CloseHandle
0x140121847  mov     rcx, cs:WPP_GLOBAL_Control
0x14012184e  cmp     rcx, rsi
0x140121851  jz      short loc_140121874
0x140121853  test    byte ptr [rcx+1Ch], 1
0x140121857  jz      short loc_140121874
0x140121859  cmp     byte ptr [rcx+19h], 4
0x14012185d  jb      short loc_140121874
0x14012185f  mov     rcx, [rcx+10h]
0x140121863  lea     r8, WPP_89d076d36fbc37c91d4ec66e793d70d4_Traceguids
0x14012186a  mov     edx, 63h ; 'c'
0x14012186f  call    WPP_SF_
0x140121874  mov     rbp, [rsp+58h+arg_10]
0x140121879  mov     eax, ebx
0x14012187b  mov     rbx, [rsp+58h+arg_8]
0x140121880  add     rsp, 40h
0x140121884  pop     r14
0x140121886  pop     rdi
0x140121887  pop     rsi
0x140121888  retn
```
