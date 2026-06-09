# CACConnectionPage::OnIHVConfigCheckbox(ushort,ushort,HWND__ *,int &)

- ea: `0x18000df1c`
- end: `0x18000e13f`
- name: `?OnIHVConfigCheckbox@CACConnectionPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `547`
- prototype: `__int64 __usercall@<rax>(CACConnectionPage *__hidden this@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, HWND@<r9>, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18000ed80`

## callees

- `0x180001e26`
- `0x180006134`
- `0x18000dc38`
- `0x18000df1c`
- `0x180010f64`
- `0x180011188`

## import_xrefs

- `USER32!EnableWindow` at `0x18000dfb4`
- `USER32!EnableWindow` at `0x18000dfb4`
- `USER32!SendMessageW` at `0x18000dfa5`
- `USER32!SendMessageW` at `0x18000dfa5`
- `wlanapi!WpFreeMemory` at `0x18000e0b2`
- `wlanapi!WpFreeMemory` at `0x18000e0b2`
- `wlanapi!WpAllocMemory` at `0x18000e0c2`
- `wlanapi!WpAllocMemory` at `0x18000e0c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e000`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e009`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e000`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e009`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e0f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e10e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e0f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e10e`

## pseudocode

```c
__int64 __fastcall CACConnectionPage::OnIHVConfigCheckbox(
        CACConnectionPage *this,
        __int64 a2,
        __int16 a3,
        HWND a4,
        int *a5)
{
  __int64 v5; // rax
  int PropertyDisplayInfo; // esi
  HWND v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // eax
  HWND v13; // rcx
  unsigned __int16 *v14; // rbp
  __int64 v15; // rax
  const OLECHAR *v16; // rcx
  const OLECHAR *v17; // rax
  IHVExtHelper *v18; // rbx
  struct _DOT11EXT_IHV_PARAMS *UpdatedIHVParams; // rax
  IHVExtHelper *v20; // rbx
  struct _DOT11EXT_IHV_PARAMS *v21; // rax
  void *v22; // r14
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rcx
  size_t v26; // r15
  void *v27; // rax
  void *v28; // rdi
  int v30; // [rsp+70h] [rbp+18h] BYREF
  void *Src; // [rsp+78h] [rbp+20h] BYREF

  Src = a4;
  LOWORD(v30) = a3;
  v5 = *((_QWORD *)this + 18);
  PropertyDisplayInfo = 0;
  v8 = (HWND)*((_QWORD *)this + 11);
  v9 = *(_QWORD *)(*(_QWORD *)(v5 + 552) + 32LL);
  Src = 0;
  v30 = 0;
  if ( v8 )
  {
    v10 = *((_QWORD *)this + 20);
    if ( v10 && (v11 = *(_QWORD *)(v10 + 24), *(_DWORD *)(v11 + 8)) )
    {
      if ( *(_DWORD *)(v11 + 8) != 1 )
      {
        PropertyDisplayInfo = -2147467259;
        goto LABEL_24;
      }
      v12 = SendMessageW(v8, 0xF0u, 0, 0);
      v13 = (HWND)*((_QWORD *)this + 10);
      *((_DWORD *)this + 31) = v12;
      EnableWindow(v13, v12);
      if ( *((_DWORD *)this + 31) )
      {
        *(_DWORD *)(v9 + 400) = 1;
        v14 = 0;
        v15 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 18) + 552LL) + 32LL);
        if ( *(_DWORD *)(v15 + 400) )
        {
          v16 = *(const OLECHAR **)(v15 + 408);
          if ( v16 )
          {
            v17 = SysAllocString(v16);
            v14 = SysAllocString(v17);
          }
        }
        v18 = *(IHVExtHelper **)(*((_QWORD *)this + 20) + 24LL);
        UpdatedIHVParams = CACConnectionPage::GetUpdatedIHVParams(this);
        PropertyDisplayInfo = IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(v18, v14, UpdatedIHVParams, 0);
        v20 = *(IHVExtHelper **)(*((_QWORD *)this + 20) + 24LL);
        v21 = CACConnectionPage::GetUpdatedIHVParams(this);
        IHVExtHelper::IHVExtHlpSetSelected(v20, v14, v21, (unsigned __int16 **)&Src, &v30, 0);
        if ( v30 )
        {
          v22 = Src;
          if ( Src )
          {
            v23 = -1;
            v24 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 18) + 552LL) + 32LL);
            do
              ++v23;
            while ( *((_WORD *)Src + v23) );
            v25 = *(_QWORD *)(v24 + 408);
            v26 = 2 * v23 + 2;
            if ( v25 )
            {
              WpFreeMemory(v25);
              *(_QWORD *)(v24 + 408) = 0;
            }
            v27 = (void *)WpAllocMemory(v26);
            v28 = v27;
            if ( v27 )
            {
              memcpy_0(v27, v22, v26);
              *(_QWORD *)(v24 + 408) = v28;
              *(_DWORD *)(v24 + 400) = 1;
            }
          }
        }
        if ( v14 )
          SysFreeString(v14);
      }
      else
      {
        *(_DWORD *)(v9 + 400) = 0;
      }
    }
    else
    {
      PropertyDisplayInfo = -2147467263;
    }
    if ( Src )
      SysFreeString((BSTR)Src);
  }
