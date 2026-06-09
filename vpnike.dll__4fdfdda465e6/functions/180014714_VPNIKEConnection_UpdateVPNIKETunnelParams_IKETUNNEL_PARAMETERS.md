# VPNIKEConnection::UpdateVPNIKETunnelParams(_IKETUNNEL_PARAMETERS_ &)

- ea: `0x180014714`
- end: `0x180014a7d`
- name: `?UpdateVPNIKETunnelParams@VPNIKEConnection@@IEAAXAEAU_IKETUNNEL_PARAMETERS_@@@Z`
- size: `873`
- prototype: `void __fastcall(VPNIKEConnection *__hidden this, struct _IKETUNNEL_PARAMETERS_ *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d620`
- `0x180013fa0`

## callees

- `0x180007610`
- `0x180007794`
- `0x180014714`
- `0x180014c38`
- `0x180076ca0`
- `0x180077552`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014941`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014930`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014930`

## string_xrefs

- `0x180014879`: `Invalid IP protocol type`

## pseudocode

```c
void __fastcall VPNIKEConnection::UpdateVPNIKETunnelParams(
        VPNIKEConnection *this,
        struct _IKETUNNEL_PARAMETERS_ *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v6; // r14d
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int128 *v10; // r9
  int v11; // eax
  __int64 v12; // rdx
  PVOID *v13; // rcx
  unsigned int v14; // ebx
  HANDLE ProcessHeap; // rax
  void *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int128 *v19; // r9
  int v20; // [rsp+20h] [rbp-49h]
  int v21; // [rsp+28h] [rbp-41h]
  __int128 v22; // [rsp+60h] [rbp-9h] BYREF
  int v23; // [rsp+70h] [rbp+7h] BYREF
  __int128 v24; // [rsp+74h] [rbp+Bh]
  __int128 v25; // [rsp+84h] [rbp+1Bh]
  int v26; // [rsp+94h] [rbp+2Bh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
  }
  v23 = 0;
  v26 = 0;
  v6 = -1;
  *((_BYTE *)this + 265) = *((_BYTE *)a2 + 40) & 1;
  *((_BYTE *)this + 266) = (*((_DWORD *)a2 + 10) & 2) != 0;
  *((_BYTE *)this + 267) = (*((_DWORD *)a2 + 10) & 4) != 0;
  v24 = 0;
  v25 = 0;
  v22 = 0;
  if ( *(_WORD *)a2 == 2 )
  {
    *((_BYTE *)this + 16) = 1;
    *((_DWORD *)this + 12) = *((_DWORD *)a2 + 1);
    *((_DWORD *)this + 17) = *((_DWORD *)a2 + 6);
  }
  else if ( *(_WORD *)a2 == 23 )
  {
    *((_BYTE *)this + 16) = 0;
    *(_OWORD *)((char *)this + 52) = *(_OWORD *)((char *)a2 + 4);
    *(_OWORD *)((char *)this + 72) = *(_OWORD *)((char *)a2 + 24);
  }
  else
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v23) = 0;
      v7 = *((_QWORD *)this + 14);
      if ( v7 && *(_QWORD *)(v7 + 16) )
        v8 = *(unsigned int *)(v7 + 16);
      else
        v8 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v23, v8);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v9 = *((_QWORD *)this + 14);
        LODWORD(v10) = v9 + 2120;
        if ( !v9 )
          v10 = &v22;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid IP protocol type",
          (_DWORD)v10,
          (v9 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
          (__int64)&v23);
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
    }
  }
  v11 = *((_DWORD *)a2 + 18);
  *((_DWORD *)this + 22) = v11;
  v12 = *((unsigned int *)a2 + 19);
  *((_DWORD *)this + 23) = v12;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    LOBYTE(a4) = *((_BYTE *)this + 265);
    LOBYTE(v21) = *((_BYTE *)this + 267);
    LOBYTE(v20) = *((_BYTE *)this + 266);
    WPP_SF_ccccDDdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      a3,
      a4,
      v20,
      v21,
      *((_BYTE *)this + 16),
      *((_DWORD *)this + 12),
      *((_DWORD *)this + 17),
      v11,
      v12);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_QWORD *)a2 + 11) )
    goto LABEL_42;
  v14 = *((_DWORD *)a2 + 20);
  ProcessHeap = GetProcessHeap();
  v16 = HeapAlloc(ProcessHeap, 8u, v14);
  *((_QWORD *)this + 35) = v16;
  if ( v16 )
  {
    memcpy_0(v16, *((const void **)a2 + 11), *((unsigned int *)a2 + 20));
    *((_DWORD *)this + 68) = *((_DWORD *)a2 + 20);
    *((_DWORD *)this + 72) = *((_DWORD *)a2 + 24);
    goto LABEL_41;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v23) = 0;
    v17 = *((_QWORD *)this + 14);
    if ( v17 && *(_QWORD *)(v17 + 16) )
      v6 = *(_DWORD *)(v17 + 16);
    ConvertPortNoToString(&v23, v6);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v18 = *((_QWORD *)this + 14);
      LODWORD(v19) = v18 + 2120;
      if ( !v18 )
        v19 = &v22;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)L"HeapAlloc() failed",
        (_DWORD)v19,
        (v18 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
        (__int64)&v23);
    }
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_42:
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 6u )
        WPP_SF_(v13[2], 29, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
      return;
    }
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids);
LABEL_41:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_42;
  }
}

