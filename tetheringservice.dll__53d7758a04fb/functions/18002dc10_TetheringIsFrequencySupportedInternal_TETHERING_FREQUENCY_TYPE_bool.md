# TetheringIsFrequencySupportedInternal(_TETHERING_FREQUENCY_TYPE,bool *)

- ea: `0x18002dc10`
- end: `0x18002ddee`
- name: `?TetheringIsFrequencySupportedInternal@@YAJW4_TETHERING_FREQUENCY_TYPE@@PEA_N@Z`
- size: `478`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800110d4`
- `0x18002d66c`

## callees

- `0x180008934`
- `0x18000bf4c`
- `0x18000bf74`
- `0x180029c8c`
- `0x18002dc10`
- `0x18002de4c`

## import_xrefs

- `wlanapi!WFDQueryPropertyInt` at `0x18002dcd4`
- `wlanapi!WFDQueryPropertyInt` at `0x18002dcd4`
- `wlanapi!WFDOpenHandleInt` at `0x18002dca2`
- `wlanapi!WFDOpenHandleInt` at `0x18002dca2`
- `wlanapi!WFDCloseHandleInt` at `0x18002dda8`
- `wlanapi!WFDCloseHandleInt` at `0x18002dda8`
- `wlanapi!WFDFreeMemoryInt` at `0x18002dd91`
- `wlanapi!WFDFreeMemoryInt` at `0x18002dd91`

## pseudocode

```c
__int64 __fastcall TetheringIsFrequencySupportedInternal(int a1, char *a2)
{
  unsigned int v4; // ebx
  char v5; // si
  int v6; // eax
  __int64 v7; // r8
  int v8; // eax
  int v9; // edi
  int v10; // edi
  int v11; // edi
  bool v12; // zf
  TetheringServiceTelemetry *v13; // rax
  __int64 v14; // rdx
  __int64 v16; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v18; // [rsp+78h] [rbp+38h] BYREF
  int v19; // [rsp+80h] [rbp+40h] BYREF
  __int64 v20; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids);
  }
  v18 = 0;
  v16 = 0;
  v20 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (int)"onecoreuap\\net\\tethering\\settings\\tetheringenabled.cpp",
      (const char *)0x80070057LL);
    return v4;
  }
  v5 = 1;
  *a2 = 0;
  v6 = WFDOpenHandleInt(1, &v18, &v16);
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_31;
    }
    v14 = 24;
LABEL_30:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v4);
    goto LABEL_31;
  }
  v19 = 0;
  v8 = WFDQueryPropertyInt(v16, 1, &v19, &v20);
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_31;
    }
    v14 = 23;
    goto LABEL_30;
  }
  v9 = a1 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
    {
      v12 = *(_DWORD *)(v20 + 92) == 0;
LABEL_19:
      if ( v12 && !IsMockFeatureSupported(L"Mock6GHzSupport") )
        v5 = 0;
      goto LABEL_22;
    }
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
      {
        v4 = -2147467263;
        goto LABEL_31;
      }
      v12 = *(_DWORD *)(v20 + 104) == 0;
      goto LABEL_19;
    }
  }
LABEL_22:
  *a2 = v5;
LABEL_31:
  if ( v20 )
  {
    WFDFreeMemoryInt(v20);
    v20 = 0;
  }
  if ( v16 )
  {
    WFDCloseHandleInt(v16);
    v16 = 0;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v7, v4, (unsigned __int8)*a2);
  }
  return v4;
}

