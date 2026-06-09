# CPicturePasswordDUIHost::_RefreshGesturePromptUX(void)

- ea: `0x180011f58`
- end: `0x180012060`
- name: `?_RefreshGesturePromptUX@CPicturePasswordDUIHost@@IEAAXXZ`
- size: `264`
- prototype: `void __fastcall(CPicturePasswordDUIHost *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f670`
- `0x180012d7c`

## callees

- `0x180011b3c`
- `0x180011f58`
- `0x18001f010`

## import_xrefs

- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180012000`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180012000`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001203c`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001203c`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x180011fd4`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x180011fd4`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x180011ff7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x180011ff7`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180011f78`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180011f78`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18001204f`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18001204f`

## pseudocode

```c
void __fastcall CPicturePasswordDUIHost::_RefreshGesturePromptUX(CPicturePasswordDUIHost *this)
{
  __int64 v2; // rbp
  struct DirectUI::Element *PageElement; // rax
  DirectUI::Element *v4; // r14
  DirectUI::Element *v5; // rdi
  __int64 v6; // rax
  struct DirectUI::Value *Int; // rax
  DirectUI::Value *v8; // rsi
  bool v9; // di
  int v10; // eax
  DirectUI::Element *v11; // rax
  unsigned int v13[12]; // [rsp+28h] [rbp-30h] BYREF

  v13[0] = 0;
  DirectUI::Element::StartDefer(this, v13);
  v2 = *((_QWORD *)this + 76);
  PageElement = CPicturePasswordDUIHost::_GetPageElement(this, L"PicturePasswordProgress");
  v4 = 0;
  v5 = PageElement;
  if ( PageElement )
  {
    v6 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)PageElement + 280LL))(PageElement);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v6 + 80LL))(
           v6,
           CPicturePasswordProgressControl::s_pClassInfo) )
    {
      v4 = v5;
    }
  }
  Int = (struct DirectUI::Value *)DirectUI::Value::CreateInt((unsigned int)v2, 0);
  v8 = Int;
  v9 = 1;
  if ( Int )
  {
    DirectUI::Element::SetValue(v4, (const struct DirectUI::PropertyInfo *)&off_18002D0C0, 1, Int);
    DirectUI::Value::Release(v8);
  }
  if ( !v2 )
  {
    v10 = *((_DWORD *)this + 180);
    if ( v10 != 5 && (*((_BYTE *)this + 881) || v10 != 3) )
      v9 = 0;
  }
  v11 = CPicturePasswordDUIHost::_GetPageElement(this, L"startOverButton");
  DirectUI::Element::SetEnabled(v11, v9);
  if ( v13[0] )
    DirectUI::Element::EndDefer(this, v13[0]);
}

```

## disassembly

```asm
0x180011f58  push    rbx
0x180011f5a  push    rbp
0x180011f5b  push    rsi
0x180011f5c  push    rdi
0x180011f5d  push    r14
0x180011f5f  sub     rsp, 30h
0x180011f63  lea     rdx, [rsp+58h+var_30]
0x180011f68  mov     [rsp+58h+var_38], rcx
0x180011f6d  mov     rbx, rcx
0x180011f70  mov     [rsp+58h+var_30], 0
0x180011f78  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x180011f7e  mov     rbp, [rbx+260h]
0x180011f85  lea     rdx, aPicturepasswor; "PicturePasswordProgress"
0x180011f8c  mov     rcx, rbx; this
0x180011f8f  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x180011f94  xor     r14d, r14d
0x180011f97  mov     rdi, rax
0x180011f9a  test    rax, rax
0x180011f9d  jz      short loc_180011FD0
0x180011f9f  mov     rcx, [rax]
0x180011fa2  mov     rax, [rcx+118h]
0x180011fa9  mov     rcx, rdi
0x180011fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fb1  mov     rdx, cs:?s_pClassInfo@CPicturePasswordProgressControl@@0PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CPicturePasswordProgressControl::s_pClassInfo
0x180011fb8  mov     r8, rax
0x180011fbb  mov     rcx, [rax]
0x180011fbe  mov     rax, [rcx+50h]
0x180011fc2  mov     rcx, r8
0x180011fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fca  test    al, al
0x180011fcc  cmovnz  r14, rdi
0x180011fd0  mov     ecx, ebp
0x180011fd2  xor     edx, edx
0x180011fd4  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x180011fda  mov     rsi, rax
0x180011fdd  mov     edi, 1
0x180011fe2  test    rax, rax
0x180011fe5  jz      short loc_180012006
0x180011fe7  mov     r9, rax
0x180011fea  lea     rdx, off_18002D0C0; "GestureCount"
0x180011ff1  mov     r8d, edi
0x180011ff4  mov     rcx, r14
0x180011ff7  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x180011ffd  mov     rcx, rsi
0x180012000  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180012006  test    rbp, rbp
0x180012009  jnz     short loc_180012027
0x18001200b  mov     eax, [rbx+2D0h]
0x180012011  cmp     eax, 5
0x180012014  jz      short loc_180012027
0x180012016  cmp     [rbx+371h], bpl
0x18001201d  jnz     short loc_180012024
0x18001201f  cmp     eax, 3
0x180012022  jz      short loc_180012027
0x180012024  xor     dil, dil
0x180012027  lea     rdx, aStartoverbutto; "startOverButton"
0x18001202e  mov     rcx, rbx; this
0x180012031  call    ?_GetPageElement@CPicturePasswordDUIHost@@IEAAPEAVElement@DirectUI@@PEBG@Z; CPicturePasswordDUIHost::_GetPageElement(ushort const *)
0x180012036  mov     dl, dil
0x180012039  mov     rcx, rax
0x18001203c  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180012042  mov     edx, [rsp+58h+var_30]
0x180012046  test    edx, edx
0x180012048  jz      short loc_180012055
0x18001204a  mov     rcx, [rsp+58h+var_38]
0x18001204f  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x180012055  add     rsp, 30h
0x180012059  pop     r14
0x18001205b  pop     rdi
0x18001205c  pop     rsi
0x18001205d  pop     rbp
0x18001205e  pop     rbx
0x18001205f  retn
```
