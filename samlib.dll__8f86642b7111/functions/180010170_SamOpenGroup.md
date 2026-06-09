# SamOpenGroup

- ea: `0x180010170`
- end: `0x180010402`
- name: `SamOpenGroup`
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
- `0x180010170`
- `0x180014a50`
- `0x180014ae0`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800101f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800101f2`
- `RPCRT4!NdrClientCall3` at `0x1800102db`
- `RPCRT4!NdrClientCall3` at `0x1800102db`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001031e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001031e`

## pseudocode

```c
__int64 __fastcall SamOpenGroup(struct _SAMP_CLIENT_INFO *a1, int a2, __int64 a3, struct _SAMP_CLIENT_INFO **a4)
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
        (unsigned int)SamOpenGroupEntry,
        (_DWORD)a1,
        a2,
        v5,
        (__int64)v10);
    }
    LocalFree(v9);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, a3, a1, a2, v5);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, &v21) )
  {
    Pointer = SampCreateNewHandle(a1, 0, &v20);
    if ( (Pointer & 0x80000000) == 0 )
    {
      *a4 = 0;
      v23.Simple = 0;
      LODWORD(v19) = v5;
      LODWORD(v18) = a2;
      v15.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x13u, 0, v21, v18, v19, &v22).Pointer;
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
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v16);
        if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
          return Pointer;
        v17 = *a4;
        goto LABEL_34;
      }
      v13 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
      return Pointer;
    v17 = 0;
LABEL_34:
    McTemplateU0dp_EventWriteTransfer(v13, SamOpenGroupExit, Pointer, v17);
    return Pointer;
  }
  v11 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dp_EventWriteTransfer(v11, SamOpenGroupExit, 3221225480LL, 0);
  return 3221225480LL;
}

```

## disassembly

