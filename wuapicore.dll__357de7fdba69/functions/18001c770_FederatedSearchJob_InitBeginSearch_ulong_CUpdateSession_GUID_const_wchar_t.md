# FederatedSearchJob::InitBeginSearch(ulong,CUpdateSession *,_GUID const &,wchar_t *)

- ea: `0x18001c770`
- end: `0x18001c965`
- name: `?InitBeginSearch@FederatedSearchJob@@UEAAJKPEAVCUpdateSession@@AEBU_GUID@@PEA_W@Z`
- size: `501`
- prototype: `__int64 __fastcall(FederatedSearchJob *__hidden this, unsigned int, struct CUpdateSession *, const struct _GUID *, wchar_t *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x18001c770`
- `0x1800313b0`
- `0x18008662c`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001c7d2`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001c7f7`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001c7d2`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001c7f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c81a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c84e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c882`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c8b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c81a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c84e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c882`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c8b3`

## string_xrefs

- `0x18001c7ab`: `C:\__w\1\s\src\Client\comapi\FederatedSearchJob.cpp`
- `0x18001c8db`: `C:\__w\1\s\src\Client\comapi\FederatedSearchJob.cpp`
- `0x18001c930`: `C:\__w\1\s\src\Client\comapi\FederatedSearchJob.cpp`

## pseudocode

```c
__int64 __fastcall FederatedSearchJob::InitBeginSearch(
        FederatedSearchJob *this,
        unsigned int a2,
        struct CUpdateSession *a3,
        const struct _GUID *a4,
        wchar_t *a5)
{
  int inited; // edi
  __int64 v7; // rdx
  char *v9; // rdi
  _QWORD *v10; // rsi
  HRESULT FreeThreadedMarshaler; // ebp
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  int SingleTriggerEvent; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *((_DWORD *)this + 132) = a2;
  inited = CSearchJob::InitBeginSearch(this, a2, a3, a4, a5);
  if ( inited < 0 )
  {
    v7 = 66;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedSearchJob.cpp",
      (const char *)(unsigned int)inited,
      v19);
    return (unsigned int)inited;
  }
  v9 = (char *)this + 656;
  v10 = (_QWORD *)((char *)this + 672);
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler((LPUNKNOWN)this + 82, (LPUNKNOWN *)this + 84);
  if ( FreeThreadedMarshaler < 0 )
  {
    if ( *v10 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
    v18 = 68;
    goto LABEL_29;
  }
  *((_QWORD *)this + 83) = this;
  v9 = (char *)this + 680;
  v10 = (_QWORD *)((char *)this + 696);
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler((LPUNKNOWN)this + 85, (LPUNKNOWN *)this + 87);
  if ( FreeThreadedMarshaler < 0 )
  {
    if ( *v10 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
    v18 = 70;
LABEL_29:
    *v10 = 0;
    *((_QWORD *)v9 + 1) = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedSearchJob.cpp",
      (const char *)(unsigned int)FreeThreadedMarshaler,
      v19);
    return (unsigned int)FreeThreadedMarshaler;
  }
  *((_QWORD *)this + 86) = this;
  v12 = (void *)*((_QWORD *)this + 75);
  if ( v12 )
  {
    CloseHandle(v12);
    *((_QWORD *)this + 75) = 0;
  }
  inited = CreateSingleTriggerEvent((void **)this + 75);
  if ( inited < 0 )
  {
    v7 = 72;
    goto LABEL_3;
  }
  v13 = (void *)*((_QWORD *)this + 76);
  if ( v13 )
  {
    CloseHandle(v13);
    *((_QWORD *)this + 76) = 0;
  }
  inited = CreateSingleTriggerEvent((void **)this + 76);
  if ( inited < 0 )
  {
    v7 = 73;
    goto LABEL_3;
  }
  v14 = (void *)*((_QWORD *)this + 78);
  if ( v14 )
  {
    CloseHandle(v14);
    *((_QWORD *)this + 78) = 0;
  }
  inited = CreateSingleTriggerEvent((void **)this + 78);
  if ( inited < 0 )
  {
    v7 = 74;
    goto LABEL_3;
  }
  v15 = (void *)*((_QWORD *)this + 96);
  if ( v15 )
  {
    CloseHandle(v15);
    *((_QWORD *)this + 96) = 0;
  }
  SingleTriggerEvent = CreateSingleTriggerEvent((void **)this + 96);
  v17 = SingleTriggerEvent;
  if ( SingleTriggerEvent >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4B,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedSearchJob.cpp",
    (const char *)(unsigned int)SingleTriggerEvent,
    v19);
  return v17;
}

```

## disassembly

