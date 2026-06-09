# RotatingBuffer::CreateRB(ulong,ulong,ulong,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,int,int,ulong)

- ea: `0x1400796f8`
- end: `0x140079a29`
- name: `?CreateRB@RotatingBuffer@@QEAAJKKKAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@HHK@Z`
- size: `817`
- prototype: `__int64 __usercall@<rax>(RotatingBuffer *this@<rcx>, __int64, int, int, DWORD flProtect)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140076410`
- `0x140078e90`

## callees

- `0x140003560`
- `0x14000a8d8`
- `0x140016954`
- `0x140018968`
- `0x140056f94`
- `0x1400796f8`
- `0x140079aac`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400797f3`
- `KERNEL32!GetTickCount` at `0x1400797f3`
- `KERNEL32!ReadFile` at `0x1400798fa`
- `KERNEL32!ReadFile` at `0x1400798fa`
- `KERNEL32!GetFileSizeEx` at `0x140079882`
- `KERNEL32!GetFileSizeEx` at `0x140079882`
- `KERNEL32!SetFilePointer` at `0x140079926`
- `KERNEL32!SetFilePointer` at `0x140079926`
- `KERNEL32!CloseHandle` at `0x1400799be`
- `KERNEL32!CloseHandle` at `0x1400799be`
- `KERNEL32!GetLastError` at `0x140079768`
- `KERNEL32!GetLastError` at `0x14007984d`
- `KERNEL32!GetLastError` at `0x14007988c`
- `KERNEL32!GetLastError` at `0x140079934`
- `KERNEL32!GetLastError` at `0x140079956`
- `KERNEL32!GetLastError` at `0x140079768`
- `KERNEL32!GetLastError` at `0x14007984d`
- `KERNEL32!GetLastError` at `0x14007988c`
- `KERNEL32!GetLastError` at `0x140079934`
- `KERNEL32!GetLastError` at `0x140079956`
- `KERNEL32!VirtualAlloc` at `0x140079757`
- `KERNEL32!VirtualAlloc` at `0x140079757`
- `KERNEL32!VirtualFree` at `0x1400799dd`
- `KERNEL32!VirtualFree` at `0x1400799dd`
- `msvcrt!srand` at `0x1400797fb`
- `msvcrt!srand` at `0x1400797fb`
- `msvcrt!rand` at `0x14007980b`
- `msvcrt!rand` at `0x14007980b`

## pseudocode

```c
__int64 __fastcall RotatingBuffer::CreateRB(
        RotatingBuffer *this,
        unsigned int a2,
        unsigned int a3,
        int a4,
        _QWORD **a5,
        int a6,
        int a7,
        DWORD flProtect)
{
  __int64 v8; // r14
  bool v9; // zf
  unsigned int v11; // ebp
  LPVOID v14; // rax
  signed int v15; // eax
  unsigned int v16; // edi
  _DWORD *v17; // r15
  unsigned int *v18; // r12
  unsigned int *v19; // r13
  int v20; // eax
  __int64 v21; // rdx
  DWORD TickCount; // eax
  __int64 i; // rbx
  void **v24; // r9
  signed int LastError; // eax
  signed int v26; // eax
  DWORD LowPart; // ebx
  DWORD v28; // eax
  DWORD v29; // r15d
  signed int v30; // eax
  signed int v31; // eax
  unsigned int j; // ebx
  void *v33; // rcx
  HANDLE hFile; // [rsp+30h] [rbp-58h] BYREF
  DWORD NumberOfBytesRead; // [rsp+38h] [rbp-50h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-48h] BYREF

  v8 = -1;
  v9 = *((_QWORD *)this + 3) == 0;
  v11 = a2;
  hFile = (HANDLE)-1LL;
  if ( !v9 )
    return 5;
  if ( a4 + a2 < a2 )
    return 2147942414LL;
  *((_DWORD *)this + 4) = flProtect;
  v14 = VirtualAlloc(0, a4 + a2, 0x1000u, flProtect);
  *((_QWORD *)this + 3) = v14;
  if ( v14 )
  {
    *(_QWORD *)((char *)this + 36) = 0;
    *(_DWORD *)this = v11;
    v20 = v11 / a3;
    v18 = (unsigned int *)((char *)this + 8);
    *((_DWORD *)this + 2) = a3;
    v19 = (unsigned int *)((char *)this + 32);
    *((_DWORD *)this + 8) = 0;
    v17 = (_DWORD *)((char *)this + 4);
    v16 = 0;
    *((_DWORD *)this + 1) = v20;
    *((_DWORD *)this + 3) = 1;
    if ( a7 )
      v11 = v20;
    mlib::m_traits<unsigned short>::CStrlen(L"SIMPLERANDOMDATA", 0x10000);
    if ( (unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
                         a5,
                         v21,
                         **a5,
                         L"SIMPLERANDOMDATA") )
    {
      if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(a5) )
      {
        if ( mlib::MCreateFile((LPCWSTR)(*a5)[3], (const unsigned __int16 *)5, &hFile, v24) )
        {
          LastError = GetLastError();
          v16 = LastError;
          if ( LastError > 0 )
            v16 = (unsigned __int16)LastError | 0x80070000;
          v8 = (__int64)hFile;
          goto LABEL_45;
        }
        v8 = (__int64)hFile;
        FileSize.QuadPart = 0;
        NumberOfBytesRead = 0;
        if ( !GetFileSizeEx(hFile, &FileSize) )
        {
          v26 = GetLastError();
          v16 = v26;
          if ( v26 > 0 )
            v16 = (unsigned __int16)v26 | 0x80070000;
          goto LABEL_45;
        }
        LowPart = FileSize.LowPart;
        if ( !FileSize.QuadPart )
        {
          v16 = -2147221502;
LABEL_45:
          if ( v8 != -1 )
            CloseHandle((HANDLE)v8);
          goto LABEL_47;
        }
        v28 = 0;
        LODWORD(hFile) = 0;
        if ( FileSize.QuadPart > 0xFFFFFFFFLL )
          LowPart = -1;
        while ( v11 )
        {
          v29 = v11;
          if ( v11 >= LowPart )
            v29 = LowPart;
          if ( !ReadFile((HANDLE)v8, (LPVOID)(*((_QWORD *)this + 3) + v28), v29, &NumberOfBytesRead, 0) )
          {
            v31 = GetLastError();
            v16 = v31;
            if ( v31 > 0 )
              v16 = (unsigned __int16)v31 | 0x80070000;
            goto LABEL_39;
          }
          if ( v29 != NumberOfBytesRead )
          {
            v16 = -2147221501;
LABEL_39:
            v17 = (_DWORD *)((char *)this + 4);
            goto LABEL_45;
          }
          v28 = v29 + (_DWORD)hFile;
          LODWORD(hFile) = v29 + (_DWORD)hFile;
          v11 -= v29;
          if ( v11 )
          {
            v9 = SetFilePointer((HANDLE)v8, 0, 0, 0) == 0;
            v28 = (unsigned int)hFile;
            if ( !v9 )
            {
              v30 = GetLastError();
              v16 = v30;
              if ( v30 > 0 )
                v16 = (unsigned __int16)v30 | 0x80070000;
              v28 = (unsigned int)hFile;
            }
          }
        }
        v17 = (_DWORD *)((char *)this + 4);
      }
    }
    else
    {
      TickCount = GetTickCount();
      srand(TickCount);
      for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
        *(_BYTE *)(i + *((_QWORD *)this + 3)) = rand();
    }
    if ( a7 )
    {
      for ( j = 1; j < *v18; ++j )
        memcpy_0((void *)(*((_QWORD *)this + 3) + j * *v17), *((const void **)this + 3), (unsigned int)*v17);
    }
    RotatingBuffer::DoBufferLocking(this, *v19);
    goto LABEL_45;
  }
  v15 = GetLastError();
  v16 = v15;
  if ( v15 > 0 )
    v16 = (unsigned __int16)v15 | 0x80070000;
  v17 = (_DWORD *)((char *)this + 4);
  v18 = (unsigned int *)((char *)this + 8);
  v19 = (unsigned int *)((char *)this + 32);
