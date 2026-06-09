# WcPreSetSecurity

- ea: `0x140028820`
- end: `0x140028985`
- name: `WcPreSetSecurity`
- size: `357`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140001bf8`
- `0x140014008`
- `0x140020988`
- `0x140028820`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140028911`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140028911`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400288e7`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400288e7`
- `FLTMGR!FltReleaseContext` at `0x140028949`
- `FLTMGR!FltReleaseContext` at `0x14002895f`
- `FLTMGR!FltReleaseContext` at `0x140028949`
- `FLTMGR!FltReleaseContext` at `0x14002895f`

## pseudocode

```c
__int64 __fastcall WcPreSetSecurity(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  struct _FLT_INSTANCE *v2; // r13
  struct _FILE_OBJECT *v3; // r12
  NTSTATUS v5; // edi
  unsigned int v6; // esi
  char ContextFileObject; // al
  struct _EX_RUNDOWN_REF *v8; // rbx
  NTSTATUS v10; // eax
  PFLT_CONTEXT v11; // [rsp+68h] [rbp+10h] BYREF
  PFLT_CONTEXT Context; // [rsp+78h] [rbp+20h] BYREF

  v2 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v3 = *(struct _FILE_OBJECT **)(a2 + 32);
  v5 = 0;
  Context = 0;
  v11 = 0;
  v6 = 1;
  ContextFileObject = WcGetContextFileObject(v2, v3, &Context, &v11);
  v8 = (struct _EX_RUNDOWN_REF *)Context;
  if ( ContextFileObject && WcIsPlaceHolder((__int64)Context) )
  {
    if ( WcIsPlaceHolderDirectory((__int64)v8, (__int64)v11) )
    {
      v10 = WcSetPlaceHolderFlags(v2, v3, v8, 2);
    }
    else
    {
      if ( (*(_DWORD *)(v8[8].Count + 12) & 2) != 0 )
        goto LABEL_2;
      if ( ExAcquireRundownProtection(v8 + 9) )
      {
        v5 = WcSetPlaceHolderFlags(v2, v3, v8, 2);
        ExReleaseRundownProtection(v8 + 9);
        goto LABEL_2;
      }
      v10 = WcExpandAndWait(CallbackData, v2, v3, (__int64)v8, 1, 9);
    }
    v5 = v10;
  }
LABEL_2:
  if ( v8 )
    FltReleaseContext(v8);
  if ( v11 )
    FltReleaseContext(v11);
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
0x140028820  mov     rax, rsp
0x140028823  mov     [rax+8], rbx
0x140028827  mov     [rax+18h], rbp
0x14002882b  push    rsi
0x14002882c  push    rdi
0x14002882d  push    r12
0x14002882f  push    r13
0x140028831  push    r15
0x140028833  sub     rsp, 30h
0x140028837  mov     r13, [rdx+18h]
0x14002883b  lea     r9, [rax+10h]
0x14002883f  mov     r12, [rdx+20h]
0x140028843  lea     r8, [rax+20h]
0x140028847  mov     rbp, rcx
0x14002884a  xor     edi, edi
0x14002884c  mov     rdx, r12; FileObject
0x14002884f  mov     [rax+20h], rdi
0x140028853  mov     rcx, r13; Instance
0x140028856  mov     [rax+10h], rdi
0x14002885a  mov     esi, 1
0x14002885f  call    WcGetContextFileObject
0x140028864  mov     rbx, [rsp+58h+Context]
0x140028869  test    al, al
0x14002886b  jnz     short loc_1400288A4
0x14002886d  test    rbx, rbx
0x140028870  jnz     loc_140028946
0x140028876  cmp     [rsp+58h+arg_8], 0
0x14002887c  jnz     loc_14002895A
0x140028882  test    edi, edi
0x140028884  js      loc_140028970
0x14002888a  mov     rbx, [rsp+58h+arg_0]
0x14002888f  mov     eax, esi
0x140028891  mov     rbp, [rsp+58h+arg_10]
0x140028896  add     rsp, 30h
0x14002889a  pop     r15
0x14002889c  pop     r13
0x14002889e  pop     r12
0x1400288a0  pop     rdi
0x1400288a1  pop     rsi
0x1400288a2  retn
0x1400288a4  mov     rcx, rbx
0x1400288a7  call    WcIsPlaceHolder
0x1400288ac  test    al, al
0x1400288ae  jz      short loc_14002886D
0x1400288b0  mov     rdx, [rsp+58h+arg_8]
0x1400288b5  mov     rcx, rbx
0x1400288b8  call    WcIsPlaceHolderDirectory
0x1400288bd  test    al, al
0x1400288bf  jz      short loc_1400288D7
0x1400288c1  mov     r9d, 2
0x1400288c7  mov     r8, rbx
0x1400288ca  mov     rdx, r12
0x1400288cd  mov     rcx, r13
0x1400288d0  call    WcSetPlaceHolderFlags
0x1400288d5  jmp     short loc_14002893F
0x1400288d7  mov     rax, [rbx+40h]
0x1400288db  mov     ecx, [rax+0Ch]
0x1400288de  test    cl, 2
0x1400288e1  jnz     short loc_14002886D
0x1400288e3  lea     rcx, [rbx+48h]; RunRef
0x1400288e7  call    cs:__imp_ExAcquireRundownProtection
0x1400288ee  nop     dword ptr [rax+rax+00h]
0x1400288f3  test    al, al
0x1400288f5  jz      short loc_140028922
0x1400288f7  mov     r9d, 2
0x1400288fd  mov     r8, rbx
0x140028900  mov     rdx, r12
0x140028903  mov     rcx, r13
0x140028906  call    WcSetPlaceHolderFlags
0x14002890b  lea     rcx, [rbx+48h]; RunRef
0x14002890f  mov     edi, eax
0x140028911  call    cs:__imp_ExReleaseRundownProtection
0x140028918  nop     dword ptr [rax+rax+00h]
0x14002891d  jmp     loc_14002886D
0x140028922  mov     [rsp+58h+var_30], 9; int
0x14002892a  mov     r9, rbx
0x14002892d  mov     r8, r12; Object
0x140028930  mov     [rsp+58h+var_38], esi; int
0x140028934  mov     rdx, r13; FltObject
0x140028937  mov     rcx, rbp; CallbackData
0x14002893a  call    WcExpandAndWait
0x14002893f  mov     edi, eax
0x140028941  jmp     loc_14002886D
0x140028946  mov     rcx, rbx; Context
0x140028949  call    cs:__imp_FltReleaseContext
0x140028950  nop     dword ptr [rax+rax+00h]
0x140028955  jmp     loc_140028876
0x14002895a  mov     rcx, [rsp+58h+arg_8]; Context
0x14002895f  call    cs:__imp_FltReleaseContext
0x140028966  nop     dword ptr [rax+rax+00h]
0x14002896b  jmp     loc_140028882
0x140028970  mov     [rbp+18h], edi
0x140028973  mov     esi, 4
0x140028978  mov     qword ptr [rbp+20h], 0
0x140028980  jmp     loc_14002888A
```
