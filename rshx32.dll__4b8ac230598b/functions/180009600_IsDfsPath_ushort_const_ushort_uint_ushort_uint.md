# IsDfsPath(ushort const *,ushort *,uint,ushort *,uint)

- ea: `0x180009600`
- end: `0x180009b50`
- name: `?IsDfsPath@@YAHPEBGPEAGI1I@Z`
- size: `1360`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, int, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180009148`
- `0x18000b6b4`

## callees

- `0x180005610`
- `0x180005684`
- `0x180009600`
- `0x18001d370`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000992b`
- `msvcrt!_wcsicmp` at `0x18000992b`
- `SHLWAPI!PathIsUNCW` at `0x18000964a`
- `SHLWAPI!PathIsUNCW` at `0x18000964a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000993a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000993a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800098df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800099d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800098df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800099d1`
- `dfscli!NetDfsGetClientInfo` at `0x1800096d2`
- `dfscli!NetDfsGetClientInfo` at `0x180009a93`
- `dfscli!NetDfsGetClientInfo` at `0x1800096d2`
- `dfscli!NetDfsGetClientInfo` at `0x180009a93`
- `netutils!NetApiBufferFree` at `0x180009889`
- `netutils!NetApiBufferFree` at `0x180009b15`
- `netutils!NetApiBufferFree` at `0x180009b23`
- `netutils!NetApiBufferFree` at `0x180009889`
- `netutils!NetApiBufferFree` at `0x180009b15`
- `netutils!NetApiBufferFree` at `0x180009b23`

## pseudocode

