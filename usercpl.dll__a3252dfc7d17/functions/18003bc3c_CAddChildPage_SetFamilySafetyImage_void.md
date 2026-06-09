# CAddChildPage::_SetFamilySafetyImage(void)

- ea: `0x18003bc3c`
- end: `0x18003bde7`
- name: `?_SetFamilySafetyImage@CAddChildPage@@AEAAXXZ`
- size: `427`
- prototype: `void __fastcall(CAddChildPage *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18003b7a0`

## callees

- `0x18003bc3c`
- `0x18006422c`
- `0x1800705e8`
- `0x180074f14`

## import_xrefs

- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x18003bc5e`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x18003bc5e`
- `USER32!SystemParametersInfoW` at `0x18003bc94`
- `USER32!SystemParametersInfoW` at `0x18003bcfe`
- `USER32!SystemParametersInfoW` at `0x18003bd67`
- `USER32!SystemParametersInfoW` at `0x18003bc94`
- `USER32!SystemParametersInfoW` at `0x18003bcfe`
- `USER32!SystemParametersInfoW` at `0x18003bd67`
- `USER32!GetSysColor` at `0x18003bca9`
- `USER32!GetSysColor` at `0x18003bd15`
- `USER32!GetSysColor` at `0x18003bd7e`
- `USER32!GetSysColor` at `0x18003bca9`
- `USER32!GetSysColor` at `0x18003bd15`
- `USER32!GetSysColor` at `0x18003bd7e`

## pseudocode

```c
void __fastcall CAddChildPage::_SetFamilySafetyImage(CAddChildPage *this)
{
  struct DirectUI::Element *Element; // rsi
  __int64 v2; // rdi
  int v3; // eax
  __int64 v4; // rcx
  int v5; // eax
  int v6; // ebx
  DWORD SysColor; // eax
  int v8; // ebx
  DWORD v9; // eax
  int v10; // ebx
  DWORD v11; // eax
  __int64 v12; // r8
  int pvParam; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+34h] [rbp-34h]
  int v15; // [rsp+3Ch] [rbp-2Ch]
  int v16; // [rsp+40h] [rbp-28h] BYREF
  __int64 v17; // [rsp+44h] [rbp-24h]
  int v18; // [rsp+4Ch] [rbp-1Ch]
  int v19; // [rsp+50h] [rbp-18h] BYREF
  __int64 v20; // [rsp+54h] [rbp-14h]
  int v21; // [rsp+5Ch] [rbp-Ch]

  Element = CBaseTaskFlowPage::_FindElement(this, L"idFamilySafetyImage");
  v2 = 9;
  v3 = GetScaleFactorForDevice(0) - 100;
  if ( v3 )
  {
    v5 = v3 - 40;
    if ( v5 )
    {
      if ( v5 == 40 )
      {
        pvParam = 16;
        v14 = 0;
        v15 = 0;
        if ( !SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0)
          || (v6 = 1, (v14 & 1) == 0)
          || (SysColor = GetSysColor(5),
              v4 = BYTE2(SysColor) + 5 * BYTE1(SysColor) + 2 * (unsigned int)(unsigned __int8)SysColor,
              (unsigned int)v4 <= 0x400) )
        {
          v6 = 0;
        }
        v2 = v6 != 0 ? 14LL : 11LL;
      }
    }
    else
    {
      v16 = 16;
      v17 = 0;
      v18 = 0;
      if ( !SystemParametersInfoW(0x42u, 0x10u, &v16, 0)
        || (v8 = 1, (v17 & 1) == 0)
        || (v9 = GetSysColor(5),
            v4 = BYTE2(v9) + 5 * BYTE1(v9) + 2 * (unsigned int)(unsigned __int8)v9,
            (unsigned int)v4 <= 0x400) )
      {
        v8 = 0;
      }
      v2 = v8 != 0 ? 13LL : 10LL;
    }
  }
  else
  {
    v19 = 16;
    v20 = 0;
    v21 = 0;
    if ( !SystemParametersInfoW(0x42u, 0x10u, &v19, 0)
      || (v10 = 1, (v20 & 1) == 0)
      || (v11 = GetSysColor(5),
          v4 = BYTE2(v11) + 5 * BYTE1(v11) + 2 * (unsigned int)(unsigned __int8)v11,
          (unsigned int)v4 <= 0x400) )
    {
      v10 = 0;
    }
    v2 = v10 != 0 ? 12LL : 9LL;
  }
  if ( (int)LoadImageScaled(v4, v2) >= 0 )
  {
    LOBYTE(v12) = 2;
    DUI_SetElementBitmap(Element, 0, v12);
  }
}

```

