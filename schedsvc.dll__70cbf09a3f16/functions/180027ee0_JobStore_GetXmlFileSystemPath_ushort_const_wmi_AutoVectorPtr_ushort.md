# JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)

- ea: `0x180027ee0`
- end: `0x1800282ef`
- name: `?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `1039`
- prototype: `__int64 __fastcall(WCHAR **, unsigned __int16 *, LPVOID *)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002506c`
- `0x180026460`
- `0x1800265fc`
- `0x1800269f0`
- `0x180027c30`
- `0x180029978`
- `0x180051ed0`
- `0x180052274`
- `0x18006baac`
- `0x18006c5b8`
- `0x18006dd0c`

## callees

- `0x180027ee0`
- `0x18002ae80`
- `0x180056794`
- `0x18005790c`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027f9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027f9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027f1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027f1a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18002825d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18002825d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall JobStore::GetXmlFileSystemPath(WCHAR **a1, unsigned __int16 *a2, LPVOID *a3)
{
  _WORD *v6; // rbx
  __int64 v7; // r14
  const wchar_t *v8; // rdi
  __int64 v9; // rcx
  const wchar_t *v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rcx
  int v13; // edx
  __int64 v14; // rcx
  _WORD *v15; // rax
  __int64 v16; // rdx
  WCHAR *v17; // r9
  bool v18; // zf
  __int64 v19; // rax
  _WORD *v20; // rdx
  _WORD *v21; // rax
  unsigned __int16 v22; // ax
  __int64 v23; // rcx
  WCHAR *v24; // rdx
  __int64 v25; // r8
  WCHAR *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  WCHAR *v29; // rax
  WCHAR *v30; // rcx
  __int64 v31; // rbp
  WCHAR *v32; // rax
  void **pExceptionObject; // [rsp+30h] [rbp-298h] BYREF
  char v35; // [rsp+38h] [rbp-290h]
  const unsigned __int16 *v36; // [rsp+40h] [rbp-288h]
  __int64 v37; // [rsp+48h] [rbp-280h]
  __int64 v38; // [rsp+50h] [rbp-278h]
  int v39; // [rsp+58h] [rbp-270h]
  __int64 v40; // [rsp+5Ch] [rbp-26Ch]
  WCHAR pszPrefix[264]; // [rsp+70h] [rbp-258h] BYREF

  v6 = HeapAlloc(g_PrivateHeap, 0, 0x20Au);
  if ( !v6 )
  {
    v35 = 0;
    v39 = 14;
    v37 = 0;
    v36 = &qword_1800A4718;
    v38 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v40 = -1;
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( *a3 )
    HeapFree(g_PrivateHeap, 0, *a3);
  v7 = 2147483646;
  *a3 = v6;
  v8 = L"\\\\?\\";
  v9 = 2147483646;
  v10 = L"\\\\?\\";
  v11 = 261;
  while ( v9 && *v10 )
  {
    *v6++ = *v10++;
    --v9;
    if ( !--v11 )
    {
      *(v6 - 1) = 0;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 19;
LABEL_66:
        WPP_SF_Sd(v12[2], v13, (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, (_DWORD)a2, 161);
        return 2147942561LL;
      }
      return 2147942561LL;
    }
  }
  v14 = 261;
  *v6 = 0;
  v15 = *a3;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = 261 - v14;
  if ( !v14 )
    goto LABEL_62;
  v17 = *a1;
  v18 = v16 == 261;
  v19 = 2147483646;
  v20 = (char *)*a3 + 2 * v16;
  if ( !v18 )
  {
    do
    {
      if ( !v19 )
        break;
      if ( !*v17 )
        break;
      *v20++ = *v17++;
      --v19;
      --v14;
    }
    while ( v14 );
  }
  v21 = v20 - 1;
  if ( v14 )
    v21 = v20;
  *v21 = 0;
  if ( !v14 )
  {
LABEL_62:
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 20;
      goto LABEL_66;
    }
    return 2147942561LL;
  }
  if ( !a2 || (v22 = *a2) == 0 )
  {
LABEL_30:
    v23 = 2147483646;
    v24 = pszPrefix;
    v25 = 261;
    while ( v23 && *v8 )
    {
      *v24++ = *v8++;
      --v23;
      if ( !--v25 )
        goto LABEL_34;
    }
    *v24 = 0;
    v26 = pszPrefix;
    v27 = 261;
    do
    {
      if ( !*v26 )
        break;
      ++v26;
      --v27;
    }
    while ( v27 );
    v28 = 261 - v27;
    if ( v27 )
    {
      v29 = *a1;
      v30 = &pszPrefix[v28];
      v31 = 261 - v28;
      if ( 261 != v28 )
      {
        do
        {
          if ( !v7 )
            break;
          if ( !*v29 )
            break;
          *v30++ = *v29++;
          --v7;
          --v31;
        }
        while ( v31 );
      }
      v32 = v30 - 1;
      if ( v31 )
        v32 = v30;
      *v32 = 0;
      if ( v31 )
      {
        if ( PathIsPrefixW(pszPrefix, (LPCWSTR)*a3) )
          return 0;
      }
    }
LABEL_34:
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 23;
      goto LABEL_66;
    }
    return 2147942561LL;
  }
  if ( a2[1] )
  {
    if ( v22 == 92 )
      goto LABEL_44;
  }
  else if ( v22 == 92 )
  {
    goto LABEL_30;
  }
  if ( (int)StringCchCatW((unsigned __int16 *)*a3, 0x105u, L"\\") >= 0 )
  {
LABEL_44:
    if ( (int)StringCchCatW((unsigned __int16 *)*a3, 0x105u, a2) < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 22;
        goto LABEL_66;
      }
      return 2147942561LL;
    }
    goto LABEL_30;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 21;
    goto LABEL_66;
  }
  return 2147942561LL;
}

```

