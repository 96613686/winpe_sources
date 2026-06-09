# INI_STORE::SetProperties(IPubResource *,IPubNamespaceSet *,IPubTransactionContext * *)

- ea: `0x180002520`
- end: `0x18000282a`
- name: `?SetProperties@INI_STORE@@UEAAJPEAVIPubResource@@PEAVIPubNamespaceSet@@PEAPEAVIPubTransactionContext@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(INI_STORE *this, struct IPubResource *, struct IPubNamespaceSet *, struct IPubTransactionContext **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001a04`
- `0x180002520`
- `0x180002a7c`
- `0x180002c84`
- `0x180002fd0`
- `0x180003340`
- `0x180003490`
- `0x180004010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180002559`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002564`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000256e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002559`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002564`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000256e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800027eb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800027f6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002801`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800027eb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800027f6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002801`
- `KERNEL32!GetPrivateProfileSectionW` at `0x1800027d1`
- `KERNEL32!GetPrivateProfileSectionW` at `0x1800027d1`

## pseudocode

```c
__int64 __fastcall INI_STORE::SetProperties(
        INI_STORE *this,
        struct IPubResource *a2,
        struct IPubNamespaceSet *a3,
        struct IPubTransactionContext **a4)
{
  INI_STORE *v7; // rcx
  int IniBinding; // ebx
  int v9; // r15d
  __int64 (__fastcall ***i)(_QWORD); // rax
  const unsigned __int16 *v11; // r12
  __int64 v12; // r14
  __int64 j; // rax
  const unsigned __int16 *v14; // rax
  __int64 (__fastcall **v15)(_QWORD); // rax
  __int64 (__fastcall ***v16)(_QWORD); // rdi
  __int64 (__fastcall ***v17)(_QWORD); // rdi
  __int64 (__fastcall ***k)(_QWORD); // rax
  const unsigned __int16 *v19; // r12
  __int64 v20; // r14
  __int64 m; // rax
  unsigned __int16 *v22; // rbx
  const unsigned __int16 *v23; // rax
  __int64 v24; // rax
  struct IPubProperty *v25; // rdi
  __int64 (__fastcall ***v26)(_QWORD); // rdi
  unsigned int v28[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v29[32]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h]
  _BYTE v31[32]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpAppName; // [rsp+88h] [rbp-78h]
  _BYTE v33[32]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v34; // [rsp+C0h] [rbp-40h]
  _BYTE v35[64]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v36[64]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR ReturnedString[16]; // [rsp+160h] [rbp+60h] BYREF

