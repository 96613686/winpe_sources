# SpCreatePhoneConverter(ushort,ushort const *,ushort const *,ISpPhoneConverter * *)

- ea: `0x1800137e0`
- end: `0x18001393f`
- name: `?SpCreatePhoneConverter@@YAJGPEBG0PEAPEAUISpPhoneConverter@@@Z`
- size: `351`
- prototype: `int(unsigned __int16, const unsigned __int16 *, const unsigned __int16 *, struct ISpPhoneConverter **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cbd8`
- `0x1800ceeb0`

## callees

- `0x1800034b0`
- `0x180004b30`
- `0x1800061d0`
- `0x18000660c`
- `0x1800137e0`
- `0x180013e58`
- `0x18001406c`
- `0x1800141c0`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800138a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800138a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpCreatePhoneConverter(
        unsigned __int16 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        LPVOID *a4)
{
  int v5; // ecx
  int v6; // r8d
  int Instance; // ebx
  _QWORD v9[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v10[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v11[264]; // [rsp+250h] [rbp+150h] BYREF

  if ( !a1
    || (v9[0] = 0,
        SpHexFromUlong(v11, a1),
        StringCchCopyW(v10, 0x104u, L"Language="),
        StringCchCatW(v10, 0x104u, v11),
        CSpDynamicString::AppendHR((CSpDynamicString *)v9, v10),
        Instance = SpCreateBestObject<ISpPhoneConverter>(v5, v9[0], v6, (_DWORD)a4),
        CSpDynamicString::_free((CSpDynamicString *)v9),
        Instance == -2147200966) )
  {
    Instance = CoCreateInstance(&CLSID_SpPhoneConverter, 0, 0x17u, &IID_ISpPhoneConverter, a4);
    if ( Instance >= 0 )
    {
      v9[0] = 0;
      if ( (**(int (__fastcall ***)(LPVOID, GUID *, _QWORD *))*a4)(*a4, &IID_ISpPhoneticAlphabetSelection, v9) < 0 )
      {
        Instance = -2147200966;
LABEL_8:
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*a4 + 16LL))(*a4);
        *a4 = 0;
        return (unsigned int)Instance;
      }
      Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v9[0] + 32LL))(v9[0], 1);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[0] + 16LL))(v9[0]);
      if ( Instance < 0 )
        goto LABEL_8;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800137e0  mov     [rsp-8+arg_8], rbx
0x1800137e5  push    rbp
0x1800137e6  push    rsi
0x1800137e7  push    rdi
0x1800137e8  lea     rbp, [rsp-370h]
0x1800137f0  sub     rsp, 470h
0x1800137f7  mov     rax, cs:__security_cookie
0x1800137fe  xor     rax, rsp
0x180013801  mov     [rbp+380h+var_20], rax
0x180013808  mov     rdi, r9
0x18001380b  xor     esi, esi
0x18001380d  test    cx, cx
0x180013810  jz      short loc_18001388D
0x180013812  mov     [rsp+480h+var_450], rsi
0x180013817  movzx   edx, cx; unsigned int
0x18001381a  lea     rcx, [rbp+380h+var_230]; unsigned __int16 *
0x180013821  call    ?SpHexFromUlong@@YAXPEAGK@Z; SpHexFromUlong(ushort *,ulong)
0x180013826  lea     r8, aLanguage_0; "Language="
0x18001382d  mov     ebx, 104h
0x180013832  mov     edx, ebx; unsigned __int64
0x180013834  lea     rcx, [rsp+480h+var_440]; unsigned __int16 *
0x180013839  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001383e  lea     r8, [rbp+380h+var_230]; unsigned __int16 *
0x180013845  mov     edx, ebx; unsigned __int64
0x180013847  lea     rcx, [rsp+480h+var_440]; unsigned __int16 *
0x18001384c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013851  lea     rdx, [rsp+480h+var_440]; unsigned __int16 *
0x180013856  lea     rcx, [rsp+480h+var_450]; this
0x18001385b  call    ?AppendHR@CSpDynamicString@@QEAAJPEBG@Z; CSpDynamicString::AppendHR(ushort const *)
0x180013860  mov     [rsp+480h+var_458], 17h
0x180013868  mov     r9, rdi
0x18001386b  mov     rdx, [rsp+480h+var_450]
0x180013870  call    ??$SpCreateBestObject@UISpPhoneConverter@@@@YAJPEBG00PEAPEAUISpPhoneConverter@@PEAUIUnknown@@K@Z; SpCreateBestObject<ISpPhoneConverter>(ushort const *,ushort const *,ushort const *,ISpPhoneConverter * *,IUnknown *,ulong)
0x180013875  mov     ebx, eax
0x180013877  lea     rcx, [rsp+480h+var_450]; this
0x18001387c  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180013881  cmp     ebx, 8004503Ah
0x180013887  jnz     loc_18001391B
0x18001388d  mov     [rsp+480h+ppv], rdi; ppv
0x180013892  lea     r9, IID_ISpPhoneConverter; riid
0x180013899  xor     edx, edx; pUnkOuter
0x18001389b  lea     r8d, [rdx+17h]; dwClsContext
0x18001389f  lea     rcx, CLSID_SpPhoneConverter; rclsid
0x1800138a6  call    cs:__imp_CoCreateInstance
0x1800138ac  mov     ebx, eax
0x1800138ae  test    eax, eax
0x1800138b0  js      short loc_18001391B
0x1800138b2  mov     [rsp+480h+var_450], rsi
0x1800138b7  mov     rcx, [rdi]
0x1800138ba  mov     rax, [rcx]
0x1800138bd  lea     r8, [rsp+480h+var_450]
0x1800138c2  lea     rdx, IID_ISpPhoneticAlphabetSelection
0x1800138c9  mov     rax, [rax]
0x1800138cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d1  test    eax, eax
0x1800138d3  js      short loc_180013904
0x1800138d5  mov     rcx, [rsp+480h+var_450]
0x1800138da  mov     rax, [rcx]
0x1800138dd  mov     edx, 1
0x1800138e2  mov     rax, [rax+20h]
0x1800138e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138eb  mov     ebx, eax
0x1800138ed  mov     rcx, [rsp+480h+var_450]
0x1800138f2  mov     rax, [rcx]
0x1800138f5  mov     rax, [rax+10h]
0x1800138f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138fe  test    ebx, ebx
0x180013900  jns     short loc_18001391B
0x180013902  jmp     short loc_180013909
0x180013904  mov     ebx, 8004503Ah
0x180013909  mov     rcx, [rdi]
0x18001390c  mov     rax, [rcx]
0x18001390f  mov     rax, [rax+10h]
0x180013913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013918  mov     [rdi], rsi
0x18001391b  mov     eax, ebx
0x18001391d  mov     rcx, [rbp+380h+var_20]
0x180013924  xor     rcx, rsp; StackCookie
0x180013927  call    __security_check_cookie
0x18001392c  mov     rbx, [rsp+480h+arg_8]
0x180013934  add     rsp, 470h
0x18001393b  pop     rdi
0x18001393c  pop     rsi
0x18001393d  pop     rbp
0x18001393e  retn
```
