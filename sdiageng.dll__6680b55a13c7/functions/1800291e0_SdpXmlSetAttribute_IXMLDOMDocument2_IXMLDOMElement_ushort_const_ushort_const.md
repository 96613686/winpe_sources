# SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)

- ea: `0x1800291e0`
- end: `0x180029397`
- name: `?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z`
- size: `439`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800034c4`
- `0x180004518`
- `0x180004d58`
- `0x18001483c`
- `0x1800151fc`
- `0x180018a9c`
- `0x18001cc2c`
- `0x18001d544`
- `0x180020fc0`
- `0x18002114c`
- `0x180021914`

## callees

- `0x180026fa0`
- `0x1800288b8`
- `0x1800291e0`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180029242`
- `OLEAUT32!__imp_SysAllocString` at `0x180029270`
- `OLEAUT32!__imp_SysAllocString` at `0x180029242`
- `OLEAUT32!__imp_SysAllocString` at `0x180029270`
- `OLEAUT32!__imp_SysFreeString` at `0x18002934f`
- `OLEAUT32!__imp_SysFreeString` at `0x180029358`
- `OLEAUT32!__imp_SysFreeString` at `0x18002934f`
- `OLEAUT32!__imp_SysFreeString` at `0x180029358`

## string_xrefs

- `0x180029219`: `SdpXmlSetAttribute`
- `0x180029284`: `SdpXmlSetAttribute`
- `0x1800292c3`: `SdpXmlSetAttribute`
- `0x180029321`: `SdpXmlSetAttribute`
- `0x18002937b`: `SdpXmlSetAttribute`

## pseudocode

```c
__int64 __fastcall SdpXmlSetAttribute(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  struct IXMLDOMElement *v4; // rdi
  unsigned int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ebx
  OLECHAR *v11; // rsi
  OLECHAR *v12; // rbp
  int RootNode; // eax
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int v15; // eax
  __int128 v17; // [rsp+20h] [rbp-58h] BYREF
  __int64 v18; // [rsp+30h] [rbp-48h]
  struct IXMLDOMElement *v19; // [rsp+90h] [rbp+18h] BYREF

  v4 = 0;
  v19 = 0;
  v17 = 0;
  if ( a3 )
  {
    if ( !a4 )
    {
      v8 = 1746;
      goto LABEL_3;
    }
    v11 = SysAllocString(a4);
    if ( !v11 )
    {
      v9 = -2147024882;
      v8 = 1752;
      goto LABEL_4;
    }
    *((_QWORD *)&v17 + 1) = v11;
    LOWORD(v17) = 8;
    v12 = SysAllocString(a3);
    if ( !v12 )
    {
      v10 = -2147024882;
      SdpDebugTrace(1u, L"SdpXmlSetAttribute", 0x6DEu, -2147024882);
LABEL_20:
      SysFreeString(v11);
      return v10;
    }
    if ( a1 )
    {
      RootNode = SdpXmlGetRootNode(a1, &v19);
      v10 = RootNode;
      if ( RootNode < 0 )
      {
        SdpDebugTrace(1u, L"SdpXmlSetAttribute", 0x6E2u, RootNode);
        v4 = v19;
LABEL_17:
        if ( v4 )
          ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
        goto LABEL_19;
      }
      v4 = v19;
      a2 = v19;
    }
    else if ( !a2 )
    {
      v10 = -2147467261;
      SdpDebugTrace(1u, L"SdpXmlSetAttribute", 0x6E7u, -2147467261);
LABEL_19:
      SysFreeString(v12);
      goto LABEL_20;
    }
    lpVtbl = a2->lpVtbl;
    v18 = 0;
    v15 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *, __int128 *))lpVtbl->setAttribute)(a2, v12, &v17);
    v10 = v15;
    if ( v15 < 0 )
      SdpDebugTrace(1u, L"SdpXmlSetAttribute", 0x6EDu, v15);
    goto LABEL_17;
  }
  v8 = 1745;
LABEL_3:
  v9 = -2147024809;
LABEL_4:
  v10 = v9;
  SdpDebugTrace(1u, L"SdpXmlSetAttribute", v8, v9);
  return v10;
}

```

## disassembly

