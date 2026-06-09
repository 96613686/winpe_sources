# ChunkWriterEnqueue

- ea: `0x18001da04`
- end: `0x18001dea2`
- name: `ChunkWriterEnqueue`
- size: `1182`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a874`

## callees

- `0x18000ea60`
- `0x180010938`
- `0x180011cc4`
- `0x18001da04`
- `0x18001dea8`
- `0x18001f8c8`
- `0x18001f944`
- `0x1800219c4`
- `0x180023bb4`
- `0x1800607b0`
- `0x180060e42`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001dad3`
- `KERNEL32!GetLastError` at `0x18001daf2`
- `KERNEL32!GetLastError` at `0x18001db6c`
- `KERNEL32!GetLastError` at `0x18001db8b`
- `KERNEL32!GetLastError` at `0x18001ddc1`
- `KERNEL32!GetLastError` at `0x18001dde0`
- `KERNEL32!GetLastError` at `0x18001dad3`
- `KERNEL32!GetLastError` at `0x18001daf2`
- `KERNEL32!GetLastError` at `0x18001db6c`
- `KERNEL32!GetLastError` at `0x18001db8b`
- `KERNEL32!GetLastError` at `0x18001ddc1`
- `KERNEL32!GetLastError` at `0x18001dde0`
- `KERNEL32!GetFileSizeEx` at `0x18001dac3`
- `KERNEL32!GetFileSizeEx` at `0x18001dac3`
- `KERNEL32!LocalFree` at `0x18001dd7f`
- `KERNEL32!LocalFree` at `0x18001de6c`
- `KERNEL32!LocalFree` at `0x18001dd7f`
- `KERNEL32!LocalFree` at `0x18001de6c`
- `bcrypt!BCryptDestroyHash` at `0x18001dd70`
- `bcrypt!BCryptDestroyHash` at `0x18001de5d`
- `bcrypt!BCryptDestroyHash` at `0x18001dd70`
- `bcrypt!BCryptDestroyHash` at `0x18001de5d`
- `bcrypt!BCryptFinishHash` at `0x18001dd55`
- `bcrypt!BCryptFinishHash` at `0x18001dd55`
- `bcrypt!BCryptHashData` at `0x18001dc84`
- `bcrypt!BCryptHashData` at `0x18001dc84`
- `bcrypt!BCryptCreateHash` at `0x18001dbfa`
- `bcrypt!BCryptCreateHash` at `0x18001dbfa`

## string_xrefs

- `0x18001da82`: `ChunkWriterEnqueue`
- `0x18001de0f`: `ChunkWriterEnqueue`

## pseudocode

