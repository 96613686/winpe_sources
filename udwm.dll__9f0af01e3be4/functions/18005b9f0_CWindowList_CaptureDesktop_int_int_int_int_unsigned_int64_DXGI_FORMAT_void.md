# CWindowList::CaptureDesktop(int,int,int,int,unsigned __int64,DXGI_FORMAT,void * *)

- ea: `0x18005b9f0`
- end: `0x18005bc88`
- name: `?CaptureDesktop@CWindowList@@UEAAJHHHH_KW4DXGI_FORMAT@@PEAPEAX@Z`
- size: `664`
- prototype: `__int64 __fastcall(CWindowList *__hidden this, int, int, int, int, unsigned __int64, enum DXGI_FORMAT, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x18001f43c`
- `0x18005b9f0`
- `0x18005bc90`
- `0x18005bca4`
- `0x18005da70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ba17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ba17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bae1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bae1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bc2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bc2d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005bb0b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005bb0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWindowList::CaptureDesktop(
        CWindowList *this,
        int a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int64 a6,
        enum DXGI_FORMAT a7,
        void **a8)
{
  __int64 v8; // rbp
  unsigned int v11; // eax
  unsigned __int64 v12; // rcx
  unsigned __int64 dwMaximumSizeLow; // rcx
  unsigned int v14; // edi
  char *FileMappingW; // rbx
  __int64 v17; // rcx
  int v18; // eax
  bool v19; // zf
  _QWORD v20[9]; // [rsp+50h] [rbp-48h] BYREF

  v8 = a4;
  v20[1] = &CDesktopManager::s_csDwmInstance;
  EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
  *a8 = 0;
  if ( a7 > DXGI_FORMAT_R8G8_UNORM )
  {
    if ( a7 == DXGI_FORMAT_R8_UNORM || a7 == DXGI_FORMAT_A8_UNORM )
    {
      v11 = 1;
      goto LABEL_8;
    }
    if ( a7 == DXGI_FORMAT_B8G8R8A8_UNORM )
      goto LABEL_7;
    v19 = a7 == DXGI_FORMAT_B8G8R8X8_UNORM;
    goto LABEL_20;
  }
  if ( a7 == DXGI_FORMAT_R8G8_UNORM )
  {
    v11 = 2;
    goto LABEL_8;
  }
  if ( a7 == DXGI_FORMAT_R32G32B32A32_FLOAT )
  {
    v11 = 32;
    goto LABEL_8;
  }
  v11 = 8;
  if ( a7 != DXGI_FORMAT_R16G16B16A16_FLOAT && a7 != DXGI_FORMAT_R16G16B16A16_UNORM )
  {
    if ( a7 == DXGI_FORMAT_R10G10B10A2_UNORM )
    {
LABEL_7:
      v11 = 4;
      goto LABEL_8;
    }
    v19 = a7 == DXGI_FORMAT_R8G8B8A8_UNORM;
LABEL_20:
    if ( !v19 )
    {
      v11 = 0;
      goto LABEL_8;
    }
    goto LABEL_7;
  }
LABEL_8:
  if ( (int)v8 > 0 && (int)a5 > 0 && v11 )
  {
    v12 = v8 * v11;
    if ( v12 > 0xFFFFFFFF )
    {
      v14 = -2147024362;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024362, 0x1846u, 0);
    }
    else
    {
      dwMaximumSizeLow = a5 * ((v12 + 3) & 0xFFFFFFFC);
      if ( dwMaximumSizeLow <= 0xFFFFFFFF )
      {
        FileMappingW = (char *)CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x8000004u, 0, dwMaximumSizeLow, 0);
        v20[0] = FileMappingW;
        if ( (unsigned __int8)wil::operator==<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(
                                v17,
                                v20) )
        {
          v14 = -2147024882;
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x1854u, 0);
          if ( (unsigned __int64)(FileMappingW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(FileMappingW);
        }
        else
        {
          v18 = CCompositor::SyncDesktopCaptureBits(
                  *((CCompositor **)CDesktopManager::s_pDesktopManagerInstance + 6),
                  (struct _LUID)0xFFFFFFFE00000000uLL,
                  a2,
                  a3,
                  v8,
                  a5,
                  a7,
                  a6,
                  FileMappingW);
          v14 = v18;
          if ( v18 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v18, 0x1860u, 0);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
          }
          else
          {
            *a8 = FileMappingW;
          }
        }
      }
      else
      {
        v14 = -2147024362;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024362, 0x184Au, 0);
      }
    }
  }
  else
  {
    v14 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024809, 0x1865u, 0);
  }
  LeaveCriticalSection(&CDesktopManager::s_csDwmInstance);
  return v14;
}

```

