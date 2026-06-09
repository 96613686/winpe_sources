# Radio::CRadioSwitchManager::EnsureSliderSwitchAndStoredStateMatch(void)

- ea: `0x18002aa14`
- end: `0x18002aae1`
- name: `?EnsureSliderSwitchAndStoredStateMatch@CRadioSwitchManager@Radio@@QEAAXXZ`
- size: `205`
- prototype: `void __fastcall(Radio::CRadioSwitchManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002aae8`
- `0x18002ac70`

## callees

- `0x18002aa14`
- `0x18002b2f4`
- `0x18002b4e8`

## import_xrefs

- `Rmapi!__imp_ReadSwitchState` at `0x18002aa77`
- `Rmapi!__imp_ReadSwitchState` at `0x18002aa77`

## pseudocode

```c
void __fastcall Radio::CRadioSwitchManager::EnsureSliderSwitchAndStoredStateMatch(Radio::CRadioSwitchManager *this)
{
  Radio::CRadioSwitchManager *v1; // rcx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  Radio::CRadioSwitchManager *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = this;
  if ( (_BYTE)word_18003EFE8 && dword_18003F248 == 4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13);
    }
    LOBYTE(v4) = 0;
    if ( (unsigned int)ReadSwitchState(qword_18003EFF0, 4, &v4) == 1114112 )
    {
      Radio::CRadioSwitchManager::_UpdateIfSliderSwitchChanged(v1, (unsigned __int8)v4);
      return;
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 14;
LABEL_17:
      WPP_SF_(v2[2], v3);
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v3 = 15;
      goto LABEL_17;
    }
  }
}

```

## disassembly

```asm
0x18002aa14  mov     [rsp+arg_0], rcx
0x18002aa19  push    rbx
0x18002aa1a  sub     rsp, 20h
0x18002aa1e  cmp     byte ptr cs:word_18003EFE8, 0
0x18002aa25  jz      loc_18002AAAE
0x18002aa2b  cmp     cs:dword_18003F248, 4
0x18002aa32  jnz     short loc_18002AAAE
0x18002aa34  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa3b  lea     rbx, WPP_GLOBAL_Control
0x18002aa42  cmp     rcx, rbx
0x18002aa45  jz      short loc_18002AA61
0x18002aa47  test    byte ptr [rcx+1Ch], 4
0x18002aa4b  jz      short loc_18002AA61
0x18002aa4d  cmp     byte ptr [rcx+19h], 4
0x18002aa51  jb      short loc_18002AA61
0x18002aa53  mov     rcx, [rcx+10h]
0x18002aa57  mov     edx, 0Dh
0x18002aa5c  call    WPP_SF_
0x18002aa61  lea     r8, [rsp+28h+arg_0]
0x18002aa66  mov     byte ptr [rsp+28h+arg_0], 0
0x18002aa6b  mov     edx, 4
0x18002aa70  lea     rcx, qword_18003EFF0
0x18002aa77  call    cs:__imp_ReadSwitchState
0x18002aa7d  cmp     eax, 110000h
0x18002aa82  jnz     short loc_18002AA8F
0x18002aa84  mov     dl, byte ptr [rsp+28h+arg_0]; bool
0x18002aa88  call    ?_UpdateIfSliderSwitchChanged@CRadioSwitchManager@Radio@@AEAAX_N@Z; Radio::CRadioSwitchManager::_UpdateIfSliderSwitchChanged(bool)
0x18002aa8d  jmp     short loc_18002AADB
0x18002aa8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa96  cmp     rcx, rbx
0x18002aa99  jz      short loc_18002AADB
0x18002aa9b  test    byte ptr [rcx+1Ch], 4
0x18002aa9f  jz      short loc_18002AADB
0x18002aaa1  cmp     byte ptr [rcx+19h], 2
0x18002aaa5  jb      short loc_18002AADB
0x18002aaa7  mov     edx, 0Eh
0x18002aaac  jmp     short loc_18002AAD2
0x18002aaae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aab5  lea     rbx, WPP_GLOBAL_Control
0x18002aabc  cmp     rcx, rbx
0x18002aabf  jz      short loc_18002AADB
0x18002aac1  test    byte ptr [rcx+1Ch], 4
0x18002aac5  jz      short loc_18002AADB
0x18002aac7  cmp     byte ptr [rcx+19h], 4
0x18002aacb  jb      short loc_18002AADB
0x18002aacd  mov     edx, 0Fh
0x18002aad2  mov     rcx, [rcx+10h]
0x18002aad6  call    WPP_SF_
0x18002aadb  add     rsp, 20h
0x18002aadf  pop     rbx
0x18002aae0  retn
```
