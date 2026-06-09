# p9fs::Handler::HandleWOpen(p9fs::SpanReader &,p9fs::Handler::MessageResponse &)

- ea: `0x180014b78`
- end: `0x180015723`
- name: `?HandleWOpen@Handler@p9fs@@AEAAJAEAVSpanReader@2@AEAVMessageResponse@12@@Z`
- size: `2987`
- prototype: `__int64 __fastcall(p9fs::Handler *__hidden this, struct p9fs::SpanReader *, struct p9fs::Handler::MessageResponse *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18000f528`

## callees

- `0x180004120`
- `0x1800074e0`
- `0x18000fe7c`
- `0x180014b78`
- `0x1800167e0`
- `0x180016840`
- `0x180016ad8`
- `0x18001bd28`
- `0x18001c93c`
- `0x180034010`

## string_xrefs

- `0x1800155d5`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall p9fs::Handler::HandleWOpen(
        p9fs::Handler *this,
        struct p9fs::SpanReader *a2,
        struct p9fs::Handler::MessageResponse *a3,
        const char *a4)
{
  p9fs::Handler *v5; // rdi
  gsl::details *v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v9; // r8
  const char *v10; // r9
  unsigned int v11; // r11d
  char *v12; // r15
  const char *v13; // r9
  unsigned int v14; // r15d
  char *v15; // r10
  char *v16; // rdx
  char *v17; // r13
  int v18; // r13d
  __int64 v19; // rdx
  unsigned __int16 v20; // r12
  __int64 v21; // rdi
  void (__fastcall *v22)(__int64, _BYTE *, __int128 *); // rbx
  int v23; // eax
  int v24; // ebx
  __int128 v25; // xmm6
  unsigned int v26; // r14d
  char v27; // r12
  char v28; // bl
  __int64 v29; // rax
  __int64 v30; // rax
  unsigned int v31; // esi
  volatile signed __int32 *v32; // rdi
  volatile signed __int32 *v33; // rdi
  p9fs::Handler *v34; // rcx
  __int64 v35; // r8
  volatile signed __int32 *v36; // rdi
  __int64 v37; // r9
  char v38; // r8
  __int64 v39; // rcx
  volatile signed __int32 *v40; // rdi
  volatile signed __int32 *v41; // rdi
  char v42; // cl
  volatile signed __int32 *v43; // rdi
  volatile signed __int32 *v44; // rdi
  char v45; // al
  volatile signed __int32 *v46; // rdi
  volatile signed __int32 *v47; // rdi
  volatile signed __int32 *v48; // rdi
  volatile signed __int32 *v49; // rdi
  volatile signed __int32 *v50; // rdi
  volatile signed __int32 *v51; // rdi
  volatile signed __int32 *v52; // rdi
  int v53; // eax
  volatile signed __int32 *v54; // rdi
  __int128 v55; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A8h]
  struct p9fs::Handler::MessageResponse *v57; // [rsp+68h] [rbp-A0h]
  int v58; // [rsp+70h] [rbp-98h]
  unsigned int v59; // [rsp+74h] [rbp-94h]
  __int64 v60; // [rsp+78h] [rbp-90h]
  p9fs::Handler *v61; // [rsp+80h] [rbp-88h]
  __int128 v62; // [rsp+88h] [rbp-80h] BYREF
  char v63; // [rsp+98h] [rbp-70h] BYREF
  __int128 v64; // [rsp+A0h] [rbp-68h]
  __int128 v65; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v66; // [rsp+C8h] [rbp-40h]
  __int128 v67; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v68[12]; // [rsp+E8h] [rbp-20h] BYREF
  char v69; // [rsp+F4h] [rbp-14h]
  __int16 v70; // [rsp+F5h] [rbp-13h]
  char v71; // [rsp+F7h] [rbp-11h]
  _BYTE v72[8]; // [rsp+F8h] [rbp-10h] BYREF
  unsigned int v73; // [rsp+100h] [rbp-8h]
  __int64 v74; // [rsp+104h] [rbp-4h]
  char v75; // [rsp+10Ch] [rbp+4h]
  __int16 v76; // [rsp+10Dh] [rbp+5h]
  char v77; // [rsp+10Fh] [rbp+7h]
  _BYTE v78[8]; // [rsp+110h] [rbp+8h] BYREF
  char *v79; // [rsp+118h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v57 = a3;
  v5 = this;
  v61 = this;
  if ( !*((_BYTE *)this + 118) )
    return 4294967201LL;
  v7 = (gsl::details *)*((_QWORD *)a2 + 2);
  v8 = *(_QWORD *)a2 - (_QWORD)v7;
  if ( v8 < 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      a4);
  if ( *(_QWORD *)a2 < (unsigned __int64)v7 )
    goto LABEL_163;
  v9 = *((_QWORD *)a2 + 1);
  v10 = (char *)v7 + 4;
  *((_QWORD *)a2 + 2) = (char *)v7 + 4;
  if ( v8 - 4 < 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      v10);
  if ( *(_QWORD *)a2 < (unsigned __int64)v10 || *(_QWORD *)a2 - (_QWORD)v10 < 4u )
    goto LABEL_163;
  v11 = *(_DWORD *)((char *)v7 + v9);
  v12 = (char *)v7 + 8;
  *((_QWORD *)a2 + 2) = (char *)v7 + 8;
  if ( v8 - 8 < 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      v10);
  if ( *(_QWORD *)a2 < (unsigned __int64)v12 || *(_QWORD *)a2 - (_QWORD)v12 < 4u )
    goto LABEL_163;
  v66 = *(_DWORD *)&v10[v9];
  v13 = (char *)v7 + 12;
  *((_QWORD *)a2 + 2) = (char *)v7 + 12;
  if ( v8 - 12 < 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      v13);
  if ( *(_QWORD *)a2 < (unsigned __int64)v13 || *(_QWORD *)a2 - (_QWORD)v13 < 4u )
    goto LABEL_163;
  v14 = *(_DWORD *)&v12[v9];
  v15 = (char *)v7 + 16;
  *((_QWORD *)a2 + 2) = (char *)v7 + 16;
  if ( v8 - 16 < 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      v13);
  if ( *(_QWORD *)a2 < (unsigned __int64)v15 || *(_QWORD *)a2 - (_QWORD)v15 < 4u )
    goto LABEL_163;
  LODWORD(v60) = *(_DWORD *)&v13[v9];
  v7 = (gsl::details *)((char *)v7 + 20);
  *((_QWORD *)a2 + 2) = v7;
  if ( *(_QWORD *)a2 - (_QWORD)v7 < 4u )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      v13);
  if ( *(_QWORD *)a2 < (unsigned __int64)v7 )
    goto LABEL_163;
  v59 = *(_DWORD *)&v15[v9];
  v16 = (char *)v7 + 4;
  *((_QWORD *)a2 + 2) = (char *)v7 + 4;
  if ( *(_QWORD *)a2 - ((_QWORD)v7 + 4) < 8u )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      v13);
  if ( *(_QWORD *)a2 < (unsigned __int64)v16 )
    goto LABEL_163;
  v58 = *(_DWORD *)((char *)v7 + v9);
  v17 = (char *)v7 + 12;
  *((_QWORD *)a2 + 2) = (char *)v7 + 12;
  if ( *(_QWORD *)a2 - ((_QWORD)v7 + 12) < 2u )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      v13);
  if ( *(_QWORD *)a2 < (unsigned __int64)v17 )
