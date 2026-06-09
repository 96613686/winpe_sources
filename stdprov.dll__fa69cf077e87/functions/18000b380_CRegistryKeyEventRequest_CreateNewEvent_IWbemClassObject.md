# CRegistryKeyEventRequest::CreateNewEvent(IWbemClassObject * *)

- ea: `0x18000b380`
- end: `0x18000b452`
- name: `?CreateNewEvent@CRegistryKeyEventRequest@@UEAAJPEAPEAUIWbemClassObject@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(CRegistryKeyEventRequest *__hidden this, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a68c`
- `0x18000b380`
- `0x180017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b3ff`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b3ff`
- `OLEAUT32!__imp_VariantInit` at `0x18000b3e9`
- `OLEAUT32!__imp_VariantInit` at `0x18000b3e9`
- `OLEAUT32!__imp_VariantClear` at `0x18000b433`
- `OLEAUT32!__imp_VariantClear` at `0x18000b433`

## string_xrefs

- `0x18000b411`: `KeyPath`

## pseudocode

```c
__int64 __fastcall CRegistryKeyEventRequest::CreateNewEvent(
        CRegistryKeyEventRequest *this,
        struct IWbemClassObject **a2)
{
  __int64 v2; // rax
  const OLECHAR *v6; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  struct IWbemClassObject *v8; // [rsp+60h] [rbp+10h] BYREF

  *a2 = 0;
  v2 = *((_QWORD *)this + 2);
  v8 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, struct IWbemClassObject **))(**(_QWORD **)(v2 + 40) + 120LL))(
         *(_QWORD *)(v2 + 40),
         0,
         &v8) < 0 )
    return 2147749894LL;
  CRegistryEventRequest::SetCommonProperties(this, v8);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = (const OLECHAR *)*((_QWORD *)this + 17);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v6);
  ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v8->lpVtbl->Put)(
    v8,
    L"KeyPath",
    0,
    &pvarg,
    0);
  VariantClear(&pvarg);
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x18000b380  mov     [rsp-8+arg_8], rbx
0x18000b385  mov     [rsp-8+arg_10], rdi
0x18000b38a  push    rbp
0x18000b38b  mov     rbp, rsp
0x18000b38e  sub     rsp, 50h
0x18000b392  mov     qword ptr [rdx], 0
0x18000b399  lea     r8, [rbp+arg_0]
0x18000b39d  mov     rax, [rcx+10h]
0x18000b3a1  mov     rbx, rcx
0x18000b3a4  mov     [rbp+arg_0], 0
0x18000b3ac  mov     rdi, rdx
0x18000b3af  xor     edx, edx
0x18000b3b1  mov     rcx, [rax+28h]
0x18000b3b5  mov     rax, [rcx]
0x18000b3b8  mov     rax, [rax+78h]
0x18000b3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3c1  test    eax, eax
0x18000b3c3  jns     short loc_18000B3CC
0x18000b3c5  mov     eax, 80041006h
0x18000b3ca  jmp     short loc_18000B442
0x18000b3cc  mov     rdx, [rbp+arg_0]; struct IWbemClassObject *
0x18000b3d0  mov     rcx, rbx; this
0x18000b3d3  call    ?SetCommonProperties@CRegistryEventRequest@@IEAAJPEAUIWbemClassObject@@@Z; CRegistryEventRequest::SetCommonProperties(IWbemClassObject *)
0x18000b3d8  xorps   xmm0, xmm0
0x18000b3db  lea     rcx, [rbp+pvarg]; pvarg
0x18000b3df  xor     eax, eax
0x18000b3e1  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000b3e5  mov     qword ptr [rbp+pvarg+10h], rax
0x18000b3e9  call    cs:__imp_VariantInit
0x18000b3ef  mov     rcx, [rbx+88h]; psz
0x18000b3f6  mov     eax, 8
0x18000b3fb  mov     word ptr [rbp+pvarg], ax
0x18000b3ff  call    cs:__imp_SysAllocString
0x18000b405  mov     rcx, [rbp+arg_0]
0x18000b409  lea     r9, [rbp+pvarg]
0x18000b40d  mov     qword ptr [rbp+pvarg+8], rax
0x18000b411  lea     rdx, aKeypath; "KeyPath"
0x18000b418  xor     r8d, r8d
0x18000b41b  mov     [rsp+50h+var_30], 0
0x18000b423  mov     rax, [rcx]
0x18000b426  mov     rax, [rax+28h]
0x18000b42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b42f  lea     rcx, [rbp+pvarg]; pvarg
0x18000b433  call    cs:__imp_VariantClear
0x18000b439  mov     rax, [rbp+arg_0]
0x18000b43d  mov     [rdi], rax
0x18000b440  xor     eax, eax
0x18000b442  mov     rbx, [rsp+50h+arg_8]
0x18000b447  mov     rdi, [rsp+50h+arg_10]
0x18000b44c  add     rsp, 50h
0x18000b450  pop     rbp
0x18000b451  retn
```
