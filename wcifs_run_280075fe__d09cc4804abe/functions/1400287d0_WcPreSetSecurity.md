# WcPreSetSecurity

- ea: `0x1400287d0`
- end: `0x140028935`
- name: `WcPreSetSecurity`
- size: `357`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140001bf8`
- `0x140014008`
- `0x140020988`
- `0x1400287d0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400288c1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400288c1`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140028897`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140028897`
- `FLTMGR!FltReleaseContext` at `0x1400288f9`
- `FLTMGR!FltReleaseContext` at `0x14002890f`
- `FLTMGR!FltReleaseContext` at `0x1400288f9`
- `FLTMGR!FltReleaseContext` at `0x14002890f`

## pseudocode

```c
__int64 __fastcall WcPreSetSecurity(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  void *v2; // r13
  struct _FILE_OBJECT *v3; // r12
  NTSTATUS v5; // edi
  unsigned int v6; // esi
  NTSTATUS v8; // eax

  v2 = *(void **)(a2 + 24);
  v3 = *(struct _FILE_OBJECT **)(a2 + 32);
  v5 = 0;
  v6 = 1;
  if ( (unsigned __int8)WcGetContextFileObject((PFLT_INSTANCE)v2, v3) && (unsigned __int8)WcIsPlaceHolder(0) )
  {
    if ( WcIsPlaceHolderDirectory(0, 0) )
    {
      v8 = WcSetPlaceHolderFlags(v2, v3, 0, 2);
    }
    else
    {
      if ( (*(_DWORD *)(MEMORY[0x40] + 12LL) & 2) != 0 )
        goto LABEL_2;
      if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)0x48) )
      {
        v5 = WcSetPlaceHolderFlags(v2, v3, 0, 2);
        ExReleaseRundownProtection((PEX_RUNDOWN_REF)0x48);
        goto LABEL_2;
      }
      v8 = WcExpandAndWait(CallbackData, v2, v3, 1, 9);
    }
    v5 = v8;
  }
LABEL_2:
  if ( v5 < 0 )
  {
    CallbackData->IoStatus.Status = v5;
    v6 = 4;
    CallbackData->IoStatus.Information = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1400287d0  mov     rax, rsp
0x1400287d3  mov     [rax+8], rbx
0x1400287d7  mov     [rax+18h], rbp
0x1400287db  push    rsi
0x1400287dc  push    rdi
0x1400287dd  push    r12
0x1400287df  push    r13
0x1400287e1  push    r15
0x1400287e3  sub     rsp, 30h
0x1400287e7  mov     r13, [rdx+18h]
0x1400287eb  lea     r9, [rax+10h]
0x1400287ef  mov     r12, [rdx+20h]
0x1400287f3  lea     r8, [rax+20h]
0x1400287f7  mov     rbp, rcx
0x1400287fa  xor     edi, edi
0x1400287fc  mov     rdx, r12; FileObject
0x1400287ff  mov     [rax+20h], rdi
0x140028803  mov     rcx, r13; Instance
0x140028806  mov     [rax+10h], rdi
0x14002880a  mov     esi, 1
0x14002880f  call    WcGetContextFileObject
0x140028814  mov     rbx, [rsp+58h+Context]
0x140028819  test    al, al
0x14002881b  jnz     short loc_140028854
0x14002881d  test    rbx, rbx
0x140028820  jnz     loc_1400288F6
0x140028826  cmp     [rsp+58h+arg_8], 0
0x14002882c  jnz     loc_14002890A
0x140028832  test    edi, edi
0x140028834  js      loc_140028920
0x14002883a  mov     rbx, [rsp+58h+arg_0]
0x14002883f  mov     eax, esi
0x140028841  mov     rbp, [rsp+58h+arg_10]
0x140028846  add     rsp, 30h
0x14002884a  pop     r15
0x14002884c  pop     r13
0x14002884e  pop     r12
0x140028850  pop     rdi
0x140028851  pop     rsi
0x140028852  retn
0x140028854  mov     rcx, rbx
0x140028857  call    WcIsPlaceHolder
0x14002885c  test    al, al
0x14002885e  jz      short loc_14002881D
0x140028860  mov     rdx, [rsp+58h+arg_8]
0x140028865  mov     rcx, rbx
0x140028868  call    WcIsPlaceHolderDirectory
0x14002886d  test    al, al
0x14002886f  jz      short loc_140028887
0x140028871  mov     r9d, 2
0x140028877  mov     r8, rbx
0x14002887a  mov     rdx, r12
0x14002887d  mov     rcx, r13
0x140028880  call    WcSetPlaceHolderFlags
0x140028885  jmp     short loc_1400288EF
0x140028887  mov     rax, [rbx+40h]
0x14002888b  mov     ecx, [rax+0Ch]
0x14002888e  test    cl, 2
0x140028891  jnz     short loc_14002881D
0x140028893  lea     rcx, [rbx+48h]; RunRef
0x140028897  call    cs:__imp_ExAcquireRundownProtection
0x14002889e  nop     dword ptr [rax+rax+00h]
0x1400288a3  test    al, al
0x1400288a5  jz      short loc_1400288D2
0x1400288a7  mov     r9d, 2
0x1400288ad  mov     r8, rbx
0x1400288b0  mov     rdx, r12
0x1400288b3  mov     rcx, r13
0x1400288b6  call    WcSetPlaceHolderFlags
0x1400288bb  lea     rcx, [rbx+48h]; RunRef
0x1400288bf  mov     edi, eax
0x1400288c1  call    cs:__imp_ExReleaseRundownProtection
0x1400288c8  nop     dword ptr [rax+rax+00h]
0x1400288cd  jmp     loc_14002881D
0x1400288d2  mov     [rsp+58h+var_30], 9; int
0x1400288da  mov     r9, rbx
0x1400288dd  mov     r8, r12; Object
0x1400288e0  mov     [rsp+58h+var_38], esi; int
0x1400288e4  mov     rdx, r13; FltObject
0x1400288e7  mov     rcx, rbp; CallbackData
0x1400288ea  call    WcExpandAndWait
0x1400288ef  mov     edi, eax
0x1400288f1  jmp     loc_14002881D
0x1400288f6  mov     rcx, rbx; Context
0x1400288f9  call    cs:__imp_FltReleaseContext
0x140028900  nop     dword ptr [rax+rax+00h]
0x140028905  jmp     loc_140028826
0x14002890a  mov     rcx, [rsp+58h+arg_8]; Context
0x14002890f  call    cs:__imp_FltReleaseContext
0x140028916  nop     dword ptr [rax+rax+00h]
0x14002891b  jmp     loc_140028832
0x140028920  mov     [rbp+18h], edi
0x140028923  mov     esi, 4
0x140028928  mov     qword ptr [rbp+20h], 0
0x140028930  jmp     loc_14002883A
```
