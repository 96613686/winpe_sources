# CHost::initDebugger(void)

- ea: `0x140008764`
- end: `0x14000884e`
- name: `?initDebugger@CHost@@IEAAJXZ`
- size: `234`
- prototype: `__int64 __fastcall(CHost *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000757c`

## callees

- `0x140008764`
- `0x1400146ac`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000881f`
- `OLEAUT32!__imp_SysFreeString` at `0x14000881f`
- `ole32!CoCreateInstance` at `0x1400087a4`
- `ole32!CoCreateInstance` at `0x1400087a4`

## pseudocode

```c
HRESULT __fastcall CHost::initDebugger(CHost *this)
{
  bool v1; // zf
  _QWORD *v3; // rdi
  HRESULT result; // eax
  _QWORD *v5; // r14
  OLECHAR *v6; // rdi
  int v7; // esi
  BSTR bstrString; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_BYTE *)this + 71) == 0;
  bstrString = 0;
  if ( v1 )
    return 0;
  v3 = (_QWORD *)((char *)this + 656);
  result = CoCreateInstance(&CLSID_ProcessDebugManager, 0, 0x17u, &IID_IProcessDebugManager64, (LPVOID *)this + 82);
  if ( result >= 0 )
  {
    v5 = (_QWORD *)((char *)this + 664);
    result = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v3 + 32LL))(*v3, (char *)this + 664);
    if ( result < 0 )
      return result;
    LoadStr(&bstrString, Global::g_lResourceBase + (*((_BYTE *)this + 71) != 0 ? 1 : 3));
    v6 = bstrString;
    if ( !bstrString )
      return -2147467259;
    v7 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(*(_QWORD *)*v5 + 112LL))(*v5, bstrString);
    SysFreeString(v6);
    if ( v7 < 0 )
      return v7;
    if ( *((_BYTE *)this + 72) )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
    return 0;
  }
  if ( result == -2147221164 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140008764  push    rbx
0x140008766  push    rsi
0x140008767  push    rdi
0x140008768  push    r14
0x14000876a  sub     rsp, 38h
0x14000876e  cmp     byte ptr [rcx+47h], 0
0x140008772  mov     rbx, rcx
0x140008775  mov     [rsp+58h+bstrString], 0
0x14000877e  jz      loc_140008842
0x140008784  lea     rdi, [rcx+290h]
0x14000878b  xor     edx, edx; pUnkOuter
0x14000878d  lea     r9, IID_IProcessDebugManager64; riid
0x140008794  mov     [rsp+58h+ppv], rdi; ppv
0x140008799  lea     rcx, CLSID_ProcessDebugManager; rclsid
0x1400087a0  lea     r8d, [rdx+17h]; dwClsContext
0x1400087a4  call    cs:__imp_CoCreateInstance
0x1400087aa  test    eax, eax
0x1400087ac  jns     short loc_1400087BD
0x1400087ae  xor     ecx, ecx
0x1400087b0  cmp     eax, 80040154h
0x1400087b5  cmovz   eax, ecx
0x1400087b8  jmp     loc_140008844
0x1400087bd  mov     rcx, [rdi]
0x1400087c0  lea     r14, [rbx+298h]
0x1400087c7  mov     rdx, r14
0x1400087ca  mov     rax, [rcx]
0x1400087cd  mov     rax, [rax+20h]
0x1400087d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087d6  test    eax, eax
0x1400087d8  js      short loc_140008844
0x1400087da  mov     al, [rbx+47h]
0x1400087dd  lea     rcx, [rsp+58h+bstrString]; unsigned __int16 **
0x1400087e2  neg     al
0x1400087e4  sbb     edx, edx
0x1400087e6  and     edx, 0FFFFFFFEh
0x1400087e9  add     edx, 3
0x1400087ec  add     edx, cs:?g_lResourceBase@Global@@2JA; unsigned int
0x1400087f2  call    ?LoadStr@@YAHPEAPEAGI@Z; LoadStr(ushort * *,uint)
0x1400087f7  mov     rdi, [rsp+58h+bstrString]
0x1400087fc  test    rdi, rdi
0x1400087ff  jnz     short loc_140008808
0x140008801  mov     eax, 80004005h
0x140008806  jmp     short loc_140008844
0x140008808  mov     rcx, [r14]
0x14000880b  mov     rdx, rdi
0x14000880e  mov     rax, [rcx]
0x140008811  mov     rax, [rax+70h]
0x140008815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000881a  mov     rcx, rdi; bstrString
0x14000881d  mov     esi, eax
0x14000881f  call    cs:__imp_SysFreeString
0x140008825  test    esi, esi
0x140008827  jns     short loc_14000882D
0x140008829  mov     eax, esi
0x14000882b  jmp     short loc_140008844
0x14000882d  cmp     byte ptr [rbx+48h], 0
0x140008831  jz      short loc_140008842
0x140008833  mov     rcx, [r14]
0x140008836  mov     rax, [rcx]
0x140008839  mov     rax, [rax+20h]
0x14000883d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008842  xor     eax, eax
0x140008844  add     rsp, 38h
0x140008848  pop     r14
0x14000884a  pop     rdi
0x14000884b  pop     rsi
0x14000884c  pop     rbx
0x14000884d  retn
```
