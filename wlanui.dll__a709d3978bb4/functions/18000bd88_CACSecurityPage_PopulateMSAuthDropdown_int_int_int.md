# CACSecurityPage::PopulateMSAuthDropdown(int,int,int)

- ea: `0x18000bd88`
- end: `0x18000c047`
- name: `?PopulateMSAuthDropdown@CACSecurityPage@@AEAAJHHH@Z`
- size: `703`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, int, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008720`

## callees

- `0x180005e64`
- `0x1800060d4`
- `0x180006f98`
- `0x18000739c`
- `0x180007404`
- `0x1800078f4`
- `0x180007ae4`
- `0x1800083d4`
- `0x18000bd88`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000bf18`
- `KERNEL32!GetProcessHeap` at `0x18000c019`
- `KERNEL32!GetProcessHeap` at `0x18000bf18`
- `KERNEL32!GetProcessHeap` at `0x18000c019`
- `KERNEL32!HeapFree` at `0x18000bf26`
- `KERNEL32!HeapFree` at `0x18000c027`
- `KERNEL32!HeapFree` at `0x18000bf26`
- `KERNEL32!HeapFree` at `0x18000c027`
- `USER32!LoadStringW` at `0x18000bf63`
- `USER32!LoadStringW` at `0x18000bf63`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::PopulateMSAuthDropdown(CACSecurityPage *this, int a2, int a3, int a4)
{
  int v4; // r15d
  __int64 v8; // r10
  _DWORD *v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  _DWORD *v12; // r14
  __int64 *v13; // rsi
  unsigned int v14; // ebp
  __int64 v15; // rsi
  __int64 v16; // rdi
  __int64 v17; // rcx
  LPARAM FriendlyAuthName; // r15
  LPARAM AuthInfo; // rax
  __int64 v20; // rcx
  int v21; // r8d
  int v22; // r9d
  HWND v23; // rcx
  CACSecurityPage *v24; // rcx
  struct _AUI_CIPHER_INFO *CipherInfo; // r15
  HANDLE ProcessHeap; // rax
  __int64 v27; // rcx
  LPARAM v28; // rax
  LPARAM v29; // rdi
  int v30; // eax
  HWND v31; // rcx
  CACSecurityPage *v32; // rcx
  struct _AUI_CIPHER_INFO *v33; // rax
  struct _AUI_CIPHER_INFO *v34; // rsi
  HANDLE v35; // rax

  v4 = a4;
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 552LL) + 32LL) + 424LL);
  if ( *(_DWORD *)(v8 + 16) > 1u && (v9 = (_DWORD *)*((_QWORD *)this + 3), *v9) )
  {
    v10 = 0;
LABEL_4:
    v11 = 0;
    while ( 1 )
    {
      v12 = (_DWORD *)(*(_QWORD *)(v8 + 24) + 8 * v11);
      if ( v9[2 * v10 + 1] == *v12 && v9[2 * v10 + 2] == v12[1] )
        break;
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= *(_DWORD *)(v8 + 16) )
      {
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 < *v9 )
          goto LABEL_4;
        goto LABEL_9;
      }
    }
  }
  else
  {
LABEL_9:
    v12 = *(_DWORD **)(v8 + 24);
  }
  v13 = (__int64 *)*((_QWORD *)this + 4);
  if ( !v13 )
    return (unsigned int)-2147418113;
  v15 = *v13;
  v14 = 0;
  while ( v15 )
  {
    v16 = *(_QWORD *)(v15 + 16);
    if ( (unsigned int)(*((_DWORD *)this + 329) - 3) <= 1 || (unsigned int)(*(_DWORD *)(v16 + 4) - 3) > 1 )
    {
      FriendlyAuthName = CACSecurityPage::GetFriendlyAuthName(this, *(unsigned int *)(v16 + 4));
      if ( FriendlyAuthName )
      {
        AuthInfo = CACSecurityPage::CreateAuthInfo(
                     v17,
                     1,
                     *(unsigned int *)(v16 + 4),
                     *(unsigned int *)(v16 + 8),
                     0,
                     -1);
        ComboBox_AddItem(*((HWND *)this + 8), FriendlyAuthName, AuthInfo);
        ++*((_DWORD *)this + 310);
        v4 = a4;
        if ( !a4 )
          goto LABEL_26;
        if ( !a3 && *v12 == (unsigned int)CACSecurityPage::AUIAuth2Auth(v20, *(unsigned int *)(v16 + 4)) )
        {
          v23 = (HWND)*((_QWORD *)this + 8);
          *((_DWORD *)this + 14) = v21;
          ComboBox_SetCurSelNotify(v23, v22);
          CipherInfo = CACSecurityPage::CreateCipherInfo(v24, v12[1], 1);
          if ( v16 )
          {
            if ( !*(_DWORD *)(v16 + 12) || *(_DWORD *)v16 )
              CACSecurityPage::DisplayCiphersForMSAuth(this, (struct _AUI_AUTH_INFO *)v16, 1, CipherInfo);
            else
              CACSecurityPage::DisplayCiphersForIHVAuth((HWND *)this, (struct _AUI_AUTH_INFO *)v16, 1, CipherInfo, 0);
          }
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, CipherInfo);
        }
      }
    }
    v4 = a4;