```asm
0x180010170  mov     rax, rsp
0x180010173  mov     [rax+8], rbx
0x180010177  mov     [rax+10h], rsi
0x18001017b  mov     [rax+20h], r9
0x18001017f  push    rdi
0x180010180  push    r12
0x180010182  push    r13
0x180010184  sub     rsp, 70h
0x180010188  mov     r12, r9
0x18001018b  mov     esi, r8d
0x18001018e  mov     r13d, edx
0x180010191  mov     rbx, rcx
0x180010194  mov     qword ptr [rax-40h], 0
0x18001019c  mov     qword ptr [rax-38h], 0
0x1800101a4  mov     qword ptr [rax-30h], 0
0x1800101ac  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800101b3  jz      short loc_1800101F8
0x1800101b5  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x1800101ba  mov     rdi, rax
0x1800101bd  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800101c4  jz      short loc_1800101EF
0x1800101c6  lea     rcx, aUnknown; "<unknown>"
0x1800101cd  test    rax, rax
0x1800101d0  cmovnz  rcx, rax
0x1800101d4  mov     [rsp+88h+var_60], rcx
0x1800101d9  mov     dword ptr [rsp+88h+var_68], esi
0x1800101dd  mov     r9d, r13d
0x1800101e0  mov     r8, rbx
0x1800101e3  lea     rdx, SamOpenGroupEntry
0x1800101ea  call    McTemplateU0pqqz_EventWriteTransfer
0x1800101ef  mov     rcx, rdi; hMem
0x1800101f2  call    cs:__imp_LocalFree
0x1800101f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101ff  mov     dil, 2
0x180010202  test    [rcx+1Ch], dil
0x180010206  jz      short loc_180010228
0x180010208  cmp     byte ptr [rcx+19h], 4
0x18001020c  jb      short loc_180010228
0x18001020e  mov     edx, 88h
0x180010213  mov     dword ptr [rsp+88h+var_60], esi
0x180010217  mov     dword ptr [rsp+88h+var_68], r13d
0x18001021c  mov     r9, rbx
0x18001021f  mov     rcx, [rcx+10h]
0x180010223  call    WPP_SF_qDD
0x180010228  lea     rdx, [rsp+88h+var_38]; void **
0x18001022d  mov     rcx, rbx; void *
0x180010230  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x180010235  test    al, al
0x180010237  jnz     short loc_18001028B
0x180010239  mov     rcx, cs:WPP_GLOBAL_Control
0x180010240  test    [rcx+1Ch], dil
0x180010244  jz      short loc_180010264
0x180010246  cmp     [rcx+19h], dil
0x18001024a  jb      short loc_180010264
0x18001024c  mov     edx, 89h
0x180010251  mov     r9, rbx
0x180010254  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18001025b  mov     rcx, [rcx+10h]
0x18001025f  call    WPP_SF_q
0x180010264  mov     esi, 0C0000008h
0x180010269  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180010270  jz      short loc_180010284
0x180010272  xor     r9d, r9d
0x180010275  mov     r8d, esi
0x180010278  lea     rdx, SamOpenGroupExit
0x18001027f  call    McTemplateU0dp_EventWriteTransfer
0x180010284  mov     eax, esi
0x180010286  jmp     loc_1800103EC
0x18001028b  lea     r8, [rsp+88h+var_40]; struct _SAMP_CLIENT_INFO **
0x180010290  xor     edx, edx; void *
0x180010292  mov     rcx, rbx; struct _SAMP_CLIENT_INFO *
0x180010295  call    ?SampCreateNewHandle@@YAJPEAU_SAMP_CLIENT_INFO@@PEAXPEAPEAU1@@Z; SampCreateNewHandle(_SAMP_CLIENT_INFO *,void *,_SAMP_CLIENT_INFO * *)
0x18001029a  mov     ebx, eax
0x18001029c  test    eax, eax
0x18001029e  js      loc_1800103CF
0x1800102a4  mov     qword ptr [r12], 0
0x1800102ac  mov     [rsp+88h+var_28], 0
0x1800102b5  lea     rax, [rsp+88h+var_30]
0x1800102ba  mov     [rsp+88h+var_58], rax
0x1800102bf  mov     dword ptr [rsp+88h+var_60], esi
0x1800102c3  mov     dword ptr [rsp+88h+var_68], r13d
0x1800102c8  mov     r9, [rsp+88h+var_38]
0x1800102cd  xor     r8d, r8d; pReturnValue
0x1800102d0  lea     edx, [r8+13h]; nProcNum
0x1800102d4  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800102db  call    cs:__imp_NdrClientCall3
0x1800102e1  mov     rbx, rax
0x1800102e4  mov     [rsp+88h+var_28], rax
0x1800102e9  mov     [rsp+88h+var_48], eax
0x1800102ed  jmp     short loc_180010335
0x1800102ef  mov     ebx, eax
0x1800102f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102f8  test    byte ptr [rcx+1Ch], 2
0x1800102fc  jz      short loc_18001031C
0x1800102fe  cmp     byte ptr [rcx+19h], 3
0x180010302  jb      short loc_18001031C
0x180010304  mov     r9d, eax
0x180010307  mov     edx, 8Ah
0x18001030c  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180010313  mov     rcx, [rcx+10h]
0x180010317  call    WPP_SF_D
0x18001031c  mov     ecx, ebx; Status
0x18001031e  call    cs:__imp_I_RpcMapWin32Status
0x180010324  mov     ebx, eax
0x180010326  mov     [rsp+88h+var_48], eax
0x18001032a  mov     dil, 2
0x18001032d  mov     r12, [rsp+88h+arg_18]
0x180010335  test    ebx, ebx
0x180010337  js      short loc_180010348
0x180010339  mov     rax, [rsp+88h+var_30]
0x18001033e  mov     r9, [rsp+88h+var_40]
0x180010343  mov     [r9], rax
0x180010346  jmp     short loc_180010357
0x180010348  lea     rcx, [rsp+88h+var_40]; struct _SAMP_CLIENT_INFO **
0x18001034d  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x180010352  mov     r9, [rsp+88h+var_40]
0x180010357  mov     [r12], r9
0x18001035b  mov     esi, 0C0000008h
0x180010360  cmp     ebx, 0C0020003h
0x180010366  cmovz   ebx, esi
0x180010369  test    ebx, ebx
0x18001036b  js      short loc_1800103A4
0x18001036d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010374  test    [rcx+1Ch], dil
0x180010378  jz      short loc_180010395
0x18001037a  cmp     byte ptr [rcx+19h], 4
0x18001037e  jb      short loc_180010395
0x180010380  mov     edx, 8Bh
0x180010385  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18001038c  mov     rcx, [rcx+10h]
0x180010390  call    WPP_SF_q
0x180010395  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18001039c  jz      short loc_1800103EA
0x18001039e  mov     r9, [r12]
0x1800103a2  jmp     short loc_1800103DB
0x1800103a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103ab  test    [rcx+1Ch], dil
0x1800103af  jz      short loc_1800103CF
0x1800103b1  cmp     [rcx+19h], dil
0x1800103b5  jb      short loc_1800103CF
0x1800103b7  mov     edx, 8Ch
0x1800103bc  mov     r9d, ebx
0x1800103bf  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800103c6  mov     rcx, [rcx+10h]
0x1800103ca  call    WPP_SF_D
0x1800103cf  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800103d6  jz      short loc_1800103EA
0x1800103d8  xor     r9d, r9d
0x1800103db  mov     r8d, ebx
0x1800103de  lea     rdx, SamOpenGroupExit
0x1800103e5  call    McTemplateU0dp_EventWriteTransfer
0x1800103ea  mov     eax, ebx
0x1800103ec  lea     r11, [rsp+88h+var_18]
0x1800103f1  mov     rbx, [r11+20h]
0x1800103f5  mov     rsi, [r11+28h]
0x1800103f9  mov     rsp, r11
0x1800103fc  pop     r13
0x1800103fe  pop     r12
0x180010400  pop     rdi
0x180010401  retn
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
