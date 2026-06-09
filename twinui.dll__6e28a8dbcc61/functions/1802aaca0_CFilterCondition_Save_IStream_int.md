# CFilterCondition::Save(IStream *,int)

- ea: `0x1802aaca0`
- end: `0x1802aaebc`
- name: `?Save@CFilterCondition@@UEAAJPEAUIStream@@H@Z`
- size: `540`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800b23e0`
- `0x1802a9b30`
- `0x1802a9c1c`
- `0x1802aaca0`
- `0x1803a3010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802aacd5`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1802aacd5`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1802aada5`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1802aae57`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1802aada5`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x1802aae57`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1802aad56`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1802aad56`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1802aad37`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x1802aad37`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1802aacf4`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1802aad18`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1802aacf4`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x1802aad18`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802aad91`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802aae43`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802aad91`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1802aae43`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1802aae01`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1802aae01`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1802aad6a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1802aade2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1802aad6a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1802aade2`

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
              Ptr = (struct IUnknown *)g_pfn_DPA_GetPtr(*((HDPA *)this + 9), v15++);
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
0x1802aaca0  mov     [rsp-28h+arg_0], rbx
0x1802aaca5  mov     [rsp-28h+arg_8], rsi
0x1802aacaa  push    rbp
0x1802aacab  push    rdi
0x1802aacac  push    r12
0x1802aacae  push    r14
0x1802aacb0  push    r15
0x1802aacb2  mov     rbp, rsp
0x1802aacb5  sub     rsp, 30h
0x1802aacb9  mov     r12, rdx
0x1802aacbc  mov     [rbp+ppv], 0
0x1802aacc4  mov     rdi, rcx
0x1802aacc7  lea     rdx, [rbp+ppv]; ppv
0x1802aaccb  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1802aacd2  mov     r15d, r8d
0x1802aacd5  call    cs:__imp_PSCreateMemoryPropertyStore
0x1802aacdb  mov     ebx, eax
0x1802aacdd  test    eax, eax
0x1802aacdf  js      loc_1802AAEA3
0x1802aace5  mov     r8, [rdi+18h]; value
0x1802aace9  lea     rdx, propName; "Name"
0x1802aacf0  mov     rcx, [rbp+ppv]; propBag
0x1802aacf4  call    cs:__imp_PSPropertyBag_WriteBSTR
0x1802aacfa  mov     ebx, eax
0x1802aacfc  test    eax, eax
0x1802aacfe  js      loc_1802AAE93
0x1802aad04  mov     r8, [rdi+20h]; value
0x1802aad08  test    r8, r8
0x1802aad0b  jz      short loc_1802AAD28
0x1802aad0d  mov     rcx, [rbp+ppv]; propBag
0x1802aad11  lea     rdx, aInfolder; "InFolder"
0x1802aad18  call    cs:__imp_PSPropertyBag_WriteBSTR
0x1802aad1e  mov     ebx, eax
0x1802aad20  test    eax, eax
0x1802aad22  js      loc_1802AAE93
0x1802aad28  mov     rcx, [rbp+ppv]; propBag
0x1802aad2c  lea     r8, [rdi+28h]; value
0x1802aad30  lea     rdx, aKey; "Key"
0x1802aad37  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x1802aad3d  mov     ebx, eax
0x1802aad3f  test    eax, eax
0x1802aad41  js      loc_1802AAE93
0x1802aad47  mov     r8d, [rdi+3Ch]; value
0x1802aad4b  lea     rdx, aType; "Type"
0x1802aad52  mov     rcx, [rbp+ppv]; propBag
0x1802aad56  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1802aad5c  mov     ebx, eax
0x1802aad5e  test    eax, eax
0x1802aad60  js      loc_1802AAE93
0x1802aad66  xor     edx, edx; cbInit
0x1802aad68  xor     ecx, ecx; pInit
0x1802aad6a  call    cs:__imp_SHCreateMemStream
0x1802aad70  mov     rsi, rax
0x1802aad73  test    rax, rax
0x1802aad76  jz      loc_1802AAE8E
0x1802aad7c  mov     r9, [rdi+40h]; struct IUnknown *
0x1802aad80  mov     rcx, rax; pstm
0x1802aad83  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x1802aad88  mov     ebx, eax
0x1802aad8a  test    eax, eax
0x1802aad8c  js      short loc_1802AADAD
0x1802aad8e  mov     rcx, rsi; pstm
0x1802aad91  call    cs:__imp_IStream_Reset
0x1802aad97  mov     rcx, [rbp+ppv]; propBag
0x1802aad9b  lea     rdx, aCondition; "Condition"
0x1802aada2  mov     r8, rsi; value
0x1802aada5  call    cs:__imp_PSPropertyBag_WriteStream
0x1802aadab  mov     ebx, eax
0x1802aadad  mov     rax, [rsi]
0x1802aadb0  mov     rcx, rsi
0x1802aadb3  mov     rax, [rax+10h]
0x1802aadb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aadbc  test    ebx, ebx
0x1802aadbe  js      loc_1802AAE93
0x1802aadc4  mov     rax, [rdi+48h]
0x1802aadc8  test    rax, rax
0x1802aadcb  jz      loc_1802AAE74
0x1802aadd1  mov     eax, [rax]
0x1802aadd3  mov     [rbp+pv], eax
0x1802aadd6  test    eax, eax
0x1802aadd8  jz      loc_1802AAE7B
0x1802aadde  xor     edx, edx; cbInit
0x1802aade0  xor     ecx, ecx; pInit
0x1802aade2  call    cs:__imp_SHCreateMemStream
0x1802aade8  mov     rsi, rax
0x1802aadeb  test    rax, rax
0x1802aadee  jz      loc_1802AAE8E
0x1802aadf4  mov     r8d, 4; cb
0x1802aadfa  lea     rdx, [rbp+pv]; pv
0x1802aadfe  mov     rcx, rax; pstm
0x1802aae01  call    cs:__imp_IStream_Write
0x1802aae07  xor     r14d, r14d
0x1802aae0a  mov     ebx, eax
0x1802aae0c  cmp     [rbp+pv], r14d
0x1802aae10  jbe     short loc_1802AAE3C
0x1802aae12  test    ebx, ebx
0x1802aae14  js      short loc_1802AAE5F
0x1802aae16  mov     rcx, [rdi+48h]; hdpa
0x1802aae1a  mov     edx, r14d; i
0x1802aae1d  call    cs:g_pfn_DPA_GetPtr
0x1802aae23  mov     edx, r15d; int
0x1802aae26  mov     rcx, rsi; struct IStream *
0x1802aae29  mov     r8, rax; struct IUnknown *
0x1802aae2c  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1802aae31  inc     r14d
0x1802aae34  mov     ebx, eax
0x1802aae36  cmp     r14d, [rbp+pv]
0x1802aae3a  jb      short loc_1802AAE12
0x1802aae3c  test    ebx, ebx
0x1802aae3e  js      short loc_1802AAE5F
0x1802aae40  mov     rcx, rsi; pstm
0x1802aae43  call    cs:__imp_IStream_Reset
0x1802aae49  mov     rcx, [rbp+ppv]; propBag
0x1802aae4d  lea     rdx, aFilters; "Filters"
0x1802aae54  mov     r8, rsi; value
0x1802aae57  call    cs:__imp_PSPropertyBag_WriteStream
0x1802aae5d  mov     ebx, eax
0x1802aae5f  mov     rax, [rsi]
0x1802aae62  mov     rcx, rsi
0x1802aae65  mov     rax, [rax+10h]
0x1802aae69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aae6e  test    ebx, ebx
0x1802aae70  jns     short loc_1802AAE7B
0x1802aae72  jmp     short loc_1802AAE93
0x1802aae74  mov     [rbp+pv], 0
0x1802aae7b  mov     r8, [rbp+ppv]; struct IUnknown *
0x1802aae7f  mov     edx, r15d; int
0x1802aae82  mov     rcx, r12; struct IStream *
0x1802aae85  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1802aae8a  mov     ebx, eax
0x1802aae8c  jmp     short loc_1802AAE93
0x1802aae8e  mov     ebx, 8007000Eh
0x1802aae93  mov     rcx, [rbp+ppv]
0x1802aae97  mov     rax, [rcx]
0x1802aae9a  mov     rax, [rax+10h]
0x1802aae9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802aaea3  mov     rsi, [rsp+30h+arg_8]
0x1802aaea8  mov     eax, ebx
0x1802aaeaa  mov     rbx, [rsp+30h+arg_0]
0x1802aaeaf  add     rsp, 30h
0x1802aaeb3  pop     r15
0x1802aaeb5  pop     r14
0x1802aaeb7  pop     r12
0x1802aaeb9  pop     rdi
0x1802aaeba  pop     rbp
0x1802aaebb  retn
```
