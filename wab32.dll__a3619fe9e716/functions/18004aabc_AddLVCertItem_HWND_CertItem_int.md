# AddLVCertItem(HWND__ *,_CertItem *,int)

- ea: `0x18004aabc`
- end: `0x18004ac65`
- name: `?AddLVCertItem@@YAHPEAUHWND__@@PEAU_CertItem@@H@Z`
- size: `425`
- prototype: `__int64 __fastcall(HWND hWnd, struct _CertItem *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180054358`

## callees

- `0x18004aabc`
- `0x180052fdc`
- `0x1800685fc`
- `0x180091eaa`

## import_xrefs

- `USER32!SendMessageW` at `0x18004ab04`
- `USER32!SendMessageW` at `0x18004ab43`
- `USER32!SendMessageW` at `0x18004abae`
- `USER32!SendMessageW` at `0x18004abf4`
- `USER32!SendMessageW` at `0x18004ac09`
- `USER32!SendMessageW` at `0x18004ac42`
- `USER32!SendMessageW` at `0x18004ab04`
- `USER32!SendMessageW` at `0x18004ab43`
- `USER32!SendMessageW` at `0x18004abae`
- `USER32!SendMessageW` at `0x18004abf4`
- `USER32!SendMessageW` at `0x18004ac09`
- `USER32!SendMessageW` at `0x18004ac42`
- `USER32!GetParent` at `0x18004ac2e`
- `USER32!GetParent` at `0x18004ac2e`
- `CRYPT32!CertCompareCertificate` at `0x18004ab6a`
- `CRYPT32!CertCompareCertificate` at `0x18004ab6a`

## pseudocode

```c
__int64 __fastcall AddLVCertItem(HWND hWnd, struct _CertItem *a2)
{
  int v4; // r14d
  int i; // esi
  char **v6; // rax
  char *v7; // rax
  _DWORD *v8; // rax
  bool v9; // zf
  int v10; // edx
  HWND Parent; // rax
  _DWORD v13[6]; // [rsp+20h] [rbp-99h] BYREF
  char *v14; // [rsp+38h] [rbp-81h]
  int v15; // [rsp+44h] [rbp-75h]
  struct _CertItem *v16; // [rsp+48h] [rbp-71h]
  _DWORD lParam[10]; // [rsp+80h] [rbp-39h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h]

  memset_0(v13, 0, 0x58u);
  if ( a2 )
  {
    v4 = SendMessageW(hWnd, 0x1004u, 0, 0);
    for ( i = 0; i < v4; ++i )
    {
      memset_0(lParam, 0, 0x58u);
      lParam[0] = 4;
      lParam[1] = i;
      lParam[2] = 0;
      if ( (unsigned int)SendMessageW(hWnd, 0x104Bu, 0, (LPARAM)lParam)
        && CertCompareCertificate(
             1u,
             *(PCERT_INFO *)(*(_QWORD *)(*(_QWORD *)v18 + 40LL) + 24LL),
             *(PCERT_INFO *)(*(_QWORD *)(*(_QWORD *)a2 + 40LL) + 24LL)) )
      {
        goto LABEL_19;
      }
    }
    v6 = *(char ***)a2;
    v13[0] = 7;
    if ( *((_DWORD *)v6 + 5) )
      v7 = (char *)a2 + 16;
    else
      v7 = *v6;
    v14 = v7;
    v13[1] = SendMessageW(hWnd, 0x1004u, 0, 0);
    v8 = *(_DWORD **)a2;
    v13[2] = 0;
    if ( v8[7] || v8[6] || (v9 = v8[8] == 0, v15 = 0, v9) )
      v15 = 1;
    v16 = a2;
    i = SendMessageW(hWnd, 0x104Du, 0, (LPARAM)v13);
    if ( (unsigned int)SendMessageW(hWnd, 0x1004u, 0, 0) == 1 )
    {
      v10 = 0;
    }
    else
    {
      if ( !*(_DWORD *)(*(_QWORD *)a2 + 20LL) )
      {
LABEL_19:
        Parent = GetParent(hWnd);
        SendMessageW(Parent, 0x28u, (WPARAM)hWnd, 1);
        LVSelectItem(hWnd, i);
        return 1;
      }
      v10 = i;
    }
    SetLVDefaultCert(hWnd, v10);
    goto LABEL_19;
  }
  return 1;
}

```

## disassembly

