# WEBDAV_SQM_WRITER::Initialize(void)

- ea: `0x180015c98`
- end: `0x180015e09`
- name: `?Initialize@WEBDAV_SQM_WRITER@@QEAAJXZ`
- size: `369`
- prototype: `__int64 __fastcall(WEBDAV_SQM_WRITER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000806c`

## callees

- `0x180015a54`
- `0x180015c98`
- `0x1800224c2`

## import_xrefs

- `msvcrt!_aligned_malloc` at `0x180015d05`
- `msvcrt!_aligned_malloc` at `0x180015d05`
- `msvcrt!_aligned_free` at `0x180015d21`
- `msvcrt!_aligned_free` at `0x180015d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015db9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015dfc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015dfc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015d38`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015d38`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015daa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015daa`

## pseudocode

```c
__int64 __fastcall WEBDAV_SQM_WRITER::Initialize(WEBDAV_SQM_WRITER *this)
{
  _QWORD *v1; // rdi
  signed int ProcessorInformation; // ebx
  unsigned int v3; // ebx
  __int64 v4; // r15
  size_t v5; // r14
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
  void *v8; // rcx
  struct _TP_TIMER *v9; // rcx
  unsigned int v11; // edx
  __int64 v12; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  unsigned int v15; // [rsp+50h] [rbp+8h] BYREF
  int v16; // [rsp+54h] [rbp+Ch]
  size_t Alignment; // [rsp+58h] [rbp+10h] BYREF
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+18h] BYREF

  v16 = HIDWORD(this);
  v1 = DAV_HTTP_MODULE::sm_pSqmWriter;
  pftDueTime = 0;
  LODWORD(Alignment) = 0;
  v15 = 0;
  ProcessorInformation = PER_CPU<unsigned long>::GetProcessorInformation(&Alignment, &v15);
  if ( ProcessorInformation < 0 )
    goto LABEL_7;
  if ( (unsigned int)Alignment >= 4 )
    v3 = Alignment;
  else
    v3 = (Alignment + 3) & ~(Alignment - 1);
  v4 = (unsigned int)Alignment;
  v5 = (unsigned int)Alignment + v3 * v15;
  v6 = _aligned_malloc(v5, (unsigned int)Alignment);
  v7 = v6;
  if ( !v6 )
  {
    ProcessorInformation = -2147024882;
LABEL_7:
    v8 = (void *)v1[1];
    if ( v8 )
    {
      _aligned_free(v8);
      v1[1] = 0;
    }
    v9 = (struct _TP_TIMER *)v1[4];
    if ( v9 )
    {
      CloseThreadpoolTimer(v9);
      v1[4] = 0;
    }
    return (unsigned int)ProcessorInformation;
  }
  memset_0(v6, 0, v5);
  v11 = 0;
  *v7 = (char *)v7 + v4;
  v7[2] = v15;
  for ( v7[1] = v3; (unsigned __int64)v11 < v7[2]; *(_DWORD *)(v7[1] * v12 + *v7) = 0 )
    v12 = v11++;
  v1[1] = v7;
  ThreadpoolTimer = CreateThreadpoolTimer(WEBDAV_SQM_WRITER::DataCollectCallback, v1, 0);
  v1[4] = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    pftDueTime.dwHighDateTime = -9;
    pftDueTime.dwLowDateTime = -1640261632;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x36EE80u, 0);
    return 0;
  }
  LastError = GetLastError();
  ProcessorInformation = LastError;
  if ( LastError > 0 )
    ProcessorInformation = (unsigned __int16)LastError | 0x80070000;
  if ( ProcessorInformation < 0 )
    goto LABEL_7;
  return (unsigned int)ProcessorInformation;
}

```

## disassembly

