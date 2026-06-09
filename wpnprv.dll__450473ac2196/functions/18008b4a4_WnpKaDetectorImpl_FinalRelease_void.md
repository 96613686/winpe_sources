# WnpKaDetectorImpl::FinalRelease(void)

- ea: `0x18008b4a4`
- end: `0x18008b62f`
- name: `?FinalRelease@WnpKaDetectorImpl@@IEAAJXZ`
- size: `395`
- prototype: `__int64 __fastcall(WnpKaDetectorImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800899b4`

## callees

- `0x18000fe2c`
- `0x18008ad90`
- `0x18008b4a4`
- `0x18008eb40`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b5ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b5ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b5b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b5d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b5b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b5d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008b511`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008b511`

## pseudocode

```c
__int64 __fastcall WnpKaDetectorImpl::FinalRelease(WnpKaDetectorImpl *this)
{
  WnpKaDetectorImpl *v2; // rcx
  WnpKaDetectorImpl *v3; // rcx
  struct _TP_WORK *v4; // rcx
  __int64 v5; // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  __int64 v7; // rcx
  char *v8; // rcx
  char *v9; // rcx
  char *v10; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
  }
  WnpKaDetectorImpl::ReleaseNetworkMonitor(this);
  WnpKaDetectorImpl::DeleteWakeTimer(v2, (void **)this + 36);
  WnpKaDetectorImpl::DeleteWakeTimer(v3, (void **)this + 37);
  v4 = (struct _TP_WORK *)*((_QWORD *)this + 49);
  if ( v4 )
  {
    CloseThreadpoolWork(v4);
    *((_QWORD *)this + 49) = 0;
  }
  v5 = *((_QWORD *)this + 14);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 16LL))(v5, 1);
    *((_QWORD *)this + 14) = 0;
  }
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 15);
  if ( v6 )
  {
    (**v6)(v6, 1);
    *((_QWORD *)this + 15) = 0;
  }
  v7 = *((_QWORD *)this + 13);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 13) = 0;
  }
  v8 = (char *)*((_QWORD *)this + 50);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 50) = 0;
  }
  v9 = (char *)*((_QWORD *)this + 41);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 41) = 0;
  }
  v10 = (char *)*((_QWORD *)this + 51);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v10);
    *((_QWORD *)this + 51) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18008b4a4  mov     [rsp+arg_0], rbx
0x18008b4a9  push    rbp
0x18008b4aa  sub     rsp, 20h
0x18008b4ae  mov     rbx, rcx
0x18008b4b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b4b8  lea     rbp, WPP_GLOBAL_Control
0x18008b4bf  cmp     rcx, rbp
0x18008b4c2  jz      short loc_18008B4E5
0x18008b4c4  test    byte ptr [rcx+1Ch], 8
0x18008b4c8  jz      short loc_18008B4E5
0x18008b4ca  cmp     byte ptr [rcx+19h], 6
0x18008b4ce  jb      short loc_18008B4E5
0x18008b4d0  mov     rcx, [rcx+10h]
0x18008b4d4  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008b4db  mov     edx, 1Ch
0x18008b4e0  call    WPP_SF_
0x18008b4e5  mov     rcx, rbx; this
0x18008b4e8  call    ?ReleaseNetworkMonitor@WnpKaDetectorImpl@@AEAAXXZ; WnpKaDetectorImpl::ReleaseNetworkMonitor(void)
0x18008b4ed  lea     rdx, [rbx+120h]; void **
0x18008b4f4  call    ?DeleteWakeTimer@WnpKaDetectorImpl@@AEAAXPEAPEAX@Z; WnpKaDetectorImpl::DeleteWakeTimer(void * *)
0x18008b4f9  lea     rdx, [rbx+128h]; void **
0x18008b500  call    ?DeleteWakeTimer@WnpKaDetectorImpl@@AEAAXPEAPEAX@Z; WnpKaDetectorImpl::DeleteWakeTimer(void * *)
0x18008b505  mov     rcx, [rbx+188h]; pwk
0x18008b50c  test    rcx, rcx
0x18008b50f  jz      short loc_18008B522
0x18008b511  call    cs:__imp_CloseThreadpoolWork
0x18008b517  mov     qword ptr [rbx+188h], 0
0x18008b522  mov     rcx, [rbx+70h]
0x18008b526  test    rcx, rcx
0x18008b529  jz      short loc_18008B544
0x18008b52b  mov     rax, [rcx]
0x18008b52e  mov     edx, 1
0x18008b533  mov     rax, [rax+10h]
0x18008b537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b53c  mov     qword ptr [rbx+70h], 0
0x18008b544  mov     rcx, [rbx+78h]
0x18008b548  test    rcx, rcx
0x18008b54b  jz      short loc_18008B565
0x18008b54d  mov     rax, [rcx]
0x18008b550  mov     edx, 1
0x18008b555  mov     rax, [rax]
0x18008b558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b55d  mov     qword ptr [rbx+78h], 0
0x18008b565  mov     rcx, [rbx+68h]
0x18008b569  test    rcx, rcx
0x18008b56c  jz      short loc_18008B582
0x18008b56e  mov     rax, [rcx]
0x18008b571  mov     rax, [rax+10h]
0x18008b575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b57a  mov     qword ptr [rbx+68h], 0
0x18008b582  mov     rcx, [rbx+190h]; hObject
0x18008b589  lea     rax, [rcx-1]
0x18008b58d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008b591  ja      short loc_18008B5A4
0x18008b593  call    cs:__imp_CloseHandle
0x18008b599  mov     qword ptr [rbx+190h], 0
0x18008b5a4  mov     rcx, [rbx+148h]; hObject
0x18008b5ab  lea     rax, [rcx-1]
0x18008b5af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008b5b3  ja      short loc_18008B5C6
0x18008b5b5  call    cs:__imp_CloseHandle
0x18008b5bb  mov     qword ptr [rbx+148h], 0
0x18008b5c6  mov     rcx, [rbx+198h]; hObject
0x18008b5cd  lea     rax, [rcx-1]
0x18008b5d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008b5d5  ja      short loc_18008B5E8
0x18008b5d7  call    cs:__imp_CloseHandle
0x18008b5dd  mov     qword ptr [rbx+198h], 0
0x18008b5e8  lea     rcx, [rbx+160h]; lpCriticalSection
0x18008b5ef  call    cs:__imp_DeleteCriticalSection
0x18008b5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b5fc  cmp     rcx, rbp
0x18008b5ff  jz      short loc_18008B622
0x18008b601  test    byte ptr [rcx+1Ch], 8
0x18008b605  jz      short loc_18008B622
0x18008b607  cmp     byte ptr [rcx+19h], 6
0x18008b60b  jb      short loc_18008B622
0x18008b60d  mov     rcx, [rcx+10h]
0x18008b611  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008b618  mov     edx, 1Dh
0x18008b61d  call    WPP_SF_
0x18008b622  mov     rbx, [rsp+28h+arg_0]
0x18008b627  xor     eax, eax
0x18008b629  add     rsp, 20h
0x18008b62d  pop     rbp
0x18008b62e  retn
```
