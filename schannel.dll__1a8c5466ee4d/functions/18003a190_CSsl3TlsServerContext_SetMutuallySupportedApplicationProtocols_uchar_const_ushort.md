# CSsl3TlsServerContext::SetMutuallySupportedApplicationProtocols(uchar * const,ushort)

- ea: `0x18003a190`
- end: `0x18003a43a`
- name: `?SetMutuallySupportedApplicationProtocols@CSsl3TlsServerContext@@QEAAKQEAEG@Z`
- size: `682`
- prototype: `__int64 __fastcall(CSsl3TlsServerContext *this, unsigned __int8 *const, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017060`

## callees

- `0x1800214f0`
- `0x18003a190`
- `0x180057c8c`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a3aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a3aa`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003a35b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003a35b`

## pseudocode

```c
__int64 __fastcall CSsl3TlsServerContext::SetMutuallySupportedApplicationProtocols(
        CSsl3TlsServerContext *this,
        unsigned __int8 *const a2,
        unsigned __int16 a3,
        __int64 a4)
{
  CCipherMill *v5; // rcx
  __int64 result; // rax
  unsigned __int8 *v7; // rcx
  unsigned __int8 *v8; // rbp
  __int64 v9; // rax
  unsigned __int8 *v10; // rcx
  __int64 v11; // rax
  int v12; // edi
  unsigned int v13; // r12d
  unsigned __int8 *v14; // rcx
  unsigned __int16 v15; // ax
  unsigned __int8 *v16; // rsi
  SIZE_T v17; // r14
  unsigned __int8 *i; // rbx
  __int64 v19; // r15
  __int64 v20; // rcx
  _WORD *v21; // rax
  __int64 v22; // rdx
  char *v23; // [rsp+20h] [rbp-58h]
  unsigned __int64 v24; // [rsp+28h] [rbp-50h]
  unsigned __int8 *v25; // [rsp+30h] [rbp-48h]
  unsigned __int16 v26; // [rsp+80h] [rbp+8h]
  unsigned __int8 *v27; // [rsp+88h] [rbp+10h]
  int v28; // [rsp+98h] [rbp+20h]

  v27 = a2;
  if ( *((_QWORD *)this + 336) )
    return 0;
  if ( !a2 )
    return 87;
  if ( (unsigned __int16)(a3 - 2) <= 0xFFFBu )
  {
    v7 = a2;
    v8 = &a2[a3];
    while ( 1 )
    {
      if ( v7 >= v8 )
      {
        v11 = *((_QWORD *)this + 313);
        if ( !v11 )
          return 87;
        LOWORD(v12) = 0;
        v23 = 0;
        v13 = 0;
        v14 = (unsigned __int8 *)(v11 + 6);
        v28 = 0;
        v15 = *(_WORD *)(v11 + 4);
        v26 = v15;
        v25 = v14;
        while ( v13 < 2 )
        {
          v16 = v14;
          v24 = (unsigned __int64)&v14[v15];
          if ( (unsigned __int64)v14 < v24 )
          {
            do
            {
              v17 = *v16;
              for ( i = a2; ; i += v19 + 1 )
              {
                if ( i >= v8 )
                  goto LABEL_20;
                v19 = *i;
                if ( (_BYTE)v17 == (_BYTE)v19 && RtlCompareMemory(v16 + 1, i + 1, v17) == v17 )
                  break;
              }
              if ( *((_QWORD *)this + 336) )
              {
                memcpy_0(v23, v16, (unsigned __int16)(v17 + 1));
                v23 += (unsigned __int16)(v17 + 1);
LABEL_20:
                LOWORD(v12) = v28;
                goto LABEL_21;
              }
              HIWORD(v12) = HIWORD(v28);
              LOWORD(v12) = v17 + 1 + v28;
              v28 = v12;
LABEL_21:
              a2 = v27;
              v16 += v17 + 1;
            }
            while ( (unsigned __int64)v16 < v24 );
          }
          if ( !(_WORD)v12 )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_4536224b51c63d9a1593beb928bc374a_Traceguids);
            }
            LOBYTE(a4) = 120;
            CSslContext::SetErrorAndFatalAlert(this, 1208, 2148074343LL, a4);
            result = 2148074343LL;
            *((_DWORD *)this + 23) = 96;
            *((_WORD *)this + 60) = 30722;
            return result;
          }
          if ( !*((_QWORD *)this + 336) )
          {
            v20 = (unsigned int)(unsigned __int16)v12 + 6;
            if ( LsaTable )
              v21 = (_WORD *)(*(__int64 (__fastcall **)(__int64, unsigned __int8 *const))(LsaTable + 40))(v20, a2);
            else
              v21 = LocalAlloc(0x40u, (unsigned int)v20);
            *((_QWORD *)this + 336) = v21;
            if ( !v21 )
              return 14;
            v21[2] = v12;
            v23 = (char *)(*((_QWORD *)this + 336) + 6LL);
          }
          v14 = v25;
          ++v13;
          a2 = v27;
          v15 = v26;
        }
        return 0;
      }
      v9 = *v7;
      if ( !(_BYTE)v9 )
        break;
      v10 = &v7[v9];
      if ( v10 >= v8 )
        break;
      v7 = v10 + 1;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 77;
      goto LABEL_45;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 75;
LABEL_45:
      WPP_SF_(*((_QWORD *)v5 + 2), v22, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
    }
  }
  return 2148074278LL;
}

```

