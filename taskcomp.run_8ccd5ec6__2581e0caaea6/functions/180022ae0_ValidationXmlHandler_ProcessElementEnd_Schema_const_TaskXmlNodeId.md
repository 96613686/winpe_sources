# ValidationXmlHandler::ProcessElementEnd(Schema const &,TaskXmlNodeId)

- ea: `0x180022ae0`
- end: `0x1800232aa`
- name: `?ProcessElementEnd@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@@Z`
- size: `1994`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d600`

## callees

- `0x1800033d0`
- `0x180003c9c`
- `0x180003f7c`
- `0x180004090`
- `0x1800053bc`
- `0x1800053e8`
- `0x18000d128`
- `0x18000d2d8`
- `0x18000d308`
- `0x18001822c`
- `0x18001bcc0`
- `0x18001c95c`
- `0x18001d220`
- `0x18001d25c`
- `0x18001d298`
- `0x18001d320`
- `0x180022640`
- `0x18002277c`
- `0x180022ae0`

## string_xrefs

- `0x180022c4a`: `AtServiceAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ValidationXmlHandler::ProcessElementEnd(__int64 a1, int *a2, int a3)
{
  unsigned int v6; // r15d
  _QWORD *v7; // rdi
  __int64 Entry; // rax
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  _QWORD *v17; // r14
  JobBucket *v18; // rbx
  int v19; // edi
  TSTimePeriod *Periodicity; // rax
  _DWORD *v21; // r9
  int v22; // eax
  __int16 v23; // cx
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  int v27; // ebx
  int v28; // ebx
  int v29; // ebx
  TSTimePeriod *v30; // rax
  __int64 v31; // r9
  TSTimePeriod *Deadline; // rax
  __int64 v33; // r9
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rdx
  _QWORD *v37; // rcx
  _QWORD *v38; // rax
  const WCHAR **v39; // rax
  const WCHAR *v40; // rdx
  int v41; // eax
  __int64 v42; // rcx
  int v43; // eax
  _BYTE v44[16]; // [rsp+20h] [rbp-20h] BYREF
  char v45[8]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v46; // [rsp+38h] [rbp-8h]
  bool v47; // [rsp+80h] [rbp+40h] BYREF
  __int64 v48; // [rsp+88h] [rbp+48h] BYREF

  v6 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    Entry = Schema::GetEntry(a2, (unsigned int)a3);
    WPP_SF_S(v7[2], 12, WPP_66bc7a8e9c2933fa102678c8dfb90698_Traceguids, *(_QWORD *)(Entry + 8));
  }
  if ( a3 <= 39 )
  {
    if ( a3 != 39 )
    {
      v9 = a3 - 1;
      if ( v9 )
      {
        v10 = v9 - 20;
        if ( v10 )
        {
          v11 = v10 - 2;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              v13 = v12 - 1;
              if ( v13 )
              {
                v14 = v13 - 2;
                if ( v14 )
                {
                  v15 = v14 - 8;
                  if ( v15 )
                  {
                    if ( v15 != 2 )
                      return v6;
                  }
                }
                goto LABEL_79;
              }
              v45[0] = 0;
              v46 = 0;
              if ( !(unsigned __int8)TSTime::operator==(a1 + 296, v45) )
              {
                v45[0] = 0;
                v46 = 0;
                if ( (unsigned __int8)TSTime::operator!=(a1 + 312, v45) )
                {
                  v45[0] = 0;
                  v46 = -1;
                  if ( (unsigned __int8)TSTime::operator!=(a1 + 312, v45) )
                  {
                    if ( (unsigned __int8)TSTime::operator<(a1 + 416, a1 + 312) )
                      *(_OWORD *)(a1 + 416) = *(_OWORD *)(a1 + 312);
                  }
                }
                *(_DWORD *)(a1 + 264) = *(_DWORD *)(a1 + 136);
                *(_DWORD *)(a1 + 288) = *(_DWORD *)(a1 + 132);
                goto LABEL_83;
              }
              goto LABEL_71;
            }
          }
        }
LABEL_79:
        v45[0] = 0;
        v46 = 0;
        if ( (unsigned __int8)TSTime::operator!=(a1 + 312, v45) )
        {
          v45[0] = 0;
          v46 = -1;
          if ( (unsigned __int8)TSTime::operator!=(a1 + 312, v45) )
          {
            if ( (unsigned __int8)TSTime::operator<(a1 + 416, a1 + 312) )
              *(_OWORD *)(a1 + 416) = *(_OWORD *)(a1 + 312);
          }
        }
        goto LABEL_83;
      }
      if ( *a2 == 0x10000 )
      {
        if ( !*(_BYTE *)(a1 + 104) )
        {
          _bstr_t::operator=(a1 + 72, L"AtServiceAccount");
          *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) |= 0x100000u;
          *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) &= 0xFFF03FFF;
          *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) |= 0x40000u;
        }
        if ( !*(_DWORD *)(a1 + 436) )
        {
          *(_DWORD *)(a1 + 108) = 12;
          return 2147750681LL;
        }
      }
      if ( (*(_BYTE *)(a1 + 48) & 2) != 0 || !(unsigned __int8)_bstr_t::operator!(a1 + 72) )
      {
        if ( !*(_DWORD *)(a1 + 440) )
        {
          *(_DWORD *)(a1 + 108) = 102;
          return 2147750681LL;
        }
        if ( *(_DWORD *)(a1 + 432) == -1 )
        {
          v17 = (_QWORD *)(a1 + 40);
        }
        else
        {
          v45[0] = 0;
          v46 = 0;
          if ( (unsigned __int8)TSTime::operator==(v45, a1 + 416) && *a2 >= 65538 )
          {
            *(_DWORD *)(a1 + 108) = 18;
            return 2147750681LL;
          }
          v17 = (_QWORD *)(a1 + 40);
          v18 = *(JobBucket **)(a1 + 40);
          v19 = *(_DWORD *)(a1 + 432);
          JobBucket::InitOptionalSettings(v18);
          *(_DWORD *)(*((_QWORD *)v18 + 26) + 12LL) = v19;
        }
        Periodicity = (TSTimePeriod *)JobBucket::GetPeriodicity(*v17, v45);
        if ( TSTimePeriod::IsEmpty(Periodicity) )
          goto LABEL_44;
        if ( (*v21 & 0x100) == 0 )
        {
          *(_DWORD *)(a1 + 108) = 72;
          return 2147750680LL;
        }
        if ( (*v21 & 0x2000000) != 0 )
        {
LABEL_44:
          if ( (*v21 & 0x20000000) == 0 || (*v21 & 0x2000000) != 0 )
            return v6;
        }
        *(_DWORD *)(a1 + 108) = 131;
        return 2147750680LL;
      }
