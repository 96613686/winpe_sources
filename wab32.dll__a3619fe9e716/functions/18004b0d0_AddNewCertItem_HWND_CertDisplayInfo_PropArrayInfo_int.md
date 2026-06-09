# AddNewCertItem(HWND__ *,_CertDisplayInfo *,_PropArrayInfo *,int)

- ea: `0x18004b0d0`
- end: `0x18004b410`
- name: `?AddNewCertItem@@YAHPEAUHWND__@@PEAU_CertDisplayInfo@@PEAU_PropArrayInfo@@H@Z`
- size: `832`
- prototype: `__int64 __fastcall(HWND, struct _CertDisplayInfo *, struct _PropArrayInfo *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004f324`
- `0x180050100`

## callees

- `0x1800045e4`
- `0x18000553c`
- `0x180033ae0`
- `0x18004b0d0`
- `0x18004c8f4`
- `0x18004eea4`
- `0x1800685fc`
- `0x180069e24`
- `0x180069f38`
- `0x18006a750`
- `0x180091eaa`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18004b2bc`
- `KERNEL32!lstrcmpiW` at `0x18004b2bc`
- `KERNEL32!LocalAlloc` at `0x18004b26d`
- `KERNEL32!LocalAlloc` at `0x18004b2fd`
- `KERNEL32!LocalAlloc` at `0x18004b26d`
- `KERNEL32!LocalAlloc` at `0x18004b2fd`
- `USER32!SendMessageW` at `0x18004b11b`
- `USER32!SendMessageW` at `0x18004b164`
- `USER32!SendMessageW` at `0x18004b1bd`
- `USER32!SendMessageW` at `0x18004b226`
- `USER32!SendMessageW` at `0x18004b256`
- `USER32!SendMessageW` at `0x18004b295`
- `USER32!SendMessageW` at `0x18004b11b`
- `USER32!SendMessageW` at `0x18004b164`
- `USER32!SendMessageW` at `0x18004b1bd`
- `USER32!SendMessageW` at `0x18004b226`
- `USER32!SendMessageW` at `0x18004b256`
- `USER32!SendMessageW` at `0x18004b295`
- `USER32!GetDlgItem` at `0x18004b0f5`
- `USER32!GetDlgItem` at `0x18004b20a`
- `USER32!GetDlgItem` at `0x18004b0f5`
- `USER32!GetDlgItem` at `0x18004b20a`
- `CRYPT32!CertCompareCertificate` at `0x18004b18b`
- `CRYPT32!CertCompareCertificate` at `0x18004b18b`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18004b316`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18004b316`

## pseudocode

```c
__int64 __fastcall AddNewCertItem(HWND a1, struct _CertDisplayInfo *a2, struct _PropArrayInfo *a3, int a4)
{
  HWND DlgItem; // rax
  __int64 v9; // rbp
  HWND v10; // rsi
  int v11; // r12d
  int i; // ebx
  unsigned int v13; // esi
  __int64 v14; // rcx
  __int64 v15; // rax
  HWND v16; // rsi
  int v17; // eax
  int v18; // ebx
  int v19; // r13d
  int v20; // eax
  const WCHAR *v21; // rsi
  const WCHAR *v22; // rdx
  __int64 v23; // rax
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rbx
  unsigned __int16 *v26; // rcx
  int v27; // eax
  unsigned __int16 *v28; // r8
  int v29; // eax
  unsigned __int16 *v30; // r8
  __int64 v31; // rax
  HWND hWnd; // [rsp+30h] [rbp-B8h]
  void *v34; // [rsp+38h] [rbp-B0h] BYREF
  _DWORD lParam[10]; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+68h] [rbp-80h]

  DlgItem = GetDlgItem(a1, 2475);
  v9 = -1;
  v10 = DlgItem;
  if ( a4 )
  {
    v11 = SendMessageW(DlgItem, 0x1004u, 0, 0);
    for ( i = 0; i < v11; ++i )
    {
      memset_0(lParam, 0, 0x58u);
      lParam[0] = 4;
      lParam[1] = i;
      lParam[2] = 0;
      if ( (unsigned int)SendMessageW(v10, 0x104Bu, 0, (LPARAM)lParam)
        && CertCompareCertificate(
             1u,
             *(PCERT_INFO *)(*(_QWORD *)(*(_QWORD *)v36 + 40LL) + 24LL),
             *(PCERT_INFO *)(*((_QWORD *)a2 + 5) + 24LL)) )
      {
        ShowMessageBox(a1, 4308, 64);
        SendMessageW(a1, 0x28u, (WPARAM)v10, 1);
        LVSelectItem(v10, i);
        v13 = 1;
LABEL_8:
        FreeCertdisplayinfo(a2);
        return v13;
      }
    }
    v14 = *((_QWORD *)a2 + 1);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      if ( v15 )
      {
        hWnd = GetDlgItem(a1, 96);
        v16 = hWnd;
        v17 = SendMessageW(hWnd, 0x146u, 0, 0);
        if ( v17 > 1 )
        {
          v18 = 0;
          v19 = v17 - 1;
          while ( v18 < v19 )
          {
            v20 = SendMessageW(v16, 0x149u, v18, 0);
            if ( v20 != -1 )
            {
              v34 = LocalAlloc(0x40u, 2LL * (v20 + 1));
              v21 = (const WCHAR *)v34;
              if ( v34 )
              {
                *(_WORD *)v34 = 0;
                SendMessageW(hWnd, 0x148u, v18, (LPARAM)v21);
                v22 = (const WCHAR *)*((_QWORD *)a2 + 1);
                if ( v22 )
                {
                  v23 = -1;
                  do
                    ++v23;
                  while ( v21[v23] );
                  if ( v23 && !lstrcmpiW(v21, v22) )
                  {
                    LocalFreeAndNull(&v34);
                    goto LABEL_27;
                  }
                }
                LocalFreeAndNull(&v34);
                v16 = hWnd;
              }
              else
              {
                v16 = hWnd;
              }
            }
            ++v18;
          }
        }
        v27 = ShowMessageBoxParam(a1, 0x10D3u, 51, *(_QWORD *)a2, *((_QWORD *)a2 + 1)) - 2;
        if ( !v27 )
        {
          v13 = 1;
          goto LABEL_8;
        }
        v29 = v27 - 4;
        if ( v29 )
        {
          if ( v29 != 1 )
            goto LABEL_27;
          v30 = (unsigned __int16 *)&szNULL;
        }
        else
        {
          HrAddEmailToObj(a3, *((unsigned __int16 **)a2 + 1), v28);
          v30 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
        }
        FillCertComboWithEmailAddresses(a1, a3, v30);
      }
    }
  }
