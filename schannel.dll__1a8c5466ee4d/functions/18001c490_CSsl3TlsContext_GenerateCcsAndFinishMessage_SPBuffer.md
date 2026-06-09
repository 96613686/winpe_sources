# CSsl3TlsContext::GenerateCcsAndFinishMessage(SPBuffer *)

- ea: `0x18001c490`
- end: `0x18001c969`
- name: `?GenerateCcsAndFinishMessage@CSsl3TlsContext@@IEAAKPEAUSPBuffer@@@Z`
- size: `1241`
- prototype: `unsigned int __fastcall(CSsl3TlsContext *__hidden this, struct SPBuffer *)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000217c`
- `0x18001aecc`
- `0x18001b774`
- `0x18001b840`

## callees

- `0x18001c490`
- `0x18001c970`
- `0x18001cc80`
- `0x1800214f0`
- `0x180057c8c`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001c651`
- `ntdll!RtlReleaseResource` at `0x18001c651`
- `ntdll!RtlAcquireResourceShared` at `0x18001c5ff`
- `ntdll!RtlAcquireResourceShared` at `0x18001c5ff`
- `ncrypt!SslComputeFinishedHash` at `0x18001c63c`
- `ncrypt!SslComputeFinishedHash` at `0x18001c63c`
- `ncrypt!SslFreeObject` at `0x18001c554`
- `ncrypt!SslFreeObject` at `0x18001c554`

## pseudocode

```c
__int64 __fastcall CSsl3TlsContext::GenerateCcsAndFinishMessage(CSsl3TlsContext *this, struct SPBuffer *a2)
{
  char v2; // al
  __int64 v4; // r12
  __int64 v5; // r15
  __int64 v7; // rdx
  unsigned int v8; // r8d
  __int64 v9; // rsi
  __int64 v10; // r14
  unsigned int v11; // r13d
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rcx
  bool v15; // zf
  unsigned int v16; // edi
  _BYTE *v17; // rsi
  __int64 *v18; // rax
  unsigned int v19; // r12d
  __int64 v20; // r9
  __int64 v21; // r15
  size_t v22; // r12
  char v23; // dl
  unsigned int v24; // r11d
  __int64 v25; // r9
  __int16 v26; // r10
  _BYTE *v27; // r8
  _BYTE *v28; // r14
  __int16 v29; // cx
  __int64 v30; // rdx
  unsigned int v31; // eax
  __int64 v32; // r9
  unsigned int v33; // esi
  __int64 result; // rax
  __int16 v35; // cx
  unsigned int v36; // [rsp+80h] [rbp+8h]
  unsigned int v37; // [rsp+80h] [rbp+8h]
  int v38; // [rsp+88h] [rbp+10h]
  _BYTE *v39; // [rsp+90h] [rbp+18h]
  unsigned int v40; // [rsp+98h] [rbp+20h]

  v2 = *((_BYTE *)this + 1953);
  v4 = 0;
  v5 = *((_QWORD *)this + 232);
  v7 = *((_QWORD *)a2 + 1) + *((unsigned int *)a2 + 1);
  if ( !v2 && (*((_BYTE *)this + 32) & 4) != 0 )
    v8 = *((_DWORD *)this + 11);
  else
    v8 = 0;
  v9 = *((unsigned int *)this + 15);
  v10 = 12;
  v11 = 12;
  v36 = v8;
  v40 = *((_DWORD *)this + 15);
  if ( !v2 )
    v11 = 4;
  *(_BYTE *)(v9 + v8 + v7) = 1;
  if ( *((_BYTE *)this + 1953) )
  {
    v29 = *((_WORD *)this + 17);
    *(_BYTE *)(v7 + 2) = v29;
    *(_BYTE *)(v7 + 1) = HIBYTE(v29);
    *(_BYTE *)v7 = 20;
    *(_WORD *)(v7 + 11) = 256;
    *((_DWORD *)a2 + 1) += v8 + v9 + 1;
  }
  else
  {
    v12 = CSsl3TlsContext::WrapMessage(this, a2, 20, 1);
    v37 = v12;
    if ( v12 )
    {
      LOBYTE(v13) = 80;
      CSslContext::SetErrorAndFatalAlert(this, 950, v12, v13);
      return v37;
    }
    *((_WORD *)this + 16) |= 8u;
    *((_WORD *)this + 16) |= 4u;
    if ( !*((_BYTE *)this + 1953) )
    {
      v14 = *((_QWORD *)this + 234);
      if ( v14 )
        SslFreeObject(v14, 0);
    }
    v15 = *((_BYTE *)this + 1953) == 0;
    *((_QWORD *)this + 234) = *((_QWORD *)this + 236);
    *((_QWORD *)this + 236) = 0;
    if ( v15 )
      *((_QWORD *)this + 238) = 0;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
    if ( (*((_BYTE *)this + 32) & 4) != 0 )
    {
      v8 = *((_DWORD *)this + 11);
      v36 = v8;
    }
    else
    {
      v8 = 0;
      v36 = 0;
    }
  }
  v16 = 12;
  v38 = *((_DWORD *)this + 22) & 0xA2AA0;
  if ( (*((_DWORD *)this + 22) & 0xF3FC0) == 0 )
    v16 = 36;
  v39 = (_BYTE *)(*((_QWORD *)a2 + 1) + *((unsigned int *)a2 + 1));
  v17 = &v39[v8 + v11 + v9];
  RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL), 1u);
  v18 = (__int64 *)*((_QWORD *)this + 1);
  if ( v18 )
    v4 = *v18;
  v19 = SslComputeFinishedHash(
          v4,
          *(_QWORD *)(*((_QWORD *)this + 14) + 32LL),
          *((_QWORD *)this + 289),
          v17,
          v16,
          2 - (unsigned int)(v38 != 0));
  RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL));
  if ( v19 )
  {
    LOBYTE(v20) = 80;
    CSslContext::SetErrorAndFatalAlert(this, 901, v19, v20);
    return v19;
  }
  v21 = (unsigned __int16)v5 & 0x8000;
  if ( !*((_BYTE *)this + 2060) )
  {
    memcpy_0((char *)this + 2061, v17, v16);
    *((_BYTE *)this + 2060) = 1;
    CSsl3TlsContext::SetTokenBindingEKM(this);
  }
  if ( v38 )
  {
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
    v22 = v16;
    memcpy_0((char *)this + 2097, v17, v16);
    *((_DWORD *)this + 534) = v16;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
    v22 = v16;
    memcpy_0((char *)this + 2140, v17, v16);
    *((_DWORD *)this + 544) = v16;
  }
  v23 = *((_BYTE *)this + 1953);
  v24 = v40;
  v25 = v36;
  v26 = *((_WORD *)this + 970);
  v27 = &v39[v40 + v36];
  if ( !v23 )
    v10 = 4;
  *v27 = 20;
  if ( v23 )
  {
    v27[5] = v26;
    v27[4] = HIBYTE(v26);
    *(_DWORD *)(v27 + 7) = 0;
    v27[6] = 0;
    v27[11] = v16;
  }
  v27[3] = v16;
  *(_WORD *)(v27 + 1) = 0;
  if ( v17 )
  {
    memcpy_0(&v27[v10], v17, v22);
    v25 = v36;
    v24 = v40;
  }
  if ( *((_BYTE *)this + 1953) )
    ++*((_WORD *)this + 970);
  if ( v21 )
  {
    if ( !v38 )
      goto LABEL_40;
LABEL_45:
    v28 = v39;
    v30 = (unsigned int)v25;
    LOBYTE(v25) = 1;
    v31 = (*(__int64 (__fastcall **)(CSsl3TlsContext *, _BYTE *, _QWORD, __int64))(*(_QWORD *)this + 568LL))(
            this,
            &v39[v24 + v30],
            v16 + v11,
            v25);
    v33 = v31;
    if ( v31 )
    {
      LOBYTE(v32) = 80;
      CSslContext::SetErrorAndFatalAlert(this, 1000, v31, v32);
      return v33;
    }
    goto LABEL_46;
  }
  if ( !v38 )
    goto LABEL_45;
