# CEventsDB::Create(void)

- ea: `0x140037088`
- end: `0x1400372a6`
- name: `?Create@CEventsDB@@QEAAJXZ`
- size: `542`
- prototype: `__int64 __fastcall(CEventsDB *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140068c18`

## callees

- `0x1400065e0`
- `0x140007020`
- `0x140018df0`
- `0x140037088`
- `0x14003cd64`
- `0x14003f17c`
- `0x140047798`
- `0x140093924`
- `0x140097fac`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14003715f`
- `KERNEL32!CreateEventW` at `0x14003715f`
- `KERNEL32!GetLastError` at `0x14003716a`
- `KERNEL32!GetLastError` at `0x14003716a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEventsDB::Create(CEventsDB *this)
{
  const WCHAR *v2; // rbx
  unsigned int UUID; // eax
  signed int v4; // edi
  HANDLE EventW; // rax
  enum _SE_OBJECT_TYPE v6; // edx
  unsigned int v7; // r8d
  signed int v8; // r9d
  signed int LastError; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // edi
  PVOID *v13; // r10
  LPCWSTR lpName; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids);
  v2 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  lpName = v2;
  UUID = CreateUUID((char *)this + 8);
  v4 = UUID;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, UUID);
  }
  if ( v4 < 0 )
    goto LABEL_29;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
    &lpName,
    L"Global\\%ls",
    *((_QWORD *)this + 1));
  v2 = lpName;
  EventW = CreateEventW(0, 1, 0, lpName);
  if ( EventW )
  {
    *(_QWORD *)this = EventW;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    else
      v4 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = *((unsigned __int8 *)WPP_GLOBAL_Control + 25);
      v10 = 5;
      if ( v8 )
        v10 = 2;
      if ( v6 >= v10 )
        WPP_SF_DSq(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, v8, (__int64)v2, 0);
    }
    if ( v4 < 0 )
      goto LABEL_29;
  }
  v11 = SetInteractiveAndNetworkHandleACLs(*(void **)this, v6, v7, v8);
  v12 = v11;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v11);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 )
  {
    v4 = 0;
    goto LABEL_33;
  }
  v4 = -2147467259;
LABEL_29:
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 8);
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_37;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_33:
  if ( v13 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v13 + 28) & 1) != 0
    && *((unsigned __int8 *)v13 + 25) >= ((v4 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v13[2], 19, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, (unsigned int)v4);
  }
LABEL_37:
  ATL::CStringData::Release((ATL::CStringData *)(v2 - 12));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140037088  mov     [rsp+arg_0], rbx
