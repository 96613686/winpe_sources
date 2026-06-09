# WcGetSetSiloContext

- ea: `0x140014570`
- end: `0x1400148b4`
- name: `WcGetSetSiloContext`
- size: `836`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140020e60`

## callees

- `0x1400020c4`
- `0x140004198`
- `0x1400080c0`
- `0x140014570`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x14001459c`
- `ntoskrnl!PsIsHostSilo` at `0x14001459c`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140014720`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140014720`
- `ntoskrnl!ExInitializeResourceLite` at `0x140014730`
- `ntoskrnl!ExInitializeResourceLite` at `0x140014730`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400147b3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140014898`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400147b3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140014898`
- `ntoskrnl!PsCreateSiloContext` at `0x14001469d`
- `ntoskrnl!PsCreateSiloContext` at `0x14001469d`
- `ntoskrnl!PsInsertSiloContext` at `0x14001474a`
- `ntoskrnl!PsInsertSiloContext` at `0x14001474a`
- `ntoskrnl!PsGetSiloContext` at `0x140014666`
- `ntoskrnl!PsGetSiloContext` at `0x1400147d5`
- `ntoskrnl!PsGetSiloContext` at `0x140014666`
- `ntoskrnl!PsGetSiloContext` at `0x1400147d5`
- `FLTMGR!FltReleaseContext` at `0x140014883`
- `FLTMGR!FltReleaseContext` at `0x140014883`
- `FLTMGR!FltGetInstanceContext` at `0x140014615`
- `FLTMGR!FltGetInstanceContext` at `0x140014615`

## pseudocode

```c
__int64 __fastcall WcGetSetSiloContext(__int64 a1, struct _FLT_INSTANCE *a2, int a3, int a4, _QWORD *a5)
{
  __int64 v9; // rdx
  unsigned int v10; // ebx
  int v11; // r9d
  int SiloContext; // eax
  int v13; // eax
  __int64 v14; // rbx
  int inserted; // eax
  int v16; // eax
  __int64 v17; // rax
  char v19; // [rsp+30h] [rbp-28h]
  char v20; // [rsp+38h] [rbp-20h]
  __int64 v21; // [rsp+40h] [rbp-18h] BYREF
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-10h] BYREF

  v21 = 0;
  Context = 0;
  if ( (unsigned __int8)PsIsHostSilo(a1) )
  {
    v10 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_26;
    v20 = 13;
    v11 = 15;
    v19 = -59;
    goto LABEL_4;
  }
  FltGetInstanceContext(a2, &Context);
  v9 = *((unsigned int *)Context + 4);
  if ( (_DWORD)v9 == -1 )
  {
    v10 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = 13;
      v11 = 16;
      v19 = -47;
LABEL_4:
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        9,
        v11,
        (__int64)WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\context.c",
        v19,
        v20);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  SiloContext = PsGetSiloContext(a1, v9, &v21);
  v10 = SiloContext;
  if ( SiloContext != -1073741275 )
  {
    if ( SiloContext < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = SiloContext;
        v11 = 21;
        v19 = 17;
        goto LABEL_4;
      }
      goto LABEL_26;
    }
    goto LABEL_24;
  }
  v13 = PsCreateSiloContext(a1, 224, 512, WcCleanupSiloContext, &v21);
  v10 = v13;
  if ( v13 >= 0 )
  {
    v14 = v21;
    memset((void *)(v21 + 8), 0, 0xD0u);
    *(_QWORD *)v14 = a1;
    *(_DWORD *)(v14 + 216) = a3;
    *(_DWORD *)(v14 + 220) = a4;
    RtlInitializeGenericTableAvl(
      (PRTL_AVL_TABLE)(v14 + 112),
      (PRTL_AVL_COMPARE_ROUTINE)WcCompareUnionTableEntry,
      WcAllocateUnionTableEntry,
      WcFreeUnionTableEntry,
      0);
    ExInitializeResourceLite((PERESOURCE)(v14 + 8));
    inserted = PsInsertSiloContext(a1, *((unsigned int *)Context + 4), v21);
    v10 = inserted;
    if ( inserted == -1073741637 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 3;
        WPP_RECORDER_SF_sD(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          9,
          18,
          (__int64)WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\context.c",
          248);
      }
      PsDereferenceSiloContext(v21);
      v21 = 0;
      v16 = PsGetSiloContext(a1, *((unsigned int *)Context + 4), &v21);
      v10 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v20 = v16;
          v11 = 19;
          v19 = 1;
          goto LABEL_4;
        }
        goto LABEL_26;
      }
LABEL_25:
      v10 = 0;
      goto LABEL_26;
    }
    if ( inserted < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = inserted;
        v11 = 20;
        v19 = 11;
        goto LABEL_4;
      }
      goto LABEL_26;
    }
LABEL_24:
    v17 = v21;
    v21 = 0;
    *a5 = v17;
    goto LABEL_25;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v20 = v13;
    v11 = 17;
    v19 = -27;
    goto LABEL_4;
  }
LABEL_26:
  if ( Context )
    FltReleaseContext(Context);
  if ( v21 )
    PsDereferenceSiloContext(v21);
  return v10;
}

```

