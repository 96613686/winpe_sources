# CDiagnosticProvider::InitSynch(void)

- ea: `0x180007660`
- end: `0x1800077b6`
- name: `?InitSynch@CDiagnosticProvider@@UEAAJXZ`
- size: `342`
- prototype: `__int64 __fastcall(CDiagnosticProvider *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x180002f00`
- `0x180003540`
- `0x180007660`
- `0x180008710`
- `0x180009da0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800076bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800076bf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007774`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007785`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007774`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076d1`

## pseudocode

```c
__int64 __fastcall CDiagnosticProvider::InitSynch(CDiagnosticProvider *this)
{
  int v2; // esi
  int v3; // ebp
  __int64 v4; // rdx
  __int64 v5; // rcx
  int inited; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  void (__fastcall ***v10)(_QWORD, __int64); // rcx

  v2 = 0;
  v3 = 0;
  inited = SDiagPrvSyncObject::InitSynch(this);
  if ( inited >= 0 )
  {
    inited = SDiagPrviInitializeCriticalSection((struct _RTL_CRITICAL_SECTION *)((char *)this + 88));
    if ( inited >= 0 )
    {
      v2 = 1;
      inited = SDiagPrviInitializeCriticalSection((struct _RTL_CRITICAL_SECTION *)((char *)this + 128));
      if ( inited >= 0 )
      {
        v3 = 1;
        EventW = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)this + 21) = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          inited = LastError;
          if ( LastError > 0 )
            inited = (unsigned __int16)LastError | 0x80070000;
          if ( inited < 0 )
            goto LABEL_16;
        }
        v9 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 8);
        if ( v9 )
        {
          (**v9)(v9, 1);
          *((_QWORD *)this + 8) = 0;
        }
        inited = CLocalContentDiagnosticProviderImpl::CreateInstance((struct IDiagnosticProviderImpl **)this + 8, v4);
        if ( inited >= 0 )
        {
          v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 9);
          if ( v10 )
          {
            (**v10)(v10, 1);
            *((_QWORD *)this + 9) = 0;
          }
          inited = CBWCContentDiagnosticProviderImpl::CreateInstance((struct IDiagnosticProviderImpl **)this + 9, v4);
          if ( inited >= 0 )
            *((_DWORD *)this + 21) = 1;
        }
      }
    }
  }
  if ( inited )
  {
LABEL_16:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v5, v4, "CDiagnosticProvider::InitSynch", (unsigned int)inited);
    if ( inited < 0 )
    {
      if ( v2 )
        DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      if ( v3 )
        DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    }
    return (unsigned int)inited;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(v5, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticProvider::InitSynch");
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180007660  push    rbx
0x180007662  push    rbp
0x180007663  push    rsi
0x180007664  push    rdi
0x180007665  push    r14
0x180007667  sub     rsp, 20h
0x18000766b  mov     rdi, rcx
0x18000766e  xor     esi, esi
0x180007670  xor     ebp, ebp
0x180007672  call    ?InitSynch@SDiagPrvSyncObject@@UEAAJXZ; SDiagPrvSyncObject::InitSynch(void)
0x180007677  lea     r14d, [rsi+1]
0x18000767b  mov     ebx, eax
0x18000767d  test    eax, eax
0x18000767f  js      loc_18000774C
0x180007685  lea     rcx, [rdi+58h]; struct _RTL_CRITICAL_SECTION *
0x180007689  call    ?SDiagPrviInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; SDiagPrviInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x18000768e  mov     ebx, eax
0x180007690  test    eax, eax
0x180007692  js      loc_18000774C
0x180007698  lea     rcx, [rdi+80h]; struct _RTL_CRITICAL_SECTION *
0x18000769f  mov     esi, r14d
0x1800076a2  call    ?SDiagPrviInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; SDiagPrviInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800076a7  mov     ebx, eax
0x1800076a9  test    eax, eax
0x1800076ab  js      loc_18000774C
0x1800076b1  xor     r9d, r9d; lpName
0x1800076b4  xor     r8d, r8d; bInitialState
0x1800076b7  mov     edx, r14d; bManualReset
0x1800076ba  xor     ecx, ecx; lpEventAttributes
0x1800076bc  mov     ebp, r14d
0x1800076bf  call    cs:__imp_CreateEventW
0x1800076c5  mov     [rdi+0A8h], rax
0x1800076cc  test    rax, rax
0x1800076cf  jnz     short loc_1800076EA
0x1800076d1  call    cs:__imp_GetLastError
0x1800076d7  mov     ebx, eax
0x1800076d9  test    eax, eax
0x1800076db  jle     short loc_1800076E6
0x1800076dd  movzx   ebx, ax
0x1800076e0  or      ebx, 80070000h
0x1800076e6  test    ebx, ebx
0x1800076e8  js      short loc_180007750
0x1800076ea  lea     rbx, [rdi+40h]
0x1800076ee  mov     rcx, [rbx]
0x1800076f1  test    rcx, rcx
0x1800076f4  jz      short loc_18000770B
0x1800076f6  mov     rax, [rcx]
0x1800076f9  mov     edx, r14d
0x1800076fc  mov     rax, [rax]
0x1800076ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007704  mov     qword ptr [rbx], 0
0x18000770b  mov     rcx, rbx; struct IDiagnosticProviderImpl **
0x18000770e  call    ?CreateInstance@CLocalContentDiagnosticProviderImpl@@SAJPEAPEAVIDiagnosticProviderImpl@@@Z; CLocalContentDiagnosticProviderImpl::CreateInstance(IDiagnosticProviderImpl * *)
0x180007713  mov     ebx, eax
0x180007715  test    eax, eax
0x180007717  js      short loc_18000774C
0x180007719  lea     rbx, [rdi+48h]
0x18000771d  mov     rcx, [rbx]
0x180007720  test    rcx, rcx
0x180007723  jz      short loc_18000773A
0x180007725  mov     rax, [rcx]
0x180007728  mov     edx, r14d
0x18000772b  mov     rax, [rax]
0x18000772e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007733  mov     qword ptr [rbx], 0
0x18000773a  mov     rcx, rbx; struct IDiagnosticProviderImpl **
0x18000773d  call    ?CreateInstance@CBWCContentDiagnosticProviderImpl@@SAJPEAPEAVIDiagnosticProviderImpl@@@Z; CBWCContentDiagnosticProviderImpl::CreateInstance(IDiagnosticProviderImpl * *)
0x180007742  mov     ebx, eax
0x180007744  test    eax, eax
0x180007746  js      short loc_18000774C
0x180007748  mov     [rdi+54h], r14d
0x18000774c  test    ebx, ebx
0x18000774e  jz      short loc_18000778D
0x180007750  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180007757  jz      short loc_180007768
0x180007759  mov     r9d, ebx
0x18000775c  lea     r8, aCdiagnosticpro_5; "CDiagnosticProvider::InitSynch"
0x180007763  call    McTemplateU0sq_EventWriteTransfer
0x180007768  test    ebx, ebx
0x18000776a  jns     short loc_1800077A9
0x18000776c  test    esi, esi
0x18000776e  jz      short loc_18000777A
0x180007770  lea     rcx, [rdi+58h]; lpCriticalSection
0x180007774  call    cs:__imp_DeleteCriticalSection
0x18000777a  test    ebp, ebp
0x18000777c  jz      short loc_1800077A9
0x18000777e  lea     rcx, [rdi+80h]; lpCriticalSection
0x180007785  call    cs:__imp_DeleteCriticalSection
0x18000778b  jmp     short loc_1800077A9
0x18000778d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, r14b
0x180007794  jz      short loc_1800077A9
0x180007796  lea     r8, aCdiagnosticpro_5; "CDiagnosticProvider::InitSynch"
0x18000779d  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800077a4  call    McTemplateU0s_EventWriteTransfer
0x1800077a9  mov     eax, ebx
0x1800077ab  add     rsp, 20h
0x1800077af  pop     r14
0x1800077b1  pop     rdi
0x1800077b2  pop     rsi
0x1800077b3  pop     rbp
0x1800077b4  pop     rbx
0x1800077b5  retn
```
