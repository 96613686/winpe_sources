# CACSecurityPage::InitAuthCipherData(void)

- ea: `0x180008720`
- end: `0x18000893b`
- name: `?InitAuthCipherData@CACSecurityPage@@AEAAJXZ`
- size: `539`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000a7f8`

## callees

- `0x1800078f4`
- `0x180007ae4`
- `0x18000833c`
- `0x180008388`
- `0x180008720`
- `0x18000b63c`
- `0x18000b6f8`
- `0x18000ba98`
- `0x18000bb54`
- `0x18000bd88`
- `0x18000c050`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180008860`
- `KERNEL32!HeapAlloc` at `0x180008860`
- `KERNEL32!GetProcessHeap` at `0x18000884f`
- `KERNEL32!GetProcessHeap` at `0x1800088c6`
- `KERNEL32!GetProcessHeap` at `0x18000884f`
- `KERNEL32!GetProcessHeap` at `0x1800088c6`
- `KERNEL32!HeapFree` at `0x1800088d4`
- `KERNEL32!HeapFree` at `0x1800088d4`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::InitAuthCipherData(CACSecurityPage *this)
{
  __int64 v2; // r15
  __int64 v3; // rax
  __int64 v4; // r13
  int v5; // ebp
  int v6; // r14d
  int v7; // r12d
  int v8; // esi
  __int64 v9; // rcx
  int v10; // edx
  int v11; // r8d
  HANDLE ProcessHeap; // rax
  struct _AUI_CIPHER_INFO *v13; // r14
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rax
  HANDLE v15; // rax
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // rbp
  struct _AUI_AUTH_INFO *v17; // rax
  int v19; // [rsp+80h] [rbp+8h] BYREF

  v19 = 0;
  v2 = *(_QWORD *)(*((_QWORD *)this + 5) + 552LL);
  v3 = *(_QWORD *)(v2 + 32);
  v4 = *(_QWORD *)(v3 + 424);
  if ( !*(_DWORD *)(v3 + 432) )
  {
    v5 = 1;
    v6 = 0;
LABEL_5:
    v7 = 0;
    goto LABEL_7;
  }
  v5 = 0;
  if ( *(_DWORD *)(v3 + 436) )
  {
    v6 = 1;
    goto LABEL_5;
  }
  v6 = 0;
  v7 = 1;
LABEL_7:
  v8 = CACSecurityPage::PopulateMSAuthList(this, &v19);
  if ( v8 >= 0 )
  {
    if ( *(_DWORD *)(v2 + 16) != 2 )
    {
      CACSecurityPage::PopulateIHVOneXAuthList(this);
      CACSecurityPage::PopulateIHVSecAuthList(this);
    }
    v9 = *(_QWORD *)(v4 + 24);
    *(_QWORD *)((char *)this + 1316) = *(_QWORD *)v9;
    v11 = 0;
    if ( v9 )
    {
      if ( v5 )
      {
        if ( *(_DWORD *)v9 == 1 )
        {
          v10 = *(_DWORD *)(v9 + 4);
          if ( ((v10 - 1) & 0xFFFFFEFB) == 0 && v10 != 261 && *(_DWORD *)(v4 + 32) )
            v11 = 1;
        }
      }
    }
    v8 = CACSecurityPage::PopulateMSAuthDropdown(this, v19, v11, v5);
    if ( v8 >= 0 )
    {
      if ( *(_DWORD *)(v2 + 16) == 2
        || (v8 = CACSecurityPage::PopulateIHVOneXDropdown(this, v6), v8 >= 0)
        && (v8 = CACSecurityPage::PopulateIHVSecDropdown(this, v7), v8 >= 0) )
      {
        if ( CACSecurityPage::GetCurrentlySelectedCipher(this) )
        {
          ProcessHeap = GetProcessHeap();
          v13 = (struct _AUI_CIPHER_INFO *)HeapAlloc(ProcessHeap, 8u, 8u);
          *(_DWORD *)v13 = *(_DWORD *)CACSecurityPage::GetCurrentlySelectedCipher(this);
          *((_DWORD *)v13 + 1) = *((_DWORD *)CACSecurityPage::GetCurrentlySelectedCipher(this) + 1);
          CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth((HWND *)this);
          if ( CurrentlySelectedAuth )
          {
            if ( !*((_DWORD *)CurrentlySelectedAuth + 3) || *(_DWORD *)CurrentlySelectedAuth )
              CACSecurityPage::DisplayCiphersForMSAuth(this, CurrentlySelectedAuth, 1, v13);
            else
              CACSecurityPage::DisplayCiphersForIHVAuth((HWND *)this, CurrentlySelectedAuth, 1, v13, 0);
          }
          v15 = GetProcessHeap();
          HeapFree(v15, 0, v13);
        }
        else
        {
          CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher(this);
          v17 = CACSecurityPage::GetCurrentlySelectedAuth((HWND *)this);
          if ( v17 )
          {
            if ( !*((_DWORD *)v17 + 3) || *(_DWORD *)v17 )
              CACSecurityPage::DisplayCiphersForMSAuth(this, v17, 1, CurrentlySelectedCipher);
            else
              CACSecurityPage::DisplayCiphersForIHVAuth((HWND *)this, v17, 1, CurrentlySelectedCipher, 0);
          }
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008720  mov     rax, rsp
0x180008723  push    rbx
0x180008724  push    rbp
0x180008725  push    rsi
0x180008726  push    rdi
0x180008727  push    r12
0x180008729  push    r13
0x18000872b  push    r14
0x18000872d  push    r15
0x18000872f  sub     rsp, 38h
0x180008733  mov     rbx, rcx
0x180008736  xor     ecx, ecx
0x180008738  mov     [rax+8], ecx
0x18000873b  mov     rax, [rbx+28h]
0x18000873f  lea     edi, [rcx+1]
0x180008742  mov     r15, [rax+228h]
0x180008749  mov     rax, [r15+20h]
0x18000874d  mov     r13, [rax+1A8h]
0x180008754  cmp     [rax+1B0h], ecx
0x18000875a  jnz     short loc_180008763
0x18000875c  mov     ebp, edi
0x18000875e  mov     r14d, ecx
0x180008761  jmp     short loc_180008770
0x180008763  mov     ebp, ecx
0x180008765  cmp     [rax+1B4h], ecx
0x18000876b  jz      short loc_180008775
0x18000876d  mov     r14d, edi
0x180008770  mov     r12d, ecx
0x180008773  jmp     short loc_18000877B
0x180008775  mov     r14d, ecx
0x180008778  mov     r12d, edi
0x18000877b  lea     rdx, [rsp+78h+arg_0]; int *
0x180008783  mov     rcx, rbx; this
0x180008786  call    ?PopulateMSAuthList@CACSecurityPage@@AEAAJPEAH@Z; CACSecurityPage::PopulateMSAuthList(int *)
0x18000878b  mov     esi, eax
0x18000878d  test    eax, eax
0x18000878f  js      loc_180008928
0x180008795  cmp     dword ptr [r15+10h], 2
0x18000879a  jz      short loc_1800087AC
0x18000879c  mov     rcx, rbx; this
0x18000879f  call    ?PopulateIHVOneXAuthList@CACSecurityPage@@AEAAJXZ; CACSecurityPage::PopulateIHVOneXAuthList(void)
0x1800087a4  mov     rcx, rbx; this
0x1800087a7  call    ?PopulateIHVSecAuthList@CACSecurityPage@@AEAAJXZ; CACSecurityPage::PopulateIHVSecAuthList(void)
0x1800087ac  mov     rcx, [r13+18h]
0x1800087b0  mov     rax, [rcx]
0x1800087b3  mov     [rbx+524h], rax
0x1800087ba  test    rcx, rcx
0x1800087bd  jz      short loc_1800087EB
0x1800087bf  test    ebp, ebp
0x1800087c1  jz      short loc_1800087EB
0x1800087c3  cmp     [rcx], edi
0x1800087c5  jnz     short loc_1800087EB
0x1800087c7  mov     edx, [rcx+4]
0x1800087ca  lea     eax, [rdx-1]
0x1800087cd  test    eax, 0FFFFFEFBh
0x1800087d2  jnz     short loc_1800087EB
0x1800087d4  cmp     edx, 105h
0x1800087da  jz      short loc_1800087EB
0x1800087dc  cmp     dword ptr [r13+20h], 0
0x1800087e1  jz      short loc_1800087EB
0x1800087e3  mov     r8d, edi
0x1800087e6  xor     r13d, r13d
0x1800087e9  jmp     short loc_1800087F1
0x1800087eb  xor     r13d, r13d
0x1800087ee  mov     r8d, r13d; int
0x1800087f1  mov     edx, [rsp+78h+arg_0]; int
0x1800087f8  mov     r9d, ebp; int
0x1800087fb  mov     rcx, rbx; this
0x1800087fe  call    ?PopulateMSAuthDropdown@CACSecurityPage@@AEAAJHHH@Z; CACSecurityPage::PopulateMSAuthDropdown(int,int,int)
0x180008803  mov     esi, eax
0x180008805  test    eax, eax
0x180008807  js      loc_180008928
0x18000880d  cmp     dword ptr [r15+10h], 2
0x180008812  jz      short loc_18000883E
0x180008814  mov     edx, r14d; int
0x180008817  mov     rcx, rbx; this
0x18000881a  call    ?PopulateIHVOneXDropdown@CACSecurityPage@@AEAAJH@Z; CACSecurityPage::PopulateIHVOneXDropdown(int)
0x18000881f  mov     esi, eax
0x180008821  test    eax, eax
0x180008823  js      loc_180008928
0x180008829  mov     edx, r12d; int
0x18000882c  mov     rcx, rbx; this
0x18000882f  call    ?PopulateIHVSecDropdown@CACSecurityPage@@AEAAJH@Z; CACSecurityPage::PopulateIHVSecDropdown(int)
0x180008834  mov     esi, eax
0x180008836  test    eax, eax
0x180008838  js      loc_180008928
0x18000883e  mov     rcx, rbx; this
0x180008841  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x180008846  test    rax, rax
0x180008849  jz      loc_1800088DC
0x18000884f  call    cs:__imp_GetProcessHeap
0x180008855  mov     edx, 8; dwFlags
0x18000885a  mov     rcx, rax; hHeap
0x18000885d  mov     r8d, edx; dwBytes
0x180008860  call    cs:__imp_HeapAlloc
0x180008866  mov     rcx, rbx; this
0x180008869  mov     r14, rax
0x18000886c  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x180008871  mov     ecx, [rax]
0x180008873  mov     [r14], ecx
0x180008876  mov     rcx, rbx; this
0x180008879  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000887e  mov     ecx, [rax+4]
0x180008881  mov     [r14+4], ecx
0x180008885  mov     rcx, rbx; this
0x180008888  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000888d  test    rax, rax
0x180008890  jz      short loc_1800088C6
0x180008892  cmp     [rax+0Ch], r13d
0x180008896  jz      short loc_1800088B5
0x180008898  cmp     [rax], r13d
0x18000889b  jnz     short loc_1800088B5
0x18000889d  mov     r9, r14; struct _AUI_CIPHER_INFO *
0x1800088a0  mov     [rsp+78h+var_58], r13d; int
0x1800088a5  mov     r8d, edi; int
0x1800088a8  mov     rdx, rax; struct _AUI_AUTH_INFO *
0x1800088ab  mov     rcx, rbx; this
0x1800088ae  call    ?DisplayCiphersForIHVAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@H@Z; CACSecurityPage::DisplayCiphersForIHVAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *,int)
0x1800088b3  jmp     short loc_1800088C6
0x1800088b5  mov     r9, r14; struct _AUI_CIPHER_INFO *
0x1800088b8  mov     r8d, edi; int
0x1800088bb  mov     rdx, rax; struct _AUI_AUTH_INFO *
0x1800088be  mov     rcx, rbx; this
0x1800088c1  call    ?DisplayCiphersForMSAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@@Z; CACSecurityPage::DisplayCiphersForMSAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *)
0x1800088c6  call    cs:__imp_GetProcessHeap
0x1800088cc  mov     r8, r14; lpMem
0x1800088cf  xor     edx, edx; dwFlags
0x1800088d1  mov     rcx, rax; hHeap
0x1800088d4  call    cs:__imp_HeapFree
0x1800088da  jmp     short loc_180008928
0x1800088dc  mov     rcx, rbx; this
0x1800088df  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x1800088e4  mov     rcx, rbx; this
0x1800088e7  mov     rbp, rax
0x1800088ea  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x1800088ef  test    rax, rax
0x1800088f2  jz      short loc_180008928
0x1800088f4  cmp     [rax+0Ch], r13d
0x1800088f8  jz      short loc_180008917
0x1800088fa  cmp     [rax], r13d
0x1800088fd  jnz     short loc_180008917
0x1800088ff  mov     r9, rbp; struct _AUI_CIPHER_INFO *
0x180008902  mov     [rsp+78h+var_58], r13d; int
0x180008907  mov     r8d, edi; int
0x18000890a  mov     rdx, rax; struct _AUI_AUTH_INFO *
0x18000890d  mov     rcx, rbx; this
0x180008910  call    ?DisplayCiphersForIHVAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@H@Z; CACSecurityPage::DisplayCiphersForIHVAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *,int)
0x180008915  jmp     short loc_180008928
0x180008917  mov     r9, rbp; struct _AUI_CIPHER_INFO *
0x18000891a  mov     r8d, edi; int
0x18000891d  mov     rdx, rax; struct _AUI_AUTH_INFO *
0x180008920  mov     rcx, rbx; this
0x180008923  call    ?DisplayCiphersForMSAuth@CACSecurityPage@@AEAAXPEAU_AUI_AUTH_INFO@@HPEAU_AUI_CIPHER_INFO@@@Z; CACSecurityPage::DisplayCiphersForMSAuth(_AUI_AUTH_INFO *,int,_AUI_CIPHER_INFO *)
0x180008928  mov     eax, esi
0x18000892a  add     rsp, 38h
0x18000892e  pop     r15
0x180008930  pop     r14
0x180008932  pop     r13
0x180008934  pop     r12
0x180008936  pop     rdi
0x180008937  pop     rsi
0x180008938  pop     rbp
0x180008939  pop     rbx
0x18000893a  retn
```
