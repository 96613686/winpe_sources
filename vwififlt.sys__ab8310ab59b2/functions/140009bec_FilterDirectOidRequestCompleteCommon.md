# FilterDirectOidRequestCompleteCommon

- ea: `0x140009bec`
- end: `0x140009e67`
- name: `FilterDirectOidRequestCompleteCommon`
- size: `635`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400097e4`
- `0x14000d310`

## callees

- `0x140009bec`
- `0x14000ada8`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000f150`

## import_xrefs

- `NDIS!NdisFreeCloneOidRequest` at `0x140009cae`
- `NDIS!NdisFreeCloneOidRequest` at `0x140009cae`

## pseudocode

```c
void __fastcall FilterDirectOidRequestCompleteCommon(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  unsigned int v5; // r14d
  unsigned int v8; // ebp
  _DWORD *v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // r8

  v5 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 200, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  v8 = *(_DWORD *)(a2 + 32);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 201, a3, v8, v5);
  v9 = *(_DWORD **)(a2 + 216);
  if ( !v9 )
    TraceAssert("OriginalRequest", "onecoreuap\\net\\vwifi\\filter\\filter.c", 3193);
  v10 = *(_QWORD *)(a2 + 224);
  if ( !v10 )
    TraceAssert("pFilterMpCtx", "onecoreuap\\net\\vwifi\\filter\\filter.c", 3196);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 202, a3, v8, *(_DWORD *)(v10 + 104));
  if ( *(_DWORD *)(a2 + 4) == 12 )
  {
    v9[13] = *(_DWORD *)(a2 + 52);
    v9[16] = *(_DWORD *)(a2 + 64);
    v9[17] = *(_DWORD *)(a2 + 68);
    v9[15] = *(_DWORD *)(a2 + 60);
  }
  else
  {
    v9[13] = *(_DWORD *)(a2 + 52);
    v9[14] = *(_DWORD *)(a2 + 56);
  }
  *(_QWORD *)(a2 + 216) = 0;
  NdisFreeCloneOidRequest(*(NDIS_HANDLE *)(a1 + 128), (PNDIS_OID_REQUEST)a2);
  if ( (*(_BYTE *)(v10 + 2)
     || (TraceAssert("pFilterMpCtx->fMpStarted", "onecoreuap\\net\\vwifi\\filter\\filter.c", 3230), *(_BYTE *)(v10 + 2)))
    && a4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 203, v11, v8, *(_DWORD *)(v10 + 104));
    (*(void (__fastcall **)(_QWORD, _DWORD *, _QWORD))(v10 + 88))(*(_QWORD *)(v10 + 56), v9, v5);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 204, v11, v8, *(_DWORD *)(v10 + 104));
  }
  _InterlockedDecrement((volatile signed __int32 *)(v10 + 136));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 205, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
}

```

## disassembly

