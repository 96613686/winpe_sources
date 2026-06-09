# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800049f0`
- end: `0x180004b15`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `293`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004720`
- `0x1800049f0`

## callees

- `0x18000204a`
- `0x18000209e`
- `0x1800049f0`
- `0x1800066d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004ab5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004af4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004ab5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004af4`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rdx
  char *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rsi
  _BYTE *v14; // rsi
  __int64 v15; // rbp
  size_t v16; // rbx
  size_t v17; // rdi

  result = 0;
  *a3 = 0;
  if ( a2 )
  {
    result = wil::details::ThreadFailureCallbackHolder::GetThreadContext(a1, a2[2], a3, a4);
    v9 = a2[4];
    if ( v9 )
    {
      if ( !*(_DWORD *)v9 )
        *(_DWORD *)v9 = _InterlockedIncrement(&wil::details::ThreadFailureCallbackHolder::s_telemetryId);
      if ( !*((_DWORD *)a1 + 20) )
      {
        *((_OWORD *)a1 + 5) = *(_OWORD *)v9;
        *((_QWORD *)a1 + 12) = *((_QWORD *)v9 + 2);
      }
      v10 = &a3[a4];
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v10 - v13 <= 2 )
        return 1;
      *v13 = 92;
      v14 = v13 + 1;
      v15 = *((_QWORD *)v9 + 1);
      do
        ++v11;
      while ( *(_BYTE *)(v11 + v15) );
      v16 = v11 + 1;
      v17 = v10 - v14;
      if ( v16 >= v17 )
        v16 = v17;
      if ( v16 )
      {
        if ( !v14 )
        {
LABEL_16:
          *(_DWORD *)_o__errno() = 22;
LABEL_23:
          invalid_parameter_noinfo();
          goto LABEL_24;
        }
        if ( v15 && v17 >= v16 )
        {
          memcpy_0(v14, *((const void **)v9 + 1), v16);
        }
        else
        {
          memset_0(v14, 0, v17);
          if ( !v15 )
            goto LABEL_16;
          if ( v17 < v16 )
          {
            *(_DWORD *)_o__errno() = 34;
            goto LABEL_23;
          }
        }
      }
LABEL_24:
      v14[v16 - 1] = 0;
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800049f0  push    rbx
0x1800049f2  push    rbp
0x1800049f3  push    rsi
0x1800049f4  push    rdi
0x1800049f5  sub     rsp, 28h
0x1800049f9  xor     al, al
0x1800049fb  mov     byte ptr [r8], 0
0x1800049ff  mov     rbp, r9
0x180004a02  mov     rsi, r8
0x180004a05  mov     rdi, rdx
0x180004a08  mov     rbx, rcx
0x180004a0b  test    rdx, rdx
0x180004a0e  jz      loc_180004B0C
0x180004a14  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004a18  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004a1d  mov     rdx, [rdi+20h]
0x180004a21  test    rdx, rdx
0x180004a24  jz      loc_180004B0C
0x180004a2a  cmp     dword ptr [rdx], 0
0x180004a2d  jnz     short loc_180004A40
0x180004a2f  mov     eax, 1
0x180004a34  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004a3c  inc     eax
0x180004a3e  mov     [rdx], eax
0x180004a40  cmp     dword ptr [rbx+50h], 0
0x180004a44  jnz     short loc_180004A57
0x180004a46  movups  xmm0, xmmword ptr [rdx]
0x180004a49  movups  xmmword ptr [rbx+50h], xmm0
0x180004a4d  movsd   xmm1, qword ptr [rdx+10h]
0x180004a52  movsd   qword ptr [rbx+60h], xmm1
0x180004a57  movups  xmm0, xmmword ptr [rdx]
0x180004a5a  lea     rdi, [rsi+rbp]
0x180004a5e  movups  xmmword ptr [rbx+68h], xmm0
0x180004a62  movsd   xmm1, qword ptr [rdx+10h]
0x180004a67  movsd   qword ptr [rbx+78h], xmm1
0x180004a6c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004a70  mov     rax, rbx
0x180004a73  inc     rax
0x180004a76  cmp     byte ptr [rsi+rax], 0
0x180004a7a  jnz     short loc_180004A73
0x180004a7c  add     rsi, rax
0x180004a7f  mov     rax, rdi
0x180004a82  sub     rax, rsi
0x180004a85  cmp     rax, 2
0x180004a89  jle     short loc_180004B0A
0x180004a8b  mov     byte ptr [rsi], 5Ch ; '\'
0x180004a8e  inc     rsi
0x180004a91  mov     rbp, [rdx+8]
0x180004a95  inc     rbx
0x180004a98  cmp     byte ptr [rbx+rbp], 0
0x180004a9c  jnz     short loc_180004A95
0x180004a9e  inc     rbx
0x180004aa1  sub     rdi, rsi
0x180004aa4  cmp     rbx, rdi
0x180004aa7  cmovnb  rbx, rdi
0x180004aab  test    rbx, rbx
0x180004aae  jz      short loc_180004B05
0x180004ab0  test    rsi, rsi
0x180004ab3  jnz     short loc_180004AC3
0x180004ab5  call    cs:__imp__o__errno
0x180004abb  mov     dword ptr [rax], 16h
0x180004ac1  jmp     short loc_180004B00
0x180004ac3  test    rbp, rbp
0x180004ac6  jz      short loc_180004ADD
0x180004ac8  cmp     rdi, rbx
0x180004acb  jb      short loc_180004ADD
0x180004acd  mov     r8, rbx; Size
0x180004ad0  mov     rdx, rbp; Src
0x180004ad3  mov     rcx, rsi; void *
0x180004ad6  call    memcpy_0
0x180004adb  jmp     short loc_180004B05
0x180004add  mov     r8, rdi; Size
0x180004ae0  xor     edx, edx; Val
0x180004ae2  mov     rcx, rsi; void *
0x180004ae5  call    memset_0
0x180004aea  test    rbp, rbp
0x180004aed  jz      short loc_180004AB5
0x180004aef  cmp     rdi, rbx
0x180004af2  jnb     short loc_180004B05
0x180004af4  call    cs:__imp__o__errno
0x180004afa  mov     dword ptr [rax], 22h ; '"'
0x180004b00  call    _invalid_parameter_noinfo
0x180004b05  mov     byte ptr [rbx+rsi-1], 0
0x180004b0a  mov     al, 1
0x180004b0c  add     rsp, 28h
0x180004b10  pop     rdi
0x180004b11  pop     rsi
0x180004b12  pop     rbp
0x180004b13  pop     rbx
0x180004b14  retn
```
