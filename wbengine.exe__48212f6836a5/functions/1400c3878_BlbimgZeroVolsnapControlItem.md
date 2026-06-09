# BlbimgZeroVolsnapControlItem

- ea: `0x1400c3878`
- end: `0x1400c3c77`
- name: `BlbimgZeroVolsnapControlItem`
- size: `1023`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14002d6c4`
- `0x140108698`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x1400c3878`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1400c3a63`
- `KERNEL32!SetFilePointer` at `0x1400c3b7e`
- `KERNEL32!SetFilePointer` at `0x1400c3a63`
- `KERNEL32!SetFilePointer` at `0x1400c3b7e`
- `KERNEL32!LocalAlloc` at `0x1400c38e5`
- `KERNEL32!LocalAlloc` at `0x1400c38e5`
- `KERNEL32!ReadFile` at `0x1400c3ac6`
- `KERNEL32!ReadFile` at `0x1400c3ac6`
- `KERNEL32!WriteFile` at `0x1400c3bd3`
- `KERNEL32!WriteFile` at `0x1400c3bd3`
- `KERNEL32!LocalFree` at `0x1400c3c32`
- `KERNEL32!LocalFree` at `0x1400c3c32`
- `KERNEL32!CreateFileW` at `0x1400c3971`
- `KERNEL32!CreateFileW` at `0x1400c3971`
- `KERNEL32!CloseHandle` at `0x1400c3c29`
- `KERNEL32!CloseHandle` at `0x1400c3c29`
- `KERNEL32!GetLastError` at `0x1400c38f3`
- `KERNEL32!GetLastError` at `0x1400c3980`
- `KERNEL32!GetLastError` at `0x1400c3a15`
- `KERNEL32!GetLastError` at `0x1400c3a6d`
- `KERNEL32!GetLastError` at `0x1400c3ad0`
- `KERNEL32!GetLastError` at `0x1400c3b88`
- `KERNEL32!GetLastError` at `0x1400c3bdd`
- `KERNEL32!GetLastError` at `0x1400c38f3`
- `KERNEL32!GetLastError` at `0x1400c3980`
- `KERNEL32!GetLastError` at `0x1400c3a15`
- `KERNEL32!GetLastError` at `0x1400c3a6d`
- `KERNEL32!GetLastError` at `0x1400c3ad0`
- `KERNEL32!GetLastError` at `0x1400c3b88`
- `KERNEL32!GetLastError` at `0x1400c3bdd`
- `KERNEL32!DeviceIoControl` at `0x1400c3a0b`
- `KERNEL32!DeviceIoControl` at `0x1400c3a0b`

## pseudocode

```c
__int64 __fastcall BlbimgZeroVolsnapControlItem(LPCWSTR lpFileName)
{
  _OWORD *v2; // r14
  signed int v3; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v8; // eax
  _QWORD *v9; // rcx
  int v10; // edx
  signed int v11; // eax
  signed int v12; // eax
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  signed int v20; // eax
  signed int v21; // eax
  _OWORD v23[11]; // [rsp+40h] [rbp-59h] BYREF
  DWORD BytesReturned; // [rsp+108h] [rbp+6Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
  }
  BytesReturned = 0;
  memset_0(v23, 0, 0x80u);
  v2 = LocalAlloc(0, 0x10000u);
  if ( v2 )
  {
    FileW = CreateFileW(lpFileName, 0xC0000000, 7u, 0, 3u, 0x2000080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          131,
          (unsigned int)WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids,
          (_DWORD)lpFileName,
          v4);
      }
      goto LABEL_56;
    }
    if ( DeviceIoControl(FileW, 0x90020u, 0, 0, 0, 0, &BytesReturned, 0) )
    {
      if ( SetFilePointer(FileW, 0, 0, 0) )
      {
        v11 = GetLastError();
        v4 = v11;
        if ( v11 > 0 )
          v4 = (unsigned __int16)v11 | 0x80070000;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_55;
        }
        v10 = 133;
      }
      else if ( ReadFile(FileW, v2, 0x10000u, &BytesReturned, 0) )
      {
        v13 = v23[1];
        v2[480] = v23[0];
        v14 = v23[2];
        v2[481] = v13;
        v15 = v23[3];
        v2[482] = v14;
        v16 = v23[4];
        v2[483] = v15;
        v17 = v23[5];
        v2[484] = v16;
        v18 = v23[6];
        v2[485] = v17;
        v19 = v23[7];
        v2[486] = v18;
        v2[487] = v19;
        if ( SetFilePointer(FileW, 0, 0, 0) )
        {
          v20 = GetLastError();
          v4 = v20;
          if ( v20 > 0 )
            v4 = (unsigned __int16)v20 | 0x80070000;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_55;
          }
          v10 = 135;
        }
        else
        {
          v4 = 0;
          if ( WriteFile(FileW, v2, 0x10000u, &BytesReturned, 0) )
            goto LABEL_55;
          v21 = GetLastError();
          v4 = v21;
          if ( v21 > 0 )
            v4 = (unsigned __int16)v21 | 0x80070000;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_55;
          }
          v10 = 136;
        }
      }
      else
      {
        v12 = GetLastError();
        v4 = v12;
        if ( v12 > 0 )
          v4 = (unsigned __int16)v12 | 0x80070000;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_55;
        }
        v10 = 134;
      }
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_55;
      }
      v10 = 132;
    }
    WPP_SF_Sd(v9[2], v10, (unsigned int)WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids, (_DWORD)lpFileName, v4);
