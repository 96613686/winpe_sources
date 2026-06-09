# SdpXmlCheckNode(IXMLDOMNode *,ushort const *)

- ea: `0x180028038`
- end: `0x1800280f1`
- name: `?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z`
- size: `185`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *)`
- caller_count: `22`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002d20`
- `0x180003b2c`
- `0x180003e50`
- `0x1800040e8`
- `0x180016228`
- `0x180016630`
- `0x18001a0bc`
- `0x18001a530`
- `0x18001bf34`
- `0x18001c6e8`
- `0x18001d20c`
- `0x18001dc28`
- `0x18001f010`
- `0x18001fc10`
- `0x180020648`
- `0x1800208f4`
- `0x180020c7c`
- `0x180022ce0`
- `0x180023020`
- `0x180023680`
- `0x180025ff0`
- `0x180026790`

## callees

- `0x180026efc`
- `0x180026fa0`
- `0x180028038`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800280ac`
- `msvcrt!_wcsicmp` at `0x1800280ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280de`

## string_xrefs

- `0x180028062`: `SdpXmlCheckNode`

## pseudocode

```c
__int64 __fastcall SdpXmlCheckNode(struct IXMLDOMNode *a1, const unsigned __int16 *a2)
{
  unsigned int v3; // r8d
  int v4; // r9d
  unsigned int v5; // ebx
  int v6; // eax
  wchar_t *String1; // [rsp+30h] [rbp+8h] BYREF

  String1 = 0;
  if ( !a1 )
  {
    v3 = 1485;
LABEL_3:
    v4 = -2147024809;
    v5 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpXmlCheckNode", v3, v4);
    goto LABEL_11;
  }
  if ( !a2 )
  {
    v3 = 1486;
    goto LABEL_3;
  }
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))a1->lpVtbl->get_nodeName)(a1, &String1);
  v5 = v6;
  if ( v6 < 0 )
  {
    v4 = v6;
    v3 = 1489;
    goto LABEL_4;
  }
  if ( _wcsicmp(String1, a2) )
  {
    SdpDebugPrint(1u, "Node Parsing mismatch: was %ws, expected %ws\n", String1, a2);
    v5 = 1;
  }
LABEL_11:
  if ( String1 )
    SysFreeString(String1);
  return v5;
}

```

## disassembly

```asm
0x180028038  mov     [rsp+arg_8], rbx
0x18002803d  push    rdi
0x18002803e  sub     rsp, 20h
0x180028042  mov     [rsp+28h+String1], 0
0x18002804b  mov     rdi, rdx
0x18002804e  test    rcx, rcx
0x180028051  jnz     short loc_180028075
0x180028053  mov     r8d, 5CDh; int
0x180028059  mov     r9d, 80070057h; int
0x18002805f  mov     ebx, r9d
0x180028062  lea     rdx, aSdpxmlchecknod; "SdpXmlCheckNode"
0x180028069  mov     ecx, 1; Level
0x18002806e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028073  jmp     short loc_1800280D4
0x180028075  test    rdi, rdi
0x180028078  jnz     short loc_180028082
0x18002807a  mov     r8d, 5CEh
0x180028080  jmp     short loc_180028059
0x180028082  mov     rax, [rcx]
0x180028085  lea     rdx, [rsp+28h+String1]
0x18002808a  mov     rax, [rax+38h]
0x18002808e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028093  mov     ebx, eax
0x180028095  test    eax, eax
0x180028097  jns     short loc_1800280A4
0x180028099  mov     r9d, eax
0x18002809c  mov     r8d, 5D1h
0x1800280a2  jmp     short loc_180028062
0x1800280a4  mov     rcx, [rsp+28h+String1]; String1
0x1800280a9  mov     rdx, rdi; String2
0x1800280ac  call    cs:__imp__wcsicmp
0x1800280b2  test    eax, eax
0x1800280b4  jz      short loc_1800280D4
0x1800280b6  mov     r8, [rsp+28h+String1]
0x1800280bb  lea     rdx, aNodeParsingMis; "Node Parsing mismatch: was %ws, expecte"...
0x1800280c2  mov     r9, rdi
0x1800280c5  mov     ecx, 1; Level
0x1800280ca  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1800280cf  mov     ebx, 1
0x1800280d4  mov     rcx, [rsp+28h+String1]; bstrString
0x1800280d9  test    rcx, rcx
0x1800280dc  jz      short loc_1800280E4
0x1800280de  call    cs:__imp_SysFreeString
0x1800280e4  mov     eax, ebx
0x1800280e6  mov     rbx, [rsp+28h+arg_8]
0x1800280eb  add     rsp, 20h
0x1800280ef  pop     rdi
0x1800280f0  retn
```