LABEL_163:
    gsl::details::terminate(v7);
  *(_QWORD *)&v62 = *(_QWORD *)&v16[v9];
  *((_QWORD *)a2 + 2) = (char *)v7 + 14;
  v18 = *(unsigned __int16 *)&v17[v9];
  v55 = 0;
  p9fs::Handler::LookupFid(v5, &v55, v11);
  v67 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v55 + 208LL))(v55, &v67);
  (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)v67 + 232LL))(v67, v68);
  if ( !(_WORD)v18 )
  {
    v28 = 1;
    v27 = 1;
    v42 = v69;
LABEL_99:
    v45 = v60;
    if ( (v60 & 2) != 0 && v42 < 0 )
    {
      v46 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
          if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
        }
      }
      v47 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
      if ( *((_QWORD *)&v55 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
          if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
        }
      }
      return 4294967275LL;
    }
    if ( (v14 & 0x10000) != 0 && v42 >= 0 )
    {
      v48 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
          if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
        }
      }
      v49 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
      if ( *((_QWORD *)&v55 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
          if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
        }
      }
      return 4294967276LL;
    }
    if ( (v60 & 1) != 0 )
    {
      v26 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v67 + 200LL))(v67, 8);
      if ( (v26 & 0x80000000) != 0 )
        goto LABEL_123;
      v42 = v69;
      v45 = v60;
    }
    if ( (v42 & 2) != 0 )
    {
      if ( (v45 & 4) == 0 )
      {
LABEL_83:
        LOBYTE(v19) = 4;
LABEL_72:
        v35 = (unsigned __int16)v18;
        v34 = v5;
        goto LABEL_49;
      }
      goto LABEL_134;
    }
    if ( v27 )
    {
      v53 = v14 & 3;
      if ( v53 != 3 )
      {
        if ( v42 >= 0 || (unsigned int)(v53 - 1) > 1 )
        {
LABEL_153:
          (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(*(_QWORD *)v67 + 32LL))(v67, v78, v14 & 0xFFFFFF3F);
          if ( !v78[0] )
          {
            v31 = (unsigned int)v79;
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x426,
              (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
              (const char *)(unsigned int)v79,
              (int)"%hs",
              "result");
            v54 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
            if ( *((_QWORD *)&v67 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
                if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
              }
            }
            v33 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
            if ( !*((_QWORD *)&v55 + 1) )
              return v31;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) != 1 )
              return v31;
            (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
            if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) != 1 )
              return v31;
            goto LABEL_56;
          }
          goto LABEL_134;
        }
