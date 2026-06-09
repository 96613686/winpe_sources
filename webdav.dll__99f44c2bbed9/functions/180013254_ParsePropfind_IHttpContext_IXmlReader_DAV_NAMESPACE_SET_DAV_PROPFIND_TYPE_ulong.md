# ParsePropfind(IHttpContext *,IXmlReader *,DAV_NAMESPACE_SET *,DAV_PROPFIND_TYPE *,ulong)

- ea: `0x180013254`
- end: `0x1800134ea`
- name: `?ParsePropfind@@YAJPEAVIHttpContext@@PEAUIXmlReader@@PEAVDAV_NAMESPACE_SET@@PEAW4DAV_PROPFIND_TYPE@@K@Z`
- size: `662`
- prototype: `int(struct IHttpContext *, struct IXmlReader *, struct DAV_NAMESPACE_SET *, enum DAV_PROPFIND_TYPE *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000ed10`

## callees

- `0x1800121d8`
- `0x180013254`
- `0x18001e184`
- `0x18001e6a4`
- `0x18001e998`
- `0x18001ea6c`
- `0x18001eca4`
- `0x1800224e6`
- `0x180023010`

## string_xrefs

- `0x180013471`: `Found Multiple <prop> Entries, But MultiProp Disabled In Config`
- `0x1800134b8`: `Unexpected XML Element`

## pseudocode

```c
__int64 __fastcall ParsePropfind(
        struct IHttpContext *a1,
        struct IXmlReader *a2,
        struct DAV_NAMESPACE_SET *a3,
        enum DAV_PROPFIND_TYPE *a4,
        unsigned int a5)
{
  __int64 result; // rax
  const unsigned __int16 *v10; // rdx
  int v11; // edi
  int v12; // r14d
  int i; // eax
  wchar_t *v14; // rbx
  unsigned int v15; // ebx
  __int64 v16; // rax
  const wchar_t *v17; // r8
  const wchar_t *v18; // rdx
  unsigned int v19; // [rsp+30h] [rbp-58h] BYREF
  wchar_t *v20; // [rsp+38h] [rbp-50h] BYREF
  wchar_t *String1[9]; // [rsp+40h] [rbp-48h] BYREF

  v19 = 0;
  String1[0] = 0;
  v20 = 0;
  result = XmlFindNodeByType(a2, XmlNodeType_Element);
  if ( (int)result < 0 )
    return result;
  result = XmlCheckNodeName(a2, v10, L"propfind");
  if ( (int)result < 0 )
    return result;
  v11 = -1;
  v12 = 0;
  for ( i = XmlFindFirstSubElement(a2, &v19, (const unsigned __int16 **)String1, (const unsigned __int16 **)&v20);
        ;
        i = XmlFindNextSubElement(a2, v19, (const unsigned __int16 **)String1, (const unsigned __int16 **)&v20) )
  {
    v15 = i;
    if ( i == 1 )
      break;
    if ( i < 0 )
      return v15;
    if ( !wcscmp_0(String1[0], L"DAV:") )
    {
      v14 = v20;
      if ( !wcscmp_0(v20, L"propname") )
      {
        if ( v11 != -1 || v12 )
        {
          v15 = -2147024809;
          v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
          v17 = L"propname";
          goto LABEL_35;
        }
        v11 = 1;
      }
      else if ( !wcscmp_0(v14, L"allprop") )
      {
        if ( v11 != -1 )
        {
          v15 = -2147024809;
          v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
          v17 = L"allprop";
          goto LABEL_35;
        }
        v11 = 0;
      }
      else
      {
        if ( !wcscmp_0(v14, L"include") )
        {
          if ( (unsigned int)(v11 + 1) > 1 )
            goto LABEL_34;
          v12 = 1;
        }
        else
        {
          if ( wcscmp_0(v14, L"prop") )
            continue;
          if ( v12 )
          {
            v15 = -2147024809;
            v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
            v17 = L"prop";
            goto LABEL_35;
          }
          if ( v11 != -1 && ((a5 & 2) == 0 || v11 != 2) )
          {
            v15 = -2147024809;
            v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
            v17 = 0;
            v18 = L"Found Multiple <prop> Entries, But MultiProp Disabled In Config";
            goto LABEL_36;
          }
          v11 = 2;
        }
        v15 = AddXmlElementsToNamespaceSet(a2, a3, a5);
        if ( (v15 & 0x80000000) != 0 )
          return v15;
      }
    }
  }
  v15 = XmlSkipRemainingNodes(a2);
  if ( (v15 & 0x80000000) != 0 )
    return v15;
  if ( v11 != -1 && (!v12 || !v11) )
  {
    *(_DWORD *)a4 = v11;
    return v15;
  }
LABEL_34:
  v15 = -2147024809;
  v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  v17 = L"include";
LABEL_35:
  v18 = L"Unexpected XML Element";
LABEL_36:
  (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, char))(*(_QWORD *)v16 + 32LL))(
    v16,
    v18,
    v17,
    0,
    3);
  return v15;
}

```