LABEL_113:
      *(_DWORD *)(a1 + 108) = 36;
      return 2147750681LL;
    }
    if ( !*(_BYTE *)(a1 + 140) || (v45[0] = 0, v46 = 0, (unsigned __int8)TSTime::operator==(a1 + 296, v45)) )
    {
LABEL_71:
      *(_DWORD *)(a1 + 108) = 17;
      return 2147750681LL;
    }
    v45[0] = 0;
    v46 = 0;
    if ( (unsigned __int8)TSTime::operator!=(a1 + 312, v45) )
    {
      v45[0] = 0;
      v46 = -1;
      if ( (unsigned __int8)TSTime::operator!=(a1 + 312, v45) )
      {
        if ( (unsigned __int8)TSTime::operator<(a1 + 416, a1 + 312) )
          *(_OWORD *)(a1 + 416) = *(_OWORD *)(a1 + 312);
      }
    }
    *(_DWORD *)(a1 + 264) = *(_DWORD *)(a1 + 136);
    *(_DWORD *)(a1 + 288) = *(_DWORD *)(a1 + 132);
    switch ( *(_DWORD *)(a1 + 268) )
    {
      case 2:
        if ( *(_WORD *)(a1 + 274) )
          goto LABEL_83;
        break;
      case 3:
        v22 = *(_DWORD *)(a1 + 272);
        if ( !v22 )
        {
          *(_DWORD *)(a1 + 108) = 67;
          return 2147750681LL;
        }
        v23 = *(_WORD *)(a1 + 276);
        if ( v23
          && ((v22 & 0x9FFFFFFF) != 0
           || (v22 & 0x20000000) != 0 && (v23 & 0xFFD) != 0
           || (v22 & 0x40000000) != 0 && (v23 & 0xAD5) != 0) )
        {
          goto LABEL_83;
        }
        goto LABEL_68;
      case 4:
        if ( *(_WORD *)(a1 + 272) )
        {
          if ( !*(_WORD *)(a1 + 274) )
          {
            *(_DWORD *)(a1 + 108) = 69;
            return 2147750681LL;
          }
          if ( *(_WORD *)(a1 + 276) )
          {
LABEL_83:
            *(_DWORD *)(a1 + 112) = 0;
            return v6;
          }
LABEL_68:
          *(_DWORD *)(a1 + 108) = 53;
          return 2147750681LL;
        }
        break;
      default:
        goto LABEL_83;
    }
    *(_DWORD *)(a1 + 108) = 44;
    return 2147750681LL;
  }
  v24 = a3 - 98;
  if ( !v24 )
  {
    if ( (*(_BYTE *)(a1 + 48) & 2) != 0 )
      goto LABEL_115;
    if ( (unsigned __int8)_bstr_t::operator!(a1 + 72) )
      goto LABEL_113;
    if ( *(_BYTE *)(a1 + 489) )
    {
LABEL_115:
      v36 = *(_QWORD *)(a1 + 40);
      v37 = *(_QWORD **)(v36 + 176);
      if ( v37 && *v37 )
        goto LABEL_121;
      if ( (unsigned int)((__int64)(*(_QWORD *)(v36 + 192) - *(_QWORD *)(v36 + 184)) >> 3) )
      {
        *(_DWORD *)(a1 + 108) = 145;
        return 2147750681LL;
      }
      if ( v37 && *v37 )
      {
LABEL_121:
        if ( (*(_DWORD *)(v36 + 16) & 0x1000000) != 0 )
        {
          *(_DWORD *)(a1 + 108) = 101;
          return 2147750680LL;
        }
      }
      v38 = *(_QWORD **)(a1 + 80);
      if ( !v38 || !*v38 )
        _bstr_t::operator=(a1 + 80, a1 + 96);
      if ( *(_BYTE *)(a1 + 489)
        || !(unsigned int)_bstr_t::_Compare((_bstr_t *)(a1 + 80), (const struct _bstr_t *)(a1 + 96)) )
      {
        *(_BYTE *)(a1 + 489) = 0;
        *(_BYTE *)(a1 + 104) = 1;
        if ( !_bstr_t::length((_bstr_t *)(a1 + 72)) || (*(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) & 0x100000) != 0 )
        {
          v42 = *(_QWORD *)(a1 + 40);
          v43 = *(_DWORD *)(v42 + 16);
          if ( (v43 & 0xFC000) == 0 )
            *(_DWORD *)(v42 + 16) = v43 & 0xFFF03FFF | 0x10000;
        }
        else
        {
          v48 = 0;
          v39 = *(const WCHAR ***)(a1 + 72);
          if ( v39 )
            v40 = *v39;
          else
            v40 = 0;
          v6 = User::FromUsername((struct User *)&v48, v40);
          if ( (v6 & 0x80000000) == 0 )
          {
            if ( User::IsService((User *)&v48) )
              *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) & 0xFFF03FFF | 0x20000;
          }
          else if ( (*(_BYTE *)(a1 + 48) & 4) != 0 )
          {
            v6 = 0;
          }
          else
          {
            v41 = 111;
            if ( (*(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) & 0xFC000) != 0x8000 )
              v41 = 36;
            *(_DWORD *)(a1 + 108) = v41;
          }
          wmi::AutoRef<User::UserEntry>::Release(&v48);
        }
        return v6;
      }
    }
    *(_DWORD *)(a1 + 108) = 109;
    return 2147750681LL;
  }
  v25 = v24 - 4;
  if ( !v25 )
  {
    if ( (*(_BYTE *)(a1 + 48) & 2) != 0 || *(_BYTE *)(a1 + 489) )
    {
      v35 = *(_QWORD **)(a1 + 80);
      if ( !v35 || !*v35 )
        _bstr_t::operator=(a1 + 80, a1 + 96);
      if ( *(_BYTE *)(a1 + 489)
        || !(unsigned int)_bstr_t::_Compare((_bstr_t *)(a1 + 80), (const struct _bstr_t *)(a1 + 96)) )
      {
        *(_BYTE *)(a1 + 489) = 0;
        *(_BYTE *)(a1 + 105) = 0;
        return v6;
      }
    }
    *(_DWORD *)(a1 + 108) = 110;
    return 2147750681LL;
  }
  v26 = v25 - 1;
  if ( !v26 )
  {
    if ( !_bstr_t::length((_bstr_t *)(a1 + 480)) )
    {
      *(_DWORD *)(a1 + 108) = 104;
      return 2147750678LL;
    }
    return v6;
  }
  v27 = v26 - 10;
  if ( !v27 )
  {
    if ( (*(_BYTE *)(a1 + 48) & 4) == 0 )
      return 2147750704LL;
    if ( _bstr_t::length((_bstr_t *)(a1 + 448))
      || _bstr_t::length((_bstr_t *)(a1 + 456))
      || _bstr_t::length((_bstr_t *)(a1 + 464)) )
    {
      if ( _bstr_t::length((_bstr_t *)(a1 + 472)) )
        return v6;
      *(_DWORD *)(a1 + 108) = 120;
    }
    else
    {
      *(_DWORD *)(a1 + 108) = 116;
    }
    return 2147750681LL;
  }
  v28 = v27 - 15;
  if ( !v28 )
  {
    if ( (*(_BYTE *)(a1 + 48) & 4) != 0 )
      return v6;
    return 2147750704LL;
  }
  v29 = v28 - 8;
  if ( !v29 )
  {
    v30 = (TSTimePeriod *)JobBucket::GetPeriodicity(*(_QWORD *)(a1 + 40), v45);
    if ( TSTimePeriod::IsEmpty(v30) )
    {
      *(_DWORD *)(a1 + 108) = 137;
      return 2147750681LL;
    }
    Deadline = (TSTimePeriod *)JobBucket::GetDeadline(v31, v45);
    if ( TSTimePeriod::IsEmpty(Deadline) )
      return v6;
    JobBucket::GetPeriodicity(v33, v45);
    JobBucket::GetDeadline(v34, v44);
    v47 = 0;
    if ( (int)TSTimePeriod::IsLessThen((TSTimePeriod *)v45, (const struct TSTimePeriod *)v44, &v47) >= 0 && v47 )
      return v6;
    *(_DWORD *)(a1 + 108) = 138;
    return 2147750680LL;
  }
  if ( v29 == 5 )
    goto LABEL_79;
  return v6;
}