LABEL_27:
  v13 = 0;
  v24 = (unsigned __int16 *)LocalAlloc(0x40u, 0x228u);
  v25 = v24;
  if ( v24 )
  {
    *(_QWORD *)v24 = a2;
    *((_QWORD *)v24 + 1) = CertDuplicateCertificateContext(*((PCCERT_CONTEXT *)a2 + 5));
    *((_QWORD *)v25 + 68) = 0;
    v26 = *(unsigned __int16 **)a2;
    if ( *(_QWORD *)a2 )
    {
      do
        ++v9;
      while ( v26[v9] );
    }
    else
    {
      LODWORD(v9) = 0;
    }
    if ( (int)v9 + 1 > 260 )
      *(_WORD *)(*(_QWORD *)a2 + 2LL * TruncatePos(v26, 0x103u)) = 0;
    StringCchCopyW(v25 + 8, 0x104u, *(const unsigned __int16 **)a2);
    *((_QWORD *)v25 + 67) = *((_QWORD *)a3 + 23);
    v31 = *((_QWORD *)a3 + 23);
    if ( v31 )
      *(_QWORD *)(v31 + 544) = v25;
    *((_QWORD *)a3 + 23) = v25;
    return 1;
  }
  return v13;
}

```

## disassembly

```asm
0x18004b0d0  push    rbx
0x18004b0d2  push    rbp
0x18004b0d3  push    rsi
0x18004b0d4  push    rdi
0x18004b0d5  push    r12
0x18004b0d7  push    r13
0x18004b0d9  push    r14
0x18004b0db  push    r15
0x18004b0dd  sub     rsp, 0A8h
0x18004b0e4  mov     rdi, rdx
0x18004b0e7  mov     ebx, r9d
0x18004b0ea  mov     edx, 9ABh; nIDDlgItem
0x18004b0ef  mov     r14, r8
0x18004b0f2  mov     r15, rcx
0x18004b0f5  call    cs:__imp_GetDlgItem
0x18004b0fb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18004b0ff  xor     r12d, r12d
0x18004b102  mov     rsi, rax
0x18004b105  test    ebx, ebx
0x18004b107  jz      loc_18004B2F0
0x18004b10d  xor     r9d, r9d; lParam
0x18004b110  xor     r8d, r8d; wParam
0x18004b113  mov     edx, 1004h; Msg
0x18004b118  mov     rcx, rax; hWnd
0x18004b11b  call    cs:__imp_SendMessageW
0x18004b121  xor     r13d, r13d
0x18004b124  mov     r12, rax
0x18004b127  mov     ebx, r13d
0x18004b12a  cmp     ebx, r12d
0x18004b12d  jge     loc_18004B1DC
0x18004b133  xor     edx, edx; Val
0x18004b135  lea     rcx, [rsp+0E8h+lParam]; void *
0x18004b13a  lea     r8d, [rdx+58h]; Size
0x18004b13e  call    memset_0
0x18004b143  lea     r9, [rsp+0E8h+lParam]; lParam
0x18004b148  mov     dword ptr [rsp+0E8h+lParam], 4
0x18004b150  xor     r8d, r8d; wParam
0x18004b153  mov     dword ptr [rsp+0E8h+lParam+4], ebx
0x18004b157  mov     edx, 104Bh; Msg
0x18004b15c  mov     [rsp+0E8h+var_A0], r13d
0x18004b161  mov     rcx, rsi; hWnd
0x18004b164  call    cs:__imp_SendMessageW
0x18004b16a  test    eax, eax
0x18004b16c  jz      short loc_18004B195
0x18004b16e  mov     rax, [rsp+0E8h+var_80]
0x18004b173  mov     r8, [rdi+28h]
0x18004b177  mov     rcx, [rax]
0x18004b17a  mov     r8, [r8+18h]; pCertId2
0x18004b17e  mov     rdx, [rcx+28h]
0x18004b182  mov     ecx, 1; dwCertEncodingType
0x18004b187  mov     rdx, [rdx+18h]; pCertId1
0x18004b18b  call    cs:__imp_CertCompareCertificate
0x18004b191  test    eax, eax
0x18004b193  jnz     short loc_18004B199
0x18004b195  inc     ebx
0x18004b197  jmp     short loc_18004B12A
0x18004b199  mov     edx, 10D4h; int
0x18004b19e  mov     r8d, 40h ; '@'; int
0x18004b1a4  mov     rcx, r15; hWnd
0x18004b1a7  call    ?ShowMessageBox@@YAHPEAUHWND__@@HH@Z; ShowMessageBox(HWND__ *,int,int)
0x18004b1ac  mov     ebp, 1
0x18004b1b1  mov     r8, rsi; wParam
0x18004b1b4  mov     r9d, ebp; lParam
0x18004b1b7  mov     rcx, r15; hWnd
0x18004b1ba  lea     edx, [rbp+27h]; Msg
0x18004b1bd  call    cs:__imp_SendMessageW
0x18004b1c3  mov     edx, ebx; int
0x18004b1c5  mov     rcx, rsi; hWnd
0x18004b1c8  call    ?LVSelectItem@@YAXPEAUHWND__@@H@Z; LVSelectItem(HWND__ *,int)
0x18004b1cd  mov     esi, ebp
0x18004b1cf  mov     rcx, rdi; struct _CertDisplayInfo *
0x18004b1d2  call    ?FreeCertdisplayinfo@@YAXPEAU_CertDisplayInfo@@@Z; FreeCertdisplayinfo(_CertDisplayInfo *)
0x18004b1d7  jmp     loc_18004B3FA
0x18004b1dc  mov     rcx, [rdi+8]
0x18004b1e0  xor     r12d, r12d
0x18004b1e3  test    rcx, rcx
0x18004b1e6  jz      loc_18004B2F0
0x18004b1ec  mov     rax, rbp
0x18004b1ef  inc     rax
0x18004b1f2  cmp     [rcx+rax*2], r12w
0x18004b1f7  jnz     short loc_18004B1EF
0x18004b1f9  test    rax, rax
0x18004b1fc  jz      loc_18004B2F0
0x18004b202  mov     edx, 60h ; '`'; nIDDlgItem
0x18004b207  mov     rcx, r15; hDlg
0x18004b20a  call    cs:__imp_GetDlgItem
0x18004b210  xor     r9d, r9d; lParam
0x18004b213  xor     r8d, r8d; wParam
0x18004b216  mov     rcx, rax; hWnd
0x18004b219  mov     [rsp+0E8h+hWnd], rax
0x18004b21e  mov     edx, 146h; Msg
0x18004b223  mov     rsi, rax
0x18004b226  call    cs:__imp_SendMessageW
0x18004b22c  cmp     eax, 1
0x18004b22f  jle     loc_18004B33B
0x18004b235  mov     ebx, r12d
0x18004b238  lea     r13d, [rax-1]
0x18004b23c  cmp     ebx, r13d
0x18004b23f  jge     loc_18004B33B
0x18004b245  movsxd  r12, ebx
0x18004b248  xor     r9d, r9d; lParam
0x18004b24b  mov     r8, r12; wParam
0x18004b24e  mov     edx, 149h; Msg
0x18004b253  mov     rcx, rsi; hWnd
0x18004b256  call    cs:__imp_SendMessageW
0x18004b25c  cmp     eax, ebp
0x18004b25e  jz      short loc_18004B2DC
0x18004b260  inc     eax
0x18004b262  mov     ecx, 40h ; '@'; uFlags
0x18004b267  movsxd  rdx, eax
0x18004b26a  add     rdx, rdx; uBytes
0x18004b26d  call    cs:__imp_LocalAlloc
0x18004b273  mov     [rsp+0E8h+var_B0], rax
0x18004b278  mov     rsi, rax
0x18004b27b  test    rax, rax
0x18004b27e  jz      short loc_18004B2D7
0x18004b280  mov     rcx, [rsp+0E8h+hWnd]; hWnd
0x18004b285  xor     eax, eax
0x18004b287  mov     r9, rsi; lParam
0x18004b28a  mov     [rsi], ax
0x18004b28d  mov     r8, r12; wParam
0x18004b290  mov     edx, 148h; Msg
0x18004b295  call    cs:__imp_SendMessageW
0x18004b29b  mov     rdx, [rdi+8]; lpString2
0x18004b29f  xor     r12d, r12d
0x18004b2a2  test    rdx, rdx
0x18004b2a5  jz      short loc_18004B2C6
0x18004b2a7  mov     rax, rbp
0x18004b2aa  inc     rax
0x18004b2ad  cmp     [rsi+rax*2], r12w
0x18004b2b2  jnz     short loc_18004B2AA
0x18004b2b4  test    rax, rax
0x18004b2b7  jz      short loc_18004B2C6
0x18004b2b9  mov     rcx, rsi; lpString1
0x18004b2bc  call    cs:__imp_lstrcmpiW
0x18004b2c2  test    eax, eax
0x18004b2c4  jz      short loc_18004B2E6
0x18004b2c6  lea     rcx, [rsp+0E8h+var_B0]; void **
0x18004b2cb  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x18004b2d0  mov     rsi, [rsp+0E8h+hWnd]
0x18004b2d5  jmp     short loc_18004B2DF
0x18004b2d7  mov     rsi, [rsp+0E8h+hWnd]
0x18004b2dc  xor     r12d, r12d
0x18004b2df  inc     ebx
0x18004b2e1  jmp     loc_18004B23C
0x18004b2e6  lea     rcx, [rsp+0E8h+var_B0]; void **
0x18004b2eb  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x18004b2f0  mov     edx, 228h; uBytes
0x18004b2f5  mov     ecx, 40h ; '@'; uFlags
0x18004b2fa  mov     esi, r12d
0x18004b2fd  call    cs:__imp_LocalAlloc
0x18004b303  mov     rbx, rax
0x18004b306  test    rax, rax
0x18004b309  jz      loc_18004B3FA
0x18004b30f  mov     [rax], rdi
0x18004b312  mov     rcx, [rdi+28h]; pCertContext
0x18004b316  call    cs:__imp_CertDuplicateCertificateContext
0x18004b31c  mov     [rbx+8], rax
0x18004b320  mov     [rbx+220h], r12
0x18004b327  mov     rcx, [rdi]; unsigned __int16 *
0x18004b32a  test    rcx, rcx
0x18004b32d  jz      short loc_18004B39C
0x18004b32f  inc     rbp
0x18004b332  cmp     [rcx+rbp*2], r12w
0x18004b337  jnz     short loc_18004B32F
0x18004b339  jmp     short loc_18004B39F
0x18004b33b  mov     rax, [rdi+8]
0x18004b33f  mov     edx, 10D3h; uID
0x18004b344  mov     r9, [rdi]
0x18004b347  mov     r8d, 33h ; '3'; int
0x18004b34d  mov     rcx, r15; hWnd
0x18004b350  mov     [rsp+0E8h+var_C8], rax
0x18004b355  call    ?ShowMessageBoxParam@@YAHPEAUHWND__@@HHZZ; ShowMessageBoxParam(HWND__ *,int,int,...)
0x18004b35a  sub     eax, 2
0x18004b35d  jz      short loc_18004B392
0x18004b35f  sub     eax, 4
0x18004b362  jz      short loc_18004B372
0x18004b364  cmp     eax, 1
0x18004b367  jnz     short loc_18004B2F0
0x18004b369  lea     r8, ?szNULL@@3QBGB; ushort const near * const szNULL
0x18004b370  jmp     short loc_18004B382
0x18004b372  mov     rdx, [rdi+8]; unsigned __int16 *
0x18004b376  mov     rcx, r14; struct _PropArrayInfo *
0x18004b379  call    ?HrAddEmailToObj@@YAJPEAU_PropArrayInfo@@PEAG1@Z; HrAddEmailToObj(_PropArrayInfo *,ushort *,ushort *)
0x18004b37e  mov     r8, [rdi+8]; unsigned __int16 *
0x18004b382  mov     rdx, r14; struct _PropArrayInfo *
0x18004b385  mov     rcx, r15; HWND
0x18004b388  call    ?FillCertComboWithEmailAddresses@@YAXPEAUHWND__@@PEAU_PropArrayInfo@@PEAG@Z; FillCertComboWithEmailAddresses(HWND__ *,_PropArrayInfo *,ushort *)
0x18004b38d  jmp     loc_18004B2F0
0x18004b392  mov     esi, 1
0x18004b397  jmp     loc_18004B1CF
0x18004b39c  mov     rbp, r12
0x18004b39f  lea     eax, [rbp+1]
0x18004b3a2  mov     esi, 104h
0x18004b3a7  cmp     eax, esi
0x18004b3a9  jle     short loc_18004B3BE
0x18004b3ab  lea     edx, [rsi-1]; unsigned int
0x18004b3ae  call    ?TruncatePos@@YAKPEAGK@Z; TruncatePos(ushort *,ulong)
0x18004b3b3  mov     rcx, [rdi]
0x18004b3b6  mov     r8d, eax
0x18004b3b9  mov     [rcx+r8*2], r12w
0x18004b3be  mov     r8, [rdi]; unsigned __int16 *
0x18004b3c1  lea     rcx, [rbx+10h]; unsigned __int16 *
0x18004b3c5  mov     rdx, rsi; unsigned __int64
0x18004b3c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004b3cd  mov     rax, [r14+0B8h]
0x18004b3d4  mov     [rbx+218h], rax
0x18004b3db  mov     rax, [r14+0B8h]
0x18004b3e2  test    rax, rax
0x18004b3e5  jz      short loc_18004B3EE
0x18004b3e7  mov     [rax+220h], rbx
0x18004b3ee  mov     [r14+0B8h], rbx
0x18004b3f5  mov     esi, 1
0x18004b3fa  mov     eax, esi
0x18004b3fc  add     rsp, 0A8h
0x18004b403  pop     r15
0x18004b405  pop     r14
0x18004b407  pop     r13
0x18004b409  pop     r12
0x18004b40b  pop     rdi
0x18004b40c  pop     rsi
0x18004b40d  pop     rbp
0x18004b40e  pop     rbx
0x18004b40f  retn
```
