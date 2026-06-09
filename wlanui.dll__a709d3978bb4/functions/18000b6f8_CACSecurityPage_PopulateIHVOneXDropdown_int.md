# CACSecurityPage::PopulateIHVOneXDropdown(int)

- ea: `0x18000b6f8`
- end: `0x18000ba91`
- name: `?PopulateIHVOneXDropdown@CACSecurityPage@@AEAAJH@Z`
- size: `921`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180008720`

## callees

- `0x180005e64`
- `0x1800060a0`
- `0x1800060d4`
- `0x18000739c`
- `0x180007404`
- `0x1800078f4`
- `0x180007ae4`
- `0x1800082f8`
- `0x18000b6f8`
- `0x180010ef0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000ba53`
- `KERNEL32!GetProcessHeap` at `0x18000ba53`
- `KERNEL32!HeapFree` at `0x18000ba61`
- `KERNEL32!HeapFree` at `0x18000ba61`
- `USER32!SendMessageW` at `0x18000b7c4`
- `USER32!SendMessageW` at `0x18000b885`
- `USER32!SendMessageW` at `0x18000b7c4`
- `USER32!SendMessageW` at `0x18000b885`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba6f`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::PopulateIHVOneXDropdown(CACSecurityPage *this, int a2)
{
  __int64 v2; // rax
  int v3; // r15d
  int v5; // r12d
  int v6; // r13d
  _DWORD *AuthInfo; // rbp
  _DWORD *v8; // rdi
  OLECHAR *CurrentIHVSecurityProfile; // r14
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // r14d
  _QWORD *v13; // rcx
  unsigned int v14; // r14d
  int v15; // ebx
  _DWORD *ItemDataPtr; // rax
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // eax
  int v21; // edx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  bool v25; // zf
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rdx
  unsigned int v31; // eax
  unsigned int v32; // eax
  LPARAM v33; // rbx
  __int64 v34; // rcx
  int v35; // eax
  unsigned int v36; // r8d
  _DWORD *v37; // rax
  HWND v38; // rcx
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rax
  unsigned __int64 v42; // rcx
  _DWORD *v43; // rax
  unsigned int v44; // edx
  struct _AUI_CIPHER_INFO *CipherInfo; // rax
  struct _AUI_CIPHER_INFO *v46; // rbx
  HANDLE ProcessHeap; // rax
  LPARAM lParam[11]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v50; // [rsp+90h] [rbp+8h]
  unsigned int v52; // [rsp+A0h] [rbp+18h]
  unsigned __int16 *v53; // [rsp+A8h] [rbp+20h]

  v2 = *((_QWORD *)this + 154);
  v3 = 0;
  lParam[0] = 0;
  if ( !v2 || !*(_DWORD *)(v2 + 52) )
    return 0;
  v50 = 0;
  v5 = 0;
  v6 = 0;
  AuthInfo = 0;
  v8 = 0;
  CurrentIHVSecurityProfile = CACSecurityPage::GetCurrentIHVSecurityProfile(this);
  v53 = CurrentIHVSecurityProfile;
  v52 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 154) + 40LL) + 8LL);
  if ( v52 )
  {
    while ( 1 )
    {
      v10 = *((_QWORD *)this + 154);
      v11 = *(_QWORD *)(v10 + 40);
      v12 = *(_DWORD *)(v11 + 36);
      v13 = *(_QWORD **)(v11 + 24);
      v14 = v3 + v12;
      if ( v13 )
      {
        if ( *v13 && *(_DWORD *)(v13[v3 & (unsigned int)-(v14 != 0)] + 28LL) )
          break;
      }
      lParam[0] = 0;
      v30 = *(_QWORD *)(v10 + 40);
      if ( v14 )
        v31 = v14 - *(_DWORD *)(v30 + 36);
      else
        v31 = 0;
      v32 = (*(__int64 (__fastcall **)(_QWORD, LPARAM *))(**(_QWORD **)(*(_QWORD *)v30 + 8LL * v31) + 24LL))(
              *(_QWORD *)(*(_QWORD *)v30 + 8LL * v31),
              lParam);
      v33 = lParam[0];
      v50 = v32;
      AuthInfo = (_DWORD *)CACSecurityPage::CreateAuthInfo(v34, 0, 0, 1, 1, v14);
      v35 = ComboBox_AddItem(*((HWND *)this + 8), v33, (LPARAM)AuthInfo);
      v6 = v35;
      if ( !v8 )
      {
        v5 = v35;
LABEL_39:
        v8 = AuthInfo;
      }
LABEL_40:
      if ( a2 && AuthInfo && AuthInfo[3] )
      {
        v36 = v14;
        CurrentIHVSecurityProfile = v53;
        if ( (unsigned int)IHVExtHelper::IHVExtHlpGetSelected(
                             *(IHVExtHelper **)(*((_QWORD *)this + 154) + 40LL),
                             v53,
                             v36) )
        {
          v8 = AuthInfo;
          v5 = v6;
        }
      }
      else
      {
        CurrentIHVSecurityProfile = v53;
      }
      if ( ++v3 >= v52 )
        goto LABEL_47;
    }
    v15 = 0;
    if ( !(unsigned int)SendMessageW(*((HWND *)this + 8), 0x146u, 0, 0) )
      goto LABEL_40;
    while ( 1 )
    {
      ItemDataPtr = ComboBox_GetItemDataPtr(*((HWND *)this + 8), v15);
      AuthInfo = ItemDataPtr;
      if ( ItemDataPtr && ItemDataPtr[3] && !*ItemDataPtr )
        goto LABEL_30;
      v17 = *(_QWORD *)(*((_QWORD *)this + 154) + 40LL);
      if ( v14 )
        v18 = v14 - *(_DWORD *)(v17 + 36);
      else
        v18 = 0;
      v19 = *(_QWORD *)(*(_QWORD *)(v17 + 24) + 8LL * v18);
      v20 = AuthInfo[1];
      v21 = *(_DWORD *)(v19 + 32);
      if ( v20 > 6 )
      {
        v26 = v20 - 7;
        if ( !v26 )
          goto LABEL_30;
        v27 = v26 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( !v28 )
            goto LABEL_30;
          v29 = v28 - 2;
          if ( v29 )
          {
            if ( v29 != 2147483636 )
              goto LABEL_30;
            v24 = 0;
            v25 = v21 == 0;
          }
          else
          {
            v24 = 0;
            v25 = v21 == 3;
          }
        }
        else
        {
          v24 = 0;
          v25 = v21 == 4;
        }
      }
      else if ( v20 == 6 )
      {
        v24 = 0;
        v25 = v21 == 2;
      }
      else
      {
        v22 = v20 - 1;
        if ( !v22 )
          goto LABEL_30;
        v23 = v22 - 1;
        if ( !v23 )
          goto LABEL_30;
        v24 = v23 - 1;
        if ( v24 )
          goto LABEL_30;
        v25 = v21 == 1;
      }
      LOBYTE(v24) = v25;
      if ( v24 )
      {
        AuthInfo[2] = 1;
        v6 = v15;
        AuthInfo[3] = 1;
        AuthInfo[4] = v14;
        if ( !v8 )
        {
          v5 = v15;
          goto LABEL_39;
        }
        goto LABEL_40;
      }
LABEL_30:
      if ( ++v15 >= (unsigned int)SendMessageW(*((HWND *)this + 8), 0x146u, 0, 0) )
        goto LABEL_40;
    }
  }
