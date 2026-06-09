# CImage::~CImage(void)

- ea: `0x180003a60`
- end: `0x180003b8a`
- name: `??1CImage@@UEAA@XZ`
- size: `298`
- prototype: `void __fastcall(CImage *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003b90`
- `0x180006090`
- `0x18000a948`

## callees

- `0x180003a60`
- `0x180009198`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003a85`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003a9f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003ab9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003ad3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003a85`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003a9f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003ab9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003ad3`
- `KERNEL32!GetProcessHeap` at `0x180003aed`
- `KERNEL32!GetProcessHeap` at `0x180003aed`
- `KERNEL32!HeapFree` at `0x180003b01`
- `KERNEL32!HeapFree` at `0x180003b01`

## pseudocode

```c
void __fastcall CImage::~CImage(CImage *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx

  *(_QWORD *)this = &CImage::`vftable';
  CImage::CleanupImageInfo(this);
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 11) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 12);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 12) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 13);
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 13) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 14);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 14) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 15);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    if ( HeapFree(ProcessHeap, 0, v6) )
      *((_QWORD *)this + 15) = 0;
  }
  v8 = *((_QWORD *)this + 48);
  if ( v8 )
  {
    v9 = v8 + 8 + *(int *)(*(_QWORD *)(v8 + 8) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 48) = 0;
  }
  v10 = *((_QWORD *)this + 47);
  if ( v10 )
  {
    v11 = v10 + 8 + *(int *)(*(_QWORD *)(v10 + 8) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)this + 47) = 0;
  }
  *(_QWORD *)this = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x180003a60  mov     [rsp+arg_0], rbx
0x180003a65  push    rdi
0x180003a66  sub     rsp, 20h
0x180003a6a  lea     rax, ??_7CImage@@6B@; const CImage::`vftable'
0x180003a71  mov     rbx, rcx
0x180003a74  mov     [rcx], rax
0x180003a77  call    ?CleanupImageInfo@CImage@@AEAAXXZ; CImage::CleanupImageInfo(void)
0x180003a7c  mov     rcx, [rbx+58h]
0x180003a80  test    rcx, rcx
0x180003a83  jz      short loc_180003A96
0x180003a85  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003a8c  nop     dword ptr [rax+rax+00h]
0x180003a91  and     qword ptr [rbx+58h], 0
0x180003a96  mov     rcx, [rbx+60h]
0x180003a9a  test    rcx, rcx
0x180003a9d  jz      short loc_180003AB0
0x180003a9f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003aa6  nop     dword ptr [rax+rax+00h]
0x180003aab  and     qword ptr [rbx+60h], 0
0x180003ab0  mov     rcx, [rbx+68h]
0x180003ab4  test    rcx, rcx
0x180003ab7  jz      short loc_180003ACA
0x180003ab9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003ac0  nop     dword ptr [rax+rax+00h]
0x180003ac5  and     qword ptr [rbx+68h], 0
0x180003aca  mov     rcx, [rbx+70h]
0x180003ace  test    rcx, rcx
0x180003ad1  jz      short loc_180003AE4
0x180003ad3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003ada  nop     dword ptr [rax+rax+00h]
0x180003adf  and     qword ptr [rbx+70h], 0
0x180003ae4  mov     rdi, [rbx+78h]
0x180003ae8  test    rdi, rdi
0x180003aeb  jz      short loc_180003B16
0x180003aed  call    cs:__imp_GetProcessHeap
0x180003af4  nop     dword ptr [rax+rax+00h]
0x180003af9  mov     r8, rdi; lpMem
0x180003afc  xor     edx, edx; dwFlags
0x180003afe  mov     rcx, rax; hHeap
0x180003b01  call    cs:__imp_HeapFree
0x180003b08  nop     dword ptr [rax+rax+00h]
0x180003b0d  test    eax, eax
0x180003b0f  jz      short loc_180003B16
0x180003b11  and     qword ptr [rbx+78h], 0
0x180003b16  mov     rdx, [rbx+180h]
0x180003b1d  test    rdx, rdx
0x180003b20  jz      short loc_180003B45
0x180003b22  mov     rax, [rdx+8]
0x180003b26  add     rdx, 8
0x180003b2a  movsxd  rcx, dword ptr [rax+4]
0x180003b2e  add     rcx, rdx
0x180003b31  mov     rax, [rcx]
0x180003b34  mov     rax, [rax+10h]
0x180003b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b3d  and     qword ptr [rbx+180h], 0
0x180003b45  mov     rdx, [rbx+178h]
0x180003b4c  test    rdx, rdx
0x180003b4f  jz      short loc_180003B74
0x180003b51  mov     rax, [rdx+8]
0x180003b55  add     rdx, 8
0x180003b59  movsxd  rcx, dword ptr [rax+4]
0x180003b5d  add     rcx, rdx
0x180003b60  mov     rax, [rcx]
0x180003b63  mov     rax, [rax+10h]
0x180003b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b6c  and     qword ptr [rbx+178h], 0
0x180003b74  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x180003b7b  mov     [rbx], rax
0x180003b7e  mov     rbx, [rsp+28h+arg_0]
0x180003b83  add     rsp, 20h
0x180003b87  pop     rdi
0x180003b88  retn
```
