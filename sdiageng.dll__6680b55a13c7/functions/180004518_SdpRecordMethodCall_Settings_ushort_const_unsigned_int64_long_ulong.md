# SdpRecordMethodCall(Settings *,ushort const *,unsigned __int64,long,ulong,...)

- ea: `0x180004518`
- end: `0x180004d51`
- name: `?SdpRecordMethodCall@@YAJPEAVSettings@@PEBG_KJKZZ`
- size: `2105`
- prototype: `__int64(struct Settings *, const unsigned __int16 *, __int64, unsigned int, unsigned int, ...)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x18000ad80`
- `0x18000cf00`
- `0x18000fcf0`
- `0x180011630`

## callees

- `0x1800012a4`
- `0x180002978`
- `0x180004380`
- `0x180004518`
- `0x18000533c`
- `0x180005ffc`
- `0x18002146c`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002827c`
- `0x1800291e0`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000465e`
- `msvcrt!_wcsicmp` at `0x18000469b`
- `msvcrt!_wcsicmp` at `0x1800046d8`
- `msvcrt!_wcsicmp` at `0x180004711`
- `msvcrt!_wcsicmp` at `0x180004af2`
- `msvcrt!_wcsicmp` at `0x180004b31`
- `msvcrt!_wcsicmp` at `0x180004b70`
- `msvcrt!_wcsicmp` at `0x180004bab`
- `msvcrt!_wcsicmp` at `0x180004be6`
- `msvcrt!_wcsicmp` at `0x18000465e`
- `msvcrt!_wcsicmp` at `0x18000469b`
- `msvcrt!_wcsicmp` at `0x1800046d8`
- `msvcrt!_wcsicmp` at `0x180004711`
- `msvcrt!_wcsicmp` at `0x180004af2`
- `msvcrt!_wcsicmp` at `0x180004b31`
- `msvcrt!_wcsicmp` at `0x180004b70`
- `msvcrt!_wcsicmp` at `0x180004bab`
- `msvcrt!_wcsicmp` at `0x180004be6`

## string_xrefs

- `0x180004607`: `<?xml version="1.0" encoding="utf-8"?><Function/>`
- `0x180004b69`: `PackagePath`

## pseudocode

