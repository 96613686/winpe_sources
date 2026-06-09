# ClientBFEHandler::DeletePolicy(uchar,in_addr *,in6_addr *)

- ea: `0x180031220`
- end: `0x180031782`
- name: `?DeletePolicy@ClientBFEHandler@@QEAAKEPEAUin_addr@@PEAUin6_addr@@@Z`
- size: `1378`
- prototype: `__int64 __fastcall(ClientBFEHandler *this, char, struct in_addr *, struct in6_addr *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f240`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180007894`
- `0x18002e6f4`
- `0x180031220`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x180031582`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x180031582`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003171e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003171e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031710`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031710`

## string_xrefs

- `0x180031604`: `FwpmIPsecTunnelDeleteByKey failed: %d`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::DeletePolicy(
        ClientBFEHandler *this,
        char a2,
        struct in_addr *a3,
        struct in6_addr *a4)
{
  struct in6_addr *v4; // rsi
  PVOID *v8; // rbx
  _QWORD *i; // rax
  _QWORD *v10; // r12
  unsigned int v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // r15d
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int128 *v19; // r9
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int128 *v28; // r9
  unsigned int BfeHandle; // eax
  unsigned int v30; // ebx
  DWORD v31; // eax
  DWORD v32; // ebx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rcx
  __int128 *v40; // r9
  HANDLE ProcessHeap; // rax
  HANDLE engineHandle; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD **v43; // [rsp+38h] [rbp-C8h]
  __int128 v44; // [rsp+40h] [rbp-C0h] BYREF
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v46; // [rsp+54h] [rbp-ACh]
  __int128 v47; // [rsp+64h] [rbp-9Ch]
  int v48; // [rsp+74h] [rbp-8Ch]
  int v49; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v50[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v4 = a4;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a2 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, a4);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  engineHandle = 0;
  v49 = 0;
  memset_0(v50, 0, sizeof(v50));
  v45 = 0;
  v48 = 0;
  v46 = 0;
  v47 = 0;
  v44 = 0;
  if ( a2 )
  {
    if ( a3 )
      goto LABEL_7;
LABEL_17:
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_d(v8[2], 165, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 87);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_38;
    LOWORD(v45) = 0;
    v13 = *((_QWORD *)this + 6);
    if ( v13 && (v14 = *(_QWORD *)(v13 + 112)) != 0 && *(_QWORD *)(v14 + 16) )
      v15 = *(_DWORD *)(v14 + 16);
    else
      v15 = -1;
    ConvertPortNoToString(&v45, v15);
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_37:
      v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_38:
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
        WPP_SF_d(v8[2], 166, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 87);
      return 87;
    }
    v16 = *((_QWORD *)this + 6);
    v17 = (_QWORD *)(v16 + 112);
    if ( v16 )
    {
      if ( *v17 )
        v18 = *v17 + 2686LL;
      else
        v18 = 0;
      if ( *v17 )
      {
        v19 = (__int128 *)(*v17 + 2120LL);
LABEL_36:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid param",
          (_DWORD)v19,
          v18,
          (__int64)&v45);
        goto LABEL_37;
      }
    }
    else
    {
      v18 = 0;
    }
    v19 = &v44;
    goto LABEL_36;
  }
  if ( !v4 )
    goto LABEL_17;
LABEL_7:
  for ( i = (_QWORD *)((char *)this + 56); ; i = v10 )
  {
    v10 = (_QWORD *)*i;
    v43 = (_QWORD **)i;
    if ( !v10 )
      break;
    if ( a2 == *((_BYTE *)v10 + 8) )
    {
      v11 = -1;
      if ( a2 )
      {
        if ( a3->S_un.S_addr == *((_DWORD *)v10 + 3) )
        {
          if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 5u )
          {
            v12 = 167;
            goto LABEL_50;
          }
          goto LABEL_51;
        }
      }
      else if ( *(_QWORD *)&v4->u.Word[4] == *(_QWORD *)((char *)v10 + 20)
             && *(_QWORD *)v4->u.Byte == *(_QWORD *)((char *)v10 + 12) )
      {
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 5u )
        {
          v12 = 168;
LABEL_50:
          WPP_SF_(v8[2], v12, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
        }
LABEL_51:
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v45) = 0;
          v21 = *((_QWORD *)this + 6);
          if ( v21 && (v22 = *(_QWORD *)(v21 + 112)) != 0 && *(_QWORD *)(v22 + 16) )
            v23 = *(unsigned int *)(v22 + 16);
          else
            v23 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v45, v23);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v24 = *((_QWORD *)this + 6);
            if ( v24 )
            {
              v25 = *(_QWORD *)(v24 + 112);
              if ( v25 )
                v26 = v25 + 2686;
              else
                v26 = 0;
              v27 = *(_QWORD *)(v24 + 112);
              if ( v27 )
              {
                LODWORD(v28) = v27 + 2120;
                goto LABEL_66;
              }
            }
            else
            {
              v26 = 0;
            }
            v28 = &v44;
LABEL_66:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)L"Deleting Policy for Server address",
              (_DWORD)v28,
              v26,
              (__int64)&v45);
          }
        }
        BfeHandle = BFEHandler::GetBfeHandle(&engineHandle);
        v30 = BfeHandle;
        if ( engineHandle )
        {
          v31 = FwpmIPsecTunnelDeleteByKey0(engineHandle, (const GUID *)((char *)v10 + 44));
          v32 = v31;
          if ( v31 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v31);
            }
            if ( (byte_1800AA941 & 8) != 0 )
            {
              LOWORD(v49) = 0;
              LOWORD(v45) = 0;
              v33 = *((_QWORD *)this + 6);
              if ( v33 )
              {
                v34 = *(_QWORD *)(v33 + 112);
                if ( v34 )
                {
                  if ( *(_QWORD *)(v34 + 16) )
                    v11 = *(_DWORD *)(v34 + 16);
                }
              }
              ConvertPortNoToString(&v45, v11);
              FormatRRASErrorString(&v49, L"FwpmIPsecTunnelDeleteByKey failed: %d", v32);
              goto LABEL_90;
            }
          }
          goto LABEL_100;
        }
        if ( BfeHandle
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            170,
            &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
            BfeHandle);
        }
        if ( (byte_1800AA941 & 8) == 0 )
          goto LABEL_100;
        LOWORD(v49) = 0;
        LOWORD(v45) = 0;
        v35 = *((_QWORD *)this + 6);
        if ( v35 )
        {
          v36 = *(_QWORD *)(v35 + 112);
          if ( v36 )
          {
            if ( *(_QWORD *)(v36 + 16) )
              v11 = *(_DWORD *)(v36 + 16);
          }
        }
        ConvertPortNoToString(&v45, v11);
        FormatRRASErrorString(&v49, L"GetBfeHandle failed: %d", v30);
LABEL_90:
        if ( (byte_1800AA941 & 8) == 0 )
        {
LABEL_100:
          *v43 = (_QWORD *)**v43;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v10);
          v8 = (PVOID *)WPP_GLOBAL_Control;
          break;
        }
        v37 = *((_QWORD *)this + 6);
        v38 = (_QWORD *)(v37 + 112);
        if ( v37 )
        {
          if ( *v38 )
            v39 = *v38 + 2686LL;
          else
            v39 = 0;
          if ( *v38 )
          {
            v40 = (__int128 *)(*v38 + 2120LL);
LABEL_99:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)&v49,
              (_DWORD)v40,
              v39,
              (__int64)&v45);
            goto LABEL_100;
          }
        }
        else
        {
          v39 = 0;
        }
        v40 = &v44;
        goto LABEL_99;
      }
    }
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 171, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180031220  push    rbp
0x180031222  push    rbx
0x180031223  push    rsi
0x180031224  push    rdi
0x180031225  push    r12
0x180031227  push    r13
0x180031229  push    r14
0x18003122b  push    r15
0x18003122d  lea     rbp, [rsp-798h]
0x180031235  sub     rsp, 898h
0x18003123c  mov     rax, cs:__security_cookie
0x180031243  xor     rax, rsp
0x180031246  mov     [rbp+7D0h+var_50], rax
0x18003124d  mov     rsi, r9
0x180031250  mov     r14, r8
0x180031253  mov     dil, dl
0x180031256  mov     r13, rcx
0x180031259  mov     rbx, cs:WPP_GLOBAL_Control
0x180031260  lea     r12, WPP_GLOBAL_Control
0x180031267  cmp     rbx, r12
0x18003126a  jz      short loc_18003129A
0x18003126c  test    byte ptr [rbx+1Ch], 1
0x180031270  jz      short loc_18003129A
0x180031272  cmp     byte ptr [rbx+19h], 6
0x180031276  jb      short loc_18003129A
0x180031278  mov     rcx, [rbx+10h]
0x18003127c  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031283  test    dl, dl
0x180031285  mov     edx, 0A4h
0x18003128a  setnz   r9b
0x18003128e  call    WPP_SF_c
0x180031293  mov     rbx, cs:WPP_GLOBAL_Control
0x18003129a  xor     eax, eax
0x18003129c  mov     [rsp+8D0h+engineHandle], 0
0x1800312a5  xor     edx, edx; Val
0x1800312a7  mov     [rbp+7D0h+var_850], eax
0x1800312aa  mov     r8d, 7FCh; Size
0x1800312b0  lea     rcx, [rbp+7D0h+var_84C]; void *
0x1800312b4  call    memset_0
0x1800312b9  xor     eax, eax
0x1800312bb  xorps   xmm0, xmm0
0x1800312be  mov     [rsp+8D0h+var_880], eax
0x1800312c2  mov     [rsp+8D0h+var_85C], eax
0x1800312c6  movups  [rsp+8D0h+var_87C], xmm0
0x1800312cb  movups  [rsp+8D0h+var_86C], xmm0
0x1800312d0  movups  [rsp+8D0h+var_890], xmm0
0x1800312d5  test    dil, dil
0x1800312d8  jz      short loc_180031348
0x1800312da  test    r14, r14
0x1800312dd  jz      short loc_18003134D
0x1800312df  lea     rax, [r13+38h]
0x1800312e3  mov     r12, [rax]
0x1800312e6  mov     [rsp+8D0h+var_898], rax
0x1800312eb  test    r12, r12
0x1800312ee  jz      loc_18003172D
0x1800312f4  cmp     dil, [r12+8]
0x1800312f9  jnz     loc_18003147F
0x1800312ff  or      r15d, 0FFFFFFFFh
0x180031303  test    dil, dil
0x180031306  jz      loc_18003146A
0x18003130c  mov     eax, [r12+0Ch]
0x180031311  cmp     [r14], eax
0x180031314  jnz     loc_18003147F
0x18003131a  lea     rsi, WPP_GLOBAL_Control
0x180031321  cmp     rbx, rsi
0x180031324  jz      loc_1800314B4
0x18003132a  test    byte ptr [rbx+1Ch], 1
0x18003132e  jz      loc_1800314B4
0x180031334  cmp     byte ptr [rbx+19h], 5
0x180031338  jb      loc_1800314B4
0x18003133e  mov     edx, 0A7h
0x180031343  jmp     loc_1800314A4
0x180031348  test    rsi, rsi
0x18003134b  jnz     short loc_1800312DF
0x18003134d  mov     edi, 57h ; 'W'
0x180031352  cmp     rbx, r12
0x180031355  jz      short loc_180031380
0x180031357  test    byte ptr [rbx+1Ch], 1
0x18003135b  jz      short loc_180031380
0x18003135d  cmp     byte ptr [rbx+19h], 2
0x180031361  jb      short loc_180031380
0x180031363  mov     rcx, [rbx+10h]
0x180031367  lea     edx, [rdi+4Eh]
0x18003136a  mov     r9d, edi
0x18003136d  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031374  call    WPP_SF_d
0x180031379  mov     rbx, cs:WPP_GLOBAL_Control
0x180031380  test    cs:byte_1800AA941, 4
0x180031387  jz      loc_18003143A
0x18003138d  xor     eax, eax
0x18003138f  mov     word ptr [rsp+8D0h+var_880], ax
0x180031394  mov     rax, [r13+30h]
0x180031398  test    rax, rax
0x18003139b  jz      short loc_1800313B3
0x18003139d  mov     rax, [rax+70h]
0x1800313a1  test    rax, rax
0x1800313a4  jz      short loc_1800313B3
0x1800313a6  cmp     qword ptr [rax+10h], 0
0x1800313ab  jz      short loc_1800313B3
0x1800313ad  mov     r15d, [rax+10h]
0x1800313b1  jmp     short loc_1800313B7
0x1800313b3  or      r15d, 0FFFFFFFFh
0x1800313b7  mov     edx, r15d
0x1800313ba  lea     rcx, [rsp+8D0h+var_880]
0x1800313bf  call    ConvertPortNoToString
0x1800313c4  test    cs:byte_1800AA941, 4
0x1800313cb  jz      short loc_180031433
0x1800313cd  mov     rcx, [r13+30h]
0x1800313d1  lea     rax, [rcx+70h]
0x1800313d5  test    rcx, rcx
0x1800313d8  jz      short loc_180031403
0x1800313da  mov     rdx, [rax]
0x1800313dd  test    rdx, rdx
0x1800313e0  jz      short loc_1800313EB
0x1800313e2  lea     rcx, [rdx+0A7Eh]
0x1800313e9  jmp     short loc_1800313F2
0x1800313eb  test    rcx, rcx
0x1800313ee  jz      short loc_180031403
0x1800313f0  xor     ecx, ecx
0x1800313f2  mov     rdx, [rax]
0x1800313f5  test    rdx, rdx
0x1800313f8  jz      short loc_180031405
0x1800313fa  lea     r9, [rdx+848h]
0x180031401  jmp     short loc_18003140A
0x180031403  xor     ecx, ecx
0x180031405  lea     r9, [rsp+8D0h+var_890]
0x18003140a  lea     rax, [rsp+8D0h+var_880]
0x18003140f  mov     [rsp+8D0h+var_8A8], rax
0x180031414  lea     r8, aInvalidParam; "Invalid param"
0x18003141b  mov     [rsp+8D0h+var_8B0], rcx
0x180031420  lea     rdx, RasVpnIkeParamTraceError
0x180031427  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003142e  call    McTemplateU0zjzz_EventWriteTransfer
0x180031433  mov     rbx, cs:WPP_GLOBAL_Control
0x18003143a  cmp     rbx, r12
0x18003143d  jz      short loc_180031463
0x18003143f  test    byte ptr [rbx+1Ch], 1
0x180031443  jz      short loc_180031463
0x180031445  cmp     byte ptr [rbx+19h], 6
0x180031449  jb      short loc_180031463
0x18003144b  mov     rcx, [rbx+10h]
0x18003144f  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031456  mov     edx, 0A6h
0x18003145b  mov     r9d, edi
0x18003145e  call    WPP_SF_d
0x180031463  mov     eax, edi
0x180031465  jmp     loc_18003175F
0x18003146a  mov     rax, [r12+14h]
0x18003146f  cmp     [rsi+8], rax
0x180031473  jnz     short loc_18003147F
0x180031475  mov     rax, [r12+0Ch]
0x18003147a  cmp     [rsi], rax
0x18003147d  jz      short loc_180031487
0x18003147f  mov     rax, r12
0x180031482  jmp     loc_1800312E3
0x180031487  lea     rsi, WPP_GLOBAL_Control
0x18003148e  cmp     rbx, rsi
0x180031491  jz      short loc_1800314B4
0x180031493  test    byte ptr [rbx+1Ch], 1
0x180031497  jz      short loc_1800314B4
0x180031499  cmp     byte ptr [rbx+19h], 5
0x18003149d  jb      short loc_1800314B4
0x18003149f  mov     edx, 0A8h
0x1800314a4  mov     rcx, [rbx+10h]
0x1800314a8  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800314af  call    WPP_SF_
0x1800314b4  mov     dil, 8
0x1800314b7  test    cs:byte_1800AA941, dil
0x1800314be  jz      loc_180031563
0x1800314c4  xor     eax, eax
0x1800314c6  mov     word ptr [rsp+8D0h+var_880], ax
0x1800314cb  mov     rax, [r13+30h]
0x1800314cf  test    rax, rax
0x1800314d2  jz      short loc_1800314E9
0x1800314d4  mov     rax, [rax+70h]
0x1800314d8  test    rax, rax
0x1800314db  jz      short loc_1800314E9
0x1800314dd  cmp     qword ptr [rax+10h], 0
0x1800314e2  jz      short loc_1800314E9
0x1800314e4  mov     edx, [rax+10h]
0x1800314e7  jmp     short loc_1800314EC
0x1800314e9  mov     edx, r15d
0x1800314ec  lea     rcx, [rsp+8D0h+var_880]
0x1800314f1  call    ConvertPortNoToString
0x1800314f6  test    cs:byte_1800AA941, dil
0x1800314fd  jz      short loc_180031563
0x1800314ff  mov     rcx, [r13+30h]
0x180031503  test    rcx, rcx
0x180031506  jz      short loc_180031533
0x180031508  mov     rdx, [rcx+70h]
0x18003150c  test    rdx, rdx
0x18003150f  jz      short loc_18003151A
0x180031511  add     rdx, 0A7Eh
0x180031518  jmp     short loc_180031521
0x18003151a  test    rcx, rcx
0x18003151d  jz      short loc_180031533
0x18003151f  xor     edx, edx
0x180031521  mov     rcx, [rcx+70h]
0x180031525  test    rcx, rcx
0x180031528  jz      short loc_180031535
0x18003152a  lea     r9, [rcx+848h]
0x180031531  jmp     short loc_18003153A
0x180031533  xor     edx, edx
0x180031535  lea     r9, [rsp+8D0h+var_890]
0x18003153a  lea     rax, [rsp+8D0h+var_880]
0x18003153f  mov     [rsp+8D0h+var_8A8], rax
0x180031544  lea     r8, aDeletingPolicy; "Deleting Policy for Server address"
0x18003154b  mov     [rsp+8D0h+var_8B0], rdx
0x180031550  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180031557  lea     rdx, RasVpnIkeParamTraceInfo
0x18003155e  call    McTemplateU0zjzz_EventWriteTransfer
0x180031563  lea     rcx, [rsp+8D0h+engineHandle]; void **
0x180031568  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x18003156d  mov     rcx, [rsp+8D0h+engineHandle]; engineHandle
0x180031572  mov     ebx, eax
0x180031574  test    rcx, rcx
0x180031577  jz      loc_18003160D
0x18003157d  lea     rdx, [r12+2Ch]; key
0x180031582  call    cs:__imp_FwpmIPsecTunnelDeleteByKey0
0x180031588  mov     ebx, eax
0x18003158a  test    eax, eax
0x18003158c  jz      loc_180031702
0x180031592  mov     rcx, cs:WPP_GLOBAL_Control
0x180031599  cmp     rcx, rsi
0x18003159c  jz      short loc_1800315C2
0x18003159e  test    byte ptr [rcx+1Ch], 1
0x1800315a2  jz      short loc_1800315C2
0x1800315a4  cmp     byte ptr [rcx+19h], 2
0x1800315a8  jb      short loc_1800315C2
0x1800315aa  mov     rcx, [rcx+10h]
0x1800315ae  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800315b5  mov     edx, 0A9h
0x1800315ba  mov     r9d, eax
0x1800315bd  call    WPP_SF_d
0x1800315c2  test    cs:byte_1800AA941, dil
0x1800315c9  jz      loc_180031702
0x1800315cf  xor     eax, eax
0x1800315d1  mov     word ptr [rbp+7D0h+var_850], ax
0x1800315d5  mov     word ptr [rsp+8D0h+var_880], ax
0x1800315da  mov     rax, [r13+30h]
0x1800315de  test    rax, rax
0x1800315e1  jz      short loc_1800315F7
0x1800315e3  mov     rax, [rax+70h]
0x1800315e7  test    rax, rax
0x1800315ea  jz      short loc_1800315F7
0x1800315ec  cmp     qword ptr [rax+10h], 0
0x1800315f1  jz      short loc_1800315F7
0x1800315f3  mov     r15d, [rax+10h]
0x1800315f7  mov     edx, r15d
0x1800315fa  lea     rcx, [rsp+8D0h+var_880]
0x1800315ff  call    ConvertPortNoToString
0x180031604  lea     rdx, aFwpmipsectunne_0; "FwpmIPsecTunnelDeleteByKey failed: %d"
0x18003160b  jmp     short loc_18003168A
0x18003160d  test    ebx, ebx
0x18003160f  jz      short loc_180031641
0x180031611  mov     rcx, cs:WPP_GLOBAL_Control
0x180031618  cmp     rcx, rsi
0x18003161b  jz      short loc_180031641
0x18003161d  test    byte ptr [rcx+1Ch], 1
0x180031621  jz      short loc_180031641
0x180031623  cmp     byte ptr [rcx+19h], 2
0x180031627  jb      short loc_180031641
0x180031629  mov     rcx, [rcx+10h]
0x18003162d  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031634  mov     edx, 0AAh
0x180031639  mov     r9d, ebx
0x18003163c  call    WPP_SF_d
0x180031641  test    cs:byte_1800AA941, dil
0x180031648  jz      loc_180031702
0x18003164e  xor     eax, eax
0x180031650  mov     word ptr [rbp+7D0h+var_850], ax
0x180031654  mov     word ptr [rsp+8D0h+var_880], ax
0x180031659  mov     rax, [r13+30h]
0x18003165d  test    rax, rax
0x180031660  jz      short loc_180031676
0x180031662  mov     rax, [rax+70h]
0x180031666  test    rax, rax
0x180031669  jz      short loc_180031676
0x18003166b  cmp     qword ptr [rax+10h], 0
0x180031670  jz      short loc_180031676
0x180031672  mov     r15d, [rax+10h]
0x180031676  mov     edx, r15d
0x180031679  lea     rcx, [rsp+8D0h+var_880]
0x18003167e  call    ConvertPortNoToString
0x180031683  lea     rdx, aGetbfehandleFa; "GetBfeHandle failed: %d"
0x18003168a  mov     r8d, ebx
0x18003168d  lea     rcx, [rbp+7D0h+var_850]
0x180031691  call    FormatRRASErrorString
0x180031696  test    cs:byte_1800AA941, dil
0x18003169d  jz      short loc_180031702
0x18003169f  mov     rcx, [r13+30h]
0x1800316a3  lea     rax, [rcx+70h]
0x1800316a7  test    rcx, rcx
0x1800316aa  jz      short loc_1800316D5
0x1800316ac  mov     rdx, [rax]
0x1800316af  test    rdx, rdx
0x1800316b2  jz      short loc_1800316BD
0x1800316b4  lea     rcx, [rdx+0A7Eh]
0x1800316bb  jmp     short loc_1800316C4
0x1800316bd  test    rcx, rcx
  ... truncated ...
```