LABEL_47:
  if ( a2 && v8 )
  {
    if ( *v8 )
      v37 = v8 + 1;
    else
      v37 = v8 + 4;
    v38 = (HWND)*((_QWORD *)this + 8);
    *((_DWORD *)this + 14) = *v37;
    ComboBox_SetCurSelNotify(v38, v5);
    v39 = *(_QWORD *)(*((_QWORD *)this + 154) + 40LL);
    v40 = v8[4];
    if ( v40 )
      v41 = (unsigned int)(v40 - *(_DWORD *)(v39 + 36));
    else
      v41 = 0;
    v42 = *(_QWORD *)(v39 + 24);
    if ( v42
      && *(_QWORD *)v42
      && (v43 = *(_DWORD **)(v42 + 8 * v41), v42 = (unsigned int)v43[5], (unsigned int)v42 < v43[4]) )
    {
      v44 = v42 + v43[6];
    }
    else
    {
      v44 = 0;
    }
    CipherInfo = CACSecurityPage::CreateCipherInfo((CACSecurityPage *)v42, v44, 0);
    v46 = CipherInfo;
    if ( !v8[3] || *v8 )
      CACSecurityPage::DisplayCiphersForMSAuth(this, (struct _AUI_AUTH_INFO *)v8, 1, CipherInfo);
    else
      CACSecurityPage::DisplayCiphersForIHVAuth(this, (struct _AUI_AUTH_INFO *)v8, 1, CipherInfo, 0);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v46);
  }
  if ( CurrentIHVSecurityProfile )
    SysFreeString(CurrentIHVSecurityProfile);
  return v50;
}

