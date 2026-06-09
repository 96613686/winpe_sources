# ImageRequestManager::~ImageRequestManager(void)

- ea: `0x180034b10`
- end: `0x180034c46`
- name: `??1ImageRequestManager@@QEAA@XZ`
- size: `310`
- prototype: `void __fastcall(ImageRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180086680`

## callees

- `0x180004e38`
- `0x180034b10`
- `0x180034ca8`
- `0x180071cf4`
- `0x1800c5ec4`
- `0x1800c5f68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034b2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034b81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034b2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034b81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034b6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034c00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034b6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034c00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b74`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034c09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b74`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034c09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034b4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034bc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034be0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034b4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034bc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034be0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034b5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034bd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034bee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034b5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034bd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034bee`

## pseudocode

```c
void __fastcall ImageRequestManager::~ImageRequestManager(ImageRequestManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  WPN_TILE_IMAGE_REQUEST *v3; // rcx
  void *v4; // rsi
  HANDLE ProcessHeap; // rax
  void **v6; // rsi
  char *v7; // rdi
  void **v8; // rax
  void *v9; // r14
  HANDLE v10; // rax
  HANDLE v11; // rax

  *(_QWORD *)this = &ImageRequestManager::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (WPN_TILE_IMAGE_REQUEST *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    WPN_TILE_IMAGE_REQUEST::Cleanup(v3);
    v4 = (void *)*((_QWORD *)this + 1);
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
      *((_QWORD *)this + 1) = 0;
    }
  }
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  v6 = (void **)((char *)this + 64);
  while ( 1 )
  {
    v7 = (char *)*v6;
    if ( *v6 == v6 )
      break;
    if ( *((void ***)v7 + 1) != v6 || (v8 = *(void ***)v7, *(char **)(*(_QWORD *)v7 + 8LL) != v7) )
      __fastfail(3u);
    *v6 = v8;
    v8[1] = v6;
    WPN_IMAGE_REQUEST_ENTRY::Cleanup(*((WPN_IMAGE_REQUEST_ENTRY **)v7 + 2));
    WpnCallbackReference::Release((WpnCallbackReference *)(v7 + 24));
    v9 = (void *)*((_QWORD *)v7 + 2);
    if ( v9 )
    {
      v10 = GetProcessHeap();
      HeapFree(v10, 0, v9);
      *((_QWORD *)v7 + 2) = 0;
    }
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v7);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 408);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 400);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 392);
  ImageUrlHash::~ImageUrlHash((ImageRequestManager *)((char *)this + 120));
}

```

## disassembly

```asm
0x180034b10  push    rbx
0x180034b12  push    rbp
0x180034b13  push    rsi
0x180034b14  push    rdi
0x180034b15  push    r14
0x180034b17  sub     rsp, 20h
0x180034b1b  mov     rbx, rcx
0x180034b1e  lea     rax, ??_7ImageRequestManager@@6B@; const ImageRequestManager::`vftable'
0x180034b25  mov     [rcx], rax
0x180034b28  lea     rdi, [rcx+18h]
0x180034b2c  mov     rcx, rdi; lpCriticalSection
0x180034b2f  call    cs:__imp_EnterCriticalSection
0x180034b35  mov     rcx, [rbx+8]; this
0x180034b39  test    rcx, rcx
0x180034b3c  jz      short loc_180034B68
0x180034b3e  call    ?Cleanup@WPN_TILE_IMAGE_REQUEST@@QEAAXXZ; WPN_TILE_IMAGE_REQUEST::Cleanup(void)
0x180034b43  mov     rsi, [rbx+8]
0x180034b47  test    rsi, rsi
0x180034b4a  jz      short loc_180034B68
0x180034b4c  call    cs:__imp_GetProcessHeap
0x180034b52  mov     r8, rsi; lpMem
0x180034b55  xor     edx, edx; dwFlags
0x180034b57  mov     rcx, rax; hHeap
0x180034b5a  call    cs:__imp_HeapFree
0x180034b60  mov     qword ptr [rbx+8], 0
0x180034b68  mov     rcx, rdi; lpCriticalSection
0x180034b6b  call    cs:__imp_LeaveCriticalSection
0x180034b71  mov     rcx, rdi; lpCriticalSection
0x180034b74  call    cs:__imp_DeleteCriticalSection
0x180034b7a  lea     rbp, [rbx+50h]
0x180034b7e  mov     rcx, rbp; lpCriticalSection
0x180034b81  call    cs:__imp_EnterCriticalSection
0x180034b87  lea     rsi, [rbx+40h]
0x180034b8b  mov     rdi, [rsi]
0x180034b8e  cmp     rdi, rsi
0x180034b91  jz      short loc_180034BFD
0x180034b93  cmp     [rdi+8], rsi
0x180034b97  jnz     short loc_180034BF6
0x180034b99  mov     rax, [rdi]
0x180034b9c  cmp     [rax+8], rdi
0x180034ba0  jnz     short loc_180034BF6
0x180034ba2  mov     [rsi], rax
0x180034ba5  mov     [rax+8], rsi
0x180034ba9  mov     rcx, [rdi+10h]; this
0x180034bad  call    ?Cleanup@WPN_IMAGE_REQUEST_ENTRY@@QEAAXXZ; WPN_IMAGE_REQUEST_ENTRY::Cleanup(void)
0x180034bb2  lea     rcx, [rdi+18h]; this
0x180034bb6  call    ?Release@WpnCallbackReference@@QEAAXXZ; WpnCallbackReference::Release(void)
0x180034bbb  mov     r14, [rdi+10h]
0x180034bbf  test    r14, r14
0x180034bc2  jz      short loc_180034BE0
0x180034bc4  call    cs:__imp_GetProcessHeap
0x180034bca  mov     r8, r14; lpMem
0x180034bcd  xor     edx, edx; dwFlags
0x180034bcf  mov     rcx, rax; hHeap
0x180034bd2  call    cs:__imp_HeapFree
0x180034bd8  mov     qword ptr [rdi+10h], 0
0x180034be0  call    cs:__imp_GetProcessHeap
0x180034be6  mov     rcx, rax; hHeap
0x180034be9  mov     r8, rdi; lpMem
0x180034bec  xor     edx, edx; dwFlags
0x180034bee  call    cs:__imp_HeapFree
0x180034bf4  jmp     short loc_180034B8B
0x180034bf6  mov     ecx, 3
0x180034bfb  int     29h; Win8: RtlFailFast(ecx)
0x180034bfd  mov     rcx, rbp; lpCriticalSection
0x180034c00  call    cs:__imp_LeaveCriticalSection
0x180034c06  mov     rcx, rbp; lpCriticalSection
0x180034c09  call    cs:__imp_DeleteCriticalSection
0x180034c0f  lea     rcx, [rbx+198h]
0x180034c16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034c1b  lea     rcx, [rbx+190h]
0x180034c22  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034c27  lea     rcx, [rbx+188h]
0x180034c2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034c33  lea     rcx, [rbx+78h]; this
0x180034c37  add     rsp, 20h
0x180034c3b  pop     r14
0x180034c3d  pop     rdi
0x180034c3e  pop     rsi
0x180034c3f  pop     rbp
0x180034c40  pop     rbx
0x180034c41  jmp     ??1ImageUrlHash@@QEAA@XZ; ImageUrlHash::~ImageUrlHash(void)
```
