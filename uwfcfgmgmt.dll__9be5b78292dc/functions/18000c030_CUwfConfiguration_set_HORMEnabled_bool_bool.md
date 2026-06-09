# CUwfConfiguration::set_HORMEnabled(bool,bool)

- ea: `0x18000c030`
- end: `0x18000c0e4`
- name: `?set_HORMEnabled@CUwfConfiguration@@QEAAJ_N0@Z`
- size: `180`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, unsigned __int8, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017230`

## callees

- `0x18000a150`
- `0x18000a8c8`
- `0x18000bdf4`
- `0x18000c030`
- `0x18000d18c`

## string_xrefs

- `0x18000c06c`: `HKLM\SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Dynamic`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::set_HORMEnabled(CUwfConfiguration *this, unsigned __int8 a2, char a3)
{
  CUwfConfiguration *v6; // rcx
  int updated; // ebx

  updated = CUwfConfiguration::UpdateDWORDValue(this, (CUwfConfiguration *)((char *)this + 24), L"HormEnabled", a2, 0);
  if ( updated < 0 )
    goto LABEL_11;
  if ( !a3 )
    return (unsigned int)updated;
  updated = CUwfConfiguration::commitRegKeyValue(
              v6,
              L"HKLM\\SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Dynamic",
              L"HormEnabled");
  if ( updated < 0 )
    goto LABEL_11;
  if ( !a2 )
  {
    updated = CUwfConfiguration::set_BootMgrHORMEnabled(this, 0);
    if ( updated < 0 )
      goto LABEL_11;
    updated = CUwfConfiguration::set_WinResumeHORMEnabled(this, 0);
    if ( updated < 0 )
    {
      CUwfConfiguration::set_BootMgrHORMEnabled(this, 1);
      goto LABEL_11;
    }
    return (unsigned int)updated;
  }
  updated = CUwfConfiguration::set_WinResumeHORMEnabled(this, 1);
  if ( updated < 0 )
  {
LABEL_11:
    *((_DWORD *)this + 4) = updated;
    return (unsigned int)updated;
  }
  updated = CUwfConfiguration::set_BootMgrHORMEnabled(this, 1);
  if ( updated < 0 )
  {
    CUwfConfiguration::set_WinResumeHORMEnabled(this, 0);
    goto LABEL_11;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c030  push    rbx
0x18000c032  push    rbp
0x18000c033  push    rsi
0x18000c034  push    rdi
0x18000c035  sub     rsp, 38h
0x18000c039  movzx   esi, dl
0x18000c03c  mov     bpl, r8b
0x18000c03f  mov     r9d, esi; unsigned int
0x18000c042  mov     [rsp+58h+var_38], 0; bool
0x18000c047  lea     rdx, [rcx+18h]; struct CUwfRegKey *
0x18000c04b  mov     rdi, rcx
0x18000c04e  lea     r8, aHormenabled; "HormEnabled"
0x18000c055  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c05a  mov     ebx, eax
0x18000c05c  test    eax, eax
0x18000c05e  js      short loc_18000C0D6
0x18000c060  test    bpl, bpl
0x18000c063  jz      short loc_18000C0D9
0x18000c065  lea     r8, aHormenabled; "HormEnabled"
0x18000c06c  lea     rdx, aHklmSystemCurr_0; "HKLM\\SYSTEM\\CurrentControlSet\\Servic"...
0x18000c073  call    ?commitRegKeyValue@CUwfConfiguration@@AEAAJPEBG0@Z; CUwfConfiguration::commitRegKeyValue(ushort const *,ushort const *)
0x18000c078  mov     ebx, eax
0x18000c07a  test    eax, eax
0x18000c07c  js      short loc_18000C0D6
0x18000c07e  mov     rcx, rdi; this
0x18000c081  test    sil, sil
0x18000c084  jz      short loc_18000C0AF
0x18000c086  mov     dl, 1; bool
0x18000c088  call    ?set_WinResumeHORMEnabled@CUwfConfiguration@@AEAAJ_N@Z; CUwfConfiguration::set_WinResumeHORMEnabled(bool)
0x18000c08d  mov     ebx, eax
0x18000c08f  test    eax, eax
0x18000c091  js      short loc_18000C0D6
0x18000c093  mov     dl, 1; bool
0x18000c095  mov     rcx, rdi; this
0x18000c098  call    ?set_BootMgrHORMEnabled@CUwfConfiguration@@AEAAJ_N@Z; CUwfConfiguration::set_BootMgrHORMEnabled(bool)
0x18000c09d  mov     ebx, eax
0x18000c09f  test    eax, eax
0x18000c0a1  jns     short loc_18000C0D9
0x18000c0a3  xor     edx, edx; bool
0x18000c0a5  mov     rcx, rdi; this
0x18000c0a8  call    ?set_WinResumeHORMEnabled@CUwfConfiguration@@AEAAJ_N@Z; CUwfConfiguration::set_WinResumeHORMEnabled(bool)
0x18000c0ad  jmp     short loc_18000C0D6
0x18000c0af  xor     edx, edx; bool
0x18000c0b1  call    ?set_BootMgrHORMEnabled@CUwfConfiguration@@AEAAJ_N@Z; CUwfConfiguration::set_BootMgrHORMEnabled(bool)
0x18000c0b6  mov     ebx, eax
0x18000c0b8  test    eax, eax
0x18000c0ba  js      short loc_18000C0D6
0x18000c0bc  xor     edx, edx; bool
0x18000c0be  mov     rcx, rdi; this
0x18000c0c1  call    ?set_WinResumeHORMEnabled@CUwfConfiguration@@AEAAJ_N@Z; CUwfConfiguration::set_WinResumeHORMEnabled(bool)
0x18000c0c6  mov     ebx, eax
0x18000c0c8  test    eax, eax
0x18000c0ca  jns     short loc_18000C0D9
0x18000c0cc  mov     dl, 1; bool
0x18000c0ce  mov     rcx, rdi; this
0x18000c0d1  call    ?set_BootMgrHORMEnabled@CUwfConfiguration@@AEAAJ_N@Z; CUwfConfiguration::set_BootMgrHORMEnabled(bool)
0x18000c0d6  mov     [rdi+10h], ebx
0x18000c0d9  mov     eax, ebx
0x18000c0db  add     rsp, 38h
0x18000c0df  pop     rdi
0x18000c0e0  pop     rsi
0x18000c0e1  pop     rbp
0x18000c0e2  pop     rbx
0x18000c0e3  retn
```
