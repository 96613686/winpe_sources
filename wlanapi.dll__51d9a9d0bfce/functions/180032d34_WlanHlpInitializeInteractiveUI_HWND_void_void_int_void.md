# WlanHlpInitializeInteractiveUI(HWND__ *,void *,void *,int *,void * *)

- ea: `0x180032d34`
- end: `0x180032f6a`
- name: `?WlanHlpInitializeInteractiveUI@@YAKPEAUHWND__@@PEAX1PEAHPEAPEAX@Z`
- size: `566`
- prototype: `unsigned int __fastcall(HWND, void *, void *, int *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800285d0`

## callees

- `0x180019e60`
- `0x180019ea4`
- `0x18002ef9c`
- `0x180031fb8`
- `0x180032d34`
- `0x18003af3c`
- `0x18003af80`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180032ed9`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180032ed9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032d92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032dae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032d92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032dae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180032e41`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180032e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032dbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032f24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WlanHlpInitializeInteractiveUI(HWND a1, int *a2, int *a3, int *a4, void **a5)
{
  int *v5; // rbx
  CWlanSSODialogSink *v7; // rbp
  int *v8; // r12
  _QWORD *v9; // rsi
  unsigned int v10; // edx
  DWORD LastError; // r14d
  int **v12; // rdi
  int *EventW; // r15
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  void *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  int **v21; // [rsp+30h] [rbp-48h] BYREF

  v5 = a4;
  v7 = 0;
  v21 = 0;
  v8 = 0;
  v9 = 0;
  LastError = AllocateWLMemory(64, &v21);
  v12 = v21;
  if ( LastError )
  {
    EventW = 0;
  }
  else
  {
    EventW = (int *)CreateEventW(0, 1, 0, L"UIFinishEvent");
    if ( EventW && (v8 = (int *)CreateEventW(0, 0, 0, L"UIRequestEvent")) != 0 )
    {
      v14 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
      v9 = v14;
      v21 = (int **)v14;
      if ( v14 )
      {
        v15 = v14 + 1;
        v14[1] = 0;
        v14[2] = 0;
        v14[3] = 0;
        v14[4] = 0;
        v14[5] = 0;
        v16 = operator new(0x10u);
        v16[1] = 0;
        *v15 = v16;
        *v16 = v15;
        *v9 = &CLockedUIRequestQueue<CInteractiveUIRequest *>::`vftable';
        InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 6));
        v5 = a4;
      }
      else
      {
        v9 = 0;
      }
      if ( v9 )
      {
        v17 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
        {
          v18 = ATL::CComObject<CWlanSSODialogSink>::CComObject<CWlanSSODialogSink>(v17);
          v7 = (CWlanSSODialogSink *)v18;
          if ( v18 )
            *(_QWORD *)(v18 + 72) = a1;
        }
        else
        {
          v7 = 0;
        }
        *v12 = v5;
        v12[1] = EventW;
        v12[2] = v8;
        v12[3] = a2;
        v12[5] = a3;
        v12[6] = (int *)v9;
        v12[7] = (int *)v7;
        v19 = _o__beginthreadex(0, 0, RunInteractiveUIThread, v12, 0, 0, v21);
        if ( v19 != -1 )
        {
          v12[4] = (int *)v19;
          *a5 = v12;
          return LastError;
        }
        LastError = 1003;
      }
      else
      {
        LastError = 14;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( !LastError )
        return LastError;
    }
  }
  if ( v12 )
    FreeWLMemory(v12);
  if ( EventW )
    CloseHandle(EventW);
  if ( v8 )
    CloseHandle(v8);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v9)(v9, 1);
  if ( v7 )
    CWlanSSODialogSink::`scalar deleting destructor'(v7, v10);
  return LastError;
}

```

## disassembly

```asm
0x180032d34  mov     rax, rsp
0x180032d37  mov     [rax+8], rbx
0x180032d3b  mov     [rax+20h], r9
0x180032d3f  mov     [rax+18h], r8
0x180032d43  mov     [rax+10h], rdx
0x180032d47  push    rbp
0x180032d48  push    rsi
0x180032d49  push    rdi
0x180032d4a  push    r12
0x180032d4c  push    r13
0x180032d4e  push    r14
0x180032d50  push    r15
0x180032d52  sub     rsp, 40h
0x180032d56  mov     rbx, r9
0x180032d59  mov     r13, rcx
0x180032d5c  xor     ebp, ebp
0x180032d5e  mov     [rax-48h], rbp
0x180032d62  xor     r12d, r12d
0x180032d65  xor     esi, esi
0x180032d67  lea     rdx, [rax-48h]
0x180032d6b  lea     ecx, [rbp+40h]
0x180032d6e  call    AllocateWLMemory
0x180032d73  mov     r14d, eax
0x180032d76  mov     rdi, [rsp+78h+var_48]
0x180032d7b  test    eax, eax
0x180032d7d  jnz     loc_180032EFE
0x180032d83  lea     r9, Name; "UIFinishEvent"
0x180032d8a  xor     r8d, r8d; bInitialState
0x180032d8d  lea     edx, [rbp+1]; bManualReset
0x180032d90  xor     ecx, ecx; lpEventAttributes
0x180032d92  call    cs:__imp_CreateEventW
0x180032d98  mov     r15, rax
0x180032d9b  test    rax, rax
0x180032d9e  jz      short loc_180032DBC
0x180032da0  lea     r9, aUirequestevent; "UIRequestEvent"
0x180032da7  xor     r8d, r8d; bInitialState
0x180032daa  xor     edx, edx; bManualReset
0x180032dac  xor     ecx, ecx; lpEventAttributes
0x180032dae  call    cs:__imp_CreateEventW
0x180032db4  mov     r12, rax
0x180032db7  test    rax, rax
0x180032dba  jnz     short loc_180032DD2
0x180032dbc  call    cs:__imp_GetLastError
0x180032dc2  mov     r14d, eax
0x180032dc5  test    eax, eax
0x180032dc7  jz      loc_180032F4F
0x180032dcd  jmp     loc_180032F01
0x180032dd2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032dd9  mov     ecx, 58h ; 'X'; unsigned __int64
0x180032dde  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180032de3  mov     rsi, rax
0x180032de6  mov     [rsp+78h+var_48], rax
0x180032deb  test    rax, rax
0x180032dee  jz      short loc_180032E51
0x180032df0  lea     rbx, [rax+8]
0x180032df4  mov     qword ptr [rbx], 0
0x180032dfb  mov     qword ptr [rbx+8], 0
0x180032e03  mov     qword ptr [rbx+10h], 0
0x180032e0b  mov     qword ptr [rbx+18h], 0
0x180032e13  mov     qword ptr [rbx+20h], 0
0x180032e1b  mov     ecx, 10h; Size
0x180032e20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032e25  mov     qword ptr [rax+8], 0
0x180032e2d  mov     [rbx], rax
0x180032e30  mov     [rax], rbx
0x180032e33  lea     rax, ??_7?$CLockedUIRequestQueue@PEAVCInteractiveUIRequest@@@@6B@; const CLockedUIRequestQueue<CInteractiveUIRequest *>::`vftable'
0x180032e3a  mov     [rsi], rax
0x180032e3d  lea     rcx, [rsi+30h]; lpCriticalSection
0x180032e41  call    cs:__imp_InitializeCriticalSection
0x180032e47  mov     rbx, [rsp+78h+arg_18]
0x180032e4f  jmp     short loc_180032E53
0x180032e51  xor     esi, esi
0x180032e53  test    rsi, rsi
0x180032e56  jnz     short loc_180032E61
0x180032e58  lea     r14d, [rsi+0Eh]
0x180032e5c  jmp     loc_180032F01
0x180032e61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032e68  mov     ecx, 78h ; 'x'; unsigned __int64
0x180032e6d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180032e72  test    rax, rax
0x180032e75  jz      short loc_180032E8D
0x180032e77  mov     rcx, rax
0x180032e7a  call    ??0?$CComObject@VCWlanSSODialogSink@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CWlanSSODialogSink>::CComObject<CWlanSSODialogSink>(void *)
0x180032e7f  mov     rbp, rax
0x180032e82  test    rax, rax
0x180032e85  jz      short loc_180032E8F
0x180032e87  mov     [rax+48h], r13
0x180032e8b  jmp     short loc_180032E8F
0x180032e8d  xor     ebp, ebp
0x180032e8f  mov     [rdi], rbx
0x180032e92  mov     [rdi+8], r15
0x180032e96  mov     [rdi+10h], r12
0x180032e9a  mov     rax, [rsp+78h+arg_8]
0x180032ea2  mov     [rdi+18h], rax
0x180032ea6  mov     rax, [rsp+78h+arg_10]
0x180032eae  mov     [rdi+28h], rax
0x180032eb2  mov     [rdi+30h], rsi
0x180032eb6  mov     [rdi+38h], rbp
0x180032eba  mov     [rsp+78h+var_50], 0
0x180032ec3  mov     [rsp+78h+var_58], 0
0x180032ecb  mov     r9, rdi
0x180032ece  lea     r8, ?RunInteractiveUIThread@@YAIPEAX@Z; RunInteractiveUIThread(void *)
0x180032ed5  xor     edx, edx
0x180032ed7  xor     ecx, ecx
0x180032ed9  call    cs:__imp__o__beginthreadex
0x180032edf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032ee3  jnz     short loc_180032EED
0x180032ee5  mov     r14d, 3EBh
0x180032eeb  jmp     short loc_180032F01
0x180032eed  mov     [rdi+20h], rax
0x180032ef1  mov     rax, [rsp+78h+arg_20]
0x180032ef9  mov     [rax], rdi
0x180032efc  jmp     short loc_180032F4F
0x180032efe  xor     r15d, r15d
0x180032f01  test    rdi, rdi
0x180032f04  jz      short loc_180032F0E
0x180032f06  mov     rcx, rdi
0x180032f09  call    FreeWLMemory
0x180032f0e  test    r15, r15
0x180032f11  jz      short loc_180032F1C
0x180032f13  mov     rcx, r15; hObject
0x180032f16  call    cs:__imp_CloseHandle
0x180032f1c  test    r12, r12
0x180032f1f  jz      short loc_180032F2A
0x180032f21  mov     rcx, r12; hObject
0x180032f24  call    cs:__imp_CloseHandle
0x180032f2a  test    rsi, rsi
0x180032f2d  jz      short loc_180032F42
0x180032f2f  mov     rax, [rsi]
0x180032f32  mov     edx, 1
0x180032f37  mov     rcx, rsi
0x180032f3a  mov     rax, [rax]
0x180032f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f42  test    rbp, rbp
0x180032f45  jz      short loc_180032F4F
0x180032f47  mov     rcx, rbp; this
0x180032f4a  call    ??_GCWlanSSODialogSink@@QEAAPEAXI@Z; CWlanSSODialogSink::`scalar deleting destructor'(uint)
0x180032f4f  mov     eax, r14d
0x180032f52  mov     rbx, [rsp+78h+arg_0]
0x180032f5a  add     rsp, 40h
0x180032f5e  pop     r15
0x180032f60  pop     r14
0x180032f62  pop     r13
0x180032f64  pop     r12
0x180032f66  pop     rdi
0x180032f67  pop     rsi
0x180032f68  pop     rbp
0x180032f69  retn
```