## disassembly

```asm
0x18003a190  mov     [rsp+arg_10], rbx
0x18003a195  mov     [rsp+arg_8], rdx
0x18003a19a  push    rbp
0x18003a19b  push    rsi
0x18003a19c  push    rdi
0x18003a19d  push    r12
0x18003a19f  push    r13
0x18003a1a1  push    r14
0x18003a1a3  push    r15
0x18003a1a5  sub     rsp, 40h
0x18003a1a9  cmp     qword ptr [rcx+0A80h], 0
0x18003a1b1  mov     r13, rcx
0x18003a1b4  jnz     loc_18003A39C
0x18003a1ba  test    rdx, rdx
0x18003a1bd  jz      loc_18003A3F4
0x18003a1c3  lea     eax, [r8-2]
0x18003a1c7  mov     ecx, 0FFFBh
0x18003a1cc  cmp     ax, cx
0x18003a1cf  jbe     short loc_18003A205
0x18003a1d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1d8  lea     rax, WPP_GLOBAL_Control
0x18003a1df  cmp     rcx, rax
0x18003a1e2  jnz     loc_18003A3E0
0x18003a1e8  mov     eax, 80090326h
0x18003a1ed  mov     rbx, [rsp+78h+arg_10]
0x18003a1f5  add     rsp, 40h
0x18003a1f9  pop     r15
0x18003a1fb  pop     r14
0x18003a1fd  pop     r13
0x18003a1ff  pop     r12
0x18003a201  pop     rdi
0x18003a202  pop     rsi
0x18003a203  pop     rbp
0x18003a204  retn
0x18003a205  movzx   ebp, r8w
0x18003a209  mov     rcx, rdx
0x18003a20c  add     rbp, rdx
0x18003a20f  nop
0x18003a210  cmp     rcx, rbp
0x18003a213  jnb     short loc_18003A231
0x18003a215  movzx   eax, byte ptr [rcx]
0x18003a218  test    al, al
0x18003a21a  jz      loc_18003A3B5
0x18003a220  add     rcx, rax
0x18003a223  cmp     rcx, rbp
0x18003a226  jnb     loc_18003A3B5
0x18003a22c  inc     rcx
0x18003a22f  jmp     short loc_18003A210
0x18003a231  mov     rax, [r13+9C8h]
0x18003a238  test    rax, rax
0x18003a23b  jz      loc_18003A3F4
0x18003a241  xor     ecx, ecx
0x18003a243  xor     edi, edi
0x18003a245  mov     [rsp+78h+var_58], rcx
0x18003a24a  xor     r12d, r12d
0x18003a24d  lea     rcx, [rax+6]
0x18003a251  mov     [rsp+78h+arg_18], edi
0x18003a258  movzx   eax, word ptr [rax+4]
0x18003a25c  mov     [rsp+78h+arg_0], ax
0x18003a264  mov     [rsp+78h+var_48], rcx
0x18003a269  cmp     r12d, 2
0x18003a26d  jnb     loc_18003A39C
0x18003a273  movzx   eax, ax
0x18003a276  mov     rsi, rcx
0x18003a279  add     rax, rcx
0x18003a27c  mov     [rsp+78h+var_50], rax
0x18003a281  cmp     rcx, rax
0x18003a284  jnb     short loc_18003A2E1
0x18003a286  movzx   r14d, byte ptr [rsi]
0x18003a28a  mov     rbx, rdx
0x18003a28d  cmp     rbx, rbp
0x18003a290  jnb     short loc_18003A2C5
0x18003a292  movzx   r15d, byte ptr [rbx]
0x18003a296  cmp     r14b, r15b
0x18003a299  jz      loc_18003A350
0x18003a29f  inc     rbx
0x18003a2a2  add     rbx, r15
0x18003a2a5  jmp     short loc_18003A28D
0x18003a2a7  mov     r15, [rsp+78h+var_58]
0x18003a2ac  mov     rdx, rsi; Src
0x18003a2af  movzx   ebx, ax
0x18003a2b2  mov     rcx, r15; void *
0x18003a2b5  mov     r8d, ebx; Size
0x18003a2b8  call    memcpy_0
0x18003a2bd  add     r15, rbx
0x18003a2c0  mov     [rsp+78h+var_58], r15
0x18003a2c5  mov     edi, [rsp+78h+arg_18]
0x18003a2cc  mov     rdx, [rsp+78h+arg_8]
0x18003a2d4  inc     rsi
0x18003a2d7  add     rsi, r14
0x18003a2da  cmp     rsi, [rsp+78h+var_50]
0x18003a2df  jb      short loc_18003A286
0x18003a2e1  test    di, di
0x18003a2e4  jz      loc_18003A3FE
0x18003a2ea  cmp     qword ptr [r13+0A80h], 0
0x18003a2f2  jnz     short loc_18003A333
0x18003a2f4  mov     rax, cs:LsaTable
0x18003a2fb  movzx   ecx, di
0x18003a2fe  add     ecx, 6
0x18003a301  test    rax, rax
0x18003a304  jz      loc_18003A3A3
0x18003a30a  mov     rax, [rax+28h]
0x18003a30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a313  mov     [r13+0A80h], rax
0x18003a31a  test    rax, rax
0x18003a31d  jz      short loc_18003A392
0x18003a31f  mov     [rax+4], di
0x18003a323  mov     rcx, [r13+0A80h]
0x18003a32a  add     rcx, 6
0x18003a32e  mov     [rsp+78h+var_58], rcx
0x18003a333  mov     rcx, [rsp+78h+var_48]
0x18003a338  inc     r12d
0x18003a33b  mov     rdx, [rsp+78h+arg_8]
0x18003a343  movzx   eax, [rsp+78h+arg_0]
0x18003a34b  jmp     loc_18003A269
0x18003a350  lea     rdx, [rbx+1]; Source2
0x18003a354  mov     r8, r14; Length
0x18003a357  lea     rcx, [rsi+1]; Source1
0x18003a35b  call    cs:__imp_RtlCompareMemory
0x18003a361  cmp     rax, r14
0x18003a364  jnz     loc_18003A29F
0x18003a36a  cmp     qword ptr [r13+0A80h], 0
0x18003a372  lea     eax, [r14+1]
0x18003a376  jnz     loc_18003A2A7
0x18003a37c  mov     edi, [rsp+78h+arg_18]
0x18003a383  add     di, ax
0x18003a386  mov     [rsp+78h+arg_18], edi
0x18003a38d  jmp     loc_18003A2CC
0x18003a392  mov     eax, 0Eh
0x18003a397  jmp     loc_18003A1ED
0x18003a39c  xor     eax, eax
0x18003a39e  jmp     loc_18003A1ED
0x18003a3a3  mov     edx, ecx; uBytes
0x18003a3a5  mov     ecx, 40h ; '@'; uFlags
0x18003a3aa  call    cs:__imp_LocalAlloc
0x18003a3b0  jmp     loc_18003A313
0x18003a3b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3bc  lea     rax, WPP_GLOBAL_Control
0x18003a3c3  cmp     rcx, rax
0x18003a3c6  jz      loc_18003A1E8
0x18003a3cc  test    byte ptr [rcx+1Ch], 1
0x18003a3d0  jz      loc_18003A1E8
0x18003a3d6  mov     edx, 4Dh ; 'M'
0x18003a3db  jmp     loc_18008EC85
0x18003a3e0  test    byte ptr [rcx+1Ch], 1
0x18003a3e4  jz      loc_18003A1E8
0x18003a3ea  mov     edx, 4Bh ; 'K'
0x18003a3ef  jmp     loc_18008EC85
0x18003a3f4  mov     eax, 57h ; 'W'
0x18003a3f9  jmp     loc_18003A1ED
0x18003a3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a405  lea     rax, WPP_GLOBAL_Control
0x18003a40c  cmp     rcx, rax
0x18003a40f  jz      loc_18008EC56
0x18003a415  test    byte ptr [rcx+1Ch], 1
0x18003a419  jz      loc_18008EC56
0x18003a41f  mov     rcx, [rcx+10h]
0x18003a423  lea     r8, WPP_4536224b51c63d9a1593beb928bc374a_Traceguids
0x18003a42a  mov     edx, 45h ; 'E'
0x18003a42f  call    WPP_SF_
0x18003a434  nop
0x18003a435  jmp     loc_18008EC56
0x18008ec56  mov     r9b, 78h ; 'x'
0x18008ec59  mov     edx, 4B8h
0x18008ec5e  mov     r8d, 80090367h
0x18008ec64  mov     rcx, r13
0x18008ec67  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18008ec6c  mov     eax, 80090367h
0x18008ec71  mov     dword ptr [r13+5Ch], 60h ; '`'
0x18008ec79  mov     word ptr [r13+78h], 7802h
0x18008ec80  jmp     loc_18003A1ED
0x18008ec85  mov     rcx, [rcx+10h]
0x18008ec89  lea     r8, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids
0x18008ec90  call    WPP_SF_
0x18008ec95  nop
0x18008ec96  jmp     loc_18003A1E8
```
