# CScriptedDiag::GetUniqueName(ushort * *)

- ea: `0x18000c910`
- end: `0x18000ca29`
- name: `?GetUniqueName@CScriptedDiag@@AEAAJPEAPEAG@Z`
- size: `281`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c3fc`

## callees

- `0x1800012a4`
- `0x18000c910`
- `0x180026fa0`
- `0x1800278d4`
- `0x1800298c0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18000c9ff`
- `RPCRT4!RpcStringFreeW` at `0x18000c9ff`
- `RPCRT4!UuidCreate` at `0x18000c96f`
- `RPCRT4!UuidCreate` at `0x18000c96f`
- `RPCRT4!UuidToStringW` at `0x18000c992`
- `RPCRT4!UuidToStringW` at `0x18000c992`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::GetUniqueName(CScriptedDiag *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rbx
  unsigned int v4; // edi
  int v5; // r8d
  int v6; // r9d
  int v7; // eax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 *v10; // [rsp+28h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-28h] BYREF

  v2 = 0;
  StringUuid = 0;
  v10 = 0;
  Uuid = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 2008;
    v6 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"CScriptedDiag::GetUniqueName", v5, v6);
    goto LABEL_11;
  }
  if ( UuidCreate(&Uuid) )
  {
    v6 = -2147467259;
    v5 = 2011;
    v4 = -2147467259;
    goto LABEL_3;
  }
  if ( UuidToStringW(&Uuid, &StringUuid) )
  {
    v6 = -2147467259;
    v5 = 2014;
    v4 = -2147467259;
    goto LABEL_3;
  }
  v7 = SdpStrCat(L"SDIAG", StringUuid, 0x5Fu, &v10);
  v4 = v7;
  if ( v7 >= 0 )
  {
    *a2 = v10;
  }
  else
  {
    SdpDebugTrace(1u, L"CScriptedDiag::GetUniqueName", 2017, v7);
    v2 = v10;
  }
LABEL_11:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( v2 )
    operator delete(v2);
  return v4;
}

```

## disassembly

```asm
0x18000c910  push    rbp
0x18000c912  push    rbx
0x18000c913  push    rsi
0x18000c914  push    rdi
0x18000c915  mov     rbp, rsp
0x18000c918  sub     rsp, 58h
0x18000c91c  mov     rax, cs:__security_cookie
0x18000c923  xor     rax, rsp
0x18000c926  mov     [rbp+var_18], rax
0x18000c92a  xor     ebx, ebx
0x18000c92c  mov     [rbp+StringUuid], 0
0x18000c934  mov     [rbp+var_30], rbx
0x18000c938  xorps   xmm0, xmm0
0x18000c93b  mov     rsi, rdx
0x18000c93e  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18000c942  test    rdx, rdx
0x18000c945  jnz     short loc_18000C96B
0x18000c947  mov     edi, 80070057h
0x18000c94c  mov     r8d, 7D8h; int
0x18000c952  mov     r9d, edi; int
0x18000c955  lea     rdx, aCscripteddiagG_10; "CScriptedDiag::GetUniqueName"
0x18000c95c  mov     ecx, 1; Level
0x18000c961  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c966  jmp     loc_18000C9F4
0x18000c96b  lea     rcx, [rbp+Uuid]; Uuid
0x18000c96f  call    cs:__imp_UuidCreate
0x18000c975  test    eax, eax
0x18000c977  jz      short loc_18000C98A
0x18000c979  mov     r9d, 80004005h
0x18000c97f  mov     r8d, 7DBh
0x18000c985  mov     edi, r9d
0x18000c988  jmp     short loc_18000C955
0x18000c98a  lea     rdx, [rbp+StringUuid]; StringUuid
0x18000c98e  lea     rcx, [rbp+Uuid]; Uuid
0x18000c992  call    cs:__imp_UuidToStringW
0x18000c998  test    eax, eax
0x18000c99a  jz      short loc_18000C9AD
0x18000c99c  mov     r9d, 80004005h
0x18000c9a2  mov     r8d, 7DEh
0x18000c9a8  mov     edi, r9d
0x18000c9ab  jmp     short loc_18000C955
0x18000c9ad  mov     rdx, [rbp+StringUuid]; unsigned __int16 *
0x18000c9b1  lea     r9, [rbp+var_30]; unsigned __int16 **
0x18000c9b5  mov     r8d, 5Fh ; '_'; unsigned __int16
0x18000c9bb  lea     rcx, aSdiag; "SDIAG"
0x18000c9c2  call    ?SdpStrCat@@YAJPEBG0GPEAPEAG@Z; SdpStrCat(ushort const *,ushort const *,ushort,ushort * *)
0x18000c9c7  mov     edi, eax
0x18000c9c9  test    eax, eax
0x18000c9cb  jns     short loc_18000C9ED
0x18000c9cd  mov     r9d, eax; int
0x18000c9d0  lea     rdx, aCscripteddiagG_10; "CScriptedDiag::GetUniqueName"
0x18000c9d7  mov     r8d, 7E1h; int
0x18000c9dd  mov     ecx, 1; Level
0x18000c9e2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c9e7  mov     rbx, [rbp+var_30]
0x18000c9eb  jmp     short loc_18000C9F4
0x18000c9ed  mov     rax, [rbp+var_30]
0x18000c9f1  mov     [rsi], rax
0x18000c9f4  cmp     [rbp+StringUuid], 0
0x18000c9f9  jz      short loc_18000CA05
0x18000c9fb  lea     rcx, [rbp+StringUuid]; String
0x18000c9ff  call    cs:__imp_RpcStringFreeW
0x18000ca05  test    rbx, rbx
0x18000ca08  jz      short loc_18000CA12
0x18000ca0a  mov     rcx, rbx; Block
0x18000ca0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ca12  mov     eax, edi
0x18000ca14  mov     rcx, [rbp+var_18]
0x18000ca18  xor     rcx, rsp; StackCookie
0x18000ca1b  call    __security_check_cookie
0x18000ca20  add     rsp, 58h
0x18000ca24  pop     rdi
0x18000ca25  pop     rsi
0x18000ca26  pop     rbx
0x18000ca27  pop     rbp
0x18000ca28  retn
```