LABEL_24:
  *a5 = 1;
  return LresFromHr(PropertyDisplayInfo);
}

```

## disassembly

```asm
0x18000df1c  mov     r11, rsp
0x18000df1f  mov     [r11+8], rbx
0x18000df23  mov     [r11+10h], rbp
0x18000df27  mov     [r11+20h], r9
0x18000df2b  mov     [r11+18h], r8w
0x18000df30  push    rsi
0x18000df31  push    rdi
0x18000df32  push    r12
0x18000df34  push    r14
0x18000df36  push    r15
0x18000df38  sub     rsp, 30h
0x18000df3c  mov     rax, [rcx+90h]
0x18000df43  xor     r12d, r12d
0x18000df46  mov     rdi, rcx
0x18000df49  mov     esi, r12d
0x18000df4c  mov     rcx, [rcx+58h]; hWnd
0x18000df50  mov     rdx, [rax+228h]
0x18000df57  mov     rbx, [rdx+20h]
0x18000df5b  mov     [r11+20h], r12
0x18000df5f  mov     [r11+18h], r12d
0x18000df63  test    rcx, rcx
0x18000df66  jz      loc_18000E114
0x18000df6c  mov     rax, [rdi+0A0h]
0x18000df73  test    rax, rax
0x18000df76  jz      loc_18000E0FF
0x18000df7c  mov     rax, [rax+18h]
0x18000df80  cmp     [rax+8], r12d
0x18000df84  jbe     loc_18000E0FF
0x18000df8a  cmp     dword ptr [rax+8], 1
0x18000df8e  jz      short loc_18000DF9A
0x18000df90  mov     esi, 80004005h
0x18000df95  jmp     loc_18000E114
0x18000df9a  xor     r9d, r9d; lParam
0x18000df9d  xor     r8d, r8d; wParam
0x18000dfa0  mov     edx, 0F0h; Msg
0x18000dfa5  call    cs:__imp_SendMessageW
0x18000dfab  mov     rcx, [rdi+50h]; hWnd
0x18000dfaf  mov     edx, eax; bEnable
0x18000dfb1  mov     [rdi+7Ch], eax
0x18000dfb4  call    cs:__imp_EnableWindow
0x18000dfba  cmp     [rdi+7Ch], r12d
0x18000dfbe  jnz     short loc_18000DFCC
0x18000dfc0  mov     [rbx+190h], r12d
0x18000dfc7  jmp     loc_18000E104
0x18000dfcc  mov     dword ptr [rbx+190h], 1
0x18000dfd6  mov     rbp, r12
0x18000dfd9  mov     rax, [rdi+90h]
0x18000dfe0  mov     rcx, [rax+228h]
0x18000dfe7  mov     rax, [rcx+20h]
0x18000dfeb  cmp     [rax+190h], r12d
0x18000dff2  jz      short loc_18000E012
0x18000dff4  mov     rcx, [rax+198h]; psz
0x18000dffb  test    rcx, rcx
0x18000dffe  jz      short loc_18000E012
0x18000e000  call    cs:__imp_SysAllocString
0x18000e006  mov     rcx, rax; psz
0x18000e009  call    cs:__imp_SysAllocString
0x18000e00f  mov     rbp, rax
0x18000e012  mov     rcx, [rdi+0A0h]
0x18000e019  mov     rbx, [rcx+18h]
0x18000e01d  mov     rcx, rdi; this
0x18000e020  call    ?GetUpdatedIHVParams@CACConnectionPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACConnectionPage::GetUpdatedIHVParams(void)
0x18000e025  xor     r9d, r9d; unsigned int
0x18000e028  mov     r8, rax; struct _DOT11EXT_IHV_PARAMS *
0x18000e02b  mov     rdx, rbp; unsigned __int16 *
0x18000e02e  mov     rcx, rbx; this
0x18000e031  call    ?IHVExtHlpLoadPropertyDisplayInfo@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@K@Z; IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(ushort *,_DOT11EXT_IHV_PARAMS *,ulong)
0x18000e036  mov     esi, eax
0x18000e038  mov     rcx, rdi; this
0x18000e03b  mov     rax, [rdi+0A0h]
0x18000e042  mov     rbx, [rax+18h]
0x18000e046  call    ?GetUpdatedIHVParams@CACConnectionPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACConnectionPage::GetUpdatedIHVParams(void)
0x18000e04b  lea     rcx, [rsp+58h+arg_10]
0x18000e050  mov     [rsp+58h+var_30], r12d; unsigned int
0x18000e055  mov     [rsp+58h+var_38], rcx; int *
0x18000e05a  lea     r9, [rsp+58h+Src]; unsigned __int16 **
0x18000e05f  mov     rcx, rbx; this
0x18000e062  mov     r8, rax; struct _DOT11EXT_IHV_PARAMS *
0x18000e065  mov     rdx, rbp; unsigned __int16 *
0x18000e068  call    ?IHVExtHlpSetSelected@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@PEAPEAGPEAHK@Z; IHVExtHelper::IHVExtHlpSetSelected(ushort *,_DOT11EXT_IHV_PARAMS *,ushort * *,int *,ulong)
0x18000e06d  cmp     [rsp+58h+arg_10], r12d
0x18000e072  jz      short loc_18000E0EF
0x18000e074  mov     r14, [rsp+58h+Src]
0x18000e079  test    r14, r14
0x18000e07c  jz      short loc_18000E0EF
0x18000e07e  mov     rax, [rdi+90h]
0x18000e085  mov     rcx, [rax+228h]
0x18000e08c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e090  mov     rbx, [rcx+20h]
0x18000e094  inc     rax
0x18000e097  cmp     [r14+rax*2], r12w
0x18000e09c  jnz     short loc_18000E094
0x18000e09e  mov     rcx, [rbx+198h]
0x18000e0a5  lea     r15, ds:2[rax*2]
0x18000e0ad  test    rcx, rcx
0x18000e0b0  jz      short loc_18000E0BF
0x18000e0b2  call    cs:__imp_WpFreeMemory
0x18000e0b8  mov     [rbx+198h], r12
0x18000e0bf  mov     rcx, r15
0x18000e0c2  call    cs:__imp_WpAllocMemory
0x18000e0c8  mov     rdi, rax
0x18000e0cb  test    rax, rax
0x18000e0ce  jz      short loc_18000E0EF
0x18000e0d0  mov     r8, r15; Size
0x18000e0d3  mov     rdx, r14; Src
0x18000e0d6  mov     rcx, rax; void *
0x18000e0d9  call    memcpy_0
0x18000e0de  mov     [rbx+198h], rdi
0x18000e0e5  mov     dword ptr [rbx+190h], 1
0x18000e0ef  test    rbp, rbp
0x18000e0f2  jz      short loc_18000E104
0x18000e0f4  mov     rcx, rbp; bstrString
0x18000e0f7  call    cs:__imp_SysFreeString
0x18000e0fd  jmp     short loc_18000E104
0x18000e0ff  mov     esi, 80004001h
0x18000e104  mov     rcx, [rsp+58h+Src]; bstrString
0x18000e109  test    rcx, rcx
0x18000e10c  jz      short loc_18000E114
0x18000e10e  call    cs:__imp_SysFreeString
0x18000e114  mov     rax, [rsp+58h+arg_20]
0x18000e11c  mov     ecx, esi; int
0x18000e11e  mov     dword ptr [rax], 1
0x18000e124  mov     rbx, [rsp+58h+arg_0]
0x18000e129  mov     rbp, [rsp+58h+arg_8]
0x18000e12e  add     rsp, 30h
0x18000e132  pop     r15
0x18000e134  pop     r14
0x18000e136  pop     r12
0x18000e138  pop     rdi
0x18000e139  pop     rsi
0x18000e13a  jmp     ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
```
