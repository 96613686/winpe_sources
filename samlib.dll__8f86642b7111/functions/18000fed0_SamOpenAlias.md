# SamOpenAlias

- ea: `0x18000fed0`
- end: `0x180010162`
- name: `SamOpenAlias`
- size: `658`
- prototype: `__int64 __fastcall(struct _SAMP_CLIENT_INFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180008590`

## callees

- `0x180003220`
- `0x180003370`
- `0x180005e90`
- `0x18000807c`
- `0x18000baf8`
- `0x18000bfa8`
- `0x18000fed0`
- `0x180014a50`
- `0x180014ae0`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ff52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ff52`
- `RPCRT4!NdrClientCall3` at `0x18001003b`
- `RPCRT4!NdrClientCall3` at `0x18001003b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001007e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001007e`

## pseudocode

```c
__int64 __fastcall SamOpenAlias(struct _SAMP_CLIENT_INFO *a1, int a2, __int64 a3, struct _SAMP_CLIENT_INFO **a4)
{
  int v5; // esi
  unsigned __int16 *CallingProcessInfo; // rax
  unsigned __int16 *v9; // rdi
  const wchar_t *v10; // rcx
  PVOID v11; // rcx
  PVOID v13; // rcx
  unsigned int Pointer; // ebx
  CLIENT_CALL_RETURN v15; // rax
  struct _SAMP_CLIENT_INFO *v16; // r9
  struct _SAMP_CLIENT_INFO *v17; // r9
  __int64 v18; // [rsp+20h] [rbp-68h]
  __int64 v19; // [rsp+28h] [rbp-60h]
  struct _SAMP_CLIENT_INFO *v20; // [rsp+48h] [rbp-40h] BYREF
  void *v21; // [rsp+50h] [rbp-38h] BYREF
  __int64 v22; // [rsp+58h] [rbp-30h] BYREF
  CLIENT_CALL_RETURN v23; // [rsp+60h] [rbp-28h]

  v5 = a3;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v9 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v10 = L"<unknown>";
      if ( CallingProcessInfo )
        v10 = CallingProcessInfo;
      McTemplateU0pqqz_EventWriteTransfer(
        (_DWORD)v10,
        (unsigned int)SamOpenAliasEntry,
        (_DWORD)a1,
        a2,
        v5,
        (__int64)v10);
    }
    LocalFree(v9);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, a3, a1, a2, v5);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, &v21) )
  {
    Pointer = SampCreateNewHandle(a1, 0, &v20);
    if ( (Pointer & 0x80000000) == 0 )
    {
      *a4 = 0;
      v23.Simple = 0;
      LODWORD(v19) = v5;
      LODWORD(v18) = a2;
      v15.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x1Bu, 0, v21, v18, v19, &v22).Pointer;
      Pointer = (unsigned int)v15.Pointer;
      v23.Pointer = v15.Pointer;
      if ( SLODWORD(v15.Simple) < 0 )
      {
        SampFreeHandle(&v20);
        v16 = v20;
      }
      else
      {
        v16 = v20;
        *(_QWORD *)v20 = v22;
      }
      *a4 = v16;
      if ( Pointer == -1073610749 )
        Pointer = -1073741816;
      if ( (Pointer & 0x80000000) == 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v16);
        if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
          return Pointer;
        v17 = *a4;
        goto LABEL_34;
      }
      v13 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
      return Pointer;
    v17 = 0;
LABEL_34:
    McTemplateU0dp_EventWriteTransfer(v13, SamOpenAliasExit, Pointer, v17);
    return Pointer;
  }
  v11 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dp_EventWriteTransfer(v11, SamOpenAliasExit, 3221225480LL, 0);
  return 3221225480LL;
}

