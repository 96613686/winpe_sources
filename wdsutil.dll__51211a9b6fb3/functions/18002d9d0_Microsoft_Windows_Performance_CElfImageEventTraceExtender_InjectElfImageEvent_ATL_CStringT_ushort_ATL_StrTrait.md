# Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Microsoft::Windows::Performance::CryptographicHasher &,_LARGE_INTEGER,ulong)

- ea: `0x18002d9d0`
- end: `0x18002de8c`
- name: `?InjectElfImageEvent@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@EEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCryptographicHasher@234@T_LARGE_INTEGER@@K@Z`
- size: `1212`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d66`
- `0x18002d9d0`
- `0x18002eb60`
- `0x1800319a2`
- `0x1800319ae`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18002db3e`
- `msvcrt!wcscpy_s` at `0x18002db3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002dd46`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002dd8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002de40`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002de6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002dd46`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002dd8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002de40`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002de6a`
- `KERNEL32!CloseHandle` at `0x18002dd55`
- `KERNEL32!CloseHandle` at `0x18002de4f`
- `KERNEL32!CloseHandle` at `0x18002de79`
- `KERNEL32!CloseHandle` at `0x18002dd55`
- `KERNEL32!CloseHandle` at `0x18002de4f`
- `KERNEL32!CloseHandle` at `0x18002de79`
- `KERNEL32!ReadFile` at `0x18002da73`
- `KERNEL32!ReadFile` at `0x18002dc78`
- `KERNEL32!ReadFile` at `0x18002da73`
- `KERNEL32!ReadFile` at `0x18002dc78`
- `KERNEL32!GetFileSize` at `0x18002db55`
- `KERNEL32!GetFileSize` at `0x18002db55`
- `KERNEL32!SetFilePointer` at `0x18002dc48`
- `KERNEL32!SetFilePointer` at `0x18002dc48`
- `KERNEL32!CreateFileW` at `0x18002da2a`
- `KERNEL32!CreateFileW` at `0x18002da2a`
- `bcrypt!BCryptFinishHash` at `0x18002dd2b`
- `bcrypt!BCryptFinishHash` at `0x18002dd2b`
- `bcrypt!BCryptHashData` at `0x18002db8f`
- `bcrypt!BCryptHashData` at `0x18002dbb7`
- `bcrypt!BCryptHashData` at `0x18002dbdf`
- `bcrypt!BCryptHashData` at `0x18002dc06`
- `bcrypt!BCryptHashData` at `0x18002dce6`
- `bcrypt!BCryptHashData` at `0x18002db8f`
- `bcrypt!BCryptHashData` at `0x18002dbb7`
- `bcrypt!BCryptHashData` at `0x18002dbdf`
- `bcrypt!BCryptHashData` at `0x18002dc06`
- `bcrypt!BCryptHashData` at `0x18002dce6`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(
        __int64 a1,
        LPCWSTR *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  HANDLE FileW; // r14
  LPCWSTR v10; // rax
  int v11; // ecx
  _WORD *v12; // rdi
  unsigned __int64 v13; // rcx
  rsize_t v14; // rdx
  _QWORD *v15; // r15
  DWORD FileSize; // eax
  LONG v17; // r12d
  int v19; // ebx
  size_t v20; // r15
  __int64 v21; // rcx
  _BYTE v22[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int128 Buffer; // [rsp+60h] [rbp-A0h] BYREF
  UCHAR pbInput[16]; // [rsp+70h] [rbp-90h] BYREF
  UCHAR v28[16]; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+90h] [rbp-70h]
  __int16 v30; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[2]; // [rsp+A2h] [rbp-5Eh] BYREF
  int v32; // [rsp+A4h] [rbp-5Ch]
  __int64 v33; // [rsp+B0h] [rbp-50h]
  __int128 v34; // [rsp+B8h] [rbp-48h]
  _WORD *v35; // [rsp+E8h] [rbp-18h]
  int v36; // [rsp+F0h] [rbp-10h]
  int v37; // [rsp+F4h] [rbp-Ch]
  UCHAR v38[16]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v39; // [rsp+110h] [rbp+10h]

  FileW = CreateFileW(*a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 2147500037LL;
  NumberOfBytesRead = 0;
  v29 = 0;
  Buffer = 0;
  *(_OWORD *)pbInput = 0;
  *(_OWORD *)v28 = 0;
  if ( !ReadFile(FileW, &Buffer, 0x34u, &NumberOfBytesRead, 0)
    || NumberOfBytesRead != 52
    || memcmp_0(&Buffer, &qword_18003BC00, 4u)
    || WORD2(Buffer) != 257
    || BYTE6(Buffer) != 1
    || *(_WORD *)&v28[10] != 32 )
  {
    goto LABEL_34;
  }
  v10 = *a2;
  v22[0] = 0;
  v24 = 0;
  v11 = *((_DWORD *)v10 - 4) + 32 * *(unsigned __int16 *)&v28[12];
  v25 = 0;
  std::vector<char>::_Construct_n(&v24, (unsigned int)(2 * v11 + 94), v22);
  v12 = (_WORD *)v24;
  v13 = (unsigned __int64)*(unsigned __int16 *)&v28[12] << 6;
  v14 = (unsigned __int16)(*(*a2 - 8) + 1);
  v15 = (_QWORD *)(v24 + 28);
  *(_WORD *)(v24 + 26) = v14;
  wcscpy_s((wchar_t *)((char *)v15 + v13), v14, *a2);
  *(_DWORD *)v12 = 0;
  FileSize = GetFileSize(FileW, 0);
  *((_DWORD *)v12 + 1) = FileSize;
  if ( FileSize == -1 )
  {
LABEL_33:
    operator delete(v12);
    goto LABEL_34;
  }
  v12[12] = *(_WORD *)&v28[12];
  if ( *(_BYTE *)a3 )
  {
    if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), (PUCHAR)&Buffer, 0x10u, 0) < 0 )
      *(_BYTE *)a3 = 0;
    if ( *(_BYTE *)a3 )
    {
      if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), &pbInput[2], 2u, 0) < 0 )
        *(_BYTE *)a3 = 0;
      if ( *(_BYTE *)a3 )
      {
        if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), &pbInput[4], 4u, 0) < 0 )
          *(_BYTE *)a3 = 0;
        if ( *(_BYTE *)a3 && BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), &v28[4], 4u, 0) < 0 )
          *(_BYTE *)a3 = 0;
      }
    }
  }
  v17 = *(_DWORD *)&pbInput[12];
  if ( *(unsigned __int16 *)&v28[10] * *(unsigned __int16 *)&v28[12] )
  {
    while ( 1 )
    {
      *(_OWORD *)v38 = 0;
      v39 = 0;
      if ( SetFilePointer(FileW, v17, 0, 0) == -1
        || !ReadFile(FileW, v38, 0x20u, &NumberOfBytesRead, 0)
        || NumberOfBytesRead != 32 )
      {
        break;
      }
      *v15 = *(unsigned int *)v38;
      v15[2] = *(unsigned int *)&v38[4];
      v15[3] = *(unsigned int *)&v38[8];
      v15[4] = *(unsigned int *)&v38[12];
      v15[5] = (unsigned int)v39;
      v15[6] = DWORD1(v39);
      v15[1] = DWORD2(v39);
      v15[7] = HIDWORD(v39);
      v15 += 8;
      if ( *(_BYTE *)a3 && BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), v38, 0x20u, 0) < 0 )
        *(_BYTE *)a3 = 0;
      v17 += *(unsigned __int16 *)&v28[10];
      if ( v17 == *(_DWORD *)&pbInput[12] + *(unsigned __int16 *)&v28[10] * *(unsigned __int16 *)&v28[12] )
        goto LABEL_29;
    }
    if ( v12 )
      operator delete(v12);
    v19 = -2147467259;
    goto LABEL_46;
  }
