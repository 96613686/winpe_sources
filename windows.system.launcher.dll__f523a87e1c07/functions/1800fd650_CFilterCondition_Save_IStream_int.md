# CFilterCondition::Save(IStream *,int)

- ea: `0x1800fd650`
- end: `0x1800fd86c`
- name: `?Save@CFilterCondition@@UEAAJPEAUIStream@@H@Z`
- size: `540`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800fce3c`
- `0x1800fcf28`
- `0x1800fd650`
- `0x180111010`

## import_xrefs

- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1800fd6e7`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1800fd6e7`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1800fd755`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1800fd807`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1800fd755`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1800fd807`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800fd685`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800fd685`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1800fd706`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1800fd706`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1800fd6a4`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1800fd6c8`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1800fd6a4`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1800fd6c8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800fd71a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800fd792`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800fd71a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800fd792`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800fd741`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800fd7f3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800fd741`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800fd7f3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800fd7b1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800fd7b1`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_GetPtr` at `0x1800fd7cd`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_GetPtr` at `0x1800fd7cd`

## pseudocode

```c
__int64 __fastcall CFilterCondition::Save(CFilterCondition *this, struct IStream *a2, int a3)
{
  HRESULT v6; // ebx
  OLECHAR *v7; // r8
  struct IStream *v8; // rax
  const struct _GUID *const *v9; // rdx
  unsigned int v10; // r8d
  IStream *v11; // rsi
  unsigned int *v12; // rax
  IStream *v13; // rax
  struct IStream *v14; // rsi
  unsigned int v15; // r14d
  struct IUnknown *Ptr; // rax
  void *ppv; // [rsp+20h] [rbp-10h] BYREF
  unsigned int pv; // [rsp+78h] [rbp+48h] BYREF

  ppv = 0;
  v6 = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv);
  if ( v6 >= 0 )
  {
    v6 = PSPropertyBag_WriteBSTR((IPropertyBag *)ppv, L"Name", *((BSTR *)this + 3));
    if ( v6 < 0 )
      goto LABEL_24;
    v7 = (OLECHAR *)*((_QWORD *)this + 4);
    if ( v7 )
    {
      v6 = PSPropertyBag_WriteBSTR((IPropertyBag *)ppv, L"InFolder", v7);
      if ( v6 < 0 )
        goto LABEL_24;
    }
    v6 = PSPropertyBag_WritePropertyKey((IPropertyBag *)ppv, L"Key", (const PROPERTYKEY *const)this + 2);
    if ( v6 < 0 )
      goto LABEL_24;
    v6 = PSPropertyBag_WriteDWORD((IPropertyBag *)ppv, L"Type", *((_DWORD *)this + 15));
    if ( v6 < 0 )
      goto LABEL_24;
    v8 = SHCreateMemStream(0, 0);
    v11 = v8;
    if ( !v8 )
      goto LABEL_23;
    v6 = IUnknown_SaveKnownImplToStream(v8, v9, v10, *((struct IUnknown **)this + 8));
    if ( v6 >= 0 )
    {
      IStream_Reset(v11);
      v6 = PSPropertyBag_WriteStream((IPropertyBag *)ppv, L"Condition", v11);
    }
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v6 < 0 )
      goto LABEL_24;
    v12 = (unsigned int *)*((_QWORD *)this + 9);
    if ( v12 )
    {
      pv = *v12;
      if ( pv )
      {
        v13 = SHCreateMemStream(0, 0);
        v14 = v13;
        if ( v13 )
        {
          v15 = 0;
          v6 = IStream_Write(v13, &pv, 4u);
          if ( pv )
          {
            while ( v6 >= 0 )
            {
              Ptr = (struct IUnknown *)DPA_GetPtr(*((HDPA *)this + 9), v15++);
              v6 = IUnknown_SaveToStream(v14, a3, Ptr);
              if ( v15 >= pv )
                goto LABEL_17;
            }
          }
          else
          {
LABEL_17:
            if ( v6 >= 0 )
            {
              IStream_Reset(v14);
              v6 = PSPropertyBag_WriteStream((IPropertyBag *)ppv, L"Filters", v14);
            }
          }
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v14 + 16LL))(v14);
          if ( v6 < 0 )
            goto LABEL_24;
          goto LABEL_22;
        }
