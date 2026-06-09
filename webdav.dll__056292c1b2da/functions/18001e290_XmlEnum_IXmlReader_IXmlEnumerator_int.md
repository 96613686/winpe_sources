# XmlEnum(IXmlReader *,IXmlEnumerator *,int)

- ea: `0x18001e290`
- end: `0x18001e4f6`
- name: `?XmlEnum@@YAJPEAUIXmlReader@@PEAVIXmlEnumerator@@H@Z`
- size: `614`
- prototype: `__int64 __fastcall(struct IXmlReader *, struct IXmlEnumerator *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001317c`
- `0x180013858`

## callees

- `0x18001e290`
- `0x18001e5e4`
- `0x180023010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001e33a`
- `iisutil!PuDbgPrint` at `0x18001e33a`

## string_xrefs

- `0x18001e319`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001e30b`: `XmlEnum`

## pseudocode

```c
__int64 __fastcall XmlEnum(struct IXmlReader *a1, struct IXmlEnumerator *a2, int a3)
{
  __int64 (__fastcall **v3)(struct IXmlEnumerator *, struct IXmlReader *); // rax
  int EndElementAtDepth; // esi
  int v7; // ebp
  int i; // eax
  int v9; // eax
  int v10; // eax
  int v11; // ecx
  struct IXmlReaderVtbl *lpVtbl; // rax
  int v14; // [rsp+68h] [rbp+10h] BYREF
  int v15; // [rsp+70h] [rbp+18h] BYREF
  int v16; // [rsp+78h] [rbp+20h] BYREF

  v15 = a3;
  v3 = *(__int64 (__fastcall ***)(struct IXmlEnumerator *, struct IXmlReader *))a2;
  v15 = 0;
  EndElementAtDepth = (*v3)(a2, a1);
  if ( EndElementAtDepth >= 0 )
  {
    v7 = 0;
    ((void (__fastcall *)(struct IXmlReader *))a1->lpVtbl->MoveToElement)(a1);
    for ( i = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a1->lpVtbl->GetNodeType)(a1, &v15);
          ;
          i = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a1->lpVtbl->Read)(a1, &v15) )
    {
      EndElementAtDepth = i;
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
          718,
          "XmlEnum",
          "hr = %08lx, nodeType = %lu\n",
          i,
          v15);
      if ( EndElementAtDepth == 1 )
      {
LABEL_43:
        EndElementAtDepth = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 88LL))(
                              a2,
                              a1);
        goto LABEL_44;
      }
      if ( EndElementAtDepth < 0 )
        goto LABEL_44;
      if ( v15 > 8 )
        break;
      switch ( v15 )
      {
        case 8:
          v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 48LL))(a2, a1);
          break;
        case 1:
          v10 = ((__int64 (__fastcall *)(struct IXmlReader *))a1->lpVtbl->IsEmptyElement)(a1);
          v11 = v7 + 1;
          if ( v10 )
            v11 = v7;
          v7 = v11;
          v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 8LL))(a2, a1);
          break;
        case 2:
          v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 16LL))(a2, a1);
          break;
        case 3:
          v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 24LL))(a2, a1);
          break;
        case 4:
          v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 32LL))(a2, a1);
          break;
        case 7:
          v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 40LL))(a2, a1);
          break;
        default:
          goto LABEL_26;
      }
LABEL_31:
      if ( !v7 || !v9 )
        goto LABEL_43;
      if ( v9 != 1 )
      {
        if ( v9 != 2 )
        {
          EndElementAtDepth = -2147024809;
          goto LABEL_44;
        }
        lpVtbl = a1->lpVtbl;
        v14 = 0;
        v16 = 0;
        EndElementAtDepth = ((__int64 (__fastcall *)(struct IXmlReader *, int *))lpVtbl->GetNodeType)(a1, &v14);
        if ( EndElementAtDepth < 0 )
          goto LABEL_44;
        if ( v14 == 1 && !((unsigned int (__fastcall *)(struct IXmlReader *))a1->lpVtbl->IsEmptyElement)(a1) )
        {
          EndElementAtDepth = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a1->lpVtbl->GetDepth)(a1, &v16);
          if ( EndElementAtDepth >= 0 )
            EndElementAtDepth = XmlFindEndElementAtDepth(a1, v16 + 1);
          if ( EndElementAtDepth < 0 )
            goto LABEL_44;
        }
      }
    }
    switch ( v15 )
    {
      case 10:
        v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 56LL))(a2, a1);
        goto LABEL_31;
      case 13:
        v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 64LL))(a2, a1);
        goto LABEL_31;
      case 15:
        --v7;
        v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 72LL))(a2, a1);
        goto LABEL_31;
      case 17:
        v9 = (*(__int64 (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 80LL))(a2, a1);
        goto LABEL_31;
    }
