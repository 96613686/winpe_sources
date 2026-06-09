# DUIFramework_SetFocusByFocusIndicator(DirectUI::Element *)

- ea: `0x180052e2c`
- end: `0x180052f33`
- name: `?DUIFramework_SetFocusByFocusIndicator@@YAJPEAVElement@DirectUI@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180054450`

## callees

- `0x180052e2c`
- `0x180057010`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180052e5c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180052ea7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180052e5c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180052ea7`
- `DUI70!StrToID` at `0x180052e4a`
- `DUI70!StrToID` at `0x180052e4a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180052e95`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180052e95`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x180052ed5`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x180052ed5`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180052e82`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180052e82`

## pseudocode

```c
__int64 __fastcall DUIFramework_SetFocusByFocusIndicator(struct DirectUI::Element *a1)
{
  unsigned int v2; // esi
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  struct DirectUI::Value *Value; // rax
  unsigned __int16 v6; // bx
  struct DirectUI::Element *v7; // rbx
  __int64 v8; // rax
  __int128 v10; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+40h] [rbp-18h]

  v2 = -2147467259;
  v3 = StrToID(L"FocusIndicator");
  Descendent = DirectUI::Element::FindDescendent(a1, v3);
  if ( Descendent )
  {
    Value = DirectUI::Element::GetValue(Descendent, (const struct DirectUI::PropertyInfo *)&off_18006F6B8, 2, 0);
    v6 = *((_WORD *)Value + 4);
    DirectUI::Value::Release(Value);
    v7 = DirectUI::Element::FindDescendent(a1, v6);
    if ( v7 )
    {
      v11 = 0;
      v10 = 0;
      DirectUI::NavReference::Init((DirectUI::NavReference *)&v10, v7, 0);
      v8 = (*(__int64 (__fastcall **)(struct DirectUI::Element *, _QWORD, __int64, __int128 *, int))(*(_QWORD *)v7 + 152LL))(
             v7,
             0,
             3,
             &v10,
             3);
      if ( v8 )
        v7 = (struct DirectUI::Element *)v8;
      (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v7 + 168LL))(v7);
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180052e2c  mov     [rsp+arg_0], rbx
0x180052e31  mov     [rsp+arg_8], rsi
0x180052e36  push    rdi
0x180052e37  sub     rsp, 50h
0x180052e3b  mov     rdi, rcx
0x180052e3e  mov     esi, 80004005h
0x180052e43  lea     rcx, aFocusindicator; "FocusIndicator"
0x180052e4a  call    cs:__imp_StrToID
0x180052e51  nop     dword ptr [rax+rax+00h]
0x180052e56  movzx   edx, ax
0x180052e59  mov     rcx, rdi
0x180052e5c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180052e63  nop     dword ptr [rax+rax+00h]
0x180052e68  test    rax, rax
0x180052e6b  jz      loc_180052F20
0x180052e71  xor     r9d, r9d
0x180052e74  lea     rdx, off_18006F6B8; "firsttabtarget"
0x180052e7b  mov     rcx, rax
0x180052e7e  lea     r8d, [r9+2]
0x180052e82  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180052e89  nop     dword ptr [rax+rax+00h]
0x180052e8e  mov     rcx, rax
0x180052e91  movzx   ebx, word ptr [rax+8]
0x180052e95  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180052e9c  nop     dword ptr [rax+rax+00h]
0x180052ea1  movzx   edx, bx
0x180052ea4  mov     rcx, rdi
0x180052ea7  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180052eae  nop     dword ptr [rax+rax+00h]
0x180052eb3  mov     rbx, rax
0x180052eb6  test    rax, rax
0x180052eb9  jz      short loc_180052F20
0x180052ebb  xorps   xmm0, xmm0
0x180052ebe  lea     rcx, [rsp+58h+var_28]
0x180052ec3  xor     eax, eax
0x180052ec5  xor     r8d, r8d
0x180052ec8  mov     rdx, rbx
0x180052ecb  mov     [rsp+58h+var_18], rax
0x180052ed0  movups  [rsp+58h+var_28], xmm0
0x180052ed5  call    cs:__imp_?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z; DirectUI::NavReference::Init(DirectUI::Element *,tagRECT *)
0x180052edc  nop     dword ptr [rax+rax+00h]
0x180052ee1  mov     rax, [rbx]
0x180052ee4  lea     r9, [rsp+58h+var_28]
0x180052ee9  mov     r8d, 3
0x180052eef  xor     edx, edx
0x180052ef1  mov     rcx, rbx
0x180052ef4  mov     [rsp+58h+var_38], r8d
0x180052ef9  mov     rax, [rax+98h]
0x180052f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f05  test    rax, rax
0x180052f08  cmovnz  rbx, rax
0x180052f0c  mov     rcx, rbx
0x180052f0f  mov     rax, [rbx]
0x180052f12  mov     rax, [rax+0A8h]
0x180052f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f1e  xor     esi, esi
0x180052f20  mov     rbx, [rsp+58h+arg_0]
0x180052f25  mov     eax, esi
0x180052f27  mov     rsi, [rsp+58h+arg_8]
0x180052f2c  add     rsp, 50h
0x180052f30  pop     rdi
0x180052f31  retn
```