## disassembly

```asm
0x140014570  push    rbp
0x140014572  push    rbx
0x140014573  push    rsi
0x140014574  push    rdi
0x140014575  push    r14
0x140014577  push    r15
0x140014579  mov     rbp, rsp
0x14001457c  sub     rsp, 58h
0x140014580  mov     edi, r9d
0x140014583  mov     [rbp+var_18], 0
0x14001458b  mov     esi, r8d
0x14001458e  mov     [rbp+Context], 0
0x140014596  mov     rbx, rdx
0x140014599  mov     r15, rcx
0x14001459c  call    cs:__imp_PsIsHostSilo
0x1400145a3  nop     dword ptr [rax+rax+00h]
0x1400145a8  test    al, al
0x1400145aa  jz      short loc_14001460E
0x1400145ac  mov     eax, 0C000000Dh
0x1400145b1  mov     ebx, eax
0x1400145b3  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400145ba  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400145c1  jz      loc_14001487A
0x1400145c7  mov     dword ptr [rsp+58h+var_20], eax
0x1400145cb  mov     r9d, 0Fh
0x1400145d1  mov     dword ptr [rsp+58h+var_28], 3C5h
0x1400145d9  lea     rsi, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\wcifs\\context."...
0x1400145e0  lea     r14, WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids
0x1400145e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400145ee  mov     r8d, 9
0x1400145f4  mov     [rsp+58h+var_30], rsi
0x1400145f9  mov     dl, 2
0x1400145fb  mov     [rsp+58h+TableContext], r14
0x140014600  mov     rcx, [rcx+40h]
0x140014604  call    WPP_RECORDER_SF_sDd
0x140014609  jmp     loc_14001487A
0x14001460e  lea     rdx, [rbp+Context]; Context
0x140014612  mov     rcx, rbx; Instance
0x140014615  call    cs:__imp_FltGetInstanceContext
0x14001461c  nop     dword ptr [rax+rax+00h]
0x140014621  mov     rax, [rbp+Context]
0x140014625  mov     edx, [rax+10h]
0x140014628  cmp     edx, 0FFFFFFFFh
0x14001462b  jnz     short loc_14001465F
0x14001462d  mov     eax, 0C000000Dh
0x140014632  mov     ebx, eax
0x140014634  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001463b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140014642  jz      loc_14001487A
0x140014648  mov     dword ptr [rsp+58h+var_20], eax
0x14001464c  mov     r9d, 10h
0x140014652  mov     dword ptr [rsp+58h+var_28], 3D1h
0x14001465a  jmp     loc_1400145D9
0x14001465f  lea     r8, [rbp+var_18]
0x140014663  mov     rcx, r15
0x140014666  call    cs:__imp_PsGetSiloContext
0x14001466d  nop     dword ptr [rax+rax+00h]
0x140014672  mov     ebx, eax
0x140014674  cmp     eax, 0C0000225h
0x140014679  jnz     loc_14001483A
0x14001467f  lea     rax, [rbp+var_18]
0x140014683  mov     edx, 0E0h
0x140014688  lea     r9, WcCleanupSiloContext
0x14001468f  mov     [rsp+58h+TableContext], rax
0x140014694  mov     r8d, 200h
0x14001469a  mov     rcx, r15
0x14001469d  call    cs:__imp_PsCreateSiloContext
0x1400146a4  nop     dword ptr [rax+rax+00h]
0x1400146a9  mov     ebx, eax
0x1400146ab  test    eax, eax
0x1400146ad  jns     short loc_1400146DA
0x1400146af  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400146b6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400146bd  jz      loc_14001487A
0x1400146c3  mov     dword ptr [rsp+58h+var_20], eax
0x1400146c7  mov     r9d, 11h
0x1400146cd  mov     dword ptr [rsp+58h+var_28], 3E5h
0x1400146d5  jmp     loc_1400145D9
0x1400146da  mov     rbx, [rbp+var_18]
0x1400146de  xor     edx, edx; Val
0x1400146e0  mov     r8d, 0D0h; Size
0x1400146e6  lea     rcx, [rbx+8]; void *
0x1400146ea  call    memset
0x1400146ef  lea     rcx, [rbx+70h]; Table
0x1400146f3  mov     [rbx], r15
0x1400146f6  lea     r9, WcFreeUnionTableEntry; FreeRoutine
0x1400146fd  mov     [rbx+0D8h], esi
0x140014703  lea     r8, WcAllocateUnionTableEntry; AllocateRoutine
0x14001470a  mov     [rbx+0DCh], edi
0x140014710  lea     rdx, WcCompareUnionTableEntry; CompareRoutine
0x140014717  mov     [rsp+58h+TableContext], 0; TableContext
0x140014720  call    cs:__imp_RtlInitializeGenericTableAvl
0x140014727  nop     dword ptr [rax+rax+00h]
0x14001472c  lea     rcx, [rbx+8]; Resource
0x140014730  call    cs:__imp_ExInitializeResourceLite
0x140014737  nop     dword ptr [rax+rax+00h]
0x14001473c  mov     rdx, [rbp+Context]
0x140014740  mov     rcx, r15
0x140014743  mov     r8, [rbp+var_18]
0x140014747  mov     edx, [rdx+10h]
0x14001474a  call    cs:__imp_PsInsertSiloContext
0x140014751  nop     dword ptr [rax+rax+00h]
0x140014756  mov     ebx, eax
0x140014758  cmp     eax, 0C00000BBh
0x14001475d  jnz     loc_14001480F
0x140014763  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001476a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140014771  lea     rsi, aOnecoreBaseFsW_6; "onecore\\base\\fs\\wci\\wcifs\\context."...
0x140014778  lea     r14, WPP_950001495d7d34274b0ab8b7fcc7b560_Traceguids
0x14001477f  jz      short loc_1400147AF
0x140014781  mov     rcx, cs:WPP_GLOBAL_Control
0x140014788  mov     r9d, 12h
0x14001478e  mov     dword ptr [rsp+58h+var_28], 3F8h
0x140014796  mov     dl, 3
0x140014798  mov     [rsp+58h+var_30], rsi
0x14001479d  mov     [rsp+58h+TableContext], r14
0x1400147a2  mov     rcx, [rcx+40h]
0x1400147a6  lea     r8d, [r9-9]
0x1400147aa  call    WPP_RECORDER_SF_sD
0x1400147af  mov     rcx, [rbp+var_18]
0x1400147b3  call    cs:__imp_PsDereferenceSiloContext
0x1400147ba  nop     dword ptr [rax+rax+00h]
0x1400147bf  mov     rdx, [rbp+Context]
0x1400147c3  lea     r8, [rbp+var_18]
0x1400147c7  mov     [rbp+var_18], 0
0x1400147cf  mov     rcx, r15
0x1400147d2  mov     edx, [rdx+10h]
0x1400147d5  call    cs:__imp_PsGetSiloContext
0x1400147dc  nop     dword ptr [rax+rax+00h]
0x1400147e1  mov     ebx, eax
0x1400147e3  test    eax, eax
0x1400147e5  jns     loc_140014878
0x1400147eb  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400147f2  jz      loc_14001487A
0x1400147f8  mov     dword ptr [rsp+58h+var_20], eax
0x1400147fc  mov     r9d, 13h
0x140014802  mov     dword ptr [rsp+58h+var_28], 401h
0x14001480a  jmp     loc_1400145E7
0x14001480f  test    eax, eax
0x140014811  jns     short loc_140014865
0x140014813  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001481a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140014821  jz      short loc_14001487A
0x140014823  mov     dword ptr [rsp+58h+var_20], eax
0x140014827  mov     r9d, 14h
0x14001482d  mov     dword ptr [rsp+58h+var_28], 40Bh
0x140014835  jmp     loc_1400145D9
0x14001483a  test    eax, eax
0x14001483c  jns     short loc_140014865
0x14001483e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140014845  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001484c  jz      short loc_14001487A
0x14001484e  mov     dword ptr [rsp+58h+var_20], eax
0x140014852  mov     r9d, 15h
0x140014858  mov     dword ptr [rsp+58h+var_28], 411h
0x140014860  jmp     loc_1400145D9
0x140014865  mov     rax, [rbp+var_18]
0x140014869  mov     rcx, [rbp+arg_20]
0x14001486d  mov     [rbp+var_18], 0
0x140014875  mov     [rcx], rax
0x140014878  xor     ebx, ebx
0x14001487a  mov     rcx, [rbp+Context]; Context
0x14001487e  test    rcx, rcx
0x140014881  jz      short loc_14001488F
0x140014883  call    cs:__imp_FltReleaseContext
0x14001488a  nop     dword ptr [rax+rax+00h]
0x14001488f  mov     rcx, [rbp+var_18]
0x140014893  test    rcx, rcx
0x140014896  jz      short loc_1400148A4
0x140014898  call    cs:__imp_PsDereferenceSiloContext
0x14001489f  nop     dword ptr [rax+rax+00h]
0x1400148a4  mov     eax, ebx
0x1400148a6  add     rsp, 58h
0x1400148aa  pop     r15
0x1400148ac  pop     r14
0x1400148ae  pop     rdi
0x1400148af  pop     rsi
0x1400148b0  pop     rbx
0x1400148b1  pop     rbp
0x1400148b2  retn
```
