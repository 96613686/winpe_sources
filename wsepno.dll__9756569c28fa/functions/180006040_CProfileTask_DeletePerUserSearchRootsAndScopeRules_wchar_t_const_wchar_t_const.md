# CProfileTask::DeletePerUserSearchRootsAndScopeRules(wchar_t const *,wchar_t const *)

- ea: `0x180006040`
- end: `0x1800065df`
- name: `?DeletePerUserSearchRootsAndScopeRules@CProfileTask@@QEAAJPEB_W0@Z`
- size: `1439`
- prototype: `__int64 __fastcall(CProfileTask *this, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006b50`
- `0x180006d10`

## callees

- `0x180001794`
- `0x180001b9c`
- `0x180003b7c`
- `0x180003be0`
- `0x180006040`
- `0x18000a6bc`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800061b9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800061b9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006223`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000643f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006223`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000643f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000628a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006465`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000628a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006465`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000608d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000608d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProfileTask::DeletePerUserSearchRootsAndScopeRules(
        CProfileTask *this,
        const wchar_t *a2,
        const wchar_t *a3)
{
  const wchar_t *v3; // r13
  int v6; // edi
  unsigned __int128 v7; // rax
  void *v8; // r9
  WCHAR *v9; // rsi
  __int64 v10; // rbx
  wchar_t *v11; // r14
  WCHAR *v12; // rdi
  wchar_t *v13; // rax
  _WORD *v14; // rdx
  WCHAR v15; // ax
  _WORD *v16; // r8
  __int64 v17; // rcx
  signed int v18; // ebx
  __int64 v19; // rsi
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rax
  wchar_t *v22; // rax
  wchar_t *v23; // rdi
  __int64 v24; // rax
  wchar_t *v25; // rcx
  unsigned __int64 v26; // rdx
  wchar_t *v27; // r9
  wchar_t v28; // r8
  wchar_t *v29; // rcx
  __int64 cchCount2; // rsi
  signed int i; // eax
  wchar_t *v32; // rcx
  const wchar_t *v33; // rbx
  __int64 (__fastcall *v34)(const wchar_t *, __int64, wchar_t **, _QWORD); // r14
  wchar_t *v35; // rcx
  const wchar_t *v36; // rcx
  wchar_t *Str; // [rsp+30h] [rbp-39h] BYREF
  PCNZWCH lpString2; // [rsp+38h] [rbp-31h] BYREF
  __int64 v40; // [rsp+40h] [rbp-29h] BYREF
  const wchar_t *v41; // [rsp+48h] [rbp-21h] BYREF
  __int64 v42; // [rsp+50h] [rbp-19h] BYREF
  __int64 v43; // [rsp+58h] [rbp-11h] BYREF
  __int64 v44; // [rsp+60h] [rbp-9h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-1h] BYREF
  wchar_t *v46; // [rsp+70h] [rbp+7h]
  __int128 v47; // [rsp+78h] [rbp+Fh] BYREF
  wchar_t v48; // [rsp+88h] [rbp+1Fh]

  v3 = a3;
  v41 = a3;
  ppv = 0;
  v44 = 0;
  if ( CoCreateInstance(
         &GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39,
         0,
         0x15u,
         &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69,
         &ppv) < 0
    || (v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 80LL))(
               ppv,
               L"SystemIndex",
               &v44),
        v6 < 0) )
  {
    v6 = -2147023838;
  }
  v40 = 0;
  if ( v6 >= 0 )
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 224LL))(v44, &v40);
  v43 = 0;
  if ( v6 >= 0 )
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL))(v40, &v43);
  v42 = 0;
  if ( !v6 )
  {
    do
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v43 + 24LL))(v43, 1, &v42);
      if ( v6 )
        break;
      Str = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v42 + 48LL))(v42, &Str);
      v9 = 0;
      lpString2 = 0;
      if ( v6 >= 0 )
      {
        v10 = -1;
        do
          ++v10;
        while ( Str[v10] );
        v46 = 0;
        v7 = (unsigned int)v10 * (unsigned __int128)2uLL;
        if ( is_mul_ok((unsigned int)v10, 2u) )
        {
          v6 = ProfNotif_HeapAlloc(2LL * (unsigned int)v10, SDWORD2(v7), (void **)&lpString2, v8);
          v9 = (WCHAR *)lpString2;
          if ( v6 >= 0 )
          {
            v11 = Str;
            v12 = (WCHAR *)lpString2;
            *lpString2 = 0;
            v13 = wcsstr(v11, L"://{");
            if ( v13 )
            {
              v14 = v13 + 4;
              v15 = v13[4];
              if ( v15 )
              {
                v16 = v14;
                do
                {
                  if ( v15 == 125 )
                    break;
                  *v12++ = v15;
                  if ( (unsigned int)(v16 - v11) >= (int)v10 - 1 )
                    break;
                  v15 = *++v14;
                }
                while ( *v14 );
              }
              *v12 = 0;
            }
            if ( CompareStringW(0x7Fu, 1u, a2, -1, v9, -1) == 2 )
            {
              LODWORD(v7) = (*(__int64 (__fastcall **)(__int64, wchar_t *))(*(_QWORD *)v40 + 40LL))(v40, Str);
              v6 = v7;
              if ( (v7 & 0x80000000) != 0LL )
              {
                if ( (_DWORD)v7 != -2147023838 )
                  (*(void (__fastcall **)(CProfileTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, (unsigned int)v7);
              }
              else
              {
                (*(void (__fastcall **)(CProfileTask *))(*(_QWORD *)this + 16LL))(this);
              }
            }
            else
            {
              v6 = 0;
            }
          }
        }
        else
        {
          v6 = -2147024362;
        }
      }
      ProfNotif_HeapFree(v9, *((void **)&v7 + 1));
      CoTaskMemFree(Str);
      v17 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    while ( !v6 );
    v3 = v41;
  }
  v18 = 0;
  if ( v6 != 1 )
    v18 = v6;
  if ( v18 < 0 )
    goto LABEL_78;
  v47 = *(_OWORD *)L"file:///";
  v48 = aFile[8];
  v19 = -1;
  do
    ++v19;
  while ( v3[v19] );
  v20 = v19 + 9;
  v21 = 2 * v20;
  if ( !is_mul_ok(v20, 2u) )
    v21 = -1;
  v22 = (wchar_t *)operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
  v23 = v22;
  v46 = v22;
  if ( v22 )
  {
    if ( v20 )
    {
      if ( v20 <= 0x7FFFFFFF )
      {
        v24 = 2147483646;
        v25 = (wchar_t *)&v47;
        v26 = v20;
        v27 = v23;
        do
        {
          if ( !v24 )
            break;
          v28 = *v25;
          if ( !*v25 )
            break;
          ++v25;
          *v27++ = v28;
          --v24;
          --v26;
        }
        while ( v26 );
        v18 = v26 == 0 ? 0x8007007A : 0;
        v29 = v27 - 1;
        if ( v26 )
          v29 = v27;
        *v29 = 0;
        if ( v26 )
        {
          v18 = StringCchCatW(v23, v20, v3);
          if ( v18 >= 0 )
          {
            v41 = 0;
            v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v40 + 80LL))(v40, &v41);
            if ( !v18 )
            {
              cchCount2 = -1;
              do
                ++cchCount2;
              while ( v23[cchCount2] );
              Str = 0;
              for ( i = (*(__int64 (__fastcall **)(const wchar_t *, __int64, wchar_t **, _QWORD))(*(_QWORD *)v41 + 24LL))(
                          v41,
                          1,
                          &Str,
                          0); ; i = v34(v33, 1, &Str, 0) )
              {
                v18 = i;
                if ( i )
                  break;
                lpString2 = 0;
                if ( (*(int (__fastcall **)(wchar_t *, PCNZWCH *))(*(_QWORD *)Str + 24LL))(Str, &lpString2) >= 0 )
                {
                  if ( CompareStringW(0x7Fu, 1u, v23, -1, lpString2, cchCount2) == 2 )
                    (*(void (__fastcall **)(__int64, PCNZWCH))(*(_QWORD *)v40 + 144LL))(v40, lpString2);
                  CoTaskMemFree((LPVOID)lpString2);
                }
                v32 = Str;
                if ( Str )
                {
                  Str = 0;
                  (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v32 + 16LL))(v32);
                  v32 = Str;
                }
                v33 = v41;
                v34 = *(__int64 (__fastcall **)(const wchar_t *, __int64, wchar_t **, _QWORD))(*(_QWORD *)v41 + 24LL);
                if ( v32 )
                {
                  Str = 0;
                  (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v32 + 16LL))(v32);
                }
              }
              v35 = Str;
              if ( Str )
              {
                Str = 0;
                (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v35 + 16LL))(v35);
              }
            }
            v36 = v41;
            if ( v41 )
            {
              v41 = 0;
              (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v36 + 16LL))(v36);
            }
          }
        }
      }
      else
      {
        v18 = -2147024809;
        *v22 = 0;
      }
    }
    else
    {
      v18 = -2147024809;
    }
  }
  else
  {
    v18 = -2147024882;
  }
  if ( v23 )
    operator delete(v23);
  if ( v18 < 0 )
  {
LABEL_78:
    if ( v18 == -2147023838 || v18 == -2147024875 )
      v18 = 0;
  }
  else
  {
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 128LL))(v40);
  }
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180006040  mov     [rsp-8+arg_18], rbx
0x180006045  push    rbp
0x180006046  push    rsi
0x180006047  push    rdi
0x180006048  push    r12
0x18000604a  push    r13
0x18000604c  push    r14
0x18000604e  push    r15
0x180006050  lea     rbp, [rsp-27h]
0x180006055  sub     rsp, 90h
0x18000605c  mov     r13, r8
0x18000605f  mov     [rbp+57h+var_78], r8
0x180006063  mov     r12, rdx
0x180006066  mov     r15, rcx
0x180006069  xor     r14d, r14d
0x18000606c  mov     [rbp+57h+var_58], r14
0x180006070  lea     rax, [rbp+57h+var_58]
0x180006074  mov     [rsp+0C0h+ppv], rax; ppv
0x180006079  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x180006080  xor     edx, edx; pUnkOuter
0x180006082  lea     r8d, [r14+15h]; dwClsContext
0x180006086  lea     rcx, _GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39; rclsid
0x18000608d  call    cs:__imp_CoCreateInstance
0x180006093  mov     [rbp+57h+var_60], r14
0x180006097  test    eax, eax
0x180006099  js      short loc_1800060BC
0x18000609b  mov     rcx, [rbp+57h+var_58]
0x18000609f  mov     rax, [rcx]
0x1800060a2  lea     r8, [rbp+57h+var_60]
0x1800060a6  lea     rdx, aSystemindex; "SystemIndex"
0x1800060ad  mov     rax, [rax+50h]
0x1800060b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b6  mov     edi, eax
0x1800060b8  test    eax, eax
0x1800060ba  jns     short loc_1800060C1
0x1800060bc  mov     edi, 80070422h
0x1800060c1  mov     [rbp+57h+var_80], r14
0x1800060c5  test    edi, edi
0x1800060c7  js      short loc_1800060E2
0x1800060c9  mov     rcx, [rbp+57h+var_60]
0x1800060cd  mov     rax, [rcx]
0x1800060d0  lea     rdx, [rbp+57h+var_80]
0x1800060d4  mov     rax, [rax+0E0h]
0x1800060db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e0  mov     edi, eax
0x1800060e2  mov     [rbp+57h+var_68], r14
0x1800060e6  test    edi, edi
0x1800060e8  js      short loc_180006100
0x1800060ea  mov     rcx, [rbp+57h+var_80]
0x1800060ee  mov     rax, [rcx]
0x1800060f1  lea     rdx, [rbp+57h+var_68]
0x1800060f5  mov     rax, [rax+30h]
0x1800060f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060fe  mov     edi, eax
0x180006100  mov     [rbp+57h+var_70], r14
0x180006104  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006108  test    edi, edi
0x18000610a  jnz     loc_1800062BB
0x180006110  or      r13, rcx
0x180006113  mov     rcx, [rbp+57h+var_68]
0x180006117  mov     rax, [rcx]
0x18000611a  xor     r9d, r9d
0x18000611d  lea     r8, [rbp+57h+var_70]
0x180006121  lea     edx, [r9+1]
0x180006125  mov     rax, [rax+18h]
0x180006129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000612e  mov     edi, eax
0x180006130  test    eax, eax
0x180006132  jnz     loc_1800062B3
0x180006138  mov     [rbp+57h+Str], r14
0x18000613c  mov     rcx, [rbp+57h+var_70]
0x180006140  mov     rax, [rcx]
0x180006143  lea     rdx, [rbp+57h+Str]
0x180006147  mov     rax, [rax+30h]
0x18000614b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006150  mov     edi, eax
0x180006152  mov     rsi, r14
0x180006155  mov     [rbp+57h+lpString2], r14
0x180006159  test    eax, eax
0x18000615b  js      loc_18000627E
0x180006161  mov     rax, [rbp+57h+Str]
0x180006165  mov     rbx, r13
0x180006168  inc     rbx
0x18000616b  cmp     [rax+rbx*2], r14w
0x180006170  jnz     short loc_180006168
0x180006172  mov     [rbp+57h+var_50], r14
0x180006176  mov     ecx, ebx
0x180006178  mov     eax, 2
0x18000617d  mul     rcx
0x180006180  test    rdx, rdx
0x180006183  jnz     loc_180006279
0x180006189  lea     r8, [rbp+57h+lpString2]; void **
0x18000618d  mov     rcx, rax; dwBytes
0x180006190  call    ?ProfNotif_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; ProfNotif_HeapAlloc(unsigned __int64,int,void * *,void *)
0x180006195  mov     edi, eax
0x180006197  mov     rsi, [rbp+57h+lpString2]
0x18000619b  test    eax, eax
0x18000619d  js      loc_18000627E
0x1800061a3  mov     r14, [rbp+57h+Str]
0x1800061a7  mov     rdi, rsi
0x1800061aa  xor     eax, eax
0x1800061ac  mov     [rsi], ax
0x1800061af  lea     rdx, SubStr; "://{"
0x1800061b6  mov     rcx, r14; Str
0x1800061b9  call    cs:__imp_wcsstr
0x1800061bf  mov     rdx, rax
0x1800061c2  test    rax, rax
0x1800061c5  jz      short loc_180006208
0x1800061c7  add     rdx, 8
0x1800061cb  movzx   eax, word ptr [rdx]
0x1800061ce  test    ax, ax
0x1800061d1  jz      short loc_1800061FF
0x1800061d3  mov     r8, rdx
0x1800061d6  cmp     ax, 7Dh ; '}'
0x1800061da  jz      short loc_1800061FF
0x1800061dc  mov     [rdi], ax
0x1800061df  add     rdi, 2
0x1800061e3  mov     rcx, r8
0x1800061e6  sub     rcx, r14
0x1800061e9  sar     rcx, 1
0x1800061ec  lea     eax, [rbx-1]
0x1800061ef  cmp     ecx, eax
0x1800061f1  jnb     short loc_1800061FF
0x1800061f3  add     rdx, 2
0x1800061f7  movzx   eax, word ptr [rdx]
0x1800061fa  test    ax, ax
0x1800061fd  jnz     short loc_1800061D6
0x1800061ff  xor     r14d, r14d
0x180006202  mov     [rdi], r14w
0x180006206  jmp     short loc_18000620B
0x180006208  xor     r14d, r14d
0x18000620b  mov     [rsp+0C0h+cchCount2], r13d; cchCount2
0x180006210  mov     [rsp+0C0h+ppv], rsi; lpString2
0x180006215  mov     r9d, r13d; cchCount1
0x180006218  mov     r8, r12; lpString1
0x18000621b  mov     edx, 1; dwCmpFlags
0x180006220  lea     ecx, [rdx+7Eh]; Locale
0x180006223  call    cs:__imp_CompareStringW
0x180006229  cmp     eax, 2
0x18000622c  jnz     short loc_180006274
0x18000622e  mov     rcx, [rbp+57h+var_80]
0x180006232  mov     rax, [rcx]
0x180006235  mov     rdx, [rbp+57h+Str]
0x180006239  mov     rax, [rax+28h]
0x18000623d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006242  mov     edi, eax
0x180006244  test    eax, eax
0x180006246  js      short loc_180006259
0x180006248  mov     rax, [r15]
0x18000624b  mov     rcx, r15
0x18000624e  mov     rax, [rax+10h]
0x180006252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006257  jmp     short loc_18000627E
0x180006259  cmp     edi, 80070422h
0x18000625f  jz      short loc_18000627E
0x180006261  mov     rax, [r15]
0x180006264  mov     edx, edi
0x180006266  mov     rcx, r15
0x180006269  mov     rax, [rax+18h]
0x18000626d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006272  jmp     short loc_18000627E
0x180006274  mov     edi, r14d
0x180006277  jmp     short loc_18000627E
0x180006279  mov     edi, 80070216h
0x18000627e  mov     rcx, rsi; lpMem
0x180006281  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x180006286  mov     rcx, [rbp+57h+Str]; pv
0x18000628a  call    cs:__imp_CoTaskMemFree
0x180006290  nop
0x180006291  mov     rcx, [rbp+57h+var_70]
0x180006295  test    rcx, rcx
0x180006298  jz      short loc_1800062AB
0x18000629a  mov     [rbp+57h+var_70], r14
0x18000629e  mov     rax, [rcx]
0x1800062a1  mov     rax, [rax+10h]
0x1800062a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062aa  nop
0x1800062ab  test    edi, edi
0x1800062ad  jz      loc_180006113
0x1800062b3  mov     r13, [rbp+57h+var_78]
0x1800062b7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800062bb  mov     ebx, r14d
0x1800062be  mov     r15d, 1
0x1800062c4  cmp     edi, r15d
0x1800062c7  cmovnz  ebx, edi
0x1800062ca  test    ebx, ebx
0x1800062cc  js      loc_180006541
0x1800062d2  movups  xmm0, xmmword ptr cs:aFile; "file:///"
0x1800062d9  movups  [rbp+57h+var_48], xmm0
0x1800062dd  movzx   eax, word ptr cs:aFile+10h; ""
0x1800062e4  mov     [rbp+57h+var_38], ax
0x1800062e8  mov     rsi, rcx
0x1800062eb  inc     rsi
0x1800062ee  cmp     [r13+rsi*2+0], r14w
0x1800062f4  jnz     short loc_1800062EB
0x1800062f6  add     rsi, 9
0x1800062fa  mov     r12d, 2
0x180006300  mov     eax, r12d
0x180006303  mul     rsi
0x180006306  cmovb   rax, rcx
0x18000630a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006311  mov     rcx, rax; unsigned __int64
0x180006314  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006319  mov     rdi, rax
0x18000631c  mov     [rbp+57h+var_50], rax
0x180006320  test    rax, rax
0x180006323  jz      loc_180006514
0x180006329  test    rsi, rsi
0x18000632c  jz      loc_180006504
0x180006332  cmp     rsi, 7FFFFFFFh
0x180006339  jbe     short loc_180006345
0x18000633b  mov     ebx, 80070057h
0x180006340  jmp     loc_18000650E
0x180006345  mov     eax, 7FFFFFFEh
0x18000634a  lea     rcx, [rbp+57h+var_48]
0x18000634e  mov     rdx, rsi
0x180006351  mov     r9, rdi
0x180006354  test    rax, rax
0x180006357  jz      short loc_180006375
0x180006359  movzx   r8d, word ptr [rcx]
0x18000635d  test    r8w, r8w
0x180006361  jz      short loc_180006375
0x180006363  add     rcx, r12
0x180006366  mov     [r9], r8w
0x18000636a  add     r9, r12
0x18000636d  sub     rax, r15
0x180006370  sub     rdx, r15
0x180006373  jnz     short loc_180006354
0x180006375  mov     rax, rdx
0x180006378  neg     rax
0x18000637b  sbb     ebx, ebx
0x18000637d  not     ebx
0x18000637f  and     ebx, 8007007Ah
0x180006385  lea     rcx, [r9-2]
0x180006389  test    rdx, rdx
0x18000638c  cmovnz  rcx, r9
0x180006390  mov     [rcx], r14w
0x180006394  jz      loc_180006519
0x18000639a  mov     r8, r13; wchar_t *
0x18000639d  mov     rdx, rsi; unsigned __int64
0x1800063a0  mov     rcx, rdi; wchar_t *
0x1800063a3  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800063a8  mov     ebx, eax
0x1800063aa  test    eax, eax
0x1800063ac  js      loc_180006519
0x1800063b2  mov     [rbp+57h+var_78], r14
0x1800063b6  mov     rcx, [rbp+57h+var_80]
0x1800063ba  mov     rax, [rcx]
0x1800063bd  lea     rdx, [rbp+57h+var_78]
0x1800063c1  mov     rax, [rax+50h]
0x1800063c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ca  mov     ebx, eax
0x1800063cc  test    eax, eax
0x1800063ce  jnz     loc_1800064E8
0x1800063d4  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800063d8  mov     rsi, r13
0x1800063db  inc     rsi
0x1800063de  cmp     [rdi+rsi*2], r14w
0x1800063e3  jnz     short loc_1800063DB
0x1800063e5  mov     [rbp+57h+Str], r14
0x1800063e9  mov     rcx, [rbp+57h+var_78]
0x1800063ed  mov     rax, [rcx]
0x1800063f0  xor     r9d, r9d
0x1800063f3  lea     r8, [rbp+57h+Str]
0x1800063f7  mov     edx, r15d
0x1800063fa  mov     rax, [rax+18h]
0x1800063fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006403  jmp     loc_1800064C4
0x180006408  mov     [rbp+57h+lpString2], r14
0x18000640c  mov     rcx, [rbp+57h+Str]
0x180006410  mov     rax, [rcx]
0x180006413  lea     rdx, [rbp+57h+lpString2]
0x180006417  mov     rax, [rax+18h]
0x18000641b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006420  test    eax, eax
0x180006422  js      short loc_18000646C
0x180006424  mov     rax, [rbp+57h+lpString2]
0x180006428  mov     [rsp+0C0h+cchCount2], esi; cchCount2
0x18000642c  mov     [rsp+0C0h+ppv], rax; lpString2
0x180006431  mov     r9d, r13d; cchCount1
0x180006434  mov     r8, rdi; lpString1
0x180006437  mov     edx, r15d; dwCmpFlags
0x18000643a  mov     ecx, 7Fh; Locale
0x18000643f  call    cs:__imp_CompareStringW
0x180006445  cmp     eax, r12d
0x180006448  jnz     short loc_180006461
0x18000644a  mov     rcx, [rbp+57h+var_80]
0x18000644e  mov     rax, [rcx]
0x180006451  mov     rdx, [rbp+57h+lpString2]
0x180006455  mov     rax, [rax+90h]
0x18000645c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006461  mov     rcx, [rbp+57h+lpString2]; pv
0x180006465  call    cs:__imp_CoTaskMemFree
0x18000646b  nop
0x18000646c  mov     rcx, [rbp+57h+Str]
0x180006470  test    rcx, rcx
0x180006473  jz      short loc_180006489
0x180006475  mov     [rbp+57h+Str], r14
0x180006479  mov     rax, [rcx]
0x18000647c  mov     rax, [rax+10h]
  ... truncated ...
```
