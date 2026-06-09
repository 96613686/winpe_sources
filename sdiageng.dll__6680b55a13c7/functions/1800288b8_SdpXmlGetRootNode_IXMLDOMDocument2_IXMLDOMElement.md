# SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)

- ea: `0x1800288b8`
- end: `0x180028981`
- name: `?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMElement **)`
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800034c4`
- `0x180016630`
- `0x180017c90`
- `0x18001955c`
- `0x18001c224`
- `0x18001ee38`
- `0x18001f844`
- `0x180022570`
- `0x180027ea4`
- `0x18002827c`
- `0x18002848c`
- `0x1800286a4`
- `0x1800291e0`

## callees

- `0x180026fa0`
- `0x1800288b8`
- `0x18002a010`

## string_xrefs

- `0x18002894d`: `SdpXmlGetRootNode`

## pseudocode

```c
__int64 __fastcall SdpXmlGetRootNode(struct IXMLDOMDocument2 *a1, struct IXMLDOMElement **a2)
{
  int v3; // r9d
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  int v6; // eax
  struct IXMLDOMElement v7; // rax
  struct IXMLDOMElement *v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, struct IXMLDOMElement **))a1->lpVtbl->get_documentElement)(
             a1,
             &v9);
      v5 = v6;
      if ( v6 >= 0 )
      {
        if ( v6 != 1 && v9 )
        {
          v7.lpVtbl = v9->lpVtbl;
          *a2 = v9;
          ((void (*)(void))v7.lpVtbl->AddRef)();
          goto LABEL_12;
        }
        v5 = -2147467259;
        v4 = 744;
        v3 = -2147467259;
      }
      else
      {
        v3 = v6;
        v4 = 743;
      }
    }
    else
    {
      v3 = -2147024809;
      v4 = 740;
      v5 = -2147024809;
    }
  }
  else
  {
    v3 = -2147024809;
    v4 = 739;
    v5 = -2147024809;
  }
  SdpDebugTrace(1u, L"SdpXmlGetRootNode", v4, v3);
LABEL_12:
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v9->lpVtbl->Release)(v9);
  return v5;
}

```

## disassembly

```asm
0x1800288b8  mov     [rsp+arg_8], rbx
0x1800288bd  push    rdi
0x1800288be  sub     rsp, 20h
0x1800288c2  mov     [rsp+28h+arg_0], 0
0x1800288cb  mov     rdi, rdx
0x1800288ce  test    rcx, rcx
0x1800288d1  jnz     short loc_1800288E4
0x1800288d3  mov     r9d, 80070057h
0x1800288d9  mov     r8d, 2E3h
0x1800288df  mov     ebx, r9d
0x1800288e2  jmp     short loc_18002894D
0x1800288e4  test    rdi, rdi
0x1800288e7  jnz     short loc_1800288FA
0x1800288e9  mov     r9d, 80070057h
0x1800288ef  mov     r8d, 2E4h
0x1800288f5  mov     ebx, r9d
0x1800288f8  jmp     short loc_18002894D
0x1800288fa  mov     rax, [rcx]
0x1800288fd  lea     rdx, [rsp+28h+arg_0]
0x180028902  mov     rax, [rax+168h]
0x180028909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002890e  mov     ebx, eax
0x180028910  test    eax, eax
0x180028912  jns     short loc_18002891F
0x180028914  mov     r9d, eax
0x180028917  mov     r8d, 2E7h
0x18002891d  jmp     short loc_18002894D
0x18002891f  cmp     eax, 1
0x180028922  jz      short loc_18002893F
0x180028924  mov     rcx, [rsp+28h+arg_0]
0x180028929  test    rcx, rcx
0x18002892c  jz      short loc_18002893F
0x18002892e  mov     rax, [rcx]
0x180028931  mov     [rdi], rcx
0x180028934  mov     rax, [rax+8]
0x180028938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002893d  jmp     short loc_18002895E
0x18002893f  mov     ebx, 80004005h
0x180028944  mov     r8d, 2E8h; int
0x18002894a  mov     r9d, ebx; int
0x18002894d  lea     rdx, aSdpxmlgetrootn; "SdpXmlGetRootNode"
0x180028954  mov     ecx, 1; Level
0x180028959  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002895e  mov     rcx, [rsp+28h+arg_0]
0x180028963  test    rcx, rcx
0x180028966  jz      short loc_180028974
0x180028968  mov     rax, [rcx]
0x18002896b  mov     rax, [rax+10h]
0x18002896f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028974  mov     eax, ebx
0x180028976  mov     rbx, [rsp+28h+arg_8]
0x18002897b  add     rsp, 20h
0x18002897f  pop     rdi
0x180028980  retn
```
