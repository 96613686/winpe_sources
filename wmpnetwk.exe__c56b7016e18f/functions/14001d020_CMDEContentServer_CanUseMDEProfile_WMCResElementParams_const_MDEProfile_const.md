# CMDEContentServer::CanUseMDEProfile(_WMCResElementParams const *,MDEProfile const *)

- ea: `0x14001d020`
- end: `0x14001d514`
- name: `?CanUseMDEProfile@CMDEContentServer@@AEAAHPEBU_WMCResElementParams@@PEBUMDEProfile@@@Z`
- size: `1268`
- prototype: `__int64 __fastcall(CMDEContentServer *__hidden this, const struct _WMCResElementParams *, const struct MDEProfile *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001bef0`
- `0x14001c430`

## callees

- `0x14001d020`
- `0x14001d520`
- `0x14001dfa0`
- `0x14003e4e0`
- `0x14004a834`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x14001d0ac`
- `KERNEL32!CompareStringOrdinal` at `0x14001d2fa`
- `KERNEL32!CompareStringOrdinal` at `0x14001d500`
- `KERNEL32!CompareStringOrdinal` at `0x14001d0ac`
- `KERNEL32!CompareStringOrdinal` at `0x14001d2fa`
- `KERNEL32!CompareStringOrdinal` at `0x14001d500`
- `KERNEL32!CompareStringW` at `0x14001d159`
- `KERNEL32!CompareStringW` at `0x14001d190`
- `KERNEL32!CompareStringW` at `0x14001d1c7`
- `KERNEL32!CompareStringW` at `0x14001d33b`
- `KERNEL32!CompareStringW` at `0x14001d423`
- `KERNEL32!CompareStringW` at `0x14001d4cb`
- `KERNEL32!CompareStringW` at `0x14001d159`
- `KERNEL32!CompareStringW` at `0x14001d190`
- `KERNEL32!CompareStringW` at `0x14001d1c7`
- `KERNEL32!CompareStringW` at `0x14001d33b`
- `KERNEL32!CompareStringW` at `0x14001d423`
- `KERNEL32!CompareStringW` at `0x14001d4cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14001d488`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14001d488`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::CanUseMDEProfile(
        CMDEContentServer *this,
        const struct _WMCResElementParams *a2,
        const struct MDEProfile *a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  const WCHAR *v8; // rcx
  unsigned __int64 v9; // rax
  int v10; // edx
  int v11; // eax
  int *v13; // rsi
  int v14; // r14d
  __int64 v15; // r12
  int v16; // esi
  __int64 v17; // rcx
  const WCHAR *v18; // rcx
  unsigned __int64 v19; // rax
  int v20; // edx
  int v21; // r14d
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  int v25; // eax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, a2, a3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = 0;
  if ( *((_DWORD *)this + 112) || *((_DWORD *)a3 + 14) != 1 )
  {
    v8 = *(const WCHAR **)a2;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = 6;
    if ( v9 < 6 )
      v10 = v9;
    if ( CompareStringOrdinal(v8, v10, L"video/", -1, 1) == 2 )
    {
      v18 = (const WCHAR *)*((_QWORD *)a3 + 4);
      v19 = -1;
      do
        ++v19;
      while ( v18[v19] );
      v20 = 6;
      if ( v19 < 6 )
        v20 = v19;
      if ( CompareStringOrdinal(v18, v20, L"audio/", -1, 1) == 2 )
        goto LABEL_10;
    }
    v11 = *((_DWORD *)a3 + 14);
    if ( v11 )
    {
      if ( v11 != 1 )
        goto LABEL_10;
      v13 = (int *)((char *)a2 + 128);
      v25 = *((_DWORD *)a2 + 32);
      if ( (v25 & 2) != 0
        && ((v25 & 0x40) == 0 || !*(_QWORD *)a2 || (unsigned int)_o__wcsnicmp(*(_QWORD *)a2, L"video/", 6)) )
      {
        goto LABEL_10;
      }
    }
    else
    {
      v13 = (int *)((char *)a2 + 128);
      if ( (*((_BYTE *)a2 + 128) & 1) != 0 )
        goto LABEL_10;
    }
    if ( (unsigned int)CMDEContentServer::ProfileMatchesMIME(a3, *(const unsigned __int16 **)a2) )
    {
      if ( *((_DWORD *)a3 + 5) )
      {
        v14 = *v13;
        v15 = *((_QWORD *)a2 + 4);
        if ( CompareStringW(0x7Fu, 1u, *((PCNZWCH *)a3 + 4), 6, L"image/", -1) == 2 )
        {
          if ( *(_QWORD *)a2 )
            CompareStringW(0x7Fu, 1u, *((PCNZWCH *)a3 + 4), -1, *(PCNZWCH *)a2, -1);
        }
        else if ( CompareStringW(0x7Fu, 1u, *((PCNZWCH *)a3 + 4), 6, L"audio/", -1) == 2 )
        {
          v16 = CompareStringW(0x7Fu, 1u, *((PCNZWCH *)a3 + 4), 9, L"audio/L16", -1);
          if ( !*((_DWORD *)a3 + 43) )
          {
            v17 = *(_QWORD *)&GUID_NULL.Data1 - *((_QWORD *)a2 + 12);
            if ( *(_QWORD *)&GUID_NULL.Data1 == *((_QWORD *)a2 + 12) )
              v17 = *(_QWORD *)GUID_NULL.Data4 - *((_QWORD *)a2 + 13);
            if ( !v17 )
              goto LABEL_79;
            v22 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)((char *)a3 + 140);
            if ( !v22 )
              v22 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)((char *)a3 + 148);
            if ( !v22 )
            {
LABEL_79:
              if ( *(_QWORD *)a2 )
                CompareStringW(0x7Fu, 1u, *((PCNZWCH *)a3 + 4), -1, *(PCNZWCH *)a2, -1);
            }
          }
          if ( v16 == 2 )
          {
            if ( (v14 & 0x10) != 0 && (*((_DWORD *)a3 + 22) != 44100 || *((_DWORD *)a2 + 22) != *((_DWORD *)a3 + 25)) )
              goto LABEL_10;
          }
          else if ( (v14 & 0x2000) != 0 && !v15 )
          {
            goto LABEL_10;
          }
        }
        else
        {
          v21 = v14 & 0x800;
          if ( !*((_DWORD *)a3 + 44) )
          {
            v23 = *(_QWORD *)&GUID_NULL.Data1 - *((_QWORD *)a2 + 14);
            if ( *(_QWORD *)&GUID_NULL.Data1 == *((_QWORD *)a2 + 14) )
              v23 = *(_QWORD *)GUID_NULL.Data4 - *((_QWORD *)a2 + 15);
            if ( !v23 )
              goto LABEL_80;
            v24 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)((char *)a3 + 156);
            if ( !v24 )
              v24 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)((char *)a3 + 164);
            if ( !v24 )
            {
LABEL_80:
              if ( *(_QWORD *)a2 )
                CompareStringW(0x7Fu, 1u, *((PCNZWCH *)a3 + 4), -1, *(PCNZWCH *)a2, -1);
            }
          }
          if ( v21
            || !*((_DWORD *)a3 + 45)
            && *((_DWORD *)a3 + 31) > 0x240u
            && *((_DWORD *)a2 + 18) <= 0x2D0u
            && *((_DWORD *)a2 + 19) <= 0x240u )
          {
            goto LABEL_10;
          }
        }
        if ( (*((_DWORD *)a2 + 32) & 0x4000) != 0
          && CompareStringOrdinal(*((LPCWCH *)a3 + 4), -1, L"video/mpeg", -1, 1) == 2
          || !CMDEContentServer::IsDecoderAvailable(this, a2, a3) )
        {
          goto LABEL_10;
        }
      }
      v7 = 1;
    }