```

## disassembly

```asm
0x18000b6f8  mov     [rsp+arg_8], edx
0x18000b6fc  push    rbx
0x18000b6fd  push    rbp
0x18000b6fe  push    rsi
0x18000b6ff  push    rdi
0x18000b700  push    r12
0x18000b702  push    r13
0x18000b704  push    r14
0x18000b706  push    r15
0x18000b708  sub     rsp, 48h
0x18000b70c  mov     rax, [rcx+4D0h]
0x18000b713  xor     r15d, r15d
0x18000b716  mov     [rsp+88h+lParam], r15
0x18000b71b  mov     rsi, rcx
0x18000b71e  test    rax, rax
0x18000b721  jz      loc_18000BA7E
0x18000b727  cmp     [rax+34h], r15d
0x18000b72b  jz      loc_18000BA7E
0x18000b731  mov     [rsp+88h+arg_0], r15d
0x18000b739  mov     r12d, r15d
0x18000b73c  mov     r13d, r15d
0x18000b73f  mov     ebp, r15d
0x18000b742  mov     edi, r15d
0x18000b745  call    ?GetCurrentIHVSecurityProfile@CACSecurityPage@@AEAAPEAGXZ; CACSecurityPage::GetCurrentIHVSecurityProfile(void)
0x18000b74a  mov     r14, rax
0x18000b74d  mov     [rsp+88h+arg_18], rax
0x18000b755  mov     rax, [rsi+4D0h]
0x18000b75c  mov     rcx, [rax+28h]
0x18000b760  mov     eax, [rcx+8]
0x18000b763  mov     [rsp+88h+arg_10], eax
0x18000b76a  test    eax, eax
0x18000b76c  jz      loc_18000B990
0x18000b772  mov     r8, [rsi+4D0h]
0x18000b779  mov     rcx, [r8+28h]
0x18000b77d  mov     r14d, [rcx+24h]
0x18000b781  mov     rcx, [rcx+18h]
0x18000b785  add     r14d, r15d
0x18000b788  mov     eax, r14d
0x18000b78b  neg     eax
0x18000b78d  sbb     edx, edx
0x18000b78f  and     edx, r15d
0x18000b792  test    rcx, rcx
0x18000b795  jz      loc_18000B8BB
0x18000b79b  cmp     qword ptr [rcx], 0
0x18000b79f  jz      loc_18000B8BB
0x18000b7a5  mov     rcx, [rcx+rdx*8]
0x18000b7a9  cmp     dword ptr [rcx+1Ch], 0
0x18000b7ad  jz      loc_18000B8BB
0x18000b7b3  mov     rcx, [rsi+40h]; hWnd
0x18000b7b7  xor     r9d, r9d; lParam
0x18000b7ba  xor     r8d, r8d; wParam
0x18000b7bd  mov     edx, 146h; Msg
0x18000b7c2  xor     ebx, ebx
0x18000b7c4  call    cs:__imp_SendMessageW
0x18000b7ca  test    eax, eax
0x18000b7cc  jz      loc_18000B938
0x18000b7d2  mov     rcx, [rsi+40h]; HWND
0x18000b7d6  mov     edx, ebx; int
0x18000b7d8  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x18000b7dd  mov     rbp, rax
0x18000b7e0  test    rax, rax
0x18000b7e3  jz      short loc_18000B7F4
0x18000b7e5  cmp     dword ptr [rax+0Ch], 0
0x18000b7e9  jz      short loc_18000B7F4
0x18000b7eb  cmp     dword ptr [rax], 0
0x18000b7ee  jz      loc_18000B874
0x18000b7f4  mov     rax, [rsi+4D0h]
0x18000b7fb  mov     rdx, [rax+28h]
0x18000b7ff  test    r14d, r14d
0x18000b802  jz      short loc_18000B80C
0x18000b804  mov     eax, r14d
0x18000b807  sub     eax, [rdx+24h]
0x18000b80a  jmp     short loc_18000B80E
0x18000b80c  xor     eax, eax
0x18000b80e  mov     ecx, eax
0x18000b810  mov     rax, [rdx+18h]
0x18000b814  mov     rcx, [rax+rcx*8]
0x18000b818  mov     eax, [rbp+4]
0x18000b81b  mov     edx, [rcx+20h]
0x18000b81e  cmp     eax, 6
0x18000b821  ja      short loc_18000B840
0x18000b823  jz      short loc_18000B839
0x18000b825  sub     eax, 1
0x18000b828  jz      short loc_18000B874
0x18000b82a  sub     eax, 1
0x18000b82d  jz      short loc_18000B874
0x18000b82f  sub     eax, 1
0x18000b832  jnz     short loc_18000B874
0x18000b834  cmp     edx, 1
0x18000b837  jmp     short loc_18000B86D
0x18000b839  xor     eax, eax
0x18000b83b  cmp     edx, 2
0x18000b83e  jmp     short loc_18000B86D
0x18000b840  sub     eax, 7
0x18000b843  jz      short loc_18000B874
0x18000b845  sub     eax, 1
0x18000b848  jz      short loc_18000B868
0x18000b84a  sub     eax, 1
0x18000b84d  jz      short loc_18000B874
0x18000b84f  sub     eax, 2
0x18000b852  jz      short loc_18000B861
0x18000b854  cmp     eax, 7FFFFFF4h
0x18000b859  jnz     short loc_18000B874
0x18000b85b  xor     eax, eax
0x18000b85d  test    edx, edx
0x18000b85f  jmp     short loc_18000B86D
0x18000b861  xor     eax, eax
0x18000b863  cmp     edx, 3
0x18000b866  jmp     short loc_18000B86D
0x18000b868  xor     eax, eax
0x18000b86a  cmp     edx, 4
0x18000b86d  setz    al
0x18000b870  test    eax, eax
0x18000b872  jnz     short loc_18000B898
0x18000b874  mov     rcx, [rsi+40h]; hWnd
0x18000b878  xor     r9d, r9d; lParam
0x18000b87b  xor     r8d, r8d; wParam
0x18000b87e  mov     edx, 146h; Msg
0x18000b883  inc     ebx
0x18000b885  call    cs:__imp_SendMessageW
0x18000b88b  cmp     ebx, eax
0x18000b88d  jb      loc_18000B7D2
0x18000b893  jmp     loc_18000B938
0x18000b898  mov     dword ptr [rbp+8], 1
0x18000b89f  mov     r13d, ebx
0x18000b8a2  mov     dword ptr [rbp+0Ch], 1
0x18000b8a9  mov     [rbp+10h], r14d
0x18000b8ad  test    rdi, rdi
0x18000b8b0  jnz     loc_18000B938
0x18000b8b6  mov     r12d, ebx
0x18000b8b9  jmp     short loc_18000B935
0x18000b8bb  mov     [rsp+88h+lParam], 0
0x18000b8c4  mov     rdx, [r8+28h]
0x18000b8c8  test    r14d, r14d
0x18000b8cb  jz      short loc_18000B8D5
0x18000b8cd  mov     eax, r14d
0x18000b8d0  sub     eax, [rdx+24h]
0x18000b8d3  jmp     short loc_18000B8D7
0x18000b8d5  xor     eax, eax
0x18000b8d7  mov     ecx, eax
0x18000b8d9  mov     rax, [rdx]
0x18000b8dc  lea     rdx, [rsp+88h+lParam]
0x18000b8e1  mov     rcx, [rax+rcx*8]
0x18000b8e5  mov     rax, [rcx]
0x18000b8e8  mov     rax, [rax+18h]
0x18000b8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f1  mov     rbx, [rsp+88h+lParam]
0x18000b8f6  xor     r8d, r8d
0x18000b8f9  mov     [rsp+88h+arg_0], eax
0x18000b900  xor     edx, edx
0x18000b902  mov     eax, 1
0x18000b907  mov     [rsp+88h+var_60], r14d
0x18000b90c  mov     r9d, eax
0x18000b90f  mov     [rsp+88h+var_68], eax
0x18000b913  call    ?CreateAuthInfo@CACSecurityPage@@AEAAPEAU_AUI_AUTH_INFO@@HW4AUI_DOT11_AUTH_ALGORITHM@@HHK@Z; CACSecurityPage::CreateAuthInfo(int,AUI_DOT11_AUTH_ALGORITHM,int,int,ulong)
0x18000b918  mov     rcx, [rsi+40h]; hWnd
0x18000b91c  mov     r8, rax; LPARAM
0x18000b91f  mov     rdx, rbx; lParam
0x18000b922  mov     rbp, rax
0x18000b925  call    ?ComboBox_AddItem@@YAHPEAUHWND__@@PEBGPEAX@Z; ComboBox_AddItem(HWND__ *,ushort const *,void *)
0x18000b92a  mov     r13d, eax
0x18000b92d  test    rdi, rdi
0x18000b930  jnz     short loc_18000B938
0x18000b932  mov     r12d, eax
0x18000b935  mov     rdi, rbp
0x18000b938  cmp     [rsp+88h+arg_8], 0
0x18000b940  jz      short loc_18000B977
0x18000b942  test    rbp, rbp
0x18000b945  jz      short loc_18000B977
0x18000b947  cmp     dword ptr [rbp+0Ch], 0
0x18000b94b  jz      short loc_18000B977
0x18000b94d  mov     rcx, [rsi+4D0h]
0x18000b954  mov     r8d, r14d; unsigned int
0x18000b957  mov     r14, [rsp+88h+arg_18]
0x18000b95f  mov     rdx, r14; unsigned __int16 *
0x18000b962  mov     rcx, [rcx+28h]; this
0x18000b966  call    ?IHVExtHlpGetSelected@IHVExtHelper@@QEAAHPEAGK@Z; IHVExtHelper::IHVExtHlpGetSelected(ushort *,ulong)
0x18000b96b  test    eax, eax
0x18000b96d  jz      short loc_18000B97F
0x18000b96f  mov     rdi, rbp
0x18000b972  mov     r12d, r13d
0x18000b975  jmp     short loc_18000B97F
0x18000b977  mov     r14, [rsp+88h+arg_18]
0x18000b97f  inc     r15d
0x18000b982  cmp     r15d, [rsp+88h+arg_10]
0x18000b98a  jb      loc_18000B772
0x18000b990  cmp     [rsp+88h+arg_8], 0
0x18000b998  jz      loc_18000BA67
0x18000b99e  test    rdi, rdi
0x18000b9a1  jz      loc_18000BA67
0x18000b9a7  cmp     dword ptr [rdi], 0
0x18000b9aa  jz      short loc_18000B9B6
0x18000b9ac  lea     rax, [rdi+4]
0x18000b9b0  lea     rbx, [rdi+10h]
0x18000b9b4  jmp     short loc_18000B9BD
0x18000b9b6  lea     rax, [rdi+10h]
0x18000b9ba  mov     rbx, rax
0x18000b9bd  mov     eax, [rax]
0x18000b9bf  mov     edx, r12d; int
0x18000b9c2  mov     rcx, [rsi+40h]; hWnd
0x18000b9c6  mov     [rsi+38h], eax
0x18000b9c9  call    ?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z; ComboBox_SetCurSelNotify(HWND__ *,int)
0x18000b9ce  mov     rax, [rsi+4D0h]
0x18000b9d5  xor     r15d, r15d
0x18000b9d8  mov     rcx, [rax+28h]
0x18000b9dc  mov     eax, [rbx]
0x18000b9de  test    eax, eax
0x18000b9e0  jz      short loc_18000B9E7
0x18000b9e2  sub     eax, [rcx+24h]
0x18000b9e5  jmp     short loc_18000B9EA
0x18000b9e7  mov     eax, r15d
0x18000b9ea  mov     rcx, [rcx+18h]; this
0x18000b9ee  test    rcx, rcx
0x18000b9f1  jz      short loc_18000BA0B
0x18000b9f3  cmp     [rcx], r15
0x18000b9f6  jz      short loc_18000BA0B
0x18000b9f8  mov     rax, [rcx+rax*8]
0x18000b9fc  mov     ecx, [rax+14h]
0x18000b9ff  cmp     ecx, [rax+10h]
0x18000ba02  jnb     short loc_18000BA0B
0x18000ba04  mov     edx, [rax+18h]
0x18000ba07  add     edx, ecx
0x18000ba09  jmp     short loc_18000BA0E
0x18000ba0b  mov     edx, r15d; unsigned int
0x18000ba0e  xor     r8d, r8d; int
0x18000ba11  call    ?CreateCipherInfo@CACSecurityPage@@AEAAPEAU_AUI_CIPHER_INFO@@KH@Z; CACSecurityPage::CreateCipherInfo(ulong,int)
0x18000ba16  mov     rbx, rax
0x18000ba19  cmp     [rdi+0Ch], r15d
0x18000ba1d  jz      short loc_18000BA3F
0x18000ba1f  cmp     [rdi], r15d
0x18000ba22  jnz     short loc_18000BA3F
0x18000ba24  mov     r9, rax; struct _AUI_CIPHER_INFO *
0x18000ba27  mov     [rsp+88h+var_68], r15d; int
0x18000ba2c  mov     r8d, 1; int
0x18000ba32  mov     rdx, rdi; struct _AUI_AUTH_INFO *
0x18000ba35  mov     rcx, rsi; this
0x18000ba38  call    ?DisplayCiphersForIHVAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@H@Z; CACSecurityPage::DisplayCiphersForIHVAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *,int)
0x18000ba3d  jmp     short loc_18000BA53
0x18000ba3f  mov     r9, rbx; struct _AUI_CIPHER_INFO *
0x18000ba42  mov     r8d, 1; int
0x18000ba48  mov     rdx, rdi; struct _AUI_AUTH_INFO *
0x18000ba4b  mov     rcx, rsi; this
0x18000ba4e  call    ?DisplayCiphersForMSAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@@Z; CACSecurityPage::DisplayCiphersForMSAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *)
0x18000ba53  call    cs:__imp_GetProcessHeap
0x18000ba59  mov     r8, rbx; lpMem
0x18000ba5c  xor     edx, edx; dwFlags
0x18000ba5e  mov     rcx, rax; hHeap
0x18000ba61  call    cs:__imp_HeapFree
0x18000ba67  test    r14, r14
0x18000ba6a  jz      short loc_18000BA75
0x18000ba6c  mov     rcx, r14; bstrString
0x18000ba6f  call    cs:__imp_SysFreeString
0x18000ba75  mov     eax, [rsp+88h+arg_0]
0x18000ba7c  jmp     short loc_18000BA80
0x18000ba7e  xor     eax, eax
0x18000ba80  add     rsp, 48h
0x18000ba84  pop     r15
0x18000ba86  pop     r14
0x18000ba88  pop     r13
0x18000ba8a  pop     r12
0x18000ba8c  pop     rdi
0x18000ba8d  pop     rsi
0x18000ba8e  pop     rbp
0x18000ba8f  pop     rbx
0x18000ba90  retn
```
