# WcGetSetContextFileObject

- ea: `0x140029658`
- end: `0x140029cc1`
- name: `WcGetSetContextFileObject`
- size: `1641`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64, int, int, _QWORD *, _QWORD *)`
- caller_count: `10`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140018e28`
- `0x14001bcec`
- `0x14001ecb8`
- `0x14001ef50`
- `0x140026260`
- `0x140026e30`
- `0x1400278a4`
- `0x140031940`
- `0x1400338b0`
- `0x140034410`

## callees

- `0x140001500`
- `0x140001ffc`
- `0x1400020c4`
- `0x140002294`
- `0x1400048a4`
- `0x1400053f8`
- `0x140007c60`
- `0x140029658`
- `0x140029cc8`
- `0x140029d84`
- `0x140029f84`
- `0x14002a11c`
- `0x14002a664`
- `0x14002f9e4`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x1400297c2`
- `ntoskrnl!IoGetSilo` at `0x1400297c2`
- `ntoskrnl!PsGetParentSilo` at `0x1400297d1`
- `ntoskrnl!PsGetParentSilo` at `0x1400297d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029cb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029cb0`
- `FLTMGR!FltGetFileContext` at `0x140029837`
- `FLTMGR!FltGetFileContext` at `0x140029837`
- `FLTMGR!FltGetStreamContext` at `0x1400297a3`
- `FLTMGR!FltGetStreamContext` at `0x1400297a3`
- `FLTMGR!FltQueryInformationFile` at `0x140029759`
- `FLTMGR!FltQueryInformationFile` at `0x140029759`
- `FLTMGR!FltReleaseContext` at `0x140029c7d`
- `FLTMGR!FltReleaseContext` at `0x140029c8e`
- `FLTMGR!FltReleaseContext` at `0x140029c7d`
- `FLTMGR!FltReleaseContext` at `0x140029c8e`

## string_xrefs

- `0x14002977a`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400299b7`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140029a3e`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140029a92`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140029b3e`: `onecore\base\fs\wci\wcifs\create.c`

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
  unsigned __int16 *v8; // r12
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
  ULONG Instancea[3]; // [rsp+6Ch] [rbp-65h] BYREF
  __int64 v34[2]; // [rsp+78h] [rbp-59h] BYREF
  __int64 v35; // [rsp+88h] [rbp-49h]
  unsigned __int16 *v36; // [rsp+90h] [rbp-41h] BYREF
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
    v8 = (unsigned __int16 *)*((_QWORD *)v30 + 8);
  }
  else
  {
    ReparseData = WcGetReparseData(Instance, FileObject, FileObject->FileName.Length, &v36, Instancea);
    v8 = v36;
    StreamContext = ReparseData;
    if ( ReparseData < 0 )
      goto LABEL_26;
    if ( *(_DWORD *)v36 != *(_DWORD *)(a3 + 36) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 3;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v27,
          5,
          11,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          246,
          *(_DWORD *)v36);
      }
      StreamContext = 260;
      goto LABEL_26;
    }
    v28 = WcValidateWcReparseInfo((__int64)v36, Instancea[0]);
    StreamContext = v28;
    if ( v28 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
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
  WORD1(v37) = v8[16];
  LOWORD(v37) = WORD1(v37);
  *((_QWORD *)&v37 + 1) = v8 + 17;
  v13 = FltQueryInformationFile(Instance, FileObject, &FileInformation, 0x18u, FileStandardInformation, 0);
  StreamContext = v13;
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDqd(
        wil_details_featureDescriptors_a->DeviceExtension,
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
        if ( (*((_DWORD *)v8 + 3) & 4) != 0 )
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
              wil_details_featureDescriptors_a->DeviceExtension,
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
            wil_details_featureDescriptors_a->DeviceExtension,
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
      if ( (*((_DWORD *)v8 + 3) & 4) != 0
        && !BYTE5(v41)
        && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 3;
        WPP_RECORDER_SF_sDqd(
          wil_details_featureDescriptors_a->DeviceExtension,
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
          wil_details_featureDescriptors_a->DeviceExtension,
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
      wil_details_featureDescriptors_a->DeviceExtension,
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
0x140029658  mov     [rsp-8+arg_18], rbx
0x14002965d  push    rbp
0x14002965e  push    rsi
0x14002965f  push    rdi
0x140029660  push    r12
0x140029662  push    r13
0x140029664  push    r14
0x140029666  push    r15
0x140029668  lea     rbp, [rsp-0Fh]
0x14002966d  sub     rsp, 0E0h
0x140029674  mov     rax, cs:__security_cookie
0x14002967b  xor     rax, rsp
0x14002967e  mov     [rbp+3Fh+var_40], rax
0x140029682  mov     rax, [rbp+3Fh+arg_28]
0x140029686  xorps   xmm0, xmm0
0x140029689  mov     [rbp+3Fh+var_68], rax
0x14002968d  mov     rsi, r8
0x140029690  mov     rax, [rbp+3Fh+arg_30]
0x140029694  xor     r12d, r12d
0x140029697  mov     [rbp+3Fh+var_60], rax
0x14002969b  mov     r13, rdx
0x14002969e  xor     eax, eax
0x1400296a0  mov     [rbp+3Fh+var_A8], r9d
0x1400296a4  mov     [rbp+3Fh+var_48], rax
0x1400296a8  lea     r9, [rbp+3Fh+Context]
0x1400296ac  lea     rax, [rbp+3Fh+var_98]
0x1400296b0  mov     [rbp+3Fh+var_88], r8
0x1400296b4  mov     [rbp+3Fh+var_90], rax
0x1400296b8  lea     r8, [rbp+3Fh+var_B8]
0x1400296bc  lea     rax, [rbp+3Fh+var_98]
0x1400296c0  mov     qword ptr [rbp+3Fh+Instance+4], rcx
0x1400296c4  mov     [rbp+3Fh+var_98], rax
0x1400296c8  mov     rdi, rcx
0x1400296cb  mov     [rbp+3Fh+Context], 0
0x1400296d3  mov     [rbp+3Fh+var_B8], 0
0x1400296db  mov     [rbp+3Fh+var_80], r12
0x1400296df  mov     dword ptr [rbp+3Fh+Instance], r12d
0x1400296e3  movups  [rbp+3Fh+FileInformation], xmm0
0x1400296e7  movups  [rbp+3Fh+var_78], xmm0
0x1400296eb  call    WcGetContextFileObject
0x1400296f0  mov     [rsp+110h+var_C0], al
0x1400296f4  test    al, al
0x1400296f6  jz      loc_140029970
0x1400296fc  mov     rcx, [rbp+3Fh+var_B8]
0x140029700  call    WcIsExpanded
0x140029705  mov     rcx, [rbp+3Fh+Context]
0x140029709  test    al, al
0x14002970b  jnz     loc_1400299FA
0x140029711  test    rcx, rcx
0x140029714  jnz     loc_1400299FA
0x14002971a  mov     rcx, [rbp+3Fh+var_B8]
0x14002971e  mov     r12, [rcx+40h]
0x140029722  movzx   eax, word ptr [r12+20h]
0x140029728  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x14002972c  mov     esi, 5
0x140029731  mov     word ptr [rbp+3Fh+var_78+2], ax
0x140029735  mov     word ptr [rbp+3Fh+var_78], ax
0x140029739  mov     rdx, r13; FileObject
0x14002973c  lea     rax, [r12+22h]
0x140029741  mov     [rsp+110h+LengthReturned], 0; LengthReturned
0x14002974a  mov     rcx, rdi; Instance
0x14002974d  mov     qword ptr [rbp+3Fh+var_78+8], rax
0x140029751  lea     r9d, [rsi+13h]; Length
0x140029755  mov     [rsp+110h+FileInformationClass], esi; FileInformationClass
0x140029759  call    cs:__imp_FltQueryInformationFile
0x140029760  nop     dword ptr [rax+rax+00h]
0x140029765  mov     ebx, eax
0x140029767  test    eax, eax
0x140029769  js      loc_140029A7E
0x14002976f  cmp     byte ptr [rbp+3Fh+var_48+6], 0
0x140029773  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002977a  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140029781  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140029788  jnz     loc_140029825
0x14002978e  cmp     byte ptr [rbp+3Fh+var_48+7], 0
0x140029792  jnz     loc_140029825
0x140029798  mov     rcx, qword ptr [rbp+3Fh+Instance+4]; Instance
0x14002979c  lea     r8, [rbp+3Fh+Context]; Context
0x1400297a0  mov     rdx, r13; FileObject
0x1400297a3  call    cs:__imp_FltGetStreamContext
0x1400297aa  nop     dword ptr [rax+rax+00h]
0x1400297af  mov     ebx, eax
0x1400297b1  test    eax, eax
0x1400297b3  jns     short loc_140029825
0x1400297b5  cmp     byte ptr [rbp+3Fh+var_48+5], 0
0x1400297b9  jnz     loc_140029AFD
0x1400297bf  mov     rcx, r13
0x1400297c2  call    cs:__imp_IoGetSilo
0x1400297c9  nop     dword ptr [rax+rax+00h]
0x1400297ce  mov     rcx, rax
0x1400297d1  call    cs:__imp_PsGetParentSilo
0x1400297d8  nop     dword ptr [rax+rax+00h]
0x1400297dd  mov     r9d, [rbp+3Fh+var_A8]
0x1400297e1  lea     r8, [r12+8]
0x1400297e6  mov     rdx, [rbp+3Fh+var_88]
0x1400297ea  mov     rcx, rax
0x1400297ed  lea     rax, [rbp+3Fh+var_98]
0x1400297f1  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x1400297f6  call    WcGetSourceList
0x1400297fb  mov     ebx, eax
0x1400297fd  test    eax, eax
0x1400297ff  jns     short loc_140029825
0x140029801  cmp     byte ptr [rbp+3Fh+var_48+5], 0
0x140029805  jz      loc_140029B1F
0x14002980b  cmp     eax, 0C0000034h
0x140029810  jnz     loc_140029B13
0x140029816  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002981d  jnz     loc_140029B8F
0x140029823  xor     ebx, ebx
0x140029825  cmp     [rsp+110h+var_C0], 0
0x14002982a  jnz     short loc_140029888
0x14002982c  mov     rcx, qword ptr [rbp+3Fh+Instance+4]; Instance
0x140029830  lea     r8, [rbp+3Fh+var_B8]; Context
0x140029834  mov     rdx, r13; FileObject
0x140029837  call    cs:__imp_FltGetFileContext
0x14002983e  nop     dword ptr [rax+rax+00h]
0x140029843  mov     ebx, eax
0x140029845  test    eax, eax
0x140029847  jns     short loc_140029888
0x140029849  mov     eax, [r12+0Ch]
0x14002984e  mov     esi, 2
0x140029853  test    al, 4
0x140029855  jnz     loc_140029BCA
0x14002985b  mov     rcx, qword ptr [rbp+3Fh+Instance+4]; Instance
0x14002985f  lea     rax, [rbp+3Fh+var_B8]
0x140029863  mov     r9, r12
0x140029866  mov     qword ptr [rsp+110h+FileInformationClass], rax; __int64
0x14002986b  mov     r8d, esi
0x14002986e  mov     rdx, r13; FileObject
0x140029871  call    WcGetSetFileContext
0x140029876  mov     ebx, eax
0x140029878  test    eax, eax
0x14002987a  js      loc_140029C23
0x140029880  xor     r12d, r12d
0x140029883  lea     esi, [r12+5]
0x140029888  cmp     byte ptr [rbp+3Fh+var_48+6], 0
0x14002988c  jnz     short loc_1400298F2
0x14002988e  cmp     byte ptr [rbp+3Fh+var_48+7], 0
0x140029892  jnz     short loc_1400298F2
0x140029894  mov     rcx, [rbp+3Fh+Context]
0x140029898  test    rcx, rcx
0x14002989b  jnz     short loc_1400298F6
0x14002989d  mov     rcx, [rbp+3Fh+var_98]
0x1400298a1  lea     rax, [rbp+3Fh+var_98]
0x1400298a5  mov     r9, [rbp+3Fh+var_88]
0x1400298a9  cmp     rcx, rax
0x1400298ac  mov     r8, [rbp+3Fh+var_B8]; Context
0x1400298b0  lea     rax, [rbp+3Fh+Context]
0x1400298b4  mov     [rsp+110h+var_D8], rax; __int64
0x1400298b9  mov     rdx, r13; FileObject
0x1400298bc  lea     rax, [rbp+3Fh+var_98]
0x1400298c0  mov     [rsp+110h+var_E0], rax; __int64
0x1400298c5  mov     rax, qword ptr [rbp+3Fh+FileInformation+8]
0x1400298c9  mov     [rsp+110h+LengthReturned], rax; __int64
0x1400298ce  jz      loc_140029A01
0x1400298d4  mov     rcx, [rcx+18h]
0x1400298d8  mov     eax, [rcx+18h]
0x1400298db  mov     [rsp+110h+FileInformationClass], eax; int
0x1400298df  mov     rcx, qword ptr [rbp+3Fh+Instance+4]; Instance
0x1400298e3  call    WcGetSetStreamContext
0x1400298e8  mov     ebx, eax
0x1400298ea  test    eax, eax
0x1400298ec  js      loc_140029C35
0x1400298f2  mov     rcx, [rbp+3Fh+Context]
0x1400298f6  mov     rax, [rbp+3Fh+var_B8]
0x1400298fa  mov     rdx, [rbp+3Fh+var_68]
0x1400298fe  mov     [rbp+3Fh+var_B8], 0
0x140029906  mov     [rbp+3Fh+Context], 0
0x14002990e  mov     [rdx], rax
0x140029911  mov     rax, [rbp+3Fh+var_60]
0x140029915  mov     [rax], rcx
0x140029918  mov     rcx, [rbp+3Fh+Context]; Context
0x14002991c  test    rcx, rcx
0x14002991f  jnz     loc_140029C7D
0x140029925  mov     rcx, [rbp+3Fh+var_B8]; Context
0x140029929  test    rcx, rcx
0x14002992c  jnz     loc_140029C8E
0x140029932  cmp     [rsp+110h+var_C0], 0
0x140029937  jz      loc_140029C9F
0x14002993d  lea     rcx, [rbp+3Fh+var_98]
0x140029941  call    WcFreeSourceList
0x140029946  mov     eax, ebx
0x140029948  mov     rcx, [rbp+3Fh+var_40]
0x14002994c  xor     rcx, rsp; StackCookie
0x14002994f  call    __security_check_cookie
0x140029954  mov     rbx, [rsp+110h+arg_18]
0x14002995c  add     rsp, 0E0h
0x140029963  pop     r15
0x140029965  pop     r14
0x140029967  pop     r13
0x140029969  pop     r12
0x14002996b  pop     rdi
0x14002996c  pop     rsi
0x14002996d  pop     rbp
0x14002996e  retn
0x140029970  movzx   r8d, word ptr [r13+58h]
0x140029975  lea     rax, [rbp+3Fh+Instance]
0x140029979  lea     r9, [rbp+3Fh+var_80]
0x14002997d  mov     qword ptr [rsp+110h+FileInformationClass], rax; __int64
0x140029982  mov     rdx, r13; FileObject
0x140029985  mov     rcx, rdi; Instance
0x140029988  call    WcGetReparseData
0x14002998d  mov     r12, [rbp+3Fh+var_80]
0x140029991  mov     ebx, eax
0x140029993  test    eax, eax
0x140029995  js      short loc_140029918
0x140029997  mov     eax, [r12]
0x14002999b  cmp     eax, [rsi+24h]
0x14002999e  jz      short loc_140029A0E
0x1400299a0  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400299a7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400299ae  jz      short loc_1400299F0
0x1400299b0  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400299b7  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400299be  mov     dword ptr [rsp+110h+var_D8], eax
0x1400299c2  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400299c9  mov     r9d, 0Bh
0x1400299cf  mov     dword ptr [rsp+110h+var_E0], 0F6h
0x1400299d7  mov     [rsp+110h+LengthReturned], r14
0x1400299dc  mov     dl, 3
0x1400299de  mov     rcx, [rcx+40h]
0x1400299e2  mov     qword ptr [rsp+110h+FileInformationClass], r15
0x1400299e7  lea     r8d, [r9-6]
0x1400299eb  call    WPP_RECORDER_SF_sDd
0x1400299f0  mov     ebx, 104h
0x1400299f5  jmp     loc_140029918
0x1400299fa  xor     ebx, ebx
0x1400299fc  jmp     loc_1400298F6
0x140029a01  mov     [rsp+110h+FileInformationClass], 10h
0x140029a09  jmp     loc_1400298DF
0x140029a0e  mov     edx, dword ptr [rbp+3Fh+Instance]
0x140029a11  mov     rcx, r12
0x140029a14  call    WcValidateWcReparseInfo
0x140029a19  mov     ebx, eax
0x140029a1b  test    eax, eax
0x140029a1d  jns     loc_140029722
0x140029a23  lea     rdi, WPP_RECORDER_INITIALIZED
0x140029a2a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140029a31  jz      loc_140029918
0x140029a37  mov     rcx, cs:wil_details_featureDescriptors_a
0x140029a3e  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140029a45  mov     dword ptr [rsp+110h+var_D8], eax
0x140029a49  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140029a50  mov     r9d, 0Ch
0x140029a56  mov     dword ptr [rsp+110h+var_E0], 102h
0x140029a5e  mov     [rsp+110h+LengthReturned], r14
0x140029a63  mov     rcx, [rcx+40h]
0x140029a67  mov     qword ptr [rsp+110h+FileInformationClass], r15
0x140029a6c  lea     edx, [r9-0Ah]
0x140029a70  lea     r8d, [r9-7]
0x140029a74  call    WPP_RECORDER_SF_sDd
0x140029a79  jmp     loc_140029918
0x140029a7e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140029a85  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140029a8c  jz      short loc_140029AF3
0x140029a8e  mov     [rsp+110h+var_D0], eax
0x140029a92  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140029a99  mov     r9d, 0Dh
0x140029a9f  mov     [rsp+110h+var_D8], r13
0x140029aa4  mov     dword ptr [rsp+110h+var_E0], 11Ah
0x140029aac  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140029ab3  mov     r8d, esi
0x140029ab6  lea     edx, [r9-0Bh]
0x140029aba  jmp     short loc_140029AD9
0x140029abc  mov     [rsp+110h+var_D0], eax
0x140029ac0  mov     r9d, 11h
0x140029ac6  mov     [rsp+110h+var_D8], r13
0x140029acb  mov     dl, 4
0x140029acd  mov     dword ptr [rsp+110h+var_E0], 1A6h
0x140029ad5  lea     r8d, [r9-0Ch]
0x140029ad9  mov     rcx, cs:wil_details_featureDescriptors_a
0x140029ae0  mov     [rsp+110h+LengthReturned], r14
0x140029ae5  mov     qword ptr [rsp+110h+FileInformationClass], r15
0x140029aea  mov     rcx, [rcx+40h]
0x140029aee  call    WPP_RECORDER_SF_sDqd
0x140029af3  mov     ebx, 0C0000022h
0x140029af8  jmp     loc_140029918
0x140029afd  mov     eax, [r12+0Ch]
0x140029b02  test    al, 4
0x140029b04  jnz     loc_140029825
0x140029b0a  or      [rbp+3Fh+var_A8], 1
0x140029b0e  jmp     loc_1400297BF
0x140029b13  cmp     ebx, 0C000003Ah
0x140029b19  jz      loc_140029816
0x140029b1f  lea     rdi, WPP_RECORDER_INITIALIZED
0x140029b26  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140029b2d  jz      short loc_140029B79
0x140029b2f  mov     rcx, cs:wil_details_featureDescriptors_a
0x140029b36  lea     rax, [rbp+3Fh+var_78]
0x140029b3a  mov     [rsp+110h+var_D0], ebx
0x140029b3e  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140029b45  mov     [rsp+110h+var_D8], rax
0x140029b4a  lea     r15, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140029b51  mov     r9d, 0Fh
0x140029b57  mov     dword ptr [rsp+110h+var_E0], 162h
0x140029b5f  mov     rcx, [rcx+40h]
0x140029b63  mov     r8d, esi
0x140029b66  mov     [rsp+110h+LengthReturned], r14
0x140029b6b  mov     qword ptr [rsp+110h+FileInformationClass], r15
0x140029b70  lea     edx, [r9-0Dh]
  ... truncated ...
```
