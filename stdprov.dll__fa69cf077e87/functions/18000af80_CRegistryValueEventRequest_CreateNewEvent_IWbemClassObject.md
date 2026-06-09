# CRegistryValueEventRequest::CreateNewEvent(IWbemClassObject * *)

- ea: `0x18000af80`
- end: `0x18000b08d`
- name: `?CreateNewEvent@CRegistryValueEventRequest@@UEAAJPEAPEAUIWbemClassObject@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(CRegistryValueEventRequest *__hidden this, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a68c`
- `0x18000af80`
- `0x180017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000affc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b041`
- `OLEAUT32!__imp_SysAllocString` at `0x18000affc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b041`
- `OLEAUT32!__imp_VariantInit` at `0x18000afe6`
- `OLEAUT32!__imp_VariantInit` at `0x18000afe6`
- `OLEAUT32!__imp_VariantClear` at `0x18000b030`
- `OLEAUT32!__imp_VariantClear` at `0x18000b075`
- `OLEAUT32!__imp_VariantClear` at `0x18000b030`
- `OLEAUT32!__imp_VariantClear` at `0x18000b075`

## string_xrefs

- `0x18000b00e`: `KeyPath`

## pseudocode

```c
__int64 __fastcall CRegistryValueEventRequest::CreateNewEvent(
        CRegistryValueEventRequest *this,
        struct IWbemClassObject **a2)
{
  __int64 v2; // rax
  const OLECHAR *v6; // rcx
  const OLECHAR *v7; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  struct IWbemClassObject *v9; // [rsp+80h] [rbp+28h] BYREF

  *a2 = 0;
  v2 = *((_QWORD *)this + 2);
  v9 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, struct IWbemClassObject **))(**(_QWORD **)(v2 + 48) + 120LL))(
         *(_QWORD *)(v2 + 48),
         0,
         &v9) < 0 )
    return 2147749894LL;
  CRegistryEventRequest::SetCommonProperties(this, v9);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = (const OLECHAR *)*((_QWORD *)this + 17);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v6);
  ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v9->lpVtbl->Put)(
    v9,
    L"KeyPath",
    0,
    &pvarg,
    0);
  VariantClear(&pvarg);
  v7 = (const OLECHAR *)*((_QWORD *)this + 28);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v7);
  ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v9->lpVtbl->Put)(
    v9,
    L"ValueName",
    0,
    &pvarg,
    0);
  VariantClear(&pvarg);
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x18000af80  push    rbp
0x18000af82  push    rbx
0x18000af83  push    rsi
0x18000af84  push    rdi
0x18000af85  mov     rbp, rsp
0x18000af88  sub     rsp, 58h
0x18000af8c  mov     qword ptr [rdx], 0
0x18000af93  lea     r8, [rbp+arg_0]
0x18000af97  mov     rax, [rcx+10h]
0x18000af9b  mov     rbx, rcx
0x18000af9e  mov     [rbp+arg_0], 0
0x18000afa6  mov     rdi, rdx
0x18000afa9  xor     edx, edx
0x18000afab  mov     rcx, [rax+30h]
0x18000afaf  mov     rax, [rcx]
0x18000afb2  mov     rax, [rax+78h]
0x18000afb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afbb  test    eax, eax
0x18000afbd  jns     short loc_18000AFC9
0x18000afbf  mov     eax, 80041006h
0x18000afc4  jmp     loc_18000B084
0x18000afc9  mov     rdx, [rbp+arg_0]; struct IWbemClassObject *
0x18000afcd  mov     rcx, rbx; this
0x18000afd0  call    ?SetCommonProperties@CRegistryEventRequest@@IEAAJPEAUIWbemClassObject@@@Z; CRegistryEventRequest::SetCommonProperties(IWbemClassObject *)
0x18000afd5  xorps   xmm0, xmm0
0x18000afd8  lea     rcx, [rbp+pvarg]; pvarg
0x18000afdc  xor     eax, eax
0x18000afde  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000afe2  mov     qword ptr [rbp+pvarg+10h], rax
0x18000afe6  call    cs:__imp_VariantInit
0x18000afec  mov     rcx, [rbx+88h]; psz
0x18000aff3  mov     esi, 8
0x18000aff8  mov     word ptr [rbp+pvarg], si
0x18000affc  call    cs:__imp_SysAllocString
0x18000b002  mov     rcx, [rbp+arg_0]
0x18000b006  lea     r9, [rbp+pvarg]
0x18000b00a  mov     qword ptr [rbp+pvarg+8], rax
0x18000b00e  lea     rdx, aKeypath; "KeyPath"
0x18000b015  xor     r8d, r8d
0x18000b018  mov     [rsp+58h+var_38], 0
0x18000b020  mov     rax, [rcx]
0x18000b023  mov     rax, [rax+28h]
0x18000b027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02c  lea     rcx, [rbp+pvarg]; pvarg
0x18000b030  call    cs:__imp_VariantClear
0x18000b036  mov     rcx, [rbx+0E0h]; psz
0x18000b03d  mov     word ptr [rbp+pvarg], si
0x18000b041  call    cs:__imp_SysAllocString
0x18000b047  mov     rcx, [rbp+arg_0]
0x18000b04b  lea     r9, [rbp+pvarg]
0x18000b04f  mov     qword ptr [rbp+pvarg+8], rax
0x18000b053  lea     rdx, aValuename; "ValueName"
0x18000b05a  xor     r8d, r8d
0x18000b05d  mov     [rsp+58h+var_38], 0
0x18000b065  mov     rax, [rcx]
0x18000b068  mov     rax, [rax+28h]
0x18000b06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b071  lea     rcx, [rbp+pvarg]; pvarg
0x18000b075  call    cs:__imp_VariantClear
0x18000b07b  mov     rax, [rbp+arg_0]
0x18000b07f  mov     [rdi], rax
0x18000b082  xor     eax, eax
0x18000b084  add     rsp, 58h
0x18000b088  pop     rdi
0x18000b089  pop     rsi
0x18000b08a  pop     rbx
0x18000b08b  pop     rbp
0x18000b08c  retn
```