LABEL_55:
    CloseHandle(FileW);
LABEL_56:
    LocalFree(v2);
    goto LABEL_57;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_58:
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        WPP_SF_(v5[2], 137, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
      return v4;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
LABEL_57:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_58;
  }
  return v4;
}

```

## disassembly

```asm
0x1400c3878  push    rbp
0x1400c387a  push    rbx
0x1400c387b  push    rsi
0x1400c387c  push    rdi
0x1400c387d  push    r13
0x1400c387f  push    r14
0x1400c3881  lea     rbp, [rsp-2Fh]
0x1400c3886  sub     rsp, 0C8h
0x1400c388d  mov     rdi, rcx
0x1400c3890  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3897  lea     r13, WPP_GLOBAL_Control
0x1400c389e  cmp     rcx, r13
0x1400c38a1  jz      short loc_1400C38C4
0x1400c38a3  test    byte ptr [rcx+1Ch], 4
0x1400c38a7  jz      short loc_1400C38C4
0x1400c38a9  cmp     byte ptr [rcx+19h], 4
0x1400c38ad  jb      short loc_1400C38C4
0x1400c38af  mov     rcx, [rcx+10h]
0x1400c38b3  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400c38ba  mov     edx, 81h
0x1400c38bf  call    WPP_SF_
0x1400c38c4  xor     edx, edx; Val
0x1400c38c6  mov     [rbp+57h+BytesReturned], 0
0x1400c38cd  mov     r8d, 80h; Size
0x1400c38d3  lea     rcx, [rbp+57h+var_B0]; void *
0x1400c38d7  call    memset_0
0x1400c38dc  mov     ebx, 10000h
0x1400c38e1  xor     ecx, ecx; uFlags
0x1400c38e3  mov     edx, ebx; uBytes
0x1400c38e5  call    cs:__imp_LocalAlloc
0x1400c38eb  mov     r14, rax
0x1400c38ee  test    rax, rax
0x1400c38f1  jnz     short loc_1400C3949
0x1400c38f3  call    cs:__imp_GetLastError
0x1400c38f9  mov     ebx, eax
0x1400c38fb  test    eax, eax
0x1400c38fd  jle     short loc_1400C3908
0x1400c38ff  movzx   ebx, ax
0x1400c3902  or      ebx, 80070000h
0x1400c3908  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c390f  cmp     rcx, r13
0x1400c3912  jz      loc_1400C3C65
0x1400c3918  test    byte ptr [rcx+1Ch], 4
0x1400c391c  jz      loc_1400C3C3F
0x1400c3922  cmp     byte ptr [rcx+19h], 2
0x1400c3926  jb      loc_1400C3C3F
0x1400c392c  mov     rcx, [rcx+10h]
0x1400c3930  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400c3937  mov     edx, 82h
0x1400c393c  mov     r9d, ebx
0x1400c393f  call    WPP_SF_d
0x1400c3944  jmp     loc_1400C3C38
0x1400c3949  xor     r9d, r9d; lpSecurityAttributes
0x1400c394c  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x1400c3955  mov     [rsp+0F0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1400c395d  mov     edx, 0C0000000h; dwDesiredAccess
0x1400c3962  mov     rcx, rdi; lpFileName
0x1400c3965  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x1400c396d  lea     r8d, [r9+7]; dwShareMode
0x1400c3971  call    cs:__imp_CreateFileW
0x1400c3977  mov     rsi, rax
0x1400c397a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400c397e  jnz     short loc_1400C39DA
0x1400c3980  call    cs:__imp_GetLastError
0x1400c3986  mov     ebx, eax
0x1400c3988  test    eax, eax
0x1400c398a  jle     short loc_1400C3995
0x1400c398c  movzx   ebx, ax
0x1400c398f  or      ebx, 80070000h
0x1400c3995  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c399c  cmp     rcx, r13
0x1400c399f  jz      loc_1400C3C2F
0x1400c39a5  test    byte ptr [rcx+1Ch], 4
0x1400c39a9  jz      loc_1400C3C2F
0x1400c39af  cmp     byte ptr [rcx+19h], 2
0x1400c39b3  jb      loc_1400C3C2F
0x1400c39b9  mov     rcx, [rcx+10h]
0x1400c39bd  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400c39c4  mov     edx, 83h
0x1400c39c9  mov     [rsp+0F0h+dwCreationDisposition], ebx
0x1400c39cd  mov     r9, rdi
0x1400c39d0  call    WPP_SF_Sd
0x1400c39d5  jmp     loc_1400C3C2F
0x1400c39da  mov     [rsp+0F0h+lpOverlapped], 0; lpOverlapped
0x1400c39e3  lea     rax, [rbp+57h+BytesReturned]
0x1400c39e7  mov     [rsp+0F0h+hTemplateFile], rax; lpBytesReturned
0x1400c39ec  xor     r9d, r9d; nInBufferSize
0x1400c39ef  mov     [rsp+0F0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1400c39f7  xor     r8d, r8d; lpInBuffer
0x1400c39fa  mov     edx, 90020h; dwIoControlCode
0x1400c39ff  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; lpOutBuffer
0x1400c3a08  mov     rcx, rsi; hDevice
0x1400c3a0b  call    cs:__imp_DeviceIoControl
0x1400c3a11  test    eax, eax
0x1400c3a13  jnz     short loc_1400C3A58
0x1400c3a15  call    cs:__imp_GetLastError
0x1400c3a1b  mov     ebx, eax
0x1400c3a1d  test    eax, eax
0x1400c3a1f  jle     short loc_1400C3A2A
0x1400c3a21  movzx   ebx, ax
0x1400c3a24  or      ebx, 80070000h
0x1400c3a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3a31  cmp     rcx, r13
0x1400c3a34  jz      loc_1400C3C26
0x1400c3a3a  test    byte ptr [rcx+1Ch], 4
0x1400c3a3e  jz      loc_1400C3C26
0x1400c3a44  cmp     byte ptr [rcx+19h], 2
0x1400c3a48  jb      loc_1400C3C26
0x1400c3a4e  mov     edx, 84h
0x1400c3a53  jmp     loc_1400C3C0F
0x1400c3a58  xor     r9d, r9d; dwMoveMethod
0x1400c3a5b  xor     r8d, r8d; lpDistanceToMoveHigh
0x1400c3a5e  xor     edx, edx; lDistanceToMove
0x1400c3a60  mov     rcx, rsi; hFile
0x1400c3a63  call    cs:__imp_SetFilePointer
0x1400c3a69  test    eax, eax
0x1400c3a6b  jz      short loc_1400C3AB0
0x1400c3a6d  call    cs:__imp_GetLastError
0x1400c3a73  mov     ebx, eax
0x1400c3a75  test    eax, eax
0x1400c3a77  jle     short loc_1400C3A82
0x1400c3a79  movzx   ebx, ax
0x1400c3a7c  or      ebx, 80070000h
0x1400c3a82  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3a89  cmp     rcx, r13
0x1400c3a8c  jz      loc_1400C3C26
0x1400c3a92  test    byte ptr [rcx+1Ch], 4
0x1400c3a96  jz      loc_1400C3C26
0x1400c3a9c  cmp     byte ptr [rcx+19h], 2
0x1400c3aa0  jb      loc_1400C3C26
0x1400c3aa6  mov     edx, 85h
0x1400c3aab  jmp     loc_1400C3C0F
0x1400c3ab0  lea     r9, [rbp+57h+BytesReturned]; lpNumberOfBytesRead
0x1400c3ab4  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; lpOverlapped
0x1400c3abd  mov     r8d, ebx; nNumberOfBytesToRead
0x1400c3ac0  mov     rdx, r14; lpBuffer
0x1400c3ac3  mov     rcx, rsi; hFile
0x1400c3ac6  call    cs:__imp_ReadFile
0x1400c3acc  test    eax, eax
0x1400c3ace  jnz     short loc_1400C3B13
0x1400c3ad0  call    cs:__imp_GetLastError
0x1400c3ad6  mov     ebx, eax
0x1400c3ad8  test    eax, eax
0x1400c3ada  jle     short loc_1400C3AE5
0x1400c3adc  movzx   ebx, ax
0x1400c3adf  or      ebx, 80070000h
0x1400c3ae5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3aec  cmp     rcx, r13
0x1400c3aef  jz      loc_1400C3C26
0x1400c3af5  test    byte ptr [rcx+1Ch], 4
0x1400c3af9  jz      loc_1400C3C26
0x1400c3aff  cmp     byte ptr [rcx+19h], 2
0x1400c3b03  jb      loc_1400C3C26
0x1400c3b09  mov     edx, 86h
0x1400c3b0e  jmp     loc_1400C3C0F
0x1400c3b13  movaps  xmm0, [rbp+57h+var_B0]
0x1400c3b17  xor     r9d, r9d; dwMoveMethod
0x1400c3b1a  movaps  xmm1, [rbp+57h+var_A0]
0x1400c3b1e  xor     r8d, r8d; lpDistanceToMoveHigh
0x1400c3b21  movups  xmmword ptr [r14+1E00h], xmm0
0x1400c3b29  xor     edx, edx; lDistanceToMove
0x1400c3b2b  mov     rcx, rsi; hFile
0x1400c3b2e  movaps  xmm0, [rbp+57h+var_90]
0x1400c3b32  movups  xmmword ptr [r14+1E10h], xmm1
0x1400c3b3a  movaps  xmm1, [rbp+57h+var_80]
0x1400c3b3e  movups  xmmword ptr [r14+1E20h], xmm0
0x1400c3b46  movaps  xmm0, [rbp+57h+var_70]
0x1400c3b4a  movups  xmmword ptr [r14+1E30h], xmm1
0x1400c3b52  movaps  xmm1, [rbp+57h+var_60]
0x1400c3b56  movups  xmmword ptr [r14+1E40h], xmm0
0x1400c3b5e  movaps  xmm0, [rbp+57h+var_50]
0x1400c3b62  movups  xmmword ptr [r14+1E50h], xmm1
0x1400c3b6a  movaps  xmm1, [rbp+57h+var_40]
0x1400c3b6e  movups  xmmword ptr [r14+1E60h], xmm0
0x1400c3b76  movups  xmmword ptr [r14+1E70h], xmm1
0x1400c3b7e  call    cs:__imp_SetFilePointer
0x1400c3b84  test    eax, eax
0x1400c3b86  jz      short loc_1400C3BBC
0x1400c3b88  call    cs:__imp_GetLastError
0x1400c3b8e  mov     ebx, eax
0x1400c3b90  test    eax, eax
0x1400c3b92  jle     short loc_1400C3B9D
0x1400c3b94  movzx   ebx, ax
0x1400c3b97  or      ebx, 80070000h
0x1400c3b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3ba4  cmp     rcx, r13
0x1400c3ba7  jz      short loc_1400C3C26
0x1400c3ba9  test    byte ptr [rcx+1Ch], 4
0x1400c3bad  jz      short loc_1400C3C26
0x1400c3baf  cmp     byte ptr [rcx+19h], 2
0x1400c3bb3  jb      short loc_1400C3C26
0x1400c3bb5  mov     edx, 87h
0x1400c3bba  jmp     short loc_1400C3C0F
0x1400c3bbc  xor     ebx, ebx
0x1400c3bbe  lea     r9, [rbp+57h+BytesReturned]; lpNumberOfBytesWritten
0x1400c3bc2  mov     r8d, 10000h; nNumberOfBytesToWrite
0x1400c3bc8  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rbx; lpOverlapped
0x1400c3bcd  mov     rdx, r14; lpBuffer
0x1400c3bd0  mov     rcx, rsi; hFile
0x1400c3bd3  call    cs:__imp_WriteFile
0x1400c3bd9  test    eax, eax
0x1400c3bdb  jnz     short loc_1400C3C26
0x1400c3bdd  call    cs:__imp_GetLastError
0x1400c3be3  mov     ebx, eax
0x1400c3be5  test    eax, eax
0x1400c3be7  jle     short loc_1400C3BF2
0x1400c3be9  movzx   ebx, ax
0x1400c3bec  or      ebx, 80070000h
0x1400c3bf2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3bf9  cmp     rcx, r13
0x1400c3bfc  jz      short loc_1400C3C26
0x1400c3bfe  test    byte ptr [rcx+1Ch], 4
0x1400c3c02  jz      short loc_1400C3C26
0x1400c3c04  cmp     byte ptr [rcx+19h], 2
0x1400c3c08  jb      short loc_1400C3C26
0x1400c3c0a  mov     edx, 88h
0x1400c3c0f  mov     rcx, [rcx+10h]
0x1400c3c13  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400c3c1a  mov     r9, rdi
0x1400c3c1d  mov     [rsp+0F0h+dwCreationDisposition], ebx
0x1400c3c21  call    WPP_SF_Sd
0x1400c3c26  mov     rcx, rsi; hObject
0x1400c3c29  call    cs:__imp_CloseHandle
0x1400c3c2f  mov     rcx, r14; hMem
0x1400c3c32  call    cs:__imp_LocalFree
0x1400c3c38  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3c3f  cmp     rcx, r13
0x1400c3c42  jz      short loc_1400C3C65
0x1400c3c44  test    byte ptr [rcx+1Ch], 4
0x1400c3c48  jz      short loc_1400C3C65
0x1400c3c4a  cmp     byte ptr [rcx+19h], 4
0x1400c3c4e  jb      short loc_1400C3C65
0x1400c3c50  mov     rcx, [rcx+10h]
0x1400c3c54  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400c3c5b  mov     edx, 89h
0x1400c3c60  call    WPP_SF_
0x1400c3c65  mov     eax, ebx
0x1400c3c67  add     rsp, 0C8h
0x1400c3c6e  pop     r14
0x1400c3c70  pop     r13
0x1400c3c72  pop     rdi
0x1400c3c73  pop     rsi
0x1400c3c74  pop     rbx
0x1400c3c75  pop     rbp
0x1400c3c76  retn
```
