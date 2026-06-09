# SBE2PauseBuffer::CSBE2PauseBufferWriter::WorkerThread(void)

- ea: `0x1800aa530`
- end: `0x1800aa77b`
- name: `?WorkerThread@CSBE2PauseBufferWriter@SBE2PauseBuffer@@AEAAXXZ`
- size: `587`
- prototype: `void __fastcall(SBE2PauseBuffer::CSBE2PauseBufferWriter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800aa790`

## callees

- `0x1800089b8`
- `0x18002d050`
- `0x1800612b4`
- `0x180062710`
- `0x1800627f0`
- `0x1800a8f08`
- `0x1800aa3b0`
- `0x1800aa530`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800aa552`
- `KERNEL32!GetCurrentThread` at `0x1800aa552`
- `KERNEL32!WaitForSingleObject` at `0x1800aa60b`
- `KERNEL32!WaitForSingleObject` at `0x1800aa60b`
- `KERNEL32!LeaveCriticalSection` at `0x1800aa6bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800aa720`
- `KERNEL32!LeaveCriticalSection` at `0x1800aa6bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800aa720`
- `KERNEL32!EnterCriticalSection` at `0x1800aa696`
- `KERNEL32!EnterCriticalSection` at `0x1800aa6f8`
- `KERNEL32!EnterCriticalSection` at `0x1800aa696`
- `KERNEL32!EnterCriticalSection` at `0x1800aa6f8`
- `KERNEL32!SetThreadPriority` at `0x1800aa6d7`
- `KERNEL32!SetThreadPriority` at `0x1800aa6ef`
- `KERNEL32!SetThreadPriority` at `0x1800aa6d7`
- `KERNEL32!SetThreadPriority` at `0x1800aa6ef`
- `ole32!CoInitializeEx` at `0x1800aa5b9`
- `ole32!CoInitializeEx` at `0x1800aa5b9`
- `ole32!CoUninitialize` at `0x1800aa75c`
- `ole32!CoUninitialize` at `0x1800aa75c`

## string_xrefs

- `0x1800aa5cc`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`
- `0x1800aa624`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`
- `0x1800aa731`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`

## pseudocode

