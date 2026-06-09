# LaunchUIInteraction::CreateSpecificDocument(IXMLDOMDocument2 * *,int)

- ea: `0x180026500`
- end: `0x180026705`
- name: `?CreateSpecificDocument@LaunchUIInteraction@@EEAAJPEAPEAUIXMLDOMDocument2@@H@Z`
- size: `517`
- prototype: `__int64 __fastcall(const OLECHAR **this, struct IXMLDOMDocument2 **, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800012a4`
- `0x18000571c`
- `0x180026500`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002827c`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800265e0`
- `OLEAUT32!__imp_SysAllocString` at `0x180026600`
- `OLEAUT32!__imp_SysAllocString` at `0x1800265e0`
- `OLEAUT32!__imp_SysAllocString` at `0x180026600`
- `OLEAUT32!__imp_SysFreeString` at `0x1800266d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800266d8`

## string_xrefs

- `0x180026633`: `CommandLine`
- `0x180026547`: `LaunchUIInteraction::CreateSpecificDocument`
- `0x18002657c`: `LaunchUIInteraction::CreateSpecificDocument`
- `0x1800265bc`: `LaunchUIInteraction::CreateSpecificDocument`
- `0x18002664a`: `LaunchUIInteraction::CreateSpecificDocument`
- `0x180026689`: `LaunchUIInteraction::CreateSpecificDocument`
- `0x180026563`: `<?xml version="1.0" encoding="utf-8"?><LaunchUIInteraction/>`

## pseudocode

```c
__int64 __fastcall LaunchUIInteraction::CreateSpecificDocument(
        const OLECHAR **this,
        struct IXMLDOMDocument2 **a2,
        int a3)
{
  struct IXMLDOMElement *v3; // r15
  OLECHAR *v4; // r14
  unsigned int v8; // ebx
  OLECHAR *v9; // rsi
  int v10; // eax
  int v11; // r9d
  int v12; // r8d
  struct IXMLDOMDocument2 *v13; // rdi
  int v14; // eax
  int v15; // eax
  int v16; // eax
  struct IXMLDOMElement *v18; // [rsp+30h] [rbp-10h] BYREF
  struct IXMLDOMDocument2 *v19; // [rsp+88h] [rbp+48h] BYREF
  OLECHAR *psz; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  v19 = 0;
  v4 = 0;
  v18 = 0;
  psz = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    SdpDebugTrace(1u, L"LaunchUIInteraction::CreateSpecificDocument", 103, -2147024809);
    return v8;
  }
  v9 = 0;
  v10 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><LaunchUIInteraction/>", &v19);
  v8 = v10;
  if ( v10 >= 0 )
  {
    if ( a3 )
    {
      v9 = SysAllocString(this[12]);
      if ( !v9 )
      {
        v11 = -2147024882;
        v12 = 123;
        v8 = -2147024882;
        goto LABEL_5;
      }
    }
    else
    {
      v14 = SdpSubstituteParamSet(&psz, this[12], (struct _SDIAG_PARAMSET *)(this + 13));
      v8 = v14;
      if ( v14 < 0 )
      {
        SdpDebugTrace(1u, L"LaunchUIInteraction::CreateSpecificDocument", 116, v14);
        v13 = v19;
        v4 = psz;
        goto LABEL_18;
      }
      v4 = psz;
      v9 = SysAllocString(psz);
      if ( !v9 )
      {
        v11 = -2147024882;
        v12 = 119;
        v8 = -2147024882;
        goto LABEL_5;
      }
    }
    v13 = v19;
    v15 = SdpXmlCreateNode(v19, 0, L"CommandLine", 0, &v18);
    v8 = v15;
    if ( v15 >= 0 )
    {
      v3 = v18;
      v16 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *))v18->lpVtbl->put_text)(v18, v9);
      v8 = v16;
      if ( v16 >= 0 )
      {
        *a2 = v13;
        v13 = 0;
      }
      else
      {
        SdpDebugTrace(1u, L"LaunchUIInteraction::CreateSpecificDocument", 135, v16);
      }
    }
    else
    {
      SdpDebugTrace(1u, L"LaunchUIInteraction::CreateSpecificDocument", 132, v15);
      v3 = v18;
    }
    goto LABEL_18;
  }
  v11 = v10;
  v12 = 106;
LABEL_5:
  SdpDebugTrace(1u, L"LaunchUIInteraction::CreateSpecificDocument", v12, v11);
  v13 = v19;
LABEL_18:
  if ( v13 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v13->lpVtbl->Release)(v13);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
  if ( v9 )
    SysFreeString(v9);
  if ( v4 )
    operator delete(v4);
  return v8;
}

```