## disassembly

```asm
0x180027ee0  push    rbx
0x180027ee2  push    rsi
0x180027ee3  push    r12
0x180027ee5  push    r13
0x180027ee7  push    r15
0x180027ee9  sub     rsp, 2A0h
0x180027ef0  mov     rax, cs:__security_cookie
0x180027ef7  xor     rax, rsp
0x180027efa  mov     [rsp+2C8h+var_48], rax
0x180027f02  mov     r15, r8
0x180027f05  mov     r12, rdx
0x180027f08  mov     r13, rcx
0x180027f0b  xor     edx, edx; dwFlags
0x180027f0d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180027f14  mov     r8d, 20Ah; dwBytes
0x180027f1a  call    cs:__imp_HeapAlloc
0x180027f20  mov     rbx, rax
0x180027f23  test    rax, rax
0x180027f26  jnz     short loc_180027F73
0x180027f28  mov     [rsp+2C8h+var_290], al
0x180027f2c  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180027f33  xor     esi, esi
0x180027f35  mov     [rsp+2C8h+var_270], 0Eh
0x180027f3d  lea     rax, qword_1800A4718
0x180027f44  mov     [rsp+2C8h+var_280], rsi
0x180027f49  mov     [rsp+2C8h+var_288], rax
0x180027f4e  lea     rcx, [rsp+2C8h+pExceptionObject]; pExceptionObject
0x180027f53  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180027f5a  mov     [rsp+2C8h+var_278], rsi
0x180027f5f  mov     [rsp+2C8h+pExceptionObject], rax
0x180027f64  mov     [rsp+2C8h+var_26C], 0FFFFFFFFFFFFFFFFh
0x180027f6d  call    _CxxThrowException_0
0x180027f73  mov     r8, [r15]; lpMem
0x180027f76  mov     [rsp+2C8h+arg_0], rbp
0x180027f7e  mov     [rsp+2C8h+var_30], rdi
0x180027f86  mov     [rsp+2C8h+var_38], r14
0x180027f8e  test    r8, r8
0x180027f91  jz      short loc_180027FA2
0x180027f93  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180027f9a  xor     edx, edx; dwFlags
0x180027f9c  call    cs:__imp_HeapFree
0x180027fa2  mov     r14d, 7FFFFFFEh
0x180027fa8  mov     [r15], rbx
0x180027fab  lea     rdi, asc_1800A3E68; "\\\\?\\"
0x180027fb2  mov     ebp, 105h
0x180027fb7  mov     ecx, r14d
0x180027fba  mov     rdx, rdi
0x180027fbd  mov     r8d, ebp
0x180027fc0  test    rcx, rcx
0x180027fc3  jz      short loc_180028026
0x180027fc5  movzx   eax, word ptr [rdx]
0x180027fc8  test    ax, ax
0x180027fcb  jz      short loc_180027FE3
0x180027fcd  mov     [rbx], ax
0x180027fd0  add     rdx, 2
0x180027fd4  add     rbx, 2
0x180027fd8  dec     rcx
0x180027fdb  sub     r8, 1
0x180027fdf  jnz     short loc_180027FC0
0x180027fe1  jmp     short loc_180027FE8
0x180027fe3  test    r8, r8
0x180027fe6  jnz     short loc_180028026
0x180027fe8  xor     esi, esi
0x180027fea  mov     [rbx-2], si
0x180027fee  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ff5  lea     rax, WPP_GLOBAL_Control
0x180027ffc  cmp     rcx, rax
0x180027fff  jz      loc_1800282B2
0x180028005  test    dword ptr [rcx+1Ch], 40000h
0x18002800c  jz      loc_1800282B2
0x180028012  cmp     byte ptr [rcx+19h], 2
0x180028016  jb      loc_1800282B2
0x18002801c  mov     edx, 13h
0x180028021  jmp     loc_180028297
0x180028026  xor     esi, esi
0x180028028  mov     rcx, rbp
0x18002802b  mov     [rbx], si
0x18002802e  mov     r8, [r15]
0x180028031  mov     rax, r8
0x180028034  cmp     [rax], si
0x180028037  jz      short loc_180028043
0x180028039  add     rax, 2
0x18002803d  sub     rcx, 1
0x180028041  jnz     short loc_180028034
0x180028043  mov     rdx, rbp
0x180028046  sub     rdx, rcx
0x180028049  test    rcx, rcx
0x18002804c  cmovz   rdx, rsi
0x180028050  jz      loc_180028270
0x180028056  mov     r9, [r13+0]
0x18002805a  mov     rcx, rbp
0x18002805d  sub     rcx, rdx
0x180028060  mov     rax, r14
0x180028063  lea     rdx, [r8+rdx*2]
0x180028067  jz      short loc_180028094
0x180028069  nop     dword ptr [rax+00000000h]
0x180028070  test    rax, rax
0x180028073  jz      short loc_180028094
0x180028075  movzx   r8d, word ptr [r9]
0x180028079  test    r8w, r8w
0x18002807d  jz      short loc_180028094
0x18002807f  mov     [rdx], r8w
0x180028083  add     r9, 2
0x180028087  add     rdx, 2
0x18002808b  dec     rax
0x18002808e  sub     rcx, 1
0x180028092  jnz     short loc_180028070
0x180028094  test    rcx, rcx
0x180028097  lea     rax, [rdx-2]
0x18002809b  cmovnz  rax, rdx
0x18002809f  mov     [rax], si
0x1800280a2  jz      loc_180028270
0x1800280a8  test    r12, r12
0x1800280ab  jz      short loc_1800280C5
0x1800280ad  movzx   eax, word ptr [r12]
0x1800280b2  test    ax, ax
0x1800280b5  jz      short loc_1800280C5
0x1800280b7  cmp     [r12+2], si
0x1800280bd  jnz     short loc_180028131
0x1800280bf  cmp     ax, 5Ch ; '\'
0x1800280c3  jnz     short loc_180028137
0x1800280c5  mov     rcx, r14
0x1800280c8  lea     rdx, [rsp+2C8h+pszPrefix]
0x1800280cd  mov     r8, rbp
0x1800280d0  test    rcx, rcx
0x1800280d3  jz      loc_1800281DC
0x1800280d9  movzx   eax, word ptr [rdi]
0x1800280dc  test    ax, ax
0x1800280df  jz      loc_1800281D3
0x1800280e5  mov     [rdx], ax
0x1800280e8  add     rdi, 2
0x1800280ec  add     rdx, 2
0x1800280f0  dec     rcx
0x1800280f3  sub     r8, 1
0x1800280f7  jnz     short loc_1800280D0
0x1800280f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180028100  lea     rax, WPP_GLOBAL_Control
0x180028107  cmp     rcx, rax
0x18002810a  jz      loc_1800282B2
0x180028110  test    dword ptr [rcx+1Ch], 40000h
0x180028117  jz      loc_1800282B2
0x18002811d  cmp     byte ptr [rcx+19h], 2
0x180028121  jb      loc_1800282B2
0x180028127  mov     edx, 17h
0x18002812c  jmp     loc_180028297
0x180028131  cmp     ax, 5Ch ; '\'
0x180028135  jz      short loc_180028185
0x180028137  mov     rcx, [r15]; unsigned __int16 *
0x18002813a  lea     r8, asc_1800A3DA8; "\\"
0x180028141  mov     rdx, rbp; unsigned __int64
0x180028144  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028149  test    eax, eax
0x18002814b  jns     short loc_180028185
0x18002814d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028154  lea     rax, WPP_GLOBAL_Control
0x18002815b  cmp     rcx, rax
0x18002815e  jz      loc_1800282B2
0x180028164  test    dword ptr [rcx+1Ch], 40000h
0x18002816b  jz      loc_1800282B2
0x180028171  cmp     byte ptr [rcx+19h], 2
0x180028175  jb      loc_1800282B2
0x18002817b  mov     edx, 15h
0x180028180  jmp     loc_180028297
0x180028185  mov     rcx, [r15]; unsigned __int16 *
0x180028188  mov     r8, r12; unsigned __int16 *
0x18002818b  mov     rdx, rbp; unsigned __int64
0x18002818e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028193  test    eax, eax
0x180028195  jns     loc_1800280C5
0x18002819b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281a2  lea     rax, WPP_GLOBAL_Control
0x1800281a9  cmp     rcx, rax
0x1800281ac  jz      loc_1800282B2
0x1800281b2  test    dword ptr [rcx+1Ch], 40000h
0x1800281b9  jz      loc_1800282B2
0x1800281bf  cmp     byte ptr [rcx+19h], 2
0x1800281c3  jb      loc_1800282B2
0x1800281c9  mov     edx, 16h
0x1800281ce  jmp     loc_180028297
0x1800281d3  test    r8, r8
0x1800281d6  jz      loc_1800280F9
0x1800281dc  mov     [rdx], si
0x1800281df  lea     rax, [rsp+2C8h+pszPrefix]
0x1800281e4  mov     rcx, rbp
0x1800281e7  cmp     [rax], si
0x1800281ea  jz      short loc_1800281F6
0x1800281ec  add     rax, 2
0x1800281f0  sub     rcx, 1
0x1800281f4  jnz     short loc_1800281E7
0x1800281f6  mov     rdx, rbp
0x1800281f9  sub     rdx, rcx
0x1800281fc  test    rcx, rcx
0x1800281ff  cmovz   rdx, rsi
0x180028203  jz      loc_1800280F9
0x180028209  mov     rax, [r13+0]
0x18002820d  lea     rcx, [rsp+2C8h+pszPrefix]
0x180028212  lea     rcx, [rcx+rdx*2]
0x180028216  sub     rbp, rdx
0x180028219  jz      short loc_180028241
0x18002821b  nop     dword ptr [rax+rax+00h]
0x180028220  test    r14, r14
0x180028223  jz      short loc_180028241
0x180028225  movzx   edx, word ptr [rax]
0x180028228  test    dx, dx
0x18002822b  jz      short loc_180028241
0x18002822d  mov     [rcx], dx
0x180028230  add     rax, 2
0x180028234  add     rcx, 2
0x180028238  dec     r14
0x18002823b  sub     rbp, 1
0x18002823f  jnz     short loc_180028220
0x180028241  test    rbp, rbp
0x180028244  lea     rax, [rcx-2]
0x180028248  cmovnz  rax, rcx
0x18002824c  mov     [rax], si
0x18002824f  jz      loc_1800280F9
0x180028255  mov     rdx, [r15]; pszPath
0x180028258  lea     rcx, [rsp+2C8h+pszPrefix]; pszPrefix
0x18002825d  call    cs:__imp_PathIsPrefixW
0x180028263  cmp     eax, 1
0x180028266  jnz     loc_1800280F9
0x18002826c  xor     eax, eax
0x18002826e  jmp     short loc_1800282B7
0x180028270  mov     rcx, cs:WPP_GLOBAL_Control
0x180028277  lea     rax, WPP_GLOBAL_Control
0x18002827e  cmp     rcx, rax
0x180028281  jz      short loc_1800282B2
0x180028283  test    dword ptr [rcx+1Ch], 40000h
0x18002828a  jz      short loc_1800282B2
0x18002828c  cmp     byte ptr [rcx+19h], 2
0x180028290  jb      short loc_1800282B2
0x180028292  mov     edx, 14h
0x180028297  mov     rcx, [rcx+10h]
0x18002829b  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x1800282a2  mov     r9, r12
0x1800282a5  mov     [rsp+2C8h+var_2A8], 800700A1h
0x1800282ad  call    WPP_SF_Sd
0x1800282b2  mov     eax, 800700A1h
0x1800282b7  mov     rdi, [rsp+2C8h+var_30]
0x1800282bf  mov     rbp, [rsp+2C8h+arg_0]
0x1800282c7  mov     r14, [rsp+2C8h+var_38]
0x1800282cf  mov     rcx, [rsp+2C8h+var_48]
0x1800282d7  xor     rcx, rsp; StackCookie
0x1800282da  call    __security_check_cookie
0x1800282df  add     rsp, 2A0h
0x1800282e6  pop     r15
0x1800282e8  pop     r13
0x1800282ea  pop     r12
0x1800282ec  pop     rsi
0x1800282ed  pop     rbx
0x1800282ee  retn
```
