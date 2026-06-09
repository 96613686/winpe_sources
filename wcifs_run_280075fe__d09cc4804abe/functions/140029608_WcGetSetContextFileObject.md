# WcGetSetContextFileObject

- ea: `0x140029608`
- end: `0x140029c71`
- name: `WcGetSetContextFileObject`
- size: `1641`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int, __int64, __int64)`
- caller_count: `10`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140018e28`
- `0x14001bcec`
- `0x14001ecb8`
- `0x14001ef50`
- `0x140026210`
- `0x140026de0`
- `0x140027854`
- `0x1400318f0`
- `0x140033860`
- `0x1400343c0`

## callees

- `0x140001500`
- `0x140001ffc`
- `0x1400020c4`
- `0x140002294`
- `0x1400048a4`
- `0x1400053f8`
- `0x140007c60`
- `0x140029608`
- `0x140029c78`
- `0x140029d34`
- `0x140029f34`
- `0x14002a0cc`
- `0x14002a614`
- `0x14002f994`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x140029772`
- `ntoskrnl!IoGetSilo` at `0x140029772`
- `ntoskrnl!PsGetParentSilo` at `0x140029781`
- `ntoskrnl!PsGetParentSilo` at `0x140029781`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c60`
- `FLTMGR!FltGetFileContext` at `0x1400297e7`
- `FLTMGR!FltGetFileContext` at `0x1400297e7`
- `FLTMGR!FltGetStreamContext` at `0x140029753`
- `FLTMGR!FltGetStreamContext` at `0x140029753`
- `FLTMGR!FltQueryInformationFile` at `0x140029709`
- `FLTMGR!FltQueryInformationFile` at `0x140029709`
- `FLTMGR!FltReleaseContext` at `0x140029c2d`
- `FLTMGR!FltReleaseContext` at `0x140029c3e`
- `FLTMGR!FltReleaseContext` at `0x140029c2d`
- `FLTMGR!FltReleaseContext` at `0x140029c3e`

## string_xrefs

