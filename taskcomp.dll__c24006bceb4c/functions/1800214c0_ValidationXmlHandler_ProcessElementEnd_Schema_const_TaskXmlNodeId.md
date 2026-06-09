# ValidationXmlHandler::ProcessElementEnd(Schema const &,TaskXmlNodeId)

- ea: `0x1800214c0`
- end: `0x180021c89`
- name: `?ProcessElementEnd@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@@Z`
- size: `1993`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cd80`

## callees

- `0x180003250`
- `0x180003af0`
- `0x180003dac`
- `0x180003ec0`
- `0x1800050fc`
- `0x18000518c`
- `0x18000c8f4`
- `0x18000ca8c`
- `0x18000cabc`
- `0x18001724c`
- `0x18001a928`
- `0x18001b45c`
- `0x18001bd00`
- `0x18001bd3c`
- `0x18001bd78`
- `0x18001be00`
- `0x180021018`
- `0x180021154`
- `0x1800214c0`

## string_xrefs

- `0x18002162a`: `AtServiceAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ValidationXmlHandler::ProcessElementEnd(__int64 a1, int *a2, int a3)
{
  unsigned int v6; // r15d
  _QWORD *v7; // rdi
  __int64 *Entry; // rax
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
    Entry = Schema::GetEntry(a2, a3);
    WPP_SF_S(v7[2], 12, WPP_66bc7a8e9c2933fa102678c8dfb90698_Traceguids, Entry[1]);
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
        _bstr_t::operator=((_bstr_t *)(a1 + 80), a1 + 96);
      if ( *(_BYTE *)(a1 + 489)
        || !(unsigned int)_bstr_t::_Compare((_bstr_t::Data_t **)(a1 + 80), (const struct _bstr_t::Data_t **)(a1 + 96)) )
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
        _bstr_t::operator=((_bstr_t *)(a1 + 80), a1 + 96);
      if ( *(_BYTE *)(a1 + 489)
        || !(unsigned int)_bstr_t::_Compare((_bstr_t::Data_t **)(a1 + 80), (const struct _bstr_t::Data_t **)(a1 + 96)) )
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
0x1800214c0  mov     [rsp-28h+arg_0], rbx
0x1800214c5  mov     [rsp-28h+arg_8], rsi
0x1800214ca  push    rbp
0x1800214cb  push    rdi
0x1800214cc  push    r12
0x1800214ce  push    r14
0x1800214d0  push    r15
0x1800214d2  mov     rbp, rsp
0x1800214d5  sub     rsp, 40h
0x1800214d9  mov     ebx, r8d
0x1800214dc  mov     r14, rdx
0x1800214df  mov     rsi, rcx
0x1800214e2  xor     r12d, r12d
0x1800214e5  mov     r15d, r12d
0x1800214e8  lea     rax, WPP_GLOBAL_Control
0x1800214ef  mov     rdi, cs:WPP_GLOBAL_Control
0x1800214f6  cmp     rdi, rax
0x1800214f9  jz      short loc_18002152A
0x1800214fb  test    byte ptr [rdi+1Ch], 80h
0x1800214ff  jz      short loc_18002152A
0x180021501  cmp     byte ptr [rdi+19h], 5
0x180021505  jb      short loc_18002152A
0x180021507  mov     edx, ebx
0x180021509  mov     rcx, r14
0x18002150c  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180021511  lea     edx, [r12+0Ch]
0x180021516  mov     r9, [rax+8]
0x18002151a  lea     r8, WPP_66bc7a8e9c2933fa102678c8dfb90698_Traceguids
0x180021521  mov     rcx, [rdi+10h]
0x180021525  call    WPP_SF_S
0x18002152a  cmp     ebx, 27h ; '''
0x18002152d  jg      loc_1800218C5
0x180021533  jz      loc_180021751
0x180021539  sub     ebx, 1
0x18002153c  jz      loc_180021617
0x180021542  sub     ebx, 14h
0x180021545  jz      loc_180021900
0x18002154b  sub     ebx, 2
0x18002154e  jz      loc_180021900
0x180021554  sub     ebx, 1
0x180021557  jz      loc_180021900
0x18002155d  sub     ebx, 1
0x180021560  jz      short loc_180021582
0x180021562  sub     ebx, 2
0x180021565  jz      loc_180021900
0x18002156b  sub     ebx, 8
0x18002156e  jz      loc_180021900
0x180021574  cmp     ebx, 2
0x180021577  jz      loc_180021900
0x18002157d  jmp     loc_180021C6F
0x180021582  mov     [rbp+var_10], r12b
0x180021586  mov     [rbp+var_8], r12
0x18002158a  lea     rcx, [rsi+128h]
0x180021591  lea     rdx, [rbp+var_10]
0x180021595  call    ??8TSTime@@QEBA_NAEBV0@@Z; TSTime::operator==(TSTime const &)
0x18002159a  test    al, al
0x18002159c  jnz     loc_1800218B9
0x1800215a2  mov     [rbp+var_10], r12b
0x1800215a6  mov     [rbp+var_8], r12
0x1800215aa  lea     rbx, [rsi+138h]
0x1800215b1  lea     rdx, [rbp+var_10]
0x1800215b5  mov     rcx, rbx
0x1800215b8  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x1800215bd  test    al, al
0x1800215bf  jz      short loc_1800215FA
0x1800215c1  mov     [rbp+var_10], r12b
0x1800215c5  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x1800215cd  lea     rdx, [rbp+var_10]
0x1800215d1  mov     rcx, rbx
0x1800215d4  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x1800215d9  test    al, al
0x1800215db  jz      short loc_1800215FA
0x1800215dd  lea     rdi, [rsi+1A0h]
0x1800215e4  mov     rdx, rbx
0x1800215e7  mov     rcx, rdi
0x1800215ea  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x1800215ef  test    al, al
0x1800215f1  jz      short loc_1800215FA
0x1800215f3  movups  xmm0, xmmword ptr [rbx]
0x1800215f6  movdqu  xmmword ptr [rdi], xmm0
0x1800215fa  mov     eax, [rsi+88h]
0x180021600  mov     [rsi+108h], eax
0x180021606  mov     eax, [rsi+84h]
0x18002160c  mov     [rsi+120h], eax
0x180021612  jmp     loc_180021958
0x180021617  cmp     dword ptr [r14], 10000h
0x18002161e  jnz     short loc_18002166D
0x180021620  cmp     [rsi+68h], r12b
0x180021624  jnz     short loc_180021653
0x180021626  lea     rcx, [rsi+48h]
0x18002162a  lea     rdx, ValueName; "AtServiceAccount"
0x180021631  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180021636  mov     rax, [rsi+28h]
0x18002163a  bts     dword ptr [rax+10h], 14h
0x18002163f  mov     rax, [rsi+28h]
0x180021643  and     dword ptr [rax+10h], 0FFF03FFFh
0x18002164a  mov     rax, [rsi+28h]
0x18002164e  bts     dword ptr [rax+10h], 12h
0x180021653  cmp     [rsi+1B4h], r12d
0x18002165a  jnz     short loc_18002166D
0x18002165c  mov     dword ptr [rsi+6Ch], 0Ch
0x180021663  mov     eax, 80041319h
0x180021668  jmp     loc_180021C72
0x18002166d  test    byte ptr [rsi+30h], 2
0x180021671  jnz     short loc_180021684
0x180021673  lea     rcx, [rsi+48h]
0x180021677  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18002167c  test    al, al
0x18002167e  jnz     loc_180021AFB
0x180021684  cmp     [rsi+1B8h], r12d
0x18002168b  jnz     short loc_180021696
0x18002168d  mov     dword ptr [rsi+6Ch], 66h ; 'f'
0x180021694  jmp     short loc_180021663
0x180021696  cmp     dword ptr [rsi+1B0h], 0FFFFFFFFh
0x18002169d  jz      short loc_1800216EE
0x18002169f  mov     [rbp+var_10], r12b
0x1800216a3  mov     [rbp+var_8], r12
0x1800216a7  lea     rdx, [rsi+1A0h]
0x1800216ae  lea     rcx, [rbp+var_10]
0x1800216b2  call    ??8TSTime@@QEBA_NAEBV0@@Z; TSTime::operator==(TSTime const &)
0x1800216b7  test    al, al
0x1800216b9  jz      short loc_1800216CD
0x1800216bb  cmp     dword ptr [r14], 10002h
0x1800216c2  jl      short loc_1800216CD
0x1800216c4  mov     dword ptr [rsi+6Ch], 12h
0x1800216cb  jmp     short loc_180021663
0x1800216cd  lea     r14, [rsi+28h]
0x1800216d1  mov     rbx, [r14]
0x1800216d4  mov     edi, [rsi+1B0h]
0x1800216da  mov     rcx, rbx; this
0x1800216dd  call    ?InitOptionalSettings@JobBucket@@IEAAXXZ; JobBucket::InitOptionalSettings(void)
0x1800216e2  mov     rax, [rbx+0D0h]
0x1800216e9  mov     [rax+0Ch], edi
0x1800216ec  jmp     short loc_1800216F2
0x1800216ee  lea     r14, [rsi+28h]
0x1800216f2  mov     rcx, [r14]
0x1800216f5  lea     r9, [rcx+10h]
0x1800216f9  lea     rdx, [rbp+var_10]
0x1800216fd  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x180021702  mov     rcx, rax; this
0x180021705  call    ?IsEmpty@TSTimePeriod@@QEBA_NXZ; TSTimePeriod::IsEmpty(void)
0x18002170a  mov     ecx, 2000000h
0x18002170f  test    al, al
0x180021711  jnz     short loc_180021732
0x180021713  test    dword ptr [r9], 100h
0x18002171a  jnz     short loc_18002172D
0x18002171c  mov     dword ptr [rsi+6Ch], 48h ; 'H'
0x180021723  mov     eax, 80041318h
0x180021728  jmp     loc_180021C72
0x18002172d  test    [r9], ecx
0x180021730  jz      short loc_180021748
0x180021732  test    dword ptr [r9], 20000000h
0x180021739  jz      loc_180021C6F
0x18002173f  test    [r9], ecx
0x180021742  jnz     loc_180021C6F
0x180021748  mov     dword ptr [rsi+6Ch], 83h
0x18002174f  jmp     short loc_180021723
0x180021751  cmp     [rsi+8Ch], r12b
0x180021758  jz      loc_1800218B9
0x18002175e  mov     [rbp+var_10], r12b
0x180021762  mov     [rbp+var_8], r12
0x180021766  lea     rcx, [rsi+128h]
0x18002176d  lea     rdx, [rbp+var_10]
0x180021771  call    ??8TSTime@@QEBA_NAEBV0@@Z; TSTime::operator==(TSTime const &)
0x180021776  test    al, al
0x180021778  jnz     loc_1800218B9
0x18002177e  mov     [rbp+var_10], r12b
0x180021782  mov     [rbp+var_8], r12
0x180021786  lea     rbx, [rsi+138h]
0x18002178d  lea     rdx, [rbp+var_10]
0x180021791  mov     rcx, rbx
0x180021794  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x180021799  test    al, al
0x18002179b  jz      short loc_1800217D6
0x18002179d  mov     [rbp+var_10], r12b
0x1800217a1  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x1800217a9  lea     rdx, [rbp+var_10]
0x1800217ad  mov     rcx, rbx
0x1800217b0  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x1800217b5  test    al, al
0x1800217b7  jz      short loc_1800217D6
0x1800217b9  lea     rdi, [rsi+1A0h]
0x1800217c0  mov     rdx, rbx
0x1800217c3  mov     rcx, rdi
0x1800217c6  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x1800217cb  test    al, al
0x1800217cd  jz      short loc_1800217D6
0x1800217cf  movups  xmm0, xmmword ptr [rbx]
0x1800217d2  movdqu  xmmword ptr [rdi], xmm0
0x1800217d6  mov     eax, [rsi+88h]
0x1800217dc  mov     [rsi+108h], eax
0x1800217e2  mov     eax, [rsi+84h]
0x1800217e8  mov     [rsi+120h], eax
0x1800217ee  mov     ecx, [rsi+10Ch]
0x1800217f4  sub     ecx, 2
0x1800217f7  jz      loc_18002189F
0x1800217fd  sub     ecx, 1
0x180021800  jz      short loc_18002183E
0x180021802  cmp     ecx, 1
0x180021805  jnz     loc_180021958
0x18002180b  cmp     [rsi+110h], r12w
0x180021813  jz      loc_1800218AD
0x180021819  cmp     [rsi+112h], r12w
0x180021821  jnz     short loc_18002182F
0x180021823  mov     dword ptr [rsi+6Ch], 45h ; 'E'
0x18002182a  jmp     loc_180021663
0x18002182f  cmp     [rsi+114h], r12w
0x180021837  jz      short loc_180021893
0x180021839  jmp     loc_180021958
0x18002183e  mov     eax, [rsi+110h]
0x180021844  test    eax, eax
0x180021846  jnz     short loc_180021854
0x180021848  mov     dword ptr [rsi+6Ch], 43h ; 'C'
0x18002184f  jmp     loc_180021663
0x180021854  movzx   ecx, word ptr [rsi+114h]
0x18002185b  test    cx, cx
0x18002185e  jz      short loc_180021893
0x180021860  test    eax, 9FFFFFFFh
0x180021865  jnz     loc_180021958
0x18002186b  bt      eax, 1Dh
0x18002186f  jnb     short loc_18002187F
0x180021871  mov     edx, 0FFDh
0x180021876  test    dx, cx
0x180021879  jnz     loc_180021958
0x18002187f  bt      eax, 1Eh
0x180021883  jnb     short loc_180021893
0x180021885  mov     eax, 0AD5h
0x18002188a  test    ax, cx
0x18002188d  jnz     loc_180021958
0x180021893  mov     dword ptr [rsi+6Ch], 35h ; '5'
0x18002189a  jmp     loc_180021663
0x18002189f  cmp     [rsi+112h], r12w
0x1800218a7  jnz     loc_180021958
0x1800218ad  mov     dword ptr [rsi+6Ch], 2Ch ; ','
0x1800218b4  jmp     loc_180021663
0x1800218b9  mov     dword ptr [rsi+6Ch], 11h
0x1800218c0  jmp     loc_180021663
0x1800218c5  sub     ebx, 62h ; 'b'
0x1800218c8  jz      loc_180021AE8
0x1800218ce  sub     ebx, 4
0x1800218d1  jz      loc_180021A85
0x1800218d7  sub     ebx, 1
0x1800218da  jz      loc_180021A60
0x1800218e0  sub     ebx, 0Ah
0x1800218e3  jz      loc_1800219F4
0x1800218e9  sub     ebx, 0Fh
0x1800218ec  jz      loc_1800219E9
0x1800218f2  sub     ebx, 8
0x1800218f5  jz      short loc_180021961
0x1800218f7  cmp     ebx, 5
0x1800218fa  jnz     loc_180021C6F
0x180021900  mov     [rbp+var_10], r12b
0x180021904  mov     [rbp+var_8], r12
0x180021908  lea     rbx, [rsi+138h]
0x18002190f  lea     rdx, [rbp+var_10]
0x180021913  mov     rcx, rbx
0x180021916  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x18002191b  test    al, al
0x18002191d  jz      short loc_180021958
0x18002191f  mov     [rbp+var_10], r12b
0x180021923  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x18002192b  lea     rdx, [rbp+var_10]
0x18002192f  mov     rcx, rbx
0x180021932  call    ??9TSTime@@QEBA_NAEBV0@@Z; TSTime::operator!=(TSTime const &)
0x180021937  test    al, al
0x180021939  jz      short loc_180021958
0x18002193b  lea     rdi, [rsi+1A0h]
0x180021942  mov     rdx, rbx
0x180021945  mov     rcx, rdi
0x180021948  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x18002194d  test    al, al
0x18002194f  jz      short loc_180021958
0x180021951  movups  xmm0, xmmword ptr [rbx]
0x180021954  movdqu  xmmword ptr [rdi], xmm0
0x180021958  mov     [rsi+70h], r12d
0x18002195c  jmp     loc_180021C6F
0x180021961  mov     r9, [rsi+28h]
0x180021965  lea     rdx, [rbp+var_10]
0x180021969  mov     rcx, r9
0x18002196c  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x180021971  mov     rcx, rax; this
0x180021974  call    ?IsEmpty@TSTimePeriod@@QEBA_NXZ; TSTimePeriod::IsEmpty(void)
0x180021979  cmp     al, 1
0x18002197b  jnz     short loc_180021989
0x18002197d  mov     dword ptr [rsi+6Ch], 89h
0x180021984  jmp     loc_180021663
0x180021989  lea     rdx, [rbp+var_10]
0x18002198d  mov     rcx, r9
0x180021990  call    ?GetDeadline@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetDeadline(void)
0x180021995  mov     rcx, rax; this
0x180021998  call    ?IsEmpty@TSTimePeriod@@QEBA_NXZ; TSTimePeriod::IsEmpty(void)
0x18002199d  test    al, al
0x18002199f  jnz     loc_180021C6F
0x1800219a5  lea     rdx, [rbp+var_10]
0x1800219a9  mov     rcx, r9
0x1800219ac  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x1800219b1  lea     rdx, [rbp+var_20]
0x1800219b5  call    ?GetDeadline@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetDeadline(void)
0x1800219ba  mov     [rbp+arg_10], r12b
0x1800219be  lea     r8, [rbp+arg_10]; bool *
  ... truncated ...
```
