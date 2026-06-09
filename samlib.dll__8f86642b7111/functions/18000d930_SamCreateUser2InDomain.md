# SamCreateUser2InDomain

- ea: `0x18000d930`
- end: `0x18000ddd6`
- name: `SamCreateUser2InDomain`
- size: `1190`
- prototype: `__int64 __usercall@<rax>(struct _SAMP_CLIENT_INFO *@<rcx>, struct _UNICODE_STRING *@<rdx>, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180003220`
- `0x180003370`
- `0x1800040e0`
- `0x180005e90`
- `0x1800078c0`
- `0x18000807c`
- `0x18000bbe0`
- `0x18000c2a8`
- `0x18000d930`
- `0x18000dde0`
- `0x18000e4e0`
- `0x180014a50`
- `0x180014ae0`
- `0x180014eb8`
- `0x180015e18`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9cd`
- `RPCRT4!NdrClientCall3` at `0x18000dad7`
- `RPCRT4!NdrClientCall3` at `0x18000dad7`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000db3b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000db3b`

## pseudocode

```c
__int64 __fastcall SamCreateUser2InDomain(
        struct _SAMP_CLIENT_INFO *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        int a4,
        struct _SAMP_CLIENT_INFO **a5,
        _DWORD *a6,
        _DWORD *a7)
{
  unsigned __int16 *CallingProcessInfo; // rax
  int v12; // edx
  unsigned __int16 *v13; // r14
  const wchar_t *v14; // rcx
  int v15; // edx
  int v16; // ecx
  struct _SAMP_CLIENT_INFO **v18; // rdx
  int v19; // ecx
  int Pointer; // ebx
  CLIENT_CALL_RETURN v21; // rax
  CLIENT_CALL_RETURN v22; // r8
  int UserInDomain; // eax
  unsigned int v24; // edi
  int v25; // eax
  int v26; // eax
  _DWORD *v27; // r15
  struct _SAMP_CLIENT_INFO *v28; // r9
  int v29; // ecx
  __int64 v30; // [rsp+28h] [rbp-80h]
  __int64 v31; // [rsp+30h] [rbp-78h]
  struct _SAMP_CLIENT_INFO *v32; // [rsp+58h] [rbp-50h] BYREF
  __int64 v33; // [rsp+60h] [rbp-48h] BYREF
  struct _SAMP_CLIENT_INFO *v34; // [rsp+68h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-38h]

  v32 = 0;
  v34 = 0;
  v33 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    hMem = SampDuplicateUnicodeString(a2);
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v13 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v14 = L"<unknown>";
      if ( CallingProcessInfo )
        v14 = CallingProcessInfo;
      McTemplateU0pzqqz_EventWriteTransfer((_DWORD)v14, v12, (_DWORD)a1, (_DWORD)hMem, a3, a4, (__int64)v14);
    }
    LocalFree(v13);
    LocalFree(hMem);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qZDD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)a1, (__int64)a2, a3, a4);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, (void **)&v34) )
  {
    Pointer = SampCreateNewHandle(a1, 0, &v32);
    if ( Pointer < 0 )
      goto LABEL_55;
    *a5 = 0;
    *a7 = 0;
    hMem = 0;
    LODWORD(v31) = a4;
    LODWORD(v30) = a3;
    v21.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x32u, 0, v34, a2, v30, v31, &v33, a6, a7).Pointer;
    Pointer = (int)v21.Pointer;
    hMem = (HLOCAL)v21.Simple;
    if ( LODWORD(v21.Pointer) == -1073610706 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
      UserInDomain = SamCreateUserInDomain(v34, a2, (__int64)a7);
      Pointer = UserInDomain;
      if ( UserInDomain >= 0 )
      {
        *(_QWORD *)v32 = v33;
        v24 = a3 | 5;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v24);
        v25 = SamSetInformationUser(v32);
        Pointer = v25;
        if ( v25 < 0 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              53,
              &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
              (unsigned int)v25);
          v26 = SamDeleteUser(v32);
          if ( v26 < 0 )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                54,
                &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
                (unsigned int)v26);
          }
          else
          {
            v32 = 0;
          }
        }
        v27 = a6;
        *a6 = 0;
        goto LABEL_40;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
          (unsigned int)UserInDomain);
    }
    v27 = a6;
LABEL_40:
    if ( Pointer < 0 )
    {
      if ( v32 )
        SampFreeHandle(&v32);
    }
    else
    {
      *(_QWORD *)v32 = v33;
    }
    v28 = v32;
    v18 = a5;
    *a5 = v32;
    if ( Pointer == -1073610749 )
      Pointer = -1073741816;
    if ( Pointer >= 0 )
    {
      v29 = (int)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_qDD)(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          (CLIENT_CALL_RETURN)v22.Simple,
          v28,
          *v27,
          *a7);
        v18 = a5;
      }
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
        McTemplateU0dpqq_EventWriteTransfer(v29, (_DWORD)v18, Pointer, (unsigned int)*v18, *v27, *a7);
      return (unsigned int)Pointer;
    }
    v19 = (int)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
        (unsigned int)Pointer);
LABEL_55:
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0dpqq_EventWriteTransfer(v19, (_DWORD)v18, Pointer, 0, 0, 0);
    return (unsigned int)Pointer;
  }
  v16 = (int)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dpqq_EventWriteTransfer(v16, v15, -1073741816, 0, 0, 0);
  return 3221225480LL;
}

```

