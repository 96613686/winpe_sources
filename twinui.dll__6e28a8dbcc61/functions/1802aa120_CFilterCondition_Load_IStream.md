# CFilterCondition::Load(IStream *)

- ea: `0x1802aa120`
- end: `0x1802aa356`
- name: `?Load@CFilterCondition@@UEAAJPEAUIStream@@@Z`
- size: `566`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1802a7dd0`
- `0x1802a9990`
- `0x1802a9a04`
- `0x1802aa120`
- `0x1802aabac`
- `0x1803a3010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802aa16a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802aa16a`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1802aa219`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1802aa2b0`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1802aa219`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1802aa2b0`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x1802aa1f2`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x1802aa1f2`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x1802aa1d3`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x1802aa1d3`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1802aa19f`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1802aa1be`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1802aa19f`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1802aa1be`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802aa229`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802aa229`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1802aa2cf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1802aa2cf`

## pseudocode

```c
__int64 __fastcall CFilterCondition::Load(CFilterCondition *this, struct IStream *a2)
{
  HRESULT BSTR; // ebx
  _QWORD *v5; // rsi
  struct IStream *v6; // rcx
  const struct _GUID *const *v7; // rdx
  unsigned int v8; // r8d
  const struct _GUID *v9; // r9
  unsigned int v10; // esi
  const struct _GUID *v11; // rdx
  IStream *pstm; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v14; // [rsp+38h] [rbp-8h] BYREF
  void *pv; // [rsp+70h] [rbp+30h] BYREF
  void *ppv; // [rsp+80h] [rbp+40h] BYREF
  IStream *value; // [rsp+88h] [rbp+48h] BYREF

  BSTR = -2147418113;
  if ( !*((_QWORD *)this + 3) )
  {
    v5 = (_QWORD *)((char *)this + 64);
    if ( !*((_QWORD *)this + 8) )
    {
      ppv = 0;
      BSTR = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv);
      if ( BSTR >= 0 )
      {
        BSTR = IUnknown_LoadFromStream(a2, (struct IUnknown *)ppv);
        if ( BSTR >= 0 )
        {
          BSTR = PSPropertyBag_ReadBSTR((IPropertyBag *)ppv, L"Name", (BSTR *)this + 3);
          if ( BSTR >= 0 )
          {
            PSPropertyBag_ReadBSTR((IPropertyBag *)ppv, L"InFolder", (BSTR *)this + 4);
            BSTR = PSPropertyBag_ReadInt((IPropertyBag *)ppv, L"Type", (INT *)this + 15);
            if ( BSTR >= 0 )
            {
              BSTR = PSPropertyBag_ReadPropertyKey((IPropertyBag *)ppv, L"Key", (PROPERTYKEY *)this + 2);
              if ( BSTR >= 0 )
              {
                value = 0;
                BSTR = PSPropertyBag_ReadStream((IPropertyBag *)ppv, L"Condition", &value);
                if ( BSTR >= 0 )
                {
                  IStream_Reset(value);
                  v6 = value;
                  *v5 = 0;
                  pv = 0;
                  BSTR = IUnknown_LoadKnownImplFromStream(v6, v7, v8, v9, &pv);
                  if ( BSTR >= 0 )
                  {
                    BSTR = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))pv)(
                             pv,
                             &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                             v5);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)pv + 16LL))(pv);
                  }
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)value + 16LL))(value);
                }
                pstm = 0;
                if ( BSTR >= 0 && PSPropertyBag_ReadStream((IPropertyBag *)ppv, L"Filters", &pstm) >= 0 )
                {
                  LODWORD(pv) = 0;
                  v10 = 0;
                  for ( BSTR = IStream_Read(pstm, &pv, 4u); v10 < (unsigned int)pv; ++v10 )
                  {
                    if ( BSTR < 0 )
                      break;
                    v14 = 0;
                    BSTR = SHLoadFilterFromStream(pstm, v11, (void **)&v14);
                    if ( BSTR >= 0 )
                    {
                      BSTR = CFilterCondition::AddObject((CFilterCondition *)((char *)this + 8), v14);
                      ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
                    }
                  }
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
                }
              }
            }
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  return (unsigned int)BSTR;
}

```

## disassembly