```c
void __fastcall SBE2PauseBuffer::CSBE2PauseBufferWriter::WorkerThread(SBE2PauseBuffer::CSBE2PauseBufferWriter *this)
{
  HANDLE CurrentThread; // r12
  int v3; // r8d
  unsigned int v4; // eax
  __int64 v5; // r14
  HRESULT v6; // r15d
  signed int v7; // r9d
  unsigned int v8; // r8d
  unsigned int i; // ebx
  DWORD v10; // edx
  DWORD v11; // eax
  signed int v12; // esi
  SBECoreUtil *v13; // rcx
  unsigned __int64 SystemTime; // rbp
  struct IPauseBufferNode *v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = 0;
  CurrentThread = GetCurrentThread();
  v4 = CTSDVRSettings::DVRGetVal_(
         *((_DWORD *)this + 266) + 328,
         (unsigned int)L"BackingStoreEachFileDurationSeconds",
         v3,
         300,
         5,
         -1,
         *((_QWORD *)this + 133) + 928LL);
  if ( v4 <= 0x41uLL )
    v5 = 5000;
  else
    v5 = 1000LL * v4 - 60000;
  v6 = CoInitializeEx(0, 0);
  if ( v6 >= 0 )
  {
LABEL_6:
    for ( i = -1; ; i -= 100 )
    {
      do
      {
        while ( 1 )
        {
          if ( *((_DWORD *)this + 230) )
            goto LABEL_31;
          v10 = 100;
          if ( i <= 0x64 )
            v10 = i;
          v11 = WaitForSingleObject(*((HANDLE *)this + 114), v10);
          v12 = v11;
          if ( v11 && v11 != 258 )
          {
            SBEBasicTracers::EtwTraceAssert(
              (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 48),
              "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbwriter.cpp",
              0xEEu);
            v7 = v12 > 0 ? (unsigned __int16)v12 | 0x80070000 : v12;
            if ( v7 < 0 )
            {
              v8 = 239;
              goto LABEL_30;
            }
          }
          if ( *((_DWORD *)this + 230) )
            goto LABEL_31;
          SBE2PauseBuffer::CSBE2PauseBufferWriter::Win7WorkaroundToDataStuckInSBESink(this);
          if ( v12 == 258 )
            break;
LABEL_21:
          SystemTime = SBECoreUtil::GetSystemTime(v13);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
          i = 0;
          if ( v5 + *((_QWORD *)this + 122) > SystemTime )
            i = *((_DWORD *)this + 244) + v5 - SystemTime;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
          if ( !i )
          {
            if ( !v15 )
            {
              SetThreadPriority(CurrentThread, -1);
              SBE2PauseBuffer::CSBE2PauseBufferWriter::CreatePauseBufferNode(this, &v15);
              SetThreadPriority(CurrentThread, 0);
            }
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
            if ( !*((_QWORD *)this + 123) )
            {
              *((_QWORD *)this + 123) = v15;
              v15 = 0;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
            goto LABEL_6;
          }
        }
      }
      while ( i == -1 );
      if ( i <= 0x64 )
        goto LABEL_21;
    }
  }
  SBEBasicTracers::EtwTraceAssert(
    (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 48),
    "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbwriter.cpp",
    0xD7u);
  v7 = v6;
  v8 = 216;
LABEL_30:
  SBEBasicTracers::EtwTraceError(
    (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 48),
    "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbwriter.cpp",
    v8,
    v7);
LABEL_31:
  EhEtw::TPtr<IEhTraceSpan>::Release(&v15);
  EhEtw::TPtr<IEhTraceSpan>::Release((char *)this + 984);
  if ( v6 >= 0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800aa530  mov     [rsp+arg_8], rbx
0x1800aa535  mov     [rsp+arg_10], rbp
0x1800aa53a  push    rsi
0x1800aa53b  push    rdi
0x1800aa53c  push    r12
0x1800aa53e  push    r14
0x1800aa540  push    r15
0x1800aa542  sub     rsp, 40h
0x1800aa546  mov     rdi, rcx
0x1800aa549  mov     [rsp+68h+arg_0], 0
0x1800aa552  call    cs:__imp_GetCurrentThread
0x1800aa558  mov     rcx, [rdi+428h]
0x1800aa55f  lea     rdx, aBackingstoreea; "BackingStoreEachFileDurationSeconds"
0x1800aa566  add     rcx, 148h
0x1800aa56d  mov     r12, rax
0x1800aa570  mov     r9d, 12Ch
0x1800aa576  lea     rax, [rcx+258h]
0x1800aa57d  mov     [rsp+68h+var_38], rax
0x1800aa582  mov     [rsp+68h+var_40], 0FFFFFFFFh
0x1800aa58a  mov     [rsp+68h+var_48], 5
0x1800aa592  call    ?DVRGetVal_@CTSDVRSettings@@AEAAKPEBGHKKKPEAU?$CTRegVal@K@1@@Z; CTSDVRSettings::DVRGetVal_(ushort const *,int,ulong,ulong,ulong,CTSDVRSettings::CTRegVal<ulong> *)
0x1800aa597  mov     eax, eax
0x1800aa599  cmp     rax, 41h ; 'A'
0x1800aa59d  jbe     short loc_1800AA5AF
0x1800aa59f  imul    r14, rax, 3E8h
0x1800aa5a6  sub     r14, 0EA60h
0x1800aa5ad  jmp     short loc_1800AA5B5
0x1800aa5af  mov     r14d, 1388h
0x1800aa5b5  xor     edx, edx; dwCoInit
0x1800aa5b7  xor     ecx, ecx; pvReserved
0x1800aa5b9  call    cs:__imp_CoInitializeEx
0x1800aa5bf  mov     r15d, eax
0x1800aa5c2  test    eax, eax
0x1800aa5c4  jns     short loc_1800AA5EA
0x1800aa5c6  mov     r8d, 0D7h; unsigned int
0x1800aa5cc  lea     rdx, aMultimediaDsho_27; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800aa5d3  lea     rcx, [rdi+30h]; struct CEhEventTracer *
0x1800aa5d7  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800aa5dc  mov     r9d, r15d
0x1800aa5df  mov     r8d, 0D8h
0x1800aa5e5  jmp     loc_1800AA731
0x1800aa5ea  or      ebx, 0FFFFFFFFh
0x1800aa5ed  cmp     dword ptr [rdi+398h], 0
0x1800aa5f4  jnz     loc_1800AA741
0x1800aa5fa  mov     rcx, [rdi+390h]; hHandle
0x1800aa601  mov     edx, 64h ; 'd'
0x1800aa606  cmp     ebx, edx
0x1800aa608  cmovbe  edx, ebx; dwMilliseconds
0x1800aa60b  call    cs:__imp_WaitForSingleObject
0x1800aa611  mov     esi, eax
0x1800aa613  test    eax, eax
0x1800aa615  jz      short loc_1800AA651
0x1800aa617  cmp     eax, 102h
0x1800aa61c  jz      short loc_1800AA651
0x1800aa61e  mov     r8d, 0EEh; unsigned int
0x1800aa624  lea     rdx, aMultimediaDsho_27; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800aa62b  lea     rcx, [rdi+30h]; struct CEhEventTracer *
0x1800aa62f  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800aa634  test    esi, esi
0x1800aa636  jg      short loc_1800AA63D
0x1800aa638  mov     r9d, esi
0x1800aa63b  jmp     short loc_1800AA648
0x1800aa63d  movzx   r9d, si
0x1800aa641  or      r9d, 80070000h; unsigned int
0x1800aa648  test    r9d, r9d
0x1800aa64b  js      loc_1800AA72B
0x1800aa651  cmp     dword ptr [rdi+398h], 0
0x1800aa658  jnz     loc_1800AA741
0x1800aa65e  mov     rcx, rdi; this
0x1800aa661  call    ?Win7WorkaroundToDataStuckInSBESink@CSBE2PauseBufferWriter@SBE2PauseBuffer@@AEAAJXZ; SBE2PauseBuffer::CSBE2PauseBufferWriter::Win7WorkaroundToDataStuckInSBESink(void)
0x1800aa666  cmp     esi, 102h
0x1800aa66c  jnz     short loc_1800AA684
0x1800aa66e  cmp     ebx, 0FFFFFFFFh
0x1800aa671  jz      loc_1800AA5ED
0x1800aa677  cmp     ebx, 64h ; 'd'
0x1800aa67a  jbe     short loc_1800AA684
0x1800aa67c  add     ebx, 0FFFFFF9Ch
0x1800aa67f  jmp     loc_1800AA5ED
0x1800aa684  call    ?GetSystemTime@SBECoreUtil@@YA_KXZ; SBECoreUtil::GetSystemTime(void)
0x1800aa689  lea     rsi, [rdi+3A8h]
0x1800aa690  mov     rbp, rax
0x1800aa693  mov     rcx, rsi; lpCriticalSection
0x1800aa696  call    cs:__imp_EnterCriticalSection
0x1800aa69c  mov     rdx, [rdi+3D0h]
0x1800aa6a3  xor     ebx, ebx
0x1800aa6a5  add     rdx, r14
0x1800aa6a8  cmp     rdx, rbp
0x1800aa6ab  jbe     short loc_1800AA6B8
0x1800aa6ad  mov     ebx, r14d
0x1800aa6b0  sub     ebx, ebp
0x1800aa6b2  add     ebx, [rdi+3D0h]
0x1800aa6b8  mov     rcx, rsi; lpCriticalSection
0x1800aa6bb  call    cs:__imp_LeaveCriticalSection
0x1800aa6c1  test    ebx, ebx
0x1800aa6c3  jnz     loc_1800AA5ED
0x1800aa6c9  cmp     [rsp+68h+arg_0], 0
0x1800aa6cf  jnz     short loc_1800AA6F5
0x1800aa6d1  or      edx, 0FFFFFFFFh; nPriority
0x1800aa6d4  mov     rcx, r12; hThread
0x1800aa6d7  call    cs:__imp_SetThreadPriority
0x1800aa6dd  lea     rdx, [rsp+68h+arg_0]; struct IPauseBufferNode **
0x1800aa6e2  mov     rcx, rdi; this
0x1800aa6e5  call    ?CreatePauseBufferNode@CSBE2PauseBufferWriter@SBE2PauseBuffer@@AEAAJPEAPEAUIPauseBufferNode@@@Z; SBE2PauseBuffer::CSBE2PauseBufferWriter::CreatePauseBufferNode(IPauseBufferNode * *)
0x1800aa6ea  xor     edx, edx; nPriority
0x1800aa6ec  mov     rcx, r12; hThread
0x1800aa6ef  call    cs:__imp_SetThreadPriority
0x1800aa6f5  mov     rcx, rsi; lpCriticalSection
0x1800aa6f8  call    cs:__imp_EnterCriticalSection
0x1800aa6fe  cmp     qword ptr [rdi+3D8h], 0
0x1800aa706  jnz     short loc_1800AA71D
0x1800aa708  mov     rax, [rsp+68h+arg_0]
0x1800aa70d  mov     [rdi+3D8h], rax
0x1800aa714  mov     [rsp+68h+arg_0], 0
0x1800aa71d  mov     rcx, rsi; lpCriticalSection
0x1800aa720  call    cs:__imp_LeaveCriticalSection
0x1800aa726  jmp     loc_1800AA5EA
0x1800aa72b  mov     r8d, 0EFh; unsigned int
0x1800aa731  lea     rdx, aMultimediaDsho_27; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800aa738  lea     rcx, [rdi+30h]; struct CEhEventTracer *
0x1800aa73c  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800aa741  lea     rcx, [rsp+68h+arg_0]
0x1800aa746  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x1800aa74b  lea     rcx, [rdi+3D8h]
0x1800aa752  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x1800aa757  test    r15d, r15d
0x1800aa75a  js      short loc_1800AA762
0x1800aa75c  call    cs:__imp_CoUninitialize
0x1800aa762  lea     r11, [rsp+68h+var_28]
0x1800aa767  mov     rbx, [r11+38h]
0x1800aa76b  mov     rbp, [r11+40h]
0x1800aa76f  mov     rsp, r11
0x1800aa772  pop     r15
0x1800aa774  pop     r14
0x1800aa776  pop     r12
0x1800aa778  pop     rdi
0x1800aa779  pop     rsi
0x1800aa77a  retn
```
