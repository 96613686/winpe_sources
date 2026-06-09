# TextInteraction::ParseSpecificChildren(IXMLDOMNodeList *)

- ea: `0x180025ff0`
- end: `0x1800260f1`
- name: `?ParseSpecificChildren@TextInteraction@@EEAAJPEAUIXMLDOMNodeList@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(TextInteraction *this, struct IXMLDOMNodeList *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180025ff0`
- `0x180026fa0`
- `0x180028038`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180026089`
- `msvcrt!_wcsicmp` at `0x180026089`
- `OLEAUT32!__imp_SysFreeString` at `0x18002609c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002609c`

## pseudocode

```c
__int64 __fastcall TextInteraction::ParseSpecificChildren(TextInteraction *this, struct IXMLDOMNodeList *a2)
{
  int v3; // eax
  struct IXMLDOMNode *v4; // rdi
  unsigned int v5; // ebx
  int v6; // r9d
  int v7; // r8d
  int v8; // eax
  int v9; // eax
  OLECHAR *v10; // rcx
  struct IXMLDOMNode *v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  v3 = SdpXmlNextNode(a2, &v12);
  v4 = v12;
  v5 = v3;
  if ( v3 < 0 )
  {
    v6 = v3;
    v7 = 53;
LABEL_14:
    SdpDebugTrace(1u, L"TextInteraction::ParseSpecificChildren", v7, v6);
    goto LABEL_15;
  }
  v8 = SdpXmlCheckNode(v12, L"RegularExpression");
  v5 = v8;
  if ( v8 < 0 )
  {
    v6 = v8;
LABEL_13:
    v7 = 54;
    goto LABEL_14;
  }
  if ( v8 == 1 || !v4 )
  {
    v5 = -2147467259;
    v6 = -2147467259;
    goto LABEL_13;
  }
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))v4->lpVtbl->get_text)(v4, (char *)this + 96);
  v5 = v9;
  if ( v9 < 0 )
  {
    v6 = v9;
    v7 = 57;
    goto LABEL_14;
  }
  if ( !_wcsicmp(&word_18002DFCC, *((const wchar_t **)this + 12)) )
  {
    v10 = (OLECHAR *)*((_QWORD *)this + 12);
    if ( v10 )
    {
      SysFreeString(v10);
      *((_QWORD *)this + 12) = 0;
    }
  }
LABEL_15:
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  return v5;
}

```

## disassembly

```asm
0x180025ff0  mov     r11, rsp
0x180025ff3  mov     [r11+8], rbx
0x180025ff7  mov     [r11+10h], rsi
0x180025ffb  push    rdi
0x180025ffc  sub     rsp, 20h
0x180026000  mov     rax, rdx
0x180026003  mov     qword ptr [r11+18h], 0
0x18002600b  mov     rsi, rcx
0x18002600e  lea     rdx, [r11+18h]; struct IXMLDOMNode **
0x180026012  mov     rcx, rax; struct IXMLDOMNodeList *
0x180026015  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18002601a  mov     rdi, [rsp+28h+arg_10]
0x18002601f  mov     ebx, eax
0x180026021  test    eax, eax
0x180026023  jns     short loc_180026033
0x180026025  mov     r9d, eax
0x180026028  mov     r8d, 35h ; '5'
0x18002602e  jmp     loc_1800260BA
0x180026033  lea     rdx, aRegularexpress; "RegularExpression"
0x18002603a  mov     rcx, rdi; struct IXMLDOMNode *
0x18002603d  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180026042  mov     ebx, eax
0x180026044  test    eax, eax
0x180026046  jns     short loc_18002604D
0x180026048  mov     r9d, eax
0x18002604b  jmp     short loc_1800260B4
0x18002604d  cmp     eax, 1
0x180026050  jz      short loc_1800260AC
0x180026052  test    rdi, rdi
0x180026055  jz      short loc_1800260AC
0x180026057  mov     rax, [rdi]
0x18002605a  lea     rdx, [rsi+60h]
0x18002605e  mov     rcx, rdi
0x180026061  mov     rax, [rax+0D0h]
0x180026068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002606d  mov     ebx, eax
0x18002606f  test    eax, eax
0x180026071  jns     short loc_18002607E
0x180026073  mov     r9d, eax
0x180026076  mov     r8d, 39h ; '9'
0x18002607c  jmp     short loc_1800260BA
0x18002607e  mov     rdx, [rsi+60h]; String2
0x180026082  lea     rcx, word_18002DFCC; String1
0x180026089  call    cs:__imp__wcsicmp
0x18002608f  test    eax, eax
0x180026091  jnz     short loc_1800260CB
0x180026093  mov     rcx, [rsi+60h]; bstrString
0x180026097  test    rcx, rcx
0x18002609a  jz      short loc_1800260CB
0x18002609c  call    cs:__imp_SysFreeString
0x1800260a2  mov     qword ptr [rsi+60h], 0
0x1800260aa  jmp     short loc_1800260CB
0x1800260ac  mov     ebx, 80004005h
0x1800260b1  mov     r9d, ebx; int
0x1800260b4  mov     r8d, 36h ; '6'; int
0x1800260ba  lea     rdx, aTextinteractio_3; "TextInteraction::ParseSpecificChildren"
0x1800260c1  mov     ecx, 1; Level
0x1800260c6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800260cb  test    rdi, rdi
0x1800260ce  jz      short loc_1800260DF
0x1800260d0  mov     rax, [rdi]
0x1800260d3  mov     rcx, rdi
0x1800260d6  mov     rax, [rax+10h]
0x1800260da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260df  mov     rsi, [rsp+28h+arg_8]
0x1800260e4  mov     eax, ebx
0x1800260e6  mov     rbx, [rsp+28h+arg_0]
0x1800260eb  add     rsp, 20h
0x1800260ef  pop     rdi
0x1800260f0  retn
```