```asm
0x1802aa120  mov     [rsp-28h+arg_8], rbx
0x1802aa125  push    rbp
0x1802aa126  push    rsi
0x1802aa127  push    rdi
0x1802aa128  push    r14
0x1802aa12a  push    r15
0x1802aa12c  mov     rbp, rsp
0x1802aa12f  sub     rsp, 40h
0x1802aa133  cmp     qword ptr [rcx+18h], 0
0x1802aa138  mov     r15, rdx
0x1802aa13b  mov     rdi, rcx
0x1802aa13e  mov     ebx, 8000FFFFh
0x1802aa143  jnz     loc_1802AA343
0x1802aa149  lea     rsi, [rcx+40h]
0x1802aa14d  cmp     qword ptr [rsi], 0
0x1802aa151  jnz     loc_1802AA343
0x1802aa157  lea     rdx, [rbp+ppv]; ppv
0x1802aa15b  mov     [rbp+ppv], 0
0x1802aa163  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1802aa16a  call    cs:__imp_PSCreateMemoryPropertyStore
0x1802aa170  mov     ebx, eax
0x1802aa172  test    eax, eax
0x1802aa174  js      loc_1802AA343
0x1802aa17a  mov     rdx, [rbp+ppv]; struct IUnknown *
0x1802aa17e  mov     rcx, r15; struct IStream *
0x1802aa181  call    ?IUnknown_LoadFromStream@@YAJPEAUIStream@@PEAUIUnknown@@@Z; IUnknown_LoadFromStream(IStream *,IUnknown *)
0x1802aa186  mov     ebx, eax
0x1802aa188  test    eax, eax
0x1802aa18a  js      loc_1802AA333
0x1802aa190  mov     rcx, [rbp+ppv]; propBag
0x1802aa194  lea     r8, [rdi+18h]; value
0x1802aa198  lea     rdx, propName; "Name"
0x1802aa19f  call    cs:__imp_PSPropertyBag_ReadBSTR
0x1802aa1a5  mov     ebx, eax
0x1802aa1a7  test    eax, eax
0x1802aa1a9  js      loc_1802AA333
0x1802aa1af  mov     rcx, [rbp+ppv]; propBag
0x1802aa1b3  lea     r8, [rdi+20h]; value
0x1802aa1b7  lea     rdx, aInfolder; "InFolder"
0x1802aa1be  call    cs:__imp_PSPropertyBag_ReadBSTR
0x1802aa1c4  mov     rcx, [rbp+ppv]; propBag
0x1802aa1c8  lea     r8, [rdi+3Ch]; value
0x1802aa1cc  lea     rdx, aType; "Type"
0x1802aa1d3  call    cs:__imp_PSPropertyBag_ReadInt
0x1802aa1d9  mov     ebx, eax
0x1802aa1db  test    eax, eax
0x1802aa1dd  js      loc_1802AA333
0x1802aa1e3  mov     rcx, [rbp+ppv]; propBag
0x1802aa1e7  lea     r8, [rdi+28h]; value
0x1802aa1eb  lea     rdx, aKey; "Key"
0x1802aa1f2  call    cs:__imp_PSPropertyBag_ReadPropertyKey
0x1802aa1f8  mov     ebx, eax
0x1802aa1fa  test    eax, eax
0x1802aa1fc  js      loc_1802AA333
0x1802aa202  mov     rcx, [rbp+ppv]; propBag
0x1802aa206  lea     r8, [rbp+value]; value
0x1802aa20a  lea     rdx, aCondition; "Condition"
0x1802aa211  mov     [rbp+value], 0
0x1802aa219  call    cs:__imp_PSPropertyBag_ReadStream
0x1802aa21f  mov     ebx, eax
0x1802aa221  test    eax, eax
0x1802aa223  js      short loc_1802AA291
0x1802aa225  mov     rcx, [rbp+value]; pstm
0x1802aa229  call    cs:__imp_IStream_Reset
0x1802aa22f  mov     rcx, [rbp+value]; struct IStream *
0x1802aa233  lea     rax, [rbp+pv]
0x1802aa237  mov     [rsp+40h+var_20], rax; void **
0x1802aa23c  mov     qword ptr [rsi], 0
0x1802aa243  mov     [rbp+pv], 0
0x1802aa24b  call    ?IUnknown_LoadKnownImplFromStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IAEBU2@PEAPEAX@Z; IUnknown_LoadKnownImplFromStream(IStream *,_GUID const * const *,uint,_GUID const &,void * *)
0x1802aa250  mov     ebx, eax
0x1802aa252  test    eax, eax
0x1802aa254  js      short loc_1802AA281
0x1802aa256  mov     rcx, [rbp+pv]
0x1802aa25a  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x1802aa261  mov     r8, rsi
0x1802aa264  mov     rax, [rcx]
0x1802aa267  mov     rax, [rax]
0x1802aa26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aa26f  mov     rcx, [rbp+pv]
0x1802aa273  mov     ebx, eax
0x1802aa275  mov     rax, [rcx]
0x1802aa278  mov     rax, [rax+10h]
0x1802aa27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aa281  mov     rcx, [rbp+value]
0x1802aa285  mov     rax, [rcx]
0x1802aa288  mov     rax, [rax+10h]
0x1802aa28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aa291  mov     [rbp+pstm], 0
0x1802aa299  test    ebx, ebx
0x1802aa29b  js      loc_1802AA333
0x1802aa2a1  mov     rcx, [rbp+ppv]; propBag
0x1802aa2a5  lea     r8, [rbp+pstm]; value
0x1802aa2a9  lea     rdx, aFilters; "Filters"
0x1802aa2b0  call    cs:__imp_PSPropertyBag_ReadStream
0x1802aa2b6  test    eax, eax
0x1802aa2b8  js      short loc_1802AA333
0x1802aa2ba  mov     rcx, [rbp+pstm]; pstm
0x1802aa2be  lea     rdx, [rbp+pv]; pv
0x1802aa2c2  mov     r8d, 4; cb
0x1802aa2c8  mov     dword ptr [rbp+pv], 0
0x1802aa2cf  call    cs:__imp_IStream_Read
0x1802aa2d5  xor     esi, esi
0x1802aa2d7  mov     ebx, eax
0x1802aa2d9  cmp     dword ptr [rbp+pv], esi
0x1802aa2dc  jbe     short loc_1802AA323
0x1802aa2de  test    ebx, ebx
0x1802aa2e0  js      short loc_1802AA323
0x1802aa2e2  mov     rcx, [rbp+pstm]; struct IStream *
0x1802aa2e6  lea     r8, [rbp+var_8]; void **
0x1802aa2ea  mov     [rbp+var_8], 0
0x1802aa2f2  call    ?SHLoadFilterFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; SHLoadFilterFromStream(IStream *,_GUID const &,void * *)
0x1802aa2f7  mov     ebx, eax
0x1802aa2f9  test    eax, eax
0x1802aa2fb  js      short loc_1802AA31C
0x1802aa2fd  mov     rdx, [rbp+var_8]; struct IUnknown *
0x1802aa301  lea     rcx, [rdi+8]; this
0x1802aa305  call    ?AddObject@CFilterCondition@@UEAAJPEAUIUnknown@@@Z; CFilterCondition::AddObject(IUnknown *)
0x1802aa30a  mov     rcx, [rbp+var_8]
0x1802aa30e  mov     ebx, eax
0x1802aa310  mov     rax, [rcx]
0x1802aa313  mov     rax, [rax+10h]
0x1802aa317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aa31c  inc     esi
0x1802aa31e  cmp     esi, dword ptr [rbp+pv]
0x1802aa321  jb      short loc_1802AA2DE
0x1802aa323  mov     rcx, [rbp+pstm]
0x1802aa327  mov     rax, [rcx]
0x1802aa32a  mov     rax, [rax+10h]
0x1802aa32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aa333  mov     rcx, [rbp+ppv]
0x1802aa337  mov     rax, [rcx]
0x1802aa33a  mov     rax, [rax+10h]
0x1802aa33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aa343  mov     eax, ebx
0x1802aa345  mov     rbx, [rsp+40h+arg_8]
0x1802aa34a  add     rsp, 40h
0x1802aa34e  pop     r15
0x1802aa350  pop     r14
0x1802aa352  pop     rdi
0x1802aa353  pop     rsi
0x1802aa354  pop     rbp
0x1802aa355  retn
```
