# CWcnEapTransport::DoTargetedScan(CSbSafeBuffer const *)

- ea: `0x1800452e0`
- end: `0x180045497`
- name: `?DoTargetedScan@CWcnEapTransport@@UEAAJPEBVCSbSafeBuffer@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(CWcnEapTransport *__hidden this, const struct CSbSafeBuffer *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180001e16`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180044fb8`
- `0x1800452e0`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045389`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045389`

## string_xrefs

- `0x180045370`: `pSsid`

## pseudocode

```c
__int64 __fastcall CWcnEapTransport::DoTargetedScan(CWcnEapTransport *this, const struct CSbSafeBuffer *a2)
{
  _QWORD *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // ebx
  _BYTE *v12; // r10
  unsigned int v13; // eax
  __int64 v14; // r10
  unsigned int v15; // eax
  __int64 v16; // r10
  struct _DOT11_SSID v17; // [rsp+30h] [rbp-48h] BYREF

  memset(&v17, 0, sizeof(v17));
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 23, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *((_QWORD *)this + 34) = GetTickCount64();
    v8 = *((_QWORD *)a2 + 3);
    if ( v8 )
      v9 = *(_QWORD *)(v8 + 8) - *(_QWORD *)v8;
    else
      LODWORD(v9) = 0;
    v17.uSSIDLength = v9;
    if ( (unsigned int)(v9 - 1) > 0x1F )
    {
      v11 = -2147024809;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = (unsigned int)GetIndent(0);
          WPP_SF_sd(*(_QWORD *)(v14 + 16), 25, (unsigned int)WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, v13, 32);
          goto LABEL_20;
        }
        goto LABEL_21;
      }
    }
    else
    {
      memcpy_0(v17.ucSSID, *(const void **)v8, (unsigned int)v9);
      v10 = CWcnEapTransport::DoDiscoveryInternal(this, &v17);
      v11 = v10;
      if ( v10 >= 0 )
      {
LABEL_20:
        v12 = WPP_GLOBAL_Control;
        goto LABEL_21;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids,
            (unsigned int)v10);
          goto LABEL_20;
        }
