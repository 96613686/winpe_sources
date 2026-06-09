# CVdsService::LoadHbaPorts(void)

- ea: `0x14000b5bc`
- end: `0x14000b996`
- name: `?LoadHbaPorts@CVdsService@@CAJXZ`
- size: `986`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140009e70`

## callees

- `0x14000b5bc`
- `0x14000f98c`
- `0x140012c48`
- `0x14002e123`
- `0x1400381a4`
- `0x14003e23c`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b902`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b902`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b8d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b8d9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000b7f9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000b7f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b659`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b670`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b68c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b6a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b6bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b6db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b659`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b670`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b68c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b6a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b6bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b6db`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14000b639`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14000b639`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000b61f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000b61f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000b96b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000b96b`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000b8ec`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14000b8ec`
- `vdsutil!VdsTraceW` at `0x14000b75a`
- `vdsutil!VdsTraceW` at `0x14000b781`
- `vdsutil!VdsTraceW` at `0x14000b7b5`
- `vdsutil!VdsTraceW` at `0x14000b832`
- `vdsutil!VdsTraceW` at `0x14000b864`
- `vdsutil!VdsTraceW` at `0x14000b8ca`
- `vdsutil!VdsTraceW` at `0x14000b95f`
- `vdsutil!VdsTraceW` at `0x14000b75a`
- `vdsutil!VdsTraceW` at `0x14000b781`
- `vdsutil!VdsTraceW` at `0x14000b7b5`
- `vdsutil!VdsTraceW` at `0x14000b832`
- `vdsutil!VdsTraceW` at `0x14000b864`
- `vdsutil!VdsTraceW` at `0x14000b8ca`
- `vdsutil!VdsTraceW` at `0x14000b95f`

## string_xrefs

- `0x14000b60e`: `CVdsService::LoadHbaPorts()`
- `0x14000b632`: `hbaapi.dll`
- `0x14000b956`: `CVdsService::LoadHbaPorts, 1`
- `0x14000b67e`: `HBA_OpenAdapter`
- `0x14000b751`: `CVdsService::LoadHbaPorts hbaStatus=%lX, 2`
- `0x14000b778`: `CVdsService::LoadHbaPorts, 3`
- `0x14000b7ac`: `CVdsService::LoadHbaPorts hbaStatus=%lX, 4`
- `0x14000b805`: `CVdsService::LoadHbaPorts, 5, hr=%lX`
- `0x14000b829`: `CVdsService::LoadHbaPorts hbaStatus=%lX, 6`
- `0x14000b85b`: `CVdsService::LoadHbaPorts, 7`
- `0x14000b895`: `CVdsService::LoadHbaPorts, 8, hr=%lX`
- `0x14000b8be`: `CVdsService::LoadHbaPorts, 9, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 CVdsService::LoadHbaPorts(void)
{
  HMODULE LibraryW; // rax
  __int64 (*ProcAddress)(void); // rbx
  FARPROC v2; // rsi
  FARPROC v3; // r13
  FARPROC v4; // rdi
  FARPROC v5; // r14
  FARPROC v6; // rax
  unsigned int v7; // edi
  unsigned int v8; // r12d
  unsigned int i; // r14d
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // r15d
  unsigned int v13; // eax
  unsigned int v14; // esi
  __int64 (__fastcall *v15)(_QWORD, _QWORD, _QWORD); // r12
  HRESULT v16; // eax
  unsigned int v17; // eax
  CVdsHbaPortInternal *v18; // rbx
  int v19; // eax
  int v20; // eax
  void *v22; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v23; // [rsp+28h] [rbp-D8h]
  CVdsHbaPortInternal *v24; // [rsp+30h] [rbp-D0h] BYREF
  INT_PTR (__stdcall *v25)(); // [rsp+38h] [rbp-C8h]
  __int64 (__fastcall *v26)(_QWORD, _QWORD); // [rsp+40h] [rbp-C0h]
  FARPROC v27; // [rsp+48h] [rbp-B8h]
  void (__fastcall *v28)(_QWORD); // [rsp+50h] [rbp-B0h]
  _BYTE v29[16]; // [rsp+58h] [rbp-A8h] BYREF
  GUID pguid; // [rsp+68h] [rbp-98h] BYREF
  struct HBA_PortAttributes v31; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[1932]; // [rsp+300h] [rbp+200h] BYREF
  unsigned int v33; // [rsp+A8Ch] [rbp+98Ch]
  _BYTE v34[264]; // [rsp+B90h] [rbp+A90h] BYREF

  memset_0(v32, 0, 0x890u);
  memset_0(&v31, 0, sizeof(v31));
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v29, 0x5Eu, "CVdsService::LoadHbaPorts()");
  LibraryW = CVdsService::m_hHbaapiModule;
  if ( !CVdsService::m_hHbaapiModule )
  {
    LibraryW = LoadLibraryW(L"hbaapi.dll");
    CVdsService::m_hHbaapiModule = LibraryW;
    if ( !LibraryW )
      goto LABEL_37;
  }
  ProcAddress = GetProcAddress(LibraryW, "HBA_GetNumberOfAdapters");
  v2 = GetProcAddress(CVdsService::m_hHbaapiModule, "HBA_GetAdapterName");
  v25 = v2;
  v3 = GetProcAddress(CVdsService::m_hHbaapiModule, "HBA_OpenAdapter");
  v4 = GetProcAddress(CVdsService::m_hHbaapiModule, "HBA_GetAdapterAttributes");
  v26 = (__int64 (__fastcall *)(_QWORD, _QWORD))v4;
  v5 = GetProcAddress(CVdsService::m_hHbaapiModule, "HBA_GetAdapterPortAttributes");
  v27 = v5;
  v6 = GetProcAddress(CVdsService::m_hHbaapiModule, "HBA_CloseAdapter");
  v28 = (void (__fastcall *)(_QWORD))v6;
  if ( !ProcAddress )
    goto LABEL_37;
  if ( v2 && v3 && v4 && v5 && v6 )
  {
    v7 = 0;
    v8 = ProcAddress();
    v23 = v8;
    for ( i = 0; i < v8; ++i )
    {
      v10 = ((__int64 (__fastcall *)(_QWORD, _BYTE *))v2)(i, v34);
      if ( v10 )
      {
        VdsTraceW(0, L"CVdsService::LoadHbaPorts hbaStatus=%lX, 2", v10);
      }
      else
      {
        v11 = ((__int64 (__fastcall *)(_BYTE *))v3)(v34);
        v12 = v11;
        if ( v11 )
        {
          v13 = v26(v11, v32);
          if ( v13 )
          {
            VdsTraceW(0, L"CVdsService::LoadHbaPorts hbaStatus=%lX, 4", v13);
            v7 = -2147467259;
          }
          else
          {
            v7 = 0;
            v14 = 0;
            if ( v33 )
            {
              v15 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v27;
              do
              {
                pguid = 0;
                v24 = 0;
                v22 = 0;
                v16 = CoCreateGuid(&pguid);
                v7 = v16;
                if ( v16 >= 0 )
                {
                  v17 = v15(v12, v14, &v31);
                  if ( v17 )
                  {
                    VdsTraceW(0, L"CVdsService::LoadHbaPorts hbaStatus=%lX, 6", v17);
                    v7 = -2147467259;
                  }
                  else
                  {
                    ATL::CComObject<CVdsHbaPortInternal>::CreateInstance((__int64 *)&v24);
                    v18 = v24;
                    if ( v24 )
                    {
                      (*(void (__fastcall **)(CVdsHbaPortInternal *))(*(_QWORD *)v24 + 8LL))(v24);
                      v19 = CVdsHbaPortInternal::Initialize(v18, &pguid, &v31);
                      v7 = v19;
                      if ( v19 >= 0 )
                      {
                        v20 = (**(__int64 (__fastcall ***)(CVdsHbaPortInternal *, GUID *, void **))v18)(
                                v18,
                                &IID_IUnknown,
                                &v22);
                        v7 = v20;
                        if ( v20 >= 0 )
                        {
                          EnterCriticalSection(&g_GlobalCriticalSection);
                          CRtlList::InsertTailPointer((CRtlList *)CVdsService::m_lstHbaPorts, v22);
                          v22 = 0;
                          LeaveCriticalSection(&g_GlobalCriticalSection);
                        }
                        else
                        {
                          VdsTraceW(0, L"CVdsService::LoadHbaPorts, 9, hr=%lX", (unsigned int)v20);
                        }
                      }
                      else
                      {
                        VdsTraceW(0, L"CVdsService::LoadHbaPorts, 8, hr=%lX", (unsigned int)v19);
                      }
                    }
                    else
                    {
                      v7 = -2147024882;
                      VdsTraceW(0, L"CVdsService::LoadHbaPorts, 7");
                    }
                  }
                }
                else
                {
                  VdsTraceW(0, L"CVdsService::LoadHbaPorts, 5, hr=%lX", (unsigned int)v16);
                }
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
                ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v24);
                ++v14;
              }
              while ( v14 < v33 );
              v8 = v23;
            }
            v2 = v25;
          }
          v28(v12);
          continue;
        }
        VdsTraceW(0, L"CVdsService::LoadHbaPorts, 3");
      }
      v7 = -2147467259;
    }
  }
  else
  {
LABEL_37:
    v7 = -2147212288;
    VdsTraceW(0, L"CVdsService::LoadHbaPorts, 1");
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v29);
  return v7;
}

