# CreateHidaFromStorageItemVector(Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *> *,void * *)

- ea: `0x180023b94`
- end: `0x180023d32`
- name: `?CreateHidaFromStorageItemVector@@YAJPEAU?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@PEAPEAX@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053900`

## callees

- `0x18000581b`
- `0x1800096c8`
- `0x180023b94`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180023c67`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180023c67`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180023c3d`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180023c52`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180023c85`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180023cb4`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180023c3d`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180023c52`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180023c85`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180023cb4`
- `COMCTL32!__imp_DPA_Create` at `0x180023be5`
- `COMCTL32!__imp_DPA_Create` at `0x180023be5`
- `COMCTL32!__imp_DPA_Destroy` at `0x180023d15`
- `COMCTL32!__imp_DPA_Destroy` at `0x180023d15`
- `COMCTL32!__imp_DPA_DestroyCallback` at `0x180023d04`
- `COMCTL32!__imp_DPA_DestroyCallback` at `0x180023d04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateHidaFromStorageItemVector(__int64 a1, _QWORD *a2)
{
  int v4; // ebx
  unsigned int v5; // ebp
  __int64 v6; // r13
  unsigned int v7; // r15d
  unsigned int v8; // ebx
  __int64 i; // rdi
  _DWORD *v10; // rax
  _DWORD *v11; // rsi
  __int64 v12; // r12
  UINT v13; // ebx
  UINT v14; // r15d
  const ITEMIDLIST *v15; // rdi
  UINT v16; // ebx
  int cItemGrow; // [rsp+60h] [rbp+8h] BYREF
  HDPA hdpa; // [rsp+68h] [rbp+10h] BYREF
  HDPA *p_hdpa; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  hdpa = 0;
  cItemGrow = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 56LL))(a1, &cItemGrow);
  if ( v4 >= 0 )
  {
    hdpa = DPA_Create(cItemGrow);
    if ( hdpa )
    {
      p_hdpa = &hdpa;
      v4 = IterateOverVector_Windows::Storage::IStorageItem__lambda_0b6673e7cc62c5cb12d30d33ce09830a___(a1, &p_hdpa);
      if ( v4 < 0 )
        goto LABEL_17;
      if ( hdpa )
        v5 = *(_DWORD *)hdpa;
      else
        v5 = 0;
      v6 = *((_QWORD *)hdpa + 1);
      v7 = 4 * v5 + 8;
      v8 = v7 + ILGetSize(&c_idlDesktop);
      for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
        v8 += ILGetSize(*(LPCITEMIDLIST *)(v6 + 8 * i));
      v10 = GlobalAlloc(0x40u, v8);
      v11 = v10;
      if ( v10 )
      {
        *v10 = v5;
        if ( v5 )
        {
          v12 = 0;
          v13 = ILGetSize(&c_idlDesktop);
          v11[1] = v7;
          memcpy_0((char *)v11 + v7, &c_idlDesktop, v13);
          v14 = v13 + v7;
          do
          {
            v15 = *(const ITEMIDLIST **)(v6 + 8 * v12);
            v12 = (unsigned int)(v12 + 1);
            v16 = ILGetSize(v15);
            v11[(unsigned int)v12 + 1] = v14;
            memcpy_0((char *)v11 + v14, v15, v16);
            v14 += v16;
          }
          while ( (_DWORD)v12 != v5 );
          *a2 = v11;
          goto LABEL_15;
        }
      }
      *a2 = v10;
      if ( v10 )
      {
LABEL_15:
        v4 = 0;
        goto LABEL_17;
      }
    }
    v4 = -2147024882;
  }
LABEL_17:
  if ( hdpa )
  {
    DPA_DestroyCallback(hdpa, CDPA_Base<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyCoTaskMem>::_StandardDestroyCB, 0);
    hdpa = 0;
    DPA_Destroy(0);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180023b94  mov     [rsp+arg_18], rbx
0x180023b99  push    rbp
0x180023b9a  push    rsi
0x180023b9b  push    rdi
0x180023b9c  push    r12
0x180023b9e  push    r13
0x180023ba0  push    r14
0x180023ba2  push    r15
0x180023ba4  sub     rsp, 20h
0x180023ba8  mov     r14, rdx
0x180023bab  mov     rdi, rcx
0x180023bae  mov     qword ptr [rdx], 0
0x180023bb5  mov     [rsp+58h+hdpa], 0
0x180023bbe  mov     [rsp+58h+cItemGrow], 0
0x180023bc6  mov     rax, [rcx]
0x180023bc9  lea     rdx, [rsp+58h+cItemGrow]
0x180023bce  mov     rax, [rax+38h]
0x180023bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bd7  mov     ebx, eax
0x180023bd9  test    eax, eax
0x180023bdb  js      loc_180023CF0
0x180023be1  mov     ecx, [rsp+58h+cItemGrow]; cItemGrow
0x180023be5  call    cs:__imp_DPA_Create
0x180023beb  mov     [rsp+58h+hdpa], rax
0x180023bf0  test    rax, rax
0x180023bf3  jz      loc_180023CEB
0x180023bf9  lea     rax, [rsp+58h+hdpa]
0x180023bfe  mov     [rsp+58h+arg_10], rax
0x180023c03  lea     rdx, [rsp+58h+arg_10]
0x180023c08  mov     rcx, rdi
0x180023c0b  call    IterateOverVector_Windows__Storage__IStorageItem__lambda_0b6673e7cc62c5cb12d30d33ce09830a___
0x180023c10  mov     ebx, eax
0x180023c12  test    eax, eax
0x180023c14  js      loc_180023CF0
0x180023c1a  mov     rax, [rsp+58h+hdpa]
0x180023c1f  test    rax, rax
0x180023c22  jz      short loc_180023C28
0x180023c24  mov     ebp, [rax]
0x180023c26  jmp     short loc_180023C2A
0x180023c28  xor     ebp, ebp
0x180023c2a  mov     r13, [rax+8]
0x180023c2e  lea     r15d, ds:8[rbp*4]
0x180023c36  lea     rcx, c_idlDesktop; pidl
0x180023c3d  call    cs:__imp_ILGetSize
0x180023c43  lea     ebx, [r15+rax]
0x180023c47  xor     edi, edi
0x180023c49  test    ebp, ebp
0x180023c4b  jz      short loc_180023C60
0x180023c4d  mov     rcx, [r13+rdi*8+0]; pidl
0x180023c52  call    cs:__imp_ILGetSize
0x180023c58  add     ebx, eax
0x180023c5a  inc     edi
0x180023c5c  cmp     edi, ebp
0x180023c5e  jb      short loc_180023C4D
0x180023c60  mov     edx, ebx; dwBytes
0x180023c62  mov     ecx, 40h ; '@'; uFlags
0x180023c67  call    cs:__imp_GlobalAlloc
0x180023c6d  mov     rsi, rax
0x180023c70  test    rax, rax
0x180023c73  jz      short loc_180023CDF
0x180023c75  mov     [rax], ebp
0x180023c77  test    ebp, ebp
0x180023c79  jz      short loc_180023CDF
0x180023c7b  xor     r12d, r12d
0x180023c7e  lea     rcx, c_idlDesktop; pidl
0x180023c85  call    cs:__imp_ILGetSize
0x180023c8b  mov     ebx, eax
0x180023c8d  mov     [rsi+4], r15d
0x180023c91  mov     r8d, eax; Size
0x180023c94  mov     ecx, r15d
0x180023c97  add     rcx, rsi; void *
0x180023c9a  lea     rdx, c_idlDesktop; Src
0x180023ca1  call    memcpy_0
0x180023ca6  add     r15d, ebx
0x180023ca9  mov     rdi, [r13+r12*8+0]
0x180023cae  inc     r12d
0x180023cb1  mov     rcx, rdi; pidl
0x180023cb4  call    cs:__imp_ILGetSize
0x180023cba  mov     ebx, eax
0x180023cbc  mov     [rsi+r12*4+4], r15d
0x180023cc1  mov     r8d, eax; Size
0x180023cc4  mov     ecx, r15d
0x180023cc7  add     rcx, rsi; void *
0x180023cca  mov     rdx, rdi; Src
0x180023ccd  call    memcpy_0
0x180023cd2  add     r15d, ebx
0x180023cd5  cmp     r12d, ebp
0x180023cd8  jnz     short loc_180023CA9
0x180023cda  mov     [r14], rsi
0x180023cdd  jmp     short loc_180023CE7
0x180023cdf  mov     [r14], rsi
0x180023ce2  test    rsi, rsi
0x180023ce5  jz      short loc_180023CEB
0x180023ce7  xor     ebx, ebx
0x180023ce9  jmp     short loc_180023CF0
0x180023ceb  mov     ebx, 8007000Eh
0x180023cf0  mov     rcx, [rsp+58h+hdpa]; hdpa
0x180023cf5  test    rcx, rcx
0x180023cf8  jz      short loc_180023D1B
0x180023cfa  xor     r8d, r8d; pData
0x180023cfd  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@U_ITEMIDLIST_ABSOLUTE@@VCTContainer_PolicyCoTaskMem@@@@CAHPEAU_ITEMIDLIST_ABSOLUTE@@PEAX@Z; pfnCB
0x180023d04  call    cs:__imp_DPA_DestroyCallback
0x180023d0a  mov     [rsp+58h+hdpa], 0
0x180023d13  xor     ecx, ecx; hdpa
0x180023d15  call    cs:__imp_DPA_Destroy
0x180023d1b  mov     eax, ebx
0x180023d1d  mov     rbx, [rsp+58h+arg_18]
0x180023d22  add     rsp, 20h
0x180023d26  pop     r15
0x180023d28  pop     r14
0x180023d2a  pop     r13
0x180023d2c  pop     r12
0x180023d2e  pop     rdi
0x180023d2f  pop     rsi
0x180023d30  pop     rbp
0x180023d31  retn
```
