# IECreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x180002240`
- end: `0x1800022e5`
- name: `?IECreateInstance@@YAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z`
- size: `165`
- prototype: `__int64 __usercall@<rax>(const struct _GUID *@<rcx>, struct IUnknown *@<rdx>, unsigned int@<r8d>, const struct _GUID *@<r9>, void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010084`
- `0x180010cb0`
- `0x180017084`
- `0x1800188b0`
- `0x180019170`

## callees

- `0x180002240`
- `0x180002610`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800022de`

## pseudocode

```c
HRESULT __fastcall IECreateInstance(
        const struct _GUID *a1,
        struct IUnknown *a2,
        DWORD a3,
        const struct _GUID *a4,
        void **a5)
{
  LPVOID *v5; // rbx
  void *v9; // rdi
  int v10; // ebx
  void *v12; // [rsp+68h] [rbp+10h] BYREF

  v5 = a5;
  v12 = 0;
  *a5 = 0;
  if ( (a3 & 1) == 0
    || (int)ECFGetClassObject(
              (const struct EASYCLASSFACTORY *)a1,
              (int)a2,
              a1,
              &GUID_00000001_0000_0000_c000_000000000046,
              &v12) < 0 )
  {
    return CoCreateInstance(a1, 0, a3, a4, v5);
  }
  v9 = v12;
  v10 = (*(__int64 (__fastcall **)(void *, _QWORD, const struct _GUID *, LPVOID *))(*(_QWORD *)v12 + 24LL))(
          v12,
          0,
          a4,
          v5);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
  return v10;
}

```

## disassembly

```asm
0x180002240  mov     [rsp+arg_8], rdx
0x180002245  push    rbx
0x180002246  push    rbp
0x180002247  push    rsi
0x180002248  push    rdi
0x180002249  sub     rsp, 38h
0x18000224d  mov     rbx, [rsp+58h+arg_20]
0x180002255  xor     eax, eax
0x180002257  mov     [rsp+58h+arg_8], rax
0x18000225c  mov     rbp, r9
0x18000225f  mov     esi, r8d
0x180002262  mov     rdi, rcx
0x180002265  mov     [rbx], rax
0x180002268  test    r8b, 1
0x18000226c  jz      short loc_1800022C3
0x18000226e  lea     rax, [rsp+58h+arg_8]
0x180002273  mov     r8, rcx; struct _GUID *
0x180002276  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; struct _GUID *
0x18000227d  mov     [rsp+58h+var_38], rax; void **
0x180002282  call    ?ECFGetClassObject@@YAJPEBUEASYCLASSFACTORY@@HAEBU_GUID@@1PEAPEAX@Z; ECFGetClassObject(EASYCLASSFACTORY const *,int,_GUID const &,_GUID const &,void * *)
0x180002287  test    eax, eax
0x180002289  js      short loc_1800022C3
0x18000228b  mov     rdi, [rsp+58h+arg_8]
0x180002290  mov     r9, rbx
0x180002293  mov     r8, rbp
0x180002296  xor     edx, edx
0x180002298  mov     rcx, rdi
0x18000229b  mov     rax, [rdi]
0x18000229e  mov     rax, [rax+18h]
0x1800022a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a7  mov     rdx, [rdi]
0x1800022aa  mov     ebx, eax
0x1800022ac  mov     rcx, rdi
0x1800022af  mov     rax, [rdx+10h]
0x1800022b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022b8  mov     eax, ebx
0x1800022ba  add     rsp, 38h
0x1800022be  pop     rdi
0x1800022bf  pop     rsi
0x1800022c0  pop     rbp
0x1800022c1  pop     rbx
0x1800022c2  retn
0x1800022c3  mov     r9, rbp
0x1800022c6  mov     [rsp+58h+arg_20], rbx
0x1800022ce  mov     r8d, esi
0x1800022d1  xor     edx, edx
0x1800022d3  mov     rcx, rdi
0x1800022d6  add     rsp, 38h
0x1800022da  pop     rdi
0x1800022db  pop     rsi
0x1800022dc  pop     rbp
0x1800022dd  pop     rbx
0x1800022de  jmp     cs:__imp_CoCreateInstance
```
