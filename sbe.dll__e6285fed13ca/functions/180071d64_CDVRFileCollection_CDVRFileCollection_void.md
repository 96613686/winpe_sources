# CDVRFileCollection::~CDVRFileCollection(void)

- ea: `0x180071d64`
- end: `0x180071f6c`
- name: `??1CDVRFileCollection@@MEAA@XZ`
- size: `520`
- prototype: `void __fastcall(CDVRFileCollection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180071fc0`

## callees

- `0x1800017e0`
- `0x180071d64`
- `0x180073c20`
- `0x180074d6c`
- `0x180074ec4`
- `0x180076948`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180071da1`
- `KERNEL32!CloseHandle` at `0x180071f3c`
- `KERNEL32!CloseHandle` at `0x180071f4b`
- `KERNEL32!CloseHandle` at `0x1800b4d98`
- `KERNEL32!CloseHandle` at `0x1800b4daa`
- `KERNEL32!CloseHandle` at `0x180071da1`
- `KERNEL32!CloseHandle` at `0x180071f3c`
- `KERNEL32!CloseHandle` at `0x180071f4b`
- `KERNEL32!CloseHandle` at `0x1800b4d98`
- `KERNEL32!CloseHandle` at `0x1800b4daa`
- `KERNEL32!DeleteCriticalSection` at `0x180071f55`
- `KERNEL32!DeleteCriticalSection` at `0x180071f55`
- `KERNEL32!DeleteCriticalSection` at `0x1800b4dbb`
- `KERNEL32!UnmapViewOfFile` at `0x180071f1d`
- `KERNEL32!UnmapViewOfFile` at `0x1800b4d77`
- `KERNEL32!UnmapViewOfFile` at `0x180071f1d`
- `KERNEL32!UnmapViewOfFile` at `0x1800b4d77`

## pseudocode

```c
void __fastcall CDVRFileCollection::~CDVRFileCollection(CDVRFileCollection *this, unsigned __int64 a2)
{
  int v3; // edi
  void *v4; // rcx
  unsigned int *v5; // r8
  int i; // eax
  __int64 v7; // r9
  struct _SHARED_LIST_ENTRY *j; // r9
  __int64 v9; // rdx
  __int64 v10; // r10
  __int64 v11; // r11
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  int v15; // eax
  const void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  unsigned int v19; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)this = &CDVRFileCollection::`vftable';
  v19 = 0;
  v3 = 0;
  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 != (void *)-1LL )
    CloseHandle(v4);
  if ( *((_QWORD *)this + 4) )
  {
    if ( (*((_DWORD *)this + 43) & 0x100) != 0 )
    {
      v3 = 1;
      CDVRFileCollection::Lock((__int64)this, *((const struct CDVRFileCollection::CClientInfo **)this + 3), &v19, 2u, 0);
      for ( i = 0; i < 32; ++i )
        ;
      v7 = *((_QWORD *)this + 4);
      if ( !*(_DWORD *)(v7 + 56) )
      {
        if ( *(_DWORD *)(v7 + 20) )
        {
          for ( j = (struct _SHARED_LIST_ENTRY *)(v7 + 1896); ; *(_DWORD *)((char *)j - 530) = 0 )
          {
            v9 = *(_WORD *)j == 0xFFFF || !(unsigned int)IsSharedListPointerValid(j)
               ? *((_QWORD *)this + 4) + 1896LL
               : 568LL * *(unsigned __int16 *)j + *((_QWORD *)this + 5) + 562LL;
            v10 = *((_QWORD *)this + 4) + 1896LL;
            if ( v9 == v10 )
              break;
            if ( *(_WORD *)j == 0xFFFF || !(unsigned int)IsSharedListPointerValid(j) )
              j = (struct _SHARED_LIST_ENTRY *)v10;
            else
              j = (struct _SHARED_LIST_ENTRY *)(568 * v11 + *((_QWORD *)this + 5) + 562LL);
          }
          CDVRFileCollection::DeleteUnusedInvalidFileNodes(this, 1, v5);
        }
      }
    }
  }
  operator delete(*((void **)this + 13), a2);
  operator delete(*((void **)this + 14), v12);
  operator delete(*((void **)this + 15), v13);
  if ( v3 )
    CDVRFileCollection::Unlock(this, v14, v19, 2, 0);
  v15 = *((_DWORD *)this + 43);
  if ( (v15 & 2) != 0 )
  {
    operator delete(*((void **)this + 4), v14);
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
  }
  else if ( (v15 & 1) != 0 )
  {
    v16 = (const void *)*((_QWORD *)this + 4);
    if ( v16 )
    {
      UnmapViewOfFile(v16);
      *((_QWORD *)this + 4) = 0;
    }
    *((_QWORD *)this + 5) = 0;
    v17 = (void *)*((_QWORD *)this + 6);
    if ( v17 )
      CloseHandle(v17);
  }
  v18 = (void *)*((_QWORD *)this + 12);
  if ( v18 )
    CloseHandle(v18);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
}

```

## disassembly

