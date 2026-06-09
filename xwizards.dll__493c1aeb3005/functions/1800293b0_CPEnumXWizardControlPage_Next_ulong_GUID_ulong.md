# CPEnumXWizardControlPage::Next(ulong,_GUID * *,ulong *)

- ea: `0x1800293b0`
- end: `0x1800296d1`
- name: `?Next@CPEnumXWizardControlPage@@UEAAJKPEAPEAU_GUID@@PEAK@Z`
- size: `801`
- prototype: `int(CPEnumXWizardControlPage *__hidden this, unsigned int, struct _GUID **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x180024a8c`
- `0x180024b10`
- `0x1800293b0`
- `0x180032a02`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029455`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029455`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002961b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002961b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029642`

## pseudocode

```c
__int64 __fastcall CPEnumXWizardControlPage::Next(
        CPEnumXWizardControlPage *this,
        unsigned int a2,
        struct _GUID **a3,
        unsigned int *a4)
{
  unsigned int *v4; // r15
  unsigned int v5; // r14d
  CPEnumXWizardControlPage *v6; // rbx
  int v7; // edi
  unsigned int v8; // esi
  _DWORD *v9; // r12
  bool v10; // zf
  bool v11; // sf
  struct _GUID *v12; // r14
  struct _GUID *v13; // rax
  struct _GUID *v14; // r13
  unsigned __int64 v15; // rdx
  __int64 *v16; // rbx
  __int64 v17; // rdi
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rax
  bool v21; // al
  __int64 v22; // rcx
  __int64 v23; // r13
  __int64 v24; // r14
  struct _GUID **v25; // r13
  unsigned int v27; // [rsp+20h] [rbp-68h]
  int v28; // [rsp+24h] [rbp-64h]
  __int64 (__fastcall *v29)(__int64, __int64, struct _GUID *); // [rsp+28h] [rbp-60h]
  struct _GUID *v30; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID *v31; // [rsp+38h] [rbp-50h]
  char *v32; // [rsp+40h] [rbp-48h]
  struct _GUID **v33; // [rsp+48h] [rbp-40h]

  v4 = a4;
  v5 = a2;
  v6 = this;
  if ( a3 && (a4 || a2 == 1) )
  {
    v33 = a3;
    v7 = 0;
    v8 = 0;
    v27 = 0;
    v9 = (_DWORD *)((char *)this + 104);
    v32 = (char *)this + 104;
    v28 = *((_DWORD *)this + 26);
    if ( a4 )
      *a4 = 0;
    memset_0(a3, 0, 8LL * a2);
LABEL_7:
    v10 = v7 == 0;
    v11 = v7 < 0;
    while ( v10 )
    {
      if ( v8 >= v5 )
        goto LABEL_50;
      v12 = (struct _GUID *)CoTaskMemAlloc(0x10u);
      v31 = v12;
      v13 = (struct _GUID *)CoTaskMemAlloc(0x10u);
      v14 = v13;
      v30 = v13;
      if ( v12 && v13 )
      {
        *v12 = 0;
        v15 = (unsigned int)*v9;
        if ( (_DWORD)v15 == *((_DWORD *)v6 + 27) )
        {
          v7 = 1;
        }
        else
        {
          v16 = (__int64 *)((char *)v6 + 80);
          if ( v15 < (v16[1] - *v16) >> 3 )
          {
            *v12 = *(struct _GUID *)*(_QWORD *)std::vector<_XWIZARD_PAGE_DATA *>::at(v16, v15);
            CoTaskMemFree(v14);
            goto LABEL_40;
          }
          v17 = *((_QWORD *)this + 8);
          if ( v17 )
          {
            v29 = *(__int64 (__fastcall **)(__int64, __int64, struct _GUID *))(*(_QWORD *)v17 + 80LL);
            if ( (_DWORD)v15 )
            {
              v18 = *(_QWORD *)std::vector<_XWIZARD_PAGE_DATA *>::at(v16, (unsigned int)(v15 - 1));
              v19 = v29(v17, v18, v12);
            }
            else
            {
              v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _GUID *))(*(_QWORD *)v17 + 80LL))(v17, 0, v12);
            }
          }
          else
          {
            v19 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 9) + 80LL))(
                    *((_QWORD *)this + 9),
                    v12);
          }
          v7 = v19;
          if ( v19 < 0 )
          {
LABEL_41:
            v6 = this;
          }
          else
          {
            v20 = *(_QWORD *)&v12->Data1 - *(_QWORD *)&GUID_NULL.Data1;
            if ( *(_QWORD *)&v12->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
              v20 = *(_QWORD *)v12->Data4 - *(_QWORD *)GUID_NULL.Data4;
            if ( v20 )
            {
              v7 = 0;
              try
              {
                *v14 = *v12;
                v21 = (unsigned __int64)&v30 < v16[1] && *v16 <= (unsigned __int64)&v30;
                v22 = v16[2];
                if ( v21 )
                {
                  v23 = *v16;
                  if ( v16[1] == v22 )
                    std::vector<_GUID *>::_Reserve(v16);
                  *(_QWORD *)v16[1] = *(_QWORD *)(*v16 + 8 * (((__int64)&v30 - v23) >> 3));
                }
                else
                {
                  if ( v16[1] == v22 )
                    std::vector<_GUID *>::_Reserve(v16);
                  *(_QWORD *)v16[1] = v14;
                }
                v16[1] += 8;
              }
              catch ( std::bad_alloc )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    10,
                    &WPP_d4256cb9cd783c1ed4ccbaed64b6cca7_Traceguids,
                    2147942414LL);
                v4 = a4;
                v7 = -2147024882;
                v12 = v31;
                v14 = v30;
                v8 = v27;
                v9 = v32;
                goto LABEL_41;
              }
LABEL_40:
              a3[v8++] = v12;
              v27 = v8;
              ++*v9;
LABEL_47:
              v6 = this;
              v5 = a2;
              goto LABEL_7;
            }
            v7 = 1;
            v6 = this;
            *((_DWORD *)this + 27) = *v9;
          }
        }
      }
      else
      {
        v7 = -2147024882;
      }
      CoTaskMemFree(v12);
      CoTaskMemFree(v14);
      v10 = v7 == 0;
      v11 = v7 < 0;
      v5 = a2;
      if ( v7 < 0 )
      {
        v24 = 0;
        if ( v8 )
        {
          v25 = v33;
          do
          {
            CoTaskMemFree(v25[v24]);
            v25[v24] = 0;
            v24 = (unsigned int)(v24 + 1);
          }
          while ( (unsigned int)v24 < v8 );
        }
        *v9 = v28;
        goto LABEL_47;
      }
    }
    if ( !v11 )
    {
LABEL_50:
      if ( v4 )
        *v4 = v8;
    }
  }
  else
  {
    v7 = -2147467261;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_d4256cb9cd783c1ed4ccbaed64b6cca7_Traceguids,
      (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800293b0  mov     rax, rsp
0x1800293b3  mov     [rax+20h], r9
0x1800293b7  mov     [rax+18h], r8
0x1800293bb  mov     [rax+10h], edx
0x1800293be  mov     [rax+8], rcx
0x1800293c2  push    rbx
0x1800293c3  push    rsi
0x1800293c4  push    rdi
0x1800293c5  push    r12
0x1800293c7  push    r13
0x1800293c9  push    r14
0x1800293cb  push    r15
0x1800293cd  sub     rsp, 50h
0x1800293d1  mov     r15, r9
0x1800293d4  mov     rax, r8
0x1800293d7  mov     r14d, edx
0x1800293da  mov     rbx, rcx
0x1800293dd  test    r8, r8
0x1800293e0  jz      loc_180029689
0x1800293e6  test    r9, r9
0x1800293e9  jnz     short loc_1800293F5
0x1800293eb  cmp     r14d, 1
0x1800293ef  jnz     loc_180029689
0x1800293f5  mov     [rsp+88h+var_40], rax
0x1800293fa  xor     edi, edi
0x1800293fc  xor     esi, esi
0x1800293fe  mov     [rsp+88h+var_68], esi
0x180029402  lea     r12, [rcx+68h]
0x180029406  mov     [rsp+88h+var_48], r12
0x18002940b  mov     ecx, [r12]
0x18002940f  mov     [rsp+88h+var_64], ecx
0x180029413  test    r9, r9
0x180029416  jz      short loc_18002941B
0x180029418  mov     [r9], esi
0x18002941b  mov     r8, r14
0x18002941e  shl     r8, 3; Size
0x180029422  xor     edx, edx; Val
0x180029424  mov     rcx, rax; void *
0x180029427  call    memset_0
0x18002942c  test    edi, edi
0x18002942e  jnz     loc_18002967D
0x180029434  cmp     esi, r14d
0x180029437  jnb     loc_18002967F
0x18002943d  mov     ecx, 10h; cb
0x180029442  call    cs:__imp_CoTaskMemAlloc
0x180029448  mov     r14, rax
0x18002944b  mov     [rsp+88h+var_50], rax
0x180029450  mov     ecx, 10h; cb
0x180029455  call    cs:__imp_CoTaskMemAlloc
0x18002945b  mov     r13, rax
0x18002945e  mov     [rsp+88h+var_58], rax
0x180029463  test    r14, r14
0x180029466  jz      loc_180029676
0x18002946c  test    rax, rax
0x18002946f  jz      loc_180029676
0x180029475  xorps   xmm0, xmm0
0x180029478  movups  xmmword ptr [r14], xmm0
0x18002947c  mov     edx, [r12]
0x180029480  cmp     edx, [rbx+6Ch]
0x180029483  jnz     short loc_18002948F
0x180029485  mov     edi, 1
0x18002948a  jmp     loc_18002960F
0x18002948f  add     rbx, 50h ; 'P'
0x180029493  mov     rax, [rbx+8]
0x180029497  sub     rax, [rbx]
0x18002949a  sar     rax, 3
0x18002949e  cmp     rdx, rax
0x1800294a1  jnb     short loc_1800294C4
0x1800294a3  mov     rcx, rbx
0x1800294a6  call    ?at@?$vector@PEAU_XWIZARD_PAGE_DATA@@V?$allocator@PEAU_XWIZARD_PAGE_DATA@@@std@@@std@@QEAAAEAPEAU_XWIZARD_PAGE_DATA@@_K@Z; std::vector<_XWIZARD_PAGE_DATA *>::at(unsigned __int64)
0x1800294ab  mov     rdx, [rax]
0x1800294ae  movups  xmm0, xmmword ptr [rdx]
0x1800294b1  movdqu  xmmword ptr [r14], xmm0
0x1800294b6  mov     rcx, r13; pv
0x1800294b9  call    cs:__imp_CoTaskMemFree
0x1800294bf  jmp     loc_1800295CE
0x1800294c4  mov     rcx, [rsp+88h+arg_0]
0x1800294cc  mov     rdi, [rcx+40h]
0x1800294d0  test    rdi, rdi
0x1800294d3  jz      short loc_180029508
0x1800294d5  mov     rax, [rdi]
0x1800294d8  mov     rax, [rax+50h]
0x1800294dc  mov     [rsp+88h+var_60], rax
0x1800294e1  test    edx, edx
0x1800294e3  jz      short loc_1800294F9
0x1800294e5  dec     edx
0x1800294e7  mov     rcx, rbx
0x1800294ea  call    ?at@?$vector@PEAU_XWIZARD_PAGE_DATA@@V?$allocator@PEAU_XWIZARD_PAGE_DATA@@@std@@@std@@QEAAAEAPEAU_XWIZARD_PAGE_DATA@@_K@Z; std::vector<_XWIZARD_PAGE_DATA *>::at(unsigned __int64)
0x1800294ef  mov     rdx, [rax]
0x1800294f2  mov     rax, [rsp+88h+var_60]
0x1800294f7  jmp     short loc_1800294FB
0x1800294f9  xor     edx, edx
0x1800294fb  mov     r8, r14
0x1800294fe  mov     rcx, rdi
0x180029501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029506  jmp     short loc_18002951B
0x180029508  mov     rcx, [rcx+48h]
0x18002950c  mov     rax, [rcx]
0x18002950f  mov     rdx, r14
0x180029512  mov     rax, [rax+50h]
0x180029516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002951b  mov     edi, eax
0x18002951d  test    eax, eax
0x18002951f  js      loc_180029607
0x180029525  mov     rax, [r14]
0x180029528  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18002952f  jnz     short loc_18002953C
0x180029531  mov     rax, [r14+8]
0x180029535  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18002953c  test    rax, rax
0x18002953f  jnz     short loc_180029558
0x180029541  lea     edi, [rax+1]
0x180029544  mov     eax, [r12]
0x180029548  mov     rbx, [rsp+88h+arg_0]
0x180029550  mov     [rbx+6Ch], eax
0x180029553  jmp     loc_18002960F
0x180029558  xor     edi, edi
0x18002955a  movups  xmm0, xmmword ptr [r14]
0x18002955e  movdqu  xmmword ptr [r13+0], xmm0
0x180029564  lea     rax, [rsp+88h+var_58]
0x180029569  cmp     rax, [rbx+8]
0x18002956d  jnb     short loc_18002957D
0x18002956f  lea     rax, [rsp+88h+var_58]
0x180029574  cmp     [rbx], rax
0x180029577  ja      short loc_18002957D
0x180029579  mov     al, 1
0x18002957b  jmp     short loc_18002957F
0x18002957d  xor     al, al
0x18002957f  mov     rcx, [rbx+10h]
0x180029583  test    al, al
0x180029585  jz      short loc_1800295B4
0x180029587  mov     r13, [rbx]
0x18002958a  cmp     [rbx+8], rcx
0x18002958e  jnz     short loc_180029598
0x180029590  mov     rcx, rbx
0x180029593  call    ?_Reserve@?$vector@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@IEAAX_K@Z; std::vector<_GUID *>::_Reserve(unsigned __int64)
0x180029598  lea     rdx, [rsp+88h+var_58]
0x18002959d  sub     rdx, r13
0x1800295a0  sar     rdx, 3
0x1800295a4  mov     rax, [rbx]
0x1800295a7  mov     rcx, [rbx+8]
0x1800295ab  mov     rax, [rax+rdx*8]
0x1800295af  mov     [rcx], rax
0x1800295b2  jmp     short loc_1800295C9
0x1800295b4  cmp     [rbx+8], rcx
0x1800295b8  jnz     short loc_1800295C2
0x1800295ba  mov     rcx, rbx
0x1800295bd  call    ?_Reserve@?$vector@PEAU_GUID@@V?$allocator@PEAU_GUID@@@std@@@std@@IEAAX_K@Z; std::vector<_GUID *>::_Reserve(unsigned __int64)
0x1800295c2  mov     rax, [rbx+8]
0x1800295c6  mov     [rax], r13
0x1800295c9  add     qword ptr [rbx+8], 8
0x1800295ce  mov     eax, esi
0x1800295d0  mov     rcx, [rsp+88h+arg_10]
0x1800295d8  mov     [rcx+rax*8], r14
0x1800295dc  inc     esi
0x1800295de  mov     [rsp+88h+var_68], esi
0x1800295e2  inc     dword ptr [r12]
0x1800295e6  jmp     short loc_180029661
0x1800295e8  mov     r15, [rsp+88h+arg_18]
0x1800295f0  mov     edi, dword ptr [rsp+88h+var_60]
0x1800295f4  mov     r14, [rsp+88h+var_50]
0x1800295f9  mov     r13, [rsp+88h+var_58]
0x1800295fe  mov     esi, [rsp+88h+var_68]
0x180029602  mov     r12, [rsp+88h+var_48]
0x180029607  mov     rbx, [rsp+88h+arg_0]
0x18002960f  mov     rcx, r14; pv
0x180029612  call    cs:__imp_CoTaskMemFree
0x180029618  mov     rcx, r13; pv
0x18002961b  call    cs:__imp_CoTaskMemFree
0x180029621  test    edi, edi
0x180029623  mov     r14d, [rsp+88h+arg_8]
0x18002962b  jns     loc_18002942E
0x180029631  xor     r14d, r14d
0x180029634  test    esi, esi
0x180029636  jz      short loc_180029659
0x180029638  mov     r13, [rsp+88h+var_40]
0x18002963d  mov     rcx, [r13+r14*8+0]; pv
0x180029642  call    cs:__imp_CoTaskMemFree
0x180029648  mov     qword ptr [r13+r14*8+0], 0
0x180029651  inc     r14d
0x180029654  cmp     r14d, esi
0x180029657  jb      short loc_18002963D
0x180029659  mov     eax, [rsp+88h+var_64]
0x18002965d  mov     [r12], eax
0x180029661  mov     rbx, [rsp+88h+arg_0]
0x180029669  mov     r14d, [rsp+88h+arg_8]
0x180029671  jmp     loc_18002942C
0x180029676  mov     edi, 8007000Eh
0x18002967b  jmp     short loc_18002960F
0x18002967d  js      short loc_18002968E
0x18002967f  test    r15, r15
0x180029682  jz      short loc_18002968E
0x180029684  mov     [r15], esi
0x180029687  jmp     short loc_18002968E
0x180029689  mov     edi, 80004003h
0x18002968e  lea     rax, WPP_GLOBAL_Control
0x180029695  mov     rcx, cs:WPP_GLOBAL_Control
0x18002969c  cmp     rcx, rax
0x18002969f  jz      short loc_1800296BF
0x1800296a1  test    byte ptr [rcx+1Ch], 10h
0x1800296a5  jz      short loc_1800296BF
0x1800296a7  mov     edx, 0Bh
0x1800296ac  mov     r9d, edi
0x1800296af  lea     r8, WPP_d4256cb9cd783c1ed4ccbaed64b6cca7_Traceguids
0x1800296b6  mov     rcx, [rcx+10h]
0x1800296ba  call    WPP_SF_d
0x1800296bf  mov     eax, edi
0x1800296c1  add     rsp, 50h
0x1800296c5  pop     r15
0x1800296c7  pop     r14
0x1800296c9  pop     r13
0x1800296cb  pop     r12
0x1800296cd  pop     rdi
0x1800296ce  pop     rsi
0x1800296cf  pop     rbx
0x1800296d0  retn
```
