# JobStore::CreateXmlFolder(ushort const *,ushort const *)

- ea: `0x1800265fc`
- end: `0x180026931`
- name: `?CreateXmlFolder@JobStore@@QEAAJPEBG0@Z`
- size: `821`
- prototype: `__int64 __fastcall(JobStore *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800213f8`
- `0x180024ce0`
- `0x18002506c`
- `0x18006c840`

## callees

- `0x18001a260`
- `0x1800265c4`
- `0x1800265fc`
- `0x180027ee0`
- `0x18002a9e0`
- `0x18004c550`
- `0x180056794`
- `0x18006bb70`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002674f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002674f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002672f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800268d0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002672f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800268d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026676`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026676`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18002681f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18002681f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18002685a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18002685a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobStore::CreateXmlFolder(JobStore *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int XmlFileSystemPath; // ebx
  struct _SECURITY_ATTRIBUTES *v8; // r14
  void *v9; // rbx
  unsigned int v10; // edi
  signed int LastError; // eax
  _QWORD *v12; // rcx
  int v13; // edx
  LPWSTR v14; // r15
  LPWSTR v15; // rax
  LPWSTR v16; // rsi
  WCHAR v17; // ax
  _WORD *v18; // rdi
  struct _SECURITY_ATTRIBUTES *v19; // rdx
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  void **v21; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( !JobStore::GetUseXmlStore(this) )
    return 0;
  lpMem = 0;
  XmlFileSystemPath = JobStore::GetXmlFileSystemPath(this, a2, &lpMem);
  if ( XmlFileSystemPath >= 0 )
  {
    v21 = &ATL::CSecurityDesc::`vftable';
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v8 = 0;
    v9 = lpMem;
    if ( a3 )
    {
      if ( !ATL::CSecurityDesc::FromString((ATL::CSecurityDesc *)&v21, a3) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
            (_DWORD)a3,
            58);
        }
        v10 = -2147023558;
        goto LABEL_49;
      }
      v24 = v22;
      LODWORD(v23) = 24;
      LODWORD(v25) = 0;
      v8 = (struct _SECURITY_ATTRIBUTES *)&v23;
    }
    if ( !CreateDirectoryW((LPCWSTR)v9, v8) )
    {
      memset_0(pszPath, 0, 0x208u);
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError != 3 )
      {
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
            (_DWORD)v9,
            v10);
        }
        goto LABEL_49;
      }
      if ( (int)StringCchCopyW(pszPath, 0x104u, (const unsigned __int16 *)v9) < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v13 = 29;
LABEL_28:
        WPP_SF_Sd(v12[2], v13, (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, (_DWORD)v9, 206);
LABEL_29:
        v10 = -2147024690;
LABEL_49:
        v21 = &ATL::CSecurityDesc::`vftable';
        ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v21);
        operator delete(v9);
        return v10;
      }
      v14 = PathAddBackslashW(pszPath);
      if ( !v14 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v13 = 30;
        goto LABEL_28;
      }
      v15 = PathSkipRootW(pszPath);
      v16 = v15;
      if ( !v15 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v13 = 31;
        goto LABEL_28;
      }
      if ( *v15 )
      {
        do
        {
          v17 = *v16;
          do
          {
            if ( v17 == 92 )
              break;
            v17 = *++v16;
          }
          while ( *v16 );
          if ( !*v16 )
            break;
          *v16 = 0;
          v18 = v16 + 1;
          v19 = v8;
          if ( v16 + 1 != v14 )
            v19 = 0;
          CreateDirectoryW(pszPath, v19);
          *v16++ = 92;
        }
        while ( *v18 );
      }
    }
    v10 = 0;
    goto LABEL_49;
  }
  if ( lpMem )
    HeapFree(g_PrivateHeap, 0, lpMem);
  return (unsigned int)XmlFileSystemPath;
}