LABEL_152:
        v14 &= 0xFFFFFFFC;
        goto LABEL_153;
      }
      if ( (v14 & 0x200) != 0 )
        goto LABEL_152;
    }
LABEL_134:
    LOBYTE(v19) = v28;
    v26 = p9fs::Handler::WriteWOpenReply(v5, v19, (unsigned __int16)v18, v67, v62, v57);
    if ( (v26 & 0x80000000) == 0 )
    {
      v62 = 0;
      if ( *((_QWORD *)&v67 + 1) )
        _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 1u);
      v62 = v67;
      p9fs::Handler::EmplaceFid(v5, v66, &v62);
      v51 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
          if ( _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
        }
      }
      v52 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
      if ( *((_QWORD *)&v55 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
          if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
        }
      }
      return 0;
    }
LABEL_123:
    v50 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
    if ( *((_QWORD *)&v67 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
        if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
      }
    }
    v41 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
    if ( *((_QWORD *)&v55 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
        if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
          goto LABEL_80;
      }
    }
    return v26;
  }
  v20 = 0;
  if ( v18 - 1 <= 0 )
    goto LABEL_28;
  do
  {
    v21 = v67;
    v22 = *(void (__fastcall **)(__int64, _BYTE *, __int128 *))(*(_QWORD *)v67 + 8LL);
    v65 = *(_OWORD *)p9fs::SpanReader::Name(a2, v72);
    v22(v21, v78, &v65);
    if ( !v78[0] )
    {
      v31 = (unsigned int)v79;
      if ( (_DWORD)v79 == -20 )
      {
        LOBYTE(v19) = 4;
      }
      else
      {
        if ( (_DWORD)v79 != -2 )
        {
          v32 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
          if ( *((_QWORD *)&v67 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
              if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
            }
          }
          v33 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
          if ( !*((_QWORD *)&v55 + 1) )
            return v31;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) != 1 )
            return v31;
          (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
          if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) != 1 )
            return v31;
LABEL_56:
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
          return v31;
        }
        LOBYTE(v19) = 2;
      }
      v34 = v61;
      v35 = v20;