```asm
0x1800291e0  mov     rax, rsp
0x1800291e3  push    rbx
0x1800291e4  push    rbp
0x1800291e5  push    rsi
0x1800291e6  push    rdi
0x1800291e7  push    r14
0x1800291e9  push    r15
0x1800291eb  sub     rsp, 48h
0x1800291ef  xor     edi, edi
0x1800291f1  xor     r15d, r15d
0x1800291f4  mov     [rax+18h], rdi
0x1800291f8  xorps   xmm0, xmm0
0x1800291fb  mov     rbp, r8
0x1800291fe  mov     rbx, rdx
0x180029201  mov     r14, rcx
0x180029204  movups  xmmword ptr [rax-58h], xmm0
0x180029208  test    r8, r8
0x18002920b  jnz     short loc_180029232
0x18002920d  mov     r8d, 6D1h; int
0x180029213  mov     r9d, 80070057h; int
0x180029219  lea     rdx, aSdpxmlsetattri; "SdpXmlSetAttribute"
0x180029220  mov     ecx, 1; Level
0x180029225  mov     ebx, r9d
0x180029228  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002922d  jmp     loc_18002935E
0x180029232  test    r9, r9
0x180029235  jnz     short loc_18002923F
0x180029237  mov     r8d, 6D2h
0x18002923d  jmp     short loc_180029213
0x18002923f  mov     rcx, r9; psz
0x180029242  call    cs:__imp_SysAllocString
0x180029248  mov     rsi, rax
0x18002924b  test    rax, rax
0x18002924e  jnz     short loc_18002925E
0x180029250  mov     r9d, 8007000Eh
0x180029256  mov     r8d, 6D8h
0x18002925c  jmp     short loc_180029219
0x18002925e  mov     eax, 8
0x180029263  mov     qword ptr [rsp+78h+var_58+8], rsi
0x180029268  mov     rcx, rbp; psz
0x18002926b  mov     word ptr [rsp+78h+var_58], ax
0x180029270  call    cs:__imp_SysAllocString
0x180029276  mov     rbp, rax
0x180029279  test    rax, rax
0x18002927c  jnz     short loc_1800292A1
0x18002927e  mov     r9d, 8007000Eh; int
0x180029284  lea     rdx, aSdpxmlsetattri; "SdpXmlSetAttribute"
0x18002928b  mov     r8d, 6DEh; int
0x180029291  lea     ecx, [rax+1]; Level
0x180029294  mov     ebx, r9d
0x180029297  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002929c  jmp     loc_180029355
0x1800292a1  test    r14, r14
0x1800292a4  jz      loc_18002936D
0x1800292aa  lea     rdx, [rsp+78h+arg_10]; struct IXMLDOMElement **
0x1800292b2  mov     rcx, r14; struct IXMLDOMDocument2 *
0x1800292b5  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x1800292ba  mov     ebx, eax
0x1800292bc  test    eax, eax
0x1800292be  jns     short loc_1800292E4
0x1800292c0  mov     r9d, eax; int
0x1800292c3  lea     rdx, aSdpxmlsetattri; "SdpXmlSetAttribute"
0x1800292ca  mov     r8d, 6E2h; int
0x1800292d0  mov     ecx, 1; Level
0x1800292d5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800292da  mov     rdi, [rsp+78h+arg_10]
0x1800292e2  jmp     short loc_180029338
0x1800292e4  mov     rdi, [rsp+78h+arg_10]
0x1800292ec  mov     rbx, rdi
0x1800292ef  mov     rax, [rbx]
0x1800292f2  lea     r8, [rsp+78h+var_58]
0x1800292f7  movups  xmm0, [rsp+78h+var_58]
0x1800292fc  mov     rdx, rbp
0x1800292ff  mov     [rsp+78h+var_48], r15
0x180029304  mov     rcx, rbx
0x180029307  mov     rax, [rax+168h]
0x18002930e  movaps  [rsp+78h+var_58], xmm0
0x180029313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029318  mov     ebx, eax
0x18002931a  test    eax, eax
0x18002931c  jns     short loc_180029338
0x18002931e  mov     r9d, eax; int
0x180029321  lea     rdx, aSdpxmlsetattri; "SdpXmlSetAttribute"
0x180029328  mov     r8d, 6EDh; int
0x18002932e  mov     ecx, 1; Level
0x180029333  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180029338  test    rdi, rdi
0x18002933b  jz      short loc_18002934C
0x18002933d  mov     rax, [rdi]
0x180029340  mov     rcx, rdi
0x180029343  mov     rax, [rax+10h]
0x180029347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002934c  mov     rcx, rbp; bstrString
0x18002934f  call    cs:__imp_SysFreeString
0x180029355  mov     rcx, rsi; bstrString
0x180029358  call    cs:__imp_SysFreeString
0x18002935e  mov     eax, ebx
0x180029360  add     rsp, 48h
0x180029364  pop     r15
0x180029366  pop     r14
0x180029368  pop     rdi
0x180029369  pop     rsi
0x18002936a  pop     rbp
0x18002936b  pop     rbx
0x18002936c  retn
0x18002936d  test    rbx, rbx
0x180029370  jnz     loc_1800292EF
0x180029376  mov     ebx, 80004003h
0x18002937b  lea     rdx, aSdpxmlsetattri; "SdpXmlSetAttribute"
0x180029382  mov     r9d, ebx; int
0x180029385  mov     r8d, 6E7h; int
0x18002938b  mov     ecx, 1; Level
0x180029390  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180029395  jmp     short loc_18002934C
```
