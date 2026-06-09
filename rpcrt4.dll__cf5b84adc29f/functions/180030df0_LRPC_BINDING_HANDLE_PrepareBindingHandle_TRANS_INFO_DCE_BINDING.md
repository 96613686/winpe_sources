# LRPC_BINDING_HANDLE::PrepareBindingHandle(TRANS_INFO *,DCE_BINDING *)

- ea: `0x180030df0`
- end: `0x180031107`
- name: `?PrepareBindingHandle@LRPC_BINDING_HANDLE@@UEAAJPEAVTRANS_INFO@@PEAVDCE_BINDING@@@Z`
- size: `791`
- prototype: `__int64 __fastcall(LRPC_BINDING_HANDLE *__hidden this, struct TRANS_INFO *, struct DCE_BINDING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180022fb8`
- `0x180028670`
- `0x1800295d8`
- `0x18002f480`
- `0x18002fff0`
- `0x180030df0`
- `0x180031110`
- `0x1800a1b88`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180031025`
- `ntdll!RtlLeaveCriticalSection` at `0x180031025`
- `ntdll!RtlEnterCriticalSection` at `0x180030f90`
- `ntdll!RtlEnterCriticalSection` at `0x180030f90`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800310aa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800310aa`

## pseudocode

```c
__int64 __fastcall LRPC_BINDING_HANDLE::PrepareBindingHandle(
        LRPC_BINDING_HANDLE *this,
        struct TRANS_INFO *a2,
        struct DCE_BINDING *a3)
{
  unsigned __int16 *v3; // rdi
  _WORD *v6; // rcx
  _WORD *v7; // rax
  unsigned int i; // ecx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // edi
  char v14; // [rsp+90h] [rbp-80h] BYREF
  char v15; // [rsp+98h] [rbp-78h] BYREF
  __int64 v16; // [rsp+A0h] [rbp-70h] BYREF
  int v17; // [rsp+A8h] [rbp-68h]
  LRPC_BINDING_HANDLE *v18; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v19; // [rsp+B8h] [rbp-58h] BYREF
  char v20[16]; // [rsp+C0h] [rbp-50h] BYREF
  char *v21; // [rsp+D0h] [rbp-40h]
  __int64 v22; // [rsp+D8h] [rbp-38h]
  char *v23; // [rsp+E0h] [rbp-30h]
  __int64 v24; // [rsp+E8h] [rbp-28h]
  LRPC_BINDING_HANDLE **v25; // [rsp+F0h] [rbp-20h]
  __int64 v26; // [rsp+F8h] [rbp-18h]
  __int64 *v27; // [rsp+100h] [rbp-10h]
  __int64 v28; // [rsp+108h] [rbp-8h]
  __int64 *v29; // [rsp+110h] [rbp+0h]
  __int64 v30; // [rsp+118h] [rbp+8h]

  v3 = (unsigned __int16 *)*((_QWORD *)a3 + 1);
  v16 = 0;
  v17 = 0;
  if ( v3 && *v3 && CompareStringW(0x7Fu, 1u, v3, -1, gLocalComputerName, -1) != 2 )
  {
    RpcpErrorAddRecord(2u, 1707, 0x3A3u, v3, (unsigned __int16 *)gLocalComputerName);
    return 1707;
  }
  v6 = (_WORD *)*((_QWORD *)a3 + 3);
  if ( v6 && *v6 )
  {
    v11 = I_RpcParseSecurity(v6, &v16);
    v12 = v11;
    if ( v11 )
    {
      RpcpErrorAddRecord(2u, v11, 0x3A2u, 0, 0);
      return v12;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
    v13 = 3;
    if ( HIDWORD(v16) <= 3 )
      v13 = dword_1800E7D60[SHIDWORD(v16)];
    LRPC_BINDING_HANDLE::Unbind(this, 1);
    v12 = LRPC_BASE_BINDING_HANDLE::SetAuthInformation(
            this,
            0,
            6u,
            10,
            0,
            0,
            0,
            0,
            v13,
            (unsigned __int8)v17,
            0,
            1u,
            0,
            0,
            0,
            BYTE1(v17),
            0,
            0);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
    if ( v12 )
      return v12;
  }
  *((_QWORD *)this + 77) = a3;
  v7 = (_WORD *)*((_QWORD *)a3 + 2);
  if ( v7 && *v7 )
  {
    if ( dword_1800FE624 )
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 104 )
          goto LABEL_13;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v10 = (int)(*((_DWORD *)this + 99) << 16);
        v21 = &v14;
        v16 = v10 | 4;
        v23 = &v15;
        v26 = 8;
        v25 = &v18;
        v27 = &v19;
        v29 = &v16;
        v28 = 8;
        v30 = 8;
        v19 = 34;
        v18 = this;
        v15 = 61;
        v14 = 104;
        v22 = 1;
        v24 = 1;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          (_DWORD)a3,
          6,
          (__int64)v20);
      }
    }
LABEL_13:
    *((_DWORD *)this + 99) = 4;
  }
  else
  {
    if ( dword_1800FE624 )
      LogEventToEtw(0x68u, 0x3Du, (__int64)this, 34, (int)(*((_DWORD *)this + 99) << 16) | 1LL);
    *((_DWORD *)this + 99) = 1;
    *((_DWORD *)this + 124) |= 0x10u;
  }
  return 0;
}

```