LABEL_49:
      v31 = p9fs::Handler::WriteWOpenReply(v34, v19, v35, v67, v62, v57);
      v36 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
          if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
        }
      }
      v33 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
      if ( !*((_QWORD *)&v55 + 1) )
        return v31;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) != 1 )
        return v31;
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) != 1 )
        return v31;
      goto LABEL_56;
    }
    ++v20;
  }
  while ( v20 < v18 - 1 );
  v5 = v61;
LABEL_28:
  v65 = 0;
  p9fs::SpanReader::Name(a2, &v65);
  LODWORD(v56) = 0;
  v23 = v14 & 0xC0;
  LODWORD(v61) = v23;
  v24 = v14 & 0x40;
  v25 = v65;
  while ( 2 )
  {
    if ( v23 == 192 )
    {
LABEL_34:
      v27 = 1;
      v28 = 1;
      if ( (v14 & 0x40) == 0 )
        goto LABEL_86;
      v64 = 0;
      v65 = v25;
      v29 = *(_QWORD *)v67;
      if ( (v14 & 0x10000) != 0 )
      {
        v30 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int128 *, _QWORD, int))(v29 + 48))(v67, v78, &v65, v59, v58);
      }
      else
      {
        v27 = 0;
        v37 = v14;
        LODWORD(v37) = v14 | 0x80;
        v30 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int128 *, __int64, unsigned int, int))(v29 + 40))(
                v67,
                v78,
                &v65,
                v37,
                v59,
                v58);
      }
      if ( (char *)v30 == &v63 )
      {
        v39 = v64;
        v26 = v64;
      }
      else
      {
        v38 = *(_BYTE *)v30;
        if ( *(_BYTE *)v30 )
        {
          v39 = *(_QWORD *)(v30 + 8);
          v19 = *(_QWORD *)(v30 + 16);
          *((_QWORD *)&v64 + 1) = v19;
          v26 = v39;
        }
        else
        {
          v26 = *(_DWORD *)(v30 + 8);
          LODWORD(v64) = v26;
          v39 = v64;
        }
        v28 = v38;
      }
      if ( v28 )
      {
        *(_QWORD *)v68 = v39;
        *(_DWORD *)&v68[8] = DWORD2(v64);
        v42 = BYTE12(v64);
        v69 = BYTE12(v64);
        v70 = *(_WORD *)((char *)&v64 + 13);
        v71 = HIBYTE(v64);
        v28 = 1;
        goto LABEL_87;
      }
      if ( v26 != -17 || (v14 & 0x80u) != 0 )
        goto LABEL_73;
      v27 = 1;
      LODWORD(v56) = v56 + 1;
      if ( (unsigned int)v56 >= 3 )
      {
        v28 = 1;
LABEL_86:
        v42 = v69;
LABEL_87:
        if ( (_DWORD)v56 != 3 )
          goto LABEL_99;
        v43 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
        if ( *((_QWORD *)&v67 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
            if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
          }
        }
        v44 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
        if ( *((_QWORD *)&v55 + 1)
          && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
          if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
        }
        return 4294967291LL;
      }
      v24 = v14 & 0x40;
      v23 = (int)v61;
      continue;
    }
    break;
  }
  v65 = v25;
  (*(void (__fastcall **)(_QWORD, _BYTE *, __int128 *))(*(_QWORD *)v67 + 8LL))(v67, v72, &v65);
  if ( v72[0] )
  {
    *(_DWORD *)v68 = v73;
    *(_QWORD *)&v68[4] = v74;
    v42 = v75;
    v69 = v75;
    v70 = v76;
    v71 = v77;
    v27 = 1;
    v28 = 0;
    goto LABEL_87;
  }
  v26 = v73;
  if ( v73 == -20 )
  {
    LOWORD(v18) = v18 - 1;
    goto LABEL_83;
  }
  if ( v73 == -2 )
  {
    if ( !v24 )
    {
      LOWORD(v18) = v18 - 1;
      LOBYTE(v19) = 3;
      goto LABEL_72;
    }
    goto LABEL_34;
  }
LABEL_73:
  v40 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
  if ( *((_QWORD *)&v67 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
  }
  v41 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
  if ( !*((_QWORD *)&v55 + 1) )
    return v26;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) != 1 )
    return v26;
  (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
  if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) != 1 )
    return v26;