LABEL_26:
    v15 = *(_QWORD *)(v15 + 8);
  }
  if ( a2 )
  {
    LoadStringW(hInstance, 0x42D2u, (LPWSTR)this + 48, 256);
    v28 = CACSecurityPage::CreateAuthInfo(v27, 1, 0x7FFFFFFF, 1, 0, -1);
    v29 = v28;
    if ( this == (CACSecurityPage *)-96LL || !v28 )
    {
      return (unsigned int)-2147024882;
    }
    else
    {
      v30 = ComboBox_AddItem(*((HWND *)this + 8), (LPARAM)this + 96, v28);
      ++*((_DWORD *)this + 310);
      if ( v4 && a3 )
      {
        v31 = (HWND)*((_QWORD *)this + 8);
        *((_DWORD *)this + 14) = *(_DWORD *)(v29 + 4);
        ComboBox_SetCurSelNotify(v31, v30);
        v33 = CACSecurityPage::CreateCipherInfo(v32, v12[1], 1);
        v34 = v33;
        if ( !*(_DWORD *)(v29 + 12) || *(_DWORD *)v29 )
          CACSecurityPage::DisplayCiphersForMSAuth(this, (struct _AUI_AUTH_INFO *)v29, 1, v33);
        else
          CACSecurityPage::DisplayCiphersForIHVAuth((HWND *)this, (struct _AUI_AUTH_INFO *)v29, 1, v33, 0);
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v34);
      }
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18000bd88  mov     [rsp+arg_18], r9d
0x18000bd8d  push    rbx
0x18000bd8e  push    rbp
0x18000bd8f  push    rsi
0x18000bd90  push    rdi
0x18000bd91  push    r12
0x18000bd93  push    r13
0x18000bd95  push    r14
0x18000bd97  push    r15
0x18000bd99  sub     rsp, 38h
0x18000bd9d  mov     rax, [rcx+28h]
0x18000bda1  mov     r15d, r9d
0x18000bda4  mov     r12d, r8d
0x18000bda7  mov     r13d, edx
0x18000bdaa  mov     rbx, rcx
0x18000bdad  mov     r10, [rax+228h]
0x18000bdb4  mov     rax, [r10+20h]
0x18000bdb8  mov     r10, [rax+1A8h]
0x18000bdbf  cmp     dword ptr [r10+10h], 1
0x18000bdc4  jbe     short loc_18000BE00
0x18000bdc6  mov     r8, [rcx+18h]
0x18000bdca  cmp     dword ptr [r8], 0
0x18000bdce  jbe     short loc_18000BE00
0x18000bdd0  xor     ecx, ecx
0x18000bdd2  mov     r11, [r10+18h]
0x18000bdd6  xor     edx, edx
0x18000bdd8  mov     edi, [r8+rcx*8+4]
0x18000bddd  lea     r14, [r11+rdx*8]
0x18000bde1  cmp     edi, [r14]
0x18000bde4  jnz     short loc_18000BDF1
0x18000bde6  mov     eax, [r14+4]
0x18000bdea  cmp     [r8+rcx*8+8], eax
0x18000bdef  jz      short loc_18000BE04
0x18000bdf1  inc     edx
0x18000bdf3  cmp     edx, [r10+10h]
0x18000bdf7  jb      short loc_18000BDDD
0x18000bdf9  inc     ecx
0x18000bdfb  cmp     ecx, [r8]
0x18000bdfe  jb      short loc_18000BDD2
0x18000be00  mov     r14, [r10+18h]
0x18000be04  mov     rsi, [rbx+20h]
0x18000be08  test    rsi, rsi
0x18000be0b  jnz     short loc_18000BE17
0x18000be0d  mov     ebp, 8000FFFFh
0x18000be12  jmp     loc_18000C034
0x18000be17  mov     rsi, [rsi]
0x18000be1a  xor     ebp, ebp
0x18000be1c  jmp     loc_18000BF38
0x18000be21  mov     eax, [rbx+524h]
0x18000be27  mov     rdi, [rsi+10h]
0x18000be2b  sub     eax, 3
0x18000be2e  cmp     eax, 1
0x18000be31  jbe     short loc_18000BE42
0x18000be33  mov     eax, [rdi+4]
0x18000be36  sub     eax, 3
0x18000be39  cmp     eax, 1
0x18000be3c  jbe     loc_18000BF2C
0x18000be42  mov     edx, [rdi+4]
0x18000be45  mov     rcx, rbx
0x18000be48  call    ?GetFriendlyAuthName@CACSecurityPage@@AEAAPEBGW4AUI_DOT11_AUTH_ALGORITHM@@@Z; CACSecurityPage::GetFriendlyAuthName(AUI_DOT11_AUTH_ALGORITHM)
0x18000be4d  mov     r15, rax
0x18000be50  test    rax, rax
0x18000be53  jz      loc_18000BF2C
0x18000be59  mov     r9d, [rdi+8]
0x18000be5d  mov     edx, 1
0x18000be62  mov     r8d, [rdi+4]
0x18000be66  mov     [rsp+78h+var_50], 0FFFFFFFFh
0x18000be6e  mov     [rsp+78h+var_58], ebp
0x18000be72  call    ?CreateAuthInfo@CACSecurityPage@@AEAAPEAU_AUI_AUTH_INFO@@HW4AUI_DOT11_AUTH_ALGORITHM@@HHK@Z; CACSecurityPage::CreateAuthInfo(int,AUI_DOT11_AUTH_ALGORITHM,int,int,ulong)
0x18000be77  mov     rcx, [rbx+40h]; hWnd
0x18000be7b  mov     r8, rax; LPARAM
0x18000be7e  mov     rdx, r15; lParam
0x18000be81  call    ?ComboBox_AddItem@@YAHPEAUHWND__@@PEBGPEAX@Z; ComboBox_AddItem(HWND__ *,ushort const *,void *)
0x18000be86  inc     dword ptr [rbx+4D8h]
0x18000be8c  mov     r9d, eax
0x18000be8f  mov     r15d, [rsp+78h+arg_18]
0x18000be97  test    r15d, r15d
0x18000be9a  jz      loc_18000BF34
0x18000bea0  test    r12d, r12d
0x18000bea3  jnz     loc_18000BF2C
0x18000bea9  mov     r8d, [rdi+4]
0x18000bead  mov     edx, r8d
0x18000beb0  call    ?AUIAuth2Auth@CACSecurityPage@@AEAA?AW4_DOT11_AUTH_ALGORITHM@@W4AUI_DOT11_AUTH_ALGORITHM@@@Z; CACSecurityPage::AUIAuth2Auth(AUI_DOT11_AUTH_ALGORITHM)
0x18000beb5  cmp     [r14], eax
0x18000beb8  jnz     short loc_18000BF2C
0x18000beba  mov     rcx, [rbx+40h]; hWnd
0x18000bebe  mov     edx, r9d; int
0x18000bec1  mov     [rbx+38h], r8d
0x18000bec5  call    ?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z; ComboBox_SetCurSelNotify(HWND__ *,int)
0x18000beca  mov     edx, [r14+4]; unsigned int
0x18000bece  lea     r8d, [r12+1]; int
0x18000bed3  call    ?CreateCipherInfo@CACSecurityPage@@AEAAPEAU_AUI_CIPHER_INFO@@KH@Z; CACSecurityPage::CreateCipherInfo(ulong,int)
0x18000bed8  mov     r15, rax
0x18000bedb  xor     eax, eax
0x18000bedd  test    rdi, rdi
0x18000bee0  jz      short loc_18000BF18
0x18000bee2  cmp     [rdi+0Ch], eax
0x18000bee5  jz      short loc_18000BF04
0x18000bee7  cmp     [rdi], eax
0x18000bee9  jnz     short loc_18000BF04
0x18000beeb  mov     r9, r15; struct _AUI_CIPHER_INFO *
0x18000beee  mov     [rsp+78h+var_58], eax; int
0x18000bef2  lea     r8d, [r12+1]; int
0x18000bef7  mov     rdx, rdi; struct _AUI_AUTH_INFO *
0x18000befa  mov     rcx, rbx; this
0x18000befd  call    ?DisplayCiphersForIHVAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@H@Z; CACSecurityPage::DisplayCiphersForIHVAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *,int)
0x18000bf02  jmp     short loc_18000BF18
0x18000bf04  mov     r9, r15; struct _AUI_CIPHER_INFO *
0x18000bf07  mov     r8d, 1; int
0x18000bf0d  mov     rdx, rdi; struct _AUI_AUTH_INFO *
0x18000bf10  mov     rcx, rbx; this
0x18000bf13  call    ?DisplayCiphersForMSAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@@Z; CACSecurityPage::DisplayCiphersForMSAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *)
0x18000bf18  call    cs:__imp_GetProcessHeap
0x18000bf1e  mov     r8, r15; lpMem
0x18000bf21  xor     edx, edx; dwFlags
0x18000bf23  mov     rcx, rax; hHeap
0x18000bf26  call    cs:__imp_HeapFree
0x18000bf2c  mov     r15d, [rsp+78h+arg_18]
0x18000bf34  mov     rsi, [rsi+8]
0x18000bf38  test    rsi, rsi
0x18000bf3b  jnz     loc_18000BE21
0x18000bf41  test    r13d, r13d
0x18000bf44  jz      loc_18000C034
0x18000bf4a  mov     rcx, cs:hInstance; hInstance
0x18000bf51  lea     rsi, [rbx+60h]
0x18000bf55  mov     r8, rsi; lpBuffer
0x18000bf58  mov     r9d, 100h; cchBufferMax
0x18000bf5e  mov     edx, 42D2h; uID
0x18000bf63  call    cs:__imp_LoadStringW
0x18000bf69  xor     r13d, r13d
0x18000bf6c  mov     [rsp+78h+var_50], 0FFFFFFFFh
0x18000bf74  mov     r8d, 7FFFFFFFh
0x18000bf7a  mov     [rsp+78h+var_58], r13d
0x18000bf7f  lea     eax, [r13+1]
0x18000bf83  mov     r9d, eax
0x18000bf86  mov     edx, eax
0x18000bf88  call    ?CreateAuthInfo@CACSecurityPage@@AEAAPEAU_AUI_AUTH_INFO@@HW4AUI_DOT11_AUTH_ALGORITHM@@HHK@Z; CACSecurityPage::CreateAuthInfo(int,AUI_DOT11_AUTH_ALGORITHM,int,int,ulong)
0x18000bf8d  mov     rdi, rax
0x18000bf90  test    rsi, rsi
0x18000bf93  jz      loc_18000C02F
0x18000bf99  test    rax, rax
0x18000bf9c  jz      loc_18000C02F
0x18000bfa2  mov     rcx, [rbx+40h]; hWnd
0x18000bfa6  mov     r8, rax; LPARAM
0x18000bfa9  mov     rdx, rsi; lParam
0x18000bfac  call    ?ComboBox_AddItem@@YAHPEAUHWND__@@PEBGPEAX@Z; ComboBox_AddItem(HWND__ *,ushort const *,void *)
0x18000bfb1  inc     dword ptr [rbx+4D8h]
0x18000bfb7  mov     edx, eax; int
0x18000bfb9  test    r15d, r15d
0x18000bfbc  jz      short loc_18000C034
0x18000bfbe  test    r12d, r12d
0x18000bfc1  jz      short loc_18000C034
0x18000bfc3  mov     eax, [rdi+4]
0x18000bfc6  mov     rcx, [rbx+40h]; hWnd
0x18000bfca  mov     [rbx+38h], eax
0x18000bfcd  call    ?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z; ComboBox_SetCurSelNotify(HWND__ *,int)
0x18000bfd2  mov     edx, [r14+4]; unsigned int
0x18000bfd6  lea     r15d, [r13+1]
0x18000bfda  mov     r8d, r15d; int
0x18000bfdd  call    ?CreateCipherInfo@CACSecurityPage@@AEAAPEAU_AUI_CIPHER_INFO@@KH@Z; CACSecurityPage::CreateCipherInfo(ulong,int)
0x18000bfe2  mov     rsi, rax
0x18000bfe5  cmp     [rdi+0Ch], r13d
0x18000bfe9  jz      short loc_18000C008
0x18000bfeb  cmp     [rdi], r13d
0x18000bfee  jnz     short loc_18000C008
0x18000bff0  mov     r9, rax; struct _AUI_CIPHER_INFO *
0x18000bff3  mov     [rsp+78h+var_58], r13d; int
0x18000bff8  mov     r8d, r15d; int
0x18000bffb  mov     rdx, rdi; struct _AUI_AUTH_INFO *
0x18000bffe  mov     rcx, rbx; this
0x18000c001  call    ?DisplayCiphersForIHVAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@H@Z; CACSecurityPage::DisplayCiphersForIHVAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *,int)
0x18000c006  jmp     short loc_18000C019
0x18000c008  mov     r9, rsi; struct _AUI_CIPHER_INFO *
0x18000c00b  mov     r8d, r15d; int
0x18000c00e  mov     rdx, rdi; struct _AUI_AUTH_INFO *
0x18000c011  mov     rcx, rbx; this
0x18000c014  call    ?DisplayCiphersForMSAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@@Z; CACSecurityPage::DisplayCiphersForMSAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *)
0x18000c019  call    cs:__imp_GetProcessHeap
0x18000c01f  mov     r8, rsi; lpMem
0x18000c022  xor     edx, edx; dwFlags
0x18000c024  mov     rcx, rax; hHeap
0x18000c027  call    cs:__imp_HeapFree
0x18000c02d  jmp     short loc_18000C034
0x18000c02f  mov     ebp, 8007000Eh
0x18000c034  mov     eax, ebp
0x18000c036  add     rsp, 38h
0x18000c03a  pop     r15
0x18000c03c  pop     r14
0x18000c03e  pop     r13
0x18000c040  pop     r12
0x18000c042  pop     rdi
0x18000c043  pop     rsi
0x18000c044  pop     rbp
0x18000c045  pop     rbx
0x18000c046  retn
```
