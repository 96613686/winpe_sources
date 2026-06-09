# TetheringIsAuthSupportedInternal(_TETHERING_AUTH_TYPE,bool *)

- ea: `0x18002d66c`
- end: `0x18002d85f`
- name: `?TetheringIsAuthSupportedInternal@@YAJW4_TETHERING_AUTH_TYPE@@PEA_N@Z`
- size: `499`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800110d4`
- `0x18001a3ec`
- `0x18002a640`
- `0x18002b2dc`

## callees

- `0x180008934`
- `0x18000bf4c`
- `0x18000bf74`
- `0x180029c8c`
- `0x18002d66c`
- `0x18002dc10`
- `0x18002de4c`

## import_xrefs

- `wlanapi!WFDQueryPropertyInt` at `0x18002d735`
- `wlanapi!WFDQueryPropertyInt` at `0x18002d735`
- `wlanapi!WFDOpenHandleInt` at `0x18002d703`
- `wlanapi!WFDOpenHandleInt` at `0x18002d703`
- `wlanapi!WFDCloseHandleInt` at `0x18002d813`
- `wlanapi!WFDCloseHandleInt` at `0x18002d813`
- `wlanapi!WFDFreeMemoryInt` at `0x18002d7f5`
- `wlanapi!WFDFreeMemoryInt` at `0x18002d7f5`

## pseudocode

```c
__int64 __fastcall TetheringIsAuthSupportedInternal(int a1, char *a2)
{
  unsigned int v4; // ebx
  char v5; // si
  int v6; // eax
  __int64 v7; // r8
  int v8; // eax
  int v9; // edi
  TetheringServiceTelemetry *v10; // rax
  __int64 v11; // rdx
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  char v16; // [rsp+78h] [rbp+38h] BYREF
  int v17; // [rsp+80h] [rbp+40h] BYREF
  int v18; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids);
  }
  v17 = 0;
  v14 = 0;
  v13 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x102,
      (int)"onecoreuap\\net\\tethering\\settings\\tetheringenabled.cpp",
      (const char *)0x80070057LL);
    return v4;
  }
  v5 = 1;
  *a2 = 0;
  v6 = WFDOpenHandleInt(1, &v17, &v14);
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_29;
    }
    v11 = 28;
LABEL_27:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v4);
    goto LABEL_28;
  }
  v18 = 0;
  v8 = WFDQueryPropertyInt(v14, 1, &v18, &v13);
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_29;
    }
    v11 = 27;
    goto LABEL_27;
  }
  v9 = a1 - 1;
  if ( !v9 )
  {
LABEL_20:
    *a2 = v5;
    goto LABEL_28;
  }
  if ( (unsigned int)(v9 - 1) < 2 )
  {
    v16 = 0;
    if ( !*(_DWORD *)(v13 + 108)
      && !IsMockFeatureSupported(L"MockWPA3Support")
      && ((int)TetheringIsFrequencySupportedInternal(4, &v16) < 0 || !v16) )
    {
      v5 = 0;
    }
    goto LABEL_20;
  }
  v4 = -2147467263;
LABEL_28:
  v10 = WPP_GLOBAL_Control;
LABEL_29:
  if ( v13 )
  {
    WFDFreeMemoryInt(v13);
    v10 = WPP_GLOBAL_Control;
    v13 = 0;
  }
  if ( v14 )
  {
    WFDCloseHandleInt(v14);
    v10 = WPP_GLOBAL_Control;
    v14 = 0;
  }
  if ( v10 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    WPP_SF_dl(*((_QWORD *)v10 + 2), 29, v7, v4, (unsigned __int8)*a2);
  return v4;
}