```

## disassembly

```asm
0x1800265fc  mov     [rsp-8+arg_18], rbx
0x180026601  push    rbp
0x180026602  push    rsi
0x180026603  push    rdi
0x180026604  push    r12
0x180026606  push    r13
0x180026608  push    r14
0x18002660a  push    r15
0x18002660c  lea     rbp, [rsp-180h]
0x180026614  sub     rsp, 280h
0x18002661b  mov     rax, cs:__security_cookie
0x180026622  xor     rax, rsp
0x180026625  mov     [rbp+1B0h+var_40], rax
0x18002662c  mov     rdi, r8
0x18002662f  mov     rsi, rdx
0x180026632  mov     rbx, rcx
0x180026635  call    ?GetUseXmlStore@JobStore@@QEBAEXZ; JobStore::GetUseXmlStore(void)
0x18002663a  xor     r12d, r12d
0x18002663d  test    al, al
0x18002663f  jnz     short loc_180026648
0x180026641  xor     eax, eax
0x180026643  jmp     loc_180026907
0x180026648  mov     [rsp+2B0h+lpMem], r12
0x18002664d  lea     r8, [rsp+2B0h+lpMem]
0x180026652  mov     rdx, rsi
0x180026655  mov     rcx, rbx
0x180026658  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x18002665d  mov     ebx, eax
0x18002665f  test    eax, eax
0x180026661  jns     short loc_180026683
0x180026663  mov     r8, [rsp+2B0h+lpMem]; lpMem
0x180026668  test    r8, r8
0x18002666b  jz      short loc_18002667C
0x18002666d  xor     edx, edx; dwFlags
0x18002666f  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180026676  call    cs:__imp_HeapFree
0x18002667c  mov     eax, ebx
0x18002667e  jmp     loc_180026907
0x180026683  lea     r13, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x18002668a  mov     [rsp+2B0h+var_278], r13
0x18002668f  mov     [rsp+2B0h+var_270], r12
0x180026694  mov     [rsp+2B0h+var_268], r12
0x180026699  mov     [rsp+2B0h+var_260], r12
0x18002669e  mov     [rsp+2B0h+var_258], r12
0x1800266a3  mov     r14, r12
0x1800266a6  mov     rbx, [rsp+2B0h+lpMem]
0x1800266ab  test    rdi, rdi
0x1800266ae  jz      short loc_180026729
0x1800266b0  mov     rdx, rdi; StringSecurityDescriptor
0x1800266b3  lea     rcx, [rsp+2B0h+var_278]; this
0x1800266b8  call    ?FromString@CSecurityDesc@ATL@@QEAA_NPEBG@Z; ATL::CSecurityDesc::FromString(ushort const *)
0x1800266bd  test    al, al
0x1800266bf  jnz     short loc_18002670D
0x1800266c1  lea     rax, WPP_GLOBAL_Control
0x1800266c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266cf  cmp     rcx, rax
0x1800266d2  jz      short loc_180026703
0x1800266d4  test    dword ptr [rcx+1Ch], 40000h
0x1800266db  jz      short loc_180026703
0x1800266dd  cmp     byte ptr [rcx+19h], 2
0x1800266e1  jb      short loc_180026703
0x1800266e3  mov     edx, 1Bh
0x1800266e8  mov     [rsp+2B0h+var_290], 53Ah
0x1800266f0  mov     r9, rdi
0x1800266f3  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x1800266fa  mov     rcx, [rcx+10h]
0x1800266fe  call    WPP_SF_Sd
0x180026703  mov     edi, 8007053Ah
0x180026708  jmp     loc_1800268ED
0x18002670d  mov     rax, [rsp+2B0h+var_270]
0x180026712  mov     [rsp+2B0h+var_260], rax
0x180026717  mov     dword ptr [rsp+2B0h+var_268], 18h
0x18002671f  mov     dword ptr [rsp+2B0h+var_258], r12d
0x180026724  lea     r14, [rsp+2B0h+var_268]
0x180026729  mov     rdx, r14; lpSecurityAttributes
0x18002672c  mov     rcx, rbx; lpPathName
0x18002672f  call    cs:__imp_CreateDirectoryW
0x180026735  test    eax, eax
0x180026737  jnz     loc_1800268EA
0x18002673d  xor     edx, edx; Val
0x18002673f  mov     r8d, 208h; Size
0x180026745  lea     rcx, [rsp+2B0h+pszPath]; void *
0x18002674a  call    memset_0
0x18002674f  call    cs:__imp_GetLastError
0x180026755  mov     edi, eax
0x180026757  cmp     eax, 3
0x18002675a  jz      short loc_1800267B8
0x18002675c  test    eax, eax
0x18002675e  jle     short loc_180026769
0x180026760  movzx   edi, ax
0x180026763  or      edi, 80070000h
0x180026769  lea     rax, WPP_GLOBAL_Control
0x180026770  mov     rcx, cs:WPP_GLOBAL_Control
0x180026777  cmp     rcx, rax
0x18002677a  jz      loc_1800268ED
0x180026780  test    dword ptr [rcx+1Ch], 40000h
0x180026787  jz      loc_1800268ED
0x18002678d  cmp     byte ptr [rcx+19h], 2
0x180026791  jb      loc_1800268ED
0x180026797  mov     edx, 1Ch
0x18002679c  mov     [rsp+2B0h+var_290], edi
0x1800267a0  mov     r9, rbx
0x1800267a3  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x1800267aa  mov     rcx, [rcx+10h]
0x1800267ae  call    WPP_SF_Sd
0x1800267b3  jmp     loc_1800268ED
0x1800267b8  mov     r8, rbx; unsigned __int16 *
0x1800267bb  mov     edx, 104h; unsigned __int64
0x1800267c0  lea     rcx, [rsp+2B0h+pszPath]; unsigned __int16 *
0x1800267c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800267ca  test    eax, eax
0x1800267cc  jns     short loc_18002681A
0x1800267ce  lea     rax, WPP_GLOBAL_Control
0x1800267d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267dc  cmp     rcx, rax
0x1800267df  jz      short loc_180026810
0x1800267e1  test    dword ptr [rcx+1Ch], 40000h
0x1800267e8  jz      short loc_180026810
0x1800267ea  cmp     byte ptr [rcx+19h], 2
0x1800267ee  jb      short loc_180026810
0x1800267f0  mov     edx, 1Dh
0x1800267f5  mov     [rsp+2B0h+var_290], 800700CEh
0x1800267fd  mov     r9, rbx
0x180026800  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180026807  mov     rcx, [rcx+10h]
0x18002680b  call    WPP_SF_Sd
0x180026810  mov     edi, 800700CEh
0x180026815  jmp     loc_1800268ED
0x18002681a  lea     rcx, [rsp+2B0h+pszPath]; pszPath
0x18002681f  call    cs:__imp_PathAddBackslashW
0x180026825  mov     r15, rax
0x180026828  test    rax, rax
0x18002682b  jnz     short loc_180026855
0x18002682d  lea     rax, WPP_GLOBAL_Control
0x180026834  mov     rcx, cs:WPP_GLOBAL_Control
0x18002683b  cmp     rcx, rax
0x18002683e  jz      short loc_180026810
0x180026840  test    dword ptr [rcx+1Ch], 40000h
0x180026847  jz      short loc_180026810
0x180026849  cmp     byte ptr [rcx+19h], 2
0x18002684d  jb      short loc_180026810
0x18002684f  lea     edx, [r15+1Eh]
0x180026853  jmp     short loc_1800267F5
0x180026855  lea     rcx, [rsp+2B0h+pszPath]; pszPath
0x18002685a  call    cs:__imp_PathSkipRootW
0x180026860  mov     rsi, rax
0x180026863  test    rax, rax
0x180026866  jnz     short loc_180026892
0x180026868  lea     rax, WPP_GLOBAL_Control
0x18002686f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026876  cmp     rcx, rax
0x180026879  jz      short loc_180026810
0x18002687b  test    dword ptr [rcx+1Ch], 40000h
0x180026882  jz      short loc_180026810
0x180026884  cmp     byte ptr [rcx+19h], 2
0x180026888  jb      short loc_180026810
0x18002688a  lea     edx, [rsi+1Fh]
0x18002688d  jmp     loc_1800267F5
0x180026892  cmp     [rax], r12w
0x180026896  jz      short loc_1800268EA
0x180026898  mov     r13d, 5Ch ; '\'
0x18002689e  movzx   eax, word ptr [rsi]
0x1800268a1  cmp     ax, r13w
0x1800268a5  jz      short loc_1800268B3
0x1800268a7  add     rsi, 2
0x1800268ab  movzx   eax, word ptr [rsi]
0x1800268ae  test    ax, ax
0x1800268b1  jnz     short loc_1800268A1
0x1800268b3  cmp     [rsi], r12w
0x1800268b7  jz      short loc_1800268E3
0x1800268b9  mov     [rsi], r12w
0x1800268bd  lea     rdi, [rsi+2]
0x1800268c1  mov     rdx, r14
0x1800268c4  cmp     rdi, r15
0x1800268c7  cmovnz  rdx, r12; lpSecurityAttributes
0x1800268cb  lea     rcx, [rsp+2B0h+pszPath]; lpPathName
0x1800268d0  call    cs:__imp_CreateDirectoryW
0x1800268d6  mov     [rsi], r13w
0x1800268da  mov     rsi, rdi
0x1800268dd  cmp     [rdi], r12w
0x1800268e1  jnz     short loc_18002689E
0x1800268e3  lea     r13, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x1800268ea  mov     edi, r12d
0x1800268ed  mov     [rsp+2B0h+var_278], r13
0x1800268f2  lea     rcx, [rsp+2B0h+var_278]; this
0x1800268f7  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1800268fc  nop
0x1800268fd  mov     rcx, rbx; void *
0x180026900  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026905  mov     eax, edi
0x180026907  mov     rcx, [rbp+1B0h+var_40]
0x18002690e  xor     rcx, rsp; StackCookie
0x180026911  call    __security_check_cookie
0x180026916  mov     rbx, [rsp+2B0h+arg_18]
0x18002691e  add     rsp, 280h
0x180026925  pop     r15
0x180026927  pop     r14
0x180026929  pop     r13
0x18002692b  pop     r12
0x18002692d  pop     rdi
0x18002692e  pop     rsi
0x18002692f  pop     rbp
0x180026930  retn
```