```

## disassembly

```asm
0x18000fed0  mov     rax, rsp
0x18000fed3  mov     [rax+8], rbx
0x18000fed7  mov     [rax+10h], rsi
0x18000fedb  mov     [rax+20h], r9
0x18000fedf  push    rdi
0x18000fee0  push    r12
0x18000fee2  push    r13
0x18000fee4  sub     rsp, 70h
0x18000fee8  mov     r12, r9
0x18000feeb  mov     esi, r8d
0x18000feee  mov     r13d, edx
0x18000fef1  mov     rbx, rcx
0x18000fef4  mov     qword ptr [rax-40h], 0
0x18000fefc  mov     qword ptr [rax-38h], 0
0x18000ff04  mov     qword ptr [rax-30h], 0
0x18000ff0c  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000ff13  jz      short loc_18000FF58
0x18000ff15  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000ff1a  mov     rdi, rax
0x18000ff1d  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000ff24  jz      short loc_18000FF4F
0x18000ff26  lea     rcx, aUnknown; "<unknown>"
0x18000ff2d  test    rax, rax
0x18000ff30  cmovnz  rcx, rax
0x18000ff34  mov     [rsp+88h+var_60], rcx
0x18000ff39  mov     dword ptr [rsp+88h+var_68], esi
0x18000ff3d  mov     r9d, r13d
0x18000ff40  mov     r8, rbx
0x18000ff43  lea     rdx, SamOpenAliasEntry
0x18000ff4a  call    McTemplateU0pqqz_EventWriteTransfer
0x18000ff4f  mov     rcx, rdi; hMem
0x18000ff52  call    cs:__imp_LocalFree
0x18000ff58  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff5f  mov     dil, 2
0x18000ff62  test    [rcx+1Ch], dil
0x18000ff66  jz      short loc_18000FF88
0x18000ff68  cmp     byte ptr [rcx+19h], 4
0x18000ff6c  jb      short loc_18000FF88
0x18000ff6e  mov     edx, 0B2h
0x18000ff73  mov     dword ptr [rsp+88h+var_60], esi
0x18000ff77  mov     dword ptr [rsp+88h+var_68], r13d
0x18000ff7c  mov     r9, rbx
0x18000ff7f  mov     rcx, [rcx+10h]
0x18000ff83  call    WPP_SF_qDD
0x18000ff88  lea     rdx, [rsp+88h+var_38]; void **
0x18000ff8d  mov     rcx, rbx; void *
0x18000ff90  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000ff95  test    al, al
0x18000ff97  jnz     short loc_18000FFEB
0x18000ff99  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffa0  test    [rcx+1Ch], dil
0x18000ffa4  jz      short loc_18000FFC4
0x18000ffa6  cmp     [rcx+19h], dil
0x18000ffaa  jb      short loc_18000FFC4
0x18000ffac  mov     edx, 0B3h
0x18000ffb1  mov     r9, rbx
0x18000ffb4  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000ffbb  mov     rcx, [rcx+10h]
0x18000ffbf  call    WPP_SF_q
0x18000ffc4  mov     esi, 0C0000008h
0x18000ffc9  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000ffd0  jz      short loc_18000FFE4
0x18000ffd2  xor     r9d, r9d
0x18000ffd5  mov     r8d, esi
0x18000ffd8  lea     rdx, SamOpenAliasExit
0x18000ffdf  call    McTemplateU0dp_EventWriteTransfer
0x18000ffe4  mov     eax, esi
0x18000ffe6  jmp     loc_18001014C
0x18000ffeb  lea     r8, [rsp+88h+var_40]; struct _SAMP_CLIENT_INFO **
0x18000fff0  xor     edx, edx; void *
0x18000fff2  mov     rcx, rbx; struct _SAMP_CLIENT_INFO *
0x18000fff5  call    ?SampCreateNewHandle@@YAJPEAU_SAMP_CLIENT_INFO@@PEAXPEAPEAU1@@Z; SampCreateNewHandle(_SAMP_CLIENT_INFO *,void *,_SAMP_CLIENT_INFO * *)
0x18000fffa  mov     ebx, eax
0x18000fffc  test    eax, eax
0x18000fffe  js      loc_18001012F
0x180010004  mov     qword ptr [r12], 0
0x18001000c  mov     [rsp+88h+var_28], 0
0x180010015  lea     rax, [rsp+88h+var_30]
0x18001001a  mov     [rsp+88h+var_58], rax
0x18001001f  mov     dword ptr [rsp+88h+var_60], esi
0x180010023  mov     dword ptr [rsp+88h+var_68], r13d
0x180010028  mov     r9, [rsp+88h+var_38]
0x18001002d  xor     r8d, r8d; pReturnValue
0x180010030  lea     edx, [r8+1Bh]; nProcNum
0x180010034  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001003b  call    cs:__imp_NdrClientCall3
0x180010041  mov     rbx, rax
0x180010044  mov     [rsp+88h+var_28], rax
0x180010049  mov     [rsp+88h+var_48], eax
0x18001004d  jmp     short loc_180010095
0x18001004f  mov     ebx, eax
0x180010051  mov     rcx, cs:WPP_GLOBAL_Control
0x180010058  test    byte ptr [rcx+1Ch], 2
0x18001005c  jz      short loc_18001007C
0x18001005e  cmp     byte ptr [rcx+19h], 3
0x180010062  jb      short loc_18001007C
0x180010064  mov     r9d, eax
0x180010067  mov     edx, 0B4h
0x18001006c  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180010073  mov     rcx, [rcx+10h]
0x180010077  call    WPP_SF_D
0x18001007c  mov     ecx, ebx; Status
0x18001007e  call    cs:__imp_I_RpcMapWin32Status
0x180010084  mov     ebx, eax
0x180010086  mov     [rsp+88h+var_48], eax
0x18001008a  mov     dil, 2
0x18001008d  mov     r12, [rsp+88h+arg_18]
0x180010095  test    ebx, ebx
0x180010097  js      short loc_1800100A8
0x180010099  mov     rax, [rsp+88h+var_30]
0x18001009e  mov     r9, [rsp+88h+var_40]
0x1800100a3  mov     [r9], rax
0x1800100a6  jmp     short loc_1800100B7
0x1800100a8  lea     rcx, [rsp+88h+var_40]; struct _SAMP_CLIENT_INFO **
0x1800100ad  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x1800100b2  mov     r9, [rsp+88h+var_40]
0x1800100b7  mov     [r12], r9
0x1800100bb  mov     esi, 0C0000008h
0x1800100c0  cmp     ebx, 0C0020003h
0x1800100c6  cmovz   ebx, esi
0x1800100c9  test    ebx, ebx
0x1800100cb  js      short loc_180010104
0x1800100cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100d4  test    [rcx+1Ch], dil
0x1800100d8  jz      short loc_1800100F5
0x1800100da  cmp     byte ptr [rcx+19h], 4
0x1800100de  jb      short loc_1800100F5
0x1800100e0  mov     edx, 0B5h
0x1800100e5  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800100ec  mov     rcx, [rcx+10h]
0x1800100f0  call    WPP_SF_q
0x1800100f5  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800100fc  jz      short loc_18001014A
0x1800100fe  mov     r9, [r12]
0x180010102  jmp     short loc_18001013B
0x180010104  mov     rcx, cs:WPP_GLOBAL_Control
0x18001010b  test    [rcx+1Ch], dil
0x18001010f  jz      short loc_18001012F
0x180010111  cmp     [rcx+19h], dil
0x180010115  jb      short loc_18001012F
0x180010117  mov     edx, 0B6h
0x18001011c  mov     r9d, ebx
0x18001011f  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180010126  mov     rcx, [rcx+10h]
0x18001012a  call    WPP_SF_D
0x18001012f  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180010136  jz      short loc_18001014A
0x180010138  xor     r9d, r9d
0x18001013b  mov     r8d, ebx
0x18001013e  lea     rdx, SamOpenAliasExit
0x180010145  call    McTemplateU0dp_EventWriteTransfer
0x18001014a  mov     eax, ebx
0x18001014c  lea     r11, [rsp+88h+var_18]
0x180010151  mov     rbx, [r11+20h]
0x180010155  mov     rsi, [r11+28h]
0x180010159  mov     rsp, r11
0x18001015c  pop     r13
0x18001015e  pop     r12
0x180010160  pop     rdi
0x180010161  retn
0x180017cf0  push    rbp
0x180017cf2  sub     rsp, 40h
0x180017cf6  mov     rbp, rdx
0x180017cf9  mov     rcx, [rcx]
0x180017cfc  mov     ecx, [rcx]; ExceptionCode
0x180017cfe  call    cs:__imp_I_RpcExceptionFilter
0x180017d04  nop
0x180017d05  add     rsp, 40h
0x180017d09  pop     rbp
0x180017d0a  retn
```