```c
__int64 __fastcall IsDfsPath(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned __int8 v5; // r13
  unsigned __int8 v6; // si
  const unsigned __int16 *v7; // rbx
  WCHAR *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  int v12; // ebx
  const wchar_t **v13; // r12
  LPBYTE v14; // rdx
  char v15; // r9
  unsigned __int16 v16; // r8
  _WORD *v17; // rcx
  unsigned __int16 *v18; // r15
  unsigned int v19; // r9d
  __int64 v20; // r10
  unsigned int v21; // r8d
  __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // r10
  __int64 v25; // r9
  _WORD *v26; // r11
  char *v27; // rax
  char *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // r9
  unsigned __int16 *v32; // r10
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // r14
  __int64 v37; // r15
  __int64 v38; // rax
  __int64 v39; // rcx
  unsigned __int64 v40; // rsi
  unsigned __int16 *v41; // rbx
  bool v42; // di
  const unsigned __int16 *v43; // r8
  int v44; // esi
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rsi
  int v48; // r13d
  __int64 v49; // rdx
  __int64 v50; // rax
  unsigned __int64 v51; // rdi
  unsigned __int16 *v52; // rax
  unsigned __int16 *v53; // rbx
  signed int v54; // edi
  __int64 v55; // rcx
  WCHAR *v56; // rax
  WCHAR *v57; // r8
  __int64 v58; // rdx
  WCHAR *v59; // rcx
  DWORD ClientInfo; // eax
  char v62; // [rsp+30h] [rbp-D0h]
  LPBYTE Buffer; // [rsp+38h] [rbp-C8h] BYREF
  int v64; // [rsp+40h] [rbp-C0h]
  int v65; // [rsp+44h] [rbp-BCh]
  unsigned __int64 v66; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v67; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v68; // [rsp+58h] [rbp-A8h]
  WCHAR DfsEntryPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v70[2]; // [rsp+270h] [rbp+170h] BYREF
  char v71; // [rsp+274h] [rbp+174h] BYREF
  unsigned __int16 v72[264]; // [rsp+480h] [rbp+380h] BYREF

  v5 = 0;
  v68 = a4;
  v6 = 0;
  v62 = 0;
  LODWORD(v66) = a3;
  v7 = a1;
  v67 = a2;
  if ( PathIsUNCW(a1) )
  {
    Buffer = 0;
    v8 = DfsEntryPath;
    v9 = 2147483646;
    v10 = 260;
    do
    {
      if ( !v9 )
        break;
      if ( !*v7 )
        break;
      *v8++ = *v7++;
      --v9;
      --v10;
    }
    while ( v10 );
    v11 = v8 - 1;
    if ( v10 )
      v11 = v8;
    *v11 = 0;
    if ( v10 )
    {
      LOBYTE(v64) = 0;
      v12 = 0;
      v13 = 0;
      if ( NetDfsGetClientInfo(DfsEntryPath, 0, 0, 3u, &Buffer) )
      {
LABEL_83:
        v14 = Buffer;
      }
      else
      {
        while ( 1 )
        {
          v14 = Buffer;
          v15 = 0;
          v16 = 0;
          v17 = *(_WORD **)Buffer;
          if ( **(_WORD **)Buffer == 92 && v17[1] != 92 )
            v5 = 1;
          do
          {
            if ( !*v17 )
              break;
            if ( *v17 == 92 )
            {
              v15 = 1;
            }
            else if ( v15 )
            {
              ++v16;
              v15 = 0;
            }
            ++v17;
          }
          while ( v16 <= 2u );
          v18 = v68;
          if ( v16 == 2 )
          {
            v65 = v12 + 1;
            if ( (unsigned int)(v12 + 1) > 2 )
              break;
          }
          else
          {
            v65 = 0;
          }
          v19 = 0;
          if ( *((_DWORD *)Buffer + 5) )
          {
            v20 = *((_QWORD *)Buffer + 3);
            v21 = 0;
            while ( 1 )
            {
              if ( (*(_BYTE *)(v20 + 24LL * v21) & 2) != 0 )
              {
                v6 = 1;
                v62 = 1;
                v19 = v21;
                if ( (*(_BYTE *)(v20 + 24LL * v21) & 4) != 0 )
                  break;
              }
              if ( ++v21 >= *((_DWORD *)Buffer + 5) )
                goto LABEL_28;
            }
          }
          else
          {
LABEL_28:
            if ( !v6 )
              break;
          }
          v22 = v19;
          if ( v67 )
          {
            v23 = *((_QWORD *)Buffer + 3);
            *(_DWORD *)v70 = 6029404;
            v24 = 2147483646;
            v25 = 258;
            v26 = *(_WORD **)(v23 + 24 * v22 + 8);
            v27 = &v71;
            do
            {
              if ( !v24 )
                break;
              if ( !*v26 )
                break;
              *(_WORD *)v27 = *v26++;
              v27 += 2;
              --v24;
              --v25;
            }
            while ( v25 );
            v28 = v27 - 2;
            if ( v25 )
              v28 = v27;
            *(_WORD *)v28 = 0;
          }
          v29 = 24 * v22;
          if ( v18 )
          {
            v30 = 2147483646;
            v31 = 260;
            v32 = *(unsigned __int16 **)(*((_QWORD *)v14 + 3) + v29 + 16);
            v33 = v72;
            do
            {
              if ( !v30 )
                break;
              if ( !*v32 )
                break;
              *v33++ = *v32++;
              --v30;
              --v31;
            }
            while ( v31 );
            v34 = v33 - 1;
            if ( v31 )
              v34 = v33;
            *v34 = 0;
          }
          v35 = *((_QWORD *)v14 + 3);
          v36 = *(_QWORD *)(v35 + v29 + 8);
          v37 = *(_QWORD *)(v35 + v29 + 16);
          if ( v13 )
          {
            NetApiBufferFree(v13);
            v14 = Buffer;
          }
          v13 = (const wchar_t **)v14;
          v14 = 0;
          Buffer = 0;
          if ( (_BYTE)v64 )
            break;
          v38 = -1;
          v39 = -1;
          do
            ++v39;
          while ( *(_WORD *)(v36 + 2 * v39) );
          do
            ++v38;
          while ( *(_WORD *)(v37 + 2 * v38) );
          v40 = v39 + (v5 ^ 1LL) + v38 + 3;
          v41 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v40);
          if ( !v41 )
            goto LABEL_85;
          v42 = 0;
          v43 = L"\\%s\\%s";
          if ( !v5 )
            v43 = L"\\\\%s\\%s";
          v44 = StringCchPrintfW(v41, v40, v43, v36, v37);
          if ( v44 >= 0 )
            v42 = _wcsicmp(v41, *v13) == 0;
          LocalFree(v41);
          if ( v44 < 0 )
          {
LABEL_85:
            v6 = v62;
            goto LABEL_83;
          }
          if ( v42 )
          {
            v14 = Buffer;
            break;
          }
          v45 = -1;
          do
            ++v45;
          while ( DfsEntryPath[v45] );
          v46 = -1;
          do
            ++v46;
          while ( (*v13)[v46] );
          v47 = v5 + v46;
          v48 = (unsigned __int8)v64;
          v49 = -1;
          if ( v45 == v47 )
            v48 = 1;
          v64 = v48;
          v5 = 0;
          do
            ++v49;
          while ( *(_WORD *)(v36 + 2 * v49) );
          v50 = -1;
          do
            ++v50;
          while ( *(_WORD *)(v37 + 2 * v50) );
          v51 = v49 + 4 + v50 + v45 - v47;
          v52 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v51);
          v53 = v52;
          if ( !v52 )
            goto LABEL_85;
          v54 = StringCchPrintfW(v52, v51, L"\\\\%s\\%s%s", v36, v37, &DfsEntryPath[v47]);
          if ( v54 >= 0 )
          {
            v55 = 2147483646;
            v56 = DfsEntryPath;
            v57 = v53;
            v58 = 260;
            do
            {
              if ( !v55 )
                break;
              if ( !*v57 )
                break;
              *v56++ = *v57++;
              --v55;
              --v58;
            }
            while ( v58 );
            v59 = v56 - 1;
            if ( v58 )
              v59 = v56;
            v54 = v58 == 0 ? 0x8007007A : 0;
            *v59 = 0;
          }
          LocalFree(v53);
          if ( v54 < 0 )
            goto LABEL_85;
          ClientInfo = NetDfsGetClientInfo(DfsEntryPath, 0, 0, 3u, &Buffer);
          v6 = v62;
          v12 = v65;
          if ( ClientInfo )
          {
            v14 = Buffer;
            break;
          }
        }
        v6 = v62;
        if ( v62 && v13 )
        {
          StringCchCopyW(v67, (unsigned int)v66, v70);
          StringCchCopyW(v68, a5, v72);
          goto LABEL_83;
        }
      }
      if ( v14 )
        NetApiBufferFree(v14);
      if ( v13 )
        NetApiBufferFree(v13);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180009600  push    rbp
0x180009602  push    rbx
0x180009603  push    rsi
0x180009604  push    rdi
0x180009605  push    r12
0x180009607  push    r13
0x180009609  push    r14
0x18000960b  push    r15
0x18000960d  lea     rbp, [rsp-5A8h]
0x180009615  sub     rsp, 6A8h
0x18000961c  mov     rax, cs:__security_cookie
0x180009623  xor     rax, rsp
0x180009626  mov     [rbp+5E0h+var_50], rax
0x18000962d  xor     r13d, r13d
0x180009630  mov     [rsp+6E0h+var_688], r9
0x180009635  mov     sil, r13b
0x180009638  mov     [rsp+6E0h+var_6B0], r13b
0x18000963d  mov     dword ptr [rsp+6E0h+var_698], r8d
0x180009642  mov     rbx, rcx
0x180009645  mov     [rsp+6E0h+var_690], rdx
0x18000964a  call    cs:__imp_PathIsUNCW
0x180009650  test    eax, eax
0x180009652  jz      loc_180009B29
0x180009658  mov     [rsp+6E0h+var_6A8], r13
0x18000965d  lea     rax, [rsp+6E0h+DfsEntryPath]
0x180009662  mov     ecx, 7FFFFFFEh
0x180009667  lea     r10d, [r13+2]
0x18000966b  mov     edx, 104h
0x180009670  lea     r9d, [r13+1]
0x180009674  test    rcx, rcx
0x180009677  jz      short loc_180009695
0x180009679  movzx   r8d, word ptr [rbx]
0x18000967d  test    r8w, r8w
0x180009681  jz      short loc_180009695
0x180009683  mov     [rax], r8w
0x180009687  add     rbx, r10
0x18000968a  add     rax, r10
0x18000968d  sub     rcx, r9
0x180009690  sub     rdx, r9
0x180009693  jnz     short loc_180009674
0x180009695  test    rdx, rdx
0x180009698  lea     rcx, [rax-2]
0x18000969c  cmovnz  rcx, rax
0x1800096a0  mov     [rcx], r13w
0x1800096a4  jz      loc_180009B29
0x1800096aa  lea     rax, [rsp+6E0h+var_6A8]
0x1800096af  mov     byte ptr [rsp+6E0h+var_6A0], r13b
0x1800096b4  mov     r9d, 3; Level
0x1800096ba  mov     [rsp+6E0h+Buffer], rax; Buffer
0x1800096bf  xor     r8d, r8d; ShareName
0x1800096c2  lea     rcx, [rsp+6E0h+DfsEntryPath]; DfsEntryPath
0x1800096c7  xor     edx, edx; ServerName
0x1800096c9  mov     ebx, r13d
0x1800096cc  mov     r12, r13
0x1800096cf  mov     edi, r13d
0x1800096d2  call    cs:__imp_NetDfsGetClientInfo
0x1800096d8  test    eax, eax
0x1800096da  jnz     loc_180009AF3
0x1800096e0  mov     eax, 5Ch ; '\'
0x1800096e5  mov     rdx, [rsp+6E0h+var_6A8]
0x1800096ea  mov     r9b, r13b
0x1800096ed  mov     r8d, r13d
0x1800096f0  mov     rcx, [rdx]
0x1800096f3  cmp     ax, [rcx]
0x1800096f6  jnz     short loc_180009709
0x1800096f8  cmp     ax, [rcx+2]
0x1800096fc  jz      short loc_180009709
0x1800096fe  mov     r11d, 1
0x180009704  mov     r13b, r11b
0x180009707  jmp     short loc_18000970F
0x180009709  mov     r11d, 1
0x18000970f  xor     r10d, r10d
0x180009712  lea     r15d, [r10+2]
0x180009716  lea     r14d, [r10+5Ch]
0x18000971a  cmp     r10w, [rcx]
0x18000971e  jz      short loc_180009740
0x180009720  cmp     r14w, [rcx]
0x180009724  jnz     short loc_18000972B
0x180009726  mov     r9b, r11b
0x180009729  jmp     short loc_180009737
0x18000972b  test    r9b, r9b
0x18000972e  jz      short loc_180009737
0x180009730  add     r8w, r11w
0x180009734  mov     r9b, r10b
0x180009737  add     rcx, r15
0x18000973a  cmp     r8w, r15w
0x18000973e  jbe     short loc_18000971A
0x180009740  mov     r14, [rsp+6E0h+var_690]
0x180009745  cmp     r8w, r15w
0x180009749  mov     r15, [rsp+6E0h+var_688]
0x18000974e  jnz     short loc_180009763
0x180009750  inc     ebx
0x180009752  mov     [rsp+6E0h+var_69C], ebx
0x180009756  cmp     ebx, 2
0x180009759  ja      loc_180009AB4
0x18000975f  xor     ebx, ebx
0x180009761  jmp     short loc_180009769
0x180009763  xor     ebx, ebx
0x180009765  mov     [rsp+6E0h+var_69C], ebx
0x180009769  mov     r9d, ebx
0x18000976c  cmp     [rdx+14h], ebx
0x18000976f  jbe     short loc_1800097A1
0x180009771  mov     r10, [rdx+18h]
0x180009775  mov     r8d, ebx
0x180009778  mov     eax, r8d
0x18000977b  lea     rcx, [rax+rax*2]
0x18000977f  test    byte ptr [r10+rcx*8], 2
0x180009784  jz      short loc_180009798
0x180009786  test    byte ptr [r10+rcx*8], 4
0x18000978b  mov     sil, r11b
0x18000978e  mov     [rsp+6E0h+var_6B0], r11b
0x180009793  mov     r9d, r8d
0x180009796  jnz     short loc_1800097AA
0x180009798  add     r8d, r11d
0x18000979b  cmp     r8d, [rdx+14h]
0x18000979f  jb      short loc_180009778
0x1800097a1  test    sil, sil
0x1800097a4  jz      loc_180009AB4
0x1800097aa  mov     r8d, r9d
0x1800097ad  test    r14, r14
0x1800097b0  jz      short loc_180009810
0x1800097b2  mov     rax, [rdx+18h]
0x1800097b6  lea     rcx, [r8+r8*2]
0x1800097ba  mov     dword ptr [rbp+5E0h+var_470], 5C005Ch
0x1800097c4  mov     r10d, 7FFFFFFEh
0x1800097ca  mov     r9d, 102h
0x1800097d0  mov     r11, [rax+rcx*8+8]
0x1800097d5  lea     rax, [rbp+5E0h+var_46C]
0x1800097dc  test    r10, r10
0x1800097df  jz      short loc_180009802
0x1800097e1  movzx   ecx, word ptr [r11]
0x1800097e5  test    cx, cx
0x1800097e8  jz      short loc_180009802
0x1800097ea  mov     [rax], cx
0x1800097ed  add     r11, 2
0x1800097f1  mov     ecx, 1
0x1800097f6  add     rax, 2
0x1800097fa  sub     r10, rcx
0x1800097fd  sub     r9, rcx
0x180009800  jnz     short loc_1800097DC
0x180009802  test    r9, r9
0x180009805  lea     rcx, [rax-2]
0x180009809  cmovnz  rcx, rax
0x18000980d  mov     [rcx], bx
0x180009810  lea     rax, [r8+r8*2]
0x180009814  lea     r8, ds:0[rax*8]
0x18000981c  test    r15, r15
0x18000981f  jz      short loc_180009873
0x180009821  mov     rax, [rdx+18h]
0x180009825  mov     ecx, 7FFFFFFEh
0x18000982a  mov     r9d, 104h
0x180009830  mov     r10, [rax+r8+10h]
0x180009835  lea     rax, [rbp+5E0h+var_260]
0x18000983c  test    rcx, rcx
0x18000983f  jz      short loc_180009865
0x180009841  movzx   r11d, word ptr [r10]
0x180009845  test    r11w, r11w
0x180009849  jz      short loc_180009865
0x18000984b  mov     [rax], r11w
0x18000984f  add     r10, 2
0x180009853  mov     r11d, 1
0x180009859  add     rax, 2
0x18000985d  sub     rcx, r11
0x180009860  sub     r9, r11
0x180009863  jnz     short loc_18000983C
0x180009865  test    r9, r9
0x180009868  lea     rcx, [rax-2]
0x18000986c  cmovnz  rcx, rax
0x180009870  mov     [rcx], bx
0x180009873  mov     rax, [rdx+18h]
0x180009877  mov     r14, [rax+r8+8]
0x18000987c  mov     r15, [rax+r8+10h]
0x180009881  test    r12, r12
0x180009884  jz      short loc_180009894
0x180009886  mov     rcx, r12; Buffer
0x180009889  call    cs:__imp_NetApiBufferFree
0x18000988f  mov     rdx, [rsp+6E0h+var_6A8]
0x180009894  mov     r12, rdx
0x180009897  mov     rdx, rbx
0x18000989a  mov     [rsp+6E0h+var_6A8], rbx
0x18000989f  cmp     byte ptr [rsp+6E0h+var_6A0], bl
0x1800098a3  jnz     loc_180009AB4
0x1800098a9  movzx   edx, r13b
0x1800098ad  xor     rdx, 1
0x1800098b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800098b5  mov     rcx, rax
0x1800098b8  inc     rcx
0x1800098bb  cmp     [r14+rcx*2], bx
0x1800098c0  jnz     short loc_1800098B8
0x1800098c2  inc     rax
0x1800098c5  cmp     [r15+rax*2], bx
0x1800098ca  jnz     short loc_1800098C2
0x1800098cc  lea     rsi, [rax+3]
0x1800098d0  add     rsi, rdx
0x1800098d3  add     rsi, rcx
0x1800098d6  mov     ecx, 40h ; '@'; uFlags
0x1800098db  lea     rdx, [rsi+rsi]; uBytes
0x1800098df  call    cs:__imp_LocalAlloc
0x1800098e5  xor     ecx, ecx
0x1800098e7  mov     rbx, rax
0x1800098ea  test    rax, rax
0x1800098ed  jz      loc_180009B01
0x1800098f3  lea     rax, aSS; "\\\\%s\\%s"
0x1800098fa  mov     [rsp+6E0h+Buffer], r15
0x1800098ff  mov     dil, cl
0x180009902  lea     r8, aSS_0; "\\%s\\%s"
0x180009909  test    r13b, r13b
0x18000990c  mov     r9, r14
0x18000990f  mov     rdx, rsi; unsigned __int64
0x180009912  mov     rcx, rbx; unsigned __int16 *
0x180009915  cmovz   r8, rax; unsigned __int16 *
0x180009919  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000991e  mov     esi, eax
0x180009920  test    eax, eax
0x180009922  js      short loc_180009937
0x180009924  mov     rdx, [r12]; String2
0x180009928  mov     rcx, rbx; String1
0x18000992b  call    cs:__imp__wcsicmp
0x180009931  test    eax, eax
0x180009933  setz    dil
0x180009937  mov     rcx, rbx; hMem
0x18000993a  call    cs:__imp_LocalFree
0x180009940  xor     r9d, r9d
0x180009943  test    esi, esi
0x180009945  js      loc_180009B01
0x18000994b  test    dil, dil
0x18000994e  jnz     loc_180009AFA
0x180009954  or      r10, 0FFFFFFFFFFFFFFFFh
0x180009958  lea     rax, [rsp+6E0h+DfsEntryPath]
0x18000995d  mov     rcx, r10
0x180009960  inc     rcx
0x180009963  cmp     [rax+rcx*2], r9w
0x180009968  jnz     short loc_180009960
0x18000996a  mov     rdx, [r12]
0x18000996e  mov     rax, r10
0x180009971  movzx   r8d, r13b
0x180009975  inc     rax
0x180009978  cmp     [rdx+rax*2], r9w
0x18000997d  jnz     short loc_180009975
0x18000997f  mov     r13d, [rsp+6E0h+var_6A0]
0x180009984  lea     rsi, [r8+rax]
0x180009988  cmp     rcx, rsi
0x18000998b  movzx   r13d, r13b
0x18000998f  mov     eax, 1
0x180009994  mov     rdx, r10
0x180009997  cmovz   r13d, eax
0x18000999b  mov     [rsp+6E0h+var_6A0], r13d
0x1800099a0  xor     r13d, r13d
0x1800099a3  inc     rdx
0x1800099a6  cmp     [r14+rdx*2], r13w
0x1800099ab  jnz     short loc_1800099A3
0x1800099ad  mov     rax, r10
0x1800099b0  inc     rax
0x1800099b3  cmp     [r15+rax*2], r13w
0x1800099b8  jnz     short loc_1800099B0
0x1800099ba  sub     rcx, rsi
0x1800099bd  add     rdx, 4
0x1800099c1  lea     rdi, [rax+rcx]
0x1800099c5  mov     ecx, 40h ; '@'; uFlags
0x1800099ca  add     rdi, rdx
0x1800099cd  lea     rdx, [rdi+rdi]; uBytes
0x1800099d1  call    cs:__imp_LocalAlloc
0x1800099d7  mov     rbx, rax
0x1800099da  test    rax, rax
0x1800099dd  jz      loc_180009B01
0x1800099e3  lea     rcx, [rsp+6E0h+DfsEntryPath]
0x1800099e8  mov     r9, r14
0x1800099eb  lea     rcx, [rcx+rsi*2]
0x1800099ef  mov     rdx, rdi; unsigned __int64
0x1800099f2  mov     [rsp+6E0h+var_6B8], rcx
0x1800099f7  lea     r8, aSSS; "\\\\%s\\%s%s"
0x1800099fe  mov     rcx, rax; unsigned __int16 *
0x180009a01  mov     [rsp+6E0h+Buffer], r15
0x180009a06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009a0b  mov     edi, eax
0x180009a0d  test    eax, eax
0x180009a0f  js      short loc_180009A68
0x180009a11  mov     ecx, 7FFFFFFEh
0x180009a16  lea     rax, [rsp+6E0h+DfsEntryPath]
0x180009a1b  mov     r8, rbx
0x180009a1e  mov     edx, 104h
0x180009a23  test    rcx, rcx
0x180009a26  jz      short loc_180009A4C
0x180009a28  movzx   r9d, word ptr [r8]
0x180009a2c  test    r9w, r9w
0x180009a30  jz      short loc_180009A4C
0x180009a32  mov     [rax], r9w
0x180009a36  add     r8, 2
0x180009a3a  mov     r9d, 1
0x180009a40  add     rax, 2
0x180009a44  sub     rcx, r9
0x180009a47  sub     rdx, r9
0x180009a4a  jnz     short loc_180009A23
0x180009a4c  test    rdx, rdx
0x180009a4f  lea     rcx, [rax-2]
0x180009a53  cmovnz  rcx, rax
0x180009a57  neg     rdx
0x180009a5a  sbb     edi, edi
0x180009a5c  not     edi
0x180009a5e  and     edi, 8007007Ah
  ... truncated ...
```
