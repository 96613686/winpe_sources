# OpenExternalEtlFile

- ea: `0x180077be8`
- end: `0x180077dd5`
- name: `OpenExternalEtlFile`
- size: `493`
- prototype: `volatile signed __int32 **__fastcall(volatile signed __int32 **, const wchar_t **, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800762f8`

## callees

- `0x18000a180`
- `0x180016250`
- `0x1800613d8`
- `0x180077be8`
- `0x18008cc24`
- `0x180092008`
- `0x1800d334c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180077c08`
- `RPCRT4!RpcImpersonateClient` at `0x180077c08`
- `RPCRT4!RpcRevertToSelf` at `0x180077db7`
- `RPCRT4!RpcRevertToSelf` at `0x180077db7`

## pseudocode

```c
volatile signed __int32 **__fastcall OpenExternalEtlFile(volatile signed __int32 **a1, const wchar_t **a2, __int64 a3)
{
  unsigned int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // edi
  volatile signed __int32 *v9; // rax
  __int128 v11; // [rsp+30h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v13; // [rsp+50h] [rbp-20h]
  int v14; // [rsp+58h] [rbp-18h]
  __int64 v15; // [rsp+5Ch] [rbp-14h]
  char v16; // [rsp+64h] [rbp-Ch]

  v6 = RpcImpersonateClient(0);
  v8 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v6);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v13 = 0;
    v14 = v8;
    v15 = -1;
    v16 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (unsigned __int8)AreAnyRestrictionsEnabled(256, v7) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 50);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = 50;
    v15 = 0x354FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !FileExists(*a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 2);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = 2;
    v15 = 0x359FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v9 = (volatile signed __int32 *)operator new(0x2A8u);
  if ( v9 )
  {
    v11 = *(_OWORD *)a2;
    v9 = (volatile signed __int32 *)ExternalEtlFile::ExternalEtlFile(v9, &v11, a3);
  }
  *a1 = v9;
  if ( v9 )
    _InterlockedIncrement(v9 + 2);
  RpcRevertToSelf();
  return a1;
}

```

## disassembly

