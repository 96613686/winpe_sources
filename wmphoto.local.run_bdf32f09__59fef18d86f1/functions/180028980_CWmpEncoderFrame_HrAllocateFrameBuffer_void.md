# CWmpEncoderFrame::HrAllocateFrameBuffer(void)

- ea: `0x180028980`
- end: `0x180028ca1`
- name: `?HrAllocateFrameBuffer@CWmpEncoderFrame@@MEAAJXZ`
- size: `801`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180028530`
- `0x180028fb0`

## callees

- `0x180028980`
- `0x18002dbd0`
- `0x18002de74`
- `0x1800320d8`
- `0x180035e50`
- `0x180036ba4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180028ab5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180028ab5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180028c38`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180028c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028bbe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028bee`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028bee`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028bb3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028c0a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028bb3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028c0a`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180028b86`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180028b86`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180028b01`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180028b01`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180028ad8`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180028ad8`

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
0x180028980  mov     [rsp-8+arg_8], rbx
0x180028985  mov     [rsp-8+arg_10], rsi
0x18002898a  push    rbp
0x18002898b  push    rdi
0x18002898c  push    r14
0x18002898e  lea     rbp, [rsp-190h]
0x180028996  sub     rsp, 290h
0x18002899d  mov     rax, cs:__security_cookie
0x1800289a4  xor     rax, rsp
0x1800289a7  mov     [rbp+1A0h+var_20], rax
0x1800289ae  xor     r14d, r14d
0x1800289b1  mov     rdi, rcx
0x1800289b4  mov     ebx, r14d
0x1800289b7  cmp     [rcx+10300h], r14
0x1800289be  jnz     loc_180028C78
0x1800289c4  cmp     [rcx+50h], r14
0x1800289c8  jz      loc_180028C73
0x1800289ce  cmp     [rcx+64h], r14d
0x1800289d2  jz      loc_180028C6C
0x1800289d8  cmp     [rcx+68h], r14d
0x1800289dc  jz      loc_180028C6C
0x1800289e2  mov     ecx, [rcx+64h]
0x1800289e5  lea     r10d, [r14+10h]
0x1800289e9  mov     edx, r10d
0x1800289ec  mov     qword ptr [rsp+2A0h+NumberOfBytesWritten], r14
0x1800289f1  lea     r8, [rsp+2A0h+NumberOfBytesWritten]
0x1800289f6  mov     [rsp+2A0h+pullResult], r14
0x1800289fb  mov     [rsp+2A0h+ullMultiplier], r14
0x180028a00  mov     [rsp+2A0h+Size], r14
0x180028a05  call    PadupSafe
0x180028a0a  test    eax, eax
0x180028a0c  jnz     loc_180028C65
0x180028a12  mov     rdx, qword ptr [rsp+2A0h+NumberOfBytesWritten]
0x180028a17  lea     r8, [rsp+2A0h+pullResult]
0x180028a1c  mov     rcx, [rdi+50h]
0x180028a20  call    Bit2ByteSafe
0x180028a25  test    eax, eax
0x180028a27  jnz     loc_180028C65
0x180028a2d  mov     rcx, [rsp+2A0h+pullResult]
0x180028a32  lea     r9, [rdi+10308h]
0x180028a39  mov     r8, r9
0x180028a3c  lea     edx, [r10+70h]
0x180028a40  call    PadupSafe
0x180028a45  test    eax, eax
0x180028a47  jnz     loc_180028C65
0x180028a4d  mov     ecx, [rdi+68h]
0x180028a50  lea     r8, [rsp+2A0h+ullMultiplier]
0x180028a55  mov     edx, r10d
0x180028a58  call    PadupSafe
0x180028a5d  test    eax, eax
0x180028a5f  jnz     loc_180028C65
0x180028a65  mov     rdx, [rsp+2A0h+ullMultiplier]; ullMultiplier
0x180028a6a  lea     r8, [rsp+2A0h+pullResult]; pullResult
0x180028a6f  mov     rcx, [r9]; ullMultiplicand
0x180028a72  mov     [rsp+2A0h+pullResult], r14
0x180028a77  call    ULongLongMult
0x180028a7c  test    eax, eax
0x180028a7e  jnz     loc_180028C65
0x180028a84  mov     rsi, [rsp+2A0h+pullResult]
0x180028a89  lea     r8, [rsp+2A0h+Size]; pullResult
0x180028a8e  mov     rcx, [r9]; ullMultiplicand
0x180028a91  cmp     rsi, 8000000h
0x180028a98  jbe     loc_180028C1E
0x180028a9e  mov     edx, r10d; ullMultiplier
0x180028aa1  call    ULongLongMult
0x180028aa6  mov     ebx, eax
0x180028aa8  test    eax, eax
0x180028aaa  js      loc_180028C78
0x180028ab0  mov     ecx, 208h; Size
0x180028ab5  call    cs:__imp_malloc
0x180028abb  mov     [rdi+10410h], rax
0x180028ac2  mov     rbx, rax
0x180028ac5  test    rax, rax
0x180028ac8  jz      loc_180028C17
0x180028ace  lea     rdx, [rsp+2A0h+PathName]
0x180028ad3  mov     ecx, 104h
0x180028ad8  call    cs:__imp_GetTempPath2W
0x180028ade  dec     eax
0x180028ae0  cmp     eax, 102h
0x180028ae5  ja      loc_180028C12
0x180028aeb  mov     r9, [rdi+10410h]; lpTempFileName
0x180028af2  lea     rdx, PrefixString; "wdp"
0x180028af9  xor     r8d, r8d; uUnique
0x180028afc  lea     rcx, [rsp+2A0h+PathName]; lpPathName
0x180028b01  call    cs:__imp_GetTempFileNameW
0x180028b07  test    eax, eax
0x180028b09  jz      loc_180028C12
0x180028b0f  mov     r8d, r14d
0x180028b12  mov     r9d, r14d
0x180028b15  mov     edx, r14d
0x180028b18  mov     rax, [rdi+10410h]
0x180028b1f  mov     ecx, r8d
0x180028b22  cmp     [rax+rcx*2], r14w
0x180028b27  jz      short loc_180028B5F
0x180028b29  mov     eax, r9d
0x180028b2c  mov     cl, [rax+rbx]
0x180028b2f  test    cl, cl
0x180028b31  jz      short loc_180028B3A
0x180028b33  mov     eax, edx
0x180028b35  inc     edx
0x180028b37  mov     [rax+rbx], cl
0x180028b3a  lea     eax, [r9+1]
0x180028b3e  mov     r10b, [rax+rbx]
0x180028b42  test    r10b, r10b
0x180028b45  jz      short loc_180028B4F
0x180028b47  mov     eax, edx
0x180028b49  inc     edx
0x180028b4b  mov     [rax+rbx], r10b
0x180028b4f  inc     r8d
0x180028b52  add     r9d, 2
0x180028b56  cmp     r8d, 104h
0x180028b5d  jb      short loc_180028B18
0x180028b5f  mov     eax, r8d
0x180028b62  xor     r9d, r9d; lpSecurityAttributes
0x180028b65  mov     [rsp+2A0h+hTemplateFile], r14; hTemplateFile
0x180028b6a  xor     r8d, r8d; dwShareMode
0x180028b6d  mov     [rsp+2A0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180028b72  mov     edx, 0C0000000h; dwDesiredAccess
0x180028b77  mov     rcx, rbx; lpFileName
0x180028b7a  mov     [rsp+2A0h+dwCreationDisposition], 2; dwCreationDisposition
0x180028b82  mov     [rax+rbx], r14b
0x180028b86  call    cs:__imp_CreateFileA
0x180028b8c  mov     [rdi+10408h], rax
0x180028b93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028b97  jz      short loc_180028C17
0x180028b99  lea     rdx, [rsi-1]; lDistanceToMove
0x180028b9d  xor     r9d, r9d; dwMoveMethod
0x180028ba0  mov     rcx, rdx
0x180028ba3  lea     r8, [rsp+2A0h+ullMultiplier]; lpDistanceToMoveHigh
0x180028ba8  sar     rcx, 20h
0x180028bac  mov     dword ptr [rsp+2A0h+ullMultiplier], ecx
0x180028bb0  mov     rcx, rax; hFile
0x180028bb3  call    cs:__imp_SetFilePointer
0x180028bb9  cmp     eax, 0FFFFFFFFh
0x180028bbc  jnz     short loc_180028BC8
0x180028bbe  call    cs:__imp_GetLastError
0x180028bc4  test    eax, eax
0x180028bc6  jnz     short loc_180028C17
0x180028bc8  mov     rcx, [rdi+10408h]; hFile
0x180028bcf  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180028bd4  mov     r8d, 1; nNumberOfBytesToWrite
0x180028bda  mov     [rsp+2A0h+NumberOfBytesWritten], r14d
0x180028bdf  lea     rdx, [rsp+2A0h+Buffer]; lpBuffer
0x180028be4  mov     [rsp+2A0h+Buffer], r14b
0x180028be9  mov     qword ptr [rsp+2A0h+dwCreationDisposition], r14; lpOverlapped
0x180028bee  call    cs:__imp_WriteFile
0x180028bf4  cmp     [rsp+2A0h+NumberOfBytesWritten], r14d
0x180028bf9  jz      short loc_180028C17
0x180028bfb  mov     rcx, [rdi+10408h]; hFile
0x180028c02  xor     r9d, r9d; dwMoveMethod
0x180028c05  xor     r8d, r8d; lpDistanceToMoveHigh
0x180028c08  xor     edx, edx; lDistanceToMove
0x180028c0a  call    cs:__imp_SetFilePointer
0x180028c10  jmp     short loc_180028C2E
0x180028c12  or      eax, 0FFFFFFFFh
0x180028c15  jmp     short loc_180028C7A
0x180028c17  mov     eax, 8007000Eh
0x180028c1c  jmp     short loc_180028C7A
0x180028c1e  mov     rdx, [rsp+2A0h+ullMultiplier]; ullMultiplier
0x180028c23  call    ULongLongMult
0x180028c28  mov     ebx, eax
0x180028c2a  test    eax, eax
0x180028c2c  js      short loc_180028C78
0x180028c2e  mov     rcx, [rsp+2A0h+Size]; Size
0x180028c33  mov     edx, 80h; Alignment
0x180028c38  call    cs:__imp__aligned_malloc
0x180028c3e  mov     [rdi+10300h], rax
0x180028c45  test    rax, rax
0x180028c48  jz      short loc_180028C5E
0x180028c4a  mov     r8, [rsp+2A0h+Size]; Size
0x180028c4f  xor     edx, edx; Val
0x180028c51  mov     rcx, rax; void *
0x180028c54  mov     ebx, r14d
0x180028c57  call    memset_0
0x180028c5c  jmp     short loc_180028C78
0x180028c5e  mov     ebx, 8007000Eh
0x180028c63  jmp     short loc_180028C78
0x180028c65  mov     ebx, 80070216h
0x180028c6a  jmp     short loc_180028C78
0x180028c6c  mov     ebx, 88982F51h
0x180028c71  jmp     short loc_180028C78
0x180028c73  mov     ebx, 88982F80h
0x180028c78  mov     eax, ebx
0x180028c7a  mov     rcx, [rbp+1A0h+var_20]
0x180028c81  xor     rcx, rsp; StackCookie
0x180028c84  call    __security_check_cookie
0x180028c89  lea     r11, [rsp+2A0h+var_10]
0x180028c91  mov     rbx, [r11+28h]
0x180028c95  mov     rsi, [r11+30h]
0x180028c99  mov     rsp, r11
0x180028c9c  pop     r14
0x180028c9e  pop     rdi
0x180028c9f  pop     rbp
0x180028ca0  retn
```