```asm
0x18001c770  mov     r11, rsp
0x18001c773  mov     [r11+8], rbx
0x18001c777  mov     [r11+10h], rbp
0x18001c77b  mov     [r11+18h], rsi
0x18001c77f  push    rdi
0x18001c780  sub     rsp, 30h
0x18001c784  mov     rax, [rsp+38h+arg_20]
0x18001c789  mov     rbx, rcx
0x18001c78c  mov     [r11-18h], rax
0x18001c790  mov     [rcx+210h], edx
0x18001c796  call    ?InitBeginSearch@CSearchJob@@UEAAJKPEAVCUpdateSession@@AEBU_GUID@@PEA_W@Z; CSearchJob::InitBeginSearch(ulong,CUpdateSession *,_GUID const &,wchar_t *)
0x18001c79b  mov     edi, eax
0x18001c79d  test    eax, eax
0x18001c79f  jns     short loc_18001C7C1
0x18001c7a1  mov     edx, 42h ; 'B'; void *
0x18001c7a6  mov     rcx, [rsp+38h]; this
0x18001c7ab  lea     r8, aCW1SSrcClientC_35; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x18001c7b2  mov     r9d, edi; char *
0x18001c7b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7ba  mov     eax, edi
0x18001c7bc  jmp     loc_18001C950
0x18001c7c1  lea     rdi, [rbx+290h]
0x18001c7c8  lea     rsi, [rdi+10h]
0x18001c7cc  mov     rcx, rdi; punkOuter
0x18001c7cf  mov     rdx, rsi; ppunkMarshal
0x18001c7d2  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001c7d8  mov     ebp, eax
0x18001c7da  test    eax, eax
0x18001c7dc  js      loc_18001C912
0x18001c7e2  mov     [rdi+8], rbx
0x18001c7e6  lea     rdi, [rbx+2A8h]
0x18001c7ed  lea     rsi, [rdi+10h]
0x18001c7f1  mov     rcx, rdi; punkOuter
0x18001c7f4  mov     rdx, rsi; ppunkMarshal
0x18001c7f7  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001c7fd  mov     ebp, eax
0x18001c7ff  test    eax, eax
0x18001c801  js      loc_18001C8F7
0x18001c807  mov     [rdi+8], rbx
0x18001c80b  lea     rdi, [rbx+258h]
0x18001c812  mov     rcx, [rdi]; hObject
0x18001c815  test    rcx, rcx
0x18001c818  jz      short loc_18001C827
0x18001c81a  call    cs:__imp_CloseHandle
0x18001c820  mov     qword ptr [rdi], 0
0x18001c827  mov     rcx, rdi; void **
0x18001c82a  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x18001c82f  mov     edi, eax
0x18001c831  test    eax, eax
0x18001c833  jns     short loc_18001C83F
0x18001c835  mov     edx, 48h ; 'H'
0x18001c83a  jmp     loc_18001C7A6
0x18001c83f  lea     rdi, [rbx+260h]
0x18001c846  mov     rcx, [rdi]; hObject
0x18001c849  test    rcx, rcx
0x18001c84c  jz      short loc_18001C85B
0x18001c84e  call    cs:__imp_CloseHandle
0x18001c854  mov     qword ptr [rdi], 0
0x18001c85b  mov     rcx, rdi; void **
0x18001c85e  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x18001c863  mov     edi, eax
0x18001c865  test    eax, eax
0x18001c867  jns     short loc_18001C873
0x18001c869  mov     edx, 49h ; 'I'
0x18001c86e  jmp     loc_18001C7A6
0x18001c873  lea     rdi, [rbx+270h]
0x18001c87a  mov     rcx, [rdi]; hObject
0x18001c87d  test    rcx, rcx
0x18001c880  jz      short loc_18001C88F
0x18001c882  call    cs:__imp_CloseHandle
0x18001c888  mov     qword ptr [rdi], 0
0x18001c88f  mov     rcx, rdi; void **
0x18001c892  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x18001c897  mov     edi, eax
0x18001c899  test    eax, eax
0x18001c89b  jns     short loc_18001C8A7
0x18001c89d  mov     edx, 4Ah ; 'J'
0x18001c8a2  jmp     loc_18001C7A6
0x18001c8a7  mov     rcx, [rbx+300h]; hObject
0x18001c8ae  test    rcx, rcx
0x18001c8b1  jz      short loc_18001C8C4
0x18001c8b3  call    cs:__imp_CloseHandle
0x18001c8b9  mov     qword ptr [rbx+300h], 0
0x18001c8c4  lea     rcx, [rbx+300h]; void **
0x18001c8cb  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x18001c8d0  mov     ebx, eax
0x18001c8d2  test    eax, eax
0x18001c8d4  jns     short loc_18001C8F3
0x18001c8d6  mov     rcx, [rsp+38h]; this
0x18001c8db  lea     r8, aCW1SSrcClientC_35; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x18001c8e2  mov     r9d, eax; char *
0x18001c8e5  mov     edx, 4Bh ; 'K'; void *
0x18001c8ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c8ef  mov     eax, ebx
0x18001c8f1  jmp     short loc_18001C950
0x18001c8f3  xor     eax, eax
0x18001c8f5  jmp     short loc_18001C950
0x18001c8f7  mov     rcx, [rsi]
0x18001c8fa  test    rcx, rcx
0x18001c8fd  jz      short loc_18001C90B
0x18001c8ff  mov     rax, [rcx]
0x18001c902  mov     rax, [rax+10h]
0x18001c906  call    _guard_dispatch_icall
0x18001c90b  mov     edx, 46h ; 'F'
0x18001c910  jmp     short loc_18001C92B
0x18001c912  mov     rcx, [rsi]
0x18001c915  test    rcx, rcx
0x18001c918  jz      short loc_18001C926
0x18001c91a  mov     rax, [rcx]
0x18001c91d  mov     rax, [rax+10h]
0x18001c921  call    _guard_dispatch_icall
0x18001c926  mov     edx, 44h ; 'D'; void *
0x18001c92b  mov     rcx, [rsp+38h]; this
0x18001c930  lea     r8, aCW1SSrcClientC_35; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x18001c937  mov     qword ptr [rsi], 0
0x18001c93e  mov     r9d, ebp; char *
0x18001c941  mov     qword ptr [rdi+8], 0
0x18001c949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c94e  mov     eax, ebp
0x18001c950  mov     rbx, [rsp+38h+arg_0]
0x18001c955  mov     rbp, [rsp+38h+arg_8]
0x18001c95a  mov     rsi, [rsp+38h+arg_10]
0x18001c95f  add     rsp, 30h
0x18001c963  pop     rdi
0x18001c964  retn
```