```

## disassembly

```asm
0x180014714  mov     [rsp-8+arg_10], rbx
0x180014719  push    rbp
0x18001471a  push    rsi
0x18001471b  push    rdi
0x18001471c  push    r13
0x18001471e  push    r14
0x180014720  lea     rbp, [rsp-37h]
0x180014725  sub     rsp, 0A0h
0x18001472c  mov     rax, cs:__security_cookie
0x180014733  xor     rax, rsp
0x180014736  mov     [rbp+57h+var_28], rax
0x18001473a  mov     rsi, rdx
0x18001473d  mov     rdi, rcx
0x180014740  mov     rcx, cs:WPP_GLOBAL_Control
0x180014747  lea     r13, WPP_GLOBAL_Control
0x18001474e  cmp     rcx, r13
0x180014751  jz      short loc_180014774
0x180014753  test    byte ptr [rcx+1Ch], 1
0x180014757  jz      short loc_180014774
0x180014759  cmp     byte ptr [rcx+19h], 6
0x18001475d  jb      short loc_180014774
0x18001475f  mov     rcx, [rcx+10h]
0x180014763  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x18001476a  mov     edx, 19h
0x18001476f  call    WPP_SF_
0x180014774  xor     eax, eax
0x180014776  xorps   xmm0, xmm0
0x180014779  mov     [rbp+57h+var_50], eax
0x18001477c  mov     edx, 2
0x180014781  mov     [rbp+57h+var_2C], eax
0x180014784  or      r14d, 0FFFFFFFFh
0x180014788  mov     al, [rsi+28h]
0x18001478b  and     al, 1
0x18001478d  mov     [rdi+109h], al
0x180014793  mov     eax, [rsi+28h]
0x180014796  shr     eax, 1
0x180014798  and     al, 1
0x18001479a  mov     [rdi+10Ah], al
0x1800147a0  mov     eax, [rsi+28h]
0x1800147a3  shr     eax, 2
0x1800147a6  and     al, 1
0x1800147a8  mov     [rdi+10Bh], al
0x1800147ae  movups  [rbp+57h+var_4C], xmm0
0x1800147b2  movups  [rbp+57h+var_3C], xmm0
0x1800147b6  movups  [rbp+57h+var_60], xmm0
0x1800147ba  cmp     dx, [rsi]
0x1800147bd  jnz     short loc_1800147D4
0x1800147bf  mov     byte ptr [rdi+10h], 1
0x1800147c3  mov     eax, [rsi+4]
0x1800147c6  mov     [rdi+30h], eax
0x1800147c9  mov     eax, [rsi+18h]
0x1800147cc  mov     [rdi+44h], eax
0x1800147cf  jmp     loc_1800148B6
0x1800147d4  mov     eax, 17h
0x1800147d9  cmp     ax, [rsi]
0x1800147dc  jnz     short loc_1800147F9
0x1800147de  mov     byte ptr [rdi+10h], 0
0x1800147e2  movups  xmm0, xmmword ptr [rsi+4]
0x1800147e6  movdqu  xmmword ptr [rdi+34h], xmm0
0x1800147eb  movups  xmm1, xmmword ptr [rsi+18h]
0x1800147ef  movdqu  xmmword ptr [rdi+48h], xmm1
0x1800147f4  jmp     loc_1800148B6
0x1800147f9  test    cs:byte_1800AA941, 4
0x180014800  jz      loc_18001488A
0x180014806  xor     eax, eax
0x180014808  mov     word ptr [rbp+57h+var_50], ax
0x18001480c  mov     rax, [rdi+70h]
0x180014810  test    rax, rax
0x180014813  jz      short loc_180014821
0x180014815  cmp     qword ptr [rax+10h], 0
0x18001481a  jz      short loc_180014821
0x18001481c  mov     edx, [rax+10h]
0x18001481f  jmp     short loc_180014824
0x180014821  mov     edx, r14d
0x180014824  lea     rcx, [rbp+57h+var_50]
0x180014828  call    ConvertPortNoToString
0x18001482d  test    cs:byte_1800AA941, 4
0x180014834  jz      short loc_180014885
0x180014836  mov     rdx, [rdi+70h]
0x18001483a  mov     rax, rdx
0x18001483d  neg     rax
0x180014840  sbb     r8, r8
0x180014843  lea     rcx, [rdx+0A7Eh]
0x18001484a  and     r8, rcx
0x18001484d  lea     r9, [rdx+848h]
0x180014854  test    rdx, rdx
0x180014857  jnz     short loc_18001485D
0x180014859  lea     r9, [rbp+57h+var_60]
0x18001485d  lea     rax, [rbp+57h+var_50]
0x180014861  mov     [rsp+0C0h+var_98], rax
0x180014866  lea     rdx, RasVpnIkeParamTraceError
0x18001486d  mov     [rsp+0C0h+var_A0], r8
0x180014872  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014879  lea     r8, aInvalidIpProto; "Invalid IP protocol type"
0x180014880  call    McTemplateU0zjzz_EventWriteTransfer
0x180014885  mov     edx, 2
0x18001488a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014891  cmp     rcx, r13
0x180014894  jz      short loc_1800148B6
0x180014896  test    byte ptr [rcx+1Ch], 1
0x18001489a  jz      short loc_1800148B6
0x18001489c  cmp     [rcx+19h], dl
0x18001489f  jb      short loc_1800148B6
0x1800148a1  mov     rcx, [rcx+10h]
0x1800148a5  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x1800148ac  mov     edx, 1Ah
0x1800148b1  call    WPP_SF_
0x1800148b6  mov     eax, [rsi+48h]
0x1800148b9  mov     [rdi+58h], eax
0x1800148bc  mov     edx, [rsi+4Ch]
0x1800148bf  mov     [rdi+5Ch], edx
0x1800148c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148c9  cmp     rcx, r13
0x1800148cc  jz      short loc_180014922
0x1800148ce  test    byte ptr [rcx+1Ch], 1
0x1800148d2  jz      short loc_180014922
0x1800148d4  cmp     byte ptr [rcx+19h], 5
0x1800148d8  jb      short loc_180014922
0x1800148da  mov     r9b, [rdi+109h]
0x1800148e1  mov     rcx, [rcx+10h]
0x1800148e5  mov     [rsp+0C0h+var_70], edx
0x1800148e9  mov     [rsp+0C0h+var_78], eax
0x1800148ed  mov     eax, [rdi+44h]
0x1800148f0  mov     [rsp+0C0h+var_80], eax
0x1800148f4  mov     eax, [rdi+30h]
0x1800148f7  mov     [rsp+0C0h+var_88], eax
0x1800148fb  mov     al, [rdi+10h]
0x1800148fe  mov     [rsp+0C0h+var_90], al
0x180014902  mov     al, [rdi+10Bh]
0x180014908  mov     byte ptr [rsp+0C0h+var_98], al
0x18001490c  mov     al, [rdi+10Ah]
0x180014912  mov     byte ptr [rsp+0C0h+var_A0], al
0x180014916  call    WPP_SF_ccccDDdd
0x18001491b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014922  cmp     qword ptr [rsi+58h], 0
0x180014927  jz      loc_180014A34
0x18001492d  mov     ebx, [rsi+50h]
0x180014930  call    cs:__imp_GetProcessHeap
0x180014936  mov     r8d, ebx; dwBytes
0x180014939  mov     edx, 8; dwFlags
0x18001493e  mov     rcx, rax; hHeap
0x180014941  call    cs:__imp_HeapAlloc
0x180014947  mov     [rdi+118h], rax
0x18001494e  test    rax, rax
0x180014951  jnz     loc_180014A0B
0x180014957  test    cs:byte_1800AA941, 4
0x18001495e  jz      short loc_1800149DC
0x180014960  mov     word ptr [rbp+57h+var_50], ax
0x180014964  mov     rax, [rdi+70h]
0x180014968  test    rax, rax
0x18001496b  jz      short loc_180014978
0x18001496d  cmp     qword ptr [rax+10h], 0
0x180014972  jz      short loc_180014978
0x180014974  mov     r14d, [rax+10h]
0x180014978  mov     edx, r14d
0x18001497b  lea     rcx, [rbp+57h+var_50]
0x18001497f  call    ConvertPortNoToString
0x180014984  test    cs:byte_1800AA941, 4
0x18001498b  jz      short loc_1800149DC
0x18001498d  mov     rdx, [rdi+70h]
0x180014991  mov     rax, rdx
0x180014994  neg     rax
0x180014997  sbb     r8, r8
0x18001499a  lea     rcx, [rdx+0A7Eh]
0x1800149a1  and     r8, rcx
0x1800149a4  lea     r9, [rdx+848h]
0x1800149ab  test    rdx, rdx
0x1800149ae  jnz     short loc_1800149B4
0x1800149b0  lea     r9, [rbp+57h+var_60]
0x1800149b4  lea     rax, [rbp+57h+var_50]
0x1800149b8  mov     [rsp+0C0h+var_98], rax
0x1800149bd  lea     rdx, RasVpnIkeParamTraceError
0x1800149c4  mov     [rsp+0C0h+var_A0], r8
0x1800149c9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800149d0  lea     r8, aHeapallocFaile; "HeapAlloc() failed"
0x1800149d7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800149dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149e3  cmp     rcx, r13
0x1800149e6  jz      short loc_180014A5A
0x1800149e8  test    byte ptr [rcx+1Ch], 1
0x1800149ec  jz      short loc_180014A34
0x1800149ee  cmp     byte ptr [rcx+19h], 2
0x1800149f2  jb      short loc_180014A34
0x1800149f4  mov     rcx, [rcx+10h]
0x1800149f8  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x1800149ff  mov     edx, 1Ch
0x180014a04  call    WPP_SF_
0x180014a09  jmp     short loc_180014A2D
0x180014a0b  mov     r8d, [rsi+50h]; Size
0x180014a0f  mov     rcx, rax; void *
0x180014a12  mov     rdx, [rsi+58h]; Src
0x180014a16  call    memcpy_0
0x180014a1b  mov     eax, [rsi+50h]
0x180014a1e  mov     [rdi+110h], eax
0x180014a24  mov     eax, [rsi+60h]
0x180014a27  mov     [rdi+120h], eax
0x180014a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a34  cmp     rcx, r13
0x180014a37  jz      short loc_180014A5A
0x180014a39  test    byte ptr [rcx+1Ch], 1
0x180014a3d  jz      short loc_180014A5A
0x180014a3f  cmp     byte ptr [rcx+19h], 6
0x180014a43  jb      short loc_180014A5A
0x180014a45  mov     rcx, [rcx+10h]
0x180014a49  lea     r8, WPP_47a6ae5b210b32534ec1487e7a271f5a_Traceguids
0x180014a50  mov     edx, 1Dh
0x180014a55  call    WPP_SF_
0x180014a5a  mov     rcx, [rbp+57h+var_28]
0x180014a5e  xor     rcx, rsp; StackCookie
0x180014a61  call    __security_check_cookie
0x180014a66  mov     rbx, [rsp+0C0h+arg_10]
0x180014a6e  add     rsp, 0A0h
0x180014a75  pop     r14
0x180014a77  pop     r13
0x180014a79  pop     rdi
0x180014a7a  pop     rsi
0x180014a7b  pop     rbp
0x180014a7c  retn
```