LABEL_80:
  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
  return v26;
}

```

## disassembly

```asm
0x180014b78  mov     rax, rsp
0x180014b7b  mov     [rax+20h], rbx
0x180014b7f  push    rbp
0x180014b80  push    rsi
0x180014b81  push    rdi
0x180014b82  push    r12
0x180014b84  push    r13
0x180014b86  push    r14
0x180014b88  push    r15
0x180014b8a  lea     rbp, [rax-78h]
0x180014b8e  sub     rsp, 140h
0x180014b95  movaps  xmmword ptr [rax-48h], xmm6
0x180014b99  mov     rax, cs:__security_cookie
0x180014ba0  xor     rax, rsp
0x180014ba3  mov     [rbp+70h+var_50], rax
0x180014ba7  mov     [rsp+170h+var_110], r8
0x180014bac  mov     r14, rdx
0x180014baf  mov     rdi, rcx
0x180014bb2  mov     [rsp+170h+var_F8], rcx
0x180014bb7  xor     esi, esi
0x180014bb9  cmp     [rcx+76h], sil
0x180014bbd  jnz     short loc_180014BEE
0x180014bbf  lea     eax, [rsi-5Fh]
0x180014bc2  mov     rcx, [rbp+70h+var_50]
0x180014bc6  xor     rcx, rsp; StackCookie
0x180014bc9  call    __security_check_cookie
0x180014bce  lea     r11, [rsp+170h+var_30]
0x180014bd6  mov     rbx, [r11+58h]
0x180014bda  movaps  xmm6, xmmword ptr [r11-10h]
0x180014bdf  mov     rsp, r11
0x180014be2  pop     r15
0x180014be4  pop     r14
0x180014be6  pop     r13
0x180014be8  pop     r12
0x180014bea  pop     rdi
0x180014beb  pop     rsi
0x180014bec  pop     rbp
0x180014bed  retn
0x180014bee  mov     rcx, [rdx+10h]; this
0x180014bf2  mov     rdx, [rdx]
0x180014bf5  sub     rdx, rcx
0x180014bf8  mov     ebx, 4
0x180014bfd  cmp     rdx, rbx
0x180014c00  jb      loc_180015689
0x180014c06  cmp     [r14], rcx
0x180014c09  jb      loc_180015683
0x180014c0f  mov     r8, [r14+8]
0x180014c13  lea     r9, [rcx+4]; char *
0x180014c17  mov     [r14+10h], r9
0x180014c1b  lea     rax, [rdx-4]
0x180014c1f  cmp     rax, rbx
0x180014c22  jb      loc_18001569F
0x180014c28  cmp     [r14], r9
0x180014c2b  jb      loc_180015683
0x180014c31  mov     rax, [r14]
0x180014c34  sub     rax, r9
0x180014c37  cmp     rax, rbx
0x180014c3a  jb      loc_180015683
0x180014c40  mov     r11d, [r8+rcx]
0x180014c44  lea     r15, [rcx+8]
0x180014c48  mov     [r14+10h], r15
0x180014c4c  lea     rax, [rdx-8]
0x180014c50  cmp     rax, rbx
0x180014c53  jb      loc_1800156B5
0x180014c59  cmp     [r14], r15
0x180014c5c  jb      loc_180015683
0x180014c62  mov     rax, [r14]
0x180014c65  sub     rax, r15
0x180014c68  cmp     rax, rbx
0x180014c6b  jb      loc_180015683
0x180014c71  mov     eax, [r9+r8]
0x180014c75  mov     [rbp+70h+var_B0], eax
0x180014c78  lea     r9, [rcx+0Ch]; char *
0x180014c7c  mov     [r14+10h], r9
0x180014c80  lea     rax, [rdx-0Ch]
0x180014c84  cmp     rax, rbx
0x180014c87  jb      loc_1800156CB
0x180014c8d  cmp     [r14], r9
0x180014c90  jb      loc_180015683
0x180014c96  mov     rax, [r14]
0x180014c99  sub     rax, r9
0x180014c9c  cmp     rax, rbx
0x180014c9f  jb      loc_180015683
0x180014ca5  mov     r15d, [r15+r8]
0x180014ca9  lea     r10, [rcx+10h]
0x180014cad  mov     [r14+10h], r10
0x180014cb1  lea     rax, [rdx-10h]
0x180014cb5  cmp     rax, rbx
0x180014cb8  jb      loc_1800156E1
0x180014cbe  cmp     [r14], r10
0x180014cc1  jb      loc_180015683
0x180014cc7  mov     rax, [r14]
0x180014cca  sub     rax, r10
0x180014ccd  cmp     rax, rbx
0x180014cd0  jb      loc_180015683
0x180014cd6  mov     eax, [r9+r8]
0x180014cda  mov     dword ptr [rsp+170h+var_100], eax
0x180014cde  add     rcx, 14h
0x180014ce2  mov     [r14+10h], rcx
0x180014ce6  mov     rax, [r14]
0x180014ce9  sub     rax, rcx
0x180014cec  cmp     rax, rbx
0x180014cef  jb      loc_1800156F7
0x180014cf5  cmp     [r14], rcx
0x180014cf8  jb      loc_180015683
0x180014cfe  mov     eax, [r10+r8]
0x180014d02  mov     [rsp+170h+var_104], eax
0x180014d06  lea     rdx, [rcx+4]
0x180014d0a  mov     [r14+10h], rdx
0x180014d0e  mov     rax, [r14]
0x180014d11  sub     rax, rdx
0x180014d14  cmp     rax, 8
0x180014d18  jb      loc_18001570D
0x180014d1e  cmp     [r14], rdx
0x180014d21  jb      loc_180015683
0x180014d27  mov     eax, [rcx+r8]
0x180014d2b  mov     [rsp+170h+var_108], eax
0x180014d2f  lea     r13, [rdx+8]
0x180014d33  mov     [r14+10h], r13
0x180014d37  mov     rax, [r14]
0x180014d3a  sub     rax, r13
0x180014d3d  cmp     rax, 2
0x180014d41  jb      loc_18001566D
0x180014d47  cmp     [r14], r13
0x180014d4a  jb      loc_180015683
0x180014d50  mov     rbx, [rdx+r8]
0x180014d54  mov     qword ptr [rbp+70h+var_F0], rbx
0x180014d58  lea     rax, [r13+2]
0x180014d5c  mov     [r14+10h], rax
0x180014d60  movzx   r13d, word ptr [r8+r13]
0x180014d65  xorps   xmm0, xmm0
0x180014d68  movups  [rsp+170h+var_130+8], xmm0
0x180014d6d  mov     r8d, r11d
0x180014d70  lea     rdx, [rsp+170h+var_130+8]
0x180014d75  mov     rcx, rdi
0x180014d78  call    ?LookupFid@Handler@p9fs@@AEAA?AV?$shared_ptr@VFid@p9fs@@@std@@I@Z; p9fs::Handler::LookupFid(uint)
0x180014d7d  nop
0x180014d7e  xorps   xmm0, xmm0
0x180014d81  movups  [rbp+70h+var_A0], xmm0
0x180014d85  mov     rcx, qword ptr [rsp+170h+var_130+8]
0x180014d8a  mov     rax, [rcx]
0x180014d8d  lea     rdx, [rbp+70h+var_A0]
0x180014d91  mov     rax, [rax+0D0h]
0x180014d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d9d  nop
0x180014d9e  mov     rcx, qword ptr [rbp+70h+var_A0]
0x180014da2  mov     rax, [rcx]
0x180014da5  lea     rdx, [rbp+70h+var_90]
0x180014da9  mov     rax, [rax+0E8h]
0x180014db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014db5  test    r13w, r13w
0x180014db9  jz      loc_18001526A
0x180014dbf  mov     r12d, esi
0x180014dc2  lea     eax, [r13-1]
0x180014dc6  mov     dword ptr [rsp+170h+var_130], eax
0x180014dca  mov     esi, 1
0x180014dcf  test    eax, eax
0x180014dd1  jle     short loc_180014E22
0x180014dd3  mov     rdi, qword ptr [rbp+70h+var_A0]
0x180014dd7  mov     rax, [rdi]
0x180014dda  mov     rbx, [rax+8]
0x180014dde  lea     rdx, [rbp+70h+var_80]
0x180014de2  mov     rcx, r14
0x180014de5  call    ?Name@SpanReader@p9fs@@QEAA?AV?$basic_string_view@DU?$char_traits@D@std@@@std@@XZ; p9fs::SpanReader::Name(void)
0x180014dea  movups  xmm0, xmmword ptr [rax]
0x180014ded  movdqu  [rbp+70h+var_C0], xmm0
0x180014df2  lea     r8, [rbp+70h+var_C0]
0x180014df6  lea     rdx, [rbp+70h+var_68]
0x180014dfa  mov     rcx, rdi
0x180014dfd  mov     rax, rbx
0x180014e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e05  cmp     [rbp+70h+var_68], 0
0x180014e09  jz      loc_180014EFA
0x180014e0f  add     r12w, si
0x180014e13  movzx   eax, r12w
0x180014e17  cmp     eax, dword ptr [rsp+170h+var_130]
0x180014e1b  jl      short loc_180014DD3
0x180014e1d  mov     rdi, [rsp+170h+var_F8]
0x180014e22  xorps   xmm0, xmm0
0x180014e25  movups  [rbp+70h+var_C0], xmm0
0x180014e29  lea     rdx, [rbp+70h+var_C0]
0x180014e2d  mov     rcx, r14
0x180014e30  call    ?Name@SpanReader@p9fs@@QEAA?AV?$basic_string_view@DU?$char_traits@D@std@@@std@@XZ; p9fs::SpanReader::Name(void)
0x180014e35  xor     r14d, r14d
0x180014e38  mov     dword ptr [rsp+170h+var_118], r14d
0x180014e3d  mov     eax, r15d
0x180014e40  and     eax, 0C0h
0x180014e45  mov     dword ptr [rsp+170h+var_F8], eax
0x180014e49  mov     ebx, r15d
0x180014e4c  and     ebx, 40h
0x180014e4f  mov     dword ptr [rsp+170h+var_130], ebx
0x180014e53  movaps  xmm6, [rbp+70h+var_C0]
0x180014e57  cmp     eax, 0C0h
0x180014e5c  jz      short loc_180014EA8
0x180014e5e  mov     rcx, qword ptr [rbp+70h+var_A0]
0x180014e62  movdqa  [rbp+70h+var_C0], xmm6
0x180014e67  mov     rax, [rcx]
0x180014e6a  lea     r8, [rbp+70h+var_C0]
0x180014e6e  lea     rdx, [rbp+70h+var_80]
0x180014e72  mov     rax, [rax+8]
0x180014e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e7b  cmp     [rbp+70h+var_80], r14b
0x180014e7f  jnz     loc_180015182
0x180014e85  mov     r14d, [rbp+70h+var_78]
0x180014e89  cmp     r14d, 0FFFFFFECh
0x180014e8d  jz      loc_180015177
0x180014e93  cmp     r14d, 0FFFFFFFEh
0x180014e97  jnz     loc_1800150F2
0x180014e9d  xor     r14d, r14d
0x180014ea0  test    ebx, ebx
0x180014ea2  jz      loc_1800150E0
0x180014ea8  mov     r12b, sil
0x180014eab  mov     bl, sil
0x180014eae  cmp     dword ptr [rsp+170h+var_130], r14d
0x180014eb3  jz      loc_1800151AF
0x180014eb9  xorps   xmm0, xmm0
0x180014ebc  movups  [rbp+70h+var_D8], xmm0
0x180014ec0  mov     rcx, qword ptr [rbp+70h+var_A0]
0x180014ec4  movdqa  [rbp+70h+var_C0], xmm6
0x180014ec9  mov     edx, [rsp+170h+var_108]
0x180014ecd  lea     r8, [rbp+70h+var_C0]
0x180014ed1  mov     rax, [rcx]
0x180014ed4  bt      r15d, 10h
0x180014ed9  jnb     loc_180015049
0x180014edf  mov     [rsp+170h+var_150], edx
0x180014ee3  mov     r9d, [rsp+170h+var_104]
0x180014ee8  lea     rdx, [rbp+70h+var_68]
0x180014eec  mov     rax, [rax+30h]
0x180014ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ef5  jmp     loc_18001506D
0x180014efa  mov     esi, dword ptr [rbp+70h+var_60]
0x180014efd  cmp     esi, 0FFFFFFECh
0x180014f00  jz      loc_180015042
0x180014f06  cmp     esi, 0FFFFFFFEh
0x180014f09  jz      loc_180014F95
0x180014f0f  or      ebx, 0FFFFFFFFh
0x180014f12  mov     rdi, qword ptr [rbp+70h+var_A0+8]
0x180014f16  test    rdi, rdi
0x180014f19  jz      short loc_180014F4F
0x180014f1b  mov     eax, ebx
0x180014f1d  lock xadd [rdi+8], eax
0x180014f22  add     eax, ebx
0x180014f24  jnz     short loc_180014F4F
0x180014f26  mov     rax, [rdi]
0x180014f29  mov     rcx, rdi
0x180014f2c  mov     rax, [rax]
0x180014f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f34  mov     eax, ebx
0x180014f36  lock xadd [rdi+0Ch], eax
0x180014f3b  add     eax, ebx
0x180014f3d  jnz     short loc_180014F4F
0x180014f3f  mov     rax, [rdi]
0x180014f42  mov     rcx, rdi
0x180014f45  mov     rax, [rax+8]
0x180014f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f4e  nop
0x180014f4f  mov     rdi, qword ptr [rsp+170h+var_120]
0x180014f54  test    rdi, rdi
0x180014f57  jz      loc_18001503B
0x180014f5d  mov     eax, ebx
0x180014f5f  lock xadd [rdi+8], eax
0x180014f64  add     eax, ebx
0x180014f66  jnz     loc_18001503B
0x180014f6c  mov     rax, [rdi]
0x180014f6f  mov     rcx, rdi
0x180014f72  mov     rax, [rax]
0x180014f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f7a  mov     ecx, ebx
0x180014f7c  lock xadd [rdi+0Ch], ecx
0x180014f81  add     ecx, ebx
0x180014f83  jnz     loc_18001503B
0x180014f89  mov     rcx, [rdi]
0x180014f8c  mov     rax, [rcx+8]
0x180014f90  jmp     loc_180015033
0x180014f95  mov     dl, 2
0x180014f97  mov     rcx, [rsp+170h+var_F8]
0x180014f9c  movzx   r8d, r12w
0x180014fa0  mov     rax, [rsp+170h+var_110]
0x180014fa5  mov     [rsp+170h+var_148], rax
0x180014faa  mov     rax, qword ptr [rbp+70h+var_F0]
0x180014fae  mov     r9, qword ptr [rbp+70h+var_A0]
0x180014fb2  mov     qword ptr [rsp+170h+var_150], rax
0x180014fb7  call    ?WriteWOpenReply@Handler@p9fs@@AEAAJW4WOpenStatus@2@GAEAVFid@2@_KAEAVMessageResponse@12@@Z; p9fs::Handler::WriteWOpenReply(p9fs::WOpenStatus,ushort,p9fs::Fid &,unsigned __int64,p9fs::Handler::MessageResponse &)
0x180014fbc  mov     esi, eax
0x180014fbe  or      ebx, 0FFFFFFFFh
0x180014fc1  mov     rdi, qword ptr [rbp+70h+var_A0+8]
0x180014fc5  test    rdi, rdi
0x180014fc8  jz      short loc_180014FFE
0x180014fca  mov     ecx, ebx
0x180014fcc  lock xadd [rdi+8], ecx
0x180014fd1  add     ecx, ebx
0x180014fd3  jnz     short loc_180014FFE
0x180014fd5  mov     rdx, [rdi]
0x180014fd8  mov     rcx, rdi
0x180014fdb  mov     rax, [rdx]
0x180014fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fe3  mov     eax, ebx
0x180014fe5  lock xadd [rdi+0Ch], eax
0x180014fea  add     eax, ebx
0x180014fec  jnz     short loc_180014FFE
  ... truncated ...
```
