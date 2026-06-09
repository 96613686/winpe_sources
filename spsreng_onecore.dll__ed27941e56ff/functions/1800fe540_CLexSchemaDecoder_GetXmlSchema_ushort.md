# CLexSchemaDecoder::GetXmlSchema(ushort * *)

- ea: `0x1800fe540`
- end: `0x1800fe6a0`
- name: `?GetXmlSchema@CLexSchemaDecoder@@QEAAJPEAPEAG@Z`
- size: `352`
- prototype: `__int64 __fastcall(CLexSchemaDecoder *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800fd2b0`

## callees

- `0x180002db8`
- `0x1800034b0`
- `0x18000416c`
- `0x1800fe318`
- `0x1800fe414`
- `0x1800fe47c`
- `0x1800fe4a8`
- `0x1800fe540`
- `0x1800fea24`
- `0x1800feadc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800fe584`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800fe584`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLexSchemaDecoder::GetXmlSchema(CLexSchemaDecoder *this, unsigned __int16 **a2)
{
  HRESULT StreamOnHGlobal; // ebx
  const unsigned __int16 *v5; // rdx
  __int64 v6; // rdx
  unsigned int v7; // r8d
  struct IStream *v8; // rbx
  unsigned __int16 v10; // si
  LPSTREAM ppstm[2]; // [rsp+20h] [rbp-358h] BYREF
  unsigned __int16 v12[200]; // [rsp+30h] [rbp-348h] BYREF
  wchar_t Buffer[200]; // [rsp+1C0h] [rbp-1B8h] BYREF

  ppstm[0] = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
  *a2 = 0;
  if ( StreamOnHGlobal >= 0 )
  {
    v5 = (const unsigned __int16 *)*((_QWORD *)this + 1);
    if ( !v5 )
    {
      StreamOnHGlobal = -2147201023;
      goto LABEL_4;
    }
    StreamOnHGlobal = CLexSchemaDecoder::WriteString(ppstm[0], v5);
    if ( StreamOnHGlobal >= 0 )
      StreamOnHGlobal = CLexSchemaDecoder::CreateVisitTable(this);
  }
  v10 = 0;
  if ( StreamOnHGlobal >= 0 )
  {
    while ( v10 < *(_WORD *)this )
    {
      if ( *(_WORD *)(*((_QWORD *)this + 2) + 10LL * v10 + 4) == 0xFFFF )
        CLexSchemaDecoder::WriteNode(this, ppstm[0], v10);
      ++v10;
    }
  }
LABEL_4:
  CLexSchemaDecoder::DestroyVisitTable(this);
  if ( StreamOnHGlobal >= 0 )
  {
    v8 = ppstm[0];
    if ( CLexSchemaDecoder::ExtractRootName(*((const unsigned __int16 **)this + 1), v12, v7) >= 0
      && swprintf_s(Buffer, 0xC8u, L"</%s>", v12) > 0 )
    {
      CLexSchemaDecoder::WriteString(v8, Buffer);
    }
    StreamOnHGlobal = CLexSchemaDecoder::CopyStreamToString(ppstm[0], a2);
  }
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(ppstm, v6);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x1800fe540  mov     [rsp+arg_10], rbx
0x1800fe545  mov     [rsp+arg_18], rbp
0x1800fe54a  push    rsi
0x1800fe54b  push    rdi
0x1800fe54c  push    r14
0x1800fe54e  sub     rsp, 360h
0x1800fe555  mov     rax, cs:__security_cookie
0x1800fe55c  xor     rax, rsp
0x1800fe55f  mov     [rsp+378h+var_28], rax
0x1800fe567  mov     r14, rdx
0x1800fe56a  mov     rdi, rcx
0x1800fe56d  mov     [rsp+378h+ppstm], 0
0x1800fe576  lea     r8, [rsp+378h+ppstm]; ppstm
0x1800fe57b  mov     ebp, 1
0x1800fe580  mov     edx, ebp; fDeleteOnRelease
0x1800fe582  xor     ecx, ecx; hGlobal
0x1800fe584  call    cs:__imp_CreateStreamOnHGlobal
0x1800fe58a  mov     ebx, eax
0x1800fe58c  mov     qword ptr [r14], 0
0x1800fe593  test    eax, eax
0x1800fe595  js      loc_1800FE65F
0x1800fe59b  mov     rdx, [rdi+8]; unsigned __int16 *
0x1800fe59f  test    rdx, rdx
0x1800fe5a2  jnz     loc_1800FE645
0x1800fe5a8  mov     ebx, 80045001h
0x1800fe5ad  mov     rcx, rdi; this
0x1800fe5b0  call    ?DestroyVisitTable@CLexSchemaDecoder@@AEAAXXZ; CLexSchemaDecoder::DestroyVisitTable(void)
0x1800fe5b5  test    ebx, ebx
0x1800fe5b7  js      short loc_1800FE611
0x1800fe5b9  mov     rbx, [rsp+378h+ppstm]
0x1800fe5be  lea     rdx, [rsp+378h+var_348]; unsigned __int16 *
0x1800fe5c3  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800fe5c7  call    ?ExtractRootName@CLexSchemaDecoder@@CAJPEBGPEAGK@Z; CLexSchemaDecoder::ExtractRootName(ushort const *,ushort *,ulong)
0x1800fe5cc  test    eax, eax
0x1800fe5ce  js      short loc_1800FE602
0x1800fe5d0  lea     r9, [rsp+378h+var_348]
0x1800fe5d5  lea     r8, aS_1; "</%s>"
0x1800fe5dc  mov     edx, 0C8h; BufferCount
0x1800fe5e1  lea     rcx, [rsp+378h+Buffer]; Buffer
0x1800fe5e9  call    swprintf_s
0x1800fe5ee  test    eax, eax
0x1800fe5f0  jle     short loc_1800FE602
0x1800fe5f2  lea     rdx, [rsp+378h+Buffer]; unsigned __int16 *
0x1800fe5fa  mov     rcx, rbx; struct IStream *
0x1800fe5fd  call    ?WriteString@CLexSchemaDecoder@@CAJPEAUIStream@@PEBG@Z; CLexSchemaDecoder::WriteString(IStream *,ushort const *)
0x1800fe602  mov     rdx, r14; unsigned __int16 **
0x1800fe605  mov     rcx, [rsp+378h+ppstm]; struct IStream *
0x1800fe60a  call    ?CopyStreamToString@CLexSchemaDecoder@@CAJPEAUIStream@@PEAPEAG@Z; CLexSchemaDecoder::CopyStreamToString(IStream *,ushort * *)
0x1800fe60f  mov     ebx, eax
0x1800fe611  lea     rcx, [rsp+378h+ppstm]
0x1800fe616  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800fe61b  mov     eax, ebx
0x1800fe61d  mov     rcx, [rsp+378h+var_28]
0x1800fe625  xor     rcx, rsp; StackCookie
0x1800fe628  call    __security_check_cookie
0x1800fe62d  lea     r11, [rsp+378h+var_18]
0x1800fe635  mov     rbx, [r11+30h]
0x1800fe639  mov     rbp, [r11+38h]
0x1800fe63d  mov     rsp, r11
0x1800fe640  pop     r14
0x1800fe642  pop     rdi
0x1800fe643  pop     rsi
0x1800fe644  retn
0x1800fe645  mov     rcx, [rsp+378h+ppstm]; struct IStream *
0x1800fe64a  call    ?WriteString@CLexSchemaDecoder@@CAJPEAUIStream@@PEBG@Z; CLexSchemaDecoder::WriteString(IStream *,ushort const *)
0x1800fe64f  mov     ebx, eax
0x1800fe651  test    eax, eax
0x1800fe653  js      short loc_1800FE65F
0x1800fe655  mov     rcx, rdi; this
0x1800fe658  call    ?CreateVisitTable@CLexSchemaDecoder@@AEAAJXZ; CLexSchemaDecoder::CreateVisitTable(void)
0x1800fe65d  mov     ebx, eax
0x1800fe65f  xor     esi, esi
0x1800fe661  test    ebx, ebx
0x1800fe663  js      loc_1800FE5AD
0x1800fe669  cmp     si, [rdi]
0x1800fe66c  jnb     loc_1800FE5AD
0x1800fe672  movzx   eax, si
0x1800fe675  lea     rcx, [rax+rax*4]
0x1800fe679  mov     rax, [rdi+10h]
0x1800fe67d  mov     edx, 0FFFFh
0x1800fe682  cmp     [rax+rcx*2+4], dx
0x1800fe687  jnz     short loc_1800FE69A
0x1800fe689  movzx   r8d, si; unsigned __int16
0x1800fe68d  mov     rdx, [rsp+378h+ppstm]; struct IStream *
0x1800fe692  mov     rcx, rdi; this
0x1800fe695  call    ?WriteNode@CLexSchemaDecoder@@AEAAJPEAUIStream@@G@Z; CLexSchemaDecoder::WriteNode(IStream *,ushort)
0x1800fe69a  add     si, bp
0x1800fe69d  jmp     short loc_1800FE669
```
