# CMachineLockSettings::PopulateDelayLockSettings(DirectUI::TouchSelect *)

- ea: `0x18002bac4`
- end: `0x18002bb7b`
- name: `?PopulateDelayLockSettings@CMachineLockSettings@@QEAAXPEAVTouchSelect@DirectUI@@@Z`
- size: `183`
- prototype: `void __fastcall(CMachineLockSettings *__hidden this, struct DirectUI::TouchSelect *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180027dd0`

## callees

- `0x18002bac4`

## import_xrefs

- `DUI70!?SetSelectionIndex@TouchSelect@DirectUI@@QEAAJH@Z` at `0x18002bb64`
- `DUI70!?SetSelectionIndex@TouchSelect@DirectUI@@QEAAJH@Z` at `0x18002bb64`
- `DUI70!?AddString@TouchSelect@DirectUI@@QEAAJPEBGPEAPEAVElement@2@@Z` at `0x18002bb0f`
- `DUI70!?AddString@TouchSelect@DirectUI@@QEAAJPEBGPEAPEAVElement@2@@Z` at `0x18002bb0f`
- `DUI70!?RemoveAll@TouchSelect@DirectUI@@QEAAXXZ` at `0x18002bada`
- `DUI70!?RemoveAll@TouchSelect@DirectUI@@QEAAXXZ` at `0x18002bb4e`
- `DUI70!?RemoveAll@TouchSelect@DirectUI@@QEAAXXZ` at `0x18002bada`
- `DUI70!?RemoveAll@TouchSelect@DirectUI@@QEAAXXZ` at `0x18002bb4e`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18002bb2a`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18002bb73`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18002bb2a`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18002bb73`

## pseudocode

```c
void __fastcall CMachineLockSettings::PopulateDelayLockSettings(
        CMachineLockSettings *this,
        struct DirectUI::TouchSelect *a2)
{
  unsigned int v4; // ebp
  unsigned __int64 v5; // rbx
  __int64 v6; // rdx
  int v7; // r15d
  struct DirectUI::Element *v8; // [rsp+60h] [rbp+8h] BYREF

  DirectUI::TouchSelect::RemoveAll(a2);
  if ( (*((_BYTE *)this + 52) & 8) != 0 )
  {
    v4 = 0;
    v5 = 0;
    while ( v5 < *((_QWORD *)this + 2) )
    {
      v6 = *((_QWORD *)this + 1);
      v8 = 0;
      v7 = DirectUI::TouchSelect::AddString(a2, *(const unsigned __int16 **)(v6 + 16 * v5), &v8);
      if ( v7 >= 0
        && (DirectUI::Element::SetEnabled(v8, *(_BYTE *)(*((_QWORD *)this + 1) + 16 * v5 + 12)),
            *(_BYTE *)(*((_QWORD *)this + 1) + 16 * v5 + 12)) )
      {
        ++v4;
        ++v5;
      }
      else
      {
        ++v5;
        if ( v7 < 0 )
          goto LABEL_8;
      }
    }
    DirectUI::TouchSelect::SetSelectionIndex(a2, *((_DWORD *)this + 10));
    DirectUI::Element::SetEnabled(a2, v4 > 1);
  }
  else
  {
LABEL_8:
    DirectUI::TouchSelect::RemoveAll(a2);
  }
}

```

## disassembly

```asm
0x18002bac4  push    rbx
0x18002bac6  push    rbp
0x18002bac7  push    rsi
0x18002bac8  push    rdi
0x18002bac9  push    r14
0x18002bacb  push    r15
0x18002bacd  sub     rsp, 28h
0x18002bad1  mov     rsi, rcx
0x18002bad4  mov     rdi, rdx
0x18002bad7  mov     rcx, rdx
0x18002bada  call    cs:__imp_?RemoveAll@TouchSelect@DirectUI@@QEAAXXZ; DirectUI::TouchSelect::RemoveAll(void)
0x18002bae0  test    byte ptr [rsi+34h], 8
0x18002bae4  jz      short loc_18002BB4B
0x18002bae6  xor     ebp, ebp
0x18002bae8  xor     ebx, ebx
0x18002baea  mov     rcx, rdi
0x18002baed  cmp     rbx, [rsi+10h]
0x18002baf1  jnb     short loc_18002BB61
0x18002baf3  mov     rdx, [rsi+8]
0x18002baf7  lea     r8, [rsp+58h+arg_0]
0x18002bafc  mov     [rsp+58h+arg_0], 0
0x18002bb05  mov     r14, rbx
0x18002bb08  add     r14, r14
0x18002bb0b  mov     rdx, [rdx+r14*8]
0x18002bb0f  call    cs:__imp_?AddString@TouchSelect@DirectUI@@QEAAJPEBGPEAPEAVElement@2@@Z; DirectUI::TouchSelect::AddString(ushort const *,DirectUI::Element * *)
0x18002bb15  mov     r15d, eax
0x18002bb18  test    eax, eax
0x18002bb1a  js      short loc_18002BB43
0x18002bb1c  mov     rdx, [rsi+8]
0x18002bb20  mov     rcx, [rsp+58h+arg_0]
0x18002bb25  mov     dl, [rdx+r14*8+0Ch]
0x18002bb2a  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18002bb30  mov     rcx, [rsi+8]
0x18002bb34  cmp     byte ptr [rcx+r14*8+0Ch], 0
0x18002bb3a  jz      short loc_18002BB43
0x18002bb3c  inc     ebp
0x18002bb3e  inc     rbx
0x18002bb41  jmp     short loc_18002BAEA
0x18002bb43  inc     rbx
0x18002bb46  test    r15d, r15d
0x18002bb49  jns     short loc_18002BAEA
0x18002bb4b  mov     rcx, rdi
0x18002bb4e  call    cs:__imp_?RemoveAll@TouchSelect@DirectUI@@QEAAXXZ; DirectUI::TouchSelect::RemoveAll(void)
0x18002bb54  add     rsp, 28h
0x18002bb58  pop     r15
0x18002bb5a  pop     r14
0x18002bb5c  pop     rdi
0x18002bb5d  pop     rsi
0x18002bb5e  pop     rbp
0x18002bb5f  pop     rbx
0x18002bb60  retn
0x18002bb61  mov     edx, [rsi+28h]
0x18002bb64  call    cs:__imp_?SetSelectionIndex@TouchSelect@DirectUI@@QEAAJH@Z; DirectUI::TouchSelect::SetSelectionIndex(int)
0x18002bb6a  cmp     ebp, 1
0x18002bb6d  mov     rcx, rdi
0x18002bb70  setnbe  dl
0x18002bb73  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18002bb79  jmp     short loc_18002BB54
```
