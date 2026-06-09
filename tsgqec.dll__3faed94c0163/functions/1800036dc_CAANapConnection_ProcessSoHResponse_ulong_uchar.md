# CAANapConnection::ProcessSoHResponse(ulong,uchar *)

- ea: `0x1800036dc`
- end: `0x18000383a`
- name: `?ProcessSoHResponse@CAANapConnection@@QEAAJKPEAE@Z`
- size: `350`
- prototype: `__int64 __fastcall(struct INapEnforcementClientConnection **this, UINT16, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180005060`

## callees

- `0x1800022e6`
- `0x1800036dc`
- `0x180003840`
- `0x1800054b8`
- `0x180005658`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800036f3`
- `ole32!CoTaskMemAlloc` at `0x180003750`
- `ole32!CoTaskMemAlloc` at `0x1800036f3`
- `ole32!CoTaskMemAlloc` at `0x180003750`
- `ole32!CoTaskMemFree` at `0x180003817`
- `ole32!CoTaskMemFree` at `0x180003828`
- `ole32!CoTaskMemFree` at `0x180003817`
- `ole32!CoTaskMemFree` at `0x180003828`

## pseudocode

```c
__int64 __fastcall CAANapConnection::ProcessSoHResponse(
        struct INapEnforcementClientConnection **this,
        UINT16 a2,
        unsigned __int8 *a3)
{
  struct tagNetworkSoH *v6; // rax
  struct tagNetworkSoH *v7; // rdi
  int v8; // ebx
  BYTE *v9; // rax
  CAANapEnforcementClientCallback *v10; // rcx
  BYTE *data; // rcx

  v6 = (struct tagNetworkSoH *)CoTaskMemAlloc(0x10u);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 0;
    v6->size = a2;
    v9 = (BYTE *)CoTaskMemAlloc(a2);
    v7->data = v9;
    if ( v9 )
    {
      memcpy_0(v9, a3, v7->size);
      v8 = CAANapEnforcementClientCallback::ProcessSoHResponse(v10, v7, *this);
      if ( v8 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)&WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
          (unsigned int)L"m_NapEnforcementCallback->ProcessSoHResponse",
          v8);
      }
      if ( v8 == -2144927743 )
        v8 = -2147001884;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
          L"networkSohResponse->data");
      }
      v8 = -2147024882;
    }
    data = v7->data;
    if ( data )
    {
      CoTaskMemFree(data);
      v7->data = 0;
    }
    CoTaskMemFree(v7);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
        L"networkSohResponse");
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800036dc  push    rbx
0x1800036de  push    rsi
0x1800036df  push    rdi
0x1800036e0  push    r14
0x1800036e2  sub     rsp, 38h
0x1800036e6  mov     r14, rcx
0x1800036e9  mov     ebx, edx
0x1800036eb  mov     ecx, 10h; cb
0x1800036f0  mov     rsi, r8
0x1800036f3  call    cs:__imp_CoTaskMemAlloc
0x1800036f9  mov     rdi, rax
0x1800036fc  test    rax, rax
0x1800036ff  jnz     short loc_180003744
0x180003701  mov     rcx, cs:WPP_GLOBAL_Control
0x180003708  lea     rax, WPP_GLOBAL_Control
0x18000370f  cmp     rcx, rax
0x180003712  jz      short loc_18000373A
0x180003714  test    byte ptr [rcx+1Ch], 8
0x180003718  jz      short loc_18000373A
0x18000371a  cmp     byte ptr [rcx+19h], 2
0x18000371e  jb      short loc_18000373A
0x180003720  mov     rcx, [rcx+10h]
0x180003724  lea     edx, [rdi+13h]
0x180003727  lea     r9, aNetworksohresp_0; "networkSohResponse"
0x18000372e  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180003735  call    WPP_SF_S
0x18000373a  mov     ebx, 8007000Eh
0x18000373f  jmp     loc_18000382E
0x180003744  xorps   xmm0, xmm0
0x180003747  movzx   ecx, bx; cb
0x18000374a  movups  xmmword ptr [rax], xmm0
0x18000374d  mov     [rax], cx
0x180003750  call    cs:__imp_CoTaskMemAlloc
0x180003756  mov     [rdi+8], rax
0x18000375a  test    rax, rax
0x18000375d  jnz     short loc_1800037A1
0x18000375f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003766  lea     rax, WPP_GLOBAL_Control
0x18000376d  cmp     rcx, rax
0x180003770  jz      short loc_18000379A
0x180003772  test    byte ptr [rcx+1Ch], 8
0x180003776  jz      short loc_18000379A
0x180003778  cmp     byte ptr [rcx+19h], 2
0x18000377c  jb      short loc_18000379A
0x18000377e  mov     rcx, [rcx+10h]
0x180003782  lea     r9, aNetworksohresp; "networkSohResponse->data"
0x180003789  mov     edx, 14h
0x18000378e  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180003795  call    WPP_SF_S
0x18000379a  mov     ebx, 8007000Eh
0x18000379f  jmp     short loc_18000380E
0x1800037a1  movzx   r8d, word ptr [rdi]; Size
0x1800037a5  mov     rdx, rsi; Src
0x1800037a8  mov     rcx, rax; void *
0x1800037ab  call    memcpy_0
0x1800037b0  mov     r8, [r14]; struct INapEnforcementClientConnection *
0x1800037b3  mov     rdx, rdi; struct tagNetworkSoH *
0x1800037b6  call    ?ProcessSoHResponse@CAANapEnforcementClientCallback@@QEAAJPEAUtagNetworkSoH@@PEAUINapEnforcementClientConnection@@@Z; CAANapEnforcementClientCallback::ProcessSoHResponse(tagNetworkSoH *,INapEnforcementClientConnection *)
0x1800037bb  mov     ebx, eax
0x1800037bd  test    eax, eax
0x1800037bf  jns     short loc_180003800
0x1800037c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037c8  lea     rax, WPP_GLOBAL_Control
0x1800037cf  cmp     rcx, rax
0x1800037d2  jz      short loc_180003800
0x1800037d4  test    byte ptr [rcx+1Ch], 8
0x1800037d8  jz      short loc_180003800
0x1800037da  cmp     byte ptr [rcx+19h], 2
0x1800037de  jb      short loc_180003800
0x1800037e0  mov     rcx, [rcx+10h]
0x1800037e4  lea     r9, aMNapenforcemen; "m_NapEnforcementCallback->ProcessSoHRes"...
0x1800037eb  mov     edx, 15h
0x1800037f0  mov     [rsp+58h+var_38], ebx
0x1800037f4  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x1800037fb  call    WPP_SF_Sd
0x180003800  cmp     ebx, 80270001h
0x180003806  mov     eax, 800759E4h
0x18000380b  cmovz   ebx, eax
0x18000380e  mov     rcx, [rdi+8]; pv
0x180003812  test    rcx, rcx
0x180003815  jz      short loc_180003825
0x180003817  call    cs:__imp_CoTaskMemFree
0x18000381d  mov     qword ptr [rdi+8], 0
0x180003825  mov     rcx, rdi; pv
0x180003828  call    cs:__imp_CoTaskMemFree
0x18000382e  mov     eax, ebx
0x180003830  add     rsp, 38h
0x180003834  pop     r14
0x180003836  pop     rdi
0x180003837  pop     rsi
0x180003838  pop     rbx
0x180003839  retn
```
