# CAccountGroupPage::OnWizNext(void)

- ea: `0x18000f110`
- end: `0x18000f30e`
- name: `?OnWizNext@CAccountGroupPage@@UEAA_JXZ`
- size: `510`
- prototype: `__int64 __fastcall(CAccountGroupPage *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000f110`
- `0x180063a20`
- `0x1800772c0`

## import_xrefs

- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18000f23c`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18000f23c`
- `DUI70!StrToID` at `0x18000f140`
- `DUI70!StrToID` at `0x18000f1b5`
- `DUI70!StrToID` at `0x18000f227`
- `DUI70!StrToID` at `0x18000f140`
- `DUI70!StrToID` at `0x18000f1b5`
- `DUI70!StrToID` at `0x18000f227`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f14c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f1c1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f233`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f14c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f1c1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000f233`

## string_xrefs

- `0x18000f220`: `OtherComboBox`

## pseudocode

```c
__int64 __fastcall CAccountGroupPage::OnWizNext(CAccountGroupPage *this)
{
  DirectUI::Element *v1; // rbx
  __int64 v3; // rsi
  unsigned __int16 v4; // ax
  __int64 v5; // rbx
  _WORD *v6; // r10
  __int64 v7; // r8
  _WORD *v8; // r9
  __int64 v9; // rax
  __int64 v10; // rcx
  DirectUI::Element *v11; // rbx
  unsigned __int16 v12; // ax
  _WORD *v13; // r10
  __int64 v14; // rax
  DirectUI::Element *v15; // rbx
  unsigned __int16 v16; // ax
  DirectUI::Combobox *Descendent; // rax
  int Selection; // eax
  __int64 v19; // rbp
  _WORD *Ptr; // rax
  _WORD *v21; // rax
  _WORD *v22; // rax
  _WORD *v23; // r9
  _WORD *v24; // rcx
  _BYTE v26[528]; // [rsp+20h] [rbp-248h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v3 = -1;
  v4 = StrToID(L"navadminuserR");
  if ( (*((_BYTE *)DirectUI::Element::FindDescendent(v1, v4) + 148) & 0x10) != 0 )
  {
    v5 = 2147483646;
    v6 = (_WORD *)((char *)this + 2204);
    v7 = 257;
    v8 = v26;
    v9 = 2147483646;
    v10 = 257;
    do
    {
      if ( !v9 )
        break;
      if ( !*v6 )
        break;
      *v8++ = *v6++;
      --v9;
      --v10;
    }
    while ( v10 );
  }
  else
  {
    v11 = (DirectUI::Element *)*((_QWORD *)this + 8);
    v12 = StrToID(L"navstandarduserR");
    if ( (*((_BYTE *)DirectUI::Element::FindDescendent(v11, v12) + 148) & 0x10) != 0 )
    {
      v5 = 2147483646;
      v13 = (_WORD *)((char *)this + 1690);
      v7 = 257;
      v8 = v26;
      v14 = 2147483646;
      v10 = 257;
      do
      {
        if ( !v14 )
          break;
        if ( !*v13 )
          break;
        *v8++ = *v13++;
        --v14;
        --v10;
      }
      while ( v10 );
    }
    else
    {
      v15 = (DirectUI::Element *)*((_QWORD *)this + 8);
      v16 = StrToID(L"OtherComboBox");
      Descendent = DirectUI::Element::FindDescendent(v15, v16);
      Selection = DirectUI::Combobox::GetSelection(Descendent);
      v5 = 2147483646;
      v19 = 2147483646;
      Ptr = g_pfn_DPA_GetPtr(*((HDPA *)this + 209), Selection);
      v7 = 257;
      v8 = v26;
      v10 = 257;
      do
      {
        if ( !v19 )
          break;
        if ( !*Ptr )
          break;
        *v8++ = *Ptr++;
        --v19;
        --v10;
      }
      while ( v10 );
    }
  }
  v21 = v8 - 1;
  if ( v10 )
    v21 = v8;
  *v21 = 0;
  if ( v10 )
  {
    v22 = v26;
    v23 = (_WORD *)(*((_QWORD *)this + 12) + 3542LL);
    do
    {
      if ( !v5 )
        break;
      if ( !*v22 )
        break;
      *v23++ = *v22++;
      --v5;
      --v7;
    }
    while ( v7 );
    v24 = v23 - 1;
    if ( v7 )
    {
      v24 = v23;
      v3 = 0;
    }
    *v24 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18000f110  push    rbx
0x18000f112  push    rbp
0x18000f113  push    rsi
0x18000f114  push    rdi
0x18000f115  sub     rsp, 248h
0x18000f11c  mov     rax, cs:__security_cookie
0x18000f123  xor     rax, rsp
0x18000f126  mov     [rsp+268h+var_38], rax
0x18000f12e  mov     rbx, [rcx+40h]
0x18000f132  mov     rdi, rcx
0x18000f135  lea     rcx, aNavadminuserr; "navadminuserR"
0x18000f13c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f140  call    cs:__imp_StrToID
0x18000f146  movzx   edx, ax
0x18000f149  mov     rcx, rbx
0x18000f14c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000f152  test    byte ptr [rax+94h], 10h
0x18000f159  jz      short loc_18000F1AA
0x18000f15b  mov     ebx, 7FFFFFFEh
0x18000f160  lea     r10, [rdi+89Ch]
0x18000f167  mov     r8d, 101h
0x18000f16d  lea     r9, [rsp+268h+var_248]
0x18000f172  mov     eax, ebx
0x18000f174  mov     ecx, r8d
0x18000f177  xor     edx, edx
0x18000f179  test    rax, rax
0x18000f17c  jz      loc_18000F28D
0x18000f182  movzx   r11d, word ptr [r10]
0x18000f186  test    r11w, r11w
0x18000f18a  jz      loc_18000F28D
0x18000f190  mov     [r9], r11w
0x18000f194  add     r10, 2
0x18000f198  add     r9, 2
0x18000f19c  dec     rax
0x18000f19f  sub     rcx, 1
0x18000f1a3  jnz     short loc_18000F179
0x18000f1a5  jmp     loc_18000F28D
0x18000f1aa  mov     rbx, [rdi+40h]
0x18000f1ae  lea     rcx, aNavstandarduse; "navstandarduserR"
0x18000f1b5  call    cs:__imp_StrToID
0x18000f1bb  movzx   edx, ax
0x18000f1be  mov     rcx, rbx
0x18000f1c1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000f1c7  test    byte ptr [rax+94h], 10h
0x18000f1ce  jz      short loc_18000F21C
0x18000f1d0  mov     ebx, 7FFFFFFEh
0x18000f1d5  lea     r10, [rdi+69Ah]
0x18000f1dc  mov     r8d, 101h
0x18000f1e2  lea     r9, [rsp+268h+var_248]
0x18000f1e7  mov     eax, ebx
0x18000f1e9  mov     ecx, r8d
0x18000f1ec  xor     edx, edx
0x18000f1ee  test    rax, rax
0x18000f1f1  jz      loc_18000F28D
0x18000f1f7  movzx   r11d, word ptr [r10]
0x18000f1fb  test    r11w, r11w
0x18000f1ff  jz      loc_18000F28D
0x18000f205  mov     [r9], r11w
0x18000f209  add     r10, 2
0x18000f20d  add     r9, 2
0x18000f211  dec     rax
0x18000f214  sub     rcx, 1
0x18000f218  jnz     short loc_18000F1EE
0x18000f21a  jmp     short loc_18000F28D
0x18000f21c  mov     rbx, [rdi+40h]
0x18000f220  lea     rcx, aOthercombobox; "OtherComboBox"
0x18000f227  call    cs:__imp_StrToID
0x18000f22d  movzx   edx, ax
0x18000f230  mov     rcx, rbx
0x18000f233  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000f239  mov     rcx, rax
0x18000f23c  call    cs:__imp_?GetSelection@Combobox@DirectUI@@QEAAHXZ; DirectUI::Combobox::GetSelection(void)
0x18000f242  mov     rcx, [rdi+688h]; hdpa
0x18000f249  mov     ebx, 7FFFFFFEh
0x18000f24e  movsxd  rdx, eax; i
0x18000f251  mov     ebp, ebx
0x18000f253  call    cs:g_pfn_DPA_GetPtr
0x18000f259  mov     r8d, 101h
0x18000f25f  lea     r9, [rsp+268h+var_248]
0x18000f264  mov     ecx, r8d
0x18000f267  xor     edx, edx
0x18000f269  test    rbp, rbp
0x18000f26c  jz      short loc_18000F28D
0x18000f26e  movzx   r10d, word ptr [rax]
0x18000f272  test    r10w, r10w
0x18000f276  jz      short loc_18000F28D
0x18000f278  mov     [r9], r10w
0x18000f27c  add     rax, 2
0x18000f280  add     r9, 2
0x18000f284  dec     rbp
0x18000f287  sub     rcx, 1
0x18000f28b  jnz     short loc_18000F269
0x18000f28d  test    rcx, rcx
0x18000f290  lea     rax, [r9-2]
0x18000f294  cmovnz  rax, r9
0x18000f298  neg     rcx
0x18000f29b  mov     [rax], dx
0x18000f29e  sbb     eax, eax
0x18000f2a0  not     eax
0x18000f2a2  and     eax, 8007007Ah
0x18000f2a7  test    eax, eax
0x18000f2a9  js      short loc_18000F2EF
0x18000f2ab  mov     r9, [rdi+60h]
0x18000f2af  lea     rax, [rsp+268h+var_248]
0x18000f2b4  add     r9, 0DD6h
0x18000f2bb  test    rbx, rbx
0x18000f2be  jz      short loc_18000F2DD
0x18000f2c0  movzx   ecx, word ptr [rax]
0x18000f2c3  test    cx, cx
0x18000f2c6  jz      short loc_18000F2DD
0x18000f2c8  mov     [r9], cx
0x18000f2cc  add     rax, 2
0x18000f2d0  add     r9, 2
0x18000f2d4  dec     rbx
0x18000f2d7  sub     r8, 1
0x18000f2db  jnz     short loc_18000F2BB
0x18000f2dd  test    r8, r8
0x18000f2e0  lea     rcx, [r9-2]
0x18000f2e4  cmovnz  rcx, r9
0x18000f2e8  cmovnz  rsi, rdx
0x18000f2ec  mov     [rcx], dx
0x18000f2ef  mov     rax, rsi
0x18000f2f2  mov     rcx, [rsp+268h+var_38]
0x18000f2fa  xor     rcx, rsp; StackCookie
0x18000f2fd  call    __security_check_cookie
0x18000f302  add     rsp, 248h
0x18000f309  pop     rdi
0x18000f30a  pop     rsi
0x18000f30b  pop     rbp
0x18000f30c  pop     rbx
0x18000f30d  retn
```
