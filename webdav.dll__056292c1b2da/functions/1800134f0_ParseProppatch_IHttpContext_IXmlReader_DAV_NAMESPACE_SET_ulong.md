# ParseProppatch(IHttpContext *,IXmlReader *,DAV_NAMESPACE_SET *,ulong)

- ea: `0x1800134f0`
- end: `0x180013850`
- name: `?ParseProppatch@@YAJPEAVIHttpContext@@PEAUIXmlReader@@PEAVDAV_NAMESPACE_SET@@K@Z`
- size: `864`
- prototype: `int(struct IHttpContext *, struct IXmlReader *, struct DAV_NAMESPACE_SET *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000f200`

## callees

- `0x1800121d8`
- `0x1800134f0`
- `0x180013858`
- `0x18001e184`
- `0x18001e6a4`
- `0x18001e898`
- `0x18001e998`
- `0x18001ea6c`
- `0x18001eca4`
- `0x1800224e6`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180013548`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013552`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001355d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013548`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013552`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001355d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800137e1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800137eb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800137f5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800137e1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800137eb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800137f5`

## string_xrefs

- `0x180013588`: `propertyupdate`
- `0x18001361a`: `remove`
- `0x18001383d`: `Found Multiple <prop> Entries, But MultiProp Disabled In Config`

## pseudocode

```c
__int64 __fastcall ParseProppatch(
        struct IHttpContext *a1,
        struct IXmlReader *a2,
        struct DAV_NAMESPACE_SET *a3,
        unsigned int a4)
{
  int v4; // r15d
  struct IHttpContext *v5; // rsi
  const unsigned __int16 *v8; // rdx
  int NodeByType; // ebx
  int v10; // r14d
  wchar_t *v11; // rsi
  wchar_t v12; // r12
  int FirstSubElement; // eax
  const unsigned __int16 *v14; // r8
  int v15; // eax
  __int64 v16; // rax
  const wchar_t *v17; // rdx
  wchar_t *v19; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-C8h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v24; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v25; // [rsp+50h] [rbp-B0h] BYREF
  struct DAV_NAMESPACE_SET *v26; // [rsp+58h] [rbp-A8h]
  struct IHttpContext *v27; // [rsp+60h] [rbp-A0h]
  _BYTE v28[32]; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v29; // [rsp+88h] [rbp-78h]
  _BYTE v30[32]; // [rsp+A0h] [rbp-60h] BYREF
  const unsigned __int16 *v31; // [rsp+C0h] [rbp-40h]
  _BYTE v32[32]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v33; // [rsp+F8h] [rbp-8h]

  v4 = 0;
  v27 = a1;
  v5 = a1;
  v25 = 0;
  v24 = 0;
  String1 = 0;
  v19 = 0;
  v26 = a3;
  STRU::STRU((STRU *)v32);
  STRU::STRU((STRU *)v30);
  STRU::STRU((STRU *)v28);
  v21 = 0;
  v22 = 0;
  v23 = 0;
  NodeByType = XmlFindNodeByType(a2, XmlNodeType_Element);
  if ( NodeByType >= 0 )
  {
    NodeByType = XmlCheckNodeName(a2, v8, L"propertyupdate");
    if ( NodeByType >= 0 )
    {
      NodeByType = XmlFindLanguageTag(a2, (struct STRU *)v32, &v23);
      if ( NodeByType >= 0 )
      {
        v10 = 0;
        NodeByType = XmlFindFirstSubElement(
                       a2,
                       &v25,
                       (const unsigned __int16 **)&String1,
                       (const unsigned __int16 **)&v19);
        if ( NodeByType == 1 )
        {
LABEL_33:
          NodeByType = XmlSkipRemainingNodes(a2);
          if ( NodeByType >= 0 && !v10 )
          {
            NodeByType = -2147024809;
            v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v5 + 272LL))(v5);
            v17 = L"Invalid Empty PROPPATCH Entity Body";
LABEL_36:
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v16 + 32LL))(
              v16,
              v17,
              0,
              0,
              3);
          }
        }
        else
        {
          while ( NodeByType >= 0 )
          {
            if ( !wcscmp_0(String1, L"DAV:") )
            {
              v11 = v19;
              if ( !wcscmp_0(v19, L"set") || !wcscmp_0(v11, L"remove") )
              {
                v12 = *v11;
                NodeByType = XmlFindLanguageTag(a2, (struct STRU *)v30, &v22);
                if ( NodeByType >= 0 )
                {
                  FirstSubElement = XmlFindFirstSubElement(
                                      a2,
                                      &v24,
                                      (const unsigned __int16 **)&String1,
                                      (const unsigned __int16 **)&v19);
                  v11 = v19;
                  NodeByType = FirstSubElement;
                }
                if ( NodeByType == 1 )
                {
LABEL_39:
                  NodeByType = -2147024809;
                }
                else
                {
                  while ( NodeByType >= 0 )
                  {
                    if ( !wcscmp_0(String1, L"DAV:") && !wcscmp_0(v11, L"prop") )
                    {
                      if ( v4 && (a4 & 2) == 0 )
                      {
                        NodeByType = -2147024809;
                        v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v27 + 272LL))(v27);
                        v17 = L"Found Multiple <prop> Entries, But MultiProp Disabled In Config";
                        goto LABEL_36;
                      }
                      if ( v12 == 115 )
                      {
                        NodeByType = XmlFindLanguageTag(a2, (struct STRU *)v28, &v21);
                        if ( NodeByType < 0 )
                          goto LABEL_37;
                        if ( v21 )
                        {
                          v14 = v29;
                        }
                        else if ( v22 )
                        {
                          v14 = v31;
                        }
                        else
                        {
                          v14 = (const unsigned __int16 *)(v33 & -(__int64)(v23 != 0));
                        }
                        v15 = ParseSetElement(a2, v26, v14, a4);
                      }
                      else
                      {
                        v15 = AddXmlElementsToNamespaceSet(a2, v26, a4);
                      }
                      NodeByType = v15;
                      v4 = 1;
                      v10 = 1;
                      if ( v15 < 0 )
                        goto LABEL_37;
                    }
                    NodeByType = XmlFindNextSubElement(
                                   a2,
                                   v24,
                                   (const unsigned __int16 **)&String1,
                                   (const unsigned __int16 **)&v19);
                    if ( NodeByType == 1 )
                    {
                      if ( !v4 )
                        goto LABEL_39;
                      v4 = 0;
                      goto LABEL_31;
                    }
                    v11 = v19;
                  }
                }
                break;
              }
            }
