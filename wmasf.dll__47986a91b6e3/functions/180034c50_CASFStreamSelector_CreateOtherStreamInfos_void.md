# CASFStreamSelector::CreateOtherStreamInfos(void)

- ea: `0x180034c50`
- end: `0x1800350ad`
- name: `?CreateOtherStreamInfos@CASFStreamSelector@@IEAAJXZ`
- size: `1117`
- prototype: `__int64 __fastcall(CASFStreamSelector *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039510`

## callees

- `0x180001174`
- `0x1800015d0`
- `0x1800310c0`
- `0x180031360`
- `0x180033484`
- `0x180033a40`
- `0x180034c50`
- `0x180038654`
- `0x18003f294`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamSelector::CreateOtherStreamInfos(CASFStreamSelector *this)
{
  __int64 v2; // rcx
  int v3; // ebx
  unsigned int v4; // r12d
  BOOL v5; // esi
  unsigned int v6; // r14d
  _WORD *v7; // rax
  __int64 v8; // rdx
  BOOL v9; // r15d
  CASFStreamSelector::STREAM_INFO *v10; // rax
  __int64 v11; // rax
  __int64 v12; // r14
  unsigned int v13; // esi
  __int16 v15; // [rsp+30h] [rbp-D0h]
  unsigned int v16; // [rsp+34h] [rbp-CCh]
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v23; // [rsp+64h] [rbp-9Ch] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v25; // [rsp+6Ch] [rbp-94h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  __int128 Buf2; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v28[512]; // [rsp+90h] [rbp-70h] BYREF

  v20 = 0;
  v2 = *((_QWORD *)this + 3);
  v19 = 0;
  v21 = 0;
  v18 = 0;
  v17 = 0;
  v3 = ASFGetHeaderObject(v2, &CLSID_ASFLanguageListObject, &IID_IASFLanguageListObject, &v21);
  if ( v3 >= 0 )
  {
    v3 = ASFGetRootObject(*((_QWORD *)this + 3), &CLSID_ASFHeaderObject, &IID_IASFUnknownContainer, &v20);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v20 + 72LL))(
             v20,
             &CLSID_ASFStreamPropertiesObject,
             &v19);
      if ( v3 >= 0 )
      {
        LOWORD(v4) = *((_DWORD *)this + 70);
        v16 = *((_DWORD *)this + 70);
        v15 = v4;
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 40LL))(v19);
        while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v19 + 24LL))(
                   v19,
                   1,
                   &v18,
                   &v26) )
        {
          v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(v18, &IID_IASFStreamPropertiesObject, &v17);
          if ( v3 < 0 )
            break;
          if ( v18 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v18 = 0;
          }
          v22[0] = 0;
          v5 = 0;
          (*(void (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v17 + 304LL))(v17, v22);
          v6 = 0;
          if ( *((_DWORD *)this + 70) )
          {
            while ( !v5 )
            {
              v7 = (_WORD *)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[]((char *)this + 64, v6);
              v5 = *v7 == v22[0];
              if ( ++v6 >= *((_DWORD *)this + 70) )
              {
                if ( *v7 != v22[0] )
                  goto LABEL_15;
                break;
              }
            }
            if ( v17 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              v17 = 0;
            }
          }
          else
          {
LABEL_15:
            v24 = 0;
            Buf2 = 0;
            v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 128LL))(v17, &v24);
            if ( v3 < 0 )
              break;
            LOBYTE(v8) = -1;
            v3 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v17 + 320LL))(v17, v8, v28);
            if ( v3 < 0 )
              break;
            v3 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v17 + 80LL))(v17, &Buf2);
            if ( v3 < 0 )
              break;
            v9 = 0;
            if ( *((_DWORD *)this + 13) )
              v9 = memcmp_0(&CLSID_ASFAudioMedia, &Buf2, 0x10u) == 0;
            v25 = 0;
            v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 240LL))(v17, &v25);
            if ( v17 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              v17 = 0;
            }
            v23 = 0;
            (*(void (__fastcall **)(__int64, _BYTE *, __int16 *))(*(_QWORD *)v21 + 120LL))(v21, v28, &v23);
            v10 = (CASFStreamSelector::STREAM_INFO *)operator new(0x110u);
            if ( !v10 || (v11 = CASFStreamSelector::STREAM_INFO::STREAM_INFO(v10), (v12 = v11) == 0) )
            {
              v3 = -2147024882;
              break;
            }
            *(_WORD *)v11 = v22[0];
            *(_DWORD *)(v11 + 4) = v24;
            *(_WORD *)(v11 + 2) = v23;
            *(_DWORD *)(v11 + 8) = v25 >> 31 == 0;
            v13 = (unsigned __int16)v4;
            *(_DWORD *)(v11 + 12) = memcmp_0(&CLSID_ASFVideoMedia, &Buf2, 0x10u) == 0;
            *(_DWORD *)(v12 + 16) = 0;
            *(_QWORD *)(v12 + 20) = 1000;
            if ( v9 )
            {
              v15 = v4 + 1;
              v4 = (unsigned __int16)v4;
              v13 = v16;
            }
            else
            {
              v4 = *((_DWORD *)this + 70);
            }
            while ( v13 < v4
                 && *(_DWORD *)(v12 + 4) >= *(_DWORD *)(CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                          (char *)this + 64,
                                                          v13)
                                                      + 4) )
              ++v13;
            CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::InsertAt((char *)this + 64, v13, v12);
            LOWORD(v4) = v15;
          }
        }
      }
    }
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180034c50  push    rbp
0x180034c52  push    rbx
0x180034c53  push    rsi
0x180034c54  push    rdi
0x180034c55  push    r12
0x180034c57  push    r13
0x180034c59  push    r14
0x180034c5b  push    r15
0x180034c5d  lea     rbp, [rsp-1A8h]
0x180034c65  sub     rsp, 2A8h
0x180034c6c  mov     rax, cs:__security_cookie
0x180034c73  xor     rax, rsp
0x180034c76  mov     [rbp+1E0h+var_50], rax
0x180034c7d  xor     r13d, r13d
0x180034c80  lea     r9, [rsp+2E0h+var_288]
0x180034c85  mov     rdi, rcx
0x180034c88  mov     [rsp+2E0h+var_290], r13
0x180034c8d  mov     rcx, [rcx+18h]
0x180034c91  lea     r8, IID_IASFLanguageListObject
0x180034c98  lea     rdx, CLSID_ASFLanguageListObject
0x180034c9f  mov     [rsp+2E0h+var_298], r13
0x180034ca4  mov     [rsp+2E0h+var_288], r13
0x180034ca9  mov     [rsp+2E0h+var_2A0], r13
0x180034cae  mov     [rsp+2E0h+var_2A8], r13
0x180034cb3  call    ASFGetHeaderObject
0x180034cb8  mov     ebx, eax
0x180034cba  test    eax, eax
0x180034cbc  js      loc_180035006
0x180034cc2  mov     rcx, [rdi+18h]
0x180034cc6  lea     r9, [rsp+2E0h+var_290]
0x180034ccb  lea     r8, IID_IASFUnknownContainer
0x180034cd2  lea     rdx, CLSID_ASFHeaderObject
0x180034cd9  call    ASFGetRootObject
0x180034cde  mov     ebx, eax
0x180034ce0  test    eax, eax
0x180034ce2  js      loc_180035006
0x180034ce8  mov     rcx, [rsp+2E0h+var_290]
0x180034ced  lea     r8, [rsp+2E0h+var_298]
0x180034cf2  lea     rdx, CLSID_ASFStreamPropertiesObject
0x180034cf9  mov     rax, [rcx]
0x180034cfc  mov     rax, [rax+48h]
0x180034d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d05  mov     ebx, eax
0x180034d07  test    eax, eax
0x180034d09  js      loc_180035006
0x180034d0f  mov     eax, [rdi+118h]
0x180034d15  movzx   r12d, ax
0x180034d19  mov     rcx, [rsp+2E0h+var_298]
0x180034d1e  mov     [rsp+2E0h+var_2AC], eax
0x180034d22  mov     [rsp+2E0h+var_2B0], ax
0x180034d27  mov     [rsp+2E0h+var_270], r13d
0x180034d2c  mov     rax, [rcx]
0x180034d2f  mov     rax, [rax+28h]
0x180034d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d38  mov     r15d, 1
0x180034d3e  mov     rcx, [rsp+2E0h+var_298]
0x180034d43  lea     r9, [rsp+2E0h+var_270]
0x180034d48  lea     r8, [rsp+2E0h+var_2A0]
0x180034d4d  mov     edx, r15d
0x180034d50  mov     rax, [rcx]
0x180034d53  mov     rax, [rax+18h]
0x180034d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d5c  test    eax, eax
0x180034d5e  jnz     loc_180035006
0x180034d64  mov     rcx, [rsp+2E0h+var_2A0]
0x180034d69  lea     r8, [rsp+2E0h+var_2A8]
0x180034d6e  lea     rdx, IID_IASFStreamPropertiesObject
0x180034d75  mov     rax, [rcx]
0x180034d78  mov     rax, [rax]
0x180034d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d80  mov     ebx, eax
0x180034d82  test    eax, eax
0x180034d84  js      loc_180035006
0x180034d8a  mov     rcx, [rsp+2E0h+var_2A0]
0x180034d8f  test    rcx, rcx
0x180034d92  jz      short loc_180034DA5
0x180034d94  mov     rax, [rcx]
0x180034d97  mov     rax, [rax+10h]
0x180034d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034da0  mov     [rsp+2E0h+var_2A0], r13
0x180034da5  mov     rcx, [rsp+2E0h+var_2A8]
0x180034daa  lea     rdx, [rsp+2E0h+var_280]
0x180034daf  mov     [rsp+2E0h+var_280], r13w
0x180034db5  mov     esi, r13d
0x180034db8  mov     rax, [rcx]
0x180034dbb  mov     rax, [rax+130h]
0x180034dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dc7  mov     r14d, r13d
0x180034dca  cmp     [rdi+118h], r13d
0x180034dd1  jbe     short loc_180034E23
0x180034dd3  test    esi, esi
0x180034dd5  jnz     short loc_180034DFF
0x180034dd7  lea     rcx, [rdi+40h]
0x180034ddb  mov     edx, r14d
0x180034dde  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x180034de3  movzx   ecx, [rsp+2E0h+var_280]
0x180034de8  cmp     [rax], cx
0x180034deb  cmovz   esi, r15d
0x180034def  add     r14d, r15d
0x180034df2  cmp     r14d, [rdi+118h]
0x180034df9  jb      short loc_180034DD3
0x180034dfb  test    esi, esi
0x180034dfd  jz      short loc_180034E23
0x180034dff  mov     rcx, [rsp+2E0h+var_2A8]
0x180034e04  test    rcx, rcx
0x180034e07  jz      loc_180034D3E
0x180034e0d  mov     rax, [rcx]
0x180034e10  mov     rax, [rax+10h]
0x180034e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e19  mov     [rsp+2E0h+var_2A8], r13
0x180034e1e  jmp     loc_180034D3E
0x180034e23  mov     rcx, [rsp+2E0h+var_2A8]
0x180034e28  lea     rdx, [rsp+2E0h+var_278]
0x180034e2d  xorps   xmm0, xmm0
0x180034e30  mov     [rsp+2E0h+var_278], r13d
0x180034e35  movups  [rsp+2E0h+Buf2], xmm0
0x180034e3a  mov     rax, [rcx]
0x180034e3d  mov     rax, [rax+80h]
0x180034e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e49  mov     ebx, eax
0x180034e4b  test    eax, eax
0x180034e4d  js      loc_180035006
0x180034e53  mov     rcx, [rsp+2E0h+var_2A8]
0x180034e58  lea     r8, [rbp+1E0h+var_250]
0x180034e5c  mov     dl, 0FFh
0x180034e5e  mov     rax, [rcx]
0x180034e61  mov     rax, [rax+140h]
0x180034e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e6d  mov     ebx, eax
0x180034e6f  test    eax, eax
0x180034e71  js      loc_180035006
0x180034e77  mov     rcx, [rsp+2E0h+var_2A8]
0x180034e7c  lea     rdx, [rsp+2E0h+Buf2]
0x180034e81  mov     rax, [rcx]
0x180034e84  mov     rax, [rax+50h]
0x180034e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e8d  mov     ebx, eax
0x180034e8f  test    eax, eax
0x180034e91  js      loc_180035006
0x180034e97  mov     r15d, r13d
0x180034e9a  cmp     [rdi+34h], r13d
0x180034e9e  jz      short loc_180034EC4
0x180034ea0  mov     r8d, 10h; Size
0x180034ea6  lea     rdx, [rsp+2E0h+Buf2]; Buf2
0x180034eab  lea     rcx, CLSID_ASFAudioMedia; Buf1
0x180034eb2  call    memcmp_0
0x180034eb7  test    eax, eax
0x180034eb9  mov     esi, 1
0x180034ebe  cmovz   r15d, esi
0x180034ec2  jmp     short loc_180034EC9
0x180034ec4  mov     esi, 1
0x180034ec9  mov     rcx, [rsp+2E0h+var_2A8]
0x180034ece  lea     rdx, [rsp+2E0h+var_274]
0x180034ed3  mov     [rsp+2E0h+var_274], r13d
0x180034ed8  mov     rax, [rcx]
0x180034edb  mov     rax, [rax+0F0h]
0x180034ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ee7  mov     rcx, [rsp+2E0h+var_2A8]
0x180034eec  mov     ebx, eax
0x180034eee  test    rcx, rcx
0x180034ef1  jz      short loc_180034F04
0x180034ef3  mov     rax, [rcx]
0x180034ef6  mov     rax, [rax+10h]
0x180034efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034eff  mov     [rsp+2E0h+var_2A8], r13
0x180034f04  mov     rcx, [rsp+2E0h+var_288]
0x180034f09  lea     r8, [rsp+2E0h+var_27C]
0x180034f0e  mov     [rsp+2E0h+var_27C], r13w
0x180034f14  lea     rdx, [rbp+1E0h+var_250]
0x180034f18  mov     rax, [rcx]
0x180034f1b  mov     rax, [rax+78h]
0x180034f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f24  mov     ecx, 110h; Size
0x180034f29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034f2e  test    rax, rax
0x180034f31  jz      loc_180035001
0x180034f37  mov     rcx, rax; this
0x180034f3a  call    ??0STREAM_INFO@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_INFO::STREAM_INFO(void)
0x180034f3f  mov     r14, rax
0x180034f42  test    rax, rax
0x180034f45  jz      loc_180035001
0x180034f4b  movzx   ecx, [rsp+2E0h+var_280]
0x180034f50  lea     rdx, [rsp+2E0h+Buf2]; Buf2
0x180034f55  mov     [rax], cx
0x180034f58  mov     r8d, 10h; Size
0x180034f5e  mov     ecx, [rsp+2E0h+var_278]
0x180034f62  mov     [rax+4], ecx
0x180034f65  movzx   ecx, [rsp+2E0h+var_27C]
0x180034f6a  mov     [rax+2], cx
0x180034f6e  mov     ecx, [rsp+2E0h+var_274]
0x180034f72  shr     ecx, 1Fh
0x180034f75  not     ecx
0x180034f77  and     ecx, esi
0x180034f79  mov     [rax+8], ecx
0x180034f7c  lea     rcx, CLSID_ASFVideoMedia; Buf1
0x180034f83  call    memcmp_0
0x180034f88  xor     ecx, ecx
0x180034f8a  movzx   esi, r12w
0x180034f8e  test    eax, eax
0x180034f90  setz    cl
0x180034f93  test    r15d, r15d
0x180034f96  mov     [r14+0Ch], ecx
0x180034f9a  lea     r15, [rdi+40h]
0x180034f9e  mov     dword ptr [r14+10h], 0
0x180034fa6  mov     qword ptr [r14+14h], 3E8h
0x180034fae  jz      short loc_180034FC3
0x180034fb0  inc     r12w
0x180034fb4  mov     [rsp+2E0h+var_2B0], r12w
0x180034fba  mov     r12d, esi
0x180034fbd  mov     esi, [rsp+2E0h+var_2AC]
0x180034fc1  jmp     short loc_180034FCA
0x180034fc3  mov     r12d, [rdi+118h]
0x180034fca  cmp     esi, r12d
0x180034fcd  jnb     short loc_180034FE6
0x180034fcf  mov     edx, esi
0x180034fd1  mov     rcx, r15
0x180034fd4  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x180034fd9  mov     eax, [rax+4]
0x180034fdc  cmp     [r14+4], eax
0x180034fe0  jb      short loc_180034FE6
0x180034fe2  inc     esi
0x180034fe4  jmp     short loc_180034FCA
0x180034fe6  mov     r8, r14
0x180034fe9  mov     edx, esi
0x180034feb  mov     rcx, r15
0x180034fee  call    ?InsertAt@?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEAAHKPEAUSTREAM_INFO@CASFStreamSelector@@@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::InsertAt(ulong,CASFStreamSelector::STREAM_INFO *)
0x180034ff3  movzx   r12d, [rsp+2E0h+var_2B0]
0x180034ff9  xor     r13d, r13d
0x180034ffc  jmp     loc_180034D38
0x180035001  mov     ebx, 8007000Eh
0x180035006  mov     rcx, [rsp+2E0h+var_290]
0x18003500b  test    rcx, rcx
0x18003500e  jz      short loc_180035021
0x180035010  mov     rax, [rcx]
0x180035013  mov     rax, [rax+10h]
0x180035017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003501c  mov     [rsp+2E0h+var_290], r13
0x180035021  mov     rcx, [rsp+2E0h+var_298]
0x180035026  test    rcx, rcx
0x180035029  jz      short loc_18003503C
0x18003502b  mov     rax, [rcx]
0x18003502e  mov     rax, [rax+10h]
0x180035032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035037  mov     [rsp+2E0h+var_298], r13
0x18003503c  mov     rcx, [rsp+2E0h+var_288]
0x180035041  test    rcx, rcx
0x180035044  jz      short loc_180035057
0x180035046  mov     rax, [rcx]
0x180035049  mov     rax, [rax+10h]
0x18003504d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035052  mov     [rsp+2E0h+var_288], r13
0x180035057  mov     rcx, [rsp+2E0h+var_2A0]
0x18003505c  test    rcx, rcx
0x18003505f  jz      short loc_180035072
0x180035061  mov     rax, [rcx]
0x180035064  mov     rax, [rax+10h]
0x180035068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003506d  mov     [rsp+2E0h+var_2A0], r13
0x180035072  mov     rcx, [rsp+2E0h+var_2A8]
0x180035077  test    rcx, rcx
0x18003507a  jz      short loc_180035088
0x18003507c  mov     rax, [rcx]
0x18003507f  mov     rax, [rax+10h]
0x180035083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035088  mov     eax, ebx
0x18003508a  mov     rcx, [rbp+1E0h+var_50]
0x180035091  xor     rcx, rsp; StackCookie
0x180035094  call    __security_check_cookie
0x180035099  add     rsp, 2A8h
0x1800350a0  pop     r15
0x1800350a2  pop     r14
0x1800350a4  pop     r13
0x1800350a6  pop     r12
0x1800350a8  pop     rdi
0x1800350a9  pop     rsi
0x1800350aa  pop     rbx
0x1800350ab  pop     rbp
0x1800350ac  retn
```