## disassembly

```asm
0x180030df0  mov     [rsp-8+arg_8], rbx
0x180030df5  push    rbp
0x180030df6  push    rsi
0x180030df7  push    rdi
0x180030df8  push    r12
0x180030dfa  push    r13
0x180030dfc  push    r14
0x180030dfe  push    r15
0x180030e00  lea     rbp, [rsp-20h]
0x180030e05  sub     rsp, 130h
0x180030e0c  mov     rax, cs:__security_cookie
0x180030e13  xor     rax, rsp
0x180030e16  mov     [rbp+50h+var_40], rax
0x180030e1a  mov     rdi, [r8+8]
0x180030e1e  xor     eax, eax
0x180030e20  xor     r15d, r15d
0x180030e23  mov     [rbp+50h+var_C0], rax
0x180030e27  mov     [rbp+50h+var_B8], eax
0x180030e2a  mov     rsi, r8
0x180030e2d  mov     rbx, rcx
0x180030e30  lea     r12d, [rax+1]
0x180030e34  lea     r14d, [rax+2]
0x180030e38  test    rdi, rdi
0x180030e3b  jz      short loc_180030E47
0x180030e3d  cmp     [rdi], r15w
0x180030e41  jnz     loc_18003108A
0x180030e47  mov     rcx, [rsi+18h]
0x180030e4b  lea     r13, __ImageBase
0x180030e52  test    rcx, rcx
0x180030e55  jnz     loc_180030F69
0x180030e5b  mov     [rbx+268h], rsi
0x180030e62  mov     rax, [rsi+10h]
0x180030e66  test    rax, rax
0x180030e69  jz      loc_180031040
0x180030e6f  cmp     [rax], r15w
0x180030e73  jz      loc_180031040
0x180030e79  cmp     cs:dword_1800FE624, r15d
0x180030e80  jz      short loc_180030EAA
0x180030e82  mov     ecx, r15d
0x180030e85  cmp     ecx, 4
0x180030e88  jnb     short loc_180030E9D
0x180030e8a  movsxd  rax, ecx
0x180030e8d  cmp     byte ptr [rax+r13+0E66D8h], 68h ; 'h'
0x180030e96  jz      short loc_180030EAA
0x180030e98  add     ecx, r12d
0x180030e9b  jmp     short loc_180030E85
0x180030e9d  mov     edx, 8
0x180030ea2  test    cs:Microsoft_Windows_RPCEnableBits, dl
0x180030ea8  jnz     short loc_180030EDE
0x180030eaa  mov     dword ptr [rbx+18Ch], 4
0x180030eb4  xor     eax, eax
0x180030eb6  mov     rcx, [rbp+50h+var_40]
0x180030eba  xor     rcx, rsp; StackCookie
0x180030ebd  call    __security_check_cookie
0x180030ec2  mov     rbx, [rsp+160h+arg_8]
0x180030eca  add     rsp, 130h
0x180030ed1  pop     r15
0x180030ed3  pop     r14
0x180030ed5  pop     r13
0x180030ed7  pop     r12
0x180030ed9  pop     rdi
0x180030eda  pop     rsi
0x180030edb  pop     rbp
0x180030edc  retn
0x180030ede  mov     eax, [rbx+18Ch]
0x180030ee4  mov     r9d, 6
0x180030eea  shl     eax, 10h
0x180030eed  movsxd  rcx, eax
0x180030ef0  lea     rax, [rbp+50h+var_D0]
0x180030ef4  mov     [rbp+50h+var_90], rax
0x180030ef8  or      rcx, 4
0x180030efc  lea     rax, [rbp+50h+var_C8]
0x180030f00  mov     [rbp+50h+var_C0], rcx
0x180030f04  mov     [rbp+50h+var_80], rax
0x180030f08  lea     rcx, RpcEtwGuid_Context
0x180030f0f  lea     rax, [rbp+50h+var_B0]
0x180030f13  mov     [rbp+50h+var_68], rdx
0x180030f17  mov     [rbp+50h+var_70], rax
0x180030f1b  lea     rax, [rbp+50h+var_A8]
0x180030f1f  mov     [rbp+50h+var_60], rax
0x180030f23  lea     rax, [rbp+50h+var_C0]
0x180030f27  mov     [rbp+50h+var_50], rax
0x180030f2b  lea     rax, [rbp+50h+var_A0]
0x180030f2f  mov     [rbp+50h+var_58], rdx
0x180030f33  mov     [rbp+50h+var_48], rdx
0x180030f37  lea     rdx, RPCLogEvent
0x180030f3e  mov     [rsp+160h+lpString2], rax
0x180030f43  mov     [rbp+50h+var_A8], 22h ; '"'
0x180030f4b  mov     [rbp+50h+var_B0], rbx
0x180030f4f  mov     [rbp+50h+var_C8], 3Dh ; '='
0x180030f53  mov     [rbp+50h+var_D0], 68h ; 'h'
0x180030f57  mov     [rbp+50h+var_88], r12
0x180030f5b  mov     [rbp+50h+var_78], r12
0x180030f5f  call    McGenEventWrite_EtwEventWriteTransfer
0x180030f64  jmp     loc_180030EAA
0x180030f69  cmp     [rcx], r15w
0x180030f6d  jz      loc_180030E5B
0x180030f73  lea     rdx, [rbp+50h+var_C0]
0x180030f77  call    I_RpcParseSecurity
0x180030f7c  mov     edi, eax
0x180030f7e  test    eax, eax
0x180030f80  jnz     loc_1800310EA
0x180030f86  lea     r14, [rbx+130h]
0x180030f8d  mov     rcx, r14; CriticalSection
0x180030f90  call    cs:__imp_RtlEnterCriticalSection
0x180030f97  nop     dword ptr [rax+rax+00h]
0x180030f9c  mov     edi, 3
0x180030fa1  cmp     dword ptr [rbp+50h+var_C0+4], edi
0x180030fa4  ja      short loc_180030FB2
0x180030fa6  movsxd  rax, dword ptr [rbp+50h+var_C0+4]
0x180030faa  mov     edi, ds:rva dword_1800E7D60[r13+rax*4]
0x180030fb2  mov     edx, r12d; int
0x180030fb5  mov     rcx, rbx; this
0x180030fb8  call    ?Unbind@LRPC_BINDING_HANDLE@@UEAAXH@Z; LRPC_BINDING_HANDLE::Unbind(int)
0x180030fbd  movzx   eax, byte ptr [rbp+50h+var_B8+1]
0x180030fc1  mov     rcx, rbx; this
0x180030fc4  movzx   edx, byte ptr [rbp+50h+var_B8]
0x180030fc8  mov     [rsp+160h+CreatorDescriptor], r15; CreatorDescriptor
0x180030fd0  mov     [rsp+160h+var_E0], r15d; int
0x180030fd8  mov     [rsp+160h+var_E8], eax; int
0x180030fdc  mov     [rsp+160h+pSourceSid], r15; pSourceSid
0x180030fe1  mov     [rsp+160h+var_F8], r15; void *
0x180030fe6  mov     [rsp+160h+var_100], r15d; unsigned int
0x180030feb  mov     [rsp+160h+var_108], r12d; unsigned int
0x180030ff0  mov     [rsp+160h+var_110], r15d; unsigned int
0x180030ff5  mov     [rsp+160h+var_118], edx; unsigned int
0x180030ff9  xor     edx, edx; unsigned __int16 *
0x180030ffb  mov     [rsp+160h+var_120], edi; unsigned int
0x180030fff  mov     [rsp+160h+var_128], r15; struct SECURITY_CREDENTIALS *
0x180031004  mov     [rsp+160h+var_130], r15d; unsigned int
0x180031009  lea     r9d, [rdx+0Ah]; unsigned int
0x18003100d  mov     qword ptr [rsp+160h+cchCount2], r15; void *
0x180031012  lea     r8d, [rdx+6]; unsigned int
0x180031016  mov     [rsp+160h+lpString2], r15; AuthData
0x18003101b  call    ?SetAuthInformation@LRPC_BASE_BINDING_HANDLE@@UEAAJPEAGKKPEAX1KPEAVSECURITY_CREDENTIALS@@KKKKK11HH1@Z; LRPC_BASE_BINDING_HANDLE::SetAuthInformation(ushort *,ulong,ulong,void *,void *,ulong,SECURITY_CREDENTIALS *,ulong,ulong,ulong,ulong,ulong,void *,void *,int,int,void *)
0x180031020  mov     rcx, r14; CriticalSection
0x180031023  mov     edi, eax
0x180031025  call    cs:__imp_RtlLeaveCriticalSection
0x18003102c  nop     dword ptr [rax+rax+00h]
0x180031031  test    edi, edi
0x180031033  jz      loc_180030E5B
0x180031039  mov     eax, edi
0x18003103b  jmp     loc_180030EB6
0x180031040  cmp     cs:dword_1800FE624, r15d
0x180031047  jz      short loc_18003106F
0x180031049  mov     eax, [rbx+18Ch]
0x18003104f  mov     r9d, 22h ; '"'; __int64
0x180031055  shl     eax, 10h
0x180031058  mov     r8, rbx; __int64
0x18003105b  movsxd  rcx, eax
0x18003105e  mov     dl, 3Dh ; '='; unsigned __int8
0x180031060  or      rcx, r12
0x180031063  mov     [rsp+160h+lpString2], rcx; __int64
0x180031068  mov     cl, 68h ; 'h'; unsigned __int8
0x18003106a  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x18003106f  mov     [rbx+18Ch], r12d
0x180031076  mov     eax, [rbx+1F0h]
0x18003107c  or      eax, 10h
0x18003107f  mov     [rbx+1F0h], eax
0x180031085  jmp     loc_180030EB4
0x18003108a  mov     rax, cs:?gLocalComputerName@@3PEAGEA; ushort * gLocalComputerName
0x180031091  or      r9d, 0FFFFFFFFh; cchCount1
0x180031095  mov     [rsp+160h+cchCount2], r9d; cchCount2
0x18003109a  mov     r8, rdi; lpString1
0x18003109d  mov     edx, r12d; dwCmpFlags
0x1800310a0  mov     [rsp+160h+lpString2], rax; lpString2
0x1800310a5  mov     ecx, 7Fh; Locale
0x1800310aa  call    cs:__imp_CompareStringW
0x1800310b1  nop     dword ptr [rax+rax+00h]
0x1800310b6  cmp     eax, r14d
0x1800310b9  jz      loc_180030E47
0x1800310bf  mov     rax, cs:?gLocalComputerName@@3PEAGEA; ushort * gLocalComputerName
0x1800310c6  mov     ebx, 6ABh
0x1800310cb  mov     edx, ebx; int
0x1800310cd  mov     [rsp+160h+lpString2], rax; unsigned __int16 *
0x1800310d2  mov     r8d, 3A3h; unsigned __int16
0x1800310d8  mov     r9, rdi; unsigned __int16 *
0x1800310db  mov     ecx, r14d; unsigned int
0x1800310de  call    ?RpcpErrorAddRecord@@YAXKJGPEAG0@Z; RpcpErrorAddRecord(ulong,long,ushort,ushort *,ushort *)
0x1800310e3  mov     eax, ebx
0x1800310e5  jmp     loc_180030EB6
0x1800310ea  mov     r8d, 3A2h; unsigned __int16
0x1800310f0  mov     [rsp+160h+lpString2], r15; struct tagParam *
0x1800310f5  xor     r9d, r9d; int
0x1800310f8  mov     edx, edi; int
0x1800310fa  mov     ecx, r14d; unsigned int
0x1800310fd  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180031102  jmp     loc_180031039
```
