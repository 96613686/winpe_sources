# ServerXMLUpdateHandler::WriteURI(Schema const &,ITaskXmlHandler::Data const *)

- ea: `0x180035250`
- end: `0x180035834`
- name: `?WriteURI@ServerXMLUpdateHandler@@AEAAXAEBUSchema@@PEBUData@ITaskXmlHandler@@@Z`
- size: `1508`
- prototype: `void __fastcall(ServerXMLUpdateHandler *__hidden this, const struct Schema *, const struct ITaskXmlHandler::Data *)`
- caller_count: `3`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800351d0`
- `0x180041640`
- `0x180082618`

## callees

- `0x180020110`
- `0x180035250`
- `0x180035cf8`
- `0x180054824`
- `0x180056c00`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180035808`
- `OLEAUT32!__imp_SysFreeString` at `0x180035808`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180035392`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180035392`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035500`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035500`
- `RPCRT4!UuidCreate` at `0x18003572f`
- `RPCRT4!UuidCreate` at `0x18003572f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003575b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003575b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServerXMLUpdateHandler::WriteURI(
        ServerXMLUpdateHandler *this,
        const struct Schema *a2,
        const struct ITaskXmlHandler::Data *a3)
{
  const unsigned __int16 *v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r10
  unsigned __int16 v9; // r11
  int i; // ecx
  int v11; // r9d
  bool v12; // zf
  unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  unsigned __int64 v16; // rdx
  unsigned int *v17; // rbx
  unsigned int v18; // eax
  const struct SchemaEntry * near *v19; // r8
  __int64 v20; // rcx
  int v21; // eax
  int v22; // ecx
  __int64 v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r9
  const OLECHAR *v27; // rax
  __int64 v28; // rbx
  OLECHAR *v29; // r11
  OLECHAR v30; // cx
  __int64 v31; // rcx
  _WORD *v32; // rax
  __int64 v33; // rdx
  unsigned __int16 *v34; // rax
  unsigned __int16 v35; // cx
  unsigned __int64 v36; // r9
  __int64 v37; // rax
  OLECHAR v38; // r8
  const OLECHAR *v39; // rax
  OLECHAR *v40; // rcx
  int v41; // eax
  unsigned __int16 *v42; // rdx
  char v43[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h]
  int v46; // [rsp+48h] [rbp-B8h]
  __int16 v47; // [rsp+4Ch] [rbp-B4h]
  int *v48; // [rsp+60h] [rbp-A0h]
  LPVOID lpMem; // [rsp+68h] [rbp-98h]
  UUID Uuid; // [rsp+80h] [rbp-80h] BYREF
  int v51; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h]
  __int16 v53; // [rsp+A0h] [rbp-60h]
  char v54; // [rsp+4A2h] [rbp+3A2h]
  OLECHAR sz[8]; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int128 v56; // [rsp+4C0h] [rbp+3C0h]
  __int128 v57; // [rsp+4D0h] [rbp+3D0h]
  __int128 v58; // [rsp+4E0h] [rbp+3E0h]
  __int128 v59; // [rsp+4F0h] [rbp+3F0h]
  _WORD v60[264]; // [rsp+500h] [rbp+400h] BYREF

  Uuid = 0;
  *(_OWORD *)sz = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  memset_0(v60, 0, 0x20Au);
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 101);
  if ( !v6 || (v6 = *(const unsigned __int16 **)v6) == 0 )
  {
    if ( a3 )
    {
      v42 = *(unsigned __int16 **)(*((_QWORD *)a3 + 6) + 8LL);
    }
    else
    {
      v41 = UuidCreate(&Uuid);
      if ( v41 && v41 != 1824 )
      {
        if ( v41 > 0 )
          v41 = (unsigned __int16)v41 | 0x80070000;
        ServerXMLUpdateHandler::UpdateHR(this, v41);
        return;
      }
      if ( !StringFromGUID2(&Uuid, sz, 40) )
      {
        ServerXMLUpdateHandler::UpdateHR(this, -2147024774);
        return;
      }
      v42 = sz;
    }
    tsched::TaskPathCanonicalize((tsched *)v60, v42, v6);
    goto LABEL_15;
  }
  v7 = 261;
  v8 = 2147483646;
  if ( !*v6 )
  {
    v39 = L"\\";
    v40 = v60;
    do
    {
      if ( !v8 )
        goto LABEL_69;
      v38 = *v39;
      if ( !*v39 )
        goto LABEL_69;
      ++v39;
      *v40++ = v38;
      --v8;
      --v7;
    }
    while ( v7 );
    --v40;
LABEL_69:
    *v40 = 0;
    goto LABEL_15;
  }
  if ( *v6 == 92 )
    goto LABEL_5;
  v26 = 2147483646;
  v27 = L"\\";
  v28 = 261;
  v29 = v60;
  do
  {
    if ( !v26 || (v30 = *v27) == 0 )
    {
      *v29 = 0;
LABEL_5:
      v9 = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= 261 )
          goto LABEL_15;
        v11 = v6[i];
        if ( !(_WORD)v11 )
        {
          if ( v9 != 92 || i <= 1 )
          {
            v31 = 261;
            v32 = v60;
            do
            {
              if ( !*v32 )
                break;
              ++v32;
              --v31;
            }
            while ( v31 );
            if ( v31 )
            {
              v33 = v31;
              v34 = &v60[261 - v31];
              do
              {
                if ( !v8 )
                  break;
                v35 = *v6;
                if ( !*v6 )
                  break;
                ++v6;
                *v34++ = v35;
                --v8;
                --v33;
              }
              while ( v33 );
              v13 = v34 - 1;
              if ( v33 )
                v13 = v34;
              *v13 = 0;
            }
          }
          goto LABEL_15;
        }
        if ( v11 == 92 )
          break;
        if ( v11 == 32 )
        {
          if ( v9 == 92 )
            goto LABEL_15;
          v12 = v9 == 0;
          goto LABEL_10;
        }
        if ( v11 != 46 )
        {
          if ( v11 == 47 )
            goto LABEL_15;
          v12 = v11 == 58;
          goto LABEL_10;
        }
        if ( v9 == 46 || v9 == 92 && v6[i + 1] == 92 )
          goto LABEL_15;
LABEL_11:
        v9 = v6[i];
      }
      v12 = v9 == 92;
LABEL_10:
      if ( v12 )
        goto LABEL_15;
      goto LABEL_11;
    }
    ++v27;
    *v29++ = v30;
    --v26;
    --v28;
  }
  while ( v28 );
  *(v29 - 1) = 0;
LABEL_15:
  v54 &= 0xFCu;
  v53 = 0;
  v14 = -1;
  do
    ++v14;
  while ( v60[v14] );
  v51 = v14;
  bstrString = v60;
  v43[0] = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  lpMem = 0;
  v48 = &v51;
  v15 = TriggersXmlHandler::ProcessValue(this, a2, 4, v43, 0);
  if ( v15 < 0 && *((int *)this + 268) >= 0 )
    *((_DWORD *)this + 268) = v15;
  v17 = (unsigned int *)*((_QWORD *)this + 131);
  v18 = v17[38];
  if ( v18 )
  {
    v17[38] = v18 + 1;
    goto LABEL_32;
  }
  v16 = *v17;
  if ( (_DWORD)v16 == 65542 )
  {
LABEL_20:
    v19 = (&Schema::schemaEntries)[(unsigned __int16)v16] + 64;
  }
  else
  {
    switch ( (int)v16 )
    {
      case 65536:
      case 65537:
        v36 = 0;
        v37 = (unsigned __int16)v16;
        v16 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v16];
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_20;
      default:
        goto LABEL_92;
    }
    while ( v36 < v16 )
    {
      v19 = &(&Schema::schemaEntries)[v37][16 * v36];
      if ( *(_DWORD *)v19 == 4 )
        goto LABEL_22;
      ++v36;
    }
LABEL_92:
    v19 = (const struct SchemaEntry * near *)&qword_1800A1560;
  }
  if ( *(_DWORD *)v19 )
  {
LABEL_22:
    v20 = *((_QWORD *)v17 + 2);
    if ( !v20 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v16);
    v21 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, const struct SchemaEntry *, unsigned __int16 *const))(*(_QWORD *)v20 + 216LL))(
            v20,
            &ChannelPath,
            v19[1],
            Schema::namespaceUri);
    v22 = v21;
    if ( v21 >= 0 )
    {
      if ( v21 )
        goto LABEL_32;
      v23 = *((_QWORD *)v17 + 2);
      if ( !v23 )
        _com_raise_error(-2147467261, (struct IErrorInfo *)v16);
      v22 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v23 + 224LL))(v23, v60);
      if ( v22 >= 0 )
      {
LABEL_32:
        v22 = 1;
        goto LABEL_33;
      }
    }
    goto LABEL_24;
  }
  v22 = 1;
  v17[38] = 1;
LABEL_33:
  v24 = v17[38];
  if ( v24 )
  {
    v17[38] = v24 - 1;
  }
  else
  {
    v25 = *((_QWORD *)v17 + 2);
    if ( !v25 )
      _com_raise_error(-2147467261, (struct IErrorInfo *)v16);
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 120LL))(v25);
  }
  if ( v22 < 0 )
  {
LABEL_24:
    if ( *((int *)this + 268) >= 0 )
      *((_DWORD *)this + 268) = v22;
  }
  if ( lpMem )
    HeapFree(g_PrivateHeap, 0, lpMem);
  if ( (v54 & 1) != 0 )
    SysFreeString(bstrString);
}

```

