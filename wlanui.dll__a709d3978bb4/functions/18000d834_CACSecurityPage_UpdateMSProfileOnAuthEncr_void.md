# CACSecurityPage::UpdateMSProfileOnAuthEncr(void)

- ea: `0x18000d834`
- end: `0x18000d9a5`
- name: `?UpdateMSProfileOnAuthEncr@CACSecurityPage@@AEAAXXZ`
- size: `369`
- prototype: `void __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009dd0`
- `0x18000a29c`

## callees

- `0x180006f98`
- `0x18000833c`
- `0x180008388`
- `0x18000d834`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000d8dd`
- `KERNEL32!HeapAlloc` at `0x18000d942`
- `KERNEL32!HeapAlloc` at `0x18000d8dd`
- `KERNEL32!HeapAlloc` at `0x18000d942`
- `KERNEL32!GetProcessHeap` at `0x18000d8cb`
- `KERNEL32!GetProcessHeap` at `0x18000d91e`
- `KERNEL32!GetProcessHeap` at `0x18000d932`
- `KERNEL32!GetProcessHeap` at `0x18000d8cb`
- `KERNEL32!GetProcessHeap` at `0x18000d91e`
- `KERNEL32!GetProcessHeap` at `0x18000d932`
- `KERNEL32!HeapFree` at `0x18000d92c`
- `KERNEL32!HeapFree` at `0x18000d92c`

## pseudocode

```c
void __fastcall CACSecurityPage::UpdateMSProfileOnAuthEncr(HWND *this)
{
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rbp
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // r15
  __int64 v4; // rsi
  __int64 v5; // rdi
  struct _AUI_CIPHER_INFO *v6; // rax
  _BOOL8 v7; // rcx
  int v8; // eax
  _DWORD *v9; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v11; // rax
  unsigned int v12; // r14d
  int v13; // esi
  HANDLE v14; // rax
  HANDLE v15; // rax
  _DWORD *v16; // rax
  int v17; // eax

  CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth(this);
  CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher(this);
  v4 = *((_QWORD *)this[5] + 69);
  v5 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 424LL);
  v6 = CACSecurityPage::GetCurrentlySelectedCipher(this);
  if ( !CurrentlySelectedAuth )
    goto LABEL_7;
  v7 = 0;
  if ( *((_DWORD *)CurrentlySelectedAuth + 3) )
    v7 = *(_DWORD *)CurrentlySelectedAuth == 0;
  if ( (!v6 || *(_DWORD *)v6) && !v7 )
  {
LABEL_7:
    *(_DWORD *)(*(_QWORD *)(v4 + 32) + 432LL) = 0;
    v8 = *(_DWORD *)(v5 + 16);
    if ( !v8 || (v9 = *(_DWORD **)(v5 + 24)) == 0 )
    {
      *(_DWORD *)(v5 + 16) = 2;
      ProcessHeap = GetProcessHeap();
      v11 = HeapAlloc(ProcessHeap, 8u, 0x10u);
      *(_QWORD *)(v5 + 24) = v11;
      v9 = v11;
      if ( !v11 )
        return;
      v8 = *(_DWORD *)(v5 + 16);
    }
    v12 = 0;
    v13 = 0;
    if ( CurrentlySelectedAuth && CurrentlySelectedCipher )
    {
      v12 = *((_DWORD *)CurrentlySelectedAuth + 1);
      v13 = *((_DWORD *)CurrentlySelectedCipher + 1);
    }
    if ( v8 != 1
      || v13 != 4
      || (*(_DWORD *)(v5 + 16) = 2,
          v14 = GetProcessHeap(),
          HeapFree(v14, 0, v9),
          v15 = GetProcessHeap(),
          v16 = HeapAlloc(v15, 8u, 0x10u),
          *(_QWORD *)(v5 + 24) = v16,
          (v9 = v16) != 0) )
    {
      *(_DWORD *)(v5 + 16) = (v13 == 4) + 1;
      v17 = CACSecurityPage::AUIAuth2Auth(v7, v12);
      *v9 = v17;
      *(_DWORD *)(*(_QWORD *)(v5 + 24) + 4LL) = v13;
      if ( *(_DWORD *)(v5 + 16) == 2 )
      {
        *(_DWORD *)(*(_QWORD *)(v5 + 24) + 8LL) = v17;
        if ( v13 == 4 )
          *(_DWORD *)(*(_QWORD *)(v5 + 24) + 12LL) = 8;
        else
          *(_DWORD *)(v5 + 16) = 1;
      }
    }
  }
}

