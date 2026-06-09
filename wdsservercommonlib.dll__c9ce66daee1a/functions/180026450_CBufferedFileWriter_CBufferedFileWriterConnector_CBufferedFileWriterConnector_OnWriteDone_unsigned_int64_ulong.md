# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::IssueWrite(CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT *,CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::_DATA_BLOCK * *,ulong)

- ea: `0x180026450`
- end: `0x1800265f4`
- name: `?IssueWrite@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKPEAUDATA_SEGMENT@1@PEAPEAU_DATA_BLOCK@1@K@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026600`

## callees

- `0x180026450`
- `0x180026980`
- `0x180027294`
- `0x180027390`
- `0x18002e468`
- `0x18002f3a2`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026535`
- `KERNEL32!GetLastError` at `0x180026535`
- `KERNEL32!HeapAlloc` at `0x180026490`
- `KERNEL32!HeapAlloc` at `0x180026490`
- `KERNEL32!WriteFile` at `0x180026525`
- `KERNEL32!WriteFile` at `0x180026525`

## string_xrefs

- `0x180026547`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x180026583`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

## pseudocode

```c
__int64 __fastcall CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::IssueWrite(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  SIZE_T v5; // r8
  __int64 LastError; // rbx
  char *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rsi
  char *v14; // rbp
  __int64 v15; // r15
  void *v16; // rax
  DWORD v17; // r8d
  void *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-48h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp+10h] BYREF

  v5 = *(unsigned int *)(a2 + 8);
  LODWORD(LastError) = 0;
  NumberOfBytesWritten = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  v10 = (char *)HeapAlloc(hHeap, 0, v5);
  v13 = *(int *)(a2 + 12);
  v14 = v10;
  if ( (int)v13 <= *(_DWORD *)(a2 + 16) )
  {
    v15 = a3 + 8 * v13;
    while ( (unsigned int)v13 < a4 || (int)ElValidateHr_8(2147483659LL, v11, v12, 920) >= 0 )
    {
      memcpy_0(
        &v14[**(_QWORD **)v15 - *(_QWORD *)a2],
        *(const void **)(*(_QWORD *)v15 + 16LL),
        *(unsigned int *)(*(_QWORD *)v15 + 8LL));
      LODWORD(v13) = v13 + 1;
      v15 += 8;
      if ( (int)v13 > *(_DWORD *)(a2 + 16) )
        goto LABEL_6;
    }
    LODWORD(LastError) = -2147483637;
    goto LABEL_13;
  }
LABEL_6:
  v16 = *(void **)a2;
  v17 = *(_DWORD *)(a2 + 8);
  v18 = *(void **)(a1 + 48);
  Overlapped.InternalHigh = 0;
  Overlapped.hEvent = 0;
  Overlapped.Pointer = v16;
  if ( WriteFile(v18, v14, v17, &NumberOfBytesWritten, &Overlapped) )
  {
    *(_QWORD *)(a1 + 72) += NumberOfBytesWritten;
    if ( *(_QWORD *)(a1 + 72) != *(_QWORD *)(a1 + 56)
      || (LastError = (unsigned int)CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::OnAllWritesDone(a1),
          !(unsigned int)ElValidateWin32_14(
                           LastError,
                           v20,
                           "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
                           963)) )
    {
      (**(void (__fastcall ***)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 40))(
        0,
        *(unsigned int *)(a2 + 8),
        0,
        *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL));
    }
  }
  else
  {
    LastError = GetLastError();
    ElValidateWin32_14(LastError, v19, "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h", 946);
  }
  if ( (_DWORD)LastError )
LABEL_13:
    (**(void (__fastcall ***)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 40))(
      (unsigned int)LastError,
      0,
      0,
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL));
  if ( v14 )
    operator delete(v14);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180026450  mov     rax, rsp
0x180026453  mov     [rax+8], rbx
0x180026457  mov     [rax+18h], rbp
0x18002645b  push    rsi
0x18002645c  push    rdi
0x18002645d  push    r12
0x18002645f  push    r14
0x180026461  push    r15
0x180026463  sub     rsp, 50h
0x180026467  xorps   xmm0, xmm0
0x18002646a  mov     r15, r8
0x18002646d  mov     r8d, [rdx+8]; dwBytes
0x180026471  mov     r14, rdx
0x180026474  mov     rdi, rcx
0x180026477  xor     ebx, ebx
0x180026479  mov     rcx, cs:hHeap; hHeap
0x180026480  xor     edx, edx; dwFlags
0x180026482  and     [rax+10h], ebx
0x180026485  mov     r12d, r9d
0x180026488  movups  xmmword ptr [rax-48h], xmm0
0x18002648c  movups  xmmword ptr [rax-38h], xmm0
0x180026490  call    cs:__imp_HeapAlloc
0x180026497  nop     dword ptr [rax+rax+00h]
0x18002649c  movsxd  rsi, dword ptr [r14+0Ch]
0x1800264a0  mov     rbp, rax
0x1800264a3  cmp     esi, [r14+10h]
0x1800264a7  jg      short loc_1800264EF
0x1800264a9  lea     r15, [r15+rsi*8]
0x1800264ad  cmp     esi, r12d
0x1800264b0  jb      short loc_1800264CA
0x1800264b2  mov     ecx, 8000000Bh
0x1800264b7  mov     r9d, 398h
0x1800264bd  call    ElValidateHr_8
0x1800264c2  test    eax, eax
0x1800264c4  js      loc_180026559
0x1800264ca  mov     rdx, [r15]
0x1800264cd  mov     rcx, [rdx]
0x1800264d0  sub     rcx, [r14]
0x1800264d3  mov     r8d, [rdx+8]; Size
0x1800264d7  add     rcx, rbp; void *
0x1800264da  mov     rdx, [rdx+10h]; Src
0x1800264de  call    memcpy_0
0x1800264e3  inc     esi
0x1800264e5  add     r15, 8
0x1800264e9  cmp     esi, [r14+10h]
0x1800264ed  jle     short loc_1800264AD
0x1800264ef  mov     rax, [r14]
0x1800264f2  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800264fa  mov     r8d, [r14+8]; nNumberOfBytesToWrite
0x1800264fe  mov     rdx, rbp; lpBuffer
0x180026501  mov     rcx, [rdi+30h]; hFile
0x180026505  and     [rsp+78h+Overlapped.InternalHigh], rbx
0x18002650a  and     [rsp+78h+Overlapped.hEvent], rbx
0x18002650f  mov     dword ptr [rsp+78h+Overlapped.10h], eax
0x180026513  shr     rax, 20h
0x180026517  mov     dword ptr [rsp+78h+Overlapped.10h+4], eax
0x18002651b  lea     rax, [rsp+78h+Overlapped]
0x180026520  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180026525  call    cs:__imp_WriteFile
0x18002652c  nop     dword ptr [rax+rax+00h]
0x180026531  test    eax, eax
0x180026533  jnz     short loc_180026560
0x180026535  call    cs:__imp_GetLastError
0x18002653c  nop     dword ptr [rax+rax+00h]
0x180026541  mov     r9d, 3B2h
0x180026547  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x18002654e  mov     ecx, eax
0x180026550  mov     ebx, eax
0x180026552  call    ElValidateWin32_14
0x180026557  jmp     short loc_1800265B0
0x180026559  mov     ebx, 8000000Bh
0x18002655e  jmp     short loc_1800265B4
0x180026560  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x180026567  add     [rdi+48h], rax
0x18002656b  mov     rax, [rdi+48h]
0x18002656f  cmp     rax, [rdi+38h]
0x180026573  jnz     short loc_180026597
0x180026575  mov     rcx, rdi
0x180026578  call    ?OnAllWritesDone@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKXZ; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::OnAllWritesDone(void)
0x18002657d  mov     r9d, 3C3h
0x180026583  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x18002658a  mov     ecx, eax
0x18002658c  mov     ebx, eax
0x18002658e  call    ElValidateWin32_14
0x180026593  test    eax, eax
0x180026595  jnz     short loc_1800265B0
0x180026597  mov     r9, [rdi+28h]
0x18002659b  xor     r8d, r8d
0x18002659e  mov     edx, [r14+8]
0x1800265a2  xor     ecx, ecx
0x1800265a4  mov     rax, [r9]
0x1800265a7  mov     r9, [r9+8]
0x1800265ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265b0  test    ebx, ebx
0x1800265b2  jz      short loc_1800265CB
0x1800265b4  mov     r9, [rdi+28h]
0x1800265b8  xor     r8d, r8d
0x1800265bb  xor     edx, edx
0x1800265bd  mov     ecx, ebx
0x1800265bf  mov     rax, [r9]
0x1800265c2  mov     r9, [r9+8]
0x1800265c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265cb  test    rbp, rbp
0x1800265ce  jz      short loc_1800265D8
0x1800265d0  mov     rcx, rbp; lpMem
0x1800265d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800265d8  lea     r11, [rsp+78h+var_28]
0x1800265dd  mov     eax, ebx
0x1800265df  mov     rbx, [r11+30h]
0x1800265e3  mov     rbp, [r11+40h]
0x1800265e7  mov     rsp, r11
0x1800265ea  pop     r15
0x1800265ec  pop     r14
0x1800265ee  pop     r12
0x1800265f0  pop     rdi
0x1800265f1  pop     rsi
0x1800265f2  retn
```