## disassembly

```asm
0x180013254  push    rbx
0x180013256  push    rbp
0x180013257  push    rsi
0x180013258  push    rdi
0x180013259  push    r12
0x18001325b  push    r13
0x18001325d  push    r14
0x18001325f  sub     rsp, 50h
0x180013263  xor     ebx, ebx
0x180013265  mov     rbp, rdx
0x180013268  mov     rsi, rcx
0x18001326b  mov     [rsp+88h+var_58], ebx
0x18001326f  mov     rcx, rbp; struct IXmlReader *
0x180013272  mov     [rsp+88h+String1], rbx
0x180013277  mov     r13, r9
0x18001327a  mov     [rsp+88h+var_50], rbx
0x18001327f  lea     edx, [rbx+1]; enum XmlNodeType
0x180013282  mov     r12, r8
0x180013285  call    ?XmlFindNodeByType@@YAJPEAUIXmlReader@@W4XmlNodeType@@@Z; XmlFindNodeByType(IXmlReader *,XmlNodeType)
0x18001328a  test    eax, eax
0x18001328c  js      loc_1800134DB
0x180013292  lea     r8, aPropfind_1; "propfind"
0x180013299  mov     rcx, rbp; struct IXmlReader *
0x18001329c  call    ?XmlCheckNodeName@@YAJPEAUIXmlReader@@PEBG1@Z; XmlCheckNodeName(IXmlReader *,ushort const *,ushort const *)
0x1800132a1  test    eax, eax
0x1800132a3  js      loc_1800134DB
0x1800132a9  or      edi, 0FFFFFFFFh
0x1800132ac  lea     r9, [rsp+88h+var_50]; unsigned __int16 **
0x1800132b1  lea     r8, [rsp+88h+String1]; unsigned __int16 **
0x1800132b6  mov     rcx, rbp; struct IXmlReader *
0x1800132b9  lea     rdx, [rsp+88h+var_58]; unsigned int *
0x1800132be  mov     r14d, ebx
0x1800132c1  call    ?XmlFindFirstSubElement@@YAJPEAUIXmlReader@@PEAIPEAPEBG2@Z; XmlFindFirstSubElement(IXmlReader *,uint *,ushort const * *,ushort const * *)
0x1800132c6  jmp     loc_1800133D8
0x1800132cb  test    ebx, ebx
0x1800132cd  js      loc_1800134D9
0x1800132d3  mov     rcx, [rsp+88h+String1]; String1
0x1800132d8  lea     rdx, aDav; "DAV:"
0x1800132df  call    wcscmp_0
0x1800132e4  test    eax, eax
0x1800132e6  jnz     loc_1800133C2
0x1800132ec  mov     rbx, [rsp+88h+var_50]
0x1800132f1  lea     rdx, aPropname; "propname"
0x1800132f8  mov     rcx, rbx; String1
0x1800132fb  call    wcscmp_0
0x180013300  test    eax, eax
0x180013302  jnz     short loc_18001331E
0x180013304  cmp     edi, 0FFFFFFFFh
0x180013307  jnz     loc_180013414
0x18001330d  test    r14d, r14d
0x180013310  jnz     loc_180013414
0x180013316  lea     edi, [rax+1]
0x180013319  jmp     loc_1800133C2
0x18001331e  lea     rdx, aAllprop; "allprop"
0x180013325  mov     rcx, rbx; String1
0x180013328  call    wcscmp_0
0x18001332d  test    eax, eax
0x18001332f  jnz     short loc_180013341
0x180013331  cmp     edi, 0FFFFFFFFh
0x180013334  jnz     loc_180013437
0x18001333a  xor     edi, edi
0x18001333c  jmp     loc_1800133C2
0x180013341  lea     rdx, aInclude; "include"
0x180013348  mov     rcx, rbx; String1
0x18001334b  call    wcscmp_0
0x180013350  test    eax, eax
0x180013352  jnz     short loc_180013368
0x180013354  lea     eax, [rdi+1]
0x180013357  cmp     eax, 1
0x18001335a  ja      loc_18001349A
0x180013360  mov     r14d, 1
0x180013366  jmp     short loc_1800133A5
0x180013368  lea     rdx, aProp; "prop"
0x18001336f  mov     rcx, rbx; String1
0x180013372  call    wcscmp_0
0x180013377  test    eax, eax
0x180013379  jnz     short loc_1800133C2
0x18001337b  test    r14d, r14d
0x18001337e  jnz     loc_18001347A
0x180013384  cmp     edi, 0FFFFFFFFh
0x180013387  jz      short loc_1800133A0
0x180013389  test    byte ptr [rsp+88h+arg_20], 2
0x180013391  jz      loc_180013457
0x180013397  cmp     edi, 2
0x18001339a  jnz     loc_180013457
0x1800133a0  mov     edi, 2
0x1800133a5  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x1800133ad  mov     rdx, r12; struct DAV_NAMESPACE_SET *
0x1800133b0  mov     rcx, rbp; struct IXmlReader *
0x1800133b3  call    ?AddXmlElementsToNamespaceSet@@YAJPEAUIXmlReader@@PEAVDAV_NAMESPACE_SET@@K@Z; AddXmlElementsToNamespaceSet(IXmlReader *,DAV_NAMESPACE_SET *,ulong)
0x1800133b8  mov     ebx, eax
0x1800133ba  test    eax, eax
0x1800133bc  js      loc_1800134D9
0x1800133c2  mov     edx, [rsp+88h+var_58]; unsigned int
0x1800133c6  lea     r9, [rsp+88h+var_50]; unsigned __int16 **
0x1800133cb  lea     r8, [rsp+88h+String1]; unsigned __int16 **
0x1800133d0  mov     rcx, rbp; struct IXmlReader *
0x1800133d3  call    ?XmlFindNextSubElement@@YAJPEAUIXmlReader@@IPEAPEBG1@Z; XmlFindNextSubElement(IXmlReader *,uint,ushort const * *,ushort const * *)
0x1800133d8  mov     ebx, eax
0x1800133da  cmp     eax, 1
0x1800133dd  jnz     loc_1800132CB
0x1800133e3  mov     rcx, rbp; struct IXmlReader *
0x1800133e6  call    ?XmlSkipRemainingNodes@@YAJPEAUIXmlReader@@@Z; XmlSkipRemainingNodes(IXmlReader *)
0x1800133eb  mov     ebx, eax
0x1800133ed  test    eax, eax
0x1800133ef  js      loc_1800134D9
0x1800133f5  cmp     edi, 0FFFFFFFFh
0x1800133f8  jz      loc_18001349A
0x1800133fe  test    r14d, r14d
0x180013401  jz      short loc_18001340B
0x180013403  test    edi, edi
0x180013405  jnz     loc_18001349A
0x18001340b  mov     [r13+0], edi
0x18001340f  jmp     loc_1800134D9
0x180013414  mov     rax, [rsi]
0x180013417  mov     rcx, rsi
0x18001341a  mov     ebx, 80070057h
0x18001341f  mov     rax, [rax+110h]
0x180013426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001342b  lea     r8, aPropname; "propname"
0x180013432  jmp     loc_1800134B8
0x180013437  mov     rax, [rsi]
0x18001343a  mov     rcx, rsi
0x18001343d  mov     ebx, 80070057h
0x180013442  mov     rax, [rax+110h]
0x180013449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001344e  lea     r8, aAllprop; "allprop"
0x180013455  jmp     short loc_1800134B8
0x180013457  mov     rax, [rsi]
0x18001345a  mov     rcx, rsi
0x18001345d  mov     ebx, 80070057h
0x180013462  mov     rax, [rax+110h]
0x180013469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001346e  xor     r8d, r8d
0x180013471  lea     rdx, aFoundMultipleP; "Found Multiple <prop> Entries, But Mult"...
0x180013478  jmp     short loc_1800134BF
0x18001347a  mov     rax, [rsi]
0x18001347d  mov     rcx, rsi
0x180013480  mov     ebx, 80070057h
0x180013485  mov     rax, [rax+110h]
0x18001348c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013491  lea     r8, aProp; "prop"
0x180013498  jmp     short loc_1800134B8
0x18001349a  mov     rax, [rsi]
0x18001349d  mov     rcx, rsi
0x1800134a0  mov     ebx, 80070057h
0x1800134a5  mov     rax, [rax+110h]
0x1800134ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134b1  lea     r8, aInclude; "include"
0x1800134b8  lea     rdx, aUnexpectedXmlE; "Unexpected XML Element"
0x1800134bf  mov     rcx, [rax]
0x1800134c2  mov     r10, rax
0x1800134c5  xor     r9d, r9d
0x1800134c8  mov     [rsp+88h+var_68], 3
0x1800134cd  mov     rax, [rcx+20h]
0x1800134d1  mov     rcx, r10
0x1800134d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134d9  mov     eax, ebx
0x1800134db  add     rsp, 50h
0x1800134df  pop     r14
0x1800134e1  pop     r13
0x1800134e3  pop     r12
0x1800134e5  pop     rdi
0x1800134e6  pop     rsi
0x1800134e7  pop     rbp
0x1800134e8  pop     rbx
0x1800134e9  retn
```