```

## disassembly

```asm
0x18000d834  push    rbx
0x18000d836  push    rbp
0x18000d837  push    rsi
0x18000d838  push    rdi
0x18000d839  push    r13
0x18000d83b  push    r14
0x18000d83d  push    r15
0x18000d83f  sub     rsp, 20h
0x18000d843  mov     rbx, rcx
0x18000d846  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000d84b  mov     rcx, rbx; this
0x18000d84e  mov     rbp, rax
0x18000d851  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000d856  mov     rdx, [rbx+28h]
0x18000d85a  mov     rcx, rbx; this
0x18000d85d  mov     r15, rax
0x18000d860  mov     rsi, [rdx+228h]
0x18000d867  mov     rdx, [rsi+20h]
0x18000d86b  mov     rdi, [rdx+1A8h]
0x18000d872  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000d877  mov     r13d, 1
0x18000d87d  test    rbp, rbp
0x18000d880  jz      short loc_18000D8A6
0x18000d882  xor     ecx, ecx
0x18000d884  cmp     [rbp+0Ch], ecx
0x18000d887  jz      short loc_18000D890
0x18000d889  cmp     [rbp+0], ecx
0x18000d88c  cmovz   ecx, r13d
0x18000d890  test    rax, rax
0x18000d893  jz      short loc_18000D89E
0x18000d895  cmp     dword ptr [rax], 0
0x18000d898  jz      loc_18000D996
0x18000d89e  test    ecx, ecx
0x18000d8a0  jnz     loc_18000D996
0x18000d8a6  mov     rax, [rsi+20h]
0x18000d8aa  mov     dword ptr [rax+1B0h], 0
0x18000d8b4  mov     eax, [rdi+10h]
0x18000d8b7  test    eax, eax
0x18000d8b9  jz      short loc_18000D8C4
0x18000d8bb  mov     rbx, [rdi+18h]
0x18000d8bf  test    rbx, rbx
0x18000d8c2  jnz     short loc_18000D8F6
0x18000d8c4  mov     dword ptr [rdi+10h], 2
0x18000d8cb  call    cs:__imp_GetProcessHeap
0x18000d8d1  mov     edx, 8; dwFlags
0x18000d8d6  mov     rcx, rax; hHeap
0x18000d8d9  lea     r8d, [rdx+8]; dwBytes
0x18000d8dd  call    cs:__imp_HeapAlloc
0x18000d8e3  mov     [rdi+18h], rax
0x18000d8e7  mov     rbx, rax
0x18000d8ea  test    rax, rax
0x18000d8ed  jz      loc_18000D996
0x18000d8f3  mov     eax, [rdi+10h]
0x18000d8f6  xor     r14d, r14d
0x18000d8f9  xor     esi, esi
0x18000d8fb  test    rbp, rbp
0x18000d8fe  jz      short loc_18000D90D
0x18000d900  test    r15, r15
0x18000d903  jz      short loc_18000D90D
0x18000d905  mov     r14d, [rbp+4]
0x18000d909  mov     esi, [r15+4]
0x18000d90d  cmp     eax, r13d
0x18000d910  jnz     short loc_18000D954
0x18000d912  cmp     esi, 4
0x18000d915  jnz     short loc_18000D954
0x18000d917  mov     dword ptr [rdi+10h], 2
0x18000d91e  call    cs:__imp_GetProcessHeap
0x18000d924  mov     r8, rbx; lpMem
0x18000d927  xor     edx, edx; dwFlags
0x18000d929  mov     rcx, rax; hHeap
0x18000d92c  call    cs:__imp_HeapFree
0x18000d932  call    cs:__imp_GetProcessHeap
0x18000d938  mov     rcx, rax; hHeap
0x18000d93b  lea     edx, [rsi+4]; dwFlags
0x18000d93e  lea     r8d, [rsi+0Ch]; dwBytes
0x18000d942  call    cs:__imp_HeapAlloc
0x18000d948  mov     [rdi+18h], rax
0x18000d94c  mov     rbx, rax
0x18000d94f  test    rax, rax
0x18000d952  jz      short loc_18000D996
0x18000d954  xor     eax, eax
0x18000d956  mov     edx, r14d
0x18000d959  cmp     esi, 4
0x18000d95c  setz    al
0x18000d95f  add     eax, r13d
0x18000d962  mov     [rdi+10h], eax
0x18000d965  call    ?AUIAuth2Auth@CACSecurityPage@@AEAA?AW4_DOT11_AUTH_ALGORITHM@@W4AUI_DOT11_AUTH_ALGORITHM@@@Z; CACSecurityPage::AUIAuth2Auth(AUI_DOT11_AUTH_ALGORITHM)
0x18000d96a  mov     [rbx], eax
0x18000d96c  mov     rcx, [rdi+18h]
0x18000d970  mov     [rcx+4], esi
0x18000d973  cmp     dword ptr [rdi+10h], 2
0x18000d977  jnz     short loc_18000D996
0x18000d979  mov     rcx, [rdi+18h]
0x18000d97d  mov     [rcx+8], eax
0x18000d980  cmp     esi, 4
0x18000d983  jnz     short loc_18000D992
0x18000d985  mov     rax, [rdi+18h]
0x18000d989  mov     dword ptr [rax+0Ch], 8
0x18000d990  jmp     short loc_18000D996
0x18000d992  mov     [rdi+10h], r13d
0x18000d996  add     rsp, 20h
0x18000d99a  pop     r15
0x18000d99c  pop     r14
0x18000d99e  pop     r13
0x18000d9a0  pop     rdi
0x18000d9a1  pop     rsi
0x18000d9a2  pop     rbp
0x18000d9a3  pop     rbx
0x18000d9a4  retn
```
