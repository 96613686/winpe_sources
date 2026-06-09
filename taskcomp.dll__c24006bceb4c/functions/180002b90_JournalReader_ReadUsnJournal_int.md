# JournalReader::_ReadUsnJournal(int)

- ea: `0x180002b90`
- end: `0x180003058`
- name: `?_ReadUsnJournal@JournalReader@@AEAAJH@Z`
- size: `1224`
- prototype: `__int64 __fastcall(JournalReader *this, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000e274`
- `0x180011880`

## callees

- `0x180002b90`
- `0x1800074c8`
- `0x1800074d4`
- `0x18000c760`
- `0x18000efb0`
- `0x18000f2dc`
- `0x18000fbe0`
- `0x18000fc28`
- `0x18000fc80`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180002dab`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180002e41`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180002dab`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180002e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f6a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002d1f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002f36`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002d1f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002f36`

## pseudocode

```c
__int64 __fastcall JournalReader::_ReadUsnJournal(JournalReader *this, __int64 a2, __int64 a3)
{
  int v3; // edi
  unsigned int Next; // r13d
  __int64 v6; // r9
  size_t v7; // rcx
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
  size_t v37; // [rsp+80h] [rbp-98h]
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
0x180002b90  mov     [rsp+arg_8], rbx
0x180002b95  mov     [rsp+arg_10], rsi
0x180002b9a  push    rdi
0x180002b9b  push    r12
0x180002b9d  push    r13
0x180002b9f  push    r14
0x180002ba1  push    r15
0x180002ba3  sub     rsp, 0F0h
0x180002baa  mov     rax, cs:__security_cookie
0x180002bb1  xor     rax, rsp
0x180002bb4  mov     [rsp+118h+var_38], rax
0x180002bbc  mov     edi, edx
0x180002bbe  mov     r14, rcx
0x180002bc1  mov     [rsp+118h+var_C0], rcx
0x180002bc6  xor     esi, esi
0x180002bc8  mov     r13d, esi
0x180002bcb  mov     [rsp+118h+var_D4], esi
0x180002bcf  lea     r12, WPP_GLOBAL_Control
0x180002bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bdd  cmp     rcx, r12
0x180002be0  jz      short loc_180002C06
0x180002be2  test    byte ptr [rcx+1Ch], 2
0x180002be6  jz      short loc_180002C06
0x180002be8  cmp     byte ptr [rcx+19h], 4
0x180002bec  jb      short loc_180002C06
0x180002bee  mov     eax, [r14+80h]
0x180002bf5  mov     dword ptr [rsp+118h+lpOutBuffer], eax
0x180002bf9  mov     r9, [r14+78h]
0x180002bfd  mov     rcx, [rcx+10h]
0x180002c01  call    WPP_SF_id
0x180002c06  test    edi, edi
0x180002c08  jz      short loc_180002C1A
0x180002c0a  dec     dword ptr [r14+80h]
0x180002c11  mov     r9d, [r14+80h]
0x180002c18  jmp     short loc_180002C27
0x180002c1a  mov     r9d, 3
0x180002c20  mov     [r14+80h], r9d
0x180002c27  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c2e  cmp     rcx, r12
0x180002c31  jz      short loc_180002C55
0x180002c33  test    byte ptr [rcx+1Ch], 2
0x180002c37  jz      short loc_180002C55
0x180002c39  cmp     byte ptr [rcx+19h], 4
0x180002c3d  jb      short loc_180002C55
0x180002c3f  mov     edx, 1Ah
0x180002c44  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180002c4b  mov     rcx, [rcx+10h]
0x180002c4f  call    WPP_SF_d
0x180002c54  nop
0x180002c55  mov     [rsp+118h+InBuffer], rsi
0x180002c5a  mov     [rsp+118h+var_88], 20002h
0x180002c66  mov     [rsp+118h+var_A8], 80401B07h
0x180002c6e  mov     [rsp+118h+var_A4], 1
0x180002c76  mov     [rsp+118h+var_A0], 1
0x180002c7f  mov     ecx, [r14+68h]; unsigned __int64
0x180002c83  mov     [rsp+118h+var_98], rcx
0x180002c8b  mov     rax, [r14+70h]
0x180002c8f  mov     [rsp+118h+var_90], rax
0x180002c97  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002c9c  mov     rbx, rax
0x180002c9f  mov     [rsp+118h+var_B8], rax
0x180002ca4  test    rax, rax
0x180002ca7  jnz     short loc_180002CBA
0x180002ca9  xor     ecx, ecx; Block
0x180002cab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002cb0  mov     eax, 8007000Eh
0x180002cb5  jmp     loc_18000302A
0x180002cba  mov     [rsp+118h+var_D8], esi
0x180002cbe  test    edi, edi
0x180002cc0  jnz     short loc_180002CD1
0x180002cc2  mov     rcx, r14; this
0x180002cc5  call    ?_ReadNext@JournalReader@@AEAAJXZ; JournalReader::_ReadNext(void)
0x180002cca  mov     r13d, eax
0x180002ccd  mov     [rsp+118h+var_D4], eax
0x180002cd1  xor     edx, edx; Val
0x180002cd3  mov     r8d, 40h ; '@'; Size
0x180002cd9  lea     rcx, [rsp+118h+OutBuffer]; void *
0x180002ce1  call    memset_0
0x180002ce6  xor     edi, edi
0x180002ce8  mov     [rsp+118h+BytesReturned], edi
0x180002cec  mov     [rsp+118h+lpOverlapped], rdi; lpOverlapped
0x180002cf1  lea     rax, [rsp+118h+BytesReturned]
0x180002cf6  mov     [rsp+118h+lpBytesReturned], rax; lpBytesReturned
0x180002cfb  mov     [rsp+118h+nOutBufferSize], 40h ; '@'; nOutBufferSize
0x180002d03  lea     rax, [rsp+118h+OutBuffer]
0x180002d0b  mov     [rsp+118h+lpOutBuffer], rax; lpOutBuffer
0x180002d10  xor     r9d, r9d; nInBufferSize
0x180002d13  xor     r8d, r8d; lpInBuffer
0x180002d16  mov     edx, 900F4h; dwIoControlCode
0x180002d1b  mov     rcx, [r14+58h]; hDevice
0x180002d1f  call    cs:__imp_DeviceIoControl
0x180002d25  test    eax, eax
0x180002d27  jnz     short loc_180002D8A
0x180002d29  mov     rax, cs:WPP_GLOBAL_Control
0x180002d30  cmp     rax, r12
0x180002d33  jz      short loc_180002D66
0x180002d35  test    byte ptr [rax+1Ch], 2
0x180002d39  jz      short loc_180002D66
0x180002d3b  cmp     byte ptr [rax+19h], 2
0x180002d3f  jb      short loc_180002D66
0x180002d41  call    cs:__imp_GetLastError
0x180002d47  mov     edx, 1Bh
0x180002d4c  mov     r9d, eax
0x180002d4f  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180002d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d5d  mov     rcx, [rcx+10h]
0x180002d61  call    WPP_SF_d
0x180002d66  call    cs:__imp_GetLastError
0x180002d6c  mov     edi, eax
0x180002d6e  test    eax, eax
0x180002d70  jle     short loc_180002D7B
0x180002d72  movzx   edi, ax
0x180002d75  or      edi, 80070000h
0x180002d7b  mov     rcx, rbx; Block
0x180002d7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d83  mov     eax, edi
0x180002d85  jmp     loc_18000302A
0x180002d8a  mov     qword ptr [rsp+118h+DueTime], 0FFFFFFFFFFD23940h
0x180002d93  mov     [rsp+118h+nOutBufferSize], edi; fResume
0x180002d97  mov     [rsp+118h+lpOutBuffer], rdi; lpArgToCompletionRoutine
0x180002d9c  xor     r9d, r9d; pfnCompletionRoutine
0x180002d9f  xor     r8d, r8d; lPeriod
0x180002da2  lea     rdx, [rsp+118h+DueTime]; lpDueTime
0x180002da7  mov     rcx, [r14+40h]; hTimer
0x180002dab  call    cs:__imp_SetWaitableTimer
0x180002db1  test    eax, eax
0x180002db3  jnz     short loc_180002E16
0x180002db5  mov     rax, cs:WPP_GLOBAL_Control
0x180002dbc  cmp     rax, r12
0x180002dbf  jz      short loc_180002DF2
0x180002dc1  test    byte ptr [rax+1Ch], 2
0x180002dc5  jz      short loc_180002DF2
0x180002dc7  cmp     byte ptr [rax+19h], 2
0x180002dcb  jb      short loc_180002DF2
0x180002dcd  call    cs:__imp_GetLastError
0x180002dd3  mov     edx, 1Ch
0x180002dd8  mov     r9d, eax
0x180002ddb  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180002de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002de9  mov     rcx, [rcx+10h]
0x180002ded  call    WPP_SF_d
0x180002df2  call    cs:__imp_GetLastError
0x180002df8  mov     edi, eax
0x180002dfa  test    eax, eax
0x180002dfc  jle     short loc_180002E07
0x180002dfe  movzx   edi, ax
0x180002e01  or      edi, 80070000h
0x180002e07  mov     rcx, rbx; Block
0x180002e0a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e0f  mov     eax, edi
0x180002e11  jmp     loc_18000302A
0x180002e16  cmp     [r14+50h], dil
0x180002e1a  jnz     loc_180002EB1
0x180002e20  mov     qword ptr [rsp+118h+DueTime], 0FFFFFFFFEE1E5D00h
0x180002e29  mov     [rsp+118h+nOutBufferSize], edi; fResume
0x180002e2d  mov     [rsp+118h+lpOutBuffer], rdi; lpArgToCompletionRoutine
0x180002e32  xor     r9d, r9d; pfnCompletionRoutine
0x180002e35  xor     r8d, r8d; lPeriod
0x180002e38  lea     rdx, [rsp+118h+DueTime]; lpDueTime
0x180002e3d  mov     rcx, [r14+48h]; hTimer
0x180002e41  call    cs:__imp_SetWaitableTimer
0x180002e47  test    eax, eax
0x180002e49  jnz     short loc_180002EAC
0x180002e4b  mov     rax, cs:WPP_GLOBAL_Control
0x180002e52  cmp     rax, r12
0x180002e55  jz      short loc_180002E88
0x180002e57  test    byte ptr [rax+1Ch], 2
0x180002e5b  jz      short loc_180002E88
0x180002e5d  cmp     byte ptr [rax+19h], 2
0x180002e61  jb      short loc_180002E88
0x180002e63  call    cs:__imp_GetLastError
0x180002e69  mov     edx, 1Dh
0x180002e6e  mov     r9d, eax
0x180002e71  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180002e78  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e7f  mov     rcx, [rcx+10h]
0x180002e83  call    WPP_SF_d
0x180002e88  call    cs:__imp_GetLastError
0x180002e8e  mov     edi, eax
0x180002e90  test    eax, eax
0x180002e92  jle     short loc_180002E9D
0x180002e94  movzx   edi, ax
0x180002e97  or      edi, 80070000h
0x180002e9d  mov     rcx, rbx; Block
0x180002ea0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ea5  mov     eax, edi
0x180002ea7  jmp     loc_18000302A
0x180002eac  mov     byte ptr [r14+50h], 1
0x180002eb1  mov     r15, [rsp+118h+var_68]
0x180002eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ec0  cmp     rcx, r12
0x180002ec3  jz      short loc_180002EE3
0x180002ec5  test    byte ptr [rcx+1Ch], 2
0x180002ec9  jz      short loc_180002EE3
0x180002ecb  cmp     byte ptr [rcx+19h], 4
0x180002ecf  jb      short loc_180002EE3
0x180002ed1  mov     [rsp+118h+lpOutBuffer], r15
0x180002ed6  mov     r9, [r14+78h]
0x180002eda  mov     rcx, [rcx+10h]
0x180002ede  call    WPP_SF_ii
0x180002ee3  lea     rsi, [r14+78h]
0x180002ee7  cmp     [rsi], r15
0x180002eea  jge     loc_180002F90
0x180002ef0  mov     r8d, [r14+68h]; Size
0x180002ef4  xor     edx, edx; Val
0x180002ef6  mov     rcx, rbx; void *
0x180002ef9  call    memset_0
0x180002efe  mov     rax, [rsi]
0x180002f01  mov     [rsp+118h+InBuffer], rax
0x180002f06  mov     [rsp+118h+lpOverlapped], rdi; lpOverlapped
0x180002f0b  lea     rax, [rsp+118h+var_D8]
0x180002f10  mov     [rsp+118h+lpBytesReturned], rax; lpBytesReturned
0x180002f15  mov     eax, [r14+68h]
0x180002f19  mov     [rsp+118h+nOutBufferSize], eax; nOutBufferSize
0x180002f1d  mov     [rsp+118h+lpOutBuffer], rbx; lpOutBuffer
0x180002f22  mov     r9d, 30h ; '0'; nInBufferSize
0x180002f28  lea     r8, [rsp+118h+InBuffer]; lpInBuffer
0x180002f2d  mov     edx, 900BBh; dwIoControlCode
0x180002f32  mov     rcx, [r14+58h]; hDevice
0x180002f36  call    cs:__imp_DeviceIoControl
0x180002f3c  test    eax, eax
0x180002f3e  jnz     short loc_180002F9B
0x180002f40  call    cs:__imp_GetLastError
0x180002f46  cmp     eax, 49Dh
0x180002f4b  jnz     short loc_180002F52
0x180002f4d  mov     [rsi], rdi
0x180002f50  jmp     short loc_180002EE3
0x180002f52  mov     rax, cs:WPP_GLOBAL_Control
0x180002f59  cmp     rax, r12
0x180002f5c  jz      short loc_180002F90
0x180002f5e  test    byte ptr [rax+1Ch], 2
0x180002f62  jz      short loc_180002F90
0x180002f64  cmp     byte ptr [rax+19h], 2
0x180002f68  jb      short loc_180002F90
0x180002f6a  call    cs:__imp_GetLastError
0x180002f70  mov     edx, 1Fh
0x180002f75  mov     r9d, eax
0x180002f78  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x180002f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f86  mov     rcx, [rcx+10h]
0x180002f8a  call    WPP_SF_d
0x180002f8f  nop
0x180002f90  mov     rcx, rbx; Block
0x180002f93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f98  nop
0x180002f99  jmp     short loc_180003003
0x180002f9b  mov     ecx, [rsp+118h+var_D8]
0x180002f9f  cmp     ecx, 8
0x180002fa2  jbe     short loc_180002F90
0x180002fa4  lea     rdi, [rbx+8]
0x180002fa8  add     ecx, 0FFFFFFF8h
0x180002fab  mov     [rsp+118h+var_D8], ecx
0x180002faf  mov     edx, ecx
0x180002fb1  test    ecx, ecx
0x180002fb3  jz      short loc_180002FE1
0x180002fb5  test    byte ptr [rdi+34h], 10h
0x180002fb9  jnz     short loc_180002FD4
0x180002fbb  mov     rax, [r14+60h]
0x180002fbf  cmp     [rdi+10h], rax
0x180002fc3  jnz     short loc_180002FD4
0x180002fc5  mov     rdx, rdi; struct USN_RECORD_V2 *
0x180002fc8  mov     rcx, r14; this
0x180002fcb  call    ?_ProcessRecord@JournalReader@@AEAAXPEAUUSN_RECORD_V2@@@Z; JournalReader::_ProcessRecord(USN_RECORD_V2 *)
0x180002fd0  mov     ecx, [rsp+118h+var_D8]
0x180002fd4  sub     ecx, [rdi]
0x180002fd6  mov     [rsp+118h+var_D8], ecx
0x180002fda  mov     eax, [rdi]
0x180002fdc  add     rdi, rax
0x180002fdf  jmp     short loc_180002FAF
0x180002fe1  mov     rax, [rbx]
0x180002fe4  mov     [rsi], rax
0x180002fe7  xor     edi, edi
0x180002fe9  jmp     loc_180002EE3
0x180002fee  mov     rsi, [rsp+118h+var_C0]
0x180002ff3  add     rsi, 78h ; 'x'
0x180002ff7  lea     r12, WPP_GLOBAL_Control
0x180002ffe  mov     r13d, [rsp+118h+var_D4]
0x180003003  mov     rcx, cs:WPP_GLOBAL_Control
0x18000300a  cmp     rcx, r12
0x18000300d  jz      short loc_180003027
0x18000300f  test    byte ptr [rcx+1Ch], 2
0x180003013  jz      short loc_180003027
0x180003015  cmp     byte ptr [rcx+19h], 4
0x180003019  jb      short loc_180003027
0x18000301b  mov     r9, [rsi]
0x18000301e  mov     rcx, [rcx+10h]
0x180003022  call    WPP_SF_i
0x180003027  mov     eax, r13d
0x18000302a  mov     rcx, [rsp+118h+var_38]
0x180003032  xor     rcx, rsp; StackCookie
0x180003035  call    __security_check_cookie
0x18000303a  lea     r11, [rsp+118h+var_28]
0x180003042  mov     rbx, [r11+38h]
0x180003046  mov     rsi, [r11+40h]
0x18000304a  mov     rsp, r11
0x18000304d  pop     r15
0x18000304f  pop     r14
0x180003051  pop     r13
0x180003053  pop     r12
0x180003055  pop     rdi
  ... truncated ...
```