- `0x14002972a`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140029967`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400299ee`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140029a42`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140029aee`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcGetSetContextFileObject(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        int a4,
        int a5,
        _QWORD *a6,
        _QWORD *a7)
{
  _DWORD *v8; // r12
  char IsExpanded; // al
  PFLT_CONTEXT v12; // rcx
  NTSTATUS v13; // eax
  NTSTATUS StreamContext; // ebx
  __int64 Silo; // rax
  int ParentSilo; // eax
  int SourceList; // eax
  int v18; // edx
  int v19; // edx
  int SetFileContext; // eax
  int v21; // edx
  int v22; // eax
  int v23; // edx
  PFLT_CONTEXT v24; // rax
  int ReparseData; // eax
  int v27; // edx
  int v28; // eax
  char ContextFileObject; // [rsp+50h] [rbp-81h]
  PFLT_CONTEXT v30; // [rsp+58h] [rbp-79h] BYREF
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-71h] BYREF
  int v32; // [rsp+68h] [rbp-69h]
  _DWORD Instancea[3]; // [rsp+6Ch] [rbp-65h] BYREF
  __int64 v34[2]; // [rsp+78h] [rbp-59h] BYREF
  __int64 v35; // [rsp+88h] [rbp-49h]
  _DWORD *v36; // [rsp+90h] [rbp-41h]
  __int128 v37; // [rsp+98h] [rbp-39h] BYREF
  _QWORD *v38; // [rsp+A8h] [rbp-29h]
  _QWORD *v39; // [rsp+B0h] [rbp-21h]
  __int128 FileInformation; // [rsp+B8h] [rbp-19h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-9h]

  v38 = a6;
  v8 = 0;
  v39 = a7;
  v32 = a4;
  v41 = 0;
  v35 = a3;
  v34[1] = (__int64)v34;
  *(_QWORD *)&Instancea[1] = Instance;
  v34[0] = (__int64)v34;
  Context = 0;
  v30 = 0;
  v36 = 0;
  Instancea[0] = 0;
  FileInformation = 0;
  v37 = 0;
  ContextFileObject = WcGetContextFileObject(Instance, FileObject);
  if ( ContextFileObject )
  {
    IsExpanded = WcIsExpanded(v30);
    v12 = Context;
    if ( IsExpanded )
    {
      StreamContext = 0;
      goto LABEL_25;
    }
    v8 = (_DWORD *)*((_QWORD *)v30 + 8);
  }
  else
  {
    ReparseData = WcGetReparseData(Instance, FileObject, (__int64)Instancea);
    v8 = v36;
    StreamContext = ReparseData;
    if ( ReparseData < 0 )
      goto LABEL_26;
    if ( *v36 != *(_DWORD *)(a3 + 36) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 3;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          5,
          11,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          246,
          *v36);
      }
      StreamContext = 260;
      goto LABEL_26;
    }
    v28 = WcValidateWcReparseInfo(v36, Instancea[0]);
    StreamContext = v28;
    if ( v28 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          12,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          2,
          v28);
      goto LABEL_26;
    }
  }
  WORD1(v37) = *((_WORD *)v8 + 16);
  LOWORD(v37) = WORD1(v37);
  *((_QWORD *)&v37 + 1) = (char *)v8 + 34;
  v13 = FltQueryInformationFile(Instance, FileObject, &FileInformation, 0x18u, FileStandardInformation, 0);
  StreamContext = v13;
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDqd(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        13,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        26,
        (char)FileObject,
        v13);
    goto LABEL_44;
  }
  if ( !HIWORD(v41) )
  {
    StreamContext = FltGetStreamContext(*(PFLT_INSTANCE *)&Instancea[1], FileObject, &Context);
    if ( StreamContext < 0 )
    {
      if ( BYTE5(v41) )
      {
        if ( (v8[3] & 4) != 0 )
          goto LABEL_14;
        v32 |= 1u;
      }
      Silo = IoGetSilo(FileObject);
      ParentSilo = PsGetParentSilo(Silo);
      SourceList = WcGetSourceList(ParentSilo, v35, (int)v8 + 8, v32, (__int64)v34);
      StreamContext = SourceList;
      if ( SourceList < 0 )
      {
        if ( !BYTE5(v41) || SourceList != -1073741772 && SourceList != -1073741766 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_sDZd(
              WPP_GLOBAL_Control->DeviceExtension,
              2,
              5,
              15,
              (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
              98,
              (__int64)&v37,
              SourceList);
          if ( StreamContext == -1073741766 )
            StreamContext = -1073741772;
          goto LABEL_26;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 4;
          WPP_RECORDER_SF_sDZ(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            5,
            14,
            (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
            79,
            (__int64)&v37);
        }
        StreamContext = 0;
      }
    }
  }
LABEL_14:
  if ( !ContextFileObject )
  {
    StreamContext = FltGetFileContext(*(PFLT_INSTANCE *)&Instancea[1], FileObject, &v30);
    if ( StreamContext < 0 )
    {
      if ( (v8[3] & 4) != 0 && !BYTE5(v41) && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 3;
        WPP_RECORDER_SF_sDqd(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          5,
          16,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          151,
          (char)FileObject,
          StreamContext);
      }
      SetFileContext = WcGetSetFileContext(*(PFLT_INSTANCE *)&Instancea[1], FileObject, (__int64)&v30);
      StreamContext = SetFileContext;
      if ( SetFileContext >= 0 )
      {
        v8 = 0;
        goto LABEL_19;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = 4;
        WPP_RECORDER_SF_sDqd(
          WPP_GLOBAL_Control->DeviceExtension,
          v21,
          5,
          17,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          166,
          (char)FileObject,
          SetFileContext);
      }
LABEL_44:
      StreamContext = -1073741790;
      goto LABEL_26;
    }
  }
LABEL_19:
  if ( HIWORD(v41) )
    goto LABEL_24;
  v12 = Context;
  if ( Context )
  {
LABEL_25:
    v24 = v30;
    v30 = 0;
    Context = 0;
    *v38 = v24;
    *v39 = v12;
    goto LABEL_26;
  }
  v22 = (__int64 *)v34[0] == v34
      ? WcGetSetStreamContext(
          *(PFLT_INSTANCE *)&Instancea[1],
          FileObject,
          v30,
          16,
          *((__int64 *)&FileInformation + 1),
          (__int64)v34,
          (__int64)&Context)
      : WcGetSetStreamContext(
          *(PFLT_INSTANCE *)&Instancea[1],
          FileObject,
          v30,
          *(_DWORD *)(*(_QWORD *)(v34[0] + 24) + 24LL),
          *((__int64 *)&FileInformation + 1),
          (__int64)v34,
          (__int64)&Context);
  StreamContext = v22;
  if ( v22 >= 0 )
  {
LABEL_24:
    v12 = Context;
    goto LABEL_25;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v23) = 4;
    WPP_RECORDER_SF_sDqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      5,
      18,
      (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
      210,
      (char)FileObject,
      v22);
  }
LABEL_26:
  if ( Context )
    FltReleaseContext(Context);
  if ( v30 )
    FltReleaseContext(v30);
  if ( !ContextFileObject && v8 )
    ExFreePoolWithTag(v8, 0x69724357u);
  WcFreeSourceList(v34);
  return (unsigned int)StreamContext;
}

