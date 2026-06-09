# TsgQecNapConnectionProcessSoHResponse

- ea: `0x180005060`
- end: `0x180005210`
- name: `TsgQecNapConnectionProcessSoHResponse`
- size: `432`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, CAANapConnection *, DWORD, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800036dc`
- `0x180003970`
- `0x180005060`
- `0x1800053ec`
- `0x180005598`
- `0x180005658`
- `0x180006ac0`

## import_xrefs

- `msvcrt!free` at `0x180005202`
- `msvcrt!free` at `0x180005202`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000b369`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000b369`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000508a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000508a`
- `KERNEL32!GetLastError` at `0x180005110`
- `KERNEL32!GetLastError` at `0x180005110`

## pseudocode

```c
void __fastcall TsgQecNapConnectionProcessSoHResponse(
        struct _RPC_ASYNC_STATE *a1,
        CAANapConnection *a2,
        DWORD a3,
        unsigned __int8 *a4)
{
  __int64 v7; // rax
  signed int LastError; // eax
  int v9; // r8d
  int v10; // eax
  signed int v11; // [rsp+28h] [rbp-30h]
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  void *Block; // [rsp+38h] [rbp-20h] BYREF
  CAANapConnection *v14; // [rsp+68h] [rbp+10h] BYREF
  DWORD v15; // [rsp+70h] [rbp+18h]
  unsigned __int8 *v16; // [rsp+78h] [rbp+20h]

  v16 = a4;
  v15 = a3;
  v14 = a2;
  LODWORD(v12) = 0;
  RpcAsyncCompleteCall(a1, &v12);
  LODWORD(v14) = 0;
  Block = 0;
  v7 = *((_QWORD *)a2 + 7);
  if ( v7 )
  {
    v10 = AACertUtil::VerifyAndDecodeSoHR(
            *(const struct _CERT_CONTEXT **)(**(_QWORD **)(**(_QWORD **)(v7 + 16) + 16LL) + 8LL),
            a3,
            a4,
            (unsigned int *)&v14,
            (unsigned __int8 **)&Block);
    if ( v10 >= 0 )
    {
      CAANapConnection::ProcessSoHResponse(a2, (unsigned int)v14, (unsigned __int8 *)Block);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)&WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
        (unsigned int)L"AACertUtil::VerifyAndDecodeSoHR",
        v10);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = LastError;
      WPP_SF_SSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        v9,
        (unsigned int)L"pCCert",
        (__int64)L"CAANapConnection::GetCertChain",
        v11,
        v12);
    }
  }
  if ( Block )
    free(Block);
}

```

## disassembly

