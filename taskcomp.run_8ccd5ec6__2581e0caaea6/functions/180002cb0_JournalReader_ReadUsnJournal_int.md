# JournalReader::_ReadUsnJournal(int)

- ea: `0x180002cb0`
- end: `0x1800031c7`
- name: `?_ReadUsnJournal@JournalReader@@AEAAJH@Z`
- size: `1303`
- prototype: `__int64 __fastcall(JournalReader *__hidden this, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000eb64`
- `0x180012360`

## callees

- `0x180002cb0`
- `0x180007988`
- `0x180007994`
- `0x18000cf80`
- `0x18000f948`
- `0x18000fc74`
- `0x1800105a0`
- `0x1800105ec`
- `0x180010648`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180002edd`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180002f85`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180002edd`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180002f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030d3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002e3f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180003093`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002e3f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180003093`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall JournalReader::_ReadUsnJournal(JournalReader *this, __int64 a2, __int64 a3)
{
  int v3; // edi
  unsigned int Next; // r13d
  __int64 v6; // r9
  unsigned __int64 v7; // rcx
  unsigned int *lpOutBuffer; // rbx
  DWORD LastError; // eax
  signed int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // r8
  DWORD v15; // eax
  signed int v16; // eax
  DWORD v17; // eax
  signed int v18; // eax
  __int64 v19; // r15
  _QWORD *v20; // rsi
  __int64 v21; // r8
  DWORD v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  struct USN_RECORD_V2 *v25; // rdi
  DWORD v26; // ecx
  DWORD lpBytesReturned; // [rsp+40h] [rbp-D8h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-D4h]
  DWORD BytesReturned; // [rsp+48h] [rbp-D0h] BYREF
  LARGE_INTEGER DueTime; // [rsp+50h] [rbp-C8h] BYREF
  JournalReader *v31; // [rsp+58h] [rbp-C0h]
  unsigned int *v32; // [rsp+60h] [rbp-B8h]
  __int64 InBuffer; // [rsp+68h] [rbp-B0h] BYREF
  int v34; // [rsp+70h] [rbp-A8h]
  int v35; // [rsp+74h] [rbp-A4h]
  __int64 v36; // [rsp+78h] [rbp-A0h]
  unsigned __int64 v37; // [rsp+80h] [rbp-98h]
  __int64 v38; // [rsp+88h] [rbp-90h]
  __int64 v39; // [rsp+90h] [rbp-88h]
  _BYTE OutBuffer[16]; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-68h]

  v3 = a2;
  v31 = this;
  Next = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_id(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)this + 15), *((_DWORD *)this + 32));
  }
  if ( v3 )
  {
    v6 = (unsigned int)--*((_DWORD *)this + 32);
  }
  else
  {
    v6 = 3;
    *((_DWORD *)this + 32) = 3;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, v6);
  }
  InBuffer = 0;
  v39 = 131074;
  v34 = -2143282425;
  v35 = 1;
  v36 = 1;
  v7 = *((unsigned int *)this + 26);
  v37 = v7;
  v38 = *((_QWORD *)this + 14);
  lpOutBuffer = (unsigned int *)operator new[](v7);
  v32 = lpOutBuffer;
  if ( !lpOutBuffer )
  {
    operator delete(0);
    return 2147942414LL;
  }
  lpBytesReturned = 0;
  if ( !v3 )
  {
    Next = JournalReader::_ReadNext(this);
    v28 = Next;
  }
  memset_0(OutBuffer, 0, 0x40u);
  BytesReturned = 0;
  if ( !DeviceIoControl(*((HANDLE *)this + 11), 0x900F4u, 0, 0, OutBuffer, 0x40u, &BytesReturned, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, LastError);
    }
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
LABEL_40:
    operator delete(lpOutBuffer);
    return v12;
  }
  DueTime.QuadPart = -3000000;
  if ( !SetWaitableTimer(*((HANDLE *)this + 8), &DueTime, 0, 0, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, v15);
    }
    v16 = GetLastError();
    v12 = v16;
    if ( v16 > 0 )
      v12 = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_40;
  }
  if ( !*((_BYTE *)this + 80) )
  {
    DueTime.QuadPart = -300000000;
    if ( !SetWaitableTimer(*((HANDLE *)this + 9), &DueTime, 0, 0, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, v17);
      }
      v18 = GetLastError();
      v12 = v18;
      if ( v18 > 0 )
        v12 = (unsigned __int16)v18 | 0x80070000;
      goto LABEL_40;
    }
    *((_BYTE *)this + 80) = 1;
  }
  v19 = v41;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, *((_QWORD *)this + 15), v41);
  }
  while ( 1 )
  {
    v20 = (_QWORD *)((char *)this + 120);
    if ( *((_QWORD *)this + 15) >= v19 )
      break;
    memset_0(lpOutBuffer, 0, *((unsigned int *)this + 26));
    InBuffer = *v20;
    if ( DeviceIoControl(
           *((HANDLE *)this + 11),
           0x900BBu,
           &InBuffer,
           0x30u,
           lpOutBuffer,
           *((_DWORD *)this + 26),
           &lpBytesReturned,
           0) )
    {
      if ( lpBytesReturned <= 8 )
        break;
      v25 = (struct USN_RECORD_V2 *)(lpOutBuffer + 2);
      v26 = lpBytesReturned - 8;
      lpBytesReturned -= 8;
      while ( v26 )
      {
        if ( (v25->FileAttributes & 0x10) == 0 && v25->ParentFileReferenceNumber == *((_QWORD *)this + 12) )
        {
          JournalReader::_ProcessRecord(this, v25, v21);
          v26 = lpBytesReturned;
        }
        v26 -= v25->RecordLength;
        lpBytesReturned = v26;
        v25 = (struct USN_RECORD_V2 *)((char *)v25 + v25->RecordLength);
      }
      *v20 = *(_QWORD *)lpOutBuffer;
    }
    else
    {
      if ( GetLastError() != 1181 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, v22);
        }
        break;
      }
      *v20 = 0;
    }
  }
  operator delete(lpOutBuffer);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v24, *v20);
  }
  return Next;
}

```

