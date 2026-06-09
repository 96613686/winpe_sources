# CThemeManager2::~CThemeManager2(void)

- ea: `0x18001e2e8`
- end: `0x18001e3c8`
- name: `??1CThemeManager2@@EEAA@XZ`
- size: `224`
- prototype: `void __fastcall(CThemeManager2 *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053610`

## callees

- `0x18001e2e8`
- `0x18002033c`
- `0x180033698`
- `0x18003dbb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e34e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e34e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e341`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e341`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e393`

## pseudocode

```c
void __fastcall CThemeManager2::~CThemeManager2(CThemeManager2 *this)
{
  _QWORD *v1; // rdi
  bool v3; // zf
  CDimmedWindow *v4; // rcx
  struct _TP_WORK *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 i; // rsi

  v1 = (_QWORD *)((char *)this + 2112);
  v3 = *((_QWORD *)this + 264) == 0;
  *(_QWORD *)this = &CThemeManager2::`vftable';
  if ( !v3 )
    CDPA<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::DestroyCallback((char *)this + 2112);
  v4 = (CDimmedWindow *)*((_QWORD *)this + 267);
  *((_QWORD *)this + 267) = 0;
  if ( v4 )
    CDimmedWindow::Release(v4);
  v5 = (struct _TP_WORK *)*((_QWORD *)this + 269);
  if ( v5 )
    CloseThreadpoolWork(v5);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2168));
  v6 = (void *)*((_QWORD *)this + 262);
  if ( v6 )
    CloseHandle(v6);
  v7 = (void *)*((_QWORD *)this + 263);
  if ( v7 )
    CloseHandle(v7);
  if ( *((_BYTE *)this + 2360) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 556); i = (unsigned int)(i + 1) )
      CoTaskMemFree(*((LPVOID *)this + i + 279));
  }
  _InterlockedDecrement((volatile signed __int32 *)&g_cRef);
  if ( *v1 )
    CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::Destroy(v1);
}

```

## disassembly

```asm
0x18001e2e8  mov     [rsp+arg_0], rbx
0x18001e2ed  mov     [rsp+arg_8], rsi
0x18001e2f2  push    rdi
0x18001e2f3  sub     rsp, 20h
0x18001e2f7  lea     rdi, [rcx+840h]
0x18001e2fe  mov     rbx, rcx
0x18001e301  cmp     qword ptr [rdi], 0
0x18001e305  lea     rax, ??_7CThemeManager2@@6B@; const CThemeManager2::`vftable'
0x18001e30c  mov     [rcx], rax
0x18001e30f  jz      short loc_18001E319
0x18001e311  mov     rcx, rdi
0x18001e314  call    ?DestroyCallback@?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAXP6AHPEAGPEAX@Z1@Z; CDPA<ushort,CTContainer_PolicyUnOwned<ushort>>::DestroyCallback(int (*)(ushort *,void *),void *)
0x18001e319  mov     rcx, [rbx+858h]; this
0x18001e320  mov     qword ptr [rbx+858h], 0
0x18001e32b  test    rcx, rcx
0x18001e32e  jz      short loc_18001E335
0x18001e330  call    ?Release@CDimmedWindow@@QEAAKXZ; CDimmedWindow::Release(void)
0x18001e335  mov     rcx, [rbx+868h]; pwk
0x18001e33c  test    rcx, rcx
0x18001e33f  jz      short loc_18001E347
0x18001e341  call    cs:__imp_CloseThreadpoolWork
0x18001e347  lea     rcx, [rbx+878h]; lpCriticalSection
0x18001e34e  call    cs:__imp_DeleteCriticalSection
0x18001e354  mov     rcx, [rbx+830h]; hObject
0x18001e35b  test    rcx, rcx
0x18001e35e  jz      short loc_18001E366
0x18001e360  call    cs:__imp_CloseHandle
0x18001e366  mov     rcx, [rbx+838h]; hObject
0x18001e36d  test    rcx, rcx
0x18001e370  jz      short loc_18001E378
0x18001e372  call    cs:__imp_CloseHandle
0x18001e378  cmp     byte ptr [rbx+938h], 0
0x18001e37f  jz      short loc_18001E3A3
0x18001e381  xor     esi, esi
0x18001e383  cmp     [rbx+8B0h], esi
0x18001e389  jbe     short loc_18001E3A3
0x18001e38b  mov     rcx, [rbx+rsi*8+8B8h]; pv
0x18001e393  call    cs:__imp_CoTaskMemFree
0x18001e399  inc     esi
0x18001e39b  cmp     esi, [rbx+8B0h]
0x18001e3a1  jb      short loc_18001E38B
0x18001e3a3  lock dec cs:?g_cRef@@3KA; ulong g_cRef
0x18001e3aa  cmp     qword ptr [rdi], 0
0x18001e3ae  jz      short loc_18001E3B8
0x18001e3b0  mov     rcx, rdi
0x18001e3b3  call    ?Destroy@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAHXZ; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::Destroy(void)
0x18001e3b8  mov     rbx, [rsp+28h+arg_0]
0x18001e3bd  mov     rsi, [rsp+28h+arg_8]
0x18001e3c2  add     rsp, 20h
0x18001e3c6  pop     rdi
0x18001e3c7  retn
```