```c
__int64 __fastcall ChunkWriterEnqueue(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  signed int v6; // r12d
  __int64 v7; // rbx
  BCRYPT_HASH_HANDLE *v8; // r13
  __int64 v9; // r8
  int v10; // r14d
  __int64 v11; // rax
  signed int v12; // eax
  signed int v13; // ecx
  signed int v14; // eax
  __int64 v15; // rax
  signed int v16; // eax
  signed int v17; // ecx
  signed int v18; // eax
  void *AlgHandle; // rdi
  LONGLONG QuadPart; // rax
  ULONG v21; // esi
  void *v22; // rcx
  ULONG v23; // r15d
  __int64 v24; // r14
  ULONG v25; // eax
  __int64 v26; // rcx
  ULONG v27; // esi
  __int64 v28; // rdi
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r9
  __int64 v32; // r8
  signed int LastError; // eax
  signed int v34; // ecx
  signed int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rdi
  ULONG v39; // [rsp+40h] [rbp-69h]
  ULONG cbInput; // [rsp+44h] [rbp-65h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-61h] BYREF
  BCRYPT_HASH_HANDLE *phHash; // [rsp+50h] [rbp-59h] BYREF
  int v43; // [rsp+58h] [rbp-51h]
  PUCHAR pbInput; // [rsp+60h] [rbp-49h] BYREF
  __int64 v45; // [rsp+68h] [rbp-41h]
  __int64 v46; // [rsp+70h] [rbp-39h]
  _QWORD *v47; // [rsp+78h] [rbp-31h]
  __int64 v48; // [rsp+80h] [rbp-29h]
  __int64 v49; // [rsp+88h] [rbp-21h]
  __int64 v50; // [rsp+90h] [rbp-19h]
  int v51; // [rsp+98h] [rbp-11h]
  int v52; // [rsp+9Ch] [rbp-Dh]
  __int64 v53; // [rsp+A0h] [rbp-9h]
  UCHAR pbOutput[8]; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v55; // [rsp+B0h] [rbp+7h]
  int v56; // [rsp+B8h] [rbp+Fh]

  v48 = a1;
  v3 = a1;
  v45 = a3;
  v47 = a2;
  v4 = a3;
  v6 = 0;
  pbInput = 0;
  v7 = 0;
  cbInput = 0;
  v8 = 0;
  v46 = 0;
  FileSize.QuadPart = 0;
  *(_QWORD *)pbOutput = 0;
  v55 = 0;
  v56 = 0;
  phHash = 0;
  if ( !a2[5] )
  {
    v6 = -2147024809;
    v9 = 528;
LABEL_3:
    UtilReportError(L"ChunkWriterEnqueue", a2, v9, (unsigned int)v6);
    return (unsigned int)v6;
  }
  v43 = 0;
  v10 = 0;
  if ( a1 )
  {
    v11 = a1;
    if ( *(_QWORD *)(a1 + 64) )
      v11 = *(_QWORD *)(a1 + 64);
    if ( (*(_BYTE *)(v11 + 36) & 2) != 0 )
      v10 = 1;
    v43 = v10;
  }
  if ( GetFileSizeEx(*(HANDLE *)(a3 + 40), &FileSize) )
  {
    v15 = a2[4] + a2[2];
    *(_BYTE *)(v4 + 95) |= 0x10u;
    *(_QWORD *)(v4 + 96) = v15;
    *(_QWORD *)(v4 + 104) = 0;
    UpdateOffsetTableEntry(v4);
    a2[4] += FileSize.QuadPart;
    if ( (unsigned int)GetImageBuffers(v3, (unsigned int)&pbInput, (unsigned int)&cbInput, 0, 0) )
    {
      if ( v10 )
      {
        AlgHandle = (void *)p_GetAlgHandle();
        CngRsa32Compat_Alloc_ALState(AlgHandle, &phHash);
        v8 = phHash;
        if ( BCryptCreateHash(AlgHandle, phHash, (PUCHAR)phHash[1], *((_DWORD *)phHash + 4), 0, 0, 0) < 0 )
          __fastfail(7u);
        v4 = v45;
      }
      LODWORD(QuadPart) = FileSize.LowPart;
      if ( FileSize.QuadPart )
      {
        while ( 1 )
        {
          v21 = cbInput;
          phHash = (BCRYPT_HASH_HANDLE *)pbInput;
          v49 = 0;
          v50 = 0;
          v53 = 0;
          if ( !FileSize.HighPart && (unsigned int)QuadPart < cbInput )
            v21 = QuadPart;
          v22 = *(void **)(v4 + 40);
          v52 = HIDWORD(v46);
          v39 = v21;
          v51 = v7;
          if ( !(unsigned int)ReadWriteData(v22, 0) )
            break;
          if ( v10 && BCryptHashData(*v8, pbInput, v21, 0) < 0 )
            __fastfail(7u);
          v7 += v21;
          QuadPart = FileSize.QuadPart - v21;
          v46 = v7;
          FileSize.QuadPart = QuadPart;
          if ( v21 )
          {
            do
            {
              v23 = v21;
              v24 = v47[5];
              v25 = v39;
              v26 = *(unsigned int *)(v24 + 48);
              v27 = *(_DWORD *)(v24 + 52) - v26;
              if ( v39 >= v27 )
                v25 = *(_DWORD *)(v24 + 52) - v26;
              v28 = v25;
              memcpy_0((void *)(v24 + v26 + 72), phHash, v25);
              phHash = (BCRYPT_HASH_HANDLE *)((char *)phHash + v28);
              v39 -= v28;
              *(_DWORD *)(v24 + 48) += v28;
              if ( v23 >= v27 )
              {
                v29 = ChunkWriterFlush(v48, v47);
                v6 = v29;
                if ( v29 < 0 )
                {
                  v31 = (unsigned int)v29;
                  v32 = 655;
                  goto LABEL_68;
                }
              }
              v21 = v39;
            }
            while ( v39 );
            QuadPart = FileSize.QuadPart;
            v4 = v45;
            v10 = v43;
          }
          if ( !QuadPart )
          {
            v3 = v48;
            goto LABEL_52;
          }
        }
        LastError = GetLastError();
        v34 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v34 = LastError;
        if ( v34 >= 0 )
        {
          v6 = -2147467259;
        }
        else
        {
          v35 = GetLastError();
          v6 = (unsigned __int16)v35 | 0x80070000;
          if ( v35 <= 0 )
            v6 = v35;
        }
        if ( v6 < 0 )
        {
          v31 = (unsigned int)v6;
          v32 = 598;
LABEL_68:
          UtilReportError(L"ChunkWriterEnqueue", v30, v32, v31);
        }
      }
      else
      {
LABEL_52:
        if ( v10 )
        {
          if ( BCryptFinishHash(*v8, pbOutput, 0x14u, 0) < 0 )
            __fastfail(7u);
          BCryptDestroyHash(*v8);
          LocalFree(v8);
          v8 = 0;
          if ( *(_QWORD *)pbOutput != *(_QWORD *)(v4 + 120)
            || v55 != *(_QWORD *)(v4 + 128)
            || v56 != *(_DWORD *)(v4 + 136) )
          {
            v6 = -2147023504;
            v9 = 675;
            goto LABEL_3;
          }
        }
        if ( *(_DWORD *)(v4 + 160) )
        {
          v36 = 0;
          v37 = v4 + 80;
          if ( v37 )
          {
            if ( (*(_BYTE *)(v37 + 15) & 0x10) != 0 )
              v36 = *(_QWORD *)(v37 + 8) & 0xFFFFFFFFFFFFFFLL;
            else
              v36 = *(_QWORD *)(v37 + 24);
          }
          CopyProgressUpdate(v3, v36);
        }
      }
      if ( v8 )
      {
        BCryptDestroyHash(*v8);
        LocalFree(v8);
      }
    }
    else
    {
      v16 = GetLastError();
      v17 = (unsigned __int16)v16 | 0x80070000;
      if ( v16 <= 0 )
        v17 = v16;
      if ( v17 >= 0 )
      {
        v6 = -2147467259;
      }
      else
      {
        v18 = GetLastError();
        v6 = (unsigned __int16)v18 | 0x80070000;
        if ( v18 <= 0 )
          v6 = v18;
      }
      if ( v6 < 0 )
      {
        v9 = 560;
        goto LABEL_3;
      }
    }
  }
  else
  {
    v12 = GetLastError();
    v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v12 <= 0 )
      v13 = v12;
    if ( v13 >= 0 )
    {
      v6 = -2147467259;
    }
    else
    {
      v14 = GetLastError();
      v6 = (unsigned __int16)v14 | 0x80070000;
      if ( v14 <= 0 )
        v6 = v14;
    }
    if ( v6 < 0 )
    {
      v9 = 540;
      goto LABEL_3;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001da04  mov     [rsp-8+arg_18], rbx
0x18001da09  push    rbp
0x18001da0a  push    rsi
0x18001da0b  push    rdi
0x18001da0c  push    r12
0x18001da0e  push    r13
0x18001da10  push    r14
0x18001da12  push    r15
0x18001da14  lea     rbp, [rsp-27h]
0x18001da19  sub     rsp, 0D0h
0x18001da20  mov     rax, cs:__security_cookie
0x18001da27  xor     rax, rsp
0x18001da2a  mov     [rbp+57h+var_40], rax
0x18001da2e  xor     eax, eax
0x18001da30  mov     [rbp+57h+var_80], rcx
0x18001da34  mov     rsi, rcx
0x18001da37  mov     [rbp+57h+var_98], r8
0x18001da3b  xor     ecx, ecx
0x18001da3d  mov     [rbp+57h+var_88], rdx
0x18001da41  mov     rdi, r8
0x18001da44  mov     r15, rdx
0x18001da47  mov     r12d, ecx
0x18001da4a  mov     [rbp+57h+pbInput], rcx
0x18001da4e  mov     ebx, ecx
0x18001da50  mov     [rbp+57h+cbInput], ecx
0x18001da53  mov     r13d, ecx
0x18001da56  mov     [rbp+57h+var_90], rcx
0x18001da5a  mov     qword ptr [rbp+57h+FileSize], rcx
0x18001da5e  mov     qword ptr [rbp+57h+pbOutput], rax
0x18001da62  mov     [rbp+57h+var_50], rax
0x18001da66  mov     [rbp+57h+var_48], eax
0x18001da69  mov     [rbp+57h+phHash], rcx
0x18001da6d  cmp     [rdx+28h], rcx
0x18001da71  jnz     short loc_18001DA93
0x18001da73  mov     r12d, 80070057h
0x18001da79  mov     r8d, 210h
0x18001da7f  mov     r9d, r12d
0x18001da82  lea     rcx, aChunkwriterenq; "ChunkWriterEnqueue"
0x18001da89  call    UtilReportError
0x18001da8e  jmp     loc_18001DE78
0x18001da93  mov     [rbp+57h+var_A8], ecx
0x18001da96  mov     r14d, ecx
0x18001da99  test    rsi, rsi
0x18001da9c  jz      short loc_18001DABB
0x18001da9e  cmp     [rsi+40h], rcx
0x18001daa2  mov     rax, rsi
0x18001daa5  cmovnz  rax, [rsi+40h]
0x18001daaa  test    byte ptr [rax+24h], 2
0x18001daae  mov     eax, 1
0x18001dab3  cmovnz  r14d, eax
0x18001dab7  mov     [rbp+57h+var_A8], r14d
0x18001dabb  mov     rcx, [r8+28h]; hFile
0x18001dabf  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x18001dac3  call    cs:__imp_GetFileSizeEx
0x18001daca  nop     dword ptr [rax+rax+00h]
0x18001dacf  test    eax, eax
0x18001dad1  jnz     short loc_18001DB27
0x18001dad3  call    cs:__imp_GetLastError
0x18001dada  nop     dword ptr [rax+rax+00h]
0x18001dadf  movzx   ecx, ax
0x18001dae2  mov     ebx, 80070000h
0x18001dae7  or      ecx, ebx
0x18001dae9  test    eax, eax
0x18001daeb  cmovle  ecx, eax
0x18001daee  test    ecx, ecx
0x18001daf0  jns     short loc_18001DB0D
0x18001daf2  call    cs:__imp_GetLastError
0x18001daf9  nop     dword ptr [rax+rax+00h]
0x18001dafe  movzx   r12d, ax
0x18001db02  or      r12d, ebx
0x18001db05  test    eax, eax
0x18001db07  cmovle  r12d, eax
0x18001db0b  jmp     short loc_18001DB13
0x18001db0d  mov     r12d, 80004005h
0x18001db13  test    r12d, r12d
0x18001db16  jns     loc_18001DE78
0x18001db1c  mov     r8d, 21Ch
0x18001db22  jmp     loc_18001DA7F
0x18001db27  mov     rax, [r15+10h]
0x18001db2b  mov     rcx, rdi
0x18001db2e  add     rax, [r15+20h]
0x18001db32  or      byte ptr [rdi+5Fh], 10h
0x18001db36  mov     [rdi+60h], rax
0x18001db3a  xor     eax, eax
0x18001db3c  mov     [rdi+68h], rax
0x18001db40  call    UpdateOffsetTableEntry
0x18001db45  mov     rax, qword ptr [rbp+57h+FileSize]
0x18001db49  lea     r8, [rbp+57h+cbInput]
0x18001db4d  add     [r15+20h], rax
0x18001db51  lea     rdx, [rbp+57h+pbInput]
0x18001db55  xor     r15d, r15d
0x18001db58  xor     r9d, r9d
0x18001db5b  mov     rcx, rsi
0x18001db5e  mov     [rsp+100h+pbSecret], r15
0x18001db63  call    GetImageBuffers
0x18001db68  test    eax, eax
0x18001db6a  jnz     short loc_18001DBC0
0x18001db6c  call    cs:__imp_GetLastError
0x18001db73  nop     dword ptr [rax+rax+00h]
0x18001db78  movzx   ecx, ax
0x18001db7b  mov     ebx, 80070000h
0x18001db80  or      ecx, ebx
0x18001db82  test    eax, eax
0x18001db84  cmovle  ecx, eax
0x18001db87  test    ecx, ecx
0x18001db89  jns     short loc_18001DBA6
0x18001db8b  call    cs:__imp_GetLastError
0x18001db92  nop     dword ptr [rax+rax+00h]
0x18001db97  movzx   r12d, ax
0x18001db9b  or      r12d, ebx
0x18001db9e  test    eax, eax
0x18001dba0  cmovle  r12d, eax
0x18001dba4  jmp     short loc_18001DBAC
0x18001dba6  mov     r12d, 80004005h
0x18001dbac  test    r12d, r12d
0x18001dbaf  jns     loc_18001DE78
0x18001dbb5  mov     r8d, 230h
0x18001dbbb  jmp     loc_18001DA7F
0x18001dbc0  test    r14d, r14d
0x18001dbc3  jz      short loc_18001DC15
0x18001dbc5  call    p_GetAlgHandle
0x18001dbca  lea     rdx, [rbp+57h+phHash]
0x18001dbce  mov     rcx, rax
0x18001dbd1  mov     rdi, rax
0x18001dbd4  call    CngRsa32Compat_Alloc_ALState
0x18001dbd9  mov     r13, [rbp+57h+phHash]
0x18001dbdd  mov     rcx, rdi; hAlgorithm
0x18001dbe0  mov     [rsp+100h+dwFlags], r15d; dwFlags
0x18001dbe5  mov     rdx, r13; phHash
0x18001dbe8  mov     [rsp+100h+cbSecret], r15d; cbSecret
0x18001dbed  mov     [rsp+100h+pbSecret], r15; pbSecret
0x18001dbf2  mov     r9d, [r13+10h]; cbHashObject
0x18001dbf6  mov     r8, [r13+8]; pbHashObject
0x18001dbfa  call    cs:__imp_BCryptCreateHash
0x18001dc01  nop     dword ptr [rax+rax+00h]
0x18001dc06  test    eax, eax
0x18001dc08  jns     short loc_18001DC11
0x18001dc0a  mov     ecx, 7
0x18001dc0f  int     29h; Win8: RtlFailFast(ecx)
0x18001dc11  mov     rdi, [rbp+57h+var_98]
0x18001dc15  mov     rax, qword ptr [rbp+57h+FileSize]
0x18001dc19  test    rax, rax
0x18001dc1c  jz      loc_18001DD3D
0x18001dc22  mov     rcx, [rbp+57h+pbInput]
0x18001dc26  mov     esi, [rbp+57h+cbInput]
0x18001dc29  mov     [rbp+57h+phHash], rcx
0x18001dc2d  mov     [rbp+57h+var_78], r15
0x18001dc31  mov     [rbp+57h+var_70], r15
0x18001dc35  mov     [rbp+57h+var_60], r15
0x18001dc39  cmp     dword ptr [rbp+57h+FileSize+4], r15d
0x18001dc3d  jnz     short loc_18001DC44
0x18001dc3f  cmp     eax, esi
0x18001dc41  cmovb   esi, eax
0x18001dc44  mov     eax, dword ptr [rbp+57h+var_90+4]
0x18001dc47  lea     r9, [rbp+57h+var_78]
0x18001dc4b  mov     rdx, [rbp+57h+pbInput]
0x18001dc4f  mov     r8d, esi
0x18001dc52  mov     rcx, [rdi+28h]; hFile
0x18001dc56  mov     [rbp+57h+var_64], eax
0x18001dc59  mov     [rbp+57h+var_C0], esi
0x18001dc5c  mov     [rbp+57h+var_68], ebx
0x18001dc5f  mov     dword ptr [rsp+100h+pbSecret], r15d; DWORD
0x18001dc64  call    ReadWriteData
0x18001dc69  test    eax, eax
0x18001dc6b  jz      loc_18001DDC1
0x18001dc71  test    r14d, r14d
0x18001dc74  jz      short loc_18001DC9B
0x18001dc76  mov     rdx, [rbp+57h+pbInput]; pbInput
0x18001dc7a  xor     r9d, r9d; dwFlags
0x18001dc7d  mov     rcx, [r13+0]; hHash
0x18001dc81  mov     r8d, esi; cbInput
0x18001dc84  call    cs:__imp_BCryptHashData
0x18001dc8b  nop     dword ptr [rax+rax+00h]
0x18001dc90  test    eax, eax
0x18001dc92  jns     short loc_18001DC9B
0x18001dc94  mov     ecx, 7
0x18001dc99  int     29h; Win8: RtlFailFast(ecx)
0x18001dc9b  mov     rax, qword ptr [rbp+57h+FileSize]
0x18001dc9f  mov     ecx, esi
0x18001dca1  add     rbx, rcx
0x18001dca4  sub     rax, rcx
0x18001dca7  mov     [rbp+57h+var_90], rbx
0x18001dcab  mov     qword ptr [rbp+57h+FileSize], rax
0x18001dcaf  test    esi, esi
0x18001dcb1  jz      short loc_18001DD30
0x18001dcb3  mov     rax, [rbp+57h+var_88]
0x18001dcb7  mov     r15d, esi
0x18001dcba  mov     rdx, [rbp+57h+phHash]; Src
0x18001dcbe  mov     r14, [rax+28h]
0x18001dcc2  mov     eax, [rbp+57h+var_C0]
0x18001dcc5  mov     ecx, [r14+30h]
0x18001dcc9  mov     esi, [r14+34h]
0x18001dccd  sub     esi, ecx
0x18001dccf  cmp     eax, esi
0x18001dcd1  cmovnb  eax, esi
0x18001dcd4  add     rcx, 48h ; 'H'
0x18001dcd8  add     rcx, r14; void *
0x18001dcdb  mov     r8d, eax; Size
0x18001dcde  mov     edi, eax
0x18001dce0  call    memcpy_0
0x18001dce5  add     [rbp+57h+phHash], rdi
0x18001dce9  sub     [rbp+57h+var_C0], edi
0x18001dcec  add     [r14+30h], edi
0x18001dcf0  cmp     r15d, esi
0x18001dcf3  jb      short loc_18001DD1A
0x18001dcf5  mov     rdx, [rbp+57h+var_88]
0x18001dcf9  mov     rcx, [rbp+57h+var_80]
0x18001dcfd  call    ChunkWriterFlush
0x18001dd02  xor     r15d, r15d
0x18001dd05  mov     r12d, eax
0x18001dd08  test    eax, eax
0x18001dd0a  jns     short loc_18001DD1D
0x18001dd0c  mov     r9d, eax
0x18001dd0f  mov     r8d, 28Fh
0x18001dd15  jmp     loc_18001DE0F
0x18001dd1a  xor     r15d, r15d
0x18001dd1d  mov     esi, [rbp+57h+var_C0]
0x18001dd20  test    esi, esi
0x18001dd22  jnz     short loc_18001DCB3
0x18001dd24  mov     rax, qword ptr [rbp+57h+FileSize]
0x18001dd28  mov     rdi, [rbp+57h+var_98]
0x18001dd2c  mov     r14d, [rbp+57h+var_A8]
0x18001dd30  test    rax, rax
0x18001dd33  jnz     loc_18001DC22
0x18001dd39  mov     rsi, [rbp+57h+var_80]
0x18001dd3d  test    r14d, r14d
0x18001dd40  jz      loc_18001DE1D
0x18001dd46  mov     rcx, [r13+0]; hHash
0x18001dd4a  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x18001dd4e  xor     r9d, r9d; dwFlags
0x18001dd51  lea     r8d, [r9+14h]; cbOutput
0x18001dd55  call    cs:__imp_BCryptFinishHash
0x18001dd5c  nop     dword ptr [rax+rax+00h]
0x18001dd61  test    eax, eax
0x18001dd63  jns     short loc_18001DD6C
0x18001dd65  mov     ecx, 7
0x18001dd6a  int     29h; Win8: RtlFailFast(ecx)
0x18001dd6c  mov     rcx, [r13+0]; hHash
0x18001dd70  call    cs:__imp_BCryptDestroyHash
0x18001dd77  nop     dword ptr [rax+rax+00h]
0x18001dd7c  mov     rcx, r13; hMem
0x18001dd7f  call    cs:__imp_LocalFree
0x18001dd86  nop     dword ptr [rax+rax+00h]
0x18001dd8b  mov     rax, qword ptr [rbp+57h+pbOutput]
0x18001dd8f  mov     r13, r15
0x18001dd92  cmp     rax, [rdi+78h]
0x18001dd96  jnz     short loc_18001DDB0
0x18001dd98  mov     rax, [rbp+57h+var_50]
0x18001dd9c  cmp     rax, [rdi+80h]
0x18001dda3  jnz     short loc_18001DDB0
0x18001dda5  mov     eax, [rbp+57h+var_48]
0x18001dda8  cmp     eax, [rdi+88h]
0x18001ddae  jz      short loc_18001DE1D
0x18001ddb0  mov     r12d, 80070570h
0x18001ddb6  mov     r8d, 2A3h
0x18001ddbc  jmp     loc_18001DA7F
0x18001ddc1  call    cs:__imp_GetLastError
0x18001ddc8  nop     dword ptr [rax+rax+00h]
0x18001ddcd  movzx   ecx, ax
0x18001ddd0  mov     ebx, 80070000h
0x18001ddd5  or      ecx, ebx
0x18001ddd7  test    eax, eax
0x18001ddd9  cmovle  ecx, eax
0x18001dddc  test    ecx, ecx
0x18001ddde  jns     short loc_18001DDFB
0x18001dde0  call    cs:__imp_GetLastError
0x18001dde7  nop     dword ptr [rax+rax+00h]
0x18001ddec  movzx   r12d, ax
0x18001ddf0  or      r12d, ebx
0x18001ddf3  test    eax, eax
0x18001ddf5  cmovle  r12d, eax
0x18001ddf9  jmp     short loc_18001DE01
0x18001ddfb  mov     r12d, 80004005h
0x18001de01  test    r12d, r12d
0x18001de04  jns     short loc_18001DE54
0x18001de06  mov     r9d, r12d
0x18001de09  mov     r8d, 256h
0x18001de0f  lea     rcx, aChunkwriterenq; "ChunkWriterEnqueue"
0x18001de16  call    UtilReportError
0x18001de1b  jmp     short loc_18001DE54
0x18001de1d  cmp     [rdi+0A0h], r15d
0x18001de24  jz      short loc_18001DE54
0x18001de26  mov     rdx, r15
0x18001de29  add     rdi, 50h ; 'P'
0x18001de2d  jz      short loc_18001DE4C
0x18001de2f  test    byte ptr [rdi+0Fh], 10h
0x18001de33  jz      short loc_18001DE48
0x18001de35  mov     rdx, [rdi+8]
0x18001de39  mov     rax, 0FFFFFFFFFFFFFFh
0x18001de43  and     rdx, rax
0x18001de46  jmp     short loc_18001DE4C
0x18001de48  mov     rdx, [rdi+18h]
0x18001de4c  mov     rcx, rsi
0x18001de4f  call    CopyProgressUpdate
0x18001de54  test    r13, r13
0x18001de57  jz      short loc_18001DE78
0x18001de59  mov     rcx, [r13+0]; hHash
0x18001de5d  call    cs:__imp_BCryptDestroyHash
0x18001de64  nop     dword ptr [rax+rax+00h]
0x18001de69  mov     rcx, r13; hMem
  ... truncated ...
```
