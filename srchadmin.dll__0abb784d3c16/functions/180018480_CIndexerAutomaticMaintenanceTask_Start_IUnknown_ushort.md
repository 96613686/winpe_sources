# CIndexerAutomaticMaintenanceTask::Start(IUnknown *,ushort *)

- ea: `0x180018480`
- end: `0x180018589`
- name: `?Start@CIndexerAutomaticMaintenanceTask@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `265`
- prototype: `__int64 __fastcall(CIndexerAutomaticMaintenanceTask *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d4dc`
- `0x18001814c`
- `0x1800181fc`
- `0x180018480`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180018548`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180018548`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018574`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018574`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800184b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800184b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800184dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800184dc`

## pseudocode

```c
__int64 __fastcall CIndexerAutomaticMaintenanceTask::Start(
        CIndexerAutomaticMaintenanceTask *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  int Error; // ebx
  HANDLE Event; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi

  SearchOptionsTelemetry::IndexerAMTaskStarted();
  if ( a2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    if ( *((_QWORD *)this + 14) )
    {
      Error = -2147483635;
    }
    else
    {
      Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
      *((_QWORD *)this + 15) = Event;
      if ( Event || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        QueryInterface = a2->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease((char *)this + 104);
        Error = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))QueryInterface)(
                  a2,
                  &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
                  (char *)this + 104);
        if ( Error >= 0 )
        {
          (*(void (__fastcall **)(CIndexerAutomaticMaintenanceTask *))(*(_QWORD *)this + 8LL))(this);
          if ( SHCreateThreadWithHandle((WCHAR)CIndexerAutomaticMaintenanceTask::s_HandlerThreadProc) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
              (*(void (__fastcall **)(CIndexerAutomaticMaintenanceTask *))(*(_QWORD *)this + 16LL))(this);
          }
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180018480  push    rbx
0x180018482  push    rbp
0x180018483  push    rsi
0x180018484  push    rdi
0x180018485  push    r14
0x180018487  push    r15
0x180018489  sub     rsp, 38h
0x18001848d  mov     r14, rdx
0x180018490  mov     rsi, rcx
0x180018493  call    ?IndexerAMTaskStarted@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::IndexerAMTaskStarted(void)
0x180018498  test    r14, r14
0x18001849b  jnz     short loc_1800184A7
0x18001849d  mov     ebx, 80004003h
0x1800184a2  jmp     loc_18001857A
0x1800184a7  lea     rbp, [rsi+40h]
0x1800184ab  mov     [rsp+68h+arg_8], rbp
0x1800184b0  mov     rcx, rbp; lpCriticalSection
0x1800184b3  call    cs:__imp_EnterCriticalSection
0x1800184b9  nop
0x1800184ba  lea     r15, [rsi+70h]
0x1800184be  cmp     qword ptr [r15], 0
0x1800184c2  jz      short loc_1800184CE
0x1800184c4  mov     ebx, 8000000Dh
0x1800184c9  jmp     loc_180018571
0x1800184ce  xor     edx, edx; lpName
0x1800184d0  xor     ecx, ecx; lpEventAttributes
0x1800184d2  mov     r9d, 1F0003h; dwDesiredAccess
0x1800184d8  lea     r8d, [rdx+1]; dwFlags
0x1800184dc  call    cs:__imp_CreateEventExW
0x1800184e2  mov     [rsi+78h], rax
0x1800184e6  test    rax, rax
0x1800184e9  jnz     short loc_1800184F6
0x1800184eb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800184f0  mov     ebx, eax
0x1800184f2  test    eax, eax
0x1800184f4  js      short loc_180018571
0x1800184f6  mov     rax, [r14]
0x1800184f9  mov     rdi, [rax]
0x1800184fc  lea     rcx, [rsi+68h]
0x180018500  call    ?InternalRelease@?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWsPlatform>::InternalRelease(void)
0x180018505  lea     r8, [rsi+68h]
0x180018509  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180018510  mov     rcx, r14
0x180018513  mov     rax, rdi
0x180018516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001851b  mov     ebx, eax
0x18001851d  test    eax, eax
0x18001851f  js      short loc_180018571
0x180018521  mov     rax, [rsi]
0x180018524  mov     rcx, rsi
0x180018527  mov     rax, [rax+8]
0x18001852b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018530  mov     [rsp+68h+var_48], r15
0x180018535  xor     r9d, r9d
0x180018538  mov     r8d, 1010h
0x18001853e  mov     rdx, rsi
0x180018541  lea     rcx, ?s_HandlerThreadProc@CIndexerAutomaticMaintenanceTask@@CAKPEAX@Z; ch
0x180018548  call    cs:__imp_SHCreateThreadWithHandle
0x18001854e  test    eax, eax
0x180018550  jz      short loc_180018556
0x180018552  xor     ebx, ebx
0x180018554  jmp     short loc_180018571
0x180018556  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001855b  mov     ebx, eax
0x18001855d  test    eax, eax
0x18001855f  jns     short loc_180018571
0x180018561  mov     rax, [rsi]
0x180018564  mov     rcx, rsi
0x180018567  mov     rax, [rax+10h]
0x18001856b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018570  nop
0x180018571  mov     rcx, rbp; lpCriticalSection
0x180018574  call    cs:__imp_LeaveCriticalSection
0x18001857a  mov     eax, ebx
0x18001857c  add     rsp, 38h
0x180018580  pop     r15
0x180018582  pop     r14
0x180018584  pop     rdi
0x180018585  pop     rsi
0x180018586  pop     rbp
0x180018587  pop     rbx
0x180018588  retn
```