```asm
0x180071d64  mov     [rsp+arg_10], rbx
0x180071d69  mov     [rsp+arg_18], rdi
0x180071d6e  mov     [rsp+arg_0], rcx
0x180071d73  push    r14
0x180071d75  sub     rsp, 40h
0x180071d79  mov     rbx, rcx
0x180071d7c  lea     rax, ??_7CDVRFileCollection@@6B@; const CDVRFileCollection::`vftable'
0x180071d83  mov     [rcx], rax
0x180071d86  mov     [rsp+48h+arg_8], 0
0x180071d8e  xor     edi, edi
0x180071d90  mov     [rsp+48h+var_18], edi
0x180071d94  mov     rcx, [rcx+80h]; hObject
0x180071d9b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180071d9f  jz      short loc_180071DA7
0x180071da1  call    cs:__imp_CloseHandle
0x180071da7  cmp     qword ptr [rbx+20h], 0
0x180071dac  jz      loc_180071EB1
0x180071db2  test    dword ptr [rbx+0ACh], 100h
0x180071dbc  jz      loc_180071EB1
0x180071dc2  mov     edi, 1
0x180071dc7  mov     [rsp+48h+var_18], edi
0x180071dcb  mov     [rsp+48h+var_28], 0
0x180071dd3  lea     r9d, [rdi+1]
0x180071dd7  lea     r8, [rsp+48h+arg_8]
0x180071ddc  mov     rdx, [rbx+18h]
0x180071de0  mov     rcx, rbx
0x180071de3  call    ?Lock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@AEAHW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Lock(CDVRFileCollection::CClientInfo const *,int &,DVRFILECOLLECTIONCALLER,int)
0x180071de8  xor     eax, eax
0x180071dea  mov     [rsp+48h+var_14], eax
0x180071dee  cmp     eax, 20h ; ' '
0x180071df1  jge     short loc_180071DF7
0x180071df3  inc     eax
0x180071df5  jmp     short loc_180071DEA
0x180071df7  mov     r9, [rbx+20h]
0x180071dfb  cmp     dword ptr [r9+38h], 0
0x180071e00  jnz     loc_180071EB1
0x180071e06  cmp     dword ptr [r9+14h], 0
0x180071e0b  jbe     loc_180071EB1
0x180071e11  add     r9, 768h
0x180071e18  mov     r14d, 0FFFFh
0x180071e1e  cmp     [r9], r14w
0x180071e22  jz      short loc_180071E4B
0x180071e24  mov     rcx, r9; struct _SHARED_LIST_ENTRY *
0x180071e27  call    ?IsSharedListPointerValid@@YAHPEAU_SHARED_LIST_ENTRY@@@Z; IsSharedListPointerValid(_SHARED_LIST_ENTRY *)
0x180071e2c  test    eax, eax
0x180071e2e  jz      short loc_180071E4B
0x180071e30  movzx   r11d, word ptr [r9]
0x180071e34  imul    rcx, r11, 238h
0x180071e3b  mov     rdx, [rbx+28h]
0x180071e3f  add     rdx, 232h
0x180071e46  add     rdx, rcx
0x180071e49  jmp     short loc_180071E5A
0x180071e4b  mov     rdx, [rbx+20h]
0x180071e4f  add     rdx, 768h
0x180071e56  movzx   r11d, word ptr [r9]
0x180071e5a  mov     r10, [rbx+20h]
0x180071e5e  add     r10, 768h
0x180071e65  cmp     rdx, r10
0x180071e68  jz      short loc_180071EA6
0x180071e6a  cmp     [r9], r14w
0x180071e6e  jz      short loc_180071E93
0x180071e70  mov     rcx, r9; struct _SHARED_LIST_ENTRY *
0x180071e73  call    ?IsSharedListPointerValid@@YAHPEAU_SHARED_LIST_ENTRY@@@Z; IsSharedListPointerValid(_SHARED_LIST_ENTRY *)
0x180071e78  test    eax, eax
0x180071e7a  jz      short loc_180071E93
0x180071e7c  imul    rcx, r11, 238h
0x180071e83  mov     r9, [rbx+28h]
0x180071e87  add     r9, 232h
0x180071e8e  add     r9, rcx
0x180071e91  jmp     short loc_180071E96
0x180071e93  mov     r9, r10
0x180071e96  mov     dword ptr [r9-212h], 0
0x180071ea1  jmp     loc_180071E1E
0x180071ea6  mov     edx, edi; int
0x180071ea8  mov     rcx, rbx; this
0x180071eab  call    ?DeleteUnusedInvalidFileNodes@CDVRFileCollection@@IEAAJHPEAK@Z; CDVRFileCollection::DeleteUnusedInvalidFileNodes(int,ulong *)
0x180071eb0  nop
0x180071eb1  mov     rcx, [rbx+68h]; void *
0x180071eb5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180071eba  mov     rcx, [rbx+70h]; void *
0x180071ebe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180071ec3  mov     rcx, [rbx+78h]; void *
0x180071ec7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180071ecc  test    edi, edi
0x180071ece  jz      short loc_180071EEB
0x180071ed0  mov     [rsp+48h+var_28], 0
0x180071ed8  mov     r9d, 2
0x180071ede  mov     r8d, [rsp+48h+arg_8]
0x180071ee3  mov     rcx, rbx
0x180071ee6  call    ?Unlock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@HW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Unlock(CDVRFileCollection::CClientInfo const *,int,DVRFILECOLLECTIONCALLER,int)
0x180071eeb  mov     eax, [rbx+0ACh]
0x180071ef1  test    al, 2
0x180071ef3  jz      short loc_180071F10
0x180071ef5  mov     rcx, [rbx+20h]; void *
0x180071ef9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180071efe  mov     qword ptr [rbx+20h], 0
0x180071f06  mov     qword ptr [rbx+28h], 0
0x180071f0e  jmp     short loc_180071F42
0x180071f10  test    al, 1
0x180071f12  jz      short loc_180071F42
0x180071f14  mov     rcx, [rbx+20h]; lpBaseAddress
0x180071f18  test    rcx, rcx
0x180071f1b  jz      short loc_180071F2B
0x180071f1d  call    cs:__imp_UnmapViewOfFile
0x180071f23  mov     qword ptr [rbx+20h], 0
0x180071f2b  mov     qword ptr [rbx+28h], 0
0x180071f33  mov     rcx, [rbx+30h]; hObject
0x180071f37  test    rcx, rcx
0x180071f3a  jz      short loc_180071F42
0x180071f3c  call    cs:__imp_CloseHandle
0x180071f42  mov     rcx, [rbx+60h]; hObject
0x180071f46  test    rcx, rcx
0x180071f49  jz      short loc_180071F51
0x180071f4b  call    cs:__imp_CloseHandle
0x180071f51  lea     rcx, [rbx+38h]; lpCriticalSection
0x180071f55  call    cs:__imp_DeleteCriticalSection
0x180071f5b  mov     rbx, [rsp+48h+arg_10]
0x180071f60  mov     rdi, [rsp+48h+arg_18]
0x180071f65  add     rsp, 40h
0x180071f69  pop     r14
0x180071f6b  retn
0x1800b4cf5  push    rbx
0x1800b4cf7  push    rbp
0x1800b4cf8  sub     rsp, 38h
0x1800b4cfc  mov     rbp, rdx
0x1800b4cff  mov     rbx, [rbp+50h]
0x1800b4d03  mov     rcx, [rbx+68h]; void *
0x1800b4d07  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b4d0c  mov     rcx, [rbx+70h]; void *
0x1800b4d10  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b4d15  mov     rcx, [rbx+78h]; void *
0x1800b4d19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b4d1e  cmp     dword ptr [rbp+30h], 0
0x1800b4d22  jz      short loc_1800B4D3F
0x1800b4d24  mov     [rsp+48h+var_28], 0
0x1800b4d2c  mov     r9d, 2
0x1800b4d32  mov     r8d, [rbp+58h]
0x1800b4d36  mov     rcx, rbx
0x1800b4d39  call    ?Unlock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@HW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Unlock(CDVRFileCollection::CClientInfo const *,int,DVRFILECOLLECTIONCALLER,int)
0x1800b4d3e  nop
0x1800b4d3f  test    byte ptr [rbx+0ACh], 2
0x1800b4d46  jz      short loc_1800B4D63
0x1800b4d48  mov     rcx, [rbx+20h]; void *
0x1800b4d4c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b4d51  mov     qword ptr [rbx+20h], 0
0x1800b4d59  mov     qword ptr [rbx+28h], 0
0x1800b4d61  jmp     short loc_1800B4D9F
0x1800b4d63  test    byte ptr [rbx+0ACh], 1
0x1800b4d6a  jz      short loc_1800B4D9F
0x1800b4d6c  cmp     qword ptr [rbx+20h], 0
0x1800b4d71  jz      short loc_1800B4D85
0x1800b4d73  mov     rcx, [rbx+20h]; lpBaseAddress
0x1800b4d77  call    cs:__imp_UnmapViewOfFile
0x1800b4d7d  mov     qword ptr [rbx+20h], 0
0x1800b4d85  mov     qword ptr [rbx+28h], 0
0x1800b4d8d  cmp     qword ptr [rbx+30h], 0
0x1800b4d92  jz      short loc_1800B4D9F
0x1800b4d94  mov     rcx, [rbx+30h]; hObject
0x1800b4d98  call    cs:__imp_CloseHandle
0x1800b4d9e  nop
0x1800b4d9f  cmp     qword ptr [rbx+60h], 0
0x1800b4da4  jz      short loc_1800B4DB1
0x1800b4da6  mov     rcx, [rbx+60h]; hObject
0x1800b4daa  call    cs:__imp_CloseHandle
0x1800b4db0  nop
0x1800b4db1  lea     rcx, [rbx+38h]
0x1800b4db5  add     rsp, 38h
0x1800b4db9  pop     rbp
0x1800b4dba  pop     rbx
0x1800b4dbb  jmp     cs:__imp_DeleteCriticalSection
```