```c
__int64 SdpRecordMethodCall(
        struct Settings *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        ...)
{
  struct IXMLDOMElement *v9; // rsi
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  struct IXMLDOMDocument2 *v13; // r12
  int v14; // r9d
  unsigned int v15; // r8d
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int String; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // r8d
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  __int64 v34; // r15
  struct _SDIAG_VARARG *v35; // r13
  IRecordInfo *v36; // xmm1_8
  int v37; // eax
  struct IXMLDOMElement *v38; // rdx
  void *v39; // rdi
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  struct IXMLDOMElement *v50; // [rsp+38h] [rbp-C8h] BYREF
  struct IXMLDOMElement *v51; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMElement *v52; // [rsp+48h] [rbp-B8h] BYREF
  struct _SDIAG_VARARG *v53; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMDocument2 *v54; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v55; // [rsp+60h] [rbp-A0h]
  struct tagVARIANT v56; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v57[1024]; // [rsp+90h] [rbp-70h] BYREF
  va_list va; // [rsp+918h] [rbp+818h] BYREF

  va_start(va, a5);
  v54 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v9 = 0;
  Block = 0;
  v55 = 0;
  v53 = 0;
  if ( !a2 )
  {
    v10 = -2147024809;
    SdpDebugTrace(1u, L"SdpRecordMethodCall", 0x399u, -2147024809);
    return v10;
  }
  if ( !a1 )
    return 1;
  v11 = SdpParseVariableArgs(&v53, a5, va);
  v10 = v11;
  if ( v11 < 0 )
  {
    SdpDebugTrace(1u, L"SdpRecordMethodCall", 0x3ACu, v11);
    goto LABEL_108;
  }
  v55 = *((_QWORD *)a1 + 9);
  if ( v55 )
  {
    v12 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Function/>", &v54);
    v13 = v54;
    v10 = v12;
    if ( v12 < 0 )
    {
      v14 = v12;
      v15 = 959;
LABEL_97:
      SdpDebugTrace(1u, L"SdpRecordMethodCall", v15, v14);
      goto LABEL_98;
    }
    v16 = SdpXmlSetAttribute(v54, 0, L"id", a2);
    v10 = v16;
    if ( v16 < 0 )
    {
      v14 = v16;
      v15 = 965;
      goto LABEL_97;
    }
    if ( _wcsicmp(a2, L"Initialize") )
    {
      if ( _wcsicmp(a2, L"Diagnose") )
      {
        if ( _wcsicmp(a2, L"Resolve") )
        {
          if ( _wcsicmp(a2, L"Verify") )
          {
            v15 = 984;
LABEL_96:
            v14 = -2147024809;
            v10 = -2147024809;
            goto LABEL_97;
          }
          String = SdpLoadString(0, 0x87u, (unsigned __int16 **)&Block);
          v10 = String;
          if ( String < 0 )
          {
            v14 = String;
            v15 = 982;
            goto LABEL_97;
          }
        }
        else
        {
          v19 = SdpLoadString(0, 0x86u, (unsigned __int16 **)&Block);
          v10 = v19;
          if ( v19 < 0 )
          {
            v14 = v19;
            v15 = 979;
            goto LABEL_97;
          }
        }
      }
      else
      {
        v18 = SdpLoadString(0, 0x85u, (unsigned __int16 **)&Block);
        v10 = v18;
        if ( v18 < 0 )
        {
          v14 = v18;
          v15 = 976;
          goto LABEL_97;
        }
      }
    }
    else
    {
      v17 = SdpLoadString(0, 0x84u, (unsigned __int16 **)&Block);
      v10 = v17;
      if ( v17 < 0 )
      {
        v14 = v17;
        v15 = 973;
        goto LABEL_97;
      }
    }
    v21 = SdpXmlSetAttribute(v13, 0, L"name", (const unsigned __int16 *)Block);
    v10 = v21;
    if ( v21 < 0 )
    {
      v14 = v21;
      v15 = 988;
      goto LABEL_97;
    }
    if ( Block )
    {
      operator delete(Block);
      Block = 0;
    }
    v22 = StringCchPrintfW(v57, 0x400u, L"%I64u", a3);
    v10 = v22;
    if ( v22 < 0 )
    {
      v14 = v22;
      v15 = 998;
      goto LABEL_97;
    }
    v23 = SdpXmlCreateNode(v13, 0, L"Data", v57, &v50);
    v10 = v23;
    if ( v23 >= 0 )
    {
      v9 = v50;
      v25 = SdpXmlSetAttribute(0, v50, L"id", L"RunningTime");
      v10 = v25;
      if ( v25 < 0 )
      {
        v14 = v25;
        v15 = 1011;
        goto LABEL_97;
      }
      v26 = SdpLoadString(0, 0x6Au, (unsigned __int16 **)&Block);
      v10 = v26;
      if ( v26 < 0 )
      {
        v14 = v26;
        v15 = 1014;
        goto LABEL_97;
      }
      v27 = SdpXmlSetAttribute(0, v9, L"name", (const unsigned __int16 *)Block);
      v10 = v27;
      if ( v27 < 0 )
      {
        v14 = v27;
        v15 = 1017;
        goto LABEL_97;
      }
      if ( v9 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v9->lpVtbl->Release)(v9);
        v9 = 0;
        v50 = 0;
      }
      if ( Block )
      {
        operator delete(Block);
        Block = 0;
      }
      v28 = StringCchPrintfW(v57, 0x400u, L"0x%X", a4);
      v10 = v28;
      if ( v28 < 0 )
      {
        v14 = v28;
        v15 = 1027;
        goto LABEL_97;
      }
      v23 = SdpXmlCreateNode(v13, 0, L"Data", v57, &v50);
      v10 = v23;
      if ( v23 >= 0 )
      {
        v9 = v50;
        v29 = SdpXmlSetAttribute(0, v50, L"id", L"StatusCode");
        v10 = v29;
        if ( v29 < 0 )
        {
          v14 = v29;
          v15 = 1040;
          goto LABEL_97;
        }
        v30 = SdpLoadString(0, 0x6Bu, (unsigned __int16 **)&Block);
        v10 = v30;
        if ( v30 < 0 )
        {
          v14 = v30;
          v15 = 1043;
          goto LABEL_97;
        }
        v31 = SdpXmlSetAttribute(0, v9, L"name", (const unsigned __int16 *)Block);
        v10 = v31;
        if ( v31 < 0 )
        {
          v14 = v31;
          v15 = 1046;
          goto LABEL_97;
        }
        v32 = SdpXmlCreateNode(v13, 0, L"InputArguments", 0, &v51);
        v10 = v32;
        if ( v32 < 0 )
        {
          v14 = v32;
          v15 = 1057;
          goto LABEL_97;
        }
        v33 = SdpXmlCreateNode(v13, 0, L"OutputArguments", 0, &v52);
        v10 = v33;
        if ( v33 < 0 )
        {
          v14 = v33;
          v15 = 1068;
          goto LABEL_97;
        }
        v34 = 0;
        if ( a5 )
        {
          v35 = v53;
          while ( 1 )
          {
            if ( v9 )
            {
              ((void (__fastcall *)(struct IXMLDOMElement *))v9->lpVtbl->Release)(v9);
              v9 = 0;
              v50 = 0;
            }
            if ( Block )
            {
              operator delete(Block);
              Block = 0;
            }
            v36 = (IRecordInfo *)*((_QWORD *)v35 + 5 * v34 + 3);
            *(_OWORD *)&v56.vt = *(_OWORD *)((char *)v35 + 40 * v34 + 8);
            v56.pRecInfo = v36;
            v37 = SdpVariantToString(&v56, (unsigned __int16 **)&Block);
            v10 = v37;
            if ( v37 < 0 )
              break;
            v38 = v52;
            v39 = Block;
            if ( *((_DWORD *)v35 + 10 * v34 + 8) )
              v38 = v51;
            v23 = SdpXmlCreateNode(v13, v38, L"Data", (const unsigned __int16 *)Block, &v50);
            v10 = v23;
            if ( v23 < 0 )
            {
              v24 = 1096;
              goto LABEL_33;
            }
            v9 = v50;
            v40 = SdpXmlSetAttribute(0, v50, L"id", *((const unsigned __int16 **)v35 + 5 * v34));
            v10 = v40;
            if ( v40 < 0 )
            {
              v14 = v40;
              v15 = 1102;
              goto LABEL_97;
            }
            if ( v39 )
            {
              operator delete(v39);
              Block = 0;
            }
            if ( _wcsicmp(*((const wchar_t **)v35 + 5 * v34), L"Answer") )
            {
              if ( _wcsicmp(*((const wchar_t **)v35 + 5 * v34), L"Client") )
              {
                if ( _wcsicmp(*((const wchar_t **)v35 + 5 * v34), L"PackagePath") )
                {
                  if ( _wcsicmp(*((const wchar_t **)v35 + 5 * v34), L"ResolutionId") )
                  {
                    if ( _wcsicmp(*((const wchar_t **)v35 + 5 * v34), L"Result") )
                    {
                      v15 = 1126;
                      goto LABEL_96;
                    }
                    v45 = SdpLoadString(0, 0x8Du, (unsigned __int16 **)&Block);
                    v10 = v45;
                    if ( v45 < 0 )
                    {
                      v14 = v45;
                      v15 = 1124;
                      goto LABEL_97;
                    }
                  }
                  else
                  {
                    v44 = SdpLoadString(0, 0x8Cu, (unsigned __int16 **)&Block);
                    v10 = v44;
                    if ( v44 < 0 )
                    {
                      v14 = v44;
                      v15 = 1121;
                      goto LABEL_97;
                    }
                  }
                }
                else
                {
                  v43 = SdpLoadString(0, 0x8Bu, (unsigned __int16 **)&Block);
                  v10 = v43;
                  if ( v43 < 0 )
                  {
                    v14 = v43;
                    v15 = 1118;
                    goto LABEL_97;
                  }
                }
              }
              else
              {
                v42 = SdpLoadString(0, 0x89u, (unsigned __int16 **)&Block);
                v10 = v42;
                if ( v42 < 0 )
                {
                  v14 = v42;
                  v15 = 1115;
                  goto LABEL_97;
                }
              }
            }
            else
            {
              v41 = SdpLoadString(0, 0x88u, (unsigned __int16 **)&Block);
              v10 = v41;
              if ( v41 < 0 )
              {
                v14 = v41;
                v15 = 1112;
                goto LABEL_97;
              }
            }
            v46 = SdpXmlSetAttribute(0, v9, L"name", (const unsigned __int16 *)Block);
            v10 = v46;
            if ( v46 < 0 )
            {
              v14 = v46;
              v15 = 1133;
              goto LABEL_97;
            }
            v34 = (unsigned int)(v34 + 1);
            if ( (unsigned int)v34 >= a5 )
              goto LABEL_87;
          }
          v14 = v37;
          v15 = 1083;
          goto LABEL_97;
        }
LABEL_87:
        v47 = Reporter::AddXmlToReport(v55, v13, 1);
        v10 = v47;
        if ( v47 < 0 )
        {
          v14 = v47;
          v15 = 1137;
          goto LABEL_97;
        }
LABEL_98:
        if ( v13 )
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v13->lpVtbl->Release)(v13);
        if ( v9 )
          ((void (__fastcall *)(struct IXMLDOMElement *))v9->lpVtbl->Release)(v9);
        if ( v51 )
          ((void (__fastcall *)(struct IXMLDOMElement *))v51->lpVtbl->Release)(v51);
        if ( v52 )
          ((void (__fastcall *)(struct IXMLDOMElement *))v52->lpVtbl->Release)(v52);
        if ( Block )
          operator delete(Block);
        goto LABEL_108;
      }
      v24 = 1034;
    }
    else
    {
      v24 = 1005;
    }
LABEL_33:
    SdpDebugTrace(1u, L"SdpRecordMethodCall", v24, v23);
    v9 = v50;
    goto LABEL_98;
  }
  v10 = 1;
LABEL_108:
  if ( v53 )
    operator delete(v53);
  return v10;
}

```

