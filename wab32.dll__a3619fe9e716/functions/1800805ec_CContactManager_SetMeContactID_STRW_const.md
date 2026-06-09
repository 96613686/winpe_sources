# CContactManager::_SetMeContactID(STRW const *)

- ea: `0x1800805ec`
- end: `0x1800807ad`
- name: `?_SetMeContactID@CContactManager@@AEAAJPEBVSTRW@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(CContactManager *__hidden this, const struct STRW *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007f560`
- `0x18007fa4c`

## callees

- `0x180006f7c`
- `0x180008f74`
- `0x18007fd24`
- `0x1800805ec`
- `0x1800840a4`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!SHRegCloseUSKey` at `0x18008073f`
- `SHLWAPI!SHRegCloseUSKey` at `0x18008075a`
- `SHLWAPI!SHRegCloseUSKey` at `0x18008073f`
- `SHLWAPI!SHRegCloseUSKey` at `0x18008075a`
- `SHLWAPI!SHRegCreateUSKeyW` at `0x1800806d6`
- `SHLWAPI!SHRegCreateUSKeyW` at `0x1800806d6`
- `SHLWAPI!SHRegWriteUSValueW` at `0x18008072e`
- `SHLWAPI!SHRegWriteUSValueW` at `0x18008072e`

## string_xrefs

- `0x180080687`: `/PATH:`

## pseudocode

```c
__int64 __fastcall CContactManager::_SetMeContactID(CContactManager *this, const struct STRW *a2)
{
  bool v4; // zf
  unsigned int v5; // ebx
  const struct STRW *v6; // rdi
  const WCHAR *v7; // rsi
  const WCHAR *v8; // rcx
  WCHAR *v9; // rdx
  LSTATUS v10; // eax
  bool v11; // cc
  const WCHAR *v12; // r9
  HUSKEY phNewUSKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v15; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *Path; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[24]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v20[264]; // [rsp+80h] [rbp-80h] BYREF

  STRW::STRW((STRW *)&v18, &v15, 1u);
  STRW::STRW((STRW *)&v16, v20, 0x104u);
  v4 = *((_DWORD *)this + 11) == 0;
  phNewUSKey = 0;
  if ( v4 )
  {
    v5 = -2147418113;
  }
  else
  {
    v6 = (const struct STRW *)&v18;
    v7 = &Str;
    if ( a2 )
      v6 = a2;
    v8 = &Str;
    if ( *(_DWORD *)v6 )
      v8 = (const WCHAR *)*((_QWORD *)v6 + 1);
    if ( (int)CContactID::FindToken(v8, L"/PATH:", (struct STRW *)&v16) < 0 )
      goto LABEL_12;
    v9 = (WCHAR *)&Str;
    if ( v16 )
      v9 = Path;
    if ( (unsigned int)CContactManager::_IsContainedPath(this, v9) )
    {
LABEL_12:
      v10 = SHRegCreateUSKeyW(L"Software\\Microsoft\\WAB\\Me", 3u, 0, &phNewUSKey, 1u);
      v5 = v10;
      v11 = v10 <= 0;
      if ( v10 )
        goto LABEL_13;
      v12 = &Str;
      if ( *(_DWORD *)v6 )
        v12 = (const WCHAR *)*((_QWORD *)v6 + 1);
      if ( *((_DWORD *)this + 354) )
        v7 = (const WCHAR *)*((_QWORD *)this + 178);
      v10 = SHRegWriteUSValueW(phNewUSKey, v7, 1u, v12, 2 * *(_DWORD *)v6 + 2, 2u);
      v5 = v10;
      v11 = v10 <= 0;
      if ( v10 || (v10 = SHRegCloseUSKey(phNewUSKey), v5 = v10, v11 = v10 <= 0, v10) )
      {
LABEL_13:
        if ( !v11 )
          v5 = (unsigned __int16)v10 | 0x80070000;
      }
      else
      {
        phNewUSKey = 0;
      }
    }
    else
    {
      v5 = -2147024809;
    }
    if ( phNewUSKey )
      SHRegCloseUSKey(phNewUSKey);
  }
  v16 = 0;
  BUFFER::ReleaseStorage((BUFFER *)&Path);
  v18 = 0;
  BUFFER::ReleaseStorage((BUFFER *)v19);
  return v5;
}

