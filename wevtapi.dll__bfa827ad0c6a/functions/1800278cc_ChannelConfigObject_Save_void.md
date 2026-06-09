# ChannelConfigObject::Save(void)

- ea: `0x1800278cc`
- end: `0x180027a7f`
- name: `?Save@ChannelConfigObject@@QEAAXXZ`
- size: `435`
- prototype: `void __fastcall(ChannelConfigObject *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800263c0`

## callees

- `0x180006aec`
- `0x18000decc`
- `0x180023548`
- `0x180024a50`
- `0x1800278cc`
- `0x180027bac`
- `0x180038fa4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002795d`
- `RPCRT4!NdrClientCall3` at `0x18002795d`

## pseudocode

```c
void __fastcall ChannelConfigObject::Save(ChannelConfigObject *this)
{
  int v2; // edx
  int v3; // ecx
  _BYTE *v4; // r9
  char v5; // al
  unsigned int Pointer; // eax
  CLIENT_CALL_RETURN v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  __int128 pExceptionObject; // [rsp+40h] [rbp-40h] BYREF
  __int64 v11; // [rsp+50h] [rbp-30h]
  unsigned int v12; // [rsp+58h] [rbp-28h]
  int v13; // [rsp+5Ch] [rbp-24h]
  int v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h] BYREF
  int v16; // [rsp+70h] [rbp-10h]

  v15 = 0;
  v16 = 0;
  LastErrInfo::Reset(this);
  v4 = (_BYTE *)*((_QWORD *)this + 5);
  if ( (v4[4] & 1) != 0 && (byte_18004B801 & 4) != 0 )
  {
    v5 = v4[8];
    LOBYTE(v4) = v4[56];
    McTemplateU0zut_EventWriteTransfer(v3, v2, *((_QWORD *)this + 7), (_DWORD)v4, v5);
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x15u,
                            0,
                            *(_QWORD *)(*((_QWORD *)this + 6) + 72LL),
                            *((_QWORD *)this + 7),
                            *((_DWORD *)this + 28),
                            (char *)this + 32,
                            &v15).Pointer;
  v8 = Pointer;
  if ( Pointer )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids, Pointer);
    }
    v11 = 0;
    v12 = v8;
    v13 = -1;
    pExceptionObject = 0;
    v14 = 157;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (_DWORD)v15 )
  {
    LastErrInfo::Set((LastErrInfo *)v7.Pointer, (struct tag_RpcInfo *)&v15);
    v9 = v15;
    if ( !(_DWORD)v15 )
      v9 = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids, v9);
    }
    v11 = 0;
    v12 = v9;
    v13 = -1;
    pExceptionObject = 0;
    v14 = 163;
    throw (EvtException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800278cc  mov     [rsp-8+arg_8], rbx
0x1800278d1  push    rbp
0x1800278d2  mov     rbp, rsp
0x1800278d5  sub     rsp, 80h
0x1800278dc  mov     rax, cs:__security_cookie
0x1800278e3  xor     rax, rsp
0x1800278e6  mov     [rbp+var_8], rax
0x1800278ea  xor     eax, eax
0x1800278ec  mov     rbx, rcx
0x1800278ef  mov     [rbp+var_18], rax
0x1800278f3  mov     [rbp+var_10], eax
0x1800278f6  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x1800278fb  mov     r9, [rbx+28h]
0x1800278ff  test    byte ptr [r9+4], 1
0x180027904  jz      short loc_180027925
0x180027906  test    cs:byte_18004B801, 4
0x18002790d  jz      short loc_180027925
0x18002790f  movzx   eax, byte ptr [r9+8]
0x180027914  mov     r9b, [r9+38h]
0x180027918  mov     r8, [rbx+38h]
0x18002791c  mov     dword ptr [rsp+80h+var_60], eax
0x180027920  call    McTemplateU0zut_EventWriteTransfer
0x180027925  mov     r9, [rbx+30h]
0x180027929  lea     rax, [rbx+20h]
0x18002792d  lea     rcx, [rbp+var_18]
0x180027931  xor     r8d, r8d; pReturnValue
0x180027934  mov     [rsp+80h+var_48], rcx
0x180027939  lea     rcx, pProxyInfo; pProxyInfo
0x180027940  mov     [rsp+80h+var_50], rax
0x180027945  mov     eax, [rbx+70h]
0x180027948  mov     r9, [r9+48h]
0x18002794c  lea     edx, [r8+15h]; nProcNum
0x180027950  mov     [rsp+80h+var_58], eax
0x180027954  mov     rax, [rbx+38h]
0x180027958  mov     [rsp+80h+var_60], rax
0x18002795d  call    cs:__imp_NdrClientCall3
0x180027963  mov     rbx, rax
0x180027966  test    eax, eax
0x180027968  jz      short loc_1800279D6
0x18002796a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027971  lea     rdx, WPP_GLOBAL_Control
0x180027978  cmp     rcx, rdx
0x18002797b  jz      short loc_1800279A4
0x18002797d  test    dword ptr [rcx+1Ch], 40000h
0x180027984  jz      short loc_1800279A4
0x180027986  cmp     byte ptr [rcx+19h], 2
0x18002798a  jb      short loc_1800279A4
0x18002798c  mov     rcx, [rcx+10h]
0x180027990  lea     r8, WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids
0x180027997  mov     edx, 0Dh
0x18002799c  mov     r9d, ebx
0x18002799f  call    WPP_SF_D
0x1800279a4  xorps   xmm0, xmm0
0x1800279a7  mov     [rbp+var_30], 0
0x1800279af  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800279b6  mov     [rbp+var_28], ebx
0x1800279b9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800279bd  mov     [rbp+var_24], 0FFFFFFFFh
0x1800279c4  movdqu  [rbp+pExceptionObject], xmm0
0x1800279c9  mov     [rbp+var_20], 9Dh
0x1800279d0  call    _CxxThrowException_0
0x1800279d6  cmp     dword ptr [rbp+var_18], 0
0x1800279da  jz      loc_180027A62
0x1800279e0  lea     rdx, [rbp+var_18]; struct tag_RpcInfo *
0x1800279e4  call    ?Set@LastErrInfo@@QEAAXAEAUtag_RpcInfo@@@Z; LastErrInfo::Set(tag_RpcInfo &)
0x1800279e9  mov     ebx, dword ptr [rbp+var_18]
0x1800279ec  mov     eax, 507h
0x1800279f1  test    ebx, ebx
0x1800279f3  cmovz   ebx, eax
0x1800279f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279fd  lea     rdx, WPP_GLOBAL_Control
0x180027a04  cmp     rcx, rdx
0x180027a07  jz      short loc_180027A30
0x180027a09  test    dword ptr [rcx+1Ch], 40000h
0x180027a10  jz      short loc_180027A30
0x180027a12  cmp     byte ptr [rcx+19h], 2
0x180027a16  jb      short loc_180027A30
0x180027a18  mov     rcx, [rcx+10h]
0x180027a1c  lea     r8, WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids
0x180027a23  mov     edx, 0Eh
0x180027a28  mov     r9d, ebx
0x180027a2b  call    WPP_SF_D
0x180027a30  xorps   xmm0, xmm0
0x180027a33  mov     [rbp+var_30], 0
0x180027a3b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180027a42  mov     [rbp+var_28], ebx
0x180027a45  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027a49  mov     [rbp+var_24], 0FFFFFFFFh
0x180027a50  movdqu  [rbp+pExceptionObject], xmm0
0x180027a55  mov     [rbp+var_20], 0A3h
0x180027a5c  call    _CxxThrowException_0
0x180027a62  mov     rcx, [rbp+var_8]
0x180027a66  xor     rcx, rsp; StackCookie
0x180027a69  call    __security_check_cookie
0x180027a6e  mov     rbx, [rsp+80h+arg_8]
0x180027a76  add     rsp, 80h
0x180027a7d  pop     rbp
0x180027a7e  retn
```
