# SdpParseBooleanNode(IXMLDOMNode *,int *)

- ea: `0x180003814`
- end: `0x1800038bb`
- name: `?SdpParseBooleanNode@@YAJPEAUIXMLDOMNode@@PEAH@Z`
- size: `167`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001dc28`
- `0x180023680`

## callees

- `0x180003814`
- `0x180026fa0`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000388f`
- `msvcrt!_wcsicmp` at `0x18000388f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800038a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800038a8`

## pseudocode

```c
__int64 __fastcall SdpParseBooleanNode(struct IXMLDOMNode *a1, int *a2)
{
  unsigned int v3; // r8d
  int v4; // r9d
  unsigned int v5; // ebx
  int v6; // eax
  wchar_t *String1; // [rsp+30h] [rbp+8h] BYREF

  String1 = 0;
  if ( !a1 )
  {
    v3 = 294;
LABEL_3:
    v4 = -2147024809;
    v5 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpParseBooleanNode", v3, v4);
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v3 = 295;
    goto LABEL_3;
  }
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))a1->lpVtbl->get_text)(a1, &String1);
  v5 = v6;
  if ( v6 < 0 )
  {
    v4 = v6;
    v3 = 298;
    goto LABEL_4;
  }
  *a2 = _wcsicmp(String1, L"TRUE") == 0;
LABEL_10:
  if ( String1 )
    SysFreeString(String1);
  return v5;
}

```

## disassembly

```asm
0x180003814  mov     [rsp+arg_8], rbx
0x180003819  push    rdi
0x18000381a  sub     rsp, 20h
0x18000381e  mov     [rsp+28h+String1], 0
0x180003827  mov     rdi, rdx
0x18000382a  test    rcx, rcx
0x18000382d  jnz     short loc_180003851
0x18000382f  mov     r8d, 126h; int
0x180003835  mov     r9d, 80070057h; int
0x18000383b  mov     ebx, r9d
0x18000383e  lea     rdx, aSdpparseboolea; "SdpParseBooleanNode"
0x180003845  mov     ecx, 1; Level
0x18000384a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000384f  jmp     short loc_18000389E
0x180003851  test    rdi, rdi
0x180003854  jnz     short loc_18000385E
0x180003856  mov     r8d, 127h
0x18000385c  jmp     short loc_180003835
0x18000385e  mov     rax, [rcx]
0x180003861  lea     rdx, [rsp+28h+String1]
0x180003866  mov     rax, [rax+0D0h]
0x18000386d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003872  mov     ebx, eax
0x180003874  test    eax, eax
0x180003876  jns     short loc_180003883
0x180003878  mov     r9d, eax
0x18000387b  mov     r8d, 12Ah
0x180003881  jmp     short loc_18000383E
0x180003883  mov     rcx, [rsp+28h+String1]; String1
0x180003888  lea     rdx, aTrue_0; "TRUE"
0x18000388f  call    cs:__imp__wcsicmp
0x180003895  xor     ecx, ecx
0x180003897  test    eax, eax
0x180003899  setz    cl
0x18000389c  mov     [rdi], ecx
0x18000389e  mov     rcx, [rsp+28h+String1]; bstrString
0x1800038a3  test    rcx, rcx
0x1800038a6  jz      short loc_1800038AE
0x1800038a8  call    cs:__imp_SysFreeString
0x1800038ae  mov     eax, ebx
0x1800038b0  mov     rbx, [rsp+28h+arg_8]
0x1800038b5  add     rsp, 20h
0x1800038b9  pop     rdi
0x1800038ba  retn
```
