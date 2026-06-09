# CACSecurityPage::OnConfigureButton(ushort,ushort,HWND__ *,int &)

- ea: `0x180009f38`
- end: `0x18000a18d`
- name: `?OnConfigureButton@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `597`
- prototype: `__int64 __usercall@<rax>(CACSecurityPage *__hidden this@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, HWND@<r9>, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x180001e26`
- `0x180006134`
- `0x180008498`
- `0x180009f38`
- `0x18001d010`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x180009f8e`
- `USER32!IsWindowEnabled` at `0x180009f8e`
- `USER32!IsWindowVisible` at `0x180009f6e`
- `USER32!IsWindowVisible` at `0x180009f6e`
- `USER32!GetDlgItem` at `0x180009f65`
- `USER32!GetDlgItem` at `0x180009f85`
- `USER32!GetDlgItem` at `0x180009fce`
- `USER32!GetDlgItem` at `0x180009f65`
- `USER32!GetDlgItem` at `0x180009f85`
- `USER32!GetDlgItem` at `0x180009fce`
- `USER32!SendMessageW` at `0x180009ffd`
- `USER32!SendMessageW` at `0x18000a01c`
- `USER32!SendMessageW` at `0x180009ffd`
- `USER32!SendMessageW` at `0x18000a01c`
- `wlanapi!WpFreeMemory` at `0x18000a0fd`
- `wlanapi!WpFreeMemory` at `0x18000a0fd`
- `wlanapi!WpAllocMemory` at `0x18000a106`
- `wlanapi!WpAllocMemory` at `0x18000a106`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a054`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a05d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a054`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a05d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a142`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a15c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a142`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a15c`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnConfigureButton(HWND *this, __int64 a2, __int16 a3, HWND a4, int *a5)
{
  HWND DlgItem; // rax
  HWND v7; // rax
  int *v8; // r12
  __int64 v9; // rcx
  __int64 v10; // rbp
  HWND v11; // rcx
  HWND v12; // rax
  HWND v13; // rdi
  int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rdx
  const OLECHAR *v18; // rcx
  OLECHAR *v19; // rsi
  const OLECHAR *v20; // rax
  __int64 v21; // r14
  unsigned int v22; // edi
  struct _DOT11EXT_IHV_PARAMS *UpdatedIHVParams; // r9
  unsigned int v24; // edi
  __int64 v25; // rcx
  void *v26; // r15
  __int64 v27; // rax
  __int64 v28; // rcx
  size_t v29; // r14
  void *v30; // rax
  void *v31; // rdi
  int v33; // [rsp+90h] [rbp+18h] BYREF
  void *Src; // [rsp+98h] [rbp+20h] BYREF

  Src = a4;
  LOWORD(v33) = a3;
  DlgItem = GetDlgItem(this[1], 15079);
  if ( !IsWindowVisible(DlgItem) )
    return 0;
  v7 = GetDlgItem(this[1], 15079);
  if ( !IsWindowEnabled(v7) )
    return 0;
  v8 = a5;
  v9 = *((_QWORD *)this[5] + 69);
  *a5 = 0;
  v10 = *(_QWORD *)(v9 + 32);
  v11 = this[1];
  Src = 0;
  v33 = 0;
  v12 = GetDlgItem(v11, 15078);
  v13 = v12;
  if ( !this[154] || !v12 )
  {
    v14 = -2147467259;
    goto LABEL_27;
  }
  if ( (int)SendMessageW(v12, 0x147u, 0, 0) >= 0 )
  {
    v15 = SendMessageW(v13, 0x147u, 0, 0);
    v16 = v15;
    v17 = *((_QWORD *)this[154] + 4);
    if ( !*(_DWORD *)(v17 + 8) )
    {
      v14 = -2147467263;
      goto LABEL_27;
    }
    if ( v15 < *(_DWORD *)(v17 + 8) )
    {
      v18 = *(const OLECHAR **)(v10 + 440);
      v19 = 0;
      if ( v18 )
      {
        v20 = SysAllocString(v18);
        v19 = SysAllocString(v20);
      }
      v21 = *((_QWORD *)this[154] + 4);
      v22 = *(_DWORD *)(v21 + 36) + v16;
      UpdatedIHVParams = CACSecurityPage::GetUpdatedIHVParams((CACSecurityPage *)this);
      if ( v22 )
        v24 = v22 - *(_DWORD *)(v21 + 36);
      else
        v24 = 0;
      v25 = *(_QWORD *)(*(_QWORD *)v21 + 8LL * v24);
      v14 = (*(__int64 (__fastcall **)(__int64, HWND, OLECHAR *, struct _DOT11EXT_IHV_PARAMS *, void **, int *))(*(_QWORD *)v25 + 32LL))(
              v25,
              this[1],
              v19,
              UpdatedIHVParams,
              &Src,
              &v33);
      if ( v14 >= 0 && v33 )
      {
        v26 = Src;
        v27 = -1;
        do
          ++v27;
        while ( *((_WORD *)Src + v27) );
        v28 = *(_QWORD *)(v10 + 440);
        v29 = 2 * v27 + 2;
        if ( v28 )
          WpFreeMemory(v28);
        v30 = (void *)WpAllocMemory(v29);
        v31 = v30;
        if ( v30 )
        {
          memcpy_0(v30, v26, v29);
          *(_QWORD *)(v10 + 440) = v31;
          *(_DWORD *)(v10 + 432) = 1;
        }
        else
        {
          v14 = -2147024882;
        }
      }
      if ( v19 )
        SysFreeString(v19);
      goto LABEL_27;
    }
  }
  v14 = -2147418113;
LABEL_27:
  if ( Src )
    SysFreeString((BSTR)Src);
  *v8 = 1;
  return LresFromHr(v14);
}

```

## disassembly

```asm
0x180009f38  mov     [rsp+arg_0], rbx
0x180009f3d  mov     [rsp+Src], r9
0x180009f42  mov     word ptr [rsp+arg_10], r8w
0x180009f48  push    rbp
0x180009f49  push    rsi
0x180009f4a  push    rdi
0x180009f4b  push    r12
0x180009f4d  push    r13
0x180009f4f  push    r14
0x180009f51  push    r15
0x180009f53  sub     rsp, 40h
0x180009f57  mov     rbx, rcx
0x180009f5a  mov     edi, 3AE7h
0x180009f5f  mov     rcx, [rcx+8]; hDlg
0x180009f63  mov     edx, edi; nIDDlgItem
0x180009f65  call    cs:__imp_GetDlgItem
0x180009f6b  mov     rcx, rax; hWnd
0x180009f6e  call    cs:__imp_IsWindowVisible
0x180009f74  xor     r13d, r13d
0x180009f77  test    eax, eax
0x180009f79  jz      loc_18000A173
0x180009f7f  mov     rcx, [rbx+8]; hDlg
0x180009f83  mov     edx, edi; nIDDlgItem
0x180009f85  call    cs:__imp_GetDlgItem
0x180009f8b  mov     rcx, rax; hWnd
0x180009f8e  call    cs:__imp_IsWindowEnabled
0x180009f94  test    eax, eax
0x180009f96  jz      loc_18000A173
0x180009f9c  mov     rax, [rbx+28h]
0x180009fa0  lea     edx, [rdi-1]; nIDDlgItem
0x180009fa3  mov     r12, [rsp+78h+arg_20]
0x180009fab  mov     rcx, [rax+228h]
0x180009fb2  mov     [r12], r13d
0x180009fb6  mov     rbp, [rcx+20h]
0x180009fba  mov     rcx, [rbx+8]; hDlg
0x180009fbe  mov     [rsp+78h+Src], r13
0x180009fc6  mov     [rsp+78h+arg_10], r13d
0x180009fce  call    cs:__imp_GetDlgItem
0x180009fd4  mov     rdi, rax
0x180009fd7  cmp     [rbx+4D0h], r13
0x180009fde  jz      loc_18000A14A
0x180009fe4  test    rax, rax
0x180009fe7  jz      loc_18000A14A
0x180009fed  mov     esi, 147h
0x180009ff2  xor     r9d, r9d; lParam
0x180009ff5  mov     edx, esi; Msg
0x180009ff7  xor     r8d, r8d; wParam
0x180009ffa  mov     rcx, rax; hWnd
0x180009ffd  call    cs:__imp_SendMessageW
0x18000a003  test    eax, eax
0x18000a005  jns     short loc_18000A011
0x18000a007  mov     ebx, 8000FFFFh
0x18000a00c  jmp     loc_18000A14F
0x18000a011  xor     r9d, r9d; lParam
0x18000a014  xor     r8d, r8d; wParam
0x18000a017  mov     edx, esi; Msg
0x18000a019  mov     rcx, rdi; hWnd
0x18000a01c  call    cs:__imp_SendMessageW
0x18000a022  mov     rcx, [rbx+4D0h]
0x18000a029  mov     rdi, rax
0x18000a02c  mov     rdx, [rcx+20h]
0x18000a030  cmp     [rdx+8], r13d
0x18000a034  ja      short loc_18000A040
0x18000a036  mov     ebx, 80004001h
0x18000a03b  jmp     loc_18000A14F
0x18000a040  cmp     edi, [rdx+8]
0x18000a043  jnb     short loc_18000A007
0x18000a045  mov     rcx, [rbp+1B8h]; psz
0x18000a04c  mov     rsi, r13
0x18000a04f  test    rcx, rcx
0x18000a052  jz      short loc_18000A066
0x18000a054  call    cs:__imp_SysAllocString
0x18000a05a  mov     rcx, rax; psz
0x18000a05d  call    cs:__imp_SysAllocString
0x18000a063  mov     rsi, rax
0x18000a066  mov     rcx, [rbx+4D0h]
0x18000a06d  mov     r14, [rcx+20h]
0x18000a071  mov     rcx, rbx; this
0x18000a074  add     edi, [r14+24h]
0x18000a078  call    ?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ; CACSecurityPage::GetUpdatedIHVParams(void)
0x18000a07d  mov     r9, rax
0x18000a080  test    edi, edi
0x18000a082  jz      short loc_18000A08A
0x18000a084  sub     edi, [r14+24h]
0x18000a088  jmp     short loc_18000A08D
0x18000a08a  mov     edi, r13d
0x18000a08d  mov     rax, [r14]
0x18000a090  lea     rdx, [rsp+78h+arg_10]
0x18000a098  mov     [rsp+78h+var_50], rdx
0x18000a09d  mov     r8, rsi
0x18000a0a0  lea     rdx, [rsp+78h+Src]
0x18000a0a8  mov     ecx, edi
0x18000a0aa  mov     [rsp+78h+var_58], rdx
0x18000a0af  mov     rdx, [rbx+8]
0x18000a0b3  mov     rcx, [rax+rcx*8]
0x18000a0b7  mov     rax, [rcx]
0x18000a0ba  mov     rax, [rax+20h]
0x18000a0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c3  mov     ebx, eax
0x18000a0c5  test    eax, eax
0x18000a0c7  js      short loc_18000A13A
0x18000a0c9  cmp     [rsp+78h+arg_10], r13d
0x18000a0d1  jz      short loc_18000A13A
0x18000a0d3  mov     r15, [rsp+78h+Src]
0x18000a0db  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a0df  inc     rax
0x18000a0e2  cmp     [r15+rax*2], r13w
0x18000a0e7  jnz     short loc_18000A0DF
0x18000a0e9  mov     rcx, [rbp+1B8h]
0x18000a0f0  lea     r14, ds:2[rax*2]
0x18000a0f8  test    rcx, rcx
0x18000a0fb  jz      short loc_18000A103
0x18000a0fd  call    cs:__imp_WpFreeMemory
0x18000a103  mov     rcx, r14
0x18000a106  call    cs:__imp_WpAllocMemory
0x18000a10c  mov     rdi, rax
0x18000a10f  test    rax, rax
0x18000a112  jnz     short loc_18000A11B
0x18000a114  mov     ebx, 8007000Eh
0x18000a119  jmp     short loc_18000A13A
0x18000a11b  mov     r8, r14; Size
0x18000a11e  mov     rdx, r15; Src
0x18000a121  mov     rcx, rdi; void *
0x18000a124  call    memcpy_0
0x18000a129  mov     [rbp+1B8h], rdi
0x18000a130  mov     dword ptr [rbp+1B0h], 1
0x18000a13a  test    rsi, rsi
0x18000a13d  jz      short loc_18000A14F
0x18000a13f  mov     rcx, rsi; bstrString
0x18000a142  call    cs:__imp_SysFreeString
0x18000a148  jmp     short loc_18000A14F
0x18000a14a  mov     ebx, 80004005h
0x18000a14f  mov     rcx, [rsp+78h+Src]; bstrString
0x18000a157  test    rcx, rcx
0x18000a15a  jz      short loc_18000A162
0x18000a15c  call    cs:__imp_SysFreeString
0x18000a162  mov     ecx, ebx; int
0x18000a164  mov     dword ptr [r12], 1
0x18000a16c  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x18000a171  jmp     short loc_18000A175
0x18000a173  xor     eax, eax
0x18000a175  mov     rbx, [rsp+78h+arg_0]
0x18000a17d  add     rsp, 40h
0x18000a181  pop     r15
0x18000a183  pop     r14
0x18000a185  pop     r13
0x18000a187  pop     r12
0x18000a189  pop     rdi
0x18000a18a  pop     rsi
0x18000a18b  pop     rbp
0x18000a18c  retn
```
