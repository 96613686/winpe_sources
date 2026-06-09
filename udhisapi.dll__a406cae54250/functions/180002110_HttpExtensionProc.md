# HttpExtensionProc

- ea: `0x180002110`
- end: `0x180002486`
- name: `HttpExtensionProc`
- size: `886`
- prototype: `DWORD __stdcall(EXTENSION_CONTROL_BLOCK *pECB)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001400`
- `0x180001c96`
- `0x180002110`
- `0x18000249c`
- `0x1800024c4`
- `0x180002504`
- `0x1800025e8`
- `0x1800026a4`
- `0x180002af0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180002270`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180002270`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000247b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000247b`
- `WS2_32!__imp_WSAStartup` at `0x1800023eb`
- `WS2_32!__imp_WSAStartup` at `0x1800023eb`
- `WS2_32!__imp_WSACleanup` at `0x180002400`
- `WS2_32!__imp_WSACleanup` at `0x180002400`

## pseudocode

```c
DWORD __stdcall HttpExtensionProc(EXTENSION_CONTROL_BLOCK *pECB)
{
  HCONN ConnID; // rcx
  DWORD v3; // r14d
  _QWORD *v4; // r10
  const char *lpszQueryString; // r15
  __int64 v6; // rdx
  LPSTR v7; // rax
  unsigned __int64 v8; // rdi
  int v9; // esi
  const char *v10; // rdx
  __int64 v11; // r8
  char *v12; // rax
  unsigned int v14; // ebp
  unsigned int Header; // eax
  void *v16; // rdi
  void (__fastcall *v17)(EXTENSION_CONTROL_BLOCK *); // rsi
  int v18; // ecx
  unsigned int v19; // eax
  int v20; // [rsp+30h] [rbp-1E8h] BYREF
  void *Block; // [rsp+38h] [rbp-1E0h] BYREF
  WSAData WSAData; // [rsp+40h] [rbp-1D8h] BYREF

  Block = 0;
  ConnID = pECB->ConnID;
  v20 = 0;
  ((void (__fastcall *)(HCONN, __int64, int *, _QWORD, _QWORD))pECB->ServerSupportFunction)(ConnID, 1008, &v20, 0, 0);
  v3 = (v20 != 0) + 1;
  if ( !_InterlockedCompareExchange(&dword_180012180, 1, 0) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      goto LABEL_6;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids);
  }
  v4 = WPP_GLOBAL_Control;
LABEL_6:
  lpszQueryString = pECB->lpszQueryString;
  if ( !lpszQueryString )
    goto LABEL_22;
  v6 = 0x7FFFFFFF;
  v7 = pECB->lpszQueryString;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( v6 )
  {
    v9 = 0;
    while ( 1 )
    {
      if ( LODWORD((&off_18000D000)[3 * v9 + 1]) == 3 )
        goto LABEL_21;
      v10 = (&off_18000D000)[3 * v9];
      if ( v10 )
      {
        v11 = 0x7FFFFFFF;
        v12 = (&off_18000D000)[3 * v9];
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        if ( v11
          && v8 >= ((0x7FFFFFFF - v11) & (unsigned __int64)-(__int64)(v11 != 0))
          && !_strnicmp(lpszQueryString, v10, (0x7FFFFFFF - v11) & -(__int64)(v11 != 0)) )
        {
          break;
        }
      }
      if ( (unsigned int)++v9 >= 4 )
        goto LABEL_21;
    }
    v14 = (unsigned int)(&off_18000D000)[3 * v9 + 1];
    if ( v14 == 3 )
    {
LABEL_21:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_22;
    }
    Header = DwQueryHeader(pECB, "HTTP_HOST", (char **)&Block);
    v16 = Block;
    if ( !Header && Block && *(_BYTE *)Block )
    {
      memset_0(&WSAData, 0, sizeof(WSAData));
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids, v14);
      v17 = 0;
      v18 = 0;
      while ( LODWORD((&off_18000D000)[3 * v18 + 1]) != 3 )
      {
        if ( LODWORD((&off_18000D000)[3 * v18 + 1]) == v14 )
        {
          v17 = (void (__fastcall *)(EXTENSION_CONTROL_BLOCK *))*(&funcs_1800023FB + 3 * v18);
          break;
        }
        if ( (unsigned int)++v18 >= 4 )
          break;
      }
      v19 = WSAStartup(0x202u, &WSAData);
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids, v19);
        v3 = 4;
      }
      else
      {
        v17(pECB);
        WSACleanup();
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids);
      pECB->dwHttpStatusCode = 400;
      SendSimpleResponse(pECB, 0x190u);
    }
    free(v16);
  }
  else
  {
LABEL_22:
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x400) != 0 )
      WPP_SF_s(v4[2], 18, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids, pECB->lpszQueryString);
    SendSimpleResponse(pECB, 0x190u);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180002110  mov     [rsp+arg_8], rbx
0x180002115  mov     [rsp+arg_10], rbp
0x18000211a  push    rsi
0x18000211b  push    rdi
0x18000211c  push    r13
0x18000211e  push    r14
0x180002120  push    r15
0x180002122  sub     rsp, 1F0h
0x180002129  mov     rax, cs:__security_cookie
0x180002130  xor     rax, rsp
0x180002133  mov     [rsp+218h+var_38], rax
0x18000213b  mov     rbx, rcx
0x18000213e  mov     [rsp+218h+Block], 0
0x180002147  mov     rcx, [rcx+8]
0x18000214b  lea     r8, [rsp+218h+var_1E8]
0x180002150  xor     r9d, r9d
0x180002153  mov     [rsp+218h+var_1E8], 0
0x18000215b  mov     edx, 3F0h
0x180002160  mov     [rsp+218h+var_1F8], 0
0x180002169  mov     rax, [rbx+0B8h]
0x180002170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002175  mov     eax, [rsp+218h+var_1E8]
0x180002179  lea     rcx, WPP_GLOBAL_Control
0x180002180  neg     eax
0x180002182  mov     r11d, 1
0x180002188  mov     r13d, 400h
0x18000218e  sbb     r14d, r14d
0x180002191  neg     r14d
0x180002194  add     r14d, r11d
0x180002197  xor     eax, eax
0x180002199  lock cmpxchg cs:dword_180012180, r11d
0x1800021a2  jnz     short loc_1800021D0
0x1800021a4  mov     r10, cs:WPP_GLOBAL_Control
0x1800021ab  cmp     r10, rcx
0x1800021ae  jz      short loc_1800021D7
0x1800021b0  test    [r10+1Ch], r13d
0x1800021b4  jz      short loc_1800021D7
0x1800021b6  mov     rcx, [r10+10h]
0x1800021ba  lea     edx, [r11+0Ch]
0x1800021be  lea     r8, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids
0x1800021c5  call    WPP_SF_
0x1800021ca  mov     r11d, 1
0x1800021d0  mov     r10, cs:WPP_GLOBAL_Control
0x1800021d7  mov     r15, [rbx+70h]
0x1800021db  test    r15, r15
0x1800021de  jz      loc_18000229A
0x1800021e4  mov     edx, 7FFFFFFFh
0x1800021e9  mov     rax, r15
0x1800021ec  cmp     byte ptr [rax], 0
0x1800021ef  jz      short loc_1800021F9
0x1800021f1  add     rax, r11
0x1800021f4  sub     rdx, r11
0x1800021f7  jnz     short loc_1800021EC
0x1800021f9  mov     ecx, 7FFFFFFFh
0x1800021fe  mov     rax, rdx
0x180002201  sub     rcx, rdx
0x180002204  neg     rax
0x180002207  sbb     rdi, rdi
0x18000220a  and     rdi, rcx
0x18000220d  test    rdx, rdx
0x180002210  jz      loc_18000229A
0x180002216  xor     esi, esi
0x180002218  lea     rcx, off_18000D000; "content"
0x18000221f  movsxd  rax, esi
0x180002222  lea     rbp, [rax+rax*2]
0x180002226  cmp     dword ptr [rcx+rbp*8+8], 3
0x18000222b  jz      short loc_180002293
0x18000222d  mov     rdx, [rcx+rbp*8]; String2
0x180002231  test    rdx, rdx
0x180002234  jz      short loc_18000228B
0x180002236  mov     r8d, 7FFFFFFFh
0x18000223c  mov     rax, rdx
0x18000223f  cmp     byte ptr [rax], 0
0x180002242  jz      short loc_18000224C
0x180002244  add     rax, r11
0x180002247  sub     r8, r11
0x18000224a  jnz     short loc_18000223F
0x18000224c  mov     ecx, 7FFFFFFFh
0x180002251  mov     rax, r8
0x180002254  sub     rcx, r8
0x180002257  neg     rax
0x18000225a  sbb     r10, r10
0x18000225d  and     r10, rcx
0x180002260  test    r8, r8
0x180002263  jz      short loc_180002284
0x180002265  cmp     rdi, r10
0x180002268  jb      short loc_180002284
0x18000226a  mov     r8, r10; MaxCount
0x18000226d  mov     rcx, r15; String1
0x180002270  call    cs:__imp__strnicmp
0x180002276  test    eax, eax
0x180002278  jz      loc_18000232B
0x18000227e  mov     r11d, 1
0x180002284  lea     rcx, off_18000D000; "content"
0x18000228b  add     esi, r11d
0x18000228e  cmp     esi, 4
0x180002291  jb      short loc_18000221F
0x180002293  mov     r10, cs:WPP_GLOBAL_Control
0x18000229a  lea     r15, WPP_GLOBAL_Control
0x1800022a1  cmp     r10, r15
0x1800022a4  jz      short loc_1800022C5
0x1800022a6  test    [r10+1Ch], r13d
0x1800022aa  jz      short loc_1800022C5
0x1800022ac  mov     r9, [rbx+70h]
0x1800022b0  lea     r8, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids
0x1800022b7  mov     rcx, [r10+10h]
0x1800022bb  mov     edx, 12h
0x1800022c0  call    WPP_SF_s
0x1800022c5  mov     edx, 190h; unsigned int
0x1800022ca  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x1800022cd  call    ?SendSimpleResponse@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; SendSimpleResponse(_EXTENSION_CONTROL_BLOCK *,ulong)
0x1800022d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022d9  cmp     rcx, r15
0x1800022dc  jz      short loc_1800022FC
0x1800022de  test    [rcx+1Ch], r13d
0x1800022e2  jz      short loc_1800022FC
0x1800022e4  mov     rcx, [rcx+10h]
0x1800022e8  lea     r8, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids
0x1800022ef  mov     edx, 13h
0x1800022f4  mov     r9d, r14d
0x1800022f7  call    WPP_SF_d
0x1800022fc  mov     eax, r14d
0x1800022ff  mov     rcx, [rsp+218h+var_38]
0x180002307  xor     rcx, rsp; StackCookie
0x18000230a  call    __security_check_cookie
0x18000230f  lea     r11, [rsp+218h+var_28]
0x180002317  mov     rbx, [r11+38h]
0x18000231b  mov     rbp, [r11+40h]
0x18000231f  mov     rsp, r11
0x180002322  pop     r15
0x180002324  pop     r14
0x180002326  pop     r13
0x180002328  pop     rdi
0x180002329  pop     rsi
0x18000232a  retn
0x18000232b  lea     rax, off_18000D000; "content"
0x180002332  mov     ebp, [rax+rbp*8+8]
0x180002336  cmp     ebp, 3
0x180002339  jz      loc_180002293
0x18000233f  lea     r8, [rsp+218h+Block]; char **
0x180002344  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x180002347  lea     rdx, aHttpHost; "HTTP_HOST"
0x18000234e  call    ?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z; DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)
0x180002353  mov     rdi, [rsp+218h+Block]
0x180002358  test    eax, eax
0x18000235a  jnz     loc_18000243A
0x180002360  test    rdi, rdi
0x180002363  jz      loc_18000243A
0x180002369  cmp     [rdi], al
0x18000236b  jz      loc_18000243A
0x180002371  xor     edx, edx; Val
0x180002373  lea     rcx, [rsp+218h+WSAData]; void *
0x180002378  mov     r8d, 198h; Size
0x18000237e  call    memset_0
0x180002383  mov     rcx, cs:WPP_GLOBAL_Control
0x18000238a  lea     r15, WPP_GLOBAL_Control
0x180002391  cmp     rcx, r15
0x180002394  jz      short loc_1800023B4
0x180002396  test    [rcx+1Ch], r13d
0x18000239a  jz      short loc_1800023B4
0x18000239c  mov     rcx, [rcx+10h]
0x1800023a0  lea     r8, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids
0x1800023a7  mov     edx, 0Fh
0x1800023ac  mov     r9d, ebp
0x1800023af  call    WPP_SF_d
0x1800023b4  xor     esi, esi
0x1800023b6  xor     ecx, ecx
0x1800023b8  movsxd  rax, ecx
0x1800023bb  lea     rdx, [rax+rax*2]
0x1800023bf  lea     rax, off_18000D000; "content"
0x1800023c6  cmp     dword ptr [rax+rdx*8+8], 3
0x1800023cb  jz      short loc_1800023E1
0x1800023cd  cmp     [rax+rdx*8+8], ebp
0x1800023d1  jz      short loc_1800023DC
0x1800023d3  inc     ecx
0x1800023d5  cmp     ecx, 4
0x1800023d8  jb      short loc_1800023B8
0x1800023da  jmp     short loc_1800023E1
0x1800023dc  mov     rsi, ds:(funcs_1800023FB - 18000D000h)[rax+rdx*8]
0x1800023e1  mov     ecx, 202h; wVersionRequested
0x1800023e6  lea     rdx, [rsp+218h+WSAData]; lpWSAData
0x1800023eb  call    cs:__imp_WSAStartup
0x1800023f1  test    eax, eax
0x1800023f3  jnz     short loc_180002408
0x1800023f5  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x1800023f8  mov     rax, rsi
0x1800023fb  call    _guard_dispatch_icall$thunk$10345483385596137414; DwHandleContentRequest(void *) ...
0x180002400  call    cs:__imp_WSACleanup
0x180002406  jmp     short loc_180002478
0x180002408  mov     rcx, cs:WPP_GLOBAL_Control
0x18000240f  cmp     rcx, r15
0x180002412  jz      short loc_180002432
0x180002414  test    [rcx+1Ch], r13d
0x180002418  jz      short loc_180002432
0x18000241a  mov     rcx, [rcx+10h]
0x18000241e  lea     r8, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids
0x180002425  mov     edx, 10h
0x18000242a  mov     r9d, eax
0x18000242d  call    WPP_SF_d
0x180002432  mov     r14d, 4
0x180002438  jmp     short loc_180002478
0x18000243a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002441  lea     r15, WPP_GLOBAL_Control
0x180002448  cmp     rcx, r15
0x18000244b  jz      short loc_180002468
0x18000244d  test    [rcx+1Ch], r13d
0x180002451  jz      short loc_180002468
0x180002453  mov     rcx, [rcx+10h]
0x180002457  lea     r8, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids
0x18000245e  mov     edx, 11h
0x180002463  call    WPP_SF_
0x180002468  mov     edx, 190h; unsigned int
0x18000246d  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x180002470  mov     [rbx+10h], edx
0x180002473  call    ?SendSimpleResponse@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; SendSimpleResponse(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180002478  mov     rcx, rdi; Block
0x18000247b  call    cs:__imp_free
0x180002481  jmp     loc_1800022D2
```
