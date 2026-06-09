# CDVRRingBufferWriter::CreateRecorder(ushort const *,ulong,IDVRRecorder * *)

- ea: `0x18006b020`
- end: `0x18006b793`
- name: `?CreateRecorder@CDVRRingBufferWriter@@UEAAJPEBGKPEAPEAUIDVRRecorder@@@Z`
- size: `1907`
- prototype: `__int64 __fastcall(CDVRRingBufferWriter *__hidden this, LPCWSTR lpFileName, unsigned int, struct IDVRRecorder **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops`

## callees

- `0x1800017a0`
- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x18000256c`
- `0x18005769c`
- `0x180068cdc`
- `0x180069a44`
- `0x180069a70`
- `0x18006a2b0`
- `0x18006b020`
- `0x18006df48`
- `0x180070c30`
- `0x180072028`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18006b6de`
- `KERNEL32!WaitForSingleObject` at `0x18006b6de`
- `KERNEL32!InitializeCriticalSection` at `0x18006b31e`
- `KERNEL32!InitializeCriticalSection` at `0x18006b31e`
- `KERNEL32!LeaveCriticalSection` at `0x18006b6bd`
- `KERNEL32!LeaveCriticalSection` at `0x1800b4201`
- `KERNEL32!LeaveCriticalSection` at `0x18006b6bd`
- `KERNEL32!LeaveCriticalSection` at `0x1800b4201`
- `KERNEL32!EnterCriticalSection` at `0x18006b22e`
- `KERNEL32!EnterCriticalSection` at `0x18006b22e`
- `KERNEL32!GetLastError` at `0x18006b0c3`
- `KERNEL32!GetLastError` at `0x18006b174`
- `KERNEL32!GetLastError` at `0x18006b19b`
- `KERNEL32!GetLastError` at `0x18006b6e9`
- `KERNEL32!GetLastError` at `0x18006b0c3`
- `KERNEL32!GetLastError` at `0x18006b174`
- `KERNEL32!GetLastError` at `0x18006b19b`
- `KERNEL32!GetLastError` at `0x18006b6e9`
- `KERNEL32!FindClose` at `0x18006b160`
- `KERNEL32!FindClose` at `0x18006b160`
- `KERNEL32!FindFirstFileW` at `0x18006b152`
- `KERNEL32!FindFirstFileW` at `0x18006b152`
- `KERNEL32!GetFullPathNameW` at `0x18006b0b9`
- `KERNEL32!GetFullPathNameW` at `0x18006b123`
- `KERNEL32!GetFullPathNameW` at `0x18006b0b9`
- `KERNEL32!GetFullPathNameW` at `0x18006b123`

## pseudocode

