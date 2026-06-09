# bIsFolderMember(void *,_tagMPSWabFileInfo *,ulong,ulong *)

- ea: `0x1800450b8`
- end: `0x180045235`
- name: `?bIsFolderMember@@YAHPEAXPEAU_tagMPSWabFileInfo@@KPEAK@Z`
- size: `381`
- prototype: `__int64 __fastcall(HANDLE hFile, struct _tagMPSWabFileInfo *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180040e30`
- `0x180043ffc`

## callees

- `0x1800301e8`
- `0x180032588`
- `0x180033040`
- `0x1800450b8`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800451b6`
- `KERNEL32!LocalAlloc` at `0x1800451b6`
- `KERNEL32!LocalFree` at `0x18004520f`
- `KERNEL32!LocalFree` at `0x18004520f`
- `KERNEL32!GetFileSize` at `0x180045147`
- `KERNEL32!GetFileSize` at `0x180045147`
- `KERNEL32!ReadFile` at `0x1800451d7`
- `KERNEL32!ReadFile` at `0x1800451d7`

## pseudocode

```c
__int64 __fastcall bIsFolderMember(HANDLE hFile, struct _tagMPSWabFileInfo *a2, unsigned int a3, unsigned int *a4)
{
  struct _tagMPSWabIndexEntryDataEntryID *v4; // r14
  __int64 v6; // r8
  unsigned int v10; // edi
  __int64 v11; // rax
  unsigned int v12; // r14d
  DWORD FileSize; // eax
  __m128i v14; // xmm1
  __int64 v15; // rdx
  unsigned int v16; // eax
  _DWORD *v17; // rax
  _DWORD *v18; // rbx
  __int64 i; // rcx
  DWORD NumberOfBytesRead[4]; // [rsp+30h] [rbp-39h] BYREF
  _OWORD v22[2]; // [rsp+40h] [rbp-29h] BYREF
  __m128i v23; // [rsp+60h] [rbp-9h] BYREF
  DWORD nNumberOfBytesToRead[4]; // [rsp+70h] [rbp+7h]

  v4 = (struct _tagMPSWabIndexEntryDataEntryID *)*((_QWORD *)a2 + 5);
  v6 = *((_QWORD *)a2 + 3);
  v10 = 0;
  NumberOfBytesRead[0] = 0;
  if ( (unsigned int)BinSearchEID(v4, a3, *(_DWORD *)(v6 + 36), NumberOfBytesRead) )
  {
    v11 = NumberOfBytesRead[0];
    NumberOfBytesRead[0] = 0;
    v23 = 0;
    v12 = *((_DWORD *)v4 + 2 * v11 + 1);
    *(_OWORD *)nNumberOfBytesToRead = 0;
    if ( ReadDataFromWABFile(hFile, v12, &v23, 0x20u) )
    {
      FileSize = GetFileSize(hFile, 0);
      v14 = v23;
      v15 = *(unsigned int *)(*((_QWORD *)a2 + 3) + 20LL);
      v22[0] = v23;
      v22[1] = *(_OWORD *)nNumberOfBytesToRead;
      if ( (unsigned int)bIsValidRecord(v22, v15, v12, FileSize, 1, a3) )
      {
        if ( a4 )
          *a4 = _mm_cvtsi128_si32(_mm_srli_si128(v14, 4));
        v16 = _mm_cvtsi128_si32(_mm_srli_si128(v14, 12));
        if ( v16 <= 0x3FFFFFFF )
        {
          v17 = LocalAlloc(0x40u, 4LL * v16);
          v18 = v17;
          if ( v17 )
          {
            if ( ReadFile(hFile, v17, nNumberOfBytesToRead[1], NumberOfBytesRead, 0)
              && NumberOfBytesRead[0] == nNumberOfBytesToRead[1] )
            {
              for ( i = 0; (unsigned int)i < v23.m128i_i32[3]; i = (unsigned int)(i + 1) )
              {
                if ( v18[i] == PR_WAB_FOLDER_PARENT || v18[i] == 1712066818 )
                {
                  v10 = 1;
                  break;
                }
              }
            }
            LocalFree(v18);
          }
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800450b8  push    rbp
0x1800450ba  push    rbx
0x1800450bb  push    rsi
0x1800450bc  push    rdi
0x1800450bd  push    r12
0x1800450bf  push    r14
0x1800450c1  push    r15
0x1800450c3  lea     rbp, [rsp-27h]
0x1800450c8  sub     rsp, 90h
0x1800450cf  mov     rax, cs:__security_cookie
0x1800450d6  xor     rax, rsp
0x1800450d9  mov     [rbp+57h+var_40], rax
0x1800450dd  mov     r14, [rdx+28h]
0x1800450e1  mov     r12d, r8d
0x1800450e4  mov     r8, [rdx+18h]
0x1800450e8  mov     rbx, r9
0x1800450eb  mov     r15, rdx
0x1800450ee  lea     r9, [rbp+57h+NumberOfBytesRead]; unsigned int *
0x1800450f2  mov     rsi, rcx
0x1800450f5  xor     edi, edi
0x1800450f7  mov     edx, r12d; unsigned int
0x1800450fa  mov     [rbp+57h+NumberOfBytesRead], edi
0x1800450fd  mov     r8d, [r8+24h]; unsigned int
0x180045101  mov     rcx, r14; struct _tagMPSWabIndexEntryDataEntryID *
0x180045104  call    ?BinSearchEID@@YAHPEAU_tagMPSWabIndexEntryDataEntryID@@KKPEAK@Z; BinSearchEID(_tagMPSWabIndexEntryDataEntryID *,ulong,ulong,ulong *)
0x180045109  test    eax, eax
0x18004510b  jz      loc_180045215
0x180045111  mov     eax, [rbp+57h+NumberOfBytesRead]
0x180045114  lea     r9d, [rdi+20h]; unsigned int
0x180045118  xorps   xmm0, xmm0
0x18004511b  mov     [rbp+57h+NumberOfBytesRead], edi
0x18004511e  lea     r8, [rbp+57h+var_60]; void *
0x180045122  mov     rcx, rsi; hFile
0x180045125  movups  [rbp+57h+var_60], xmm0
0x180045129  mov     r14d, [r14+rax*8+4]
0x18004512e  mov     edx, r14d; unsigned int
0x180045131  movups  xmmword ptr [rbp+57h+nNumberOfBytesToRead], xmm0
0x180045135  call    ?ReadDataFromWABFile@@YAHPEAXK0K@Z; ReadDataFromWABFile(void *,ulong,void *,ulong)
0x18004513a  test    eax, eax
0x18004513c  jz      loc_180045215
0x180045142  xor     edx, edx; lpFileSizeHigh
0x180045144  mov     rcx, rsi; hFile
0x180045147  call    cs:__imp_GetFileSize
0x18004514d  mov     rdx, [r15+18h]
0x180045151  lea     rcx, [rbp+57h+var_80]
0x180045155  movups  xmm1, [rbp+57h+var_60]
0x180045159  lea     r15d, [rdi+1]
0x18004515d  mov     [rsp+0C0h+var_98], r12d
0x180045162  movups  xmm0, xmmword ptr [rbp+57h+nNumberOfBytesToRead]
0x180045166  mov     edx, [rdx+14h]
0x180045169  mov     r9d, eax
0x18004516c  mov     r8d, r14d
0x18004516f  movaps  [rbp+57h+var_80], xmm1
0x180045173  movaps  [rbp+57h+var_70], xmm0
0x180045177  mov     dword ptr [rsp+0C0h+lpOverlapped], r15d
0x18004517c  call    ?bIsValidRecord@@YAHU_tagMPSWabRecordHeader@@KKKHK@Z; bIsValidRecord(_tagMPSWabRecordHeader,ulong,ulong,ulong,int,ulong)
0x180045181  test    eax, eax
0x180045183  jz      loc_180045215
0x180045189  test    rbx, rbx
0x18004518c  jz      short loc_18004519B
0x18004518e  movdqa  xmm0, xmm1
0x180045192  psrldq  xmm0, 4
0x180045197  movd    dword ptr [rbx], xmm0
0x18004519b  psrldq  xmm1, 0Ch
0x1800451a0  movd    eax, xmm1
0x1800451a4  cmp     eax, 3FFFFFFFh
0x1800451a9  ja      short loc_180045215
0x1800451ab  mov     edx, eax
0x1800451ad  mov     ecx, 40h ; '@'; uFlags
0x1800451b2  shl     rdx, 2; uBytes
0x1800451b6  call    cs:__imp_LocalAlloc
0x1800451bc  mov     rbx, rax
0x1800451bf  test    rax, rax
0x1800451c2  jz      short loc_180045215
0x1800451c4  mov     r8d, [rbp+57h+nNumberOfBytesToRead+4]; nNumberOfBytesToRead
0x1800451c8  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800451cc  mov     rdx, rax; lpBuffer
0x1800451cf  mov     [rsp+0C0h+lpOverlapped], rdi; lpOverlapped
0x1800451d4  mov     rcx, rsi; hFile
0x1800451d7  call    cs:__imp_ReadFile
0x1800451dd  test    eax, eax
0x1800451df  jz      short loc_18004520C
0x1800451e1  mov     ecx, [rbp+57h+nNumberOfBytesToRead+4]
0x1800451e4  cmp     [rbp+57h+NumberOfBytesRead], ecx
0x1800451e7  jnz     short loc_18004520C
0x1800451e9  mov     edx, cs:?PR_WAB_FOLDER_PARENT@@3KA; ulong PR_WAB_FOLDER_PARENT
0x1800451ef  xor     ecx, ecx
0x1800451f1  cmp     ecx, dword ptr [rbp+57h+var_60+0Ch]
0x1800451f4  jnb     short loc_18004520C
0x1800451f6  cmp     [rbx+rcx*4], edx
0x1800451f9  jz      short loc_180045209
0x1800451fb  cmp     dword ptr [rbx+rcx*4], 660C1102h
0x180045202  jz      short loc_180045209
0x180045204  add     ecx, r15d
0x180045207  jmp     short loc_1800451F1
0x180045209  mov     edi, r15d
0x18004520c  mov     rcx, rbx; hMem
0x18004520f  call    cs:__imp_LocalFree
0x180045215  mov     eax, edi
0x180045217  mov     rcx, [rbp+57h+var_40]
0x18004521b  xor     rcx, rsp; StackCookie
0x18004521e  call    __security_check_cookie
0x180045223  add     rsp, 90h
0x18004522a  pop     r15
0x18004522c  pop     r14
0x18004522e  pop     r12
0x180045230  pop     rdi
0x180045231  pop     rsi
0x180045232  pop     rbx
0x180045233  pop     rbp
0x180045234  retn
```
