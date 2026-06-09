# AccessibilityDialog::SetToggleUiStates(void)

- ea: `0x14002235c`
- end: `0x1400223d0`
- name: `?SetToggleUiStates@AccessibilityDialog@@AEAAXXZ`
- size: `116`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400206e8`
- `0x140023370`

## callees

- `0x14002227c`

## string_xrefs

- `0x1400223bc`: `voiceaccess`

## pseudocode

```c
void __fastcall AccessibilityDialog::SetToggleUiStates(AccessibilityDialog *this)
{
  AccessibilityDialog::SetToggleUiState(this, L"magnifierpane");
  AccessibilityDialog::SetToggleUiState(this, L"narrator");
  AccessibilityDialog::SetToggleUiState(this, L"osk");
  AccessibilityDialog::SetToggleUiState(this, L"highcontrast");
  AccessibilityDialog::SetToggleUiState(this, L"stickykeys");
  AccessibilityDialog::SetToggleUiState(this, L"filterkeys");
  AccessibilityDialog::SetToggleUiState(this, L"voiceaccess");
}

```

## disassembly

```asm
0x14002235c  push    rbx
0x14002235e  sub     rsp, 20h
0x140022362  lea     rdx, aMagnifierpane_1; "magnifierpane"
0x140022369  mov     rbx, rcx
0x14002236c  call    ?SetToggleUiState@AccessibilityDialog@@AEAAXPEBG@Z; AccessibilityDialog::SetToggleUiState(ushort const *)
0x140022371  lea     rdx, aNarrator_1; "narrator"
0x140022378  mov     rcx, rbx; this
0x14002237b  call    ?SetToggleUiState@AccessibilityDialog@@AEAAXPEBG@Z; AccessibilityDialog::SetToggleUiState(ushort const *)
0x140022380  lea     rdx, aOsk_1; "osk"
0x140022387  mov     rcx, rbx; this
0x14002238a  call    ?SetToggleUiState@AccessibilityDialog@@AEAAXPEBG@Z; AccessibilityDialog::SetToggleUiState(ushort const *)
0x14002238f  lea     rdx, aHighcontrast_0; "highcontrast"
0x140022396  mov     rcx, rbx; this
0x140022399  call    ?SetToggleUiState@AccessibilityDialog@@AEAAXPEBG@Z; AccessibilityDialog::SetToggleUiState(ushort const *)
0x14002239e  lea     rdx, aStickykeys_0; "stickykeys"
0x1400223a5  mov     rcx, rbx; this
0x1400223a8  call    ?SetToggleUiState@AccessibilityDialog@@AEAAXPEBG@Z; AccessibilityDialog::SetToggleUiState(ushort const *)
0x1400223ad  lea     rdx, aFilterkeys_0; "filterkeys"
0x1400223b4  mov     rcx, rbx; this
0x1400223b7  call    ?SetToggleUiState@AccessibilityDialog@@AEAAXPEBG@Z; AccessibilityDialog::SetToggleUiState(ushort const *)
0x1400223bc  lea     rdx, aVoiceaccess; "voiceaccess"
0x1400223c3  mov     rcx, rbx; this
0x1400223c6  add     rsp, 20h
0x1400223ca  pop     rbx
0x1400223cb  jmp     ?SetToggleUiState@AccessibilityDialog@@AEAAXPEBG@Z; AccessibilityDialog::SetToggleUiState(ushort const *)
```