LABEL_29:
  if ( !*(_BYTE *)a3 )
    goto LABEL_32;
  if ( BCryptFinishHash(*(BCRYPT_HASH_HANDLE *)(a3 + 16), *(PUCHAR *)(a3 + 32), *(_DWORD *)(a3 + 40), 0) < 0 )
  {
    *(_BYTE *)a3 = 0;
    goto LABEL_32;
  }
  if ( !*(_BYTE *)a3 )
    goto LABEL_32;
  v20 = 16;
  if ( *(_DWORD *)(a3 + 40) <= 0x10u )
    v20 = *(unsigned int *)(a3 + 40);
  memcpy_0(v12 + 4, *(const void **)(a3 + 32), v20);
  if ( v20 != 16 )
  {
LABEL_32:
    if ( v12 )
      goto LABEL_33;
LABEL_34:
    CloseHandle(FileW);
    return 2147500037LL;
  }
  memset_0(v31, 0, 0x56u);
  v21 = *(_QWORD *)(a1 + 16);
  v30 = 4;
  v33 = a4;
  v36 = DWORD2(v24) - (_DWORD)v12;
  v37 = a5;
  v34 = ElfImageGuid;
  v32 = 0;
  v35 = v12;
  v19 = (*(__int64 (__fastcall **)(__int64, __int16 *, _QWORD, _QWORD))(*(_QWORD *)v21 + 192LL))(v21, &v30, 0, 0);
  if ( v19 < 0 )
  {
    if ( v12 )
      operator delete(v12);
LABEL_46:
    CloseHandle(FileW);
    return (unsigned int)v19;
  }
  if ( v12 )
    operator delete(v12);
  CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x18002d9d0  push    rbp