  STRU::STRU((STRU *)v29);
  STRU::STRU((STRU *)v31);
  STRU::STRU((STRU *)v33);
  v28[0] = 0;
  IniBinding = MakeIniBinding(a2, (INI_STORE *)((char *)this + 12), (struct INI_BINDING *)v29, 1);
  if ( IniBinding >= 0 )
  {
    IniBinding = INI_STORE::CalculateNewSectionSize(v7, (struct INI_BINDING *)v29, a3, v28);
    if ( IniBinding >= 0 )
    {
      if ( v28[0] < 0x7A120 )
      {
        v9 = 0;
        for ( i = (__int64 (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(struct IPubNamespaceSet *, _BYTE *))a3)(
                                                      a3,
                                                      v36);
              ;
              i = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IPubNamespaceSet *, _BYTE *))(*(_QWORD *)a3 + 8LL))(
                                                      a3,
                                                      v36) )
        {
          v17 = i;
          if ( !i || IniBinding < 0 )
            break;
          v11 = (const unsigned __int16 *)(**i)(i);
          v12 = (*v17)[2](v17);
          for ( j = (**(__int64 (__fastcall ***)(__int64, _BYTE *))v12)(v12, v35);
                ;
                j = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v12 + 8LL))(v12, v35) )
          {
            v16 = (__int64 (__fastcall ***)(_QWORD))j;
            if ( !j || IniBinding < 0 )
              break;
            if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)j + 8LL))(j) )
            {
              v14 = (const unsigned __int16 *)(**v16)(v16);
              IniBinding = WritePropertyValue((struct INI_BINDING *)v29, v14, v11, 0);
              v15 = *v16;
              if ( IniBinding < 0 )
              {
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD), _QWORD))v15[7])(v16, (unsigned int)IniBinding);
              }
              else
              {
                v9 = 1;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD), __int64, _QWORD))v15[6])(v16, 200, 0);
              }
            }
          }
        }
        for ( k = (__int64 (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(struct IPubNamespaceSet *, _BYTE *))a3)(
                                                      a3,
                                                      v36);
              ;
              k = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IPubNamespaceSet *, _BYTE *))(*(_QWORD *)a3 + 8LL))(
                                                      a3,
                                                      v36) )
        {
          v26 = k;
          if ( !k )
            break;
          if ( IniBinding < 0 )
            goto LABEL_35;
          v19 = (const unsigned __int16 *)(**k)(k);
          v20 = (*v26)[2](v26);
          for ( m = (**(__int64 (__fastcall ***)(__int64, _BYTE *))v20)(v20, v35);
                ;
                m = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v20 + 8LL))(v20, v35) )
          {
            v25 = (struct IPubProperty *)m;
            if ( !m || IniBinding < 0 )
              break;
            if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)m + 8LL))(m) )
            {
              IniBinding = EncodePropertyToString(v25, (struct STRU *)v33);
              if ( IniBinding >= 0 )
              {
                v22 = v34;
                v23 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct IPubProperty *))v25)(v25);
                IniBinding = WritePropertyValue((struct INI_BINDING *)v29, v23, v19, v22);
              }
              v24 = *(_QWORD *)v25;
              if ( IniBinding < 0 )
                (*(void (__fastcall **)(struct IPubProperty *, _QWORD))(v24 + 56))(v25, (unsigned int)IniBinding);
              else
                (*(void (__fastcall **)(struct IPubProperty *, __int64, _QWORD))(v24 + 48))(v25, 200, 0);
            }
          }
        }
        if ( IniBinding >= 0 && v9 && !GetPrivateProfileSectionW(lpAppName, ReturnedString, 0x10u, lpFileName) )
          IniBinding = DeleteEntireSection((struct INI_BINDING *)v29);
      }
      else
      {
        IniBinding = -2147024888;
      }
    }
  }
LABEL_35:
  STRU::~STRU((STRU *)v33);
  STRU::~STRU((STRU *)v31);
  STRU::~STRU((STRU *)v29);
  return (unsigned int)IniBinding;
}

