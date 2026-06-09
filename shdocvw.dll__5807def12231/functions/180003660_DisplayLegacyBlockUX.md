# DisplayLegacyBlockUX

- ea: `0x180003660`
- end: `0x180003807`
- name: `DisplayLegacyBlockUX`
- size: `423`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005914`
- `0x180015dc4`
- `0x18001a078`
- `0x18001d120`

## callees

- `0x180003660`
- `0x180003810`
- `0x1800067a0`
- `0x18001a3f0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800036ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800036ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DisplayLegacyBlockUX(
        __int64 a1,
        const unsigned __int16 *a2,
        bool a3,
        __int64 a4,
        struct IUnknown *ppv)
{
  int (__fastcall ***v9)(void *, GUID *, void **); // rbx
  char v10; // r14
  unsigned int v11; // r8d
  const struct _GUID *v12; // r9
  int v13; // edi
  void *v14; // rcx
  void *v15; // rcx
  int (__fastcall *v16)(void *, GUID *, void **); // rdi
  unsigned __int8 v17; // di
  __int64 result; // rax
  unsigned int v19; // edi
  void *v20; // [rsp+30h] [rbp-18h] BYREF
  void *v21; // [rsp+38h] [rbp-10h]

  LODWORD(ppv->lpVtbl) |= 4u;
  v9 = 0;
  v21 = 0;
  v10 = 0;
  v20 = 0;
  ppv = 0;
  if ( CoCreateInstance(
         &CLSID_PersistentZoneIdentifier,
         0,
         0x4001u,
         &GUID_cd45f185_1b21_48e2_967b_ead743a8914e,
         (LPVOID *)&ppv) < 0
    || (v13 = _AndLoadFromFile(ppv, a2, v11, v12, &v20),
        ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv),
        v13 < 0)
    || (LODWORD(ppv) = 0, (*(int (__fastcall **)(void *, struct IUnknown **))(*(_QWORD *)v20 + 24LL))(v20, &ppv) < 0) )
  {
    v14 = v20;
  }
  else
  {
    v10 = 1;
    v9 = (int (__fastcall ***)(void *, GUID *, void **))v20;
    v14 = 0;
    v21 = v20;
  }
  if ( v14 )
  {
    v20 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = 0;
  v20 = 0;
  if ( v9 )
  {
    v16 = **v9;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    if ( v16(v9, &GUID_5e4d4a35_76e4_4f30_9a3c_a40c65fadff2, &v20) >= 0 )
    {
      LODWORD(ppv) = 0;
      if ( (*(int (__fastcall **)(void *, const unsigned __int16 *, struct IUnknown **))(*(_QWORD *)v20 + 24LL))(
             v20,
             a2,
             &ppv) >= 0 )
      {
        v17 = (_DWORD)ppv != 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
        goto LABEL_16;
      }
    }
    v15 = v20;
  }
  if ( v15 )
  {
    v20 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v17 = 0;
LABEL_16:
  result = anonymous_namespace_::ShowLegacyBlockUX(a1, a2, a3, a4, v10, v17);
  v19 = result;
  if ( v9 )
  {
    ((void (__fastcall *)(int (__fastcall ***)(void *, GUID *, void **)))(*v9)[2])(v9);
    return v19;
  }
  return result;
}

```

## disassembly

```asm
0x180003660  push    rbp
0x180003662  push    rbx
0x180003663  push    rsi
0x180003664  push    rdi
0x180003665  push    r12
0x180003667  push    r13
0x180003669  push    r14
0x18000366b  push    r15
0x18000366d  mov     rbp, rsp
0x180003670  sub     rsp, 48h
0x180003674  mov     r15, r9
0x180003677  movzx   r12d, r8b
0x18000367b  mov     rsi, rdx
0x18000367e  mov     r13, rcx
0x180003681  mov     rax, [rbp+arg_20]
0x180003685  or      dword ptr [rax], 4
0x180003688  xor     edi, edi
0x18000368a  mov     ebx, edi
0x18000368c  mov     [rbp+var_10], rbx
0x180003690  mov     r14d, edi
0x180003693  mov     [rbp+var_18], rdi
0x180003697  mov     [rbp+arg_20], rdi
0x18000369b  lea     rax, [rbp+arg_20]
0x18000369f  mov     [rsp+48h+ppv], rax; ppv
0x1800036a4  lea     r9, _GUID_cd45f185_1b21_48e2_967b_ead743a8914e; riid
0x1800036ab  xor     edx, edx; pUnkOuter
0x1800036ad  mov     r8d, 4001h; dwClsContext
0x1800036b3  lea     rcx, CLSID_PersistentZoneIdentifier; rclsid
0x1800036ba  call    cs:__imp_CoCreateInstance
0x1800036c0  test    eax, eax
0x1800036c2  js      short loc_180003720
0x1800036c4  lea     rax, [rbp+var_18]
0x1800036c8  mov     [rsp+48h+ppv], rax; void **
0x1800036cd  mov     rdx, rsi; unsigned __int16 *
0x1800036d0  mov     rcx, [rbp+arg_20]; struct IUnknown *
0x1800036d4  call    ?_AndLoadFromFile@@YAJPEAUIUnknown@@PEBGKAEBU_GUID@@PEAPEAX@Z; _AndLoadFromFile(IUnknown *,ushort const *,ulong,_GUID const &,void * *)
0x1800036d9  mov     edi, eax
0x1800036db  mov     rcx, [rbp+arg_20]
0x1800036df  mov     rdx, [rcx]
0x1800036e2  mov     rax, [rdx+10h]
0x1800036e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036eb  test    edi, edi
0x1800036ed  js      short loc_18000371E
0x1800036ef  xor     edi, edi
0x1800036f1  mov     dword ptr [rbp+arg_20], edi
0x1800036f4  mov     rcx, [rbp+var_18]
0x1800036f8  mov     rax, [rcx]
0x1800036fb  lea     rdx, [rbp+arg_20]
0x1800036ff  mov     rax, [rax+18h]
0x180003703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003708  test    eax, eax
0x18000370a  js      short loc_180003720
0x18000370c  mov     r14d, 1
0x180003712  mov     rbx, [rbp+var_18]
0x180003716  mov     ecx, edi
0x180003718  mov     [rbp+var_10], rbx
0x18000371c  jmp     short loc_180003724
0x18000371e  xor     edi, edi
0x180003720  mov     rcx, [rbp+var_18]
0x180003724  test    rcx, rcx
0x180003727  jz      short loc_18000373A
0x180003729  mov     [rbp+var_18], rdi
0x18000372d  mov     rax, [rcx]
0x180003730  mov     rax, [rax+10h]
0x180003734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003739  nop
0x18000373a  mov     rcx, rdi
0x18000373d  mov     [rbp+var_18], rcx
0x180003741  test    rbx, rbx
0x180003744  jz      short loc_1800037A6
0x180003746  mov     rax, [rbx]
0x180003749  mov     rdi, [rax]
0x18000374c  lea     rcx, [rbp+var_18]
0x180003750  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003755  lea     r8, [rbp+var_18]
0x180003759  lea     rdx, _GUID_5e4d4a35_76e4_4f30_9a3c_a40c65fadff2
0x180003760  mov     rcx, rbx
0x180003763  mov     rax, rdi
0x180003766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000376b  nop
0x18000376c  xor     edi, edi
0x18000376e  test    eax, eax
0x180003770  js      short loc_1800037A2
0x180003772  mov     dword ptr [rbp+arg_20], edi
0x180003775  mov     rcx, [rbp+var_18]
0x180003779  mov     rax, [rcx]
0x18000377c  lea     r8, [rbp+arg_20]
0x180003780  mov     rdx, rsi
0x180003783  mov     rax, [rax+18h]
0x180003787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378c  test    eax, eax
0x18000378e  js      short loc_1800037A2
0x180003790  cmp     dword ptr [rbp+arg_20], edi
0x180003793  setnz   dil
0x180003797  lea     rcx, [rbp+var_18]
0x18000379b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800037a0  jmp     short loc_1800037BF
0x1800037a2  mov     rcx, [rbp+var_18]
0x1800037a6  test    rcx, rcx
0x1800037a9  jz      short loc_1800037BC
0x1800037ab  mov     [rbp+var_18], rdi
0x1800037af  mov     rax, [rcx]
0x1800037b2  mov     rax, [rax+10h]
0x1800037b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037bb  nop
0x1800037bc  xor     dil, dil
0x1800037bf  mov     [rsp+48h+var_20], dil
0x1800037c4  mov     dword ptr [rsp+48h+ppv], r14d
0x1800037c9  mov     r9, r15
0x1800037cc  movzx   r8d, r12b
0x1800037d0  mov     rdx, rsi
0x1800037d3  mov     rcx, r13
0x1800037d6  call    _anonymous_namespace___ShowLegacyBlockUX
0x1800037db  mov     edi, eax
0x1800037dd  test    rbx, rbx
0x1800037e0  jz      short loc_1800037F6
0x1800037e2  mov     rcx, [rbx]
0x1800037e5  mov     rax, [rcx+10h]
0x1800037e9  mov     rcx, rbx
0x1800037ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f1  nop
0x1800037f2  mov     eax, edi
0x1800037f4  jmp     short $+2
0x1800037f6  add     rsp, 48h
0x1800037fa  pop     r15
0x1800037fc  pop     r14
0x1800037fe  pop     r13
0x180003800  pop     r12
0x180003802  pop     rdi
0x180003803  pop     rsi
0x180003804  pop     rbx
0x180003805  pop     rbp
0x180003806  retn
```