0x18002d9d2  push    rbx
0x18002d9d3  push    rsi
0x18002d9d4  push    rdi
0x18002d9d5  push    r12
0x18002d9d7  push    r13
0x18002d9d9  push    r14
0x18002d9db  push    r15
0x18002d9dd  lea     rbp, [rsp-38h]
0x18002d9e2  sub     rsp, 138h
0x18002d9e9  mov     rax, cs:__security_cookie
0x18002d9f0  xor     rax, rsp
0x18002d9f3  mov     [rbp+70h+var_50], rax
0x18002d9f7  mov     r12, rdx
0x18002d9fa  xor     edi, edi
0x18002d9fc  mov     rbx, r9
0x18002d9ff  mov     [rsp+170h+hTemplateFile], rdi; hTemplateFile
0x18002da04  mov     rsi, r8
0x18002da07  mov     [rsp+170h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002da0f  mov     r13, rcx
0x18002da12  mov     [rsp+170h+dwCreationDisposition], 3; dwCreationDisposition
0x18002da1a  mov     rcx, [r12]; lpFileName
0x18002da1e  lea     r8d, [rdi+7]; dwShareMode
0x18002da22  xor     r9d, r9d; lpSecurityAttributes
0x18002da25  mov     edx, 80000000h; dwDesiredAccess
0x18002da2a  call    cs:__imp_CreateFileW
0x18002da31  nop     dword ptr [rax+rax+00h]
0x18002da36  mov     r14, rax
0x18002da39  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002da3d  jz      loc_18002DD61
0x18002da43  xorps   xmm0, xmm0
0x18002da46  mov     [rsp+170h+NumberOfBytesRead], edi
0x18002da4a  xor     eax, eax
0x18002da4c  mov     qword ptr [rsp+170h+dwCreationDisposition], rdi; lpOverlapped
0x18002da51  lea     r9, [rsp+170h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002da56  mov     [rbp+70h+var_E0], eax
0x18002da59  lea     r8d, [rdi+34h]; nNumberOfBytesToRead
0x18002da5d  mov     rcx, r14; hFile
0x18002da60  lea     rdx, [rsp+170h+Buffer]; lpBuffer
0x18002da65  movups  [rsp+170h+Buffer], xmm0
0x18002da6a  movups  xmmword ptr [rsp+170h+pbInput], xmm0
0x18002da6f  movups  xmmword ptr [rbp+70h+var_F0], xmm0
0x18002da73  call    cs:__imp_ReadFile
0x18002da7a  nop     dword ptr [rax+rax+00h]
0x18002da7f  test    eax, eax
0x18002da81  jz      loc_18002DD52
0x18002da87  cmp     [rsp+170h+NumberOfBytesRead], 34h ; '4'
0x18002da8c  jnz     loc_18002DD52
0x18002da92  lea     r8d, [rdi+4]; Size
0x18002da96  lea     rdx, qword_18003BC00; Buf2
0x18002da9d  lea     rcx, [rsp+170h+Buffer]; Buf1
0x18002daa2  call    memcmp_0
0x18002daa7  test    eax, eax
0x18002daa9  jnz     loc_18002DD52
0x18002daaf  cmp     byte ptr [rsp+170h+Buffer+4], 1
0x18002dab4  jnz     loc_18002DD52
0x18002daba  cmp     byte ptr [rsp+170h+Buffer+5], 1
0x18002dabf  jnz     loc_18002DD52
0x18002dac5  cmp     byte ptr [rsp+170h+Buffer+6], 1
0x18002daca  jnz     loc_18002DD52
0x18002dad0  lea     eax, [rdi+20h]
0x18002dad3  cmp     ax, word ptr [rbp+70h+var_F0+0Ah]
0x18002dad7  jnz     loc_18002DD52
0x18002dadd  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x18002dae1  lea     r8, [rsp+170h+var_130]
0x18002dae6  mov     rax, [r12]
0x18002daea  xorps   xmm0, xmm0
0x18002daed  shl     ecx, 5
0x18002daf0  mov     [rsp+170h+var_130], dil
0x18002daf5  movdqu  [rsp+170h+var_128], xmm0
0x18002dafb  add     ecx, [rax-10h]
0x18002dafe  mov     [rsp+170h+var_118], rdi
0x18002db03  lea     edx, ds:5Eh[rcx*2]
0x18002db0a  lea     rcx, [rsp+170h+var_128]
0x18002db0f  call    ?_Construct_n@?$vector@DV?$allocator@D@std@@@std@@QEAAX_KPEBD@Z; std::vector<char>::_Construct_n(unsigned __int64,char const *)
0x18002db14  mov     rax, [r12]
0x18002db18  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x18002db1c  mov     rdi, qword ptr [rsp+170h+var_128]
0x18002db21  shl     rcx, 6
0x18002db25  movzx   edx, word ptr [rax-10h]
0x18002db29  inc     dx
0x18002db2c  movzx   edx, dx; SizeInWords
0x18002db2f  lea     r15, [rdi+1Ch]
0x18002db33  mov     [rdi+1Ah], dx
0x18002db37  add     rcx, r15; Destination
0x18002db3a  mov     r8, [r12]; Source
0x18002db3e  call    cs:__imp_wcscpy_s
0x18002db45  nop     dword ptr [rax+rax+00h]
0x18002db4a  xor     r12d, r12d
0x18002db4d  xor     edx, edx; lpFileSizeHigh
0x18002db4f  mov     rcx, r14; hFile
0x18002db52  mov     [rdi], r12d
0x18002db55  call    cs:__imp_GetFileSize
0x18002db5c  nop     dword ptr [rax+rax+00h]
0x18002db61  mov     [rdi+4], eax
0x18002db64  cmp     eax, 0FFFFFFFFh
0x18002db67  jz      loc_18002DD43
0x18002db6d  movzx   eax, word ptr [rbp+70h+var_F0+0Ch]
0x18002db71  mov     [rdi+18h], ax
0x18002db75  cmp     [rsi], r12b
0x18002db78  jz      loc_18002DC19
0x18002db7e  mov     rcx, [rsi+10h]; hHash
0x18002db82  lea     r8d, [r12+10h]; cbInput
0x18002db87  xor     r9d, r9d; dwFlags
0x18002db8a  lea     rdx, [rsp+170h+Buffer]; pbInput
0x18002db8f  call    cs:__imp_BCryptHashData
0x18002db96  nop     dword ptr [rax+rax+00h]
0x18002db9b  test    eax, eax
0x18002db9d  jns     short loc_18002DBA2
0x18002db9f  mov     [rsi], r12b
0x18002dba2  cmp     [rsi], r12b
0x18002dba5  jz      short loc_18002DC19
0x18002dba7  mov     rcx, [rsi+10h]; hHash
0x18002dbab  lea     rdx, [rsp+170h+pbInput+2]; pbInput
0x18002dbb0  xor     r9d, r9d; dwFlags
0x18002dbb3  lea     r8d, [r9+2]; cbInput
0x18002dbb7  call    cs:__imp_BCryptHashData
0x18002dbbe  nop     dword ptr [rax+rax+00h]
0x18002dbc3  test    eax, eax
0x18002dbc5  jns     short loc_18002DBCA
0x18002dbc7  mov     [rsi], r12b
0x18002dbca  cmp     [rsi], r12b
0x18002dbcd  jz      short loc_18002DC19
0x18002dbcf  mov     rcx, [rsi+10h]; hHash
0x18002dbd3  lea     rdx, [rsp+170h+pbInput+4]; pbInput
0x18002dbd8  xor     r9d, r9d; dwFlags
0x18002dbdb  lea     r8d, [r9+4]; cbInput
0x18002dbdf  call    cs:__imp_BCryptHashData
0x18002dbe6  nop     dword ptr [rax+rax+00h]
0x18002dbeb  test    eax, eax
0x18002dbed  jns     short loc_18002DBF2
0x18002dbef  mov     [rsi], r12b
0x18002dbf2  cmp     [rsi], r12b
0x18002dbf5  jz      short loc_18002DC19
0x18002dbf7  mov     rcx, [rsi+10h]; hHash
0x18002dbfb  lea     rdx, [rbp+70h+var_F0+4]; pbInput
0x18002dbff  xor     r9d, r9d; dwFlags
0x18002dc02  lea     r8d, [r9+4]; cbInput
0x18002dc06  call    cs:__imp_BCryptHashData
0x18002dc0d  nop     dword ptr [rax+rax+00h]
0x18002dc12  test    eax, eax
0x18002dc14  jns     short loc_18002DC19
0x18002dc16  mov     [rsi], r12b
0x18002dc19  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x18002dc1d  movzx   eax, word ptr [rbp+70h+var_F0+0Ah]
0x18002dc21  mov     r12d, dword ptr [rsp+170h+pbInput+0Ch]
0x18002dc26  imul    ecx, eax
0x18002dc29  test    ecx, ecx
0x18002dc2b  jz      loc_18002DD14
0x18002dc31  xorps   xmm0, xmm0
0x18002dc34  xor     r9d, r9d; dwMoveMethod
0x18002dc37  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002dc3a  mov     edx, r12d; lDistanceToMove
0x18002dc3d  mov     rcx, r14; hFile
0x18002dc40  movups  xmmword ptr [rbp+70h+var_70], xmm0
0x18002dc44  movups  [rbp+70h+var_60], xmm0
0x18002dc48  call    cs:__imp_SetFilePointer
0x18002dc4f  nop     dword ptr [rax+rax+00h]
0x18002dc54  cmp     eax, 0FFFFFFFFh
0x18002dc57  jz      loc_18002DD87
0x18002dc5d  lea     r9, [rsp+170h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002dc62  mov     qword ptr [rsp+170h+dwCreationDisposition], 0; lpOverlapped
0x18002dc6b  mov     r8d, 20h ; ' '; nNumberOfBytesToRead
0x18002dc71  lea     rdx, [rbp+70h+var_70]; lpBuffer
0x18002dc75  mov     rcx, r14; hFile
0x18002dc78  call    cs:__imp_ReadFile
0x18002dc7f  nop     dword ptr [rax+rax+00h]
0x18002dc84  test    eax, eax
0x18002dc86  jz      loc_18002DD87
0x18002dc8c  cmp     [rsp+170h+NumberOfBytesRead], 20h ; ' '
0x18002dc91  jnz     loc_18002DD87
0x18002dc97  mov     eax, dword ptr [rbp+70h+var_70]
0x18002dc9a  mov     [r15], rax
0x18002dc9d  mov     eax, dword ptr [rbp+70h+var_70+4]
0x18002dca0  mov     [r15+10h], rax
0x18002dca4  mov     eax, dword ptr [rbp+70h+var_70+8]
0x18002dca7  mov     [r15+18h], rax
0x18002dcab  mov     eax, dword ptr [rbp+70h+var_70+0Ch]
0x18002dcae  mov     [r15+20h], rax
0x18002dcb2  mov     eax, dword ptr [rbp+70h+var_60]
0x18002dcb5  mov     [r15+28h], rax
0x18002dcb9  mov     eax, dword ptr [rbp+70h+var_60+4]
0x18002dcbc  mov     [r15+30h], rax
0x18002dcc0  mov     eax, dword ptr [rbp+70h+var_60+8]
0x18002dcc3  mov     [r15+8], rax
0x18002dcc7  mov     eax, dword ptr [rbp+70h+var_60+0Ch]
0x18002dcca  mov     [r15+38h], rax
0x18002dcce  add     r15, 40h ; '@'
0x18002dcd2  cmp     byte ptr [rsi], 0
0x18002dcd5  jz      short loc_18002DCF9
0x18002dcd7  mov     rcx, [rsi+10h]; hHash
0x18002dcdb  lea     rdx, [rbp+70h+var_70]; pbInput
0x18002dcdf  xor     r9d, r9d; dwFlags
0x18002dce2  lea     r8d, [r9+20h]; cbInput
0x18002dce6  call    cs:__imp_BCryptHashData
0x18002dced  nop     dword ptr [rax+rax+00h]
0x18002dcf2  test    eax, eax
0x18002dcf4  jns     short loc_18002DCF9
0x18002dcf6  mov     byte ptr [rsi], 0
0x18002dcf9  movzx   eax, word ptr [rbp+70h+var_F0+0Ah]
0x18002dcfd  movzx   ecx, word ptr [rbp+70h+var_F0+0Ch]
0x18002dd01  add     r12d, eax
0x18002dd04  imul    ecx, eax
0x18002dd07  add     ecx, dword ptr [rsp+170h+pbInput+0Ch]
0x18002dd0b  cmp     r12d, ecx
0x18002dd0e  jnz     loc_18002DC31
0x18002dd14  xor     r12d, r12d
0x18002dd17  cmp     [rsi], r12b
0x18002dd1a  jz      short loc_18002DD3E
0x18002dd1c  mov     r8d, [rsi+28h]; cbOutput
0x18002dd20  xor     r9d, r9d; dwFlags
0x18002dd23  mov     rdx, [rsi+20h]; pbOutput
0x18002dd27  mov     rcx, [rsi+10h]; hHash
0x18002dd2b  call    cs:__imp_BCryptFinishHash
0x18002dd32  nop     dword ptr [rax+rax+00h]
0x18002dd37  test    eax, eax
0x18002dd39  jns     short loc_18002DDA5
0x18002dd3b  mov     [rsi], r12b
0x18002dd3e  test    rdi, rdi
0x18002dd41  jz      short loc_18002DD52
0x18002dd43  mov     rcx, rdi
0x18002dd46  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002dd4d  nop     dword ptr [rax+rax+00h]
0x18002dd52  mov     rcx, r14; hObject
0x18002dd55  call    cs:__imp_CloseHandle
0x18002dd5c  nop     dword ptr [rax+rax+00h]
0x18002dd61  mov     eax, 80004005h
0x18002dd66  mov     rcx, [rbp+70h+var_50]
0x18002dd6a  xor     rcx, rsp; StackCookie
0x18002dd6d  call    __security_check_cookie
0x18002dd72  add     rsp, 138h
0x18002dd79  pop     r15
0x18002dd7b  pop     r14
0x18002dd7d  pop     r13
0x18002dd7f  pop     r12
0x18002dd81  pop     rdi
0x18002dd82  pop     rsi
0x18002dd83  pop     rbx
0x18002dd84  pop     rbp
0x18002dd85  retn
0x18002dd87  test    rdi, rdi
0x18002dd8a  jz      short loc_18002DD9B
0x18002dd8c  mov     rcx, rdi
0x18002dd8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002dd96  nop     dword ptr [rax+rax+00h]
0x18002dd9b  mov     ebx, 80004005h
0x18002dda0  jmp     loc_18002DE4C
0x18002dda5  cmp     [rsi], r12b
0x18002dda8  jz      short loc_18002DD3E
0x18002ddaa  cmp     dword ptr [rsi+28h], 10h
0x18002ddae  mov     r15d, 10h
0x18002ddb4  ja      short loc_18002DDBA
0x18002ddb6  mov     r15d, [rsi+28h]
0x18002ddba  mov     rdx, [rsi+20h]; Src
0x18002ddbe  lea     rcx, [rdi+8]; void *
0x18002ddc2  mov     r8, r15; Size
0x18002ddc5  call    memcpy_0
0x18002ddca  cmp     r15, 10h
0x18002ddce  jnz     loc_18002DD3E
0x18002ddd4  xor     edx, edx; Val
0x18002ddd6  lea     r8d, [r15+46h]; Size
0x18002ddda  lea     rcx, [rbp+70h+var_CE]; void *
0x18002ddde  call    memset_0
0x18002dde3  movups  xmm0, cs:ElfImageGuid
0x18002ddea  mov     rcx, [r13+10h]
0x18002ddee  lea     eax, [r15-0Ch]
0x18002ddf2  mov     [rbp+70h+var_D0], ax
0x18002ddf6  lea     rdx, [rbp+70h+var_D0]
0x18002ddfa  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18002ddfe  xor     r9d, r9d
0x18002de01  sub     eax, edi
0x18002de03  mov     [rbp+70h+var_C0], rbx
0x18002de07  mov     [rbp+70h+var_80], eax
0x18002de0a  xor     r8d, r8d
0x18002de0d  mov     eax, [rbp+70h+arg_20]
0x18002de13  mov     [rbp+70h+var_7C], eax
0x18002de16  movdqu  [rbp+70h+var_B8], xmm0
0x18002de1b  mov     [rbp+70h+var_CC], r12d
0x18002de1f  mov     [rbp+70h+var_88], rdi
0x18002de23  mov     rax, [rcx]
0x18002de26  mov     rax, [rax+0C0h]
0x18002de2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de32  mov     ebx, eax
0x18002de34  test    eax, eax
0x18002de36  jns     short loc_18002DE62
0x18002de38  test    rdi, rdi
0x18002de3b  jz      short loc_18002DE4C
0x18002de3d  mov     rcx, rdi
0x18002de40  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002de47  nop     dword ptr [rax+rax+00h]
0x18002de4c  mov     rcx, r14; hObject
0x18002de4f  call    cs:__imp_CloseHandle
0x18002de56  nop     dword ptr [rax+rax+00h]
0x18002de5b  mov     eax, ebx
0x18002de5d  jmp     loc_18002DD66
0x18002de62  test    rdi, rdi
0x18002de65  jz      short loc_18002DE76
0x18002de67  mov     rcx, rdi
0x18002de6a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002de71  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