```

## disassembly

```asm
0x18002d66c  mov     [rsp-28h+arg_0], rbx
0x18002d671  push    rbp
0x18002d672  push    rsi
0x18002d673  push    rdi
0x18002d674  push    r13
0x18002d676  push    r14
0x18002d678  mov     rbp, rsp
0x18002d67b  sub     rsp, 40h
0x18002d67f  mov     r14, rdx
0x18002d682  mov     edi, ecx
0x18002d684  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d68b  lea     r13, WPP_GLOBAL_Control
0x18002d692  cmp     rcx, r13
0x18002d695  jz      short loc_18002D6B2
0x18002d697  test    byte ptr [rcx+1Ch], 8
0x18002d69b  jz      short loc_18002D6B2
0x18002d69d  mov     rcx, [rcx+10h]
0x18002d6a1  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002d6a8  mov     edx, 1Ah
0x18002d6ad  call    WPP_SF_
0x18002d6b2  mov     [rbp+arg_10], 0
0x18002d6b9  mov     [rbp+var_8], 0
0x18002d6c1  mov     [rbp+var_10], 0
0x18002d6c9  test    r14, r14
0x18002d6cc  jnz     short loc_18002D6F0
0x18002d6ce  mov     rcx, [rbp+28h]; this
0x18002d6d2  lea     r8, aOnecoreuapNetT; "onecoreuap\\net\\tethering\\settings\\t"...
0x18002d6d9  mov     ebx, 80070057h
0x18002d6de  mov     edx, 102h; void *
0x18002d6e3  mov     r9d, ebx; char *
0x18002d6e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d6eb  jmp     loc_18002D84C
0x18002d6f0  mov     esi, 1
0x18002d6f5  mov     byte ptr [r14], 0
0x18002d6f9  mov     ecx, esi
0x18002d6fb  lea     r8, [rbp+var_8]
0x18002d6ff  lea     rdx, [rbp+arg_10]
0x18002d703  call    cs:__imp_WFDOpenHandleInt
0x18002d709  mov     ebx, eax
0x18002d70b  test    eax, eax
0x18002d70d  jle     short loc_18002D718
0x18002d70f  movzx   ebx, ax
0x18002d712  or      ebx, 80070000h
0x18002d718  test    ebx, ebx
0x18002d71a  js      loc_18002D7BB
0x18002d720  mov     rcx, [rbp+var_8]
0x18002d724  lea     r9, [rbp+var_10]
0x18002d728  lea     r8, [rbp+arg_18]
0x18002d72c  mov     [rbp+arg_18], 0
0x18002d733  mov     edx, esi
0x18002d735  call    cs:__imp_WFDQueryPropertyInt
0x18002d73b  mov     ebx, eax
0x18002d73d  test    eax, eax
0x18002d73f  jle     short loc_18002D74A
0x18002d741  movzx   ebx, ax
0x18002d744  or      ebx, 80070000h
0x18002d74a  test    ebx, ebx
0x18002d74c  js      short loc_18002D7A2
0x18002d74e  sub     edi, esi
0x18002d750  jz      short loc_18002D79D
0x18002d752  sub     edi, esi
0x18002d754  jz      short loc_18002D764
0x18002d756  cmp     edi, esi
0x18002d758  jz      short loc_18002D764
0x18002d75a  mov     ebx, 80004001h
0x18002d75f  jmp     loc_18002D7E5
0x18002d764  mov     rax, [rbp+var_10]
0x18002d768  mov     [rbp+arg_8], 0
0x18002d76c  cmp     dword ptr [rax+6Ch], 0
0x18002d770  jnz     short loc_18002D79D
0x18002d772  lea     rcx, aMockwpa3suppor; "MockWPA3Support"
0x18002d779  call    ?IsMockFeatureSupported@@YA_NPEBG@Z; IsMockFeatureSupported(ushort const *)
0x18002d77e  test    al, al
0x18002d780  jnz     short loc_18002D79D
0x18002d782  lea     rdx, [rbp+arg_8]
0x18002d786  mov     ecx, 4
0x18002d78b  call    ?TetheringIsFrequencySupportedInternal@@YAJW4_TETHERING_FREQUENCY_TYPE@@PEA_N@Z; TetheringIsFrequencySupportedInternal(_TETHERING_FREQUENCY_TYPE,bool *)
0x18002d790  test    eax, eax
0x18002d792  js      short loc_18002D79A
0x18002d794  cmp     [rbp+arg_8], 0
0x18002d798  jnz     short loc_18002D79D
0x18002d79a  xor     sil, sil
0x18002d79d  mov     [r14], sil
0x18002d7a0  jmp     short loc_18002D7E5
0x18002d7a2  mov     rax, cs:WPP_GLOBAL_Control
0x18002d7a9  cmp     rax, r13
0x18002d7ac  jz      short loc_18002D7EC
0x18002d7ae  test    [rax+1Ch], sil
0x18002d7b2  jz      short loc_18002D7EC
0x18002d7b4  mov     edx, 1Bh
0x18002d7b9  jmp     short loc_18002D7D2
0x18002d7bb  mov     rax, cs:WPP_GLOBAL_Control
0x18002d7c2  cmp     rax, r13
0x18002d7c5  jz      short loc_18002D7EC
0x18002d7c7  test    [rax+1Ch], sil
0x18002d7cb  jz      short loc_18002D7EC
0x18002d7cd  mov     edx, 1Ch
0x18002d7d2  mov     rcx, [rax+10h]
0x18002d7d6  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002d7dd  mov     r9d, ebx
0x18002d7e0  call    WPP_SF_d
0x18002d7e5  mov     rax, cs:WPP_GLOBAL_Control
0x18002d7ec  mov     rcx, [rbp+var_10]
0x18002d7f0  test    rcx, rcx
0x18002d7f3  jz      short loc_18002D80A
0x18002d7f5  call    cs:__imp_WFDFreeMemoryInt
0x18002d7fb  mov     rax, cs:WPP_GLOBAL_Control
0x18002d802  mov     [rbp+var_10], 0
0x18002d80a  mov     rcx, [rbp+var_8]
0x18002d80e  test    rcx, rcx
0x18002d811  jz      short loc_18002D828
0x18002d813  call    cs:__imp_WFDCloseHandleInt
0x18002d819  mov     rax, cs:WPP_GLOBAL_Control
0x18002d820  mov     [rbp+var_8], 0
0x18002d828  cmp     rax, r13
0x18002d82b  jz      short loc_18002D84C
0x18002d82d  test    byte ptr [rax+1Ch], 8
0x18002d831  jz      short loc_18002D84C
0x18002d833  movzx   ecx, byte ptr [r14]
0x18002d837  mov     edx, 1Dh
0x18002d83c  mov     [rsp+40h+var_20], ecx
0x18002d840  mov     r9d, ebx
0x18002d843  mov     rcx, [rax+10h]
0x18002d847  call    WPP_SF_dl
0x18002d84c  mov     eax, ebx
0x18002d84e  mov     rbx, [rsp+40h+arg_0]
0x18002d853  add     rsp, 40h
0x18002d857  pop     r14
0x18002d859  pop     r13
0x18002d85b  pop     rdi
0x18002d85c  pop     rsi
0x18002d85d  pop     rbp
0x18002d85e  retn
```