## disassembly

```asm
0x180004518  push    rbp
0x18000451a  push    rbx
0x18000451b  push    rsi
0x18000451c  push    rdi
0x18000451d  push    r12
0x18000451f  push    r13
0x180004521  push    r14
0x180004523  push    r15
0x180004525  lea     rbp, [rsp-7A8h]
0x18000452d  sub     rsp, 8A8h
0x180004534  mov     rax, cs:__security_cookie
0x18000453b  xor     rax, rsp
0x18000453e  mov     [rbp+7E0h+var_50], rax
0x180004545  xor     r12d, r12d
0x180004548  mov     r13d, r9d
0x18000454b  mov     [rsp+8E0h+var_888], r12
0x180004550  mov     r15, r8
0x180004553  mov     [rsp+8E0h+var_8A8], r12
0x180004558  mov     rdi, rdx
0x18000455b  mov     [rsp+8E0h+var_8A0], r12
0x180004560  mov     r14, rcx
0x180004563  mov     [rsp+8E0h+var_898], r12
0x180004568  mov     esi, r12d
0x18000456b  mov     [rsp+8E0h+Block], r12
0x180004570  mov     [rsp+8E0h+var_880], r12
0x180004575  mov     [rsp+8E0h+var_890], r12
0x18000457a  test    rdx, rdx
0x18000457d  jnz     short loc_1800045A2
0x18000457f  mov     r9d, 80070057h; int
0x180004585  lea     rdx, aSdprecordmetho; "SdpRecordMethodCall"
0x18000458c  mov     r8d, 399h; int
0x180004592  lea     ecx, [rdi+1]; Level
0x180004595  mov     ebx, r9d
0x180004598  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000459d  jmp     loc_180004D2C
0x1800045a2  test    r14, r14
0x1800045a5  jnz     short loc_1800045B0
0x1800045a7  lea     ebx, [r14+1]
0x1800045ab  jmp     loc_180004D2C
0x1800045b0  mov     edx, [rbp+7E0h+arg_20]; unsigned int
0x1800045b6  lea     r8, [rbp+7E0h+arg_28]; char *
0x1800045bd  lea     rcx, [rsp+8E0h+var_890]; struct _SDIAG_VARARG **
0x1800045c2  call    ?SdpParseVariableArgs@@YAJPEAPEAU_SDIAG_VARARG@@KPEAD@Z; SdpParseVariableArgs(_SDIAG_VARARG * *,ulong,char *)
0x1800045c7  mov     ebx, eax
0x1800045c9  test    eax, eax
0x1800045cb  jns     short loc_1800045EC
0x1800045cd  mov     r9d, eax; int
0x1800045d0  lea     rdx, aSdprecordmetho; "SdpRecordMethodCall"
0x1800045d7  mov     r8d, 3ACh; int
0x1800045dd  mov     ecx, 1; Level
0x1800045e2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800045e7  jmp     loc_180004D1D
0x1800045ec  mov     rax, [r14+48h]
0x1800045f0  mov     [rsp+8E0h+var_880], rax
0x1800045f5  test    rax, rax
0x1800045f8  jnz     short loc_180004602
0x1800045fa  lea     ebx, [rax+1]
0x1800045fd  jmp     loc_180004D1D
0x180004602  lea     rdx, [rsp+8E0h+var_888]; struct IXMLDOMDocument2 **
0x180004607  lea     rcx, aXmlVersion10En_2; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18000460e  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180004613  mov     r12, [rsp+8E0h+var_888]
0x180004618  mov     ebx, eax
0x18000461a  test    eax, eax
0x18000461c  jns     short loc_18000462C
0x18000461e  mov     r9d, eax
0x180004621  mov     r8d, 3BFh
0x180004627  jmp     loc_180004CA5
0x18000462c  mov     r9, rdi; unsigned __int16 *
0x18000462f  lea     r8, aId_0; "id"
0x180004636  xor     edx, edx; struct IXMLDOMElement *
0x180004638  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18000463b  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180004640  mov     ebx, eax
0x180004642  test    eax, eax
0x180004644  jns     short loc_180004654
0x180004646  mov     r9d, eax
0x180004649  mov     r8d, 3C5h
0x18000464f  jmp     loc_180004CA5
0x180004654  lea     rdx, aInitialize; "Initialize"
0x18000465b  mov     rcx, rdi; String1
0x18000465e  call    cs:__imp__wcsicmp
0x180004664  test    eax, eax
0x180004666  jnz     short loc_180004691
0x180004668  lea     r8, [rsp+8E0h+Block]; unsigned __int16 **
0x18000466d  mov     edx, 84h; unsigned int
0x180004672  xor     ecx, ecx; unsigned __int16 *
0x180004674  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180004679  mov     ebx, eax
0x18000467b  test    eax, eax
0x18000467d  jns     loc_180004744
0x180004683  mov     r9d, eax
0x180004686  mov     r8d, 3CDh
0x18000468c  jmp     loc_180004CA5
0x180004691  lea     rdx, aDiagnose; "Diagnose"
0x180004698  mov     rcx, rdi; String1
0x18000469b  call    cs:__imp__wcsicmp
0x1800046a1  test    eax, eax
0x1800046a3  jnz     short loc_1800046CE
0x1800046a5  lea     r8, [rsp+8E0h+Block]; unsigned __int16 **
0x1800046aa  mov     edx, 85h; unsigned int
0x1800046af  xor     ecx, ecx; unsigned __int16 *
0x1800046b1  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x1800046b6  mov     ebx, eax
0x1800046b8  test    eax, eax
0x1800046ba  jns     loc_180004744
0x1800046c0  mov     r9d, eax
0x1800046c3  mov     r8d, 3D0h
0x1800046c9  jmp     loc_180004CA5
0x1800046ce  lea     rdx, aResolve; "Resolve"
0x1800046d5  mov     rcx, rdi; String1
0x1800046d8  call    cs:__imp__wcsicmp
0x1800046de  test    eax, eax
0x1800046e0  jnz     short loc_180004707
0x1800046e2  lea     r8, [rsp+8E0h+Block]; unsigned __int16 **
0x1800046e7  mov     edx, 86h; unsigned int
0x1800046ec  xor     ecx, ecx; unsigned __int16 *
0x1800046ee  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x1800046f3  mov     ebx, eax
0x1800046f5  test    eax, eax
0x1800046f7  jns     short loc_180004744
0x1800046f9  mov     r9d, eax
0x1800046fc  mov     r8d, 3D3h
0x180004702  jmp     loc_180004CA5
0x180004707  lea     rdx, aVerify; "Verify"
0x18000470e  mov     rcx, rdi; String1
0x180004711  call    cs:__imp__wcsicmp
0x180004717  test    eax, eax
0x180004719  jnz     loc_180004C96
0x18000471f  lea     r8, [rsp+8E0h+Block]; unsigned __int16 **
0x180004724  mov     edx, 87h; unsigned int
0x180004729  xor     ecx, ecx; unsigned __int16 *
0x18000472b  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180004730  mov     ebx, eax
0x180004732  test    eax, eax
0x180004734  jns     short loc_180004744
0x180004736  mov     r9d, eax
0x180004739  mov     r8d, 3D6h
0x18000473f  jmp     loc_180004CA5
0x180004744  mov     r9, [rsp+8E0h+Block]; unsigned __int16 *
0x180004749  lea     r8, aName_0; "name"
0x180004750  xor     edx, edx; struct IXMLDOMElement *
0x180004752  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180004755  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18000475a  mov     ebx, eax
0x18000475c  test    eax, eax
0x18000475e  jns     short loc_18000476E
0x180004760  mov     r9d, eax
0x180004763  mov     r8d, 3DCh
0x180004769  jmp     loc_180004CA5
0x18000476e  mov     rdi, [rsp+8E0h+Block]
0x180004773  test    rdi, rdi
0x180004776  jz      short loc_180004785
0x180004778  mov     rcx, rdi; Block
0x18000477b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004780  mov     [rsp+8E0h+Block], rsi
0x180004785  mov     r14d, 400h
0x18000478b  lea     r8, aI64u; "%I64u"
0x180004792  mov     edx, r14d; unsigned __int64
0x180004795  lea     rcx, [rbp+7E0h+var_850]; unsigned __int16 *
0x180004799  mov     r9, r15
0x18000479c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800047a1  mov     ebx, eax
0x1800047a3  test    eax, eax
0x1800047a5  jns     short loc_1800047B3
0x1800047a7  mov     r9d, eax
0x1800047aa  lea     r8d, [r14-1Ah]
0x1800047ae  jmp     loc_180004CA5
0x1800047b3  lea     rax, [rsp+8E0h+var_8A8]
0x1800047b8  xor     edx, edx; struct IXMLDOMElement *
0x1800047ba  lea     r9, [rbp+7E0h+var_850]; unsigned __int16 *
0x1800047be  mov     [rsp+8E0h+var_8C0], rax; struct IXMLDOMElement **
0x1800047c3  lea     r8, aData; "Data"
0x1800047ca  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800047cd  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800047d2  mov     ebx, eax
0x1800047d4  test    eax, eax
0x1800047d6  jns     short loc_1800047FC
0x1800047d8  mov     r8d, 3EDh; int
0x1800047de  mov     r9d, eax; int
0x1800047e1  lea     rdx, aSdprecordmetho; "SdpRecordMethodCall"
0x1800047e8  mov     ecx, 1; Level
0x1800047ed  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800047f2  mov     rsi, [rsp+8E0h+var_8A8]
0x1800047f7  jmp     loc_180004CB6
0x1800047fc  mov     rsi, [rsp+8E0h+var_8A8]
0x180004801  lea     r9, aRunningtime; "RunningTime"
0x180004808  mov     rdx, rsi; struct IXMLDOMElement *
0x18000480b  lea     r8, aId_0; "id"
0x180004812  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180004814  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180004819  mov     ebx, eax
0x18000481b  test    eax, eax
0x18000481d  jns     short loc_18000482D
0x18000481f  mov     r9d, eax
0x180004822  mov     r8d, 3F3h
0x180004828  jmp     loc_180004CA5
0x18000482d  lea     r8, [rsp+8E0h+Block]; unsigned __int16 **
0x180004832  mov     edx, 6Ah ; 'j'; unsigned int
0x180004837  xor     ecx, ecx; unsigned __int16 *
0x180004839  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x18000483e  mov     ebx, eax
0x180004840  test    eax, eax
0x180004842  jns     short loc_180004852
0x180004844  mov     r9d, eax
0x180004847  mov     r8d, 3F6h
0x18000484d  jmp     loc_180004CA5
0x180004852  mov     r9, [rsp+8E0h+Block]; unsigned __int16 *
0x180004857  lea     r8, aName_0; "name"
0x18000485e  mov     rdx, rsi; struct IXMLDOMElement *
0x180004861  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180004863  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180004868  mov     ebx, eax
0x18000486a  test    eax, eax
0x18000486c  jns     short loc_18000487C
0x18000486e  mov     r9d, eax
0x180004871  mov     r8d, 3F9h
0x180004877  jmp     loc_180004CA5
0x18000487c  test    rsi, rsi
0x18000487f  jz      short loc_180004897
0x180004881  mov     rax, [rsi]
0x180004884  mov     rcx, rsi
0x180004887  mov     rax, [rax+10h]
0x18000488b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004890  xor     esi, esi
0x180004892  mov     [rsp+8E0h+var_8A8], rsi
0x180004897  mov     rdi, [rsp+8E0h+Block]
0x18000489c  test    rdi, rdi
0x18000489f  jz      short loc_1800048B2
0x1800048a1  mov     rcx, rdi; Block
0x1800048a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800048a9  mov     [rsp+8E0h+Block], 0
0x1800048b2  mov     r9d, r13d
0x1800048b5  lea     r8, a0xX; "0x%X"
0x1800048bc  mov     rdx, r14; unsigned __int64
0x1800048bf  lea     rcx, [rbp+7E0h+var_850]; unsigned __int16 *
0x1800048c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800048c8  mov     ebx, eax
0x1800048ca  test    eax, eax
0x1800048cc  jns     short loc_1800048DC
0x1800048ce  mov     r9d, eax
0x1800048d1  mov     r8d, 403h
0x1800048d7  jmp     loc_180004CA5
0x1800048dc  lea     rax, [rsp+8E0h+var_8A8]
0x1800048e1  xor     edx, edx; struct IXMLDOMElement *
0x1800048e3  lea     r9, [rbp+7E0h+var_850]; unsigned __int16 *
0x1800048e7  mov     [rsp+8E0h+var_8C0], rax; struct IXMLDOMElement **
0x1800048ec  lea     r8, aData; "Data"
0x1800048f3  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800048f6  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800048fb  mov     ebx, eax
0x1800048fd  test    eax, eax
0x1800048ff  jns     short loc_18000490C
0x180004901  mov     r8d, 40Ah
0x180004907  jmp     loc_1800047DE
0x18000490c  mov     rsi, [rsp+8E0h+var_8A8]
0x180004911  lea     r9, aStatuscode; "StatusCode"
0x180004918  mov     rdx, rsi; struct IXMLDOMElement *
0x18000491b  lea     r8, aId_0; "id"
0x180004922  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180004924  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180004929  mov     ebx, eax
0x18000492b  test    eax, eax
0x18000492d  jns     short loc_18000493D
0x18000492f  mov     r9d, eax
0x180004932  mov     r8d, 410h
0x180004938  jmp     loc_180004CA5
0x18000493d  lea     r8, [rsp+8E0h+Block]; unsigned __int16 **
0x180004942  mov     edx, 6Bh ; 'k'; unsigned int
0x180004947  xor     ecx, ecx; unsigned __int16 *
0x180004949  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x18000494e  mov     ebx, eax
0x180004950  test    eax, eax
0x180004952  jns     short loc_180004962
0x180004954  mov     r9d, eax
0x180004957  mov     r8d, 413h
0x18000495d  jmp     loc_180004CA5
0x180004962  mov     r9, [rsp+8E0h+Block]; unsigned __int16 *
0x180004967  lea     r8, aName_0; "name"
0x18000496e  mov     rdx, rsi; struct IXMLDOMElement *
0x180004971  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180004973  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180004978  mov     ebx, eax
0x18000497a  test    eax, eax
0x18000497c  jns     short loc_18000498C
0x18000497e  mov     r9d, eax
0x180004981  mov     r8d, 416h
0x180004987  jmp     loc_180004CA5
0x18000498c  lea     rax, [rsp+8E0h+var_8A0]
0x180004991  xor     r9d, r9d; unsigned __int16 *
0x180004994  lea     r8, aInputarguments; "InputArguments"
0x18000499b  mov     [rsp+8E0h+var_8C0], rax; struct IXMLDOMElement **
0x1800049a0  xor     edx, edx; struct IXMLDOMElement *
0x1800049a2  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800049a5  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800049aa  mov     ebx, eax
0x1800049ac  test    eax, eax
0x1800049ae  jns     short loc_1800049BE
0x1800049b0  mov     r9d, eax
0x1800049b3  mov     r8d, 421h
  ... truncated ...
```