LABEL_47:
  if ( v16 )
  {
    v33 = (void *)*((_QWORD *)this + 3);
    if ( v33 )
      VirtualFree(v33, 0, 0x8000u);
    *((_QWORD *)this + 3) = 0;
    *v17 = 0;
    *v18 = 0;
    *v19 = 0;
    *((_DWORD *)this + 9) = 0;
  }
  return v16;
}

```

## disassembly

```asm
0x1400796f8  mov     [rsp+arg_10], rbx
0x1400796fd  push    rbp
0x1400796fe  push    rsi
0x1400796ff  push    rdi
0x140079700  push    r12
0x140079702  push    r13
0x140079704  push    r14
0x140079706  push    r15
0x140079708  sub     rsp, 50h
0x14007970c  mov     rbx, [rsp+88h+arg_20]
0x140079714  or      r14, 0FFFFFFFFFFFFFFFFh
0x140079718  cmp     qword ptr [rcx+18h], 0
0x14007971d  mov     edi, r8d
0x140079720  mov     ebp, edx
0x140079722  mov     [rsp+88h+hFile], r14
0x140079727  mov     rsi, rcx
0x14007972a  jz      short loc_140079735
0x14007972c  lea     eax, [r14+6]
0x140079730  jmp     loc_140079A11
0x140079735  lea     eax, [r9+rdx]
0x140079739  cmp     eax, ebp
0x14007973b  jb      loc_140079A0C
0x140079741  mov     r9d, [rsp+88h+flProtect]; flProtect
0x140079749  mov     r8d, 1000h; flAllocationType
0x14007974f  mov     [rcx+10h], r9d
0x140079753  xor     ecx, ecx; lpAddress
0x140079755  mov     edx, eax; dwSize
0x140079757  call    cs:__imp_VirtualAlloc
0x14007975d  xor     ecx, ecx
0x14007975f  mov     [rsi+18h], rax
0x140079763  test    rax, rax
0x140079766  jnz     short loc_14007978E
0x140079768  call    cs:__imp_GetLastError
0x14007976e  mov     edi, eax
0x140079770  test    eax, eax
0x140079772  jle     short loc_14007977D
0x140079774  movzx   edi, ax
0x140079777  or      edi, 80070000h
0x14007977d  lea     r15, [rsi+4]
0x140079781  lea     r12, [rsi+8]
0x140079785  lea     r13, [rsi+20h]
0x140079789  jmp     loc_1400799C4
0x14007978e  xor     edx, edx
0x140079790  mov     [rsi+24h], rcx
0x140079794  mov     eax, ebp
0x140079796  mov     [rsi], ebp
0x140079798  div     edi
0x14007979a  cmp     [rsp+88h+arg_30], ecx
0x1400797a1  lea     r12, [rsi+8]
0x1400797a5  mov     [r12], edi
0x1400797a9  lea     r13, [rsi+20h]
0x1400797ad  mov     [r13+0], ecx
0x1400797b1  lea     r15, [rsi+4]
0x1400797b5  mov     edi, ecx
0x1400797b7  mov     [r15], eax
0x1400797ba  mov     edx, 10000h
0x1400797bf  mov     dword ptr [rsi+0Ch], 1
0x1400797c6  lea     rcx, aSimplerandomda; "SIMPLERANDOMDATA"
0x1400797cd  cmovnz  ebp, eax
0x1400797d0  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x1400797d5  mov     r8, [rbx]
0x1400797d8  lea     r9, aSimplerandomda; "SIMPLERANDOMDATA"
0x1400797df  mov     rcx, rbx
0x1400797e2  mov     [rsp+88h+lpOverlapped], rax
0x1400797e7  mov     r8, [r8]
0x1400797ea  call    ?comparei_str@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBAH_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::comparei_str(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x1400797ef  test    eax, eax
0x1400797f1  jnz     short loc_140079823
0x1400797f3  call    cs:__imp_GetTickCount
0x1400797f9  mov     ecx, eax; Seed
0x1400797fb  call    cs:__imp_srand
0x140079801  xor     ebx, ebx
0x140079803  test    ebp, ebp
0x140079805  jz      loc_140079975
0x14007980b  call    cs:__imp_rand
0x140079811  mov     rcx, [rsi+18h]
0x140079815  mov     [rbx+rcx], al
0x140079818  inc     ebx
0x14007981a  cmp     ebx, ebp
0x14007981c  jb      short loc_14007980B
0x14007981e  jmp     loc_140079975
0x140079823  mov     rcx, rbx
0x140079826  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x14007982b  test    al, al
0x14007982d  jnz     loc_140079975
0x140079833  mov     rcx, [rbx]
0x140079836  lea     r8, [rsp+88h+hFile]; unsigned int
0x14007983b  mov     edx, 5; unsigned __int16 *
0x140079840  mov     rcx, [rcx+18h]; lpFileName
0x140079844  call    ?MCreateFile@mlib@@YAKPEBGKAEAPEAX@Z; mlib::MCreateFile(ushort const *,ulong,void * &)
0x140079849  test    eax, eax
0x14007984b  jz      short loc_14007986C
0x14007984d  call    cs:__imp_GetLastError
0x140079853  mov     edi, eax
0x140079855  test    eax, eax
0x140079857  jle     short loc_140079862
0x140079859  movzx   edi, ax
0x14007985c  or      edi, 80070000h
0x140079862  mov     r14, [rsp+88h+hFile]
0x140079867  jmp     loc_1400799B5
0x14007986c  mov     r14, [rsp+88h+hFile]
0x140079871  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x140079876  mov     rcx, r14; hFile
0x140079879  mov     qword ptr [rsp+88h+FileSize], rdi
0x14007987e  mov     [rsp+88h+NumberOfBytesRead], edi
0x140079882  call    cs:__imp_GetFileSizeEx
0x140079888  test    eax, eax
0x14007988a  jnz     short loc_1400798AA
0x14007988c  call    cs:__imp_GetLastError
0x140079892  mov     edi, eax
0x140079894  test    eax, eax
0x140079896  jle     loc_1400799B5
0x14007989c  movzx   edi, ax
0x14007989f  or      edi, 80070000h
0x1400798a5  jmp     loc_1400799B5
0x1400798aa  mov     rbx, qword ptr [rsp+88h+FileSize]
0x1400798af  test    rbx, rbx
0x1400798b2  jnz     short loc_1400798BE
0x1400798b4  mov     edi, 80040002h
0x1400798b9  jmp     loc_1400799B5
0x1400798be  xor     eax, eax
0x1400798c0  mov     ecx, 0FFFFFFFFh
0x1400798c5  cmp     rbx, rcx
0x1400798c8  mov     dword ptr [rsp+88h+hFile], eax
0x1400798cc  cmovg   ebx, ecx
0x1400798cf  test    ebp, ebp
0x1400798d1  jz      loc_140079971
0x1400798d7  mov     edx, eax
0x1400798d9  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400798de  cmp     ebp, ebx
0x1400798e0  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x1400798e9  mov     r15d, ebp
0x1400798ec  mov     rcx, r14; hFile
0x1400798ef  cmovnb  r15d, ebx
0x1400798f3  add     rdx, [rsi+18h]; lpBuffer
0x1400798f7  mov     r8d, r15d; nNumberOfBytesToRead
0x1400798fa  call    cs:__imp_ReadFile
0x140079900  test    eax, eax
0x140079902  jz      short loc_140079956
0x140079904  cmp     r15d, [rsp+88h+NumberOfBytesRead]
0x140079909  jnz     short loc_14007994F
0x14007990b  mov     eax, dword ptr [rsp+88h+hFile]
0x14007990f  add     eax, r15d
0x140079912  mov     dword ptr [rsp+88h+hFile], eax
0x140079916  sub     ebp, r15d
0x140079919  jz      short loc_1400798CF
0x14007991b  xor     r9d, r9d; dwMoveMethod
0x14007991e  xor     r8d, r8d; lpDistanceToMoveHigh
0x140079921  xor     edx, edx; lDistanceToMove
0x140079923  mov     rcx, r14; hFile
0x140079926  call    cs:__imp_SetFilePointer
0x14007992c  test    eax, eax
0x14007992e  mov     eax, dword ptr [rsp+88h+hFile]
0x140079932  jz      short loc_1400798CF
0x140079934  call    cs:__imp_GetLastError
0x14007993a  mov     edi, eax
0x14007993c  test    eax, eax
0x14007993e  jle     short loc_140079949
0x140079940  movzx   edi, ax
0x140079943  or      edi, 80070000h
0x140079949  mov     eax, dword ptr [rsp+88h+hFile]
0x14007994d  jmp     short loc_1400798CF
0x14007994f  mov     edi, 80040003h
0x140079954  jmp     short loc_14007996B
0x140079956  call    cs:__imp_GetLastError
0x14007995c  mov     edi, eax
0x14007995e  test    eax, eax
0x140079960  jle     short loc_14007996B
0x140079962  movzx   edi, ax
0x140079965  or      edi, 80070000h
0x14007996b  lea     r15, [rsi+4]
0x14007996f  jmp     short loc_1400799B5
0x140079971  lea     r15, [rsi+4]
0x140079975  cmp     [rsp+88h+arg_30], 0
0x14007997d  jz      short loc_1400799A9
0x14007997f  mov     ebx, 1
0x140079984  cmp     [r12], ebx
0x140079988  jbe     short loc_1400799A9
0x14007998a  mov     eax, [r15]
0x14007998d  mov     rdx, [rsi+18h]; Src
0x140079991  mov     r8d, eax; Size
0x140079994  imul    eax, ebx
0x140079997  mov     ecx, eax
0x140079999  add     rcx, rdx; void *
0x14007999c  call    memcpy_0
0x1400799a1  inc     ebx
0x1400799a3  cmp     ebx, [r12]
0x1400799a7  jb      short loc_14007998A
0x1400799a9  mov     edx, [r13+0]; unsigned int
0x1400799ad  mov     rcx, rsi; this
0x1400799b0  call    ?DoBufferLocking@RotatingBuffer@@AEAAPEAEK@Z; RotatingBuffer::DoBufferLocking(ulong)
0x1400799b5  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1400799b9  jz      short loc_1400799C4
0x1400799bb  mov     rcx, r14; hObject
0x1400799be  call    cs:__imp_CloseHandle
0x1400799c4  lea     rbx, [rsi+24h]
0x1400799c8  test    edi, edi
0x1400799ca  jz      short loc_140079A08
0x1400799cc  mov     rcx, [rsi+18h]; lpAddress
0x1400799d0  test    rcx, rcx
0x1400799d3  jz      short loc_1400799E3
0x1400799d5  xor     edx, edx; dwSize
0x1400799d7  mov     r8d, 8000h; dwFreeType
0x1400799dd  call    cs:__imp_VirtualFree
0x1400799e3  mov     qword ptr [rsi+18h], 0
0x1400799eb  mov     dword ptr [r15], 0
0x1400799f2  mov     dword ptr [r12], 0
0x1400799fa  mov     dword ptr [r13+0], 0
0x140079a02  mov     dword ptr [rbx], 0
0x140079a08  mov     eax, edi
0x140079a0a  jmp     short loc_140079A11
0x140079a0c  mov     eax, 8007000Eh
0x140079a11  mov     rbx, [rsp+88h+arg_10]
0x140079a19  add     rsp, 50h
0x140079a1d  pop     r15
0x140079a1f  pop     r14
0x140079a21  pop     r13
0x140079a23  pop     r12
0x140079a25  pop     rdi
0x140079a26  pop     rsi
0x140079a27  pop     rbp
0x140079a28  retn
```