LABEL_23:
        v6 = -2147024882;
        goto LABEL_24;
      }
    }
    else
    {
      pv = 0;
    }
LABEL_22:
    v6 = IUnknown_SaveToStream(a2, a3, (struct IUnknown *)ppv);
LABEL_24:
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800fd650  mov     [rsp-28h+arg_0], rbx
0x1800fd655  mov     [rsp-28h+arg_8], rsi
0x1800fd65a  push    rbp
0x1800fd65b  push    rdi
0x1800fd65c  push    r12
0x1800fd65e  push    r14
0x1800fd660  push    r15
0x1800fd662  mov     rbp, rsp
0x1800fd665  sub     rsp, 30h
0x1800fd669  mov     r12, rdx
0x1800fd66c  mov     [rbp+ppv], 0
0x1800fd674  mov     rdi, rcx
0x1800fd677  lea     rdx, [rbp+ppv]; ppv
0x1800fd67b  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800fd682  mov     r15d, r8d
0x1800fd685  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800fd68b  mov     ebx, eax
0x1800fd68d  test    eax, eax
0x1800fd68f  js      loc_1800FD853
0x1800fd695  mov     r8, [rdi+18h]; value
0x1800fd699  lea     rdx, aName; "Name"
0x1800fd6a0  mov     rcx, [rbp+ppv]; propBag
0x1800fd6a4  call    cs:__imp_PSPropertyBag_WriteBSTR
0x1800fd6aa  mov     ebx, eax
0x1800fd6ac  test    eax, eax
0x1800fd6ae  js      loc_1800FD843
0x1800fd6b4  mov     r8, [rdi+20h]; value
0x1800fd6b8  test    r8, r8
0x1800fd6bb  jz      short loc_1800FD6D8
0x1800fd6bd  mov     rcx, [rbp+ppv]; propBag
0x1800fd6c1  lea     rdx, aInfolder; "InFolder"
0x1800fd6c8  call    cs:__imp_PSPropertyBag_WriteBSTR
0x1800fd6ce  mov     ebx, eax
0x1800fd6d0  test    eax, eax
0x1800fd6d2  js      loc_1800FD843
0x1800fd6d8  mov     rcx, [rbp+ppv]; propBag
0x1800fd6dc  lea     r8, [rdi+28h]; value
0x1800fd6e0  lea     rdx, aKey; "Key"
0x1800fd6e7  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x1800fd6ed  mov     ebx, eax
0x1800fd6ef  test    eax, eax
0x1800fd6f1  js      loc_1800FD843
0x1800fd6f7  mov     r8d, [rdi+3Ch]; value
0x1800fd6fb  lea     rdx, aType; "Type"
0x1800fd702  mov     rcx, [rbp+ppv]; propBag
0x1800fd706  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1800fd70c  mov     ebx, eax
0x1800fd70e  test    eax, eax
0x1800fd710  js      loc_1800FD843
0x1800fd716  xor     edx, edx; cbInit
0x1800fd718  xor     ecx, ecx; pInit
0x1800fd71a  call    cs:__imp_SHCreateMemStream
0x1800fd720  mov     rsi, rax
0x1800fd723  test    rax, rax
0x1800fd726  jz      loc_1800FD83E
0x1800fd72c  mov     r9, [rdi+40h]; struct IUnknown *
0x1800fd730  mov     rcx, rax; pstm
0x1800fd733  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x1800fd738  mov     ebx, eax
0x1800fd73a  test    eax, eax
0x1800fd73c  js      short loc_1800FD75D
0x1800fd73e  mov     rcx, rsi; pstm
0x1800fd741  call    cs:__imp_IStream_Reset
0x1800fd747  mov     rcx, [rbp+ppv]; propBag
0x1800fd74b  lea     rdx, aCondition; "Condition"
0x1800fd752  mov     r8, rsi; value
0x1800fd755  call    cs:__imp_PSPropertyBag_WriteStream
0x1800fd75b  mov     ebx, eax
0x1800fd75d  mov     rax, [rsi]
0x1800fd760  mov     rcx, rsi
0x1800fd763  mov     rax, [rax+10h]
0x1800fd767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd76c  test    ebx, ebx
0x1800fd76e  js      loc_1800FD843
0x1800fd774  mov     rax, [rdi+48h]
0x1800fd778  test    rax, rax
0x1800fd77b  jz      loc_1800FD824
0x1800fd781  mov     eax, [rax]
0x1800fd783  mov     [rbp+pv], eax
0x1800fd786  test    eax, eax
0x1800fd788  jz      loc_1800FD82B
0x1800fd78e  xor     edx, edx; cbInit
0x1800fd790  xor     ecx, ecx; pInit
0x1800fd792  call    cs:__imp_SHCreateMemStream
0x1800fd798  mov     rsi, rax
0x1800fd79b  test    rax, rax
0x1800fd79e  jz      loc_1800FD83E
0x1800fd7a4  mov     r8d, 4; cb
0x1800fd7aa  lea     rdx, [rbp+pv]; pv
0x1800fd7ae  mov     rcx, rax; pstm
0x1800fd7b1  call    cs:__imp_IStream_Write
0x1800fd7b7  xor     r14d, r14d
0x1800fd7ba  mov     ebx, eax
0x1800fd7bc  cmp     [rbp+pv], r14d
0x1800fd7c0  jbe     short loc_1800FD7EC
0x1800fd7c2  test    ebx, ebx
0x1800fd7c4  js      short loc_1800FD80F
0x1800fd7c6  mov     rcx, [rdi+48h]; hdpa
0x1800fd7ca  mov     edx, r14d; i
0x1800fd7cd  call    cs:__imp_DPA_GetPtr
0x1800fd7d3  mov     edx, r15d; int
0x1800fd7d6  mov     rcx, rsi; struct IStream *
0x1800fd7d9  mov     r8, rax; struct IUnknown *
0x1800fd7dc  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1800fd7e1  inc     r14d
0x1800fd7e4  mov     ebx, eax
0x1800fd7e6  cmp     r14d, [rbp+pv]
0x1800fd7ea  jb      short loc_1800FD7C2
0x1800fd7ec  test    ebx, ebx
0x1800fd7ee  js      short loc_1800FD80F
0x1800fd7f0  mov     rcx, rsi; pstm
0x1800fd7f3  call    cs:__imp_IStream_Reset
0x1800fd7f9  mov     rcx, [rbp+ppv]; propBag
0x1800fd7fd  lea     rdx, aFilters; "Filters"
0x1800fd804  mov     r8, rsi; value
0x1800fd807  call    cs:__imp_PSPropertyBag_WriteStream
0x1800fd80d  mov     ebx, eax
0x1800fd80f  mov     rax, [rsi]
0x1800fd812  mov     rcx, rsi
0x1800fd815  mov     rax, [rax+10h]
0x1800fd819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd81e  test    ebx, ebx
0x1800fd820  jns     short loc_1800FD82B
0x1800fd822  jmp     short loc_1800FD843
0x1800fd824  mov     [rbp+pv], 0
0x1800fd82b  mov     r8, [rbp+ppv]; struct IUnknown *
0x1800fd82f  mov     edx, r15d; int
0x1800fd832  mov     rcx, r12; struct IStream *
0x1800fd835  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1800fd83a  mov     ebx, eax
0x1800fd83c  jmp     short loc_1800FD843
0x1800fd83e  mov     ebx, 8007000Eh
0x1800fd843  mov     rcx, [rbp+ppv]
0x1800fd847  mov     rax, [rcx]
0x1800fd84a  mov     rax, [rax+10h]
0x1800fd84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd853  mov     rsi, [rsp+30h+arg_8]
0x1800fd858  mov     eax, ebx
0x1800fd85a  mov     rbx, [rsp+30h+arg_0]
0x1800fd85f  add     rsp, 30h
0x1800fd863  pop     r15
0x1800fd865  pop     r14
0x1800fd867  pop     r12
0x1800fd869  pop     rdi
0x1800fd86a  pop     rbp
0x1800fd86b  retn
```