```asm
0x140009bec  push    rbx
0x140009bee  push    rbp
0x140009bef  push    rsi
0x140009bf0  push    rdi
0x140009bf1  push    r13
0x140009bf3  push    r14
0x140009bf5  push    r15
0x140009bf7  sub     rsp, 30h
0x140009bfb  mov     r15b, r9b
0x140009bfe  mov     r14d, r8d
0x140009c01  mov     rbx, rdx
0x140009c04  mov     r13, rcx
0x140009c07  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c0e  lea     rdi, WPP_GLOBAL_Control
0x140009c15  cmp     rcx, rdi
0x140009c18  jz      short loc_140009C25
0x140009c1a  mov     eax, [rcx+2Ch]
0x140009c1d  test    al, 20h
0x140009c1f  jnz     loc_140009DAA
0x140009c25  mov     ebp, [rbx+20h]
0x140009c28  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c2f  cmp     rcx, rdi
0x140009c32  jz      short loc_140009C3F
0x140009c34  mov     eax, [rcx+2Ch]
0x140009c37  test    al, 4
0x140009c39  jnz     loc_140009DC4
0x140009c3f  mov     rsi, [rbx+0D8h]
0x140009c46  test    rsi, rsi
0x140009c49  jz      loc_140009DDF
0x140009c4f  mov     rdi, [rbx+0E0h]
0x140009c56  test    rdi, rdi
0x140009c59  jz      loc_140009DFD
0x140009c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c66  lea     rax, WPP_GLOBAL_Control
0x140009c6d  cmp     rcx, rax
0x140009c70  jz      short loc_140009C7D
0x140009c72  mov     eax, [rcx+2Ch]
0x140009c75  test    al, 4
0x140009c77  jnz     loc_140009E1B
0x140009c7d  mov     ecx, [rbx+4]
0x140009c80  test    ecx, ecx
0x140009c82  jz      short loc_140009C8D
0x140009c84  sub     ecx, 1
0x140009c87  jnz     loc_140009E38
0x140009c8d  mov     eax, [rbx+34h]
0x140009c90  mov     [rsi+34h], eax
0x140009c93  mov     eax, [rbx+38h]
0x140009c96  mov     [rsi+38h], eax
0x140009c99  mov     qword ptr [rbx+0D8h], 0
0x140009ca4  mov     rdx, rbx; Request
0x140009ca7  mov     rcx, [r13+80h]; SourceHandle
0x140009cae  call    cs:__imp_NdisFreeCloneOidRequest
0x140009cb5  nop     dword ptr [rax+rax+00h]
0x140009cba  cmp     byte ptr [rdi+2], 0
0x140009cbe  jz      short loc_140009D13
0x140009cc0  test    r15b, r15b
0x140009cc3  jz      short loc_140009D32
0x140009cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ccc  lea     rax, WPP_GLOBAL_Control
0x140009cd3  cmp     rcx, rax
0x140009cd6  jz      short loc_140009CF7
0x140009cd8  mov     eax, [rcx+2Ch]
0x140009cdb  test    al, 4
0x140009cdd  jz      short loc_140009CF7
0x140009cdf  mov     eax, [rdi+68h]
0x140009ce2  mov     edx, 0CBh
0x140009ce7  mov     rcx, [rcx+18h]
0x140009ceb  mov     r9d, ebp
0x140009cee  mov     [rsp+68h+var_48], eax
0x140009cf2  call    WPP_SF_Dd
0x140009cf7  mov     rax, [rdi+58h]
0x140009cfb  mov     r8d, r14d
0x140009cfe  mov     rcx, [rdi+38h]
0x140009d02  mov     rdx, rsi
0x140009d05  call    _guard_dispatch_icall
0x140009d0a  lea     rbx, WPP_GLOBAL_Control
0x140009d11  jmp     short loc_140009D45
0x140009d13  mov     r8d, 0C9Eh
0x140009d19  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140009d20  lea     rcx, aPfiltermpctxFm_0; "pFilterMpCtx->fMpStarted"
0x140009d27  call    TraceAssert
0x140009d2c  cmp     byte ptr [rdi+2], 0
0x140009d30  jnz     short loc_140009CC0
0x140009d32  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d39  lea     rbx, WPP_GLOBAL_Control
0x140009d40  cmp     rcx, rbx
0x140009d43  jnz     short loc_140009D68
0x140009d45  lock dec dword ptr [rdi+88h]
0x140009d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d53  cmp     rcx, rbx
0x140009d56  jnz     short loc_140009D89
0x140009d58  add     rsp, 30h
0x140009d5c  pop     r15
0x140009d5e  pop     r14
0x140009d60  pop     r13
0x140009d62  pop     rdi
0x140009d63  pop     rsi
0x140009d64  pop     rbp
0x140009d65  pop     rbx
0x140009d66  retn
0x140009d68  mov     eax, [rcx+2Ch]
0x140009d6b  test    al, 4
0x140009d6d  jz      short loc_140009D45
0x140009d6f  mov     eax, [rdi+68h]
0x140009d72  mov     edx, 0CCh
0x140009d77  mov     rcx, [rcx+18h]
0x140009d7b  mov     r9d, ebp
0x140009d7e  mov     [rsp+68h+var_48], eax
0x140009d82  call    WPP_SF_Dd
0x140009d87  jmp     short loc_140009D45
0x140009d89  mov     eax, [rcx+2Ch]
0x140009d8c  test    al, 20h
0x140009d8e  jz      short loc_140009D58
0x140009d90  mov     rcx, [rcx+18h]
0x140009d94  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140009d9b  mov     edx, 0CDh
0x140009da0  xor     r9d, r9d
0x140009da3  call    WPP_SF_d
0x140009da8  jmp     short loc_140009D58
0x140009daa  mov     rcx, [rcx+18h]
0x140009dae  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140009db5  mov     edx, 0C8h
0x140009dba  call    WPP_SF_
0x140009dbf  jmp     loc_140009C25
0x140009dc4  mov     rcx, [rcx+18h]
0x140009dc8  mov     edx, 0C9h
0x140009dcd  mov     r9d, ebp
0x140009dd0  mov     [rsp+68h+var_48], r14d
0x140009dd5  call    WPP_SF_Dd
0x140009dda  jmp     loc_140009C3F
0x140009ddf  mov     r8d, 0C79h
0x140009de5  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140009dec  lea     rcx, aOriginalreques; "OriginalRequest"
0x140009df3  call    TraceAssert
0x140009df8  jmp     loc_140009C4F
0x140009dfd  mov     r8d, 0C7Ch
0x140009e03  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140009e0a  lea     rcx, aPfiltermpctx; "pFilterMpCtx"
0x140009e11  call    TraceAssert
0x140009e16  jmp     loc_140009C5F
0x140009e1b  mov     eax, [rdi+68h]
0x140009e1e  mov     edx, 0CAh
0x140009e23  mov     rcx, [rcx+18h]
0x140009e27  mov     r9d, ebp
0x140009e2a  mov     [rsp+68h+var_48], eax
0x140009e2e  call    WPP_SF_Dd
0x140009e33  jmp     loc_140009C7D
0x140009e38  sub     ecx, 1
0x140009e3b  jz      loc_140009C8D
0x140009e41  cmp     ecx, 0Ah
0x140009e44  jnz     loc_140009C8D
0x140009e4a  mov     eax, [rbx+34h]
0x140009e4d  mov     [rsi+34h], eax
0x140009e50  mov     eax, [rbx+40h]
0x140009e53  mov     [rsi+40h], eax
0x140009e56  mov     eax, [rbx+44h]
0x140009e59  mov     [rsi+44h], eax
0x140009e5c  mov     eax, [rbx+3Ch]
0x140009e5f  mov     [rsi+3Ch], eax
0x140009e62  jmp     loc_140009C99
```
