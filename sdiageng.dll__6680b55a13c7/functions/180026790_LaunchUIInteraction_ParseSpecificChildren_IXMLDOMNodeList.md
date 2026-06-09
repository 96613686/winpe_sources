# LaunchUIInteraction::ParseSpecificChildren(IXMLDOMNodeList *)

- ea: `0x180026790`
- end: `0x18002694f`
- name: `?ParseSpecificChildren@LaunchUIInteraction@@EEAAJPEAUIXMLDOMNodeList@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(LaunchUIInteraction *this, struct IXMLDOMNodeList *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800040e8`
- `0x180026790`
- `0x180026fa0`
- `0x180028038`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800268db`
- `msvcrt!_wcsicmp` at `0x1800268db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800268ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800268ee`

## string_xrefs

- `0x180026880`: `CommandLine`

## pseudocode

```c
__int64 __fastcall LaunchUIInteraction::ParseSpecificChildren(LaunchUIInteraction *this, struct IXMLDOMNodeList *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // r8d
  struct IXMLDOMNode *v7; // rdi
  int v8; // eax
  int v9; // r9d
  int v10; // eax
  int v11; // r8d
  int v12; // eax
  OLECHAR *v13; // rcx
  struct IXMLDOMNode *v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = 0;
  v4 = SdpXmlNextNode(a2, &v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 58;
LABEL_3:
    SdpDebugTrace(1u, L"LaunchUIInteraction::ParseSpecificChildren", v6, v4);
    v7 = v15;
    goto LABEL_27;
  }
  v7 = v15;
  v8 = SdpXmlCheckNode(v15, L"Parameters");
  v5 = v8;
  if ( v8 < 0 )
  {
    v9 = v8;
LABEL_25:
    v11 = 59;
    goto LABEL_26;
  }
  if ( v8 == 1 || !v7 )
  {
    v9 = -2147467259;
    v5 = -2147467259;
    goto LABEL_25;
  }
  v10 = SdpParseParameters(v7, (LaunchUIInteraction *)((char *)this + 104));
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = 63;
LABEL_10:
    v9 = v10;
LABEL_26:
    SdpDebugTrace(1u, L"LaunchUIInteraction::ParseSpecificChildren", v11, v9);
    goto LABEL_27;
  }
  ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  v15 = 0;
  v4 = SdpXmlNextNode(a2, &v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 71;
    goto LABEL_3;
  }
  v7 = v15;
  v12 = SdpXmlCheckNode(v15, L"CommandLine");
  v5 = v12;
  if ( v12 < 0 )
  {
    v9 = v12;
LABEL_15:
    v11 = 72;
    goto LABEL_26;
  }
  if ( v12 == 1 || !v7 )
  {
    v9 = -2147467259;
    v5 = -2147467259;
    goto LABEL_15;
  }
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))v7->lpVtbl->get_text)(v7, (char *)this + 96);
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = 75;
    goto LABEL_10;
  }
  if ( !_wcsicmp(&word_18002DFCC, *((const wchar_t **)this + 12)) )
  {
    v13 = (OLECHAR *)*((_QWORD *)this + 12);
    if ( v13 )
    {
      SysFreeString(v13);
      *((_QWORD *)this + 12) = 0;
    }
  }
LABEL_27:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  return v5;
}

