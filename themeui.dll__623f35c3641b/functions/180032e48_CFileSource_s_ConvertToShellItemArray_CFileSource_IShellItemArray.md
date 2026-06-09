# CFileSource::s_ConvertToShellItemArray(CFileSource *,IShellItemArray * *)

- ea: `0x180032e48`
- end: `0x180032f6f`
- name: `?s_ConvertToShellItemArray@CFileSource@@SAJPEAV1@PEAPEAUIShellItemArray@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(struct CFileSource *this, struct IShellItemArray **ppv)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18004d9f0`

## callees

- `0x180004d70`
- `0x180020b3c`
- `0x180032e48`
- `0x18003633c`
- `0x18003709c`
- `0x180060cdc`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x180032f47`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x180032f47`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180032edf`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180032edf`
- `SHELL32!SHCreateItemFromIDList` at `0x180032f2c`
- `SHELL32!SHCreateItemFromIDList` at `0x180032f2c`
- `SHELL32!__imp_ILClone` at `0x180032f17`
- `SHELL32!__imp_ILClone` at `0x180032f17`
- `SHELL32!__imp_ILFree` at `0x180032eed`
- `SHELL32!__imp_ILFree` at `0x180032eed`

## pseudocode

```c
__int64 __fastcall CFileSource::s_ConvertToShellItemArray(struct CFileSource *this, struct IShellItemArray **ppv)
{
  HRESULT v4; // ebx
  unsigned int SpecificFileCount; // eax
  __int64 v6; // rcx
  UINT v7; // esi
  unsigned __int64 v8; // rbx
  LPCITEMIDLIST *v9; // rax
  LPCITEMIDLIST *v10; // r14
  __int64 v11; // rbp
  int SpecificFile; // eax
  __int64 v13; // rdi
  const ITEMIDLIST *v14; // rcx
  const ITEMIDLIST *v15; // rax
  void *ppva; // [rsp+60h] [rbp+8h] BYREF

  *ppv = 0;
  v4 = -2147024809;
  if ( this )
  {
    SpecificFileCount = CFileSource::GetSpecificFileCount(this);
    v7 = SpecificFileCount;
    if ( SpecificFileCount )
    {
      v8 = 8LL * SpecificFileCount;
      if ( !is_mul_ok(SpecificFileCount, 8u) )
        v8 = -1;
      v9 = (LPCITEMIDLIST *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
      v10 = v9;
      if ( v9 )
      {
        memset_0(v9, 0, v8);
        v11 = 0;
        while ( (unsigned int)v11 < v7 )
        {
          SpecificFile = CFileSource::GetSpecificFile(this, v11, (struct _ITEMIDLIST_ABSOLUTE **)&v10[v11]);
          v11 = (unsigned int)(v11 + 1);
          v4 = SpecificFile;
          if ( SpecificFile < 0 )
            goto LABEL_11;
        }
        v4 = SHCreateShellItemArrayFromIDLists(v7, v10, ppv);
LABEL_11:
        v13 = 0;
        do
        {
          ILFree((LPITEMIDLIST)v10[v13]);
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (unsigned int)v13 < v7 );
        operator delete(v10);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      v14 = *(const ITEMIDLIST **)(v6 + 8);
      ppva = 0;
      v15 = ILClone(v14);
      v4 = SHCreateItemFromIDList(v15, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppva);
      if ( v4 >= 0 )
      {
        v4 = SHCreateShellItemArrayFromShellItem(
               (IShellItem *)ppva,
               &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
               (void **)ppv);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppva + 16LL))(ppva);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180032e48  push    rbx
0x180032e4a  push    rbp
0x180032e4b  push    rsi
0x180032e4c  push    rdi
0x180032e4d  push    r14
0x180032e4f  push    r15
0x180032e51  sub     rsp, 28h
0x180032e55  mov     qword ptr [rdx], 0
0x180032e5c  mov     r15, rdx
0x180032e5f  mov     rdi, rcx
0x180032e62  mov     ebx, 80070057h
0x180032e67  test    rcx, rcx
0x180032e6a  jz      loc_180032F60
0x180032e70  call    ?GetSpecificFileCount@CFileSource@@QEAAKXZ; CFileSource::GetSpecificFileCount(void)
0x180032e75  mov     esi, eax
0x180032e77  test    eax, eax
0x180032e79  jz      loc_180032F0A
0x180032e7f  mov     eax, 8
0x180032e84  mul     rsi
0x180032e87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032e8e  mov     rbx, rax
0x180032e91  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180032e98  cmovb   rbx, rax
0x180032e9c  mov     rcx, rbx; unsigned __int64
0x180032e9f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180032ea4  mov     r14, rax
0x180032ea7  test    rax, rax
0x180032eaa  jz      short loc_180032F03
0x180032eac  mov     r8, rbx; Size
0x180032eaf  xor     edx, edx; Val
0x180032eb1  mov     rcx, rax; void *
0x180032eb4  call    memset_0
0x180032eb9  xor     ebp, ebp
0x180032ebb  cmp     ebp, esi
0x180032ebd  jnb     short loc_180032ED7
0x180032ebf  lea     r8, [r14+rbp*8]; struct _ITEMIDLIST_ABSOLUTE **
0x180032ec3  mov     edx, ebp; unsigned int
0x180032ec5  mov     rcx, rdi; this
0x180032ec8  call    ?GetSpecificFile@CFileSource@@QEAAJKPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CFileSource::GetSpecificFile(ulong,_ITEMIDLIST_ABSOLUTE * *)
0x180032ecd  inc     ebp
0x180032ecf  mov     ebx, eax
0x180032ed1  test    eax, eax
0x180032ed3  jns     short loc_180032EBB
0x180032ed5  jmp     short loc_180032EE7
0x180032ed7  mov     r8, r15; ppsiItemArray
0x180032eda  mov     rdx, r14; rgpidl
0x180032edd  mov     ecx, esi; cidl
0x180032edf  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x180032ee5  mov     ebx, eax
0x180032ee7  xor     edi, edi
0x180032ee9  mov     rcx, [r14+rdi*8]; pidl
0x180032eed  call    cs:__imp_ILFree
0x180032ef3  inc     edi
0x180032ef5  cmp     edi, esi
0x180032ef7  jb      short loc_180032EE9
0x180032ef9  mov     rcx, r14; lpMem
0x180032efc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032f01  jmp     short loc_180032F60
0x180032f03  mov     ebx, 8007000Eh
0x180032f08  jmp     short loc_180032F60
0x180032f0a  mov     rcx, [rcx+8]; pidl
0x180032f0e  mov     [rsp+58h+ppv], 0
0x180032f17  call    cs:__imp_ILClone
0x180032f1d  mov     rcx, rax; pidl
0x180032f20  lea     r8, [rsp+58h+ppv]; ppv
0x180032f25  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180032f2c  call    cs:__imp_SHCreateItemFromIDList
0x180032f32  mov     ebx, eax
0x180032f34  test    eax, eax
0x180032f36  js      short loc_180032F60
0x180032f38  mov     rcx, [rsp+58h+ppv]; psi
0x180032f3d  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x180032f44  mov     r8, r15; ppv
0x180032f47  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x180032f4d  mov     rcx, [rsp+58h+ppv]
0x180032f52  mov     ebx, eax
0x180032f54  mov     rax, [rcx]
0x180032f57  mov     rax, [rax+10h]
0x180032f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f60  mov     eax, ebx
0x180032f62  add     rsp, 28h
0x180032f66  pop     r15
0x180032f68  pop     r14
0x180032f6a  pop     rdi
0x180032f6b  pop     rsi
0x180032f6c  pop     rbp
0x180032f6d  pop     rbx
0x180032f6e  retn
```