## disassembly

```asm
0x18003bc3c  push    rbp
0x18003bc3e  push    rbx
0x18003bc3f  push    rsi
0x18003bc40  push    rdi
0x18003bc41  mov     rbp, rsp
0x18003bc44  sub     rsp, 68h
0x18003bc48  lea     rdx, aIdfamilysafety; "idFamilySafetyImage"
0x18003bc4f  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x18003bc54  xor     ecx, ecx
0x18003bc56  mov     rsi, rax
0x18003bc59  mov     edi, 9
0x18003bc5e  call    cs:__imp_GetScaleFactorForDevice
0x18003bc64  sub     eax, 64h ; 'd'
0x18003bc67  jz      loc_18003BD4C
0x18003bc6d  sub     eax, 28h ; '('
0x18003bc70  jz      short loc_18003BCE3
0x18003bc72  cmp     eax, 28h ; '('
0x18003bc75  jnz     loc_18003BDB2
0x18003bc7b  xor     eax, eax
0x18003bc7d  lea     edx, [rdi+7]; uiParam
0x18003bc80  xor     r9d, r9d; fWinIni
0x18003bc83  mov     [rbp+pvParam], edx
0x18003bc86  lea     r8, [rbp+pvParam]; pvParam
0x18003bc8a  mov     [rbp+var_34], rax
0x18003bc8e  lea     ecx, [rdi+39h]; uiAction
0x18003bc91  mov     [rbp+var_2C], eax
0x18003bc94  call    cs:__imp_SystemParametersInfoW
0x18003bc9a  test    eax, eax
0x18003bc9c  jz      short loc_18003BCD0
0x18003bc9e  lea     ebx, [rdi-8]
0x18003bca1  test    byte ptr [rbp+var_34], bl
0x18003bca4  jz      short loc_18003BCD0
0x18003bca6  lea     ecx, [rdi-4]; nIndex
0x18003bca9  call    cs:__imp_GetSysColor
0x18003bcaf  movzx   ecx, ax
0x18003bcb2  shr     ecx, 8
0x18003bcb5  lea     edx, [rcx+rcx*4]
0x18003bcb8  mov     ecx, eax
0x18003bcba  shr     ecx, 10h
0x18003bcbd  movzx   ecx, cl
0x18003bcc0  add     edx, ecx
0x18003bcc2  movzx   eax, al
0x18003bcc5  lea     ecx, [rdx+rax*2]
0x18003bcc8  cmp     ecx, 400h
0x18003bcce  ja      short loc_18003BCD2
0x18003bcd0  xor     ebx, ebx
0x18003bcd2  neg     ebx
0x18003bcd4  sbb     rdi, rdi
0x18003bcd7  and     edi, 3
0x18003bcda  add     rdi, 0Bh
0x18003bcde  jmp     loc_18003BDB2
0x18003bce3  mov     edx, 10h; uiParam
0x18003bce8  lea     r8, [rbp+var_28]; pvParam
0x18003bcec  xor     eax, eax
0x18003bcee  mov     [rbp+var_28], edx
0x18003bcf1  xor     r9d, r9d; fWinIni
0x18003bcf4  mov     [rbp+var_24], rax
0x18003bcf8  mov     [rbp+var_1C], eax
0x18003bcfb  lea     ecx, [rdx+32h]; uiAction
0x18003bcfe  call    cs:__imp_SystemParametersInfoW
0x18003bd04  test    eax, eax
0x18003bd06  jz      short loc_18003BD3C
0x18003bd08  mov     ebx, 1
0x18003bd0d  test    byte ptr [rbp+var_24], bl
0x18003bd10  jz      short loc_18003BD3C
0x18003bd12  lea     ecx, [rbx+4]; nIndex
0x18003bd15  call    cs:__imp_GetSysColor
0x18003bd1b  movzx   ecx, ax
0x18003bd1e  shr     ecx, 8
0x18003bd21  lea     edx, [rcx+rcx*4]
0x18003bd24  mov     ecx, eax
0x18003bd26  shr     ecx, 10h
0x18003bd29  movzx   ecx, cl
0x18003bd2c  add     edx, ecx
0x18003bd2e  movzx   eax, al
0x18003bd31  lea     ecx, [rdx+rax*2]
0x18003bd34  cmp     ecx, 400h
0x18003bd3a  ja      short loc_18003BD3E
0x18003bd3c  xor     ebx, ebx
0x18003bd3e  neg     ebx
0x18003bd40  sbb     rdi, rdi
0x18003bd43  and     edi, 3
0x18003bd46  add     rdi, 0Ah
0x18003bd4a  jmp     short loc_18003BDB2
0x18003bd4c  mov     edx, 10h; uiParam
0x18003bd51  lea     r8, [rbp+var_18]; pvParam
0x18003bd55  xor     eax, eax
0x18003bd57  mov     [rbp+var_18], edx
0x18003bd5a  xor     r9d, r9d; fWinIni
0x18003bd5d  mov     [rbp+var_14], rax
0x18003bd61  mov     [rbp+var_C], eax
0x18003bd64  lea     ecx, [rdx+32h]; uiAction
0x18003bd67  call    cs:__imp_SystemParametersInfoW
0x18003bd6d  test    eax, eax
0x18003bd6f  jz      short loc_18003BDA5
0x18003bd71  mov     ebx, 1
0x18003bd76  test    byte ptr [rbp+var_14], bl
0x18003bd79  jz      short loc_18003BDA5
0x18003bd7b  lea     ecx, [rbx+4]; nIndex
0x18003bd7e  call    cs:__imp_GetSysColor
0x18003bd84  movzx   ecx, ax
0x18003bd87  shr     ecx, 8
0x18003bd8a  lea     edx, [rcx+rcx*4]
0x18003bd8d  mov     ecx, eax
0x18003bd8f  shr     ecx, 10h
0x18003bd92  movzx   ecx, cl
0x18003bd95  add     edx, ecx
0x18003bd97  movzx   eax, al
0x18003bd9a  lea     ecx, [rdx+rax*2]
0x18003bd9d  cmp     ecx, 400h
0x18003bda3  ja      short loc_18003BDA7
0x18003bda5  xor     ebx, ebx
0x18003bda7  neg     ebx
0x18003bda9  sbb     rax, rax
0x18003bdac  and     eax, 3
0x18003bdaf  add     rdi, rax
0x18003bdb2  lea     rax, [rbp+arg_8]
0x18003bdb6  mov     [rbp+arg_8], 0
0x18003bdbe  mov     rdx, rdi
0x18003bdc1  mov     [rsp+68h+var_48], rax
0x18003bdc6  call    LoadImageScaled
0x18003bdcb  test    eax, eax
0x18003bdcd  js      short loc_18003BDDE
0x18003bdcf  mov     rdx, [rbp+arg_8]
0x18003bdd3  mov     r8b, 2
0x18003bdd6  mov     rcx, rsi
0x18003bdd9  call    ?DUI_SetElementBitmap@@YAJPEAVElement@DirectUI@@PEAUHBITMAP__@@EIW4ImageRtlMode@@_N@Z; DUI_SetElementBitmap(DirectUI::Element *,HBITMAP__ *,uchar,uint,ImageRtlMode,bool)
0x18003bdde  add     rsp, 68h
0x18003bde2  pop     rdi
0x18003bde3  pop     rsi
0x18003bde4  pop     rbx
0x18003bde5  pop     rbp
0x18003bde6  retn
```