0x14003708d  mov     [rsp+arg_10], rbp
0x140037092  push    rsi
0x140037093  push    rdi
0x140037094  push    r12
0x140037096  push    r14
0x140037098  push    r15
0x14003709a  sub     rsp, 30h
0x14003709e  mov     rsi, rcx
0x1400370a1  lea     rbp, WPP_GLOBAL_Control
0x1400370a8  lea     r15, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x1400370af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400370b6  cmp     rcx, rbp
0x1400370b9  jz      short loc_1400370D2
0x1400370bb  test    byte ptr [rcx+1Ch], 1
0x1400370bf  jz      short loc_1400370D2
0x1400370c1  mov     edx, 0Eh
0x1400370c6  mov     r8, r15
0x1400370c9  mov     rcx, [rcx+10h]
0x1400370cd  call    WPP_SF_
0x1400370d2  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400370d9  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400370e0  mov     rax, [rax+18h]
0x1400370e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400370e9  lea     rbx, [rax+18h]
0x1400370ed  mov     [rsp+58h+lpName], rbx
0x1400370f2  lea     r14, [rsi+8]
0x1400370f6  mov     rcx, r14
0x1400370f9  call    ?CreateUUID@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CreateUUID(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x1400370fe  mov     edi, eax
0x140037100  mov     r12d, 2
0x140037106  mov     rcx, cs:WPP_GLOBAL_Control
0x14003710d  cmp     rcx, rbp
0x140037110  jz      short loc_140037132
0x140037112  test    [rcx+1Ch], r12b
0x140037116  jz      short loc_140037132
0x140037118  cmp     byte ptr [rcx+19h], 4
0x14003711c  jb      short loc_140037132
0x14003711e  lea     edx, [r12+0Dh]
0x140037123  mov     r9d, eax
0x140037126  mov     r8, r15
0x140037129  mov     rcx, [rcx+10h]
0x14003712d  call    WPP_SF_d
0x140037132  test    edi, edi
0x140037134  js      loc_140037216
0x14003713a  mov     r8, [r14]
0x14003713d  lea     rdx, aGlobalLs; "Global\\%ls"
0x140037144  lea     rcx, [rsp+58h+lpName]
0x140037149  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x14003714e  mov     rbx, [rsp+58h+lpName]
0x140037153  mov     r9, rbx; lpName
0x140037156  xor     r8d, r8d; bInitialState
0x140037159  lea     edx, [r8+1]; bManualReset
0x14003715d  xor     ecx, ecx; lpEventAttributes
0x14003715f  call    cs:__imp_CreateEventW
0x140037165  test    rax, rax
0x140037168  jnz     short loc_1400371C8
0x14003716a  call    cs:__imp_GetLastError
0x140037170  mov     r9d, eax
0x140037173  test    eax, eax
0x140037175  jg      short loc_14003717B
0x140037177  mov     edi, eax
0x140037179  jmp     short loc_140037185
0x14003717b  movzx   edi, r9w
0x14003717f  or      edi, 80070000h
0x140037185  mov     rcx, cs:WPP_GLOBAL_Control
0x14003718c  cmp     rcx, rbp
0x14003718f  jz      short loc_1400371C2
0x140037191  test    [rcx+1Ch], r12b
0x140037195  jz      short loc_1400371C2
0x140037197  movzx   edx, byte ptr [rcx+19h]
0x14003719b  mov     eax, 5
0x1400371a0  test    r9d, r9d
0x1400371a3  cmovnz  eax, r12d
0x1400371a7  cmp     edx, eax
0x1400371a9  jb      short loc_1400371C2
0x1400371ab  mov     [rsp+58h+var_30], 0
0x1400371b4  mov     [rsp+58h+var_38], rbx
0x1400371b9  mov     rcx, [rcx+10h]
0x1400371bd  call    WPP_SF_DSq
0x1400371c2  test    edi, edi
0x1400371c4  jns     short loc_1400371CB
0x1400371c6  jmp     short loc_140037216
0x1400371c8  mov     [rsi], rax
0x1400371cb  mov     rcx, [rsi]; void *
0x1400371ce  call    ?SetInteractiveAndNetworkHandleACLs@@YAHPEAXW4_SE_OBJECT_TYPE@@KE@Z; SetInteractiveAndNetworkHandleACLs(void *,_SE_OBJECT_TYPE,ulong,uchar)
0x1400371d3  mov     edi, eax
0x1400371d5  mov     r10, cs:WPP_GLOBAL_Control
0x1400371dc  cmp     r10, rbp
0x1400371df  jz      short loc_140037209
0x1400371e1  test    [r10+1Ch], r12b
0x1400371e5  jz      short loc_140037209
0x1400371e7  cmp     byte ptr [r10+19h], 4
0x1400371ec  jb      short loc_140037209
0x1400371ee  mov     edx, 11h
0x1400371f3  mov     r9d, eax
0x1400371f6  mov     r8, r15
0x1400371f9  mov     rcx, [r10+10h]
0x1400371fd  call    WPP_SF_d
0x140037202  mov     r10, cs:WPP_GLOBAL_Control
0x140037209  test    edi, edi
0x14003720b  jz      short loc_140037211
0x14003720d  xor     edi, edi
0x14003720f  jmp     short loc_14003724F
0x140037211  mov     edi, 80004005h
0x140037216  mov     rcx, r14
0x140037219  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14003721e  mov     r10, cs:WPP_GLOBAL_Control
0x140037225  cmp     r10, rbp
0x140037228  jz      short loc_140037284
0x14003722a  test    [r10+1Ch], r12b
0x14003722e  jz      short loc_14003724F
0x140037230  cmp     byte ptr [r10+19h], 4
0x140037235  jb      short loc_14003724F
0x140037237  mov     edx, 12h
0x14003723c  mov     r8, r15
0x14003723f  mov     rcx, [r10+10h]
0x140037243  call    WPP_SF_
0x140037248  mov     r10, cs:WPP_GLOBAL_Control
0x14003724f  cmp     r10, rbp
0x140037252  jz      short loc_140037284
0x140037254  test    byte ptr [r10+1Ch], 1
0x140037259  jz      short loc_140037284
0x14003725b  mov     ecx, edi
0x14003725d  sar     ecx, 1Fh
0x140037260  and     ecx, 0FFFFFFFDh
0x140037263  add     ecx, 5
0x140037266  movzx   eax, byte ptr [r10+19h]
0x14003726b  cmp     eax, ecx
0x14003726d  jb      short loc_140037284
0x14003726f  mov     edx, 13h
0x140037274  mov     r9d, edi
0x140037277  mov     r8, r15
0x14003727a  mov     rcx, [r10+10h]
0x14003727e  call    WPP_SF_d
0x140037283  nop
0x140037284  lea     rcx, [rbx-18h]; this
0x140037288  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14003728d  mov     eax, edi
0x14003728f  mov     rbx, [rsp+58h+arg_0]
0x140037294  mov     rbp, [rsp+58h+arg_10]
0x140037299  add     rsp, 30h
0x14003729d  pop     r15
0x14003729f  pop     r14
0x1400372a1  pop     r12
0x1400372a3  pop     rdi
0x1400372a4  pop     rsi
0x1400372a5  retn
```
