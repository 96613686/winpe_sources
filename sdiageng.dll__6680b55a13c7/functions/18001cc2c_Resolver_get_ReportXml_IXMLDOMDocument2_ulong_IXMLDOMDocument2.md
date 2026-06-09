# Resolver::get_ReportXml(IXMLDOMDocument2 *,ulong,IXMLDOMDocument2 * *)

- ea: `0x18001cc2c`
- end: `0x18001d08d`
- name: `?get_ReportXml@Resolver@@QEAAJPEAUIXMLDOMDocument2@@KPEAPEAU2@@Z`
- size: `1121`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct IXMLDOMDocument2 *, char, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180018a9c`

## callees

- `0x1800012a4`
- `0x18000571c`
- `0x180005ffc`
- `0x18001cc2c`
- `0x180026fa0`
- `0x180027aa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002827c`
- `0x1800291e0`
- `0x18002a010`

## string_xrefs

- `0x18001ccad`: `<?xml version="1.0" encoding="utf-8"?><Resolution/>`
- `0x18001cc83`: `Resolver::get_ReportXml`
- `0x18001ccc2`: `Resolver::get_ReportXml`
- `0x18001cd0a`: `Resolver::get_ReportXml`
- `0x18001cd60`: `Resolver::get_ReportXml`
- `0x18001ce5c`: `Resolver::get_ReportXml`
- `0x18001cec2`: `Resolver::get_ReportXml`

## pseudocode

```c
__int64 __fastcall Resolver::get_ReportXml(
        const unsigned __int16 **this,
        struct IXMLDOMDocument2 *a2,
        char a3,
        struct IXMLDOMDocument2 **a4)
{
  struct IXMLDOMElement *v4; // rdi
  unsigned __int16 *v5; // r14
  void *v6; // rsi
  int v8; // r8d
  unsigned int v9; // ebx
  int v10; // eax
  struct IXMLDOMDocument2 *v11; // r12
  int v12; // eax
  int v13; // r8d
  int v14; // r9d
  const unsigned __int16 *v15; // rdx
  struct _SDIAG_PARAMSET *v16; // r13
  int v17; // eax
  int v18; // r8d
  const unsigned __int16 *v19; // rdx
  int v20; // eax
  int v21; // r8d
  int v22; // eax
  int v23; // r8d
  bool v24; // zf
  const unsigned __int16 *v25; // r9
  const unsigned __int16 *v26; // rax
  void *Block; // [rsp+30h] [rbp-20h] BYREF
  struct IXMLDOMElement *v29; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v30; // [rsp+40h] [rbp-10h] BYREF
  struct IXMLDOMDocument2 *v31; // [rsp+48h] [rbp-8h] BYREF