```asm
0x180005060  mov     rax, rsp
0x180005063  mov     [rax+20h], r9
0x180005067  mov     [rax+18h], r8d
0x18000506b  mov     [rax+10h], rdx
0x18000506f  push    rbx
0x180005070  push    rsi
0x180005071  push    rdi
0x180005072  sub     rsp, 40h
0x180005076  mov     rdi, r9
0x180005079  mov     esi, r8d
0x18000507c  mov     rbx, rdx
0x18000507f  mov     dword ptr [rax-28h], 0
0x180005086  lea     rdx, [rax-28h]; Reply
0x18000508a  call    cs:__imp_RpcAsyncCompleteCall
0x180005090  jmp     short loc_1800050F6
0x180005092  mov     ebx, eax
0x180005094  test    eax, eax
0x180005096  jle     short loc_1800050A1
0x180005098  movzx   ebx, ax
0x18000509b  or      ebx, 80070000h
0x1800050a1  lea     rcx, WPP_GLOBAL_Control
0x1800050a8  mov     rax, cs:WPP_GLOBAL_Control
0x1800050af  cmp     rax, rcx
0x1800050b2  jz      short loc_1800050E8
0x1800050b4  test    byte ptr [rax+1Ch], 1
0x1800050b8  jz      short loc_1800050E8
0x1800050ba  cmp     byte ptr [rax+19h], 2
0x1800050be  jb      short loc_1800050E8
0x1800050c0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800050c5  mov     edx, 25h ; '%'
0x1800050ca  mov     dword ptr [rsp+58h+var_38], ebx
0x1800050ce  mov     r9d, eax
0x1800050d1  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x1800050d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050df  mov     rcx, [rcx+10h]
0x1800050e3  call    WPP_SF_Dd
0x1800050e8  mov     rdi, [rsp+58h+arg_18]
0x1800050ed  mov     esi, [rsp+58h+arg_10]
0x1800050f1  mov     rbx, [rsp+58h+arg_8]
0x1800050f6  mov     dword ptr [rsp+58h+arg_8], 0
0x1800050fe  mov     [rsp+58h+Block], 0
0x180005107  mov     rax, [rbx+38h]
0x18000510b  test    rax, rax
0x18000510e  jnz     short loc_180005177
0x180005110  call    cs:__imp_GetLastError
0x180005116  test    eax, eax
0x180005118  jle     short loc_180005122
0x18000511a  movzx   eax, ax
0x18000511d  or      eax, 80070000h
0x180005122  lea     rdx, WPP_GLOBAL_Control
0x180005129  mov     rcx, cs:WPP_GLOBAL_Control
0x180005130  cmp     rcx, rdx
0x180005133  jz      loc_1800051F8
0x180005139  test    byte ptr [rcx+1Ch], 8
0x18000513d  jz      loc_1800051F8
0x180005143  cmp     byte ptr [rcx+19h], 2
0x180005147  jb      loc_1800051F8
0x18000514d  mov     edx, 26h ; '&'
0x180005152  mov     [rsp+58h+var_30], eax
0x180005156  lea     rax, aCaanapconnecti; "CAANapConnection::GetCertChain"
0x18000515d  mov     [rsp+58h+var_38], rax
0x180005162  lea     r9, aPccert; "pCCert"
0x180005169  mov     rcx, [rcx+10h]
0x18000516d  call    WPP_SF_SSd
0x180005172  jmp     loc_1800051F8
0x180005177  mov     rax, [rax+10h]
0x18000517b  mov     rcx, [rax]
0x18000517e  mov     rax, [rcx+10h]
0x180005182  mov     rcx, [rax]
0x180005185  lea     rax, [rsp+58h+Block]
0x18000518a  mov     [rsp+58h+var_38], rax; unsigned __int8 **
0x18000518f  lea     r9, [rsp+58h+arg_8]; unsigned int *
0x180005194  mov     r8, rdi; unsigned __int8 *
0x180005197  mov     edx, esi; unsigned int
0x180005199  mov     rcx, [rcx+8]; struct _CERT_CONTEXT *
0x18000519d  call    ?VerifyAndDecodeSoHR@AACertUtil@@SAJPEBU_CERT_CONTEXT@@KPEAEPEAKPEAPEAE@Z; AACertUtil::VerifyAndDecodeSoHR(_CERT_CONTEXT const *,ulong,uchar *,ulong *,uchar * *)
0x1800051a2  test    eax, eax
0x1800051a4  jns     short loc_1800051E7
0x1800051a6  lea     rdx, WPP_GLOBAL_Control
0x1800051ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051b4  cmp     rcx, rdx
0x1800051b7  jz      short loc_1800051F8
0x1800051b9  test    byte ptr [rcx+1Ch], 8
0x1800051bd  jz      short loc_1800051F8
0x1800051bf  cmp     byte ptr [rcx+19h], 2
0x1800051c3  jb      short loc_1800051F8
0x1800051c5  mov     edx, 27h ; '''
0x1800051ca  mov     dword ptr [rsp+58h+var_38], eax
0x1800051ce  lea     r9, aAacertutilVeri; "AACertUtil::VerifyAndDecodeSoHR"
0x1800051d5  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x1800051dc  mov     rcx, [rcx+10h]
0x1800051e0  call    WPP_SF_Sd
0x1800051e5  jmp     short loc_1800051F8
0x1800051e7  mov     r8, [rsp+58h+Block]; unsigned __int8 *
0x1800051ec  mov     edx, dword ptr [rsp+58h+arg_8]; unsigned int
0x1800051f0  mov     rcx, rbx; this
0x1800051f3  call    ?ProcessSoHResponse@CAANapConnection@@QEAAJKPEAE@Z; CAANapConnection::ProcessSoHResponse(ulong,uchar *)
0x1800051f8  mov     rcx, [rsp+58h+Block]; Block
0x1800051fd  test    rcx, rcx
0x180005200  jz      short loc_180005208
0x180005202  call    cs:__imp_free
0x180005208  add     rsp, 40h
0x18000520c  pop     rdi
0x18000520d  pop     rsi
0x18000520e  pop     rbx
0x18000520f  retn
0x18000b35b  push    rbp
0x18000b35d  sub     rsp, 30h
0x18000b361  mov     rbp, rdx
0x18000b364  mov     rcx, [rcx]
0x18000b367  mov     ecx, [rcx]; ExceptionCode
0x18000b369  call    cs:__imp_I_RpcExceptionFilter
0x18000b36f  nop
0x18000b370  add     rsp, 30h
0x18000b374  pop     rbp
0x18000b375  retn
```