```

## disassembly

```asm
0x14000b5bc  push    rbp
0x14000b5be  push    rbx
0x14000b5bf  push    rsi
0x14000b5c0  push    rdi
0x14000b5c1  push    r12
0x14000b5c3  push    r13
0x14000b5c5  push    r14
0x14000b5c7  push    r15
0x14000b5c9  lea     rbp, [rsp-0BA8h]
0x14000b5d1  sub     rsp, 0CA8h
0x14000b5d8  mov     rax, cs:__security_cookie
0x14000b5df  xor     rax, rsp
0x14000b5e2  mov     [rbp+0BE0h+var_48], rax
0x14000b5e9  xor     edx, edx; Val
0x14000b5eb  mov     r8d, 890h; Size
0x14000b5f1  lea     rcx, [rbp+0BE0h+var_9E0]; void *
0x14000b5f8  call    memset_0
0x14000b5fd  xor     edx, edx; Val
0x14000b5ff  mov     r8d, 278h; Size
0x14000b605  lea     rcx, [rbp+0BE0h+var_C60]; void *
0x14000b609  call    memset_0
0x14000b60e  lea     r8, aCvdsserviceLoa_15; "CVdsService::LoadHbaPorts()"
0x14000b615  mov     edx, 5Eh ; '^'
0x14000b61a  lea     rcx, [rsp+0CE0h+var_C88]
0x14000b61f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000b625  nop
0x14000b626  mov     rax, cs:?m_hHbaapiModule@CVdsService@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * CVdsService::m_hHbaapiModule
0x14000b62d  test    rax, rax
0x14000b630  jnz     short loc_14000B64F
0x14000b632  lea     rcx, aHbaapiDll; "hbaapi.dll"
0x14000b639  call    cs:__imp_LoadLibraryW
0x14000b63f  mov     cs:?m_hHbaapiModule@CVdsService@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CVdsService::m_hHbaapiModule
0x14000b646  test    rax, rax
0x14000b649  jz      loc_14000B951
0x14000b64f  lea     rdx, ProcName; "HBA_GetNumberOfAdapters"
0x14000b656  mov     rcx, rax; hModule
0x14000b659  call    cs:__imp_GetProcAddress
0x14000b65f  mov     rbx, rax
0x14000b662  lea     rdx, aHbaGetadaptern; "HBA_GetAdapterName"
0x14000b669  mov     rcx, cs:?m_hHbaapiModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14000b670  call    cs:__imp_GetProcAddress
0x14000b676  mov     rsi, rax
0x14000b679  mov     [rsp+0CE0h+var_CA8], rax
0x14000b67e  lea     rdx, aHbaOpenadapter; "HBA_OpenAdapter"
0x14000b685  mov     rcx, cs:?m_hHbaapiModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14000b68c  call    cs:__imp_GetProcAddress
0x14000b692  mov     r13, rax
0x14000b695  lea     rdx, aHbaGetadaptera; "HBA_GetAdapterAttributes"
0x14000b69c  mov     rcx, cs:?m_hHbaapiModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14000b6a3  call    cs:__imp_GetProcAddress
0x14000b6a9  mov     rdi, rax
0x14000b6ac  mov     [rsp+0CE0h+var_CA0], rax
0x14000b6b1  lea     rdx, aHbaGetadapterp; "HBA_GetAdapterPortAttributes"
0x14000b6b8  mov     rcx, cs:?m_hHbaapiModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14000b6bf  call    cs:__imp_GetProcAddress
0x14000b6c5  mov     r14, rax
0x14000b6c8  mov     [rsp+0CE0h+var_C98], rax
0x14000b6cd  lea     rdx, aHbaCloseadapte; "HBA_CloseAdapter"
0x14000b6d4  mov     rcx, cs:?m_hHbaapiModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14000b6db  call    cs:__imp_GetProcAddress
0x14000b6e1  mov     [rsp+0CE0h+var_C90], rax
0x14000b6e6  test    rbx, rbx
0x14000b6e9  jz      loc_14000B951
0x14000b6ef  test    rsi, rsi
0x14000b6f2  jz      loc_14000B951
0x14000b6f8  test    r13, r13
0x14000b6fb  jz      loc_14000B951
0x14000b701  test    rdi, rdi
0x14000b704  jz      loc_14000B951
0x14000b70a  test    r14, r14
0x14000b70d  jz      loc_14000B951
0x14000b713  test    rax, rax
0x14000b716  jz      loc_14000B951
0x14000b71c  xor     edi, edi
0x14000b71e  mov     rax, rbx
0x14000b721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b726  mov     r12d, eax
0x14000b729  mov     [rsp+0CE0h+var_CB8], eax
0x14000b72d  xor     r14d, r14d
0x14000b730  test    eax, eax
0x14000b732  jz      loc_14000B966
0x14000b738  lea     rdx, [rbp+0BE0h+var_150]
0x14000b73f  mov     ecx, r14d
0x14000b742  mov     rax, rsi
0x14000b745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b74a  test    eax, eax
0x14000b74c  jz      short loc_14000B762
0x14000b74e  mov     r8d, eax
0x14000b751  lea     rdx, aCvdsserviceLoa_1; "CVdsService::LoadHbaPorts hbaStatus=%lX"...
0x14000b758  xor     ecx, ecx
0x14000b75a  call    cs:__imp_VdsTraceW
0x14000b760  jmp     short loc_14000B787
0x14000b762  lea     rcx, [rbp+0BE0h+var_150]
0x14000b769  mov     rax, r13
0x14000b76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b771  mov     r15d, eax
0x14000b774  test    eax, eax
0x14000b776  jnz     short loc_14000B791
0x14000b778  lea     rdx, aCvdsserviceLoa_7; "CVdsService::LoadHbaPorts, 3"
0x14000b77f  xor     ecx, ecx
0x14000b781  call    cs:__imp_VdsTraceW
0x14000b787  mov     edi, 80004005h
0x14000b78c  jmp     loc_14000B943
0x14000b791  lea     rdx, [rbp+0BE0h+var_9E0]
0x14000b798  mov     ecx, r15d
0x14000b79b  mov     rax, [rsp+0CE0h+var_CA0]
0x14000b7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7a5  test    eax, eax
0x14000b7a7  jz      short loc_14000B7C5
0x14000b7a9  mov     r8d, eax
0x14000b7ac  lea     rdx, aCvdsserviceLoa_5; "CVdsService::LoadHbaPorts hbaStatus=%lX"...
0x14000b7b3  xor     ecx, ecx
0x14000b7b5  call    cs:__imp_VdsTraceW
0x14000b7bb  mov     edi, 80004005h
0x14000b7c0  jmp     loc_14000B936
0x14000b7c5  xor     edi, edi
0x14000b7c7  xor     esi, esi
0x14000b7c9  cmp     [rbp+0BE0h+var_254], esi
0x14000b7cf  jbe     loc_14000B931
0x14000b7d5  mov     r12, [rsp+0CE0h+var_C98]
0x14000b7da  xorps   xmm0, xmm0
0x14000b7dd  movups  xmmword ptr [rsp+0CE0h+pguid.Data1], xmm0
0x14000b7e2  mov     [rsp+0CE0h+var_CB0], 0
0x14000b7eb  mov     [rsp+0CE0h+var_CC0], 0
0x14000b7f4  lea     rcx, [rsp+0CE0h+pguid]; pguid
0x14000b7f9  call    cs:__imp_CoCreateGuid
0x14000b7ff  mov     edi, eax
0x14000b801  test    eax, eax
0x14000b803  jns     short loc_14000B811
0x14000b805  lea     rdx, aCvdsserviceLoa_9; "CVdsService::LoadHbaPorts, 5, hr=%lX"
0x14000b80c  jmp     loc_14000B8C5
0x14000b811  lea     r8, [rbp+0BE0h+var_C60]
0x14000b815  mov     edx, esi
0x14000b817  mov     ecx, r15d
0x14000b81a  mov     rax, r12
0x14000b81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b822  test    eax, eax
0x14000b824  jz      short loc_14000B842
0x14000b826  mov     r8d, eax
0x14000b829  lea     rdx, aCvdsserviceLoa_16; "CVdsService::LoadHbaPorts hbaStatus=%lX"...
0x14000b830  xor     ecx, ecx
0x14000b832  call    cs:__imp_VdsTraceW
0x14000b838  mov     edi, 80004005h
0x14000b83d  jmp     loc_14000B909
0x14000b842  lea     rcx, [rsp+0CE0h+var_CB0]
0x14000b847  call    ?CreateInstance@?$CComObject@VCVdsHbaPortInternal@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CVdsHbaPortInternal>::CreateInstance(ATL::CComObject<CVdsHbaPortInternal> * *)
0x14000b84c  mov     rbx, [rsp+0CE0h+var_CB0]
0x14000b851  test    rbx, rbx
0x14000b854  jnz     short loc_14000B86F
0x14000b856  mov     edi, 8007000Eh
0x14000b85b  lea     rdx, aCvdsserviceLoa_2; "CVdsService::LoadHbaPorts, 7"
0x14000b862  xor     ecx, ecx
0x14000b864  call    cs:__imp_VdsTraceW
0x14000b86a  jmp     loc_14000B909
0x14000b86f  mov     rax, [rbx]
0x14000b872  mov     rcx, rbx
0x14000b875  mov     rax, [rax+8]
0x14000b879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b87e  lea     r8, [rbp+0BE0h+var_C60]; struct HBA_PortAttributes *
0x14000b882  lea     rdx, [rsp+0CE0h+pguid]; struct _GUID *
0x14000b887  mov     rcx, rbx; this
0x14000b88a  call    ?Initialize@CVdsHbaPortInternal@@QEAAJPEBU_GUID@@PEAUHBA_PortAttributes@@@Z; CVdsHbaPortInternal::Initialize(_GUID const *,HBA_PortAttributes *)
0x14000b88f  mov     edi, eax
0x14000b891  test    eax, eax
0x14000b893  jns     short loc_14000B89E
0x14000b895  lea     rdx, aCvdsserviceLoa_14; "CVdsService::LoadHbaPorts, 8, hr=%lX"
0x14000b89c  jmp     short loc_14000B8C5
0x14000b89e  mov     rax, [rbx]
0x14000b8a1  lea     r8, [rsp+0CE0h+var_CC0]
0x14000b8a6  lea     rdx, IID_IUnknown
0x14000b8ad  mov     rcx, rbx
0x14000b8b0  mov     rax, [rax]
0x14000b8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b8b8  mov     edi, eax
0x14000b8ba  test    eax, eax
0x14000b8bc  jns     short loc_14000B8D2
0x14000b8be  lea     rdx, aCvdsserviceLoa_0; "CVdsService::LoadHbaPorts, 9, hr=%lX"
0x14000b8c5  mov     r8d, eax
0x14000b8c8  xor     ecx, ecx
0x14000b8ca  call    cs:__imp_VdsTraceW
0x14000b8d0  jmp     short loc_14000B909
0x14000b8d2  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000b8d9  call    cs:__imp_EnterCriticalSection
0x14000b8df  nop
0x14000b8e0  mov     rdx, [rsp+0CE0h+var_CC0]
0x14000b8e5  lea     rcx, ?m_lstHbaPorts@CVdsService@@0VCRtlList@@A; CRtlList CVdsService::m_lstHbaPorts
0x14000b8ec  call    cs:__imp_?InsertTailPointer@CRtlList@@QEAAHPEAX@Z; CRtlList::InsertTailPointer(void *)
0x14000b8f2  mov     [rsp+0CE0h+var_CC0], 0
0x14000b8fb  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000b902  call    cs:__imp_LeaveCriticalSection
0x14000b908  nop
0x14000b909  lea     rcx, [rsp+0CE0h+var_CC0]
0x14000b90e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000b913  nop
0x14000b914  lea     rcx, [rsp+0CE0h+var_CB0]
0x14000b919  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x14000b91e  inc     esi
0x14000b920  cmp     esi, [rbp+0BE0h+var_254]
0x14000b926  jb      loc_14000B7DA
0x14000b92c  mov     r12d, [rsp+0CE0h+var_CB8]
0x14000b931  mov     rsi, [rsp+0CE0h+var_CA8]
0x14000b936  mov     ecx, r15d
0x14000b939  mov     rax, [rsp+0CE0h+var_C90]
0x14000b93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b943  inc     r14d
0x14000b946  cmp     r14d, r12d
0x14000b949  jb      loc_14000B738
0x14000b94f  jmp     short loc_14000B966
0x14000b951  mov     edi, 80042400h
0x14000b956  lea     rdx, aCvdsserviceLoa_12; "CVdsService::LoadHbaPorts, 1"
0x14000b95d  xor     ecx, ecx
0x14000b95f  call    cs:__imp_VdsTraceW
0x14000b965  nop
0x14000b966  lea     rcx, [rsp+0CE0h+var_C88]
0x14000b96b  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000b971  mov     eax, edi
0x14000b973  mov     rcx, [rbp+0BE0h+var_48]
0x14000b97a  xor     rcx, rsp; StackCookie
0x14000b97d  call    __security_check_cookie
0x14000b982  add     rsp, 0CA8h
0x14000b989  pop     r15
0x14000b98b  pop     r14
0x14000b98d  pop     r13
0x14000b98f  pop     r12
0x14000b991  pop     rdi
0x14000b992  pop     rsi
0x14000b993  pop     rbx
0x14000b994  pop     rbp
0x14000b995  retn
```
