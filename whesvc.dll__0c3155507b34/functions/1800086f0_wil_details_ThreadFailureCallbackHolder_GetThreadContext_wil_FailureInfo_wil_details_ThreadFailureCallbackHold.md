# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800086f0`
- end: `0x180008815`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `293`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180008190`
- `0x1800086f0`

## callees

- `0x180003d0a`
- `0x180003da4`
- `0x180004575`
- `0x1800086f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800087b5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800087f4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800087b5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800087f4`

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
0x1800086f0  push    rbx
0x1800086f2  push    rbp
0x1800086f3  push    rsi
0x1800086f4  push    rdi
0x1800086f5  sub     rsp, 28h
0x1800086f9  xor     al, al
0x1800086fb  mov     byte ptr [r8], 0
0x1800086ff  mov     rbp, r9
0x180008702  mov     rsi, r8
0x180008705  mov     rdi, rdx
0x180008708  mov     rbx, rcx
0x18000870b  test    rdx, rdx
0x18000870e  jz      loc_18000880C
0x180008714  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180008718  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000871d  mov     rdx, [rdi+20h]
0x180008721  test    rdx, rdx
0x180008724  jz      loc_18000880C
0x18000872a  cmp     dword ptr [rdx], 0
0x18000872d  jnz     short loc_180008740
0x18000872f  mov     eax, 1
0x180008734  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000873c  inc     eax
0x18000873e  mov     [rdx], eax
0x180008740  cmp     dword ptr [rbx+50h], 0
0x180008744  jnz     short loc_180008757
0x180008746  movups  xmm0, xmmword ptr [rdx]
0x180008749  movups  xmmword ptr [rbx+50h], xmm0
0x18000874d  movsd   xmm1, qword ptr [rdx+10h]
0x180008752  movsd   qword ptr [rbx+60h], xmm1
0x180008757  movups  xmm0, xmmword ptr [rdx]
0x18000875a  lea     rdi, [rsi+rbp]
0x18000875e  movups  xmmword ptr [rbx+68h], xmm0
0x180008762  movsd   xmm1, qword ptr [rdx+10h]
0x180008767  movsd   qword ptr [rbx+78h], xmm1
0x18000876c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008770  mov     rax, rbx
0x180008773  inc     rax
0x180008776  cmp     byte ptr [rsi+rax], 0
0x18000877a  jnz     short loc_180008773
0x18000877c  add     rsi, rax
0x18000877f  mov     rax, rdi
0x180008782  sub     rax, rsi
0x180008785  cmp     rax, 2
0x180008789  jle     short loc_18000880A
0x18000878b  mov     byte ptr [rsi], 5Ch ; '\'
0x18000878e  inc     rsi
0x180008791  mov     rbp, [rdx+8]
0x180008795  inc     rbx
0x180008798  cmp     byte ptr [rbx+rbp], 0
0x18000879c  jnz     short loc_180008795
0x18000879e  inc     rbx
0x1800087a1  sub     rdi, rsi
0x1800087a4  cmp     rbx, rdi
0x1800087a7  cmovnb  rbx, rdi
0x1800087ab  test    rbx, rbx
0x1800087ae  jz      short loc_180008805
0x1800087b0  test    rsi, rsi
0x1800087b3  jnz     short loc_1800087C3
0x1800087b5  call    cs:__imp__o__errno
0x1800087bb  mov     dword ptr [rax], 16h
0x1800087c1  jmp     short loc_180008800
0x1800087c3  test    rbp, rbp
0x1800087c6  jz      short loc_1800087DD
0x1800087c8  cmp     rdi, rbx
0x1800087cb  jb      short loc_1800087DD
0x1800087cd  mov     r8, rbx; Size
0x1800087d0  mov     rdx, rbp; Src
0x1800087d3  mov     rcx, rsi; void *
0x1800087d6  call    memcpy_0
0x1800087db  jmp     short loc_180008805
0x1800087dd  mov     r8, rdi; Size
0x1800087e0  xor     edx, edx; Val
0x1800087e2  mov     rcx, rsi; void *
0x1800087e5  call    memset_0
0x1800087ea  test    rbp, rbp
0x1800087ed  jz      short loc_1800087B5
0x1800087ef  cmp     rdi, rbx
0x1800087f2  jnb     short loc_180008805
0x1800087f4  call    cs:__imp__o__errno
0x1800087fa  mov     dword ptr [rax], 22h ; '"'
0x180008800  call    _invalid_parameter_noinfo
0x180008805  mov     byte ptr [rbx+rsi-1], 0
0x18000880a  mov     al, 1
0x18000880c  add     rsp, 28h
0x180008810  pop     rdi
0x180008811  pop     rsi
0x180008812  pop     rbp
0x180008813  pop     rbx
0x180008814  retn
```
