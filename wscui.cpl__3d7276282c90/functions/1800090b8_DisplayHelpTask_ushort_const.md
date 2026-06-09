# DisplayHelpTask(ushort const *)

- ea: `0x1800090b8`
- end: `0x180009173`
- name: `?DisplayHelpTask@@YA_NPEBG@Z`
- size: `187`
- prototype: `bool __fastcall(OLECHAR *psz)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009d08`

## callees

- `0x1800044f8`
- `0x1800090b8`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009155`
- `OLEAUT32!__imp_SysAllocString` at `0x180009155`
- `OLEAUT32!__imp_SysFreeString` at `0x180009132`
- `OLEAUT32!__imp_SysFreeString` at `0x180009132`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800090f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800090f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall DisplayHelpTask(OLECHAR *psz)
{
  char v2; // si
  int v3; // edi
  LPVOID v5; // [rsp+48h] [rbp+10h] BYREF
  OLECHAR *v6; // [rsp+50h] [rbp+18h]

  v5 = 0;
  v2 = 1;
  if ( CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &v5) < 0 )
    return 0;
  if ( psz )
  {
    psz = SysAllocString(psz);
    v6 = psz;
    if ( !psz )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v6 = 0;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v5 + 24LL))(v5, psz);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  SysFreeString(psz);
  if ( v3 < 0 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x1800090b8  mov     r11, rsp
0x1800090bb  mov     [r11+8], rbx
0x1800090bf  mov     [r11+20h], rsi
0x1800090c3  push    rdi
0x1800090c4  sub     rsp, 30h
0x1800090c8  mov     rbx, rcx
0x1800090cb  mov     qword ptr [r11+10h], 0
0x1800090d3  lea     rax, [r11+10h]
0x1800090d7  mov     [r11-18h], rax
0x1800090db  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x1800090e2  mov     esi, 1
0x1800090e7  mov     r8d, esi; dwClsContext
0x1800090ea  xor     edx, edx; pUnkOuter
0x1800090ec  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x1800090f3  call    cs:__imp_CoCreateInstance
0x1800090f9  test    eax, eax
0x1800090fb  js      short loc_18000913C
0x1800090fd  test    rbx, rbx
0x180009100  jnz     short loc_180009152
0x180009102  mov     [rsp+38h+arg_10], rbx
0x180009107  mov     rcx, [rsp+38h+arg_8]
0x18000910c  mov     rax, [rcx]
0x18000910f  mov     rdx, rbx
0x180009112  mov     rax, [rax+18h]
0x180009116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000911b  mov     edi, eax
0x18000911d  mov     rcx, [rsp+38h+arg_8]
0x180009122  mov     rdx, [rcx]
0x180009125  mov     rax, [rdx+10h]
0x180009129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000912e  nop
0x18000912f  mov     rcx, rbx; bstrString
0x180009132  call    cs:__imp_SysFreeString
0x180009138  test    edi, edi
0x18000913a  jns     short loc_18000913F
0x18000913c  xor     sil, sil
0x18000913f  mov     al, sil
0x180009142  mov     rbx, [rsp+38h+arg_0]
0x180009147  mov     rsi, [rsp+38h+arg_18]
0x18000914c  add     rsp, 30h
0x180009150  pop     rdi
0x180009151  retn
0x180009152  mov     rcx, rbx; psz
0x180009155  call    cs:__imp_SysAllocString
0x18000915b  mov     rbx, rax
0x18000915e  mov     [rsp+38h+arg_10], rax
0x180009163  test    rax, rax
0x180009166  jnz     short loc_180009107
0x180009168  mov     ecx, 8007000Eh; int
0x18000916d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
