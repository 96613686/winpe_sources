# CWcnPageProfileCreateNew::OnGenNewKey(void)

- ea: `0x180014784`
- end: `0x180014878`
- name: `?OnGenNewKey@CWcnPageProfileCreateNew@@QEAAXXZ`
- size: `244`
- prototype: `void __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180015498`

## callees

- `0x180001820`
- `0x180002294`
- `0x18000e19c`
- `0x1800143ac`
- `0x180014784`
- `0x18001d414`
- `0x18002c9ac`

## import_xrefs

- `USER32!SetWindowTextW` at `0x180014859`
- `USER32!SetWindowTextW` at `0x180014859`

## pseudocode

```c
void __fastcall CWcnPageProfileCreateNew::OnGenNewKey(HWND *this)
{
  CWcnPageProfileCreateNew *v2; // rcx
  unsigned int SelectedItemHelper; // eax
  int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  _BYTE v7[96]; // [rsp+20h] [rbp-178h] BYREF
  WCHAR String[128]; // [rsp+80h] [rbp-118h] BYREF

  memset_0(v7, 0, 0x58u);
  SelectedItemHelper = CWcnPageProfileCreateNew::GetSelectedItemHelper(v2, this[43]);
  v4 = WcnPasswordGenerate(dword_1800369E4[7 * SelectedItemHelper], (struct tagWCN_WLAN_PASSPHRASE *)v7);
  if ( v4 >= 0 )
  {
    v4 = WcnWlanPassphraseToString((const struct tagWCN_WLAN_PASSPHRASE *)v7, 0x80u, String);
    if ( v4 >= 0 )
    {
      SetWindowTextW(this[39], String);
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 38;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 37;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, (unsigned int)v4);
    }
  }
}

```

## disassembly

```asm
0x180014784  push    rbx
0x180014786  sub     rsp, 190h
0x18001478d  mov     rax, cs:__security_cookie
0x180014794  xor     rax, rsp
0x180014797  mov     [rsp+198h+var_18], rax
0x18001479f  xor     edx, edx; Val
0x1800147a1  mov     rbx, rcx
0x1800147a4  lea     rcx, [rsp+198h+var_178]; void *
0x1800147a9  lea     r8d, [rdx+58h]; Size
0x1800147ad  call    memset_0
0x1800147b2  mov     rdx, [rbx+158h]; HWND
0x1800147b9  call    ?GetSelectedItemHelper@CWcnPageProfileCreateNew@@AEBAIPEAUHWND__@@@Z; CWcnPageProfileCreateNew::GetSelectedItemHelper(HWND__ *)
0x1800147be  mov     eax, eax
0x1800147c0  lea     rdx, [rsp+198h+var_178]; struct tagWCN_WLAN_PASSPHRASE *
0x1800147c5  imul    rcx, rax, 1Ch
0x1800147c9  lea     rax, dword_1800369E4
0x1800147d0  mov     ecx, [rcx+rax]; unsigned int
0x1800147d3  call    ?WcnPasswordGenerate@@YAJIPEAUtagWCN_WLAN_PASSPHRASE@@@Z; WcnPasswordGenerate(uint,tagWCN_WLAN_PASSPHRASE *)
0x1800147d8  test    eax, eax
0x1800147da  jns     short loc_18001480F
0x1800147dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147e3  lea     rdx, WPP_GLOBAL_Control
0x1800147ea  cmp     rcx, rdx
0x1800147ed  jz      short loc_18001485F
0x1800147ef  cmp     byte ptr [rcx+19h], 2
0x1800147f3  jb      short loc_18001485F
0x1800147f5  mov     edx, 25h ; '%'
0x1800147fa  mov     rcx, [rcx+10h]
0x1800147fe  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180014805  mov     r9d, eax
0x180014808  call    WPP_SF_d
0x18001480d  jmp     short loc_18001485F
0x18001480f  lea     r8, [rsp+198h+String]; unsigned __int16 *
0x180014817  mov     edx, 80h; unsigned int
0x18001481c  lea     rcx, [rsp+198h+var_178]; struct tagWCN_WLAN_PASSPHRASE *
0x180014821  call    ?WcnWlanPassphraseToString@@YAJPEBUtagWCN_WLAN_PASSPHRASE@@KPEAG@Z; WcnWlanPassphraseToString(tagWCN_WLAN_PASSPHRASE const *,ulong,ushort *)
0x180014826  test    eax, eax
0x180014828  jns     short loc_18001484A
0x18001482a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014831  lea     rdx, WPP_GLOBAL_Control
0x180014838  cmp     rcx, rdx
0x18001483b  jz      short loc_18001485F
0x18001483d  cmp     byte ptr [rcx+19h], 2
0x180014841  jb      short loc_18001485F
0x180014843  mov     edx, 26h ; '&'
0x180014848  jmp     short loc_1800147FA
0x18001484a  mov     rcx, [rbx+138h]; hWnd
0x180014851  lea     rdx, [rsp+198h+String]; lpString
0x180014859  call    cs:__imp_SetWindowTextW
0x18001485f  mov     rcx, [rsp+198h+var_18]
0x180014867  xor     rcx, rsp; StackCookie
0x18001486a  call    __security_check_cookie
0x18001486f  add     rsp, 190h
0x180014876  pop     rbx
0x180014877  retn
```