```

## disassembly

```asm
0x18002dc10  push    rbp
0x18002dc12  push    rbx
0x18002dc13  push    rsi
0x18002dc14  push    rdi
0x18002dc15  push    r14
0x18002dc17  mov     rbp, rsp
0x18002dc1a  sub     rsp, 40h
0x18002dc1e  mov     r14, rdx
0x18002dc21  mov     edi, ecx
0x18002dc23  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc2a  lea     rax, WPP_GLOBAL_Control
0x18002dc31  cmp     rcx, rax
0x18002dc34  jz      short loc_18002DC51
0x18002dc36  test    byte ptr [rcx+1Ch], 8
0x18002dc3a  jz      short loc_18002DC51
0x18002dc3c  mov     rcx, [rcx+10h]
0x18002dc40  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002dc47  mov     edx, 16h
0x18002dc4c  call    WPP_SF_
0x18002dc51  mov     [rbp+arg_8], 0
0x18002dc58  mov     [rbp+var_10], 0
0x18002dc60  mov     [rbp+arg_18], 0
0x18002dc68  test    r14, r14
0x18002dc6b  jnz     short loc_18002DC8F
0x18002dc6d  mov     rcx, [rbp+28h]; this
0x18002dc71  lea     r8, aOnecoreuapNetT; "onecoreuap\\net\\tethering\\settings\\t"...
0x18002dc78  mov     ebx, 80070057h
0x18002dc7d  mov     edx, 0BBh; void *
0x18002dc82  mov     r9d, ebx; char *
0x18002dc85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc8a  jmp     loc_18002DDE1
0x18002dc8f  mov     esi, 1
0x18002dc94  mov     byte ptr [r14], 0
0x18002dc98  mov     ecx, esi
0x18002dc9a  lea     r8, [rbp+var_10]
0x18002dc9e  lea     rdx, [rbp+arg_8]
0x18002dca2  call    cs:__imp_WFDOpenHandleInt
0x18002dca8  mov     ebx, eax
0x18002dcaa  test    eax, eax
0x18002dcac  jle     short loc_18002DCB7
0x18002dcae  movzx   ebx, ax
0x18002dcb1  or      ebx, 80070000h
0x18002dcb7  test    ebx, ebx
0x18002dcb9  js      loc_18002DD57
0x18002dcbf  mov     rcx, [rbp+var_10]
0x18002dcc3  lea     r9, [rbp+arg_18]
0x18002dcc7  lea     r8, [rbp+arg_10]
0x18002dccb  mov     [rbp+arg_10], 0
0x18002dcd2  mov     edx, esi
0x18002dcd4  call    cs:__imp_WFDQueryPropertyInt
0x18002dcda  mov     ebx, eax
0x18002dcdc  test    eax, eax
0x18002dcde  jle     short loc_18002DCE9
0x18002dce0  movzx   ebx, ax
0x18002dce3  or      ebx, 80070000h
0x18002dce9  test    ebx, ebx
0x18002dceb  js      short loc_18002DD37
0x18002dced  sub     edi, esi
0x18002dcef  jz      short loc_18002DD28
0x18002dcf1  sub     edi, esi
0x18002dcf3  jz      short loc_18002DD2D
0x18002dcf5  sub     edi, esi
0x18002dcf7  jz      short loc_18002DD28
0x18002dcf9  cmp     edi, esi
0x18002dcfb  jz      short loc_18002DD0B
0x18002dcfd  mov     ebx, 80004001h
0x18002dd02  lea     rdi, WPP_GLOBAL_Control
0x18002dd09  jmp     short loc_18002DD88
0x18002dd0b  mov     rax, [rbp+arg_18]
0x18002dd0f  cmp     dword ptr [rax+68h], 0
0x18002dd13  jnz     short loc_18002DD28
0x18002dd15  lea     rcx, aMock6ghzsuppor; "Mock6GHzSupport"
0x18002dd1c  call    ?IsMockFeatureSupported@@YA_NPEBG@Z; IsMockFeatureSupported(ushort const *)
0x18002dd21  test    al, al
0x18002dd23  jnz     short loc_18002DD28
0x18002dd25  xor     sil, sil
0x18002dd28  mov     [r14], sil
0x18002dd2b  jmp     short loc_18002DD02
0x18002dd2d  mov     rax, [rbp+arg_18]
0x18002dd31  cmp     dword ptr [rax+5Ch], 0
0x18002dd35  jmp     short loc_18002DD13
0x18002dd37  mov     rax, cs:WPP_GLOBAL_Control
0x18002dd3e  lea     rdi, WPP_GLOBAL_Control
0x18002dd45  cmp     rax, rdi
0x18002dd48  jz      short loc_18002DD88
0x18002dd4a  test    [rax+1Ch], sil
0x18002dd4e  jz      short loc_18002DD88
0x18002dd50  mov     edx, 17h
0x18002dd55  jmp     short loc_18002DD75
0x18002dd57  mov     rax, cs:WPP_GLOBAL_Control
0x18002dd5e  lea     rdi, WPP_GLOBAL_Control
0x18002dd65  cmp     rax, rdi
0x18002dd68  jz      short loc_18002DD88
0x18002dd6a  test    [rax+1Ch], sil
0x18002dd6e  jz      short loc_18002DD88
0x18002dd70  mov     edx, 18h
0x18002dd75  mov     rcx, [rax+10h]
0x18002dd79  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002dd80  mov     r9d, ebx
0x18002dd83  call    WPP_SF_d
0x18002dd88  mov     rcx, [rbp+arg_18]
0x18002dd8c  test    rcx, rcx
0x18002dd8f  jz      short loc_18002DD9F
0x18002dd91  call    cs:__imp_WFDFreeMemoryInt
0x18002dd97  mov     [rbp+arg_18], 0
0x18002dd9f  mov     rcx, [rbp+var_10]
0x18002dda3  test    rcx, rcx
0x18002dda6  jz      short loc_18002DDB6
0x18002dda8  call    cs:__imp_WFDCloseHandleInt
0x18002ddae  mov     [rbp+var_10], 0
0x18002ddb6  mov     rax, cs:WPP_GLOBAL_Control
0x18002ddbd  cmp     rax, rdi
0x18002ddc0  jz      short loc_18002DDE1
0x18002ddc2  test    byte ptr [rax+1Ch], 8
0x18002ddc6  jz      short loc_18002DDE1
0x18002ddc8  movzx   ecx, byte ptr [r14]
0x18002ddcc  mov     edx, 19h
0x18002ddd1  mov     [rsp+40h+var_20], ecx
0x18002ddd5  mov     r9d, ebx
0x18002ddd8  mov     rcx, [rax+10h]
0x18002dddc  call    WPP_SF_dl
0x18002dde1  mov     eax, ebx
0x18002dde3  add     rsp, 40h
0x18002dde7  pop     r14
0x18002dde9  pop     rdi
0x18002ddea  pop     rsi
0x18002ddeb  pop     rbx
0x18002ddec  pop     rbp
0x18002dded  retn
```