## disassembly

```asm
0x180002cb0  mov     [rsp+arg_8], rbx
0x180002cb5  mov     [rsp+arg_10], rsi
0x180002cba  push    rdi
0x180002cbb  push    r12
0x180002cbd  push    r13
0x180002cbf  push    r14
0x180002cc1  push    r15
0x180002cc3  sub     rsp, 0F0h
0x180002cca  mov     rax, cs:__security_cookie
0x180002cd1  xor     rax, rsp
0x180002cd4  mov     [rsp+118h+var_38], rax
0x180002cdc  mov     edi, edx
0x180002cde  mov     r14, rcx
0x180002ce1  mov     [rsp+118h+var_C0], rcx
0x180002ce6  xor     esi, esi
0x180002ce8  mov     r13d, esi
0x180002ceb  mov     [rsp+118h+var_D4], esi
0x180002cef  lea     r12, WPP_GLOBAL_Control
0x180002cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cfd  cmp     rcx, r12
0x180002d00  jz      short loc_180002D26
0x180002d02  test    byte ptr [rcx+1Ch], 2
0x180002d06  jz      short loc_180002D26
0x180002d08  cmp     byte ptr [rcx+19h], 4
0x180002d0c  jb      short loc_180002D26
0x180002d0e  mov     eax, [r14+80h]
0x180002d15  mov     dword ptr [rsp+118h+lpOutBuffer], eax
0x180002d19  mov     r9, [r14+78h]
0x180002d1d  mov     rcx, [rcx+10h]
0x180002d21  call    WPP_SF_id
0x180002d26  test    edi, edi
0x180002d28  jz      short loc_180002D3A
0x180002d2a  dec     dword ptr [r14+80h]
0x180002d31  mov     r9d, [r14+80h]
0x180002d38  jmp     short loc_180002D47
0x180002d3a  mov     r9d, 3
0x180002d40  mov     [r14+80h], r9d
0x180002d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d4e  cmp     rcx, r12
0x180002d51  jz      short loc_180002D75
0x180002d53  test    byte ptr [rcx+1Ch], 2
0x180002d57  jz      short loc_180002D75
0x180002d59  cmp     byte ptr [rcx+19h], 4
0x180002d5d  jb      short loc_180002D75
0x180002d5f  mov     edx, 1Ah
0x180002d64  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180002d6b  mov     rcx, [rcx+10h]
0x180002d6f  call    WPP_SF_d
0x180002d74  nop
0x180002d75  mov     [rsp+118h+InBuffer], rsi
0x180002d7a  mov     [rsp+118h+var_88], 20002h
0x180002d86  mov     [rsp+118h+var_A8], 80401B07h
0x180002d8e  mov     [rsp+118h+var_A4], 1
0x180002d96  mov     [rsp+118h+var_A0], 1
0x180002d9f  mov     ecx, [r14+68h]; unsigned __int64
0x180002da3  mov     [rsp+118h+var_98], rcx
0x180002dab  mov     rax, [r14+70h]
0x180002daf  mov     [rsp+118h+var_90], rax
0x180002db7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002dbc  mov     rbx, rax
0x180002dbf  mov     [rsp+118h+var_B8], rax
0x180002dc4  test    rax, rax
0x180002dc7  jnz     short loc_180002DDA
0x180002dc9  xor     ecx, ecx; Block
0x180002dcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002dd0  mov     eax, 8007000Eh
0x180002dd5  jmp     loc_180003199
0x180002dda  mov     [rsp+118h+var_D8], esi
0x180002dde  test    edi, edi
0x180002de0  jnz     short loc_180002DF1
0x180002de2  mov     rcx, r14; this
0x180002de5  call    ?_ReadNext@JournalReader@@AEAAJXZ; JournalReader::_ReadNext(void)
0x180002dea  mov     r13d, eax
0x180002ded  mov     [rsp+118h+var_D4], eax
0x180002df1  xor     edx, edx; Val
0x180002df3  mov     r8d, 40h ; '@'; Size
0x180002df9  lea     rcx, [rsp+118h+OutBuffer]; void *
0x180002e01  call    memset_0
0x180002e06  xor     edi, edi
0x180002e08  mov     [rsp+118h+BytesReturned], edi
0x180002e0c  mov     [rsp+118h+lpOverlapped], rdi; lpOverlapped
0x180002e11  lea     rax, [rsp+118h+BytesReturned]
0x180002e16  mov     [rsp+118h+lpBytesReturned], rax; lpBytesReturned
0x180002e1b  mov     [rsp+118h+nOutBufferSize], 40h ; '@'; nOutBufferSize
0x180002e23  lea     rax, [rsp+118h+OutBuffer]
0x180002e2b  mov     [rsp+118h+lpOutBuffer], rax; lpOutBuffer
0x180002e30  xor     r9d, r9d; nInBufferSize
0x180002e33  xor     r8d, r8d; lpInBuffer
0x180002e36  mov     edx, 900F4h; dwIoControlCode
0x180002e3b  mov     rcx, [r14+58h]; hDevice
0x180002e3f  call    cs:__imp_DeviceIoControl
0x180002e46  nop     dword ptr [rax+rax+00h]
0x180002e4b  test    eax, eax
0x180002e4d  jnz     short loc_180002EBC
0x180002e4f  mov     rax, cs:WPP_GLOBAL_Control
0x180002e56  cmp     rax, r12
0x180002e59  jz      short loc_180002E92
0x180002e5b  test    byte ptr [rax+1Ch], 2
0x180002e5f  jz      short loc_180002E92
0x180002e61  cmp     byte ptr [rax+19h], 2
0x180002e65  jb      short loc_180002E92
0x180002e67  call    cs:__imp_GetLastError
0x180002e6e  nop     dword ptr [rax+rax+00h]
0x180002e73  mov     edx, 1Bh
0x180002e78  mov     r9d, eax
0x180002e7b  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180002e82  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e89  mov     rcx, [rcx+10h]
0x180002e8d  call    WPP_SF_d
0x180002e92  call    cs:__imp_GetLastError
0x180002e99  nop     dword ptr [rax+rax+00h]
0x180002e9e  mov     edi, eax
0x180002ea0  test    eax, eax
0x180002ea2  jle     short loc_180002EAD
0x180002ea4  movzx   edi, ax
0x180002ea7  or      edi, 80070000h
0x180002ead  mov     rcx, rbx; Block
0x180002eb0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002eb5  mov     eax, edi
0x180002eb7  jmp     loc_180003199
0x180002ebc  mov     qword ptr [rsp+118h+DueTime], 0FFFFFFFFFFD23940h
0x180002ec5  mov     [rsp+118h+nOutBufferSize], edi; fResume
0x180002ec9  mov     [rsp+118h+lpOutBuffer], rdi; lpArgToCompletionRoutine
0x180002ece  xor     r9d, r9d; pfnCompletionRoutine
0x180002ed1  xor     r8d, r8d; lPeriod
0x180002ed4  lea     rdx, [rsp+118h+DueTime]; lpDueTime
0x180002ed9  mov     rcx, [r14+40h]; hTimer
0x180002edd  call    cs:__imp_SetWaitableTimer
0x180002ee4  nop     dword ptr [rax+rax+00h]
0x180002ee9  test    eax, eax
0x180002eeb  jnz     short loc_180002F5A
0x180002eed  mov     rax, cs:WPP_GLOBAL_Control
0x180002ef4  cmp     rax, r12
0x180002ef7  jz      short loc_180002F30
0x180002ef9  test    byte ptr [rax+1Ch], 2
0x180002efd  jz      short loc_180002F30
0x180002eff  cmp     byte ptr [rax+19h], 2
0x180002f03  jb      short loc_180002F30
0x180002f05  call    cs:__imp_GetLastError
0x180002f0c  nop     dword ptr [rax+rax+00h]
0x180002f11  mov     edx, 1Ch
0x180002f16  mov     r9d, eax
0x180002f19  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180002f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f27  mov     rcx, [rcx+10h]
0x180002f2b  call    WPP_SF_d
0x180002f30  call    cs:__imp_GetLastError
0x180002f37  nop     dword ptr [rax+rax+00h]
0x180002f3c  mov     edi, eax
0x180002f3e  test    eax, eax
0x180002f40  jle     short loc_180002F4B
0x180002f42  movzx   edi, ax
0x180002f45  or      edi, 80070000h
0x180002f4b  mov     rcx, rbx; Block
0x180002f4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f53  mov     eax, edi
0x180002f55  jmp     loc_180003199
0x180002f5a  cmp     [r14+50h], dil
0x180002f5e  jnz     loc_180003007
0x180002f64  mov     qword ptr [rsp+118h+DueTime], 0FFFFFFFFEE1E5D00h
0x180002f6d  mov     [rsp+118h+nOutBufferSize], edi; fResume
0x180002f71  mov     [rsp+118h+lpOutBuffer], rdi; lpArgToCompletionRoutine
0x180002f76  xor     r9d, r9d; pfnCompletionRoutine
0x180002f79  xor     r8d, r8d; lPeriod
0x180002f7c  lea     rdx, [rsp+118h+DueTime]; lpDueTime
0x180002f81  mov     rcx, [r14+48h]; hTimer
0x180002f85  call    cs:__imp_SetWaitableTimer
0x180002f8c  nop     dword ptr [rax+rax+00h]
0x180002f91  test    eax, eax
0x180002f93  jnz     short loc_180003002
0x180002f95  mov     rax, cs:WPP_GLOBAL_Control
0x180002f9c  cmp     rax, r12
0x180002f9f  jz      short loc_180002FD8
0x180002fa1  test    byte ptr [rax+1Ch], 2
0x180002fa5  jz      short loc_180002FD8
0x180002fa7  cmp     byte ptr [rax+19h], 2
0x180002fab  jb      short loc_180002FD8
0x180002fad  call    cs:__imp_GetLastError
0x180002fb4  nop     dword ptr [rax+rax+00h]
0x180002fb9  mov     edx, 1Dh
0x180002fbe  mov     r9d, eax
0x180002fc1  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180002fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fcf  mov     rcx, [rcx+10h]
0x180002fd3  call    WPP_SF_d
0x180002fd8  call    cs:__imp_GetLastError
0x180002fdf  nop     dword ptr [rax+rax+00h]
0x180002fe4  mov     edi, eax
0x180002fe6  test    eax, eax
0x180002fe8  jle     short loc_180002FF3
0x180002fea  movzx   edi, ax
0x180002fed  or      edi, 80070000h
0x180002ff3  mov     rcx, rbx; Block
0x180002ff6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ffb  mov     eax, edi
0x180002ffd  jmp     loc_180003199
0x180003002  mov     byte ptr [r14+50h], 1
0x180003007  mov     r15, [rsp+118h+var_68]
0x18000300f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003016  cmp     rcx, r12
0x180003019  jz      short loc_180003040
0x18000301b  test    byte ptr [rcx+1Ch], 2
0x18000301f  jz      short loc_180003040
0x180003021  cmp     byte ptr [rcx+19h], 4
0x180003025  jb      short loc_180003040
0x180003027  mov     [rsp+118h+lpOutBuffer], r15
0x18000302c  mov     r9, [r14+78h]
0x180003030  mov     rcx, [rcx+10h]
0x180003034  call    WPP_SF_ii
0x180003039  nop     dword ptr [rax+00000000h]
0x180003040  lea     rsi, [r14+78h]
0x180003044  cmp     [rsi], r15
0x180003047  jge     loc_1800030FF
0x18000304d  mov     r8d, [r14+68h]; Size
0x180003051  xor     edx, edx; Val
0x180003053  mov     rcx, rbx; void *
0x180003056  call    memset_0
0x18000305b  mov     rax, [rsi]
0x18000305e  mov     [rsp+118h+InBuffer], rax
0x180003063  mov     [rsp+118h+lpOverlapped], rdi; lpOverlapped
0x180003068  lea     rax, [rsp+118h+var_D8]
0x18000306d  mov     [rsp+118h+lpBytesReturned], rax; lpBytesReturned
0x180003072  mov     eax, [r14+68h]
0x180003076  mov     [rsp+118h+nOutBufferSize], eax; nOutBufferSize
0x18000307a  mov     [rsp+118h+lpOutBuffer], rbx; lpOutBuffer
0x18000307f  mov     r9d, 30h ; '0'; nInBufferSize
0x180003085  lea     r8, [rsp+118h+InBuffer]; lpInBuffer
0x18000308a  mov     edx, 900BBh; dwIoControlCode
0x18000308f  mov     rcx, [r14+58h]; hDevice
0x180003093  call    cs:__imp_DeviceIoControl
0x18000309a  nop     dword ptr [rax+rax+00h]
0x18000309f  test    eax, eax
0x1800030a1  jnz     short loc_18000310A
0x1800030a3  call    cs:__imp_GetLastError
0x1800030aa  nop     dword ptr [rax+rax+00h]
0x1800030af  cmp     eax, 49Dh
0x1800030b4  jnz     short loc_1800030BB
0x1800030b6  mov     [rsi], rdi
0x1800030b9  jmp     short loc_180003040
0x1800030bb  mov     rax, cs:WPP_GLOBAL_Control
0x1800030c2  cmp     rax, r12
0x1800030c5  jz      short loc_1800030FF
0x1800030c7  test    byte ptr [rax+1Ch], 2
0x1800030cb  jz      short loc_1800030FF
0x1800030cd  cmp     byte ptr [rax+19h], 2
0x1800030d1  jb      short loc_1800030FF
0x1800030d3  call    cs:__imp_GetLastError
0x1800030da  nop     dword ptr [rax+rax+00h]
0x1800030df  mov     edx, 1Fh
0x1800030e4  mov     r9d, eax
0x1800030e7  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x1800030ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030f5  mov     rcx, [rcx+10h]
0x1800030f9  call    WPP_SF_d
0x1800030fe  nop
0x1800030ff  mov     rcx, rbx; Block
0x180003102  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003107  nop
0x180003108  jmp     short loc_180003172
0x18000310a  mov     ecx, [rsp+118h+var_D8]
0x18000310e  cmp     ecx, 8
0x180003111  jbe     short loc_1800030FF
0x180003113  lea     rdi, [rbx+8]
0x180003117  add     ecx, 0FFFFFFF8h
0x18000311a  mov     [rsp+118h+var_D8], ecx
0x18000311e  mov     edx, ecx
0x180003120  test    ecx, ecx
0x180003122  jz      short loc_180003150
0x180003124  test    byte ptr [rdi+34h], 10h
0x180003128  jnz     short loc_180003143
0x18000312a  mov     rax, [r14+60h]
0x18000312e  cmp     [rdi+10h], rax
0x180003132  jnz     short loc_180003143
0x180003134  mov     rdx, rdi; struct USN_RECORD_V2 *
0x180003137  mov     rcx, r14; this
0x18000313a  call    ?_ProcessRecord@JournalReader@@AEAAXPEAUUSN_RECORD_V2@@@Z; JournalReader::_ProcessRecord(USN_RECORD_V2 *)
0x18000313f  mov     ecx, [rsp+118h+var_D8]
0x180003143  sub     ecx, [rdi]
0x180003145  mov     [rsp+118h+var_D8], ecx
0x180003149  mov     eax, [rdi]
0x18000314b  add     rdi, rax
0x18000314e  jmp     short loc_18000311E
0x180003150  mov     rax, [rbx]
0x180003153  mov     [rsi], rax
0x180003156  xor     edi, edi
0x180003158  jmp     loc_180003040
0x18000315d  mov     rsi, [rsp+118h+var_C0]
0x180003162  add     rsi, 78h ; 'x'
0x180003166  lea     r12, WPP_GLOBAL_Control
0x18000316d  mov     r13d, [rsp+118h+var_D4]
0x180003172  mov     rcx, cs:WPP_GLOBAL_Control
0x180003179  cmp     rcx, r12
0x18000317c  jz      short loc_180003196
0x18000317e  test    byte ptr [rcx+1Ch], 2
0x180003182  jz      short loc_180003196
0x180003184  cmp     byte ptr [rcx+19h], 4
0x180003188  jb      short loc_180003196
0x18000318a  mov     r9, [rsi]
0x18000318d  mov     rcx, [rcx+10h]
0x180003191  call    WPP_SF_i
  ... truncated ...
```
