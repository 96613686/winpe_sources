# JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)

- ea: `0x180022d80`
- end: `0x1800231b0`
- name: `?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `1072`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001fe44`
- `0x180021260`
- `0x180021418`
- `0x180021ba0`
- `0x180022aa0`
- `0x180023c4c`
- `0x180054550`
- `0x180054a58`
- `0x18006f0b0`
- `0x18006fc30`
- `0x180071400`

## callees

- `0x180001e10`
- `0x180022d80`
- `0x180059140`
- `0x18005a2bc`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022e42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022e42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022dba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022dba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18002310d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18002310d`

## pseudocode

```c
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
    v36 = &qword_1800A8718;
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
0x180022d80  push    rbx
0x180022d82  push    rsi
0x180022d83  push    r12
0x180022d85  push    r13
0x180022d87  push    r15
0x180022d89  sub     rsp, 2A0h
0x180022d90  mov     rax, cs:__security_cookie
0x180022d97  xor     rax, rsp
0x180022d9a  mov     [rsp+2C8h+var_48], rax
0x180022da2  mov     r15, r8
0x180022da5  mov     r12, rdx
0x180022da8  mov     r13, rcx
0x180022dab  xor     edx, edx; dwFlags
0x180022dad  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180022db4  mov     r8d, 20Ah; dwBytes
0x180022dba  call    cs:__imp_HeapAlloc
0x180022dc1  nop     dword ptr [rax+rax+00h]
0x180022dc6  mov     rbx, rax
0x180022dc9  test    rax, rax
0x180022dcc  jnz     short loc_180022E19
0x180022dce  mov     [rsp+2C8h+var_290], al
0x180022dd2  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180022dd9  xor     esi, esi
0x180022ddb  mov     [rsp+2C8h+var_270], 0Eh
0x180022de3  lea     rax, qword_1800A8718
0x180022dea  mov     [rsp+2C8h+var_280], rsi
0x180022def  mov     [rsp+2C8h+var_288], rax
0x180022df4  lea     rcx, [rsp+2C8h+pExceptionObject]; pExceptionObject
0x180022df9  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180022e00  mov     [rsp+2C8h+var_278], rsi
0x180022e05  mov     [rsp+2C8h+pExceptionObject], rax
0x180022e0a  mov     [rsp+2C8h+var_26C], 0FFFFFFFFFFFFFFFFh
0x180022e13  call    _CxxThrowException_0
0x180022e19  mov     r8, [r15]; lpMem
0x180022e1c  mov     [rsp+2C8h+arg_0], rbp
0x180022e24  mov     [rsp+2C8h+var_30], rdi
0x180022e2c  mov     [rsp+2C8h+var_38], r14
0x180022e34  test    r8, r8
0x180022e37  jz      short loc_180022E4E
0x180022e39  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180022e40  xor     edx, edx; dwFlags
0x180022e42  call    cs:__imp_HeapFree
0x180022e49  nop     dword ptr [rax+rax+00h]
0x180022e4e  mov     r14d, 7FFFFFFEh
0x180022e54  mov     [r15], rbx
0x180022e57  lea     rdi, asc_1800A7E18; "\\\\?\\"
0x180022e5e  mov     ebp, 105h
0x180022e63  mov     ecx, r14d
0x180022e66  mov     rdx, rdi
0x180022e69  mov     r8d, ebp
0x180022e6c  nop     dword ptr [rax+00h]
0x180022e70  test    rcx, rcx
0x180022e73  jz      short loc_180022ED6
0x180022e75  movzx   eax, word ptr [rdx]
0x180022e78  test    ax, ax
0x180022e7b  jz      short loc_180022E93
0x180022e7d  mov     [rbx], ax
0x180022e80  add     rdx, 2
0x180022e84  add     rbx, 2
0x180022e88  dec     rcx
0x180022e8b  sub     r8, 1
0x180022e8f  jnz     short loc_180022E70
0x180022e91  jmp     short loc_180022E98
0x180022e93  test    r8, r8
0x180022e96  jnz     short loc_180022ED6
0x180022e98  xor     esi, esi
0x180022e9a  mov     [rbx-2], si
0x180022e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ea5  lea     rax, WPP_GLOBAL_Control
0x180022eac  cmp     rcx, rax
0x180022eaf  jz      loc_180023168
0x180022eb5  test    dword ptr [rcx+1Ch], 40000h
0x180022ebc  jz      loc_180023168
0x180022ec2  cmp     byte ptr [rcx+19h], 2
0x180022ec6  jb      loc_180023168
0x180022ecc  mov     edx, 13h
0x180022ed1  jmp     loc_18002314D
0x180022ed6  xor     esi, esi
0x180022ed8  mov     rcx, rbp
0x180022edb  mov     [rbx], si
0x180022ede  mov     r8, [r15]
0x180022ee1  mov     rax, r8
0x180022ee4  cmp     [rax], si
0x180022ee7  jz      short loc_180022EF3
0x180022ee9  add     rax, 2
0x180022eed  sub     rcx, 1
0x180022ef1  jnz     short loc_180022EE4
0x180022ef3  mov     rdx, rbp
0x180022ef6  sub     rdx, rcx
0x180022ef9  test    rcx, rcx
0x180022efc  cmovz   rdx, rsi
0x180022f00  jz      loc_180023126
0x180022f06  mov     r9, [r13+0]
0x180022f0a  mov     rcx, rbp
0x180022f0d  sub     rcx, rdx
0x180022f10  mov     rax, r14
0x180022f13  lea     rdx, [r8+rdx*2]
0x180022f17  jz      short loc_180022F44
0x180022f19  nop     dword ptr [rax+00000000h]
0x180022f20  test    rax, rax
0x180022f23  jz      short loc_180022F44
0x180022f25  movzx   r8d, word ptr [r9]
0x180022f29  test    r8w, r8w
0x180022f2d  jz      short loc_180022F44
0x180022f2f  mov     [rdx], r8w
0x180022f33  add     r9, 2
0x180022f37  add     rdx, 2
0x180022f3b  dec     rax
0x180022f3e  sub     rcx, 1
0x180022f42  jnz     short loc_180022F20
0x180022f44  test    rcx, rcx
0x180022f47  lea     rax, [rdx-2]
0x180022f4b  cmovnz  rax, rdx
0x180022f4f  mov     [rax], si
0x180022f52  jz      loc_180023126
0x180022f58  test    r12, r12
0x180022f5b  jz      short loc_180022F75
0x180022f5d  movzx   eax, word ptr [r12]
0x180022f62  test    ax, ax
0x180022f65  jz      short loc_180022F75
0x180022f67  cmp     [r12+2], si
0x180022f6d  jnz     short loc_180022FE1
0x180022f6f  cmp     ax, 5Ch ; '\'
0x180022f73  jnz     short loc_180022FE7
0x180022f75  mov     rcx, r14
0x180022f78  lea     rdx, [rsp+2C8h+pszPrefix]
0x180022f7d  mov     r8, rbp
0x180022f80  test    rcx, rcx
0x180022f83  jz      loc_18002308C
0x180022f89  movzx   eax, word ptr [rdi]
0x180022f8c  test    ax, ax
0x180022f8f  jz      loc_180023083
0x180022f95  mov     [rdx], ax
0x180022f98  add     rdi, 2
0x180022f9c  add     rdx, 2
0x180022fa0  dec     rcx
0x180022fa3  sub     r8, 1
0x180022fa7  jnz     short loc_180022F80
0x180022fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fb0  lea     rax, WPP_GLOBAL_Control
0x180022fb7  cmp     rcx, rax
0x180022fba  jz      loc_180023168
0x180022fc0  test    dword ptr [rcx+1Ch], 40000h
0x180022fc7  jz      loc_180023168
0x180022fcd  cmp     byte ptr [rcx+19h], 2
0x180022fd1  jb      loc_180023168
0x180022fd7  mov     edx, 17h
0x180022fdc  jmp     loc_18002314D
0x180022fe1  cmp     ax, 5Ch ; '\'
0x180022fe5  jz      short loc_180023035
0x180022fe7  mov     rcx, [r15]; unsigned __int16 *
0x180022fea  lea     r8, asc_1800A7EC0; "\\"
0x180022ff1  mov     rdx, rbp; unsigned __int64
0x180022ff4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022ff9  test    eax, eax
0x180022ffb  jns     short loc_180023035
0x180022ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x180023004  lea     rax, WPP_GLOBAL_Control
0x18002300b  cmp     rcx, rax
0x18002300e  jz      loc_180023168
0x180023014  test    dword ptr [rcx+1Ch], 40000h
0x18002301b  jz      loc_180023168
0x180023021  cmp     byte ptr [rcx+19h], 2
0x180023025  jb      loc_180023168
0x18002302b  mov     edx, 15h
0x180023030  jmp     loc_18002314D
0x180023035  mov     rcx, [r15]; unsigned __int16 *
0x180023038  mov     r8, r12; unsigned __int16 *
0x18002303b  mov     rdx, rbp; unsigned __int64
0x18002303e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023043  test    eax, eax
0x180023045  jns     loc_180022F75
0x18002304b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023052  lea     rax, WPP_GLOBAL_Control
0x180023059  cmp     rcx, rax
0x18002305c  jz      loc_180023168
0x180023062  test    dword ptr [rcx+1Ch], 40000h
0x180023069  jz      loc_180023168
0x18002306f  cmp     byte ptr [rcx+19h], 2
0x180023073  jb      loc_180023168
0x180023079  mov     edx, 16h
0x18002307e  jmp     loc_18002314D
0x180023083  test    r8, r8
0x180023086  jz      loc_180022FA9
0x18002308c  mov     [rdx], si
0x18002308f  lea     rax, [rsp+2C8h+pszPrefix]
0x180023094  mov     rcx, rbp
0x180023097  cmp     [rax], si
0x18002309a  jz      short loc_1800230A6
0x18002309c  add     rax, 2
0x1800230a0  sub     rcx, 1
0x1800230a4  jnz     short loc_180023097
0x1800230a6  mov     rdx, rbp
0x1800230a9  sub     rdx, rcx
0x1800230ac  test    rcx, rcx
0x1800230af  cmovz   rdx, rsi
0x1800230b3  jz      loc_180022FA9
0x1800230b9  mov     rax, [r13+0]
0x1800230bd  lea     rcx, [rsp+2C8h+pszPrefix]
0x1800230c2  lea     rcx, [rcx+rdx*2]
0x1800230c6  sub     rbp, rdx
0x1800230c9  jz      short loc_1800230F1
0x1800230cb  nop     dword ptr [rax+rax+00h]
0x1800230d0  test    r14, r14
0x1800230d3  jz      short loc_1800230F1
0x1800230d5  movzx   edx, word ptr [rax]
0x1800230d8  test    dx, dx
0x1800230db  jz      short loc_1800230F1
0x1800230dd  mov     [rcx], dx
0x1800230e0  add     rax, 2
0x1800230e4  add     rcx, 2
0x1800230e8  dec     r14
0x1800230eb  sub     rbp, 1
0x1800230ef  jnz     short loc_1800230D0
0x1800230f1  test    rbp, rbp
0x1800230f4  lea     rax, [rcx-2]
0x1800230f8  cmovnz  rax, rcx
0x1800230fc  mov     [rax], si
0x1800230ff  jz      loc_180022FA9
0x180023105  mov     rdx, [r15]; pszPath
0x180023108  lea     rcx, [rsp+2C8h+pszPrefix]; pszPrefix
0x18002310d  call    cs:__imp_PathIsPrefixW
0x180023114  nop     dword ptr [rax+rax+00h]
0x180023119  cmp     eax, 1
0x18002311c  jnz     loc_180022FA9
0x180023122  xor     eax, eax
0x180023124  jmp     short loc_18002316D
0x180023126  mov     rcx, cs:WPP_GLOBAL_Control
0x18002312d  lea     rax, WPP_GLOBAL_Control
0x180023134  cmp     rcx, rax
0x180023137  jz      short loc_180023168
0x180023139  test    dword ptr [rcx+1Ch], 40000h
0x180023140  jz      short loc_180023168
0x180023142  cmp     byte ptr [rcx+19h], 2
0x180023146  jb      short loc_180023168
0x180023148  mov     edx, 14h
0x18002314d  mov     rcx, [rcx+10h]
0x180023151  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180023158  mov     r9, r12
0x18002315b  mov     [rsp+2C8h+var_2A8], 800700A1h
0x180023163  call    WPP_SF_Sd
0x180023168  mov     eax, 800700A1h
0x18002316d  mov     rdi, [rsp+2C8h+var_30]
0x180023175  mov     rbp, [rsp+2C8h+arg_0]
0x18002317d  mov     r14, [rsp+2C8h+var_38]
0x180023185  mov     rcx, [rsp+2C8h+var_48]
0x18002318d  xor     rcx, rsp; StackCookie
0x180023190  call    __security_check_cookie
0x180023195  add     rsp, 2A0h
0x18002319c  pop     r15
0x18002319e  pop     r13
0x1800231a0  pop     r12
0x1800231a2  pop     rsi
0x1800231a3  pop     rbx
0x1800231a4  retn
```