## disassembly

```asm
0x180035250  push    rbp
0x180035252  push    rbx
0x180035253  push    rsi
0x180035254  push    rdi
0x180035255  push    r14
0x180035257  lea     rbp, [rsp-620h]
0x18003525f  sub     rsp, 720h
0x180035266  mov     rax, cs:__security_cookie
0x18003526d  xor     rax, rsp
0x180035270  mov     [rbp+640h+var_30], rax
0x180035277  mov     rbx, r8
0x18003527a  mov     r14, rdx
0x18003527d  mov     rsi, rcx
0x180035280  xorps   xmm0, xmm0
0x180035283  movups  xmmword ptr [rbp+640h+Uuid.Data1], xmm0
0x180035287  xorps   xmm1, xmm1
0x18003528a  movups  xmmword ptr [rbp+640h+sz], xmm1
0x180035291  movups  [rbp+640h+var_280], xmm1
0x180035298  movups  [rbp+640h+var_270], xmm1
0x18003529f  movups  [rbp+640h+var_260], xmm1
0x1800352a6  movups  [rbp+640h+var_250], xmm1
0x1800352ad  xor     edx, edx; Val
0x1800352af  mov     r8d, 20Ah; Size
0x1800352b5  lea     rcx, [rbp+640h+var_240]; void *
0x1800352bc  call    memset_0
0x1800352c1  mov     r8, [rsi+328h]
0x1800352c8  test    r8, r8
0x1800352cb  jz      loc_18003571C
0x1800352d1  mov     r8, [r8]
0x1800352d4  test    r8, r8
0x1800352d7  jz      loc_18003571C
0x1800352dd  movzx   eax, word ptr [r8]
0x1800352e1  mov     edx, 105h
0x1800352e6  mov     r10d, 7FFFFFFEh
0x1800352ec  test    ax, ax
0x1800352ef  jz      loc_180035709
0x1800352f5  cmp     ax, 5Ch ; '\'
0x1800352f9  jnz     loc_180035552
0x1800352ff  xor     r11d, r11d
0x180035302  xor     ecx, ecx
0x180035304  cmp     ecx, edx
0x180035306  jge     short loc_180035345
0x180035308  movsxd  rdi, ecx
0x18003530b  movzx   r9d, word ptr [r8+rdi*2]
0x180035310  test    r9w, r9w
0x180035314  jz      loc_1800355A4
0x18003531a  mov     ebx, r9d
0x18003531d  cmp     r9d, 5Ch ; '\'
0x180035321  jnz     loc_18003546F
0x180035327  cmp     r11w, r9w
0x18003532b  jz      short loc_180035345
0x18003532d  movzx   r11d, r9w
0x180035331  inc     ecx
0x180035333  jmp     short loc_180035304
0x180035335  lea     rcx, [rax-2]
0x180035339  test    rdx, rdx
0x18003533c  cmovnz  rcx, rax
0x180035340  xor     eax, eax
0x180035342  mov     [rcx], ax
0x180035345  movzx   eax, [rbp+640h+var_29E]
0x18003534c  and     al, 0FCh
0x18003534e  and     al, 0FCh
0x180035350  mov     [rbp+640h+var_29E], al
0x180035356  xor     eax, eax
0x180035358  mov     [rbp+640h+var_6A0], ax
0x18003535c  lea     rcx, [rbp+640h+var_240]
0x180035363  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003536a  nop     word ptr [rax+rax+00h]
0x180035370  inc     rax
0x180035373  cmp     word ptr [rcx+rax*2], 0
0x180035378  jnz     short loc_180035370
0x18003537a  mov     [rbp+640h+var_6B0], eax
0x18003537d  lea     rax, [rbp+640h+var_240]
0x180035384  mov     [rbp+640h+bstrString], rax
0x180035388  mov     [rsp+740h+var_710], 0
0x18003538d  lea     rcx, [rsp+740h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180035392  call    cs:__imp_GetSystemTimeAsFileTime
0x180035399  nop     dword ptr [rax+rax+00h]
0x18003539e  xor     eax, eax
0x1800353a0  mov     [rsp+740h+var_700], rax
0x1800353a5  mov     [rsp+740h+var_6F8], eax
0x1800353a9  mov     [rsp+740h+var_6F4], ax
0x1800353ae  mov     [rsp+740h+lpMem], rax
0x1800353b3  lea     rax, [rbp+640h+var_6B0]
0x1800353b7  mov     [rsp+740h+var_6E0], rax
0x1800353bc  mov     [rsp+740h+var_720], 0
0x1800353c1  lea     r9, [rsp+740h+var_710]
0x1800353c6  mov     r8d, 4
0x1800353cc  mov     rdx, r14
0x1800353cf  mov     rcx, rsi
0x1800353d2  call    ?ProcessValue@TriggersXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z; TriggersXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)
0x1800353d7  test    eax, eax
0x1800353d9  js      loc_180035795
0x1800353df  mov     rbx, [rsi+418h]
0x1800353e6  mov     eax, [rbx+98h]
0x1800353ec  test    eax, eax
0x1800353ee  jnz     loc_1800357AD
0x1800353f4  mov     edx, [rbx]; struct IErrorInfo *
0x1800353f6  lea     r8, __ImageBase
0x1800353fd  cmp     edx, 10006h
0x180035403  jnz     loc_180035621
0x180035409  movzx   eax, dx; jumptable 000000018003563D cases 65538-65541
0x18003540c  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180035414  add     r8, 200h
0x18003541b  mov     eax, [r8]
0x18003541e  test    eax, eax
0x180035420  jz      loc_1800357C6
0x180035426  mov     rcx, [rbx+10h]
0x18003542a  test    rcx, rcx
0x18003542d  jz      loc_1800357D6
0x180035433  mov     rax, [rcx]
0x180035436  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x18003543d  mov     r8, [r8+8]
0x180035441  lea     rdx, ChannelPath
0x180035448  mov     rax, [rax+0D8h]
0x18003544f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035454  mov     ecx, eax
0x180035456  test    eax, eax
0x180035458  jns     short loc_18003548C
0x18003545a  cmp     dword ptr [rsi+430h], 0
0x180035461  jl      loc_1800354ED
0x180035467  mov     [rsi+430h], ecx
0x18003546d  jmp     short loc_1800354ED
0x18003546f  sub     ebx, 20h ; ' '
0x180035472  jnz     loc_180035538
0x180035478  cmp     r11w, 5Ch ; '\'
0x18003547d  jz      loc_180035345
0x180035483  test    r11w, r11w
0x180035487  jmp     loc_18003532B
0x18003548c  jnz     short loc_1800354B7
0x18003548e  mov     rcx, [rbx+10h]
0x180035492  test    rcx, rcx
0x180035495  jz      loc_1800357E1
0x18003549b  mov     rax, [rcx]
0x18003549e  lea     rdx, [rbp+640h+var_240]
0x1800354a5  mov     rax, [rax+0E0h]
0x1800354ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354b1  mov     ecx, eax
0x1800354b3  test    eax, eax
0x1800354b5  js      short loc_18003545A
0x1800354b7  mov     ecx, 1
0x1800354bc  mov     eax, [rbx+98h]
0x1800354c2  test    eax, eax
0x1800354c4  jnz     loc_1800357EC
0x1800354ca  mov     rcx, [rbx+10h]
0x1800354ce  test    rcx, rcx
0x1800354d1  jz      loc_1800357F9
0x1800354d7  mov     rax, [rcx]
0x1800354da  mov     rax, [rax+78h]
0x1800354de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354e3  mov     ecx, eax
0x1800354e5  test    ecx, ecx
0x1800354e7  js      loc_18003545A
0x1800354ed  mov     r8, [rsp+740h+lpMem]; lpMem
0x1800354f2  test    r8, r8
0x1800354f5  jz      short loc_18003550D
0x1800354f7  xor     edx, edx; dwFlags
0x1800354f9  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180035500  call    cs:__imp_HeapFree
0x180035507  nop     dword ptr [rax+rax+00h]
0x18003550c  nop
0x18003550d  test    [rbp+640h+var_29E], 1
0x180035514  jnz     loc_180035804
0x18003551a  mov     rcx, [rbp+640h+var_30]
0x180035521  xor     rcx, rsp; StackCookie
0x180035524  call    __security_check_cookie
0x180035529  add     rsp, 720h
0x180035530  pop     r14
0x180035532  pop     rdi
0x180035533  pop     rsi
0x180035534  pop     rbx
0x180035535  pop     rbp
0x180035536  retn
0x180035538  sub     ebx, 0Eh
0x18003553b  jz      loc_1800356D4
0x180035541  sub     ebx, 1
0x180035544  jz      loc_180035345
0x18003554a  cmp     ebx, 0Bh
0x18003554d  jmp     loc_18003532B
0x180035552  mov     r9, r10
0x180035555  lea     rax, asc_1800A7EC0; "\\"
0x18003555c  mov     rbx, rdx
0x18003555f  lea     r11, [rbp+640h+var_240]
0x180035566  test    r9, r9
0x180035569  jz      short loc_180035599
0x18003556b  movzx   ecx, word ptr [rax]
0x18003556e  test    cx, cx
0x180035571  jz      short loc_180035594
0x180035573  add     rax, 2
0x180035577  mov     [r11], cx
0x18003557b  add     r11, 2
0x18003557f  dec     r9
0x180035582  sub     rbx, 1
0x180035586  jnz     short loc_180035566
0x180035588  xor     eax, eax
0x18003558a  mov     [r11-2], ax
0x18003558f  jmp     loc_180035345
0x180035594  test    rbx, rbx
0x180035597  jz      short loc_180035588
0x180035599  xor     eax, eax
0x18003559b  mov     [r11], ax
0x18003559f  jmp     loc_1800352FF
0x1800355a4  cmp     r11w, 5Ch ; '\'
0x1800355a9  jz      loc_1800356FB
0x1800355af  mov     rcx, rdx
0x1800355b2  lea     rax, [rbp+640h+var_240]
0x1800355b9  cmp     word ptr [rax], 0
0x1800355bd  jz      short loc_1800355C9
0x1800355bf  add     rax, 2
0x1800355c3  sub     rcx, 1
0x1800355c7  jnz     short loc_1800355B9
0x1800355c9  mov     r9, rdx
0x1800355cc  sub     r9, rcx
0x1800355cf  xor     eax, eax
0x1800355d1  test    rcx, rcx
0x1800355d4  cmovz   r9, rax
0x1800355d8  jz      loc_180035345
0x1800355de  sub     rdx, r9
0x1800355e1  lea     rax, [rbp+640h+var_240]
0x1800355e8  lea     rax, [rax+r9*2]
0x1800355ec  jz      loc_180035335
0x1800355f2  test    r10, r10
0x1800355f5  jz      loc_180035335
0x1800355fb  movzx   ecx, word ptr [r8]
0x1800355ff  test    cx, cx
0x180035602  jz      loc_180035335
0x180035608  add     r8, 2
0x18003560c  mov     [rax], cx
0x18003560f  add     rax, 2
0x180035613  dec     r10
0x180035616  sub     rdx, 1
0x18003561a  jnz     short loc_1800355F2
0x18003561c  jmp     loc_180035335
0x180035621  lea     eax, [rdx-10000h]; switch 6 cases
0x180035627  cmp     eax, 5
0x18003562a  ja      def_18003563D; jumptable 000000018003563D default case
0x180035630  cdqe
0x180035632  mov     ecx, ds:(jpt_18003563D - 180000000h)[r8+rax*4]
0x18003563a  add     rcx, r8
0x18003563d  jmp     rcx; switch jump
0x180035643  xor     r9d, r9d; jumptable 000000018003563D cases 65536,65537
0x180035646  movzx   eax, dx
0x180035649  mov     rdx, ds:rva ?schemaEntriesCount@Schema@@0QB_KB[r8+rax*8]; unsigned __int64 const near * const Schema::schemaEntriesCount ...
0x180035651  lea     r10, rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r8]; SchemaEntry const * near * Schema::schemaEntries ...
0x180035658  lea     r10, [r10+rax*8]
0x18003565c  cmp     r9, rdx
0x18003565f  jnb     def_18003563D; jumptable 000000018003563D default case
0x180035665  mov     r8, r9
0x180035668  shl     r8, 7
0x18003566c  add     r8, [r10]
0x18003566f  cmp     dword ptr [r8], 4
0x180035673  jz      loc_180035426
0x180035679  inc     r9
0x18003567c  jmp     short loc_18003565C
0x180035680  test    r10, r10
0x180035683  jz      short loc_1800356A8
0x180035685  movzx   r8d, word ptr [rax]
0x180035689  test    r8w, r8w
0x18003568d  jz      short loc_1800356B2
0x18003568f  add     rax, 2
0x180035693  mov     [rcx], r8w
0x180035697  add     rcx, 2
0x18003569b  dec     r10
0x18003569e  sub     rdx, 1
0x1800356a2  jnz     short loc_180035680
0x1800356a4  sub     rcx, 2
0x1800356a8  xor     eax, eax
0x1800356aa  mov     [rcx], ax
0x1800356ad  jmp     loc_180035345
0x1800356b2  test    rdx, rdx
0x1800356b5  jnz     short loc_1800356A8
0x1800356b7  jmp     short loc_1800356A4
0x1800356b9  test    eax, eax
0x1800356bb  jle     short loc_1800356C5
0x1800356bd  movzx   eax, ax
0x1800356c0  or      eax, 80070000h
0x1800356c5  mov     edx, eax; int
0x1800356c7  mov     rcx, rsi; this
0x1800356ca  call    ?UpdateHR@ServerXMLUpdateHandler@@AEAAXJ@Z; ServerXMLUpdateHandler::UpdateHR(long)
0x1800356cf  jmp     loc_18003551A
0x1800356d4  cmp     r11w, 2Eh ; '.'
0x1800356d9  jz      loc_180035345
0x1800356df  cmp     r11w, 5Ch ; '\'
0x1800356e4  jnz     loc_18003532D
0x1800356ea  cmp     [r8+rdi*2+2], r11w
0x1800356f0  jz      loc_180035345
0x1800356f6  jmp     loc_18003532D
0x1800356fb  cmp     ecx, 1
0x1800356fe  jle     loc_1800355AF
0x180035704  jmp     loc_180035345
0x180035709  lea     rax, asc_1800A7EC0; "\\"
0x180035710  lea     rcx, [rbp+640h+var_240]
0x180035717  jmp     loc_180035680
0x18003571c  test    rbx, rbx
0x18003571f  jz      short loc_18003572B
0x180035721  mov     rdx, [rbx+30h]
0x180035725  mov     rdx, [rdx+8]
0x180035729  jmp     short loc_180035784
0x18003572b  lea     rcx, [rbp+640h+Uuid]; Uuid
0x18003572f  call    cs:__imp_UuidCreate
  ... truncated ...
```