  v4 = 0;
  v31 = 0;
  v5 = 0;
  v29 = 0;
  v6 = 0;
  v30 = 0;
  Block = 0;
  if ( !a4 )
  {
    v8 = 729;
LABEL_3:
    v9 = -2147024809;
    SdpDebugTrace(1u, L"Resolver::get_ReportXml", v8, -2147024809);
    return v9;
  }
  if ( !a2 )
  {
    v8 = 730;
    goto LABEL_3;
  }
  v10 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Resolution/>", &v31);
  v9 = v10;
  if ( v10 >= 0 )
  {
    v11 = v31;
    v12 = SdpXmlSetAttribute(v31, 0, L"id", this[2]);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 743;
LABEL_10:
      v14 = v12;
LABEL_11:
      SdpDebugTrace(1u, L"Resolver::get_ReportXml", v13, v14);
      goto LABEL_62;
    }
    v15 = this[4];
    if ( ((_BYTE)this[9] & 2) != 0 )
    {
      if ( !v15 )
      {
        v14 = -2147467261;
        v13 = 750;
        v9 = -2147467261;
        goto LABEL_11;
      }
      v16 = (struct _SDIAG_PARAMSET *)(this + 6);
      v17 = SdpSubstituteParamSet((unsigned __int16 **)&Block, v15, (struct _SDIAG_PARAMSET *)(this + 6));
      v9 = v17;
      if ( v17 < 0 )
      {
        v18 = 754;
LABEL_17:
        SdpDebugTrace(1u, L"Resolver::get_ReportXml", v18, v17);
        v6 = Block;
        goto LABEL_62;
      }
    }
    else
    {
      v17 = SdpStrCpy((unsigned __int16 **)&Block, v15);
      v9 = v17;
      if ( v17 < 0 )
      {
        v18 = 757;
        goto LABEL_17;
      }
      v16 = (struct _SDIAG_PARAMSET *)(this + 6);
    }
    v6 = Block;
    v12 = SdpXmlSetAttribute(v11, 0, L"name", (const unsigned __int16 *)Block);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 763;
      goto LABEL_10;
    }
    if ( v6 )
    {
      operator delete(v6);
      v6 = 0;
      Block = 0;
    }
    v19 = this[5];
    if ( ((_BYTE)this[9] & 2) != 0 )
    {
      if ( !v19 )
      {
        v14 = -2147467261;
        v13 = 776;
        v9 = -2147467261;
        goto LABEL_11;
      }
      v17 = SdpSubstituteParamSet((unsigned __int16 **)&Block, v19, v16);
      v9 = v17;
      if ( v17 < 0 )
      {
        v18 = 780;
        goto LABEL_17;
      }
    }
    else
    {
      v17 = SdpStrCpy((unsigned __int16 **)&Block, v19);
      v9 = v17;
      if ( v17 < 0 )
      {
        v18 = 783;
        goto LABEL_17;
      }
    }
    v6 = Block;
    v20 = SdpXmlCreateNode(v11, 0, L"Data", (const unsigned __int16 *)Block, &v29);
    v9 = v20;
    if ( v20 < 0 )
    {
      v21 = 792;
LABEL_34:
      SdpDebugTrace(1u, L"Resolver::get_ReportXml", v21, v20);
      v4 = v29;
      goto LABEL_62;
    }
    v4 = v29;
    v12 = SdpXmlSetAttribute(0, v29, L"id", L"Description");
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 798;
      goto LABEL_10;
    }
    v22 = SdpLoadString(0, 0x76u, &v30);
    v9 = v22;
    if ( v22 >= 0 )
    {
      v5 = v30;
      v12 = SdpXmlSetAttribute(0, v4, L"name", v30);
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 804;
        goto LABEL_10;
      }
      if ( v4 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
        v29 = 0;
      }
      if ( (a3 & 1) != 0 )
      {
        v24 = (a3 & 4) == 0;
        v25 = L"Succeeded";
        v26 = L"Failed";
      }
      else
      {
        v24 = this[1] == 0;
        v25 = L"Not Run";
        v26 = L"Informational";
      }
      if ( v24 )
        v25 = v26;
      v20 = SdpXmlCreateNode(v11, 0, L"Data", v25, &v29);
      v9 = v20;
      if ( v20 < 0 )
      {
        v21 = 831;
        goto LABEL_34;
      }
      if ( v5 )
      {
        operator delete(v5);
        v5 = 0;
        v30 = 0;
      }
      v4 = v29;
      v12 = SdpXmlSetAttribute(0, v29, L"id", L"Status");
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 839;
        goto LABEL_10;
      }
      v22 = SdpLoadString(0, 0x93u, &v30);
      v9 = v22;
      if ( v22 >= 0 )
      {
        v5 = v30;
        v12 = SdpXmlSetAttribute(0, v4, L"name", v30);
        v9 = v12;
        if ( v12 >= 0 )
        {
          v12 = SdpXmlAppend(v11, 0, a2);
          v9 = v12;
          if ( v12 >= 0 )
          {
            *a4 = v11;
            v11 = 0;
            goto LABEL_62;
          }
          v13 = 852;
        }
        else
        {
          v13 = 845;
        }
        goto LABEL_10;
      }
      v23 = 842;
    }
    else
    {
      v23 = 801;
    }
    SdpDebugTrace(1u, L"Resolver::get_ReportXml", v23, v22);
    v5 = v30;
    goto LABEL_62;
  }
  SdpDebugTrace(1u, L"Resolver::get_ReportXml", 737, v10);
  v11 = v31;