```asm
0x180077be8  mov     [rsp-18h+arg_0], rbx
0x180077bed  mov     [rsp-18h+arg_8], rsi
0x180077bf2  push    rbp
0x180077bf3  push    rdi
0x180077bf4  push    r14
0x180077bf6  mov     rbp, rsp
0x180077bf9  sub     rsp, 70h
0x180077bfd  mov     r14, r8
0x180077c00  mov     rsi, rdx
0x180077c03  mov     rbx, rcx
0x180077c06  xor     ecx, ecx; BindingHandle
0x180077c08  call    cs:__imp_RpcImpersonateClient
0x180077c0e  mov     edi, eax
0x180077c10  test    eax, eax
0x180077c12  jz      short loc_180077C88
0x180077c14  lea     rcx, WPP_GLOBAL_Control
0x180077c1b  mov     r10, cs:WPP_GLOBAL_Control
0x180077c22  cmp     r10, rcx
0x180077c25  jz      short loc_180077C4D
0x180077c27  test    byte ptr [r10+1Ch], 8
0x180077c2c  jz      short loc_180077C4D
0x180077c2e  cmp     byte ptr [r10+19h], 2
0x180077c33  jb      short loc_180077C4D
0x180077c35  mov     edx, 33h ; '3'
0x180077c3a  mov     r9d, eax
0x180077c3d  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180077c44  mov     rcx, [r10+10h]
0x180077c48  call    WPP_SF_d
0x180077c4d  lea     rax, byte_1800EC961
0x180077c54  mov     qword ptr [rbp+pExceptionObject], rax
0x180077c58  mov     qword ptr [rbp+pExceptionObject+8], 0
0x180077c60  mov     [rbp+var_20], 0
0x180077c68  mov     [rbp+var_18], edi
0x180077c6b  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180077c73  mov     [rbp+var_C], 0
0x180077c77  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180077c7e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180077c82  call    _CxxThrowException_0
0x180077c88  mov     [rbp+arg_19], 1
0x180077c8c  mov     ecx, 100h
0x180077c91  call    ?AreAnyRestrictionsEnabled@@YA_NW4FeatureRestrictions@@@Z; AreAnyRestrictionsEnabled(FeatureRestrictions)
0x180077c96  test    al, al
0x180077c98  jz      short loc_180077D06
0x180077c9a  lea     rcx, WPP_GLOBAL_Control
0x180077ca1  mov     ebx, 32h ; '2'
0x180077ca6  mov     rax, cs:WPP_GLOBAL_Control
0x180077cad  cmp     rax, rcx
0x180077cb0  jz      short loc_180077CD4
0x180077cb2  test    byte ptr [rax+1Ch], 8
0x180077cb6  jz      short loc_180077CD4
0x180077cb8  cmp     byte ptr [rax+19h], 2
0x180077cbc  jb      short loc_180077CD4
0x180077cbe  lea     edx, [rbx+2]
0x180077cc1  mov     r9d, ebx
0x180077cc4  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180077ccb  mov     rcx, [rax+10h]
0x180077ccf  call    WPP_SF_d
0x180077cd4  xorps   xmm0, xmm0
0x180077cd7  movdqu  [rbp+pExceptionObject], xmm0
0x180077cdc  mov     [rbp+var_20], 0
0x180077ce4  mov     [rbp+var_18], ebx
0x180077ce7  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x180077cee  mov     dword ptr [rbp+var_14+4], 354h
0x180077cf5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180077cfc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180077d00  call    _CxxThrowException_0
0x180077d06  mov     rcx, [rsi]; wchar_t *
0x180077d09  call    ?FileExists@@YA_NPEB_W@Z; FileExists(wchar_t const *)
0x180077d0e  test    al, al
0x180077d10  jnz     short loc_180077D80
0x180077d12  lea     rcx, WPP_GLOBAL_Control
0x180077d19  mov     rax, cs:WPP_GLOBAL_Control
0x180077d20  cmp     rax, rcx
0x180077d23  jz      short loc_180077D4A
0x180077d25  test    byte ptr [rax+1Ch], 8
0x180077d29  jz      short loc_180077D4A
0x180077d2b  cmp     byte ptr [rax+19h], 2
0x180077d2f  jb      short loc_180077D4A
0x180077d31  mov     edx, 35h ; '5'
0x180077d36  lea     r9d, [rdx-33h]
0x180077d3a  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180077d41  mov     rcx, [rax+10h]
0x180077d45  call    WPP_SF_d
0x180077d4a  xorps   xmm0, xmm0
0x180077d4d  movdqu  [rbp+pExceptionObject], xmm0
0x180077d52  mov     [rbp+var_20], 0
0x180077d5a  mov     [rbp+var_18], 2
0x180077d61  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x180077d68  mov     dword ptr [rbp+var_14+4], 359h
0x180077d6f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180077d76  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180077d7a  call    _CxxThrowException_0
0x180077d80  mov     ecx, 2A8h; dwBytes
0x180077d85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077d8a  mov     [rbp+var_48], rax
0x180077d8e  test    rax, rax
0x180077d91  jz      short loc_180077DAB
0x180077d93  movaps  xmm0, xmmword ptr [rsi]
0x180077d96  movdqa  [rbp+var_40], xmm0
0x180077d9b  mov     r8, r14
0x180077d9e  lea     rdx, [rbp+var_40]
0x180077da2  mov     rcx, rax
0x180077da5  call    ??0ExternalEtlFile@@QEAA@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@PEAX@Z; ExternalEtlFile::ExternalEtlFile(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x180077daa  nop
0x180077dab  mov     [rbx], rax
0x180077dae  test    rax, rax
0x180077db1  jz      short loc_180077DB7
0x180077db3  lock inc dword ptr [rax+8]
0x180077db7  call    cs:__imp_RpcRevertToSelf
0x180077dbd  mov     rax, rbx
0x180077dc0  lea     r11, [rsp+70h+var_s0]
0x180077dc5  mov     rbx, [r11+20h]
0x180077dc9  mov     rsi, [r11+28h]
0x180077dcd  mov     rsp, r11
0x180077dd0  pop     r14
0x180077dd2  pop     rdi
0x180077dd3  pop     rbp
0x180077dd4  retn
```