LABEL_10:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_Dd(v6[2], 80, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, 0);
  return v7;
}

```

## disassembly

```asm
0x14001d020  push    rbx
0x14001d022  sub     rsp, 50h
0x14001d026  mov     [rsp+58h+arg_0], rbp
0x14001d02b  mov     rbp, r8
0x14001d02e  mov     [rsp+58h+arg_10], rdi
0x14001d033  mov     rdi, rdx
0x14001d036  mov     [rsp+58h+var_18], r13
0x14001d03b  mov     [rsp+58h+var_28], r15
0x14001d040  mov     r15, rcx
0x14001d043  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d04a  lea     r13, WPP_GLOBAL_Control
0x14001d051  cmp     rcx, r13
0x14001d054  jnz     loc_14001D24E
0x14001d05a  xor     ebx, ebx
0x14001d05c  cmp     [r15+1C0h], ebx
0x14001d063  jz      loc_14001D49B
0x14001d069  mov     rcx, [rdi]; lpString1
0x14001d06c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14001d073  inc     rax
0x14001d076  cmp     [rcx+rax*2], bx
0x14001d07a  jnz     short loc_14001D073
0x14001d07c  mov     edx, 6
0x14001d081  mov     [rsp+58h+arg_8], rsi
0x14001d086  cmp     rax, rdx
0x14001d089  mov     [rsp+58h+var_10], r12
0x14001d08e  mov     r9d, 0FFFFFFFFh; cchCount2
0x14001d094  mov     [rsp+58h+var_20], r14
0x14001d099  cmovb   rdx, rax; cchCount1
0x14001d09d  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x14001d0a5  lea     r8, aVideo; "video/"
0x14001d0ac  call    cs:__imp_CompareStringOrdinal
0x14001d0b2  cmp     eax, 2
0x14001d0b5  jz      loc_14001D2C0
0x14001d0bb  mov     eax, [rbp+38h]
0x14001d0be  test    eax, eax
0x14001d0c0  jz      short loc_14001D106
0x14001d0c2  cmp     eax, 1
0x14001d0c5  jz      loc_14001D456
0x14001d0cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0d2  mov     r12, [rsp+58h+var_10]
0x14001d0d7  mov     rsi, [rsp+58h+arg_8]
0x14001d0dc  mov     r14, [rsp+58h+var_20]
0x14001d0e1  mov     r15, [rsp+58h+var_28]
0x14001d0e6  mov     rdi, [rsp+58h+arg_10]
0x14001d0eb  mov     rbp, [rsp+58h+arg_0]
0x14001d0f0  cmp     rcx, r13
0x14001d0f3  mov     r13, [rsp+58h+var_18]
0x14001d0f8  jnz     loc_14001D28B
0x14001d0fe  mov     eax, ebx
0x14001d100  add     rsp, 50h
0x14001d104  pop     rbx
0x14001d105  retn
0x14001d106  lea     rsi, [rdi+80h]
0x14001d10d  test    byte ptr [rsi], 1
0x14001d110  jnz     short loc_14001D0CB
0x14001d112  mov     rdx, [rdi]; unsigned __int16 *
0x14001d115  mov     rcx, rbp; struct MDEProfile *
0x14001d118  call    ?ProfileMatchesMIME@CMDEContentServer@@CAHPEBUMDEProfile@@PEBG@Z; CMDEContentServer::ProfileMatchesMIME(MDEProfile const *,ushort const *)
0x14001d11d  test    eax, eax
0x14001d11f  jz      short loc_14001D0CB
0x14001d121  cmp     [rbp+14h], ebx
0x14001d124  jz      loc_14001D244
0x14001d12a  mov     r8, [rbp+20h]; lpString1
0x14001d12e  lea     rax, aImage; "image/"
0x14001d135  mov     r14d, [rsi]
0x14001d138  mov     r9d, 6; cchCount1
0x14001d13e  mov     r12, [rdi+20h]
0x14001d142  mov     edx, 1; dwCmpFlags
0x14001d147  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x14001d14f  mov     ecx, 7Fh; Locale
0x14001d154  mov     qword ptr [rsp+58h+bIgnoreCase], rax; lpString2
0x14001d159  call    cs:__imp_CompareStringW
0x14001d15f  cmp     eax, 2
0x14001d162  jz      loc_14001D30E
0x14001d168  mov     r8, [rbp+20h]; lpString1
0x14001d16c  lea     rax, aAudio_0; "audio/"
0x14001d173  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x14001d17b  mov     r9d, 6; cchCount1
0x14001d181  mov     edx, 1; dwCmpFlags
0x14001d186  mov     qword ptr [rsp+58h+bIgnoreCase], rax; lpString2
0x14001d18b  mov     ecx, 7Fh; Locale
0x14001d190  call    cs:__imp_CompareStringW
0x14001d196  cmp     eax, 2
0x14001d199  jnz     loc_14001D346
0x14001d19f  mov     r8, [rbp+20h]; lpString1
0x14001d1a3  lea     rax, aAudioL16_1; "audio/L16"
0x14001d1aa  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x14001d1b2  mov     r9d, 9; cchCount1
0x14001d1b8  mov     edx, 1; dwCmpFlags
0x14001d1bd  mov     qword ptr [rsp+58h+bIgnoreCase], rax; lpString2
0x14001d1c2  mov     ecx, 7Fh; Locale
0x14001d1c7  call    cs:__imp_CompareStringW
0x14001d1cd  mov     esi, eax
0x14001d1cf  cmp     [rbp+0ACh], ebx
0x14001d1d5  jnz     short loc_14001D20A
0x14001d1d7  mov     rdx, qword ptr cs:GUID_NULL.Data1
0x14001d1de  mov     r8, qword ptr cs:GUID_NULL.Data4
0x14001d1e5  mov     rcx, rdx
0x14001d1e8  sub     rcx, [rdi+60h]
0x14001d1ec  jnz     short loc_14001D1F5
0x14001d1ee  mov     rcx, r8
0x14001d1f1  sub     rcx, [rdi+68h]
0x14001d1f5  test    rcx, rcx
0x14001d1f8  jnz     loc_14001D396
0x14001d1fe  mov     rax, [rdi]
0x14001d201  test    rax, rax
0x14001d204  jnz     loc_14001D4AA
0x14001d20a  cmp     esi, 2
0x14001d20d  jz      loc_14001D42E
0x14001d213  bt      r14d, 0Dh
0x14001d218  jb      loc_14001D4D6
0x14001d21e  test    dword ptr [rdi+80h], 4000h
0x14001d228  jnz     loc_14001D4E4
0x14001d22e  mov     r8, rbp; struct MDEProfile *
0x14001d231  mov     rdx, rdi; struct _WMCResElementParams *
0x14001d234  mov     rcx, r15; this
0x14001d237  call    ?IsDecoderAvailable@CMDEContentServer@@AEAA_NPEBU_WMCResElementParams@@PEBUMDEProfile@@@Z; CMDEContentServer::IsDecoderAvailable(_WMCResElementParams const *,MDEProfile const *)
0x14001d23c  test    al, al
0x14001d23e  jz      loc_14001D0CB
0x14001d244  mov     ebx, 1
0x14001d249  jmp     loc_14001D0CB
0x14001d24e  test    byte ptr [rcx+1Ch], 1
0x14001d252  jz      loc_14001D05A
0x14001d258  cmp     byte ptr [rcx+19h], 5
0x14001d25c  jb      loc_14001D05A
0x14001d262  mov     rcx, [rcx+10h]
0x14001d266  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14001d26d  mov     edx, 4Fh ; 'O'
0x14001d272  mov     qword ptr [rsp+58h+bIgnoreCase], rbp
0x14001d277  mov     r9, rdi
0x14001d27a  call    WPP_SF_qq
0x14001d27f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d286  jmp     loc_14001D05A
0x14001d28b  test    byte ptr [rcx+1Ch], 1
0x14001d28f  jz      loc_14001D0FE
0x14001d295  cmp     byte ptr [rcx+19h], 5
0x14001d299  jb      loc_14001D0FE
0x14001d29f  mov     rcx, [rcx+10h]
0x14001d2a3  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14001d2aa  mov     edx, 50h ; 'P'
0x14001d2af  mov     [rsp+58h+bIgnoreCase], ebx
0x14001d2b3  xor     r9d, r9d
0x14001d2b6  call    WPP_SF_Dd
0x14001d2bb  jmp     loc_14001D0FE
0x14001d2c0  mov     rcx, [rbp+20h]; lpString1
0x14001d2c4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14001d2cb  nop     dword ptr [rax+rax+00h]
0x14001d2d0  inc     rax
0x14001d2d3  cmp     [rcx+rax*2], bx
0x14001d2d7  jnz     short loc_14001D2D0
0x14001d2d9  mov     edx, 6
0x14001d2de  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x14001d2e6  cmp     rax, rdx
0x14001d2e9  lea     r8, aAudio_0; "audio/"
0x14001d2f0  mov     r9d, 0FFFFFFFFh; cchCount2
0x14001d2f6  cmovb   rdx, rax; cchCount1
0x14001d2fa  call    cs:__imp_CompareStringOrdinal
0x14001d300  cmp     eax, 2
0x14001d303  jz      loc_14001D0CB
0x14001d309  jmp     loc_14001D0BB
0x14001d30e  mov     rax, [rdi]
0x14001d311  test    rax, rax
0x14001d314  jz      loc_14001D21E
0x14001d31a  mov     r8, [rbp+20h]; lpString1
0x14001d31e  mov     r9d, 0FFFFFFFFh; cchCount1
0x14001d324  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x14001d32c  mov     edx, 1; dwCmpFlags
0x14001d331  mov     ecx, 7Fh; Locale
0x14001d336  mov     qword ptr [rsp+58h+bIgnoreCase], rax; lpString2
0x14001d33b  call    cs:__imp_CompareStringW
0x14001d341  jmp     loc_14001D21E
0x14001d346  and     r14d, 800h
0x14001d34d  cmp     [rbp+0B0h], ebx
0x14001d353  jz      short loc_14001D3B7
0x14001d355  test    r14d, r14d
0x14001d358  jnz     loc_14001D0CB
0x14001d35e  cmp     [rbp+0B4h], ebx
0x14001d364  jnz     loc_14001D21E
0x14001d36a  cmp     dword ptr [rbp+7Ch], 240h
0x14001d371  jbe     loc_14001D21E
0x14001d377  cmp     dword ptr [rdi+48h], 2D0h
0x14001d37e  ja      loc_14001D21E
0x14001d384  cmp     dword ptr [rdi+4Ch], 240h
0x14001d38b  jbe     loc_14001D0CB
0x14001d391  jmp     loc_14001D21E
0x14001d396  sub     rdx, [rbp+8Ch]
0x14001d39d  jnz     short loc_14001D3A9
0x14001d39f  mov     rdx, r8
0x14001d3a2  sub     rdx, [rbp+94h]
0x14001d3a9  test    rdx, rdx
0x14001d3ac  jz      loc_14001D1FE
0x14001d3b2  jmp     loc_14001D20A
0x14001d3b7  mov     rax, qword ptr cs:GUID_NULL.Data1
0x14001d3be  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x14001d3c5  mov     rcx, rax
0x14001d3c8  sub     rcx, [rdi+70h]
0x14001d3cc  jnz     short loc_14001D3D5
0x14001d3ce  mov     rcx, rdx
0x14001d3d1  sub     rcx, [rdi+78h]
0x14001d3d5  test    rcx, rcx
0x14001d3d8  jz      short loc_14001D3F6
0x14001d3da  sub     rax, [rbp+9Ch]
0x14001d3e1  jnz     short loc_14001D3ED
0x14001d3e3  mov     rax, rdx
0x14001d3e6  sub     rax, [rbp+0A4h]
0x14001d3ed  test    rax, rax
0x14001d3f0  jnz     loc_14001D355
0x14001d3f6  mov     rax, [rdi]
0x14001d3f9  test    rax, rax
0x14001d3fc  jz      loc_14001D355
0x14001d402  mov     r8, [rbp+20h]; lpString1
0x14001d406  mov     r9d, 0FFFFFFFFh; cchCount1
0x14001d40c  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x14001d414  mov     edx, 1; dwCmpFlags
0x14001d419  mov     ecx, 7Fh; Locale
0x14001d41e  mov     qword ptr [rsp+58h+bIgnoreCase], rax; lpString2
0x14001d423  call    cs:__imp_CompareStringW
0x14001d429  jmp     loc_14001D355
0x14001d42e  test    r14b, 10h
0x14001d432  jz      loc_14001D21E
0x14001d438  cmp     dword ptr [rbp+58h], 0AC44h
0x14001d43f  jnz     loc_14001D0CB
0x14001d445  mov     eax, [rbp+64h]
0x14001d448  cmp     [rdi+58h], eax
0x14001d44b  jz      loc_14001D21E
0x14001d451  jmp     loc_14001D0CB
0x14001d456  lea     rsi, [rdi+80h]
0x14001d45d  mov     eax, [rsi]
0x14001d45f  test    al, 2
0x14001d461  jz      loc_14001D112
0x14001d467  test    al, 40h
0x14001d469  jz      loc_14001D0CB
0x14001d46f  mov     rcx, [rdi]
0x14001d472  test    rcx, rcx
0x14001d475  jz      loc_14001D0CB
0x14001d47b  mov     r8d, 6
0x14001d481  lea     rdx, aVideo; "video/"
0x14001d488  call    cs:__imp__o__wcsnicmp
0x14001d48e  test    eax, eax
0x14001d490  jnz     loc_14001D0CB
0x14001d496  jmp     loc_14001D112
0x14001d49b  cmp     dword ptr [rbp+38h], 1
0x14001d49f  jz      loc_14001D0E1
0x14001d4a5  jmp     loc_14001D069
0x14001d4aa  mov     r8, [rbp+20h]; lpString1
0x14001d4ae  mov     r9d, 0FFFFFFFFh; cchCount1
0x14001d4b4  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x14001d4bc  mov     edx, 1; dwCmpFlags
0x14001d4c1  mov     ecx, 7Fh; Locale
0x14001d4c6  mov     qword ptr [rsp+58h+bIgnoreCase], rax; lpString2
0x14001d4cb  call    cs:__imp_CompareStringW
0x14001d4d1  jmp     loc_14001D20A
0x14001d4d6  test    r12, r12
0x14001d4d9  jnz     loc_14001D21E
0x14001d4df  jmp     loc_14001D0CB
0x14001d4e4  mov     rcx, [rbp+20h]; lpString1
0x14001d4e8  lea     r8, aVideoMpeg; "video/mpeg"
0x14001d4ef  mov     r9d, 0FFFFFFFFh; cchCount2
0x14001d4f5  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x14001d4fd  mov     edx, r9d; cchCount1
0x14001d500  call    cs:__imp_CompareStringOrdinal
0x14001d506  cmp     eax, 2
0x14001d509  jz      loc_14001D0CB
0x14001d50f  jmp     loc_14001D22E
```