## disassembly

```asm
0x180026500  mov     [rsp-38h+arg_0], rbx
0x180026505  push    rbp
0x180026506  push    rsi
0x180026507  push    rdi
0x180026508  push    r12
0x18002650a  push    r13
0x18002650c  push    r14
0x18002650e  push    r15
0x180026510  mov     rbp, rsp
0x180026513  sub     rsp, 40h
0x180026517  xor     r15d, r15d
0x18002651a  mov     [rbp+arg_8], 0
0x180026522  xor     r14d, r14d
0x180026525  mov     [rbp+var_10], r15
0x180026529  mov     [rbp+psz], r14
0x18002652d  mov     r13d, r8d
0x180026530  mov     r12, rdx
0x180026533  mov     rdi, rcx
0x180026536  test    rdx, rdx
0x180026539  jnz     short loc_18002655D
0x18002653b  lea     r8d, [rdx+67h]; int
0x18002653f  mov     ebx, 80070057h
0x180026544  mov     r9d, ebx; int
0x180026547  lea     rdx, aLaunchuiintera; "LaunchUIInteraction::CreateSpecificDocu"...
0x18002654e  lea     ecx, [r12+1]; Level
0x180026553  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026558  jmp     loc_1800266EB
0x18002655d  lea     rdx, [rbp+arg_8]; struct IXMLDOMDocument2 **
0x180026561  xor     esi, esi
0x180026563  lea     rcx, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18002656a  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18002656f  mov     ebx, eax
0x180026571  test    eax, eax
0x180026573  jns     short loc_180026596
0x180026575  mov     r9d, eax; int
0x180026578  lea     r8d, [rsi+6Ah]; int
0x18002657c  lea     rdx, aLaunchuiintera; "LaunchUIInteraction::CreateSpecificDocu"...
0x180026583  mov     ecx, 1; Level
0x180026588  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002658d  mov     rdi, [rbp+arg_8]
0x180026591  jmp     loc_1800266A8
0x180026596  mov     rcx, [rdi+60h]; psz
0x18002659a  test    r13d, r13d
0x18002659d  jnz     short loc_180026600
0x18002659f  mov     rdx, rcx; unsigned __int16 *
0x1800265a2  lea     r8, [rdi+68h]; struct _SDIAG_PARAMSET *
0x1800265a6  lea     rcx, [rbp+psz]; unsigned __int16 **
0x1800265aa  call    ?SdpSubstituteParamSet@@YAJPEAPEAGPEBGPEAU_SDIAG_PARAMSET@@@Z; SdpSubstituteParamSet(ushort * *,ushort const *,_SDIAG_PARAMSET *)
0x1800265af  mov     ebx, eax
0x1800265b1  test    eax, eax
0x1800265b3  jns     short loc_1800265D9
0x1800265b5  mov     r9d, eax; int
0x1800265b8  lea     r8d, [r13+74h]; int
0x1800265bc  lea     rdx, aLaunchuiintera; "LaunchUIInteraction::CreateSpecificDocu"...
0x1800265c3  lea     ecx, [r13+1]; Level
0x1800265c7  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800265cc  mov     rdi, [rbp+arg_8]
0x1800265d0  mov     r14, [rbp+psz]
0x1800265d4  jmp     loc_1800266A8
0x1800265d9  mov     r14, [rbp+psz]
0x1800265dd  mov     rcx, r14; psz
0x1800265e0  call    cs:__imp_SysAllocString
0x1800265e6  mov     rsi, rax
0x1800265e9  test    rax, rax
0x1800265ec  jnz     short loc_180026620
0x1800265ee  mov     r9d, 8007000Eh
0x1800265f4  lea     r8d, [rax+77h]
0x1800265f8  mov     ebx, r9d
0x1800265fb  jmp     loc_18002657C
0x180026600  call    cs:__imp_SysAllocString
0x180026606  mov     rsi, rax
0x180026609  test    rax, rax
0x18002660c  jnz     short loc_180026620
0x18002660e  mov     r9d, 8007000Eh
0x180026614  lea     r8d, [rax+7Bh]
0x180026618  mov     ebx, r9d
0x18002661b  jmp     loc_18002657C
0x180026620  mov     rdi, [rbp+arg_8]
0x180026624  lea     rax, [rbp+var_10]
0x180026628  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18002662b  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x180026630  xor     r9d, r9d; unsigned __int16 *
0x180026633  lea     r8, aCommandline; "CommandLine"
0x18002663a  xor     edx, edx; struct IXMLDOMElement *
0x18002663c  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180026641  mov     ebx, eax
0x180026643  test    eax, eax
0x180026645  jns     short loc_180026667
0x180026647  mov     r9d, eax; int
0x18002664a  lea     rdx, aLaunchuiintera; "LaunchUIInteraction::CreateSpecificDocu"...
0x180026651  mov     r8d, 84h; int
0x180026657  mov     ecx, 1; Level
0x18002665c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026661  mov     r15, [rbp+var_10]
0x180026665  jmp     short loc_1800266A8
0x180026667  mov     r15, [rbp+var_10]
0x18002666b  mov     rdx, rsi
0x18002666e  mov     rcx, r15
0x180026671  mov     rax, [r15]
0x180026674  mov     rax, [rax+0D8h]
0x18002667b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026680  mov     ebx, eax
0x180026682  test    eax, eax
0x180026684  jns     short loc_1800266A2
0x180026686  mov     r9d, eax; int
0x180026689  lea     rdx, aLaunchuiintera; "LaunchUIInteraction::CreateSpecificDocu"...
0x180026690  mov     r8d, 87h; int
0x180026696  mov     ecx, 1; Level
0x18002669b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800266a0  jmp     short loc_1800266A8
0x1800266a2  mov     [r12], rdi
0x1800266a6  xor     edi, edi
0x1800266a8  test    rdi, rdi
0x1800266ab  jz      short loc_1800266BC
0x1800266ad  mov     rax, [rdi]
0x1800266b0  mov     rcx, rdi
0x1800266b3  mov     rax, [rax+10h]
0x1800266b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266bc  test    r15, r15
0x1800266bf  jz      short loc_1800266D0
0x1800266c1  mov     rax, [r15]
0x1800266c4  mov     rcx, r15
0x1800266c7  mov     rax, [rax+10h]
0x1800266cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266d0  test    rsi, rsi
0x1800266d3  jz      short loc_1800266DE
0x1800266d5  mov     rcx, rsi; bstrString
0x1800266d8  call    cs:__imp_SysFreeString
0x1800266de  test    r14, r14
0x1800266e1  jz      short loc_1800266EB
0x1800266e3  mov     rcx, r14; Block
0x1800266e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800266eb  mov     eax, ebx
0x1800266ed  mov     rbx, [rsp+40h+arg_0]
0x1800266f5  add     rsp, 40h
0x1800266f9  pop     r15
0x1800266fb  pop     r14
0x1800266fd  pop     r13
0x1800266ff  pop     r12
0x180026701  pop     rdi
0x180026702  pop     rsi
0x180026703  pop     rbp
0x180026704  retn
```