```

## disassembly

```asm
0x140029608  mov     [rsp-8+arg_18], rbx
0x14002960d  push    rbp
0x14002960e  push    rsi
0x14002960f  push    rdi
0x140029610  push    r12
0x140029612  push    r13
0x140029614  push    r14
0x140029616  push    r15
0x140029618  lea     rbp, [rsp-0Fh]
0x14002961d  sub     rsp, 0E0h
0x140029624  mov     rax, cs:__security_cookie
0x14002962b  xor     rax, rsp
0x14002962e  mov     [rbp+3Fh+var_40], rax
0x140029632  mov     rax, [rbp+3Fh+arg_28]
0x140029636  xorps   xmm0, xmm0
0x140029639  mov     [rbp+3Fh+var_68], rax
0x14002963d  mov     rsi, r8
0x140029640  mov     rax, [rbp+3Fh+arg_30]
0x140029644  xor     r12d, r12d
0x140029647  mov     [rbp+3Fh+var_60], rax
0x14002964b  mov     r13, rdx
0x14002964e  xor     eax, eax
0x140029650  mov     [rbp+3Fh+var_A8], r9d
0x140029654  mov     [rbp+3Fh+var_48], rax
0x140029658  lea     r9, [rbp+3Fh+Context]
0x14002965c  lea     rax, [rbp+3Fh+var_98]
0x140029660  mov     [rbp+3Fh+var_88], r8
0x140029664  mov     [rbp+3Fh+var_90], rax
0x140029668  lea     r8, [rbp+3Fh+var_B8]
0x14002966c  lea     rax, [rbp+3Fh+var_98]
0x140029670  mov     qword ptr [rbp+3Fh+Instance+4], rcx
0x140029674  mov     [rbp+3Fh+var_98], rax
0x140029678  mov     rdi, rcx
0x14002967b  mov     [rbp+3Fh+Context], 0
0x140029683  mov     [rbp+3Fh+var_B8], 0
0x14002968b  mov     [rbp+3Fh+var_80], r12
0x14002968f  mov     dword ptr [rbp+3Fh+Instance], r12d
0x140029693  movups  [rbp+3Fh+FileInformation], xmm0
0x140029697  movups  [rbp+3Fh+var_78], xmm0
0x14002969b  call    WcGetContextFileObject
0x1400296a0  mov     [rsp+110h+var_C0], al
0x1400296a4  test    al, al
0x1400296a6  jz      loc_140029920
0x1400296ac  mov     rcx, [rbp+3Fh+var_B8]
0x1400296b0  call    WcIsExpanded
0x1400296b5  mov     rcx, [rbp+3Fh+Context]
0x1400296b9  test    al, al
0x1400296bb  jnz     loc_1400299AA
0x1400296c1  test    rcx, rcx
0x1400296c4  jnz     loc_1400299AA
0x1400296ca  mov     rcx, [rbp+3Fh+var_B8]
0x1400296ce  mov     r12, [rcx+40h]
0x1400296d2  movzx   eax, word ptr [r12+20h]
0x1400296d8  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x1400296dc  mov     esi, 5
0x1400296e1  mov     word ptr [rbp+3Fh+var_78+2], ax
0x1400296e5  mov     word ptr [rbp+3Fh+var_78], ax
0x1400296e9  mov     rdx, r13; FileObject
0x1400296ec  lea     rax, [r12+22h]
0x1400296f1  mov     [rsp+110h+LengthReturned], 0; LengthReturned
0x1400296fa  mov     rcx, rdi; Instance
0x1400296fd  mov     qword ptr [rbp+3Fh+var_78+8], rax
0x140029701  lea     r9d, [rsi+13h]; Length
0x140029705  mov     [rsp+110h+FileInformationClass], esi; FileInformationClass
0x140029709  call    cs:__imp_FltQueryInformationFile
0x140029710  nop     dword ptr [rax+rax+00h]
0x140029715  mov     ebx, eax
0x140029717  test    eax, eax
0x140029719  js      loc_140029A2E
0x14002971f  cmp     byte ptr [rbp+3Fh+var_48+6], 0
0x140029723  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002972a  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140029731  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140029738  jnz     loc_1400297D5
0x14002973e  cmp     byte ptr [rbp+3Fh+var_48+7], 0
0x140029742  jnz     loc_1400297D5
0x140029748  mov     rcx, qword ptr [rbp+3Fh+Instance+4]; Instance
0x14002974c  lea     r8, [rbp+3Fh+Context]; Context
0x140029750  mov     rdx, r13; FileObject
0x140029753  call    cs:__imp_FltGetStreamContext
0x14002975a  nop     dword ptr [rax+rax+00h]
0x14002975f  mov     ebx, eax
0x140029761  test    eax, eax
0x140029763  jns     short loc_1400297D5
0x140029765  cmp     byte ptr [rbp+3Fh+var_48+5], 0
0x140029769  jnz     loc_140029AAD
0x14002976f  mov     rcx, r13
0x140029772  call    cs:__imp_IoGetSilo
0x140029779  nop     dword ptr [rax+rax+00h]
0x14002977e  mov     rcx, rax
0x140029781  call    cs:__imp_PsGetParentSilo
0x140029788  nop     dword ptr [rax+rax+00h]
0x14002978d  mov     r9d, [rbp+3Fh+var_A8]
0x140029791  lea     r8, [r12+8]
0x140029796  mov     rdx, [rbp+3Fh+var_88]
0x14002979a  mov     rcx, rax
0x14002979d  lea     rax, [rbp+3Fh+var_98]
0x1400297a1  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x1400297a6  call    WcGetSourceList
0x1400297ab  mov     ebx, eax
0x1400297ad  test    eax, eax
0x1400297af  jns     short loc_1400297D5
0x1400297b1  cmp     byte ptr [rbp+3Fh+var_48+5], 0
0x1400297b5  jz      loc_140029ACF
0x1400297bb  cmp     eax, 0C0000034h
0x1400297c0  jnz     loc_140029AC3
0x1400297c6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400297cd  jnz     loc_140029B3F
0x1400297d3  xor     ebx, ebx
0x1400297d5  cmp     [rsp+110h+var_C0], 0
0x1400297da  jnz     short loc_140029838
0x1400297dc  mov     rcx, qword ptr [rbp+3Fh+Instance+4]; Instance
0x1400297e0  lea     r8, [rbp+3Fh+var_B8]; Context
0x1400297e4  mov     rdx, r13; FileObject
0x1400297e7  call    cs:__imp_FltGetFileContext
0x1400297ee  nop     dword ptr [rax+rax+00h]
0x1400297f3  mov     ebx, eax
0x1400297f5  test    eax, eax
0x1400297f7  jns     short loc_140029838
0x1400297f9  mov     eax, [r12+0Ch]
0x1400297fe  mov     esi, 2
0x140029803  test    al, 4
0x140029805  jnz     loc_140029B7A
0x14002980b  mov     rcx, qword ptr [rbp+3Fh+Instance+4]; Instance
0x14002980f  lea     rax, [rbp+3Fh+var_B8]
0x140029813  mov     r9, r12
0x140029816  mov     qword ptr [rsp+110h+FileInformationClass], rax; __int64
0x14002981b  mov     r8d, esi
0x14002981e  mov     rdx, r13; FileObject
0x140029821  call    WcGetSetFileContext
0x140029826  mov     ebx, eax
0x140029828  test    eax, eax
0x14002982a  js      loc_140029BD3
0x140029830  xor     r12d, r12d
0x140029833  lea     esi, [r12+5]
0x140029838  cmp     byte ptr [rbp+3Fh+var_48+6], 0
0x14002983c  jnz     short loc_1400298A2
0x14002983e  cmp     byte ptr [rbp+3Fh+var_48+7], 0
0x140029842  jnz     short loc_1400298A2
0x140029844  mov     rcx, [rbp+3Fh+Context]
0x140029848  test    rcx, rcx
0x14002984b  jnz     short loc_1400298A6
0x14002984d  mov     rcx, [rbp+3Fh+var_98]
0x140029851  lea     rax, [rbp+3Fh+var_98]
0x140029855  mov     r9, [rbp+3Fh+var_88]
0x140029859  cmp     rcx, rax
0x14002985c  mov     r8, [rbp+3Fh+var_B8]; Context
0x140029860  lea     rax, [rbp+3Fh+Context]
0x140029864  mov     [rsp+110h+var_D8], rax; __int64
0x140029869  mov     rdx, r13; FileObject
0x14002986c  lea     rax, [rbp+3Fh+var_98]
0x140029870  mov     [rsp+110h+var_E0], rax; __int64
0x140029875  mov     rax, qword ptr [rbp+3Fh+FileInformation+8]
0x140029879  mov     [rsp+110h+LengthReturned], rax; __int64
0x14002987e  jz      loc_1400299B1
0x140029884  mov     rcx, [rcx+18h]
0x140029888  mov     eax, [rcx+18h]
0x14002988b  mov     [rsp+110h+FileInformationClass], eax; int
0x14002988f  mov     rcx, qword ptr [rbp+3Fh+Instance+4]; Instance
0x140029893  call    WcGetSetStreamContext
0x140029898  mov     ebx, eax
0x14002989a  test    eax, eax
0x14002989c  js      loc_140029BE5
0x1400298a2  mov     rcx, [rbp+3Fh+Context]
0x1400298a6  mov     rax, [rbp+3Fh+var_B8]
0x1400298aa  mov     rdx, [rbp+3Fh+var_68]
0x1400298ae  mov     [rbp+3Fh+var_B8], 0
0x1400298b6  mov     [rbp+3Fh+Context], 0
0x1400298be  mov     [rdx], rax
0x1400298c1  mov     rax, [rbp+3Fh+var_60]
0x1400298c5  mov     [rax], rcx
0x1400298c8  mov     rcx, [rbp+3Fh+Context]; Context
0x1400298cc  test    rcx, rcx
0x1400298cf  jnz     loc_140029C2D
0x1400298d5  mov     rcx, [rbp+3Fh+var_B8]; Context
0x1400298d9  test    rcx, rcx
0x1400298dc  jnz     loc_140029C3E
0x1400298e2  cmp     [rsp+110h+var_C0], 0
0x1400298e7  jz      loc_140029C4F
0x1400298ed  lea     rcx, [rbp+3Fh+var_98]
0x1400298f1  call    WcFreeSourceList
0x1400298f6  mov     eax, ebx
0x1400298f8  mov     rcx, [rbp+3Fh+var_40]
0x1400298fc  xor     rcx, rsp; StackCookie
0x1400298ff  call    __security_check_cookie
0x140029904  mov     rbx, [rsp+110h+arg_18]
0x14002990c  add     rsp, 0E0h
0x140029913  pop     r15
0x140029915  pop     r14
0x140029917  pop     r13
0x140029919  pop     r12
0x14002991b  pop     rdi
0x14002991c  pop     rsi
0x14002991d  pop     rbp
0x14002991e  retn
0x140029920  movzx   r8d, word ptr [r13+58h]
0x140029925  lea     rax, [rbp+3Fh+Instance]
0x140029929  lea     r9, [rbp+3Fh+var_80]
0x14002992d  mov     qword ptr [rsp+110h+FileInformationClass], rax; __int64
0x140029932  mov     rdx, r13; FileObject
0x140029935  mov     rcx, rdi; Instance
0x140029938  call    WcGetReparseData
0x14002993d  mov     r12, [rbp+3Fh+var_80]
0x140029941  mov     ebx, eax
0x140029943  test    eax, eax
0x140029945  js      short loc_1400298C8
0x140029947  mov     eax, [r12]
0x14002994b  cmp     eax, [rsi+24h]
0x14002994e  jz      short loc_1400299BE
0x140029950  lea     rdi, WPP_RECORDER_INITIALIZED
0x140029957  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002995e  jz      short loc_1400299A0
0x140029960  mov     rcx, cs:WPP_GLOBAL_Control
0x140029967  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x14002996e  mov     dword ptr [rsp+110h+var_D8], eax
0x140029972  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140029979  mov     r9d, 0Bh
0x14002997f  mov     dword ptr [rsp+110h+var_E0], 0F6h
0x140029987  mov     [rsp+110h+LengthReturned], r14
0x14002998c  mov     dl, 3
0x14002998e  mov     rcx, [rcx+40h]
0x140029992  mov     qword ptr [rsp+110h+FileInformationClass], r15
0x140029997  lea     r8d, [r9-6]
0x14002999b  call    WPP_RECORDER_SF_sDd
0x1400299a0  mov     ebx, 104h
0x1400299a5  jmp     loc_1400298C8
0x1400299aa  xor     ebx, ebx
0x1400299ac  jmp     loc_1400298A6
0x1400299b1  mov     [rsp+110h+FileInformationClass], 10h
0x1400299b9  jmp     loc_14002988F
0x1400299be  mov     edx, dword ptr [rbp+3Fh+Instance]
0x1400299c1  mov     rcx, r12
0x1400299c4  call    WcValidateWcReparseInfo
0x1400299c9  mov     ebx, eax
0x1400299cb  test    eax, eax
0x1400299cd  jns     loc_1400296D2
0x1400299d3  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400299da  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400299e1  jz      loc_1400298C8
0x1400299e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400299ee  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400299f5  mov     dword ptr [rsp+110h+var_D8], eax
0x1400299f9  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140029a00  mov     r9d, 0Ch
0x140029a06  mov     dword ptr [rsp+110h+var_E0], 102h
0x140029a0e  mov     [rsp+110h+LengthReturned], r14
0x140029a13  mov     rcx, [rcx+40h]
0x140029a17  mov     qword ptr [rsp+110h+FileInformationClass], r15
0x140029a1c  lea     edx, [r9-0Ah]
0x140029a20  lea     r8d, [r9-7]
0x140029a24  call    WPP_RECORDER_SF_sDd
0x140029a29  jmp     loc_1400298C8
0x140029a2e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140029a35  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140029a3c  jz      short loc_140029AA3
0x140029a3e  mov     [rsp+110h+var_D0], eax
0x140029a42  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140029a49  mov     r9d, 0Dh
0x140029a4f  mov     [rsp+110h+var_D8], r13
0x140029a54  mov     dword ptr [rsp+110h+var_E0], 11Ah
0x140029a5c  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140029a63  mov     r8d, esi
0x140029a66  lea     edx, [r9-0Bh]
0x140029a6a  jmp     short loc_140029A89
0x140029a6c  mov     [rsp+110h+var_D0], eax
0x140029a70  mov     r9d, 11h
0x140029a76  mov     [rsp+110h+var_D8], r13
0x140029a7b  mov     dl, 4
0x140029a7d  mov     dword ptr [rsp+110h+var_E0], 1A6h
0x140029a85  lea     r8d, [r9-0Ch]
0x140029a89  mov     rcx, cs:WPP_GLOBAL_Control
0x140029a90  mov     [rsp+110h+LengthReturned], r14
0x140029a95  mov     qword ptr [rsp+110h+FileInformationClass], r15
0x140029a9a  mov     rcx, [rcx+40h]
0x140029a9e  call    WPP_RECORDER_SF_sDqd
0x140029aa3  mov     ebx, 0C0000022h
0x140029aa8  jmp     loc_1400298C8
0x140029aad  mov     eax, [r12+0Ch]
0x140029ab2  test    al, 4
0x140029ab4  jnz     loc_1400297D5
0x140029aba  or      [rbp+3Fh+var_A8], 1
0x140029abe  jmp     loc_14002976F
0x140029ac3  cmp     ebx, 0C000003Ah
0x140029ac9  jz      loc_1400297C6
0x140029acf  lea     rdi, WPP_RECORDER_INITIALIZED
0x140029ad6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140029add  jz      short loc_140029B29
0x140029adf  mov     rcx, cs:WPP_GLOBAL_Control
0x140029ae6  lea     rax, [rbp+3Fh+var_78]
0x140029aea  mov     [rsp+110h+var_D0], ebx
0x140029aee  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140029af5  mov     [rsp+110h+var_D8], rax
0x140029afa  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140029b01  mov     r9d, 0Fh
0x140029b07  mov     dword ptr [rsp+110h+var_E0], 162h
0x140029b0f  mov     rcx, [rcx+40h]
0x140029b13  mov     r8d, esi
0x140029b16  mov     [rsp+110h+LengthReturned], r14
0x140029b1b  mov     qword ptr [rsp+110h+FileInformationClass], r15
0x140029b20  lea     edx, [r9-0Dh]
  ... truncated ...
```