```asm
0x18004aabc  push    rbp
0x18004aabe  push    rbx
0x18004aabf  push    rsi
0x18004aac0  push    rdi
0x18004aac1  push    r12
0x18004aac3  push    r14
0x18004aac5  lea     rbp, [rsp-2Fh]
0x18004aaca  sub     rsp, 0E8h
0x18004aad1  mov     rdi, rdx
0x18004aad4  mov     rbx, rcx
0x18004aad7  xor     edx, edx; Val
0x18004aad9  lea     rcx, [rsp+110h+var_F0]; void *
0x18004aade  lea     r8d, [rdx+58h]; Size
0x18004aae2  call    memset_0
0x18004aae7  mov     r12d, 1
0x18004aaed  test    rdi, rdi
0x18004aaf0  jz      loc_18004AC52
0x18004aaf6  xor     r9d, r9d; lParam
0x18004aaf9  xor     r8d, r8d; wParam
0x18004aafc  mov     edx, 1004h; Msg
0x18004ab01  mov     rcx, rbx; hWnd
0x18004ab04  call    cs:__imp_SendMessageW
0x18004ab0a  mov     r14, rax
0x18004ab0d  xor     esi, esi
0x18004ab0f  cmp     esi, r14d
0x18004ab12  jge     short loc_18004AB7D
0x18004ab14  xor     edx, edx; Val
0x18004ab16  lea     rcx, [rbp+57h+lParam]; void *
0x18004ab1a  lea     r8d, [rdx+58h]; Size
0x18004ab1e  call    memset_0
0x18004ab23  lea     r9, [rbp+57h+lParam]; lParam
0x18004ab27  mov     dword ptr [rbp+57h+lParam], 4
0x18004ab2e  xor     r8d, r8d; wParam
0x18004ab31  mov     dword ptr [rbp+57h+lParam+4], esi
0x18004ab34  mov     edx, 104Bh; Msg
0x18004ab39  mov     [rbp+57h+var_88], 0
0x18004ab40  mov     rcx, rbx; hWnd
0x18004ab43  call    cs:__imp_SendMessageW
0x18004ab49  test    eax, eax
0x18004ab4b  jz      short loc_18004AB78
0x18004ab4d  mov     rax, [rdi]
0x18004ab50  mov     r8, [rax+28h]
0x18004ab54  mov     rax, [rbp+57h+var_68]
0x18004ab58  mov     r8, [r8+18h]; pCertId2
0x18004ab5c  mov     rcx, [rax]
0x18004ab5f  mov     rdx, [rcx+28h]
0x18004ab63  mov     ecx, r12d; dwCertEncodingType
0x18004ab66  mov     rdx, [rdx+18h]; pCertId1
0x18004ab6a  call    cs:__imp_CertCompareCertificate
0x18004ab70  test    eax, eax
0x18004ab72  jnz     loc_18004AC2B
0x18004ab78  add     esi, r12d
0x18004ab7b  jmp     short loc_18004AB0F
0x18004ab7d  mov     rax, [rdi]
0x18004ab80  mov     dword ptr [rsp+110h+var_F0], 7
0x18004ab88  cmp     dword ptr [rax+14h], 0
0x18004ab8c  jz      short loc_18004AB94
0x18004ab8e  lea     rax, [rdi+10h]
0x18004ab92  jmp     short loc_18004AB97
0x18004ab94  mov     rax, [rax]
0x18004ab97  mov     r14d, 1004h
0x18004ab9d  mov     [rsp+110h+var_D8], rax
0x18004aba2  mov     edx, r14d; Msg
0x18004aba5  xor     r9d, r9d; lParam
0x18004aba8  xor     r8d, r8d; wParam
0x18004abab  mov     rcx, rbx; hWnd
0x18004abae  call    cs:__imp_SendMessageW
0x18004abb4  mov     dword ptr [rsp+110h+var_F0+4], eax
0x18004abb8  mov     rax, [rdi]
0x18004abbb  mov     [rsp+110h+var_E8], 0
0x18004abc3  cmp     dword ptr [rax+1Ch], 0
0x18004abc7  jnz     short loc_18004ABDC
0x18004abc9  cmp     dword ptr [rax+18h], 0
0x18004abcd  jnz     short loc_18004ABDC
0x18004abcf  cmp     dword ptr [rax+20h], 0
0x18004abd3  mov     [rbp+57h+var_CC], 0
0x18004abda  jnz     short loc_18004ABE0
0x18004abdc  mov     [rbp+57h+var_CC], r12d
0x18004abe0  lea     r9, [rsp+110h+var_F0]; lParam
0x18004abe5  mov     [rbp+57h+var_C8], rdi
0x18004abe9  xor     r8d, r8d; wParam
0x18004abec  mov     edx, 104Dh; Msg
0x18004abf1  mov     rcx, rbx; hWnd
0x18004abf4  call    cs:__imp_SendMessageW
0x18004abfa  xor     r9d, r9d; lParam
0x18004abfd  xor     r8d, r8d; wParam
0x18004ac00  mov     edx, r14d; Msg
0x18004ac03  mov     rcx, rbx; hWnd
0x18004ac06  mov     rsi, rax
0x18004ac09  call    cs:__imp_SendMessageW
0x18004ac0f  cmp     eax, r12d
0x18004ac12  jnz     short loc_18004AC18
0x18004ac14  xor     edx, edx
0x18004ac16  jmp     short loc_18004AC23
0x18004ac18  mov     rax, [rdi]
0x18004ac1b  cmp     dword ptr [rax+14h], 0
0x18004ac1f  jz      short loc_18004AC2B
0x18004ac21  mov     edx, esi; int
0x18004ac23  mov     rcx, rbx; hWnd
0x18004ac26  call    ?SetLVDefaultCert@@YAXPEAUHWND__@@H@Z; SetLVDefaultCert(HWND__ *,int)
0x18004ac2b  mov     rcx, rbx; hWnd
0x18004ac2e  call    cs:__imp_GetParent
0x18004ac34  mov     r9, r12; lParam
0x18004ac37  mov     r8, rbx; wParam
0x18004ac3a  mov     rcx, rax; hWnd
0x18004ac3d  mov     edx, 28h ; '('; Msg
0x18004ac42  call    cs:__imp_SendMessageW
0x18004ac48  mov     edx, esi; int
0x18004ac4a  mov     rcx, rbx; hWnd
0x18004ac4d  call    ?LVSelectItem@@YAXPEAUHWND__@@H@Z; LVSelectItem(HWND__ *,int)
0x18004ac52  mov     eax, r12d
0x18004ac55  add     rsp, 0E8h
0x18004ac5c  pop     r14
0x18004ac5e  pop     r12
0x18004ac60  pop     rdi
0x18004ac61  pop     rsi
0x18004ac62  pop     rbx
0x18004ac63  pop     rbp
0x18004ac64  retn
```