```asm
0x180015c98  mov     rax, rsp
0x180015c9b  mov     [rax+8], rcx
0x180015c9f  push    rbx
0x180015ca0  push    rsi
0x180015ca1  push    rdi
0x180015ca2  push    r14
0x180015ca4  push    r15
0x180015ca6  sub     rsp, 20h
0x180015caa  mov     rdi, cs:?sm_pSqmWriter@DAV_HTTP_MODULE@@0PEAVWEBDAV_SQM_WRITER@@EA; WEBDAV_SQM_WRITER * DAV_HTTP_MODULE::sm_pSqmWriter
0x180015cb1  lea     rdx, [rax+8]
0x180015cb5  lea     rcx, [rax+10h]
0x180015cb9  mov     qword ptr [rax+18h], 0
0x180015cc1  mov     dword ptr [rax+10h], 0
0x180015cc8  mov     dword ptr [rax+8], 0
0x180015ccf  call    ?GetProcessorInformation@?$PER_CPU@K@@CAJPEAK0@Z; PER_CPU<ulong>::GetProcessorInformation(ulong *,ulong *)
0x180015cd4  mov     ebx, eax
0x180015cd6  test    eax, eax
0x180015cd8  js      short loc_180015D18
0x180015cda  mov     ecx, dword ptr [rsp+48h+Alignment]
0x180015cde  cmp     ecx, 4
0x180015ce1  jnb     short loc_180015CEF
0x180015ce3  lea     ebx, [rcx-1]
0x180015ce6  not     ebx
0x180015ce8  lea     eax, [rcx+3]
0x180015ceb  and     ebx, eax
0x180015ced  jmp     short loc_180015CF1
0x180015cef  mov     ebx, ecx
0x180015cf1  mov     eax, [rsp+48h+arg_0]
0x180015cf5  mov     r15, rcx
0x180015cf8  imul    eax, ebx
0x180015cfb  mov     rdx, rcx; Alignment
0x180015cfe  add     eax, ecx
0x180015d00  mov     ecx, eax; Size
0x180015d02  mov     r14d, eax
0x180015d05  call    cs:__imp__aligned_malloc
0x180015d0b  mov     rsi, rax
0x180015d0e  test    rax, rax
0x180015d11  jnz     short loc_180015D54
0x180015d13  mov     ebx, 8007000Eh
0x180015d18  mov     rcx, [rdi+8]; Block
0x180015d1c  test    rcx, rcx
0x180015d1f  jz      short loc_180015D2F
0x180015d21  call    cs:__imp__aligned_free
0x180015d27  mov     qword ptr [rdi+8], 0
0x180015d2f  mov     rcx, [rdi+20h]; pti
0x180015d33  test    rcx, rcx
0x180015d36  jz      short loc_180015D46
0x180015d38  call    cs:__imp_CloseThreadpoolTimer
0x180015d3e  mov     qword ptr [rdi+20h], 0
0x180015d46  mov     eax, ebx
0x180015d48  add     rsp, 20h
0x180015d4c  pop     r15
0x180015d4e  pop     r14
0x180015d50  pop     rdi
0x180015d51  pop     rsi
0x180015d52  pop     rbx
0x180015d53  retn
0x180015d54  mov     r8, r14; Size
0x180015d57  xor     edx, edx; Val
0x180015d59  mov     rcx, rsi; void *
0x180015d5c  call    memset_0
0x180015d61  lea     rax, [r15+rsi]
0x180015d65  xor     edx, edx
0x180015d67  mov     [rsi], rax
0x180015d6a  mov     eax, [rsp+48h+arg_0]
0x180015d6e  mov     [rsi+10h], rax
0x180015d72  mov     eax, ebx
0x180015d74  mov     [rsi+8], rax
0x180015d78  cmp     [rsp+48h+arg_0], edx
0x180015d7c  jbe     short loc_180015D99
0x180015d7e  mov     rax, [rsi]
0x180015d81  mov     ecx, edx
0x180015d83  inc     edx
0x180015d85  imul    rcx, [rsi+8]
0x180015d8a  mov     dword ptr [rcx+rax], 0
0x180015d91  mov     eax, edx
0x180015d93  cmp     rax, [rsi+10h]
0x180015d97  jb      short loc_180015D7E
0x180015d99  mov     [rdi+8], rsi
0x180015d9d  xor     r8d, r8d; pcbe
0x180015da0  lea     rcx, ?DataCollectCallback@WEBDAV_SQM_WRITER@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180015da7  mov     rdx, rdi; pv
0x180015daa  call    cs:__imp_CreateThreadpoolTimer
0x180015db0  mov     [rdi+20h], rax
0x180015db4  test    rax, rax
0x180015db7  jnz     short loc_180015DDB
0x180015db9  call    cs:__imp_GetLastError
0x180015dbf  mov     ebx, eax
0x180015dc1  test    eax, eax
0x180015dc3  jle     short loc_180015DCE
0x180015dc5  movzx   ebx, ax
0x180015dc8  or      ebx, 80070000h
0x180015dce  test    ebx, ebx
0x180015dd0  jns     loc_180015D46
0x180015dd6  jmp     loc_180015D18
0x180015ddb  xor     r9d, r9d; msWindowLength
0x180015dde  mov     [rsp+48h+pftDueTime.dwHighDateTime], 0FFFFFFF7h
0x180015de6  mov     r8d, 36EE80h; msPeriod
0x180015dec  mov     [rsp+48h+pftDueTime.dwLowDateTime], 9E3B9800h
0x180015df4  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180015df9  mov     rcx, rax; pti
0x180015dfc  call    cs:__imp_SetThreadpoolTimer
0x180015e02  xor     ebx, ebx
0x180015e04  jmp     loc_180015D46
```
