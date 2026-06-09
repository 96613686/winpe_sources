# DELETE_VERB_HANDLER::DoDelete(DAV_DEPTH)

- ea: `0x180007710`
- end: `0x18000786a`
- name: `?DoDelete@DELETE_VERB_HANDLER@@AEAAJW4DAV_DEPTH@@@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007960`

## callees

- `0x180007710`
- `0x180007870`
- `0x18001a068`
- `0x18001b2cc`
- `0x18001b4dc`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007852`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007852`

## pseudocode

```c
__int64 __fastcall DELETE_VERB_HANDLER::DoDelete(__int64 a1, int a2)
{
  __int64 v3; // rcx
  int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  const unsigned __int16 *v11; // rdi
  unsigned __int16 *v12; // rsi
  struct IBaseFileSystem *v13; // r14
  __int64 v14; // rbx
  void *EffectiveToken; // rax
  __int64 v16; // rax
  int v18; // [rsp+40h] [rbp-29h] BYREF
  __int64 v19; // [rsp+48h] [rbp-21h]
  _QWORD v20[14]; // [rsp+50h] [rbp-19h] BYREF

  v18 = 0;
  v3 = *(_QWORD *)(a1 + 240);
  v19 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 8LL))(v3, -1);
  if ( v5 >= 0 )
  {
    v5 = AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)&v18, *(struct IHttpContext **)(a1 + 8));
    if ( v5 >= 0 )
    {
      v6 = *(_QWORD *)(a1 + 24);
      v7 = *(_QWORD *)(a1 + 8);
      v8 = *(_QWORD *)(v6 + 3328);
      v20[2] = v6 + 2240;
      v20[4] = a1 + 296;
      v20[5] = *(_QWORD *)(a1 + 128);
      v20[0] = &DAV_VDIR_OP_HELPER::`vftable';
      v20[1] = v7;
      v20[3] = v8;
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 160LL))(v7);
      v20[6] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      if ( a2 )
      {
        v11 = *(const unsigned __int16 **)(a1 + 184);
        v12 = *(unsigned __int16 **)(a1 + 72);
        v13 = *(struct IBaseFileSystem **)(a1 + 240);
        v14 = *(_QWORD *)(a1 + 24);
        EffectiveToken = GetEffectiveToken(*(struct IHttpContext **)(a1 + 8));
        v10 = DeleteVDirTree(
                EffectiveToken,
                (struct IVDirOperationHelper *)v20,
                (struct IIS_VDIR_CONFIG *)(v14 + 64),
                v13,
                v12,
                v11);
      }
      else
      {
        v10 = DELETE_VERB_HANDLER::DoDepth0Delete((DELETE_VERB_HANDLER *)a1, (struct IVDirOperationHelper *)v20);
      }
      v5 = v10;
    }
  }
  v16 = **(_QWORD **)(a1 + 240);
  if ( v5 < 0 )
    (*(void (**)(void))(v16 + 24))();
  else
    v5 = (*(__int64 (**)(void))(v16 + 16))();
  if ( v18 )
    RevertToSelf();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007710  push    rbp