```

## disassembly

```asm
0x180026790  mov     rax, rsp
0x180026793  mov     [rax+8], rbx
0x180026797  mov     [rax+10h], rbp
0x18002679b  push    rsi
0x18002679c  push    rdi
0x18002679d  push    r14
0x18002679f  sub     rsp, 20h
0x1800267a3  mov     rbp, rdx
0x1800267a6  mov     qword ptr [rax+18h], 0
0x1800267ae  mov     r14, rcx
0x1800267b1  lea     rdx, [rax+18h]; struct IXMLDOMNode **
0x1800267b5  mov     rcx, rbp; struct IXMLDOMNodeList *
0x1800267b8  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x1800267bd  mov     ebx, eax
0x1800267bf  test    eax, eax
0x1800267c1  jns     short loc_1800267E6
0x1800267c3  mov     r8d, 3Ah ; ':'; int
0x1800267c9  lea     ecx, [r8-39h]; Level
0x1800267cd  lea     rdx, aLaunchuiintera_2; "LaunchUIInteraction::ParseSpecificChild"...
0x1800267d4  mov     r9d, eax; int
0x1800267d7  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800267dc  mov     rdi, [rsp+38h+arg_10]
0x1800267e1  jmp     loc_180026926
0x1800267e6  mov     rdi, [rsp+38h+arg_10]
0x1800267eb  lea     rdx, aParameters; "Parameters"
0x1800267f2  mov     rcx, rdi; struct IXMLDOMNode *
0x1800267f5  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x1800267fa  mov     ebx, eax
0x1800267fc  test    eax, eax
0x1800267fe  jns     short loc_18002680D
0x180026800  mov     r9d, eax
0x180026803  mov     ecx, 1
0x180026808  jmp     loc_180026914
0x18002680d  mov     esi, 1
0x180026812  cmp     eax, esi
0x180026814  jz      loc_180026909
0x18002681a  test    rdi, rdi
0x18002681d  jz      loc_180026909
0x180026823  lea     rdx, [r14+68h]; struct _SDIAG_PARAMSET *
0x180026827  mov     rcx, rdi; struct IXMLDOMNode *
0x18002682a  call    ?SdpParseParameters@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_PARAMSET@@@Z; SdpParseParameters(IXMLDOMNode *,_SDIAG_PARAMSET *)
0x18002682f  mov     ebx, eax
0x180026831  test    eax, eax
0x180026833  jns     short loc_180026843
0x180026835  lea     r8d, [rsi+3Eh]
0x180026839  mov     r9d, eax
0x18002683c  mov     ecx, esi
0x18002683e  jmp     loc_18002691A
0x180026843  mov     rax, [rdi]
0x180026846  mov     rcx, rdi
0x180026849  mov     rax, [rax+10h]
0x18002684d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026852  lea     rdx, [rsp+38h+arg_10]; struct IXMLDOMNode **
0x180026857  mov     [rsp+38h+arg_10], 0
0x180026860  mov     rcx, rbp; struct IXMLDOMNodeList *
0x180026863  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180026868  mov     ebx, eax
0x18002686a  test    eax, eax
0x18002686c  jns     short loc_18002687B
0x18002686e  mov     r8d, 47h ; 'G'
0x180026874  mov     ecx, esi
0x180026876  jmp     loc_1800267CD
0x18002687b  mov     rdi, [rsp+38h+arg_10]
0x180026880  lea     rdx, aCommandline; "CommandLine"
0x180026887  mov     rcx, rdi; struct IXMLDOMNode *
0x18002688a  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18002688f  mov     ebx, eax
0x180026891  test    eax, eax
0x180026893  jns     short loc_1800268A0
0x180026895  mov     r9d, eax
0x180026898  mov     r8d, 48h ; 'H'
0x18002689e  jmp     short loc_18002683C
0x1800268a0  cmp     eax, esi
0x1800268a2  jz      short loc_1800268FE
0x1800268a4  test    rdi, rdi
0x1800268a7  jz      short loc_1800268FE
0x1800268a9  mov     rax, [rdi]
0x1800268ac  lea     rdx, [r14+60h]
0x1800268b0  mov     rcx, rdi
0x1800268b3  mov     rax, [rax+0D0h]
0x1800268ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268bf  mov     ebx, eax
0x1800268c1  test    eax, eax
0x1800268c3  jns     short loc_1800268D0
0x1800268c5  mov     r8d, 4Bh ; 'K'
0x1800268cb  jmp     loc_180026839
0x1800268d0  mov     rdx, [r14+60h]; String2
0x1800268d4  lea     rcx, word_18002DFCC; String1
0x1800268db  call    cs:__imp__wcsicmp
0x1800268e1  test    eax, eax
0x1800268e3  jnz     short loc_180026926
0x1800268e5  mov     rcx, [r14+60h]; bstrString
0x1800268e9  test    rcx, rcx
0x1800268ec  jz      short loc_180026926
0x1800268ee  call    cs:__imp_SysFreeString
0x1800268f4  mov     qword ptr [r14+60h], 0
0x1800268fc  jmp     short loc_180026926
0x1800268fe  mov     r9d, 80004005h
0x180026904  mov     ebx, r9d
0x180026907  jmp     short loc_180026898
0x180026909  mov     r9d, 80004005h; int
0x18002690f  mov     ecx, esi; Level
0x180026911  mov     ebx, r9d
0x180026914  mov     r8d, 3Bh ; ';'; int
0x18002691a  lea     rdx, aLaunchuiintera_2; "LaunchUIInteraction::ParseSpecificChild"...
0x180026921  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026926  test    rdi, rdi
0x180026929  jz      short loc_18002693A
0x18002692b  mov     rax, [rdi]
0x18002692e  mov     rcx, rdi
0x180026931  mov     rax, [rax+10h]
0x180026935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002693a  mov     rbp, [rsp+38h+arg_8]
0x18002693f  mov     eax, ebx
0x180026941  mov     rbx, [rsp+38h+arg_0]
0x180026946  add     rsp, 20h
0x18002694a  pop     r14
0x18002694c  pop     rdi
0x18002694d  pop     rsi
0x18002694e  retn
```