```

## disassembly

```asm
0x180022ae0  mov     [rsp-28h+arg_0], rbx
0x180022ae5  mov     [rsp-28h+arg_8], rsi
0x180022aea  push    rbp
0x180022aeb  push    rdi
0x180022aec  push    r12
0x180022aee  push    r14
0x180022af0  push    r15
0x180022af2  mov     rbp, rsp
0x180022af5  sub     rsp, 40h
0x180022af9  mov     ebx, r8d
0x180022afc  mov     r14, rdx
0x180022aff  mov     rsi, rcx
0x180022b02  xor     r12d, r12d
0x180022b05  mov     r15d, r12d
0x180022b08  lea     rax, WPP_GLOBAL_Control
0x180022b0f  mov     rdi, cs:WPP_GLOBAL_Control
0x180022b16  cmp     rdi, rax
0x180022b19  jz      short loc_180022B4A
0x180022b1b  test    byte ptr [rdi+1Ch], 80h
0x180022b1f  jz      short loc_180022B4A
0x180022b21  cmp     byte ptr [rdi+19h], 5
0x180022b25  jb      short loc_180022B4A
0x180022b27  mov     edx, ebx
0x180022b29  mov     rcx, r14
0x180022b2c  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180022b31  lea     edx, [r12+0Ch]
0x180022b36  mov     r9, [rax+8]
0x180022b3a  lea     r8, WPP_66bc7a8e9c2933fa102678c8dfb90698_Traceguids
0x180022b41  mov     rcx, [rdi+10h]
0x180022b45  call    WPP_SF_S
0x180022b4a  cmp     ebx, 27h ; '''
0x180022b4d  jg      loc_180022EE5
0x180022b53  jz      loc_180022D71
0x180022b59  sub     ebx, 1
0x180022b5c  jz      loc_180022C37
0x180022b62  sub     ebx, 14h
0x180022b65  jz      loc_180022F20
0x180022b6b  sub     ebx, 2
0x180022b6e  jz      loc_180022F20
0x180022b74  sub     ebx, 1
0x180022b77  jz      loc_180022F20
0x180022b7d  sub     ebx, 1
0x180022b80  jz      short loc_180022BA2
0x180022b82  sub     ebx, 2
0x180022b85  jz      loc_180022F20
0x180022b8b  sub     ebx, 8
0x180022b8e  jz      loc_180022F20
0x180022b94  cmp     ebx, 2
0x180022b97  jz      loc_180022F20
0x180022b9d  jmp     loc_18002328F
0x180022ba2  mov     [rbp+var_10], r12b
0x180022ba6  mov     [rbp+var_8], r12
0x180022baa  lea     rcx, [rsi+128h]
0x180022bb1  lea     rdx, [rbp+var_10]
0x180022bb5  call    ??8TSTime@@QEBA_NAEBV0@@Z; TSTime::operator==(TSTime const &)
0x180022bba  test    al, al
0x180022bbc  jnz     loc_180022ED9
0x180022bc2  mov     [rbp+var_10], r12b
0x180022bc6  mov     [rbp+var_8], r12
0x180022bca  lea     rbx, [rsi+138h]
0x180022bd1  lea     rdx, [rbp+var_10]
0x180022bd5  mov     rcx, rbx
0x180022bd8  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x180022bdd  test    al, al
0x180022bdf  jz      short loc_180022C1A
0x180022be1  mov     [rbp+var_10], r12b
0x180022be5  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x180022bed  lea     rdx, [rbp+var_10]
0x180022bf1  mov     rcx, rbx
0x180022bf4  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x180022bf9  test    al, al
0x180022bfb  jz      short loc_180022C1A
0x180022bfd  lea     rdi, [rsi+1A0h]
0x180022c04  mov     rdx, rbx
0x180022c07  mov     rcx, rdi
0x180022c0a  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x180022c0f  test    al, al
0x180022c11  jz      short loc_180022C1A
0x180022c13  movups  xmm0, xmmword ptr [rbx]
0x180022c16  movdqu  xmmword ptr [rdi], xmm0
0x180022c1a  mov     eax, [rsi+88h]
0x180022c20  mov     [rsi+108h], eax
0x180022c26  mov     eax, [rsi+84h]
0x180022c2c  mov     [rsi+120h], eax
0x180022c32  jmp     loc_180022F78
0x180022c37  cmp     dword ptr [r14], 10000h
0x180022c3e  jnz     short loc_180022C8D
0x180022c40  cmp     [rsi+68h], r12b
0x180022c44  jnz     short loc_180022C73
0x180022c46  lea     rcx, [rsi+48h]
0x180022c4a  lea     rdx, ValueName; "AtServiceAccount"
0x180022c51  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180022c56  mov     rax, [rsi+28h]
0x180022c5a  bts     dword ptr [rax+10h], 14h
0x180022c5f  mov     rax, [rsi+28h]
0x180022c63  and     dword ptr [rax+10h], 0FFF03FFFh
0x180022c6a  mov     rax, [rsi+28h]
0x180022c6e  bts     dword ptr [rax+10h], 12h
0x180022c73  cmp     [rsi+1B4h], r12d
0x180022c7a  jnz     short loc_180022C8D
0x180022c7c  mov     dword ptr [rsi+6Ch], 0Ch
0x180022c83  mov     eax, 80041319h
0x180022c88  jmp     loc_180023292
0x180022c8d  test    byte ptr [rsi+30h], 2
0x180022c91  jnz     short loc_180022CA4
0x180022c93  lea     rcx, [rsi+48h]
0x180022c97  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180022c9c  test    al, al
0x180022c9e  jnz     loc_18002311B
0x180022ca4  cmp     [rsi+1B8h], r12d
0x180022cab  jnz     short loc_180022CB6
0x180022cad  mov     dword ptr [rsi+6Ch], 66h ; 'f'
0x180022cb4  jmp     short loc_180022C83
0x180022cb6  cmp     dword ptr [rsi+1B0h], 0FFFFFFFFh
0x180022cbd  jz      short loc_180022D0E
0x180022cbf  mov     [rbp+var_10], r12b
0x180022cc3  mov     [rbp+var_8], r12
0x180022cc7  lea     rdx, [rsi+1A0h]
0x180022cce  lea     rcx, [rbp+var_10]
0x180022cd2  call    ??8TSTime@@QEBA_NAEBV0@@Z; TSTime::operator==(TSTime const &)
0x180022cd7  test    al, al
0x180022cd9  jz      short loc_180022CED
0x180022cdb  cmp     dword ptr [r14], 10002h
0x180022ce2  jl      short loc_180022CED
0x180022ce4  mov     dword ptr [rsi+6Ch], 12h
0x180022ceb  jmp     short loc_180022C83
0x180022ced  lea     r14, [rsi+28h]
0x180022cf1  mov     rbx, [r14]
0x180022cf4  mov     edi, [rsi+1B0h]
0x180022cfa  mov     rcx, rbx; this
0x180022cfd  call    ?InitOptionalSettings@JobBucket@@IEAAXXZ; JobBucket::InitOptionalSettings(void)
0x180022d02  mov     rax, [rbx+0D0h]
0x180022d09  mov     [rax+0Ch], edi
0x180022d0c  jmp     short loc_180022D12
0x180022d0e  lea     r14, [rsi+28h]
0x180022d12  mov     rcx, [r14]
0x180022d15  lea     r9, [rcx+10h]
0x180022d19  lea     rdx, [rbp+var_10]
0x180022d1d  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x180022d22  mov     rcx, rax; this
0x180022d25  call    ?IsEmpty@TSTimePeriod@@QEBA_NXZ; TSTimePeriod::IsEmpty(void)
0x180022d2a  mov     ecx, 2000000h
0x180022d2f  test    al, al
0x180022d31  jnz     short loc_180022D52
0x180022d33  test    dword ptr [r9], 100h
0x180022d3a  jnz     short loc_180022D4D
0x180022d3c  mov     dword ptr [rsi+6Ch], 48h ; 'H'
0x180022d43  mov     eax, 80041318h
0x180022d48  jmp     loc_180023292
0x180022d4d  test    [r9], ecx
0x180022d50  jz      short loc_180022D68
0x180022d52  test    dword ptr [r9], 20000000h
0x180022d59  jz      loc_18002328F
0x180022d5f  test    [r9], ecx
0x180022d62  jnz     loc_18002328F
0x180022d68  mov     dword ptr [rsi+6Ch], 83h
0x180022d6f  jmp     short loc_180022D43
0x180022d71  cmp     [rsi+8Ch], r12b
0x180022d78  jz      loc_180022ED9
0x180022d7e  mov     [rbp+var_10], r12b
0x180022d82  mov     [rbp+var_8], r12
0x180022d86  lea     rcx, [rsi+128h]
0x180022d8d  lea     rdx, [rbp+var_10]
0x180022d91  call    ??8TSTime@@QEBA_NAEBV0@@Z; TSTime::operator==(TSTime const &)
0x180022d96  test    al, al
0x180022d98  jnz     loc_180022ED9
0x180022d9e  mov     [rbp+var_10], r12b
0x180022da2  mov     [rbp+var_8], r12
0x180022da6  lea     rbx, [rsi+138h]
0x180022dad  lea     rdx, [rbp+var_10]
0x180022db1  mov     rcx, rbx
0x180022db4  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x180022db9  test    al, al
0x180022dbb  jz      short loc_180022DF6
0x180022dbd  mov     [rbp+var_10], r12b
0x180022dc1  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x180022dc9  lea     rdx, [rbp+var_10]
0x180022dcd  mov     rcx, rbx
0x180022dd0  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x180022dd5  test    al, al
0x180022dd7  jz      short loc_180022DF6
0x180022dd9  lea     rdi, [rsi+1A0h]
0x180022de0  mov     rdx, rbx
0x180022de3  mov     rcx, rdi
0x180022de6  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x180022deb  test    al, al
0x180022ded  jz      short loc_180022DF6
0x180022def  movups  xmm0, xmmword ptr [rbx]
0x180022df2  movdqu  xmmword ptr [rdi], xmm0
0x180022df6  mov     eax, [rsi+88h]
0x180022dfc  mov     [rsi+108h], eax
0x180022e02  mov     eax, [rsi+84h]
0x180022e08  mov     [rsi+120h], eax
0x180022e0e  mov     ecx, [rsi+10Ch]
0x180022e14  sub     ecx, 2
0x180022e17  jz      loc_180022EBF
0x180022e1d  sub     ecx, 1
0x180022e20  jz      short loc_180022E5E
0x180022e22  cmp     ecx, 1
0x180022e25  jnz     loc_180022F78
0x180022e2b  cmp     [rsi+110h], r12w
0x180022e33  jz      loc_180022ECD
0x180022e39  cmp     [rsi+112h], r12w
0x180022e41  jnz     short loc_180022E4F
0x180022e43  mov     dword ptr [rsi+6Ch], 45h ; 'E'
0x180022e4a  jmp     loc_180022C83
0x180022e4f  cmp     [rsi+114h], r12w
0x180022e57  jz      short loc_180022EB3
0x180022e59  jmp     loc_180022F78
0x180022e5e  mov     eax, [rsi+110h]
0x180022e64  test    eax, eax
0x180022e66  jnz     short loc_180022E74
0x180022e68  mov     dword ptr [rsi+6Ch], 43h ; 'C'
0x180022e6f  jmp     loc_180022C83
0x180022e74  movzx   ecx, word ptr [rsi+114h]
0x180022e7b  test    cx, cx
0x180022e7e  jz      short loc_180022EB3
0x180022e80  test    eax, 9FFFFFFFh
0x180022e85  jnz     loc_180022F78
0x180022e8b  bt      eax, 1Dh
0x180022e8f  jnb     short loc_180022E9F
0x180022e91  mov     edx, 0FFDh
0x180022e96  test    dx, cx
0x180022e99  jnz     loc_180022F78
0x180022e9f  bt      eax, 1Eh
0x180022ea3  jnb     short loc_180022EB3
0x180022ea5  mov     eax, 0AD5h
0x180022eaa  test    ax, cx
0x180022ead  jnz     loc_180022F78
0x180022eb3  mov     dword ptr [rsi+6Ch], 35h ; '5'
0x180022eba  jmp     loc_180022C83
0x180022ebf  cmp     [rsi+112h], r12w
0x180022ec7  jnz     loc_180022F78
0x180022ecd  mov     dword ptr [rsi+6Ch], 2Ch ; ','
0x180022ed4  jmp     loc_180022C83
0x180022ed9  mov     dword ptr [rsi+6Ch], 11h
0x180022ee0  jmp     loc_180022C83
0x180022ee5  sub     ebx, 62h ; 'b'
0x180022ee8  jz      loc_180023108
0x180022eee  sub     ebx, 4
0x180022ef1  jz      loc_1800230A5
0x180022ef7  sub     ebx, 1
0x180022efa  jz      loc_180023080
0x180022f00  sub     ebx, 0Ah
0x180022f03  jz      loc_180023014
0x180022f09  sub     ebx, 0Fh
0x180022f0c  jz      loc_180023009
0x180022f12  sub     ebx, 8
0x180022f15  jz      short loc_180022F81
0x180022f17  cmp     ebx, 5
0x180022f1a  jnz     loc_18002328F
0x180022f20  mov     [rbp+var_10], r12b
0x180022f24  mov     [rbp+var_8], r12
0x180022f28  lea     rbx, [rsi+138h]
0x180022f2f  lea     rdx, [rbp+var_10]
0x180022f33  mov     rcx, rbx
0x180022f36  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x180022f3b  test    al, al
0x180022f3d  jz      short loc_180022F78
0x180022f3f  mov     [rbp+var_10], r12b
0x180022f43  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x180022f4b  lea     rdx, [rbp+var_10]
0x180022f4f  mov     rcx, rbx
0x180022f52  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x180022f57  test    al, al
0x180022f59  jz      short loc_180022F78
0x180022f5b  lea     rdi, [rsi+1A0h]
0x180022f62  mov     rdx, rbx
0x180022f65  mov     rcx, rdi
0x180022f68  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x180022f6d  test    al, al
0x180022f6f  jz      short loc_180022F78
0x180022f71  movups  xmm0, xmmword ptr [rbx]
0x180022f74  movdqu  xmmword ptr [rdi], xmm0
0x180022f78  mov     [rsi+70h], r12d
0x180022f7c  jmp     loc_18002328F
0x180022f81  mov     r9, [rsi+28h]
0x180022f85  lea     rdx, [rbp+var_10]
0x180022f89  mov     rcx, r9
0x180022f8c  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x180022f91  mov     rcx, rax; this
0x180022f94  call    ?IsEmpty@TSTimePeriod@@QEBA_NXZ; TSTimePeriod::IsEmpty(void)
0x180022f99  cmp     al, 1
0x180022f9b  jnz     short loc_180022FA9
0x180022f9d  mov     dword ptr [rsi+6Ch], 89h
0x180022fa4  jmp     loc_180022C83
0x180022fa9  lea     rdx, [rbp+var_10]
0x180022fad  mov     rcx, r9
0x180022fb0  call    ?GetDeadline@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetDeadline(void)
0x180022fb5  mov     rcx, rax; this
0x180022fb8  call    ?IsEmpty@TSTimePeriod@@QEBA_NXZ; TSTimePeriod::IsEmpty(void)
0x180022fbd  test    al, al
0x180022fbf  jnz     loc_18002328F
0x180022fc5  lea     rdx, [rbp+var_10]
0x180022fc9  mov     rcx, r9
0x180022fcc  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x180022fd1  lea     rdx, [rbp+var_20]
0x180022fd5  call    ?GetDeadline@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetDeadline(void)
0x180022fda  mov     [rbp+arg_10], r12b
0x180022fde  lea     r8, [rbp+arg_10]; bool *
  ... truncated ...
```
