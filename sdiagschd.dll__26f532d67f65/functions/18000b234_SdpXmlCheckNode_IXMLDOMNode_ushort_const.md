# SdpXmlCheckNode(IXMLDOMNode *,ushort const *)

- ea: `0x18000b234`
- end: `0x18000b2f7`
- name: `?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z`
- size: `195`
- prototype: `int(struct IXMLDOMNode *, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002de0`
- `0x180003100`
- `0x180003384`
- `0x180003554`
- `0x180003e10`
- `0x1800040b4`
- `0x180004c48`
- `0x180005404`
- `0x1800060bc`
- `0x1800062c4`

## callees

- `0x18000b094`
- `0x18000b13c`
- `0x18000b234`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b2a5`
- `msvcrt!_wcsicmp` at `0x18000b2a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2dd`

## string_xrefs

- `0x18000b25b`: `SdpXmlCheckNode`

## pseudocode

```c
__int64 __fastcall SdpXmlCheckNode(struct IXMLDOMNode *a1, const unsigned __int16 *a2)
{
  int v3; // r8d
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
0x18000b234  mov     [rsp+arg_8], rbx
0x18000b239  push    rdi
0x18000b23a  sub     rsp, 20h
0x18000b23e  and     [rsp+28h+String1], 0
0x18000b244  mov     rdi, rdx
0x18000b247  test    rcx, rcx
0x18000b24a  jnz     short loc_18000B26E
0x18000b24c  mov     r8d, 5CDh; int
0x18000b252  mov     r9d, 80070057h; int
0x18000b258  mov     ebx, r9d
0x18000b25b  lea     rdx, aSdpxmlchecknod; "SdpXmlCheckNode"
0x18000b262  mov     ecx, 1; Level
0x18000b267  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b26c  jmp     short loc_18000B2D3
0x18000b26e  test    rdi, rdi
0x18000b271  jnz     short loc_18000B27B
0x18000b273  mov     r8d, 5CEh
0x18000b279  jmp     short loc_18000B252
0x18000b27b  mov     rax, [rcx]
0x18000b27e  lea     rdx, [rsp+28h+String1]
0x18000b283  mov     rax, [rax+38h]
0x18000b287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b28c  mov     ebx, eax
0x18000b28e  test    eax, eax
0x18000b290  jns     short loc_18000B29D
0x18000b292  mov     r9d, eax
0x18000b295  mov     r8d, 5D1h
0x18000b29b  jmp     short loc_18000B25B
0x18000b29d  mov     rcx, [rsp+28h+String1]; String1
0x18000b2a2  mov     rdx, rdi; String2
0x18000b2a5  call    cs:__imp__wcsicmp
0x18000b2ac  nop     dword ptr [rax+rax+00h]
0x18000b2b1  test    eax, eax
0x18000b2b3  jz      short loc_18000B2D3
0x18000b2b5  mov     r8, [rsp+28h+String1]
0x18000b2ba  lea     rdx, aNodeParsingMis; "Node Parsing mismatch: was %ws, expecte"...
0x18000b2c1  mov     r9, rdi
0x18000b2c4  mov     ecx, 1; Level
0x18000b2c9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x18000b2ce  mov     ebx, 1
0x18000b2d3  mov     rcx, [rsp+28h+String1]; bstrString
0x18000b2d8  test    rcx, rcx
0x18000b2db  jz      short loc_18000B2E9
0x18000b2dd  call    cs:__imp_SysFreeString
0x18000b2e4  nop     dword ptr [rax+rax+00h]
0x18000b2e9  mov     eax, ebx
0x18000b2eb  mov     rbx, [rsp+28h+arg_8]
0x18000b2f0  add     rsp, 20h
0x18000b2f4  pop     rdi
0x18000b2f5  retn
```