LABEL_40:
  v28 = v39;
LABEL_46:
  if ( !*((_BYTE *)this + 1953) )
    return CSsl3TlsContext::WrapMessage(this, a2, 22, v16 + v11);
  *((_DWORD *)a2 + 1) += v36 + v16 + v40 + v11;
  v35 = *((_WORD *)this + 17);
  v28[2] = v35;
  v28[1] = HIBYTE(v35);
  v28[12] = v16 + v11;
  v28[11] = (unsigned __int16)(v16 + v11) >> 8;
  result = 0;
  *v28 = 22;
  return result;
}

```

## disassembly

```asm
0x18001c490  push    rbx
0x18001c492  push    rbp
0x18001c493  push    rsi
0x18001c494  push    rdi
0x18001c495  push    r12
0x18001c497  push    r13
0x18001c499  push    r14
0x18001c49b  push    r15
0x18001c49d  sub     rsp, 38h
0x18001c4a1  movzx   eax, byte ptr [rcx+7A1h]
0x18001c4a8  mov     rbp, rdx
0x18001c4ab  mov     edx, [rdx+4]
0x18001c4ae  xor     r12d, r12d
0x18001c4b1  mov     r15, [rcx+740h]
0x18001c4b8  mov     rbx, rcx
0x18001c4bb  add     rdx, [rbp+8]
0x18001c4bf  test    al, al
0x18001c4c1  jnz     short loc_18001C4CD
0x18001c4c3  test    byte ptr [rcx+20h], 4
0x18001c4c7  jnz     loc_18001C774
0x18001c4cd  mov     r8d, r12d
0x18001c4d0  mov     esi, [rcx+3Ch]
0x18001c4d3  test    al, al
0x18001c4d5  mov     r14d, 0Ch
0x18001c4db  mov     eax, r8d
0x18001c4de  mov     r13d, r14d
0x18001c4e1  mov     [rsp+78h+arg_0], r8d
0x18001c4e9  mov     ecx, 4
0x18001c4ee  mov     [rsp+78h+arg_18], rsi
0x18001c4f6  cmovz   r13d, ecx
0x18001c4fa  add     rax, rsi
0x18001c4fd  mov     byte ptr [rax+rdx], 1
0x18001c501  cmp     byte ptr [rbx+7A1h], 0
0x18001c508  jnz     loc_18001C78E
0x18001c50e  mov     r9d, 1
0x18001c514  mov     r8d, 14h
0x18001c51a  mov     rdx, rbp
0x18001c51d  mov     rcx, rbx
0x18001c520  call    ?WrapMessage@CSsl3TlsContext@@IEAAKPEAUSPBuffer@@W4eTlsRecordType@@K@Z; CSsl3TlsContext::WrapMessage(SPBuffer *,eTlsRecordType,ulong)
0x18001c525  mov     [rsp+78h+arg_0], eax
0x18001c52c  test    eax, eax
0x18001c52e  jnz     loc_18001C824
0x18001c534  or      word ptr [rbx+20h], 8
0x18001c539  or      word ptr [rbx+20h], 4
0x18001c53e  cmp     [rbx+7A1h], al
0x18001c544  jnz     short loc_18001C55A
0x18001c546  mov     rcx, [rbx+750h]
0x18001c54d  test    rcx, rcx
0x18001c550  jz      short loc_18001C55A
0x18001c552  xor     edx, edx
0x18001c554  call    cs:__imp_SslFreeObject
0x18001c55a  cmp     byte ptr [rbx+7A1h], 0
0x18001c561  mov     rax, [rbx+760h]
0x18001c568  mov     [rbx+750h], rax
0x18001c56f  mov     [rbx+760h], r12
0x18001c576  jnz     short loc_18001C57F
0x18001c578  mov     [rbx+770h], r12
0x18001c57f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c586  lea     rax, WPP_GLOBAL_Control
0x18001c58d  cmp     rcx, rax
0x18001c590  jz      short loc_18001C59C
0x18001c592  test    byte ptr [rcx+1Ch], 4
0x18001c596  jnz     loc_18001C929
0x18001c59c  test    byte ptr [rbx+20h], 4
0x18001c5a0  jnz     loc_18001C77D
0x18001c5a6  mov     r8d, r12d
0x18001c5a9  mov     [rsp+78h+arg_0], r12d
0x18001c5b1  mov     ecx, [rbx+58h]
0x18001c5b4  mov     eax, 24h ; '$'
0x18001c5b9  mov     edx, [rbp+4]
0x18001c5bc  and     ecx, 0A2AA0h
0x18001c5c2  add     rdx, [rbp+8]
0x18001c5c6  mov     edi, r14d
0x18001c5c9  test    dword ptr [rbx+58h], 0F3FC0h
0x18001c5d0  mov     [rsp+78h+arg_8], ecx
0x18001c5d7  cmovz   edi, eax
0x18001c5da  mov     ecx, r8d
0x18001c5dd  mov     eax, r13d
0x18001c5e0  add     rsi, rax
0x18001c5e3  mov     [rsp+78h+arg_10], rdx
0x18001c5eb  mov     rax, [rbx+70h]
0x18001c5ef  add     rsi, rcx
0x18001c5f2  add     rsi, rdx
0x18001c5f5  mov     dl, 1; Wait
0x18001c5f7  mov     rcx, [rax+28h]
0x18001c5fb  add     rcx, 50h ; 'P'; Resource
0x18001c5ff  call    cs:__imp_RtlAcquireResourceShared
0x18001c605  mov     eax, [rsp+78h+arg_8]
0x18001c60c  neg     eax
0x18001c60e  mov     rax, [rbx+70h]
0x18001c612  sbb     ecx, ecx
0x18001c614  add     ecx, 2
0x18001c617  mov     rdx, [rax+20h]
0x18001c61b  mov     rax, [rbx+8]
0x18001c61f  test    rax, rax
0x18001c622  jz      short loc_18001C627
0x18001c624  mov     r12, [rax]
0x18001c627  mov     r8, [rbx+908h]
0x18001c62e  mov     r9, rsi
0x18001c631  mov     [rsp+78h+var_50], ecx
0x18001c635  mov     rcx, r12
0x18001c638  mov     [rsp+78h+var_58], edi
0x18001c63c  call    cs:__imp_SslComputeFinishedHash
0x18001c642  mov     rcx, [rbx+70h]
0x18001c646  mov     r12d, eax
0x18001c649  mov     rcx, [rcx+28h]
0x18001c64d  add     rcx, 50h ; 'P'; Resource
0x18001c651  call    cs:__imp_RtlReleaseResource
0x18001c657  test    r12d, r12d
0x18001c65a  jnz     loc_18001C857
0x18001c660  and     r15d, 8000h
0x18001c667  cmp     [rbx+80Ch], r12b
0x18001c66e  jnz     short loc_18001C691
0x18001c670  mov     r8d, edi; Size
0x18001c673  lea     rcx, [rbx+80Dh]; void *
0x18001c67a  mov     rdx, rsi; Src
0x18001c67d  call    memcpy_0
0x18001c682  mov     rcx, rbx; this
0x18001c685  mov     byte ptr [rbx+80Ch], 1
0x18001c68c  call    ?SetTokenBindingEKM@CSsl3TlsContext@@IEAAKXZ; CSsl3TlsContext::SetTokenBindingEKM(void)
0x18001c691  cmp     [rsp+78h+arg_8], 0
0x18001c699  jz      loc_18001C86F
0x18001c69f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6a6  lea     rax, WPP_GLOBAL_Control
0x18001c6ad  cmp     rcx, rax
0x18001c6b0  jz      short loc_18001C6BF
0x18001c6b2  test    dword ptr [rcx+1Ch], 800h
0x18001c6b9  jnz     loc_18001C943
0x18001c6bf  lea     rcx, [rbx+831h]; void *
0x18001c6c6  mov     r8d, edi; Size
0x18001c6c9  mov     rdx, rsi; Src
0x18001c6cc  mov     r12d, edi
0x18001c6cf  call    memcpy_0
0x18001c6d4  mov     [rbx+858h], edi
0x18001c6da  movzx   edx, byte ptr [rbx+7A1h]
0x18001c6e1  mov     r11, [rsp+78h+arg_18]
0x18001c6e9  mov     r8, [rsp+78h+arg_10]
0x18001c6f1  mov     r9d, [rsp+78h+arg_0]
0x18001c6f9  movzx   r10d, word ptr [rbx+794h]
0x18001c701  mov     eax, r11d
0x18001c704  add     r8, rax
0x18001c707  mov     eax, 4
0x18001c70c  add     r8, r9
0x18001c70f  test    dl, dl
0x18001c711  cmovz   r14, rax
0x18001c715  mov     byte ptr [r8], 14h
0x18001c719  jnz     loc_18001C8C2
0x18001c71f  mov     [r8+3], dil
0x18001c723  mov     word ptr [r8+1], 0
0x18001c72a  test    rsi, rsi
0x18001c72d  jz      short loc_18001C74E
0x18001c72f  lea     rcx, [r14+r8]; void *
0x18001c733  mov     rdx, rsi; Src
0x18001c736  mov     r8, r12; Size
0x18001c739  call    memcpy_0
0x18001c73e  mov     r9d, [rsp+78h+arg_0]
0x18001c746  mov     r11, [rsp+78h+arg_18]
0x18001c74e  cmp     byte ptr [rbx+7A1h], 0
0x18001c755  jnz     loc_18001C95D
0x18001c75b  test    r15, r15
0x18001c75e  jnz     short loc_18001C7B4
0x18001c760  cmp     [rsp+78h+arg_8], r15d
0x18001c768  jz      short loc_18001C7BE
0x18001c76a  mov     r14, [rsp+78h+arg_10]
0x18001c772  jmp     short loc_18001C7F1
0x18001c774  mov     r8d, [rcx+2Ch]
0x18001c778  jmp     loc_18001C4D0
0x18001c77d  mov     r8d, [rbx+2Ch]
0x18001c781  mov     [rsp+78h+arg_0], r8d
0x18001c789  jmp     loc_18001C5B1
0x18001c78e  movzx   ecx, word ptr [rbx+22h]
0x18001c792  mov     eax, ecx
0x18001c794  mov     [rdx+2], cl
0x18001c797  shr     eax, 8
0x18001c79a  mov     [rdx+1], al
0x18001c79d  lea     eax, [rsi+1]
0x18001c7a0  add     eax, r8d
0x18001c7a3  mov     byte ptr [rdx], 14h
0x18001c7a6  mov     word ptr [rdx+0Bh], 100h
0x18001c7ac  add     [rbp+4], eax
0x18001c7af  jmp     loc_18001C5B1
0x18001c7b4  cmp     [rsp+78h+arg_8], 0
0x18001c7bc  jz      short loc_18001C76A
0x18001c7be  mov     r10, [rbx]
0x18001c7c1  lea     r8d, [rdi+r13]
0x18001c7c5  mov     r14, [rsp+78h+arg_10]
0x18001c7cd  mov     rcx, rbx
0x18001c7d0  mov     edx, r9d
0x18001c7d3  mov     r9b, 1
0x18001c7d6  mov     eax, r11d
0x18001c7d9  add     rax, r14
0x18001c7dc  add     rdx, rax
0x18001c7df  mov     rax, [r10+238h]
0x18001c7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7eb  mov     esi, eax
0x18001c7ed  test    eax, eax
0x18001c7ef  jnz     short loc_18001C840
0x18001c7f1  cmp     byte ptr [rbx+7A1h], 0
0x18001c7f8  jnz     loc_18001C8E5
0x18001c7fe  lea     r9d, [rdi+r13]
0x18001c802  mov     r8d, 16h
0x18001c808  mov     rdx, rbp
0x18001c80b  mov     rcx, rbx
0x18001c80e  call    ?WrapMessage@CSsl3TlsContext@@IEAAKPEAUSPBuffer@@W4eTlsRecordType@@K@Z; CSsl3TlsContext::WrapMessage(SPBuffer *,eTlsRecordType,ulong)
0x18001c813  add     rsp, 38h
0x18001c817  pop     r15
0x18001c819  pop     r14
0x18001c81b  pop     r13
0x18001c81d  pop     r12
0x18001c81f  pop     rdi
0x18001c820  pop     rsi
0x18001c821  pop     rbp
0x18001c822  pop     rbx
0x18001c823  retn
0x18001c824  mov     r9b, 50h ; 'P'
0x18001c827  mov     r8d, eax
0x18001c82a  mov     edx, 3B6h
0x18001c82f  mov     rcx, rbx
0x18001c832  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18001c837  mov     eax, [rsp+78h+arg_0]
0x18001c83e  jmp     short loc_18001C813
0x18001c840  mov     r9b, 50h ; 'P'
0x18001c843  mov     r8d, esi
0x18001c846  mov     edx, 3E8h
0x18001c84b  mov     rcx, rbx
0x18001c84e  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18001c853  mov     eax, esi
0x18001c855  jmp     short loc_18001C813
0x18001c857  mov     r9b, 50h ; 'P'
0x18001c85a  mov     r8d, r12d
0x18001c85d  mov     edx, 385h
0x18001c862  mov     rcx, rbx
0x18001c865  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18001c86a  mov     eax, r12d
0x18001c86d  jmp     short loc_18001C813
0x18001c86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c876  lea     rax, WPP_GLOBAL_Control
0x18001c87d  cmp     rcx, rax
0x18001c880  jnz     short loc_18001C8A2
0x18001c882  lea     rcx, [rbx+85Ch]; void *
0x18001c889  mov     r8d, edi; Size
0x18001c88c  mov     rdx, rsi; Src
0x18001c88f  mov     r12d, edi
0x18001c892  call    memcpy_0
0x18001c897  mov     [rbx+880h], edi
0x18001c89d  jmp     loc_18001C6DA
0x18001c8a2  test    dword ptr [rcx+1Ch], 800h
0x18001c8a9  jz      short loc_18001C882
0x18001c8ab  mov     rcx, [rcx+10h]
0x18001c8af  lea     r8, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids
0x18001c8b6  mov     edx, 42h ; 'B'
0x18001c8bb  call    WPP_SF_
0x18001c8c0  jmp     short loc_18001C882
0x18001c8c2  mov     [r8+5], r10b
0x18001c8c6  shr     r10w, 8
0x18001c8cb  mov     [r8+4], r10b
0x18001c8cf  mov     dword ptr [r8+7], 0
0x18001c8d7  mov     byte ptr [r8+6], 0
0x18001c8dc  mov     [r8+0Bh], dil
0x18001c8e0  jmp     loc_18001C71F
0x18001c8e5  mov     eax, [rbp+4]
0x18001c8e8  add     eax, r13d
0x18001c8eb  add     eax, dword ptr [rsp+78h+arg_18]
0x18001c8f2  add     eax, edi
0x18001c8f4  add     eax, [rsp+78h+arg_0]
0x18001c8fb  mov     [rbp+4], eax
0x18001c8fe  movzx   ecx, word ptr [rbx+22h]
0x18001c902  mov     eax, ecx
0x18001c904  mov     [r14+2], cl
0x18001c908  shr     eax, 8
0x18001c90b  mov     [r14+1], al
0x18001c90f  lea     eax, [rdi+r13]
0x18001c913  mov     [r14+0Ch], al
0x18001c917  shr     eax, 8
0x18001c91a  mov     [r14+0Bh], al
0x18001c91e  xor     eax, eax
0x18001c920  mov     byte ptr [r14], 16h
0x18001c924  jmp     loc_18001C813
0x18001c929  mov     rcx, [rcx+10h]
0x18001c92d  lea     r8, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids
0x18001c934  mov     edx, 3Bh ; ';'
0x18001c939  call    WPP_SF_
0x18001c93e  jmp     loc_18001C59C
0x18001c943  mov     rcx, [rcx+10h]
0x18001c947  lea     r8, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids
0x18001c94e  mov     edx, 41h ; 'A'
0x18001c953  call    WPP_SF_
0x18001c958  jmp     loc_18001C6BF
0x18001c95d  inc     word ptr [rbx+794h]
0x18001c964  jmp     loc_18001C75B
```
