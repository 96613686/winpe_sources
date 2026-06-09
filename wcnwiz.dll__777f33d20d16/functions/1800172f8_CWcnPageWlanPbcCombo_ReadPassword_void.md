# CWcnPageWlanPbcCombo::_ReadPassword(void)

- ea: `0x1800172f8`
- end: `0x1800173e2`
- name: `?_ReadPassword@CWcnPageWlanPbcCombo@@AEAA_NXZ`
- size: `234`
- prototype: `bool __fastcall(CWcnPageWlanPbcCombo *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800165cc`
- `0x180016f60`
- `0x1800173e8`
- `0x180017840`

## callees

- `0x18000e1dc`
- `0x1800132b8`
- `0x1800132e0`
- `0x1800172f8`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `DUI70!?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z` at `0x18001734e`
- `DUI70!?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z` at `0x18001734e`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180017360`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180017360`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CWcnPageWlanPbcCombo::_ReadPassword(CWcnPageWlanPbcCombo *this)
{
  __int64 v2; // rdx
  unsigned __int16 *v3; // rbx
  char *v4; // rax
  char v5; // al
  DirectUI::Element *v6; // rcx
  const unsigned __int16 *ContentString; // rax
  unsigned int Indent; // eax
  __int64 v9; // r10
  char v10; // r11
  struct DirectUI::Value *v12; // [rsp+40h] [rbp+8h] BYREF

  v2 = 130;
  v3 = (unsigned __int16 *)((char *)this + 376);
  v4 = (char *)this + 376;
  do
  {
    *v4++ = 0;
    --v2;
  }
  while ( v2 );
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 71) + 16LL))(*((_QWORD *)this + 71));
  v6 = (DirectUI::Element *)*((_QWORD *)this + 71);
  if ( v5 )
  {
    DirectUI::Element::GetEncodedContentString(v6, v3, 0x41u);
  }
  else
  {
    v12 = 0;
    ContentString = DirectUI::Element::GetContentString(v6, &v12);
    if ( ContentString
      && (int)StringCchCopyW(v3, 0x41u, ContentString) < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      Indent = (unsigned int)GetIndent(0);
      WPP_SF_sd(*(_QWORD *)(v9 + 16), 23, (unsigned int)WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, Indent, v10);
    }
    CValuePtr::Release((CValuePtr *)&v12);
  }
  return *v3 != 0;
}

```

## disassembly

```asm
0x1800172f8  mov     [rsp+arg_8], rbx
0x1800172fd  mov     [rsp+arg_10], rsi
0x180017302  push    rdi
0x180017303  sub     rsp, 30h
0x180017307  mov     rdi, rcx
0x18001730a  mov     edx, 82h
0x18001730f  lea     rbx, [rcx+178h]
0x180017316  mov     rax, rbx
0x180017319  xor     esi, esi
0x18001731b  mov     [rax], sil
0x18001731e  inc     rax
0x180017321  sub     rdx, 1
0x180017325  jnz     short loc_18001731B
0x180017327  mov     rcx, [rcx+238h]
0x18001732e  mov     rax, [rcx]
0x180017331  mov     rax, [rax+10h]
0x180017335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001733a  mov     rcx, [rdi+238h]
0x180017341  test    al, al
0x180017343  jz      short loc_180017356
0x180017345  mov     r8d, 41h ; 'A'
0x18001734b  mov     rdx, rbx
0x18001734e  call    cs:__imp_?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z; DirectUI::Element::GetEncodedContentString(ushort *,unsigned __int64)
0x180017354  jmp     short loc_1800173CC
0x180017356  mov     [rsp+38h+arg_0], rsi
0x18001735b  lea     rdx, [rsp+38h+arg_0]
0x180017360  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x180017366  test    rax, rax
0x180017369  jz      short loc_1800173C1
0x18001736b  mov     r8, rax; unsigned __int16 *
0x18001736e  mov     edx, 41h ; 'A'; unsigned __int64
0x180017373  mov     rcx, rbx; unsigned __int16 *
0x180017376  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001737b  mov     r11d, eax
0x18001737e  test    eax, eax
0x180017380  jns     short loc_1800173C1
0x180017382  lea     rax, WPP_GLOBAL_Control
0x180017389  mov     r10, cs:WPP_GLOBAL_Control
0x180017390  cmp     r10, rax
0x180017393  jz      short loc_1800173C1
0x180017395  cmp     byte ptr [r10+19h], 2
0x18001739a  jb      short loc_1800173C1
0x18001739c  xor     ecx, ecx; int
0x18001739e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800173a3  mov     edx, 17h
0x1800173a8  mov     [rsp+38h+var_18], r11d
0x1800173ad  mov     r9, rax
0x1800173b0  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x1800173b7  mov     rcx, [r10+10h]
0x1800173bb  call    WPP_SF_sd
0x1800173c0  nop
0x1800173c1  lea     rcx, [rsp+38h+arg_0]; this
0x1800173c6  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800173cb  nop
0x1800173cc  cmp     [rbx], si
0x1800173cf  setnz   al
0x1800173d2  mov     rbx, [rsp+38h+arg_8]
0x1800173d7  mov     rsi, [rsp+38h+arg_10]
0x1800173dc  add     rsp, 30h
0x1800173e0  pop     rdi
0x1800173e1  retn
```