0x180007712  push    rbx
0x180007713  push    rsi
0x180007714  push    rdi
0x180007715  push    r14
0x180007717  push    r15
0x180007719  lea     rbp, [rsp-2Fh]
0x18000771e  sub     rsp, 98h
0x180007725  mov     r15, rcx
0x180007728  mov     [rbp+57h+var_80], 0
0x18000772f  mov     rcx, [rcx+0F0h]
0x180007736  mov     edi, edx
0x180007738  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000773c  mov     [rbp+57h+var_78], 0
0x180007744  mov     rax, [rcx]
0x180007747  mov     rax, [rax+8]
0x18000774b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007750  mov     ebx, eax
0x180007752  test    eax, eax
0x180007754  js      loc_180007828
0x18000775a  mov     rdx, [r15+8]; struct IHttpContext *
0x18000775e  lea     rcx, [rbp+57h+var_80]; this
0x180007762  call    ?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z; AUTO_IMPERSONATE::Impersonate(IHttpContext *)
0x180007767  mov     ebx, eax
0x180007769  test    eax, eax
0x18000776b  js      loc_180007828
0x180007771  mov     rax, [r15+18h]
0x180007775  lea     r8, ??_7DAV_VDIR_OP_HELPER@@6B@; const DAV_VDIR_OP_HELPER::`vftable'
0x18000777c  mov     rcx, [r15+8]
0x180007780  mov     rdx, [rax+0D00h]
0x180007787  add     rax, 8C0h
0x18000778d  mov     [rbp+57h+var_60], rax
0x180007791  lea     rax, [r15+128h]
0x180007798  mov     [rbp+57h+var_50], rax
0x18000779c  mov     rax, [r15+80h]
0x1800077a3  mov     [rbp+57h+var_48], rax
0x1800077a7  mov     [rbp+57h+var_70], r8
0x1800077ab  mov     [rbp+57h+var_68], rcx
0x1800077af  mov     [rbp+57h+var_58], rdx
0x1800077b3  mov     rax, [rcx]
0x1800077b6  mov     rax, [rax+0A0h]
0x1800077bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077c2  mov     rdx, rax
0x1800077c5  mov     rcx, [rax]
0x1800077c8  mov     rax, [rcx+10h]
0x1800077cc  mov     rcx, rdx
0x1800077cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d4  mov     [rbp+57h+var_40], rax
0x1800077d8  test    edi, edi
0x1800077da  jnz     short loc_1800077EA
0x1800077dc  lea     rdx, [rbp+57h+var_70]; struct IVDirOperationHelper *
0x1800077e0  mov     rcx, r15; this
0x1800077e3  call    ?DoDepth0Delete@DELETE_VERB_HANDLER@@AEAAJPEAVIVDirOperationHelper@@@Z; DELETE_VERB_HANDLER::DoDepth0Delete(IVDirOperationHelper *)
0x1800077e8  jmp     short loc_180007826
0x1800077ea  mov     rcx, [r15+8]; struct IHttpContext *
0x1800077ee  mov     rdi, [r15+0B8h]
0x1800077f5  mov     rsi, [r15+48h]
0x1800077f9  mov     r14, [r15+0F0h]
0x180007800  mov     rbx, [r15+18h]
0x180007804  call    ?GetEffectiveToken@@YAPEAXPEAVIHttpContext@@@Z; GetEffectiveToken(IHttpContext *)
0x180007809  mov     r9, r14; struct IBaseFileSystem *
0x18000780c  mov     [rsp+0C0h+var_98], rdi; unsigned __int16 *
0x180007811  lea     r8, [rbx+40h]; struct IIS_VDIR_CONFIG *
0x180007815  mov     [rsp+0C0h+var_A0], rsi; unsigned __int16 *
0x18000781a  lea     rdx, [rbp+57h+var_70]; struct IVDirOperationHelper *
0x18000781e  mov     rcx, rax; void *
0x180007821  call    ?DeleteVDirTree@@YAJPEAXPEAVIVDirOperationHelper@@PEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEBG4K@Z; DeleteVDirTree(void *,IVDirOperationHelper *,IIS_VDIR_CONFIG *,IBaseFileSystem *,ushort const *,ushort const *,ulong)
0x180007826  mov     ebx, eax
0x180007828  mov     rcx, [r15+0F0h]
0x18000782f  mov     rax, [rcx]
0x180007832  test    ebx, ebx
0x180007834  js      short loc_180007843
0x180007836  mov     rax, [rax+10h]
0x18000783a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000783f  mov     ebx, eax
0x180007841  jmp     short loc_18000784C
0x180007843  mov     rax, [rax+18h]
0x180007847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000784c  cmp     [rbp+57h+var_80], 0
0x180007850  jz      short loc_180007858
0x180007852  call    cs:__imp_RevertToSelf
0x180007858  mov     eax, ebx
0x18000785a  add     rsp, 98h
0x180007861  pop     r15
0x180007863  pop     r14
0x180007865  pop     rdi
0x180007866  pop     rsi
0x180007867  pop     rbx
0x180007868  pop     rbp
0x180007869  retn
```
