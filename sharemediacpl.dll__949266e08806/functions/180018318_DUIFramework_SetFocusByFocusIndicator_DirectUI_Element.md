# DUIFramework_SetFocusByFocusIndicator(DirectUI::Element *)

- ea: `0x180018318`
- end: `0x1800183fa`
- name: `?DUIFramework_SetFocusByFocusIndicator@@YAJPEAVElement@DirectUI@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180017ed0`

## callees

- `0x180018318`
- `0x18001e010`

## import_xrefs

- `DUI70!StrToID` at `0x180018336`
- `DUI70!StrToID` at `0x180018336`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018342`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001837b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018342`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001837b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180018362`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180018362`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001836f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001836f`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x1800183a3`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x1800183a3`

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
    Value = DirectUI::Element::GetValue(Descendent, (const struct DirectUI::PropertyInfo *)&off_18002A198, 2, 0);
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
0x180018318  mov     [rsp+arg_0], rbx
0x18001831d  mov     [rsp+arg_8], rsi
0x180018322  push    rdi
0x180018323  sub     rsp, 50h
0x180018327  mov     rdi, rcx
0x18001832a  mov     esi, 80004005h
0x18001832f  lea     rcx, aFocusindicator; "FocusIndicator"
0x180018336  call    cs:__imp_StrToID
0x18001833c  movzx   edx, ax
0x18001833f  mov     rcx, rdi
0x180018342  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018348  test    rax, rax
0x18001834b  jz      loc_1800183E8
0x180018351  xor     r9d, r9d
0x180018354  lea     rdx, off_18002A198; "firsttabtarget"
0x18001835b  mov     rcx, rax
0x18001835e  lea     r8d, [r9+2]
0x180018362  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180018368  mov     rcx, rax
0x18001836b  movzx   ebx, word ptr [rax+8]
0x18001836f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018375  movzx   edx, bx
0x180018378  mov     rcx, rdi
0x18001837b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018381  mov     rbx, rax
0x180018384  test    rax, rax
0x180018387  jz      short loc_1800183E8
0x180018389  xorps   xmm0, xmm0
0x18001838c  lea     rcx, [rsp+58h+var_28]
0x180018391  xor     eax, eax
0x180018393  xor     r8d, r8d
0x180018396  mov     rdx, rbx
0x180018399  mov     [rsp+58h+var_18], rax
0x18001839e  movups  [rsp+58h+var_28], xmm0
0x1800183a3  call    cs:__imp_?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z; DirectUI::NavReference::Init(DirectUI::Element *,tagRECT *)
0x1800183a9  mov     rax, [rbx]
0x1800183ac  lea     r9, [rsp+58h+var_28]
0x1800183b1  mov     r8d, 3
0x1800183b7  xor     edx, edx
0x1800183b9  mov     rcx, rbx
0x1800183bc  mov     [rsp+58h+var_38], r8d
0x1800183c1  mov     rax, [rax+98h]
0x1800183c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183cd  test    rax, rax
0x1800183d0  cmovnz  rbx, rax
0x1800183d4  mov     rcx, rbx
0x1800183d7  mov     rax, [rbx]
0x1800183da  mov     rax, [rax+0A8h]
0x1800183e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183e6  xor     esi, esi
0x1800183e8  mov     rbx, [rsp+58h+arg_0]
0x1800183ed  mov     eax, esi
0x1800183ef  mov     rsi, [rsp+58h+arg_8]
0x1800183f4  add     rsp, 50h
0x1800183f8  pop     rdi
0x1800183f9  retn
```