LABEL_31:
            NodeByType = XmlFindNextSubElement(
                           a2,
                           v25,
                           (const unsigned __int16 **)&String1,
                           (const unsigned __int16 **)&v19);
            if ( NodeByType == 1 )
            {
              v5 = v27;
              goto LABEL_33;
            }
          }
        }
      }
    }
  }
LABEL_37:
  STRU::~STRU((STRU *)v28);
  STRU::~STRU((STRU *)v30);
  STRU::~STRU((STRU *)v32);
  return (unsigned int)NodeByType;
}

```

## disassembly

```asm
0x1800134f0  mov     [rsp-8+arg_18], rbx
0x1800134f5  push    rbp
0x1800134f6  push    rsi
0x1800134f7  push    rdi
0x1800134f8  push    r12
0x1800134fa  push    r13
0x1800134fc  push    r14
0x1800134fe  push    r15
0x180013500  lea     rbp, [rsp-20h]
0x180013505  sub     rsp, 120h
0x18001350c  mov     rax, cs:__security_cookie
0x180013513  xor     rax, rsp
0x180013516  mov     [rbp+50h+var_40], rax
0x18001351a  xor     r15d, r15d
0x18001351d  mov     [rsp+150h+var_F0], rcx
0x180013522  mov     rsi, rcx
0x180013525  mov     [rsp+150h+var_100], r15d
0x18001352a  lea     rcx, [rbp+50h+var_78]
0x18001352e  mov     [rsp+150h+var_104], r15d
0x180013533  mov     [rsp+150h+String1], r15
0x180013538  mov     r13d, r9d
0x18001353b  mov     [rsp+150h+var_120], r15
0x180013540  mov     rdi, rdx
0x180013543  mov     [rsp+150h+var_F8], r8
0x180013548  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001354e  lea     rcx, [rbp+50h+var_B0]
0x180013552  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180013558  lea     rcx, [rsp+150h+var_E8]
0x18001355d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180013563  lea     edx, [r15+1]; enum XmlNodeType
0x180013567  mov     [rsp+150h+var_110], r15d
0x18001356c  mov     rcx, rdi; struct IXmlReader *
0x18001356f  mov     [rsp+150h+var_10C], r15d
0x180013574  mov     [rsp+150h+var_108], r15d
0x180013579  call    ?XmlFindNodeByType@@YAJPEAUIXmlReader@@W4XmlNodeType@@@Z; XmlFindNodeByType(IXmlReader *,XmlNodeType)
0x18001357e  mov     ebx, eax
0x180013580  test    eax, eax
0x180013582  js      loc_1800137DC
0x180013588  lea     r8, aPropertyupdate; "propertyupdate"
0x18001358f  mov     rcx, rdi; struct IXmlReader *
0x180013592  call    ?XmlCheckNodeName@@YAJPEAUIXmlReader@@PEBG1@Z; XmlCheckNodeName(IXmlReader *,ushort const *,ushort const *)
0x180013597  mov     ebx, eax
0x180013599  test    eax, eax
0x18001359b  js      loc_1800137DC
0x1800135a1  lea     r8, [rsp+150h+var_108]; int *
0x1800135a6  mov     rcx, rdi; struct IXmlReader *
0x1800135a9  lea     rdx, [rbp+50h+var_78]; struct STRU *
0x1800135ad  call    ?XmlFindLanguageTag@@YAJPEAUIXmlReader@@PEAVSTRU@@PEAH@Z; XmlFindLanguageTag(IXmlReader *,STRU *,int *)
0x1800135b2  mov     ebx, eax
0x1800135b4  test    eax, eax
0x1800135b6  js      loc_1800137DC
0x1800135bc  lea     r9, [rsp+150h+var_120]; unsigned __int16 **
0x1800135c1  mov     rcx, rdi; struct IXmlReader *
0x1800135c4  lea     r8, [rsp+150h+String1]; unsigned __int16 **
0x1800135c9  mov     r14d, r15d
0x1800135cc  lea     rdx, [rsp+150h+var_100]; unsigned int *
0x1800135d1  call    ?XmlFindFirstSubElement@@YAJPEAUIXmlReader@@PEAIPEAPEBG2@Z; XmlFindFirstSubElement(IXmlReader *,uint *,ushort const * *,ushort const * *)
0x1800135d6  mov     ebx, eax
0x1800135d8  cmp     eax, 1
0x1800135db  jz      loc_180013791
0x1800135e1  test    ebx, ebx
0x1800135e3  js      loc_1800137DC
0x1800135e9  mov     rcx, [rsp+150h+String1]; String1
0x1800135ee  lea     rdx, aDav; "DAV:"
0x1800135f5  call    wcscmp_0
0x1800135fa  test    eax, eax
0x1800135fc  jnz     loc_18001376B
0x180013602  mov     rsi, [rsp+150h+var_120]
0x180013607  lea     rdx, aSet; "set"
0x18001360e  mov     rcx, rsi; String1
0x180013611  call    wcscmp_0
0x180013616  test    eax, eax
0x180013618  jz      short loc_180013631
0x18001361a  lea     rdx, aRemove; "remove"
0x180013621  mov     rcx, rsi; String1
0x180013624  call    wcscmp_0
0x180013629  test    eax, eax
0x18001362b  jnz     loc_18001376B
0x180013631  movzx   r12d, word ptr [rsi]
0x180013635  lea     r8, [rsp+150h+var_10C]; int *
0x18001363a  lea     rdx, [rbp+50h+var_B0]; struct STRU *
0x18001363e  mov     rcx, rdi; struct IXmlReader *
0x180013641  call    ?XmlFindLanguageTag@@YAJPEAUIXmlReader@@PEAVSTRU@@PEAH@Z; XmlFindLanguageTag(IXmlReader *,STRU *,int *)
0x180013646  mov     ebx, eax
0x180013648  test    eax, eax
0x18001364a  js      short loc_18001366A
0x18001364c  lea     r9, [rsp+150h+var_120]; unsigned __int16 **
0x180013651  mov     rcx, rdi; struct IXmlReader *
0x180013654  lea     r8, [rsp+150h+String1]; unsigned __int16 **
0x180013659  lea     rdx, [rsp+150h+var_104]; unsigned int *
0x18001365e  call    ?XmlFindFirstSubElement@@YAJPEAUIXmlReader@@PEAIPEAPEBG2@Z; XmlFindFirstSubElement(IXmlReader *,uint *,ushort const * *,ushort const * *)
0x180013663  mov     rsi, [rsp+150h+var_120]
0x180013668  mov     ebx, eax
0x18001366a  cmp     ebx, 1
0x18001366d  jz      loc_180013849
0x180013673  test    ebx, ebx
0x180013675  js      loc_1800137DC
0x18001367b  mov     rcx, [rsp+150h+String1]; String1
0x180013680  lea     rdx, aDav; "DAV:"
0x180013687  call    wcscmp_0
0x18001368c  test    eax, eax
0x18001368e  jnz     loc_180013738
0x180013694  lea     rdx, aProp; "prop"
0x18001369b  mov     rcx, rsi; String1
0x18001369e  call    wcscmp_0
0x1800136a3  test    eax, eax
0x1800136a5  jnz     loc_180013738
0x1800136ab  test    r15d, r15d
0x1800136ae  jz      short loc_1800136BA
0x1800136b0  test    r13b, 2
0x1800136b4  jz      loc_180013824
0x1800136ba  mov     rcx, rdi; struct IXmlReader *
0x1800136bd  cmp     r12w, 73h ; 's'
0x1800136c2  jnz     short loc_180013716
0x1800136c4  lea     r8, [rsp+150h+var_110]; int *
0x1800136c9  lea     rdx, [rsp+150h+var_E8]; struct STRU *
0x1800136ce  call    ?XmlFindLanguageTag@@YAJPEAUIXmlReader@@PEAVSTRU@@PEAH@Z; XmlFindLanguageTag(IXmlReader *,STRU *,int *)
0x1800136d3  mov     ebx, eax
0x1800136d5  test    eax, eax
0x1800136d7  js      loc_1800137DC
0x1800136dd  cmp     [rsp+150h+var_110], 0
0x1800136e2  jz      short loc_1800136EA
0x1800136e4  mov     r8, [rbp+50h+var_C8]
0x1800136e8  jmp     short loc_180013704
0x1800136ea  cmp     [rsp+150h+var_10C], 0
0x1800136ef  jz      short loc_1800136F7
0x1800136f1  mov     r8, [rbp+50h+var_90]
0x1800136f5  jmp     short loc_180013704
0x1800136f7  mov     eax, [rsp+150h+var_108]
0x1800136fb  neg     eax
0x1800136fd  sbb     r8, r8
0x180013700  and     r8, [rbp+50h+var_58]; unsigned __int16 *
0x180013704  mov     rdx, [rsp+150h+var_F8]; struct DAV_NAMESPACE_SET *
0x180013709  mov     r9d, r13d; unsigned int
0x18001370c  mov     rcx, rdi; struct IXmlReader *
0x18001370f  call    ?ParseSetElement@@YAJPEAUIXmlReader@@PEAVDAV_NAMESPACE_SET@@PEBGK@Z; ParseSetElement(IXmlReader *,DAV_NAMESPACE_SET *,ushort const *,ulong)
0x180013714  jmp     short loc_180013723
0x180013716  mov     rdx, [rsp+150h+var_F8]; struct DAV_NAMESPACE_SET *
0x18001371b  mov     r8d, r13d; unsigned int
0x18001371e  call    ?AddXmlElementsToNamespaceSet@@YAJPEAUIXmlReader@@PEAVDAV_NAMESPACE_SET@@K@Z; AddXmlElementsToNamespaceSet(IXmlReader *,DAV_NAMESPACE_SET *,ulong)
0x180013723  mov     ebx, eax
0x180013725  mov     eax, 1
0x18001372a  mov     r15d, eax
0x18001372d  mov     r14d, eax
0x180013730  test    ebx, ebx
0x180013732  js      loc_1800137DC
0x180013738  mov     edx, [rsp+150h+var_104]; unsigned int
0x18001373c  lea     r9, [rsp+150h+var_120]; unsigned __int16 **
0x180013741  lea     r8, [rsp+150h+String1]; unsigned __int16 **
0x180013746  mov     rcx, rdi; struct IXmlReader *
0x180013749  call    ?XmlFindNextSubElement@@YAJPEAUIXmlReader@@IPEAPEBG1@Z; XmlFindNextSubElement(IXmlReader *,uint,ushort const * *,ushort const * *)
0x18001374e  mov     ebx, eax
0x180013750  cmp     eax, 1
0x180013753  jz      short loc_18001375F
0x180013755  mov     rsi, [rsp+150h+var_120]
0x18001375a  jmp     loc_180013673
0x18001375f  test    r15d, r15d
0x180013762  jz      loc_180013849
0x180013768  xor     r15d, r15d
0x18001376b  mov     edx, [rsp+150h+var_100]; unsigned int
0x18001376f  lea     r9, [rsp+150h+var_120]; unsigned __int16 **
0x180013774  lea     r8, [rsp+150h+String1]; unsigned __int16 **
0x180013779  mov     rcx, rdi; struct IXmlReader *
0x18001377c  call    ?XmlFindNextSubElement@@YAJPEAUIXmlReader@@IPEAPEBG1@Z; XmlFindNextSubElement(IXmlReader *,uint,ushort const * *,ushort const * *)
0x180013781  mov     ebx, eax
0x180013783  cmp     eax, 1
0x180013786  jnz     loc_1800135E1
0x18001378c  mov     rsi, [rsp+150h+var_F0]
0x180013791  mov     rcx, rdi; struct IXmlReader *
0x180013794  call    ?XmlSkipRemainingNodes@@YAJPEAUIXmlReader@@@Z; XmlSkipRemainingNodes(IXmlReader *)
0x180013799  mov     ebx, eax
0x18001379b  test    eax, eax
0x18001379d  js      short loc_1800137DC
0x18001379f  test    r14d, r14d
0x1800137a2  jnz     short loc_1800137DC
0x1800137a4  mov     rax, [rsi]
0x1800137a7  mov     rcx, rsi
0x1800137aa  mov     ebx, 80070057h
0x1800137af  mov     rax, [rax+110h]
0x1800137b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137bb  lea     rdx, aInvalidEmptyPr; "Invalid Empty PROPPATCH Entity Body"
0x1800137c2  mov     rcx, rax
0x1800137c5  mov     [rsp+150h+var_130], 3
0x1800137ca  mov     rax, [rax]
0x1800137cd  xor     r9d, r9d
0x1800137d0  xor     r8d, r8d
0x1800137d3  mov     rax, [rax+20h]
0x1800137d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137dc  lea     rcx, [rsp+150h+var_E8]
0x1800137e1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800137e7  lea     rcx, [rbp+50h+var_B0]
0x1800137eb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800137f1  lea     rcx, [rbp+50h+var_78]
0x1800137f5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800137fb  mov     eax, ebx
0x1800137fd  mov     rcx, [rbp+50h+var_40]
0x180013801  xor     rcx, rsp; StackCookie
0x180013804  call    __security_check_cookie
0x180013809  mov     rbx, [rsp+150h+arg_18]
0x180013811  add     rsp, 120h
0x180013818  pop     r15
0x18001381a  pop     r14
0x18001381c  pop     r13
0x18001381e  pop     r12
0x180013820  pop     rdi
0x180013821  pop     rsi
0x180013822  pop     rbp
0x180013823  retn
0x180013824  mov     rcx, [rsp+150h+var_F0]
0x180013829  mov     ebx, 80070057h
0x18001382e  mov     rax, [rcx]
0x180013831  mov     rax, [rax+110h]
0x180013838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001383d  lea     rdx, aFoundMultipleP; "Found Multiple <prop> Entries, But Mult"...
0x180013844  jmp     loc_1800137C2
0x180013849  mov     ebx, 80070057h
0x18001384e  jmp     short loc_1800137DC
```
