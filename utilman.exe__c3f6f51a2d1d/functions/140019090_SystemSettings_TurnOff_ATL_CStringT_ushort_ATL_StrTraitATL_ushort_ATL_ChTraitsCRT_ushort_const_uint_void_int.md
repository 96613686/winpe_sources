# SystemSettings::TurnOff(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)

- ea: `0x140019090`
- end: `0x1400191c8`
- name: `?TurnOff@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140017904`

## callees

- `0x140002480`
- `0x140018ed8`
- `0x140019090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140019134`
- `KERNEL32!GetLastError` at `0x140019134`
- `USER32!SendNotifyMessageW` at `0x1400191a3`
- `USER32!SendNotifyMessageW` at `0x1400191a3`
- `USER32!SystemParametersInfoW` at `0x140019124`
- `USER32!SystemParametersInfoW` at `0x140019183`
- `USER32!SystemParametersInfoW` at `0x140019124`
- `USER32!SystemParametersInfoW` at `0x140019183`

## pseudocode

```c
signed int __fastcall SystemSettings::TurnOff(_QWORD *a1, unsigned int a2, __int64 a3, int a4)
{
  __int64 v5; // rbx
  UINT v6; // edi
  unsigned __int16 *v7; // rax
  __int64 v8; // r8
  int v9; // ecx
  int v10; // edx
  signed int result; // eax
  UINT v12; // edx
  UINT v13; // ecx
  bool v14; // zf
  _OWORD pvParam[4]; // [rsp+20h] [rbp-78h] BYREF

  v5 = 32LL * a2;
  v6 = a4 != 0 ? 3 : 0;
  v7 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v5);
  v8 = *a1 - (_QWORD)v7;
  do
  {
    v9 = *(unsigned __int16 *)((char *)v7 + v8);
    v10 = *v7 - v9;
    if ( v10 )
      break;
    ++v7;
  }
  while ( v9 );
  if ( v10 )
    return -2147024809;
  if ( *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 16) != 2 )
    return 0;
  v12 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 20);
  v13 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 8);
  memset(pvParam, 0, 60);
  LODWORD(pvParam[0]) = v12;
  if ( SystemParametersInfoW(v13, v12, pvParam, 0) )
  {
    if ( (BYTE4(pvParam[0]) & 1) != 0 )
    {
      v14 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 12) == 67;
      DWORD1(pvParam[0]) &= ~1u;
      if ( v14 && IsInMachineOOBEOrLogonUI() )
        DWORD1(pvParam[0]) |= 0x1000u;
      SystemParametersInfoW(
        *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 12),
        *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 20),
        pvParam,
        v6);
      if ( !a4 )
        SendNotifyMessageW(
          HWND_BROADCAST,
          0x1Au,
          *(unsigned int *)((char *)&SystemSettings::_systemSetting + v5 + 12),
          0);
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140019090  push    rbx
0x140019092  push    rbp
0x140019093  push    rsi
0x140019094  push    rdi
0x140019095  sub     rsp, 78h
0x140019099  mov     rax, cs:__security_cookie
0x1400190a0  xor     rax, rsp
0x1400190a3  mov     [rsp+98h+var_38], rax
0x1400190a8  mov     r8, [rcx]
0x1400190ab  lea     rbp, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x1400190b2  mov     eax, r9d
0x1400190b5  mov     ebx, edx
0x1400190b7  neg     eax
0x1400190b9  mov     esi, r9d
0x1400190bc  sbb     edi, edi
0x1400190be  shl     rbx, 5
0x1400190c2  and     edi, 3
0x1400190c5  mov     rax, [rbx+rbp]
0x1400190c9  sub     r8, rax
0x1400190cc  movzx   edx, word ptr [rax]
0x1400190cf  movzx   ecx, word ptr [rax+r8]
0x1400190d4  sub     edx, ecx
0x1400190d6  jnz     short loc_1400190E0
0x1400190d8  add     rax, 2
0x1400190dc  test    ecx, ecx
0x1400190de  jnz     short loc_1400190CC
0x1400190e0  test    edx, edx
0x1400190e2  jz      short loc_1400190EE
0x1400190e4  mov     eax, 80070057h
0x1400190e9  jmp     loc_1400191B1
0x1400190ee  cmp     dword ptr [rbx+rbp+10h], 2
0x1400190f3  jnz     loc_1400191AF
0x1400190f9  mov     edx, [rbx+rbp+14h]; uiParam
0x1400190fd  lea     r8, [rsp+98h+pvParam]; pvParam
0x140019102  mov     ecx, [rbx+rbp+8]; uiAction
0x140019106  xorps   xmm0, xmm0
0x140019109  movups  [rsp+98h+pvParam], xmm0
0x14001910e  xor     r9d, r9d; fWinIni
0x140019111  mov     dword ptr [rsp+98h+pvParam], edx
0x140019115  movups  xmmword ptr [rsp+98h+var_58], xmm0
0x14001911a  movups  xmmword ptr [rsp+98h+var_58+0Ch], xmm0
0x14001911f  movups  [rsp+98h+var_68], xmm0
0x140019124  call    cs:__imp_SystemParametersInfoW
0x14001912b  nop     dword ptr [rax+rax+00h]
0x140019130  test    eax, eax
0x140019132  jnz     short loc_14001914E
0x140019134  call    cs:__imp_GetLastError
0x14001913b  nop     dword ptr [rax+rax+00h]
0x140019140  test    eax, eax
0x140019142  jle     short loc_1400191B1
0x140019144  movzx   eax, ax
0x140019147  or      eax, 80070000h
0x14001914c  jmp     short loc_1400191B1
0x14001914e  mov     eax, dword ptr [rsp+98h+pvParam+4]
0x140019152  test    al, 1
0x140019154  jz      short loc_1400191AF
0x140019156  and     eax, 0FFFFFFFEh
0x140019159  cmp     dword ptr [rbx+rbp+0Ch], 43h ; 'C'
0x14001915e  mov     dword ptr [rsp+98h+pvParam+4], eax
0x140019162  jnz     short loc_140019173
0x140019164  call    ?IsInMachineOOBEOrLogonUI@@YA_NXZ; IsInMachineOOBEOrLogonUI(void)
0x140019169  test    al, al
0x14001916b  jz      short loc_140019173
0x14001916d  bts     dword ptr [rsp+98h+pvParam+4], 0Ch
0x140019173  mov     edx, [rbx+rbp+14h]; uiParam
0x140019177  lea     r8, [rsp+98h+pvParam]; pvParam
0x14001917c  mov     ecx, [rbx+rbp+0Ch]; uiAction
0x140019180  mov     r9d, edi; fWinIni
0x140019183  call    cs:__imp_SystemParametersInfoW
0x14001918a  nop     dword ptr [rax+rax+00h]
0x14001918f  test    esi, esi
0x140019191  jnz     short loc_1400191AF
0x140019193  mov     r8d, [rbx+rbp+0Ch]; wParam
0x140019198  lea     edx, [rsi+1Ah]; Msg
0x14001919b  xor     r9d, r9d; lParam
0x14001919e  mov     ecx, 0FFFFh; hWnd
0x1400191a3  call    cs:__imp_SendNotifyMessageW
0x1400191aa  nop     dword ptr [rax+rax+00h]
0x1400191af  xor     eax, eax
0x1400191b1  mov     rcx, [rsp+98h+var_38]
0x1400191b6  xor     rcx, rsp; StackCookie
0x1400191b9  call    __security_check_cookie
0x1400191be  add     rsp, 78h
0x1400191c2  pop     rdi
0x1400191c3  pop     rsi
0x1400191c4  pop     rbp
0x1400191c5  pop     rbx
0x1400191c6  retn
```
