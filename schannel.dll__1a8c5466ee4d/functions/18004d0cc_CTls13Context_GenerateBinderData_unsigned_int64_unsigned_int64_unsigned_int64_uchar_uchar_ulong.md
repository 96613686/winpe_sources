# CTls13Context::GenerateBinderData(unsigned __int64,unsigned __int64,unsigned __int64,uchar,uchar *,ulong)

- ea: `0x18004d0cc`
- end: `0x18004d205`
- name: `?GenerateBinderData@CTls13Context@@QEAAK_K00EPEAEK@Z`
- size: `313`
- prototype: `unsigned int __fastcall(CTls13Context *__hidden this, unsigned __int64, unsigned __int64, unsigned __int64, char, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180045a44`
- `0x180080478`

## callees

- `0x180021e64`
- `0x18004d0cc`

## import_xrefs

- `ncrypt!SslExpandBinderKey` at `0x18004d14b`
- `ncrypt!SslExpandBinderKey` at `0x18004d14b`
- `ncrypt!SslComputeFinishedHash` at `0x18004d1b6`
- `ncrypt!SslComputeFinishedHash` at `0x18004d1b6`
- `ncrypt!SslFreeObject` at `0x18004d1f3`
- `ncrypt!SslFreeObject` at `0x18004d1f3`

## pseudocode

```c
__int64 __fastcall CTls13Context::GenerateBinderData(
        CTls13Context *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  unsigned int v9; // r14d
  unsigned int v10; // ebx
  CCipherMill *v11; // rcx
  __int64 v12; // rdx
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = 0;
  if ( a2 && a3 && a4 && a6 && (v9 = a7, a7 - 1 <= 0x3F) )
  {
    v10 = SslExpandBinderKey(a2, a3, &v14, 0, 2 - (unsigned int)(a5 != 0));
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 14;
LABEL_10:
        WPP_SF_dd(*((_QWORD *)v11 + 2), v12, WPP_4e31a98c26933ecf962336674bdee316_Traceguids, v10, a5);
      }
    }
    else
    {
      v10 = SslComputeFinishedHash(a2, v14, a4, a6, v9, 0);
      if ( v10 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 15;
          goto LABEL_10;
        }
      }
    }
  }
  else
  {
    v10 = 87;
  }
  if ( v14 )
    SslFreeObject(v14, 0);
  return v10;
}

```

## disassembly

```asm
0x18004d0cc  mov     [rsp+arg_0], rcx
0x18004d0d1  push    rbx
0x18004d0d2  push    rbp
0x18004d0d3  push    rsi
0x18004d0d4  push    r14
0x18004d0d6  sub     rsp, 38h
0x18004d0da  mov     [rsp+58h+arg_0], 0
0x18004d0e3  mov     rbp, r9
0x18004d0e6  mov     r10, r8
0x18004d0e9  mov     rsi, rdx
0x18004d0ec  test    rdx, rdx
0x18004d0ef  jz      loc_18004D1E2
0x18004d0f5  test    r8, r8
0x18004d0f8  jz      loc_18004D1E2
0x18004d0fe  test    r9, r9
0x18004d101  jz      loc_18004D1E2
0x18004d107  cmp     [rsp+58h+arg_28], 0
0x18004d110  jz      loc_18004D1E2
0x18004d116  mov     r14d, [rsp+58h+arg_30]
0x18004d11e  lea     eax, [r14-1]
0x18004d122  cmp     eax, 3Fh ; '?'
0x18004d125  ja      loc_18004D1E2
0x18004d12b  mov     al, [rsp+58h+arg_20]
0x18004d132  lea     r8, [rsp+58h+arg_0]
0x18004d137  neg     al
0x18004d139  mov     rdx, r10
0x18004d13c  sbb     ecx, ecx
0x18004d13e  xor     r9d, r9d
0x18004d141  add     ecx, 2
0x18004d144  mov     [rsp+58h+var_38], ecx
0x18004d148  mov     rcx, rsi
0x18004d14b  call    cs:__imp_SslExpandBinderKey
0x18004d151  mov     ebx, eax
0x18004d153  test    eax, eax
0x18004d155  jz      short loc_18004D196
0x18004d157  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d15e  lea     rax, WPP_GLOBAL_Control
0x18004d165  cmp     rcx, rax
0x18004d168  jz      short loc_18004D1E7
0x18004d16a  test    byte ptr [rcx+1Ch], 1
0x18004d16e  jz      short loc_18004D1E7
0x18004d170  mov     edx, 0Eh
0x18004d175  movzx   eax, [rsp+58h+arg_20]
0x18004d17d  lea     r8, WPP_4e31a98c26933ecf962336674bdee316_Traceguids
0x18004d184  mov     rcx, [rcx+10h]
0x18004d188  mov     r9d, ebx
0x18004d18b  mov     [rsp+58h+var_38], eax
0x18004d18f  call    WPP_SF_dd
0x18004d194  jmp     short loc_18004D1E7
0x18004d196  mov     r9, [rsp+58h+arg_28]
0x18004d19e  mov     r8, rbp
0x18004d1a1  mov     rdx, [rsp+58h+arg_0]
0x18004d1a6  mov     rcx, rsi
0x18004d1a9  mov     [rsp+58h+var_30], 0
0x18004d1b1  mov     [rsp+58h+var_38], r14d
0x18004d1b6  call    cs:__imp_SslComputeFinishedHash
0x18004d1bc  mov     ebx, eax
0x18004d1be  test    eax, eax
0x18004d1c0  jz      short loc_18004D1E7
0x18004d1c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d1c9  lea     rax, WPP_GLOBAL_Control
0x18004d1d0  cmp     rcx, rax
0x18004d1d3  jz      short loc_18004D1E7
0x18004d1d5  test    byte ptr [rcx+1Ch], 1
0x18004d1d9  jz      short loc_18004D1E7
0x18004d1db  mov     edx, 0Fh
0x18004d1e0  jmp     short loc_18004D175
0x18004d1e2  mov     ebx, 57h ; 'W'
0x18004d1e7  mov     rcx, [rsp+58h+arg_0]
0x18004d1ec  test    rcx, rcx
0x18004d1ef  jz      short loc_18004D1F9
0x18004d1f1  xor     edx, edx
0x18004d1f3  call    cs:__imp_SslFreeObject
0x18004d1f9  mov     eax, ebx
0x18004d1fb  add     rsp, 38h
0x18004d1ff  pop     r14
0x18004d201  pop     rsi
0x18004d202  pop     rbp
0x18004d203  pop     rbx
0x18004d204  retn
```
