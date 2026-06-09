# CWmpEncoderFrame::HrAllocateFrameBuffer(void)

- ea: `0x180028940`
- end: `0x180028c9c`
- name: `?HrAllocateFrameBuffer@CWmpEncoderFrame@@MEAAJXZ`
- size: `860`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180028690`
- `0x180029040`

## callees

- `0x180028940`
- `0x18002ded0`
- `0x18002df00`
- `0x180032470`
- `0x180036420`
- `0x180037174`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180028a75`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180028a75`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180028c2c`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180028c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ba0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028bd6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028bd6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028b8f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028bf8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028b8f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028bf8`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180028b58`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180028b58`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180028acd`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180028acd`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180028a9e`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180028a9e`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::HrAllocateFrameBuffer(CWmpEncoderFrame *this)
{
  HRESULT v2; // ebx
  __int64 v3; // rcx
  int v4; // r10d
  unsigned int v5; // r10d
  ULONGLONG *v6; // r9
  ULONGLONG v7; // rcx
  ULONGLONG *v8; // r9
  unsigned int v9; // r10d
  ULONGLONG v10; // rsi
  ULONGLONG v11; // rcx
  const CHAR *v12; // rax
  const CHAR *v13; // rbx
  unsigned int v14; // r8d
  int v15; // r9d
  unsigned int v16; // edx
  CHAR v17; // cl
  __int64 v18; // rax
  CHAR v19; // r10
  __int64 v20; // rax
  HANDLE FileA; // rax
  void *v22; // rcx
  void *v24; // rax
  _BYTE Buffer[8]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-B8h] BYREF
  ULONGLONG ullMultiplier; // [rsp+50h] [rbp-B0h] BYREF
  ULONGLONG pullResult; // [rsp+58h] [rbp-A8h] BYREF
  ULONGLONG Size[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR PathName[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = 0;
  if ( *((_QWORD *)this + 8288) )
    return (unsigned int)v2;
  if ( *((_QWORD *)this + 10) )
  {
    if ( *((_DWORD *)this + 25) && *((_DWORD *)this + 26) )
    {
      v3 = *((unsigned int *)this + 25);
      *(_QWORD *)NumberOfBytesWritten = 0;
      pullResult = 0;
      ullMultiplier = 0;
      Size[0] = 0;
      if ( (unsigned int)PadupSafe(v3, 16, NumberOfBytesWritten) )
        return (unsigned int)-2147024362;
      if ( (unsigned int)Bit2ByteSafe(*((_QWORD *)this + 10), *(_QWORD *)NumberOfBytesWritten, &pullResult) )
        return (unsigned int)-2147024362;
      if ( (unsigned int)PadupSafe(pullResult, (unsigned int)(v4 + 112), (char *)this + 66312) )
        return (unsigned int)-2147024362;
      if ( (unsigned int)PadupSafe(*((unsigned int *)this + 26), v5, &ullMultiplier) )
        return (unsigned int)-2147024362;
      v7 = *v6;
      pullResult = 0;
      if ( ULongLongMult(v7, ullMultiplier, &pullResult) )
      {
        return (unsigned int)-2147024362;
      }
      else
      {
        v10 = pullResult;
        v11 = *v8;
        if ( pullResult <= 0x8000000 )
        {
          v2 = ULongLongMult(v11, ullMultiplier, Size);
          if ( v2 >= 0 )
          {
LABEL_30:
            v24 = _aligned_malloc(Size[0], 0x80u);
            *((_QWORD *)this + 8288) = v24;
            if ( v24 )
            {
              v2 = 0;
              memset_0(v24, 0, Size[0]);
            }
            else
            {
              return (unsigned int)-2147024882;
            }
          }
        }
        else
        {
          v2 = ULongLongMult(v11, v9, Size);
          if ( v2 >= 0 )
          {
            v12 = (const CHAR *)malloc(0x208u);
            *((_QWORD *)this + 8322) = v12;
            v13 = v12;
            if ( !v12 )
              return 2147942414LL;
            if ( (unsigned int)GetTempPath2W(260, PathName) - 1 > 0x102
              || !GetTempFileNameW(PathName, L"wdp", 0, *((LPWSTR *)this + 8322)) )
            {
              return 0xFFFFFFFFLL;
            }
            v14 = 0;
            v15 = 0;
            v16 = 0;
            do
            {
              if ( !*(_WORD *)(*((_QWORD *)this + 8322) + 2LL * v14) )
                break;
              v17 = v13[v15];
              if ( v17 )
              {
                v18 = v16++;
                v13[v18] = v17;
              }
              v19 = v13[v15 + 1];
              if ( v19 )
              {
                v20 = v16++;
                v13[v20] = v19;
              }
              ++v14;
              v15 += 2;
            }
            while ( v14 < 0x104 );
            v13[v14] = 0;
            FileA = CreateFileA(v13, 0xC0000000, 0, 0, 2u, 0, 0);
            *((_QWORD *)this + 8321) = FileA;
            if ( FileA == (HANDLE)-1LL )
              return 2147942414LL;
            LODWORD(ullMultiplier) = (v10 - 1) >> 32;
            if ( SetFilePointer(FileA, v10 - 1, (PLONG)&ullMultiplier, 0) == -1 )
            {
              if ( GetLastError() )
                return 2147942414LL;
            }
            v22 = (void *)*((_QWORD *)this + 8321);
            NumberOfBytesWritten[0] = 0;
            Buffer[0] = 0;
            WriteFile(v22, Buffer, 1u, NumberOfBytesWritten, 0);
            if ( !NumberOfBytesWritten[0] )
              return 2147942414LL;
            SetFilePointer(*((HANDLE *)this + 8321), 0, 0, 0);
            goto LABEL_30;
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2003292335;
    }
  }
  else
  {
    return (unsigned int)-2003292288;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180028940  mov     [rsp-8+arg_8], rbx
0x180028945  mov     [rsp-8+arg_10], rsi
0x18002894a  push    rbp
0x18002894b  push    rdi
0x18002894c  push    r14
0x18002894e  lea     rbp, [rsp-190h]
0x180028956  sub     rsp, 290h
0x18002895d  mov     rax, cs:__security_cookie
0x180028964  xor     rax, rsp
0x180028967  mov     [rbp+1A0h+var_20], rax
0x18002896e  xor     r14d, r14d
0x180028971  mov     rdi, rcx
0x180028974  mov     ebx, r14d
0x180028977  cmp     [rcx+10300h], r14
0x18002897e  jnz     loc_180028C72
0x180028984  cmp     [rcx+50h], r14
0x180028988  jz      loc_180028C6D
0x18002898e  cmp     [rcx+64h], r14d
0x180028992  jz      loc_180028C66
0x180028998  cmp     [rcx+68h], r14d
0x18002899c  jz      loc_180028C66
0x1800289a2  mov     ecx, [rcx+64h]
0x1800289a5  lea     r10d, [r14+10h]
0x1800289a9  mov     edx, r10d
0x1800289ac  mov     qword ptr [rsp+2A0h+NumberOfBytesWritten], r14
0x1800289b1  lea     r8, [rsp+2A0h+NumberOfBytesWritten]
0x1800289b6  mov     [rsp+2A0h+pullResult], r14
0x1800289bb  mov     [rsp+2A0h+ullMultiplier], r14
0x1800289c0  mov     [rsp+2A0h+Size], r14
0x1800289c5  call    PadupSafe
0x1800289ca  test    eax, eax
0x1800289cc  jnz     loc_180028C5F
0x1800289d2  mov     rdx, qword ptr [rsp+2A0h+NumberOfBytesWritten]
0x1800289d7  lea     r8, [rsp+2A0h+pullResult]
0x1800289dc  mov     rcx, [rdi+50h]
0x1800289e0  call    Bit2ByteSafe
0x1800289e5  test    eax, eax
0x1800289e7  jnz     loc_180028C5F
0x1800289ed  mov     rcx, [rsp+2A0h+pullResult]
0x1800289f2  lea     r9, [rdi+10308h]
0x1800289f9  mov     r8, r9
0x1800289fc  lea     edx, [r10+70h]
0x180028a00  call    PadupSafe
0x180028a05  test    eax, eax
0x180028a07  jnz     loc_180028C5F
0x180028a0d  mov     ecx, [rdi+68h]
0x180028a10  lea     r8, [rsp+2A0h+ullMultiplier]
0x180028a15  mov     edx, r10d
0x180028a18  call    PadupSafe
0x180028a1d  test    eax, eax
0x180028a1f  jnz     loc_180028C5F
0x180028a25  mov     rdx, [rsp+2A0h+ullMultiplier]; ullMultiplier
0x180028a2a  lea     r8, [rsp+2A0h+pullResult]; pullResult
0x180028a2f  mov     rcx, [r9]; ullMultiplicand
0x180028a32  mov     [rsp+2A0h+pullResult], r14
0x180028a37  call    ULongLongMult
0x180028a3c  test    eax, eax
0x180028a3e  jnz     loc_180028C5F
0x180028a44  mov     rsi, [rsp+2A0h+pullResult]
0x180028a49  lea     r8, [rsp+2A0h+Size]; pullResult
0x180028a4e  mov     rcx, [r9]; ullMultiplicand
0x180028a51  cmp     rsi, 8000000h
0x180028a58  jbe     loc_180028C12
0x180028a5e  mov     edx, r10d; ullMultiplier
0x180028a61  call    ULongLongMult
0x180028a66  mov     ebx, eax
0x180028a68  test    eax, eax
0x180028a6a  js      loc_180028C72
0x180028a70  mov     ecx, 208h; Size
0x180028a75  call    cs:__imp_malloc
0x180028a7c  nop     dword ptr [rax+rax+00h]
0x180028a81  mov     [rdi+10410h], rax
0x180028a88  mov     rbx, rax
0x180028a8b  test    rax, rax
0x180028a8e  jz      loc_180028C0B
0x180028a94  lea     rdx, [rsp+2A0h+PathName]
0x180028a99  mov     ecx, 104h
0x180028a9e  call    cs:__imp_GetTempPath2W
0x180028aa5  nop     dword ptr [rax+rax+00h]
0x180028aaa  dec     eax
0x180028aac  cmp     eax, 102h
0x180028ab1  ja      loc_180028C06
0x180028ab7  mov     r9, [rdi+10410h]; lpTempFileName
0x180028abe  lea     rdx, PrefixString; "wdp"
0x180028ac5  xor     r8d, r8d; uUnique
0x180028ac8  lea     rcx, [rsp+2A0h+PathName]; lpPathName
0x180028acd  call    cs:__imp_GetTempFileNameW
0x180028ad4  nop     dword ptr [rax+rax+00h]
0x180028ad9  test    eax, eax
0x180028adb  jz      loc_180028C06
0x180028ae1  mov     r8d, r14d
0x180028ae4  mov     r9d, r14d
0x180028ae7  mov     edx, r14d
0x180028aea  mov     rax, [rdi+10410h]
0x180028af1  mov     ecx, r8d
0x180028af4  cmp     [rax+rcx*2], r14w
0x180028af9  jz      short loc_180028B31
0x180028afb  mov     eax, r9d
0x180028afe  mov     cl, [rax+rbx]
0x180028b01  test    cl, cl
0x180028b03  jz      short loc_180028B0C
0x180028b05  mov     eax, edx
0x180028b07  inc     edx
0x180028b09  mov     [rax+rbx], cl
0x180028b0c  lea     eax, [r9+1]
0x180028b10  mov     r10b, [rax+rbx]
0x180028b14  test    r10b, r10b
0x180028b17  jz      short loc_180028B21
0x180028b19  mov     eax, edx
0x180028b1b  inc     edx
0x180028b1d  mov     [rax+rbx], r10b
0x180028b21  inc     r8d
0x180028b24  add     r9d, 2
0x180028b28  cmp     r8d, 104h
0x180028b2f  jb      short loc_180028AEA
0x180028b31  mov     eax, r8d
0x180028b34  xor     r9d, r9d; lpSecurityAttributes
0x180028b37  mov     [rsp+2A0h+hTemplateFile], r14; hTemplateFile
0x180028b3c  xor     r8d, r8d; dwShareMode
0x180028b3f  mov     [rsp+2A0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180028b44  mov     edx, 0C0000000h; dwDesiredAccess
0x180028b49  mov     rcx, rbx; lpFileName
0x180028b4c  mov     [rsp+2A0h+dwCreationDisposition], 2; dwCreationDisposition
0x180028b54  mov     [rax+rbx], r14b
0x180028b58  call    cs:__imp_CreateFileA
0x180028b5f  nop     dword ptr [rax+rax+00h]
0x180028b64  mov     [rdi+10408h], rax
0x180028b6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028b6f  jz      loc_180028C0B
0x180028b75  lea     rdx, [rsi-1]; lDistanceToMove
0x180028b79  xor     r9d, r9d; dwMoveMethod
0x180028b7c  mov     rcx, rdx
0x180028b7f  lea     r8, [rsp+2A0h+ullMultiplier]; lpDistanceToMoveHigh
0x180028b84  sar     rcx, 20h
0x180028b88  mov     dword ptr [rsp+2A0h+ullMultiplier], ecx
0x180028b8c  mov     rcx, rax; hFile
0x180028b8f  call    cs:__imp_SetFilePointer
0x180028b96  nop     dword ptr [rax+rax+00h]
0x180028b9b  cmp     eax, 0FFFFFFFFh
0x180028b9e  jnz     short loc_180028BB0
0x180028ba0  call    cs:__imp_GetLastError
0x180028ba7  nop     dword ptr [rax+rax+00h]
0x180028bac  test    eax, eax
0x180028bae  jnz     short loc_180028C0B
0x180028bb0  mov     rcx, [rdi+10408h]; hFile
0x180028bb7  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180028bbc  mov     r8d, 1; nNumberOfBytesToWrite
0x180028bc2  mov     [rsp+2A0h+NumberOfBytesWritten], r14d
0x180028bc7  lea     rdx, [rsp+2A0h+Buffer]; lpBuffer
0x180028bcc  mov     [rsp+2A0h+Buffer], r14b
0x180028bd1  mov     qword ptr [rsp+2A0h+dwCreationDisposition], r14; lpOverlapped
0x180028bd6  call    cs:__imp_WriteFile
0x180028bdd  nop     dword ptr [rax+rax+00h]
0x180028be2  cmp     [rsp+2A0h+NumberOfBytesWritten], r14d
0x180028be7  jz      short loc_180028C0B
0x180028be9  mov     rcx, [rdi+10408h]; hFile
0x180028bf0  xor     r9d, r9d; dwMoveMethod
0x180028bf3  xor     r8d, r8d; lpDistanceToMoveHigh
0x180028bf6  xor     edx, edx; lDistanceToMove
0x180028bf8  call    cs:__imp_SetFilePointer
0x180028bff  nop     dword ptr [rax+rax+00h]
0x180028c04  jmp     short loc_180028C22
0x180028c06  or      eax, 0FFFFFFFFh
0x180028c09  jmp     short loc_180028C74
0x180028c0b  mov     eax, 8007000Eh
0x180028c10  jmp     short loc_180028C74
0x180028c12  mov     rdx, [rsp+2A0h+ullMultiplier]; ullMultiplier
0x180028c17  call    ULongLongMult
0x180028c1c  mov     ebx, eax
0x180028c1e  test    eax, eax
0x180028c20  js      short loc_180028C72
0x180028c22  mov     rcx, [rsp+2A0h+Size]; Size
0x180028c27  mov     edx, 80h; Alignment
0x180028c2c  call    cs:__imp__aligned_malloc
0x180028c33  nop     dword ptr [rax+rax+00h]
0x180028c38  mov     [rdi+10300h], rax
0x180028c3f  test    rax, rax
0x180028c42  jz      short loc_180028C58
0x180028c44  mov     r8, [rsp+2A0h+Size]; Size
0x180028c49  xor     edx, edx; Val
0x180028c4b  mov     rcx, rax; void *
0x180028c4e  mov     ebx, r14d
0x180028c51  call    memset_0
0x180028c56  jmp     short loc_180028C72
0x180028c58  mov     ebx, 8007000Eh
0x180028c5d  jmp     short loc_180028C72
0x180028c5f  mov     ebx, 80070216h
0x180028c64  jmp     short loc_180028C72
0x180028c66  mov     ebx, 88982F51h
0x180028c6b  jmp     short loc_180028C72
0x180028c6d  mov     ebx, 88982F80h
0x180028c72  mov     eax, ebx
0x180028c74  mov     rcx, [rbp+1A0h+var_20]
0x180028c7b  xor     rcx, rsp; StackCookie
0x180028c7e  call    __security_check_cookie
0x180028c83  lea     r11, [rsp+2A0h+var_10]
0x180028c8b  mov     rbx, [r11+28h]
0x180028c8f  mov     rsi, [r11+30h]
0x180028c93  mov     rsp, r11
0x180028c96  pop     r14
0x180028c98  pop     rdi
0x180028c99  pop     rbp
0x180028c9a  retn
```
