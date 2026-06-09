# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::IssueWrite(CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT *,CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::_DATA_BLOCK * *,ulong)

- ea: `0x180027580`
- end: `0x18002771a`
- name: `?IssueWrite@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKPEAUDATA_SEGMENT@1@PEAPEAU_DATA_BLOCK@1@K@Z`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027720`

## callees

- `0x1800012e0`
- `0x1800024a6`
- `0x180027580`
- `0x180027ac0`
- `0x1800283e4`
- `0x1800284e0`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800276f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800276f2`
- `KERNEL32!WriteFile` at `0x180027644`
- `KERNEL32!WriteFile` at `0x180027644`
- `KERNEL32!GetLastError` at `0x180027654`
- `KERNEL32!GetLastError` at `0x180027654`

## string_xrefs

- `0x180027666`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x1800276a2`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

## pseudocode

```c
__int64 __fastcall CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::IssueWrite(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  size_t v5; // rcx
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
  v10 = (char *)operator new(v5);
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
0x180027580  mov     rax, rsp
0x180027583  mov     [rax+8], rbx
0x180027587  mov     [rax+18h], rbp
0x18002758b  push    rsi
0x18002758c  push    rdi
0x18002758d  push    r12
0x18002758f  push    r14
0x180027591  push    r15
0x180027593  sub     rsp, 50h
0x180027597  xorps   xmm0, xmm0
0x18002759a  mov     rdi, rcx
0x18002759d  mov     ecx, [rdx+8]; Size
0x1800275a0  xor     ebx, ebx
0x1800275a2  and     [rax+10h], ebx
0x1800275a5  mov     r12d, r9d
0x1800275a8  movups  xmmword ptr [rax-48h], xmm0
0x1800275ac  mov     r15, r8
0x1800275af  mov     r14, rdx
0x1800275b2  movups  xmmword ptr [rax-38h], xmm0
0x1800275b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800275bb  movsxd  rsi, dword ptr [r14+0Ch]
0x1800275bf  mov     rbp, rax
0x1800275c2  cmp     esi, [r14+10h]
0x1800275c6  jg      short loc_18002760E
0x1800275c8  lea     r15, [r15+rsi*8]
0x1800275cc  cmp     esi, r12d
0x1800275cf  jb      short loc_1800275E9
0x1800275d1  mov     ecx, 8000000Bh
0x1800275d6  mov     r9d, 398h
0x1800275dc  call    ElValidateHr_8
0x1800275e1  test    eax, eax
0x1800275e3  js      loc_180027678
0x1800275e9  mov     rdx, [r15]
0x1800275ec  mov     rcx, [rdx]
0x1800275ef  sub     rcx, [r14]
0x1800275f2  mov     r8d, [rdx+8]; Size
0x1800275f6  add     rcx, rbp; void *
0x1800275f9  mov     rdx, [rdx+10h]; Src
0x1800275fd  call    memcpy_0
0x180027602  inc     esi
0x180027604  add     r15, 8
0x180027608  cmp     esi, [r14+10h]
0x18002760c  jle     short loc_1800275CC
0x18002760e  mov     rax, [r14]
0x180027611  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180027619  mov     r8d, [r14+8]; nNumberOfBytesToWrite
0x18002761d  mov     rdx, rbp; lpBuffer
0x180027620  mov     rcx, [rdi+30h]; hFile
0x180027624  and     [rsp+78h+Overlapped.InternalHigh], rbx
0x180027629  and     [rsp+78h+Overlapped.hEvent], rbx
0x18002762e  mov     dword ptr [rsp+78h+Overlapped.10h], eax
0x180027632  shr     rax, 20h
0x180027636  mov     dword ptr [rsp+78h+Overlapped.10h+4], eax
0x18002763a  lea     rax, [rsp+78h+Overlapped]
0x18002763f  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180027644  call    cs:__imp_WriteFile
0x18002764b  nop     dword ptr [rax+rax+00h]
0x180027650  test    eax, eax
0x180027652  jnz     short loc_18002767F
0x180027654  call    cs:__imp_GetLastError
0x18002765b  nop     dword ptr [rax+rax+00h]
0x180027660  mov     r9d, 3B2h
0x180027666  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x18002766d  mov     ecx, eax
0x18002766f  mov     ebx, eax
0x180027671  call    ElValidateWin32_14
0x180027676  jmp     short loc_1800276CF
0x180027678  mov     ebx, 8000000Bh
0x18002767d  jmp     short loc_1800276D3
0x18002767f  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x180027686  add     [rdi+48h], rax
0x18002768a  mov     rax, [rdi+48h]
0x18002768e  cmp     rax, [rdi+38h]
0x180027692  jnz     short loc_1800276B6
0x180027694  mov     rcx, rdi
0x180027697  call    ?OnAllWritesDone@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKXZ; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::OnAllWritesDone(void)
0x18002769c  mov     r9d, 3C3h
0x1800276a2  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800276a9  mov     ecx, eax
0x1800276ab  mov     ebx, eax
0x1800276ad  call    ElValidateWin32_14
0x1800276b2  test    eax, eax
0x1800276b4  jnz     short loc_1800276CF
0x1800276b6  mov     r9, [rdi+28h]
0x1800276ba  xor     r8d, r8d
0x1800276bd  mov     edx, [r14+8]
0x1800276c1  xor     ecx, ecx
0x1800276c3  mov     rax, [r9]
0x1800276c6  mov     r9, [r9+8]
0x1800276ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276cf  test    ebx, ebx
0x1800276d1  jz      short loc_1800276EA
0x1800276d3  mov     r9, [rdi+28h]
0x1800276d7  xor     r8d, r8d
0x1800276da  xor     edx, edx
0x1800276dc  mov     ecx, ebx
0x1800276de  mov     rax, [r9]
0x1800276e1  mov     r9, [r9+8]
0x1800276e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276ea  test    rbp, rbp
0x1800276ed  jz      short loc_1800276FE
0x1800276ef  mov     rcx, rbp
0x1800276f2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800276f9  nop     dword ptr [rax+rax+00h]
0x1800276fe  lea     r11, [rsp+78h+var_28]
0x180027703  mov     eax, ebx
0x180027705  mov     rbx, [r11+30h]
0x180027709  mov     rbp, [r11+40h]
0x18002770d  mov     rsp, r11
0x180027710  pop     r15
0x180027712  pop     r14
0x180027714  pop     r12
0x180027716  pop     rdi
0x180027717  pop     rsi
0x180027718  retn
```