LABEL_62:
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->Release)(v11);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    operator delete(v5);
  if ( v6 )
    operator delete(v6);
  return v9;
}

```

## disassembly

```asm
0x18001cc2c  mov     rax, rsp
0x18001cc2f  mov     [rax+8], rbx
0x18001cc33  mov     [rax+20h], r9
0x18001cc37  mov     [rax+18h], r8d
0x18001cc3b  mov     [rax+10h], rdx
0x18001cc3f  push    rbp
0x18001cc40  push    rsi
0x18001cc41  push    rdi
0x18001cc42  push    r12
0x18001cc44  push    r13
0x18001cc46  push    r14
0x18001cc48  push    r15
0x18001cc4a  mov     rbp, rsp
0x18001cc4d  sub     rsp, 50h
0x18001cc51  xor     edi, edi
0x18001cc53  mov     [rbp+var_8], 0
0x18001cc5b  xor     r14d, r14d
0x18001cc5e  mov     [rbp+var_18], rdi
0x18001cc62  xor     esi, esi
0x18001cc64  mov     [rbp+var_10], r14
0x18001cc68  mov     [rbp+Block], rsi
0x18001cc6c  mov     rax, rdx
0x18001cc6f  mov     r15, rcx
0x18001cc72  test    r9, r9
0x18001cc75  jnz     short loc_18001CC9C
0x18001cc77  mov     r8d, 2D9h; int
0x18001cc7d  mov     r9d, 80070057h; int
0x18001cc83  lea     rdx, aResolverGetRep; "Resolver::get_ReportXml"
0x18001cc8a  mov     ecx, 1; Level
0x18001cc8f  mov     ebx, r9d
0x18001cc92  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001cc97  jmp     loc_18001D073
0x18001cc9c  test    rax, rax
0x18001cc9f  jnz     short loc_18001CCA9
0x18001cca1  mov     r8d, 2DAh
0x18001cca7  jmp     short loc_18001CC7D
0x18001cca9  lea     rdx, [rbp+var_8]; struct IXMLDOMDocument2 **
0x18001ccad  lea     rcx, aXmlVersion10En_19; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001ccb4  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18001ccb9  mov     ebx, eax
0x18001ccbb  test    eax, eax
0x18001ccbd  jns     short loc_18001CCE2
0x18001ccbf  mov     r9d, eax; int
0x18001ccc2  lea     rdx, aResolverGetRep; "Resolver::get_ReportXml"
0x18001ccc9  mov     r8d, 2E1h; int
0x18001cccf  mov     ecx, 1; Level
0x18001ccd4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001ccd9  mov     r12, [rbp+var_8]
0x18001ccdd  jmp     loc_18001D030
0x18001cce2  mov     r12, [rbp+var_8]
0x18001cce6  lea     r8, aId_0; "id"
0x18001cced  mov     r9, [r15+10h]; unsigned __int16 *
0x18001ccf1  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18001ccf4  xor     edx, edx; struct IXMLDOMElement *
0x18001ccf6  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001ccfb  mov     ebx, eax
0x18001ccfd  test    eax, eax
0x18001ccff  jns     short loc_18001CD20
0x18001cd01  mov     r8d, 2E7h; int
0x18001cd07  mov     r9d, eax; int
0x18001cd0a  lea     rdx, aResolverGetRep; "Resolver::get_ReportXml"
0x18001cd11  mov     ecx, 1; Level
0x18001cd16  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001cd1b  jmp     loc_18001D030
0x18001cd20  test    byte ptr [r15+48h], 2
0x18001cd25  mov     rdx, [r15+20h]; unsigned __int16 *
0x18001cd29  jz      short loc_18001CD7A
0x18001cd2b  test    rdx, rdx
0x18001cd2e  jnz     short loc_18001CD41
0x18001cd30  mov     r9d, 80004003h
0x18001cd36  mov     r8d, 2EEh
0x18001cd3c  mov     ebx, r9d
0x18001cd3f  jmp     short loc_18001CD0A
0x18001cd41  lea     r13, [r15+30h]
0x18001cd45  mov     r8, r13; struct _SDIAG_PARAMSET *
0x18001cd48  lea     rcx, [rbp+Block]; unsigned __int16 **
0x18001cd4c  call    ?SdpSubstituteParamSet@@YAJPEAPEAGPEBGPEAU_SDIAG_PARAMSET@@@Z; SdpSubstituteParamSet(ushort * *,ushort const *,_SDIAG_PARAMSET *)
0x18001cd51  mov     ebx, eax
0x18001cd53  test    eax, eax
0x18001cd55  jns     short loc_18001CD95
0x18001cd57  mov     r8d, 2F2h; int
0x18001cd5d  mov     r9d, eax; int
0x18001cd60  lea     rdx, aResolverGetRep; "Resolver::get_ReportXml"
0x18001cd67  mov     ecx, 1; Level
0x18001cd6c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001cd71  mov     rsi, [rbp+Block]
0x18001cd75  jmp     loc_18001D030
0x18001cd7a  lea     rcx, [rbp+Block]; unsigned __int16 **
0x18001cd7e  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001cd83  mov     ebx, eax
0x18001cd85  test    eax, eax
0x18001cd87  jns     short loc_18001CD91
0x18001cd89  mov     r8d, 2F5h
0x18001cd8f  jmp     short loc_18001CD5D
0x18001cd91  lea     r13, [r15+30h]
0x18001cd95  mov     rsi, [rbp+Block]
0x18001cd99  lea     r8, aName_0; "name"
0x18001cda0  mov     r9, rsi; unsigned __int16 *
0x18001cda3  xor     edx, edx; struct IXMLDOMElement *
0x18001cda5  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18001cda8  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001cdad  mov     ebx, eax
0x18001cdaf  test    eax, eax
0x18001cdb1  jns     short loc_18001CDBE
0x18001cdb3  mov     r8d, 2FBh
0x18001cdb9  jmp     loc_18001CD07
0x18001cdbe  test    rsi, rsi
0x18001cdc1  jz      short loc_18001CDD1
0x18001cdc3  mov     rcx, rsi; Block
0x18001cdc6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cdcb  xor     esi, esi
0x18001cdcd  mov     [rbp+Block], rsi
0x18001cdd1  test    byte ptr [r15+48h], 2
0x18001cdd6  mov     rdx, [r15+28h]; unsigned __int16 *
0x18001cdda  jz      short loc_18001CE12
0x18001cddc  test    rdx, rdx
0x18001cddf  jnz     short loc_18001CDF5
0x18001cde1  mov     r9d, 80004003h
0x18001cde7  mov     r8d, 308h
0x18001cded  mov     ebx, r9d
0x18001cdf0  jmp     loc_18001CD0A
0x18001cdf5  mov     r8, r13; struct _SDIAG_PARAMSET *
0x18001cdf8  lea     rcx, [rbp+Block]; unsigned __int16 **
0x18001cdfc  call    ?SdpSubstituteParamSet@@YAJPEAPEAGPEBGPEAU_SDIAG_PARAMSET@@@Z; SdpSubstituteParamSet(ushort * *,ushort const *,_SDIAG_PARAMSET *)
0x18001ce01  mov     ebx, eax
0x18001ce03  test    eax, eax
0x18001ce05  jns     short loc_18001CE2C
0x18001ce07  mov     r8d, 30Ch
0x18001ce0d  jmp     loc_18001CD5D
0x18001ce12  lea     rcx, [rbp+Block]; unsigned __int16 **
0x18001ce16  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001ce1b  mov     ebx, eax
0x18001ce1d  test    eax, eax
0x18001ce1f  jns     short loc_18001CE2C
0x18001ce21  mov     r8d, 30Fh
0x18001ce27  jmp     loc_18001CD5D
0x18001ce2c  mov     rsi, [rbp+Block]
0x18001ce30  lea     rax, [rbp+var_18]
0x18001ce34  mov     r9, rsi; unsigned __int16 *
0x18001ce37  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x18001ce3c  lea     r8, aData; "Data"
0x18001ce43  xor     edx, edx; struct IXMLDOMElement *
0x18001ce45  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18001ce48  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001ce4d  mov     ebx, eax
0x18001ce4f  test    eax, eax
0x18001ce51  jns     short loc_18001CE76
0x18001ce53  mov     r8d, 318h; int
0x18001ce59  mov     r9d, eax; int
0x18001ce5c  lea     rdx, aResolverGetRep; "Resolver::get_ReportXml"
0x18001ce63  mov     ecx, 1; Level
0x18001ce68  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001ce6d  mov     rdi, [rbp+var_18]
0x18001ce71  jmp     loc_18001D030
0x18001ce76  mov     rdi, [rbp+var_18]
0x18001ce7a  lea     r9, aDescription; "Description"
0x18001ce81  mov     rdx, rdi; struct IXMLDOMElement *
0x18001ce84  lea     r8, aId_0; "id"
0x18001ce8b  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001ce8d  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001ce92  mov     ebx, eax
0x18001ce94  test    eax, eax
0x18001ce96  jns     short loc_18001CEA3
0x18001ce98  mov     r8d, 31Eh
0x18001ce9e  jmp     loc_18001CD07
0x18001cea3  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18001cea7  mov     edx, 76h ; 'v'; unsigned int
0x18001ceac  xor     ecx, ecx; unsigned __int16 *
0x18001ceae  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x18001ceb3  mov     ebx, eax
0x18001ceb5  test    eax, eax
0x18001ceb7  jns     short loc_18001CEDC
0x18001ceb9  mov     r8d, 321h; int
0x18001cebf  mov     r9d, eax; int
0x18001cec2  lea     rdx, aResolverGetRep; "Resolver::get_ReportXml"
0x18001cec9  mov     ecx, 1; Level
0x18001cece  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001ced3  mov     r14, [rbp+var_10]
0x18001ced7  jmp     loc_18001D030
0x18001cedc  mov     r14, [rbp+var_10]
0x18001cee0  lea     r8, aName_0; "name"
0x18001cee7  mov     r9, r14; unsigned __int16 *
0x18001ceea  mov     rdx, rdi; struct IXMLDOMElement *
0x18001ceed  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001ceef  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001cef4  mov     ebx, eax
0x18001cef6  test    eax, eax
0x18001cef8  jns     short loc_18001CF05
0x18001cefa  mov     r8d, 324h
0x18001cf00  jmp     loc_18001CD07
0x18001cf05  test    rdi, rdi
0x18001cf08  jz      short loc_18001CF21
0x18001cf0a  mov     rax, [rdi]
0x18001cf0d  mov     rcx, rdi
0x18001cf10  mov     rax, [rax+10h]
0x18001cf14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf19  mov     [rbp+var_18], 0
0x18001cf21  mov     eax, [rbp+arg_10]
0x18001cf24  test    al, 1
0x18001cf26  jz      short loc_18001CF3A
0x18001cf28  test    al, 4
0x18001cf2a  lea     r9, aSucceeded; "Succeeded"
0x18001cf31  lea     rax, aFailed; "Failed"
0x18001cf38  jmp     short loc_18001CF4D
0x18001cf3a  cmp     qword ptr [r15+8], 0
0x18001cf3f  lea     r9, aNotRun; "Not Run"
0x18001cf46  lea     rax, aInformational; "Informational"
0x18001cf4d  cmovz   r9, rax; unsigned __int16 *
0x18001cf51  lea     r8, aData; "Data"
0x18001cf58  lea     rax, [rbp+var_18]
0x18001cf5c  xor     edx, edx; struct IXMLDOMElement *
0x18001cf5e  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18001cf61  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x18001cf66  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001cf6b  mov     ebx, eax
0x18001cf6d  test    eax, eax
0x18001cf6f  jns     short loc_18001CF7C
0x18001cf71  mov     r8d, 33Fh
0x18001cf77  jmp     loc_18001CE59
0x18001cf7c  test    r14, r14
0x18001cf7f  jz      short loc_18001CF90
0x18001cf81  mov     rcx, r14; Block
0x18001cf84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cf89  xor     r14d, r14d
0x18001cf8c  mov     [rbp+var_10], r14
0x18001cf90  mov     rdi, [rbp+var_18]
0x18001cf94  lea     r9, aStatus; "Status"
0x18001cf9b  mov     rdx, rdi; struct IXMLDOMElement *
0x18001cf9e  lea     r8, aId_0; "id"
0x18001cfa5  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001cfa7  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001cfac  mov     ebx, eax
0x18001cfae  test    eax, eax
0x18001cfb0  jns     short loc_18001CFBD
0x18001cfb2  mov     r8d, 347h
0x18001cfb8  jmp     loc_18001CD07
0x18001cfbd  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18001cfc1  mov     edx, 93h; unsigned int
0x18001cfc6  xor     ecx, ecx; unsigned __int16 *
0x18001cfc8  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x18001cfcd  mov     ebx, eax
0x18001cfcf  test    eax, eax
0x18001cfd1  jns     short loc_18001CFDE
0x18001cfd3  mov     r8d, 34Ah
0x18001cfd9  jmp     loc_18001CEBF
0x18001cfde  mov     r14, [rbp+var_10]
0x18001cfe2  lea     r8, aName_0; "name"
0x18001cfe9  mov     r9, r14; unsigned __int16 *
0x18001cfec  mov     rdx, rdi; struct IXMLDOMElement *
0x18001cfef  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001cff1  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001cff6  mov     ebx, eax
0x18001cff8  test    eax, eax
0x18001cffa  jns     short loc_18001D007
0x18001cffc  mov     r8d, 34Dh
0x18001d002  jmp     loc_18001CD07
0x18001d007  mov     r8, [rbp+arg_8]; struct IXMLDOMDocument2 *
0x18001d00b  xor     edx, edx; struct IXMLDOMElement *
0x18001d00d  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18001d010  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001d015  mov     ebx, eax
0x18001d017  test    eax, eax
0x18001d019  jns     short loc_18001D026
0x18001d01b  mov     r8d, 354h
0x18001d021  jmp     loc_18001CD07
0x18001d026  mov     rax, [rbp+arg_18]
0x18001d02a  mov     [rax], r12
0x18001d02d  xor     r12d, r12d
0x18001d030  test    r12, r12
0x18001d033  jz      short loc_18001D045
0x18001d035  mov     rax, [r12]
0x18001d039  mov     rcx, r12
0x18001d03c  mov     rax, [rax+10h]
0x18001d040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d045  test    rdi, rdi
0x18001d048  jz      short loc_18001D059
0x18001d04a  mov     rax, [rdi]
0x18001d04d  mov     rcx, rdi
0x18001d050  mov     rax, [rax+10h]
0x18001d054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d059  test    r14, r14
0x18001d05c  jz      short loc_18001D066
0x18001d05e  mov     rcx, r14; Block
0x18001d061  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d066  test    rsi, rsi
0x18001d069  jz      short loc_18001D073
0x18001d06b  mov     rcx, rsi; Block
0x18001d06e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d073  mov     eax, ebx
0x18001d075  mov     rbx, [rsp+50h+arg_0]
0x18001d07d  add     rsp, 50h
0x18001d081  pop     r15
0x18001d083  pop     r14
0x18001d085  pop     r13
0x18001d087  pop     r12
0x18001d089  pop     rdi
0x18001d08a  pop     rsi
0x18001d08b  pop     rbp
0x18001d08c  retn
```
