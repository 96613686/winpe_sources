# CFilterCondition::Save(IStream *,int)

- ea: `0x180428ce0`
- end: `0x180428f5c`
- name: `?Save@CFilterCondition@@UEAAJPEAUIStream@@H@Z`
- size: `636`
- prototype: `int(CFilterCondition *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18003c520`
- `0x180166ce8`
- `0x180166ecc`
- `0x1803b1f60`
- `0x180428ce0`
- `0x18067d010`

## import_xrefs

- `PROPSYS!PSPropertyBag_WriteStream` at `0x180428e23`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x180428eec`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x180428e23`
- `PROPSYS!PSPropertyBag_WriteStream` at `0x180428eec`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180428db5`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180428db5`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x180428d90`
- `PROPSYS!PSPropertyBag_WritePropertyKey` at `0x180428d90`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180428d41`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180428d6b`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180428d41`
- `PROPSYS!PSPropertyBag_WriteBSTR` at `0x180428d6b`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180428d1c`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180428d1c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180428e09`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180428ed2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180428e09`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180428ed2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180428e8b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180428e8b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180428dcf`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180428e66`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180428dcf`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180428e66`

## pseudocode

```c
__int64 __fastcall CFilterCondition::Save(CFilterCondition *this, struct IStream *a2, int a3)
{
  HRESULT v6; // ebx
  OLECHAR *v7; // r8
  struct IStream *v8; // rax
  IStream *v9; // rdi
  unsigned int *v10; // rax
  IStream *v11; // rax
  struct IStream *v12; // rdi
  unsigned int v13; // r14d
  struct IUnknown *Ptr; // rax
  void *ppv; // [rsp+20h] [rbp-20h] BYREF
  unsigned int pv; // [rsp+28h] [rbp-18h] BYREF

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
    v9 = v8;
    if ( !v8 )
      goto LABEL_23;
    v6 = IUnknown_SaveKnownImplToStream(
           v8,
           (const struct _GUID *const *)&off_18068F0B0,
           3u,
           *((struct IUnknown **)this + 8));
    if ( v6 >= 0 )
    {
      IStream_Reset(v9);
      v6 = PSPropertyBag_WriteStream((IPropertyBag *)ppv, L"Condition", v9);
    }
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v6 < 0 )
      goto LABEL_24;
    v10 = (unsigned int *)*((_QWORD *)this + 9);
    if ( v10 )
    {
      pv = *v10;
      if ( pv )
      {
        v11 = SHCreateMemStream(0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = 0;
          v6 = IStream_Write(v11, &pv, 4u);
          if ( pv )
          {
            while ( v6 >= 0 )
            {
              Ptr = (struct IUnknown *)DPA_GetPtr(*((HDPA *)this + 9), v13++);
              v6 = IUnknown_SaveToStream(v12, a3, Ptr);
              if ( v13 >= pv )
                goto LABEL_17;
            }
          }
          else
          {
LABEL_17:
            if ( v6 >= 0 )
            {
              IStream_Reset(v12);
              v6 = PSPropertyBag_WriteStream((IPropertyBag *)ppv, L"Filters", v12);
            }
          }
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v12 + 16LL))(v12);
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
0x180428ce0  push    rbp
0x180428ce2  push    rbx
0x180428ce3  push    rsi
0x180428ce4  push    rdi
0x180428ce5  push    r12
0x180428ce7  push    r14
0x180428ce9  push    r15
0x180428ceb  mov     rbp, rsp
0x180428cee  sub     rsp, 40h
0x180428cf2  mov     rax, cs:__security_cookie
0x180428cf9  xor     rax, rsp
0x180428cfc  mov     [rbp+var_10], rax
0x180428d00  mov     r12, rdx
0x180428d03  mov     [rbp+ppv], 0
0x180428d0b  mov     rsi, rcx
0x180428d0e  lea     rdx, [rbp+ppv]; ppv
0x180428d12  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180428d19  mov     r15d, r8d
0x180428d1c  call    cs:__imp_PSCreateMemoryPropertyStore
0x180428d23  nop     dword ptr [rax+rax+00h]
0x180428d28  mov     ebx, eax
0x180428d2a  test    eax, eax
0x180428d2c  js      loc_180428F3E
0x180428d32  mov     r8, [rsi+18h]; value
0x180428d36  lea     rdx, aName; "Name"
0x180428d3d  mov     rcx, [rbp+ppv]; propBag
0x180428d41  call    cs:__imp_PSPropertyBag_WriteBSTR
0x180428d48  nop     dword ptr [rax+rax+00h]
0x180428d4d  mov     ebx, eax
0x180428d4f  test    eax, eax
0x180428d51  js      loc_180428F2E
0x180428d57  mov     r8, [rsi+20h]; value
0x180428d5b  test    r8, r8
0x180428d5e  jz      short loc_180428D81
0x180428d60  mov     rcx, [rbp+ppv]; propBag
0x180428d64  lea     rdx, aInfolder; "InFolder"
0x180428d6b  call    cs:__imp_PSPropertyBag_WriteBSTR
0x180428d72  nop     dword ptr [rax+rax+00h]
0x180428d77  mov     ebx, eax
0x180428d79  test    eax, eax
0x180428d7b  js      loc_180428F2E
0x180428d81  mov     rcx, [rbp+ppv]; propBag
0x180428d85  lea     r8, [rsi+28h]; value
0x180428d89  lea     rdx, aKey; "Key"
0x180428d90  call    cs:__imp_PSPropertyBag_WritePropertyKey
0x180428d97  nop     dword ptr [rax+rax+00h]
0x180428d9c  mov     ebx, eax
0x180428d9e  test    eax, eax
0x180428da0  js      loc_180428F2E
0x180428da6  mov     r8d, [rsi+3Ch]; value
0x180428daa  lea     rdx, aType_1; "Type"
0x180428db1  mov     rcx, [rbp+ppv]; propBag
0x180428db5  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180428dbc  nop     dword ptr [rax+rax+00h]
0x180428dc1  mov     ebx, eax
0x180428dc3  test    eax, eax
0x180428dc5  js      loc_180428F2E
0x180428dcb  xor     edx, edx; cbInit
0x180428dcd  xor     ecx, ecx; pInit
0x180428dcf  call    cs:__imp_SHCreateMemStream
0x180428dd6  nop     dword ptr [rax+rax+00h]
0x180428ddb  mov     rdi, rax
0x180428dde  test    rax, rax
0x180428de1  jz      loc_180428F29
0x180428de7  mov     r9, [rsi+40h]; struct IUnknown *
0x180428deb  lea     rdx, off_18068F0B0; struct _GUID **
0x180428df2  mov     r8d, 3; unsigned int
0x180428df8  mov     rcx, rax; pstm
0x180428dfb  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x180428e00  mov     ebx, eax
0x180428e02  test    eax, eax
0x180428e04  js      short loc_180428E31
0x180428e06  mov     rcx, rdi; pstm
0x180428e09  call    cs:__imp_IStream_Reset
0x180428e10  nop     dword ptr [rax+rax+00h]
0x180428e15  mov     rcx, [rbp+ppv]; propBag
0x180428e19  lea     rdx, aCondition; "Condition"
0x180428e20  mov     r8, rdi; value
0x180428e23  call    cs:__imp_PSPropertyBag_WriteStream
0x180428e2a  nop     dword ptr [rax+rax+00h]
0x180428e2f  mov     ebx, eax
0x180428e31  mov     rax, [rdi]
0x180428e34  mov     rcx, rdi
0x180428e37  mov     rax, [rax+10h]
0x180428e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180428e40  test    ebx, ebx
0x180428e42  js      loc_180428F2E
0x180428e48  mov     rax, [rsi+48h]
0x180428e4c  test    rax, rax
0x180428e4f  jz      loc_180428F0F
0x180428e55  mov     eax, [rax]
0x180428e57  mov     [rbp+pv], eax
0x180428e5a  test    eax, eax
0x180428e5c  jz      loc_180428F16
0x180428e62  xor     edx, edx; cbInit
0x180428e64  xor     ecx, ecx; pInit
0x180428e66  call    cs:__imp_SHCreateMemStream
0x180428e6d  nop     dword ptr [rax+rax+00h]
0x180428e72  mov     rdi, rax
0x180428e75  test    rax, rax
0x180428e78  jz      loc_180428F29
0x180428e7e  mov     r8d, 4; cb
0x180428e84  lea     rdx, [rbp+pv]; pv
0x180428e88  mov     rcx, rax; pstm
0x180428e8b  call    cs:__imp_IStream_Write
0x180428e92  nop     dword ptr [rax+rax+00h]
0x180428e97  xor     r14d, r14d
0x180428e9a  mov     ebx, eax
0x180428e9c  cmp     [rbp+pv], r14d
0x180428ea0  jbe     short loc_180428ECB
0x180428ea2  test    ebx, ebx
0x180428ea4  js      short loc_180428EFA
0x180428ea6  mov     rcx, [rsi+48h]; hdpa
0x180428eaa  mov     edx, r14d; i
0x180428ead  call    DPA_GetPtr
0x180428eb2  mov     r8, rax; struct IUnknown *
0x180428eb5  mov     edx, r15d; int
0x180428eb8  mov     rcx, rdi; struct IStream *
0x180428ebb  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x180428ec0  inc     r14d
0x180428ec3  mov     ebx, eax
0x180428ec5  cmp     r14d, [rbp+pv]
0x180428ec9  jb      short loc_180428EA2
0x180428ecb  test    ebx, ebx
0x180428ecd  js      short loc_180428EFA
0x180428ecf  mov     rcx, rdi; pstm
0x180428ed2  call    cs:__imp_IStream_Reset
0x180428ed9  nop     dword ptr [rax+rax+00h]
0x180428ede  mov     rcx, [rbp+ppv]; propBag
0x180428ee2  lea     rdx, aFilters; "Filters"
0x180428ee9  mov     r8, rdi; value
0x180428eec  call    cs:__imp_PSPropertyBag_WriteStream
0x180428ef3  nop     dword ptr [rax+rax+00h]
0x180428ef8  mov     ebx, eax
0x180428efa  mov     rax, [rdi]
0x180428efd  mov     rcx, rdi
0x180428f00  mov     rax, [rax+10h]
0x180428f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180428f09  test    ebx, ebx
0x180428f0b  jns     short loc_180428F16
0x180428f0d  jmp     short loc_180428F2E
0x180428f0f  mov     [rbp+pv], 0
0x180428f16  mov     r8, [rbp+ppv]; struct IUnknown *
0x180428f1a  mov     edx, r15d; int
0x180428f1d  mov     rcx, r12; struct IStream *
0x180428f20  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x180428f25  mov     ebx, eax
0x180428f27  jmp     short loc_180428F2E
0x180428f29  mov     ebx, 8007000Eh
0x180428f2e  mov     rcx, [rbp+ppv]
0x180428f32  mov     rax, [rcx]
0x180428f35  mov     rax, [rax+10h]
0x180428f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180428f3e  mov     eax, ebx
0x180428f40  mov     rcx, [rbp+var_10]
0x180428f44  xor     rcx, rsp; StackCookie
0x180428f47  call    __security_check_cookie
0x180428f4c  add     rsp, 40h
0x180428f50  pop     r15
0x180428f52  pop     r14
0x180428f54  pop     r12
0x180428f56  pop     rdi
0x180428f57  pop     rsi
0x180428f58  pop     rbx
0x180428f59  pop     rbp
0x180428f5a  retn
```
