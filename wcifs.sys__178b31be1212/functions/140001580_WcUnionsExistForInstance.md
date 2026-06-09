# WcUnionsExistForInstance

- ea: `0x140001580`
- end: `0x1400016ad`
- name: `WcUnionsExistForInstance`
- size: `301`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, _DWORD *, _DWORD *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400149c0`
- `0x14001a148`
- `0x140024090`
- `0x140024380`
- `0x140024880`
- `0x1400260d0`
- `0x140027780`
- `0x140028d00`

## callees

- `0x140001580`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x1400015ed`
- `ntoskrnl!PsIsHostSilo` at `0x1400015ed`
- `ntoskrnl!IoGetSilo` at `0x1400015db`
- `ntoskrnl!IoGetSilo` at `0x1400015db`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140001677`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140001677`
- `ntoskrnl!PsGetSiloContext` at `0x140001646`
- `ntoskrnl!PsGetSiloContext` at `0x140001646`
- `FLTMGR!FltReleaseContext` at `0x140001616`
- `FLTMGR!FltReleaseContext` at `0x140001616`
- `FLTMGR!FltGetInstanceContext` at `0x1400015af`
- `FLTMGR!FltGetInstanceContext` at `0x1400015af`

## pseudocode

```c
__int64 __fastcall WcUnionsExistForInstance(struct _FLT_INSTANCE *a1, __int64 a2, _DWORD *a3, _DWORD *a4)
{
  PFLT_CONTEXT v7; // rcx
  __int64 v8; // rax
  unsigned __int8 v9; // bl
  __int64 Silo; // rdi
  char IsHostSilo; // al
  __int64 v13; // rdx
  int v14; // r8d
  int v15; // edx
  PFLT_CONTEXT Context; // [rsp+20h] [rbp-18h] BYREF
  __int64 v17; // [rsp+28h] [rbp-10h] BYREF

  Context = 0;
  v17 = 0;
  FltGetInstanceContext(a1, &Context);
  v7 = Context;
  v8 = *((_QWORD *)Context + 7);
  if ( v8 )
  {
    v14 = *(_DWORD *)(v8 + 36);
    v15 = *(_DWORD *)(v8 + 40);
  }
  else if ( *((_DWORD *)Context + 16) )
  {
    v14 = *((_DWORD *)Context + 70);
    v15 = *((_DWORD *)Context + 71);
  }
  else
  {
    v9 = 0;
    Silo = IoGetSilo(a2);
    IsHostSilo = PsIsHostSilo(Silo);
    v7 = Context;
    if ( IsHostSilo )
      goto LABEL_4;
    v13 = *((unsigned int *)Context + 4);
    if ( (_DWORD)v13 == -1 )
      goto LABEL_4;
    if ( (int)PsGetSiloContext(Silo, v13, &v17) < 0 )
    {
      v7 = Context;
      goto LABEL_4;
    }
    v14 = *(_DWORD *)(v17 + 216);
    v15 = *(_DWORD *)(v17 + 220);
    v7 = Context;
  }
  v9 = 1;
  if ( a3 )
    *a3 = v14;
  if ( a4 )
    *a4 = v15;
LABEL_4:
  if ( v7 )
    FltReleaseContext(v7);
  if ( v17 )
    PsDereferenceSiloContext(v17);
  return v9;
}

```

## disassembly

```asm
0x140001580  push    rbx
0x140001582  sub     rsp, 30h
0x140001586  mov     [rsp+38h+arg_0], rsi
0x14000158b  xor     eax, eax
0x14000158d  mov     [rsp+38h+arg_8], rdi
0x140001592  mov     rsi, r9
0x140001595  mov     rdi, rdx
0x140001598  mov     [rsp+38h+arg_10], r14
0x14000159d  lea     rdx, [rsp+38h+Context]; Context
0x1400015a2  mov     [rsp+38h+Context], rax
0x1400015a7  mov     r14, r8
0x1400015aa  mov     [rsp+38h+var_10], rax
0x1400015af  call    cs:__imp_FltGetInstanceContext
0x1400015b6  nop     dword ptr [rax+rax+00h]
0x1400015bb  mov     rcx, [rsp+38h+Context]
0x1400015c0  mov     rax, [rcx+38h]
0x1400015c4  test    rax, rax
0x1400015c7  jnz     loc_14000165D
0x1400015cd  cmp     [rcx+40h], eax
0x1400015d0  ja      loc_140001685
0x1400015d6  mov     rcx, rdi
0x1400015d9  xor     bl, bl
0x1400015db  call    cs:__imp_IoGetSilo
0x1400015e2  nop     dword ptr [rax+rax+00h]
0x1400015e7  mov     rcx, rax
0x1400015ea  mov     rdi, rax
0x1400015ed  call    cs:__imp_PsIsHostSilo
0x1400015f4  nop     dword ptr [rax+rax+00h]
0x1400015f9  mov     rcx, [rsp+38h+Context]; Context
0x1400015fe  test    al, al
0x140001600  jz      short loc_140001636
0x140001602  mov     r14, [rsp+38h+arg_10]
0x140001607  mov     rdi, [rsp+38h+arg_8]
0x14000160c  mov     rsi, [rsp+38h+arg_0]
0x140001611  test    rcx, rcx
0x140001614  jz      short loc_140001622
0x140001616  call    cs:__imp_FltReleaseContext
0x14000161d  nop     dword ptr [rax+rax+00h]
0x140001622  mov     rcx, [rsp+38h+var_10]
0x140001627  test    rcx, rcx
0x14000162a  jnz     short loc_140001677
0x14000162c  movzx   eax, bl
0x14000162f  add     rsp, 30h
0x140001633  pop     rbx
0x140001634  retn
0x140001636  mov     edx, [rcx+10h]
0x140001639  cmp     edx, 0FFFFFFFFh
0x14000163c  jz      short loc_140001602
0x14000163e  lea     r8, [rsp+38h+var_10]
0x140001643  mov     rcx, rdi
0x140001646  call    cs:__imp_PsGetSiloContext
0x14000164d  nop     dword ptr [rax+rax+00h]
0x140001652  test    eax, eax
0x140001654  jns     short loc_140001694
0x140001656  mov     rcx, [rsp+38h+Context]
0x14000165b  jmp     short loc_140001602
0x14000165d  mov     r8d, [rax+24h]
0x140001661  mov     edx, [rax+28h]
0x140001664  mov     bl, 1
0x140001666  test    r14, r14
0x140001669  jz      short loc_14000166E
0x14000166b  mov     [r14], r8d
0x14000166e  test    rsi, rsi
0x140001671  jz      short loc_140001602
0x140001673  mov     [rsi], edx
0x140001675  jmp     short loc_140001602
0x140001677  call    cs:__imp_PsDereferenceSiloContext
0x14000167e  nop     dword ptr [rax+rax+00h]
0x140001683  jmp     short loc_14000162C
0x140001685  mov     r8d, [rcx+118h]
0x14000168c  mov     edx, [rcx+11Ch]
0x140001692  jmp     short loc_140001664
0x140001694  mov     rcx, [rsp+38h+var_10]
0x140001699  mov     r8d, [rcx+0D8h]
0x1400016a0  mov     edx, [rcx+0DCh]
0x1400016a6  mov     rcx, [rsp+38h+Context]
0x1400016ab  jmp     short loc_140001664
```