```

## disassembly

```asm
0x180002520  push    rbp
0x180002522  push    rbx
0x180002523  push    rsi
0x180002524  push    rdi
0x180002525  push    r12
0x180002527  push    r14
0x180002529  push    r15
0x18000252b  lea     rbp, [rsp-90h]
0x180002533  sub     rsp, 190h
0x18000253a  mov     rax, cs:__security_cookie
0x180002541  xor     rax, rsp
0x180002544  mov     [rbp+0C0h+var_40], rax
0x18000254b  mov     rbx, rcx
0x18000254e  mov     rsi, r8
0x180002551  lea     rcx, [rsp+1C0h+var_190]
0x180002556  mov     rdi, rdx
0x180002559  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000255f  lea     rcx, [rsp+1C0h+var_158]
0x180002564  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000256a  lea     rcx, [rbp+0C0h+var_120]
0x18000256e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002574  lea     rdx, [rbx+0Ch]; struct INI_OPTIONS *
0x180002578  mov     [rsp+1C0h+var_1A0], 0
0x180002580  mov     r9d, 1; int
0x180002586  lea     r8, [rsp+1C0h+var_190]; struct INI_BINDING *
0x18000258b  mov     rcx, rdi; struct IPubResource *
0x18000258e  call    ?MakeIniBinding@@YAJPEAVIPubResource@@PEAUINI_OPTIONS@@PEAUINI_BINDING@@H@Z; MakeIniBinding(IPubResource *,INI_OPTIONS *,INI_BINDING *,int)
0x180002593  mov     ebx, eax
0x180002595  test    eax, eax
0x180002597  js      loc_1800027E7
0x18000259d  lea     r9, [rsp+1C0h+var_1A0]; unsigned int *
0x1800025a2  mov     r8, rsi; struct IPubNamespaceSet *
0x1800025a5  lea     rdx, [rsp+1C0h+var_190]; struct INI_BINDING *
0x1800025aa  call    ?CalculateNewSectionSize@INI_STORE@@AEAAJPEAUINI_BINDING@@PEAVIPubNamespaceSet@@PEAK@Z; INI_STORE::CalculateNewSectionSize(INI_BINDING *,IPubNamespaceSet *,ulong *)
0x1800025af  mov     ebx, eax
0x1800025b1  test    eax, eax
0x1800025b3  js      loc_1800027E7
0x1800025b9  cmp     [rsp+1C0h+var_1A0], 7A120h
0x1800025c1  jb      short loc_1800025CD
0x1800025c3  mov     ebx, 80070008h
0x1800025c8  jmp     loc_1800027E7
0x1800025cd  mov     rax, [rsi]
0x1800025d0  xor     r15d, r15d
0x1800025d3  mov     rax, [rax]
0x1800025d6  jmp     loc_1800026A1
0x1800025db  test    ebx, ebx
0x1800025dd  js      loc_1800026B9
0x1800025e3  mov     rcx, [rdi]
0x1800025e6  mov     rax, [rcx]
0x1800025e9  mov     rcx, rdi
0x1800025ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025f1  mov     rcx, [rdi]
0x1800025f4  mov     r12, rax
0x1800025f7  mov     rax, [rcx+10h]
0x1800025fb  mov     rcx, rdi
0x1800025fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002603  mov     r14, rax
0x180002606  mov     rcx, [rax]
0x180002609  mov     rax, [rcx]
0x18000260c  jmp     short loc_180002682
0x18000260e  test    ebx, ebx
0x180002610  js      loc_18000269A
0x180002616  mov     rcx, [rdi]
0x180002619  mov     rax, [rcx+8]
0x18000261d  mov     rcx, rdi
0x180002620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002625  test    rax, rax
0x180002628  jnz     short loc_18000267B
0x18000262a  mov     rax, [rdi]
0x18000262d  mov     rcx, rdi
0x180002630  mov     rax, [rax]
0x180002633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002638  mov     rdx, rax; unsigned __int16 *
0x18000263b  lea     rcx, [rsp+1C0h+var_190]; struct INI_BINDING *
0x180002640  xor     r9d, r9d; unsigned __int16 *
0x180002643  mov     r8, r12; unsigned __int16 *
0x180002646  call    ?WritePropertyValue@@YAJPEAUINI_BINDING@@PEBG11@Z; WritePropertyValue(INI_BINDING *,ushort const *,ushort const *,ushort const *)
0x18000264b  mov     ebx, eax
0x18000264d  mov     rcx, rdi
0x180002650  mov     rax, [rdi]
0x180002653  test    ebx, ebx
0x180002655  js      short loc_180002670
0x180002657  mov     rax, [rax+30h]
0x18000265b  xor     r8d, r8d
0x18000265e  mov     edx, 0C8h
0x180002663  mov     r15d, 1
0x180002669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000266e  jmp     short loc_18000267B
0x180002670  mov     rax, [rax+38h]
0x180002674  mov     edx, ebx
0x180002676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000267b  mov     rax, [r14]
0x18000267e  mov     rax, [rax+8]
0x180002682  lea     rdx, [rbp+0C0h+var_E0]
0x180002686  mov     rcx, r14
0x180002689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000268e  mov     rdi, rax
0x180002691  test    rax, rax
0x180002694  jnz     loc_18000260E
0x18000269a  mov     rax, [rsi]
0x18000269d  mov     rax, [rax+8]
0x1800026a1  lea     rdx, [rbp+0C0h+var_A0]
0x1800026a5  mov     rcx, rsi
0x1800026a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ad  mov     rdi, rax
0x1800026b0  test    rax, rax
0x1800026b3  jnz     loc_1800025DB
0x1800026b9  mov     rax, [rsi]
0x1800026bc  mov     rax, [rax]
0x1800026bf  jmp     loc_18000279D
0x1800026c4  test    ebx, ebx
0x1800026c6  js      loc_1800027E7
0x1800026cc  mov     rcx, [rdi]
0x1800026cf  mov     rax, [rcx]
0x1800026d2  mov     rcx, rdi
0x1800026d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026da  mov     rcx, [rdi]
0x1800026dd  mov     r12, rax
0x1800026e0  mov     rax, [rcx+10h]
0x1800026e4  mov     rcx, rdi
0x1800026e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ec  mov     r14, rax
0x1800026ef  mov     rcx, [rax]
0x1800026f2  mov     rax, [rcx]
0x1800026f5  jmp     loc_18000277E
0x1800026fa  test    ebx, ebx
0x1800026fc  js      loc_180002796
0x180002702  mov     rcx, [rdi]
0x180002705  mov     rax, [rcx+8]
0x180002709  mov     rcx, rdi
0x18000270c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002711  test    rax, rax
0x180002714  jz      short loc_180002777
0x180002716  lea     rdx, [rbp+0C0h+var_120]; struct STRU *
0x18000271a  mov     rcx, rdi; struct IPubProperty *
0x18000271d  call    ?EncodePropertyToString@@YAJPEAVIPubProperty@@PEAVSTRU@@@Z; EncodePropertyToString(IPubProperty *,STRU *)
0x180002722  mov     ebx, eax
0x180002724  test    eax, eax
0x180002726  js      short loc_18000274F
0x180002728  mov     rax, [rdi]
0x18000272b  mov     rcx, rdi
0x18000272e  mov     rbx, [rbp+0C0h+var_100]
0x180002732  mov     rax, [rax]
0x180002735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273a  mov     r9, rbx; unsigned __int16 *
0x18000273d  lea     rcx, [rsp+1C0h+var_190]; struct INI_BINDING *
0x180002742  mov     r8, r12; unsigned __int16 *
0x180002745  mov     rdx, rax; unsigned __int16 *
0x180002748  call    ?WritePropertyValue@@YAJPEAUINI_BINDING@@PEBG11@Z; WritePropertyValue(INI_BINDING *,ushort const *,ushort const *,ushort const *)
0x18000274d  mov     ebx, eax
0x18000274f  mov     rax, [rdi]
0x180002752  mov     rcx, rdi
0x180002755  test    ebx, ebx
0x180002757  js      short loc_18000276C
0x180002759  mov     rax, [rax+30h]
0x18000275d  xor     r8d, r8d
0x180002760  mov     edx, 0C8h
0x180002765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276a  jmp     short loc_180002777
0x18000276c  mov     rax, [rax+38h]
0x180002770  mov     edx, ebx
0x180002772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002777  mov     rax, [r14]
0x18000277a  mov     rax, [rax+8]
0x18000277e  lea     rdx, [rbp+0C0h+var_E0]
0x180002782  mov     rcx, r14
0x180002785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000278a  mov     rdi, rax
0x18000278d  test    rax, rax
0x180002790  jnz     loc_1800026FA
0x180002796  mov     rax, [rsi]
0x180002799  mov     rax, [rax+8]
0x18000279d  lea     rdx, [rbp+0C0h+var_A0]
0x1800027a1  mov     rcx, rsi
0x1800027a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027a9  mov     rdi, rax
0x1800027ac  test    rax, rax
0x1800027af  jnz     loc_1800026C4
0x1800027b5  test    ebx, ebx
0x1800027b7  js      short loc_1800027E7
0x1800027b9  test    r15d, r15d
0x1800027bc  jz      short loc_1800027E7
0x1800027be  mov     r9, [rsp+1C0h+lpFileName]; lpFileName
0x1800027c3  lea     rdx, [rbp+0C0h+ReturnedString]; lpReturnedString
0x1800027c7  mov     rcx, [rbp+0C0h+lpAppName]; lpAppName
0x1800027cb  mov     r8d, 10h; nSize
0x1800027d1  call    cs:__imp_GetPrivateProfileSectionW
0x1800027d7  test    eax, eax
0x1800027d9  jnz     short loc_1800027E7
0x1800027db  lea     rcx, [rsp+1C0h+var_190]; struct INI_BINDING *
0x1800027e0  call    ?DeleteEntireSection@@YAJPEAUINI_BINDING@@@Z; DeleteEntireSection(INI_BINDING *)
0x1800027e5  mov     ebx, eax
0x1800027e7  lea     rcx, [rbp+0C0h+var_120]
0x1800027eb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800027f1  lea     rcx, [rsp+1C0h+var_158]
0x1800027f6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800027fc  lea     rcx, [rsp+1C0h+var_190]
0x180002801  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002807  mov     eax, ebx
0x180002809  mov     rcx, [rbp+0C0h+var_40]
0x180002810  xor     rcx, rsp; StackCookie
0x180002813  call    __security_check_cookie
0x180002818  add     rsp, 190h
0x18000281f  pop     r15
0x180002821  pop     r14
0x180002823  pop     r12
0x180002825  pop     rdi
0x180002826  pop     rsi
0x180002827  pop     rbx
0x180002828  pop     rbp
0x180002829  retn
```
