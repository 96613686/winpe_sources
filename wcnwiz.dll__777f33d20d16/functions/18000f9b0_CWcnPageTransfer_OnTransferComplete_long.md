# CWcnPageTransfer::OnTransferComplete(long)

- ea: `0x18000f9b0`
- end: `0x18000faab`
- name: `?OnTransferComplete@CWcnPageTransfer@@QEAAXJ@Z`
- size: `251`
- prototype: `void __fastcall(CWcnPageTransfer *__hidden this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d130`
- `0x18001d210`

## callees

- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18000f9b0`
- `0x18000fab4`
- `0x18002de1c`

## import_xrefs

- `USER32!PostMessageW` at `0x18000faa4`

## pseudocode

```c
void __fastcall CWcnPageTransfer::OnTransferComplete(CWcnPageTransfer *this, int a2)
{
  const char *v4; // rax
  __int64 v5; // r10
  unsigned int Indent; // eax
  __int64 v7; // r10
  int v8; // eax

  if ( a2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      Indent = (unsigned int)GetIndent(0);
      WPP_SF_sd(*(_QWORD *)(v7 + 16), 24, (unsigned int)WPP_f4c38ae3bfce38568dc55083d17d9862_Traceguids, Indent, a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v4 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 23, WPP_f4c38ae3bfce38568dc55083d17d9862_Traceguids, v4);
  }
  *(_DWORD *)(*((_QWORD *)this + 24) + 8LL) = a2;
  if ( !a2 )
  {
    v8 = CWcnPageTransfer::SaveProfile(this);
    if ( v8 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_f4c38ae3bfce38568dc55083d17d9862_Traceguids,
        (unsigned int)v8);
  }
  PostMessageW(*((HWND *)this + 20), 0x471u, 1u, 0);
}

```

## disassembly

```asm
0x18000f9b0  mov     [rsp+arg_0], rbx
0x18000f9b5  mov     [rsp+arg_8], rsi
0x18000f9ba  push    rdi
0x18000f9bb  sub     rsp, 30h
0x18000f9bf  mov     edi, edx
0x18000f9c1  mov     rsi, rcx
0x18000f9c4  test    edx, edx
0x18000f9c6  js      short loc_18000FA03
0x18000f9c8  mov     r10, cs:WPP_GLOBAL_Control
0x18000f9cf  lea     rbx, WPP_GLOBAL_Control
0x18000f9d6  cmp     r10, rbx
0x18000f9d9  jz      short loc_18000FA40
0x18000f9db  cmp     byte ptr [r10+19h], 4
0x18000f9e0  jb      short loc_18000FA40
0x18000f9e2  xor     ecx, ecx; int
0x18000f9e4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000f9e9  mov     rcx, [r10+10h]
0x18000f9ed  lea     r8, WPP_f4c38ae3bfce38568dc55083d17d9862_Traceguids
0x18000f9f4  mov     edx, 17h
0x18000f9f9  mov     r9, rax
0x18000f9fc  call    WPP_SF_s
0x18000fa01  jmp     short loc_18000FA40
0x18000fa03  mov     r10, cs:WPP_GLOBAL_Control
0x18000fa0a  lea     rbx, WPP_GLOBAL_Control
0x18000fa11  cmp     r10, rbx
0x18000fa14  jz      short loc_18000FA40
0x18000fa16  cmp     byte ptr [r10+19h], 2
0x18000fa1b  jb      short loc_18000FA40
0x18000fa1d  xor     ecx, ecx; int
0x18000fa1f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000fa24  mov     rcx, [r10+10h]
0x18000fa28  lea     r8, WPP_f4c38ae3bfce38568dc55083d17d9862_Traceguids
0x18000fa2f  mov     edx, 18h
0x18000fa34  mov     [rsp+38h+var_18], edi
0x18000fa38  mov     r9, rax
0x18000fa3b  call    WPP_SF_sd
0x18000fa40  mov     rax, [rsi+0C0h]
0x18000fa47  mov     [rax+8], edi
0x18000fa4a  test    edi, edi
0x18000fa4c  jnz     short loc_18000FA82
0x18000fa4e  mov     rcx, rsi; this
0x18000fa51  call    ?SaveProfile@CWcnPageTransfer@@QEAAJXZ; CWcnPageTransfer::SaveProfile(void)
0x18000fa56  test    eax, eax
0x18000fa58  jns     short loc_18000FA82
0x18000fa5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa61  cmp     rcx, rbx
0x18000fa64  jz      short loc_18000FA82
0x18000fa66  cmp     byte ptr [rcx+19h], 3
0x18000fa6a  jb      short loc_18000FA82
0x18000fa6c  mov     rcx, [rcx+10h]
0x18000fa70  lea     edx, [rdi+19h]
0x18000fa73  mov     r9d, eax
0x18000fa76  lea     r8, WPP_f4c38ae3bfce38568dc55083d17d9862_Traceguids
0x18000fa7d  call    WPP_SF_d
0x18000fa82  mov     rcx, [rsi+0A0h]
0x18000fa89  xor     r9d, r9d
0x18000fa8c  mov     edx, 471h
0x18000fa91  lea     r8d, [r9+1]
0x18000fa95  mov     rbx, [rsp+38h+arg_0]
0x18000fa9a  mov     rsi, [rsp+38h+arg_8]
0x18000fa9f  add     rsp, 30h
0x18000faa3  pop     rdi
0x18000faa4  jmp     cs:__imp_PostMessageW
```
