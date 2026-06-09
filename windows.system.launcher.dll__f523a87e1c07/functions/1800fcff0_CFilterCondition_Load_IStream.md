# CFilterCondition::Load(IStream *)

- ea: `0x1800fcff0`
- end: `0x1800fd226`
- name: `?Load@CFilterCondition@@UEAAJPEAUIStream@@@Z`
- size: `566`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800f3be0`
- `0x1800fc670`
- `0x1800fcc80`
- `0x1800fcff0`
- `0x1800fd3b8`
- `0x180111010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800fd03a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800fd03a`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1800fd0e9`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1800fd180`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1800fd0e9`
- `PROPSYS!PSPropertyBag_ReadStream` at `0x1800fd180`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x1800fd0c2`
- `PROPSYS!PSPropertyBag_ReadPropertyKey` at `0x1800fd0c2`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x1800fd0a3`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x1800fd0a3`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1800fd06f`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1800fd08e`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1800fd06f`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1800fd08e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800fd0f9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800fd0f9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800fd19f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800fd19f`

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
0x1800fcff0  mov     [rsp-28h+arg_8], rbx
0x1800fcff5  push    rbp
0x1800fcff6  push    rsi
0x1800fcff7  push    rdi
0x1800fcff8  push    r14
0x1800fcffa  push    r15
0x1800fcffc  mov     rbp, rsp
0x1800fcfff  sub     rsp, 40h
0x1800fd003  cmp     qword ptr [rcx+18h], 0
0x1800fd008  mov     r15, rdx
0x1800fd00b  mov     rdi, rcx
0x1800fd00e  mov     ebx, 8000FFFFh
0x1800fd013  jnz     loc_1800FD213
0x1800fd019  lea     rsi, [rcx+40h]
0x1800fd01d  cmp     qword ptr [rsi], 0
0x1800fd021  jnz     loc_1800FD213
0x1800fd027  lea     rdx, [rbp+ppv]; ppv
0x1800fd02b  mov     [rbp+ppv], 0
0x1800fd033  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800fd03a  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800fd040  mov     ebx, eax
0x1800fd042  test    eax, eax
0x1800fd044  js      loc_1800FD213
0x1800fd04a  mov     rdx, [rbp+ppv]; struct IUnknown *
0x1800fd04e  mov     rcx, r15; struct IStream *
0x1800fd051  call    ?IUnknown_LoadFromStream@@YAJPEAUIStream@@PEAUIUnknown@@@Z; IUnknown_LoadFromStream(IStream *,IUnknown *)
0x1800fd056  mov     ebx, eax
0x1800fd058  test    eax, eax
0x1800fd05a  js      loc_1800FD203
0x1800fd060  mov     rcx, [rbp+ppv]; propBag
0x1800fd064  lea     r8, [rdi+18h]; value
0x1800fd068  lea     rdx, aName; "Name"
0x1800fd06f  call    cs:__imp_PSPropertyBag_ReadBSTR
0x1800fd075  mov     ebx, eax
0x1800fd077  test    eax, eax
0x1800fd079  js      loc_1800FD203
0x1800fd07f  mov     rcx, [rbp+ppv]; propBag
0x1800fd083  lea     r8, [rdi+20h]; value
0x1800fd087  lea     rdx, aInfolder; "InFolder"
0x1800fd08e  call    cs:__imp_PSPropertyBag_ReadBSTR
0x1800fd094  mov     rcx, [rbp+ppv]; propBag
0x1800fd098  lea     r8, [rdi+3Ch]; value
0x1800fd09c  lea     rdx, aType; "Type"
0x1800fd0a3  call    cs:__imp_PSPropertyBag_ReadInt
0x1800fd0a9  mov     ebx, eax
0x1800fd0ab  test    eax, eax
0x1800fd0ad  js      loc_1800FD203
0x1800fd0b3  mov     rcx, [rbp+ppv]; propBag
0x1800fd0b7  lea     r8, [rdi+28h]; value
0x1800fd0bb  lea     rdx, aKey; "Key"
0x1800fd0c2  call    cs:__imp_PSPropertyBag_ReadPropertyKey
0x1800fd0c8  mov     ebx, eax
0x1800fd0ca  test    eax, eax
0x1800fd0cc  js      loc_1800FD203
0x1800fd0d2  mov     rcx, [rbp+ppv]; propBag
0x1800fd0d6  lea     r8, [rbp+value]; value
0x1800fd0da  lea     rdx, aCondition; "Condition"
0x1800fd0e1  mov     [rbp+value], 0
0x1800fd0e9  call    cs:__imp_PSPropertyBag_ReadStream
0x1800fd0ef  mov     ebx, eax
0x1800fd0f1  test    eax, eax
0x1800fd0f3  js      short loc_1800FD161
0x1800fd0f5  mov     rcx, [rbp+value]; pstm
0x1800fd0f9  call    cs:__imp_IStream_Reset
0x1800fd0ff  mov     rcx, [rbp+value]; struct IStream *
0x1800fd103  lea     rax, [rbp+pv]
0x1800fd107  mov     [rsp+40h+var_20], rax; void **
0x1800fd10c  mov     qword ptr [rsi], 0
0x1800fd113  mov     [rbp+pv], 0
0x1800fd11b  call    ?IUnknown_LoadKnownImplFromStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IAEBU2@PEAPEAX@Z; IUnknown_LoadKnownImplFromStream(IStream *,_GUID const * const *,uint,_GUID const &,void * *)
0x1800fd120  mov     ebx, eax
0x1800fd122  test    eax, eax
0x1800fd124  js      short loc_1800FD151
0x1800fd126  mov     rcx, [rbp+pv]
0x1800fd12a  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x1800fd131  mov     r8, rsi
0x1800fd134  mov     rax, [rcx]
0x1800fd137  mov     rax, [rax]
0x1800fd13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd13f  mov     rcx, [rbp+pv]
0x1800fd143  mov     ebx, eax
0x1800fd145  mov     rax, [rcx]
0x1800fd148  mov     rax, [rax+10h]
0x1800fd14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd151  mov     rcx, [rbp+value]
0x1800fd155  mov     rax, [rcx]
0x1800fd158  mov     rax, [rax+10h]
0x1800fd15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd161  mov     [rbp+pstm], 0
0x1800fd169  test    ebx, ebx
0x1800fd16b  js      loc_1800FD203
0x1800fd171  mov     rcx, [rbp+ppv]; propBag
0x1800fd175  lea     r8, [rbp+pstm]; value
0x1800fd179  lea     rdx, aFilters; "Filters"
0x1800fd180  call    cs:__imp_PSPropertyBag_ReadStream
0x1800fd186  test    eax, eax
0x1800fd188  js      short loc_1800FD203
0x1800fd18a  mov     rcx, [rbp+pstm]; pstm
0x1800fd18e  lea     rdx, [rbp+pv]; pv
0x1800fd192  mov     r8d, 4; cb
0x1800fd198  mov     dword ptr [rbp+pv], 0
0x1800fd19f  call    cs:__imp_IStream_Read
0x1800fd1a5  xor     esi, esi
0x1800fd1a7  mov     ebx, eax
0x1800fd1a9  cmp     dword ptr [rbp+pv], esi
0x1800fd1ac  jbe     short loc_1800FD1F3
0x1800fd1ae  test    ebx, ebx
0x1800fd1b0  js      short loc_1800FD1F3
0x1800fd1b2  mov     rcx, [rbp+pstm]; struct IStream *
0x1800fd1b6  lea     r8, [rbp+var_8]; void **
0x1800fd1ba  mov     [rbp+var_8], 0
0x1800fd1c2  call    ?SHLoadFilterFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; SHLoadFilterFromStream(IStream *,_GUID const &,void * *)
0x1800fd1c7  mov     ebx, eax
0x1800fd1c9  test    eax, eax
0x1800fd1cb  js      short loc_1800FD1EC
0x1800fd1cd  mov     rdx, [rbp+var_8]; struct IUnknown *
0x1800fd1d1  lea     rcx, [rdi+8]; this
0x1800fd1d5  call    ?AddObject@CFilterCondition@@UEAAJPEAUIUnknown@@@Z; CFilterCondition::AddObject(IUnknown *)
0x1800fd1da  mov     rcx, [rbp+var_8]
0x1800fd1de  mov     ebx, eax
0x1800fd1e0  mov     rax, [rcx]
0x1800fd1e3  mov     rax, [rax+10h]
0x1800fd1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd1ec  inc     esi
0x1800fd1ee  cmp     esi, dword ptr [rbp+pv]
0x1800fd1f1  jb      short loc_1800FD1AE
0x1800fd1f3  mov     rcx, [rbp+pstm]
0x1800fd1f7  mov     rax, [rcx]
0x1800fd1fa  mov     rax, [rax+10h]
0x1800fd1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd203  mov     rcx, [rbp+ppv]
0x1800fd207  mov     rax, [rcx]
0x1800fd20a  mov     rax, [rax+10h]
0x1800fd20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd213  mov     eax, ebx
0x1800fd215  mov     rbx, [rsp+40h+arg_8]
0x1800fd21a  add     rsp, 40h
0x1800fd21e  pop     r15
0x1800fd220  pop     r14
0x1800fd222  pop     rdi
0x1800fd223  pop     rsi
0x1800fd224  pop     rbp
0x1800fd225  retn
```