## disassembly

```asm
0x18000d930  mov     rax, rsp
0x18000d933  mov     [rax+8], rbx
0x18000d937  mov     [rax+20h], r9d
0x18000d93b  mov     [rax+18h], r8d
0x18000d93f  mov     [rax+10h], rdx
0x18000d943  push    rsi
0x18000d944  push    rdi
0x18000d945  push    r13
0x18000d947  push    r14
0x18000d949  push    r15
0x18000d94b  sub     rsp, 80h
0x18000d952  mov     r15d, r9d
0x18000d955  mov     edi, r8d
0x18000d958  mov     r13, rdx
0x18000d95b  mov     rbx, rcx
0x18000d95e  xor     esi, esi
0x18000d960  mov     [rax-54h], esi
0x18000d963  mov     [rax-50h], rsi
0x18000d967  mov     [rax-40h], rsi
0x18000d96b  mov     [rax-48h], rsi
0x18000d96f  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d976  jz      short loc_18000D9D3
0x18000d978  mov     rcx, rdx; struct _UNICODE_STRING *
0x18000d97b  call    ?SampDuplicateUnicodeString@@YAPEAGPEAU_UNICODE_STRING@@@Z; SampDuplicateUnicodeString(_UNICODE_STRING *)
0x18000d980  mov     [rsp+0A8h+hMem], rax
0x18000d985  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000d98a  mov     r14, rax
0x18000d98d  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000d994  jz      short loc_18000D9BF
0x18000d996  lea     rcx, aUnknown; "<unknown>"
0x18000d99d  test    rax, rax
0x18000d9a0  cmovnz  rcx, rax
0x18000d9a4  mov     [rsp+0A8h+var_78], rcx
0x18000d9a9  mov     dword ptr [rsp+0A8h+var_80], r15d
0x18000d9ae  mov     dword ptr [rsp+0A8h+var_88], edi
0x18000d9b2  mov     r9, [rsp+0A8h+hMem]
0x18000d9b7  mov     r8, rbx
0x18000d9ba  call    McTemplateU0pzqqz_EventWriteTransfer
0x18000d9bf  mov     rcx, r14; hMem
0x18000d9c2  call    cs:__imp_LocalFree
0x18000d9c8  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18000d9cd  call    cs:__imp_LocalFree
0x18000d9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9da  mov     r14b, 2
0x18000d9dd  test    [rcx+1Ch], r14b
0x18000d9e1  jz      short loc_18000DA03
0x18000d9e3  cmp     byte ptr [rcx+19h], 4
0x18000d9e7  jb      short loc_18000DA03
0x18000d9e9  mov     dword ptr [rsp+0A8h+var_78], r15d
0x18000d9ee  mov     dword ptr [rsp+0A8h+var_80], edi
0x18000d9f2  mov     [rsp+0A8h+var_88], r13
0x18000d9f7  mov     r9, rbx
0x18000d9fa  mov     rcx, [rcx+10h]
0x18000d9fe  call    WPP_SF_qZDD
0x18000da03  lea     rdx, [rsp+0A8h+var_40]; void **
0x18000da08  mov     rcx, rbx; void *
0x18000da0b  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000da10  test    al, al
0x18000da12  jnz     short loc_18000DA67
0x18000da14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da1b  test    [rcx+1Ch], r14b
0x18000da1f  jz      short loc_18000DA3F
0x18000da21  cmp     [rcx+19h], r14b
0x18000da25  jb      short loc_18000DA3F
0x18000da27  mov     edx, 31h ; '1'
0x18000da2c  mov     r9, rbx
0x18000da2f  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000da36  mov     rcx, [rcx+10h]
0x18000da3a  call    WPP_SF_q
0x18000da3f  mov     edi, 0C0000008h
0x18000da44  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000da4b  jz      short loc_18000DA60
0x18000da4d  mov     dword ptr [rsp+0A8h+var_80], esi
0x18000da51  mov     dword ptr [rsp+0A8h+var_88], esi
0x18000da55  xor     r9d, r9d
0x18000da58  mov     r8d, edi
0x18000da5b  call    McTemplateU0dpqq_EventWriteTransfer
0x18000da60  mov     eax, edi
0x18000da62  jmp     loc_18000DDBE
0x18000da67  lea     r8, [rsp+0A8h+var_50]; struct _SAMP_CLIENT_INFO **
0x18000da6c  xor     edx, edx; void *
0x18000da6e  mov     rcx, rbx; struct _SAMP_CLIENT_INFO *
0x18000da71  call    ?SampCreateNewHandle@@YAJPEAU_SAMP_CLIENT_INFO@@PEAXPEAPEAU1@@Z; SampCreateNewHandle(_SAMP_CLIENT_INFO *,void *,_SAMP_CLIENT_INFO * *)
0x18000da76  mov     ebx, eax
0x18000da78  test    eax, eax
0x18000da7a  js      loc_18000DDA0
0x18000da80  mov     rax, [rsp+0A8h+arg_20]
0x18000da88  mov     [rax], rsi
0x18000da8b  mov     rax, [rsp+0A8h+arg_30]
0x18000da93  mov     [rax], esi
0x18000da95  mov     [rsp+0A8h+hMem], rsi
0x18000da9a  mov     [rsp+0A8h+var_60], rax
0x18000da9f  mov     rax, [rsp+0A8h+arg_28]
0x18000daa7  mov     [rsp+0A8h+var_68], rax
0x18000daac  lea     rax, [rsp+0A8h+var_48]
0x18000dab1  mov     [rsp+0A8h+var_70], rax
0x18000dab6  mov     dword ptr [rsp+0A8h+var_78], r15d
0x18000dabb  mov     dword ptr [rsp+0A8h+var_80], edi
0x18000dabf  mov     [rsp+0A8h+var_88], r13
0x18000dac4  mov     r9, [rsp+0A8h+var_40]
0x18000dac9  xor     r8d, r8d; pReturnValue
0x18000dacc  lea     edx, [r8+32h]; nProcNum
0x18000dad0  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000dad7  call    cs:__imp_NdrClientCall3
0x18000dadd  mov     rbx, rax
0x18000dae0  mov     [rsp+0A8h+hMem], rax
0x18000dae5  mov     [rsp+0A8h+var_58], eax
0x18000dae9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daf0  jmp     loc_18000DB75
0x18000daf5  mov     ebx, eax
0x18000daf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dafe  test    byte ptr [rcx+1Ch], 2
0x18000db02  jz      short loc_18000DB29
0x18000db04  cmp     byte ptr [rcx+19h], 3
0x18000db08  jb      short loc_18000DB29
0x18000db0a  mov     r9d, eax
0x18000db0d  mov     edx, 32h ; '2'
0x18000db12  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000db19  mov     rcx, [rcx+10h]
0x18000db1d  call    WPP_SF_D
0x18000db22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db29  cmp     ebx, 6D1h
0x18000db2f  jz      short loc_18000DB50
0x18000db31  cmp     ebx, 0C002002Eh
0x18000db37  jz      short loc_18000DB50
0x18000db39  mov     ecx, ebx; Status
0x18000db3b  call    cs:__imp_I_RpcMapWin32Status
0x18000db41  mov     ebx, eax
0x18000db43  mov     [rsp+0A8h+var_58], eax
0x18000db47  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db4e  jmp     short loc_18000DB59
0x18000db50  mov     ebx, 0C002002Eh
0x18000db55  mov     [rsp+0A8h+var_58], ebx
0x18000db59  xor     esi, esi
0x18000db5b  mov     r14b, 2
0x18000db5e  mov     r15d, [rsp+0A8h+arg_18]
0x18000db66  mov     edi, [rsp+0A8h+arg_10]
0x18000db6d  mov     r13, [rsp+0A8h+arg_8]
0x18000db75  cmp     ebx, 0C002002Eh
0x18000db7b  jnz     loc_18000DCCE
0x18000db81  test    [rcx+1Ch], r14b
0x18000db85  jz      short loc_18000DBA2
0x18000db87  cmp     byte ptr [rcx+19h], 3
0x18000db8b  jb      short loc_18000DBA2
0x18000db8d  mov     edx, 33h ; '3'
0x18000db92  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000db99  mov     rcx, [rcx+10h]
0x18000db9d  call    WPP_SF_
0x18000dba2  or      r15d, 20h
0x18000dba6  mov     rax, [rsp+0A8h+arg_30]
0x18000dbae  mov     [rsp+0A8h+var_88], rax; __int64
0x18000dbb3  lea     r9, [rsp+0A8h+var_48]
0x18000dbb8  mov     r8d, r15d
0x18000dbbb  mov     rdx, r13; struct _UNICODE_STRING *
0x18000dbbe  mov     rcx, [rsp+0A8h+var_40]; struct _SAMP_CLIENT_INFO *
0x18000dbc3  call    SamCreateUserInDomain
0x18000dbc8  mov     ebx, eax
0x18000dbca  test    eax, eax
0x18000dbcc  js      loc_18000DCA3
0x18000dbd2  mov     rcx, [rsp+0A8h+var_48]
0x18000dbd7  mov     rax, [rsp+0A8h+var_50]
0x18000dbdc  mov     [rax], rcx
0x18000dbdf  or      edi, 5
0x18000dbe2  mov     [rsp+0A8h+var_54], edi
0x18000dbe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbed  test    [rcx+1Ch], r14b
0x18000dbf1  jz      short loc_18000DC11
0x18000dbf3  cmp     byte ptr [rcx+19h], 4
0x18000dbf7  jb      short loc_18000DC11
0x18000dbf9  mov     edx, 34h ; '4'
0x18000dbfe  mov     r9d, edi
0x18000dc01  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000dc08  mov     rcx, [rcx+10h]
0x18000dc0c  call    WPP_SF_D
0x18000dc11  lea     r8, [rsp+0A8h+var_54]
0x18000dc16  mov     edx, 10h
0x18000dc1b  mov     rcx, [rsp+0A8h+var_50]; void *
0x18000dc20  call    SamSetInformationUser
0x18000dc25  mov     ebx, eax
0x18000dc27  test    eax, eax
0x18000dc29  jns     short loc_18000DC96
0x18000dc2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc32  test    [rcx+1Ch], r14b
0x18000dc36  jz      short loc_18000DC56
0x18000dc38  cmp     [rcx+19h], r14b
0x18000dc3c  jb      short loc_18000DC56
0x18000dc3e  mov     edx, 35h ; '5'
0x18000dc43  mov     r9d, eax
0x18000dc46  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000dc4d  mov     rcx, [rcx+10h]
0x18000dc51  call    WPP_SF_D
0x18000dc56  mov     rcx, [rsp+0A8h+var_50]; void *
0x18000dc5b  call    SamDeleteUser
0x18000dc60  test    eax, eax
0x18000dc62  js      short loc_18000DC6B
0x18000dc64  mov     [rsp+0A8h+var_50], rsi
0x18000dc69  jmp     short loc_18000DC96
0x18000dc6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc72  test    [rcx+1Ch], r14b
0x18000dc76  jz      short loc_18000DC96
0x18000dc78  cmp     [rcx+19h], r14b
0x18000dc7c  jb      short loc_18000DC96
0x18000dc7e  mov     edx, 36h ; '6'
0x18000dc83  mov     r9d, eax
0x18000dc86  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000dc8d  mov     rcx, [rcx+10h]
0x18000dc91  call    WPP_SF_D
0x18000dc96  mov     r15, [rsp+0A8h+arg_28]
0x18000dc9e  mov     [r15], esi
0x18000dca1  jmp     short loc_18000DCD6
0x18000dca3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcaa  test    [rcx+1Ch], r14b
0x18000dcae  jz      short loc_18000DCCE
0x18000dcb0  cmp     [rcx+19h], r14b
0x18000dcb4  jb      short loc_18000DCCE
0x18000dcb6  mov     edx, 37h ; '7'
0x18000dcbb  mov     r9d, eax
0x18000dcbe  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000dcc5  mov     rcx, [rcx+10h]
0x18000dcc9  call    WPP_SF_D
0x18000dcce  mov     r15, [rsp+0A8h+arg_28]
0x18000dcd6  test    ebx, ebx
0x18000dcd8  js      short loc_18000DCE9
0x18000dcda  mov     rcx, [rsp+0A8h+var_48]
0x18000dcdf  mov     rax, [rsp+0A8h+var_50]
0x18000dce4  mov     [rax], rcx
0x18000dce7  jmp     short loc_18000DCFA
0x18000dce9  cmp     [rsp+0A8h+var_50], rsi
0x18000dcee  jz      short loc_18000DCFA
0x18000dcf0  lea     rcx, [rsp+0A8h+var_50]; struct _SAMP_CLIENT_INFO **
0x18000dcf5  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x18000dcfa  mov     r9, [rsp+0A8h+var_50]
0x18000dcff  mov     rdx, [rsp+0A8h+arg_20]
0x18000dd07  mov     [rdx], r9
0x18000dd0a  mov     edi, 0C0000008h
0x18000dd0f  cmp     ebx, 0C0020003h
0x18000dd15  cmovz   ebx, edi
0x18000dd18  test    ebx, ebx
0x18000dd1a  js      short loc_18000DD75
0x18000dd1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd23  mov     rdi, [rsp+0A8h+arg_30]
0x18000dd2b  test    [rcx+1Ch], r14b
0x18000dd2f  jz      short loc_18000DD5A
0x18000dd31  cmp     byte ptr [rcx+19h], 4
0x18000dd35  jb      short loc_18000DD5A
0x18000dd37  mov     edx, 38h ; '8'
0x18000dd3c  mov     eax, [rdi]
0x18000dd3e  mov     dword ptr [rsp+0A8h+var_80], eax
0x18000dd42  mov     eax, [r15]
0x18000dd45  mov     dword ptr [rsp+0A8h+var_88], eax
0x18000dd49  mov     rcx, [rcx+10h]
0x18000dd4d  call    WPP_SF_qDD
0x18000dd52  mov     rdx, [rsp+0A8h+arg_20]
0x18000dd5a  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000dd61  jz      short loc_18000DDBC
0x18000dd63  mov     eax, [rdi]
0x18000dd65  mov     dword ptr [rsp+0A8h+var_80], eax
0x18000dd69  mov     eax, [r15]
0x18000dd6c  mov     dword ptr [rsp+0A8h+var_88], eax
0x18000dd70  mov     r9, [rdx]
0x18000dd73  jmp     short loc_18000DDB4
0x18000dd75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd7c  test    [rcx+1Ch], r14b
0x18000dd80  jz      short loc_18000DDA0
0x18000dd82  cmp     [rcx+19h], r14b
0x18000dd86  jb      short loc_18000DDA0
0x18000dd88  mov     edx, 39h ; '9'
0x18000dd8d  mov     r9d, ebx
0x18000dd90  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000dd97  mov     rcx, [rcx+10h]
0x18000dd9b  call    WPP_SF_D
0x18000dda0  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000dda7  jz      short loc_18000DDBC
0x18000dda9  mov     dword ptr [rsp+0A8h+var_80], esi
0x18000ddad  mov     dword ptr [rsp+0A8h+var_88], esi
0x18000ddb1  xor     r9d, r9d
0x18000ddb4  mov     r8d, ebx
0x18000ddb7  call    McTemplateU0dpqq_EventWriteTransfer
0x18000ddbc  mov     eax, ebx
0x18000ddbe  mov     rbx, [rsp+0A8h+arg_0]
0x18000ddc6  add     rsp, 80h
0x18000ddcd  pop     r15
0x18000ddcf  pop     r14
0x18000ddd1  pop     r13
0x18000ddd3  pop     rdi
0x18000ddd4  pop     rsi
0x18000ddd5  retn
0x180017dde  push    rbp
0x180017de0  sub     rsp, 50h
0x180017de4  mov     rbp, rdx
0x180017de7  mov     rcx, [rcx]
0x180017dea  mov     ecx, [rcx]; ExceptionCode
0x180017dec  call    cs:__imp_I_RpcExceptionFilter
0x180017df2  nop
0x180017df3  add     rsp, 50h
0x180017df7  pop     rbp
0x180017df8  retn
```