## disassembly

```asm
0x18005b9f0  push    rbx
0x18005b9f2  push    rbp
0x18005b9f3  push    rsi
0x18005b9f4  push    rdi
0x18005b9f5  push    r12
0x18005b9f7  push    r14
0x18005b9f9  push    r15
0x18005b9fb  sub     rsp, 60h
0x18005b9ff  mov     ebp, r9d
0x18005ba02  mov     r15d, r8d
0x18005ba05  mov     r12d, edx
0x18005ba08  lea     rax, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x18005ba0f  mov     [rsp+98h+var_40], rax
0x18005ba14  mov     rcx, rax; lpCriticalSection
0x18005ba17  call    cs:__imp_EnterCriticalSection
0x18005ba1d  nop
0x18005ba1e  mov     r14, qword ptr [rsp+98h+arg_38.LowPart]
0x18005ba26  mov     qword ptr [r14], 0
0x18005ba2d  mov     edi, [rsp+98h+arg_30]
0x18005ba34  cmp     edi, 31h ; '1'
0x18005ba37  jg      loc_18005BBB5
0x18005ba3d  jz      loc_18005BC42
0x18005ba43  mov     ecx, edi
0x18005ba45  sub     ecx, 2
0x18005ba48  jz      loc_18005BC38
0x18005ba4e  mov     eax, 8
0x18005ba53  sub     ecx, eax
0x18005ba55  jz      short loc_18005BA6A
0x18005ba57  sub     ecx, 1
0x18005ba5a  jz      short loc_18005BA6A
0x18005ba5c  sub     ecx, 0Dh
0x18005ba5f  jnz     loc_18005BBA5
0x18005ba65  mov     eax, 4
0x18005ba6a  test    ebp, ebp
0x18005ba6c  jle     loc_18005BBD7
0x18005ba72  mov     esi, [rsp+98h+arg_20]
0x18005ba79  test    esi, esi
0x18005ba7b  jle     loc_18005BBD7
0x18005ba81  test    eax, eax
0x18005ba83  jz      loc_18005BBD7
0x18005ba89  mov     ecx, eax
0x18005ba8b  imul    rcx, rbp
0x18005ba8f  mov     edx, 0FFFFFFFFh
0x18005ba94  mov     [rsp+98h+lpName], 0; void *
0x18005ba9d  cmp     rcx, rdx
0x18005baa0  ja      loc_18005BB8F
0x18005baa6  add     rcx, 3
0x18005baaa  mov     eax, 0FFFFFFFCh
0x18005baaf  and     rcx, rax
0x18005bab2  imul    rcx, rsi
0x18005bab6  cmp     rcx, rdx
0x18005bab9  jbe     short loc_18005BAF8
0x18005babb  mov     r9d, 80070216h; int
0x18005bac1  mov     edi, r9d
0x18005bac4  mov     [rsp+98h+dwMaximumSizeLow], 184Ah; unsigned int
0x18005bacc  xor     r8d, r8d; unsigned int
0x18005bacf  xor     edx, edx; int *
0x18005bad1  lea     ecx, [rdx+14h]; unsigned int
0x18005bad4  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18005bad9  nop
0x18005bada  lea     rcx, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; lpCriticalSection
0x18005bae1  call    cs:__imp_LeaveCriticalSection
0x18005bae7  mov     eax, edi
0x18005bae9  add     rsp, 60h
0x18005baed  pop     r15
0x18005baef  pop     r14
0x18005baf1  pop     r12
0x18005baf3  pop     rdi
0x18005baf4  pop     rsi
0x18005baf5  pop     rbp
0x18005baf6  pop     rbx
0x18005baf7  retn
0x18005baf8  mov     [rsp+98h+dwMaximumSizeLow], ecx; dwMaximumSizeLow
0x18005bafc  xor     r9d, r9d; dwMaximumSizeHigh
0x18005baff  xor     edx, edx; lpFileMappingAttributes
0x18005bb01  mov     r8d, 8000004h; flProtect
0x18005bb07  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18005bb0b  call    cs:__imp_CreateFileMappingW
0x18005bb11  mov     rbx, rax
0x18005bb14  mov     [rsp+98h+var_48], rax
0x18005bb19  lea     rdx, [rsp+98h+var_48]
0x18005bb1e  call    ??$?8V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@YA_N$$TAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@0@@Z; wil::operator==<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(std::nullptr_t,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18005bb23  test    al, al
0x18005bb25  jnz     loc_18005BBF5
0x18005bb2b  mov     [rsp+98h+arg_38.LowPart], 0
0x18005bb36  mov     [rsp+98h+arg_38.HighPart], 0FFFFFFFEh
0x18005bb41  mov     [rsp+98h+var_58], rbx; void *
0x18005bb46  mov     rax, [rsp+98h+arg_28]
0x18005bb4e  mov     [rsp+98h+var_60], rax; unsigned __int64
0x18005bb53  mov     [rsp+98h+var_68], edi; enum DXGI_FORMAT
0x18005bb57  mov     dword ptr [rsp+98h+lpName], esi; unsigned int
0x18005bb5b  mov     [rsp+98h+dwMaximumSizeLow], ebp; unsigned int
0x18005bb5f  mov     r9d, r15d; int
0x18005bb62  mov     r8d, r12d; int
0x18005bb65  mov     rdx, qword ptr [rsp+98h+arg_38.LowPart]; struct _LUID
0x18005bb6d  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18005bb74  mov     rcx, [rcx+30h]; this
0x18005bb78  call    ?SyncDesktopCaptureBits@CCompositor@@QEAAJU_LUID@@HHIIW4DXGI_FORMAT@@_KPEAX@Z; CCompositor::SyncDesktopCaptureBits(_LUID,int,int,uint,uint,DXGI_FORMAT,unsigned __int64,void *)
0x18005bb7d  mov     edi, eax
0x18005bb7f  test    eax, eax
0x18005bb81  js      loc_18005BC56
0x18005bb87  mov     [r14], rbx
0x18005bb8a  jmp     loc_18005BADA
0x18005bb8f  mov     r9d, 80070216h
0x18005bb95  mov     edi, r9d
0x18005bb98  mov     [rsp+98h+dwMaximumSizeLow], 1846h
0x18005bba0  jmp     loc_18005BACC
0x18005bba5  cmp     ecx, 4
0x18005bba8  jz      loc_18005BA65
0x18005bbae  xor     eax, eax
0x18005bbb0  jmp     loc_18005BA6A
0x18005bbb5  mov     ecx, edi
0x18005bbb7  sub     ecx, 3Dh ; '='
0x18005bbba  jz      loc_18005BC4C
0x18005bbc0  sub     ecx, 4
0x18005bbc3  jz      loc_18005BC4C
0x18005bbc9  sub     ecx, 16h
0x18005bbcc  jz      loc_18005BA65
0x18005bbd2  cmp     ecx, 1
0x18005bbd5  jmp     short loc_18005BBA8
0x18005bbd7  mov     edi, 80070057h
0x18005bbdc  mov     [rsp+98h+lpName], 0
0x18005bbe5  mov     [rsp+98h+dwMaximumSizeLow], 1865h
0x18005bbed  mov     r9d, edi
0x18005bbf0  jmp     loc_18005BACC
0x18005bbf5  mov     edi, 8007000Eh
0x18005bbfa  mov     [rsp+98h+lpName], 0; void *
0x18005bc03  mov     [rsp+98h+dwMaximumSizeLow], 1854h; unsigned int
0x18005bc0b  mov     r9d, edi; int
0x18005bc0e  xor     r8d, r8d; unsigned int
0x18005bc11  xor     edx, edx; int *
0x18005bc13  lea     ecx, [rdx+14h]; unsigned int
0x18005bc16  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18005bc1b  nop
0x18005bc1c  lea     rax, [rbx-1]
0x18005bc20  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005bc24  ja      loc_18005BADA
0x18005bc2a  mov     rcx, rbx; hObject
0x18005bc2d  call    cs:__imp_CloseHandle
0x18005bc33  jmp     loc_18005BADA
0x18005bc38  mov     eax, 20h ; ' '
0x18005bc3d  jmp     loc_18005BA6A
0x18005bc42  mov     eax, 2
0x18005bc47  jmp     loc_18005BA6A
0x18005bc4c  mov     eax, 1
0x18005bc51  jmp     loc_18005BA6A
0x18005bc56  mov     [rsp+98h+lpName], 0; void *
0x18005bc5f  mov     [rsp+98h+dwMaximumSizeLow], 1860h; unsigned int
0x18005bc67  mov     r9d, eax; int
0x18005bc6a  xor     r8d, r8d; unsigned int
0x18005bc6d  xor     edx, edx; int *
0x18005bc6f  lea     ecx, [rdx+14h]; unsigned int
0x18005bc72  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18005bc77  nop
0x18005bc78  lea     rcx, [rsp+98h+var_48]
0x18005bc7d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005bc82  jmp     loc_18005BADA
```
