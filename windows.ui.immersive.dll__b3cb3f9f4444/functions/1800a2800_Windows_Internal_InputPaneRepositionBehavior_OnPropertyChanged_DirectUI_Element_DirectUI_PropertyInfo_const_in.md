# Windows::Internal::InputPaneRepositionBehavior::OnPropertyChanged(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)

- ea: `0x1800a2800`
- end: `0x1800a29ed`
- name: `?OnPropertyChanged@InputPaneRepositionBehavior@Internal@Windows@@UEAAJPEAVElement@DirectUI@@PEBUPropertyInfo@5@HPEAVValue@5@2@Z`
- size: `493`
- prototype: `int(Windows::Internal::InputPaneRepositionBehavior *__hidden this, struct DirectUI::Element *, const struct DirectUI::PropertyInfo *, int, struct DirectUI::Value *, struct DirectUI::Value *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18003a074`
- `0x18005dbcc`
- `0x180064dd0`
- `0x1800a2800`
- `0x1800ed010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800a285f`
- `USER32!IsRectEmpty` at `0x1800a2871`
- `USER32!IsRectEmpty` at `0x1800a285f`
- `USER32!IsRectEmpty` at `0x1800a2871`
- `USER32!EqualRect` at `0x1800a2848`
- `USER32!EqualRect` at `0x1800a2848`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x1800a2889`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x1800a289c`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x1800a2905`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x1800a2918`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x1800a2889`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x1800a289c`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x1800a2905`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x1800a2918`
- `DUI70!?LocationProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800a281a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::InputPaneRepositionBehavior::OnPropertyChanged(
        const RECT *this,
        struct DirectUI::Element *a2,
        const struct DirectUI::PropertyInfo *a3,
        int a4,
        struct DirectUI::Value *a5,
        struct DirectUI::Value *a6)
{
  int v8; // esi
  BOOL v9; // ebx
  const struct tagPOINT *v10; // rbx
  int v11; // eax
  int v12; // ebx
  const struct tagPOINT *Point; // r14
  const struct tagPOINT *v14; // r13
  unsigned int v15; // ebx
  unsigned int left; // ebx
  int v18; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-14h]
  _QWORD v20[2]; // [rsp+58h] [rbp-10h] BYREF

  v8 = 0;
  if ( DirectUI::PropNotify::IsEqual(a3, a4, DirectUI::Element::LocationProp) )
  {
    v20[0] = 0;
    if ( EqualRect(this + 3, this + 2)
      || (v9 = IsRectEmpty(this + 2), IsRectEmpty(this + 3) == v9)
      || (v10 = DirectUI::Value::GetPoint(a6), DirectUI::Value::GetPoint(a5)->x != v10->x) )
    {
      left = this[4].left;
      if ( left != -1 )
      {
        if ( (int)DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)v20) >= 0 )
          (*(void (__fastcall **)(_QWORD, struct DirectUI::Element *, _QWORD))(*(_QWORD *)v20[0] + 272LL))(
            v20[0],
            a2,
            left);
        this[4].left = -1;
      }
    }
    else
    {
      v11 = this[3].bottom - this[3].top;
      v12 = this[2].bottom - this[2].top;
      v18 = 0;
      if ( v12 <= v11 )
        v12 = v11;
      v8 = DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)v20);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, struct DirectUI::Element *, const RECT *, int *))(*(_QWORD *)v20[0]
                                                                                                + 256LL))(
               v20[0],
               a2,
               this + 4,
               &v18);
        if ( v8 >= 0 )
        {
          Point = DirectUI::Value::GetPoint(a6);
          v14 = DirectUI::Value::GetPoint(a5);
          v19 = this[4].left;
          v8 = DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)v20);
          if ( v8 >= 0 )
            v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct DirectUI::Element *, const struct tagPOINT *, const struct tagPOINT *, const RECT *, _DWORD, int))(*(_QWORD *)v20[0] + 304LL))(
                   v20[0],
                   v19,
                   a2,
                   v14,
                   Point,
                   this + 2,
                   0,
                   v12);
          v15 = this[4].left;
          if ( (int)DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)v20) >= 0 )
            (*(void (__fastcall **)(_QWORD, struct DirectUI::Element *, _QWORD))(*(_QWORD *)v20[0] + 264LL))(
              v20[0],
              a2,
              v15);
        }
      }
    }
    DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)v20);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a2800  push    rbp
0x1800a2802  push    rbx
0x1800a2803  push    rsi
0x1800a2804  push    rdi
0x1800a2805  push    r12
0x1800a2807  push    r13
0x1800a2809  push    r14
0x1800a280b  push    r15
0x1800a280d  mov     rbp, rsp
0x1800a2810  sub     rsp, 68h
0x1800a2814  mov     rax, r8
0x1800a2817  mov     r12, rdx
0x1800a281a  mov     r8, cs:__imp_?LocationProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; const struct DirectUI::PropertyInfo *(*)(void)
0x1800a2821  mov     rdi, rcx
0x1800a2824  mov     rcx, rax; struct DirectUI::PropertyInfo *
0x1800a2827  mov     edx, r9d; int
0x1800a282a  xor     esi, esi
0x1800a282c  call    ?IsEqual@PropNotify@DirectUI@@SA_NPEBUPropertyInfo@2@HP6APEBU32@XZ@Z; DirectUI::PropNotify::IsEqual(DirectUI::PropertyInfo const *,int,DirectUI::PropertyInfo const * (*)(void))
0x1800a2831  test    al, al
0x1800a2833  jz      loc_1800A29D9
0x1800a2839  lea     r15, [rdi+20h]
0x1800a283d  mov     [rbp+var_10], rsi
0x1800a2841  mov     rdx, r15; lprc2
0x1800a2844  lea     rcx, [rdi+30h]; lprc1
0x1800a2848  call    cs:__imp_EqualRect
0x1800a284f  nop     dword ptr [rax+rax+00h]
0x1800a2854  test    eax, eax
0x1800a2856  jnz     loc_1800A299B
0x1800a285c  mov     rcx, r15; lprc
0x1800a285f  call    cs:__imp_IsRectEmpty
0x1800a2866  nop     dword ptr [rax+rax+00h]
0x1800a286b  lea     rcx, [rdi+30h]; lprc
0x1800a286f  mov     ebx, eax
0x1800a2871  call    cs:__imp_IsRectEmpty
0x1800a2878  nop     dword ptr [rax+rax+00h]
0x1800a287d  cmp     eax, ebx
0x1800a287f  jz      loc_1800A299B
0x1800a2885  mov     rcx, [rbp+arg_28]
0x1800a2889  call    cs:__imp_?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ; DirectUI::Value::GetPoint(void)
0x1800a2890  nop     dword ptr [rax+rax+00h]
0x1800a2895  mov     rcx, [rbp+arg_20]
0x1800a2899  mov     rbx, rax
0x1800a289c  call    cs:__imp_?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ; DirectUI::Value::GetPoint(void)
0x1800a28a3  nop     dword ptr [rax+rax+00h]
0x1800a28a8  mov     ecx, [rax]
0x1800a28aa  cmp     ecx, [rbx]
0x1800a28ac  jnz     loc_1800A299B
0x1800a28b2  mov     eax, [rdi+3Ch]
0x1800a28b5  lea     rcx, [rbp+var_10]; this
0x1800a28b9  sub     eax, [rdi+34h]
0x1800a28bc  mov     ebx, [rdi+2Ch]
0x1800a28bf  sub     ebx, [rdi+24h]
0x1800a28c2  cmp     ebx, eax
0x1800a28c4  mov     [rbp+var_18], esi
0x1800a28c7  cmovle  ebx, eax
0x1800a28ca  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x1800a28cf  mov     esi, eax
0x1800a28d1  test    eax, eax
0x1800a28d3  js      loc_1800A29D0
0x1800a28d9  mov     rcx, [rbp+var_10]
0x1800a28dd  lea     r9, [rbp+var_18]
0x1800a28e1  lea     r8, [rdi+40h]
0x1800a28e5  mov     rdx, r12
0x1800a28e8  mov     rax, [rcx]
0x1800a28eb  mov     rax, [rax+100h]
0x1800a28f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a28f7  mov     esi, eax
0x1800a28f9  test    eax, eax
0x1800a28fb  js      loc_1800A29D0
0x1800a2901  mov     rcx, [rbp+arg_28]
0x1800a2905  call    cs:__imp_?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ; DirectUI::Value::GetPoint(void)
0x1800a290c  nop     dword ptr [rax+rax+00h]
0x1800a2911  mov     rcx, [rbp+arg_20]
0x1800a2915  mov     r14, rax
0x1800a2918  call    cs:__imp_?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ; DirectUI::Value::GetPoint(void)
0x1800a291f  nop     dword ptr [rax+rax+00h]
0x1800a2924  mov     r13, rax
0x1800a2927  lea     rcx, [rbp+var_10]; this
0x1800a292b  mov     eax, [rdi+40h]
0x1800a292e  mov     [rbp+var_14], eax
0x1800a2931  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x1800a2936  mov     esi, eax
0x1800a2938  test    eax, eax
0x1800a293a  js      short loc_1800A2970
0x1800a293c  mov     rcx, [rbp+var_10]
0x1800a2940  mov     r9, r13
0x1800a2943  mov     edx, [rbp+var_14]
0x1800a2946  mov     [rsp+68h+var_30], ebx
0x1800a294a  mov     [rsp+68h+var_38], 0
0x1800a2952  mov     r8, [rcx]
0x1800a2955  mov     [rsp+68h+var_40], r15
0x1800a295a  mov     [rsp+68h+var_48], r14
0x1800a295f  mov     rax, [r8+130h]
0x1800a2966  mov     r8, r12
0x1800a2969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a296e  mov     esi, eax
0x1800a2970  mov     ebx, [rdi+40h]
0x1800a2973  lea     rcx, [rbp+var_10]; this
0x1800a2977  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x1800a297c  test    eax, eax
0x1800a297e  js      short loc_1800A29D0
0x1800a2980  mov     rcx, [rbp+var_10]
0x1800a2984  mov     r8d, ebx
0x1800a2987  mov     rdx, r12
0x1800a298a  mov     rax, [rcx]
0x1800a298d  mov     rax, [rax+108h]
0x1800a2994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2999  jmp     short loc_1800A29D0
0x1800a299b  mov     ebx, [rdi+40h]
0x1800a299e  cmp     ebx, 0FFFFFFFFh
0x1800a29a1  jz      short loc_1800A29D0
0x1800a29a3  lea     rcx, [rbp+var_10]; this
0x1800a29a7  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x1800a29ac  test    eax, eax
0x1800a29ae  js      short loc_1800A29C9
0x1800a29b0  mov     rcx, [rbp+var_10]
0x1800a29b4  mov     r8d, ebx
0x1800a29b7  mov     rdx, r12
0x1800a29ba  mov     rax, [rcx]
0x1800a29bd  mov     rax, [rax+110h]
0x1800a29c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a29c9  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x1800a29d0  lea     rcx, [rbp+var_10]; this
0x1800a29d4  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x1800a29d9  mov     eax, esi
0x1800a29db  add     rsp, 68h
0x1800a29df  pop     r15
0x1800a29e1  pop     r14
0x1800a29e3  pop     r13
0x1800a29e5  pop     r12
0x1800a29e7  pop     rdi
0x1800a29e8  pop     rsi
0x1800a29e9  pop     rbx
0x1800a29ea  pop     rbp
0x1800a29eb  retn
```