LABEL_21:
        if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (v11 < 0 || v12[25] >= 6u) )
        {
          v15 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v16 + 16), 27, (unsigned int)WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, v15, v11);
        }
      }
    }
    return (unsigned int)v11;
  }
  if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
    WPP_SF_s(v4[2], 24, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, "pSsid");
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800452e0  mov     [rsp+arg_10], rbx
0x1800452e5  push    rbp
0x1800452e6  push    rsi
0x1800452e7  push    rdi
0x1800452e8  sub     rsp, 60h
0x1800452ec  mov     rax, cs:__security_cookie
0x1800452f3  xor     rax, rsp
0x1800452f6  mov     [rsp+78h+var_20], rax
0x1800452fb  xorps   xmm0, xmm0
0x1800452fe  xor     eax, eax
0x180045300  movups  xmmword ptr [rsp+78h+var_48.uSSIDLength], xmm0
0x180045305  mov     dword ptr [rsp+78h+var_48.ucSSID+1Ch], eax
0x180045309  mov     rbx, rdx
0x18004530c  movups  xmmword ptr [rsp+78h+var_48.ucSSID+0Ch], xmm0
0x180045311  mov     rdi, rcx
0x180045314  mov     r10, cs:WPP_GLOBAL_Control
0x18004531b  lea     rsi, WPP_GLOBAL_Control
0x180045322  lea     rbp, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x180045329  cmp     r10, rsi
0x18004532c  jz      short loc_180045358
0x18004532e  cmp     byte ptr [r10+19h], 6
0x180045333  jb      short loc_180045358
0x180045335  lea     ecx, [rax+1]; int
0x180045338  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004533d  mov     rcx, [r10+10h]
0x180045341  mov     edx, 17h
0x180045346  mov     r9, rax
0x180045349  mov     r8, rbp
0x18004534c  call    WPP_SF_s
0x180045351  mov     r10, cs:WPP_GLOBAL_Control
0x180045358  test    rbx, rbx
0x18004535b  jnz     short loc_180045389
0x18004535d  cmp     r10, rsi
0x180045360  jz      short loc_18004537F
0x180045362  cmp     byte ptr [r10+19h], 2
0x180045367  jb      short loc_18004537F
0x180045369  mov     rcx, [r10+10h]
0x18004536d  lea     edx, [rbx+18h]
0x180045370  lea     r9, aPssid; "pSsid"
0x180045377  mov     r8, rbp
0x18004537a  call    WPP_SF_s
0x18004537f  mov     eax, 80004003h
0x180045384  jmp     loc_18004547A
0x180045389  call    cs:__imp_GetTickCount64
0x18004538f  mov     [rdi+110h], rax
0x180045396  mov     rdx, [rbx+18h]
0x18004539a  test    rdx, rdx
0x18004539d  jz      short loc_1800453A8
0x18004539f  mov     rcx, [rdx+8]
0x1800453a3  sub     rcx, [rdx]
0x1800453a6  jmp     short loc_1800453AA
0x1800453a8  xor     ecx, ecx
0x1800453aa  lea     eax, [rcx-1]
0x1800453ad  mov     [rsp+78h+var_48.uSSIDLength], ecx
0x1800453b1  cmp     eax, 1Fh
0x1800453b4  ja      short loc_180045406
0x1800453b6  mov     rdx, [rdx]; Src
0x1800453b9  mov     r8d, ecx; Size
0x1800453bc  lea     rcx, [rsp+78h+var_48.ucSSID]; void *
0x1800453c1  call    memcpy_0
0x1800453c6  lea     rdx, [rsp+78h+var_48]; struct _DOT11_SSID *
0x1800453cb  mov     rcx, rdi; this
0x1800453ce  call    ?DoDiscoveryInternal@CWcnEapTransport@@AEAAJPEBU_DOT11_SSID@@_N@Z; CWcnEapTransport::DoDiscoveryInternal(_DOT11_SSID const *,bool)
0x1800453d3  mov     ebx, eax
0x1800453d5  test    eax, eax
0x1800453d7  jns     short loc_180045441
0x1800453d9  mov     r10, cs:WPP_GLOBAL_Control
0x1800453e0  cmp     r10, rsi
0x1800453e3  jz      loc_180045478
0x1800453e9  cmp     byte ptr [r10+19h], 2
0x1800453ee  jb      short loc_180045448
0x1800453f0  mov     rcx, [r10+10h]
0x1800453f4  mov     edx, 1Ah
0x1800453f9  mov     r9d, eax
0x1800453fc  mov     r8, rbp
0x1800453ff  call    WPP_SF_d
0x180045404  jmp     short loc_180045441
0x180045406  mov     ebx, 80070057h
0x18004540b  mov     r10, cs:WPP_GLOBAL_Control
0x180045412  cmp     r10, rsi
0x180045415  jz      short loc_180045478
0x180045417  cmp     byte ptr [r10+19h], 2
0x18004541c  jb      short loc_180045448
0x18004541e  xor     ecx, ecx; int
0x180045420  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180045425  mov     rcx, [r10+10h]
0x180045429  mov     edx, 19h
0x18004542e  mov     r9, rax
0x180045431  mov     [rsp+78h+var_58], 20h ; ' '
0x180045439  mov     r8, rbp
0x18004543c  call    WPP_SF_sd
0x180045441  mov     r10, cs:WPP_GLOBAL_Control
0x180045448  cmp     r10, rsi
0x18004544b  jz      short loc_180045478
0x18004544d  test    ebx, ebx
0x18004544f  js      short loc_180045458
0x180045451  cmp     byte ptr [r10+19h], 6
0x180045456  jb      short loc_180045478
0x180045458  or      ecx, 0FFFFFFFFh; int
0x18004545b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180045460  mov     rcx, [r10+10h]
0x180045464  mov     edx, 1Bh
0x180045469  mov     r9, rax
0x18004546c  mov     [rsp+78h+var_58], ebx
0x180045470  mov     r8, rbp
0x180045473  call    WPP_SF_sd
0x180045478  mov     eax, ebx
0x18004547a  mov     rcx, [rsp+78h+var_20]
0x18004547f  xor     rcx, rsp; StackCookie
0x180045482  call    __security_check_cookie
0x180045487  mov     rbx, [rsp+78h+arg_10]
0x18004548f  add     rsp, 60h
0x180045493  pop     rdi
0x180045494  pop     rsi
0x180045495  pop     rbp
0x180045496  retn
```