```

## disassembly

```asm
0x1800805ec  mov     [rsp-8+arg_10], rbx
0x1800805f1  mov     [rsp-8+arg_18], rsi
0x1800805f6  push    rbp
0x1800805f7  push    rdi
0x1800805f8  push    r14
0x1800805fa  lea     rbp, [rsp-1A0h]
0x180080602  sub     rsp, 2A0h
0x180080609  mov     rax, cs:__security_cookie
0x180080610  xor     rax, rsp
0x180080613  mov     [rbp+1B0h+var_20], rax
0x18008061a  mov     r14, rcx
0x18008061d  mov     rbx, rdx
0x180080620  lea     rdx, [rsp+2B0h+var_278]; unsigned __int16 *
0x180080625  mov     r8d, 1; unsigned int
0x18008062b  lea     rcx, [rsp+2B0h+var_250]; this
0x180080630  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180080635  mov     r8d, 104h; unsigned int
0x18008063b  lea     rcx, [rsp+2B0h+var_270]; this
0x180080640  lea     rdx, [rbp+1B0h+var_230]; unsigned __int16 *
0x180080644  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180080649  cmp     dword ptr [r14+2Ch], 0
0x18008064e  mov     [rsp+2B0h+phNewUSKey], 0
0x180080657  jnz     short loc_180080663
0x180080659  mov     ebx, 8000FFFFh
0x18008065e  jmp     loc_180080760
0x180080663  test    rbx, rbx
0x180080666  lea     rdi, [rsp+2B0h+var_250]
0x18008066b  lea     rsi, Str
0x180080672  cmovnz  rdi, rbx
0x180080676  mov     rcx, rsi
0x180080679  cmp     dword ptr [rdi], 0
0x18008067c  jz      short loc_180080682
0x18008067e  mov     rcx, [rdi+8]; psz1
0x180080682  lea     r8, [rsp+2B0h+var_270]; this
0x180080687  lea     rdx, aPath; "/PATH:"
0x18008068e  call    ?FindToken@CContactID@@SAJPEBG0PEAVSTRW@@@Z; CContactID::FindToken(ushort const *,ushort const *,STRW *)
0x180080693  test    eax, eax
0x180080695  js      short loc_1800806BB
0x180080697  cmp     [rsp+2B0h+var_270], 0
0x18008069c  mov     rdx, rsi
0x18008069f  mov     rcx, r14; this
0x1800806a2  cmovnz  rdx, [rsp+2B0h+Path]; Path
0x1800806a8  call    ?_IsContainedPath@CContactManager@@AEAAHPEBG@Z; CContactManager::_IsContainedPath(ushort const *)
0x1800806ad  test    eax, eax
0x1800806af  jnz     short loc_1800806BB
0x1800806b1  mov     ebx, 80070057h
0x1800806b6  jmp     loc_180080750
0x1800806bb  xor     r8d, r8d; hRelativeUSKey
0x1800806be  mov     [rsp+2B0h+dwFlags], 1; dwFlags
0x1800806c6  lea     r9, [rsp+2B0h+phNewUSKey]; phNewUSKey
0x1800806cb  lea     rcx, aSoftwareMicros_16; "Software\\Microsoft\\WAB\\Me"
0x1800806d2  lea     edx, [r8+3]; samDesired
0x1800806d6  call    cs:__imp_SHRegCreateUSKeyW
0x1800806dc  mov     ebx, eax
0x1800806de  test    eax, eax
0x1800806e0  jz      short loc_1800806EF
0x1800806e2  jle     short loc_180080750
0x1800806e4  movzx   ebx, ax
0x1800806e7  or      ebx, 80070000h
0x1800806ed  jmp     short loc_180080750
0x1800806ef  mov     eax, [rdi]
0x1800806f1  mov     r9, rsi
0x1800806f4  test    eax, eax
0x1800806f6  jz      short loc_1800806FC
0x1800806f8  mov     r9, [rdi+8]; pvData
0x1800806fc  cmp     dword ptr [r14+588h], 0
0x180080704  jz      short loc_18008070D
0x180080706  mov     rsi, [r14+590h]
0x18008070d  mov     rcx, [rsp+2B0h+phNewUSKey]; hUSKey
0x180080712  lea     eax, ds:2[rax*2]
0x180080719  mov     [rsp+2B0h+var_288], 2; dwFlags
0x180080721  mov     r8d, 1; dwType
0x180080727  mov     rdx, rsi; pwzValue
0x18008072a  mov     [rsp+2B0h+dwFlags], eax; cbData
0x18008072e  call    cs:__imp_SHRegWriteUSValueW
0x180080734  mov     ebx, eax
0x180080736  test    eax, eax
0x180080738  jnz     short loc_1800806E2
0x18008073a  mov     rcx, [rsp+2B0h+phNewUSKey]; hUSKey
0x18008073f  call    cs:__imp_SHRegCloseUSKey
0x180080745  mov     ebx, eax
0x180080747  test    eax, eax
0x180080749  jnz     short loc_1800806E2
0x18008074b  mov     [rsp+2B0h+phNewUSKey], rbx
0x180080750  mov     rcx, [rsp+2B0h+phNewUSKey]; hUSKey
0x180080755  test    rcx, rcx
0x180080758  jz      short loc_180080760
0x18008075a  call    cs:__imp_SHRegCloseUSKey
0x180080760  lea     rcx, [rsp+2B0h+Path]; this
0x180080765  mov     [rsp+2B0h+var_270], 0
0x18008076d  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x180080772  lea     rcx, [rsp+2B0h+var_248]; this
0x180080777  mov     [rsp+2B0h+var_250], 0
0x18008077f  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x180080784  mov     eax, ebx
0x180080786  mov     rcx, [rbp+1B0h+var_20]
0x18008078d  xor     rcx, rsp; StackCookie
0x180080790  call    __security_check_cookie
0x180080795  lea     r11, [rsp+2B0h+var_10]
0x18008079d  mov     rbx, [r11+30h]
0x1800807a1  mov     rsi, [r11+38h]
0x1800807a5  mov     rsp, r11
0x1800807a8  pop     r14
0x1800807aa  pop     rdi
0x1800807ab  pop     rbp
0x1800807ac  retn
```