```c
__int64 __fastcall CDVRRingBufferWriter::CreateRecorder(
        CDVRRingBufferWriter *this,
        LPCWSTR lpFileName,
        unsigned int a3,
        struct IDVRRecorder **a4)
{
  char v4; // r14
  WCHAR *v7; // r15
  unsigned int v8; // edi
  signed int v9; // ebx
  DWORD FullPathNameW; // eax
  DWORD LastError; // eax
  unsigned __int64 v12; // rdx
  DWORD v13; // r14d
  WCHAR *v14; // rax
  DWORD v15; // eax
  HANDLE FirstFileW; // rax
  int v17; // eax
  bool v18; // cc
  _QWORD *v20; // rdi
  char *v21; // rsi
  int v22; // ebx
  unsigned __int64 v23; // rdx
  _QWORD *v24; // rax
  WCHAR *v25; // rax
  char *v26; // rax
  CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE *v27; // rax
  __int64 v28; // r14
  CDVRFileCollection *v29; // rax
  struct _LIST_ENTRY *v30; // rax
  struct _LIST_ENTRY *Flink; // rbx
  __int64 v32; // rcx
  CSBERecordingAttributesWM *v33; // rax
  int v34; // eax
  unsigned int v35; // edx
  int v36; // r14d
  signed int v37; // eax
  WCHAR *v38; // [rsp+78h] [rbp-300h]
  char v39; // [rsp+84h] [rbp-2F4h]
  int v40; // [rsp+88h] [rbp-2F0h]
  unsigned __int16 *v42; // [rsp+B8h] [rbp-2C0h] BYREF
  struct _LIST_ENTRY *v43; // [rsp+C0h] [rbp-2B8h] BYREF
  struct _LIST_ENTRY *v44; // [rsp+C8h] [rbp-2B0h] BYREF
  WCHAR Buffer[2]; // [rsp+D0h] [rbp-2A8h] BYREF
  unsigned int v46[3]; // [rsp+D4h] [rbp-2A4h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-298h] BYREF

  v4 = a3;
  v39 = a3;
  v7 = 0;
  v38 = 0;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( !lpFileName || a3 > 3 )
    return 2147942487LL;
  v8 = 0;
  v9 = 0;
  Buffer[0] = 0;
  FullPathNameW = GetFullPathNameW(lpFileName, 0, Buffer, 0);
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
LABEL_16:
    v9 = LastError;
    goto LABEL_17;
  }
  v13 = FullPathNameW + 1;
  v14 = (WCHAR *)operator new[](saturated_mul(FullPathNameW + 1, 2u));
  v7 = v14;
  v38 = v14;
  if ( !v14 )
  {
    v8 = -2147024882;
LABEL_8:
    v4 = v39;
    goto LABEL_17;
  }
  v15 = GetFullPathNameW(lpFileName, v13, v14, 0);
  if ( !v15 || v15 > v13 )
  {
    LastError = GetLastError();
    v4 = v39;
    goto LABEL_16;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(v7, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    FindClose(FirstFileW);
    v9 = 183;
    goto LABEL_8;
  }
  v9 = GetLastError();
  v4 = v39;
  if ( v9 == 2 )
    v9 = 0;
LABEL_17:
  if ( v8 )
  {
    v18 = v9 <= 0;
    if ( !v9 )
    {
LABEL_24:
      operator delete(v7, v12);
      v17 = 1;
      v40 = 1;
      goto LABEL_25;
    }
LABEL_21:
    if ( v18 )
      v8 = v9;
    else
      v8 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_24;
  }
  v17 = 0;
  v40 = 0;
  v18 = v9 <= 0;
  if ( v9 )
    goto LABEL_21;
LABEL_25:
  if ( v17 )
    return v8;
  v20 = 0;
  v21 = 0;
  v22 = -2147467259;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  *(_DWORD *)Buffer = 0;
  if ( *((_DWORD *)this + 122) == 0x80000000 )
    goto LABEL_65;
  v24 = operator new(0x48u);
  v20 = v24;
  if ( v24 )
  {
    *v24 = -1;
    v24[1] = -1;
    v24[2] = 0;
    v24[3] = 0;
    v24[4] = 0;
    v24[7] = v38;
    v24[8] = 1;
    v24[6] = 0;
    v24[5] = 0;
    v22 = 0;
    *(_DWORD *)Buffer = 0;
  }
  else
  {
    v20 = 0;
    v22 = *(_DWORD *)Buffer;
  }
  if ( !v20 )
    goto LABEL_32;
  v25 = 0;
  v38 = 0;
  if ( v22 >= 0 )
  {
    v26 = (char *)operator new(0x70u);
    v21 = v26;
    if ( v26 )
    {
      *(_QWORD *)v26 = &CDVRRecorder::`vftable'{for `IDVRRecorder'};
      *((_QWORD *)v26 + 1) = &CDVRRecorder::`vftable'{for `IDVRIORecordingAttributes'};
      *((_QWORD *)v26 + 2) = -1;
      *((_QWORD *)v26 + 3) = -1;
      *((_QWORD *)v26 + 4) = this;
      *((_QWORD *)v26 + 5) = v20 + 5;
      *((_DWORD *)v26 + 22) = 0;
      *((_QWORD *)v26 + 12) = 0;
      *((_QWORD *)v26 + 13) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v26 + 48));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 + 4) + 8LL))(*((_QWORD *)v21 + 4));
      *(_DWORD *)Buffer = 0;
    }
    else
    {
      v21 = 0;
    }
    if ( v21 )
    {
      v20[4] = v21;
      v22 = *(_DWORD *)Buffer;
      if ( *(int *)Buffer < 0 )
        goto LABEL_65;
      if ( (v4 & 1) != 0 )
      {
        v27 = (CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE *)operator new(0x58u);
        if ( v27 )
          v28 = CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE::ASF_MULTI_FILE_RECORDER_NODE(
                  v27,
                  (struct CDVRRingBufferWriter::ASF_RECORDER_NODE *)v20,
                  *((_DWORD *)this + 150),
                  *((void ***)this + 76),
                  (int *)Buffer);
        else
          v28 = 0;
        if ( !v28 )
          goto LABEL_32;
        v22 = *(_DWORD *)Buffer;
        if ( *(int *)Buffer < 0 )
        {
          CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE::`scalar deleting destructor'(
            (CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE *)v28,
            v23);
          goto LABEL_65;
        }
        *((_DWORD *)v20 + 16) |= 8u;
        v20[3] = v28;
        v22 = *(_DWORD *)Buffer;
        if ( *(int *)Buffer < 0 )
          goto LABEL_65;
        v29 = (CDVRFileCollection *)operator new(0x1B0u);
        if ( v29 )
          v29 = CDVRFileCollection::CDVRFileCollection(
                  v29,
                  (const struct CDVRFileCollection::CClientInfo *)(v28 + 32),
                  1,
                  1,
                  0xDu,
                  7u,
                  1,
                  *((_DWORD *)this + 16),
                  *((const unsigned __int16 **)this + 4),
                  (LPCWSTR)v20[7],
                  1,
                  *((_DWORD *)this + 38),
                  (int *)Buffer);
        if ( !v29 )
          goto LABEL_32;
        *(_QWORD *)(v28 + 8) = v29;
        v22 = *(_DWORD *)Buffer;
        if ( *(int *)Buffer < 0 )
          goto LABEL_65;
        v43 = 0;
        v42 = 0;
        v46[0] = 0;
        v22 = CDVRFileCollection::AddFile(
                v29,
                (const struct CDVRFileCollection::CClientInfo *)(v28 + 32),
                (LPCWSTR *)&v42,
                0,
                0,
                1u,
                0,
                1,
                0x7FFFFFFFFFFFFFFFLL,
                v46);
        *(_DWORD *)Buffer = v22;
        if ( v22 < 0 )
          goto LABEL_65;
        v22 = CDVRRingBufferWriter::PrepareAFreeWriterNode(
                this,
                v42,
                *(_DWORD *)(v28 + 48),
                *(void ***)(v28 + 56),
                1u,
                0,
                1u,
                v46[0],
                (struct CDVRRingBufferWriter::ASF_RECORDER_NODE *)v20,
                1,
                &v43);
        *(_DWORD *)Buffer = v22;
        v42 = 0;
        if ( v22 < 0 )
          goto LABEL_65;
        v20[2] = v43 - 1;
      }
      else
      {
        v44 = 0;
        v22 = CDVRRingBufferWriter::PrepareAFreeWriterNode(
                this,
                0,
                *((_DWORD *)this + 150),
                *((void ***)this + 76),
                0,
                *v20,
                v20[1],
                0,
                (struct CDVRRingBufferWriter::ASF_RECORDER_NODE *)v20,
                1,
                &v44);
        *(_DWORD *)Buffer = v22;
        if ( v22 < 0 )
          goto LABEL_65;
        v30 = v44 - 1;
        v20[2] = v44 - 1;
        Flink = v30[3].Flink;
        if ( Flink )
        {
          v32 = *((_QWORD *)v21 + 12);
          if ( v32 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            *((_QWORD *)v21 + 12) = 0;
          }
          *((_QWORD *)v21 + 12) = Flink;
          ((void (__fastcall *)(struct _LIST_ENTRY *))Flink->Flink->Blink)(Flink);
          if ( !*((_QWORD *)v21 + 13) )
          {
            v33 = (CSBERecordingAttributesWM *)operator new(0x20u);
            if ( v33 )
              v33 = CSBERecordingAttributesWM::CSBERecordingAttributesWM(v33, *((struct IWMHeaderInfo **)v21 + 12), 0);
            *((_QWORD *)v21 + 13) = v33;
          }
        }
      }
      v34 = CDVRRingBufferWriter::AddToRecordersList(this, (struct _LIST_ENTRY *)(v20 + 5));
      *(_DWORD *)Buffer = v34;
      v22 = 0;
      if ( v34 < 0 )
        v22 = v34;
      goto LABEL_65;
    }
LABEL_32:
    v22 = -2147024882;
LABEL_65:
    v25 = v38;
  }
  if ( v22 >= 0 )
  {
    v36 = v40;
  }
  else
  {
    operator delete(v25, v23);
    if ( v21 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v21 + 72LL))(v21, 1);
    }
    else if ( v20 )
    {
      CDVRRingBufferWriter::ASF_RECORDER_NODE::`scalar deleting destructor'(
        (CDVRRingBufferWriter::ASF_RECORDER_NODE *)v20,
        v35);
    }
    v36 = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  if ( !v36 )
  {
    if ( WaitForSingleObject(*(HANDLE *)(v20[2] + 88LL), 0xFFFFFFFF) == -1 )
    {
      v37 = GetLastError();
      v22 = v37;
      if ( v37 > 0 )
        v22 = (unsigned __int16)v37 | 0x80070000;
    }
    if ( v22 >= 0
      && (v22 = *((_DWORD *)v20 + 17), v22 >= 0)
      && (v22 = (**(__int64 (__fastcall ***)(char *, GUID *, struct IDVRRecorder **))v21)(v21, &IID_IDVRRecorder, a4),
          v22 >= 0) )
    {
      if ( (v39 & 2) != 0 )
      {
        (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 8LL))(v21);
        *((_DWORD *)v20 + 16) |= 4u;
      }
    }
    else if ( v21 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v21 + 72LL))(v21, 1);
    }
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18006b020  push    rbx
0x18006b022  push    rsi
0x18006b023  push    rdi
0x18006b024  push    r12
0x18006b026  push    r13
0x18006b028  push    r14
0x18006b02a  push    r15
0x18006b02c  sub     rsp, 340h
0x18006b033  mov     rax, cs:__security_cookie
0x18006b03a  xor     rax, rsp
0x18006b03d  mov     [rsp+378h+var_48], rax
0x18006b045  mov     rax, r9
0x18006b048  mov     [rsp+378h+var_2D0], rax
0x18006b050  mov     r14d, r8d
0x18006b053  mov     [rsp+378h+var_2F4], r8d
0x18006b05b  mov     rsi, rdx
0x18006b05e  mov     r13, rcx
0x18006b061  mov     [rsp+378h+var_2C8], rcx
0x18006b069  xor     r15d, r15d
0x18006b06c  mov     [rsp+378h+var_300], r15
0x18006b071  test    r9, r9
0x18006b074  jz      loc_18006B76B
0x18006b07a  mov     [r9], r15
0x18006b07d  test    rdx, rdx
0x18006b080  jz      loc_18006B76B
0x18006b086  cmp     r8d, 3
0x18006b08a  ja      loc_18006B76B
0x18006b090  xor     edi, edi
0x18006b092  mov     [rsp+378h+var_308], edi
0x18006b096  xor     ebx, ebx
0x18006b098  mov     [rsp+378h+var_2F8], ebx
0x18006b09f  xor     eax, eax
0x18006b0a1  mov     [rsp+378h+Buffer], ax
0x18006b0a9  xor     r9d, r9d; lpFilePart
0x18006b0ac  lea     r8, [rsp+378h+Buffer]; lpBuffer
0x18006b0b4  xor     edx, edx; nBufferLength
0x18006b0b6  mov     rcx, rsi; lpFileName
0x18006b0b9  call    cs:__imp_GetFullPathNameW
0x18006b0bf  test    eax, eax
0x18006b0c1  jnz     short loc_18006B0D2
0x18006b0c3  call    cs:__imp_GetLastError
0x18006b0c9  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006b0cd  jmp     loc_18006B1A9
0x18006b0d2  lea     r14d, [rax+1]
0x18006b0d6  mov     ecx, r14d
0x18006b0d9  mov     eax, 2
0x18006b0de  mul     rcx
0x18006b0e1  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18006b0e8  cmovb   rax, r12
0x18006b0ec  mov     rcx, rax; unsigned __int64
0x18006b0ef  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006b0f4  mov     r15, rax
0x18006b0f7  mov     [rsp+378h+var_300], rax
0x18006b0fc  test    rax, rax
0x18006b0ff  jnz     short loc_18006B117
0x18006b101  mov     edi, 8007000Eh
0x18006b106  mov     [rsp+378h+var_308], edi
0x18006b10a  mov     r14d, [rsp+378h+var_2F4]
0x18006b112  jmp     loc_18006B1B2
0x18006b117  xor     r9d, r9d; lpFilePart
0x18006b11a  mov     r8, r15; lpBuffer
0x18006b11d  mov     edx, r14d; nBufferLength
0x18006b120  mov     rcx, rsi; lpFileName
0x18006b123  call    cs:__imp_GetFullPathNameW
0x18006b129  test    eax, eax
0x18006b12b  jz      short loc_18006B19B
0x18006b12d  cmp     eax, r14d
0x18006b130  ja      short loc_18006B19B
0x18006b132  xor     edx, edx; Val
0x18006b134  mov     r8d, 250h; Size
0x18006b13a  lea     rcx, [rsp+378h+FindFileData]; void *
0x18006b142  call    memset_0
0x18006b147  lea     rdx, [rsp+378h+FindFileData]; lpFindFileData
0x18006b14f  mov     rcx, r15; lpFileName
0x18006b152  call    cs:__imp_FindFirstFileW
0x18006b158  cmp     rax, r12
0x18006b15b  jz      short loc_18006B174
0x18006b15d  mov     rcx, rax; hFindFile
0x18006b160  call    cs:__imp_FindClose
0x18006b166  mov     ebx, 0B7h
0x18006b16b  mov     [rsp+378h+var_2F8], ebx
0x18006b172  jmp     short loc_18006B10A
0x18006b174  call    cs:__imp_GetLastError
0x18006b17a  mov     ebx, eax
0x18006b17c  mov     [rsp+378h+var_2F8], eax
0x18006b183  mov     r14d, [rsp+378h+var_2F4]
0x18006b18b  cmp     eax, 2
0x18006b18e  jnz     short loc_18006B1B2
0x18006b190  xor     ebx, ebx
0x18006b192  mov     [rsp+378h+var_2F8], ebx
0x18006b199  jmp     short loc_18006B1B2
0x18006b19b  call    cs:__imp_GetLastError
0x18006b1a1  mov     r14d, [rsp+378h+var_2F4]
0x18006b1a9  mov     [rsp+378h+var_2F8], eax
0x18006b1b0  mov     ebx, eax
0x18006b1b2  test    edi, edi
0x18006b1b4  jnz     short loc_18006B1C9
0x18006b1b6  xor     eax, eax
0x18006b1b8  mov     [rsp+378h+var_2F0], eax
0x18006b1bf  test    ebx, ebx
0x18006b1c1  jnz     short loc_18006B1CD
0x18006b1c3  lea     r15d, [rdi+1]
0x18006b1c7  jmp     short loc_18006B1F4
0x18006b1c9  test    ebx, ebx
0x18006b1cb  jz      short loc_18006B1DC
0x18006b1cd  jg      short loc_18006B1D3
0x18006b1cf  mov     edi, ebx
0x18006b1d1  jmp     short loc_18006B1DC
0x18006b1d3  movzx   edi, bx
0x18006b1d6  or      edi, 80070000h
0x18006b1dc  mov     rcx, r15; void *
0x18006b1df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b1e4  mov     r15d, 1
0x18006b1ea  mov     eax, r15d
0x18006b1ed  mov     [rsp+378h+var_2F0], eax
0x18006b1f4  test    eax, eax
0x18006b1f6  jz      short loc_18006B1FF
0x18006b1f8  mov     eax, edi
0x18006b1fa  jmp     loc_18006B770
0x18006b1ff  xor     edi, edi
0x18006b201  mov     [rsp+378h+var_2E0], rdi
0x18006b209  xor     esi, esi
0x18006b20b  mov     [rsp+378h+var_2E8], rsi
0x18006b213  mov     ebx, 80004005h
0x18006b218  mov     [rsp+378h+var_308], ebx
0x18006b21c  lea     rax, [r13+1F0h]
0x18006b223  mov     [rsp+378h+lpCriticalSection], rax
0x18006b22b  mov     rcx, rax; lpCriticalSection
0x18006b22e  call    cs:__imp_EnterCriticalSection
0x18006b234  nop
0x18006b235  mov     dword ptr [rsp+378h+Buffer], esi
0x18006b23c  cmp     dword ptr [r13+1E8h], 80000000h
0x18006b247  jz      loc_18006B66D
0x18006b24d  lea     ecx, [rdi+48h]; Size
0x18006b250  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b255  mov     rdi, rax
0x18006b258  test    rax, rax
0x18006b25b  jz      short loc_18006B294
0x18006b25d  mov     [rax], r12
0x18006b260  mov     [rax+8], r12
0x18006b264  mov     [rax+10h], rsi
0x18006b268  mov     [rax+18h], rsi
0x18006b26c  mov     [rax+20h], rsi
0x18006b270  mov     rax, [rsp+378h+var_300]
0x18006b275  mov     [rdi+38h], rax
0x18006b279  mov     qword ptr [rdi+40h], 1
0x18006b281  mov     [rdi+30h], rsi
0x18006b285  mov     [rdi+28h], rsi
0x18006b289  xor     ebx, ebx
0x18006b28b  mov     dword ptr [rsp+378h+Buffer], ebx
0x18006b292  jmp     short loc_18006B29D
0x18006b294  xor     edi, edi
0x18006b296  mov     ebx, dword ptr [rsp+378h+Buffer]
0x18006b29d  mov     [rsp+378h+var_2E0], rdi
0x18006b2a5  test    rdi, rdi
0x18006b2a8  jnz     short loc_18006B2B4
0x18006b2aa  mov     ebx, 8007000Eh
0x18006b2af  jmp     loc_18006B66D
0x18006b2b4  xor     eax, eax
0x18006b2b6  mov     [rsp+378h+var_300], rax
0x18006b2bb  test    ebx, ebx
0x18006b2bd  jns     short loc_18006B2C8
0x18006b2bf  mov     [rsp+378h+var_308], ebx
0x18006b2c3  jmp     loc_18006B676
0x18006b2c8  mov     ecx, 70h ; 'p'; Size
0x18006b2cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b2d2  mov     rsi, rax
0x18006b2d5  test    rax, rax
0x18006b2d8  jz      short loc_18006B341
0x18006b2da  lea     rax, ??_7CDVRRecorder@@6BIDVRRecorder@@@; const CDVRRecorder::`vftable'{for `IDVRRecorder'}
0x18006b2e1  mov     [rsi], rax
0x18006b2e4  lea     rax, ??_7CDVRRecorder@@6BIDVRIORecordingAttributes@@@; const CDVRRecorder::`vftable'{for `IDVRIORecordingAttributes'}
0x18006b2eb  mov     [rsi+8], rax
0x18006b2ef  mov     [rsi+10h], r12
0x18006b2f3  mov     [rsi+18h], r12
0x18006b2f7  mov     [rsi+20h], r13
0x18006b2fb  lea     rax, [rdi+28h]
0x18006b2ff  mov     [rsi+28h], rax
0x18006b303  mov     dword ptr [rsi+58h], 0
0x18006b30a  mov     qword ptr [rsi+60h], 0
0x18006b312  mov     qword ptr [rsi+68h], 0
0x18006b31a  lea     rcx, [rsi+30h]; lpCriticalSection
0x18006b31e  call    cs:__imp_InitializeCriticalSection
0x18006b324  mov     rcx, [rsi+20h]
0x18006b328  mov     rax, [rcx]
0x18006b32b  mov     rax, [rax+8]
0x18006b32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b334  mov     dword ptr [rsp+378h+Buffer], 0
0x18006b33f  jmp     short loc_18006B343
0x18006b341  xor     esi, esi
0x18006b343  mov     [rsp+378h+var_2E8], rsi
0x18006b34b  test    rsi, rsi
0x18006b34e  jz      loc_18006B2AA
0x18006b354  mov     [rdi+20h], rsi
0x18006b358  mov     ebx, dword ptr [rsp+378h+Buffer]
0x18006b35f  test    ebx, ebx
0x18006b361  js      loc_18006B66D
0x18006b367  test    r15b, r14b
0x18006b36a  jz      loc_18006B574
0x18006b370  mov     ecx, 58h ; 'X'; Size
0x18006b375  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b37a  test    rax, rax
0x18006b37d  jz      short loc_18006B3AA
0x18006b37f  lea     rcx, [rsp+378h+Buffer]
0x18006b387  mov     [rsp+378h+var_358], rcx; int *
0x18006b38c  mov     r9, [r13+260h]; void **
0x18006b393  mov     r8d, [r13+258h]; unsigned int
0x18006b39a  mov     rdx, rdi; struct CDVRRingBufferWriter::ASF_RECORDER_NODE *
0x18006b39d  mov     rcx, rax; this
0x18006b3a0  call    ??0ASF_MULTI_FILE_RECORDER_NODE@CDVRRingBufferWriter@@QEAA@PEAUASF_RECORDER_NODE@1@KPEAPEAXPEAJ@Z; CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE::ASF_MULTI_FILE_RECORDER_NODE(CDVRRingBufferWriter::ASF_RECORDER_NODE *,ulong,void * *,long *)
0x18006b3a5  mov     r14, rax
0x18006b3a8  jmp     short loc_18006B3AD
0x18006b3aa  xor     r14d, r14d
0x18006b3ad  test    r14, r14
0x18006b3b0  jz      loc_18006B2AA
0x18006b3b6  mov     ebx, dword ptr [rsp+378h+Buffer]
0x18006b3bd  test    ebx, ebx
0x18006b3bf  jns     short loc_18006B3D2
0x18006b3c1  mov     [rsp+378h+var_308], ebx
0x18006b3c5  mov     rcx, r14; this
0x18006b3c8  call    ??_GASF_MULTI_FILE_RECORDER_NODE@CDVRRingBufferWriter@@QEAAPEAXI@Z; CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE::`scalar deleting destructor'(uint)
0x18006b3cd  jmp     loc_18006B671
0x18006b3d2  or      dword ptr [rdi+40h], 8
0x18006b3d6  mov     [rdi+18h], r14
0x18006b3da  mov     ebx, dword ptr [rsp+378h+Buffer]
0x18006b3e1  test    ebx, ebx
0x18006b3e3  js      loc_18006B66D
0x18006b3e9  mov     ecx, 1B0h; Size
0x18006b3ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b3f3  test    rax, rax
0x18006b3f6  jz      short loc_18006B456
0x18006b3f8  lea     rcx, [rsp+378h+Buffer]
0x18006b400  mov     [rsp+378h+var_318], rcx; int *
0x18006b405  mov     ecx, [r13+98h]
0x18006b40c  mov     [rsp+378h+var_320], ecx; int
0x18006b410  mov     dword ptr [rsp+378h+var_328], r15d; int
0x18006b415  mov     rcx, [rdi+38h]
0x18006b419  mov     [rsp+378h+lpFileName], rcx; lpFileName
0x18006b41e  mov     rcx, [r13+20h]
0x18006b422  mov     [rsp+378h+var_338], rcx; unsigned __int16 *
0x18006b427  mov     ecx, [r13+40h]
0x18006b42b  mov     [rsp+378h+var_340], ecx; unsigned int
0x18006b42f  mov     dword ptr [rsp+378h+var_348], r15d; int
0x18006b434  mov     [rsp+378h+var_350], 7; unsigned int
0x18006b43c  mov     dword ptr [rsp+378h+var_358], 0Dh; unsigned int
0x18006b444  mov     r9d, r15d; unsigned int
0x18006b447  mov     r8d, r15d; unsigned int
0x18006b44a  lea     rdx, [r14+20h]; struct CDVRFileCollection::CClientInfo *
0x18006b44e  mov     rcx, rax; this
0x18006b451  call    ??0CDVRFileCollection@@QEAA@PEBUCClientInfo@0@KKKKHKPEBG1HHPEAJ@Z; CDVRFileCollection::CDVRFileCollection(CDVRFileCollection::CClientInfo const *,ulong,ulong,ulong,ulong,int,ulong,ushort const *,ushort const *,int,int,long *)
0x18006b456  test    rax, rax
0x18006b459  jz      loc_18006B2AA
0x18006b45f  mov     [r14+8], rax
0x18006b463  mov     ebx, dword ptr [rsp+378h+Buffer]
0x18006b46a  test    ebx, ebx
0x18006b46c  js      loc_18006B66D
0x18006b472  mov     [rsp+378h+var_2B8], 0
0x18006b47e  mov     [rsp+378h+var_2C0], 0
0x18006b48a  mov     [rsp+378h+var_2A4], 0
0x18006b495  lea     rcx, [rsp+378h+var_2A4]
0x18006b49d  mov     [rsp+378h+lpFileName], rcx; unsigned int *
0x18006b4a2  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18006b4ac  mov     [rsp+378h+var_338], rcx; __int64
0x18006b4b1  mov     [rsp+378h+var_340], r15d; int
0x18006b4b6  mov     dword ptr [rsp+378h+var_348], 0; int
0x18006b4be  mov     qword ptr [rsp+378h+var_350], r15; unsigned __int64
0x18006b4c3  mov     [rsp+378h+var_358], 0; unsigned __int64
0x18006b4cc  xor     r9d, r9d; int
0x18006b4cf  lea     r8, [rsp+378h+var_2C0]; unsigned __int16 **
0x18006b4d7  lea     rdx, [r14+20h]; struct CDVRFileCollection::CClientInfo *
0x18006b4db  mov     rcx, rax; this
0x18006b4de  call    ?AddFile@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@PEAPEAGH_K2HH_JPEAK@Z; CDVRFileCollection::AddFile(CDVRFileCollection::CClientInfo const *,ushort * *,int,unsigned __int64,unsigned __int64,int,int,__int64,ulong *)
0x18006b4e3  mov     ebx, eax
0x18006b4e5  mov     dword ptr [rsp+378h+Buffer], eax
0x18006b4ec  test    eax, eax
0x18006b4ee  jns     short loc_18006B4F9
0x18006b4f0  mov     [rsp+378h+var_308], eax
0x18006b4f4  jmp     loc_18006B671
0x18006b4f9  lea     rax, [rsp+378h+var_2B8]
0x18006b501  mov     [rsp+378h+var_328], rax; struct _LIST_ENTRY **
0x18006b506  mov     dword ptr [rsp+378h+lpFileName], r15d; int
0x18006b50b  mov     [rsp+378h+var_338], rdi; struct CDVRRingBufferWriter::ASF_RECORDER_NODE *
0x18006b510  mov     eax, [rsp+378h+var_2A4]
0x18006b517  mov     [rsp+378h+var_340], eax; unsigned int
0x18006b51b  mov     [rsp+378h+var_348], r15; unsigned __int64
0x18006b520  mov     qword ptr [rsp+378h+var_350], 0; unsigned __int64
0x18006b529  mov     dword ptr [rsp+378h+var_358], r15d; unsigned int
0x18006b52e  mov     r9, [r14+38h]; void **
0x18006b532  mov     r8d, [r14+30h]; unsigned int
0x18006b536  mov     rdx, [rsp+378h+var_2C0]; unsigned __int16 *
0x18006b53e  mov     rcx, r13; this
0x18006b541  call    ?PrepareAFreeWriterNode@CDVRRingBufferWriter@@IEAAJPEBGKPEAPEAXK_K2KPEAUASF_RECORDER_NODE@1@HAEAPEAU_LIST_ENTRY@@@Z; CDVRRingBufferWriter::PrepareAFreeWriterNode(ushort const *,ulong,void * *,ulong,unsigned __int64,unsigned __int64,ulong,CDVRRingBufferWriter::ASF_RECORDER_NODE *,int,_LIST_ENTRY * &)
0x18006b546  mov     ebx, eax
0x18006b548  mov     dword ptr [rsp+378h+Buffer], eax
0x18006b54f  mov     [rsp+378h+var_2C0], 0
0x18006b55b  test    eax, eax
0x18006b55d  js      short loc_18006B4F0
0x18006b55f  mov     rax, [rsp+378h+var_2B8]
0x18006b567  add     rax, 0FFFFFFFFFFFFFFF0h
0x18006b56b  mov     [rdi+10h], rax
  ... truncated ...
```