LABEL_26:
    v9 = 1;
    goto LABEL_31;
  }
LABEL_44:
  (*(void (__fastcall **)(struct IXmlEnumerator *, struct IXmlReader *))(*(_QWORD *)a2 + 96LL))(a2, a1);
  return (unsigned int)EndElementAtDepth;
}

```

## disassembly

```asm
0x18001e290  mov     [rsp+arg_0], rbx
0x18001e295  mov     [rsp+arg_10], r8d
0x18001e29a  push    rbp
0x18001e29b  push    rsi
0x18001e29c  push    rdi
0x18001e29d  sub     rsp, 40h
0x18001e2a1  mov     rax, [rdx]
0x18001e2a4  mov     rdi, rdx
0x18001e2a7  mov     rbx, rcx
0x18001e2aa  mov     [rsp+58h+arg_10], 0
0x18001e2b2  mov     rdx, rcx
0x18001e2b5  mov     rcx, rdi
0x18001e2b8  mov     rax, [rax]
0x18001e2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2c0  mov     esi, eax
0x18001e2c2  test    eax, eax
0x18001e2c4  js      loc_18001E4D5
0x18001e2ca  mov     rax, [rbx]
0x18001e2cd  xor     ebp, ebp
0x18001e2cf  mov     rcx, rbx
0x18001e2d2  mov     rax, [rax+58h]
0x18001e2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2db  mov     rax, [rbx]
0x18001e2de  mov     rax, [rax+38h]
0x18001e2e2  lea     rdx, [rsp+58h+arg_10]
0x18001e2e7  mov     rcx, rbx
0x18001e2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2ef  mov     esi, eax
0x18001e2f1  mov     eax, cs:g_dwDebugFlags
0x18001e2f7  test    al, 3
0x18001e2f9  setnz   cl
0x18001e2fc  bt      eax, 1Bh
0x18001e300  setb    al
0x18001e303  test    al, cl
0x18001e305  jz      short loc_18001E340
0x18001e307  mov     eax, [rsp+58h+arg_10]
0x18001e30b  lea     r9, aXmlenum; "XmlEnum"
0x18001e312  mov     rcx, cs:g_pDebug
0x18001e319  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001e320  mov     [rsp+58h+var_28], eax
0x18001e324  mov     r8d, 2CEh
0x18001e32a  lea     rax, aHr08lxNodetype; "hr = %08lx, nodeType = %lu\n"
0x18001e331  mov     [rsp+58h+var_30], esi
0x18001e335  mov     [rsp+58h+var_38], rax
0x18001e33a  call    cs:__imp_PuDbgPrint
0x18001e340  cmp     esi, 1
0x18001e343  jz      loc_18001E4C1
0x18001e349  test    esi, esi
0x18001e34b  js      loc_18001E4D5
0x18001e351  mov     ecx, [rsp+58h+arg_10]
0x18001e355  cmp     ecx, 8
0x18001e358  jg      short loc_18001E3CA
0x18001e35a  jz      short loc_18001E3C1
0x18001e35c  sub     ecx, 1
0x18001e35f  jz      short loc_18001E39C
0x18001e361  sub     ecx, 1
0x18001e364  jz      short loc_18001E393
0x18001e366  sub     ecx, 1
0x18001e369  jz      short loc_18001E38A
0x18001e36b  sub     ecx, 1
0x18001e36e  jz      short loc_18001E381
0x18001e370  cmp     ecx, 3
0x18001e373  jnz     short loc_18001E3DE
0x18001e375  mov     rax, [rdi]
0x18001e378  mov     rax, [rax+28h]
0x18001e37c  jmp     loc_18001E409
0x18001e381  mov     rax, [rdi]
0x18001e384  mov     rax, [rax+20h]
0x18001e388  jmp     short loc_18001E409
0x18001e38a  mov     rax, [rdi]
0x18001e38d  mov     rax, [rax+18h]
0x18001e391  jmp     short loc_18001E409
0x18001e393  mov     rax, [rdi]
0x18001e396  mov     rax, [rax+10h]
0x18001e39a  jmp     short loc_18001E409
0x18001e39c  mov     rax, [rbx]
0x18001e39f  mov     rcx, rbx
0x18001e3a2  mov     rax, [rax+0A0h]
0x18001e3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3ae  test    eax, eax
0x18001e3b0  lea     ecx, [rbp+1]
0x18001e3b3  mov     rax, [rdi]
0x18001e3b6  cmovnz  ecx, ebp
0x18001e3b9  mov     ebp, ecx
0x18001e3bb  mov     rax, [rax+8]
0x18001e3bf  jmp     short loc_18001E409
0x18001e3c1  mov     rax, [rdi]
0x18001e3c4  mov     rax, [rax+30h]
0x18001e3c8  jmp     short loc_18001E409
0x18001e3ca  cmp     ecx, 0Ah
0x18001e3cd  jz      short loc_18001E402
0x18001e3cf  cmp     ecx, 0Dh
0x18001e3d2  jz      short loc_18001E3F9
0x18001e3d4  cmp     ecx, 0Fh
0x18001e3d7  jz      short loc_18001E3EE
0x18001e3d9  cmp     ecx, 11h
0x18001e3dc  jz      short loc_18001E3E5
0x18001e3de  mov     eax, 1
0x18001e3e3  jmp     short loc_18001E414
0x18001e3e5  mov     rax, [rdi]
0x18001e3e8  mov     rax, [rax+50h]
0x18001e3ec  jmp     short loc_18001E409
0x18001e3ee  mov     rax, [rdi]
0x18001e3f1  dec     ebp
0x18001e3f3  mov     rax, [rax+48h]
0x18001e3f7  jmp     short loc_18001E409
0x18001e3f9  mov     rax, [rdi]
0x18001e3fc  mov     rax, [rax+40h]
0x18001e400  jmp     short loc_18001E409
0x18001e402  mov     rax, [rdi]
0x18001e405  mov     rax, [rax+38h]
0x18001e409  mov     rdx, rbx
0x18001e40c  mov     rcx, rdi
0x18001e40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e414  test    ebp, ebp
0x18001e416  jz      loc_18001E4C1
0x18001e41c  test    eax, eax
0x18001e41e  jz      loc_18001E4C1
0x18001e424  cmp     eax, 1
0x18001e427  jz      loc_18001E4AE
0x18001e42d  cmp     eax, 2
0x18001e430  jnz     loc_18001E4BA
0x18001e436  mov     rax, [rbx]
0x18001e439  lea     rdx, [rsp+58h+arg_8]
0x18001e43e  mov     rcx, rbx
0x18001e441  mov     [rsp+58h+arg_8], 0
0x18001e449  mov     [rsp+58h+arg_18], 0
0x18001e451  mov     rax, [rax+38h]
0x18001e455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e45a  mov     esi, eax
0x18001e45c  test    eax, eax
0x18001e45e  js      short loc_18001E4D5
0x18001e460  cmp     [rsp+58h+arg_8], 1
0x18001e465  jnz     short loc_18001E4AE
0x18001e467  mov     rax, [rbx]
0x18001e46a  mov     rcx, rbx
0x18001e46d  mov     rax, [rax+0A0h]
0x18001e474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e479  test    eax, eax
0x18001e47b  jnz     short loc_18001E4AE
0x18001e47d  mov     rax, [rbx]
0x18001e480  lea     rdx, [rsp+58h+arg_18]
0x18001e485  mov     rcx, rbx
0x18001e488  mov     rax, [rax+0C0h]
0x18001e48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e494  mov     esi, eax
0x18001e496  test    eax, eax
0x18001e498  js      short loc_18001E4AA
0x18001e49a  mov     edx, [rsp+58h+arg_18]
0x18001e49e  mov     rcx, rbx; struct IXmlReader *
0x18001e4a1  inc     edx; unsigned int
0x18001e4a3  call    ?XmlFindEndElementAtDepth@@YAJPEAUIXmlReader@@I@Z; XmlFindEndElementAtDepth(IXmlReader *,uint)
0x18001e4a8  mov     esi, eax
0x18001e4aa  test    esi, esi
0x18001e4ac  js      short loc_18001E4D5
0x18001e4ae  mov     rax, [rbx]
0x18001e4b1  mov     rax, [rax+30h]
0x18001e4b5  jmp     loc_18001E2E2
0x18001e4ba  mov     esi, 80070057h
0x18001e4bf  jmp     short loc_18001E4D5
0x18001e4c1  mov     rax, [rdi]
0x18001e4c4  mov     rdx, rbx
0x18001e4c7  mov     rcx, rdi
0x18001e4ca  mov     rax, [rax+58h]
0x18001e4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4d3  mov     esi, eax
0x18001e4d5  mov     rax, [rdi]
0x18001e4d8  mov     rdx, rbx
0x18001e4db  mov     rcx, rdi
0x18001e4de  mov     rax, [rax+60h]
0x18001e4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4e7  mov     rbx, [rsp+58h+arg_0]
0x18001e4ec  mov     eax, esi
0x18001e4ee  add     rsp, 40h
0x18001e4f2  pop     rdi
0x18001e4f3  pop     rsi
0x18001e4f4  pop     rbp
0x18001e4f5  retn
```
