# SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)

- ea: `0x1400191d0`
- end: `0x14001939b`
- name: `?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400172b0`

## callees

- `0x140002480`
- `0x140018ed8`
- `0x140018fd4`
- `0x1400191d0`
- `0x140026a44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140019381`
- `KERNEL32!GetLastError` at `0x140019381`
- `USER32!SendNotifyMessageW` at `0x140019320`
- `USER32!SendNotifyMessageW` at `0x140019320`
- `USER32!SystemParametersInfoW` at `0x1400192b4`
- `USER32!SystemParametersInfoW` at `0x140019300`
- `USER32!SystemParametersInfoW` at `0x140019371`
- `USER32!SystemParametersInfoW` at `0x1400192b4`
- `USER32!SystemParametersInfoW` at `0x140019300`
- `USER32!SystemParametersInfoW` at `0x140019371`

## pseudocode

```c
signed int __fastcall SystemSettings::TurnOn(_QWORD *a1, unsigned int a2, UINT *a3, int a4)
{
  __int64 v6; // rbx
  UINT v7; // esi
  unsigned __int16 *v8; // rax
  __int64 v9; // r8
  int v10; // ecx
  int v11; // edx
  signed int result; // eax
  int v13; // ecx
  int v14; // ecx
  UINT v15; // eax
  UINT v16; // ecx
  bool v17; // zf
  UINT *v18; // r8
  UINT v19; // edx
  _OWORD pvParam[4]; // [rsp+20h] [rbp-68h] BYREF

  v6 = 32LL * a2;
  v7 = a4 != 0 ? 3 : 0;
  v8 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v6);
  v9 = *a1 - (_QWORD)v8;
  do
  {
    v10 = *(unsigned __int16 *)((char *)v8 + v9);
    v11 = *v8 - v10;
    if ( v11 )
      break;
    ++v8;
  }
  while ( v10 );
  if ( v11 )
    return -2147024809;
  if ( wcscmp_0(*(const wchar_t **)((char *)&SystemSettings::_systemSetting + v6), L"animations")
    || (result = SystemSettings::SetAdditionalAnimationSetting((PVOID)*a3), result >= 0) )
  {
    v13 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 16);
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
          return 0;
        v15 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 20);
        if ( !a3 )
        {
          v16 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 8);
          memset(pvParam, 0, 60);
          LODWORD(pvParam[0]) = v15;
          if ( SystemParametersInfoW(v16, v15, pvParam, 0) )
          {
            if ( (BYTE4(pvParam[0]) & 1) == 0 )
            {
              v17 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 12) == 67;
              DWORD1(pvParam[0]) |= 1u;
              if ( v17 && IsInMachineOOBEOrLogonUI() )
                DWORD1(pvParam[0]) |= 0x1000u;
              SystemParametersInfoW(
                *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 12),
                *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 20),
                pvParam,
                v7);
              if ( !a4 )
                SendNotifyMessageW(
                  HWND_BROADCAST,
                  0x1Au,
                  *(unsigned int *)((char *)&SystemSettings::_systemSetting + v6 + 12),
                  0);
            }
            return 0;
          }
          goto LABEL_26;
        }
        *a3 = v15;
        v18 = a3;
      }
      else
      {
        v18 = (UINT *)(int)*a3;
      }
      v19 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 20);
    }
    else
    {
      v18 = *(UINT **)((char *)&SystemSettings::_systemSetting + v6 + 24);
      v19 = *a3;
    }
    if ( !SystemParametersInfoW(*(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 12), v19, v18, v7) )
    {
LABEL_26:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400191d0  mov     [rsp+arg_0], rbx
0x1400191d5  mov     [rsp+arg_18], rbp
0x1400191da  push    rsi
0x1400191db  push    rdi
0x1400191dc  push    r14
0x1400191de  sub     rsp, 70h
0x1400191e2  mov     rax, cs:__security_cookie
0x1400191e9  xor     rax, rsp
0x1400191ec  mov     [rsp+88h+var_28], rax
0x1400191f1  mov     eax, r9d
0x1400191f4  mov     ebx, edx
0x1400191f6  neg     eax
0x1400191f8  lea     r14, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x1400191ff  mov     rdi, r8
0x140019202  mov     ebp, r9d
0x140019205  mov     r8, [rcx]
0x140019208  sbb     esi, esi
0x14001920a  shl     rbx, 5
0x14001920e  and     esi, 3
0x140019211  mov     rax, [rbx+r14]
0x140019215  sub     r8, rax
0x140019218  movzx   edx, word ptr [rax]
0x14001921b  movzx   ecx, word ptr [rax+r8]
0x140019220  sub     edx, ecx
0x140019222  jnz     short loc_14001922C
0x140019224  add     rax, 2
0x140019228  test    ecx, ecx
0x14001922a  jnz     short loc_140019218
0x14001922c  test    edx, edx
0x14001922e  jz      short loc_14001923A
0x140019230  mov     eax, 80070057h
0x140019235  jmp     loc_14001932E
0x14001923a  mov     rcx, [rbx+r14]; String1
0x14001923e  lea     rdx, aAnimations; "animations"
0x140019245  call    wcscmp_0
0x14001924a  test    eax, eax
0x14001924c  jnz     short loc_14001925D
0x14001924e  mov     ecx, [rdi]; pvParam
0x140019250  call    ?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z; SystemSettings::SetAdditionalAnimationSetting(uint)
0x140019255  test    eax, eax
0x140019257  js      loc_14001932E
0x14001925d  mov     ecx, [rbx+r14+10h]
0x140019262  test    ecx, ecx
0x140019264  jz      loc_140019362
0x14001926a  sub     ecx, 1
0x14001926d  jz      loc_14001935D
0x140019273  cmp     ecx, 1
0x140019276  jnz     loc_14001932C
0x14001927c  mov     eax, [rbx+r14+14h]
0x140019281  test    rdi, rdi
0x140019284  jnz     loc_140019351
0x14001928a  mov     ecx, [rbx+r14+8]; uiAction
0x14001928f  lea     r8, [rsp+88h+pvParam]; pvParam
0x140019294  xorps   xmm0, xmm0
0x140019297  xor     r9d, r9d; fWinIni
0x14001929a  movups  [rsp+88h+pvParam], xmm0
0x14001929f  mov     edx, eax; uiParam
0x1400192a1  mov     dword ptr [rsp+88h+pvParam], eax
0x1400192a5  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x1400192aa  movups  xmmword ptr [rsp+88h+var_48+0Ch], xmm0
0x1400192af  movups  [rsp+88h+var_58], xmm0
0x1400192b4  call    cs:__imp_SystemParametersInfoW
0x1400192bb  nop     dword ptr [rax+rax+00h]
0x1400192c0  test    eax, eax
0x1400192c2  jz      loc_140019381
0x1400192c8  mov     eax, dword ptr [rsp+88h+pvParam+4]
0x1400192cc  test    al, 1
0x1400192ce  jnz     short loc_14001932C
0x1400192d0  or      eax, 1
0x1400192d3  cmp     dword ptr [rbx+r14+0Ch], 43h ; 'C'
0x1400192d9  mov     dword ptr [rsp+88h+pvParam+4], eax
0x1400192dd  jnz     short loc_1400192EE
0x1400192df  call    ?IsInMachineOOBEOrLogonUI@@YA_NXZ; IsInMachineOOBEOrLogonUI(void)
0x1400192e4  test    al, al
0x1400192e6  jz      short loc_1400192EE
0x1400192e8  bts     dword ptr [rsp+88h+pvParam+4], 0Ch
0x1400192ee  mov     edx, [rbx+r14+14h]; uiParam
0x1400192f3  lea     r8, [rsp+88h+pvParam]; pvParam
0x1400192f8  mov     ecx, [rbx+r14+0Ch]; uiAction
0x1400192fd  mov     r9d, esi; fWinIni
0x140019300  call    cs:__imp_SystemParametersInfoW
0x140019307  nop     dword ptr [rax+rax+00h]
0x14001930c  test    ebp, ebp
0x14001930e  jnz     short loc_14001932C
0x140019310  mov     r8d, [rbx+r14+0Ch]; wParam
0x140019315  lea     edx, [rbp+1Ah]; Msg
0x140019318  xor     r9d, r9d; lParam
0x14001931b  mov     ecx, 0FFFFh; hWnd
0x140019320  call    cs:__imp_SendNotifyMessageW
0x140019327  nop     dword ptr [rax+rax+00h]
0x14001932c  xor     eax, eax
0x14001932e  mov     rcx, [rsp+88h+var_28]
0x140019333  xor     rcx, rsp; StackCookie
0x140019336  call    __security_check_cookie
0x14001933b  lea     r11, [rsp+88h+var_18]
0x140019340  mov     rbx, [r11+20h]
0x140019344  mov     rbp, [r11+38h]
0x140019348  mov     rsp, r11
0x14001934b  pop     r14
0x14001934d  pop     rdi
0x14001934e  pop     rsi
0x14001934f  retn
0x140019351  mov     [rdi], eax
0x140019353  mov     r8, rdi
0x140019356  mov     edx, [rbx+r14+14h]
0x14001935b  jmp     short loc_140019369
0x14001935d  movsxd  r8, dword ptr [rdi]
0x140019360  jmp     short loc_140019356
0x140019362  mov     r8, [rbx+r14+18h]; pvParam
0x140019367  mov     edx, [rdi]; uiParam
0x140019369  mov     ecx, [rbx+r14+0Ch]; uiAction
0x14001936e  mov     r9d, esi; fWinIni
0x140019371  call    cs:__imp_SystemParametersInfoW
0x140019378  nop     dword ptr [rax+rax+00h]
0x14001937d  test    eax, eax
0x14001937f  jnz     short loc_14001932C
0x140019381  call    cs:__imp_GetLastError
0x140019388  nop     dword ptr [rax+rax+00h]
0x14001938d  test    eax, eax
0x14001938f  jle     short loc_14001932E
0x140019391  movzx   eax, ax
0x140019394  or      eax, 80070000h
0x140019399  jmp     short loc_14001932E
```
